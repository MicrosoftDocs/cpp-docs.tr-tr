---
title: Derleyici hatası C3053
ms.date: 11/04/2016
f1_keywords:
- C3053
helpviewer_keywords:
- C3053
ms.assetid: ab9a25f3-e341-4f6e-8e69-069b4a963a64
ms.openlocfilehash: 8889388dc07f871bb60de44d317f9c8882795b03
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2020
ms.locfileid: "91506187"
---
# <a name="compiler-error-c3053"></a>Derleyici hatası C3053

' symbol ': ' threadprivate ' yalnızca genel veya statik veri öğeleri için geçerlidir

[Threadprivate](../../parallel/openmp/reference/openmp-directives.md#threadprivate) öğesine geçirilen semboller genel ya da statik olmalıdır.

Aşağıdaki örnek C3053 oluşturur:

```cpp
// C3053.cpp
// compile with: /openmp
void Test() {
   int x, y;
   #pragma omp threadprivate(x, y)   // C3053
   #pragma omp parallel copyin(x, y)
   {
      x = y;
   }
}
```

Olası çözüm:

```cpp
// C3053b.cpp
// compile with: /openmp /LD
int x, y;
#pragma omp threadprivate(x, y)

void Test() {
   #pragma omp parallel copyin(x, y)
   {
      x = y;
   }
}
```
