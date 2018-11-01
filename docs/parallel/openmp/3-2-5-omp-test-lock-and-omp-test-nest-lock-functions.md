---
title: 3.2.5 omp_test_lock ve omp_test_nest_lock İşlevleri
ms.date: 11/04/2016
ms.assetid: 36818945-c22c-4c24-b754-4e73eba6f3f8
ms.openlocfilehash: e8e03699f807f23f139075560592d8846467f2c5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50512760"
---
# <a name="325-omptestlock-and-omptestnestlock-functions"></a>3.2.5 omp_test_lock ve omp_test_nest_lock İşlevleri

Bu işlevler bir kilidi ayarlama girişiminde bulunuldu ancak iş parçacığının yürütülmesini engellemez. Biçimi aşağıdaki gibidir:

```
#include <omp.h>
int omp_test_lock(omp_lock_t *lock);
int omp_test_nest_lock(omp_nest_lock_t *lock);
```

Bağımsız değişken bir başlatılmış kilit değişkene işaret etmelidir. Bu işlevler, aynı şekilde kilit ayarlama girişimi `omp_set_lock` ve `omp_set_nest_lock`dışında iş parçacığının yürütülmesini engellemez.

Basit bir kilitleme `omp_test_lock` işlevi lock başarılı bir şekilde ayarlanmışsa sıfır olmayan bir değer döndürür; Aksi takdirde, sıfır döndürür.

Bir nestable kilit için `omp_test_nest_lock` işlevi lock başarılı bir şekilde ayarlanmışsa yeni iç içe geçme sayısını döndürür; Aksi takdirde, sıfır döndürür.