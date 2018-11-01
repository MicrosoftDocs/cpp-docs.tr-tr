---
title: Derleyici Hatası C3033
ms.date: 11/04/2016
f1_keywords:
- C3033
helpviewer_keywords:
- C3033
ms.assetid: 8628b6bb-a650-4ed2-af13-57acd2f7ddbb
ms.openlocfilehash: 57c2cc120a5c155d02e0e601dc2ff8924badbe67
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50460907"
---
# <a name="compiler-error-c3033"></a>Derleyici Hatası C3033

'var': 'yan tümcesi' yan tümcesindeki değişken const nitelenmiş türde olamaz

Belirli bir yan tümce için geçirilen değer olamaz `const` değişkenleri.

Aşağıdaki örnek, C3033 oluşturur:

```
// C3033.cpp
// compile with: /openmp /link vcomps.lib
int main() {
   const int val = 1;
   int val2 = 1;

   #pragma omp parallel reduction(+ : val)   // C3033
   ;

   #pragma omp parallel reduction(+ : val2)   // OK
   ;
}
```