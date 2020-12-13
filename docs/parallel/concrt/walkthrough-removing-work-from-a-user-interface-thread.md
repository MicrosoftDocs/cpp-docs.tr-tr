---
description: 'Daha fazla bilgi edinin: Izlenecek yol: User-Interface iş parçacığından kaldırma'
title: 'İzlenecek yol: Kullanıcı Arabirimi İş Parçacığından İşi Kaldırma'
ms.date: 08/19/2019
helpviewer_keywords:
- user-interface threads, removing work from [Concurrency Runtime]
- removing work from user-interface threads [Concurrency Runtime]
ms.assetid: a4a65cc2-b3bc-4216-8fa8-90529491de02
ms.openlocfilehash: 816e8446771cda907397f43386c33476cf3665b8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97340924"
---
# <a name="walkthrough-removing-work-from-a-user-interface-thread"></a>İzlenecek yol: Kullanıcı Arabirimi İş Parçacığından İşi Kaldırma

Bu belge, bir Microsoft Foundation Sınıfları (MFC) uygulamasında kullanıcı arabirimi (UI) iş parçacığı tarafından gerçekleştirilen işi çalışan iş parçacığına taşımak için Eşzamanlılık Çalışma Zamanı nasıl kullanacağınızı gösterir. Bu belgede ayrıca uzun bir çizim işleminin performansının nasıl iyileştireceğiniz gösterilmektedir.

Engelleme işlemlerini boşaltarak (örneğin, çizim) çalışan iş parçacıkları için iş akışı iş parçacığından kaldırma, uygulamanızın yanıt hızını iyileştirebilirler. Bu izlenecek yol, uzun bir engelleme işlemini göstermek için Mandelbrot Fractal 'i oluşturan bir çizim yordamı kullanır. Her bir pikselin hesaplaması diğer tüm hesaplamalarından bağımsız olduğundan, Mandelert Fractal 'in üretilmesi de paralelleştirme için iyi bir adaydır.

## <a name="prerequisites"></a>Önkoşullar

Bu yönergeyi başlamadan önce aşağıdaki konuları okuyun:

- [Görev Paralelliği](../../parallel/concrt/task-parallelism-concurrency-runtime.md)

- [Zaman uyumsuz Ileti blokları](../../parallel/concrt/asynchronous-message-blocks.md)

- [İleti geçirme Işlevleri](../../parallel/concrt/message-passing-functions.md)

- [Paralel algoritmalar](../../parallel/concrt/parallel-algorithms.md)

