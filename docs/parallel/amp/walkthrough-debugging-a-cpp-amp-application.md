---
title: "İzlenecek yol: C++ AMP uygulamasında hata ayıklama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- debugging, C++ Accelerated Massive Parallelism
- C++ AMP, debugging
- C++ Accelerated Massive Parallelism, debugging
- debugging, C++ AMP
ms.assetid: 40e92ecc-f6ba-411c-960c-b3047b854fb5
caps.latest.revision: "35"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: d3dc050418d8053e04053d5eafbd328e49bd473b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="walkthrough-debugging-a-c-amp-application"></a>İzlenecek yol: C++ AMP Uygulamasında Hata Ayıklama
Bu konu, grafik işlemci birimi (GPU) yararlanmak için C++ hızlandırılmış yoğun paralellik (C++ AMP) kullanan bir uygulama hata ayıklama gösterilmiştir. Uzun bir diziye tamsayılar toplayan bir paralel azaltma programı kullanır. Bu izlenecek yol aşağıdaki görevleri gösterir:  
  
-   GPU hata ayıklayıcı başlatılıyor.  
  
-   GPU iş parçacıkları penceresi GPU iş parçacıkları inceleniyor.  
  
-   Aynı anda birden çok GPU iş parçacıkları çağrı yığınları izlemek için Paralel Yığınlar penceresini kullanma.  
  
-   Tek bir ifade değerleri aynı anda birden çok iş parçacıkları arasında incelemek için paralel İzleme penceresini kullanma.  
  
-   İşaretleme, dondurma, çözme ve GPU iş parçacıkları gruplandırma.  
  
-   Belirli bir konuma bir kutucuk tüm iş parçacıklarının kodda yürütülüyor.  
  
## <a name="prerequisites"></a>Önkoşullar  
 Bu kılavuza başlamadan önce:  
  
-   Okuma [C++ AMP'ye genel bakış](../../parallel/amp/cpp-amp-overview.md).  
  
-   Bu satırı emin olun sayılar metin Düzenleyicisi'nde görüntülenir. Daha fazla bilgi için bkz: [nasıl yapılır: görüntü satır numaralarını Düzenleyicisi'nde](/visualstudio/ide/reference/how-to-display-line-numbers-in-the-editor).  
  
-   Çalıştırdığınızdan emin olun [!INCLUDE[win8](../../build/reference/includes/win8_md.md)] veya [!INCLUDE[winserver8](../../build/reference/includes/winserver8_md.md)] yazılım öykünücüsünde hata ayıklamayı desteklemek için.  
  
 [!INCLUDE[note_settings_general](../../mfc/includes/note_settings_general_md.md)]  
  
### <a name="to-create-the-sample-project"></a>Örnek proje oluşturmak için  
  
1.  Visual Studio'yu başlatın.  
  
2.  Menü çubuğunda seçin **dosya**, **yeni**, **proje**.  
  
3.  Altında **yüklü** Şablonlar bölmesinde seçin **Visual C++**.  
  
4.  Seçin **Win32 konsol uygulaması**, türü `AMPMapReduce` içinde **adı** kutusuna ve ardından **Tamam** düğmesi.  
  
5.  Seçin **sonraki** düğmesi.  
  
6.  Clear **önceden derlenmiş üstbilgi** onay kutusunu işaretleyin ve ardından **son** düğmesi.  
  
7.  İçinde **Çözüm Gezgini**, stdafx.h, targetver.h ve stdafx.cpp projeden silin.  
  
8.  AMPMapReduce.cpp açın ve içeriğini aşağıdaki kodla değiştirin.  
  
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
  
9. Menü çubuğunda seçin **dosya**, **Tümünü Kaydet**.  
  
10. İçinde **Çözüm Gezgini**, kısayol menüsünü açın **AMPMapReduce**ve ardından **özellikleri**.  
  
11. İçinde **özellik sayfaları** iletişim kutusunda **yapılandırma özellikleri**, seçin **C/C++**, **önceden derlenmiş üstbilgiler**.  
  
12. İçin **önceden derlenmiş üstbilgi** özelliği, select **kullanarak önceden derlenmiş üstbilgi**ve ardından **Tamam** düğmesi.  
  
13. Menü çubuğunda seçin **yapı**, **yapı çözümü**.  
  
## <a name="debugging-the-cpu-code"></a>CPU kodda hata ayıklama  
 Bu yordamda, bu uygulama CPU kodda doğru olduğundan emin olmak için yerel Windows hata ayıklayıcı kullanır. Bu uygulamada özellikle ilginç CPU kod kesimi `for` içinde döngü `reduction_sum_gpu_kernel` işlevi. GPU üzerinde çalıştırılan ağaç tabanlı paralel azaltma denetler.  
  
