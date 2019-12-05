---
title: __noop
ms.date: 09/02/2019
f1_keywords:
- __noop_cpp
- __noop
helpviewer_keywords:
- __noop keyword [C++]
ms.assetid: 81ac6e97-7bf8-496b-b3c4-fd02837573e5
ms.openlocfilehash: aec4df98413bf34ac1e2966d012bb905edd4775e
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/05/2019
ms.locfileid: "74857937"
---
# <a name="__noop"></a>__noop

**Microsoft 'a özgü**

`__noop` iç, bir işlevin yoksayılması gerektiğini belirtir. Bağımsız değişken listesi ayrıştırılır, ancak bağımsız değişkenler için kod oluşturulmaz. Değişken sayıda bağımsız değişken alan genel hata ayıklama işlevlerinde kullanılmak üzere tasarlanmıştır.

Derleyici, derleme zamanında `__noop` iç öğesini 0 ' a dönüştürür.

## <a name="example"></a>Örnek

Aşağıdaki kod `__noop`nasıl kullanabileceğinizi gösterir.

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

[Derleyici iç](../intrinsics/compiler-intrinsics.md) bilgileri\
[Anahtar Sözcükler](../cpp/keywords-cpp.md)
