---
title: 'İzlenecek yol: Görevleri ve XML HTTP İsteklerini Kullanarak Bağlanma'
ms.date: 11/04/2016
helpviewer_keywords:
- connecting to web services, UWP apps [C++]
- IXMLHTTPRequest2 and tasks, example
- IXHR2 and tasks, example
ms.assetid: e8e12d46-604c-42a7-abfd-b1d1bb2ed6b3
ms.openlocfilehash: 69e365c0f0bbee7014b6d754c920bd6241064fdf
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50495580"
---
# <a name="walkthrough-connecting-using-tasks-and-xml-http-requests"></a>İzlenecek yol: Görevleri ve XML HTTP İsteklerini Kullanarak Bağlanma

Bu örnek nasıl kullanılacağını gösterir [Ixmlhttprequest2](/previous-versions/windows/desktop/api/msxml6/nn-msxml6-ixmlhttprequest2) ve [Ixmlhttprequest2callback](/previous-versions/windows/desktop/api/msxml6/nn-msxml6-ixmlhttprequest2callback) arabirimleri birlikte bir web hizmeti, bir evrensel Windows Platformu (UWP HTTP GET ve POST istekleri göndermek için görevler ) uygulama. Birleştirme tarafından `IXMLHTTPRequest2` görevleri ile birlikte diğer görevlerle ölçeklemesini kod yazabilirsiniz. Örneğin, indirme görev görevleri zinciri bir parçası olarak kullanabilirsiniz. İş iptal edildiğinde indirme görev de yanıt verebilirsiniz.

> [!TIP]
>  C++ REST SDK'sı, C++ uygulaması kullanarak UWP uygulaması veya bir masaüstü C++ uygulama HTTP isteklerini gerçekleştirmek için de kullanabilirsiniz. Daha fazla bilgi için bkz. [C++ REST SDK (Codename "Kazablanka")](https://github.com/Microsoft/cpprestsdk).

Görevler hakkında daha fazla bilgi için bkz. [görev Paralelliği](../../parallel/concrt/task-parallelism-concurrency-runtime.md). Bir UWP uygulamasında görevler kullanma hakkında daha fazla bilgi için bkz. [C++ zaman uyumsuz programlamada](/windows/uwp/threading-async/asynchronous-programming-in-cpp-universal-windows-platform-apps) ve [oluşturma zaman uyumsuz işlemler c++ UWP uygulamaları için](../../parallel/concrt/creating-asynchronous-operations-in-cpp-for-windows-store-apps.md).

Bu belge ilk nasıl oluşturulacağını gösterir `HttpRequest` ve bunun destekleyici sınıfları. Ardından, C++ ve XAML kullanan bir UWP uygulamasında bu sınıfının nasıl kullanılacağını gösterir.

Kullanan bir örnek için `IXMLHTTPRequest2` ancak olmayan görevleri kullanın, bkz: [hızlı başlangıç: XML HTTP isteğini (Ixmlhttprequest2) kullanarak bağlanma](/previous-versions/windows/apps/hh770550\(v=win.10\)).

> [!TIP]
>  `IXMLHTTPRequest2` ve `IXMLHTTPRequest2Callback` bir UWP uygulamasında kullanmak için önerdiğimiz arabirimdir. Bu örnek masaüstü uygulamasını kullanmak için de uyarlayabilirsiniz.

## <a name="prerequisites"></a>Önkoşullar

## <a name="defining-the-httprequest-httprequestbufferscallback-and-httprequeststringcallback-classes"></a>HttpRequest, HttpRequestBuffersCallback ve HttpRequestStringCallback Sınıflarını Tanımlama

Kullanırken `IXMLHTTPRequest2` HTTP üzerinden web istekleri oluşturmak için arabirim, uygulamanız `IXMLHTTPRequest2Callback` sunucu yanıtını almak ve diğer olaylarına tepki vermek için arabirim. Bu örnek tanımlar `HttpRequest` web istekleri oluşturmak için sınıf ve `HttpRequestBuffersCallback` ve `HttpRequestStringCallback` yanıtları işlemek için sınıflar. `HttpRequestBuffersCallback` Ve `HttpRequestStringCallback` destek sınıfları `HttpRequest` sınıfı; yalnızca çalışmanıza `HttpRequest` uygulama kodundan sınıfı.

