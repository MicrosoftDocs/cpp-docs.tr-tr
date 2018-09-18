---
title: Derleyici Hatası C3040 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3040
dev_langs:
- C++
helpviewer_keywords:
- C3040
ms.assetid: 29e857ac-74f0-4ec6-becf-9026e38c160e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 419178a7ff71817c418aa791ae1f6cce116cd986
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46057700"
---
# <a name="compiler-error-c3040"></a>Derleyici Hatası C3040

'var': 'reduction' yan tümcesindeki değişkenin türü 'operator' azaltma işleciyle uyumsuz

Bir değişkende bir [azaltma](../../parallel/openmp/reference/reduction.md) azaltma işleciyle yan tümcesi kullanılamaz.

Aşağıdaki örnek, C3040 oluşturur:

```
// C3040.cpp
// compile with: /openmp /c
#include "omp.h"
double d;

int main() {
   #pragma omp parallel reduction(&:d)   // C3040
      ;

   #pragma omp parallel reduction(-:d)  // OK
      ;
}
```