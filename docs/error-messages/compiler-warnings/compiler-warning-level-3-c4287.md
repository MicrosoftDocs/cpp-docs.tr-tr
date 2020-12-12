---
description: 'Daha fazla bilgi edinin: Derleyici Uyarısı (düzey 3) C4287'
title: Derleyici Uyarısı (düzey 3) C4287
ms.date: 11/04/2016
f1_keywords:
- C4287
helpviewer_keywords:
- C4287
ms.assetid: 1bf3bff8-6402-4d06-95ba-431678a790a7
ms.openlocfilehash: a82ad437a4ba6e7e374e7eb8f50359e7bf667e9a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97344087"
---
# <a name="compiler-warning-level-3-c4287"></a>Derleyici Uyarısı (düzey 3) C4287

' operator ': işaretsiz/negatif sabit uyuşmazlığı

İşaretsiz bir değişken negatif bir sayı olan bir işlemde kullanıldı.

Bu uyarı varsayılan olarak kapalıdır. Daha fazla bilgi için bkz. [Varsayılan olarak kapalı olan Derleyici uyarıları](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .

## <a name="example"></a>Örnek

Aşağıdaki örnek C4287 oluşturur:

```cpp
// C4287.cpp
// compile with: /W3
#pragma warning(default : 4287)
#include <stdio.h>

int main()
{
    unsigned int u = 1;
    if (u < -1)   // C4287
        printf_s("u LT -1");
    else
        printf_s("u !LT -1");
    return 0;
}
```
