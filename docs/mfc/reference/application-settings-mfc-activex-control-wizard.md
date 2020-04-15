---
title: Uygulama Ayarları, MFC ActiveX Denetim Sihirbazı
ms.date: 11/04/2016
f1_keywords:
- vc.appwiz.mfc.ctl.appset
helpviewer_keywords:
- MFC ActiveX Control Wizard, application settings
ms.assetid: 48475194-cc63-467f-8499-f142269a4c1c
ms.openlocfilehash: 55f202ffabe945e55589ab1fc771a1757e23ca2f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372469"
---
# <a name="application-settings-mfc-activex-control-wizard"></a>Uygulama Ayarları, MFC ActiveX Denetim Sihirbazı

Yeni bir MFC ActiveX projesinin temel özelliklerini tasarlamak ve eklemek için MFC ActiveX Denetim Sihirbazı'nın bu sayfasını kullanın. Bu ayarlar, denetimin belirli bir özelliği ne de öğesi için değil, uygulamanın kendisi için geçerlidir.

- **Çalışma zamanı lisansı**

   Denetimle dağıtmak için bir kullanıcı lisans dosyası oluşturmak için bu seçeneği belirleyin. Lisans bir metin dosyası, *projname*.lic olduğunu. Bu dosya, denetimin bir örneğinin tasarım zamanı ortamında oluşturulmasına izin vermek için denetimin DLL'si ile aynı dizinde olmalıdır. Bu dosyayı genellikle denetiminiz ile dağıtırsınız, ancak müşterileriniz dağıtmaz.

- **Yardım dosyaları oluşturma**

   Saplı yardım dosyaları oluşturmak için bu seçeneği seçin ve projeyi denetiminize yardımcı olacak şekilde yapılandırın. Bu seçenek olmadan oluşturulan varsayılan proje, yalnızca kullanıcı denetimi sağ tıklattığında, F1 kullandığında veya denetimin kapsayıcısı **üzerinde Yardım'ı** tıklattığında görüntülenen bir **About** kutusu oluşturur.

   > [!NOTE]
   > Yardımın nasıl görüntüleneceği, denetiminizin kapsayıcısıyla nasıl etkileşimde deleneceğine bağlıdır. Kapsayıcınıza yardım eklerseniz, yardımı uygun şekilde görüntülemek için denetim ve kapsayıcı arasındaki iletileri işlemeniz gerekir.

   Sihirbazı kullanarak yardım dosyaları oluşturduğunuzda, projeniz aşağıdakileri içerir:

  - .vcxproj dosyası, proje oluşturulurken yardım dosyasını oluşturmak ve yapılandırmak için kod içerir.

  - Dosya *projnamePropPage*.cpp dosyası oluşturucu bir [SetHelpInfo](../../mfc/reference/colepropertypage-class.md#sethelpinfo) işlevi içerir.

  - Projname.hpj dosyası, ActiveX denetiminin yardım dosyasını oluşturmak için yardım derleyicisi tarafından kullanılan yardım projesi dosyasıdır. .hpj dosyası, yardım dosyanızı oluşturma yla ilgili bilgileri ve yardım dosyasının içerdiği ek dosyalara (örneğin bit eşlemler) giden yolları içeren bir metin dosyasıdır.

  - Proje, bitmap dosyalarını ve yardım konusu dosyasını *(projname*.rtf) içeren HLP dizinini içerir. Bu yardım konusu dosyası, birçok ActiveX denetimi tarafından desteklenen ortak özellikler, olaylar ve yöntemler için standart yardım konularını içerir. Belirli yardım konularını eklemek veya kaldırmak için .rtf dosyasını edebilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[MFC ActiveX Denetim Sihirbazı](../../mfc/reference/mfc-activex-control-wizard.md)<br/>
[Denetim Adları, MFC ActiveX Denetim Sihirbazı](../../mfc/reference/control-names-mfc-activex-control-wizard.md)<br/>
[Denetim Ayarları, MFC ActiveX Denetim Sihirbazı](../../mfc/reference/control-settings-mfc-activex-control-wizard.md)
