---
title: 3.1.4 omp_get_thread_num işlevi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 5220402b-c109-4b1f-ba79-002e93d08617
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5a21a682c051daffde16b3d5cfc63fd2d679c4de
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46444924"
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