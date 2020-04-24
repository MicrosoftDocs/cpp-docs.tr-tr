---
title: 'İzlenecek yol: Görevleri ve XML HTTP İsteklerini Kullanarak Bağlanma'
ms.date: 04/25/2019
helpviewer_keywords:
- connecting to web services, UWP apps [C++]
- IXMLHTTPRequest2 and tasks, example
- IXHR2 and tasks, example
ms.assetid: e8e12d46-604c-42a7-abfd-b1d1bb2ed6b3
ms.openlocfilehash: 2c627a543ec18702bf5358ff0170bec177fd7497
ms.sourcegitcommit: 89d9e1cb08fa872483d1cde98bc2a7c870e505e9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "82032271"
---
# <a name="walkthrough-connecting-using-tasks-and-xml-http-requests"></a>İzlenecek yol: Görevleri ve XML HTTP İsteklerini Kullanarak Bağlanma

Bu örnek, [IXMLHTTPRequest2](/windows/win32/api/msxml6/nn-msxml6-ixmlhttprequest2) ve [IXMLHTTPRequest2Callback](/windows/win32/api/msxml6/nn-msxml6-ixmlhttprequest2callback) arabirimlerinin, EVRENSEL Windows Platformu (UWP) uygulamasındaki bir web hizmetine HTTP GET ve POST isteklerini gönderme görevleriyle birlikte nasıl kullanılacağını gösterir. Görevlerle `IXMLHTTPRequest2` birleştirerek, diğer görevlerle oluşan kod yazabilirsiniz. Örneğin, karşıdan yükleme görevini görev zincirinin bir parçası olarak kullanabilirsiniz. Çalışma iptal edildiğinde indirme görevi de yanıt verebilir.

> [!TIP]
> C++ REST SDK'yı, Bir UWP uygulamasından C++ uygulamasını kullanarak veya bir masaüstü C++ uygulamasından HTTP isteklerini gerçekleştirmek için de kullanabilirsiniz. Daha fazla bilgi için [Bkz. C++ REST SDK (Kod adı "Kazablanka")](https://github.com/Microsoft/cpprestsdk).

Görevler hakkında daha fazla bilgi için [Görev Paralelliği'ne](../../parallel/concrt/task-parallelism-concurrency-runtime.md)bakın. Bir UWP uygulamasında görevlerin nasıl kullanılacağı hakkında daha fazla bilgi için [C++'da Asynchronous programlama](/windows/uwp/threading-async/asynchronous-programming-in-cpp-universal-windows-platform-apps) ve [UWP Uygulamaları için C++'da Eşzamanlı İşlemler Oluşturma'ya](../../parallel/concrt/creating-asynchronous-operations-in-cpp-for-windows-store-apps.md)bakın.

Bu belge ilk olarak `HttpRequest` nasıl oluşturulacak ve destekleyici sınıfları gösterir. Daha sonra C++ ve XAML kullanan bir UWP uygulamasından bu sınıfın nasıl kullanılacağını gösterir.

Görevleri kullanan `IXMLHTTPRequest2` ancak kullanmayan bir örnek için [bkz: Quickstart: XML HTTP Request (IXMLHTTPRequest2) kullanarak bağlanma.](/previous-versions/windows/apps/hh770550\(v=win.10\))

> [!TIP]
> `IXMLHTTPRequest2`ve `IXMLHTTPRequest2Callback` bir UWP uygulamasında kullanılmasını önerdiğimiz arayüzlerdir. Bu örneği bir masaüstü uygulamasında kullanmak üzere de uyarlayabilirsiniz.

## <a name="prerequisites"></a>Önkoşullar

UWP desteği Visual Studio 2017 ve sonraki yıllarda isteğe bağlıdır. Yüklemek için Windows Başlat menüsünden Visual Studio Yükleyici'yi açın ve kullandığınız Visual Studio sürümünü seçin. **Değiştir** düğmesini tıklatın ve **UWP Geliştirme** kutusunun işaretli olduğundan emin olun. **İsteğe Bağlı Bileşenler** altında **C++ UWP Araçları'nın** kontrol edildiğinden emin olun. Visual Studio 2017 için v141 veya Visual Studio 2019 için v142 kullanın.

## <a name="defining-the-httprequest-httprequestbufferscallback-and-httprequeststringcallback-classes"></a>HttpRequest, HttpRequestBuffersCallback ve HttpRequestStringCallback Sınıflarını Tanımlama

