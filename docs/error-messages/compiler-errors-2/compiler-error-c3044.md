---
title: Derleyici Hatası C3044 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3044
dev_langs:
- C++
helpviewer_keywords:
- C3044
ms.assetid: 9f3e25b2-4676-49ab-97bf-6c88cd0fa377
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 61021438711544bb9e6489855f8bcb46a867a1d4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3044"></a>Derleyici Hatası C3044
'bölüm': yalnızca doğrudan bir OpenMP 'bölüm' yönergesi altında iç içe geçmiş  
  
 Bulunan derleyici bir `section` yönergesi yanlış kullanıldı. Daha fazla bilgi için bkz: [bölümleri](../../parallel/openmp/reference/sections-openmp.md).  
  
 Aşağıdaki örnek C3044 oluşturur:  
  
```  
// C3044.cpp  
// compile with: /openmp /c  
#include "omp.h"  
int main() {  
   int n2 = 2, n3 = 3;  
  
   #pragma omp parallel  
   {  
      ++n2;  
  
      #pragma omp sections  
      {  
         ++n2;  
      }  
  
      #pragma omp section   // C3044  
      {  
         ++n3;  
      }  
   }  
  
   #pragma omp parallel  
   {  
      ++n2;  
  
      #pragma omp sections  
      {  
         #pragma omp section   // OK  
         {  
            ++n3;  
         }  
      }  
   }  
}  
```