`GetAsync`, `PostAsync` Yöntemlerinin `HttpRequest` sınıfı HTTP GET ve POST işlemleri, sırasıyla Başlat olanak tanır. Bu yöntemleri `HttpRequestStringCallback` sunucu yanıtını bir dize olarak okumak için sınıf. `SendAsync` Ve `ReadAsync` yöntemleri öbekler halinde büyük içerik akışı, sağlar. Bu yöntemlerin her iade [concurrency::task](../../parallel/concrt/reference/task-class.md) işlemi temsil etmek için. `GetAsync` Ve `PostAsync` yöntemleri `task<std::wstring>` değer, burada `wstring` bölümü sunucu yanıtını temsil eder. `SendAsync` Ve `ReadAsync` yöntemleri `task<void>` değerleri; bu görevler gönderme ve okuma işlemlerini tamamladıktan sonra tamamlandı.

Çünkü `IXMLHTTPRequest2` arabirimleri zaman uyumsuz olarak davranan, bu örnekte [concurrency::task_completion_event](../../parallel/concrt/reference/task-completion-event-class.md) geri çağırma nesnesi tamamlandığında veya indirme işlemi iptal sonra tamamlanan bir görev oluşturmak için. `HttpRequest` Sınıfı, bir görev tabanlı devamlılık nihai sonucu ayarlamak için bu görevi oluşturur. `HttpRequest` Sınıfı önceki görevde bir hata oluşturur veya iptal edilen bile devamlılık görevi çalıştığından emin olmak için bir görev tabanlı devamlılık kullanır. Görev tabanlı devamlılık hakkında daha fazla bilgi için bkz: [görev Paralelliği](../../parallel/concrt/task-parallelism-concurrency-runtime.md)

