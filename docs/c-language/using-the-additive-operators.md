---
title: Ek İşleçlerini Kullanma
ms.date: 11/04/2016
helpviewer_keywords:
- operators [C++], addition
- additive operators
ms.assetid: 7d54841e-436d-4ae8-9865-1ac1829e6f22
ms.openlocfilehash: 0e2d802a77c56b8f458b614b29e86e2e1d30a55e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62344882"
---
# <a name="using-the-additive-operators"></a>Ek İşleçlerini Kullanma

Aşağıdaki örneklerde, toplama ve çıkarma işleçleri gösterilmekte ve bu bildirimler kullanılmaktadır:

```
int i = 4, j;
float x[10];
float *px;
```

Bu deyimler eşdeğerdir:

```
px = &x[4 + i];
px = &x[4] + i;
```

Değeri `i` bir **float** uzunluğu ile çarpılır ve öğesine `&x[4]`eklenir. Sonuçta elde edilen işaretçi değeri, `x[8]` adresidir.

```
j = &x[i] - &x[i-2];
```

Bu örnekte, üçüncü `x` öğesinin (`x[i-2]` tarafından verilmiştir) adresi, beşinci `x` öğesinin (`x[i]` tarafından verilmiştir) adresinden çıkarılır. Fark bir **float**uzunluğuna bölünür; Sonuç 2 tamsayı değeridir.

## <a name="see-also"></a>Ayrıca bkz.

[C eklenebilir Işleçler](../c-language/c-additive-operators.md)
