---
title: Otomasyon Sunucuları
ms.date: 11/04/2016
helpviewer_keywords:
- Automation servers
- COM components, Automation servers
- dispatch maps [MFC], Automation servers
- servers, Automation
ms.assetid: 523fd155-51ce-4f91-b986-b74bdbdd7d92
ms.openlocfilehash: 0c7f3a3bd37c5f7f5696de363aa646f5376f4e75
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50468802"
---
# <a name="automation-servers"></a>Otomasyon Sunucuları

Otomasyon, uygulamanız nesneleri başka bir uygulamaya uygulanan değiştirmek ya da bunlar işlenebilir nesneleri kullanıma sunmak için mümkün kılar. Otomasyon sunucusu programlanabilir nesneler (Otomasyon nesneleri olarak adlandırılır) diğer uygulamalara kullanıma sunan bir uygulamasıdır (adlı [Otomasyon istemcileri](../mfc/automation-clients.md)). Otomasyon sunucuları bazen Otomasyon bileşenleri olarak adlandırılır.

Otomasyon nesnelerini kullanıma sunma nesneleri doğrudan erişerek bazı yordamları otomatikleştirmek için istemcileri etkinleştirir ve işlevsellik sunucu kullanılabilir hale getirir. Uygulamaların diğer uygulamalar için kullanışlı olan işlevler sağladığınızda, bu şekilde nesnelerini kullanıma sunma yararlıdır. Örneğin, bir sözcük işlemcisi diğer programları kullanabilmesi yazım denetimi işlevselliğini doğurabilir. Nesneleri riskini böylece diğer uygulamaların hazır işlevini kullanarak kendi uygulamalarını işlevselliğini geliştirmek için satıcıları sağlar.

Bu Otomasyon nesneleri özellikler ve yöntemler, dış arayüze sahip. Otomasyon nesnesi özniteliklerini adlandırılmış bir özellikler. Bir C++ sınıf veri üyeleri gibi özelliklerdir. Otomasyon nesneler üzerinde çalışan işlevler yöntemlerdir. Bir C++ sınıfı gibi genel üye işlevlerinin yöntemlerdir.

> [!NOTE]
>  Özellikleri gibi C++ veri üyelerini olsa da, bunlar doğrudan erişilebilir değildir. Saydam erişim sağlamak için Otomasyon nesnesi ile bir çift get/set üye işlevleri iç bir değişkende bunlara erişmek için ayarlayın.

Ortak, iyi tanımlanmış bir arabirim aracılığıyla uygulamanın işlevselliği kullanıma sunma Otomasyon, bir tek genel programlama dilinde yerine Microsoft Visual Basic gibi çeşitli ve uygulamaya özgü makrosu uygulamalar oluşturmanıza olanak sağlar Diller.

##  <a name="_core_support_for_automation_servers"></a> Otomasyon sunucuları için destek

Visual C++ ve MFC çerçevesi otomasyon sunucuları için kapsamlı destek sağlar. Otomasyon sunucusu, uygulamanızın işlevselliğini çalışmalarınızı odaklanmanız yaparken yükü çoğunu işleyin.

Otomasyonu desteklemek için framework'ün asıl dağıtım eşlemesi, bildirimler ve yöntemler ve özellikler için OLE açmanız gerekiyordu çağrıları genişletir makroları birtakım mekanizmadır. Tipik dağıtım eşlemesi şöyle görünür:

[!code-cpp[NVC_MFCAutomation#1](../mfc/codesnippet/cpp/automation-servers_1.cpp)]

Sınıf Görünümü ve Özellikler penceresinde eşlemeleri dağıtma sürdürmeye yardımcı olmak. Karşılık gelen bir sınıfa bir yeni yöntem veya özellik eklediğinizde Visual C++ ekler `DISP_FUNCTION` veya `DISP_PROPERTY` makrosu gösteren sınıf adı, iç ve dış adları yöntemi veya özelliği ve veri türlerinin parametrelere sahip.

**Sınıfı Ekle** iletişim kutusu da basitleştirir ve Otomasyon sınıfları bildirimi özellikleri ve operations management. Sınıf Ekle iletişim kutusu, projenize bir sınıf eklemek için kullandığınızda, taban sınıfı belirtin. Otomasyon temel sınıfı izin veriyorsa, Sınıf Ekle iletişim kutusu denetimleri Otomasyon, yeni bir sınıf desteklemesi gerekip gerekmediğini "oluşturulabilir OLE (diğer bir deyişle, mi sınıfın nesneleri bir COM istemciden istek üzerine oluşturulabilir)" olup olmadığını belirtmek için kullandığınız görüntüler. ve kullanmak COM istemcisi için dış adı.

**Sınıfı Ekle** iletişim kutusu, bir sınıf bildiriminin ardından oluşturur, OLE, özellikler için uygun makroları dahil olmak üzere belirtildi. Ayrıca, sınıfın üye işlevleri uygulaması için çatı kodu ekler.

MFC Uygulama Sihirbazı, baştan sonra, Otomasyon sunucu uygulaması alınırken yer alan adımların basitleştirir. Seçerseniz **Otomasyon** onay kutusundan **Gelişmiş Özellikler** sayfasında, MFC Uygulama Sihirbazı, uygulamanızın ekler `InitInstance` işlev çağrıları, Otomasyon kaydetmek için gerekli Nesne ve Otomasyon sunucusu çalıştırın.

### <a name="what-do-you-want-to-do"></a>Ne yapmak istiyorsunuz

- [Otomasyon istemcileri hakkında bilgi edinin](../mfc/automation-clients.md)

- [CCmdTarget sınıfı hakkında daha fazla bilgi edinin](../mfc/reference/ccmdtarget-class.md)

- [COleDispatchDriver sınıfı hakkında daha fazla bilgi edinin](../mfc/reference/coledispatchdriver-class.md)

## <a name="see-also"></a>Ayrıca Bkz.

[Otomatikleştirme](../mfc/automation.md)<br/>
[MFC Uygulama Sihirbazı](../mfc/reference/mfc-application-wizard.md)

