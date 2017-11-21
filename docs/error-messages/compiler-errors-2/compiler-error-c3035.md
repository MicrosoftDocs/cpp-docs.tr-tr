---
title: "Derleyici Hatası C3035 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3035
dev_langs: C++
helpviewer_keywords: C3035
ms.assetid: af34fad2-2b45-42d0-a9ff-04eab3e91c37
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 820a09741508c710d851182d9e1a02489c1ed2ac
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3035"></a>Derleyici Hatası C3035
OpenMP 'sıralı' yönergesi gerekir bağlamak doğrudan 'İçin' veya 'için parallel' 'sıralı' yan tümcesi ile yönergesi  
  
 Sıralı bir yan tümcesi ill oluşturulmuş.  
  
 Aşağıdaki örnek C3035 oluşturur:  
  
```  
// C3035.cpp  
// compile with: /openmp /link vcomps.lib  
int main() {  
   int n = 0, x, i;  
  
   #pragma omp parallel private(n)  
   {  
      #pragma omp ordered   // C3035  
      // Try the following line instead:  
      // #pragma omp for ordered  
       for (i = 0 ; i < 10 ; ++i)  
         ;  
   }  
}  
```