Arayüzü HTTP `IXMLHTTPRequest2` üzerinden web istekleri oluşturmak için kullandığınızda, sunucu yanıtını almak ve diğer olaylara tepki vermek için `IXMLHTTPRequest2Callback` arabirimi uygularsınız. Bu örnek, `HttpRequest` web isteklerini oluşturmak için `HttpRequestBuffersCallback` `HttpRequestStringCallback` sınıfı ve yanıtları işlemek için sınıfları tanımlar. Ve `HttpRequestBuffersCallback` `HttpRequestStringCallback` sınıflar `HttpRequest` sınıfı destekler; yalnızca uygulama kodundan `HttpRequest` sınıfla çalışırsınız.

Sınıfın `GetAsync` `PostAsync` yöntemleri `HttpRequest` sırasıyla HTTP GET ve POST işlemlerini başlatmanızı sağlar. Bu yöntemler, `HttpRequestStringCallback` sunucu yanıtını dize olarak okumak için sınıfı kullanır. Ve `SendAsync` `ReadAsync` yöntemler, büyük içeriği parçalar halinde akışınıza olanak tanır. Bu yöntemlerher döner [eşzamanlılık::görev](../../parallel/concrt/reference/task-class.md) işlemi temsil etmek. Ve `GetAsync` `PostAsync` yöntemler, `task<std::wstring>` parçanın `wstring` sunucunun yanıtını temsil ettiği değer üretir. Ve `SendAsync` `ReadAsync` yöntemler `task<void>` değerler üretir; gönderme ve okuma işlemleri tamamlandığında bu görevler tamamlar.

