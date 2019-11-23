---
title: 'İzlenecek yol: Görevleri ve XML HTTP İsteklerini Kullanarak Bağlanma'
ms.date: 04/25/2019
helpviewer_keywords:
- connecting to web services, UWP apps [C++]
- IXMLHTTPRequest2 and tasks, example
- IXHR2 and tasks, example
ms.assetid: e8e12d46-604c-42a7-abfd-b1d1bb2ed6b3
ms.openlocfilehash: b11b56578cadc4b3bd037acf84014a718f9fad84
ms.sourcegitcommit: 389c559918d9bfaf303d262ee5430d787a662e92
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/25/2019
ms.locfileid: "69512138"
---
# <a name="walkthrough-connecting-using-tasks-and-xml-http-requests"></a>İzlenecek yol: Görevleri ve XML HTTP İsteklerini Kullanarak Bağlanma

Bu örnek, bir Evrensel Windows Platformu (UWP) uygulamasında bir Web hizmetine HTTP GET ve POST istekleri göndermek için [IXMLHTTPRequest2](/windows/win32/api/msxml6/nn-msxml6-ixmlhttprequest2) ve [IXMLHTTPRequest2Callback](/windows/win32/api/msxml6/nn-msxml6-ixmlhttprequest2callback) arabirimlerinin görevlerle birlikte nasıl kullanılacağını gösterir. Görevlerle birlikte `IXMLHTTPRequest2` birleştirerek diğer görevlerle Birleşik bir kod yazabilirsiniz. Örneğin, İndirme görevini bir görev zincirinin parçası olarak kullanabilirsiniz. İndirme görevi, iş iptal edildiğinde da yanıt verebilir.

> [!TIP]
>  Uygulama veya Masaüstü C++ UYGULAMASıNDAN bir C++ UWP uygulamasından http istekleri gerçekleştirmek için REST SDK 'sını de kullanabilirsiniz. C++ Daha fazla bilgi için bkz [ C++ . Rest SDK (kod adı "Casablanca")](https://github.com/Microsoft/cpprestsdk).

Görevler hakkında daha fazla bilgi için bkz. [Görev Paralelliği](../../parallel/concrt/task-parallelism-concurrency-runtime.md). UWP uygulamasında görevlerin nasıl kullanılacağı hakkında daha fazla bilgi için bkz. ' [de C++ zaman uyumsuz programlama](/windows/uwp/threading-async/asynchronous-programming-in-cpp-universal-windows-platform-apps) ve [UWP uygulamaları için içinde C++ zaman uyumsuz işlemler oluşturma](../../parallel/concrt/creating-asynchronous-operations-in-cpp-for-windows-store-apps.md).

Bu belge ilk olarak `HttpRequest` ve destekleyici sınıflarının nasıl oluşturulacağını gösterir. Daha sonra, ve XAML kullanan C++ bir UWP uygulamasından bu sınıfın nasıl kullanılacağını gösterir.

`IXMLHTTPRequest2` kullanan ancak görevleri kullanmayan bir örnek için bkz. [hızlı başlangıç: XML http isteği (IXMLHTTPRequest2) kullanarak bağlanma](/previous-versions/windows/apps/hh770550\(v=win.10\)).

> [!TIP]
>  `IXMLHTTPRequest2` ve `IXMLHTTPRequest2Callback`, UWP uygulamasında kullanmak için önerdiğimiz arabirimlerdir. Ayrıca, bu örneği bir masaüstü uygulamasında kullanmak üzere uyarlayabilirsiniz.

## <a name="prerequisites"></a>Önkoşullar

UWP desteği, Visual Studio 2017 ve üzeri sürümlerde isteğe bağlıdır. Yüklemek için, Windows Başlat menüsünden Visual Studio Yükleyicisi açın ve kullandığınız Visual Studio sürümünü seçin. **Değiştir** düğmesine tıklayın ve **UWP geliştirme** kutucuğunun işaretli olduğundan emin olun. **İsteğe bağlı bileşenler** altında,  **C++ UWP araçlarının** işaretli olduğundan emin olun. Visual Studio 2017 için v141 veya Visual Studio 2019 için v142 kullanın.

## <a name="defining-the-httprequest-httprequestbufferscallback-and-httprequeststringcallback-classes"></a>HttpRequest, HttpRequestBuffersCallback ve HttpRequestStringCallback Sınıflarını Tanımlama

