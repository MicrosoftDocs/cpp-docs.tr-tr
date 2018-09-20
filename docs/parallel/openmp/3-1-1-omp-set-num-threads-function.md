---
title: 3.1.1 omp_set_num_threads işlevi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: b94cf2b5-8011-4a3b-ba56-676982642857
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 85f7ff733583e531b449caf2039817b71165da52
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46426802"
---
# <a name="311-ompsetnumthreads-function"></a>3.1.1 omp_set_num_threads İşlevi

`omp_set_num_threads` İşlevi varsayılan belirtmeyin sonraki paralel bölgeleri için kullanılacak iş parçacığı sayısını ayarlar bir `num_threads` yan tümcesi. Biçimi aşağıdaki gibidir:

```
#include <omp.h>
void omp_set_num_threads(int num_threads);
```

Parametresinin değeri *num_threads* pozitif bir tamsayı olmalıdır. İş parçacığı sayısını yerleştirmenin dinamik ayarına etkin bağlı etkisini bağlıdır. Kurallar arasındaki etkileşimi hakkında kapsamlı bir dizi için `omp_set_num_threads` işlev ve iş parçacıklarını yerleştirmenin dinamik ayarına bölüm 2.3 8 sayfasında bakın.

Bu işlev, bir program bölümünden çağrıldığında yukarıda açıklanan etkisi burada `omp_in_parallel` işlev, sıfır döndürür. Programın bir kısmını çağrılır, burada `omp_in_parallel` işlevi sıfır dışında bir değeri döndürür, bu işlevin davranış tanımlanmamıştır.

Bu çağrı, üzerinde önceliğe sahiptir. `OMP_NUM_THREADS` ortam değişkeni. Çağırarak gerçekleştirilebilir iş parçacığı sayısı için varsayılan değer `omp_set_num_threads` ayarlayarak `OMP_NUM_THREADS` ortam değişkeni, tek bir açıkça geçersiz kılınabilir **paralel** belirterek yönergesi `num_threads` yan tümcesi.

## <a name="cross-references"></a>Başvuruları çapraz:

- `omp_set_dynamic` işlev, bkz: [bölümü 3.1.7](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md) sayfasında 39.

- `omp_get_dynamic` işlev, bkz: [bölümü 3.1.8](../../parallel/openmp/3-1-8-omp-get-dynamic-function.md) 40 sayfasında.

- `OMP_NUM_THREADS` ortam değişkeni, bkz: [bölümü 4.2](../../parallel/openmp/4-2-omp-num-threads.md) sayfasında 48 ve bölüm 2.3 8 sayfasında.

- `num_threads` yan tümcesi bkz [bölümü 2.3](../../parallel/openmp/2-3-parallel-construct.md) sayfasında 8