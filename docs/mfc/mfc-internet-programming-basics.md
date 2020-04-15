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
ms.openlocfilehash: 5a8fb7bf07ec631869075c5977dcec468143ad56
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366283"
---
# <a name="mfc-internet-programming-basics"></a>MFC Internet Programlama Temelleri

Microsoft, hem istemci hem de sunucu uygulamalarını programlamak için birçok API sağlar. Birçok yeni uygulamalar Internet için yazılmış ve teknolojiler, tarayıcı yetenekleri ve güvenlik seçenekleri değiştikçe, yeni uygulama türleri yazılacaktır. Tarayıcılar istemci bilgisayarlarda çalışır, World Wide Web'e erişim sağlar ve metin, grafik, ActiveX denetimleri ve belgeler içeren HTML sayfalarını görüntüler. Sunucular FTP, HTTP ve gopher hizmetleri sağlar ve CGI kullanarak sunucu uzantısı uygulamaları çalıştırın. Özel uygulamanız bilgi alabilir ve Internet'te veri sağlayabilir.

>[!IMPORTANT]
> ActiveX, yeni geliştirme için kullanılmaması gereken eski bir teknolojidir. Daha fazla bilgi için [ActiveX Denetimleri'ne](activex-controls.md)bakın.

![İstemci ve sunucu uygulamaları](../mfc/media/vc38bq1.gif "İstemci ve sunucu uygulamaları")

MFC, Internet programlamayı destekleyen sınıflar sağlar. ActiveX denetimleri ve Etkin belgeler yazmak için [COleControl](../mfc/reference/colecontrol-class.md) ve [CDocObjectServer](../mfc/reference/cdocobjectserver-class.md) ve ilgili MFC sınıflarını kullanabilirsiniz. FTP, HTTP ve gopher gibi Internet protokollerini kullanarak dosya ve bilgi almak için [CInternetSession,](../mfc/reference/cinternetsession-class.md) [CFtpConnection](../mfc/reference/cftpconnection-class.md)ve [CAsyncMonikerFile](../mfc/reference/casyncmonikerfile-class.md) gibi MFC sınıflarını kullanabilirsiniz.

## <a name="in-this-section"></a>Bu Bölümde

- [İnternet ile İlgili MFC Sınıfları](../mfc/internet-related-mfc-classes.md)

- [Konuya Göre İnternet Bilgileri](../mfc/internet-information-by-topic.md)

- [Göreve Göre İnternet Bilgileri](../mfc/internet-information-by-task.md)

- [Internet'te Etkin Teknoloji](../mfc/active-technology-on-the-internet.md)

- [WinInet Temelleri](../mfc/wininet-basics.md)

- [HTML Temelleri](../mfc/html-basics.md)

## <a name="related-sections"></a>İlgili Bölümler

- [Internet'te ActiveX Denetimleri](../mfc/activex-controls-on-the-internet.md)

- [İnternette Asynchronous Monikers](../mfc/asynchronous-monikers-on-the-internet.md)

- [Win32 İnternet Uzantıları (WinInet)](../mfc/win32-internet-extensions-wininet.md)

- [MFC Internet Programlama Görevleri](../mfc/mfc-internet-programming-tasks.md)

- [Uygulama Tasarımı Seçimleri](../mfc/application-design-choices.md)

- [MFC Uygulamaları Yazma](../mfc/writing-mfc-applications.md)

- [Internet Uygulamalarını Test Etme](../mfc/testing-internet-applications.md)

- [İnternet Güvenliği](../mfc/internet-security-cpp.md)

- [DHTML Denetimleri İçin ATL Desteği](../atl/atl-support-for-dhtml-controls.md)

## <a name="web-sites-for-more-information"></a><a name="_core_web_sites_for_more_information"></a>Daha Fazla Bilgi İçin Web Siteleri

Microsoft Internet teknolojisi hakkında daha fazla bilgi için [Microsoft Geliştirici Ağı (MSDN)](https://go.microsoft.com/fwlink/p/?linkid=56322) Web sitesine bakın. (Bağlantılar önceden haber vermeden değişebilir.)

Geliştiriciler için bu Web sitesi, Microsoft geliştirme araçları ve teknolojilerini kullanma hakkında bilgiler ve son ve yaklaşan konferanslar hakkında en iyi haberleri içerir. Bu sayfadan ,.NET ve XML Geliştirici Merkezleri de dahil olmak üzere birçok ilgili geliştirici sitelerine atlayabilirsiniz. Ayrıca beta SDK'ları ve örneklerini de indirebilirsiniz.

[World Wide Web Konsorsiyumu (W3C),](https://go.microsoft.com/fwlink/p/?linkid=37125) HTML, HTTP, CGI ve diğer World Wide Web teknolojileri için teknik özellikler yayımlar.

## <a name="more-internet-help"></a><a name="_core_more_internet_help"></a>Daha Fazla İnternet Yardımı

Windows SDK'nın OLE bölümü, OLE programlama hakkında ek bilgiler içerir. Bu bilgiler, MFC sınıfları yerine win32 WinInet işlevlerini doğrudan kullanma hakkında ayrıntılı bilgi sağlar. Ayrıca Internet teknolojileri hakkında genel bakış bilgileri içerir.
