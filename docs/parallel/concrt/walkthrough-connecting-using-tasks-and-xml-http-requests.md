---
description: 'Daha fazla bilgi edinin: Izlenecek yol: görevleri ve XML HTTP Isteklerini kullanarak bağlanma'
title: 'İzlenecek yol: Görevleri ve XML HTTP İsteklerini Kullanarak Bağlanma'
ms.date: 04/25/2019
helpviewer_keywords:
- connecting to web services, UWP apps [C++]
- IXMLHTTPRequest2 and tasks, example
- IXHR2 and tasks, example
ms.assetid: e8e12d46-604c-42a7-abfd-b1d1bb2ed6b3
ms.openlocfilehash: 88f58639b09c1b996922261c889c4844f1da4963
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97167571"
---
# <a name="walkthrough-connecting-using-tasks-and-xml-http-requests"></a>İzlenecek yol: Görevleri ve XML HTTP İsteklerini Kullanarak Bağlanma

Bu örnek, bir Evrensel Windows Platformu (UWP) uygulamasında bir Web hizmetine HTTP GET ve POST istekleri göndermek için [IXMLHTTPRequest2](/windows/win32/api/msxml6/nn-msxml6-ixmlhttprequest2) ve [IXMLHTTPRequest2Callback](/windows/win32/api/msxml6/nn-msxml6-ixmlhttprequest2callback) arabirimlerinin görevlerle birlikte nasıl kullanılacağını gösterir. `IXMLHTTPRequest2`Görevlerle birlikte birleştirerek, diğer görevlerle Birleşik bir kod yazabilirsiniz. Örneğin, İndirme görevini bir görev zincirinin parçası olarak kullanabilirsiniz. İndirme görevi, iş iptal edildiğinde da yanıt verebilir.

> [!TIP]
> C++ uygulamasını kullanarak veya bir masaüstü C++ uygulamasından bir UWP uygulamasından HTTP istekleri gerçekleştirmek için C++ REST SDK 'sını de kullanabilirsiniz. Daha fazla bilgi için bkz. [C++ Rest SDK (kod adı "Casablanca")](https://github.com/Microsoft/cpprestsdk).

Görevler hakkında daha fazla bilgi için bkz. [Görev Paralelliği](../../parallel/concrt/task-parallelism-concurrency-runtime.md). UWP uygulamasında görevlerin nasıl kullanılacağı hakkında daha fazla bilgi için bkz. [c++ ' da zaman uyumsuz programlama](/windows/uwp/threading-async/asynchronous-programming-in-cpp-universal-windows-platform-apps) ve [UWP uygulamaları için C++ ' da zaman uyumsuz işlemler oluşturma](../../parallel/concrt/creating-asynchronous-operations-in-cpp-for-windows-store-apps.md).

Bu belgede önce `HttpRequest` ve destekleyici sınıflarının nasıl oluşturulduğu gösterilir. Daha sonra bu sınıfın C++ ve XAML kullanan UWP uygulamasından nasıl kullanılacağını gösterir.

Görevleri kullanan ancak kullanmayan bir örnek için `IXMLHTTPRequest2` bkz. [hızlı başlangıç: XML http Isteği (IXMLHTTPRequest2) kullanarak bağlanma](/previous-versions/windows/apps/hh770550\(v=win.10\)).

> [!TIP]
> `IXMLHTTPRequest2``IXMLHTTPRequest2Callback`UWP uygulamasında kullanmak için önerdiğimiz arabirimlerdir. Ayrıca, bu örneği bir masaüstü uygulamasında kullanmak üzere uyarlayabilirsiniz.

## <a name="prerequisites"></a>Önkoşullar

UWP desteği, Visual Studio 2017 ve üzeri sürümlerde isteğe bağlıdır. Yüklemek için, Windows Başlat menüsünden Visual Studio Yükleyicisi açın ve kullandığınız Visual Studio sürümünü seçin. **Değiştir** düğmesine tıklayın ve **UWP geliştirme** kutucuğunun işaretli olduğundan emin olun. **Isteğe bağlı bileşenler** altında **C++ UWP araçları** ' nın işaretli olduğundan emin olun. Visual Studio 2017 için v141 veya Visual Studio 2019 için v142 kullanın.

## <a name="defining-the-httprequest-httprequestbufferscallback-and-httprequeststringcallback-classes"></a>HttpRequest, HttpRequestBuffersCallback ve HttpRequestStringCallback Sınıflarını Tanımlama

