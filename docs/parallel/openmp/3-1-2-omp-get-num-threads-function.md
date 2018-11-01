---
title: 3.1.2 omp_get_num_threads İşlevi
ms.date: 11/04/2016
ms.assetid: bcdd76e2-d96b-4884-ac8f-e55fc0c42801
ms.openlocfilehash: 587b49f70896bcfe8c1a805a4ebb13a11e9bb7d0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50465253"
---
# <a name="312-ompgetnumthreads-function"></a>3.1.2 omp_get_num_threads İşlevi

**Omp_get_num_threads** işlevi döndürür iş parçacığı sayısını şu anda takım içinden çağırıldığında bir paralel bölgenin yürütme. Biçimi aşağıdaki gibidir:

```
#include <omp.h>
int omp_get_num_threads(void);
```

**Num_threads** yan tümcesi **omp_set_num_threads** işlevi ve **OMP_NUM_THREADS** ortam değişkeni denetimi bir takım olarak iş parçacığı sayısı.

İş parçacığı sayısı kullanıcı tarafından açıkça ayarlanmadı, uygulama tanımlı varsayılandır. Bu işlev en yakın kapsayan bağlar **paralel** yönergesi. Bu işlev, bir program seri bir kısmını veya serileştirilmiş bir iç içe geçmiş bir paralel bölgenin çağrılırsa, 1 döndürür.

## <a name="cross-references"></a>Başvuruları çapraz:

- **OMP_NUM_THREADS** ortam değişkeni, bkz: [bölümü 4.2](../../parallel/openmp/4-2-omp-num-threads.md) sayfasında 48.

- **num_threads** yan tümcesi bkz [bölümü 2.3](../../parallel/openmp/2-3-parallel-construct.md) 8 sayfasında.

- **Paralel** oluşturmak için bkz: [bölümü 2.3](../../parallel/openmp/2-3-parallel-construct.md) 8 sayfasında.