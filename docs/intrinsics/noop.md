---
title: __noop
ms.date: 11/04/2016
f1_keywords:
- __noop_cpp
- __noop
helpviewer_keywords:
- __noop keyword [C++]
ms.assetid: 81ac6e97-7bf8-496b-b3c4-fd02837573e5
ms.openlocfilehash: 674b5170dd2bba7038dfe11af906e31540acd993
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62262989"
---
# <a name="noop"></a>__noop

**Microsoft'a özgü**

`__noop` İç işlev yoksayılıp yoksayılmaması gerektiğini belirtir ve bağımsız değişken listesi ayrıştırılır ancak kod üretilmedi bağımsız değişkenleri. Değişken sayıda bağımsız değişken genel hata ayıklama işlevlerini kullanmak için tasarlanmıştır.

Derleyici dönüştürür `__noop` 0 derleme zamanında iç.

## <a name="example"></a>Örnek

Aşağıdaki kod nasıl kullanabileceğinizi gösterir `__noop`.

```
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

[Derleyici İç Bilgileri](../intrinsics/compiler-intrinsics.md)<br/>
[Anahtar Sözcükler](../cpp/keywords-cpp.md)