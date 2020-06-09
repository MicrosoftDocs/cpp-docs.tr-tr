---
title: MFC Internet Programlama Görevleri
ms.date: 09/12/2018
helpviewer_keywords:
- Internet applications [MFC], getting started
- Internet applications [MFC], first steps
ms.assetid: 6377e9b8-07c4-4380-b63b-05f5a9061313
ms.openlocfilehash: 6d8a542ada94bc52ee2000bc92ae0457ec87609c
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84617958"
---
# <a name="mfc-internet-programming-tasks"></a>MFC Internet Programlama Görevleri

Bu bölüm, uygulamalarınıza Internet desteği ekleme hakkında ayrıntılı adımlar içerir. Mevcut uygulamalarınızı Internet 'Te etkinleştirmek için MFC sınıflarının nasıl kullanılacağı ve mevcut COM bileşeninizin etkin belge desteğinin nasıl ekleneceği hakkında konular yer alır. Güncel hisse senedi fiyatları, Sütburgh 'nın futbol puanlarını ve Antarktika Microsoft 'un en son sıcaklığını içeren bir belge oluşturmak istiyor musunuz, Internet üzerinden bunu yapmanıza yardımcı olmak için bir dizi teknoloji sağlar.

Etkin teknolojiler, ActiveX denetimlerini (eski adıyla OLE denetimleri) ve etkin belgeleri içerir. Dosyaları Internet üzerinden kolayca almak ve kaydetmek için WinInet; ve verimli veri indirme için zaman uyumsuz bilinen adlar. Visual C++, bir başlangıç uygulaması ile hızlıca çalışmaya başlamanıza yardımcı olacak sihirbazlar sağlar. Bu teknolojilere giriş için bkz. [MFC Internet Programlama Temelleri](mfc-internet-programming-basics.md) ve [MFC com](mfc-com.md).

Her zaman bir dosyaya FTP istiyor ancak WinSock ve ağ programlama protokollerini yapılandırmadınız WinInet sınıfları bu protokolleri kapsüllemek için, HTTP, FTP ve gopher kullanarak dosyaları indirmek üzere Internet üzerinde bir istemci uygulaması yazmak için kullanabileceğiniz basit bir işlevler kümesi sağlar. WinInet kullanarak sabit sürücünüzdeki veya dünyanın dört bir yanındaki dizinleri arayabilirsiniz. Çeşitli farklı türlerdeki verileri saydam bir şekilde toplayabilir ve bunu tümleşik bir arabirimdeki kullanıcıya sunabilirsiniz.

Zaman uyumsuz adların indirileceği büyük miktarlarda veriniz, büyük nesnelerin aşamalı olarak oluşturulmasına yönelik bir COM (bileşen nesne modeli) çözümü sağlar. WinInet, zaman uyumsuz olarak da kullanılabilir.

Aşağıdaki tabloda, bu teknolojilerle yapabileceklerinizden bazıları açıklanmaktadır.

|Sahipsiniz|İstediğiniz|Yapmanız gerekir|
|--------------|-----------------|----------------|
|Bir Web sunucusu.|Oturum açmaları ve URL istekleriyle ilgili ayrıntılı bilgileri izleyin.|Filtre yazma, oturum açma olayları ve URL eşleme için istek bildirimleri yazın.|
|Bir Web tarayıcısı.|Dinamik içerik sağlayın.|ActiveX denetimleri ve etkin belgeler oluşturun.|
|Belge tabanlı uygulama.|FTP 'ye bir dosya için destek ekleyin.|WinInet veya zaman uyumsuz adlar kullanın.|

Başlamanıza daha fazla bilgi için aşağıdaki konulara bakın:

- [Uygulama Tasarımı Seçimleri](application-design-choices.md)

- [MFC Uygulamaları Yazma](writing-mfc-applications.md)

- [Internet 'te ActiveX denetimleri](activex-controls-on-the-internet.md)

- [Varolan bir ActiveX denetimini yükseltme](upgrading-an-existing-activex-control.md)

- [Internet 'te zaman uyumsuz bilinen adlar](asynchronous-monikers-on-the-internet.md)

- [Internet Uygulamalarını Test Etme](testing-internet-applications.md)

- [Internet güvenliği](internet-security-cpp.md)

## <a name="see-also"></a>Ayrıca bkz.

[MFC Internet Programlama Temelleri](mfc-internet-programming-basics.md)<br/>
[Göreve göre Internet bilgileri](internet-information-by-task.md)
