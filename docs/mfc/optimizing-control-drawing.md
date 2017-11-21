---
title: "Denetim çizimini iyileştirme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: MFC ActiveX controls [MFC], optimizing
ms.assetid: 29ff985d-9bf5-4678-b62d-aad12def75fb
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: b7b78bd517e7f31168c13595ec699b223ba458e4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="optimizing-control-drawing"></a>Denetim Çizimini İyileştirme
Kendisini bir kapsayıcı tarafından sağlanan cihaz bağlamına çizmek için bir denetim istendiğinde, genellikle GDI Nesneleri (örneğin, kalemler, Fırçalar ve yazı tipleri) cihaz bağlamına seçer, çizim işlemlerini gerçekleştirir ve önceki GDI nesneleri geri yükler. Daha önce seçilen nesneleri denetimleri tek tek geri yüklemezseniz kapsayıcı aynı cihaz bağlamına çizilecek birden çok denetimleri varsa ve her denetim gerektirdiği GDI nesneleri seçer, zaman kaydedilebilir. Tüm denetimler çizilmiş sonra kapsayıcı özgün nesneleri otomatik olarak geri yükleyebilirsiniz.  
  
 Bir kapsayıcı bu teknik destekleyip desteklemediğini belirlemek için bir denetim çağırabilirsiniz [COleControl::IsOptimizedDraw](../mfc/reference/colecontrol-class.md#isoptimizeddraw) üye işlevi. Bu işlev döndürürse **doğru**, denetim daha önce seçilen nesneleri geri yüklemek normal adımını atlayabilirsiniz.  
  
 Aşağıdaki (iyileştirilmemiş) sahip bir denetim göz önünde bulundurun `OnDraw` işlevi:  
  
 [!code-cpp[NVC_MFC_AxOpt#15](../mfc/codesnippet/cpp/optimizing-control-drawing_1.cpp)]  
  
 Bu örnekte fırça ve Kalem kapsamının dışında olduğunuzda bunların Yıkıcılar çağrılır anlamına yerel değişkenlerdir, (zaman `OnDraw` çalışması sona erer). Yıkıcılar karşılık gelen GDI Nesneleri silme girişiminde bulunur. Ancak bunları döndürme bağlı cihaz bağlamı içine seçili bırakın planlıyorsanız, bunlar silinmemelidir `OnDraw`.  
  
 Önlemek için [CPen](../mfc/reference/cpen-class.md) ve [CBrush](../mfc/reference/cbrush-class.md) zaman zarar nesnelerin `OnDraw` sonlandığında üye değişkenlerine yerel değişkenler yerine bunları depolamak. Denetimin sınıf bildiriminde iki yeni üye değişkenleri için bildirimleri ekleyin:  
  
 [!code-cpp[NVC_MFC_AxOpt#16](../mfc/codesnippet/cpp/optimizing-control-drawing_2.h)]  
[!code-cpp[NVC_MFC_AxOpt#17](../mfc/codesnippet/cpp/optimizing-control-drawing_3.h)]  
  
 Ardından, `OnDraw` işlevi yeniden yazılmıştır gibi:  
  
 [!code-cpp[NVC_MFC_AxOpt#18](../mfc/codesnippet/cpp/optimizing-control-drawing_4.cpp)]  
  
 Kalem ve oluşturulmasını fırça her zaman bu yaklaşımı önler `OnDraw` olarak adlandırılır. Ek örnek veri koruma hızlı geliştirme geliyor.  
  
 ForeColor veya BackColor özelliği değişirse kalem veya fırça yeniden oluşturulması gerekir. Bunu yapmak için geçersiz kılma [OnForeColorChanged](../mfc/reference/colecontrol-class.md#onforecolorchanged) ve [OnBackColorChanged](../mfc/reference/colecontrol-class.md#onbackcolorchanged) üye işlevleri:  
  
 [!code-cpp[NVC_MFC_AxOpt#19](../mfc/codesnippet/cpp/optimizing-control-drawing_5.cpp)]  
  
 Son olarak, gereksiz ortadan kaldırmak için `SelectObject` çağrıları, değişiklik `OnDraw` gibi:  
  
 [!code-cpp[NVC_MFC_AxOpt#20](../mfc/codesnippet/cpp/optimizing-control-drawing_6.cpp)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC ActiveX denetimleri: iyileştirme](../mfc/mfc-activex-controls-optimization.md)   
 [COleControl sınıfı](../mfc/reference/colecontrol-class.md)   
 [MFC ActiveX denetimleri](../mfc/mfc-activex-controls.md)   
 [MFC ActiveX denetimleri](../mfc/mfc-activex-controls.md)   
 [MFC ActiveX Denetim Sihirbazı](../mfc/reference/mfc-activex-control-wizard.md)   
 [MFC ActiveX denetimleri: ActiveX denetimini boyama](../mfc/mfc-activex-controls-painting-an-activex-control.md)

