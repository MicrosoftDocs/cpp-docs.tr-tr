---
title: A.23   ordered Yönergesi Örnekleri
ms.date: 11/04/2016
ms.assetid: f8fa761b-7fc5-4447-95f9-8571e9ca31bf
ms.openlocfilehash: 2868b771fd57613981f3c6458b48493a1b26eee4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50472286"
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