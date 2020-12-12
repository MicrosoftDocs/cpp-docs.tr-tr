---
description: 'Hakkında daha fazla bilgi edinin: true (C++)'
title: true (C++)
ms.date: 11/04/2016
f1_keywords:
- true_cpp
helpviewer_keywords:
- true keyword [C++]
ms.assetid: 96be2a70-51c3-4250-9752-874d25a5a11e
ms.openlocfilehash: 6f3a9a183a30057ab3a013dad6e03458e6532658
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97186460"
---
# <a name="true-c"></a>true (C++)

## <a name="syntax"></a>Syntax

```
bool-identifier = true ;
bool-expression logical-operator true ;
```

## <a name="remarks"></a>Açıklamalar

Bu anahtar sözcük, [bool](../cpp/bool-cpp.md) türünde bir değişken veya koşullu ifade için iki değerden biridir (koşullu ifade artık gerçek bir Boolean ifadedir). `i`Türünde ise **`bool`** , ifade `i = true;` **`true`** öğesine atar `i` .

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

[Anahtar sözcükler](../cpp/keywords-cpp.md)
