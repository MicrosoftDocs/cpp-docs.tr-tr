---
title: Derleyici Hatası C3036
ms.date: 11/04/2016
f1_keywords:
- C3036
helpviewer_keywords:
- C3036
ms.assetid: 10c6993e-bc42-4a07-85c7-cdc34ac30906
ms.openlocfilehash: c1dc060a5d198b78e652a1b6b239655439209f66
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50613752"
---
# <a name="compiler-error-c3036"></a>Derleyici Hatası C3036

'operator': OpenMP 'reduction' yan tümcesinde geçersiz işleç belirteci

A [azaltma](../../parallel/openmp/reference/reduction.md) yan tümcesi düzgün belirtilmedi.

Aşağıdaki örnek, C3036 oluşturur:

```
// C3036.cpp
// compile with: /openmp
static float a[1000], b[1000], c[1000];
void test1(int first, int last) {
   static float dp = 0.0f;
   #pragma omp for nowait reduction(.:dp)   // C3036
   // try the following line instead
   // #pragma omp for nowait reduction(+: dp)
   for (int i = first ; i <= last ; ++i)
      dp += a[i] * b[i];
}
```