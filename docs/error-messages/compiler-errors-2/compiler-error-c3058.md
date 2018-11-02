---
title: Derleyici Hatası C3058
ms.date: 11/04/2016
f1_keywords:
- C3058
helpviewer_keywords:
- C3058
ms.assetid: 669d08c8-0b58-4351-88aa-c6e6e1af481c
ms.openlocfilehash: 5655fe8ebeb8f1b61d7acbba5313c2e3ab2a2b4c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50547244"
---
# <a name="compiler-error-c3058"></a>Derleyici Hatası C3058

'symbol': simge 'copyin'yan içinde kullanılmadan önce 'threadprivate' olarak bildirilmedi

Bir sembol önce bildirilmelidir [threadprivate](../../parallel/openmp/reference/threadprivate.md) içinde kullanılmadan önce bir [copyin](../../parallel/openmp/reference/copyin.md) yan tümcesi.

Aşağıdaki örnek, C3058 oluşturur:

```
// C3058.cpp
// compile with: /openmp
int x, y, z;
#pragma omp threadprivate(x, z)

void test() {
   #pragma omp parallel copyin(x, y)   // C3058
   {
   }
}
```

Olası çözüm:

```
// C3058b.cpp
// compile with: /openmp /LD
int x, y, z;
#pragma omp threadprivate(x, y)

void test() {
   #pragma omp parallel copyin(x, y)
   {
   }
}
```