### <a name="to-debug-the-cpu-code"></a>CPU kodun hatalarını ayıklamak için  
  
1.  İçinde **Çözüm Gezgini**, kısayol menüsünü açın **AMPMapReduce**ve ardından **özellikleri**.  
  
2.  İçinde **özellik sayfaları** iletişim kutusunda **yapılandırma özellikleri**, seçin **hata ayıklama**. Doğrulayın **yerel Windows hata ayıklayıcı** seçildiyse **başlatmak için hata ayıklayıcı** listesi.  
  
3.  Kod düzenleyicisine döndür.  
  
4.  (Yaklaşık satırları 67 satır 70) aşağıdaki çizimde gösterilen kod satırlarındaki kesme noktalarını ayarlayın.  
  
     ![CPU kesme noktaları](../../parallel/amp/media/campcpubreakpoints.png "campcpubreakpoints")  
CPU kesme noktaları  
  
5.  Menü çubuğunda seçin **hata ayıklama**, **hata ayıklamayı Başlat**.  
  
6.  İçinde **Yereller** penceresinde değeri gözlemlemek `stride_size` 70 satırında bir kesme noktası ulaşılana kadar.  
  
7.  Menü çubuğunda seçin **hata ayıklama**, **durdurma hata ayıklama**.  
  
## <a name="debugging-the-gpu-code"></a>GPU kodunda hata ayıklama  
 Bu bölümde yer alan kodu GPU kodunda hata ayıklama gösterilmektedir, `sum_kernel_tiled` işlevi. GPU kodunda her "Taşı" için tamsayılar toplamını paralel olarak hesaplar.  
  
### <a name="to-debug-the-gpu-code"></a>GPU kodunda hata ayıklama  
  
1.  İçinde **Çözüm Gezgini**, kısayol menüsünü açın **AMPMapReduce**ve ardından **özellikleri**.  
  
2.  İçinde **özellik sayfaları** iletişim kutusunda **yapılandırma özellikleri**, seçin **hata ayıklama**.  
  
3.  İçinde **başlatmak için hata ayıklayıcı** listesinde **yerel Windows hata ayıklayıcı**.  
  
4.  İçinde **hata ayıklayıcı türü** listesinde **yalnızca GPU**.  
  
5.  Seçin **Tamam** düğmesi.  
  
6.  Bir kesme noktası satırında 30, aşağıdaki çizimde gösterildiği gibi ayarlayın.  
  
     ![GPU kesme noktaları](../../parallel/amp/media/campgpubreakpoints.png "campgpubreakpoints")  
GPU kesme noktası  
  
7.  Menü çubuğunda seçin **hata ayıklama**, **hata ayıklamayı Başlat**. Kesme noktaları 67 ve 70 satırlarındaki CPU kodda GPU Bu kod satırları CPU üzerinde çalıştırıldığı için hata ayıklama sırasında yürütülmedi.  
  
### <a name="to-use-the-gpu-threads-window"></a>GPU iş parçacıkları penceresi kullanmak için  
  
1.  Menü çubuğunda GPU iş parçacıkları penceresini açmak üzere seçin **hata ayıklama**, **Windows**, **GPU iş parçacıkları**.  
  
     Görüntülenen GPU iş parçacıkları penceresi GPU iş parçacıkları durumunu inceleyebilirsiniz.  
  
2.  Visual Studio sonundaki GPU iş parçacıkları penceresini yerleştirme. Seçin **genişletin iş parçacığı anahtarı** kutucuğu ve iş parçacığı metin kutuları görüntülenecek düğmesi. GPU iş parçacıkları penceresi, aşağıdaki çizimde gösterildiği gibi GPU iş parçacıkları, etkin ve engellenen toplam sayısını gösterir.  
  
     ![GPU iş parçacıkları penceresi 4 etkin iş parçacığı ile](../../parallel/amp/media/campc.png "campc")  
