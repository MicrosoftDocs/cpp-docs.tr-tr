---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 4) C4938'
title: Derleyici Uyarısı (düzey 4) C4938
ms.date: 11/04/2016
f1_keywords:
- C4938
helpviewer_keywords:
- C4938
ms.assetid: 6acac81a-9d23-465e-b700-ed4b6e8edcd0
ms.openlocfilehash: 3b327581b0eb790e74d6fddc2bca1e027f40d89e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97234598"
---
# <a name="compiler-warning-level-4-c4938"></a>Derleyici Uyarısı (düzey 4) C4938

' var ': kayan nokta azaltma değişkeni,/fp: Strict veya #pragma altında tutarsız sonuçlara neden olabilir fenv_access

Toplam farklı bir düzende hesaplandığından, [/FP: Strict](../../build/reference/fp-specify-floating-point-behavior.md) veya [fenv_access](../../preprocessor/fenv-access.md) OpenMP kayan nokta indirimleriyle birlikte kullanmamalısınız. Bu nedenle, sonuçlar/openmpno olmadan sonuçlardan farklı olabilir.

Aşağıdaki örnek C4938 oluşturur:

```cpp
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

Açık paralelleştirme olmadan, toplam aşağıdaki gibi hesaplanır:

```
sum = a[first] + a[first + 1] + ... + a[last];
```

Açık paralelleştirme (ve iki iş parçacığı) ile toplam, aşağıdaki gibi hesaplanır:

```
sum1 = a[first] + ... a[first + last / 2];
sum2 = a[(first + last / 2) + 1] + ... a[last];
sum = sum1 + sum2;
```
