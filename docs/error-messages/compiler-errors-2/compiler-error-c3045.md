---
title: Derleyici hatası C3045
ms.date: 11/04/2016
f1_keywords:
- C3045
helpviewer_keywords:
- C3045
ms.assetid: 9351ba3e-3d3f-455f-ac90-a810fa9fd947
ms.openlocfilehash: fc5c2b526133ea0de70d11c3a01269436701de79
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2020
ms.locfileid: "91506287"
---
# <a name="compiler-error-c3045"></a>Derleyici hatası C3045

OpenMP ' sections ' yönergesinden sonra bileşik bir ifade bekleniyor. ' {' Eksik

Küme ayraçları ile ayrılmış bir kod bloğu, bir [bölüm](../../parallel/openmp/reference/openmp-directives.md#sections-openmp) yönergesini izlemelidir.

Aşağıdaki örnek C3045 oluşturur:

```cpp
// C3045.cpp
// compile with: /openmp /c
#include "omp.h"

int main() {
   int n2 = 2, n3 = 3;

   #pragma omp parallel
   {
      ++n2;

      #pragma omp sections
         ++n2;   // C3045

      #pragma omp sections   // OK
      {
         ++n3;
      }
   }
}
```
