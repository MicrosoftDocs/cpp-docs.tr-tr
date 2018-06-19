---
title: A.18 yönergeleri için iç içe geçmiş | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: ae2b2e0b-ec94-43f8-928c-6d621b51f0df
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c0f52baeaa4b6c37f0da1b818a5ae2b8471dabc9
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33690874"
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