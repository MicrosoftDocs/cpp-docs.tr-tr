---
title: A.3   Paralel Bölgeleri Kullanma
ms.date: 11/04/2016
ms.assetid: 575216a1-960a-47f7-9c82-7f660291fcfe
ms.openlocfilehash: 573c4f7c47c90bc6d567c4640360aa6abee5a48c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50459000"
---
# <a name="a3---using-parallel-regions"></a>A.3   Paralel Bölgeleri Kullanma

`parallel` Yönergesi ([bölümü 2.3](../../parallel/openmp/2-3-parallel-construct.md) sayfasında 8) dilimi kaba paralel programlarında kullanılabilir. Aşağıdaki örnekte, her bir iş parçacığı bir paralel bölgenin içinde hangi bölümünün genel dizi karar `x` üzerinde çalışmak için iş parçacığı sayısına göre:

```
#pragma omp parallel shared(x, npoints) private(iam, np, ipoints)
{
    iam = omp_get_thread_num();
    np =  omp_get_num_threads();
    ipoints = npoints / np;
    subdomain(x, iam, ipoints);
}
```