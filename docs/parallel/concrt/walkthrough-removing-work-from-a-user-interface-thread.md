---
title: 'İzlenecek yol: Kullanıcı arabirimi Iş parçacığından Iş kaldırma'
ms.date: 04/25/2019
helpviewer_keywords:
- user-interface threads, removing work from [Concurrency Runtime]
- removing work from user-interface threads [Concurrency Runtime]
ms.assetid: a4a65cc2-b3bc-4216-8fa8-90529491de02
ms.openlocfilehash: 214796777968c8aec7116a848e791aeef0d3af7b
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69512258"
---
# <a name="walkthrough-removing-work-from-a-user-interface-thread"></a>İzlenecek yol: Kullanıcı arabirimi Iş parçacığından Iş kaldırma

Bu belge, bir Microsoft Foundation Sınıfları (MFC) uygulamasında kullanıcı arabirimi (UI) iş parçacığı tarafından gerçekleştirilen işi çalışan iş parçacığına taşımak için Eşzamanlılık Çalışma Zamanı nasıl kullanacağınızı gösterir. Bu belgede ayrıca uzun bir çizim işleminin performansının nasıl iyileştireceğiniz gösterilmektedir.

Engelleme işlemlerini boşaltarak (örneğin, çizim) çalışan iş parçacıkları için iş akışı iş parçacığından kaldırma, uygulamanızın yanıt hızını iyileştirebilirler. Bu izlenecek yol, uzun bir engelleme işlemini göstermek için Mandelbrot Fractal 'i oluşturan bir çizim yordamı kullanır. Her bir pikselin hesaplaması diğer tüm hesaplamalarından bağımsız olduğundan, Mandelert Fractal 'in üretilmesi de paralelleştirme için iyi bir adaydır.

## <a name="prerequisites"></a>Önkoşullar

Bu yönergeyi başlamadan önce aşağıdaki konuları okuyun:

- [Görev Paralelliği](../../parallel/concrt/task-parallelism-concurrency-runtime.md)

- [Zaman Uyumsuz İleti Blokları](../../parallel/concrt/asynchronous-message-blocks.md)

- [İleti Geçirme İşlevleri](../../parallel/concrt/message-passing-functions.md)

- [Paralel Algoritmalar](../../parallel/concrt/parallel-algorithms.md)

