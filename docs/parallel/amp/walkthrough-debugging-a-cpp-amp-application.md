---
title: 'İzlenecek yol: C++ AMP uygulamasında hata ayıklama'
ms.date: 04/23/2019
helpviewer_keywords:
- debugging, C++ Accelerated Massive Parallelism
- C++ AMP, debugging
- C++ Accelerated Massive Parallelism, debugging
- debugging, C++ AMP
ms.assetid: 40e92ecc-f6ba-411c-960c-b3047b854fb5
ms.openlocfilehash: 3f358f66d1e8a64c5042b60d7385de26a559642e
ms.sourcegitcommit: 18d3b1e9cdb4fc3a76f7a650c31994bdbd2bde64
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/29/2019
ms.locfileid: "64877541"
---
# <a name="walkthrough-debugging-a-c-amp-application"></a>İzlenecek yol: C++ AMP uygulamasında hata ayıklama

Bu konuda, grafik işlemci birimi (GPU) yararlanmak için C++ Accelerated Massive Parallelism (C++ AMP) kullanan bir uygulamanın hatalarını ayıklamak gösterilmektedir. Bu, büyük bir tamsayı dizisi toplayan bir paralel azaltma program kullanır. Bu izlenecek yol aşağıdaki görevleri gösterir:

- GPU hata ayıklayıcısı başlatılıyor.

- GPU iş parçacıkları GPU iş parçacıkları penceresinde inceleniyor.

- Kullanarak **Paralel Yığınlar** penceresi aynı anda birden çok GPU iş parçacığı çağrı yığınlarını gözlemleyin.

- Kullanarak **paralel izleme** tek bir ifadedeki değerlerin aynı anda birden çok iş parçacığı arasında incelemek için penceresi.

- İşaretleme, dondurma, çözme ve GPU iş parçacıkları gruplandırma.

- Belirli bir konuma bir kutucuğun tüm iş parçacıkları, kod yürütülüyor.

## <a name="prerequisites"></a>Önkoşullar

Bu kılavuza başlamadan önce:

