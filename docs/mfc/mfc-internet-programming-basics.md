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
ms.openlocfilehash: eee045e198f61c088e302c40deb2de406adab428
ms.sourcegitcommit: 28eae422049ac3381c6b1206664455dbb56cbfb6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/31/2019
ms.locfileid: "66449743"
---
# <a name="mfc-internet-programming-basics"></a>MFC Internet Programlama Temelleri

Microsoft, hem istemci hem de sunucu uygulamalarına programlama için birçok API'ler sağlar. İnternet'e birçok yeni uygulama yazılan ve yeni uygulama türleri teknolojileri, tarayıcı yetenekleri ve güvenlik seçenekleri değişiklik yazılır. Tarayıcılar, World Wide Web erişim sağlayarak ve metin, grafik, ActiveX denetimleri ve belgeleri içeren HTML sayfalarını görüntüleme istemci bilgisayarlarda çalışması. Sunucuları, FTP, HTTP ve gopher hizmetleri sağlamak ve CGI kullanmanın server uzantısı uygulamalarını çalıştırmak. Özel uygulamanızın bilgi alabilir ve Internet'te veriler sağlar.

>[!IMPORTANT]
> ActiveX yeni geliştirme projeleri için kullanılmaması gereken eski bir teknolojidir. Daha fazla bilgi için [ActiveX denetimlerini](activex-controls.md).

![İstemci ve sunucu uygulamaları](../mfc/media/vc38bq1.gif "istemci ve sunucu uygulamaları")

MFC Internet programlama destekleyen sınıflar sağlar. Kullanabileceğiniz [COleControl](../mfc/reference/colecontrol-class.md) ve [CDocObjectServer](../mfc/reference/cdocobjectserver-class.md) ve ilgili MFC sınıfları ActiveX denetimleri ve etkin belgeler yazılacak. MFC sınıfları gibi kullanabileceğiniz [Cınternetsession](../mfc/reference/cinternetsession-class.md), [CFtpConnection](../mfc/reference/cftpconnection-class.md), ve [CAsyncMonikerFile](../mfc/reference/casyncmonikerfile-class.md) dosyaları ve FTP gibi Internet protokollerini kullanarak bilgileri almak için HTTP ve gopher.

## <a name="in-this-section"></a>Bu Bölümde

- [Internet ile İlgili MFC Sınıfları](../mfc/internet-related-mfc-classes.md)

- [Konuya Göre Internet Bilgileri](../mfc/internet-information-by-topic.md)

- [Göreve Göre Internet Bilgileri](../mfc/internet-information-by-task.md)

- [Internet'te Etkin Teknoloji](../mfc/active-technology-on-the-internet.md)

- [WinInet Temelleri](../mfc/wininet-basics.md)

- [HTML Temelleri](../mfc/html-basics.md)

## <a name="related-sections"></a>İlgili Bölümler

- [Internet'te ActiveX Denetimleri](../mfc/activex-controls-on-the-internet.md)

- [Internet'teki Zaman Uyumsuz Adlar](../mfc/asynchronous-monikers-on-the-internet.md)

- [Win32 Internet Uzantıları (WinInet)](../mfc/win32-internet-extensions-wininet.md)

- [MFC Internet Programlama Görevleri](../mfc/mfc-internet-programming-tasks.md)

- [Uygulama Tasarımı Seçimleri](../mfc/application-design-choices.md)

- [MFC Uygulamaları Yazma](../mfc/writing-mfc-applications.md)

- [Internet Uygulamalarını Test Etme](../mfc/testing-internet-applications.md)

- [Internet güvenliği](../mfc/internet-security-cpp.md)

- [DHTML Denetimleri için ATL Desteği](../atl/atl-support-for-dhtml-controls.md)

##  <a name="_core_web_sites_for_more_information"></a> Daha fazla bilgi için Web siteleri

Microsoft Internet teknolojisi hakkında ek bilgi için bkz: [Microsoft Developer Network (MSDN)](https://go.microsoft.com/fwlink/p/?linkid=56322) Web sitesi. (Bağlantılar değiştirilebilir.)

Bu Web sitesi geliştiricileri için Microsoft geliştirme araçları ve teknolojileri ve güncel ve gelecek konferanslarda hakkında öne çıkan Haberler kullanma hakkında bilgi içerir. Bu sayfadan XML Geliştirici merkezleri ve .NET dahil olmak üzere birçok ilgili Geliştirici sitesi atlayabilirsiniz. Beta SDK'lar ve örnekler de indirebilirsiniz.

[World Wide Web Consortium (W3C)](https://go.microsoft.com/fwlink/p/?linkid=37125) HTML, HTTP, CGI ve diğer World Wide Web teknolojileri özellikleri yayımlar.

##  <a name="_core_more_internet_help"></a> Daha fazla Internet Yardımı

Windows SDK'sı OLE bölümünü OLE programlama hakkında ek bilgiler içerir. Bu bilgiler, Win32 WinINet işlevleri doğrudan kullanmak yerine MFC sınıflarını kullanma hakkında ayrıntılı bilgi sağlar. Ayrıca Internet teknolojileri hakkında genel bilgiler içerir.
