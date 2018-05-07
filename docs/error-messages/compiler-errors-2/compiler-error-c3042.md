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
ms.openlocfilehash: 32d2f88702bb3c1c2439dd2931ee269c9c1413ae
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3042"></a>Derleyici Hatası C3042
'copyprivate' ve 'nowait' yan tümceleri üzerinde OpenMP 'yönergesi' yönergesi birlikte bulunamaz  
  
 [Copyprivate](../../parallel/openmp/reference/copyprivate.md) ve [nowait](../../parallel/openmp/reference/nowait.md) yan tümceleri üzerinde belirtilen yönergesi karşılıklı olarak birbirini dışlar. Bu hatayı düzeltmek için aşağıdakilerden birini veya her ikisini de kaldırmak `copyprivate` veya `nowait` yan tümceleri.  
  
 Aşağıdaki örnek C3042 oluşturur:  
  
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