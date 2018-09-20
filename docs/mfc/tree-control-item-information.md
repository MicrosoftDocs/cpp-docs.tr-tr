---
title: Ağaç denetim öğesi bilgileri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- tree controls [MFC], item information
- CTreeCtrl class [MFC], item information
ms.assetid: 8dcab855-27de-49e9-95d8-f78ba963ea71
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a61d6dbf2084288d6015e8fc2c08bfc2283d4ba4
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46391026"
---
# <a name="tree-control-item-information"></a>Ağaç Denetim Öğesi Bilgileri

Ağaç denetimleri ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) denetimindeki öğeler hakkında bilgi almak üye işlevleri vardır. [GetItem](../mfc/reference/ctreectrl-class.md#getitem) üye işlevi, bazılarını veya tümünü bir öğeyle ilişkili verileri alır. Bu veriler, öğenin metni, durumu, resimleri, alt öğelerinin sayısını ve bir uygulama tarafından tanımlanan bir 32-bit veri değeri içerebilir. Ayrıca bir [SetItem](../mfc/reference/ctreectrl-class.md#setitem) bazılarını veya tümünü bir öğeyle ilişkili verileri ayarlayabilirsiniz işlevi.

[GetItemState](../mfc/reference/ctreectrl-class.md#getitemstate), [Getıtemtext](../mfc/reference/ctreectrl-class.md#getitemtext), [Getıtemdata](../mfc/reference/ctreectrl-class.md#getitemdata), ve [GetItemImage](../mfc/reference/ctreectrl-class.md#getitemimage) üye işlevleri, tek tek öznitelikler almak bir öğe. Bu işlevlerin her biri, bir öğenin öznitelikleri ayarlamaya yönelik karşılık gelen bir Set işlevi vardır.

[GetNextItem](../mfc/reference/ctreectrl-class.md#getnextitem) üye işlevi, belirtilen ilişki geçerli öğesine atanmış ağaç denetim öğesi alır. Bu işlev, bir öğenin üst, sonraki veya önceki görünür öğesi, ilk alt öğe ve benzeri alabilirsiniz. Ağacı gezme üye işlevleri de vardır: [GetRootItem](../mfc/reference/ctreectrl-class.md#getrootitem), [GetFirstVisibleItem](../mfc/reference/ctreectrl-class.md#getfirstvisibleitem), [GetNextVisibleItem](../mfc/reference/ctreectrl-class.md#getnextvisibleitem), [GetPrevVisibleItem](../mfc/reference/ctreectrl-class.md#getprevvisibleitem), [GetChildItem](../mfc/reference/ctreectrl-class.md#getchilditem), [GetNextSiblingItem](../mfc/reference/ctreectrl-class.md#getnextsiblingitem), [GetPrevSiblingItem](../mfc/reference/ctreectrl-class.md#getprevsiblingitem), [GetParentItem](../mfc/reference/ctreectrl-class.md#getparentitem), [GetSelectedItem](../mfc/reference/ctreectrl-class.md#getselecteditem), ve [GetDropHilightItem](../mfc/reference/ctreectrl-class.md#getdrophilightitem).

[GetItemRect](../mfc/reference/ctreectrl-class.md#getitemrect) üye işlevi bir ağaç denetim öğesi için sınırlayıcı dikdörtgeni alır. [GetCount](../mfc/reference/ctreectrl-class.md#getcount) ve [GetVisibleCount](../mfc/reference/ctreectrl-class.md#getvisiblecount) üye işlevleri, bir ağaç denetimindeki öğeler sayısını ve ağaç denetimin penceresinde sırasıyla görüntülenmekte olan öğe sayısını alın. Çağırarak belirli bir öğe görünür olduğundan emin olabilirsiniz [EnsureVisible](../mfc/reference/ctreectrl-class.md#ensurevisible) üye işlevi.

## <a name="see-also"></a>Ayrıca Bkz.

[CTreeCtrl Kullanma](../mfc/using-ctreectrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)

