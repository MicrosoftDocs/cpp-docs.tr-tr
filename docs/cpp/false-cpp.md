---
title: false (C++)
ms.date: 11/04/2016
f1_keywords:
- false_cpp
helpviewer_keywords:
- false keyword [C++]
ms.assetid: cc13aec5-1f02-4d38-8dbf-5473ea2b354f
ms.openlocfilehash: 5fc27c7f1dfde7d1f686f0a752652773ade9cc0e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62183732"
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