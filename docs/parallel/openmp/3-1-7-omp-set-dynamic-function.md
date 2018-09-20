---
title: 3.1.7 omp_set_dynamic işlevi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 1fba961b-b82c-4a1e-ab0f-e4be826e50ab
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 807e5739c571f7aa8e9f723a0a48c8c46f1e6d09
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46441570"
---
# <a name="317-ompsetdynamic-function"></a>3.1.7 omp_set_dynamic İşlevi

**Omp_set_dynamic** işlevini etkinleştirir veya paralel bölgeleri yürütülmesi için kullanılabilir iş parçacığı sayısını yerleştirmenin dinamik ayarına devre dışı bırakır. Biçimi aşağıdaki gibidir:

```
#include <omp.h>
void omp_set_dynamic(int dynamic_threads);
```

Varsa *dynamic_threads* değerlendirir sıfır olmayan bir değer sonraki paralel bölgeleri yürütmek için kullanılan iş parçacıklarının sayısını otomatik olarak sistem kaynakları en iyi şekilde yararlanmak için çalışma zamanı ortamı tarafından ayarlanması. Sonuç olarak kullanıcı tarafından belirtilen iş parçacığı sayısı en fazla iş parçacığı sayısıdır. Bir paralel bölgenin yürütme takım iş parçacıkları, paralel bölgenin süresi boyunca sabit kalır ve tarafından bildirilen **omp_get_num_threads** işlevi.

Varsa *dynamic_threads* değerlendirir 0 olarak yerleştirmenin dinamik ayarına devre dışı bırakıldı.

Bu işlev, bir program bölümünden çağrıldığında yukarıda açıklanan etkisi burada **omp_in_parallel** işlev, sıfır döndürür. Programın bir kısmını çağrılır, burada **omp_in_parallel** işlevi sıfır dışında bir değeri döndürür, bu işlevin davranış tanımlanmamıştır.

Bir çağrı **omp_set_dynamic** üzerinden önceliğe sahip **omp_dynamıc** ortam değişkeni.

Yerleştirmenin dinamik ayarına iş parçacığı sayısı için varsayılan uygulama tanımlanır. Sonuç olarak, belirli bir sayıya doğru yürütme için iş parçacığı bağımlı kullanıcı kodlarını açıkça dinamik iş parçacığı devre dışı bırakmanız gerekir. Uygulamaları, iş parçacığı sayısını dinamik olarak ayarlama olanağı sağlamak için gerekli değildir, ancak tüm platformlar arasında taşınabilirlik desteklemek için arabirim sağlamak için gerekli.

## <a name="cross-references"></a>Başvuruları çapraz:

- **omp_get_num_threads** çalışması için bkz: [bölümü 3.1.2](../../parallel/openmp/3-1-2-omp-get-num-threads-function.md) 37 sayfasında.

- **Omp_dynamıc** ortam değişkeni, bkz: [bölümü 4.3](../../parallel/openmp/4-3-omp-dynamic.md) 49 sayfasında.

- **omp_in_parallel** çalışması için bkz: [bölümü 3.1.6](../../parallel/openmp/3-1-6-omp-in-parallel-function.md) 38 sayfasında.