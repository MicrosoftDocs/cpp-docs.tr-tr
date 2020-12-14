---
description: 'Daha fazla bilgi edinin: Izlenecek yol: C++ AMP bir uygulamada hata ayıklama'
title: 'İzlenecek yol: C++ AMP Uygulamasında Hata Ayıklama'
ms.date: 04/23/2019
helpviewer_keywords:
- debugging, C++ Accelerated Massive Parallelism
- C++ AMP, debugging
- C++ Accelerated Massive Parallelism, debugging
- debugging, C++ AMP
ms.assetid: 40e92ecc-f6ba-411c-960c-b3047b854fb5
ms.openlocfilehash: 77ae45b07967d92ba162e77dd8a9dccd696a1008
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97344919"
---
# <a name="walkthrough-debugging-a-c-amp-application"></a>İzlenecek yol: C++ AMP Uygulamasında Hata Ayıklama

Bu konu başlığı altında, grafik işleme birimi 'nden (GPU) yararlanmak için C++ Accelerated Massive Parallelism (C++ AMP) kullanan bir uygulamada hata ayıklama işleminin nasıl yapılacağı gösterilmektedir. Büyük bir tamsayı dizisini toplayan paralel azaltma programını kullanır. Bu izlenecek yol aşağıdaki görevleri gösterir:

- GPU hata ayıklayıcısı başlatılıyor.

- GPU iş parçacıkları penceresindeki GPU iş parçacıkları inceleniyor.

- Birden çok GPU iş parçacığının çağrı yığınlarını aynı anda gözlemlemek için **Paralel Yığınlar** penceresini kullanma.

- Aynı anda birden çok iş parçacığında tek bir ifadenin değerlerini incelemek için **paralel izleme** penceresini kullanma.

- GPU iş parçacıklarını bayrak, donduruyor, thakelebek ve gruplandırıyor.

- Bir kutucuğun tüm iş parçacıkları kodda belirli bir konuma yürütülüyor.

## <a name="prerequisites"></a>Önkoşullar

Bu izlenecek yolu başlatmak için:

- [C++ amp genel bakış](../../parallel/amp/cpp-amp-overview.md)konusunu okuyun.

- Satır numaralarının metin düzenleyicisinde görüntülendiğinden emin olun. Daha fazla bilgi için bkz. [nasıl yapılır: düzenleyicide satır numaralarını görüntüleme](/visualstudio/ide/reference/how-to-display-line-numbers-in-the-editor).

- Yazılım öykünücüsünde hata ayıklamayı desteklemek için en az Windows 8 veya Windows Server 2012 çalıştırdığınızdan emin olun.

[!INCLUDE[note_settings_general](../../mfc/includes/note_settings_general_md.md)]

### <a name="to-create-the-sample-project"></a>Örnek proje oluşturmak için

Proje oluşturmaya yönelik yönergeler, kullandığınız Visual Studio sürümüne bağlı olarak farklılık gösterir. Bu sayfanın sol üst kısmında doğru sürümün seçili olduğundan emin olun.

::: moniker range="msvc-160"

### <a name="to-create-the-sample-project-in-visual-studio-2019"></a>Visual Studio 2019 'de örnek proje oluşturmak için

1.  >  > **Yeni proje oluştur** iletişim kutusunu açmak için menü çubuğunda dosya yeni **Proje** ' yi seçin.

1. İletişim kutusunun üst kısmında,  **dili** **C++** olarak ayarlayın, **platformu** **Windows**'a ayarlayın ve **proje türünü** **konsol** olarak ayarlayın.

1. Filtre uygulanmış proje türleri listesinden **konsol uygulaması** ' nı seçin ve ardından **İleri**' yi seçin. Bir sonraki sayfada, `AMPMapReduce` proje için bir ad belirtmek üzere **ad** kutusuna girin ve isterseniz proje konumunu belirtin.

   ![Projeyi adlandırın](../../build/media/mathclient-project-name-2019.png "Projeyi adlandırın")

1. İstemci projesini oluşturmak için **Oluştur** düğmesini seçin.

::: moniker-end

::: moniker range="<=msvc-150"

### <a name="to-create-the-sample-project-in-visual-studio-2017-or-visual-studio-2015"></a>Visual Studio 2017 veya Visual Studio 2015 ' de örnek proje oluşturmak için

