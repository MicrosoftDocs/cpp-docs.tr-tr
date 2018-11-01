---
title: A.12   atomic Yönergesini Kullanma
ms.date: 11/04/2016
ms.assetid: d3ba3c87-413d-4efa-8a45-8a7f28ab0164
ms.openlocfilehash: 0f75b182e2cae11f0e72d5ca1e67f887294e8f69
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50504451"
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