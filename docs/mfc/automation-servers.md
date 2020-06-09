---
title: Otomasyon Sunucuları
ms.date: 11/04/2016
helpviewer_keywords:
- Automation servers
- COM components, Automation servers
- dispatch maps [MFC], Automation servers
- servers, Automation
ms.assetid: 523fd155-51ce-4f91-b986-b74bdbdd7d92
ms.openlocfilehash: 4c2ef77e20b7dccfa8cd6830c090111601331642
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84619413"
---
# <a name="automation-servers"></a>Otomasyon Sunucuları

Otomasyon, uygulamanızın başka bir uygulamada uygulanan nesneleri işlemesini veya işlenebilmeleri için nesneleri kullanıma sunmasını mümkün kılar. Otomasyon sunucusu, programlanabilir nesneleri (Otomasyon nesneleri olarak adlandırılır) diğer uygulamalara ( [Otomasyon istemcileri](automation-clients.md)olarak adlandırılır) sunan bir uygulamadır. Otomasyon sunucuları bazen Otomasyon bileşenleri olarak adlandırılır.

Otomasyon nesnelerinin ortaya çıkarılması, istemcilerin, sunucunun kullanılabilir hale getirdiği nesnelere ve işlevlere doğrudan erişerek belirli yordamları otomatikleştirmesini sağlar. Bu şekilde nesneleri göstermek, uygulamalar diğer uygulamalar için yararlı olan işlevler sağladığınızda yararlı olur. Örneğin, bir sözcük işlemcisi, diğer programların kullanabilmesi için yazım denetimi işlevini kullanıma sunmayabilir. Nesnelerin açığa çıkması, satıcıların diğer uygulamaların kullanıma açık işlevlerini kullanarak uygulamalarının işlevselliğini geliştirmesine olanak sağlar.

Bu Otomasyon nesnelerinin dış arabirimi olarak özellikleri ve yöntemleri vardır. Özellikler, Otomasyon nesnesinin öznitelikleri olarak adlandırılır. Özellikler bir C++ sınıfının veri üyeleri gibidir. Yöntemler Otomasyon nesnelerinde çalışan işlevlerdir. Yöntemler bir C++ sınıfının ortak üye işlevleri gibidir.

> [!NOTE]
> Özellikler C++ veri üyeleri gibi olsa da, bunlar doğrudan erişilebilir değildir. Şeffaf erişim sağlamak için, Otomasyon nesnesinde, bunlara erişmek üzere Get/Set üye işlevlerinin bulunduğu bir iç değişken ayarlayın.

Otomasyon, yaygın, iyi tanımlanmış bir arabirim aracılığıyla uygulama işlevselliğini ortaya çıkararak uygulamaları, uygulamaya özgü farklı makro dilleri yerine Microsoft Visual Basic gibi tek bir genel programlama dilinde oluşturmayı mümkün kılar.

## <a name="support-for-automation-servers"></a><a name="_core_support_for_automation_servers"></a>Otomasyon sunucuları için destek

Visual C++ ve MFC çerçevesi otomasyon sunucuları için kapsamlı destek sağlar. Otomasyon sunucusu oluşturma konusunda ek yükün çoğunu idare eder; böylece çabalarınızı uygulamanızın işlevlerine odaklanırsınız.

Framework 'ün destekleme için temel mekanizması, OLE için yöntemler ve özellikler sunmak için gereken bildirimlere ve çağrılara genişleyen bir makro kümesi olan dağıtım haritasıdır. Tipik bir dağıtım eşlemesi şöyle görünür:

[!code-cpp[NVC_MFCAutomation#1](codesnippet/cpp/automation-servers_1.cpp)]

[Sınıf Sihirbazı](reference/mfc-class-wizard.md) ve dağıtım haritalarını korumaya yardımcı sınıf görünümü. Bir sınıfa yeni bir yöntem veya özellik eklediğinizde, Visual Studio, `DISP_FUNCTION` `DISP_PROPERTY` sınıf adını, dış ve iç adları ve veri türlerini belirten parametrelere sahip karşılık gelen veya makroyu ekler.

**Sınıf Ekle** iletişim kutusu ayrıca Otomasyon sınıflarının bildirimini ve özelliklerinin ve işlemlerinin yönetimini basitleştirir. Projenize bir sınıf eklemek için sınıf Ekle iletişim kutusunu kullandığınızda, onun temel sınıfını belirtirsiniz. Temel sınıf otomasyona izin veriyorsa, sınıf Ekle iletişim kutusu, yeni sınıfın Otomasyonu desteklemesi gerekip gerekmediğini, "OLE creatable" olup olmadığını (yani, bir COM istemcisinden gelen bir istek üzerinde sınıf nesnelerinin oluşturulup oluşturuamayacağını) ve COM istemcisinin kullanacağı dış adı belirten denetimleri görüntüler.

**Sınıf Ekle** iletişim kutusu daha sonra belirttiğiniz OLE özelliklerine yönelik uygun makroları içeren bir sınıf bildirimi oluşturur. Ayrıca, sınıfınızın üye işlevlerinin uygulanması için iskelet kodunu ekler.

MFC Uygulama Sihirbazı, Otomasyon sunucusu uygulamanızı arka planda alma ile ilgili adımları basitleştirir. **Gelişmiş Özellikler** sayfasında **Otomasyon** onay kutusunu seçerseniz, MFC Uygulama Sihirbazı uygulamanızın `InitInstance` işlevine Otomasyon nesnelerinizi kaydetmek için gereken çağrıları ekler ve uygulamanızı bir Otomasyon sunucusu olarak çalıştırır.

### <a name="what-do-you-want-to-do"></a>Ne yapmak istiyorsunuz?

- [Otomasyon istemcileri hakkında bilgi edinin](automation-clients.md)

- [CCmdTarget sınıfı hakkında daha fazla bilgi edinin](reference/ccmdtarget-class.md)

- [Sınıf Cotadispatchdriver hakkında daha fazla bilgi edinin](reference/coledispatchdriver-class.md)

## <a name="see-also"></a>Ayrıca bkz.

[Otomasyon](automation.md)<br/>
[MFC Uygulama Sihirbazı](reference/mfc-application-wizard.md)
