---
title: Uygulama Tasarımı Seçimleri
ms.date: 11/04/2016
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
ms.openlocfilehash: cdb294e4ab808a7e4cbcec457f6e744eff9f12cb
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57302825"
---
# <a name="application-design-choices"></a>Uygulama Tasarımı Seçimleri

Bu makalede bazı İnternet'e programlama yaparken dikkate alınması gereken tasarım konularını açıklar.

Bu makalede ele alınan konular:

- [İntranet ve Internet](#_core_intranet_versus_internet)

- [İstemci veya sunucu uygulaması](#_core_client_or_server_application)

- [](#_core_the_web_page)

- [Tarayıcı veya tek başına uygulama](#_core_browser_or_standalone)

- [Internet üzerindeki COM](#_core_com_on_the_internet)

- [İstemci verilerini Hizmetleri indirin](#_core_client_data_download_services)

Programınız şimdi yazma başlatmak için bkz: hazırsanız [MFC uygulamaları yazma](../mfc/writing-mfc-applications.md).

##  <a name="_core_intranet_versus_internet"></a> İntranet ve Internet

Birçok uygulama, Internet'te çalışmasına ve tarayıcı ve Internet erişimi olan herkes erişebilir. İşletmelerin de TCP/IP protokolleriyle şirket çapında ağlara ve Web tarayıcıları intranet uyguluyor. İntranet bir kolayca yükseltilebilir, merkezi kaynak şirket çapında bilgi sunar. Bunlar, yazılımı yükseltmek için teslim ve anketler tablo haline getirme, müşteri desteği ve bilgi teslimi için kullanılabilir. Aşağıdaki tabloda, intranet ve Internet özellikleri karşılaştırılır.

|Internet|İntranet|
|--------------|--------------|
|Düşük bant genişliği|Yüksek bant genişliği|
|Düşük güvenlik verileri ve sistemleri|Veri ve sistemlere denetimli erişim|
|İçerik en az denetim|Yüksek denetim içeriği|

##  <a name="_core_client_or_server_application"></a> İstemci veya sunucu uygulaması

Uygulamanız, istemci bilgisayarda veya sunucusu bilgisayarında çalıştırabilirsiniz. Uygulamanız da bir sunucu üzerinde depolanabilir ve ardından Internet üzerinden indirilen ve bir istemci bilgisayarda çalışması. MFC WinINet sınıfları, dosyaları indirmek için istemci uygulamaları için kullanılır. MFC ve zaman uyumsuz ad sınıfları dosyalarını indirmek ve özellikleri denetlemek için kullanılır. ActiveX denetimleri ve etkin belgeler için sınıflar, bir istemcide çalışmasına sunucusundan indirilen uygulamalar ve istemci uygulamaları için kullanılır.

##  <a name="_core_the_web_page"></a> Web sayfası: HTML, etkin belgeler ActiveX denetimleri

Microsoft, bir Web sayfasında içerik sağlayan çeşitli yollar sunar. Web sayfaları, standart HTML veya HTML kullanabileceğiniz uzantılar, ActiveX denetimleri gibi dinamik içerik sağlamak, nesne etiketi gibi.

Genellikle, Web tarayıcıları HTML sayfalarını görüntüler. Etkin belgeler, COM özellikli bir tarayıcı basit ve tıklama arabiriminde uygulamanızın verilerini de görüntüleyebilirsiniz. Etkin belge sunucunuz, tüm istemci alanında kendi menüleri ve araç çubuklarını belge, tam çerçeve görüntüleyebilirsiniz.

ActiveX denetimleri, yazma, sunucudan zaman uyumsuz olarak ve bir Web sayfasında görüntülenir. VBScript gibi bir komut dosyası dili bilgi server için göndermeden önce istemci tarafı doğrulama gerçekleştirmek için kullanabilirsiniz.

##  <a name="_core_browser_or_standalone"></a> Tarayıcı veya tek başına uygulama

Bir HTML sayfası ve bir tarayıcıda görüntülenen etkin belge sunucuları katıştırılmış ActiveX denetimlerini yazabilirsiniz. Bir Web sunucusunda ISAPI uygulamanızı çalıştırmak için bir istek göndermek için bir düğme içeren HTML sayfaları yazabilirsiniz. Dosyaları indirmek ve bir tarayıcı uygulaması kullanmadan, kullanıcıya bilgileri görüntülemek için Internet protokolleri kullanan tek başına bir uygulama yazabilirsiniz.

##  <a name="_core_com_on_the_internet"></a> Internet üzerindeki COM

ActiveX denetimleri, etkin belgeler ve zaman uyumsuz adlar COM (Bileşen Nesne modeli) teknolojilerini kullanın.

ActiveX denetimleri, Internet sitelerine belgeler ve sayfalar için dinamik içerik sağlar. COM ile ActiveX denetimlerini ve tam çerçeve belgeleri etkin belgeler kullanarak oluşturabilirsiniz.

Zaman uyumsuz adlar bir artımlı iyi bir Internet ortamda gerçekleştirmek bir denetim sağlamak için özellikler sağlamak veya verileri indirmek aşamalı anlamına gelir. Denetimleri de iyi Ayrıca kendi verilerini zaman uyumsuz olarak aynı anda alınıyor diğer denetimleri ile çalışması gerekir.

##  <a name="_core_client_data_download_services"></a> İstemci verilerini Hizmetleri indirin

İki veri aktarmak için istemci yardımcı olacak API'leri WinINet ve zaman uyumsuz adlar kümeleridir. Büyük .gif ve .avi dosyaları ve ActiveX denetimlerini, HTML sayfasında varsa, zaman uyumsuz adlar kullanarak veya zaman uyumsuz olarak WinINet kullanarak zaman uyumsuz olarak indirerek kullanıcıya uygulamanın yanıt verme hızını artırabilirsiniz.

Internet üzerindeki genel bir görev veri aktarıyor. Etkin teknoloji (örneğin, bir ActiveX denetimini varsa) zaten kullanıyorsanız, bunu indirilirken veri aşamalı olarak işlemek için zaman uyumsuz adlar kullanabilirsiniz. WinINet HTTP, FTP ve gopher gibi common Internet protokolleri kullanarak veri aktarmak için kullanabilirsiniz. Her iki yöntem de Protokolü bağımsızlığı ve WinSock ve TCP/IP'yi kullanarak bir soyut katman sağlar. Kullanmaya devam edebilirsiniz [WinSock](../mfc/windows-sockets-in-mfc.md) doğrudan.

Aşağıdaki tabloda Internet üzerinden veri aktarımı için MFC kullanarak çeşitli yollarını özetler.

|Bu protokol kullanın|Bu koşullar altında|Bu sınıflar kullanma|
|-----------------------|----------------------------|-------------------------|
|[Internet karşıdan kullanarak zaman uyumsuz adlar](../mfc/asynchronous-monikers-on-the-internet.md)|COM, ActiveX denetimlerini kullanarak zaman uyumsuz aktarımı için ve herhangi bir Internet Protokolü.|[CAsyncMonikerFile](../mfc/reference/casyncmonikerfile-class.md), [CDataPathProperty](../mfc/reference/cdatapathproperty-class.md)|
|[WinINet](../mfc/win32-internet-extensions-wininet.md)|HTTP, FTP ve gopher Internet protokolleri için. Veriler zaman uyumlu veya zaman uyumsuz olarak aktarılabilen ve bir sistem genelinde önbellekte depolanır.|[Cınternetsession](../mfc/reference/cinternetsession-class.md), [CFtpFileFind](../mfc/reference/cftpfilefind-class.md), [CGopherFileFind](../mfc/reference/cgopherfilefind-class.md)ve çok daha fazlası.|
|[WinSock](../mfc/windows-sockets-in-mfc.md)|En yüksek verimlilik ve denetim için. Yuva ve TCP/IP protokolleri düzeyde bilinmesini gerektirir.|[CSocket](../mfc/reference/csocket-class.md), [Casyncsocket'ini](../mfc/reference/casyncsocket-class.md)|

## <a name="see-also"></a>Ayrıca bkz.

[MFC Internet Programlama Görevleri](../mfc/mfc-internet-programming-tasks.md)<br/>
[MFC Internet Programlama Temelleri](../mfc/mfc-internet-programming-basics.md)<br/>
[Win32 Internet Uzantıları (WinInet)](../mfc/win32-internet-extensions-wininet.md)<br/>
[Internet'teki Zaman Uyumsuz Adlar](../mfc/asynchronous-monikers-on-the-internet.md)
