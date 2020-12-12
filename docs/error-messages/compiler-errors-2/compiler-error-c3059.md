---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3059'
title: Derleyici hatası C3059
ms.date: 11/04/2016
f1_keywords:
- C3059
helpviewer_keywords:
- C3059
ms.assetid: 57220324-8286-4cab-a1ab-45385eb1eae0
ms.openlocfilehash: 82629fb77a0cf589f4e311d951fcf1540e0b7c8f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97281762"
---
# <a name="compiler-error-c3059"></a>Derleyici hatası C3059

' var ': ' threadprivate ' simgesi ' Clause ' yan tümcesinde kullanılamaz

Bir [threadprivate](../../parallel/openmp/reference/openmp-directives.md#threadprivate) simgesi bir yan tümcesinde kullanıldı.

Aşağıdaki örnek C3059 oluşturur:

```cpp
// C3059.cpp
// compile with: /openmp
#include "omp.h"
int x, y;
#pragma omp threadprivate(x, y)

int main() {
   #pragma omp parallel private(x, y)   // C3059
   {
      x = y;
   }
}
```

Olası çözüm:

```cpp
// C3059b.cpp
// compile with: /openmp
#include "omp.h"
int x = 0, y = 0;

int main() {
   #pragma omp parallel firstprivate(y) private(x)
   {
      x = y;
   }
}
```
