---
title: 'İzlenecek yol: Kullanıcı Arabirimi İş Parçacığından İşi Kaldırma'
ms.date: 08/19/2019
helpviewer_keywords:
- user-interface threads, removing work from [Concurrency Runtime]
- removing work from user-interface threads [Concurrency Runtime]
ms.assetid: a4a65cc2-b3bc-4216-8fa8-90529491de02
ms.openlocfilehash: 52bc98ef339a19c6ec2a53697f532a9a94b6c9a6
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81377437"
---
# <a name="walkthrough-removing-work-from-a-user-interface-thread"></a>İzlenecek yol: Kullanıcı Arabirimi İş Parçacığından İşi Kaldırma

Bu belge, Bir Microsoft Hazırlık Sınıfları (MFC) uygulamasında kullanıcı arabirimi (UI) iş parçacığı tarafından gerçekleştirilen işi bir alt iş parçacığına taşımak için Eşzamanlılık Çalışma Zamanı'nın nasıl kullanılacağını gösterir. Bu belge, uzun bir çizim işleminin performansını nasıl artırılabildiğini de gösterir.

Engelleme işlemlerini boşaltarak çalışmayı Kullanıcı Arabirimi iş parçacığından kaldırmak, örneğin çizim, çalışma iş parçacıklarına uygulamanızın yanıt verme yeteneğini artırabilir. Bu izlenecek yol, uzun bir engelleme işlemi göstermek için Mandelbrot fraktal üreten bir çizim yordamı kullanır. Her pikselin hesaplanması diğer tüm hesaplamalardan bağımsız olduğundan, Mandelbrot fraktal'ın üretimi de paralelleştirme için iyi bir adaydır.

## <a name="prerequisites"></a>Ön koşullar

Bu izbiyi başlatmadan önce aşağıdaki konuları okuyun:

- [Görev Paralelliği](../../parallel/concrt/task-parallelism-concurrency-runtime.md)

- [Zaman Uyumsuz İleti Blokları](../../parallel/concrt/asynchronous-message-blocks.md)

- [İleti Geçirme İşlevleri](../../parallel/concrt/message-passing-functions.md)

- [Paralel Algoritmalar](../../parallel/concrt/parallel-algorithms.md)

