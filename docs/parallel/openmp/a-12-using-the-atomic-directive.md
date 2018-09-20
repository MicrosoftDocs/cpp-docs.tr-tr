---
title: A.12 atomic yönergesini kullanma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: d3ba3c87-413d-4efa-8a45-8a7f28ab0164
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 04daed582cfe87f6e4803b30919af3e07037de7f
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46378754"
---
# <a name="a12---using-the-atomic-directive"></a>A.12   atomic Yönergesini Kullanma

Aşağıdaki örnek, yarış durumları ortadan kaldırır (bir öğenin aynı anda güncelleştirmeleri *x* birden çok iş parçacığı tarafından) kullanarak `atomic` yönergesi ([bölümü 2.6.4](../../parallel/openmp/2-6-4-atomic-construct.md) sayfasında 19):

```
#pragma omp parallel for shared(x, y, index, n)
    for (i=0; i<n; i++)
    {
        #pragma omp atomic
            x[index[i]] += work1(i);
        y[i] += work2(i);
    }
```

Kullanmanın avantajı `atomic` yönergesiyse Bu örnekte iki farklı öğeler paralel olarak gerçekleşmesi için x güncelleştirmeleri sağlar. Varsa bir `critical` yönergesi ([bölümü 2.6.2](../../parallel/openmp/2-6-2-critical-construct.md) sayfasında 18) öğelerine tüm güncelleştirmeleri sonra bunun yerine, kullanılan *x* seri olarak (, tüm sipariş garanti rağmen) yürütülmesi.

Unutmayın `atomic` yönergesi hemen ardından yalnızca C veya C++ ifadesi için geçerlidir.  Sonuç olarak, öğeleri *y* Bu örnekte otomatik olarak güncelleştirilmez.