`IXMLHTTPRequest2`Http üzerinden Web istekleri oluşturmak için arabirimini kullandığınızda, `IXMLHTTPRequest2Callback` sunucu yanıtını almak ve diğer olaylara yanıt vermek için arabirimini uygulayın. Bu örnek, `HttpRequest` Web istekleri oluşturmak için sınıfını ve `HttpRequestBuffersCallback` `HttpRequestStringCallback` yanıtları işlemek için ve sınıflarını tanımlar. `HttpRequestBuffersCallback`Ve `HttpRequestStringCallback` sınıfları `HttpRequest` sınıfı destekler; yalnızca `HttpRequest` uygulama kodundaki sınıfla çalışırsınız.

, `GetAsync` `PostAsync` `HttpRequest` SıNıFıNıN YÖNTEMLERI sırasıyla http get ve post işlemlerini başlamanıza olanak sağlar. Bu yöntemler, `HttpRequestStringCallback` sunucu yanıtını bir dize olarak okumak için sınıfını kullanır. `SendAsync`Ve `ReadAsync` yöntemleri, öbeklerde büyük içerik akışını sağlar. Bu yöntemlerin her biri, işlemi temsil etmek için [concurrency:: Task](../../parallel/concrt/reference/task-class.md) döndürür. `GetAsync`Ve `PostAsync` yöntemleri, `task<std::wstring>` `wstring` parçanın sunucunun yanıtını temsil ettiği değeri üretir. `SendAsync`Ve `ReadAsync` yöntemleri değerler üretir `task<void>` ; gönderme ve okuma işlemleri tamamlandığında bu görevler tamamlanır.

`IXMLHTTPRequest2`Arabirimler zaman uyumsuz olarak davranacağından, bu örnek, geri çağırma nesnesi tamamlandıktan sonra tamamlanan bir görev oluşturmak için [concurrency:: task_completion_event](../../parallel/concrt/reference/task-completion-event-class.md) kullanır ve indirme işlemini iptal eder. `HttpRequest`Sınıfı, son sonucu ayarlamak için bu görevden görev tabanlı bir devamlılık oluşturur. `HttpRequest`Bu sınıf, önceki görev bir hata üretse veya iptal edildiğinde bile devamlılık görevinin çalışmasını sağlamak için görev tabanlı devamlılık kullanır. Görev tabanlı devamlılıklar hakkında daha fazla bilgi için bkz. [Görev Paralelliği](../../parallel/concrt/task-parallelism-concurrency-runtime.md)

İptali desteklemek için,, `HttpRequest` `HttpRequestBuffersCallback` ve `HttpRequestStringCallback` sınıfları iptal belirteçlerini kullanır. `HttpRequestBuffersCallback`Ve `HttpRequestStringCallback` sınıfları, görev tamamlama olayının iptal 'e yanıt vermesini sağlamak için [concurrency:: cancellation_token:: register_callback](reference/cancellation-token-class.md#register_callback) yöntemini kullanır. Bu iptal geri çağırması indirmeyi iptal eder. İptal hakkında daha fazla bilgi için bkz. [iptal](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md#cancellation).

### <a name="to-define-the-httprequest-class"></a>HttpRequest Sınıfını tanımlamak için

1. Ana menüden **Dosya**  >  **Yeni**  >  **Proje**' yi seçin.

1. Boş bir XAML uygulama projesi oluşturmak için C++ **boş uygulaması (Evrensel Windows)** şablonunu kullanın. Bu örnek, projeyi adlandırır `UsingIXMLHTTPRequest2` .

1. Projeye HttpRequest. h adlı bir üst bilgi dosyası ve HttpRequest. cpp adlı bir kaynak dosyası ekleyin.

