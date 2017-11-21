---
title: MFC Internet Programlama temelleri | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
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
caps.latest.revision: "18"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: a0c436a7fc1b7d567ed6cc684e76b46628de97d9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="mfc-internet-programming-basics"></a>MFC Internet Programlama Temelleri
Microsoft, istemci ve sunucu uygulamaları programlama için birçok API'ler sağlar. Internet için birçok yeni uygulama yazılmış ve yeni uygulama türlerini teknolojileri, tarayıcı yetenekleri ve güvenlik seçeneklerini değiştir yazılır. Tarayıcılar World Wide Web erişimi sağlama ve metin, grafik, ActiveX denetimleri ve belgeleri içeren HTML sayfalarını görüntüleme istemci bilgisayarlarda çalıştırın. Sunucuları, FTP, HTTP ve gopher hizmetleri sağlamak ve sunucu uzantısı uygulamaları CGI kullanmanın çalıştırın. Özel uygulamanızı bilgilerini almak ve veri Internet'te sağlayın.  
  
 ![İstemci ve sunucu uygulamaları](../mfc/media/vc38bq1.gif "vc38bq1")  
  
 MFC Internet programlama destekleyen sınıflar sağlar. Kullanabileceğiniz [COleControl](../mfc/reference/colecontrol-class.md) ve [CDocObjectServer](../mfc/reference/cdocobjectserver-class.md) ve ilgili ActiveX denetimlerini ve etkin belgeler yazmak için MFC sınıfları. MFC sınıfları gibi kullanabilir [CInternetSession](../mfc/reference/cinternetsession-class.md), [CFtpConnection](../mfc/reference/cftpconnection-class.md), ve [CAsyncMonikerFile](../mfc/reference/casyncmonikerfile-class.md) dosya ve FTP gibi Internet protokolleri kullanarak bilgi almak için HTTP ve gopher.  
  
## <a name="in-this-section"></a>Bu Bölümde  
  
-   [Internet ile ilgili MFC sınıfları](../mfc/internet-related-mfc-classes.md)  
  
-   [Konuya göre Internet bilgileri](../mfc/internet-information-by-topic.md)  
  
-   [Göreve göre Internet bilgileri](../mfc/internet-information-by-task.md)  
  
-   [Internet'te etkin teknoloji](../mfc/active-technology-on-the-internet.md)  
  
-   [WinINet temelleri](../mfc/wininet-basics.md)  
  
-   [HTML temelleri](../mfc/html-basics.md)  
  
-   [HTTP temelleri](../mfc/http-basics.md)  
  
## <a name="related-sections"></a>İlgili Bölümler  
  
-   [Internet'te ActiveX denetimleri](../mfc/activex-controls-on-the-internet.md)  
  
-   [Internet'te etkin belgeler](../mfc/active-documents-on-the-internet.md)  
  
-   [Internet'teki zaman uyumsuz adlar](../mfc/asynchronous-monikers-on-the-internet.md)  
  
-   [Win32 Internet Uzantıları (WinINet)](../mfc/win32-internet-extensions-wininet.md)  
  
-   [MFC Internet programlama görevleri](../mfc/mfc-internet-programming-tasks.md)  
  
-   [Uygulama tasarımı seçimleri](../mfc/application-design-choices.md)  
  
-   [MFC uygulamaları yazma](../mfc/writing-mfc-applications.md)  
  
-   [Internet uygulamalarını test etme](../mfc/testing-internet-applications.md)  
  
-   [Internet güvenliği](../mfc/internet-security-cpp.md)  
  
-   [DHTML denetimleri için ATL desteği](../atl/atl-support-for-dhtml-controls.md)  
  
##  <a name="_core_web_sites_for_more_information"></a>Daha fazla bilgi için Web siteleri  
 Microsoft Internet teknolojisi hakkında ek bilgi için bkz: [Microsoft Developer Network (MSDN)](http://go.microsoft.com/fwlink/linkid=56322) Web sitesi. (Bağlantılar bildirilmeksizin değiştirilebilir.)  
  
 Bu Web sitesi geliştiricileri için Microsoft geliştirme araçları ve teknolojileri ve son ve yaklaşan konferans ilgili üst hikayeler kullanma hakkında bilgi içerir. Bu sayfadan .NET ve XML Geliştirici Merkezi gibi birçok ilgili Geliştirici sitelere atlayabilirsiniz. Ayrıca, beta SDK'ları ve örnekleri de indirebilirsiniz.  
  
 [World Wide Web Konsorsiyumu (W3C)](http://go.microsoft.com/fwlink/linkid=37125) HTML, HTTP, CGI ve diğer World Wide Web teknolojileri için belirtimler yayımlar.  
  
##  <a name="_core_more_internet_help"></a>Internet ile ilgili daha fazla yardım  
 Windows SDK'sı OLE bölümü OLE programlama hakkında ek bilgi içerir. Bu bilgiler MFC sınıfları aracılığıyla yapmak yerine, doğrudan, Win32 WinINet işlevlerini kullanma hakkında ayrıntılı bilgi sağlar. Ayrıca, Internet teknolojileri hakkında genel bilgi içerir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  



