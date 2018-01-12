---
title: "MFC WinINet sınıfları kullanarak Internet istemci uygulaması yazma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- Internet client applications [MFC]
- WinInet classes [MFC], programming
- Internet client applications [MFC], writing
- Internet applications [MFC], WinInet
- Internet applications [MFC], client applications
- MFC, Internet applications
ms.assetid: a2c4a40c-a94e-4b3e-9dbf-f8a8dc8e5428
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 07b97d4af18ff560a48aadb3ba71b61609f82a85
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="writing-an-internet-client-application-using-mfc-wininet-classes"></a>MFC WinInet Sınıfları Kullanarak Internet İstemci Uygulaması Yazma
Her Internet istemci uygulaması Internet oturumu temelidir. MFC Internet oturumları sınıfındaki nesneler olarak uygulayan [CInternetSession](../mfc/reference/cinternetsession-class.md). Bu sınıf kullanarak, bir Internet oturum ya da birkaç eşzamanlı oturumlar oluşturabilirsiniz.  
  
 Bir sunucu ile iletişim kurmak için gereken bir [CInternetConnection](../mfc/reference/cinternetconnection-class.md) nesne yanı sıra bir `CInternetSession`. Oluşturabileceğiniz bir `CInternetConnection` kullanarak [CInternetSession::GetFtpConnection](../mfc/reference/cinternetsession-class.md#getftpconnection), [CInternetSession::GetHttpConnection](../mfc/reference/cinternetsession-class.md#gethttpconnection), veya [CInternetSession::GetGopherConnection](../mfc/reference/cinternetsession-class.md#getgopherconnection). Bu çağrılardan her protokolü türüne bağlıdır. Bu çağrı okuma veya yazma için bir dosya sunucusunda açmayın. Veri okumaya veya yazmaya yapmak istiyorsanız, dosya ayrı bir adım olarak açmanız gerekir.  
  
 Çoğu Internet oturumlarının `CInternetSession` nesne çalışır el el ile bir [CInternetFile](../mfc/reference/cinternetfile-class.md) nesnesi:  
  
-   Bir Internet oturumu için bir örneğini oluşturmanız gerekir [CInternetSession](../mfc/reference/cinternetsession-class.md).  
  
-   Internet oturumunuzu okur veya veri yazar, bir örneğini oluşturmanız gerekir `CInternetFile` (veya alt sınıfları [CHttpFile](../mfc/reference/chttpfile-class.md) veya [CGopherFile](../mfc/reference/cgopherfile-class.md)). Veri okuma yapmanın en kolay yolu çağırmaktır [CInternetSession::OpenURL](../mfc/reference/cinternetsession-class.md#openurl). Bu işlev bir Evrensel Kaynak Konum Belirleyicisi (tarafından sağlanan URL) ayrıştırır, URL tarafından belirtilen sunucu bir bağlantı açar ve salt okunur döndürür `CInternetFile` nesnesi. `CInternetSession::OpenURL`bir protokol türüne özgü değildir — tüm FTP, HTTP veya gopher URL'sini aynı çağrı çalışır. `CInternetSession::OpenURL`Yerel dosyalarıyla'bile çalışır (döndüren bir `CStdioFile` yerine bir `CInternetFile`).  
  
-   Oturum okumaz veya veri yazma Internet bağlantınızın ancak gerçekleştirirse, bir FTP dizindeki dosyayı silme gibi diğer görevler, bir örneğini oluşturmak gerekmeyebilir `CInternetFile`.  
  
 Oluşturmanın iki yolu vardır bir `CInternetFile` nesnesi:  
  
-   Kullanırsanız `CInternetSession::OpenURL` çağrısı, sunucu bağlantısı kurmak için `OpenURL` döndüren bir `CStdioFile`.  
  
-   Varsa kullanmak **CInternetSession::GetFtpConnection**, `GetGopherConnection`, veya `GetHttpConnection` sunucu bağlantısı kurmak için çağırmalısınız `CFtpConnection::OpenFile`, `CGopherConnection::OpenFile`, veya **CHttpConnection::OpenRequest,**  sırasıyla döndürmek için bir `CInternetFile`, `CGopherFile`, veya `CHttpFile`sırasıyla.  
  
 Internet istemci uygulaması uygulamaya ilişkin adımlar, temel genel bir Internet istemcisi oluşturduğunuz bağlı olarak farklılık **OpenURL** veya birini kullanarak bir protokole özgü istemci **GetConnection** İşlevler.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz  
  
-   [Genel FTP, HTTP ve gopher çalışan Internet istemci uygulaması nasıl yazma](../mfc/steps-in-a-typical-internet-client-application.md)  
  
-   [Bir dosyayı açan bir FTP istemci uygulaması nasıl yazma](../mfc/steps-in-a-typical-ftp-client-application.md)  
  
-   [Bir dosya açılmaz ancak dosya silme gibi bir dizin işlemi gerçekleştiren bir FTP istemci uygulaması nasıl yazma](../mfc/steps-in-a-typical-ftp-client-application-to-delete-a-file.md)  
  
-   [Gopher istemci uygulaması yazma biçimini](../mfc/steps-in-a-typical-gopher-client-application.md)  
  
-   [HTTP istemci uygulamanın nasıl yazma](../mfc/steps-in-a-typical-http-client-application.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Win32 Internet Uzantıları (WinINet)](../mfc/win32-internet-extensions-wininet.md)   
 [Internet istemci uygulamaları oluşturmak için MFC sınıfları](../mfc/mfc-classes-for-creating-internet-client-applications.md)   
 [Internet İstemci Sınıfları için Önkoşullar](../mfc/prerequisites-for-internet-client-classes.md)
