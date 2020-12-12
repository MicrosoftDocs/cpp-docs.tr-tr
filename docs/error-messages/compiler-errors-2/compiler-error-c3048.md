---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3048'
title: Derleyici hatası C3048
ms.date: 11/04/2016
f1_keywords:
- C3048
helpviewer_keywords:
- C3048
ms.assetid: 48e07091-94d9-471d-befe-7e2507631edd
ms.openlocfilehash: 68ad1ac216a08c8a1851ecb5e25e4201ae787da4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97269802"
---
# <a name="compiler-error-c3048"></a>Derleyici hatası C3048

' #Pragma omp atomik ' takip eden ifade yanlış biçimde

Atomik yönerge yanlış belirtildi.

Aşağıdaki örnek C3048 oluşturur:

```cpp
// C3048.cpp
// compile with: /openmp vcomps.lib
#include "omp.h"
#include <stdio.h>

int main() {
   int a[10];
   omp_set_num_threads(4);
   #pragma omp parallel
   {
      #pragma omp atomic
      a[0] = 1;   // C3048
      // try the following line instead
      // a[0] += 1;
   }
}
```
