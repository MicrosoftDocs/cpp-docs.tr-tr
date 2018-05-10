---
title: 'İzlenecek yol: Bir kullanıcı arabirimi iş parçacığından işi kaldırma | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- user-interface threads, removing work from [Concurrency Runtime]
- removing work from user-interface threads [Concurrency Runtime]
ms.assetid: a4a65cc2-b3bc-4216-8fa8-90529491de02
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0502ce728c35b08d927cea48ee5b82756980aec5
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
---
# <a name="walkthrough-removing-work-from-a-user-interface-thread"></a>İzlenecek yol: Kullanıcı Arabirimi İş Parçacığından İşi Kaldırma
Bu belge eşzamanlılık çalışma zamanı bir çalışan iş parçacığı için Microsoft Foundation sınıfları (MFC) uygulamasında kullanıcı arabirimi (UI) iş parçacığı tarafından gerçekleştirilen iş taşımak için nasıl kullanılacağını gösterir. Bu belge, ayrıca uzun bir çizim işlem performansını artırmak nasıl gösterir.  
  
 Durdurma işlemlerini devrederek kullanıcı Arabirimi iş parçacığından işi kaldırma, örneğin, çalışan iş parçacığı için çizim, uygulamanızın yanıtlama artırabilir. Bu kılavuzda, uzun bir engelleme işlem göstermek için Mandelbrot düzgünleştiren parçalı oluşturan bir çizim yordam kullanılır. Her piksel hesaplama diğer tüm hesaplamaları bağımsız olduğundan Mandelbrot düzgünleştiren parçalı nesil de paralelleştirme için iyi bir aday değildir.  
  
## <a name="prerequisites"></a>Önkoşullar  
 Bu kılavuza başlamadan önce aşağıdaki konuları okuyun:  
  
-   [Görev Paralelliği](../../parallel/concrt/task-parallelism-concurrency-runtime.md)  
  
-   [Zaman Uyumsuz İleti Blokları](../../parallel/concrt/asynchronous-message-blocks.md)  
  
-   [İleti Geçirme İşlevleri](../../parallel/concrt/message-passing-functions.md)  
  
-   [Paralel Algoritmalar](../../parallel/concrt/parallel-algorithms.md)  
  