1. Visual Studio’yu çalıştırın.

1. Menü çubuğunda **Dosya** > **Yeni** > **Proje**' yi seçin.

1. Şablonlar bölmesinde **yüklü** altında **Visual C++**' yi seçin.

1. **Win32 konsol uygulaması**' nı seçin, `AMPMapReduce` **ad** kutusuna yazın ve **Tamam** düğmesini seçin.

1. **İleri** düğmesini seçin.

1. **Önceden derlenmiş üst bilgi** onay kutusunu temizleyin ve ardından **son** düğmesini seçin.

1. **Çözüm Gezgini**, *sthefx. h*, *targetver. h* ve *stdadfx. cpp* öğesini projeden silin.

::: moniker-end

İleri

1. AMPMapReduce. cpp ' i açın ve içeriğini aşağıdaki kodla değiştirin.

```cpp
    // AMPMapReduce.cpp defines the entry point for the program.
    // The program performs a parallel-sum reduction that computes the sum of an array of integers.

    #include <stdio.h>
    #include <tchar.h>
    #include <amp.h>

    const int BLOCK_DIM = 32;

    using namespace concurrency;

    void sum_kernel_tiled(tiled_index<BLOCK_DIM> t_idx, array<int, 1> &A, int stride_size) restrict(amp)
    {
        tile_static int localA[BLOCK_DIM];

        index<1> globalIdx = t_idx.global * stride_size;
        index<1> localIdx = t_idx.local;

        localA[localIdx[0]] =  A[globalIdx];

        t_idx.barrier.wait();

        // Aggregate all elements in one tile into the first element.
        for (int i = BLOCK_DIM / 2; i > 0; i /= 2)
        {
            if (localIdx[0] < i)
            {

                localA[localIdx[0]] += localA[localIdx[0] + i];
            }

            t_idx.barrier.wait();
        }

        if (localIdx[0] == 0)
        {
            A[globalIdx] = localA[0];
        }
    }

    int size_after_padding(int n)
    {
        // The extent might have to be slightly bigger than num_stride to
        // be evenly divisible by BLOCK_DIM. You can do this by padding with zeros.
        // The calculation to do this is BLOCK_DIM * ceil(n / BLOCK_DIM)
        return ((n - 1) / BLOCK_DIM + 1) * BLOCK_DIM;
    }

    int reduction_sum_gpu_kernel(array<int, 1> input)
    {
        int len = input.extent[0];

        //Tree-based reduction control that uses the CPU.
        for (int stride_size = 1; stride_size < len; stride_size *= BLOCK_DIM)
        {
            // Number of useful values in the array, given the current
            // stride size.
            int num_strides = len / stride_size;

            extent<1> e(size_after_padding(num_strides));

            // The sum kernel that uses the GPU.
            parallel_for_each(extent<1>(e).tile<BLOCK_DIM>(), [&input, stride_size] (tiled_index<BLOCK_DIM> idx) restrict(amp)
            {
                sum_kernel_tiled(idx, input, stride_size);
            });
        }

        array_view<int, 1> output = input.section(extent<1>(1));
        return output[0];
    }

    int cpu_sum(const std::vector<int> &arr) {
        int sum = 0;
        for (size_t i = 0; i < arr.size(); i++) {
            sum += arr[i];
        }
        return sum;
    }

    std::vector<int> rand_vector(unsigned int size) {
        srand(2011);

        std::vector<int> vec(size);
        for (size_t i = 0; i < size; i++) {
            vec[i] = rand();
        }
        return vec;
    }

    array<int, 1> vector_to_array(const std::vector<int> &vec) {
        array<int, 1> arr(vec.size());
        copy(vec.begin(), vec.end(), arr);
        return arr;
    }

    int _tmain(int argc, _TCHAR* argv[])
    {
        std::vector<int> vec = rand_vector(10000);
        array<int, 1> arr = vector_to_array(vec);

        int expected = cpu_sum(vec);
        int actual = reduction_sum_gpu_kernel(arr);

        bool passed = (expected == actual);
        if (!passed) {
            printf("Actual (GPU): %d, Expected (CPU): %d", actual, expected);
        }
        printf("sum: %s\n", passed  "Passed!" : "Failed!");

        getchar();

        return 0;
    }
```

