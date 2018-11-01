---
title: 3.1.7 omp_set_dynamic İşlevi
ms.date: 11/04/2016
ms.assetid: 1fba961b-b82c-4a1e-ab0f-e4be826e50ab
ms.openlocfilehash: 641b2ecfdb19aec9387aa299d22a041f25b22929
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50492943"
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