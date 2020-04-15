---
title: Uygulama Tasarımı Seçimleri
ms.date: 09/12/2019
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
ms.openlocfilehash: 89f3e5c108de1cf7b3b73a33a08e2c50b1333c92
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374636"
---
# <a name="application-design-choices"></a>Uygulama Tasarımı Seçimleri

Bu makalede, Internet için programlama yaparken göz önünde bulundurulması gereken bazı tasarım sorunları tartışılmaktadır.

Bu makalede ele alınan konular şunlardır:

- [Intranet Karşı İnternet](#_core_intranet_versus_internet)

- [İstemci veya Sunucu Uygulaması](#_core_client_or_server_application)

- [Web Sayfası](#_core_the_web_page)

- [Tarayıcı veya Tek Başına Uygulama](#_core_browser_or_standalone)

- [Internet'te COM](#_core_com_on_the_internet)

- [İstemci Veri İndirme Hizmetleri](#_core_client_data_download_services)

Programınızı yazmaya şimdi başlamaya hazırsanız, [MFC Uygulamaları Yazma'ya](../mfc/writing-mfc-applications.md)bakın.

## <a name="intranet-versus-internet"></a><a name="_core_intranet_versus_internet"></a>Intranet Karşı İnternet

Birçok uygulama Internet'te çalışır ve tarayıcısı ve Internet erişimi olan herkes tarafından erişilebilir. İşletmeler ayrıca TCP/IP protokolleri ve Web tarayıcıları kullanarak şirket çapında ağlar olan intranetleri de uyguluyor. Intranet'ler, şirket çapında bilgi için kolayca yükseltilebilir, merkezi bir kaynak sunar. Bunlar, yazılımları yükseltmek, anketleri sunmak ve tablolama, müşteri desteği ve bilgi teslimi için kullanılabilir. Aşağıdaki tablo, Internet ve intranet özelliklerini karşılaştırın.

|Internet|Intranet|
|--------------|--------------|
|Düşük bant genişliği|Yüksek bant genişliği|
|Veri ve sistemlerin daha az güvenliği|Verilere ve sistemlere kontrollü erişim|
|İçeriğin en az kontrolü|İçeriğin yüksek kontrolü|

## <a name="client-or-server-application"></a><a name="_core_client_or_server_application"></a>İstemci veya Sunucu Uygulaması

Uygulamanız istemci bilgisayarda veya sunucu bilgisayarında çalışabilir. Uygulamanız bir sunucuda da depolanabilir ve daha sonra Internet üzerinden indirilebilir ve istemci bilgisayarda çalıştırılabilir. MFC WinInet sınıfları, istemci uygulamalarının dosyalarını karşıdan yüklemesi için kullanılır. Dosyaları indirmek ve özellikleri denetlemek için MFC ve asynchronous takma aparatları kullanılır. ActiveX denetimleri ve Etkin belgeler için sınıflar istemci uygulamaları ve istemci üzerinde çalıştırmak için sunucudan indirilen uygulamalar için kullanılır.

## <a name="the-web-page-html-active-documents-activex-controls"></a><a name="_core_the_web_page"></a>Web Sayfası: HTML, Aktif Belgeler, ActiveX Denetimleri

Microsoft, Bir Web sayfasında içerik sağlamanın çeşitli yollarını sunar. Web sayfaları, ActiveX denetimleri gibi dinamik içerik sağlamak için nesne etiketi gibi standart HTML veya HTML uzantılarını kullanabilir.

Web tarayıcıları genellikle HTML sayfalarını görüntüler. Etkin belgeler, uygulamanızın verilerini COM özellikli bir tarayıcının basit nokta ve tıkla arabiriminde de görüntüleyebilir. Etkin belge sunucunuz belgenizi, tam çerçevenizi tüm istemci alanında, kendi menüleri ve araç çubuklarıyla görüntüleyebilir.

Yazdığınız ActiveX denetimleri sunucudan eşit olarak indirilebilir ve bir Web sayfasında görüntülenebilir. Sunucuya bilgi göndermeden önce istemci tarafı doğrulamagerçekleştirmek için VBScript gibi bir komut dosyası dili kullanabilirsiniz.

## <a name="browser-or-stand-alone-application"></a><a name="_core_browser_or_standalone"></a>Tarayıcı veya Tek Başına Uygulama

HTML sayfasına katıştırılmış ActiveX denetimleri ve tarayıcıda görüntülenen Etkin belge sunucuları yazabilirsiniz. ISAPI uygulamanızı bir Web sunucusunda çalıştırmak için istek göndermek için düğme içeren HTML sayfaları yazabilirsiniz. Dosyaları indirmek ve bilgileri tarayıcı uygulaması kullanmadan kullanıcınıza görüntülemek için Internet protokollerini kullanan tek başına bir uygulama yazabilirsiniz.

## <a name="com-on-the-internet"></a><a name="_core_com_on_the_internet"></a>Internet'te COM

ActiveX denetimleri, Etkin belgeler ve asynchronous monikers tüm COM (Bileşen Nesne Modeli) teknolojilerini kullanır.

ActiveX denetimleri, Internet sitelerindeki belgelere ve sayfalara dinamik içerik sağlar. COM ile ActiveX denetimleri ve tam kare belgeleri Etkin belgeleri kullanarak oluşturabilirsiniz.

Asynchronous monikers veri indirmek için artımlı veya ilerici araçlar da dahil olmak üzere bir Internet ortamında iyi performans için bir denetim sağlamak için özellikler sağlar. Denetimler, verilerini aynı anda eşzamanlı olarak alıyor olabilecek diğer denetimlerle de iyi çalışmalıdır.

## <a name="client-data-download-services"></a><a name="_core_client_data_download_services"></a>İstemci Veri İndirme Hizmetleri

Müşterilerinize veri aktarımı nıza yardımcı olacak iki API kümesi WinInet ve eşzamanlı monikers'tir. HTML sayfanızda büyük .gif ve .avi dosyalarınız ve ActiveX denetimleriniz varsa, eşzamanlı olarak asynchronöz moniker ler kullanarak veya WinInet asynchronously kullanarak kullanıcıya yanıt verme yeteneğini artırabilirsiniz.

Internet'te yaygın bir görev veri aktarımıdır. Active teknolojisini zaten kullanıyorsanız (örneğin, ActiveX denetiminiz varsa), verileri karşıdan yüklerken aşamalı olarak işlemek için eşzamanlı moniker'ler kullanabilirsiniz. HTTP, FTP ve gopher gibi yaygın Internet protokollerini kullanarak veri aktarmak için WinInet'i kullanabilirsiniz. Her iki yöntem de protokol bağımsızlığı sağlar ve WinSock ve TCP/IP'yi kullanmak için soyut bir katman sağlar. [WinSock'u](../mfc/windows-sockets-in-mfc.md) doğrudan kullanabilirsiniz.

Aşağıdaki tablo, Internet üzerinden veri aktarmak için MFC kullanmanın çeşitli yollarını özetlemektedir.

|Bu protokolü kullanma|Bu koşullar altında|Bu sınıfları kullanma|
|-----------------------|----------------------------|-------------------------|
|[Asynchronous Monikers kullanarak Internet İndirme](../mfc/asynchronous-monikers-on-the-internet.md)|COM, ActiveX denetimleri ve herhangi bir Internet protokolü kullanarak eşzamanlı aktarım için.|[CAsyncMonikerFile](../mfc/reference/casyncmonikerfile-class.md), [CDataPathProperty](../mfc/reference/cdatapathproperty-class.md)|
|[WinInet](../mfc/win32-internet-extensions-wininet.md)|HTTP, FTP ve gopher için Internet protokolleri için. Veriler eşzamanlı veya eşzamanlı olarak aktarılabilir ve sistem çapında bir önbellekte depolanabilir.|[CInternetSession](../mfc/reference/cinternetsession-class.md), [CFtpFileFind](../mfc/reference/cftpfilefind-class.md), [CGopherFileFind](../mfc/reference/cgopherfilefind-class.md), ve daha birçok.|
|[Winsock](../mfc/windows-sockets-in-mfc.md)|Maksimum verimlilik ve kontrol için. Soketlerin ve TCP/IP protokollerinin anlaşılmasını gerektirir.|[CSocket](../mfc/reference/csocket-class.md), [CAsyncSocket](../mfc/reference/casyncsocket-class.md)|

## <a name="see-also"></a>Ayrıca bkz.

[MFC Internet Programlama Görevleri](../mfc/mfc-internet-programming-tasks.md)<br/>
[MFC İnternet Programlama Temelleri](../mfc/mfc-internet-programming-basics.md)<br/>
[Win32 İnternet Uzantıları (WinInet)](../mfc/win32-internet-extensions-wininet.md)<br/>
[İnternette Asynchronous Monikers](../mfc/asynchronous-monikers-on-the-internet.md)
