---
title: Derleyici Uyarısı (düzey 4) C4668
ms.date: 11/04/2016
f1_keywords:
- C4668
helpviewer_keywords:
- C4668
ms.assetid: c6585460-bc4a-4a15-9242-4cbfce53c961
ms.openlocfilehash: 11d96941a1efddde87068af8829e24259f2fa312
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50529980"
---
# <a name="compiler-warning-level-4-c4668"></a>Derleyici Uyarısı (düzey 4) C4668

'symbol' önişlemci makrosu olarak tanımlanmamış, 'directives' için '0' ile değiştiriliyor

Bir sembol tanımlı değil, bir önişlemci yönergesi ile kullanıldı. Simgenin false olarak değerlendirir. Simge tanımlamak için kullanabilirsiniz [#define yönergesi](../../preprocessor/hash-define-directive-c-cpp.md) veya [/D](../../build/reference/d-preprocessor-definitions.md) derleyici seçeneği.

Varsayılan olarak bu uyarıyı kapalıdır. Bkz: [derleyici uyarıları emin olan kapalı varsayılan](../../preprocessor/compiler-warnings-that-are-off-by-default.md) daha fazla bilgi için.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C4668 oluşturur:

```
// C4668.cpp
// compile with: /W4
#include <stdio.h>

#pragma warning (default : 4668)   // turn warning on

int main()
{
    #if q   // C4668, q is not defined
        printf_s("defined");
    #else
        printf_s("undefined");
    #endif
}
```