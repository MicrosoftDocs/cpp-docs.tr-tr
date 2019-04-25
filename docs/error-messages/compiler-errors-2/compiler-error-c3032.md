---
title: Derleyici Hatası C3032
ms.date: 11/04/2016
f1_keywords:
- C3032
helpviewer_keywords:
- C3032
ms.assetid: 6a92bd8e-319f-4a99-aef4-a9021f6f9928
ms.openlocfilehash: 8e103d36bf3e49cfbb0a3724c044794601aabcee
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62256847"
---
# <a name="compiler-error-c3032"></a>Derleyici Hatası C3032

'var': 'yan tümcesi' yan tümcesindeki değişken 'type' eksik türe sahip olamaz

Belirli bir yan tümce için geçirilen türler derleyici için tümüyle görünür olmalıdır.

Aşağıdaki örnek, C3032 oluşturur:

```
// C3032.cpp
// compile with: /openmp /link vcomps.lib
#include "omp.h"

struct Incomplete;
extern struct Incomplete inc;

int main() {
   int i = 9;
   #pragma omp parallel private(inc)   // C3032
      ;

   #pragma omp parallel private(i)     // OK
      ;

}
```