---
title: 3.1.8 omp_get_dynamic İşlevi
ms.date: 11/04/2016
ms.assetid: c03e2daf-29c9-49e3-9b67-b980ad1ab195
ms.openlocfilehash: d9476894e5aff4cc7bb9c67fbbeb14d185b65f5e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50566432"
---
# <a name="318-ompgetdynamic-function"></a>3.1.8 omp_get_dynamic İşlevi

**Omp_get_dynamic** işlevi, iş parçacıkları yerleştirmenin dinamik ayarına etkinleştirilmişse ve 0 döndürür sıfır olmayan bir değer döndürür. Biçimi aşağıdaki gibidir:

```
#include <omp.h>
int omp_get_dynamic(void);
```

Uygulama iş parçacığı sayısını yerleştirmenin dinamik ayarına uygulamaz, bu işlev her zaman 0 değerini döndürür.

## <a name="cross-references"></a>Başvuruları çapraz:

- Dinamik iş parçacığı ayarlama ile ilgili açıklama için bkz: [bölümü 3.1.7](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md) sayfasında 39.