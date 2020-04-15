---
title: Otomasyon Sunucuları
ms.date: 11/04/2016
helpviewer_keywords:
- Automation servers
- COM components, Automation servers
- dispatch maps [MFC], Automation servers
- servers, Automation
ms.assetid: 523fd155-51ce-4f91-b986-b74bdbdd7d92
ms.openlocfilehash: 391cb2f6ff5673296f40e21113e3a6510f71d475
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370834"
---
# <a name="automation-servers"></a>Otomasyon Sunucuları

Otomasyon, uygulamanızın başka bir uygulamada uygulanan nesneleri işlemesini veya nesneleri manipüle edilebilmeleri için ortaya çıkarmasını mümkün kılar. Otomasyon sunucusu, programlanabilir nesneleri (Otomasyon nesneleri olarak adlandırılır) diğer uygulamalara [(Otomasyon istemcileri](../mfc/automation-clients.md)olarak adlandırılır) maruz eden bir uygulamadır. Otomasyon sunucuları bazen Otomasyon bileşenleri olarak adlandırılır.

Otomasyon nesnelerini açığa çıkarmak, istemcilerin sunucunun sağladığı nesnelere ve işlevselliklere doğrudan erişerek belirli yordamları otomatikleştirmesini sağlar. Uygulamalar diğer uygulamalar için yararlı işlevsellik sağladığında nesneleri bu şekilde teşhir etmek yararlıdır. Örneğin, bir sözcük işlemcisi yazım denetimi işlevini ortaya çıkarabilir, böylece diğer programlar bunu kullanabilir. Böylece nesnelerin pozu, satıcıların diğer uygulamaların hazır işlevselliğini kullanarak uygulamalarının işlevselliğini geliştirmelerine olanak tanır.

Bu Otomasyon nesneleri, dış arabirimleri olarak özelliklere ve yöntemlere sahiptir. Özellikler, Otomasyon nesnesinin öznitelikleri olarak adlandırılır. Özellikler, C++ sınıfının veri üyeleri gibidir. Yöntemler, Otomasyon nesneleri üzerinde çalışan işlevlerdir. Yöntemler, C++ sınıfının ortak üye işlevleri gibidir.

> [!NOTE]
> Özellikler C++ veri üyeleri gibi olsa da, doğrudan erişilebilir değildir. Saydam erişim sağlamak için, Otomasyon nesnesinde bir çift al/ayarlı üye işlevi yle bir iç değişken ayarlayın.

Otomasyon, uygulama işlevselliğini ortak ve iyi tanımlanmış bir arayüz aracılığıyla ortaya çıkararak, çeşitli, uygulamaya özgü makro dilleryerine Microsoft Visual Basic gibi tek bir genel programlama dilinde uygulama oluşturmayı mümkün kılar.

## <a name="support-for-automation-servers"></a><a name="_core_support_for_automation_servers"></a>Otomasyon Sunucuları desteği

Visual C++ ve MFC çerçevesi Otomasyon sunucuları için kapsamlı destek sağlar. Bir Otomasyon sunucusu nun yapımında yer alan ek yükün çoğunu ele aldıklarından, çalışmalarınızı uygulamanızın işlevselliği üzerine odaklayabilirsiniz.

Otomasyonu desteklemek için çerçevenin temel mekanizması, OLE'nin yöntemlerini ve özelliklerini ortaya çıkarmak için gerekli olan bildirimlere ve çağrılara genişleyen bir makro kümesi olan sevk haritasıdır. Tipik bir gönderme haritası şuna benzer:

[!code-cpp[NVC_MFCAutomation#1](../mfc/codesnippet/cpp/automation-servers_1.cpp)]

[Sınıf Sihirbazı](reference/mfc-class-wizard.md) ve Sınıf Görünümü, gönderme eşlemlerini korumada yardımcı olur. Bir sınıfa yeni bir yöntem veya özellik eklediğinizde, Visual Studio sınıf adını, yöntemin veya özelliğin dış ve iç adlarını ve veri türlerini gösteren parametreleriçeren bir karşılık gelen `DISP_FUNCTION` veya `DISP_PROPERTY` makro ekler.

**Sınıf Ekle** iletişim kutusu, Otomasyon sınıflarının bildirimini ve bunların özelliklerinin ve işlemlerinin yönetimini de kolaylaştırır. Projenize sınıf eklemek için Sınıf Ekle iletişim kutusunu kullandığınızda, taban sınıfını belirtirsiniz. Taban sınıf Otomasyon'a izin veriyorsa, Sınıf Ekle iletişim kutusu, yeni sınıfın Otomasyonu destekleyip desteklememesi gerektiğini, "OLE creatable" olup olmadığını (diğer bir zamanda, sınıfın nesnelerinin COM istemcisinden gelen bir istek üzerine oluşturulup oluşturulamayacağını) ve COM istemcisinin kullanması için dış adı belirtmek için kullandığınız denetimleri görüntüler.

**Sınıf Ekle** iletişim kutusu, belirttiğiniz OLE özellikleri için uygun makroları da içeren bir sınıf bildirimi oluşturur. Ayrıca, sınıfınızın üye işlevlerinin uygulanması için iskelet kodunu da ekler.

MFC Application Wizard, otomasyon sunucusu uygulamanızı kullanıma çıkarmaadımlarını basitleştirir. **Gelişmiş Özellikler** sayfasından **Otomasyon** onay kutusunu seçerseniz, MFC Uygulama Sihirbazı `InitInstance` uygulamanızın işlevine Otomasyon nesnelerinizi kaydetmek ve uygulamanızı Otomasyon sunucusu olarak çalıştırmak için gereken çağrıları ekler.

### <a name="what-do-you-want-to-do"></a>Ne yapmak istiyorsun?

- [Otomasyon istemcileri hakkında bilgi edinin](../mfc/automation-clients.md)

- [CCmdTarget sınıfı hakkında daha fazla bilgi edinin](../mfc/reference/ccmdtarget-class.md)

- [Sınıf COleDispatchDriver hakkında daha fazla bilgi edinin](../mfc/reference/coledispatchdriver-class.md)

## <a name="see-also"></a>Ayrıca bkz.

[Otomasyon](../mfc/automation.md)<br/>
[MFC Uygulama Sihirbazı](../mfc/reference/mfc-application-wizard.md)