GPU iş parçacıkları penceresi  
  
     Bu hesaplama için ayrılan 313 döşeme vardır. Her bölme 32 iş parçacığı içerir. GPU yerel hata ayıklama yazılım öykünücüsünde oluştuğundan dört etkin GPU iş parçacığı vardır. Dört iş parçacığı yönergeleri aynı anda yürütün ve sonra birlikte sonraki yönerge geçin.  
  
     GPU iş parçacıkları penceresi vardır dört GPU iş parçacıkları etkin ve 28 GPU iş parçacıkları engellenen adresindeki [tile_barrier::wait](reference/tile-barrier-class.md#wait) çizgi 21 hakkında tanımlanan deyimi (`t_idx.barrier.wait();`). Tüm 32 GPU iş parçacıkları ilk döşeme ait `tile[0]`. Bir ok geçerli iş parçacığı içeren satırı işaret eder. Farklı bir iş parçacığı için geçiş yapmak için aşağıdaki yöntemlerden birini kullanın:  

  
    -   GPU iş parçacıkları penceresinde geçmek iş parçacığı için satırda kısayol menüsünü açın ve seçin **iş parçacığının geçiş**. Birden çok iş parçacığı satır temsil ediyorsa, iş parçacığı koordinatlara göre ilk iş parçacığına geçiş yapar.  
  
    -   İş parçacığı kutucuğu ve iş parçacığı değerlerini ilgili metin kutularına girin ve ardından **anahtar iş parçacığı** düğmesi.  
  
     Çağrı yığını penceresinde geçerli GPU iş parçacığının çağrı yığını görüntülenir.  
  
### <a name="to-use-the-parallel-stacks-window"></a>Paralel Yığınlar penceresini kullanmak için  
  
1.  Menü çubuğunda Paralel Yığınlar penceresini açmak üzere seçin **hata ayıklama**, **Windows**, **Paralel Yığınlar**.  
  
     Paralel Yığınlar penceresini, aynı anda birden çok GPU iş parçacıkları yığın çerçeveleri incelemek için kullanabilirsiniz.  
  
2.  Visual Studio sonundaki Paralel Yığınlar penceresini yerleştirme.  
  
3.  Olduğundan emin olun **iş parçacığı** sol üst köşesindeki listesinde seçilir. Aşağıdaki çizimde, Paralel Yığınlar penceresini GPU iş parçacıkları penceresinde gördüğünüz GPU iş parçacıkları çağrı yığını odaklanmış görünümünü gösterir.  
  
     ![Paralel Yığınlar penceresini 4 etkin iş parçacığı ile](../../parallel/amp/media/campd.png "campd")  
Paralel Yığınlar penceresi  
  
     32 iş parçacığı oluştu `_kernel_stub` lambda ifadesine `parallel_for_each` işlev çağrısı ve sonra `sum_kernel_tiled` paralel azaltma oluştuğu işlevi. 28 32 iş parçacığı dışında progressed için [tile_barrier::wait](reference/tile-barrier-class.md#wait) deyimi ve diğer 4 iş parçacıklarının etkin kalır ancak satırında 22, engellenmiş olarak kalır `sum_kernel_tiled` satırı 30 işlevi.  

  
     Paralel Yığınlar penceresinin zengin DataTip GPU iş parçacıkları penceresinde kullanılabilir GPU iş parçacığı özelliklerini inceleyebilirsiniz. Bunu yapmak için fare işaretçisini yığın çerçevesi rest **sum_kernel_tiled**. Aşağıdaki çizimde DataTip gösterir.  
  
     ![Paralel Yığınlar penceresini DataTip](../../parallel/amp/media/campe.png "campe")  
GPU iş parçacığı DataTip  
  
     Paralel Yığınlar penceresini hakkında daha fazla bilgi için bkz: [Paralel Yığınlar penceresini kullanarak](/visualstudio/debugger/using-the-parallel-stacks-window).  
  
### <a name="to-use-the-parallel-watch-window"></a>Paralel Gözcü penceresi kullanmak için  
  
1.  Menü çubuğunda, paralel Gözcü penceresi açmak için **hata ayıklama**, **Windows**, **paralel Gözcü**, **paralel Gözcü 1**.  
  
     Paralel Gözcü penceresi değerlerin ifade birden çok iş parçacıkları arasında incelemek için kullanabilirsiniz.  
  
2.  Paralel Gözcü 1 penceresine Visual Studio altına yerleştir. Paralel Gözcü penceresi tabloda 32 satır vardır. Her GPU iş parçacıkları penceresi ve Paralel Yığınlar penceresini görünen bir GPU iş parçacığı karşılık gelir. Şimdi, değerleri tüm 32 GPU iş parçacıkları arasında incelemek istediğiniz ifadeler girebilirsiniz.  
  
3.  Seçin **Gözcü Ekle** sütun başlığını girin `localIdx`ve ardından Enter tuşuna seçin.  
  
4.  Seçin **Gözcü Ekle** sütun başlığını tekrar, türü `globalIdx`ve ardından Enter tuşuna seçin.  
  
5.  Seçin **Gözcü Ekle** sütun başlığını tekrar, türü `localA[localIdx[0]]`ve ardından Enter tuşuna seçin.  
  
     Karşılık gelen sütunun başlığını seçerek belirtilen ifadeye göre sıralama yapabilirsiniz.  
  
     Seçin **localA [localIdx [0]]** sütunu sıralamak için sütun başlığını. Aşağıdaki çizimde sıralamada sonuçlarını gösterir **localA [localIdx [0]]**.  
  
     ![Paralel Gözcü penceresi sıralanmış sonuçlarla](../../parallel/amp/media/campf.png "campf")  
 Sıralama sonuçları  
  
     Paralel Gözcü penceresi içeriği Excel düğmesini seçerek ve ardından seçme Excel'e aktarabilirsiniz **Excel'de Aç**. Geliştirme bilgisayarınızda yüklü Excel varsa, bu içeriği içeren bir Excel çalışma sayfası açılır.  
  
6.  Paralel Gözcü penceresi sağ üst köşesinde Boole ifadeleri kullanarak içeriği filtre uygulamak için kullanabileceğiniz bir filtre denetimi yoktur. ENTER `localA[localIdx[0]] > 20000` filtre denetimi metin kutusuna ve ardından Enter tuşuna seçin.  
  
     Pencere artık yalnızca iş parçacıklarında hangi içerir `localA[localIdx[0]]` değerdir 20000 büyük. İçeriği hala kendisine göre sıralandığı `localA[localIdx[0]]` daha önce gerçekleştirdiğiniz sıralama eylem sütun.  
  
## <a name="flagging-gpu-threads"></a>GPU iş parçacıkları işaretleme  
 Bunları GPU iş parçacıkları penceresi, paralel Gözcü penceresi veya DataTip Paralel Yığınlar penceresinde işaretlemesini tarafından belirli GPU iş parçacıkları işaretleyebilirsiniz. GPU iş parçacıkları penceresi satırda birden çok iş parçacığı içeriyorsa, o satırdaki işaretlemesini satır içinde bulunan tüm iş parçacıklarının işaretler.  
  
### <a name="to-flag-gpu-threads"></a>Bayrak GPU iş parçacıkları  
  
1.  Seçin **[iş parçacığı]** paralel Gözcü 1 penceresinde döşeme dizini ve iş parçacığı dizini göre sıralamak için sütun başlığını.  
  
2.  Menü çubuğunda seçin **hata ayıklama**, **devam**, dört iş parçacığı, neden olan ilerleme durumu (AMPMapReduce.cpp 32 satırında tanımlanan) sonraki engel için etkin.  
  
3.  Şimdi etkin olan dört iş parçacığı içeren satırı sol tarafındaki bayrağı simgesini seçin.  
  
     Aşağıdaki çizimde, dört etkin bayraklı iş parçacığı GPU iş parçacıkları penceresinde gösterir.  
  
     ![GPU iş parçacıkları penceresi bayraklı iş parçacığı ile](../../parallel/amp/media/campg.png "campg")  
GPU iş parçacıkları penceresi etkin iş parçacıkları  
  
     Paralel Gözcü penceresi ve her iki Paralel Yığınlar penceresini DataTip bayraklı iş parçacığı gösterir.  
  
4.  Bayrak dört iş parçacığı üzerinde odaklanmak istiyorsanız, GPU iş parçacıkları, paralel Gözcü ve Paralel Yığınlar windows bayraklı iş parçacıkları Göster seçebilirsiniz.  
  
     Yalnızca bayrak Göster düğmesini herhangi bir windows veya üzerinde seçin **hata ayıklama konumu** araç. Aşağıdaki çizimde yalnızca işaretlenen Göster düğmesini gösterir **hata ayıklama konumu** araç.  
  
     ![Konum araç çubuğunu göster'i yalnızca bayrak simgesiyle hata ayıklama](../../parallel/amp/media/camph.png "camph")  
Yalnızca bayrak düğmesini göster  
  
     Şimdi GPU iş parçacıkları, paralel Gözcü ve Paralel Yığınlar windows bayraklı iş parçacıkları görüntüler.  
  
## <a name="freezing-and-thawing-gpu-threads"></a>Dondurma ve GPU iş parçacıkları çözme  
 Freeze (askıya alma) ve (devam) GPU iş parçacıkları GPU iş parçacıkları penceresi veya paralel Gözcü penceresi çözme. Freeze ve CPU iş parçacığı aynı şekilde çözme; bilgi için bkz: [nasıl yapılır: iş parçacıkları penceresini kullanma](/visualstudio/debugger/how-to-use-the-threads-window).  
  
### <a name="to-freeze-and-thaw-gpu-threads"></a>Freeze ve GPU iş parçacıkları çözme  
  
1.  Seçin **yalnızca Göster bayrağı** tüm iş parçacıkları görüntülenecek düğmesi.  
  
2.  Menü çubuğunda seçin **hata ayıklama**, **devam**.  
  
3.  Etkin satır için kısayol menüsünü açın ve ardından **Dondur**.  
  
     GPU iş parçacıkları penceresi, aşağıdaki çizimde, tüm dört iş parçacığı dondurulmuş olduğunu gösterir.  
  
     ![GPU iş parçacıkları windows dondurulmuş iş parçacığı gösteren](../../parallel/amp/media/campk.png "campk")  
GPU iş parçacıkları penceresi dondurulmuş iş parçacıkları  
  
     Benzer şekilde, paralel Gözcü penceresi tüm dört iş parçacığı dondurulmuş olduğunu gösterir.  
  
4.  Menü çubuğunda seçin **hata ayıklama**, **devam** sonraki dört GPU iş parçacıkları 22 satırında engel geçmiş ilerleme ve 30 satırında bir kesme noktası ulaşmak için izin vermek için. GPU iş parçacıkları penceresi dört önceden dondurulmuş iş parçacığı kalmasını dondurulmuş ve etkin durumda gösterir.  
  
5.  Menü çubuğunda seçin **hata ayıklama**, **devam**.  
  
6.  Paralel Gözcü penceresinden tek tek veya birden çok GPU iş parçacıkları ayrıca çözme.  
  
### <a name="to-group-gpu-threads"></a>İçin Grup GPU iş parçacıkları  
  
1.  İş parçacıkları biri için kısayol menüsünde **GPU iş parçacıkları** penceresinde, seçin **Group By**, **adresi**.  
  
     GPU iş parçacıkları penceresi parçacıklarında adresine göre gruplandırılır. Adres her grup iş parçacığı bulunduğu ayrıştırılmış yönergesinde karşılık gelir. 24 iş parçacığı satırında 22 olduğunuz nerede [tile_barrier::wait yöntemi](reference/tile-barrier-class.md#wait) yürütülür. satırı 32 barrier yönergesi 12 iş parçacığı altındadır. Bu iş parçacıkları dördünü işaretlenir. Kesme noktası 30 satırında sekiz iş parçacığı altındadır. Bu iş parçacıkları dördünü dondurulmuş. Aşağıdaki çizimde gruplandırılmış iş parçacığı GPU iş parçacıkları penceresinde gösterir.  

  
     ![İş parçacığı ile GPU iş parçacıkları penceresi adresine göre gruplandırılmış](../../parallel/amp/media/campl.png "campl")  
GPU iş parçacıkları penceresi gruplandırılmış iş parçacıkları  
  
2.  De gerçekleştirebilirsiniz **Group By** paralel Gözcü penceresi veri kılavuzunun için kısayol menüsünü açarak işlemi seçme **Group By**ve ardından nasıl istediğiniz karşılık gelen menü öğesi iş parçacığı gruplandırmak için.  
  
## <a name="running-all-threads-to-a-specific-location-in-code"></a>Belirli bir konuma kodda çalışan tüm iş parçacığı  
 Kullanarak imlecin bulunduğu satırı verilen parçasında tüm iş parçacıklarını çalıştırmak **çalıştırmak geçerli döşeme için imleç**.  
  
### <a name="to-run-all-threads-to-the-location-marked-by-the-cursor"></a>İmleç ile işaretlenmiş konuma tüm iş parçacıklarını çalıştırmak için  
  
1.  Dondurulmuş iş parçacığı için kısayol menüsünden seçin **çözme**.  
  
2.  Kod Düzenleyicisi'nde imleci satırında 30 yerleştirin.  
  
3.  Kod Düzenleyicisi için kısayol menüsünden seçin **çalıştırmak geçerli döşeme için imleç**.  
  
     Daha önce satırı 21 engel adresindeki engellendi 24 iş parçacığı satır 32 progressed. Bu gösterilen **GPU iş parçacıkları** penceresi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ AMP'ye genel bakış](../../parallel/amp/cpp-amp-overview.md)   
 [GPU kodunda hata ayıklama](/visualstudio/debugger/debugging-gpu-code)   
 [Nasıl yapılır: GPU iş parçacıkları penceresini kullanma](/visualstudio/debugger/how-to-use-the-gpu-threads-window)   
 [Nasıl yapılır: paralel İzleme penceresini kullanma](/visualstudio/debugger/how-to-use-the-parallel-watch-window)   
 [Eşzamanlılık görselleştiricisi ile C++ AMP kodunu analiz etme](http://go.microsoft.com/fwlink/linkid=253987&clcid=0x409)

