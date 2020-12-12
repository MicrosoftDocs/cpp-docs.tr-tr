---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3018'
title: Derleyici hatası C3018
ms.date: 11/04/2016
f1_keywords:
- C3018
helpviewer_keywords:
- C3018
ms.assetid: 685be45f-f116-43a8-a88d-05ab6616e2f1
ms.openlocfilehash: cb2b144a09edc4dbe64f4940e476cca0f73c585b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97285831"
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
