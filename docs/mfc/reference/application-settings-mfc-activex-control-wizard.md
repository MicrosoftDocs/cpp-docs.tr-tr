---
title: "Uygulama ayarları, MFC ActiveX Denetim Sihirbazı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.appwiz.mfc.ctl.appset
dev_langs: C++
helpviewer_keywords: MFC ActiveX Control Wizard, application settings
ms.assetid: 48475194-cc63-467f-8499-f142269a4c1c
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 46310e3194104fd5a0470c810dddf26cd362287c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="application-settings-mfc-activex-control-wizard"></a>Uygulama Ayarları, MFC ActiveX Denetim Sihirbazı
Tasarım ve yeni bir MFC ActiveX projesine temel özellikleri eklemek için MFC ActiveX Denetim Sihirbazı'nın bu sayfayı kullanın. Bu ayarlar uygulamanın kendisinin ve belirli veritabanında bir veya daha fazla denetim öğesinin geçerlidir.  
  
 **Çalışma zamanı lisans**  
 Denetimle dağıtmak için kullanıcının lisans dosyası oluşturmak için bu seçeneği belirleyin. Bir metin dosyası lisans olduğundan *projname*.lic. Bu dosyayı bir tasarım zamanı ortamında oluşturulacak denetim örneği izin vermek için denetimin DLL ile aynı dizinde olmalıdır. Genellikle bu dosya, denetimiyle dağıtmak, ancak müşterilerinizin dağıtmayın.  
  
 **Yardım dosyaları oluşturma**  
 Tamamlanmamış Yardım dosyalarını oluşturmak ve projenin denetlemek için Yardım içerecek şekilde yapılandırmak için bu seçeneği belirleyin. Bu seçenek olmadan, oluşturulan bir varsayılan proje yalnızca oluşturur bir **hakkında** kullanıcı sağ denetimi tıklattığında görüntülenen kutusunda F1 kullanır veya tıklattığında **yardımcı** denetimin kapsayıcısı üzerinde.  
  
> [!NOTE]
>  Yardım nasıl görüntüleneceğini denetiminizi kapsayıcısı ile nasıl etkileşim bağlıdır. Kapsayıcı ile Yardım eklerseniz, Yardım'ı uygun şekilde görüntülemek için Denetim ve kapsayıcı arasında iletileri işlemelidir.  
  
 Yardım dosyaları Sihirbazı'nı kullanarak oluşturduğunuzda, projenizin aşağıdakileri içerir:  
  
-   Dosya .vcxproj oluşturmak ve proje yapılandırıldığında Yardım dosyasını yapılandırmak için kodunu içerir.  
  
-   Dosya *projnamePropPage*.cpp dosya içeren bir [SetHelpInfo](../../mfc/reference/colepropertypage-class.md#sethelpinfo) oluşturucuda işlevi.  
  
-   Dosya projname.hpj ActiveX denetiminin Yardım dosyasını oluşturmak için Yardım Derleyici tarafından kullanılan Yardım proje dosyası değil. Yardım dosyası ve Yardım dosyasını içeren ek dosyalar (örneğin, bit eşlemler) yollarını oluşturma hakkında bilgi içeren bir metin dosyası .hpj dosyasıdır.  
  
-   Proje Yardım bit eşlem dosyaları ve Yardım konusunu dosyasını içerecek şekilde HLP directory proje içeriyor (*projname*.rtf). Bu Yardım konusu dosya ortak özellikleri, olayları ve birçok ActiveX denetimleri tarafından desteklenen yöntemleri için standart Yardım konularını içerir. .rtf belirli Yardım konuları ekleyip dosyaya düzenleyebilirsiniz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC ActiveX Denetim Sihirbazı](../../mfc/reference/mfc-activex-control-wizard.md)   
 [Denetim adları, MFC ActiveX Denetim Sihirbazı](../../mfc/reference/control-names-mfc-activex-control-wizard.md)   
 [Denetim ayarları, MFC ActiveX Denetim Sihirbazı](../../mfc/reference/control-settings-mfc-activex-control-wizard.md)

