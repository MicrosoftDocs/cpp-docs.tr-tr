---
title: "MFC ActiveX denetimleri: İyileştirme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- MFC ActiveX controls [MFC], windowless
- flicker-free ActiveX controls
- MFC ActiveX controls [MFC], mouse interaction
- device contexts, unclipped for MFC ActiveX controls
- MFC ActiveX controls [MFC], optimizing
- performance, ActiveX controls
- optimization, ActiveX controls
- MFC ActiveX controls [MFC], flicker-free
- windowless MFC ActiveX controls
- MFC ActiveX controls [MFC], active/inactive state
- optimizing performance, ActiveX controls
ms.assetid: 8b11f26a-190d-469b-b594-5336094a0109
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 46a17a6594db6c59148042f6e8c6cc72c7068dc0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="mfc-activex-controls-optimization"></a>MFC ActiveX Denetimleri: İyileştirme
Bu makalede, ActiveX denetimleri daha iyi performans için en iyi duruma getirmek için kullanabileceğiniz teknikler açıklanmaktadır.  
  
 Konular [kapatma kapalı görünürken etkinleştir seçeneğini](../mfc/turning-off-the-activate-when-visible-option.md) ve [sağlama fare etkileşimi sırasında etkin olmayan](../mfc/providing-mouse-interaction-while-inactive.md) etkinleştirilinceye kadar bir pencere oluşturma denetimleri tartışın. Konu [penceresiz etkinleştirme sağlama](../mfc/providing-windowless-activation.md) bile etkin olduğunda, hiçbir zaman bir pencere oluşturma denetimleri açıklar.  
  
 Windows OLE nesneleri için iki ana sakıncaları vardır: Bunlar nesneleri saydam veya etkin olduğunda dikdörtgen olmayan engellemek ve büyük yükünü örnek oluşturma ve görüntüleme denetimlerinin ekleyin. Genellikle, bir pencere oluşturma bir denetimin oluşturulma zamanı yüzde 60'ını alır. Tek bir paylaşılan pencere (genellikle kapsayıcının) ve bazı dağıtırken kod, bir denetim genellikle bir performans kaybı olmadan aynı penceresi Hizmetleri alır. Bir pencere sahip nesne için çoğunlukla gereksiz ek yük istenir.  
  
 Denetim belirli kapsayıcılarında kullanıldığında, bazı en iyi duruma getirme mutlaka performansı değil. Örneğin, bu özellik uygulama eski kapsayıcılarında bir yararı sağlamaz şekilde 1996 öncesinde yayımlanan kapsayıcıları penceresiz etkinleştirme desteklememektedir. Ancak, neredeyse her kapsayıcı Kalıcılık, destekler, böylece denetiminizin Kalıcılık kodu en iyi duruma getirme büyük olasılıkla tüm kapsayıcı kendi performansını artırır. Denetim, özellikle kapsayıcı belirli bir tür ile kullanılacak amaçlanıyorsa, araştırmak hangisinin bu iyileştirmeler, kapsayıcı tarafından desteklenen isteyebilirsiniz. Genel olarak, Bununla birlikte, birçok büyük olasılıkla, yanı sıra denetim gerçekleştirir emin olmak için belirli denetimine geçerli olduğu gibi bu teknikler kapsayıcıları geniş bir yelpazede gibi uygulamak denemelisiniz.  
  
 Bu iyileştirmeler çoğunu uygulayabilirsiniz [MFC ActiveX Denetim Sihirbazı](../mfc/reference/mfc-activex-control-wizard.md), [denetim ayarlarını](../mfc/reference/control-settings-mfc-activex-control-wizard.md) sayfası.  
  
### <a name="mfc-activex-control-wizard-ole-optimization-options"></a>MFC ActiveX Denetim Sihirbazı OLE en iyi duruma getirme seçenekleri  
  
|MFC ActiveX Denetim Sihirbazı'nda denetim ayarı|Eylem|Daha fazla bilgi|  
|-------------------------------------------------------|------------|----------------------|  
|**Görünür zaman etkinleştirme** onay kutusu|Temizle|[Kapatma etkinleştirin görünür seçeneği](../mfc/turning-off-the-activate-when-visible-option.md)|  
|**Penceresiz etkinleştirme** onay kutusu|Seçim|[Penceresiz Etkinleştirme Sağlama](../mfc/providing-windowless-activation.md)|  
|**Kesilmemiş cihaz bağlamı** onay kutusu|Seçim|[Kesilmemiş Bir Cihaz Bağlamı Kullanma](../mfc/using-an-unclipped-device-context.md)|  
|**Titreşimsiz etkinleştirme** onay kutusu|Seçim|[Titreşimsiz Etkinleştirme Sağlama](../mfc/providing-flicker-free-activation.md)|  
|**Fare işaretçisini bildirimleri etkin olmadığında** onay kutusu|Seçim|[Devre Dışı İken Fare Etkileşimi Sağlama](../mfc/providing-mouse-interaction-while-inactive.md)|  
|**Kod çizim en iyi duruma getirilmiş** onay kutusu|Seçim|[Denetim Çizimini İyileştirme](../mfc/optimizing-control-drawing.md)|  
  
 Bu iyileştirmeler uygulamak üye işlevleri hakkında ayrıntılı bilgi için bkz: [COleControl](../mfc/reference/colecontrol-class.md). Üye işlevleri gibi kullanarak, listelenen [penceresiz işlemleri](http://msdn.microsoft.com/en-us/e9e28f79-9a70-4ae4-a5aa-b3e92f1904df) ve [etkin olmayan işaretçi işleme işlevleri](http://msdn.microsoft.com/en-us/e9e28f79-9a70-4ae4-a5aa-b3e92f1904df).  
  
 Daha fazla bilgi için bkz.:  
  
-   [Kalıcılığı ve Başlatmayı İyileştirme](../mfc/optimizing-persistence-and-initialization.md)  
  
-   [Penceresiz Etkinleştirme Sağlama](../mfc/providing-windowless-activation.md)  
  
-   [Kapatma etkinleştirin görünür seçeneği](../mfc/turning-off-the-activate-when-visible-option.md)  
  
-   [Devre Dışı İken Fare Etkileşimi Sağlama](../mfc/providing-mouse-interaction-while-inactive.md)  
  
-   [Titreşimsiz Etkinleştirme Sağlama](../mfc/providing-flicker-free-activation.md)  
  
-   [Kesilmemiş Bir Cihaz Bağlamı Kullanma](../mfc/using-an-unclipped-device-context.md)  
  
-   [Denetim Çizimini İyileştirme](../mfc/optimizing-control-drawing.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC ActiveX Denetimleri](../mfc/mfc-activex-controls.md)

