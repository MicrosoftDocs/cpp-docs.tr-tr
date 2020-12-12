---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3019'
title: Derleyici hatası C3019
ms.date: 11/04/2016
f1_keywords:
- C3019
helpviewer_keywords:
- C3019
ms.assetid: 31a6d9b6-d29f-4499-9ad8-48dd751e87c7
ms.openlocfilehash: d2f07eabdbe0694e2c227cace26ac81f3a5dc237
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97285792"
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
