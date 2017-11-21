---
title: "Derleyici Hatası C3043 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3043
dev_langs: C++
helpviewer_keywords: C3043
ms.assetid: 0ef55e63-e82b-48eb-9d44-690950ac34c6
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 2ec3f70fa176b8562067985b5b2d48ee2aa39b8e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3043"></a>Derleyici Hatası C3043
OpenMP 'kritik' yönergesi aynı ada sahip 'kritik' yönergesinde iç içe olamaz  
  
 A [kritik](../../parallel/openmp/reference/critical.md) yönergesi iç içe geçirilemez içinde bir `critical` aynı adı kullanan yönergesi.  
  
 Aşağıdaki örnek C3043 oluşturur:  
  
```  
// C3043.cpp  
// compile with: /openmp /c  
#include "omp.h"  
  
int main() {  
   int n1 = 1, n2 = 2, n3 = 3;  
  
   #pragma omp parallel  
   {  
      ++n2;  
  
      #pragma omp critical(MyTest)  
      {  
         ++n2;  
  
         #pragma omp critical(MyTest)   // C3043  
         // try the following line instead  
         // #pragma omp critical(MyTest2)  
         {  
            ++n3;  
         }  
      }  
   }  
}  
```