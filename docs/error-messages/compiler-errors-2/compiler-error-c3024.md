---
title: Derleyici hatası C3024
ms.date: 11/04/2016
f1_keywords:
- C3024
helpviewer_keywords:
- C3024
ms.assetid: 1c031c28-ce37-4de3-aead-cfe76b261856
ms.openlocfilehash: e344fe5eeffb32b3490b41a3d3374638cc19ba1f
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74742021"
---
# <a name="compiler-error-c3024"></a>Derleyici hatası C3024

' Schedule (Runtime) ': chunk_size ifadeye izin verilmiyor

Zamanlama yan tümcesinin çalışma zamanı parametresine bir değer geçirilemez.

Aşağıdaki örnek C3024 oluşturur:

```cpp
// C3024.cpp
// compile with: /openmp /link vcomps.lib
#include <stdio.h>
#include "omp.h"

int main() {
   int i;

   #pragma omp parallel for schedule(runtime, 10)   // C3024
   for (i = 0; i < 10; ++i) ;

   #pragma omp parallel for schedule(runtime)   // OK
   for (i = 0; i < 10; ++i) ;
}
```
