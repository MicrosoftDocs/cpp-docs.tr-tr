---
description: 'Hakkında daha fazla bilgi edinin: toplama Işleçlerini kullanma'
title: Ek İşleçlerini Kullanma
ms.date: 11/04/2016
helpviewer_keywords:
- operators [C++], addition
- additive operators
ms.assetid: 7d54841e-436d-4ae8-9865-1ac1829e6f22
ms.openlocfilehash: d56a1b2e2696ae88598306271ed02c417ef63b0c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97318370"
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

Değeri, `i` bir ' nin uzunluğu ile çarpılır **`float`** ve öğesine eklenir `&x[4]` . Sonuçta elde edilen işaretçi değeri, `x[8]` adresidir.

```
j = &x[i] - &x[i-2];
```

Bu örnekte, üçüncü `x` öğesinin (`x[i-2]` tarafından verilmiştir) adresi, beşinci `x` öğesinin (`x[i]` tarafından verilmiştir) adresinden çıkarılır. Fark a 'nın uzunluğuna bölünür **`float`** ; sonuç, 2 tamsayı değeridir.

## <a name="see-also"></a>Ayrıca bkz.

[C eklenebilir Işleçler](../c-language/c-additive-operators.md)
