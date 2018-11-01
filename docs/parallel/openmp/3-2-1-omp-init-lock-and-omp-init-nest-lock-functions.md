---
title: 3.2.1 omp_init_lock ve omp_init_nest_lock İşlevleri
ms.date: 11/04/2016
ms.assetid: 098a2721-b16a-484f-bc83-4b8e281e382c
ms.openlocfilehash: 2d15aacb5e6743d18150fb45bea85b7ca22a401f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50472786"
---
# <a name="321-ompinitlock-and-ompinitnestlock-functions"></a>3.2.1 omp_init_lock ve omp_init_nest_lock İşlevleri

Bu işlevler bir kilit başlatma, yalnızca bir yöntem sağlar. Her işlev parametresi ile ilişkili kilit başlatır *kilit* sonraki çağrılarda kullanılmak. Biçimi aşağıdaki gibidir:

```
#include <omp.h>
void omp_init_lock(omp_lock_t *lock);
void omp_init_nest_lock(omp_nest_lock_t *lock);
```

İlk durum açılmış (diğer bir deyişle, hiçbir iş parçacığı kilit sahibi). Nestable kilit, ilk iç içe geçme sayısı sıfırdır. Zaten başlatılmış bir kilit değişkeniyle bu yordamların birini çağırmaya uyumsuzdur.