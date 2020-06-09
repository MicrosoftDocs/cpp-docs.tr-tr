---
title: MFC Internet Programlama Temelleri
ms.date: 11/19/2018
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
ms.openlocfilehash: 3265bffb393eeff1d8a04a41357e2b138aa0ebf7
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84615568"
---
# <a name="mfc-internet-programming-basics"></a>MFC Internet Programlama Temelleri

Microsoft, hem istemci hem de sunucu uygulamalarını programlamak için birçok API sağlar. Internet için birçok yeni uygulama yazılıyor ve teknolojiler, tarayıcı özellikleri ve güvenlik seçenekleri değiştikçe, yeni uygulama türleri yazılacak. Tarayıcılar, World Wide Web erişim sağlayan ve metin, grafik, ActiveX denetimleri ve belgeler içeren HTML sayfalarını görüntüleyen istemci bilgisayarlarda çalışır. Sunucular, FTP, HTTP ve gopher hizmetleri sağlar ve CGI kullanarak sunucu uzantısı uygulamaları çalıştırır. Özel uygulamanız bilgi alabilir ve Internet 'te veri sağlayabilir.

>[!IMPORTANT]
> ActiveX, yeni geliştirme için kullanılması gereken eski bir teknolojidir. Daha fazla bilgi için bkz. [ActiveX denetimleri](activex-controls.md).

![İstemci ve sunucu uygulamaları](../mfc/media/vc38bq1.gif "İstemci ve sunucu uygulamaları")

MFC, Internet programlamayı destekleyen sınıflar sağlar. ActiveX denetimleri ve etkin belgeler yazmak için [COleControl](reference/colecontrol-class.md) ve [CDOCOBJECTSERVER](reference/cdocobjectserver-class.md) ve ilgili MFC sınıflarını kullanabilirsiniz. FTP, HTTP ve gopher gibi Internet protokollerini kullanarak dosya ve bilgi almak için [CInternetSession](reference/cinternetsession-class.md), [CFtpConnection](reference/cftpconnection-class.md)ve [CAsyncMonikerFile](reference/casyncmonikerfile-class.md) gibi MFC sınıflarını kullanabilirsiniz.

## <a name="in-this-section"></a>Bu Bölümde

- [Internet ile Ilgili MFC sınıfları](internet-related-mfc-classes.md)

- [Konuya göre Internet bilgileri](internet-information-by-topic.md)

- [Göreve göre Internet bilgileri](internet-information-by-task.md)

- [Internet'te Etkin Teknoloji](active-technology-on-the-internet.md)

- [Winınet temelleri](wininet-basics.md)

- [HTML Temelleri](html-basics.md)

## <a name="related-sections"></a>İlgili Bölümler

- [Internet 'te ActiveX denetimleri](activex-controls-on-the-internet.md)

- [Internet 'te zaman uyumsuz bilinen adlar](asynchronous-monikers-on-the-internet.md)

- [Win32 Internet Uzantıları (Winınet)](win32-internet-extensions-wininet.md)

- [MFC Internet Programlama Görevleri](mfc-internet-programming-tasks.md)

- [Uygulama Tasarımı Seçimleri](application-design-choices.md)

- [MFC Uygulamaları Yazma](writing-mfc-applications.md)

- [Internet Uygulamalarını Test Etme](testing-internet-applications.md)

- [Internet güvenliği](internet-security-cpp.md)

- [DHTML Denetimleri İçin ATL Desteği](../atl/atl-support-for-dhtml-controls.md)

## <a name="web-sites-for-more-information"></a><a name="_core_web_sites_for_more_information"></a>Daha fazla bilgi için Web siteleri

Microsoft Internet teknolojisi hakkında daha fazla bilgi için bkz. [Microsoft Developer Network (MSDN)](https://go.microsoft.com/fwlink/p/?linkid=56322) Web sitesi. (Bağlantılar bildirimde bulunmaksızın değişebilir.)

Geliştiriciler için bu Web sitesi, Microsoft geliştirme araçları ve teknolojilerini kullanma hakkında bilgi ve en son ve gelecek konferanslara yönelik popüler yazıları içerir. Bu sayfadan, .NET ve XML Geliştirici merkezleri dahil olmak üzere birçok ilgili geliştirici sitesine atlayabilirsiniz. Beta SDK 'larını ve örnekleri de indirebilirsiniz.

[World Wide Web Konsorsiyumu (W3C)](https://go.microsoft.com/fwlink/p/?linkid=37125) , HTML, http, CGI ve diğer World Wide Web teknolojileri için belirtimleri yayımlar.

## <a name="more-internet-help"></a><a name="_core_more_internet_help"></a>Daha fazla Internet yardımı

Windows SDK OLE bölümü OLE programlama hakkında ek bilgiler içerir. Bu bilgiler, MFC sınıfları yerine doğrudan Win32 WinInet işlevlerini kullanma hakkında ayrıntılı bilgi sağlar. Ayrıca Internet teknolojileriyle ilgili genel bilgiler içerir.
