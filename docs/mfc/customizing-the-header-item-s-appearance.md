---
title: Üstbilgi öğesi özelleştirme&#39;s görünüm | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- header controls [MFC], customization of items
- CHeaderCtrl class [MFC], customizing the items
- HDS_ styles
ms.assetid: b1e1e326-ec7d-4dbd-a46f-96a3e2055618
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e09f8bc0b61e22435ee348968f117940b57132e3
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/25/2018
ms.locfileid: "36930881"
---
# <a name="customizing-the-header-item39s-appearance"></a>Üstbilgi öğesi özelleştirme&#39;s görünümü
Ayarlayarak *dwStyle* üstbilgi denetimi ilk oluşturduğunuzda parametre ([CHeaderCtrl::Create](../mfc/reference/cheaderctrl-class.md#create)), görünüm tanımlayabilirsiniz ve üstbilgi davranışını öğelerini ya da üstbilgisi denetimi.  
  
 Örnekleme ayarlayabileceğiniz stilleri ve bunların amaçla şöyledir:  
  
-   Basma düğmesi gibi ara üstbilgi öğesi yapma **HDS_BUTTONS** stili.  
  
     Fare tıklamaları verileri Microsoft Outlook içinde gerçekleştirilir gibi belirli bir sütuna göre sıralama gibi bir üstbilgi öğesinin yanıt eylemleri gerçekleştirmek istiyorsanız, bu stil kullanın.  
  
-   Fare imlecini üzerlerine başarılı olduğunda üstbilgi öğeleri "sıcak izleme" görünümünü sunmak için bunu kullanın **HDS_HOTTRACK** stili.  
  
     Etkin izleme görüntüler 3B anahat işaretçinin aksi düz bir öğeyi üzerinden geçerken çubuğu.  
  
-   Üstbilgi denetimi gizli olduğunu belirtmek için kullanın **HDS_HIDDEN** stili.  
  
     **HDS_HIDDEN** stilini gösterir üstbilgi denetimine veri kapsayıcısını ve görsel bir denetim kullanılmak üzere tasarlanmıştır. Bu stili otomatik olarak denetim gizlemez ancak, bunun yerine, davranışını etkiler `CHeaderCtrl::Layout`. Döndürülen değerin *cy* üyesi `WINDOWPOS` yapısı sıfır olacak belirten denetimi kullanıcıya görünür olmamalıdır.  
  
 Bu özellikler hakkında daha fazla bilgi için bkz: [öğeleri](http://msdn.microsoft.com/library/windows/desktop/bb775238) Windows SDK. Üstbilgi denetimine öğe ekleme hakkında daha fazla bilgi için bkz: [üstbilgi denetimine öğe eklemeyi](../mfc/adding-items-to-the-header-control.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CHeaderCtrl kullanma](../mfc/using-cheaderctrl.md)   
 [Denetimler](../mfc/controls-mfc.md)

