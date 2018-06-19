---
title: Sıralı yönergesi A.23 örnekleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: f8fa761b-7fc5-4447-95f9-8571e9ca31bf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 37cc4ea9db8cbd1a7bf095e2bde0ae482053a584
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33692762"
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