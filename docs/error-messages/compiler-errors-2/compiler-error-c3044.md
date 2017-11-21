---
title: "Derleyici Hatası C3044 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3044
dev_langs: C++
helpviewer_keywords: C3044
ms.assetid: 9f3e25b2-4676-49ab-97bf-6c88cd0fa377
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 313b5d1d6b0d8204d4d4716d0671e8093f4978d5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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