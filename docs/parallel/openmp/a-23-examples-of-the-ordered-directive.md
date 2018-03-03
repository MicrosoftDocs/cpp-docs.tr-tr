---
title: "Sıralı yönergesi A.23 örnekleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: f8fa761b-7fc5-4447-95f9-8571e9ca31bf
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 83d77bb4f064a7ee69b013b36de919b57486b3e8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="a23---examples-of-the-ordered-directive"></a>A.23   ordered Yönergesi Örnekleri
Birden çok sıralı bölümlerle olması mümkündür bir `for` ile belirtilen `ordered` yan tümcesi. İlk örnek uyumsuz olduğundan API aşağıdaki belirtir:  
  
 "Yineleme döngüsü ile bir `for` yapı gerekir değil yürütme aynı `ordered` yönerge fazla bir kez ve gerekir değil yürütme birden fazla `ordered` yönergesi." (Bkz [bölüm 2.6.6](../../parallel/openmp/2-6-6-ordered-construct.md) sayfasında 22)  
  
 Uyumsuz Bu örnekte, tüm yinelemeleri 2 sıralı bölümleri yürütün:  
  
```  
#pragma omp for ordered  
for (i=0; i<n; i++)   
{  
    ...  
    #pragma omp ordered  
    { ... }  
    ...  
    #pragma omp ordered  
    { ... }  
    ...  
}  
```  
  
 Aşağıdaki uyumlu örnekte gösterildiği bir `for` birden çok bölüm sıralı:  
  
```  
#pragma omp for ordered  
for (i=0; i<n; i++)   
{  
    ...  
    if (i <= 10)   
    {  
        ...  
        #pragma omp ordered  
        { ... }  
    }  
    ...  
    (i > 10)   
    {  
        ...  
        #pragma omp ordered  
        { ... }  
    }  
    ...  
}  
```