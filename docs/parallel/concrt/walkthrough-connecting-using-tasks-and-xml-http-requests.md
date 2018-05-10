---
title: 'İzlenecek yol: Görevleri ve XML HTTP isteklerini kullanarak bağlanma | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- connecting to web services, UWP apps [C++]
- IXMLHTTPRequest2 and tasks, example
- IXHR2 and tasks, example
ms.assetid: e8e12d46-604c-42a7-abfd-b1d1bb2ed6b3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 411d52201aad69a94267615cd0a2acbe6376f64d
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
---
# <a name="walkthrough-connecting-using-tasks-and-xml-http-requests"></a>İzlenecek yol: Görevleri ve XML HTTP İsteklerini Kullanarak Bağlanma
Bu örnek nasıl kullanılacağını gösterir [Ixmlhttprequest2](http://msdn.microsoft.com/en-us/bbc11c4a-aecf-4d6d-8275-3e852e309908) ve [Ixmlhttprequest2callback](http://msdn.microsoft.com/en-us/aa4b3f4c-6e28-458b-be25-6cce8865fc71) bir web hizmeti, bir evrensel Windows Platformu (UWP HTTP GET ve POST istekleri göndermek için görevler birlikte arabirimleri ) uygulama. Birleştirme tarafından `IXMLHTTPRequest2` görevleri ile birlikte, diğer görevlerle oluşturur kod yazabilirsiniz. Örneğin, indirme görevinin görevleri zinciri bir parçası olarak kullanabilirsiniz. İş iptal ettiğinizde indirme görev ayrıca yanıt verebilir.  
  
> [!TIP]
>  C++ REST SDK, C++ uygulamasını kullanarak bir UWP uygulaması veya bir masaüstü C++ uygulaması HTTP isteklerini gerçekleştirmek için de kullanabilirsiniz. Daha fazla bilgi için bkz: [C++ REST SDK (kod adı "Casablanca")](https://github.com/Microsoft/cpprestsdk).  
  
 Görevler hakkında daha fazla bilgi için bkz: [görev Paralelliği](../../parallel/concrt/task-parallelism-concurrency-runtime.md). UWP uygulamasında görevler kullanma hakkında daha fazla bilgi için bkz: [c++ zaman uyumsuz programlama](/windows/uwp/threading-async/asynchronous-programming-in-cpp-universal-windows-platform-apps) ve [oluşturma zaman uyumsuz işlemleri c++ UWP uygulamalar için](../../parallel/concrt/creating-asynchronous-operations-in-cpp-for-windows-store-apps.md).  
  
 Bu belge ilk nasıl oluşturulacağını gösterir `HttpRequest` ve bunun destekleyici sınıfları. Ardından, C++ ve XAML kullanan bir UWP uygulaması'ndan bu sınıfının nasıl kullanılacağını gösterir.  
  
 Kullanır daha eksiksiz bir örnek için `HttpReader` sınıfı bu belgede açıklanan bkz [geliştirme, Bing Haritalar seyahat iyileştirici, bir Windows mağazası uygulaması JavaScript ve C++](http://msdn.microsoft.com/library/974cf025-de1a-4299-b7dd-c6c7bf0e5d30). Kullanan başka bir örnek için `IXMLHTTPRequest2` ancak yok görevleri kullanın, bkz: [hızlı başlangıç: XML HTTP istek (Ixmlhttprequest2) kullanarak bağlanma](http://msdn.microsoft.com/en-us/cc7aed53-b2c5-4d83-b85d-cff2f5ba7b35).  
  
> [!TIP]
>  `IXMLHTTPRequest2` ve `IXMLHTTPRequest2Callback` bir UWP uygulamasında kullanmak için önerdiğimiz arabirimlerdir. Bu örnek bir masaüstü uygulamasının kullanmak için de uyarlayabilirsiniz.  
  
## <a name="prerequisites"></a>Önkoşullar  
  
## <a name="defining-the-httprequest-httprequestbufferscallback-and-httprequeststringcallback-classes"></a>HttpRequest, HttpRequestBuffersCallback ve HttpRequestStringCallback Sınıflarını Tanımlama  
 Kullandığınızda `IXMLHTTPRequest2` HTTP üzerinden web istekleri oluşturmak için arabirim, uygulamanız `IXMLHTTPRequest2Callback` sunucu yanıtı almak ve diğer olaylarına tepki vermek için arabirim. Bu örnek tanımlar `HttpRequest` web istekleri oluşturmak için sınıf ve `HttpRequestBuffersCallback` ve `HttpRequestStringCallback` yanıtları işlemek için sınıflar. `HttpRequestBuffersCallback` Ve `HttpRequestStringCallback` sınıfları Destek `HttpRequest` sınıfı; yalnızca çalışmanıza `HttpRequest` uygulama kodundan sınıfı.  
  
 `GetAsync`, `PostAsync` Yöntemlerinin `HttpRequest` sınıfı HTTP GET ve POST işlemleri, sırasıyla Başlat olanak tanır. Bu yöntemleri `HttpRequestStringCallback` sunucu yanıtı bir dize olarak okumak için sınıf. `SendAsync` Ve `ReadAsync` yöntemleri parçalar büyük içerik akışı sağlamak için sağlar. Bu yöntemlerin her iade [concurrency::task](../../parallel/concrt/reference/task-class.md) işlemi temsil etmek için. `GetAsync` Ve `PostAsync` yöntemleri `task<std::wstring>` değeri, burada `wstring` bölümü sunucunun yanıtını temsil eder. `SendAsync` Ve `ReadAsync` yöntemleri `task<void>` değerleri; bu görevler gönderme ve okuma işlemlerini tamamladıktan sonra tamamlandı.  
  
 Çünkü `IXMLHTTPRequest2` arabirimleri hareket zaman uyumsuz olarak, bu örnek kullanır [concurrency::task_completion_event](../../parallel/concrt/reference/task-completion-event-class.md) geri çağırma nesnesi tamamlandığında veya yükleme işlemi iptal sonra tamamlanan bir görev oluşturmak için. `HttpRequest` Sınıfı nihai sonucu ayarlamak için bu görevi görev tabanlı bir devamlılık oluşturur. `HttpRequest` Sınıfı önceki görev bir hata oluşturur veya iptal olsa bile devamlılık görevi çalıştığından emin olmak için görev tabanlı bir devamlılık kullanır. Görev tabanlı devamlılıklar hakkında daha fazla bilgi için bkz: [görev Paralelliği](../../parallel/concrt/task-parallelism-concurrency-runtime.md)  
  
 İptali desteklemek için `HttpRequest`, `HttpRequestBuffersCallback`, ve `HttpRequestStringCallback` sınıfları iptal belirteçlerini kullanır. `HttpRequestBuffersCallback` Ve `HttpRequestStringCallback` sınıfları kullanım [CONCURRENCY::cancellation_token:: register_callback](reference/cancellation-token-class.md#register_callback) görev tamamlama olayı için İptali yanıtlamasını etkinleştirmek için yöntemi. Bu iptal geri yüklemeyi durdurur. İptal etme hakkında daha fazla bilgi için bkz: [iptal](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md#cancellation).  
  
#### <a name="to-define-the-httprequest-class"></a>HttpRequest Sınıfını tanımlamak için  
  
1.  Visual C++ kullanma **boş uygulama (XAML)** boş bir XAML uygulama projesi oluşturmak için şablon. Bu örnek proje adları `UsingIXMLHTTPRequest2`.  
  
2.  HttpRequest.h adlı bir üstbilgi dosyası ve HttpRequest.cpp adlı bir kaynak dosyası projeye ekleyin.  
  
3.  Pch.h bu kodu ekleyin:  
  
     [!code-cpp[concrt-using-ixhr2#1](../../parallel/concrt/codesnippet/cpp/walkthrough-connecting-using-tasks-and-xml-http-requests_1.h)]  
  
4.  HttpRequest.h bu kodu ekleyin:  
  
     [!code-cpp[concrt-using-ixhr2#2](../../parallel/concrt/codesnippet/cpp/walkthrough-connecting-using-tasks-and-xml-http-requests_2.h)]  
  
5.  HttpRequest.cpp bu kodu ekleyin:  
  
     [!code-cpp[concrt-using-ixhr2#3](../../parallel/concrt/codesnippet/cpp/walkthrough-connecting-using-tasks-and-xml-http-requests_3.cpp)]  
  
## <a name="using-the-httprequest-class-in-a-uwp-app"></a>UWP uygulamasında HttpRequest sınıfını kullanma  
 Bu bölümde nasıl kullanılacağı ortaya `HttpRequest` bir UWP uygulamasında sınıfı. Uygulama, bir URL kaynağı tanımlayan bir giriş kutusu ve GET ve POST işlemleri düğme komutları ve geçerli işlemi iptal düğmesi komutu sağlar.  
  
#### <a name="to-use-the-httprequest-class"></a>HttpRequest Sınıfını kullanmak için  
  
1.  MainPage.xaml içinde tanımlayın [StackPanel](http://msdn.microsoft.com/library/windows/apps/xaml/windows.ui.xaml.controls.stackpanel.aspx) şekilde öğesi.  
  
     [!code-xml[concrt-using-ixhr2#A1](../../parallel/concrt/codesnippet/xaml/walkthrough-connecting-using-tasks-and-xml-http-requests_4.xaml)]  
  
2.  Bu MainPage.xaml.h içinde eklemek `#include` yönergesi:  
  
     [!code-cpp[concrt-using-ixhr2#A2](../../parallel/concrt/codesnippet/cpp/walkthrough-connecting-using-tasks-and-xml-http-requests_5.h)]  
  
3.  MainPage.xaml.h içinde ekleme `private` için üye değişkenleri `MainPage` sınıfı:  
  
     [!code-cpp[concrt-using-ixhr2#A3](../../parallel/concrt/codesnippet/cpp/walkthrough-connecting-using-tasks-and-xml-http-requests_6.h)]  
  
4.  MainPage.xaml.h içinde bildirme `private` yöntemi `ProcessHttpRequest`:  
  
     [!code-cpp[concrt-using-ixhr2#A4](../../parallel/concrt/codesnippet/cpp/walkthrough-connecting-using-tasks-and-xml-http-requests_7.h)]  
  
5.  MainPage.xaml.cpp içinde ekleme `using` deyimleri:  
  
     [!code-cpp[concrt-using-ixhr2#A5](../../parallel/concrt/codesnippet/cpp/walkthrough-connecting-using-tasks-and-xml-http-requests_8.cpp)]  
  
6.  MainPage.xaml.cpp içinde uygulamak `GetButton_Click`, `PostButton_Click`, ve `CancelButton_Click` yöntemlerinin `MainPage` sınıfı.  
  
     [!code-cpp[concrt-using-ixhr2#A6](../../parallel/concrt/codesnippet/cpp/walkthrough-connecting-using-tasks-and-xml-http-requests_9.cpp)]  
  
    > [!TIP]


    >  Uygulamanızı iptalleri destek gerektirmiyorsa geçirmek [concurrency::cancellation_token:: none](reference/cancellation-token-class.md#none) için `HttpRequest::GetAsync` ve `HttpRequest::PostAsync` yöntemleri.  


  
7.  MainPage.xaml.cpp içinde uygulamak `MainPage::ProcessHttpRequest` yöntemi.  
  
     [!code-cpp[concrt-using-ixhr2#A7](../../parallel/concrt/codesnippet/cpp/walkthrough-connecting-using-tasks-and-xml-http-requests_10.cpp)]  
  
8.  Proje Özellikleri'nde altında **bağlayıcı**, **giriş**, belirtin `shcore.lib` ve `msxml6.lib`.  
  
 Çalışan uygulamanın şöyledir:  
  
 ![Çalışan Windows çalışma zamanı uygulamanın](../../parallel/concrt/media/concrt_usingixhr2.png "concrt_usingixhr2")  
  
## <a name="next-steps"></a>Sonraki Adımlar  
 [Eşzamanlılık Çalışma Zamanı İzlenecek Yollar](../../parallel/concrt/concurrency-runtime-walkthroughs.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Görev Paralelliği](../../parallel/concrt/task-parallelism-concurrency-runtime.md)   
 [PPL'de iptal](cancellation-in-the-ppl.md)   
 [C++ zaman uyumsuz programlama](/windows/uwp/threading-async/asynchronous-programming-in-cpp-universal-windows-platform-apps)   
 [UWP uygulamaları için C++ içinde zaman uyumsuz işlemler oluşturma](../../parallel/concrt/creating-asynchronous-operations-in-cpp-for-windows-store-apps.md)   
 [Hızlı Başlangıç: XML HTTP istek (Ixmlhttprequest2) kullanarak bağlanma](http://msdn.microsoft.com/en-us/cc7aed53-b2c5-4d83-b85d-cff2f5ba7b35)   
 [task sınıfı (eşzamanlılık çalışma zamanı)](../../parallel/concrt/reference/task-class.md)   
 [task_completion_event Sınıfı](../../parallel/concrt/reference/task-completion-event-class.md)
