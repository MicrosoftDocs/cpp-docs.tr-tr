---
title: "A.18 yönergeleri için iç içe geçmiş | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: ae2b2e0b-ec94-43f8-928c-6d621b51f0df
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: bdbd65d74b45ed1d7bfc69c24c214383e0567a31
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="a18---nested-for-directives"></a>A.18   Yönergeler için İç İçe Konulan
Aşağıdaki örneği `for` yönerge iç içe geçme ([bölüm 2.9](../../parallel/openmp/2-9-directive-nesting.md) sayfasında 33) uyumlu olmadığından iç ve dış `for` yönergeleri bağlamak için farklı paralel bölgeler:  
  
```  
#pragma omp parallel default(shared)  
{  
    #pragma omp for  
        for (i=0; i<n; i++)   
        {  
            #pragma omp parallel shared(i, n)  
            {  
                #pragma omp for  
                    for (j=0; j<n; j++)  
                        work(i, j);  
            }  
        }  
}  
```  
  
 Önceki örnekte aşağıdaki çeşitlemesi de uyumludur:  
  
```  
#pragma omp parallel default(shared)  
{  
    #pragma omp for  
        for (i=0; i<n; i++)  
            work1(i, n);  
}  
  
void work1(int i, int n)  
{  
    int j;  
    #pragma omp parallel default(shared)  
    {  
        #pragma omp for  
            for (j=0; j<n; j++)  
                work2(i, j);  
    }  
    return;  
}  
```