- [PPL'de İptal](cancellation-in-the-ppl.md)

Ayrıca, bu yönergeyi başlamadan önce MFC uygulama geliştirme ve GDI+ temellerini de anladığınızı öneririz. MFC hakkında daha fazla bilgi için bkz. [MFC masaüstü uygulamaları](../../mfc/mfc-desktop-applications.md). GDI+ hakkında daha fazla bilgi için bkz. [GDI+](/windows/win32/gdiplus/-gdiplus-gdi-start).

## <a name="sections"></a><a name="top"></a> Başlıklı

Bu izlenecek yol aşağıdaki bölümleri içerir:

- [MFC uygulaması oluşturma](#application)

- [Mandelbrot uygulamasının seri sürümünü uygulama](#serial)

- [User-Interface iş parçacığından Iş kaldırılıyor](#removing-work)

- [Çizim performansını iyileştirme](#performance)

- [Iptal için destek ekleme](#cancellation)

## <a name="creating-the-mfc-application"></a><a name="application"></a> MFC uygulaması oluşturma

Bu bölümde, temel MFC uygulamasının nasıl oluşturulacağı açıklanmaktadır.

### <a name="to-create-a-visual-c-mfc-application"></a>Visual C++ MFC uygulaması oluşturmak için

1. Tüm varsayılan ayarlarla bir MFC uygulaması oluşturmak için **MFC Uygulama Sihirbazı** ' nı kullanın. Visual Studio sürümünüz için sihirbazın nasıl açılacağı hakkında yönergeler için bkz. [Izlenecek yol: yenı MFC kabuk denetimlerini kullanma](../../mfc/walkthrough-using-the-new-mfc-shell-controls.md) .

1. Proje için bir ad yazın, örneğin, `Mandelbrot` ve ardından **MFC Uygulama sihirbazını** göstermek için **Tamam** ' a tıklayın.

1. **Uygulama türü** bölmesinde **tek belge**' yi seçin. **Belge/görünüm mimarisi desteği** onay kutusunun temizlenmiş olduğundan emin olun.

1. Projeyi oluşturmak ve **MFC Uygulama Sihirbazı 'nı** kapatmak için **son** ' a tıklayın.

   Uygulamanın oluşturup çalıştırarak başarıyla oluşturulduğunu doğrulayın. Uygulamayı derlemek için, **Yapı** menüsünde **çözüm oluştur**' a tıklayın. Uygulama başarıyla yapılandığında **hata ayıklama** menüsünde **hata ayıklamayı Başlat** ' a tıklayarak uygulamayı çalıştırın.

## <a name="implementing-the-serial-version-of-the-mandelbrot-application"></a><a name="serial"></a> Mandelbrot uygulamasının seri sürümünü uygulama

Bu bölüm, Mandelbrot Fractal 'in nasıl çizileceğini açıklar. Bu sürüm, Mandeli Fractal 'i bir GDI+ [bit eşlem](/windows/win32/api/gdiplusheaders/nl-gdiplusheaders-bitmap) nesnesine çizer ve ardından bu bit eşlemin içeriğini istemci penceresine kopyalar.

#### <a name="to-implement-the-serial-version-of-the-mandelbrot-application"></a>Mandelbrot uygulamasının seri sürümünü uygulamak için

1. *Pch. h* Içinde (Visual Studio 2017 ve önceki sürümlerde *stdadfx. h* ), aşağıdaki yönergeyi ekleyin `#include` :

   [!code-cpp[concrt-mandelbrot#1](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_1.h)]

1. ChildView. h içinde, `pragma` yönergesinden sonra `BitmapPtr` türü tanımlayın. Türü, bir `BitmapPtr` `Bitmap` nesnenin birden çok bileşen tarafından paylaşılabilmesi için bir işaretçi sağlar. `Bitmap`Artık herhangi bir bileşen tarafından başvurulmuyorsa nesne silinir.

   [!code-cpp[concrt-mandelbrot#2](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_2.h)]

1. ChildView. h içinde, sınıfının bölümüne aşağıdaki kodu ekleyin **`protected`** `CChildView` :

   [!code-cpp[concrt-mandelbrot#3](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_3.h)]

1. ChildView. cpp içinde, aşağıdaki satırları açıklama veya kaldırma.

   [!code-cpp[concrt-mandelbrot#4](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_4.cpp)]

   Hata ayıklama yapılarında, bu adım uygulamanın `DEBUG_NEW` GDI+ ile uyumlu olmayan ayırıcıyı kullanmasını önler.

1. ChildView. cpp içinde, **`using`** ad alanına bir yönerge ekleyin `Gdiplus` .

   [!code-cpp[concrt-mandelbrot#5](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_5.cpp)]

1. GDI+ ' yı `CChildView` başlatmak ve kapatmak için aşağıdaki kodu sınıfın oluşturucusuna ve yıkıcılarına ekleyin.

   [!code-cpp[concrt-mandelbrot#6](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_6.cpp)]

1. Yöntemini uygulayın `CChildView::DrawMandelbrot` . Bu yöntem, belirtilen nesneye Mandelbrot Fractal çizer `Bitmap` .

   [!code-cpp[concrt-mandelbrot#7](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_7.cpp)]

1. Yöntemini uygulayın `CChildView::OnPaint` . Bu yöntem, `CChildView::DrawMandelbrot` öğesini çağırır ve sonra `Bitmap` nesnenin içeriğini pencereye kopyalar.

   [!code-cpp[concrt-mandelbrot#8](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_8.cpp)]

1. Uygulamanın oluşturup çalıştırarak başarıyla güncelleştirildiğinden emin olun.

Aşağıdaki çizimde, Mandelbrot uygulamasının sonuçları gösterilmektedir.

![Mandelbrot uygulaması](../../parallel/concrt/media/mandelbrot.png "Mandelbrot uygulaması")

Her pikselin hesaplaması hesaplama açısından pahalı olduğundan, UI iş parçacığı genel hesaplama bitene kadar ek iletileri işleyemez. Bu, uygulamadaki yanıt hızını düşürebilir. Ancak, Kullanıcı arabirimi iş parçacığından iş kaldırarak bu sorunu da ortadan kaldırabilirsiniz.

[[Üst](#top)]

## <a name="removing-work-from-the-ui-thread"></a><a name="removing-work"></a> Kullanıcı arabirimi Iş parçacığından kaldırma

Bu bölüm, çizim işinin Mandelbrot uygulamasındaki UI iş parçacığından nasıl kaldırılacağını gösterir. Çizim işini UI iş parçacığından çalışan iş parçacığına taşıyarak, çalışan iş parçacığı görüntüyü arka planda oluşturduğu için Kullanıcı arabirimi iş parçacığı iletileri işleyebilir.

Eşzamanlılık Çalışma Zamanı görevleri çalıştırmak için üç yol sağlar: [görev grupları](../../parallel/concrt/task-parallelism-concurrency-runtime.md), [zaman uyumsuz aracılar](../../parallel/concrt/asynchronous-agents.md)ve [hafif görevler](../../parallel/concrt/task-scheduler-concurrency-runtime.md). Kullanıcı arabirimi iş parçacığından iş kaldırmak için bu mekanizmalardan herhangi birini kullanabilseniz de, görev grupları iptali desteklediği için bu örnek bir [concurrency:: task_group](reference/task-group-class.md) nesnesi kullanır. Bu izlenecek yol daha sonra, istemci penceresi yeniden boyutlandırılırken gerçekleştirilen iş miktarını azaltmak ve pencere yok edildiğinde temizleme işlemini gerçekleştirmek için iptal 'i kullanır.

Bu örnek ayrıca, Kullanıcı arabirimi iş parçacığını ve çalışan iş parçacığını birbirleriyle iletişim kuracak şekilde etkinleştirmek için bir [concurrency:: unbounded_buffer](reference/unbounded-buffer-class.md) nesnesi kullanır. Çalışan iş parçacığı görüntüyü üretirse, nesnesine nesnesine bir işaretçi gönderir `Bitmap` `unbounded_buffer` ve ardından Kullanıcı arabirimi iş parçacığına bir Paint iletisi gönderir. UI iş parçacığı bundan sonra nesnesinden nesnesinden alır `unbounded_buffer` `Bitmap` ve istemci penceresine çizer.

#### <a name="to-remove-the-drawing-work-from-the-ui-thread"></a>Kullanıcı arabirimi iş parçacığından çizim işini kaldırmak için

1. *Pch. h* Içinde (Visual Studio 2017 ve önceki sürümlerde *stdadfx. h* ), aşağıdaki yönergeleri ekleyin `#include` :

   [!code-cpp[concrt-mandelbrot#101](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_9.h)]

1. ChildView. h içinde, `task_group` `unbounded_buffer` sınıfının bölümüne ve üye değişkenlerini ekleyin **`protected`** `CChildView` . `task_group`Nesne, çizim gerçekleştiren görevleri barındırır; `unbounded_buffer` nesne tamamlanmış Mandelt görüntüsünü tutar.

   [!code-cpp[concrt-mandelbrot#102](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_10.h)]

1. ChildView. cpp içinde, **`using`** ad alanına bir yönerge ekleyin `concurrency` .

   [!code-cpp[concrt-mandelbrot#103](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_11.cpp)]

1. `CChildView::DrawMandelbrot`Yöntemine çağrısından sonra, `Bitmap::UnlockBits` nesneyi UI iş parçacığına iletmek için [concurrency:: Send](reference/concurrency-namespace-functions.md#send) işlevini çağırın `Bitmap` . Ardından Kullanıcı arabirimi iş parçacığına bir Paint iletisi gönderin ve istemci alanını geçersiz kılın.

   [!code-cpp[concrt-mandelbrot#104](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_12.cpp)]

1. `CChildView::OnPaint`Güncelleştirilmiş nesneyi almak için yöntemini güncelleştirin `Bitmap` ve görüntüyü istemci penceresine çizin.

   [!code-cpp[concrt-mandelbrot#105](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_13.cpp)]

   `CChildView::OnPaint`Yöntemi, ileti arabelleğinde yoksa Mandelbrot görüntüsünü oluşturmak için bir görev oluşturur. İleti ara belleği, `Bitmap` ilk Paint iletisi gibi durumlarda ve istemci penceresinin önüne başka bir pencere taşındığında bir nesne içermeyecektir.

1. Uygulamanın oluşturup çalıştırarak başarıyla güncelleştirildiğinden emin olun.

Çizim işi arka planda gerçekleştirildiğinden, Kullanıcı arabirimi artık daha çabuk yanıt verir.

[[Üst](#top)]

## <a name="improving-drawing-performance"></a><a name="performance"></a> Çizim performansını iyileştirme

Her bir pikselin hesaplaması diğer tüm hesaplamalarından bağımsız olduğundan, Mandelert Fractal 'in üretimi paralelleştirme için iyi bir adaydır. Çizim yordamını paralel hale getirmek için, **`for`** yöntemindeki dış döngüyü `CChildView::DrawMandelbrot` aşağıdaki şekilde [eşzamanlılık::p arallel_for](reference/concurrency-namespace-functions.md#parallel_for) algoritmasına bir çağrıya dönüştürün.

[!code-cpp[concrt-mandelbrot#301](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_14.cpp)]

Her bir bit eşlem öğesinin hesaplaması bağımsız olduğundan, bit eşlem belleğine erişen çizim işlemlerini eşitlemeniz gerekmez. Bu, kullanılabilir işlemcilerin sayısı arttıkça performansın ölçeklendirilmesine olanak sağlar.

[[Üst](#top)]

## <a name="adding-support-for-cancellation"></a><a name="cancellation"></a> Iptal için destek ekleme

Bu bölümde pencere yeniden boyutlandırmanın nasıl işleneceği ve pencere yok edildiğinde etkin çizim görevlerinin nasıl iptal edileceği açıklanmaktadır.

[PPL 'de belge iptali](cancellation-in-the-ppl.md) , İptalin çalışma zamanında nasıl çalıştığını açıklar. İptal etme birlikte çalışır; Bu nedenle, hemen gerçekleşmez. İptal edilen bir görevi durdurmak için, çalışma zamanı görevden sonraki bir çağrı sırasında çalışma zamanına bir iç özel durum atar. Önceki bölümde, `parallel_for` Çizim görevinin performansını artırmak için algoritmanın nasıl kullanılacağı gösterilmektedir. ' A yapılan çağrı, `parallel_for` çalışma zamanının görevi durdurmasını sağlar ve bu nedenle İptalin çalışmasına olanak sağlar.

### <a name="cancelling-active-tasks"></a>Etkin görevleri iptal etme

Mandelbrot uygulaması, `Bitmap` boyutları istemci penceresinin boyutuyla eşleşen nesneler oluşturur. İstemci penceresi her yeniden boyutlandırılırken, uygulama yeni pencere boyutu için bir görüntü oluşturmak üzere ek bir arka plan görevi oluşturur. Uygulama bu ara görüntüleri gerektirmez; yalnızca son pencere boyutu için görüntü gerektirir. Uygulamanın bu ek işi gerçekleştirmesini engellemek için, ve iletileri için ileti işleyicilerindeki etkin çizim görevlerini iptal edebilir `WM_SIZE` `WM_SIZING` ve ardından pencere yeniden boyutlandırdıktan sonra çizim işini yeniden zamanlayabilirsiniz.

Pencere yeniden boyutlandırılırken etkin çizim görevlerini iptal etmek için uygulama, ve iletileri için işleyicilerde [concurrency:: task_group:: Cancel](reference/task-group-class.md#cancel) yöntemini çağırır `WM_SIZING` `WM_SIZE` . `WM_SIZE`İleti işleyicisi Ayrıca tüm etkin görevlerin tamamlanmasını beklemek için [concurrency:: task_group:: wait](reference/task-group-class.md#wait) yöntemini çağırır ve sonra güncelleştirilmiş pencere boyutu için çizim görevinin müşteri sizinle randevusunu.

İstemci penceresi yok edildiğinde, etkin çizim görevlerini iptal etmek iyi bir uygulamadır. Etkin çizim görevlerinin iptal edilmesi, çalışan iş parçacıklarının istemci penceresi yok edilirken Kullanıcı arabirimi iş parçacığına ileti göndermediğinden emin olur. Uygulama, ileti için işleyicide etkin olan tüm çizim görevlerini iptal eder `WM_DESTROY` .

### <a name="responding-to-cancellation"></a>Iptal 'e yanıt verme

`CChildView::DrawMandelbrot`Çizim görevini gerçekleştiren yöntemi iptal 'e yanıt vermelidir. Çalışma zamanı görevleri iptal etmek için özel durum işleme kullandığından, `CChildView::DrawMandelbrot` tüm kaynakların doğru şekilde temizlendiğinden emin olmak için yöntemin özel durum güvenli bir mekanizma kullanması gerekir. Bu örnek, görev iptal edildiğinde bit eşlem bitlerinin kilidinin açılması güvence altına almak için *kaynak alımı başlatma* (rampa) modelini kullanır.

##### <a name="to-add-support-for-cancellation-in-the-mandelbrot-application"></a>Mandelbrot uygulamasında iptal desteği eklemek için

1. ChildView. h içinde, **`protected`** sınıfının bölümünde,, `CChildView` `OnSize` `OnSizing` ve `OnDestroy` ileti eşleme işlevlerine yönelik bildirimler ekleyin.

   [!code-cpp[concrt-mandelbrot#201](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_15.h)]

1. ChildView. cpp içinde, ileti eşlemini,, ve iletileri için işleyiciler içerecek şekilde değiştirin `WM_SIZE` `WM_SIZING` `WM_DESTROY` .

   [!code-cpp[concrt-mandelbrot#202](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_16.cpp)]

1. Yöntemini uygulayın `CChildView::OnSizing` . Bu yöntem, varolan çizim görevlerini iptal eder.

   [!code-cpp[concrt-mandelbrot#203](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_17.cpp)]

1. Yöntemini uygulayın `CChildView::OnSize` . Bu yöntem, var olan çizim görevlerini iptal eder ve güncelleştirilmiş istemci pencere boyutu için yeni bir çizim görevi oluşturur.

   [!code-cpp[concrt-mandelbrot#204](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_18.cpp)]

1. Yöntemini uygulayın `CChildView::OnDestroy` . Bu yöntem, varolan çizim görevlerini iptal eder.

   [!code-cpp[concrt-mandelbrot#205](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_19.cpp)]

1. ChildView. cpp içinde, bir `scope_guard` sınıfını tanımlayın.

   [!code-cpp[concrt-mandelbrot#206](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_20.cpp)]

1. Çağrısının ardından yöntemine aşağıdaki kodu ekleyin `CChildView::DrawMandelbrot` `Bitmap::LockBits` :

   [!code-cpp[concrt-mandelbrot#207](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_21.cpp)]

   Bu kod, bir nesnesi oluşturarak iptali işler `scope_guard` . Nesne kapsam dışına çıktığında, bit eşlem bitlerinin kilidini açar.

1. `CChildView::DrawMandelbrot` `scope_guard` Bit eşlem bitleri kilidi açıldıktan sonra, ancak herhangi bir ileti kullanıcı arabirimi iş parçacığına gönderilmeden önce, yöntemi kapatmak için yönteminin sonunu değiştirin. Bu, bit eşlem bitlerinin kilidi açılmadan önce UI iş parçacığının güncelleştirilmesini sağlar.

   [!code-cpp[concrt-mandelbrot#208](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_22.cpp)]

1. Uygulamanın oluşturup çalıştırarak başarıyla güncelleştirildiğinden emin olun.

Pencereyi yeniden boyutlandırdığınızda, çizim işi yalnızca son pencere boyutu için gerçekleştirilir. Pencere yok edildiğinde, etkin çizim görevleri de iptal edilir.

[[Üst](#top)]

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Çalışma Zamanı Izlenecek yollar](../../parallel/concrt/concurrency-runtime-walkthroughs.md)<br/>
[Görev Paralelliği](../../parallel/concrt/task-parallelism-concurrency-runtime.md)<br/>
[Zaman uyumsuz Ileti blokları](../../parallel/concrt/asynchronous-message-blocks.md)<br/>
[İleti geçirme Işlevleri](../../parallel/concrt/message-passing-functions.md)<br/>
[Paralel algoritmalar](../../parallel/concrt/parallel-algorithms.md)<br/>
[PPL'de İptal](cancellation-in-the-ppl.md)<br/>
[MFC masaüstü uygulamaları](../../mfc/mfc-desktop-applications.md)
