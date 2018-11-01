---
title: 3.2.2 omp_destroy_lock ve omp_destroy_nest_lock İşlevleri
ms.date: 11/04/2016
ms.assetid: d334907d-94f7-4bbf-b20e-41d53484cbff
ms.openlocfilehash: 02f739ab2834db7eca9b051e6659644c39b51e84
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50666212"
---
# <a name="322-ompdestroylock-and-ompdestroynestlock-functions"></a>3.2.2 omp_destroy_lock ve omp_destroy_nest_lock İşlevleri

Bu işlevler işaret kilit değişkenine emin *kilit* başlatılmadı. Biçimi aşağıdaki gibidir:

```
#include <omp.h>
void omp_destroy_lock(omp_lock_t *lock);
void omp_destroy_nest_lock(omp_nest_lock_t *lock);
```

Çağırın ya da bu yordamların başlatılmamış veya kilidinin kilit değişken ile uyumsuzdur.