-   [PPL'de İptal](cancellation-in-the-ppl.md)  
  
 Ayrıca, MFC Uygulama geliştirme temelleri anlamanız öneririz ve [!INCLUDE[ndptecgdiplus](../../parallel/concrt/includes/ndptecgdiplus_md.md)] bu kılavuza başlamadan önce. MFC hakkında daha fazla bilgi için bkz: [MFC Masaüstü uygulamaları](../../mfc/mfc-desktop-applications.md). Hakkında daha fazla bilgi için [!INCLUDE[ndptecgdiplus](../../parallel/concrt/includes/ndptecgdiplus_md.md)], bkz: [GDI +](https://msdn.microsoft.com/en-us/library/windows/desktop/ms533798).  
  
##  <a name="top"></a> Bölümler  
 Bu kılavuz aşağıdaki bölümleri içerir:  
  
-   [MFC uygulaması oluşturma](#application)  
  
-   [Seri sürümü Mandelbrot uygulamasının uygulama](#serial)  
  
-   [Kullanıcı arabirimi iş parçacığından işi kaldırma](#removing-work)  
  
-   [Çizim performansı artırma](#performance)  
  
-   [İptal etme desteği ekleme](#cancellation)  
  
##  <a name="application"></a> MFC uygulaması oluşturma  
 Bu bölümde temel MFC uygulamasının nasıl oluşturulacağını açıklar.  
  
### <a name="to-create-a-visual-c-mfc-application"></a>Visual C++ MFC uygulaması oluşturmak için  
  
1.  Üzerinde **dosya** menüsünde tıklatın **yeni**ve ardından **proje**.  
  
2.  İçinde **yeni proje** iletişim kutusunda **yüklü şablonlar** bölmesinde, **Visual C++** ve ardından **şablonları** bölmesinde, **MFC uygulaması**. Proje için bir ad yazın, örneğin, `Mandelbrot`ve ardından **Tamam** görüntülemek için **MFC Uygulama Sihirbazı'nı**.  
  
3.  İçinde **uygulama türü** bölmesinde, **tek bir belge**. Emin **belge/görünüm mimarisi desteği** onay kutusu işaretli.  
  
4.  Tıklatın **son** projesi oluşturun ve kapatmak için **MFC Uygulama Sihirbazı'nı**.  
  
     Derleme ve çalışan uygulamanın başarıyla oluşturulduğunu doğrulayın. Uygulama üzerinde oluşturmak için **yapı** menüsünde tıklatın **yapı çözümü**. Uygulama başarıyla oluşturursa tıklayarak uygulamayı çalıştırın **hata ayıklamayı Başlat** üzerinde **hata ayıklama** menüsü.  
  
##  <a name="serial"></a> Seri sürümü Mandelbrot uygulamasının uygulama  
 Bu bölümde, Mandelbrot düzgünleştiren parçalı çizmek açıklar. Bu sürüm için Mandelbrot düzgünleştiren parçalı çizer bir [!INCLUDE[ndptecgdiplus](../../parallel/concrt/includes/ndptecgdiplus_md.md)] [bit eşlem](https://msdn.microsoft.com/library/ms534420.aspx) nesne ve ardından bu bit eşlem içeriğini istemci penceresine kopyalar.  
  
#### <a name="to-implement-the-serial-version-of-the-mandelbrot-application"></a>Seri sürümü Mandelbrot uygulamasının uygulamak için  
  
1.  Aşağıdaki Stdafx.h'de ekleyin `#include` yönergesi:  
  
     [!code-cpp[concrt-mandelbrot#1](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_1.h)]  
  
2.  ChildView.h içinde sonra `pragma` yönergesi, tanımlamak `BitmapPtr` türü. `BitmapPtr` Türü etkinleştirir gösteren bir işaretçi bir `Bitmap` birden çok bileşenleri tarafından paylaşılmak üzere nesne. `Bitmap` Nesne artık herhangi bir bileşen tarafından başvurulduğunda silinir.  
  
     [!code-cpp[concrt-mandelbrot#2](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_2.h)]  
  
3.  Aşağıdaki kodu ChildView.h içinde eklemek `protected` bölümünü `CChildView` sınıfı:  
  
     [!code-cpp[concrt-mandelbrot#3](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_3.h)]  
  
4.  ChildView.cpp, çıkışı açıklama veya aşağıdaki satırları kaldırın.  
  
     [!code-cpp[concrt-mandelbrot#4](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_4.cpp)]  
  
     Hata ayıklama derlemelerinde, bu adımı kullanarak uygulamanın engeller `DEBUG_NEW` ile uyumsuz ayırıcısı [!INCLUDE[ndptecgdiplus](../../parallel/concrt/includes/ndptecgdiplus_md.md)].  
  
5.  ChildView.cpp içinde eklemek bir `using` için yönerge `Gdiplus` ad alanı.  
  
     [!code-cpp[concrt-mandelbrot#5](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_5.cpp)]  
  
6.  Aşağıdaki kod Oluşturucu için ekleyip yıkıcısı `CChildView` başlatmak ve kapatmak için sınıf [!INCLUDE[ndptecgdiplus](../../parallel/concrt/includes/ndptecgdiplus_md.md)].  
  
     [!code-cpp[concrt-mandelbrot#6](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_6.cpp)]  
  
7.  Uygulama `CChildView::DrawMandelbrot` yöntemi. Bu yöntem Mandelbrot düzgünleştiren parçalı belirtilen çizer `Bitmap` nesnesi.  
  
     [!code-cpp[concrt-mandelbrot#7](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_7.cpp)]  
  
8.  Uygulama `CChildView::OnPaint` yöntemi. Bu yöntemi çağırır `CChildView::DrawMandelbrot` ve içeriğini kopyalar `Bitmap` penceresine nesnesi.  
  
     [!code-cpp[concrt-mandelbrot#8](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_8.cpp)]  
  
9. Uygulama oluşturma ve onu çalıştırma başarıyla güncelleştirildi doğrulayın.  
  
 Aşağıdaki çizimde Mandelbrot uygulama sonuçlarını gösterir.  
  
 ![Mandelbrot uygulama](../../parallel/concrt/media/mandelbrot.png "mandelbrot")  
  
 Her piksel için hesaplama pkı'ya pahalı olduğu için kullanıcı Arabirimi iş parçacığı genel hesaplama tamamlanana kadar ek iletileri işleyemez. Bu uygulamada yanıtlama hızı azaltma. Ancak, kullanıcı Arabirimi iş parçacığından iş kaldırarak bu sorunu hafifletmek.  
  
 [[Üst](#top)]  
  
##  <a name="removing-work"></a> Kullanıcı Arabirimi iş parçacığından işi kaldırma  
 Bu bölüm, kullanıcı Arabirimi iş parçacığı Mandelbrot uygulamada çizim iş kaldırmak gösterilmiştir. Bir çalışan iş parçacığı için kullanıcı Arabirimi iş parçacığından çizim iş taşıyarak, çalışan iş parçacığı arka planda görüntüyü oluştururken kullanıcı Arabirimi iş parçacığı iletileri işleyebilir.  
  
 Eşzamanlılık Çalışma zamanı görevleri çalıştırmak için üç yol sunar: [görev grupları](../../parallel/concrt/task-parallelism-concurrency-runtime.md), [zaman uyumsuz aracılar](../../parallel/concrt/asynchronous-agents.md), ve [Basit görevler](../../parallel/concrt/task-scheduler-concurrency-runtime.md). Kullanıcı Arabirimi iş parçacığından iş kaldırmak için Bu mekanizmaların birini kullanabilirsiniz ancak bu örnek kullanan bir [concurrency::task_group](reference/task-group-class.md) görev grupları iptal desteklemediğinden nesne. Bu kılavuzda daha sonra istemci penceresi yeniden boyutlandırıldığında, gerçekleştirilen iş miktarını azaltın ve pencere bozulduğunda temizlenmesini iptal kullanılır.  
  
 Bu örnek ayrıca kullanan bir [concurrency::unbounded_buffer](reference/unbounded-buffer-class.md) kullanıcı Arabirimi iş parçacığı ve birbirleri ile iletişim kurmak için çalışan iş parçacığı etkinleştirmek için nesne. Çalışan iş parçacığı görüntü üretiyor sonra bir işaretçi gönderir `Bitmap` nesnesini `unbounded_buffer` nesne ve kullanıcı Arabirimi iş parçacığı boyama ileti gönderir. Kullanıcı Arabirimi iş parçacığı ardından alan `unbounded_buffer` nesne `Bitmap` nesne ve istemci penceresine çizer.  
  
#### <a name="to-remove-the-drawing-work-from-the-ui-thread"></a>Kullanıcı Arabirimi iş parçacığından çizim iş kaldırmak için  
  
1.  Aşağıdaki Stdafx.h'de ekleyin `#include` yönergeleri:  
  
     [!code-cpp[concrt-mandelbrot#101](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_9.h)]  
  
2.  ChildView.h içinde eklemek `task_group` ve `unbounded_buffer` için üye değişkenleri `protected` bölümünü `CChildView` sınıfı. `task_group` Nesnesi tutar çizim; gerçekleştirdiği görevleri `unbounded_buffer` nesnesi tamamlanmış Mandelbrot görüntü tutar.  
  
     [!code-cpp[concrt-mandelbrot#102](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_10.h)]  
  
3.  ChildView.cpp içinde eklemek bir `using` için yönerge `concurrency` ad alanı.  
  
     [!code-cpp[concrt-mandelbrot#103](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_11.cpp)]  
  

4.  İçinde `CChildView::DrawMandelbrot` çağrısından sonra yöntemi `Bitmap::UnlockBits`, çağrı [concurrency::send](reference/concurrency-namespace-functions.md#send) geçirmek için işlevi `Bitmap` kullanıcı Arabirimi iş parçacığı nesnesine. Daha sonra kullanıcı Arabirimi iş parçacığı boyama ileti gönderme ve istemci alanı geçersiz.  

  
     [!code-cpp[concrt-mandelbrot#104](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_12.cpp)]  
  
5.  Güncelleştirme `CChildView::OnPaint` güncelleştirilmiş almak üzere yöntemini `Bitmap` nesne ve görüntünün istemci penceresine çizin.  
  
     [!code-cpp[concrt-mandelbrot#105](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_13.cpp)]  
  
     `CChildView::OnPaint` Yöntemi, bir ileti arabellek mevcut değilse Mandelbrot görüntü oluşturmak için bir görev oluşturur. İleti arabelleği değil içerecek bir `Bitmap` ve başka bir pencere önünde istemci penceresi taşındığında ilk boyama ileti gibi durumlarda nesne.  
  
6.  Uygulama oluşturma ve onu çalıştırma başarıyla güncelleştirildi doğrulayın.  
  
 Çizim iş arka planda gerçekleştirildiği için kullanıcı Arabirimi daha iyi yanıt sunulmuştur.  
  
 [[Üst](#top)]  
  
##  <a name="performance"></a> Çizim performansı artırma  

 Her piksel hesaplama diğer tüm hesaplamaları bağımsız olduğundan Mandelbrot düzgünleştiren parçalı nesil paralelleştirme için iyi bir adaydır. Paralel hale çizim yordamı için dış Dönüştür `for` içinde döngü `CChildView::DrawMandelbrot` yöntemine yapılan bir çağrı [concurrency::parallel_for](reference/concurrency-namespace-functions.md#parallel_for) şekilde algoritması.  

  
 [!code-cpp[concrt-mandelbrot#301](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_14.cpp)]  
  
 Her bir bit eşlem öğesinin hesaplama bağımsız olduğundan, bit eşlem belleğe erişim çizim görevleri eşitleme gerekmez. Bu, kullanılabilir işlemci artar sayı olarak ölçeklemek performans sağlar.  
  
 [[Üst](#top)]  
  
##  <a name="cancellation"></a> İptal etme desteği ekleme  
 Bu bölümde, pencere yeniden boyutlandırma nasıl ele alınacağını ve pencere bozulduğunda herhangi etkin çizim görevleri iptal etme açıklanmaktadır.  
  
 Belge [PPL'de iptal](cancellation-in-the-ppl.md) İptallerin çalışma zamanı'nda açıklanır. İptal işbirlikçi; Bu nedenle, hemen gerçekleşmez. İptal edilen bir görevi durdurmak için çalışma zamanı bir iç özel durum görevi sonraki çağrı sırasında çalışma zamanı içine oluşturur. Önceki bölümde nasıl kullanılacağını gösterir `parallel_for` çizim görev performansını artırmak için algoritması. Çağrı `parallel_for` görevi durdurmak çalışma zamanı sağlar ve bu nedenle çalışmaya iptal sağlar.  
  
### <a name="cancelling-active-tasks"></a>Etkin görevleri iptal etme  
 Mandelbrot uygulaması oluşturur `Bitmap` olan boyutlar istemci pencere boyutunu eşleşen nesneleri. Uygulama, istemci pencere yeniden boyutlandırılır her zaman, yeni pencere boyutu için görüntü oluşturmak için bir ek arka plan görevi oluşturur. Uygulama Ara bu görüntüleri gerektirmez; yalnızca görüntü son pencere boyutunu gerektiriyor. Bu ek iş gerçekleştirmeyi uygulama önlemek için tüm etkin çizim görevleri için ileti işleyiciler iptal edebilirsiniz `WM_SIZE` ve `WM_SIZING` iletileri ve sonra yeniden çizim penceresi yeniden boyutlandırıldıktan sonra çalışır.  
  
 Pencereyi yeniden boyutlandırıldığında çizim etkin görevleri iptal etmek için uygulama çağırır [concurrency::task_group::cancel](reference/task-group-class.md#cancel) yöntemi işleyiciler için `WM_SIZING` ve `WM_SIZE` iletileri. İşleyicisi `WM_SIZE` iletisi de çağrıları [concurrency::task_group::wait](reference/task-group-class.md#wait) yöntemi tüm etkin tamamlamak için görevler ve güncelleştirilmiş pencere boyutu için çizim görev reschedules için bekleyin.  
  
 İstemci pencere bozulduğunda, tüm etkin çizim görevleri iptal etme iyi bir uygulamadır. Tüm etkin çizim görevleri iptal etme istemci penceresi yok sonra çalışan iş parçacığı kullanıcı Arabirimi iş parçacığı iletileri göndermeyin emin olur. Uygulama işleyicisi hiçbir etkin çizim görevleri iptal `WM_DESTROY` ileti.  
  
### <a name="responding-to-cancellation"></a>İptal için yanıt  
 `CChildView::DrawMandelbrot` Çizim görevi gerçekleştirir, yöntemi iptali için yanıt gerekir. Çalışma zamanı özel durum görevleri iptal etmek işleme kullandığından `CChildView::DrawMandelbrot` yöntemi, tüm kaynakların doğru temizlenmiş emin güvence altına almak için bir özel durum güvenli mekanizması kullanmalıdır. Bu örnekte *kaynak edinme olan başlatma* görev iptal ettiğinizde, bit eşlem BITS kilidi güvence altına almak için (RAII) deseni.  
  
##### <a name="to-add-support-for-cancellation-in-the-mandelbrot-application"></a>Mandelbrot uygulamada iptal desteği ekleme  
  
1.  ChildView.h içinde içinde `protected` bölümünü `CChildView` sınıfı, bildirimler için ekleme `OnSize`, `OnSizing`, ve `OnDestroy` ileti eşlemesi işlevleri.  
  
     [!code-cpp[concrt-mandelbrot#201](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_15.h)]  
  
2.  İleti eşlemesi için işleyiciler içerecek şekilde ChildView.cpp içinde değiştirmek `WM_SIZE`, `WM_SIZING`, ve `WM_DESTROY` iletileri.  
  
     [!code-cpp[concrt-mandelbrot#202](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_16.cpp)]  
  
3.  Uygulama `CChildView::OnSizing` yöntemi. Bu yöntem herhangi bir varolan çizim görevi iptal eder.  
  
     [!code-cpp[concrt-mandelbrot#203](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_17.cpp)]  
  
4.  Uygulama `CChildView::OnSize` yöntemi. Bu yöntem herhangi bir varolan çizim görevi iptal eder ve güncelleştirilmiş istemci pencere boyutu için yeni bir çizim görev oluşturur.  
  
     [!code-cpp[concrt-mandelbrot#204](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_18.cpp)]  
  
5.  Uygulama `CChildView::OnDestroy` yöntemi. Bu yöntem herhangi bir varolan çizim görevi iptal eder.  
  
     [!code-cpp[concrt-mandelbrot#205](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_19.cpp)]  
  
6.  ChildView.cpp içinde tanımlayın `scope_guard` RAII deseni uygular sınıfı.  
  
     [!code-cpp[concrt-mandelbrot#206](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_20.cpp)]  
  
7.  Aşağıdaki kodu ekleyin `CChildView::DrawMandelbrot` yöntemini çağırdıktan sonra `Bitmap::LockBits`:  
  
     [!code-cpp[concrt-mandelbrot#207](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_21.cpp)]  
  
     Bu kod oluşturarak iptalleri işleme bir `scope_guard` nesnesi. Nesne kapsam ayrıldığında, bit eşlem BITS kilidini açar.  
  
8.  Sonuna değiştirme `CChildView::DrawMandelbrot` yöntemi yok sayın `scope_guard` bit eşlem BITS kilidi olduktan sonra ancak tüm iletiler için kullanıcı Arabirimi iş parçacığı gönderilmeden önce nesne. Bu, bit eşlem BITS kilidi önce kullanıcı Arabirimi iş parçacığı güncelleştirilmez sağlar.  
  
     [!code-cpp[concrt-mandelbrot#208](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_22.cpp)]  
  
9. Uygulama oluşturma ve onu çalıştırma başarıyla güncelleştirildi doğrulayın.  
  
 Pencereyi yeniden boyutlandırdığınızda iş çizim yalnızca son pencere boyutu için gerçekleştirilir. Pencere bozulduğunda tüm etkin çizim görevler de iptal edilir.  
  
 [[Üst](#top)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Çalışma zamanı izlenecek yollar](../../parallel/concrt/concurrency-runtime-walkthroughs.md)   
 [Görev Paralelliği](../../parallel/concrt/task-parallelism-concurrency-runtime.md)   
 [Zaman uyumsuz ileti blokları](../../parallel/concrt/asynchronous-message-blocks.md)   
 [İleti geçirme işlevleri](../../parallel/concrt/message-passing-functions.md)   
 [Paralel algoritmalar](../../parallel/concrt/parallel-algorithms.md)   
 [PPL'de iptal](cancellation-in-the-ppl.md)   
 [MFC Masaüstü Uygulamaları](../../mfc/mfc-desktop-applications.md)
