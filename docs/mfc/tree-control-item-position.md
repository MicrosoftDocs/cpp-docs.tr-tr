---
description: 'Daha fazla bilgi edinin: Ağaç Denetim öğesi konumu'
title: Ağaç Denetim Öğesi Konumu
ms.date: 11/04/2016
helpviewer_keywords:
- CTreeCtrl class [MFC], item position
- item position in tree controls
- tree controls [MFC], item position
- position, CTreeCtrl items
ms.assetid: cd264344-2cf9-4d90-9ea8-c6900b6f60e7
ms.openlocfilehash: 7eeab82c48344f7e16a31b8d6962007024277dfc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97264082"
---
# <a name="tree-control-item-position"></a>Ağaç Denetim Öğesi Konumu

Öğe, üye işlevi kullanılarak ağaç denetimine ([Ctreecini](../mfc/reference/ctreectrl-class.md)) eklendiğinde bir öğenin ilk konumu ayarlanır `InsertItem` . Üye işlevi çağrısı, üst öğenin tanıtıcısını ve yeni öğe eklenecek öğenin tanıtıcısını belirtir. İkinci işleyici, belirtilen üst öğenin bir alt öğesini veya şu değerlerden birini tanımlamalıdır: `TVI_FIRST` , `TVI_LAST` , veya `TVI_SORT` .

`TVI_FIRST`Veya `TVI_LAST` belirtildiğinde, ağaç denetimi, belirtilen üst öğenin alt öğe listesinin başına veya sonuna yeni öğe koyar. Belirtildiğinde `TVI_SORT` , ağaç denetimi, öğe etiketlerinin metnine göre alfabetik sırada alt öğeler listesine yeni öğe ekler.

[SortChildren](../mfc/reference/ctreectrl-class.md#sortchildren) member işlevini çağırarak, bir üst öğenin alt öğe listesini alfabetik sırada yerleştirebilirsiniz. Bu işlev, belirtilen üst öğeden azalan alt öğe düzeylerinin aynı zamanda alfabetik sırada sıralanıp sıralanmayacağını belirten bir parametre içerir.

[SortChildrenCB](../mfc/reference/ctreectrl-class.md#sortchildrencb) üye işlevi, tanımladığınız ölçütlere göre alt öğeleri sıralamanıza olanak tanır. Bu işlevi çağırdığınızda, iki alt öğenin göreli sırası karar verilmesi gerektiğinde ağaç denetiminin çağırabileceği uygulama tanımlı bir geri çağırma işlevi belirtirsiniz. Geri arama işlevi, karşılaştırılan öğeler için 2 32 bitlik uygulama tanımlı değerler ve çağrılırken belirttiğiniz üçüncü 32 bit bir değer alır `SortChildrenCB` .

## <a name="see-also"></a>Ayrıca bkz.

[CTreeCtrl Kullanma](../mfc/using-ctreectrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
