---
title: Derleyici Hatası C3016 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3016
dev_langs:
- C++
helpviewer_keywords:
- C3016
ms.assetid: 3423467e-e8bb-4f35-b4db-7925cafa74c1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d77686f669dcd767a1d79c0ac60360f1bb2aa81b
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46047557"
---
# <a name="compiler-error-c3016"></a>Derleyici Hatası C3016

'var': OpenMP 'for' deyimindeki dizin değişkeni integral türünün işaretli gerekir

Dizin değişkeni bir OpenMP `for` deyimi, imzalı bir tamsayı türü olmalıdır.

Aşağıdaki örnek, C3016 oluşturur:

```
// C3016.cpp
// compile with: /openmp
int main()
{
   #pragma omp parallel
   {
      unsigned int i = 0;
      // Try the following line instead:
      // int i = 0;

      #pragma omp for
      for (i = 0; i <= 10; ++i)   // C3016
      {
      }
   }
}
```