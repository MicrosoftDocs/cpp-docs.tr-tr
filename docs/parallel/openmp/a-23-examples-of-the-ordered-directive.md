---
title: A.23 ordered yönergesi örnekleri | Microsoft Docs
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
ms.openlocfilehash: ec609a77e9bdc7cbdbb0822dfde0a88110ce0244
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46405976"
---
# <a name="a23---examples-of-the-ordered-directive"></a>A.23   ordered Yönergesi Örnekleri

Birden çok sıralı bölümleri olası bir `for` ile belirtilen `ordered` yan tümcesi. İlk örnek uyumsuz olduğundan aşağıdaki API belirtir:

"Bir yineleme döngüsü ile bir `for` yapısı gerekir değil yürütme aynı `ordered` yönerge fazla bir kez ve gerekir değil yürütme birden fazla `ordered` yönergesi." (Bkz [bölümü 2.6.6](../../parallel/openmp/2-6-6-ordered-construct.md) sayfasında 22)

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