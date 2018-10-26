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
ms.openlocfilehash: 60139821c1b15673fac0fb8f9ec3925cbfa6dc31
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50052103"
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