1. Menü çubuğunda **Dosya**  >  **Tümünü Kaydet**' i seçin.

1. **Çözüm Gezgini**, **AMPMapReduce** kısayol menüsünü açın ve ardından **Özellikler**' i seçin.

1. **Özellik sayfaları** iletişim kutusunda, **yapılandırma özellikleri** altında **C/C++**  >  **önceden derlenmiş üst bilgiler**' i seçin.

1. **Önceden derlenmiş üst bilgi** özelliği Için, **önceden derlenmiş üst bilgiler kullanmayan**' ı seçin ve ardından **Tamam** düğmesini seçin.

1. Menü **çubuğunda Build**  >  **Build Solution** öğesini seçin.

## <a name="debugging-the-cpu-code"></a>CPU kodunda hata ayıklama

Bu yordamda, bu uygulamadaki CPU kodunun doğru olduğundan emin olmak için yerel Windows hata ayıklayıcısı ' nı kullanacaksınız. Bu uygulamadaki CPU kodu segmenti, **`for`** işlev içindeki döngüdür `reduction_sum_gpu_kernel` . GPU üzerinde çalıştırılan ağaç tabanlı paralel küçültmeye göre kontrol eder.

### <a name="to-debug-the-cpu-code"></a>CPU kodunda hata ayıklamak için

1. **Çözüm Gezgini**, **AMPMapReduce** kısayol menüsünü açın ve ardından **Özellikler**' i seçin.

2. **Özellik sayfaları** iletişim kutusunda, **yapılandırma özellikleri** altında **hata ayıklama**' yı seçin. **Başlatmak Için hata ayıklayıcı** 'Da **yerel Windows hata ayıklayıcısı** ' nın seçildiğini doğrulayın.

3. **Kod düzenleyicisine** geri dönün.

4. Aşağıdaki çizimde gösterilen kod satırlarında kesme noktaları ayarlayın (yaklaşık satırlar 67 satır 70).

   ![CPU kesme noktaları](../../parallel/amp/media/campcpubreakpoints.png "CPU kesme noktaları") <br/>
   CPU kesme noktaları

5. Menü çubuğunda **hata**  >  **ayıklamayı Başlat hata** Ayıkla ' yı seçin.

6. **Yereller** penceresinde, `stride_size` 70 satırındaki kesme noktasına ulaşılana kadar değerini gözlemleyin.

7. Menü çubuğunda **hata**  >  **ayıklamayı Durdur hata** Ayıkla ' yı seçin.

## <a name="debugging-the-gpu-code"></a>GPU kodunda hata ayıklama

Bu bölümde, işlevinde bulunan kod olan GPU kodunda hata ayıklama işlemi gösterilmektedir `sum_kernel_tiled` . GPU kodu, her "blok" için tamsayıların toplamını paralel olarak hesaplar.

### <a name="to-debug-the-gpu-code"></a>GPU kodunda hata ayıklamak için

1. **Çözüm Gezgini**, **AMPMapReduce** kısayol menüsünü açın ve ardından **Özellikler**' i seçin.

2. **Özellik sayfaları** iletişim kutusunda, **yapılandırma özellikleri** altında **hata ayıklama**' yı seçin.

3. **Başlatmak Için hata ayıklayıcı** listesinde, **yerel Windows hata ayıklayıcısı**' nı seçin.

4. **Hata ayıklayıcı tür** listesinde, **Auto** seçeneğinin seçildiğini doğrulayın.

    **Auto** varsayılan değerdir. Windows 10 ' dan önce, **GPU yalnızca** **Otomatik** yerine gerekli değerdir.

5. **Tamam** düğmesini seçin.

6. Aşağıdaki çizimde gösterildiği gibi, 30. satırda bir kesme noktası ayarlayın.

   ![GPU kesme noktaları](../../parallel/amp/media/campgpubreakpoints.png "GPU kesme noktaları") <br/>
   GPU kesme noktası

7. Menü çubuğunda **hata**  >  **ayıklamayı Başlat hata** Ayıkla ' yı seçin. 67 ve 70 satırlarındaki CPU kodundaki kesme noktaları, bu kod satırları CPU üzerinde yürütüldüğü için GPU hata ayıklaması sırasında yürütülmez.

