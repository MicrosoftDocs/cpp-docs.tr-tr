---
title: Ek İşleçlerini Kullanma
ms.date: 11/04/2016
helpviewer_keywords:
- operators [C++], addition
- additive operators
ms.assetid: 7d54841e-436d-4ae8-9865-1ac1829e6f22
ms.openlocfilehash: 0e2d802a77c56b8f458b614b29e86e2e1d30a55e
ms.sourcegitcommit: f4be868c0d1d78e550fba105d4d3c993743a1f4b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/12/2019
ms.locfileid: "56151435"
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

Değerini `i` uzunluğu ile çarpılan bir **float** ve eklenen `&x[4]`. Sonuçta elde edilen işaretçi değeri, `x[8]` adresidir.

```
j = &x[i] - &x[i-2];
```

Bu örnekte, üçüncü `x` öğesinin (`x[i-2]` tarafından verilmiştir) adresi, beşinci `x` öğesinin (`x[i]` tarafından verilmiştir) adresinden çıkarılır. Fark uzunluğuna bölünür bir **float**; tamsayı değeri 2 sonucudur.

## <a name="see-also"></a>Ayrıca bkz.

[C Ek İşleçleri](../c-language/c-additive-operators.md)