İptali desteklemek için `HttpRequest`, `HttpRequestBuffersCallback`, ve `HttpRequestStringCallback` iptal belirteçlerini sınıflarını kullanın. `HttpRequestBuffersCallback` Ve `HttpRequestStringCallback` sınıfları kullanın [CONCURRENCY::cancellation_token:: register_callback](reference/cancellation-token-class.md#register_callback) iptal için yanıt vermek görev tamamlama olayı etkinleştirmek için yöntemi. Bu iptal geri yüklemeyi durdurur. İptal etme hakkında daha fazla bilgi için bkz. [iptal](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md#cancellation).

#### <a name="to-define-the-httprequest-class"></a>HttpRequest Sınıfını tanımlamak için

1. Visual c++'ta kullanmak **boş uygulama (XAML)** boş bir XAML uygulaması projesi oluşturmak için şablon. Bu örnek proje adları `UsingIXMLHTTPRequest2`.

1. Projeye HttpRequest.h adlı bir üstbilgi dosyası ve HttpRequest.cpp adlı bir kaynak dosyası ekleyin.

1. Pch.h içinde bu kodu ekleyin:

   [!code-cpp[concrt-using-ixhr2#1](../../parallel/concrt/codesnippet/cpp/walkthrough-connecting-using-tasks-and-xml-http-requests_1.h)]

1. HttpRequest.h içinde bu kodu ekleyin:

   [!code-cpp[concrt-using-ixhr2#2](../../parallel/concrt/codesnippet/cpp/walkthrough-connecting-using-tasks-and-xml-http-requests_2.h)]

1. HttpRequest.cpp içinde bu kodu ekleyin:

   [!code-cpp[concrt-using-ixhr2#3](../../parallel/concrt/codesnippet/cpp/walkthrough-connecting-using-tasks-and-xml-http-requests_3.cpp)]

## <a name="using-the-httprequest-class-in-a-uwp-app"></a>HttpRequest sınıfını bir UWP uygulamasında kullanma

Bu bölümde, nasıl kullanılacağını gösteren `HttpRequest` bir UWP uygulamasında sınıfı. Uygulama, bir URL kaynağı tanımlar bir giriş kutusu ve GET ve POST işlemleri düğme komutları ve geçerli işlemi iptal eden bir düğme komutunu sağlar.

#### <a name="to-use-the-httprequest-class"></a>HttpRequest Sınıfını kullanmak için

1. MainPage.xaml içinde tanımlayın [StackPanel](https://msdn.microsoft.com/library/windows/apps/xaml/windows.ui.xaml.controls.stackpanel.aspx) şekilde öğesi.

   [!code-xml[concrt-using-ixhr2#A1](../../parallel/concrt/codesnippet/xaml/walkthrough-connecting-using-tasks-and-xml-http-requests_4.xaml)]

1. Mainpage.xaml.h içinde bu düz bu ekleme `#include` yönergesi:

   [!code-cpp[concrt-using-ixhr2#A2](../../parallel/concrt/codesnippet/cpp/walkthrough-connecting-using-tasks-and-xml-http-requests_5.h)]

1. Mainpage.xaml.h içinde bu düz eklemeniz `private` üye değişkenlerine `MainPage` sınıfı:

   [!code-cpp[concrt-using-ixhr2#A3](../../parallel/concrt/codesnippet/cpp/walkthrough-connecting-using-tasks-and-xml-http-requests_6.h)]

1. Mainpage.xaml.h içinde bu düz bildirmek `private` yöntemi `ProcessHttpRequest`:

   [!code-cpp[concrt-using-ixhr2#A4](../../parallel/concrt/codesnippet/cpp/walkthrough-connecting-using-tasks-and-xml-http-requests_7.h)]

1. MainPage.xaml.cpp içinde eklemeniz `using` ifadeleri:

   [!code-cpp[concrt-using-ixhr2#A5](../../parallel/concrt/codesnippet/cpp/walkthrough-connecting-using-tasks-and-xml-http-requests_8.cpp)]

1. Mainpage.xaml.cpp içinde `GetButton_Click`, `PostButton_Click`, ve `CancelButton_Click` yöntemlerinin `MainPage` sınıfı.

   [!code-cpp[concrt-using-ixhr2#A6](../../parallel/concrt/codesnippet/cpp/walkthrough-connecting-using-tasks-and-xml-http-requests_9.cpp)]

    > [!TIP]

    >  Uygulamanızı iptal için destek gerektirmiyorsa geçirmek [concurrency::cancellation_token:: none](reference/cancellation-token-class.md#none) için `HttpRequest::GetAsync` ve `HttpRequest::PostAsync` yöntemleri.

1. Mainpage.xaml.cpp içinde `MainPage::ProcessHttpRequest` yöntemi.

   [!code-cpp[concrt-using-ixhr2#A7](../../parallel/concrt/codesnippet/cpp/walkthrough-connecting-using-tasks-and-xml-http-requests_10.cpp)]

1. Proje özelliklerinde altında **bağlayıcı**, **giriş**, belirtin `shcore.lib` ve `msxml6.lib`.

Çalışan uygulamaya şu şekildedir:

![Çalışan Windows çalışma zamanı uygulama](../../parallel/concrt/media/concrt_usingixhr2.png "concrt_usingixhr2")

## <a name="next-steps"></a>Sonraki Adımlar

[Eşzamanlılık Çalışma Zamanı İzlenecek Yollar](../../parallel/concrt/concurrency-runtime-walkthroughs.md)

## <a name="see-also"></a>Ayrıca Bkz.

[Görev Paralelliği](../../parallel/concrt/task-parallelism-concurrency-runtime.md)<br/>
[PPL'de İptal](cancellation-in-the-ppl.md)<br/>
[C++ zaman uyumsuz programlama](/windows/uwp/threading-async/asynchronous-programming-in-cpp-universal-windows-platform-apps)<br/>
[UWP Uygulamaları için C++ Uygulamasında Zaman Uyumsuz İşlemler Oluşturma](../../parallel/concrt/creating-asynchronous-operations-in-cpp-for-windows-store-apps.md)<br/>
[Hızlı Başlangıç: XML HTTP isteğini (Ixmlhttprequest2) kullanarak bağlanma](/previous-versions/windows/apps/hh770550\(v=win.10\))
[task sınıfı (eşzamanlılık çalışma zamanı)](../../parallel/concrt/reference/task-class.md)<br/>
[task_completion_event Sınıfı](../../parallel/concrt/reference/task-completion-event-class.md)
