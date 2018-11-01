---
title: Derleyici Hatası C3042
ms.date: 11/04/2016
f1_keywords:
- C3042
helpviewer_keywords:
- C3042
ms.assetid: bf73f61e-5bd2-40a8-9b06-6244e6a15a41
ms.openlocfilehash: deb3b8d6251316bceb71ce03f2bda88520bbb9b3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50626804"
---
# <a name="compiler-error-c3042"></a>Derleyici Hatası C3042

'copyprivate' ve 'nowait' yan tümceleri OpenMP 'yönergesi' yönergesinde birlikte görünemez

[Copyprivate](../../parallel/openmp/reference/copyprivate.md) ve [nowait](../../parallel/openmp/reference/nowait.md) yan tümceleri belirtilen yönergesinde karşılıklı olarak birbirini dışlar. Bu hatayı düzeltmek için aşağıdakilerden birini veya her ikisini de kaldırın `copyprivate` veya `nowait` yan tümceleri.

Aşağıdaki örnek, C3042 oluşturur:

```
// C3042.cpp
// compile with: /openmp /c
#include <stdio.h>
#include "omp.h"

double d;

int main() {
    #pragma omp parallel private(d)
   {
      #pragma omp single copyprivate(d) nowait   // C3042
      {
      }
   }
}
```