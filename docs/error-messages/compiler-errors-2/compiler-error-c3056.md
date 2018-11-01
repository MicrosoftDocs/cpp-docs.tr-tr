---
title: Derleyici Hatası C3056
ms.date: 11/04/2016
f1_keywords:
- C3056
helpviewer_keywords:
- C3056
ms.assetid: 9500173d-870b-49b3-8e88-0ee93586d19a
ms.openlocfilehash: d33aa6679c6dc68b7f1a62e75aff6fadc65dc7bd
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50447417"
---
# <a name="compiler-error-c3056"></a>Derleyici Hatası C3056

'symbol': simge değil 'threadprivate' yönergesiyle aynı kapsamda

Kullanılan bir sembolü bir [threadprivate](../../parallel/openmp/reference/threadprivate.md) yan tümcesi, aynı kapsamda olmalıdır `threadprivate` yan tümcesi.

Aşağıdaki örnek, C3056 oluşturur:

```
// C3056.cpp
// compile with: /openmp
int x, y;
void test() {
   #pragma omp threadprivate(x, y)   // C3056
   #pragma omp parallel copyin(x, y)
   {
      x = y;
   }
}
```

Olası çözüm:

```
// C3056b.cpp
// compile with: /openmp /LD
int x, y;
#pragma omp threadprivate(x, y)
void test() {
   #pragma omp parallel copyin(x, y)
   {
      x = y;
   }
}
```