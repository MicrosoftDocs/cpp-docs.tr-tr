---
description: 'Hakkında daha fazla bilgi edinin: __noop'
title: __noop
ms.date: 09/02/2019
f1_keywords:
- __noop_cpp
- __noop
helpviewer_keywords:
- __noop keyword [C++]
ms.assetid: 81ac6e97-7bf8-496b-b3c4-fd02837573e5
ms.openlocfilehash: 4b140141e0f773f01cd666dd67f77244d7aef8a5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97222469"
---
# <a name="__noop"></a>__noop

**Microsoft'a Özgü**

İç öğe, **`__noop`** bir işlevin yoksayılması gerektiğini belirtir. Bağımsız değişken listesi ayrıştırılır, ancak bağımsız değişkenler için kod oluşturulmaz. Değişken sayıda bağımsız değişken alan genel hata ayıklama işlevlerinde kullanılmak üzere tasarlanmıştır.

Derleyici, **`__noop`** derleme zamanında iç öğesini 0 ' a dönüştürür.

## <a name="example"></a>Örnek

Aşağıdaki kod nasıl kullanabileceğinizi gösterir **`__noop`** .

```cpp
// compiler_intrinsics__noop.cpp
// compile with or without /DDEBUG
#include <stdio.h>

#if DEBUG
   #define PRINT   printf_s
#else
   #define PRINT   __noop
#endif

int main() {
   PRINT("\nhello\n");
}
```

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)\
[Anahtar sözcükler](../cpp/keywords-cpp.md)
