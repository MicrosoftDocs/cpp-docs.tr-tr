---
title: A.10   Ardışık Sıralamayı Belirtme
ms.date: 11/04/2016
ms.assetid: 5c65a9b1-0fc5-4cad-a5a9-9ce10b25d25c
ms.openlocfilehash: 4e3a146e1bca988f46cf7a7ee504644f96dab67e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50575259"
---
# <a name="a10---specifying-sequential-ordering"></a>A.10   Ardışık Sıralamayı Belirtme

Bölümler sıralı ([bölümü 2.6.6](../../parallel/openmp/2-6-6-ordered-construct.md) sayfasında 22) sıralı olarak paralel olarak yapılan iş çıktısı sıralama için kullanışlıdır. Aşağıdaki program, dizinleri sırayla kullanıma yazdırır:

```
#pragma omp for ordered schedule(dynamic)
    for (i=lb; i<ub; i+=st)
        work(i);
void work(int k)
{
    #pragma omp ordered
        printf_s(" %d", k);
}
```