1. PCH. h içinde şu kodu ekleyin:

   [!code-cpp[concrt-using-ixhr2#1](../../parallel/concrt/codesnippet/cpp/walkthrough-connecting-using-tasks-and-xml-http-requests_1.h)]

1. HttpRequest. h içinde şu kodu ekleyin:

   [!code-cpp[concrt-using-ixhr2#2](../../parallel/concrt/codesnippet/cpp/walkthrough-connecting-using-tasks-and-xml-http-requests_2.h)]

1. HttpRequest. cpp içinde şu kodu ekleyin:

   [!code-cpp[concrt-using-ixhr2#3](../../parallel/concrt/codesnippet/cpp/walkthrough-connecting-using-tasks-and-xml-http-requests_3.cpp)]

## <a name="using-the-httprequest-class-in-a-uwp-app"></a>UWP uygulamasında HttpRequest sınıfını kullanma

Bu bölümde, `HttpRequest` sınıfının BIR UWP uygulamasında nasıl kullanılacağı gösterilmektedir. Uygulama, URL kaynağını ve GET ve POST işlemlerini gerçekleştiren düğme komutlarını ve geçerli işlemi iptal eden bir Button komutunu tanımlayan bir giriş kutusu sağlar.

### <a name="to-use-the-httprequest-class"></a>HttpRequest Sınıfını kullanmak için

1. MainPage. xaml dosyasında, [StackPanel](/uwp/api/windows.ui.xaml.controls.stackpanel) öğesini aşağıdaki gibi tanımlayın.

   [!code-xml[concrt-using-ixhr2#A1](../../parallel/concrt/codesnippet/xaml/walkthrough-connecting-using-tasks-and-xml-http-requests_4.xaml)]

1. MainPage. xaml. h içinde şu yönergeyi ekleyin `#include` :

   [!code-cpp[concrt-using-ixhr2#A2](../../parallel/concrt/codesnippet/cpp/walkthrough-connecting-using-tasks-and-xml-http-requests_5.h)]

1. MainPage. xaml. h içinde bu **`private`** üye değişkenlerini `MainPage` sınıfa ekleyin:

   [!code-cpp[concrt-using-ixhr2#A3](../../parallel/concrt/codesnippet/cpp/walkthrough-connecting-using-tasks-and-xml-http-requests_6.h)]

1. MainPage. xaml. h içinde, yöntemi bildirin **`private`** `ProcessHttpRequest` :

   [!code-cpp[concrt-using-ixhr2#A4](../../parallel/concrt/codesnippet/cpp/walkthrough-connecting-using-tasks-and-xml-http-requests_7.h)]

1. MainPage. xaml. cpp içinde şu deyimleri ekleyin **`using`** :

   [!code-cpp[concrt-using-ixhr2#A5](../../parallel/concrt/codesnippet/cpp/walkthrough-connecting-using-tasks-and-xml-http-requests_8.cpp)]

1. MainPage. xaml. cpp içinde, sınıfının, `GetButton_Click` `PostButton_Click` ve yöntemlerini uygulayın `CancelButton_Click` `MainPage` .

   [!code-cpp[concrt-using-ixhr2#A6](../../parallel/concrt/codesnippet/cpp/walkthrough-connecting-using-tasks-and-xml-http-requests_9.cpp)]

   > [!TIP]
   > Uygulamanız iptal için destek gerektirmiyorsa, ve yöntemlerine [concurrency:: cancellation_token:: None](reference/cancellation-token-class.md#none) geçirin `HttpRequest::GetAsync` `HttpRequest::PostAsync` .

1. MainPage. xaml. cpp içinde `MainPage::ProcessHttpRequest` yöntemini uygulayın.

   [!code-cpp[concrt-using-ixhr2#A7](../../parallel/concrt/codesnippet/cpp/walkthrough-connecting-using-tasks-and-xml-http-requests_10.cpp)]

1. Proje Özellikleri ' nde **bağlayıcı**, **giriş**, ve belirtin ' i seçin `shcore.lib` `msxml6.lib` .

Çalışan uygulama şu şekildedir:

![Çalışan Windows Çalışma Zamanı uygulaması](../../parallel/concrt/media/concrt_usingixhr2.png "Çalışan Windows Çalışma Zamanı uygulaması")

## <a name="next-steps"></a>Sonraki Adımlar

[Eşzamanlılık Çalışma Zamanı Izlenecek yollar](../../parallel/concrt/concurrency-runtime-walkthroughs.md)

## <a name="see-also"></a>Ayrıca bkz.

[Görev Paralelliği](../../parallel/concrt/task-parallelism-concurrency-runtime.md)<br/>
[PPL'de İptal](cancellation-in-the-ppl.md)<br/>
[C++ ' da zaman uyumsuz programlama](/windows/uwp/threading-async/asynchronous-programming-in-cpp-universal-windows-platform-apps)<br/>
[UWP uygulamaları için C++ ' da zaman uyumsuz Işlemler oluşturma](../../parallel/concrt/creating-asynchronous-operations-in-cpp-for-windows-store-apps.md)<br/>
[Hızlı başlangıç: XML http isteği kullanarak bağlanma (IXMLHTTPRequest2)](/previous-versions/windows/apps/hh770550\(v=win.10\)) 
 [Task sınıfı (eşzamanlılık çalışma zamanı)](../../parallel/concrt/reference/task-class.md)<br/>
[task_completion_event sınıfı](../../parallel/concrt/reference/task-completion-event-class.md)
