---
title: Üstbilgi denetimindeki öğeleri sıralama | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- DS_DRAGDROP
dev_langs:
- C++
helpviewer_keywords:
- sequence [MFC]
- sequence [MFC], header control items
- OrderToIndex method [MFC]
- DS_DRAGDROP notification [MFC]
- GetOrderArray method [MFC]
- SetOrderArray method [MFC]
- header controls [MFC], ordering items
ms.assetid: 5aaef872-75b5-49c5-8fed-6f9a81fca812
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f446eb557fab4f4ff6396042e832e4584546bd96
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46416831"
---
# <a name="ordering-items-in-the-header-control"></a>Üstbilgi Denetimindeki Öğeleri Sıralama

Kaydederler [bir üstbilgi denetimine öğe eklendiğinde](../mfc/adding-items-to-the-header-control.md), yönetmek veya bunların sırası ile aşağıdaki işlevleri hakkında bilgi edinin:

- [CHeaderCtrl::GetOrderArray](../mfc/reference/cheaderctrl-class.md#getorderarray) ve [CHeaderCtrl::SetOrderArray](../mfc/reference/cheaderctrl-class.md#setorderarray)

     Alır ve üstbilgi öğeleri soldan sağa sırasını ayarlar.

- [CHeaderCtrl::OrderToIndex](../mfc/reference/cheaderctrl-class.md#ordertoindex).

     Özel üstbilgi öğesi için dizin değerini alır.

Önceki üye işlevlerinin yanı sıra HDS_DRAGDROP stili kullanıcının üstbilgi denetimindeki üstbilgi öğeleri sürükleyip izin verir. Daha fazla bilgi için [üstbilgi öğeleri için sürükle ve bırak desteği sağlama](../mfc/providing-drag-and-drop-support-for-header-items.md).

## <a name="see-also"></a>Ayrıca Bkz.

[CHeaderCtrl Kullanma](../mfc/using-cheaderctrl.md)

