---
title: "Derleyici Hatası C3048 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3048
dev_langs: C++
helpviewer_keywords: C3048
ms.assetid: 48e07091-94d9-471d-befe-7e2507631edd
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: a17a103bf49040496b886799bf58910eedff8051
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3048"></a>Derleyici Hatası C3048
'#Pragma omp atomik' aşağıdaki ifade yanlış biçime sahiptir  
  
 Atomik yönergesi hatalı şekilde belirtildi.  
  
 Aşağıdaki örnek C3048 oluşturur:  
  
```  
// C3048.cpp  
// compile with: /openmp vcomps.lib  
#include "omp.h"  
#include <stdio.h>  
  
int main() {  
   int a[10];  
   omp_set_num_threads(4);  
   #pragma omp parallel  
   {  
      #pragma omp atomic  
      a[0] = 1;   // C3048  
      // try the following line instead  
      // a[0] += 1;  
   }  
}  
```