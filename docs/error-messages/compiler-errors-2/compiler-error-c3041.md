---
title: Derleyici Hatası C3041
ms.date: 11/04/2016
f1_keywords:
- C3041
helpviewer_keywords:
- C3041
ms.assetid: 9df1ae44-3ac7-4c6c-899f-f35ffe7ccf0d
ms.openlocfilehash: 43f75e9d054f574eb121d20eb35d302cef849566
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50479137"
---
# <a name="compiler-error-c3041"></a>Derleyici Hatası C3041

'var': 'copyprivate' yan tümcesindeki değişken kapsayan bağlamda özel olmalıdır

Bir değişken geçirilen [copyprivate](../../parallel/openmp/reference/copyprivate.md) kapsayan bağlamda paylaşılamaz.

Aşağıdaki örnek, C3041 oluşturur:

```
// C3041.cpp
// compile with: /openmp /c
#include "omp.h"
double d;
int main() {
   #pragma omp parallel shared(d)
   // try the following line instead
   // #pragma omp parallel private(d)
   {
      // or don't make d copyprivate
      #pragma omp single copyprivate(d)   // C3041
      {
      }
   }
}
```