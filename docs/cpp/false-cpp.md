---
title: false (C++)
ms.date: 11/04/2016
f1_keywords:
- false_cpp
helpviewer_keywords:
- false keyword [C++]
ms.assetid: cc13aec5-1f02-4d38-8dbf-5473ea2b354f
ms.openlocfilehash: 5fc27c7f1dfde7d1f686f0a752652773ade9cc0e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50464070"
---
# <a name="false-c"></a>false (C++)

Anahtar sözcüğü bir değişken türü için iki değerlerden biri [bool](../cpp/bool-cpp.md) ya da bir koşullu ifade (artık bir koşullu ifade olan bir **true** Boole ifadesi). Örneğin, varsa `i` türünde bir değişken **bool**, `i = false;` deyimi atar **false** için `i`.

## <a name="example"></a>Örnek

```cpp
// bool_false.cpp
#include <stdio.h>

int main()
{
    bool bb = true;
    printf_s("%d\n", bb);
    bb = false;
    printf_s("%d\n", bb);
}
```

```Output
1
0
```

## <a name="see-also"></a>Ayrıca bkz.

[Anahtar Sözcükler](../cpp/keywords-cpp.md)