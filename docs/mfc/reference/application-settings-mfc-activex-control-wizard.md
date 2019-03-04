---
title: Uygulama Ayarları, MFC ActiveX Denetim Sihirbazı
ms.date: 11/04/2016
f1_keywords:
- vc.appwiz.mfc.ctl.appset
helpviewer_keywords:
- MFC ActiveX Control Wizard, application settings
ms.assetid: 48475194-cc63-467f-8499-f142269a4c1c
ms.openlocfilehash: 3201b5882a1de4064d924fbb28ee1c575ab8ccbe
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57281167"
---
# <a name="application-settings-mfc-activex-control-wizard"></a>Uygulama Ayarları, MFC ActiveX Denetim Sihirbazı

Tasarım ve temel özelliklerine yeni MFC ActiveX projeye eklemek için MFC ActiveX Denetim Sihirbazı'nın bu sayfayı kullanın. Bu ayarlar, uygulamanın kendisi için ve belirli özellik ya da öğe denetimi için geçerlidir.

- **Çalışma zamanı lisansı**

   Denetim ile dağıtmak için bir kullanıcı lisans dosyası oluşturmak için bu seçeneği seçin. Bir metin dosyası lisanstır *projname*.lic. Bu dosya, bir tasarım zamanı ortamında oluşturulması için denetimi bir örneğini izin vermek için Denetim DLL ile aynı dizinde olmalıdır. Genellikle bu dosya ile denetiminizi dağıtmak, ancak müşterilerinizin dağıtmayın.

- **Yardım dosyaları oluştur**

   Saptama Yardım dosyaları oluşturmak ve proje denetiminiz için Yardım'ı içerecek şekilde yapılandırmak için bu seçeneği belirleyin. Bu seçenek olmadan oluşturulan bir varsayılan proje yalnızca oluşturduğu bir **hakkında** kullanıcı denetimi sağ tıkladıktan sonra görüntülenen kutusunda F1 kullanır veya tıkladığında **yardımcı** denetimin kapsayıcısı üzerinde.

   > [!NOTE]
   > Yardım nasıl görüntüleneceğini denetim kapsayıcısı ile nasıl etkileştiğini bağlıdır. Yardım ile kapsayıcınız dahil ederseniz, Yardım'ı uygun şekilde görüntülemek için Denetim ve kapsayıcı arasında iletileri işlemesi gerekir.

   Yardım dosyaları Sihirbazı'nı kullanarak oluşturduğunuzda, projenizi aşağıdakileri içerir:

   - Dosya .vcxproj oluşturmak ve proje derlenirken Yardım dosyasını yapılandırmak için kodu içerir.

   - Dosya *projnamePropPage*.cpp dosyası içeren bir [SetHelpInfo](../../mfc/reference/colepropertypage-class.md#sethelpinfo) oluşturucu işlevi.

   - Dosya projname.hpj ActiveX denetiminin Yardım dosyasını oluşturmak için Yardım Derleyici tarafından kullanılan Yardım proje dosyası var. Yardım dosyanızı ve Yardım dosyasını içerir (örneğin, bit eşlemler) ek dosyalara olan yolları oluşturma hakkında bilgi içeren bir metin dosyasının .hpj dosyasıdır.

   - Projenin proje Yardım bit eşlem dosyaları ve Yardım konusu dosyasını içerecek şekilde HLP dizini içerir (*projname*.rtf). Bu Yardım konusu dosya için yaygın özellikleri, olayları ve çok sayıda ActiveX denetimi tarafından desteklenen yöntemleri standart Yardım konularını içerir. .Rtf dosyasının belirli Yardım konuları ekleyip düzenleyebilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[MFC ActiveX Denetim Sihirbazı](../../mfc/reference/mfc-activex-control-wizard.md)<br/>
[Denetim Adları, MFC ActiveX Denetim Sihirbazı](../../mfc/reference/control-names-mfc-activex-control-wizard.md)<br/>
[Denetim Ayarları, MFC ActiveX Denetim Sihirbazı](../../mfc/reference/control-settings-mfc-activex-control-wizard.md)
