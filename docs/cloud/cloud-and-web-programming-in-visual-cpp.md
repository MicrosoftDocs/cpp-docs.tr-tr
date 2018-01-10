---
title: Bulut ve Web programlama Visual C++'ta | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-azure
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: b63611f1-9723-44d0-ba7f-c3ebef341313
caps.latest.revision: "13"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3aaf02f645ae61c75fb4ede3f5bc8e820039d1cc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="cloud-and-web-programming-in-visual-c"></a>Visual C++'da Bulut ve Web Programlama
C++'da, web ve bulut bağlamak için birkaç seçeneğiniz vardır.  
  
 [Windows Azure mobil hizmetler](http://www.windowsazure.com/develop/mobile/)  
 Windows Azure Mobile Services'a bağlanmak için Windows mağazası uygulamaları veya Windows Masaüstü uygulamaları kullanabilirsiniz yerel API'ler sağlar. Çoğu Web sitesinde örnekler, C# ' ta olsa da, C++ de kullanabilirsiniz. Daha fazla bilgi için bkz: [hızlı başlangıç: C++ kullanarak bir mobil hizmet ekleme](http://msdn.microsoft.com/library/windows/apps/dn263181.aspx).  

 [C++ için Microsoft Azure Storage istemci kitaplığı](https://blogs.msdn.microsoft.com/windowsazurestorage/2015/04/29/microsoft-azure-storage-client-library-for-c-v1-0-0-general-availability/)  
 C++ için Azure Storage istemci kitaplığı, ancak bunlarla sınırlı olmamak aşağıdaki yetenekleri de dahil olmak üzere Azure storage ile çalışmak için kapsamlı bir API sağlar:

- Oluşturma, okuma, silme ve blob kapsayıcılar, tablolar ve Kuyruklar listesi.
- Oluşturma, okuma, silme, liste ve kopyalama BLOB'lar artı okuma ve blob'u aralıklarını yazma.
- Ekle, Sil, Değiştir, birleştirme ve sorgu varlıklar Azure tablosunda.
- Sıraya alma ve Azure sıradaki iletiler dequeue.
- Gevşek kapsayıcıları, BLOB'lar, tablolar ve Kuyruklar listesinde ve gevşek varlıklar sorgulama

[OneDrive API](https://dev.onedrive.com/README.htm)  
 OneDrive API uygulamanızı dosyalara ve klasörlere Office 365 ve SharePoint Server 2016 bağlanmak için HTTP Hizmetleri kümesi sağlar.

[C++ REST SDK (kod adı "Casablanca")](https://github.com/Microsoft/cpprestsdk)  
REST Hizmetleri ile etkileşim kurmaya yönelik modern, platformlar arası, zaman uyumsuz bir API sağlar.

-   JSON belgesini ayrıştırma ve seri hale getirme için yerleşik destek ile herhangi bir HTTP sunucusuna karşı REST çağrılarını gerçekleştirin
-   OAuth 1 ve 2 ' nin yerel yeniden yönlendirme dinleyici dahil olmak üzere destekler
-   Uzak Hizmetleri karşı Websockets bağlantıları oluşturma
-   Tam olarak zaman uyumsuz görev yerleşik bir iş parçacığı havuzu dahil olmak üzere PPL üzerinde temel API

Windows Masaüstü (7 +), Windows Server (2012 +), Evrensel Windows platformu, Linux, OSX, Android ve iOS destekler. 
  
[Windows::Web::http::HttpClient](https://msdn.microsoft.com/en-us/library/windows/apps/windows.web.http.httpclient.aspx)  
 .NET Framework sınıf System.Web ad alanında aynı ada sahip bir Windows çalışma zamanı HTTP istemci sınıfı modellendiği. `HttpClient`tam olarak destekler zaman uyumsuz indirin ve HTTP ve ardışık düzen özel HTTP işleyicileri ekleme etkinleştirmek ardışık düzen filtreleri üzerinden yükleyin. Windows SDK'sı ölçülen ağları, OAuth kimlik doğrulaması ve daha fazlası için örnek filtreleri içerir. Evrensel Windows platformu hedefleyen uygulamalar için kullanmanızı öneririz `Windows::Web:HttpClient` sınıfı. 
  
[Ixmlhttprequest2 arabirimi](http://msdn.microsoft.com/library/windows/apps/hh831151.aspx)  
 HTTP üzerinden Internet'e bağlanmak için Windows mağazası uygulamaları veya Windows Masaüstü uygulamaları kullanabilirsiniz ve sorunu GET, PUT ve diğer HTTP komutlar yerel bir COM arabirimi sağlar. Daha fazla bilgi için bkz: [izlenecek yol: bağlanma kullanarak görevleri ve XML HTTP isteklerini](../parallel/concrt/walkthrough-connecting-using-tasks-and-xml-http-requests.md).  
  
[Windows Internet (WinINet)](http://msdn.microsoft.com/library/windows/desktop/aa385331\(v=vs.85\).aspx)  
 Windows masaüstü uygulamalarında Internet'e bağlanmak için kullanabileceğiniz Windows API.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual C++](../visual-cpp-in-visual-studio.md)   
 [Ağlar ve web Hizmetleri (C# / VB/C++ ve XAML kullanarak Windows mağazası uygulamaları) bağlanma](http://msdn.microsoft.com/library/windows/apps/br229573.aspx)