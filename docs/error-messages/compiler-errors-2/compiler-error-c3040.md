---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3040'
title: Derleyici hatası C3040
ms.date: 11/04/2016
f1_keywords:
- C3040
helpviewer_keywords:
- C3040
ms.assetid: 29e857ac-74f0-4ec6-becf-9026e38c160e
ms.openlocfilehash: e43f7e6e63d7ec2462247a9846febd4c0b4eab4a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97269945"
---
# <a name="compiler-error-c3040"></a>Derleyici hatası C3040

' var ': ' azaltma ' yan tümcesindeki değişkenin türü ' operator ' azaltma işleci ile uyumsuz

[Azaltma](../../parallel/openmp/reference/openmp-clauses.md#reduction) yan tümcesindeki bir değişken, azaltma işleci ile kullanılamaz.

Aşağıdaki örnek C3040 oluşturur:

```cpp
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
