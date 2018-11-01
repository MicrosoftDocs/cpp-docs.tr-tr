---
title: Ağaç Denetim Öğesi Konumu
ms.date: 11/04/2016
helpviewer_keywords:
- CTreeCtrl class [MFC], item position
- item position in tree controls
- tree controls [MFC], item position
- position, CTreeCtrl items
ms.assetid: cd264344-2cf9-4d90-9ea8-c6900b6f60e7
ms.openlocfilehash: d39e48cf940f3e5e903fc8a1c82952d5c2550c05
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50501211"
---
# <a name="tree-control-item-position"></a>Ağaç Denetim Öğesi Konumu

Ağaç denetimi için öğe eklendiğinde bir öğenin ilk konumunu ayarlanır ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) kullanarak `InsertItem` üye işlevi. Üye işlev çağrısı, üst öğesinin tanıtıcısı ve daha sonra eklenecek yeni öğe olan öğenin tanıtıcı belirtir. İkinci tanıtıcı belirli bir üst grubun bir alt öğesi tanımlamalıdır veya bu değerlerden birini: `TVI_FIRST`, `TVI_LAST`, veya `TVI_SORT`.

Zaman `TVI_FIRST` veya `TVI_LAST` belirtilirse, ağaç denetimi, belirli bir üst öğenin alt öğelerinin listesini başında veya sonunda yeni öğe yerleştirir. Zaman `TVI_SORT` belirtilirse, ağaç denetimi etiketlerini metne göre alfabetik sırada alt öğe listesine yeni öğe ekler.

Çağırarak bir üst öğenin alt öğelerinin listesi alfabetik sırada koyabilirsiniz [SortChildren](../mfc/reference/ctreectrl-class.md#sortchildren) üye işlevi. Bu işlev, belirtilen üst öğesinden azalan düzende alt öğelerinin tüm düzeyleri de alfabetik olarak sıralanmış olup olmadığını belirten bir parametre içerir.

[SortChildrenCB](../mfc/reference/ctreectrl-class.md#sortchildrencb) üye işlevi, belirlediğiniz ölçütlere göre alt öğeleri sıralama olanak tanır. Bu işlev çağırdığınızda, iki alt öğelerin göreli sırasını kampanyanızın olması gerektiğinde ağaç denetimi çağırabilen bir uygulama tanımlı geri çağırma işlevi belirtin. Uygulama tanımlı iki 32-bit değerleri karşılaştırılan öğelerin ve çağırırken belirttiğiniz üçüncü bir 32-bit değeri geri çağırma işlevini alır `SortChildrenCB`.

## <a name="see-also"></a>Ayrıca Bkz.

[CTreeCtrl Kullanma](../mfc/using-ctreectrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)

