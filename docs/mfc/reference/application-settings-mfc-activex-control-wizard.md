---
description: 'Daha fazla bilgi edinin: uygulama ayarları, MFC ActiveX Denetim Sihirbazı'
title: Uygulama Ayarları, MFC ActiveX Denetim Sihirbazı
ms.date: 11/04/2016
f1_keywords:
- vc.appwiz.mfc.ctl.appset
helpviewer_keywords:
- MFC ActiveX Control Wizard, application settings
ms.assetid: 48475194-cc63-467f-8499-f142269a4c1c
ms.openlocfilehash: dac370f7ba3461534f2fd4782869e7ddcb50336a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97322817"
---
# <a name="application-settings-mfc-activex-control-wizard"></a>Uygulama Ayarları, MFC ActiveX Denetim Sihirbazı

Yeni bir MFC ActiveX projesine temel özellikler tasarlamak ve eklemek için MFC ActiveX denetimi Sihirbazı 'nın bu sayfasını kullanın. Bu ayarlar, uygulamanın kendisi için geçerlidir ve denetimin belirli bir özelliğine ya da öğesine uygulanmaz.

- **Çalışma zamanı lisansı**

   Denetimle dağıtılacak bir Kullanıcı Lisans dosyası oluşturmak için bu seçeneği belirleyin. Lisans, *ProjName*. lik adlı bir metin dosyasıdır. Bu dosya, bir denetimin örneğinin bir tasarım zamanı ortamında oluşturulmasını sağlamak için denetimin DLL 'SI ile aynı dizinde olmalıdır. Bu dosyayı genellikle denetiminle dağıtırsınız, ancak müşterileriniz dağıtmaz.

- **Yardım dosyaları oluştur**

   Saplaması yardım dosyaları oluşturmak ve denetimi için yardım eklemek üzere projeyi yapılandırmak için bu seçeneği belirleyin. Bu seçenek olmadan oluşturulan varsayılan bir proje, yalnızca Kullanıcı denetime tıkladığında görüntülenen bir **hakkında** kutusunu oluşturur, F1 kullanır veya denetimin kapsayıcısı üzerinde **Yardım** ' a tıklar.

   > [!NOTE]
   > Yardım 'ın nasıl görüntüleneceği, denetiminizin kapsayıcıniyle nasıl etkileşime bağlıdır. Kapsayıcınıza yardım eklerseniz, yardımı uygun şekilde göstermek için denetim ve kapsayıcı arasındaki iletileri işlemeniz gerekir.

   Sihirbazı kullanarak yardım dosyaları oluşturduğunuzda projeniz şunları içerir:

  - . Vcxproj dosyası, proje oluşturulduğunda yardım dosyası derlemek ve yapılandırmak için kod içerir.

  - *ProjnamePropPage*. cpp dosyası, oluşturucuda bir [SetHelpInfo](../../mfc/reference/colepropertypage-class.md#sethelpinfo) işlevi içerir.

  - Projname. hpj dosyası, Yardım derleyicisi tarafından ActiveX denetiminin yardım dosyasını oluşturmak için kullanılan Yardım proje dosyasıdır. . Hpj dosyası yardım dosyanızı oluşturma hakkındaki bilgileri ve yardım dosyasının içerdiği ek dosyalara yolları (örneğin, bit eşlemler) içeren bir metin dosyasıdır.

  - Proje, proje yardımı bit eşlem dosyalarını ve yardım konusu dosyasını (*ProjName*. rtf) içeren hlp dizinini içerir. Bu Yardım konusu dosyası, birçok ActiveX denetimi tarafından desteklenen ortak özellikler, olaylar ve yöntemler için standart Yardım konularını içerir. Özel yardım konuları eklemek veya kaldırmak için. rtf dosyasını düzenleyebilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[MFC ActiveX denetimi Sihirbazı](../../mfc/reference/mfc-activex-control-wizard.md)<br/>
[Denetim adları, MFC ActiveX denetimi Sihirbazı](../../mfc/reference/control-names-mfc-activex-control-wizard.md)<br/>
[Denetim ayarları, MFC ActiveX Denetim Sihirbazı](../../mfc/reference/control-settings-mfc-activex-control-wizard.md)
