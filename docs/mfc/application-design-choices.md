---
title: "Uygulama tasarımı seçimleri | Microsoft Docs"
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
- design
- application design [MFC], design goals
- application design [MFC], Internet applications
- Internet applications [MFC], designing applications
- Internet [MFC], vs. intranets
- applications [MFC], Internet
- server applications [MFC], vs. client applications on Internet
- client applications [MFC], vs. server applications on Internet
ms.assetid: 9b96172c-b4d4-4c69-bfb2-226ce0de6d08
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4b78c4c086b40f786d86411c99279245704a48a8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="application-design-choices"></a>Uygulama Tasarımı Seçimleri
Bu makalede Internet için programlama yaparken dikkate alınması gereken tasarım sorunlardan bazıları açıklanmaktadır.  
  
 Bu makalede ele alınan konular şunlardır:  
  
-   [İntranet ve Internet](#_core_intranet_versus_internet)  
  
-   [İstemci veya sunucu uygulaması](#_core_client_or_server_application)  
  
-   [](#_core_the_web_page)  
  
-   [Tarayıcı veya tek başına uygulama](#_core_browser_or_standalone)  
  
-   [Internet üzerindeki COM](#_core_com_on_the_internet)  
  
-   [İstemci Veri Hizmetleri indirin](#_core_client_data_download_services)  
  
 Programınızı yazmayı şimdi başlatmak için bkz: hazırsanız [MFC uygulamaları yazma](../mfc/writing-mfc-applications.md).  
  
##  <a name="_core_intranet_versus_internet"></a>İntranet ve Internet  
 Birçok uygulama, Internet'te çalışmasına ve tarayıcısı ve Internet erişimi olan herkes erişebilir. İşletmeler protokolleriyle kullanan şirket çapında ağlar ve Web tarayıcıları, intranetler da uyguluyor. İntranet kolayca yükseltilebilir, merkezi bir kaynak şirket çapında bilgi sunar. Bunlar, yazılım yükseltme, dağıtma ve anketler tablo haline getirme için müşteri desteği ve bilgi teslimi için kullanılabilir. Aşağıdaki tabloda, intranet ve Internet özellikleri karşılaştırılır.  
  
|Internet|İntranet|  
|--------------|--------------|  
|Düşük bant genişliği|Yüksek bant genişliği|  
|Düşük güvenlik verilerinin ve sistemler|Veri ve sistemler denetimli erişim|  
|İçerik en az denetim|İçeriğin yüksek denetim|  
  
##  <a name="_core_client_or_server_application"></a>İstemci veya sunucu uygulaması  
 Uygulamanızı bir istemci bilgisayara veya bir sunucu bilgisayarında çalıştırabilirsiniz. Uygulamanız da bir sunucu üzerinde depolanabilir ve sonra Internet'te yüklediğiniz ve bir istemci bilgisayarda çalışması. MFC WinINet sınıfları istemci uygulamaları için dosyalarını indirmek için kullanılır. MFC ve zaman uyumsuz ad sınıfları dosyalarını indirmek ve özellikleri denetlemek için kullanılır. ActiveX denetimleri ve etkin belgeler için sınıflar istemci uygulamaları için ve bir istemcide çalışmasına izin sunucusundan yüklenen uygulamalar için kullanılır.  
  
##  <a name="_core_the_web_page"></a>Web sayfası: HTML, etkin belgeler ActiveX denetimleri  
 Microsoft, bir Web sayfasında içerik sağlama çeşitli yollarını sunar. Web sayfaları, standart HTML veya HTML kullanabileceğiniz ActiveX denetimleri gibi dinamik içerik sağlamak için nesne etiketini gibi uzantıları.  
  
 Web tarayıcıları genellikle HTML sayfaları görüntüler. Etkin belgeler, COM özellikli bir tarayıcı basit noktası tıklatma arabiriminde uygulamanızın verilerini de görüntüleyebilirsiniz. Etkin belge sunucunuzu, tüm istemci alanında kendi menüleri ve araç çubuklarını belgesi, tam çerçeve görüntüleyebilirsiniz.  
  
 ActiveX denetimleri yazdığınız zaman uyumsuz olarak sunucusundan indirilen ve bir Web sayfasında görüntülenir. Bir komut dosyası dili VBScript gibi bilgileri sunucuya göndermeden önce istemci tarafı doğrulama gerçekleştirmek için kullanabilirsiniz.  
  
##  <a name="_core_browser_or_standalone"></a>Tarayıcı veya tek başına uygulama  
 HTML sayfası ve bir tarayıcıda görüntülenen etkin belge sunucuları katıştırılmış ActiveX denetimlerini yazabilirsiniz. Bir Web sunucusundaki ISAPI uygulamanızı çalıştırmak için bir istek göndermek için bir düğme içeren HTML sayfaları yazabilirsiniz. Dosyaları indirin ve tarayıcı uygulaması kullanmadan, kullanıcı bilgilerini görüntülemek için Internet protokolleri kullanır tek başına bir uygulama yazabilirsiniz.  
  
##  <a name="_core_com_on_the_internet"></a>Internet üzerindeki COM  
 ActiveX denetimleri, etkin belgeler ve zaman uyumsuz adlar COM (Bileşen Nesne modeli) teknolojileri kullanır.  
  
 ActiveX denetimleri Internet sitelerinde belgeler ve sayfalar için dinamik içerik sağlar. COM ile ActiveX denetimlerini ve tam çerçeve belgeleri etkin belgeler kullanarak oluşturabilirsiniz.  
  
 Bir artımlı dahil olmak üzere iyi bir Internet ortamında gerçekleştirmek denetimi etkinleştirmek için özellikler zaman uyumsuz adlar sağlamak veya veri indirmek aşamalı anlamına gelir. Denetimler de iyi ayrıca verilerini zaman uyumsuz olarak aynı anda alma diğer denetimleri ile çalışması gerekir.  
  
##  <a name="_core_client_data_download_services"></a>İstemci Veri Hizmetleri indirin  
 WinINet ve zaman uyumsuz adları için istemci aktarım verilerini yardımcı olacak API'leri iki kümeleridir. Büyük .gif ve .avi dosyaları ve ActiveX denetimlerini HTML sayfanızda varsa, zaman uyumsuz olarak zaman uyumsuz adlar kullanılarak veya WinINet zaman uyumsuz olarak kullanarak yükleyerek kullanıcıya yanıt hızını artırabilir.  
  
 Internet'teki ortak görev verileri aktarıyor. Etkin teknoloji (örneğin bir ActiveX denetimini varsa) zaten kullanıyorsanız, bunu indirilirken veri aşamalı olarak işlemek için zaman uyumsuz adlar kullanabilirsiniz. WinINet, HTTP, FTP ve gopher gibi ortak Internet protokolleri kullanarak veri aktarmak için kullanabilirsiniz. Her iki yöntem Protokolü bağımsızlığı sağlayın ve WinSock ve TCP/IP'yi kullanmanın bir soyut katman sağlar. Kullanmaya devam edebilirsiniz [WinSock](../mfc/windows-sockets-in-mfc.md) doğrudan.  
  
 Aşağıdaki tabloda Internet üzerinden veri aktarımı için MFC kullanarak çeşitli yolları özetler.  
  
|Bu iletişim kuralı kullanın|Bu koşullar altında|Bu sınıflarını kullanma|  
|-----------------------|----------------------------|-------------------------|  
|[Internet indirme kullanarak zaman uyumsuz adlar](../mfc/asynchronous-monikers-on-the-internet.md)|COM, ActiveX denetimlerini kullanarak zaman uyumsuz aktarım için ve tüm Internet Protokolü.|[CAsyncMonikerFile](../mfc/reference/casyncmonikerfile-class.md), [CDataPathProperty](../mfc/reference/cdatapathproperty-class.md)|  
|[WinINet](../mfc/win32-internet-extensions-wininet.md)|HTTP, FTP ve gopher Internet protokolleri için. Veri eşzamanlı veya zaman uyumsuz olarak aktarılabilir ve sistem genelinde önbellekte depolanır.|[CInternetSession](../mfc/reference/cinternetsession-class.md), [CFtpFileFind](../mfc/reference/cftpfilefind-class.md), [CGopherFileFind](../mfc/reference/cgopherfilefind-class.md)ve çok daha fazlası.|  
|[WinSock](../mfc/windows-sockets-in-mfc.md)|Maksimum etkinlik ve denetim için. Yuva ve protokolleriyle anlaşılmasını gerektirir.|[CSocket](../mfc/reference/csocket-class.md), [CAsyncSocket](../mfc/reference/casyncsocket-class.md)|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC Internet programlama görevleri](../mfc/mfc-internet-programming-tasks.md)   
 [MFC Internet Programlama temelleri](../mfc/mfc-internet-programming-basics.md)   
 [Win32 Internet Uzantıları (WinINet)](../mfc/win32-internet-extensions-wininet.md)   
 [Internet'teki Zaman Uyumsuz Adlar](../mfc/asynchronous-monikers-on-the-internet.md)

