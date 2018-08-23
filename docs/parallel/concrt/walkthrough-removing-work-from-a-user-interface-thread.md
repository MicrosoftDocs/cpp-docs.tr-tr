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
ms.openlocfilehash: e3da35d2134daa20faf53336902ba6612f4b9904
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42612109"
---
# <a name="walkthrough-removing-work-from-a-user-interface-thread"></a>İzlenecek yol: Kullanıcı Arabirimi İş Parçacığından İşi Kaldırma
Bu belge, bir çalışan iş parçacığı için Microsoft Foundation Classes (MFC) uygulamasında kullanıcı arabirimi (UI) iş parçacığı tarafından gerçekleştirilen iş taşımak için eşzamanlılık çalışma zamanı nasıl yapılacağı açıklanır. Bu belge ayrıca uzun bir çizim işlem performansını gösterir.  
  
 İş, engelleme işlemleri boşaltarak UI iş parçacığından işi kaldırma, örneğin, çizim, çalışan iş parçacıkları için uygulamanızın yanıt hızını artırabilirsiniz. Bu izlenecek yolda engelleme kilitlemekten göstermek için Mandelbrot düzgünleştiren parçalı oluşturan çizim bir yordamı kullanır. Her pikselin hesaplama diğer tüm hesaplamaları bağımsız Mandelbrot düzgünleştiren parçalı oluşturulmasını da paralelleştirme için iyi bir aday olduğundan.  
  
## <a name="prerequisites"></a>Önkoşullar  
 Bu kılavuza başlamadan önce aşağıdaki konuları okuyun:  
  
-   [Görev Paralelliği](../../parallel/concrt/task-parallelism-concurrency-runtime.md)  
  
-   [Zaman Uyumsuz İleti Blokları](../../parallel/concrt/asynchronous-message-blocks.md)  
  
-   [İleti Geçirme İşlevleri](../../parallel/concrt/message-passing-functions.md)  
  
-   [Paralel Algoritmalar](../../parallel/concrt/parallel-algorithms.md)  
  
