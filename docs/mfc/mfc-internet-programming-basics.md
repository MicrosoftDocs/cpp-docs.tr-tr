---
title: MFC Internet Programlama temelleri | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- ISAPI extensions, programming with ISAPI
- Internet applications [MFC]
- ISAPI
- ActiveX controls [MFC], Internet
- programming [MFC], Internet
- Web applications [MFC], MFC classes
- ISAPI filters [MFC], programming with ISAPI
- Internet applications [MFC], ActiveX controls
- Internet applications [MFC], writing
- Internet applications [MFC], Active technology
- Active technology [MFC]
- Internet content [MFC]
- WinInet classes [MFC]
ms.assetid: 6df2dfd0-6e3f-4587-9d01-2a32f00f8a6f
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1c03cdca832dcf0627ad033082085661c3b26847
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/03/2018
---
# <a name="mfc-internet-programming-basics"></a>MFC Internet Programlama Temelleri
Microsoft, istemci ve sunucu uygulamaları programlama için birçok API'ler sağlar. Internet için birçok yeni uygulama yazılmış ve yeni uygulama türlerini teknolojileri, tarayıcı yetenekleri ve güvenlik seçeneklerini değiştir yazılır. Tarayıcılar World Wide Web erişimi sağlama ve metin, grafik, ActiveX denetimleri ve belgeleri içeren HTML sayfalarını görüntüleme istemci bilgisayarlarda çalıştırın. Sunucuları, FTP, HTTP ve gopher hizmetleri sağlamak ve sunucu uzantısı uygulamaları CGI kullanmanın çalıştırın. Özel uygulamanızı bilgilerini almak ve veri Internet'te sağlayın.  
  
 ![İstemci ve sunucu uygulamaları](../mfc/media/vc38bq1.gif "vc38bq1")  
  
 MFC Internet programlama destekleyen sınıflar sağlar. Kullanabileceğiniz [COleControl](../mfc/reference/colecontrol-class.md) ve [CDocObjectServer](../mfc/reference/cdocobjectserver-class.md) ve ilgili ActiveX denetimlerini ve etkin belgeler yazmak için MFC sınıfları. MFC sınıfları gibi kullanabilir [CInternetSession](../mfc/reference/cinternetsession-class.md), [CFtpConnection](../mfc/reference/cftpconnection-class.md), ve [CAsyncMonikerFile](../mfc/reference/casyncmonikerfile-class.md) dosya ve FTP gibi Internet protokolleri kullanarak bilgi almak için HTTP ve gopher.  
  
## <a name="in-this-section"></a>Bu Bölümde  
  
-   [Internet ile İlgili MFC Sınıfları](../mfc/internet-related-mfc-classes.md)  
  
-   [Konuya Göre Internet Bilgileri](../mfc/internet-information-by-topic.md)  
  
-   [Göreve Göre Internet Bilgileri](../mfc/internet-information-by-task.md)  
  
-   [Internet'te Etkin Teknoloji](../mfc/active-technology-on-the-internet.md)  
  
-   [WinInet Temelleri](../mfc/wininet-basics.md)  
  
-   [HTML Temelleri](../mfc/html-basics.md)  
  
-   [HTTP Temelleri](../mfc/http-basics.md)  
  
## <a name="related-sections"></a>İlgili Bölümler  
  
-   [Internet'te ActiveX Denetimleri](../mfc/activex-controls-on-the-internet.md)  
  
-   [Internet'te Etkin Belgeler](../mfc/active-documents-on-the-internet.md)  
  
-   [Internet'teki Zaman Uyumsuz Adlar](../mfc/asynchronous-monikers-on-the-internet.md)  
  
-   [Win32 Internet Uzantıları (WinInet)](../mfc/win32-internet-extensions-wininet.md)  
  
-   [MFC Internet Programlama Görevleri](../mfc/mfc-internet-programming-tasks.md)  
  
-   [Uygulama Tasarımı Seçimleri](../mfc/application-design-choices.md)  
  
-   [MFC Uygulamaları Yazma](../mfc/writing-mfc-applications.md)  
  
-   [Internet Uygulamalarını Test Etme](../mfc/testing-internet-applications.md)  
  
-   [Internet güvenliği](../mfc/internet-security-cpp.md)  
  
-   [DHTML Denetimleri için ATL Desteği](../atl/atl-support-for-dhtml-controls.md)  
  
##  <a name="_core_web_sites_for_more_information"></a>Daha fazla bilgi için Web siteleri  
 Microsoft Internet teknolojisi hakkında ek bilgi için bkz: [Microsoft Developer Network (MSDN)](http://go.microsoft.com/fwlink/p/?linkid=56322) Web sitesi. (Bağlantılar bildirilmeksizin değiştirilebilir.)  
  
 Bu Web sitesi geliştiricileri için Microsoft geliştirme araçları ve teknolojileri ve son ve yaklaşan konferans ilgili üst hikayeler kullanma hakkında bilgi içerir. Bu sayfadan .NET ve XML Geliştirici Merkezi gibi birçok ilgili Geliştirici sitelere atlayabilirsiniz. Ayrıca, beta SDK'ları ve örnekleri de indirebilirsiniz.  
  
 [World Wide Web Konsorsiyumu (W3C)](http://go.microsoft.com/fwlink/p/?linkid=37125) HTML, HTTP, CGI ve diğer World Wide Web teknolojileri için belirtimler yayımlar.  
  
##  <a name="_core_more_internet_help"></a>Internet ile ilgili daha fazla yardım  
 Windows SDK'sı OLE bölümü OLE programlama hakkında ek bilgi içerir. Bu bilgiler MFC sınıfları aracılığıyla yapmak yerine, doğrudan, Win32 WinINet işlevlerini kullanma hakkında ayrıntılı bilgi sağlar. Ayrıca, Internet teknolojileri hakkında genel bilgi içerir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  