### <a name="to-use-the-gpu-threads-window"></a>GPU Iş parçacıkları penceresini kullanmak için

1. **GPU iş parçacıkları** penceresini açmak için, menü çubuğunda   >  **Windows**  >  **GPU iş parçacıkları** Hata Ayıkla ' yı seçin.

   GPU iş parçacıklarının durumunu, görüntülenen **GPU Iş parçacıkları** penceresinde inceleyebilirsiniz.

2. Visual Studio 'nun altındaki **GPU Iş parçacıkları** penceresini yerleştirin. Kutucuğu ve iş parçacığı metin kutularını göstermek için **Iş parçacığı anahtarını Genişlet** düğmesini seçin. **GPU Iş parçacıkları** penceresi, aşağıdaki çizimde gösterildiği gibi, etkin ve engellenen GPU iş parçacıklarının toplam sayısını gösterir.

   ![4 etkin iş parçacığı ile GPU Iş parçacıkları penceresi](../../parallel/amp/media/campc.png "4 etkin iş parçacığı ile GPU Iş parçacıkları penceresi") <br/>
   GPU Iş parçacıkları penceresi

   Bu hesaplama için ayrılan 313 kutucuk vardır. Her kutucuk 32 iş parçacığı içerir. Yerel GPU hata ayıklama bir yazılım öykünücüsünde gerçekleştiği için dört etkin GPU iş parçacığı vardır. Dört iş parçacığı yönergeleri eşzamanlı olarak yürütür ve sonraki yönergeyle birlikte hareket ettirin.

   **GPU Iş parçacıkları** penceresinde, ETKIN dört GPU iş parçacığı vardır ve [tile_barrier:: wait](reference/tile-barrier-class.md#wait) ifadesinde, 21. satır hakkında ' da tanımlanan 28 GPU iş parçacığı vardır `t_idx.barrier.wait();` . Tüm 32 GPU iş parçacıkları ilk kutucuğa aittir `tile[0]` . Bir ok, geçerli iş parçacığını içeren satıra işaret eder. Farklı bir iş parçacığına geçiş yapmak için aşağıdaki yöntemlerden birini kullanın:

    - **GPU Iş parçacıkları** penceresinde geçiş yapılacak iş parçacığının satırında, kısayol menüsünü açın ve **iş parçacığına geç**' i seçin. Satır birden fazla iş parçacığını temsil ediyorsa, iş parçacığı koordinatlarına göre ilk iş parçacığına geçiş yapmanız gerekir.

    - İş parçacığının kutucuğunu ve iş parçacığı değerlerini ilgili metin kutularına girip **Iş parçacığı Değiştir** düğmesini seçin.

   **Çağrı yığını** penceresi, geçerli GPU iş parçacığının çağrı yığınını görüntüler.

### <a name="to-use-the-parallel-stacks-window"></a>Paralel Yığınlar penceresini kullanmak için

1. **Paralel Yığınlar** penceresini açmak için, menü çubuğunda   >  **Windows**  >  **paralel yığınları** Hata Ayıkla ' yı seçin.

   Birden çok GPU iş parçacığının yığın çerçevelerini aynı anda incelemek için **Paralel Yığınlar** penceresini kullanabilirsiniz.

2. Visual Studio 'nun altındaki **Paralel Yığınlar** penceresini yerleştirin.

3. Sol üst köşedeki listede **Iş parçacıklarının** seçili olduğundan emin olun. Aşağıdaki çizimde, **Paralel Yığınlar** penceresi, **GPU iş PARÇACıKLARı** penceresinde gördüğünüz GPU iş parçacıklarının çağrı yığınına odaklanmış bir görünümünü gösterir.

   ![4 etkin iş parçacığından oluşan Paralel Yığınlar penceresi](../../parallel/amp/media/campd.png "4 etkin iş parçacığından oluşan Paralel Yığınlar penceresi") <br/>
   Paralel Yığınlar penceresi

   32 iş parçacığı, `_kernel_stub` `parallel_for_each` işlev çağrısındaki lambda ifadesine ve ardından `sum_kernel_tiled` işlevine, paralel azaltmanın gerçekleştiği yere gitti. 32 iş parçacığından 28 tanesi [tile_barrier:: wait](reference/tile-barrier-class.md#wait) ifadesine ilerlemedi ve 22. satırda engellenmiş durumda kalır, ancak diğer 4 iş parçacıkları ise `sum_kernel_tiled` 30. satırdaki etkin kalır.

   **Paralel Yığınlar** penceresinin zengin veri Ipucunda **GPU iş parçacıkları** PENCERESINDE kullanılabilir olan bir GPU iş parçacığının özelliklerini inceleyebilirsiniz. Bunu yapmak için fare işaretçisini **sum_kernel_tiled** yığın çerçevesinde bekletin. Aşağıdaki çizimde Datatıp gösterilmektedir.

   ![Paralel Yığınlar penceresi için Datatıp](../../parallel/amp/media/campe.png "Paralel Yığınlar penceresi için Datatıp") <br/>
   GPU iş parçacığı veri Ipucu

   **Paralel Yığınlar** penceresi hakkında daha fazla bilgi için bkz. [Paralel Yığınlar penceresini kullanma](/visualstudio/debugger/using-the-parallel-stacks-window).

### <a name="to-use-the-parallel-watch-window"></a>Paralel izleme penceresi kullanmak için

1. **Paralel izleme** penceresini açmak için, menü çubuğunda **Hata Ayıkla**  >  **Windows**  >  **paralel izleme**  >  **paralel izleme 1**' i seçin.

   Birden çok iş parçacığı içindeki bir ifadenin değerlerini incelemek için **paralel izleme** penceresini kullanabilirsiniz.

2. **Paralel izleme 1** penceresini Visual Studio 'nun en altına yerleştirin. **Paralel izleme** penceresi tablosunda 32 satır vardır. Her biri, hem GPU Iş parçacıkları penceresinde hem de **Paralel Yığınlar** penceresinde görünen bir GPU iş parçacığına karşılık gelir. Şimdi, değerlerini tüm 32 GPU iş parçacıkları genelinde incelemek istediğiniz ifadeleri girebilirsiniz.

3. **Gözcü Ekle** sütun başlığını seçin, girin `localIdx` ve **ENTER** tuşunu seçin.

4. **Gözcü Ekle** sütun başlığını tekrar seçin, yazın `globalIdx` ve **ENTER** tuşunu seçin.

5. **Gözcü Ekle** sütun başlığını tekrar seçin, yazın `localA[localIdx[0]]` ve **ENTER** tuşunu seçin.

   Karşılık gelen sütun başlığını seçerek belirtilen ifadeye göre sıralama yapabilirsiniz.

   Sütunu sıralamak için **localA [localIdx [0]]** sütun başlığını seçin. Aşağıdaki çizimde, **localA [localIdx [0]]** tarafından sıralamanın sonuçları gösterilmektedir.

   ![Sıralanmış sonuçlarla paralel izleme penceresi](../../parallel/amp/media/campf.png "Sıralanmış sonuçlarla paralel izleme penceresi") <br/>
   Sıralama sonuçları

   **Excel düğmesini seçip** **Excel 'de aç**' ı seçerek **paralel izleme** penceresindeki içeriği Excel 'e aktarabilirsiniz. Geliştirme bilgisayarınızda Excel yüklüyse, içerik içeren bir Excel çalışma sayfası açılır.

6. **Paralel izleme** penceresinin sağ üst köşesinde, Boole ifadeleri kullanarak içeriği filtrelemek için kullanabileceğiniz bir filtre denetimi vardır. `localA[localIdx[0]] > 20000`Filtre denetimi metin kutusuna girin ve **ENTER** tuşunu seçin.

   Pencerede artık yalnızca değerin 20000 ' den büyük olduğu iş parçacıkları bulunur `localA[localIdx[0]]` . İçerik hala `localA[localIdx[0]]` , daha önce gerçekleştirdiğiniz sıralama eylemi olan sütuna göre sıralanır.

## <a name="flagging-gpu-threads"></a>GPU Iş parçacıklarını bayrakla işaretlemeyi

Belirli GPU iş parçacıklarını **GPU Iş parçacıkları** penceresinde, **paralel Izleme** penceresinde veya **Paralel Yığınlar** penceresindeki datatıp işaretine göre Bayrakla işaretleyebilirsiniz. GPU Iş parçacıkları penceresindeki bir satır birden fazla iş parçacığı içeriyorsa, bu satırın satırda yer alan tüm iş parçacıklarını bayrak olarak işaretler.

### <a name="to-flag-gpu-threads"></a>GPU iş parçacıklarını işaretlemek için

1. Kutucuk dizinine ve iş parçacığı dizinine göre sıralamak için **paralel izleme 1** penceresindeki **[thread]** sütun başlığını seçin.

2. Menü çubuğunda **Hata Ayıkla**  >  **devam et**' i seçin. Bu, etkin olan dört iş parçacığının sonraki engelte ilerlemesini sağlar (32. gün: AMPMapReduce. cpp ' de tanımlanır).

3. Artık etkin olan dört iş parçacığını içeren satırın sol tarafındaki bayrak sembolünü seçin.

   Aşağıdaki çizimde, **GPU Iş parçacıkları** penceresinde dört etkin bayraklı iş parçacığı gösterilmektedir.

   ![Bayraklı iş parçacıkları ile GPU Iş parçacıkları penceresi](../../parallel/amp/media/campg.png "Bayraklı iş parçacıkları ile GPU Iş parçacıkları penceresi") <br/>
   GPU Iş parçacıkları penceresindeki etkin iş parçacıkları

   Paralel  Yığınlar penceresi ve paralel **yığınlar** penceresinin datatıp her ikisi de bayraklı iş parçacıklarını gösterir.

4. İşaretlediğiniz dört iş parçacığına odaklanmak isterseniz, **GPU Iş parçacıkları**, **paralel Izleme** ve **Paralel Yığınlar** penceresinde, yalnızca bayraklı iş parçacıklarında göstermeyi tercih edebilirsiniz.

   Herhangi bir Windows veya **hata ayıklama konumu** araç çubuğunda **bayraklı yalnızca bayrak göster** düğmesini seçin. Aşağıdaki çizimde **hata ayıklama konumu** araç çubuğunda **yalnızca bayraklı göster** düğmesi gösterilmektedir.

   ![Yalnızca Işaretli bayraklı simgesiyle hata ayıklama konumu araç çubuğu](../../parallel/amp/media/camph.png "Yalnızca Işaretli bayraklı simgesiyle hata ayıklama konumu araç çubuğu") <br/>
   **Yalnızca bayraklı düğmeyi göster**

   Artık **GPU Iş parçacıkları**, **paralel Izleme** ve **Paralel Yığınlar** Windows yalnızca bayraklı iş parçacıklarını görüntüler.

## <a name="freezing-and-thawing-gpu-threads"></a>GPU Iş parçacıklarını dondurma ve çözülmüş

GPU iş parçacıklarını, **GPU Iş parçacıkları** penceresinden ya da **paralel izleme** penceresinden dondurabilir (askıya alabilir) ve çözme (devam ettirebilirsiniz). CPU iş parçacıklarını aynı şekilde dondurabilir ve çözme yapabilirsiniz; bilgi için bkz. [nasıl yapılır: Iş parçacıkları penceresini kullanma](/visualstudio/debugger/how-to-use-the-threads-window).

### <a name="to-freeze-and-thaw-gpu-threads"></a>GPU iş parçacıklarını dondurmak ve çözme

1. Tüm iş parçacıklarını görüntülemek için, **yalnızca bayraklı göster** düğmesini seçin.

2. Menü çubuğunda **Hata Ayıkla**  >  **devam et**' i seçin.

3. Etkin satır için kısayol menüsünü açın ve ardından **dondurma**' yı seçin.

   **GPU Iş parçacıkları** penceresi aşağıdaki şekilde tüm dört iş parçacıklarının dondurulmuş olduğunu gösterir.

   ![Dondurulmuş iş parçacıklarını gösteren GPU Iş parçacıkları penceresi](../../parallel/amp/media/campk.png "Dondurulmuş iş parçacıklarını gösteren GPU Iş parçacıkları penceresi") <br/>
   **GPU Iş parçacıkları** penceresindeki dondurulmuş iş parçacıkları

   Benzer şekilde, **paralel izleme** penceresi tüm dört iş parçacıklarının dondurulmuş olduğunu gösterir.

4.   >  Sonraki dört GPU iş parçacığının 22. satırdaki engelden sonra ilerlemesini ve 30. satırdaki kesme noktasına ulaşmasını **sağlamak için menü** çubuğunda Hata Ayıkla ' yı seçin. **GPU Iş parçacıkları** penceresi, daha önce dondurulmuş olan dört iş parçacığının dondurulmuş olduğunu ve etkin durumda kaldığını gösterir.

5. Menü çubuğunda **Hata Ayıkla**, **devam et**' i seçin.

6. **Paralel izleme** penceresinde, tek veya bırden çok GPU iş parçacığını çöz de yapabilirsiniz.

### <a name="to-group-gpu-threads"></a>GPU iş parçacıklarını gruplandırmak için

1. **GPU Iş parçacıkları** penceresindeki iş parçacıklarından birinin kısayol menüsünde **grupla**' yı, **Adres**' i seçin.

   **GPU Iş parçacıkları** penceresindeki iş parçacıkları adrese göre gruplandırılır. Adres, her iş parçacığı grubunun bulunduğu ayrıştırılmış derleme içindeki yönergeye karşılık gelir. 24 iş parçacığı 22. satırdaki [tile_barrier:: wait yöntemi](reference/tile-barrier-class.md#wait) yürütülür. 12 iş parçacığı, 32. satırdaki engelin yönergesidir. Bu iş parçacıklarından dördü işaretlenir. Sekiz iş parçacığı, 30. satırdaki kesme noktasında bulunur. Bu iş parçacıklarının dördü dondurulur. Aşağıdaki çizimde, **GPU Iş parçacıkları** penceresindeki gruplanmış iş parçacıkları gösterilmektedir.

   ![Adrese göre gruplandırılmış iş parçacıkları ile GPU Iş parçacıkları penceresi](../../parallel/amp/media/campl.png "Adrese göre gruplandırılmış iş parçacıkları ile GPU Iş parçacıkları penceresi") <br/>
   **GPU Iş parçacıkları** penceresinde gruplanmış iş parçacıkları

2. Ayrıca, **paralel izleme** penceresinin veri kılavuzu için kısayol menüsünü açarak Group **by**' ı seçerek ve sonra iş parçacıklarını nasıl gruplandırmak istediğinize karşılık gelen menü öğesini seçerek **Group By** işlemini gerçekleştirebilirsiniz.

## <a name="running-all-threads-to-a-specific-location-in-code"></a>Tüm Iş parçacıklarını kodda belirli bir konuma çalıştırma

Belirli bir kutucukta yer alan tüm iş parçacıklarını, imlecin bulunduğu **geçerli kutucuğu** kullanarak imleci içeren satıra çalıştırırsınız.

### <a name="to-run-all-threads-to-the-location-marked-by-the-cursor"></a>Tüm iş parçacıklarını imleç tarafından işaretlenen konuma çalıştırmak için

1. Dondurulmuş iş parçacıklarının kısayol menüsünde **çözme**' yi seçin.

2. **Kod düzenleyicisinde** imleci 30. satıra yerleştirin.

3. **Kod Düzenleyicisi** için kısayol menüsünde, **geçerli kutucuğu imlece Çalıştır**' ı seçin.

   21. satırdaki engelde daha önce engellenen 24 iş parçacığı 32. satıra ilerlemedi. Bu, **GPU Iş parçacıkları** penceresinde gösterilir.

## <a name="see-also"></a>Ayrıca bkz.

[C++ AMP genel bakış](../../parallel/amp/cpp-amp-overview.md)<br/>
[GPU Kodunda Hata Ayıklama](/visualstudio/debugger/debugging-gpu-code)<br/>
[Nasıl yapılır: GPU Iş parçacıkları penceresini kullanma](/visualstudio/debugger/how-to-use-the-gpu-threads-window)<br/>
[Nasıl yapılır: paralel Izleme penceresini kullanma](/visualstudio/debugger/how-to-use-the-parallel-watch-window)<br/>
[Eşzamanlılık görselleştiricisi ile C++ AMP kodu analiz etme](/archive/blogs/nativeconcurrency/analyzing-c-amp-code-with-the-concurrency-visualizer)
