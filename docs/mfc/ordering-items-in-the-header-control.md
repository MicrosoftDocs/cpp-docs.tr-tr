---
title: Üstbilgi Denetimindeki Öğeleri Sıralama
ms.date: 11/04/2016
f1_keywords:
- DS_DRAGDROP
helpviewer_keywords:
- sequence [MFC]
- sequence [MFC], header control items
- OrderToIndex method [MFC]
- DS_DRAGDROP notification [MFC]
- GetOrderArray method [MFC]
- SetOrderArray method [MFC]
- header controls [MFC], ordering items
ms.assetid: 5aaef872-75b5-49c5-8fed-6f9a81fca812
ms.openlocfilehash: bae351d921c25993d6b7029f9052e1938179673b
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57282031"
---
# <a name="ordering-items-in-the-header-control"></a>Üstbilgi Denetimindeki Öğeleri Sıralama

Kaydederler [bir üstbilgi denetimine öğe eklendiğinde](../mfc/adding-items-to-the-header-control.md), yönetmek veya bunların sırası ile aşağıdaki işlevleri hakkında bilgi edinin:

- [CHeaderCtrl::GetOrderArray](../mfc/reference/cheaderctrl-class.md#getorderarray) ve [CHeaderCtrl::SetOrderArray](../mfc/reference/cheaderctrl-class.md#setorderarray)

   Alır ve üstbilgi öğeleri soldan sağa sırasını ayarlar.

- [CHeaderCtrl::OrderToIndex](../mfc/reference/cheaderctrl-class.md#ordertoindex).

   Özel üstbilgi öğesi için dizin değerini alır.

Önceki üye işlevlerinin yanı sıra HDS_DRAGDROP stili kullanıcının üstbilgi denetimindeki üstbilgi öğeleri sürükleyip izin verir. Daha fazla bilgi için [üstbilgi öğeleri için sürükle ve bırak desteği sağlama](../mfc/providing-drag-and-drop-support-for-header-items.md).

## <a name="see-also"></a>Ayrıca bkz.

[CHeaderCtrl Kullanma](../mfc/using-cheaderctrl.md)