-   [PPL'de İptal](cancellation-in-the-ppl.md)  
  
 Ayrıca bu kılavuza başlamadan önce MFC Uygulama geliştirme ve GDI + temellerini anladığınızı öneririz. MFC hakkında daha fazla bilgi için bkz: [MFC Masaüstü uygulamaları](../../mfc/mfc-desktop-applications.md). GDI + hakkında daha fazla bilgi için bkz: [GDI +](https://msdn.microsoft.com/en-us/library/windows/desktop/ms533798).  
  
##  <a name="top"></a> Bölümleri  
 Bu izlenecek yol aşağıdaki bölümleri içerir:  
  
-   [MFC uygulaması oluşturma](#application)  
  
-   [Uygulama seri Mandelbrot uygulama sürümü](#serial)  
  
-   [Kullanıcı arabirimi iş parçacığından işi kaldırma](#removing-work)  
  
-   [Çizim performansı artırma](#performance)  
  
-   [İptal için destek ekleme](#cancellation)  
  
##  <a name="application"></a> MFC uygulaması oluşturma  
 Bu bölümde, temel MFC uygulaması oluşturma işlemini açıklar.  
  
### <a name="to-create-a-visual-c-mfc-application"></a>Bir Visual C++ MFC uygulaması oluşturmak için  
  
1.  Üzerinde **dosya** menüsünde tıklatın **yeni**ve ardından **proje**.  
  
2.  İçinde **yeni proje** iletişim kutusundaki **yüklü şablonlar** bölmesinde **Visual C++** ve ardından **şablonları** bölmesinde seçin **MFC uygulaması**. Proje için bir ad yazın örneğin, `Mandelbrot`ve ardından **Tamam** görüntülenecek **MFC Uygulama Sihirbazı**.  
  
3.  İçinde **uygulama türü** bölmesinde **tek belge**. Emin **belge/görünüm mimarisi desteği** onay kutusu işaretli değilse.  
  
4.  Tıklayın **son** projeyi oluşturmak ve kapatmak için **MFC Uygulama Sihirbazı**.  
  
     Oluşturma ve çalışan uygulamanın başarıyla oluşturulduğunu doğrulayın. Uygulama derlemek için **derleme** menüsünde tıklatın **Çözümü Derle**. Uygulama başarıyla derlenirse tıklayarak uygulamayı çalıştırmak **hata ayıklamayı Başlat** üzerinde **hata ayıklama** menüsü.  
  
##  <a name="serial"></a> Uygulama seri Mandelbrot uygulama sürümü  
 Bu bölümde, Mandelbrot düzgünleştiren parçalı çizmek kullanılan nasıl açıklanmaktadır. Bu sürüm Mandelbrot düzgünleştiren parçalı bir GDI + çizer [bit eşlem](/windows/desktop/api/gdiplusheaders/nl-gdiplusheaders-bitmap) nesnesi ve ardından istemci penceresine, bit eşlem içeriğini kopyalar.  
  
#### <a name="to-implement-the-serial-version-of-the-mandelbrot-application"></a>Seri Mandelbrot uygulamanın sürümünü uygulamak için  
  
1.  Stdafx.h içinde aşağıdaki ekleme `#include` yönergesi:  
  
     [!code-cpp[concrt-mandelbrot#1](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_1.h)]  
  
2.  İçinde ChildView.h, sonra `pragma` yönergesi, tanımlama `BitmapPtr` türü. `BitmapPtr` Türü bir işaretçi sağlayan bir `Bitmap` birden çok bileşen tarafından paylaşılacak nesne. `Bitmap` Nesne artık herhangi bir bileşen tarafından başvurulduğunda silinir.  
  
     [!code-cpp[concrt-mandelbrot#2](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_2.h)]  
  
3.  ChildView.h içinde aşağıdaki kodu ekleyin `protected` bölümünü `CChildView` sınıfı:  
  
     [!code-cpp[concrt-mandelbrot#3](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_3.h)]  
  
4.  ChildView.cpp, açıklama satırı yapın veya aşağıdaki satırları kaldırın.  
  
     [!code-cpp[concrt-mandelbrot#4](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_4.cpp)]  
  
     Hata ayıklama yapılarında, bu adımı kullanarak uygulamanın engeller `DEBUG_NEW` GDI +'ile uyumsuz olan ayırıcı.  
  
5.  ChildView.cpp içinde ekleme bir `using` yönergesini `Gdiplus` ad alanı.  
  
     [!code-cpp[concrt-mandelbrot#5](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_5.cpp)]  
  
6.  Oluşturucu ve yıkıcı, için aşağıdaki kodu ekleyin `CChildView` başlatmak ve GDI + kapatmak için sınıf.  
  
     [!code-cpp[concrt-mandelbrot#6](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_6.cpp)]  
  
7.  Uygulama `CChildView::DrawMandelbrot` yöntemi. Bu yöntem Mandelbrot düzgünleştiren parçalı belirtilen çizer `Bitmap` nesne.  
  
     [!code-cpp[concrt-mandelbrot#7](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_7.cpp)]  
  
8.  Uygulama `CChildView::OnPaint` yöntemi. Bu yöntemin çağırdığı `CChildView::DrawMandelbrot` ve ardından içeriğini kopyalar `Bitmap` pencereye bir nesne.  
  
     [!code-cpp[concrt-mandelbrot#8](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_8.cpp)]  
  
9. Oluşturmaya ve çalıştırmaya uygulama başarıyla güncelleştirildiğini doğrulayın.  
  
 Aşağıdaki çizim Mandelbrot uygulama sonuçları gösterilmektedir.  
  
 ![Mandelbrot uygulama](../../parallel/concrt/media/mandelbrot.png "mandelbrot")  
  
 Hesaplama için her piksel hesaplama açısından pahalı olduğundan, genel hesaplama bitmeden UI iş parçacığı ek iletiler işleyemiyor. Bu uygulama yanıtlama hızını azaltır. Ancak, bu sorunu UI iş parçacığından işi kaldırma tarafından hafifletmek.  
  
 [[Üst](#top)]  
  
##  <a name="removing-work"></a> UI iş parçacığından işi kaldırma  
 Bu bölümde, Mandelbrot uygulama kullanıcı Arabirimi iş parçacığında çizim iş kaldırma işlemi gösterilmektedir. Bir iş parçacığı UI iş parçacığından çizim iş taşıyarak, arka planda çalışan iş parçacığı görüntü oluştururken UI iş parçacığı iletileri işleyebilir.  
  
 Eşzamanlılık Çalışma zamanı görevleri çalıştırmak için üç yol sunar: [görev grupları](../../parallel/concrt/task-parallelism-concurrency-runtime.md), [zaman uyumsuz aracılar](../../parallel/concrt/asynchronous-agents.md), ve [Basit görevler](../../parallel/concrt/task-scheduler-concurrency-runtime.md). UI iş parçacığından iş kaldırmak için Bu mekanizmaların birini kullanabilirsiniz, ancak bu örnekte bir [concurrency::task_group](reference/task-group-class.md) görev grupları iptali desteklediğinden nesne. Bu izlenecek yol, daha sonra istemci penceresi yeniden boyutlandırıldığında gerçekleştirilen iş miktarını azaltmaya ve pencerenin kaldırıldığında temizleme işlemini gerçekleştirmek için İptal kullanır.  
  
 Bu örnekte ayrıca bir [concurrency::unbounded_buffer](reference/unbounded-buffer-class.md) UI iş parçacığı ve birbirleri ile iletişim kurmak için iş parçacığı etkinleştirmek için nesne. Çalışan iş parçacığı görüntü üretiyor sonra bir işaretçi gönderdiği `Bitmap` nesnesini `unbounded_buffer` nesnesi ve ardından UI iş parçacığına bir boyama iletisi gönderir. UI iş parçacığı ardından gelen alan `unbounded_buffer` nesne `Bitmap` nesne ve istemci penceresine çizer.  
  
#### <a name="to-remove-the-drawing-work-from-the-ui-thread"></a>UI iş parçacığından çizim iş kaldırmak için  
  
1.  Stdafx.h içinde aşağıdaki ekleme `#include` yönergeleri:  
  
     [!code-cpp[concrt-mandelbrot#101](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_9.h)]  
  
2.  ChildView.h içinde ekleme `task_group` ve `unbounded_buffer` üye değişkenlerine `protected` bölümünü `CChildView` sınıfı. `task_group` Nesnesi tutar; çizim gerçekleştirdiği görevleri `unbounded_buffer` nesnesi tamamlanmış Mandelbrot görüntüsü tutar.  
  
     [!code-cpp[concrt-mandelbrot#102](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_10.h)]  
  
3.  ChildView.cpp içinde ekleme bir `using` yönergesini `concurrency` ad alanı.  
  
     [!code-cpp[concrt-mandelbrot#103](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_11.cpp)]  
  

4.  İçinde `CChildView::DrawMandelbrot` yöntem çağrısından sonra `Bitmap::UnlockBits`, çağrı [concurrency::send](reference/concurrency-namespace-functions.md#send) geçirilecek işlevi `Bitmap` UI iş parçacığı için nesne. Ardından UI iş parçacığı Boya ileti gönderin ve istemci alanı geçersiz.  

  
     [!code-cpp[concrt-mandelbrot#104](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_12.cpp)]  
  
5.  Güncelleştirme `CChildView::OnPaint` güncelleştirilmiş almak üzere yöntemini `Bitmap` nesne ve istemci penceresine görüntü çizin.  
  
     [!code-cpp[concrt-mandelbrot#105](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_13.cpp)]  
  
     `CChildView::OnPaint` Yöntemi, bir iletiyi arabelleğe mevcut değilse Mandelbrot görüntü oluşturmak için bir görev oluşturur. İleti arabelleği değil içerecek bir `Bitmap` durumlarda örneğin ilk boyama iletisi ve istemci penceresi önüne başka bir pencere taşındığında nesne.  
  
6.  Oluşturmaya ve çalıştırmaya uygulama başarıyla güncelleştirildiğini doğrulayın.  
  
 Çizim iş arka planda gerçekleştirildiği için kullanıcı Arabirimi artık daha hızlı yanıt.  
  
 [[Üst](#top)]  
  
##  <a name="performance"></a> Çizim performansı artırma  

 Her pikselin hesaplama diğer tüm hesaplamaları bağımsız olduğundan nesil Mandelbrot düzgünleştiren parçalı paralelleştirme için iyi bir adaydır. Çizim yordamı paralel hale getirmek için dış dönüştürme `for` içinde döngü `CChildView::DrawMandelbrot` yöntemine bir çağrı [concurrency::parallel_for](reference/concurrency-namespace-functions.md#parallel_for) aşağıdaki gibi bir algoritma.  

  
 [!code-cpp[concrt-mandelbrot#301](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_14.cpp)]  
  
 Her bir bit eşlem öğesinin hesaplama bağımsız olduğundan, bit eşlem bellek erişim çizim işlemlerini eşitlemeniz gerekmez. Bu performans sayısı arttıkça kullanılabilir işlemci ölçeklendirme sağlar.  
  
 [[Üst](#top)]  
  
##  <a name="cancellation"></a> İptal için destek ekleme  
 Bu bölümde, pencereyi yeniden boyutlandırma nasıl ele alınacağını ve pencerenin kaldırıldığında tüm etkin çizim görevleri iptal etme açıklanmaktadır.  
  
 Belge [ppl'de iptal](cancellation-in-the-ppl.md) iptal çalışma zamanında nasıl çalıştığını açıklar. İptali ortaktır; Bu nedenle, hemen gerçekleşmez. İptal edilen bir görev durdurmak için Çalışma Zamanı Modülü çalışma zamanı içinde görev sonraki çağrı sırasında iç özel durum oluşturur. Önceki bölümde nasıl kullanılacağını gösterir `parallel_for` çizim görev performansını artırmak için algoritma. Çağrı `parallel_for` görevi durdurmak çalışma zamanı sağlar ve bu nedenle iptal çalışacak şekilde etkinleştirir.  
  
### <a name="cancelling-active-tasks"></a>Etkin görevleri iptal ediliyor  
 Mandelbrot uygulaması oluşturan `Bitmap` boyutlarının istemci penceresinin boyutunu eşleşen nesneleri. Her seferinde istemci penceresi yeniden boyutlandırılırken, uygulamanın yeni pencere boyutu için bir görüntü oluşturmak için bir ek arka plan görevi oluşturur. Uygulama Ara görüntülerin gerektirmez; yalnızca görüntü için son pencere boyutu gerektirir. Bu ek işlemler gerçekleştirme uygulamanın önlemek için ileti işleyicileri için tüm etkin çizim görevleri iptal edebilirsiniz `WM_SIZE` ve `WM_SIZING` iletileri ve sonra yeniden çizim pencereyi yeniden boyutlandırıldıktan sonra çalışır.  
  
 Pencereyi yeniden boyutlandırıldığında çizim etkin görevleri iptal etmek için uygulamayı çağırır [concurrency::task_group::cancel](reference/task-group-class.md#cancel) işleyicileri yönteminde `WM_SIZING` ve `WM_SIZE` iletileri. İşleyici için `WM_SIZE` iletisi ayrıca çağrıları [CONCURRENCY::task_group:: wait](reference/task-group-class.md#wait) tüm etkin görevleri tamamlamak için ve ardından güncelleştirilmiş pencere boyutu için çizim görev tarih değiştirdiğinde bekleme için yöntemi.  
  
 İstemci penceresi kaldırıldığında, bu herhangi bir etkin çizim görevi iptal etmek iyi bir uygulamadır. Tüm etkin çizim görevleri iptal etme istemci penceresi yok sonra çalışan iş parçacığı UI iş parçacığı iletileri göndermeyin emin olur. Uygulama işleyicisindeki çizim herhangi etkin görevleri iptal `WM_DESTROY` ileti.  
  
### <a name="responding-to-cancellation"></a>İptal için yanıtlama  
 `CChildView::DrawMandelbrot` Çizim görev gerçekleştiren yöntemi iptal için yanıt gerekir. Çalışma zamanı özel durum görevleri iptal etmek için işleme kullandığından `CChildView::DrawMandelbrot` yöntemi, tüm kaynaklarının doğru temizlenmiş emin güvence altına almak için bir özel durum açısından güvenli mekanizması kullanmalıdır. Bu örnekte *olduğu kaynak alımı başlatma* görev iptal edildiğinde, bit eşlem bitleri kilidi güvence altına almak için (RAII) deseni.  
  
##### <a name="to-add-support-for-cancellation-in-the-mandelbrot-application"></a>Mandelbrot uygulamada iptal için destek eklemek için  
  
1.  İçinde ChildView.h, içinde `protected` bölümünü `CChildView` sınıfı, bildirimler için ekleme `OnSize`, `OnSizing`, ve `OnDestroy` ileti eşlemesi işlevleri.  
  
     [!code-cpp[concrt-mandelbrot#201](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_15.h)]  
  
2.  İleti eşlemesi için işleyiciler içerecek şekilde ChildView.cpp içinde değiştirmek `WM_SIZE`, `WM_SIZING`, ve `WM_DESTROY` iletileri.  
  
     [!code-cpp[concrt-mandelbrot#202](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_16.cpp)]  
  
3.  Uygulama `CChildView::OnSizing` yöntemi. Bu yöntem herhangi bir mevcut çizim görevi iptal eder.  
  
     [!code-cpp[concrt-mandelbrot#203](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_17.cpp)]  
  
4.  Uygulama `CChildView::OnSize` yöntemi. Bu yöntem herhangi bir mevcut çizim görevi iptal eder ve güncelleştirilmiş istemci pencere boyutu için yeni bir çizim görev oluşturur.  
  
     [!code-cpp[concrt-mandelbrot#204](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_18.cpp)]  
  
5.  Uygulama `CChildView::OnDestroy` yöntemi. Bu yöntem herhangi bir mevcut çizim görevi iptal eder.  
  
     [!code-cpp[concrt-mandelbrot#205](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_19.cpp)]  
  
6.  ChildView.cpp içinde tanımlayın `scope_guard` RAII deseni uygulayan bir sınıf.  
  
     [!code-cpp[concrt-mandelbrot#206](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_20.cpp)]  
  
7.  Aşağıdaki kodu ekleyin `CChildView::DrawMandelbrot` yöntem çağrısından sonra `Bitmap::LockBits`:  
  
     [!code-cpp[concrt-mandelbrot#207](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_21.cpp)]  
  
     Bu kod oluşturarak iptal işleme bir `scope_guard` nesne. Nesne kapsam dışına çıktığında, bit eşlem bitleri kilidini açar.  
  
8.  Sonuna değiştirme `CChildView::DrawMandelbrot` kapatmak için yöntemi `scope_guard` bit eşlem bitleri kilitsiz sonra ancak kullanıcı Arabirimi iş parçacığına herhangi bir ileti gönderilmeden önce nesne. Bu, bit eşlem bitleri kilidi olmadan önce UI iş parçacığı güncelleştirilmez sağlar.  
  
     [!code-cpp[concrt-mandelbrot#208](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_22.cpp)]  
  
9. Oluşturmaya ve çalıştırmaya uygulama başarıyla güncelleştirildiğini doğrulayın.  
  
 İş çizim penceresini yeniden boyutlandırdığınızda, yalnızca son pencere boyutunu gerçekleştirilir. Pencerenin kaldırıldığında tüm etkin çizim görevleri de iptal edilir.  
  
 [[Üst](#top)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Çalışma zamanı izlenecek yollar](../../parallel/concrt/concurrency-runtime-walkthroughs.md)   
 [Görev Paralelliği](../../parallel/concrt/task-parallelism-concurrency-runtime.md)   
 [Zaman uyumsuz ileti blokları](../../parallel/concrt/asynchronous-message-blocks.md)   
 [İleti geçirme işlevleri](../../parallel/concrt/message-passing-functions.md)   
 [Paralel algoritmalar](../../parallel/concrt/parallel-algorithms.md)   
 [Ppl'de iptal](cancellation-in-the-ppl.md)   
 [MFC Masaüstü Uygulamaları](../../mfc/mfc-desktop-applications.md)
