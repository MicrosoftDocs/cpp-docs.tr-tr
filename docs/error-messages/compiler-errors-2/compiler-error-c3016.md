---
title: "Derleyici Hatası C3016 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3016
dev_langs: C++
helpviewer_keywords: C3016
ms.assetid: 3423467e-e8bb-4f35-b4db-7925cafa74c1
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 27c5e212b0ca9dc4141210aa34ce9af2c4ccffbf
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3016"></a>Derleyici Hatası C3016
'var': 'için' deyimi OpenMP dizin değişken tamsayı türü imzalı  
  
 Bir OpenMP dizin değişkeninde `for` deyimi imzalı bir tamsayı türünde olması gerekir.  
  
 Aşağıdaki örnek C3016 oluşturur:  
  
```  
// C3016.cpp  
// compile with: /openmp  
int main()  
{  
   #pragma omp parallel  
   {  
      unsigned int i = 0;  
      // Try the following line instead:  
      // int i = 0;  
  
      #pragma omp for  
      for (i = 0; i <= 10; ++i)   // C3016  
      {  
      }  
   }  
}  
```