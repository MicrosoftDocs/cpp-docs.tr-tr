---
title: Derleyici hatası C3043
ms.date: 11/04/2016
f1_keywords:
- C3043
helpviewer_keywords:
- C3043
ms.assetid: 0ef55e63-e82b-48eb-9d44-690950ac34c6
ms.openlocfilehash: 95f11f50ad263b716694014753956a46fa9d1751
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74761383"
---
# <a name="compiler-error-c3043"></a>Derleyici hatası C3043

OpenMP ' Critical ' yönergesi aynı ada sahip ' Critical ' yönergesinde iç içe geçirilemez

[Kritik](../../parallel/openmp/reference/critical.md) yönerge aynı adı kullanan bir `critical` yönergesinde iç içe geçirilemez.

Aşağıdaki örnek C3043 oluşturur:

```cpp
// C3043.cpp
// compile with: /openmp /c
#include "omp.h"

int main() {
   int n1 = 1, n2 = 2, n3 = 3;

   #pragma omp parallel
   {
      ++n2;

      #pragma omp critical(MyTest)
      {
         ++n2;

         #pragma omp critical(MyTest)   // C3043
         // try the following line instead
         // #pragma omp critical(MyTest2)
         {
            ++n3;
         }
      }
   }
}
```
