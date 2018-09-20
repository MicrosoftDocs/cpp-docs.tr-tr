---
title: 3.1.2 omp_get_num_threads işlevi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: bcdd76e2-d96b-4884-ac8f-e55fc0c42801
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 512c09b0cf71a7fd9c7438b6f9cceb9f16126718
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46424992"
---
# <a name="312-ompgetnumthreads-function"></a>3.1.2 omp_get_num_threads İşlevi

**Omp_get_num_threads** işlevi döndürür iş parçacığı sayısını şu anda takım içinden çağırıldığında bir paralel bölgenin yürütme. Biçimi aşağıdaki gibidir:

```
#include <omp.h>
int omp_get_num_threads(void);
```

**Num_threads** yan tümcesi **omp_set_num_threads** işlevi ve **OMP_NUM_THREADS** ortam değişkeni denetimi bir takım olarak iş parçacığı sayısı.

İş parçacığı sayısı kullanıcı tarafından açıkça ayarlanmadı, uygulama tanımlı varsayılandır. Bu işlev en yakın kapsayan bağlar **paralel** yönergesi. Bu işlev, bir program seri bir kısmını veya serileştirilmiş bir iç içe geçmiş bir paralel bölgenin çağrılırsa, 1 döndürür.

## <a name="cross-references"></a>Başvuruları çapraz:

- **OMP_NUM_THREADS** ortam değişkeni, bkz: [bölümü 4.2](../../parallel/openmp/4-2-omp-num-threads.md) sayfasında 48.

- **num_threads** yan tümcesi bkz [bölümü 2.3](../../parallel/openmp/2-3-parallel-construct.md) 8 sayfasında.

- **Paralel** oluşturmak için bkz: [bölümü 2.3](../../parallel/openmp/2-3-parallel-construct.md) 8 sayfasında.