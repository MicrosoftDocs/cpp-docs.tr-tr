---
title: Derleyici Hatası C3016
ms.date: 11/04/2016
f1_keywords:
- C3016
helpviewer_keywords:
- C3016
ms.assetid: 3423467e-e8bb-4f35-b4db-7925cafa74c1
ms.openlocfilehash: edb83c210ca7e3f6c648522b893e9ed90cea1874
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50479658"
---
# <a name="compiler-error-c3016"></a>Derleyici Hatası C3016

'var': OpenMP 'for' deyimindeki dizin değişkeni integral türünün işaretli gerekir

Dizin değişkeni bir OpenMP `for` deyimi, imzalı bir tamsayı türü olmalıdır.

Aşağıdaki örnek, C3016 oluşturur:

```
// C3016.cpp
// compile with: /openmp
int main()
{
   #pragma omp parallel
   {
      unsigned int i = 0;
      // Try the following line instead:
      // int i = 0;

      #pragma omp for
      for (i = 0; i <= 10; ++i)   // C3016
      {
      }
   }
}
```