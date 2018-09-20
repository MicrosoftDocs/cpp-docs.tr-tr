---
title: 3.1.8 omp_get_dynamic işlevi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: c03e2daf-29c9-49e3-9b67-b980ad1ab195
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2c30f49eaf91353d6a7cd9bd26e0e10e95cb6acd
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46426789"
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