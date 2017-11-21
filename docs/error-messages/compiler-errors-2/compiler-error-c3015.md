---
title: "Derleyici Hatası C3015 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3015
dev_langs: C++
helpviewer_keywords: C3015
ms.assetid: d5e8e50b-7542-4b2d-8665-1b22072a5bc6
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: cc6b91b2d6fbd3158b7b6a8326e07a0228889b1b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3015"></a>Derleyici Hatası C3015
OpenMP başlatma 'için' deyimi yanlış biçime sahip  
  
 A `for` döngü OpenMP deyimi içinde tam olarak ve açıkça belirtilmesi gerekir.  
  
 Aşağıdaki örnek C3015 oluşturur:  
  
```  
// C3015.cpp  
// compile with: /openmp  
int main()  
{  
   int i = 0, j = 10;  
  
   #pragma omp parallel  
   {  
      #pragma omp for  
      for (; i < 0; i += j)   // C3015  
      // Try the following line instead:  
      // for (i = 0; i < 0; i++)   
         --j;  
   }  
}  
```