- Okuma [C++ AMP'ye genel bakış](../../parallel/amp/cpp-amp-overview.md).

- Bu satırı emin olun. sayılar, Metin Düzenleyicisi'nde görüntülenir. Daha fazla bilgi için [nasıl yapılır: Düzenleyicide satır numaralarını görüntüleme](/visualstudio/ide/reference/how-to-display-line-numbers-in-the-editor).

- En az çalıştırdığınızdan emin olun Windows 8 veya Windows Server 2012 yazılım benzetmesi üzerinde hata ayıklamayı desteklemek için. 

[!INCLUDE[note_settings_general](../../mfc/includes/note_settings_general_md.md)]

### <a name="to-create-the-sample-project"></a>Örnek proje oluşturmak için

Bir proje oluşturmak için yönergeler, kullandığınız Visual Studio'nun hangi sürümünün bağlı olarak değişir. Bu sayfanın üst sol seçili doğru sürüm olduğundan emin olun.

::: moniker range="vs-2019"

### <a name="to-create-the-sample-project-in-visual-studio-2019"></a>Örnek Proje içinde Visual Studio 2019 oluşturmak için

1. Menü çubuğunda, **dosya** > **yeni** > **proje** açmak için **yeni bir proje oluşturma** iletişim kutusu.

1. İletişim kutusunun üstündeki ayarlamak **dil** için **C++** ayarlayın **Platform** için **Windows**, ayarlayıp **proje türü** için **konsol**. 

1. Filtrelenmiş proje türleri listesinden seçim **konsol uygulaması** ardından **sonraki**. Sonraki sayfaya girin `AMPMapReduce` içinde **adı** kutusuna proje için bir ad belirtmek için ve istenen proje konumu belirtin.

   ![Projeyi adlandırın](../../build/media/mathclient-project-name-2019.png "projesini adlandırın")

1. Seçin **Oluştur** istemci projesi oluşturmak için.

::: moniker-end

::: moniker range="<=vs-2017"

### <a name="to-create-the-sample-project-in-visual-studio-2017-or-visual-studio-2015"></a>Visual Studio 2017 veya Visual Studio 2015'te örnek proje oluşturmak için

1. Visual Studio’yu çalıştırın.

2. Menü çubuğunda, **dosya** > **yeni** > **proje**.

3. Altında **yüklü** Şablonlar bölmesinde seçin **Visual C++**.

4. Seçin **Win32 konsol uygulaması**, türü `AMPMapReduce` içinde **adı** kutusuna ve ardından **Tamam** düğmesi.

5. Seçin **sonraki** düğmesi.

6. NET **önceden derlenmiş üst bilgi** onay kutusunu işaretleyin ve ardından **son** düğmesi.

7. İçinde **Çözüm Gezgini**, stdafx.h targetver.h ve stdafx.cpp projeden Sil.

::: moniker-end


8. AMPMapReduce.cpp açın ve içeriğini aşağıdaki kodla değiştirin.

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

9. Menü çubuğunda, **dosya** > **Tümünü Kaydet**.

10. İçinde **Çözüm Gezgini**, kısayol menüsünü açın **AMPMapReduce**ve ardından **özellikleri**.

11. İçinde **özellik sayfaları** iletişim kutusunun **yapılandırma özellikleri**, seçin **C/C++** > **önceden derlenmiş üst bilgiler**.

12. İçin **önceden derlenmiş üst bilgi** özelliği, select **kullanarak önceden derlenmiş üstbilgi**ve ardından **Tamam** düğmesi.

13. Menü çubuğunda, **derleme** > **Çözümü Derle**.

## <a name="debugging-the-cpu-code"></a>CPU kodda hata ayıklama

Bu yordamda, yerel Windows hata ayıklayıcı Bu uygulamadaki CPU kodu doğru olduğundan emin olmak için kullanın. Özellikle ilgi çekici Bu uygulamadaki CPU kod kesimi `for` içinde döngü `reduction_sum_gpu_kernel` işlevi. Da ağaç tabanlı ve GPU üzerinde çalıştırılan paralel azaltma denetler.

### <a name="to-debug-the-cpu-code"></a>CPU kodda hata ayıklamak için

1. İçinde **Çözüm Gezgini**, kısayol menüsünü açın **AMPMapReduce**ve ardından **özellikleri**.

2. İçinde **özellik sayfaları** iletişim kutusunun **yapılandırma özellikleri**, seçin **hata ayıklama**. Doğrulayın **yerel Windows hata ayıklayıcı** seçili **başlatmak için hata ayıklayıcı** listesi.

3. Geri dönüp **Kod Düzenleyicisi**.

4. (Yaklaşık satırları 67 satır 70) aşağıdaki çizimde gösterilen kod satırlarını üzerinde kesme noktaları ayarlayın.

   ![CPU kesme noktaları](../../parallel/amp/media/campcpubreakpoints.png "CPU kesme noktaları") <br/>
   CPU kesme noktaları

5. Menü çubuğunda, **hata ayıklama** > **hata ayıklamayı Başlat**.

6. İçinde **Yereller** penceresinde değeri gözlemleyin `stride_size` 70 satırında bir kesme noktası ulaşılana kadar.

7. Menü çubuğunda, **hata ayıklama** > **hata ayıklamayı Durdur**.

## <a name="debugging-the-gpu-code"></a>GPU kodunda hata ayıklama

Bu bölümde yer alan kod GPU kodunda hata ayıklama işlemini gösterir, `sum_kernel_tiled` işlevi. GPU kodunda paralel olarak her "blok" için tam sayının toplamını hesaplar.

### <a name="to-debug-the-gpu-code"></a>GPU kodunda hata ayıklamak için

1. İçinde **Çözüm Gezgini**, kısayol menüsünü açın **AMPMapReduce**ve ardından **özellikleri**.

2. İçinde **özellik sayfaları** iletişim kutusunun **yapılandırma özellikleri**, seçin **hata ayıklama**.

3. İçinde **başlatmak için hata ayıklayıcı** listesinden **yerel Windows hata ayıklayıcı**.

4. İçinde **hata ayıklayıcı türü** listesinde, doğrulayın **otomatik** seçilir.

    **Otomatik** varsayılan değerdir. Windows 10 önce **yalnızca GPU** yerine gerekli bir değerdir **otomatik**.

5. Seçin **Tamam** düğmesi.

6. Bir kesme noktası 30 satırında aşağıdaki çizimde gösterildiği gibi ayarlayın.

   ![GPU kesme noktaları](../../parallel/amp/media/campgpubreakpoints.png "GPU kesme noktaları") <br/>
   GPU kesme noktası

7. Menü çubuğunda, **hata ayıklama** > **hata ayıklamayı Başlat**. GPU Bu kod satırlarını CPU üzerinde yürütülen çünkü hata ayıklama sırasında CPU kod satırlarındaki 67 ve 70 kesme noktaları yürütülmez.

### <a name="to-use-the-gpu-threads-window"></a>GPU iş parçacıkları penceresini kullanmak için

1. Açmak için **GPU iş parçacıkları** menü çubuğunda, pencere **hata ayıklama** > **Windows** > **GPU iş parçacıkları**.

   GPU iş parçacıkları, durumu inceleyebilirsiniz **GPU iş parçacıkları** görüntülenen penceresi.

2. Dock **GPU iş parçacıkları** penceresinin Visual Studio'nun altındaki. Seçin **genişletin iş parçacığı anahtarı** kutucuğu ve iş parçacığı metin kutularını görüntülemek için düğmeyi. **GPU iş parçacıkları** penceresi, aşağıdaki çizimde gösterildiği gibi GPU iş parçacıkları, etkin ve engellenen toplam sayısını gösterir.

   ![GPU iş parçacıkları penceresi 4 etkin iş parçacığı sayısı ile](../../parallel/amp/media/campc.png "4 etkin iş parçacığı sayısı ile GPU iş parçacıkları penceresi") <br/>
   GPU iş parçacıkları penceresi

   Bu işlem için ayrılan 313 kutucukları vardır. Her kutucuk, 32 iş parçacığı içerir. Bir yazılım öykünücüsü üzerinde GPU yerel hata ayıklama oluştuğu için dört etkin GPU iş parçacıkları vardır. Dört iş parçacığı yönergeleri aynı anda yürütmek ve sonra birlikte sonraki yönergeyi geçin.

   İçinde **GPU iş parçacıkları** penceresinde dört GPU iş parçacıkları etkin ve 28 GPU iş parçacığı engellendi [tile_barrier::wait](reference/tile-barrier-class.md#wait) satır 21 tanımlanan deyimi (`t_idx.barrier.wait();`). Tüm 32 GPU iş parçacıkları ilk kutucuğa ait `tile[0]`. Bir ok, geçerli iş parçacığı içeren satırı işaret eder. Farklı bir iş parçacığına geçiş yapmak için aşağıdaki yöntemlerden birini kullanın:

    - İş parçacığı için geçmek için sıradaki **GPU iş parçacıkları** penceresinde, kısayol menüsünü açın ve seçin **iş parçacığının geçiş**. Birden fazla iş parçacığının satır temsil ediyorsa, iş parçacığı koordinatlarına göre ilk iş parçacığına geçiş yapar.

    - İlgili metin kutularına iş parçacığının döşeme ve iş parçacığı değerleri girin ve ardından **anahtar iş parçacığı** düğmesi.

   **Çağrı yığını** geçerli GPU iş parçacığı çağrı yığını penceresinde görüntülenir.

### <a name="to-use-the-parallel-stacks-window"></a>Paralel Yığınlar penceresini kullanmak için

1. Açmak için **Paralel Yığınlar** menü çubuğunda, pencere **hata ayıklama** > **Windows** > **Paralel Yığınlar**.

   Kullanabileceğiniz **Paralel Yığınlar** aynı anda birden çok GPU iş parçacığı yığın çerçevelerini incelemek için penceresi.

2. Dock **Paralel Yığınlar** penceresinin Visual Studio'nun altındaki.

3. Emin olun **iş parçacıkları** listenin sol üst köşedeki seçilir. Aşağıdaki çizimde, **Paralel Yığınlar** penceresi gördüğünüz GPU iş parçacıkları çağrı yığını odaklanmış bir görünümünü gösterir **GPU iş parçacıkları** penceresi.

   ![Paralel Yığınlar penceresini 4 etkin iş parçacığı sayısı ile](../../parallel/amp/media/campd.png "4 etkin iş parçacığı sayısı ile Paralel Yığınlar penceresi") <br/>
   Paralel Yığınlar penceresi

   32 iş parçacığı oluştu gelen `_kernel_stub` lambda ifadesine `parallel_for_each` işlev çağrısı ve sonra `sum_kernel_tiled` paralel azaltma oluştuğu işlevi. 28 32 iş parçacığı dışında için progressed [tile_barrier::wait](reference/tile-barrier-class.md#wait) deyimi ve diğer 4 iş parçacıklarını etkin ise satır 22'yi engellenen kalır `sum_kernel_tiled` satırı 30 işlevi.

   Kullanılabilen bir GPU iş parçacığı özelliklerini inceleyebilirsiniz **GPU iş parçacıkları** penceresi zengin DataTip içinde **Paralel Yığınlar** penceresi. Bunu yapmak için fare işaretçisini yığın çerçevesi rest **sum_kernel_tiled**. DataTip aşağıda gösterilmiştir.

   ![Paralel Yığınlar penceresi için DataTip](../../parallel/amp/media/campe.png "DataTip Paralel Yığınlar penceresi") <br/>
   GPU iş parçacığı DataTip

   Hakkında daha fazla bilgi için **Paralel Yığınlar** penceresinde görmek [Paralel Yığınlar penceresini kullanma](/visualstudio/debugger/using-the-parallel-stacks-window).

### <a name="to-use-the-parallel-watch-window"></a>Paralel İzleme penceresini kullanmak için

1. Açmak için **paralel izleme** menü çubuğunda, pencere **hata ayıklama** > **Windows** > **paralel izleme**  >  **Paralel izleme 1**.

   Kullanabileceğiniz **paralel izleme** birden çok iş parçacığı arasında ifade değerlerini incelemek için penceresi.

2. Dock **paralel Watch 1** Visual Studio altına penceresi. Tablosunda 32 satırlar var. **paralel izleme** penceresi. Her iki GPU iş parçacıkları penceresinde görünen bir GPU iş parçacığı karşılık gelir ve **Paralel Yığınlar** penceresi. Artık, değerleri tüm 32 GPU iş parçacıkları arasında incelemek istediğiniz ifadeler girebilirsiniz.

3. Seçin **Gözcü Ekle** sütun başlığını girin `localIdx`ve ardından **Enter** anahtarı.

4. Seçin **Gözcü Ekle** sütun başlığını tekrar, türü `globalIdx`ve ardından **Enter** anahtarı.

5. Seçin **Gözcü Ekle** sütun başlığını tekrar, türü `localA[localIdx[0]]`ve ardından **Enter** anahtarı.

   Karşılık gelen sütun başlığını seçerek belirtilen ifadeye göre sıralama yapabilirsiniz.

   Seçin **localA [localIdx [0]]** sütunu sıralamak için sütun üst bilgisi. Sıralama sonuçları aşağıdaki çizimde **localA [localIdx [0]]**.

   ![Paralel İzleme penceresi sıralanmış sonuçları](../../parallel/amp/media/campf.png "sıralanmış sonuçları ile paralel İzleme penceresi") <br/>
   Sonuçları sıralama

   İçeriği dışa aktarabilirsiniz **paralel izleme** seçerek Excel penceresine **Excel** düğmesine ve ardından **Excel'de Aç**. Geliştirme bilgisayarınızda bulunan Excel varsa, bu içeriği içeren bir Excel çalışma sayfası açılır.

6. Sağ üst köşesindeki **paralel izleme** penceresi, Boolean ifadeleri kullanarak içeriği filtrelemek için kullanabileceğiniz bir filtre denetimi yoktur. ENTER `localA[localIdx[0]] > 20000` filtre denetimi metin kutusuna ve ardından **Enter** anahtarı.

   Pencere artık yalnızca iş parçacığı, işlem içerir `localA[localIdx[0]]` değerdir 20000 büyük. İçeriği hala kendisine göre sıralandığı `localA[localIdx[0]]` daha önce gerçekleştirdiğiniz sıralama eylem sütunu.

## <a name="flagging-gpu-threads"></a>GPU iş parçacıkları işaretleme

Bunları işaretlemesini belirli GPU iş parçacıkları işaretleyebilirsiniz **GPU iş parçacıkları** penceresinde **paralel izleme** penceresi veya DataTip içinde **Paralel Yığınlar** penceresi. GPU iş parçacıkları penceresinde bir satır birden fazla iş parçacığı içeriyorsa, o satırın işaretlemesini satırda bulunan tüm iş parçacıkları işaretler.

### <a name="to-flag-gpu-threads"></a>Bayrak GPU iş parçacıkları

1. Seçin **[iş parçacığı]** sütun başlığına **paralel Watch 1** döşeme dizinini ve iş parçacığı dizini göre sıralamak için penceresi.

2. Menü çubuğunda, **hata ayıklama** > **devam**, dört iş parçacığı, neden olan etkin (AMPMapReduce.cpp 32 satırında tanımlanan) sonraki engel işleniyor.

3. Artık etkin olan dört iş parçacığı içeren satırı sol tarafındaki bayrağı simgesini seçin.

   Aşağıdaki çizimde dört etkin bayraklı iş parçacıklarını içinde **GPU iş parçacıkları** penceresi.

   ![GPU iş parçacıkları penceresi ile bayraklı iş parçacıklarını](../../parallel/amp/media/campg.png "bayraklı iş parçacıklarını GPU iş parçacıkları penceresi") <br/>
   GPU iş parçacıkları penceresinde Etkin iş parçacığı sayısı

   **Paralel izleme** penceresi ve, DataTip **Paralel Yığınlar** her iki pencere bayraklı iş parçacıklarını gösterir.

4. Bayrak dört iş parçacığı üzerinde odaklanmak istiyorsanız buna göstermeyi seçebilirsiniz **GPU iş parçacıkları**, **paralel izleme**, ve **Paralel Yığınlar** windows, yalnızca bayraklı iş parçacıkları.

   Seçin **sadece bayrak eklenmiş Göster** düğmesi herhangi bir Windows veya **hata ayıklama konumu** araç çubuğu. Aşağıdaki çizimde gösterildiği **sadece bayrak eklenmiş Göster** düğmesini **hata ayıklama konumu** araç çubuğu.

   ![Hata ayıklama konumu araç çubuğu Göster'i yalnızca bayrak simgesiyle](../../parallel/amp/media/camph.png "Göster'i yalnızca bayrak simgesiyle hata ayıklama konumu araç çubuğu") <br/>
   **Yalnızca bayrak eklenmiş Göster** düğmesi

   Artık **GPU iş parçacıkları**, **paralel izleme**, ve **Paralel Yığınlar** windows yalnızca bayraklı iş parçacıklarını görüntüler.

## <a name="freezing-and-thawing-gpu-threads"></a>Dondurma ve GPU iş parçacıkları çözme

Freeze (askıya alma) ve (devam) GPU iş parçacıkları veya çözme **GPU iş parçacıkları** penceresi veya **paralel izleme** penceresi. Dondurma ve aynı şekilde CPU iş parçacıklarını çözme; bilgi için [nasıl yapılır: İş parçacıkları penceresini kullanma](/visualstudio/debugger/how-to-use-the-threads-window).

### <a name="to-freeze-and-thaw-gpu-threads"></a>Freeze ve GPU iş parçacıklarını çözme

1. Seçin **sadece bayrak eklenmiş Göster** tüm iş parçacıkları görüntülenecek düğmesi.

2. Menü çubuğunda, **hata ayıklama** > **devam**.

3. Etkin bir satır için kısayol menüsünü açın ve ardından **dondurma**.

   Aşağıdaki çizim, **GPU iş parçacıkları** penceresi tüm dört iş parçacıkları dondurulmuş olduğunu gösterir.

   ![Dondurulmuş bir iş parçacığı gösteren GPU iş parçacıkları windows](../../parallel/amp/media/campk.png "GPU iş parçacıkları windows dondurulmuş bir iş parçacığı gösteriliyor") <br/>
   İş parçacıkları dondurulmuş **GPU iş parçacıkları** penceresi

   Benzer şekilde, **paralel izleme** penceresi tüm dört iş parçacıkları dondurulmuş olduğunu gösterir.

4. Menü çubuğunda, **hata ayıklama** > **devam** sonraki dört GPU iş parçacıkları satır 22 engel son ilerleme ve 30 satırında bir kesme noktasına ulaşmak için izin vermek için. **GPU iş parçacıkları** penceresi gösterir dört önceden dondurulmuş bir iş parçacığı kalmasını dondurulmuş ve etkin durumda.

5. Menü çubuğunda, **hata ayıklama**, **devam**.

6. Gelen **paralel izleme** penceresinde tek tek veya birden çok GPU iş parçacıkları çözme.

### <a name="to-group-gpu-threads"></a>İçin Grup GPU iş parçacıkları

1. Bir iş parçacığı için kısayol menüsündeki **GPU iş parçacıkları** penceresinde seçin **Group By**, **adresi**.

   İş parçacıklarında **GPU iş parçacıkları** penceresi adresine göre gruplandırılır. İçinde ayrıştırılmış kodu her iş parçacığı grubunun bulunduğu yönerge adresini karşılık gelir. 24 akışlardır 22 satırında nerede [tile_barrier::wait yöntemi](reference/tile-barrier-class.md#wait) yürütülür. 12 iş parçacığı 32 satırında barrier yönergesi altındadır. Bu iş parçacığı dört işaretlenir. Sekiz 30 satırında bir kesme noktasında akışlardır. Dört bu iş parçacıkları dondurulmuş. Gruplanmış iş parçacıkları aşağıdaki çizimde **GPU iş parçacıkları** penceresi.

   ![GPU iş parçacıkları penceresi ile iş parçacığı adresine göre gruplandırılmış](../../parallel/amp/media/campl.png "GPU iş parçacıkları penceresi ile iş parçacığı adresine göre gruplandırılmış") <br/>
   İş parçacığını gruplandırılır **GPU iş parçacıkları** penceresi

2. Ayrıca gerçekleştirebilirsiniz **Group By** veri kılavuzunun için kısayol menüsünü açarak işlemi **paralel izleme** penceresinde seçme **Group By**ve ardından menüden seçerek iş parçacıkları gruplandırmak istediğiniz nasıl karşılık gelen öğe.

## <a name="running-all-threads-to-a-specific-location-in-code"></a>Kodda belirli bir konuma çalışan tüm iş parçacıkları

Kullanarak imlecin bulunduğu satıra verilen döşemedeki tüm iş parçacıkları çalıştırmak **geçerli Kutucuğuna imlece**.

### <a name="to-run-all-threads-to-the-location-marked-by-the-cursor"></a>İmleç ile işaretlenmiş bir konuma tüm iş parçacıkları çalıştırmak için

1. İş parçacıkları dondurulmuş için kısayol menüsünde **çözme**.

2. İçinde **Kod Düzenleyicisi**, 30. satırda imleci yerleştirin.

3. Kısayol menüsünde **Kod Düzenleyicisi**, seçin **geçerli kutucuk imlece**.

   Daha önce engel satır 21, engellenen 24 iş parçacığı 32 satırına progressed. Bu gösterilen **GPU iş parçacıkları** penceresi.

## <a name="see-also"></a>Ayrıca bkz.

[C++ AMP'ye Genel Bakış](../../parallel/amp/cpp-amp-overview.md)<br/>
[GPU Kodunda Hata Ayıklama](/visualstudio/debugger/debugging-gpu-code)<br/>
[Nasıl yapılır: GPU İş Parçacıkları Penceresini Kullanma](/visualstudio/debugger/how-to-use-the-gpu-threads-window)<br/>
[Nasıl yapılır: Paralel İzleme Penceresini Kullanma](/visualstudio/debugger/how-to-use-the-parallel-watch-window)<br/>
[Eşzamanlılık görselleştiricisi ile C++ AMP kodunu analiz etme](https://blogs.msdn.microsoft.com/nativeconcurrency/2012/03/09/analyzing-c-amp-code-with-the-concurrency-visualizer/)
