---
title: Derleyici Uyarısı (düzey 4) C4938
ms.date: 11/04/2016
f1_keywords:
- C4938
helpviewer_keywords:
- C4938
ms.assetid: 6acac81a-9d23-465e-b700-ed4b6e8edcd0
ms.openlocfilehash: da2725a398a99b5943e128038e75622115a9e34f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62280210"
---
# <a name="compiler-warning-level-4-c4938"></a>Derleyici Uyarısı (düzey 4) C4938

'var': Kayan nokta azaltma değişkeni, / FP altında tutarsız sonuçlara neden olabilir: strict veya #pragma fenv_access

Kullanmamalısınız [/FP: strict](../../build/reference/fp-specify-floating-point-behavior.md) veya [fenv_access](../../preprocessor/fenv-access.md) OpenMP kayan nokta indirimleri ile toplamı farklı bir sırada hesaplandığından. Bu nedenle, sonuçları/OpenMP olmadan sonuçlarından farklı olabilir.

Aşağıdaki örnek, C4938 oluşturur:

```
// C4938.cpp
// compile with: /openmp /W4 /fp:strict /c
// #pragma fenv_access(on)
extern double *a;

double test(int first, int last) {
   double sum = 0.0;
   #pragma omp parallel for reduction(+: sum)   // C4938
   for (int i = first ; i <= last ; ++i)
      sum += a[i];
   return sum;
}
```

Açık paralelleştirme toplamı şu şekilde hesaplanır:

```
sum = a[first] + a[first + 1] + ... + a[last];
```

Açık paralelleştirme (ve iki iş parçacığı) ile toplam şu şekilde hesaplanır:

```
sum1 = a[first] + ... a[first + last / 2];
sum2 = a[(first + last / 2) + 1] + ... a[last];
sum = sum1 + sum2;
```