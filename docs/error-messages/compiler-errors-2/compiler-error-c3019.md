---
title: Derleyici hatası C3019
ms.date: 11/04/2016
f1_keywords:
- C3019
helpviewer_keywords:
- C3019
ms.assetid: 31a6d9b6-d29f-4499-9ad8-48dd751e87c7
ms.openlocfilehash: 5275ee6dd6680da3bf3aae0b657997f264762163
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87232046"
---
# <a name="compiler-error-c3019"></a>Derleyici hatası C3019

OpenMP ' for ' deyimindeki artış hatalı biçimde

Bir OpenMP döngüsünün artış bölümü, **`for`** işlecin sol ve sağ tarafında Dizin değişkenini kullanmalıdır.

Aşağıdaki örnek C3019 oluşturur:

```cpp
// C3019.cpp
// compile with: /openmp
int main()
{
   int i = 0, j = 1, n = 3;

   #pragma omp parallel
   {
      #pragma omp for
      for (i = 0; i < 10; i = j + n)   // C3019
      // Try the following line instead:
      // for (i = 0; i < 10; i++)
         j *= 2;
   }
}
```
