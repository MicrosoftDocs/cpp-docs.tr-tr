---
title: __noop
ms.date: 09/02/2019
f1_keywords:
- __noop_cpp
- __noop
helpviewer_keywords:
- __noop keyword [C++]
ms.assetid: 81ac6e97-7bf8-496b-b3c4-fd02837573e5
ms.openlocfilehash: 24ba85b1fbbba4491c03d5a81afae345228db3bd
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70217187"
---
# <a name="__noop"></a>__noop

**Microsoft 'a özgü**

İç `__noop` öğe, bir işlevin yoksayılması gerektiğini belirtir. Bağımsız değişken listesi ayrıştırılır, ancak bağımsız değişkenler için kod oluşturulmaz. Değişken sayıda bağımsız değişken alan genel hata ayıklama işlevlerinde kullanılmak üzere tasarlanmıştır.

Derleyici, derleme zamanında `__noop` iç öğesini 0 ' a dönüştürür.

## <a name="example"></a>Örnek

Aşağıdaki kod nasıl kullanabileceğinizi `__noop`gösterir.

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

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)\
[Anahtar Sözcükler](../cpp/keywords-cpp.md)
