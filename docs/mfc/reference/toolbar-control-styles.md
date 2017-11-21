---
title: ToolBar denetim stilleri | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: ToolBar control styles [MFC]
ms.assetid: 0f717eb9-fa32-4263-b852-809238863feb
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 426620f5c4282858d28e80494c1f2a53a3da0fa3
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="toolbar-control-styles"></a>ToolBar Denetim Stilleri
[CMFCToolBarButton sınıfı](../../mfc/reference/cmfctoolbarbutton-class.md) görünümünü belirleyen stili bayrakları kümesi ve düğme davranışını sahiptir. Bu bayrak birleşimi çağırarak ayarlayabileceğiniz [CMFCToolBarButton::SetStyle](../../mfc/reference/cmfctoolbarbutton-class.md#setstyle). Bu konu, stil bayrak değerleri ve anlamlarını listeler.  
  
## <a name="property-values"></a>Özellik değerleri  
 Aşağıdaki değerleri denetimini temsil eden düğmesi türünü belirleyin:  
  
 TBBS_BUTTON  
 Standart basma düğmesi (varsayılan).  
  
 TBBS_CHECKBOX  
 onay kutusunu seçin.  
  
 TBBS_CHECKGROUP  
 Onay kutularını birtakım başlangıcı.  
  
 TBBS_GROUP  
 Bir grup düğmesi başlangıcı.  
  
 TBBS_SEPARATOR  
 Ayırıcı.  
  
 Aşağıdaki değerleri denetimi geçerli durumunu temsil eder:  
  
 TBBS_CHECKED  
 Onay kutusu işaretliyse.  
  
 TBBS_DISABLED  
 Denetim devre dışı bırakıldı.  
  
 TBBS_INDETERMINATE  
 Onay kutusunu belirlenmemiş bir durumda.  
  
 TBBS_PRESSED  
 Düğmeye basıldığında.  
  
 Aşağıdaki değeri araç çubuğu düğmesini yerleşimini değiştirir:  
  
 TBBS_BREAK  
 Öğeyi sütunları ayırarak olmadan yeni bir satır veya yeni bir sütun yerleştirir.  
  
## <a name="remarks"></a>Açıklamalar  
 Geçerli stili depolanan [CMFCToolBarButton::m_nStyle](../../mfc/reference/cmfctoolbarbutton-class.md#m_nstyle). Yeni bir değer ayarlamayın `m_nStyle` doğrudan bazı türetilen sınıflar çağırdığınızda ek işleme gerçekleştirdiğinden `SetStyles`.  
  
 Görsel Yöneticisi her durum düğmeleri görünümünü belirler. Bkz: [seri hale getirme Yöneticisi](../../mfc/visualization-manager.md) daha fazla bilgi için.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxtoolbarbutton.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Makroları ve genel öğeleri](../../mfc/reference/mfc-macros-and-globals.md)   
 [CMFCToolBarButton sınıfı](../../mfc/reference/cmfctoolbarbutton-class.md)   
 [Seri hale getirme Yöneticisi](../../mfc/visualization-manager.md)


