---
description: 'Daha fazla bilgi edinin: uygulama tasarımı seçimleri'
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
ms.openlocfilehash: 0402cfe8cb58ed538e1429d2edc4f95cc9a23a0c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97335923"
---
# <a name="application-design-choices"></a>Uygulama Tasarımı Seçimleri

Bu makalede, Internet için programlama yaparken göz önünde bulundurmanız gereken bazı tasarım sorunları ele alınmaktadır.

Bu makalede ele alınan konular şunları içerir:

- [Intranet ve Internet karşılaştırması](#_core_intranet_versus_internet)

- [İstemci veya sunucu uygulaması](#_core_client_or_server_application)

- [Web sayfası](#_core_the_web_page)

- [Tarayıcı veya Stand-Alone uygulaması](#_core_browser_or_standalone)

- [Internet üzerinde COM](#_core_com_on_the_internet)

- [İstemci verileri Indirme Hizmetleri](#_core_client_data_download_services)

Programınızı yazmaya hemen başlamaya hazırsanız bkz. [MFC uygulamaları yazma](writing-mfc-applications.md).

## <a name="intranet-versus-internet"></a><a name="_core_intranet_versus_internet"></a> Intranet ve Internet karşılaştırması

Birçok uygulama Internet üzerinde çalışır ve tarayıcı ve Internet erişimi olan herkes tarafından erişilebilir. İşletmeler, TCP/IP protokolleri ve Web tarayıcıları kullanan şirket genelinde ağlar olan intranetleri de uygular. İntranetlerde şirket genelinde bilgiler için kolayca yükseltilebilir, merkezi bir kaynak sunulur. Bunlar, yazılım yükseltme, anketler için, müşteri desteği ve bilgi teslimi için kullanılabilirler. Aşağıdaki tabloda Internet ve intranet özelliklerinin özellikleri karşılaştırılmaktadır.

|İnternet|Intranet|
|--------------|--------------|
|Düşük bant genişliği|Yüksek bant genişliği|
|Verilerin ve sistemlerin azaltılmış güvenliği|Verilere ve sistemlere denetimli erişim|
|En az içerik denetimi|İçeriğin yüksek denetimi|

## <a name="client-or-server-application"></a><a name="_core_client_or_server_application"></a> İstemci veya sunucu uygulaması

Uygulamanız bir istemci bilgisayarda veya bir sunucu bilgisayarda çalışabilir. Uygulamanız Ayrıca bir sunucuda depolanabilir ve sonra Internet üzerinden indirilip istemci bilgisayarında çalıştırılabilir. MFC WinInet sınıfları, istemci uygulamalarının dosya indirmesini sağlamak için kullanılır. MFC ve zaman uyumsuz bilinen ad sınıfları dosyaları ve denetim özelliklerini indirmek için kullanılır. ActiveX denetimleri ve etkin belgeler için sınıflar, istemci uygulamaları ve sunucudan çalıştırılmak üzere sunucudan indirilen uygulamalar için kullanılır.

## <a name="the-web-page-html-active-documents-activex-controls"></a><a name="_core_the_web_page"></a> Web sayfası: HTML, etkin belgeler, ActiveX denetimleri

Microsoft, bir Web sayfasında içerik sağlamanın çeşitli yollarını sunmaktadır. Web sayfaları, ActiveX denetimleri gibi dinamik içerik sağlamak için standart HTML veya nesne etiketi gibi HTML uzantıları kullanabilir.

Web tarayıcıları genellikle HTML sayfalarını görüntüler. Etkin belgeler ayrıca, bir COM etkin tarayıcının basit nokta ve tıklama arabiriminde uygulamanızın verilerini de görüntüleyebilir. Etkin belge sunucunuz, kendi menü ve araç çubuklarıyla birlikte tüm istemci alanında Belgenizin tamamını görüntüleyebilir.

Yazdığınız ActiveX denetimleri sunucudan zaman uyumsuz olarak indirilebilir ve bir Web sayfasında görüntülenebilir. Sunucuya bilgi göndermeden önce, istemci tarafı doğrulaması gerçekleştirmek için VBScript gibi bir betik dili kullanabilirsiniz.

## <a name="browser-or-stand-alone-application"></a><a name="_core_browser_or_standalone"></a> Tarayıcı veya Stand-Alone uygulaması

Bir tarayıcıda görüntülenen bir HTML sayfasına ve etkin belge sunucularına katıştırılmış ActiveX denetimleri yazabilirsiniz. Bir Web sunucusunda ISAPI uygulamanızı çalıştırmak için bir istek göndermek üzere bir düğme içeren HTML sayfaları yazabilirsiniz. Bir tarayıcı uygulaması kullanmadan, dosyaları indirmek ve bilgileri kullanıcıya göstermek için Internet protokolleri kullanan tek başına bir uygulama yazabilirsiniz.

## <a name="com-on-the-internet"></a><a name="_core_com_on_the_internet"></a> Internet üzerinde COM

ActiveX denetimleri, etkin belgeler ve zaman uyumsuz bilinen adlar tüm COM (bileşen nesne modeli) teknolojilerini kullanır.

ActiveX denetimleri, Internet sitelerindeki belgelere ve sayfalarına dinamik içerik sağlar. COM ile, etkin belgeleri kullanarak ActiveX denetimleri ve tam çerçeve belgeleri oluşturabilirsiniz.

Zaman uyumsuz bilinen adlar, verileri indirmek için artımlı veya aşamalı bir yol da dahil olmak üzere bir denetimin Internet ortamında iyi bir şekilde gerçekleştirmesini sağlayan özellikler sunar. Denetimler ayrıca aynı anda verilerini zaman uyumsuz olarak almak için aynı zamanda diğer denetimlerle de çalışır.

## <a name="client-data-download-services"></a><a name="_core_client_data_download_services"></a> İstemci verileri Indirme Hizmetleri

İstemcinizdeki verileri aktarmaya yardımcı olacak iki API kümesi, Winınet ve zaman uyumsuz olan addır. HTML sayfanızda büyük. gif ve. avi dosyalarınız ve ActiveX denetimleri varsa, zaman uyumsuz adlar kullanarak veya WinInet zaman uyumsuz olarak indirerek kullanıcıya yanıt verme hızını artırabilirsiniz.

Internet üzerindeki ortak bir görev veri aktarıyordu. Zaten etkin teknolojiyi kullanıyorsanız (örneğin, bir ActiveX denetiminiz varsa), indirme sırasında verileri aşamalı olarak işlemek için zaman uyumsuz bilinen adlar kullanabilirsiniz. HTTP, FTP ve gopher gibi ortak Internet protokollerini kullanarak verileri aktarmak için WinInet kullanabilirsiniz. Her iki yöntem de protokol bağımsızlık sağlar ve WinSock ve TCP/IP kullanarak soyut bir katman sağlar. Hala [Winsock](windows-sockets-in-mfc.md) 'ı doğrudan kullanabilirsiniz.

Aşağıdaki tabloda, verileri Internet üzerinden aktarmak için MFC kullanmanın çeşitli yolları özetlenmektedir.

|Bu protokolü kullan|Bu koşullar altında|Bu sınıfları kullanma|
|-----------------------|----------------------------|-------------------------|
|[Zaman uyumsuz adlar kullanarak Internet Indirme](asynchronous-monikers-on-the-internet.md)|COM, ActiveX denetimleri ve herhangi bir Internet Protokolü kullanılarak zaman uyumsuz aktarım için.|[CAsyncMonikerFile](reference/casyncmonikerfile-class.md), [CDataPathProperty](reference/cdatapathproperty-class.md)|
|[WinInet](win32-internet-extensions-wininet.md)|HTTP, FTP ve gopher için Internet protokolleri için. Veriler zaman uyumlu veya zaman uyumsuz olarak aktarılabilir ve sistem genelinde bir önbellekte depolanabilir.|[CInternetSession](reference/cinternetsession-class.md), [CFtpFileFind](reference/cftpfilefind-class.md), [CGopherFileFind](reference/cgopherfilefind-class.md)ve çok daha fazlası.|
|[WinSock](windows-sockets-in-mfc.md)|En yüksek verimlilik ve denetim. Yuvalar ve TCP/IP protokollerinin anlaşılmasına gerek duyar.|[CSocket](reference/csocket-class.md), [CAsyncSocket](reference/casyncsocket-class.md)|

## <a name="see-also"></a>Ayrıca bkz.

[MFC Internet programlama görevleri](mfc-internet-programming-tasks.md)<br/>
[MFC Internet Programlama Temelleri](mfc-internet-programming-basics.md)<br/>
[Win32 Internet Uzantıları (Winınet)](win32-internet-extensions-wininet.md)<br/>
[Internet 'te zaman uyumsuz bilinen adlar](asynchronous-monikers-on-the-internet.md)