HTTP üzerinden Web istekleri oluşturmak için `IXMLHTTPRequest2` arabirimini kullandığınızda, sunucu yanıtını almak ve diğer olaylara yanıt vermek için `IXMLHTTPRequest2Callback` arabirimini uygulayın. Bu örnek, Web istekleri oluşturmak için `HttpRequest` sınıfını ve yanıtları işlemek için `HttpRequestBuffersCallback` ve `HttpRequestStringCallback` sınıflarını tanımlar. `HttpRequestBuffersCallback` ve `HttpRequestStringCallback` sınıfları `HttpRequest` sınıfını destekler; yalnızca uygulama kodundan `HttpRequest` sınıfla çalışırsınız.

`HttpRequest` sınıfının `GetAsync``PostAsync` yöntemleri, sırasıyla HTTP GET ve POST işlemlerini başlamanıza olanak sağlar. Bu yöntemler, sunucu yanıtını bir dize olarak okumak için `HttpRequestStringCallback` sınıfını kullanır. `SendAsync` ve `ReadAsync` yöntemleri, öbeklerde büyük içerik akışını sağlar. Bu yöntemlerin her biri, işlemi temsil etmek için [concurrency:: Task](../../parallel/concrt/reference/task-class.md) döndürür. `GetAsync` ve `PostAsync` yöntemleri, `wstring` bölümü sunucunun yanıtını temsil ettiği `task<std::wstring>` değeri üretir. `SendAsync` ve `ReadAsync` yöntemleri `task<void>` değerler üretir; gönderme ve okuma işlemleri tamamlandığında bu görevler tamamlanır.

`IXMLHTTPRequest2` arabirimleri zaman uyumsuz olarak davranacağından, bu örnek, geri çağırma nesnesi tamamlandıktan sonra tamamlanan bir görev oluşturmak için [concurrency:: task_completion_event](../../parallel/concrt/reference/task-completion-event-class.md) kullanır veya indirme işlemini iptal eder. `HttpRequest` sınıfı, son sonucu ayarlamak için bu görevden görev tabanlı bir devamlılık oluşturur. `HttpRequest` sınıfı, önceki görev bir hata üretse veya iptal edildiğinde bile devamlılık görevinin çalışmasını sağlamak için görev tabanlı devamlılık kullanır. Görev tabanlı devamlılıklar hakkında daha fazla bilgi için bkz. [Görev Paralelliği](../../parallel/concrt/task-parallelism-concurrency-runtime.md)

İptali desteklemek için, `HttpRequest`, `HttpRequestBuffersCallback`ve `HttpRequestStringCallback` sınıfları iptal belirteçlerini kullanır. `HttpRequestBuffersCallback` ve `HttpRequestStringCallback` sınıfları, görev tamamlama olayının iptal 'e yanıt vermesini sağlamak için [concurrency:: cancellation_token:: register_callback](reference/cancellation-token-class.md#register_callback) yöntemini kullanır. Bu iptal geri çağırması indirmeyi iptal eder. İptal hakkında daha fazla bilgi için bkz. [iptal](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md#cancellation).

#### <a name="to-define-the-httprequest-class"></a>HttpRequest Sınıfını tanımlamak için

1. Ana menüden **dosya** > **Yeni** > **Proje**' yi seçin. 

1. C++ Boş bir xaml uygulaması projesi oluşturmak için **boş uygulama (Evrensel Windows)** şablonunu kullanın. Bu örnekte projenin `UsingIXMLHTTPRequest2`adı vardır.

1. Projeye HttpRequest. h adlı bir üst bilgi dosyası ve HttpRequest. cpp adlı bir kaynak dosyası ekleyin.

