---
title: Derleyici Hatası C3029
ms.date: 11/04/2016
f1_keywords:
- C3029
helpviewer_keywords:
- C3029
ms.assetid: 655eb04d-504a-468d-8c0c-bda1e5f297b7
ms.openlocfilehash: a003a0b8fcba3609c355ae467a11b4024a0529d5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50658386"
---
# <a name="compiler-error-c3029"></a>Derleyici Hatası C3029

'symbol': yalnızca bir kez veri paylaşımı içinde görünebilir yan tümceleri OpenMP yönergesi

Bir sembol, bir yönergesi bir veya daha fazla yan tümceleri içinde birden çok kez kullanıldı. Simgenin yönergesinde yalnızca bir kez kullanılabilir.

Aşağıdaki örnek, C3029 oluşturur:

```
// C3029.cpp
// compile with: /openmp /link vcomps.lib
#include "omp.h"

int g_i;

int main() {
   int i, x;

   #pragma omp parallel reduction(+ : x, x)   // C3029
      ;

   #pragma omp parallel reduction(+ : x)   // OK
      ;

   #pragma omp parallel private(x) reduction(+ : x)   // C3029
      ;

   #pragma omp parallel reduction(+ : x)   // OK
      ;
}
```