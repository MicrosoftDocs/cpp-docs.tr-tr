---
title: Derleyici Hatası C3046 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3046
dev_langs:
- C++
helpviewer_keywords:
- C3046
ms.assetid: 2e53d835-faa1-4ec0-9807-41f3dc552635
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c2cd4ab2d1b0e85a33ba2e01d4c2115f0084e98a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46070324"
---
# <a name="compiler-error-c3046"></a>Derleyici Hatası C3046

Bir OpenMP '#pragma omp sections' bölgesinde yapısal blok eksik

A [bölümleri](../../parallel/openmp/reference/sections-openmp.md) yönergesi, bir boş bir kod bloğu içeriyor.

Aşağıdaki örnek, C3046 oluşturur:

```
// C3046.cpp
// compile with: /openmp /c
#include "omp.h"

int main() {
   int n2 = 2, n3 = 3;

   #pragma omp parallel
   {
      ++n2;

      #pragma omp sections
      {
/*
         ++n2;

         #pragma omp section
         {
            ++n3;
         }
*/
       }   // C3046 uncomment code to resolve this C3046
   }
}
```