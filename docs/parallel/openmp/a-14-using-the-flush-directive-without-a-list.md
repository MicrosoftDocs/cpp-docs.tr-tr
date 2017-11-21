---
title: "Flush yönergesi listesini olmadan kullanarak A.14 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 9e63141a-d0c6-43a5-ac16-b0bd7c89b871
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: bb948476b52cdf76e0a114bed5c95f46bb6ba86e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="a14---using-the-flush-directive-without-a-list"></a>A.14   flush Yönergesini Liste Olmadan Kullanma
Aşağıdaki örnekte (için [bölüm 2.6.5](../../parallel/openmp/2-6-5-flush-directive.md) sayfasında 20) etkilenen paylaşılan nesneler ayıran bir `flush` etkilenmez paylaşılan nesnelerinden hiçbir listesiyle yönerge:  
  
## <a name="example"></a>Örnek  
  
### <a name="code"></a>Kod  
  
```  
// omp_flush_without_list.c  
#include <omp.h>  
  
int x, *p = &x;  
  
void f1(int *q)  
{  
    *q = 1;  
    #pragma omp flush  
    // x, p, and *q are flushed  
    //   because they are shared and accessible  
    // q is not flushed because it is not shared.  
}  
  
void f2(int *q)  
{  
    #pragma omp barrier  
    *q = 2;  
  
    #pragma omp barrier  
    // a barrier implies a flush  
    // x, p, and *q are flushed  
    //   because they are shared and accessible  
    // q is not flushed because it is not shared.  
}  
  
int g(int n)  
{  
    int i = 1, j, sum = 0;  
    *p = 1;  
  
    #pragma omp parallel reduction(+: sum) num_threads(10)  
    {  
        f1(&j);  
        // i, n and sum were not flushed  
        //   because they were not accessible in f1  
        // j was flushed because it was accessible  
        sum += j;  
        f2(&j);  
        // i, n, and sum were not flushed  
        //   because they were not accessible in f2  
        // j was flushed because it was accessible  
        sum += i + j + *p + n;  
    }  
    return sum;  
}  
  
int main()  
{  
}  
```