---
description: 'Hakkında daha fazla bilgi edinin: false (C++)'
title: false (C++)
ms.date: 11/04/2016
f1_keywords:
- false_cpp
helpviewer_keywords:
- false keyword [C++]
ms.assetid: cc13aec5-1f02-4d38-8dbf-5473ea2b354f
ms.openlocfilehash: 73f1f07c858f0a578cc2d3135e560cc8e0cb9d32
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97319462"
---
# <a name="false-c"></a>false (C++)

Anahtar sözcüğü, [bool](../cpp/bool-cpp.md) türünde bir değişken veya koşullu ifade için iki değerden biridir (koşullu ifade artık bir **`true`** Boolean ifadedir). Örneğin, `i` türünde bir değişkense **`bool`** , `i = false;` ifade **`false`** öğesine atar `i` .

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

[Anahtar sözcükler](../cpp/keywords-cpp.md)
