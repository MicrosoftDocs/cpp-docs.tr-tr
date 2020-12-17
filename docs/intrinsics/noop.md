---
description: 'Microsoft C/C++ iç hakkında daha fazla bilgi edinin: __noop'
title: __noop
ms.date: 12/16/2020
f1_keywords:
- __noop_cpp
- __noop
helpviewer_keywords:
- __noop keyword [C++]
ms.assetid: 81ac6e97-7bf8-496b-b3c4-fd02837573e5
ms.openlocfilehash: 5fd300ca8d68305a12e6b5540be05aa60a042a44
ms.sourcegitcommit: 387ce22a3b0137f99cbb856a772b5a910c9eba99
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/17/2020
ms.locfileid: "97645091"
---
# `__noop`

**Microsoft 'a özgü** **`__noop`** iç öğe, bir işlevin yoksayılması gerektiğini belirtir. Bağımsız değişken listesi ayrıştırılır, ancak bağımsız değişkenler için kod oluşturulmaz. Derleyici, bağımsız değişkenleri derleyici uyarısı C4100 ve benzer analizler için Başvurulmuş olarak değerlendirir. İç öğe, `__noop` değişken sayıda bağımsız değişken alan genel hata ayıklama işlevlerinde kullanılmak üzere tasarlanmıştır.

Derleyici, **`__noop`** derleme zamanında iç öğesini 0 ' a dönüştürür.

## <a name="example"></a>Örnek

Aşağıdaki kod nasıl kullanabileceğinizi gösterir **`__noop`** .

```cpp
// compiler_intrinsics__noop.cpp
// compile using: cl /EHsc /W4 compiler_intrinsics__noop.cpp
// compile with or without /DDEBUG
#include <stdio.h>

#if DEBUG
   #define PRINT   printf_s
#else
   #define PRINT   __noop
#endif

#define IGNORE(x) { __noop(x); }

int main(int argv, char ** argc)
{
   IGNORE(argv);
   IGNORE(argc);
   PRINT("\nDEBUG is defined\n");
}
```

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)\
[Anahtar Sözcükler](../cpp/keywords-cpp.md)
