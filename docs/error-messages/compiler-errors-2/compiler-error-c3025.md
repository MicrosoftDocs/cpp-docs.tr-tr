---
title: "Derleyici Hatası C3025 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3025
dev_langs: C++
helpviewer_keywords: C3025
ms.assetid: 4442f5a3-d9ea-4873-b1fb-e7e5bd3cbe5e
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3ea53babdc7df7e6e95f5d37767d998290afc554
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3025"></a>Derleyici Hatası C3025
'yan tümcesi': tam sayı ifade bekleniyordu  
  
 Bir yan tümcesi bir tamsayı ifade gerektiriyor, ancak bir işlemesinin ifadesi verildi.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C3025 oluşturur.  
  
```  
// C3025.cpp  
// compile with: /openmp /link vcomps.lib  
#include <stdio.h>  
#include "omp.h"  
  
float f = 2.0F;  
  
int main()   
{  
    int i = 0;  
  
    // OK  
    puts("Test with int");  
    #pragma omp parallel for num_threads(i)  
    for (i = 1; i <= 2; ++i)  
        printf_s("Hello World - thread %d - iteration %d\n",  
                 omp_get_thread_num(), i);  
  
    puts("Test with float");  
    #pragma omp parallel for num_threads(f)   // C3025  
    for (i = 1; i <= 2; ++i)  
        printf_s("Hello World - thread %d - iteration %d\n",  
                 omp_get_thread_num(), i);  
}  
```