---
title: A.9   single Yönergelerini Kullanma
ms.date: 11/04/2016
ms.assetid: 0c0f9495-5794-4db9-883b-a12e3a9f1328
ms.openlocfilehash: 51a2a3438ae5abc9d24c160a986c8ea04b77c4bf
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50501315"
---
# <a name="a9---using-single-directives"></a>A.9   single Yönergelerini Kullanma

Aşağıdaki örnek, gösterir `single` yönergesi ([bölümü 2.4.3](../../parallel/openmp/2-4-3-single-construct.md) sayfasında 15). Örnekte, yalnızca bir iş parçacığı (karşılaştığı genellikle ilk iş parçacığında `single` yönergesi) ilerleme iletisi yazdırır. Hangi iş parçacığının yürütecek şekilde için kullanıcı varsayımlar yapmamalısınız `single` bölümü. Diğer tüm iş parçacıklarının atlanacak `single` bölümünde ve sonunda engel Durdur `single` oluşturun. Diğer iş parçacıkları iş parçacığını yürütmek için beklemenize gerek kalmadan geçebilirsiniz `single` bölümünde, bir `nowait` yan tümcesi belirtilebilir `single` yönergesi.

```
#pragma omp parallel
{
    #pragma omp single
        printf_s("Beginning work1.\n");
    work1();
    #pragma omp single
        printf_s("Finishing work1.\n");
    #pragma omp single nowait
        printf_s("Finished work1 and beginning work2.\n");
    work2();
}
```