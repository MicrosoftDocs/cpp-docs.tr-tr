---
title: "Üstbilgi öğesi &#39; özelleştirme s görünüm | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- header controls [MFC], customization of items
- CHeaderCtrl class [MFC], customizing the items
- HDS_ styles
ms.assetid: b1e1e326-ec7d-4dbd-a46f-96a3e2055618
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: dacb5cc7aa1c6d7c74a07ee911c5887efe1d877b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="customizing-the-header-item39s-appearance"></a>Üstbilgi öğesi &#39; özelleştirme s görünümü
Ayarlayarak *dwStyle* üstbilgi denetimi ilk oluşturduğunuzda parametre ([CHeaderCtrl::Create](../mfc/reference/cheaderctrl-class.md#create)), görünüm tanımlayabilirsiniz ve üstbilgi davranışını öğelerini ya da üstbilgisi denetimi.  
  
 Örnekleme ayarlayabileceğiniz stilleri ve bunların amaçla şöyledir:  
  
-   Basma düğmesi gibi ara üstbilgi öğesi yapma `HDS_BUTTONS` stili.  
  
     Fare tıklamaları verileri Microsoft Outlook içinde gerçekleştirilir gibi belirli bir sütuna göre sıralama gibi bir üstbilgi öğesinin yanıt eylemleri gerçekleştirmek istiyorsanız, bu stil kullanın.  
  
-   Fare imlecini üzerlerine başarılı olduğunda üstbilgi öğeleri "sıcak izleme" görünümünü sunmak için bunu kullanın `HDS_HOTTRACK` stili.  
  
     Etkin izleme görüntüler 3B anahat işaretçinin aksi düz bir öğeyi üzerinden geçerken çubuğu.  
  
-   Üstbilgi denetimi gizli olduğunu belirtmek için kullanın `HDS_HIDDEN` stili.  
  
     `HDS_HIDDEN` Stilini gösterir üstbilgi denetimine veri kapsayıcısını ve görsel bir denetim kullanılmak üzere tasarlanmıştır. Bu stili otomatik olarak denetim gizlemez ancak, bunun yerine, davranışını etkiler `CHeaderCtrl::Layout`. Döndürülen değerin **cy** üyesi `WINDOWPOS` yapısı sıfır olacak belirten denetimi kullanıcıya görünür olmamalıdır.  
  
 Bu özellikler hakkında daha fazla bilgi için bkz: [öğeleri](http://msdn.microsoft.com/library/windows/desktop/bb775238) Windows SDK. Üstbilgi denetimine öğe ekleme hakkında daha fazla bilgi için bkz: [üstbilgi denetimine öğe eklemeyi](../mfc/adding-items-to-the-header-control.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CHeaderCtrl kullanma](../mfc/using-cheaderctrl.md)   
 [Denetimler](../mfc/controls-mfc.md)

