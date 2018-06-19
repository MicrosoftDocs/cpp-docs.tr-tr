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
ms.openlocfilehash: 724e9d7c4e0ee7db80f024c30e363612cb40fed1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33385371"
---
# <a name="tree-control-item-information"></a>Ağaç Denetim Öğesi Bilgileri
Ağaç denetimleri ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) denetimindeki öğeleri hakkında bilgi almak üye işlevleri vardır. [GetItem](../mfc/reference/ctreectrl-class.md#getitem) üye işlevi bazılarını veya tümünü bir öğesiyle ilişkili verileri alır. Bu veriler, öğenin metni, durumu, görüntüler, alt öğelerin sayısını ve bir uygulama tanımlı 32-bit veri değeri dahil olabilir. Ayrıca bir [SetItem](../mfc/reference/ctreectrl-class.md#setitem) bazılarını veya tümünü bir öğesiyle ilişkili verileri ayarlayabilirsiniz işlevi.  
  
 [GetItemState](../mfc/reference/ctreectrl-class.md#getitemstate), [Getıtemtext](../mfc/reference/ctreectrl-class.md#getitemtext), [Getıtemdata](../mfc/reference/ctreectrl-class.md#getitemdata), ve [GetItemImage](../mfc/reference/ctreectrl-class.md#getitemimage) üye işlevlerini tek tek özniteliklerini almak bir öğe. Bu işlevlerin her biri bir öğe özniteliklerini ayarlamak için karşılık gelen bir Set işlevi vardır.  
  
 [GetNextItem](../mfc/reference/ctreectrl-class.md#getnextitem) üye işlevi belirtilen ilişki geçerli öğeye taşıyan ağaç denetim öğesi alır. Bu işlev, bir öğenin üst, sonraki veya önceki görünür öğesi, ilk alt öğesi ve benzeri alabilir. Ağacı gezme için üye işlevleri de vardır: [GetRootItem](../mfc/reference/ctreectrl-class.md#getrootitem), [GetFirstVisibleItem](../mfc/reference/ctreectrl-class.md#getfirstvisibleitem), [GetNextVisibleItem](../mfc/reference/ctreectrl-class.md#getnextvisibleitem), [GetPrevVisibleItem](../mfc/reference/ctreectrl-class.md#getprevvisibleitem), [GetChildItem](../mfc/reference/ctreectrl-class.md#getchilditem), [GetNextSiblingItem](../mfc/reference/ctreectrl-class.md#getnextsiblingitem), [GetPrevSiblingItem](../mfc/reference/ctreectrl-class.md#getprevsiblingitem), [GetParentItem](../mfc/reference/ctreectrl-class.md#getparentitem), [GetSelectedItem](../mfc/reference/ctreectrl-class.md#getselecteditem), ve [GetDropHilightItem](../mfc/reference/ctreectrl-class.md#getdrophilightitem).  
  
 [GetItemRect](../mfc/reference/ctreectrl-class.md#getitemrect) üye işlevi bir ağaç denetim öğesi için sınırlayıcı dikdörtgenini alır. [GetCount](../mfc/reference/ctreectrl-class.md#getcount) ve [GetVisibleCount](../mfc/reference/ctreectrl-class.md#getvisiblecount) üye işlevleri almak ağaç denetimindeki öğeleri sayısını ve ağaç denetimin penceresinde sırasıyla görüntülenmekte olan öğe sayısı. Çağırarak belirli bir öğe görünür olduğundan emin olun [EnsureVisible](../mfc/reference/ctreectrl-class.md#ensurevisible) üye işlevi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CTreeCtrl kullanma](../mfc/using-ctreectrl.md)   
 [Denetimler](../mfc/controls-mfc.md)

