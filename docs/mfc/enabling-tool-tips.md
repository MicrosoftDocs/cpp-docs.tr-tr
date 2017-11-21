---
title: "Araç ipuçlarını etkinleştirme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- initializing tool tips [MFC]
- enabling tool tips [MFC]
- tool tips [MFC], initializing
- tool tips [MFC], enabling
ms.assetid: 06b7c889-7722-4ce6-8b88-9efa50fe6369
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 7c7e35dab6a94a01851b667ce4ab3dd58aa4bd8d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="enabling-tool-tips"></a>Araç İpuçlarını Etkinleştirme
(Örneğin, bir form görünümü veya iletişim kutusu denetimleri) penceresinin alt denetimler için araç ipucu destek etkinleştirebilirsiniz.  
  
### <a name="to-enable-tool-tips-for-the-child-controls-of-a-window"></a>Pencerenin alt denetimler için araç ipuçları etkinleştirmek için  
  
1.  Çağrı `EnableToolTips` araç ipuçları sağlamak istediğiniz penceresi.  
  
2.  Her denetim için bir dize girin, [TTN_NEEDTEXT bildirimini](../mfc/handling-ttn-needtext-notification-for-tool-tips.md) işleyicisi. Alt denetimler (örneğin, form görünümü sınıfı) içeren bir pencere ileti haritasını işleyicisidir. Bu işleyici, bir işlev çağırmalıdır denetimi tanımlar ve ayarlar **pszText** araç ipucunu denetimini tarafından kullanılan metin belirtmek için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Cframewnd'den türetilmemiş pencerelerde araç ipuçları](../mfc/tool-tips-in-windows-not-derived-from-cframewnd.md)

