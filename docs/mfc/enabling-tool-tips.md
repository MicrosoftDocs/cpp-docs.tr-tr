---
title: Araç ipuçlarını etkinleştirme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- initializing tool tips [MFC]
- enabling tool tips [MFC]
- tool tips [MFC], initializing
- tool tips [MFC], enabling
ms.assetid: 06b7c889-7722-4ce6-8b88-9efa50fe6369
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 598583360eca2a65a5352fc9d284d8d359ac021c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="enabling-tool-tips"></a>Araç İpuçlarını Etkinleştirme
(Örneğin, bir form görünümü veya iletişim kutusu denetimleri) penceresinin alt denetimler için araç ipucu destek etkinleştirebilirsiniz.  
  
### <a name="to-enable-tool-tips-for-the-child-controls-of-a-window"></a>Pencerenin alt denetimler için araç ipuçları etkinleştirmek için  
  
1.  Çağrı `EnableToolTips` araç ipuçları sağlamak istediğiniz penceresi.  
  
2.  Her denetim için bir dize girin, [TTN_NEEDTEXT bildirimini](../mfc/handling-ttn-needtext-notification-for-tool-tips.md) işleyicisi. Alt denetimler (örneğin, form görünümü sınıfı) içeren bir pencere ileti haritasını işleyicisidir. Bu işleyici, bir işlev çağırmalıdır denetimi tanımlar ve ayarlar **pszText** araç ipucunu denetimini tarafından kullanılan metin belirtmek için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CFrameWnd'den Türetilmemiş Pencerelerde Araç İpuçları](../mfc/tool-tips-in-windows-not-derived-from-cframewnd.md)

