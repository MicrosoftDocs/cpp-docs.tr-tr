---
title: A.9 single yönergelerini kullanma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 0c0f9495-5794-4db9-883b-a12e3a9f1328
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5a3a201450d54355aa96f0ea712ad9fa0f70f63f
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46448096"
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