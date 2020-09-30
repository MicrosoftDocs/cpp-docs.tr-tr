---
title: Derleyici hatası C3047
ms.date: 11/04/2016
f1_keywords:
- C3047
helpviewer_keywords:
- C3047
ms.assetid: 91c14566-5958-433d-8549-0e8bc3196f76
ms.openlocfilehash: 41312e09996e2fe007cdc13c0369b5154e720841
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2020
ms.locfileid: "91506211"
---
# <a name="compiler-error-c3047"></a>Derleyici hatası C3047

Bir OpenMP ' sections ' bölgesindeki yapısal bloktan önce ' #pragma omp Section ' gelmelidir

Bir [bölüm](../../parallel/openmp/reference/openmp-directives.md#sections-openmp) yönergesi tarafından tanıtılan kod bloğundaki herhangi bir kod, bir yönerge tarafından tanıtılan kod bloğunda olmalıdır `section` .

Aşağıdaki örnek C3047 oluşturur:

```cpp
// C3047.cpp
// compile with: /openmp /c
#include "omp.h"

int main() {
   int n2 = 2, n3 = 3;

   #pragma omp parallel
   {
      ++n2;

      #pragma omp sections
      {

         #pragma omp section
         {
            ++n3;
         }

         ++n2;   // C3047 not enclosed in #pragma omp section
      }
   }
}
```