`IXMLHTTPRequest2` Arabirimler eşzamanlı hareket ettiği için, bu örnek [eşzamanlılık kullanır::task_completion_event](../../parallel/concrt/reference/task-completion-event-class.md) geri arama nesnesi tamamlandıktan veya indirme işlemini iptal ettikten sonra tamamlayan bir görev oluşturmak için. Sınıf, `HttpRequest` nihai sonucu ayarlamak için bu görevden görev tabanlı bir devamı oluşturur. Sınıf, `HttpRequest` önceki görev bir hata üretse veya iptal edilebilse bile devam görevinin çalıştığından emin olmak için görev tabanlı bir devamı kullanır. Görev tabanlı devamlar hakkında daha fazla bilgi için [Görev Paralelliği'ne](../../parallel/concrt/task-parallelism-concurrency-runtime.md) bakın

İptali desteklemek `HttpRequest`için, `HttpRequestBuffersCallback` `HttpRequestStringCallback` ve sınıflar iptal belirteçlerini kullanır. Ve `HttpRequestBuffersCallback` `HttpRequestStringCallback` sınıflar [eşzamanlılık kullanın::cancellation_token::register_callback](reference/cancellation-token-class.md#register_callback) yöntemi iptal yanıt lamak için görev tamamlama olay etkinleştirmek için. Bu iptal geri arama sı, karşıdan yüklemeyi iptal eder. İptal hakkında daha fazla bilgi için [İptal'e](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md#cancellation)bakın.

### <a name="to-define-the-httprequest-class"></a>HttpRequest Sınıfını tanımlamak için

1. Ana menüden**Yeni** >  **Dosya** > **Projesi'ni**seçin.

1. Boş bir XAML uygulama projesi oluşturmak için C++ **Boş Uygulama (Evrensel Windows)** şablonunu kullanın. Bu örnekte `UsingIXMLHTTPRequest2`proje adlandırır.

1. Projeye HttpRequest.h adlı bir üstbilgi dosyası ve HttpRequest.cpp adlı bir kaynak dosya ekleyin.

1. pch.h olarak, bu kodu ekleyin:

   [!code-cpp[concrt-using-ixhr2#1](../../parallel/concrt/codesnippet/cpp/walkthrough-connecting-using-tasks-and-xml-http-requests_1.h)]

1. HttpRequest.h'de şu kodu ekleyin:

   [!code-cpp[concrt-using-ixhr2#2](../../parallel/concrt/codesnippet/cpp/walkthrough-connecting-using-tasks-and-xml-http-requests_2.h)]

1. HttpRequest.cpp'de şu kodu ekleyin:

   [!code-cpp[concrt-using-ixhr2#3](../../parallel/concrt/codesnippet/cpp/walkthrough-connecting-using-tasks-and-xml-http-requests_3.cpp)]

## <a name="using-the-httprequest-class-in-a-uwp-app"></a>UWP Uygulamasında HttpRequest Sınıfını Kullanma

Bu bölümde, bir UWP uygulamasında `HttpRequest` sınıfın nasıl kullanılacağı gösterin. Uygulama, bir URL kaynağını tanımlayan bir giriş kutusu ve GET ve POST işlemlerini gerçekleştiren düğme komutları ve geçerli işlemi iptal eden bir düğme komutu sağlar.

### <a name="to-use-the-httprequest-class"></a>HttpRequest Sınıfını kullanmak için

1. MainPage.xaml'da [StackPanel](/uwp/api/windows.ui.xaml.controls.stackpanel) öğesini aşağıdaki gibi tanımlayın.

   [!code-xml[concrt-using-ixhr2#A1](../../parallel/concrt/codesnippet/xaml/walkthrough-connecting-using-tasks-and-xml-http-requests_4.xaml)]

1. MainPage.xaml.h'de şu `#include` yönergeyi ekleyin:

   [!code-cpp[concrt-using-ixhr2#A2](../../parallel/concrt/codesnippet/cpp/walkthrough-connecting-using-tasks-and-xml-http-requests_5.h)]

1. MainPage.xaml.h'de bu `private` üye değişkenleri `MainPage` sınıfa ekleyin:

   [!code-cpp[concrt-using-ixhr2#A3](../../parallel/concrt/codesnippet/cpp/walkthrough-connecting-using-tasks-and-xml-http-requests_6.h)]

1. MainPage.xaml.h'de yöntemi `private` `ProcessHttpRequest`bildirin:

   [!code-cpp[concrt-using-ixhr2#A4](../../parallel/concrt/codesnippet/cpp/walkthrough-connecting-using-tasks-and-xml-http-requests_7.h)]

1. MainPage.xaml.cpp'de şu `using` ifadeleri ekleyin:

   [!code-cpp[concrt-using-ixhr2#A5](../../parallel/concrt/codesnippet/cpp/walkthrough-connecting-using-tasks-and-xml-http-requests_8.cpp)]

1. MainPage.xaml.cpp'de sınıfın `GetButton_Click` `PostButton_Click`, `CancelButton_Click` ve yöntemlerini uygulayın. `MainPage`

   [!code-cpp[concrt-using-ixhr2#A6](../../parallel/concrt/codesnippet/cpp/walkthrough-connecting-using-tasks-and-xml-http-requests_9.cpp)]

   > [!TIP]
   > Uygulamanız iptal için destek gerektirmiyorsa, [eşzamanlılığı geçirin::cancellation_token:::hiçbiri](reference/cancellation-token-class.md#none) `HttpRequest::GetAsync` ve `HttpRequest::PostAsync` yöntemleri.

1. MainPage.xaml.cpp'de yöntemi `MainPage::ProcessHttpRequest` uygulayın.

   [!code-cpp[concrt-using-ixhr2#A7](../../parallel/concrt/codesnippet/cpp/walkthrough-connecting-using-tasks-and-xml-http-requests_10.cpp)]

1. Proje özelliklerinde, **Bağlayıcı**altında **Input**, Giriş `shcore.lib` `msxml6.lib`, belirtin ve .

İşte çalışan uygulama:

![Çalışan Windows Runtime uygulaması](../../parallel/concrt/media/concrt_usingixhr2.png "Çalışan Windows Runtime uygulaması")

## <a name="next-steps"></a>Sonraki Adımlar

[Eşzamanlılık Çalışma Zamanı İzlenecek Yollar](../../parallel/concrt/concurrency-runtime-walkthroughs.md)

## <a name="see-also"></a>Ayrıca bkz.

[Görev Paralelliği](../../parallel/concrt/task-parallelism-concurrency-runtime.md)<br/>
[PPL'de İptal](cancellation-in-the-ppl.md)<br/>
[C++'da asynchronous programlama](/windows/uwp/threading-async/asynchronous-programming-in-cpp-universal-windows-platform-apps)<br/>
[UWP Uygulamaları için C++ Uygulamasında Zaman Uyumsuz İşlemler Oluşturma](../../parallel/concrt/creating-asynchronous-operations-in-cpp-for-windows-store-apps.md)<br/>
[Hızlı başlatma: XML HTTP İstek (IXMLHTTPRequest2)](/previous-versions/windows/apps/hh770550\(v=win.10\))
[görev Sınıfı (Eşzamanlılık Çalışma Süresi)](../../parallel/concrt/reference/task-class.md) kullanarak bağlanma<br/>
[task_completion_event Sınıfı](../../parallel/concrt/reference/task-completion-event-class.md)