1. PCH. h içinde şu kodu ekleyin:

   [!code-cpp[concrt-using-ixhr2#1](../../parallel/concrt/codesnippet/cpp/walkthrough-connecting-using-tasks-and-xml-http-requests_1.h)]

1. HttpRequest. h içinde şu kodu ekleyin:

   [!code-cpp[concrt-using-ixhr2#2](../../parallel/concrt/codesnippet/cpp/walkthrough-connecting-using-tasks-and-xml-http-requests_2.h)]

1. HttpRequest. cpp içinde şu kodu ekleyin:

   [!code-cpp[concrt-using-ixhr2#3](../../parallel/concrt/codesnippet/cpp/walkthrough-connecting-using-tasks-and-xml-http-requests_3.cpp)]

## <a name="using-the-httprequest-class-in-a-uwp-app"></a>UWP uygulamasında HttpRequest sınıfını kullanma

Bu bölümde, UWP uygulamasında `HttpRequest` sınıfının nasıl kullanılacağı gösterilmektedir. Uygulama, URL kaynağını ve GET ve POST işlemlerini gerçekleştiren düğme komutlarını ve geçerli işlemi iptal eden bir Button komutunu tanımlayan bir giriş kutusu sağlar.

#### <a name="to-use-the-httprequest-class"></a>HttpRequest Sınıfını kullanmak için

1. MainPage. xaml dosyasında, [StackPanel](/uwp/api/Windows.UI.Xaml.Controls.StackPanel) öğesini aşağıdaki gibi tanımlayın.

   [!code-xml[concrt-using-ixhr2#A1](../../parallel/concrt/codesnippet/xaml/walkthrough-connecting-using-tasks-and-xml-http-requests_4.xaml)]

2. MainPage. xaml. h içinde bu `#include` yönergesini ekleyin:

   [!code-cpp[concrt-using-ixhr2#A2](../../parallel/concrt/codesnippet/cpp/walkthrough-connecting-using-tasks-and-xml-http-requests_5.h)]

3. MainPage. xaml. h içinde, bu `private` üye değişkenlerini `MainPage` sınıfına ekleyin:

   [!code-cpp[concrt-using-ixhr2#A3](../../parallel/concrt/codesnippet/cpp/walkthrough-connecting-using-tasks-and-xml-http-requests_6.h)]

4. MainPage. xaml. h içinde `private` yöntemi `ProcessHttpRequest`bildirin:

   [!code-cpp[concrt-using-ixhr2#A4](../../parallel/concrt/codesnippet/cpp/walkthrough-connecting-using-tasks-and-xml-http-requests_7.h)]

5. MainPage. xaml. cpp içinde şu `using` deyimlerini ekleyin:

   [!code-cpp[concrt-using-ixhr2#A5](../../parallel/concrt/codesnippet/cpp/walkthrough-connecting-using-tasks-and-xml-http-requests_8.cpp)]

6. MainPage. xaml. cpp içinde, `MainPage` sınıfının `GetButton_Click`, `PostButton_Click`ve `CancelButton_Click` yöntemlerini uygulayın.

   [!code-cpp[concrt-using-ixhr2#A6](../../parallel/concrt/codesnippet/cpp/walkthrough-connecting-using-tasks-and-xml-http-requests_9.cpp)]

   > [!TIP]
   > Uygulamanız iptal için destek gerektirmiyorsa, `HttpRequest::GetAsync` ve `HttpRequest::PostAsync` yöntemlerine [eşzamanlılık:: cancellation_token:: None](reference/cancellation-token-class.md#none) geçirin.

1. MainPage. xaml. cpp içinde `MainPage::ProcessHttpRequest` yöntemini uygulayın.

   [!code-cpp[concrt-using-ixhr2#A7](../../parallel/concrt/codesnippet/cpp/walkthrough-connecting-using-tasks-and-xml-http-requests_10.cpp)]

8. Proje özelliklerinde, **bağlayıcı**, **giriş**, `shcore.lib` ve `msxml6.lib`belirtin.

Çalışan uygulama şu şekildedir:

Çalışan ![Windows çalışma zamanı uygulaması](../../parallel/concrt/media/concrt_usingixhr2.png "çalışan Windows çalışma zamanı uygulaması")

## <a name="next-steps"></a>Sonraki Adımlar

[Eşzamanlılık Çalışma Zamanı İzlenecek Yollar](../../parallel/concrt/concurrency-runtime-walkthroughs.md)

## <a name="see-also"></a>Ayrıca bkz.

[Görev Paralelliği](../../parallel/concrt/task-parallelism-concurrency-runtime.md)<br/>
[PPL'de İptal](cancellation-in-the-ppl.md)<br/>
[İçinde zaman uyumsuz programlamaC++](/windows/uwp/threading-async/asynchronous-programming-in-cpp-universal-windows-platform-apps)<br/>
[UWP Uygulamaları için C++ Uygulamasında Zaman Uyumsuz İşlemler Oluşturma](../../parallel/concrt/creating-asynchronous-operations-in-cpp-for-windows-store-apps.md)<br/>
[Hızlı başlangıç: XML http isteği (IXMLHTTPRequest2)](/previous-versions/windows/apps/hh770550\(v=win.10\))
[görev sınıfı (eşzamanlılık çalışma zamanı)](../../parallel/concrt/reference/task-class.md) kullanarak bağlanma<br/>
[task_completion_event Sınıfı](../../parallel/concrt/reference/task-completion-event-class.md)
