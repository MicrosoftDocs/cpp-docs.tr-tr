---
title: 3.2.1 omp_init_lock ve omp_init_nest_lock işlevleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 098a2721-b16a-484f-bc83-4b8e281e382c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4303eb3ccfcb1c449022a4be32f94b9f91e6e80c
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46387009"
---
# <a name="321-ompinitlock-and-ompinitnestlock-functions"></a>3.2.1 omp_init_lock ve omp_init_nest_lock İşlevleri

Bu işlevler bir kilit başlatma, yalnızca bir yöntem sağlar. Her işlev parametresi ile ilişkili kilit başlatır *kilit* sonraki çağrılarda kullanılmak. Biçimi aşağıdaki gibidir:

```
#include <omp.h>
void omp_init_lock(omp_lock_t *lock);
void omp_init_nest_lock(omp_nest_lock_t *lock);
```

İlk durum açılmış (diğer bir deyişle, hiçbir iş parçacığı kilit sahibi). Nestable kilit, ilk iç içe geçme sayısı sıfırdır. Zaten başlatılmış bir kilit değişkeniyle bu yordamların birini çağırmaya uyumsuzdur.