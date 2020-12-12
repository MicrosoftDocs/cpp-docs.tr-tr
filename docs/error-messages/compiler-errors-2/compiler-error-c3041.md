---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3041'
title: Derleyici hatası C3041
ms.date: 11/04/2016
f1_keywords:
- C3041
helpviewer_keywords:
- C3041
ms.assetid: 9df1ae44-3ac7-4c6c-899f-f35ffe7ccf0d
ms.openlocfilehash: ce4a0b1dbbcc0dc83b84c25afd4acf43fa0af687
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97269944"
---
# <a name="compiler-error-c3041"></a>Derleyici hatası C3041

' var ': ' copyprivate ' yan tümcesindeki değişken kapsayan bağlamda özel olmalıdır

[Copyprivate](../../parallel/openmp/reference/openmp-clauses.md#copyprivate) öğesine geçirilen değişken kapsayan bağlamda paylaşılamaz.

Aşağıdaki örnek C3041 oluşturur:

```cpp
// C3041.cpp
// compile with: /openmp /c
#include "omp.h"
double d;
int main() {
   #pragma omp parallel shared(d)
   // try the following line instead
   // #pragma omp parallel private(d)
   {
      // or don't make d copyprivate
      #pragma omp single copyprivate(d)   // C3041
      {
      }
   }
}
```
