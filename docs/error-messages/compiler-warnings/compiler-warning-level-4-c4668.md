---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 4) C4668'
title: Derleyici Uyarısı (düzey 4) C4668
ms.date: 11/04/2016
f1_keywords:
- C4668
helpviewer_keywords:
- C4668
ms.assetid: c6585460-bc4a-4a15-9242-4cbfce53c961
ms.openlocfilehash: 559043027bf9fab38470223ea7735ca70297aabf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97134062"
---
# <a name="compiler-warning-level-4-c4668"></a>Derleyici Uyarısı (düzey 4) C4668

'symbol' önişlemci makrosu olarak tanımlanmamış, 'directives' için '0' ile değiştiriliyor

Tanımlanmamış bir sembol, Önişlemci yönergesiyle kullanıldı. Sembol yanlış olarak değerlendirilir. Bir sembol tanımlamak için [#define Directive](../../preprocessor/hash-define-directive-c-cpp.md) ya da [/d](../../build/reference/d-preprocessor-definitions.md) derleyici seçeneğini kullanabilirsiniz.

Bu uyarı varsayılan olarak kapalıdır. Daha fazla bilgi için bkz. [Varsayılan olarak kapalı olan Derleyici uyarıları](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .

## <a name="example"></a>Örnek

Aşağıdaki örnek C4668 oluşturur:

```cpp
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
