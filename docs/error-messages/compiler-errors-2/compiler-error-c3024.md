---
title: Derleyici Hatası C3024
ms.date: 11/04/2016
f1_keywords:
- C3024
helpviewer_keywords:
- C3024
ms.assetid: 1c031c28-ce37-4de3-aead-cfe76b261856
ms.openlocfilehash: 46a7385f530742c19c9c586be7a932d0e054b7d4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62360092"
---
# <a name="compiler-error-c3024"></a>Derleyici Hatası C3024

'schedule(runtime)': chunk_size ifadesine izin verilmez

Zamanlama yan tümcesinin çalışma zamanı parametresi için bir değer geçirilemez.

Aşağıdaki örnek, C3024 oluşturur:

```
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