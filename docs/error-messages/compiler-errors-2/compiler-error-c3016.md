---
title: Derleyici hatası C3016
ms.date: 11/04/2016
f1_keywords:
- C3016
helpviewer_keywords:
- C3016
ms.assetid: 3423467e-e8bb-4f35-b4db-7925cafa74c1
ms.openlocfilehash: ea552a987863207e708d3fd98bc64b1e99a34b51
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74742242"
---
# <a name="compiler-error-c3016"></a>Derleyici hatası C3016

' var ': OpenMP ' for ' deyimindeki dizin değişkeni işaretli tam sayı türünde olmalıdır

Bir OpenMP `for` deyimindeki dizin değişkeni işaretli bir integral türü olmalıdır.

Aşağıdaki örnek C3016 oluşturur:

```cpp
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