- [PPL'de İptal](cancellation-in-the-ppl.md)

Ayrıca, bu gözden geçirmeye başlamadan önce MFC uygulama geliştirme ve GDI+ temellerini anlamanızı öneririz. MFC hakkında daha fazla bilgi için [MFC Masaüstü Uygulamaları'na](../../mfc/mfc-desktop-applications.md)bakın. GDI+ hakkında daha fazla bilgi için [GDI+](/windows/win32/gdiplus/-gdiplus-gdi-start)bilgisine bakın.

## <a name="sections"></a><a name="top"></a>Bölüm

Bu izksiyon aşağıdaki bölümleri içerir:

- [MFC Uygulamasını Oluşturma](#application)

- [Mandelbrot Uygulamasının Seri Sürümünün Uygulanması](#serial)

- [İşi Kullanıcı Arabirimi İş parçacığından kaldırma](#removing-work)

- [Çizim Performansını Artırma](#performance)

- [İptal Için Destek Ekleme](#cancellation)

## <a name="creating-the-mfc-application"></a><a name="application"></a>MFC Uygulamasını Oluşturma

Bu bölümde, temel MFC uygulamasının nasıl oluşturulacak açıklanmaktadır.

### <a name="to-create-a-visual-c-mfc-application"></a>Visual C++ MFC uygulaması oluşturmak için

1. Tüm varsayılan ayarları içeren bir MFC uygulaması oluşturmak için **MFC Uygulama** Sihirbazı'nı kullanın. Visual Studio sürümünüz için sihirbazı nasıl açacağınıza ilişkin talimatlar için [Yeni MFC Shell Denetimlerini kullanma](../../mfc/walkthrough-using-the-new-mfc-shell-controls.md) bölümüne bakın.

1. Örneğin `Mandelbrot`proje için bir ad yazın ve **MFC Uygulama Sihirbazı'nı**görüntülemek için **Tamam'ı** tıklatın.

1. Uygulama **Türü** bölmesinde Tek **belgeyi**seçin. **Belge/Görünüm mimarisi destek** onay kutusunun temizlendiğini sağlayın.

1. Projeyi oluşturmak ve **MFC Uygulama Sihirbazı'nı**kapatmak için **Bitiş'i** tıklatın.

   Uygulamanın oluşturularak ve çalıştırılarak başarıyla oluşturulduğunu doğrulayın. Uygulamayı oluşturmak için **Yapı** menüsünde **Çözüm Oluştur'u**tıklatın. Uygulama başarılı bir şekilde yapılsa, **Hata Ayıklama** Başlat menüsünde **Hata Ayıklama başlat'ı** tıklatarak uygulamayı çalıştırın.

## <a name="implementing-the-serial-version-of-the-mandelbrot-application"></a><a name="serial"></a>Mandelbrot Uygulamasının Seri Sürümünün Uygulanması

Bu bölümde Mandelbrot fraktal çizmek için nasıl açıklanır. Bu sürüm, Mandelbrot fraktal'ı GDI+ [Bitmap](/windows/win32/api/gdiplusheaders/nl-gdiplusheaders-bitmap) nesnesine çeker ve sonra bu bit eşizin içeriğini istemci penceresine kopyalar.

#### <a name="to-implement-the-serial-version-of-the-mandelbrot-application"></a>Mandelbrot uygulamasının seri sürümünü uygulamak için

1. *Pch.h* (Visual Studio 2017 ve önceki yıllarda*stdafx.h)* olarak aşağıdaki `#include` yönergeleri ekleyin:

   [!code-cpp[concrt-mandelbrot#1](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_1.h)]

1. ChildView.h'de, `pragma` yönergeden `BitmapPtr` sonra türü tanımlayın. Tür, `BitmapPtr` bir `Bitmap` nesneye işaretçinin birden çok bileşen tarafından paylaşılmasını sağlar. Nesne `Bitmap` artık herhangi bir bileşen tarafından başvurulduğunda silinir.

   [!code-cpp[concrt-mandelbrot#2](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_2.h)]

1. ChildView.h'de sınıfın bölümüne `protected` `CChildView` aşağıdaki kodu ekleyin:

   [!code-cpp[concrt-mandelbrot#3](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_3.h)]

1. ChildView.cpp'de, aşağıdaki satırları yorumyapın veya kaldırın.

   [!code-cpp[concrt-mandelbrot#4](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_4.cpp)]

   Hata Ayıklama oluştururda, bu adım uygulamanın `DEBUG_NEW` GDI+ ile uyumsuz ayırıcıyı kullanmasını engeller.

1. ChildView.cpp'de `Gdiplus` ad `using` alanına bir yönerge ekleyin.

   [!code-cpp[concrt-mandelbrot#5](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_5.cpp)]

1. GDI+'yı başlatmak ve kapatmak için `CChildView` sınıfın oluşturucusu ve yıkıcısına aşağıdaki kodu ekleyin.

   [!code-cpp[concrt-mandelbrot#6](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_6.cpp)]

1. Yöntemi `CChildView::DrawMandelbrot` uygulayın. Bu yöntem, Belirtilen `Bitmap` nesneye Mandelbrot fraktal çizer.

   [!code-cpp[concrt-mandelbrot#7](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_7.cpp)]

1. Yöntemi `CChildView::OnPaint` uygulayın. Bu yöntem, `CChildView::DrawMandelbrot` `Bitmap` nesnenin içeriğini çağırır ve sonra pencereye kopyalar.

   [!code-cpp[concrt-mandelbrot#8](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_8.cpp)]

1. Uygulamanın bina ve çalıştırılarak başarıyla güncelleştirilerek güncelleştirin.

Aşağıdaki resimde Mandelbrot uygulamasının sonuçları gösterilmektedir.

![Mandelbrot Uygulaması](../../parallel/concrt/media/mandelbrot.png "Mandelbrot Uygulaması")

Her pikselin hesaplaması hesaplama açısından pahalı olduğundan, genel hesaplama bitene kadar ui iş parçacığı ek iletileri işleyemez. Bu, uygulamada yanıt verme yeteneğini azaltabilir. Ancak, ui iş parçacığı çalışma kaldırarak bu sorunu gidermek olabilir.

[[Üst](#top)]

## <a name="removing-work-from-the-ui-thread"></a><a name="removing-work"></a>Çalışmayı UI İş parçacığından kaldırma

Bu bölümde, Mandelbrot uygulamasındaki Kullanıcı Aracı iş parçacığıçizim çalışmasının nasıl kaldırılış edilebildiğini gösterilmektedir. Çizim çalışmasını UI iş parçacığından bir alt iş parçacığına taşıyarak, alt iş parçacığı arka planda görüntüyü oluştururken, UI iş parçacığı iletileri işleyebilir.

Eşzamanlı çalışma süresi görevleri çalıştırmak için üç yol sağlar: [görev grupları,](../../parallel/concrt/task-parallelism-concurrency-runtime.md) [eşzamanlı aracılar](../../parallel/concrt/asynchronous-agents.md)ve [hafif görevler.](../../parallel/concrt/task-scheduler-concurrency-runtime.md) Çalışmayı UI iş parçacığından kaldırmak için bu mekanizmalardan herhangi birini kullanabilirsiniz, ancak bu örnekte [eşzamanlılık::task_group](reference/task-group-class.md) nesnesi kullanılır, çünkü görev grupları iptali destekler. Bu izbis daha sonra, istemci penceresi yeniden boyutlandığında gerçekleştirilen çalışma miktarını azaltmak ve pencere yok edildiğinde temizleme gerçekleştirmek için iptal kullanır.

Bu örnek, ui iş parçacığı ve alt iş parçacığı birbirleriyle iletişim sağlamak için bir [eşzamanlılık kullanır::unbounded_buffer](reference/unbounded-buffer-class.md) nesnesi. Alt iş parçacığı görüntüyü yaptıktan sonra, `Bitmap` `unbounded_buffer` nesneye bir işaretçi gönderir ve sonra ui iş parçacığına bir paint iletisi gönderir. UI iş parçacığı daha `unbounded_buffer` sonra `Bitmap` nesnenesnealır ve istemci penceresine çizer.

#### <a name="to-remove-the-drawing-work-from-the-ui-thread"></a>Çizim çalışmasını UI iş parçacığından kaldırmak için

1. *Pch.h* (Visual Studio 2017 ve önceki yıllarda*stdafx.h)* olarak aşağıdaki `#include` yönergeleri ekleyin:

   [!code-cpp[concrt-mandelbrot#101](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_9.h)]

1. ChildView.h'de `task_group` `CChildView` sınıfın `unbounded_buffer` bölümüne `protected` üye değişkenler ekleyin ve üye değişkenler ekleyin. Nesne `task_group` çizim gerçekleştiren görevleri tutar; `unbounded_buffer` nesne tamamlanmış Mandelbrot görüntüsünü tutar.

   [!code-cpp[concrt-mandelbrot#102](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_10.h)]

1. ChildView.cpp'de `concurrency` ad `using` alanına bir yönerge ekleyin.

   [!code-cpp[concrt-mandelbrot#103](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_11.cpp)]

1. `CChildView::DrawMandelbrot` Yöntemde, çağrıdan `Bitmap::UnlockBits`sonra, eşzamanlılık `Bitmap` çağırın::nesneyi UI iş parçacığına geçirmek için işlev [gönder.](reference/concurrency-namespace-functions.md#send) Ardından, UI iş parçacığına bir paint iletisi gönderin ve istemci alanını geçersiz kılın.

   [!code-cpp[concrt-mandelbrot#104](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_12.cpp)]

1. Güncelleştirilmiş `CChildView::OnPaint` `Bitmap` nesneyi almak ve görüntüyü istemci penceresine çizmek için yöntemi güncelleştirin.

   [!code-cpp[concrt-mandelbrot#105](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_13.cpp)]

   Yöntem, `CChildView::OnPaint` ileti arabelleğinde yoksa Mandelbrot görüntüsünü oluşturmak için bir görev oluşturur. İleti arabelleği, ilk `Bitmap` boya iletisi gibi durumlarda ve istemci penceresinin önüne başka bir pencere taşındığında bir nesne içermez.

1. Uygulamanın bina ve çalıştırılarak başarıyla güncelleştirilerek güncelleştirin.

Çizim çalışması arka planda gerçekleştirildiği için UI artık daha duyarlıdır.

[[Üst](#top)]

## <a name="improving-drawing-performance"></a><a name="performance"></a>Çizim Performansını Artırma

Her pikselin hesaplanması diğer tüm hesaplamalardan bağımsız olduğundan, Mandelbrot fraktal'ın üretimi paralelleştirme için iyi bir adaydır. Çizim yordamını paralelleştirmek için, `for` yöntemdeki `CChildView::DrawMandelbrot` dış döngüyü eşzamanlılık çağrısına dönüştürün::parallel_for algoritması, aşağıdaki gibi. [concurrency::parallel_for](reference/concurrency-namespace-functions.md#parallel_for)

[!code-cpp[concrt-mandelbrot#301](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_14.cpp)]

Her biteşöğesinin hesaplaması bağımsız olduğundan, bitmap belleğine erişen çizim işlemlerini eşitlemeniz gerekmez. Bu, kullanılabilir işlemci sayısı arttıkça performansın ölçeklemesini sağlar.

[[Üst](#top)]

## <a name="adding-support-for-cancellation"></a><a name="cancellation"></a>İptal Için Destek Ekleme

Bu bölümde, pencere yeniden boyutlandırma nasıl işlenir ve pencere yok edildiğinde etkin çizim görevleri nasıl iptal edilir.

[PPL'deki](cancellation-in-the-ppl.md) belge İptal, iptalin çalışma zamanında nasıl çalıştığını açıklar. İptal kooperatiftir; bu nedenle, hemen oluşmaz. İptal edilen bir görevi durdurmak için, çalışma zamanı görevden çalışma süresine sonraki bir arama sırasında bir iç özel durum atar. Önceki bölümde, çizim görevinin `parallel_for` performansını artırmak için algoritmanın nasıl kullanılacağı gösterilmektedir. Arama, `parallel_for` çalışma zamanının görevi durdurmasını sağlar ve bu nedenle iptalin çalışmasını sağlar.

### <a name="cancelling-active-tasks"></a>Etkin Görevleri İptal Etme

Mandelbrot uygulaması, `Bitmap` boyutları istemci penceresinin boyutuyla eşleşen nesneler oluşturur. İstemci penceresi her yeniden boyutlandırılsa, uygulama yeni pencere boyutu için bir görüntü oluşturmak için ek bir arka plan görevi oluşturur. Uygulama bu ara görüntüleri gerektirmez; yalnızca son pencere boyutu için görüntü gerektirir. Uygulamanın bu ek çalışmayı gerçekleştirmesini önlemek için, ileti işleyicileri `WM_SIZE` ve iletiler için etkin çizim görevlerini iptal edebilir ve `WM_SIZING` pencere yeniden boyutlandıktan sonra çizim çalışmasını yeniden zamanlayabilirsiniz.

Pencere yeniden boyutlandığında etkin çizim görevlerini iptal etmek için, uygulama `WM_SIZE` [eşzamanlılık çağırır::task_group::ve](reference/task-group-class.md#cancel) iletileri için `WM_SIZING` işleyicileri yöntemini iptal et. İletinin işleyicisi `WM_SIZE` eşzamanlılığı da [çağırır::task_group::tüm](reference/task-group-class.md#wait) etkin görevlerin tamamlanmasını beklemek için bekleme yöntemi ve ardından güncelleştirilmiş pencere boyutu için çizim görevini yeniden zamanlar.

İstemci penceresi yok edildiğinde, etkin çizim görevlerini iptal etmek iyi bir uygulamadır. Etkin çizim görevlerinin iptali, istemci penceresi yok edildikten sonra alt iş parçacıklarının UI iş parçacığına ileti göndermemesini sağlar. Uygulama, `WM_DESTROY` iletinin işleyicisindeki etkin çizim görevlerini iptal eder.

### <a name="responding-to-cancellation"></a>İptal Yanıtı

Çizim `CChildView::DrawMandelbrot` görevini gerçekleştiren yöntem, iptale yanıt vermelidir. Çalışma zamanı görevleri iptal etmek için `CChildView::DrawMandelbrot` özel durum işleme kullandığından, yöntemtüm kaynakların doğru şekilde temizlenmesini garanti etmek için özel durum güvenli bir mekanizma kullanmalıdır. Bu örnek, görev iptal edildiğinde bit eşlemi bitlerinin kilidinin açılmasını garanti etmek için *Kaynak Edinme Başlatma* (RAII) deseni kullanır.

##### <a name="to-add-support-for-cancellation-in-the-mandelbrot-application"></a>Mandelbrot uygulamasında iptal desteği eklemek için

1. ChildView.h'de, `protected` `CChildView` sınıfın bölümünde `OnSize`, ve `OnSizing` `OnDestroy` ileti eşlemi işlevleri için bildirimler ekleyin.

   [!code-cpp[concrt-mandelbrot#201](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_15.h)]

1. ChildView.cpp'de, ileti eşlemesini `WM_SIZE`, ve `WM_SIZING` `WM_DESTROY` iletileri için işleyiciler içerecek şekilde değiştirin.

   [!code-cpp[concrt-mandelbrot#202](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_16.cpp)]

1. Yöntemi `CChildView::OnSizing` uygulayın. Bu yöntem, varolan çizim görevlerini iptal eder.

   [!code-cpp[concrt-mandelbrot#203](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_17.cpp)]

1. Yöntemi `CChildView::OnSize` uygulayın. Bu yöntem, varolan çizim görevlerini iptal eder ve güncelleştirilmiş istemci penceresi boyutu için yeni bir çizim görevi oluşturur.

   [!code-cpp[concrt-mandelbrot#204](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_18.cpp)]

1. Yöntemi `CChildView::OnDestroy` uygulayın. Bu yöntem, varolan çizim görevlerini iptal eder.

   [!code-cpp[concrt-mandelbrot#205](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_19.cpp)]

1. ChildView.cpp'de, `scope_guard` RAII modelini uygulayan sınıfı tanımlayın.

   [!code-cpp[concrt-mandelbrot#206](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_20.cpp)]

1. Aramadan sonra yönteme `CChildView::DrawMandelbrot` aşağıdaki kodu `Bitmap::LockBits`ekleyin:

   [!code-cpp[concrt-mandelbrot#207](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_21.cpp)]

   Bu kod, bir `scope_guard` nesne oluşturarak iptal iişler. Nesne kapsamdan ayrıldığında, bit eşlemi bitlerinin kilidini açar.

1. Biteş bitleri `CChildView::DrawMandelbrot` açıldıktan `scope_guard` sonra nesneyi kapatmak için yöntemin sonunu değiştirin, ancak iletiler UI iş parçacığına gönderilmeden önce. Bu, bit map bitlerinin kilidi açılmadan önce UI iş parçacığının güncelleştirilememesini sağlar.

   [!code-cpp[concrt-mandelbrot#208](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_22.cpp)]

1. Uygulamanın bina ve çalıştırılarak başarıyla güncelleştirilerek güncelleştirin.

Pencereyi yeniden boyutlandırdığınızda, çizim çalışması yalnızca son pencere boyutu için gerçekleştirilir. Pencere yok edildiğinde etkin çizim görevleri de iptal edilir.

[[Üst](#top)]

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Çalışma Zamanı İzlenecek Yollar](../../parallel/concrt/concurrency-runtime-walkthroughs.md)<br/>
[Görev Paralelliği](../../parallel/concrt/task-parallelism-concurrency-runtime.md)<br/>
[Zaman Uyumsuz İleti Blokları](../../parallel/concrt/asynchronous-message-blocks.md)<br/>
[İleti Geçirme İşlevleri](../../parallel/concrt/message-passing-functions.md)<br/>
[Paralel Algoritmalar](../../parallel/concrt/parallel-algorithms.md)<br/>
[PPL'de İptal](cancellation-in-the-ppl.md)<br/>
[MFC Masaüstü Uygulamaları](../../mfc/mfc-desktop-applications.md)
