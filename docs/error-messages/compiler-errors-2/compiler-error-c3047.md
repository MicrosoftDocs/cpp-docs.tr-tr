---
title: "Derleyici Hatası C3047 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3047
dev_langs: C++
helpviewer_keywords: C3047
ms.assetid: 91c14566-5958-433d-8549-0e8bc3196f76
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 5d2133330ab45eb4667c100cde9495e54eec15e7
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3047"></a>Derleyici Hatası C3047
'Bölüm' bölge '#pragma omp bölümü tarafından' gelmelidir OpenMP yapılandırılmış bloğunda  
  
 Tüm kod tarafından sunulan bir kod bloğu içinde bir [bölümleri](../../parallel/openmp/reference/sections-openmp.md) yönergesi tarafından sunulan bir kod bloğu olmalıdır bir `section` yönergesi.  
  
 Aşağıdaki örnek C3047 oluşturur:  
  
```  
// C3047.cpp  
// compile with: /openmp /c  
#include "omp.h"  
  
int main() {  
   int n2 = 2, n3 = 3;  
  
   #pragma omp parallel  
   {  
      ++n2;  
  
      #pragma omp sections  
      {  
  
         #pragma omp section  
         {  
            ++n3;  
         }  
  
         ++n2;   // C3047 not enclosed in #pragma omp section  
      }  
   }  
}  
```