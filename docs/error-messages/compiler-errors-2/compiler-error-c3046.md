---
title: "Derleyici Hatası C3046 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3046
dev_langs: C++
helpviewer_keywords: C3046
ms.assetid: 2e53d835-faa1-4ec0-9807-41f3dc552635
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: faeb97b8588731340bc40dfbd53a64fe7e96a77c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3046"></a>Derleyici Hatası C3046
OpenMP '#pragma omp bölümler' bölgede yapılandırılmış blok eksik  
  
 A [bölümleri](../../parallel/openmp/reference/sections-openmp.md) yönergesi boş kod bloğu sahiptir.  
  
 Aşağıdaki örnek C3046 oluşturur:  
  
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