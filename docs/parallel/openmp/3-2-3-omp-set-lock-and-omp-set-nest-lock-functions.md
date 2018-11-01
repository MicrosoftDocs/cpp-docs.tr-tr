---
title: 3.2.3 omp_set_lock ve omp_set_nest_lock İşlevleri
ms.date: 11/04/2016
ms.assetid: b5323879-f72e-418e-953f-3979fdda17a2
ms.openlocfilehash: 8efc1f844be2d1b8cf9b15242758914edd0fca14
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50617665"
---
# <a name="323-ompsetlock-and-ompsetnestlock-functions"></a>3.2.3 omp_set_lock ve omp_set_nest_lock İşlevleri

Bu işlevlerin her biri, belirtilen kilit kullanılabilir ve ardından kilit ayarlar kadar işlevi yürütme iş parçacığını engeller. Basit bir kilit kilidi ise kullanılabilir. Nestable kilit kilitli olup olmadığını veya işlev yürütme iş parçacığı tarafından zaten aitse kullanılabilir. Biçimi aşağıdaki gibidir:

```
#include <omp.h>
void omp_set_lock(omp_lock_t *lock);
void omp_set_nest_lock(omp_nest_lock_t *lock);
```

Basit bir kilit, bağımsız değişkeni için `omp_set_lock` işlevi bir başlatılmış kilit değişkene işaret etmelidir. Kilidi sahipliğini, işlevi yürütme iş parçacığı için verilir.

Nestable kilit, bağımsız değişkeni için `omp_set_nest_lock` işlevi bir başlatılmış kilit değişkene işaret etmelidir. İç içe geçme sayısının artırılması ve iş parçacığı verilir veya kilidi sahipliğini korur.