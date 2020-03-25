---
title: false (C++)
ms.date: 11/04/2016
f1_keywords:
- false_cpp
helpviewer_keywords:
- false keyword [C++]
ms.assetid: cc13aec5-1f02-4d38-8dbf-5473ea2b354f
ms.openlocfilehash: f363e309b91e44472447d040aa36752750afec6f
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80188941"
---
# <a name="false-c"></a>false (C++)

Anahtar sözcüğü, [bool](../cpp/bool-cpp.md) türünde bir değişken veya koşullu ifade için iki değerden biridir (koşullu ifade artık **Gerçek** bir Boolean ifadedir). Örneğin, `i` **bool**türünde bir değişkense, `i = false;` ifade `i`**false değerini** atar.

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
