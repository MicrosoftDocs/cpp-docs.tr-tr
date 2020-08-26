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
ms.openlocfilehash: b41ce97a9b5efe6ad84c543f5c49dd091557b3a8
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88846322"
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

- [Internet 'te etkin teknoloji](active-technology-on-the-internet.md)

- [Winınet temelleri](wininet-basics.md)

- [HTML temelleri](html-basics.md)

## <a name="related-sections"></a>İlgili Bölümler

- [Internet 'te ActiveX denetimleri](activex-controls-on-the-internet.md)

- [Internet 'te zaman uyumsuz bilinen adlar](asynchronous-monikers-on-the-internet.md)

- [Win32 Internet Uzantıları (Winınet)](win32-internet-extensions-wininet.md)

- [MFC Internet programlama görevleri](mfc-internet-programming-tasks.md)

- [Uygulama tasarımı seçimleri](application-design-choices.md)

- [MFC uygulamaları yazma](writing-mfc-applications.md)

- [Internet uygulamalarını test etme](testing-internet-applications.md)

- [Internet güvenliği](internet-security-cpp.md)

- [DHTML denetimleri için ATL desteği](../atl/atl-support-for-dhtml-controls.md)

## <a name="websites-for-more-information"></a><a name="_core_web_sites_for_more_information"></a> Daha fazla bilgi için Web siteleri

Microsoft Internet teknolojisi hakkında daha fazla bilgi için bkz. [Ağ ve Internet](/windows/win32/networking).

[World Wide Web Konsorsiyumu (W3C)](https://go.microsoft.com/fwlink/p/?linkid=37125) , HTML, http, CGI ve diğer World Wide Web teknolojileri için belirtimleri yayımlar.

## <a name="more-internet-help"></a><a name="_core_more_internet_help"></a> Daha fazla internet yardımı

Windows SDK OLE bölümü OLE programlama hakkında ek bilgiler içerir. Bu bilgiler, MFC sınıfları yerine doğrudan Win32 WinInet işlevlerini kullanma hakkında ayrıntılı bilgi sağlar. Ayrıca Internet teknolojileriyle ilgili genel bilgiler içerir.
