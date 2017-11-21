---
title: "Derleyici Hatası C3021 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3021
dev_langs: C++
helpviewer_keywords: C3021
ms.assetid: 0cef6d97-e267-438a-ac8b-0daf5bbbc2cf
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 2dd19610cdb548fa3b9a81181fa8857d8c8e8644
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3021"></a>Derleyici Hatası C3021
'arg': OpenMP yönergesi 'yönergesi' boş olmayan bağımsız değişken  
  
 Bağımsız değişken bir OpenMP yönergesi için gereklidir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C3021 oluşturur:  
  
```  
// C3021.cpp  
// compile with: /openmp  
#include <stdio.h>  
#include "omp.h"  
  
int g = 0;  
  
int main()  
{  
    int x, y, i;  
  
    #pragma omp parallel for schedule(static,)   // C3021  
    for (i = 0; i < 10; ++i) ;  
  
    #pragma omp parallel for schedule()   // C3021  
    for (i = 0; i < 10; ++i)  
        printf_s("Hello world, thread %d, iteration %d\n",  
                 omp_get_thread_num(), i);  
  
    #pragma omp parallel reduction()   // C3021  
      ;  
  
    #pragma omp parallel reduction(+ :)   // C3021  
      ;  
  
    //   
    // The following shows correct syntax examples.  
    //  
    #pragma omp parallel reduction(+ : x, y)  
      ;  
  
    #pragma omp parallel reduction(* : x, y)  
      ;  
  
    #pragma omp parallel reduction(- : x, y)  
      ;  
  
    #pragma omp parallel reduction(& : x, y)  
      ;  
  
    #pragma omp parallel reduction(^ : x, y)  
      ;  
  
    #pragma omp parallel reduction(| : x, y)  
      ;  
  
    #pragma omp parallel reduction(&& : x, y)  
      ;  
  
    #pragma omp parallel reduction(|| : x, y)  
      ;  
}  
```