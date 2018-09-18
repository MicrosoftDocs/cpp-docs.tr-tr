---
title: Derleyici Hatası C3042 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3042
dev_langs:
- C++
helpviewer_keywords:
- C3042
ms.assetid: bf73f61e-5bd2-40a8-9b06-6244e6a15a41
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 36fde6251244582a0626c80aa673ed6dd0e559d2
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46045242"
---
# <a name="compiler-error-c3042"></a>Derleyici Hatası C3042

'copyprivate' ve 'nowait' yan tümceleri OpenMP 'yönergesi' yönergesinde birlikte görünemez

[Copyprivate](../../parallel/openmp/reference/copyprivate.md) ve [nowait](../../parallel/openmp/reference/nowait.md) yan tümceleri belirtilen yönergesinde karşılıklı olarak birbirini dışlar. Bu hatayı düzeltmek için aşağıdakilerden birini veya her ikisini de kaldırın `copyprivate` veya `nowait` yan tümceleri.

Aşağıdaki örnek, C3042 oluşturur:

```
// C3042.cpp
// compile with: /openmp /c
#include <stdio.h>
#include "omp.h"

double d;

int main() {
    #pragma omp parallel private(d)
   {
      #pragma omp single copyprivate(d) nowait   // C3042
      {
      }
   }
}
```