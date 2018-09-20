---
title: A.11 sabit sayıda iş parçacığı belirtme iş | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 1d06b142-4c35-44b8-994b-20f2aed5462b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 892140425dc9f7083c606fce3ffe671a107a65ca
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46422993"
---
# <a name="a11---specifying-a-fixed-number-of-threads"></a>A.11   Sabit Sayıda İş Parçacığı Belirtme

Bazı programlar, doğru bir şekilde yürütmek için iş parçacığı, bir sabit, belirlenmiş sayısına bağlıdır.  İş parçacığı sayısını yerleştirmenin dinamik ayarına için varsayılan ayar, uygulama tanımlı olduğu için dinamik iş parçacıkları özelliği devre dışı bırakırsınız ve açıkça taşınabilirliği sağlamak için iş parçacığı sayısını ayarlayın programlara seçebilirsiniz. Aşağıdaki örnek kullanarak bunun nasıl yapılacağını gösterir `omp_set_dynamic` ([bölümü 3.1.7](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md) sayfasında 39), ve `omp_set_num_threads` ([bölümü 3.1.1](../../parallel/openmp/3-1-1-omp-set-num-threads-function.md) sayfasında 36):

```
omp_set_dynamic(0);
omp_set_num_threads(16);
#pragma omp parallel shared(x, npoints) private(iam, ipoints)
{
    if (omp_get_num_threads() != 16)
      abort();
    iam = omp_get_thread_num();
    ipoints = npoints/16;
    do_by_16(x, iam, ipoints);
}
```

Bu örnekte, yalnızca 16 iş parçacıkları tarafından yürütülürse programı doğru bir şekilde yürütür. Uygulama 16 iş parçacığı destekleme kapasitesine sahip değilse, bu örnek davranışını uygulama tarafından tanımlanır.

Bir paralel bölgenin çalışan iş parçacıklarının sayısını ayarlama dinamik iş parçacıkları bakılmaksızın bir paralel bölgenin sırasında sabit kaldığına dikkat edin. Dinamik iş parçacıkları mekanizması paralel bölgenin başlangıcında kullanılacak iş parçacığı sayısını belirler ve bölgeyi süresi boyunca sabit tutar.