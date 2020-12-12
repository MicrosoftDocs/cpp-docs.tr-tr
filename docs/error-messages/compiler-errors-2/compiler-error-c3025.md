---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3025'
title: Derleyici hatası C3025
ms.date: 11/04/2016
f1_keywords:
- C3025
helpviewer_keywords:
- C3025
ms.assetid: 4442f5a3-d9ea-4873-b1fb-e7e5bd3cbe5e
ms.openlocfilehash: c674f8343791ff3ff7a4a451e3243cadd1cd55ae
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97174279"
---
# <a name="compiler-error-c3025"></a>Derleyici hatası C3025

' Clause ': tamsayı ifadesi bekleniyor

Yan tümce bir tamsayı ifadesi gerektiriyor ancak tamsayı olmayan bir ifade verdi.

## <a name="example"></a>Örnek

Aşağıdaki örnek C3025 oluşturur.

```cpp
// C3025.cpp
// compile with: /openmp /link vcomps.lib
#include <stdio.h>
#include "omp.h"

float f = 2.0F;

int main()
{
    int i = 0;

    // OK
    puts("Test with int");
    #pragma omp parallel for num_threads(i)
    for (i = 1; i <= 2; ++i)
        printf_s("Hello World - thread %d - iteration %d\n",
                 omp_get_thread_num(), i);

    puts("Test with float");
    #pragma omp parallel for num_threads(f)   // C3025
    for (i = 1; i <= 2; ++i)
        printf_s("Hello World - thread %d - iteration %d\n",
                 omp_get_thread_num(), i);
}
```
