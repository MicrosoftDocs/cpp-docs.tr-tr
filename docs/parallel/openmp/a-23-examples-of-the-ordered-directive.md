---
title: "Sıralı yönergesi A.23 örnekleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: f8fa761b-7fc5-4447-95f9-8571e9ca31bf
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: b1d6f50eed2c4e89576dd4c17c5a87599bf59e4f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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