---
title: Derleyici hatası C3018
ms.date: 11/04/2016
f1_keywords:
- C3018
helpviewer_keywords:
- C3018
ms.assetid: 685be45f-f116-43a8-a88d-05ab6616e2f1
ms.openlocfilehash: 137d09cb510a27a495c91b343a56dd11b41b42b5
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87232059"
---
# <a name="compiler-error-c3018"></a>Derleyici hatası C3018

' var1 ': OpenMP ' for ' test veya Increment ' var2 ' Dizin değişkenini kullanmalıdır

**`for`** Bir OpenMP deyimindeki bir döngü, testi için aynı değişkeni kullanmalıdır, çünkü kendi dizini için kullanır.

Aşağıdaki örnek C3018 oluşturur:

```cpp
// C3018.cpp
// compile with: /openmp
int main()
{
   int i = 0, j = 5;

   #pragma omp parallel
   {
      #pragma omp for
      for (i = 0; j < 10; ++i)   // C3018
      // try the following line instead
      // for (i = 0; i < 10; ++i)
         j *= 2;

      #pragma omp for
      for (i = 0; i < 10; j = j + i)   // C3018
      // try the following line instead
      // for (i = 0; i < 10; i = j + i)
         j *= 2;
   }
}
```
