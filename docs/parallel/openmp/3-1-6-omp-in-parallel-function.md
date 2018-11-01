---
title: 3.1.6 omp_in_parallel İşlevi
ms.date: 11/04/2016
ms.assetid: db6e3a63-2a0a-4b8e-8cc6-c6b49edca5fb
ms.openlocfilehash: 2f251cb994771278c7f4e3f50f01e02126f6f88d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50482049"
---
# <a name="316-ompinparallel-function"></a>3.1.6 omp_in_parallel İşlevi

**Omp_in_parallel** işlevi dinamik kapsam, paralel olarak yürütülen bir paralel bölgenin içinde çağrılırsa sıfır olmayan bir değer döndürür; Aksi takdirde 0 değerini döndürür. Biçimi aşağıdaki gibidir:

```
#include <omp.h>
int omp_in_parallel(void);
```

Bu işlev bir bölge serileştirilme şeklini iç içe geçmiş bölge dahil paralel olarak yürütülen'içinde çağrılır, sıfır olmayan bir değer döndürür.