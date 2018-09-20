---
title: A.15 kullanılan iş parçacıklarının sayısını | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 026bb59a-f668-40db-a7cb-69a1bae83d2d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1042b4871f53bddb5cff894330f3afe7d8a088ef
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46428747"
---
# <a name="a15---determining-the-number-of-threads-used"></a>A.15   Kullanılan İş Parçacıklarının Sayısını Belirleme

Aşağıdaki yanlış örneği göz önünde bulundurun (için [bölümü 3.1.2](../../parallel/openmp/3-1-2-omp-get-num-threads-function.md) sayfasında 37):

```
np = omp_get_num_threads(); // misplaced
#pragma omp parallel for schedule(static)
    for (i=0; i<np; i++)
        work(i);
```

`omp_get_num_threads()` Çağrısı 1 döndürür seri koddaki bölümünde bu nedenle *np* her zaman bir önceki örnekte 1'e eşit olacaktır. Paralel bölge için dağıtılacak iş parçacığı sayısını belirlemek için çağrı paralel bölgenin içinde olmalıdır.

Aşağıdaki örnek, bir sorgu için iş parçacığı sayısı dahil olmak üzere bu program yeniden gösterilmektedir:

```
#pragma omp parallel private(i)
{
    i = omp_get_thread_num();
    work(i);
}
```