---
title: 3.1.4 omp_get_thread_num İşlevi
ms.date: 11/04/2016
ms.assetid: 5220402b-c109-4b1f-ba79-002e93d08617
ms.openlocfilehash: eca8522aeab4702be390d98faaf8920f2d732244
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50480944"
---
# <a name="314-ompgetthreadnum-function"></a>3.1.4 omp_get_thread_num İşlevi

`omp_get_thread_num` İşlevi, iş parçacığı sayısı, kendi takım içindeki işlevi yürüten iş parçacığının döndürür. 0 arasında iş parçacığı numarası kalıyor ve **omp_get_num_threads()**-1, kapsamlı. Takım ana iş parçacığı 0 parçacığıdır.

Biçimi aşağıdaki gibidir:

```
#include <omp.h>
int omp_get_thread_num(void);
```

Bir seri bölgeden çağrılırsa `omp_get_thread_num` 0 döndürür. Serileştirilen iç içe geçmiş bir paralel bölgenin içinde çağrılır, bu işlev 0 döndürür.

## <a name="cross-references"></a>Başvuruları çapraz:

- `omp_get_num_threads` işlev, bkz: [bölümü 3.1.2](../../parallel/openmp/3-1-2-omp-get-num-threads-function.md) 37 sayfasında.