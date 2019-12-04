---
title: Derleyici hatası C3021
ms.date: 11/04/2016
f1_keywords:
- C3021
helpviewer_keywords:
- C3021
ms.assetid: 0cef6d97-e267-438a-ac8b-0daf5bbbc2cf
ms.openlocfilehash: 9a90a3378690140c27fe938c269f4fb00f6eae12
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74742112"
---
# <a name="compiler-error-c3021"></a>Derleyici hatası C3021

' arg ': OpenMP yönergesinde ' Directive ' üzerinde bağımsız değişken boş

Bir OpenMP yönergesi için bağımsız değişken gereklidir.

## <a name="example"></a>Örnek

Aşağıdaki örnek C3021 oluşturur:

```cpp
// C3021.cpp
// compile with: /openmp
#include <stdio.h>
#include "omp.h"

int g = 0;

int main()
{
    int x, y, i;

    #pragma omp parallel for schedule(static,)   // C3021
    for (i = 0; i < 10; ++i) ;

    #pragma omp parallel for schedule()   // C3021
    for (i = 0; i < 10; ++i)
        printf_s("Hello world, thread %d, iteration %d\n",
                 omp_get_thread_num(), i);

    #pragma omp parallel reduction()   // C3021
      ;

    #pragma omp parallel reduction(+ :)   // C3021
      ;

    //
    // The following shows correct syntax examples.
    //
    #pragma omp parallel reduction(+ : x, y)
      ;

    #pragma omp parallel reduction(* : x, y)
      ;

    #pragma omp parallel reduction(- : x, y)
      ;

    #pragma omp parallel reduction(& : x, y)
      ;

    #pragma omp parallel reduction(^ : x, y)
      ;

    #pragma omp parallel reduction(| : x, y)
      ;

    #pragma omp parallel reduction(&& : x, y)
      ;

    #pragma omp parallel reduction(|| : x, y)
      ;
}
```
