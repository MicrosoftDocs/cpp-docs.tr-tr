---
title: "Derleyici Hatası C3019 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3019
dev_langs: C++
helpviewer_keywords: C3019
ms.assetid: 31a6d9b6-d29f-4499-9ad8-48dd751e87c7
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: fb418621a4a20fc802f22ca014c44809f80ce65b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3019"></a>Derleyici Hatası C3019
OpenMP aralıkla 'için' deyimi yanlış biçime sahip  
  
 Bir OpenMP artışı parçası `for` döngü dizini değişkeni hem sol ve sağ tarafındaki işleci kullanmanız gerekir.  
  
 Aşağıdaki örnek C3019 oluşturur:  
  
```  
// C3019.cpp  
// compile with: /openmp  
int main()  
{  
   int i = 0, j = 1, n = 3;  
  
   #pragma omp parallel  
   {  
      #pragma omp for  
      for (i = 0; i < 10; i = j + n)   // C3019  
      // Try the following line instead:  
      // for (i = 0; i < 10; i++)  
         j *= 2;  
   }  
}  
```