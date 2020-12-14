---
description: 'Daha fazla bilgi edinin: Ağaç Denetim öğesi bilgileri'
title: Ağaç Denetim Öğesi Bilgileri
ms.date: 11/04/2016
helpviewer_keywords:
- tree controls [MFC], item information
- CTreeCtrl class [MFC], item information
ms.assetid: 8dcab855-27de-49e9-95d8-f78ba963ea71
ms.openlocfilehash: ced75bdf6ed6a10e3a34536adf4af0ed1c7e0c86
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97264147"
---
# <a name="tree-control-item-information"></a>Ağaç Denetim Öğesi Bilgileri

Ağaç denetimlerinin ([Ctreeci](../mfc/reference/ctreectrl-class.md)) denetimdeki öğeler hakkında bilgi alan bir dizi üye işlevi vardır. [GetItem](../mfc/reference/ctreectrl-class.md#getitem) üye işlevi bir öğeyle ilişkili verilerin bazılarını veya tümünü alır. Bu veriler öğenin metnini, durumunu, görüntülerini, alt öğe öğelerinin sayısını ve uygulama tanımlı 32 bit veri değerini içerebilir. Ayrıca bir öğe ile ilişkili verilerin bazılarını veya tümünü ayarlayasağlayan bir [SetItem](../mfc/reference/ctreectrl-class.md#setitem) işlevi de vardır.

[GetItemState](../mfc/reference/ctreectrl-class.md#getitemstate), [GetItemText](../mfc/reference/ctreectrl-class.md#getitemtext), [GetItemData](../mfc/reference/ctreectrl-class.md#getitemdata)ve [GetItemImage](../mfc/reference/ctreectrl-class.md#getitemimage) üye işlevleri bir öğenin bağımsız özniteliklerini alır. Bu işlevlerin her biri, bir öğenin özniteliklerini ayarlamak için karşılık gelen bir set işlevine sahiptir.

[GetNextItem](../mfc/reference/ctreectrl-class.md#getnextitem) üye işlevi, geçerli öğeye belirtilen ilişkiyi oluşturan ağaç denetim öğesini alır. Bu işlev bir öğenin üst öğesini, bir sonraki veya önceki görünür öğeyi, ilk alt öğeyi vb. alabilir. Ağacın çapraz geçişini yapmak için de üye işlevleri vardır: [GetRootItem](../mfc/reference/ctreectrl-class.md#getrootitem), [GetFirstVisibleItem](../mfc/reference/ctreectrl-class.md#getfirstvisibleitem), [GetNextVisibleItem](../mfc/reference/ctreectrl-class.md#getnextvisibleitem), [GetPrevVisibleItem](../mfc/reference/ctreectrl-class.md#getprevvisibleitem), [GetChildItem](../mfc/reference/ctreectrl-class.md#getchilditem), [GetNextSiblingItem](../mfc/reference/ctreectrl-class.md#getnextsiblingitem), [GetPrevSiblingItem](../mfc/reference/ctreectrl-class.md#getprevsiblingitem), [getparentidıtem](../mfc/reference/ctreectrl-class.md#getparentitem), [getselecteditıtem](../mfc/reference/ctreectrl-class.md#getselecteditem)ve [getdrophmaltıtem](../mfc/reference/ctreectrl-class.md#getdrophilightitem).

[GetItemRect](../mfc/reference/ctreectrl-class.md#getitemrect) üye işlevi, bir ağaç denetim öğesi için sınırlayıcı dikdörtgeni alır. [GetCount](../mfc/reference/ctreectrl-class.md#getcount) ve [GetVisibleCount](../mfc/reference/ctreectrl-class.md#getvisiblecount) üye işlevleri, ağaç denetimindeki öğelerin sayısını ve şu anda ağaç denetimi penceresinde görünür olan öğelerin sayısını alır. [EnsureVisible](../mfc/reference/ctreectrl-class.md#ensurevisible) üye işlevini çağırarak belirli bir öğenin görünür olmasını sağlayabilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[CTreeCtrl Kullanma](../mfc/using-ctreectrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
