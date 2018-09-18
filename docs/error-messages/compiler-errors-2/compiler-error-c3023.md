---
title: Derleyici Hatası C3023 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3023
dev_langs:
- C++
helpviewer_keywords:
- C3023
ms.assetid: 89dcce98-3cd7-4931-a50f-87df1d2ebc9b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3941af133d03b3cc4eae11785b8f870e8058809f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46026068"
---
# <a name="compiler-error-c3023"></a>Derleyici Hatası C3023

'value': OpenMP 'yan tümcesi' yan tümcesinin bağımsız değişkeninde karşılaştı beklenmeyen belirteç

Bir yan tümce için geçirilen değer geçerli değil.

Aşağıdaki örnek, C3023 oluşturur:

```
// C3023.cpp
// compile with: /openmp /link vcomps.lib
#include <stdio.h>
#include "omp.h"

int main() {
   int i;

   #pragma omp parallel for schedule(dynamic 10)   // C3023
   for (i = 0; i < 10; ++i) ;

   #pragma omp parallel for schedule(dynamic;10)   // C3023
   for (i = 0; i < 10; ++i) ;

   // OK
   #pragma omp parallel for schedule(dynamic, 10)
   for (i = 0; i < 10; ++i)
   ;
}
```