- [PPL'de İptal](cancellation-in-the-ppl.md)

Ayrıca, bu yönergeyi başlamadan önce MFC uygulama geliştirme ve GDI+ temellerini de anladığınızı öneririz. MFC hakkında daha fazla bilgi için bkz. [MFC masaüstü uygulamaları](../../mfc/mfc-desktop-applications.md). GDI+ hakkında daha fazla bilgi için bkz. [GDI+](/windows/win32/gdiplus/-gdiplus-gdi-start).

##  <a name="top"></a>Başlıklı

Bu izlenecek yol aşağıdaki bölümleri içerir:

- [MFC uygulaması oluşturma](#application)

- [Mandelbrot uygulamasının seri sürümünü uygulama](#serial)

- [Kullanıcı arabirimi Iş parçacığından Iş kaldırma](#removing-work)

- [Çizim performansını iyileştirme](#performance)

- [Iptal için destek ekleme](#cancellation)

##  <a name="application"></a>MFC uygulaması oluşturma

Bu bölümde, temel MFC uygulamasının nasıl oluşturulacağı açıklanmaktadır.

### <a name="to-create-a-visual-c-mfc-application"></a>Bir Visual C++ MFC uygulaması oluşturmak için

1. Tüm varsayılan ayarlarla bir MFC uygulaması oluşturmak için **MFC Uygulama Sihirbazı** ' nı kullanın. Bkz [. İzlenecek yol: Visual Studio sürümünüz için sihirbazın nasıl](../../mfc/walkthrough-using-the-new-mfc-shell-controls.md) açılacağı hakkında yönergeler için yeni MFC kabuk denetimlerini kullanma.

1. Proje için bir ad yazın, örneğin `Mandelbrot`, ve ardından **MFC Uygulama sihirbazını**göstermek için **Tamam** ' a tıklayın.

1. **Uygulama türü** bölmesinde **tek belge**' yi seçin. **Belge/görünüm mimarisi desteği** onay kutusunun temizlenmiş olduğundan emin olun.

1. Projeyi oluşturmak ve **MFC Uygulama Sihirbazı 'nı**kapatmak için **son** ' a tıklayın.

   Uygulamanın oluşturup çalıştırarak başarıyla oluşturulduğunu doğrulayın. Uygulamayı derlemek için, **Yapı** menüsünde **çözüm oluştur**' a tıklayın. Uygulama başarıyla yapılandığında **hata ayıklama** menüsünde **hata ayıklamayı Başlat** ' a tıklayarak uygulamayı çalıştırın.

##  <a name="serial"></a>Mandelbrot uygulamasının seri sürümünü uygulama

Bu bölüm, Mandelbrot Fractal 'in nasıl çizileceğini açıklar. Bu sürüm, Mandeli Fractal 'i bir GDI+ [bit eşlem](/windows/win32/api/gdiplusheaders/nl-gdiplusheaders-bitmap) nesnesine çizer ve ardından bu bit eşlemin içeriğini istemci penceresine kopyalar.

#### <a name="to-implement-the-serial-version-of-the-mandelbrot-application"></a>Mandelbrot uygulamasının seri sürümünü uygulamak için

1. Stbafx. h içinde aşağıdaki `#include` yönergeyi ekleyin:

   [!code-cpp[concrt-mandelbrot#1](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_1.h)]

1. ChildView. h içinde, `pragma` yönergesinden sonra `BitmapPtr` türü tanımlayın. Türü `BitmapPtr` , bir `Bitmap` nesnenin birden çok bileşen tarafından paylaşılabilmesi için bir işaretçi sağlar. Artık herhangi bir bileşen tarafından başvurulmuyorsa nesnesilinir.`Bitmap`

   [!code-cpp[concrt-mandelbrot#2](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_2.h)]

1. ChildView. h içinde, `protected` `CChildView` sınıfının bölümüne aşağıdaki kodu ekleyin:

   [!code-cpp[concrt-mandelbrot#3](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_3.h)]

1. ChildView. cpp içinde, aşağıdaki satırları açıklama veya kaldırma.

   [!code-cpp[concrt-mandelbrot#4](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_4.cpp)]

   Hata ayıklama yapılarında, bu adım uygulamanın GDI+ ile uyumlu olmayan `DEBUG_NEW` ayırıcıyı kullanmasını önler.

1. ChildView. cpp içinde, `using` `Gdiplus` ad alanına bir yönerge ekleyin.

   [!code-cpp[concrt-mandelbrot#5](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_5.cpp)]

1. GDI+ ' yı başlatmak ve kapatmak için aşağıdaki kodu `CChildView` sınıfın oluşturucusuna ve yıkıcılarına ekleyin.

   [!code-cpp[concrt-mandelbrot#6](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_6.cpp)]

1. `CChildView::DrawMandelbrot` Yöntemini uygulayın. Bu yöntem, belirtilen `Bitmap` nesneye Mandelbrot Fractal çizer.

   [!code-cpp[concrt-mandelbrot#7](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_7.cpp)]

1. `CChildView::OnPaint` Yöntemini uygulayın. Bu yöntem, `CChildView::DrawMandelbrot` öğesini çağırır ve sonra `Bitmap` nesnenin içeriğini pencereye kopyalar.

   [!code-cpp[concrt-mandelbrot#8](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_8.cpp)]

1. Uygulamanın oluşturup çalıştırarak başarıyla güncelleştirildiğinden emin olun.

Aşağıdaki çizimde, Mandelbrot uygulamasının sonuçları gösterilmektedir.

![Mandelbrot uygulaması](../../parallel/concrt/media/mandelbrot.png "Mandelbrot uygulaması")

Her pikselin hesaplaması hesaplama açısından pahalı olduğundan, UI iş parçacığı genel hesaplama bitene kadar ek iletileri işleyemez. Bu, uygulamadaki yanıt hızını düşürebilir. Ancak, Kullanıcı arabirimi iş parçacığından iş kaldırarak bu sorunu da ortadan kaldırabilirsiniz.

[[Üst](#top)]

##  <a name="removing-work"></a>Kullanıcı arabirimi Iş parçacığından kaldırma

Bu bölüm, çizim işinin Mandelbrot uygulamasındaki UI iş parçacığından nasıl kaldırılacağını gösterir. Çizim işini UI iş parçacığından çalışan iş parçacığına taşıyarak, çalışan iş parçacığı görüntüyü arka planda oluşturduğu için Kullanıcı arabirimi iş parçacığı iletileri işleyebilir.

Eşzamanlılık Çalışma Zamanı görevleri çalıştırmak için üç yol sağlar: [görev grupları](../../parallel/concrt/task-parallelism-concurrency-runtime.md), [zaman uyumsuz aracılar](../../parallel/concrt/asynchronous-agents.md)ve [hafif görevler](../../parallel/concrt/task-scheduler-concurrency-runtime.md). Kullanıcı arabirimi iş parçacığından iş kaldırmak için bu mekanizmalardan herhangi birini kullanabilseniz de, görev grupları iptali desteklediği için bu örnek bir [concurrency:: task_group](reference/task-group-class.md) nesnesi kullanır. Bu izlenecek yol daha sonra, istemci penceresi yeniden boyutlandırılırken gerçekleştirilen iş miktarını azaltmak ve pencere yok edildiğinde temizleme işlemini gerçekleştirmek için iptal 'i kullanır.

Bu örnek ayrıca UI iş parçacığını ve çalışan iş parçacığını birbirleriyle iletişim kuracak şekilde etkinleştirmek için bir [concurrency:: unbounded_buffer](reference/unbounded-buffer-class.md) nesnesi kullanır. Çalışan iş parçacığı görüntüyü üretirse, nesnesine nesnesine bir işaretçi `Bitmap` `unbounded_buffer` gönderir ve ardından Kullanıcı arabirimi iş parçacığına bir Paint iletisi gönderir. UI iş parçacığı bundan sonra nesnesinden nesnesinden `unbounded_buffer` alır `Bitmap` ve istemci penceresine çizer.

#### <a name="to-remove-the-drawing-work-from-the-ui-thread"></a>Kullanıcı arabirimi iş parçacığından çizim işini kaldırmak için

1. Stbafx. h içinde aşağıdaki `#include` yönergeleri ekleyin:

   [!code-cpp[concrt-mandelbrot#101](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_9.h)]

1. ChildView. h `task_group` içinde, `CChildView` sınıfının `protected` bölümüne `unbounded_buffer` ve üye değişkenlerini ekleyin. Nesne, çizim gerçekleştiren görevleri barındırır `unbounded_buffer` ; nesne tamamlanmış mandelt görüntüsünü tutar. `task_group`

   [!code-cpp[concrt-mandelbrot#102](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_10.h)]

1. ChildView. cpp içinde, `using` `concurrency` ad alanına bir yönerge ekleyin.

   [!code-cpp[concrt-mandelbrot#103](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_11.cpp)]

1. Yöntemine çağrısından sonra, `Bitmap` nesneyi UI iş parçacığına iletmek için [concurrency:: Send](reference/concurrency-namespace-functions.md#send) işlevini çağırın. `Bitmap::UnlockBits` `CChildView::DrawMandelbrot` Ardından Kullanıcı arabirimi iş parçacığına bir Paint iletisi gönderin ve istemci alanını geçersiz kılın.

   [!code-cpp[concrt-mandelbrot#104](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_12.cpp)]

1. `CChildView::OnPaint` Güncelleştirilmiş`Bitmap` nesneyi almak için yöntemini güncelleştirin ve görüntüyü istemci penceresine çizin.

   [!code-cpp[concrt-mandelbrot#105](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_13.cpp)]

   `CChildView::OnPaint` Yöntemi, ileti arabelleğinde yoksa Mandelbrot görüntüsünü oluşturmak için bir görev oluşturur. İleti ara belleği, ilk Paint iletisi `Bitmap` gibi durumlarda ve istemci penceresinin önüne başka bir pencere taşındığında bir nesne içermeyecektir.

1. Uygulamanın oluşturup çalıştırarak başarıyla güncelleştirildiğinden emin olun.

Çizim işi arka planda gerçekleştirildiğinden, Kullanıcı arabirimi artık daha çabuk yanıt verir.

[[Üst](#top)]

##  <a name="performance"></a>Çizim performansını iyileştirme

Her bir pikselin hesaplaması diğer tüm hesaplamalarından bağımsız olduğundan, Mandelert Fractal 'in üretimi paralelleştirme için iyi bir adaydır. Çizim yordamını paralel hale getirmek için, `for` `CChildView::DrawMandelbrot` yöntemindeki dış döngüyü aşağıdaki şekilde [eşzamanlılık::p arallel_for](reference/concurrency-namespace-functions.md#parallel_for) algoritmasına bir çağrıya dönüştürün.

[!code-cpp[concrt-mandelbrot#301](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_14.cpp)]

Her bir bit eşlem öğesinin hesaplaması bağımsız olduğundan, bit eşlem belleğine erişen çizim işlemlerini eşitlemeniz gerekmez. Bu, kullanılabilir işlemcilerin sayısı arttıkça performansın ölçeklendirilmesine olanak sağlar.

[[Üst](#top)]

##  <a name="cancellation"></a>Iptal için destek ekleme

Bu bölümde pencere yeniden boyutlandırmanın nasıl işleneceği ve pencere yok edildiğinde etkin çizim görevlerinin nasıl iptal edileceği açıklanmaktadır.

[PPL 'de belge iptali](cancellation-in-the-ppl.md) , İptalin çalışma zamanında nasıl çalıştığını açıklar. İptal etme birlikte çalışır; Bu nedenle, hemen gerçekleşmez. İptal edilen bir görevi durdurmak için, çalışma zamanı görevden sonraki bir çağrı sırasında çalışma zamanına bir iç özel durum atar. Önceki bölümde, çizim görevinin performansını artırmak için `parallel_for` algoritmanın nasıl kullanılacağı gösterilmektedir. ' A yapılan `parallel_for` çağrı, çalışma zamanının görevi durdurmasını sağlar ve bu nedenle İptalin çalışmasına olanak sağlar.

### <a name="cancelling-active-tasks"></a>Etkin görevleri iptal etme

Mandelbrot uygulaması, boyutları `Bitmap` istemci penceresinin boyutuyla eşleşen nesneler oluşturur. İstemci penceresi her yeniden boyutlandırılırken, uygulama yeni pencere boyutu için bir görüntü oluşturmak üzere ek bir arka plan görevi oluşturur. Uygulama bu ara görüntüleri gerektirmez; yalnızca son pencere boyutu için görüntü gerektirir. Uygulamanın bu ek işi gerçekleştirmesini engellemek için, `WM_SIZE` ve `WM_SIZING` iletileri için ileti işleyicilerindeki etkin çizim görevlerini iptal edebilir ve ardından pencere yeniden boyutlandırdıktan sonra çizim işini yeniden zamanlayabilirsiniz.

Pencere yeniden boyutlandırılırken etkin çizim görevlerini iptal etmek için, uygulama işleyicilerde `WM_SIZING` ve `WM_SIZE` iletileri için [concurrency:: task_group:: Cancel](reference/task-group-class.md#cancel) metodunu çağırır. `WM_SIZE` İleti işleyicisi Ayrıca tüm etkin görevlerin tamamlanmasını beklemek için [concurrency:: task_group:: wait](reference/task-group-class.md#wait) yöntemini çağırır ve sonra güncelleştirilmiş pencere boyutu için çizim görevini müşteri sizinle randevusunu.

İstemci penceresi yok edildiğinde, etkin çizim görevlerini iptal etmek iyi bir uygulamadır. Etkin çizim görevlerinin iptal edilmesi, çalışan iş parçacıklarının istemci penceresi yok edilirken Kullanıcı arabirimi iş parçacığına ileti göndermediğinden emin olur. Uygulama, `WM_DESTROY` ileti için işleyicide etkin olan tüm çizim görevlerini iptal eder.

### <a name="responding-to-cancellation"></a>Iptal 'e yanıt verme

Çizim görevini gerçekleştiren yöntemi iptal 'e yanıt vermelidir. `CChildView::DrawMandelbrot` Çalışma zamanı görevleri iptal etmek için özel durum işleme kullandığından, `CChildView::DrawMandelbrot` tüm kaynakların doğru şekilde temizlendiğinden emin olmak için yöntemin özel durum güvenli bir mekanizma kullanması gerekir. Bu örnek, görev iptal edildiğinde bit eşlem bitlerinin kilidinin açılması güvence altına almak için *kaynak alımı başlatma* (rampa) modelini kullanır.

##### <a name="to-add-support-for-cancellation-in-the-mandelbrot-application"></a>Mandelbrot uygulamasında iptal desteği eklemek için

1. ChildView. h `protected` içinde `OnDestroy` , `CChildView` sınıfının bölümünde,, ve ileti eşleme işlevlerine yönelik `OnSize` `OnSizing`bildirimler ekleyin.

   [!code-cpp[concrt-mandelbrot#201](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_15.h)]

1. ChildView. cpp içinde, ileti eşlemini `WM_SIZE`, `WM_SIZING`, ve `WM_DESTROY` iletileri için işleyiciler içerecek şekilde değiştirin.

   [!code-cpp[concrt-mandelbrot#202](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_16.cpp)]

1. `CChildView::OnSizing` Yöntemini uygulayın. Bu yöntem, varolan çizim görevlerini iptal eder.

   [!code-cpp[concrt-mandelbrot#203](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_17.cpp)]

1. `CChildView::OnSize` Yöntemini uygulayın. Bu yöntem, var olan çizim görevlerini iptal eder ve güncelleştirilmiş istemci pencere boyutu için yeni bir çizim görevi oluşturur.

   [!code-cpp[concrt-mandelbrot#204](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_18.cpp)]

1. `CChildView::OnDestroy` Yöntemini uygulayın. Bu yöntem, varolan çizim görevlerini iptal eder.

   [!code-cpp[concrt-mandelbrot#205](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_19.cpp)]

1. ChildView. cpp içinde, bir `scope_guard` sınıfını tanımlayın.

   [!code-cpp[concrt-mandelbrot#206](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_20.cpp)]

1. Çağrısının ardından `CChildView::DrawMandelbrot` yöntemine aşağıdaki kodu ekleyin: `Bitmap::LockBits`

   [!code-cpp[concrt-mandelbrot#207](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_21.cpp)]

   Bu kod, bir `scope_guard` nesnesi oluşturarak iptali işler. Nesne kapsam dışına çıktığında, bit eşlem bitlerinin kilidini açar.

1. Bit eşlem bitleri kilidi açıldıktan `CChildView::DrawMandelbrot` sonra, ancak herhangi `scope_guard` bir ileti kullanıcı arabirimi iş parçacığına gönderilmeden önce, yöntemi kapatmak için yönteminin sonunu değiştirin. Bu, bit eşlem bitlerinin kilidi açılmadan önce UI iş parçacığının güncelleştirilmesini sağlar.

   [!code-cpp[concrt-mandelbrot#208](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_22.cpp)]

9. Uygulamanın oluşturup çalıştırarak başarıyla güncelleştirildiğinden emin olun.

Pencereyi yeniden boyutlandırdığınızda, çizim işi yalnızca son pencere boyutu için gerçekleştirilir. Pencere yok edildiğinde, etkin çizim görevleri de iptal edilir.

[[Üst](#top)]

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Çalışma Zamanı İzlenecek Yollar](../../parallel/concrt/concurrency-runtime-walkthroughs.md)<br/>
[Görev Paralelliği](../../parallel/concrt/task-parallelism-concurrency-runtime.md)<br/>
[Zaman Uyumsuz İleti Blokları](../../parallel/concrt/asynchronous-message-blocks.md)<br/>
[İleti Geçirme İşlevleri](../../parallel/concrt/message-passing-functions.md)<br/>
[Paralel Algoritmalar](../../parallel/concrt/parallel-algorithms.md)<br/>
[PPL'de İptal](cancellation-in-the-ppl.md)<br/>
[MFC Masaüstü Uygulamaları](../../mfc/mfc-desktop-applications.md)
