---
title: Derleyici Hatası C3019
ms.date: 11/04/2016
f1_keywords:
- C3019
helpviewer_keywords:
- C3019
ms.assetid: 31a6d9b6-d29f-4499-9ad8-48dd751e87c7
ms.openlocfilehash: bba90917614cbc8facb182659c288f9823d8ab45
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50432561"
---
# <a name="compiler-error-c3019"></a>Derleyici Hatası C3019

OpenMP 'for' deyimindeki artış hatalı biçimde

Bir OpenMP artırma parçası `for` hem sol ve sağ tarafındaki dizin değişkeni döngü kullanması gerekir.

Aşağıdaki örnek, C3019 oluşturur:

```
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