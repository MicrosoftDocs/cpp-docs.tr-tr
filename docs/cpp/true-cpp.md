---
title: true (C++)
ms.date: 11/04/2016
f1_keywords:
- true_cpp
helpviewer_keywords:
- true keyword [C++]
ms.assetid: 96be2a70-51c3-4250-9752-874d25a5a11e
ms.openlocfilehash: b497c3c9eb1b30074c9b7286c438d0077525e05b
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80188044"
---
# <a name="true-c"></a>true (C++)

## <a name="syntax"></a>Sözdizimi

```
bool-identifier = true ;
bool-expression logical-operator true ;
```

## <a name="remarks"></a>Açıklamalar

Bu anahtar sözcük, [bool](../cpp/bool-cpp.md) türünde bir değişken veya koşullu ifade için iki değerden biridir (koşullu ifade artık gerçek bir Boolean ifadedir). `i` **bool**türünde ise, `i = true;` deyimin `i`için **true değeri** atar.

## <a name="example"></a>Örnek

```cpp
// bool_true.cpp
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
