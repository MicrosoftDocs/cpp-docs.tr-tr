---
title: A.4 nowait yan tümcesini kullanma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: d3de2111-05ea-4ee3-a66c-57bd988712af
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: da4b69ed8ccf59fb90d17da2b85d7693d661785b
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46444508"
---
# <a name="a4---using-the-nowait-clause"></a>A.4   nowait Yan Tümcesini Kullanma

Bir paralel bölgenin içinde birden çok bağımsız döngüler varsa, kullanabileceğiniz `nowait` yan tümcesi ([bölümü 2.4.1](../../parallel/openmp/2-4-1-for-construct.md) sayfasında 11) sonunda örtük engel önlemek için `for` yönergesi, aşağıdaki gibi:

```
#pragma omp parallel
{
    #pragma omp for nowait
        for (i=1; i<n; i++)
             b[i] = (a[i] + a[i-1]) / 2.0;
    #pragma omp for nowait
        for (i=0; i<m; i++)
            y[i] = sqrt(z[i]);
}
```