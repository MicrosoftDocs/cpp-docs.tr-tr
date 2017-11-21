---
title: "Flush yönergesi olan bir liste kullanarak A.13 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 6c9d0736-07c2-47b1-a216-5293f03b6397
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: fc10c427f92ed602975fdb56436911dafbd94532
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="a13---using-the-flush-directive-with-a-list"></a>A.13   flush Yönergesini Listeyle Kullanma
Aşağıdaki örnek kullanır `flush` yönerge noktadan noktaya eşitleme iş parçacığı çiftleri arasındaki belirli nesneleri için:  
  
```  
int   sync[NUMBER_OF_THREADS];  
float work[NUMBER_OF_THREADS];  
#pragma omp parallel private(iam,neighbor) shared(work,sync)  
{  
    iam = omp_get_thread_num();  
    sync[iam] = 0;  
    #pragma omp barrier  
  
    // Do computation into my portion of work array   
    work[iam] = ...;  
  
    //  Announce that I am done with my work  
    // The first flush ensures that my work is  
    // made visible before sync.  
    // The second flush ensures that sync is made visible.  
    #pragma omp flush(work)  
    sync[iam] = 1;  
    #pragma omp flush(sync)  
  
    // Wait for neighbor  
    neighbor = (iam>0 ? iam : omp_get_num_threads()) - 1;  
    while (sync[neighbor]==0)   
    {  
        #pragma omp flush(sync)  
    }  
  
    // Read neighbor's values of work array   
    ... = work[neighbor];  
}  
```