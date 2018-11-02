---
title: 3.1.10 omp_get_nested İşlevi
ms.date: 11/04/2016
ms.assetid: 48736a25-5c6e-4e2d-aad0-421087663a3c
ms.openlocfilehash: a4db1e21f344f5cc58e2027b0816f9c8fb40b3bc
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50519931"
---
# <a name="3110-ompgetnested-function"></a>3.1.10 omp_get_nested İşlevi

`omp_get_nested` İşlevi, iç içe geçmiş paralellik etkinse, sıfır dışında bir değeri ile 0 değilse döndürür. İç içe geçmiş paralellik hakkında daha fazla bilgi için bölümüne 3.1.9 40 sayfasında bakın. Biçimi aşağıdaki gibidir:

```
#include <omp.h>
int omp_get_nested(void);
```

Bir uygulama, iç içe geçmiş paralellik uygulamıyor, bu işlev her zaman 0 döndürür.