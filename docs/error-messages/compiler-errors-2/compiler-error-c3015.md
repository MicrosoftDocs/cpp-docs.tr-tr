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
ms.workload: cplusplus
ms.openlocfilehash: d468d9db5c9809a31b1490c35187c43570370ced
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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