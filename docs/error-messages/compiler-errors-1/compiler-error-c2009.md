---
title: Derleyici Hatası C2009
ms.date: 11/04/2016
f1_keywords:
- C2009
helpviewer_keywords:
- C2009
ms.assetid: fe9d94ed-20a5-4d83-b9c4-60ee69d2f30a
ms.openlocfilehash: d2216b3fe990109828492fb2b2055e9425c1e306
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50638782"
---
# <a name="compiler-error-c2009"></a>Derleyici Hatası C2009

Makro biçimsel 'identifier' kullanılmasını

Makro tanımında biçimsel parametre listesinde birden fazla kez tanımlayıcısını kullanır. Tanımlayıcıları makro parametre listesinde benzersiz olması gerekir.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C2009 oluşturur:

```
// C2009.cpp
#include <stdio.h>

#define macro1(a,a) (a*a)   // C2009

int main()
{
    printf_s("%d\n", macro1(2));
}
```

## <a name="example"></a>Örnek

Olası çözüm:

```
// C2009b.cpp
#include <stdio.h>

#define macro2(a)   (a*a)
#define macro3(a,b) (a*b)

int main()
{
    printf_s("%d\n", macro2(2));
    printf_s("%d\n", macro3(2,4));
}
```