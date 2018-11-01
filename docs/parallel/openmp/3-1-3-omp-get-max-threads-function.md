---
title: 3.1.3 omp_get_max_threads İşlevi
ms.date: 11/04/2016
ms.assetid: 5548897c-546e-4d19-b37b-a76f6b30a0a9
ms.openlocfilehash: 3f954b5ad75b4bdb4a74323f2ab4e819850269ed
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50546598"
---
# <a name="313-ompgetmaxthreads-function"></a>3.1.3 omp_get_max_threads İşlevi

**Omp_get_max_threads** işlevi en az kadar büyük bir paralel bölgenin olmadan, bir takım oluşturmak için kullanılacak iş parçacığı sayısını olması garanti bir tamsayı döndürür bir **num_threads** yan tümcesi Bu noktada kod ile karşılaşılan şekilde yapılandırılmış. Biçimi aşağıdaki gibidir:

```
#include <omp.h>
int omp_get_max_threads(void);
```

Aşağıdaki alt sınırı değeri temel ifade **omp_get_max_threads**:

```

threads-used-for-next-team
<= omp_get_max_threads

```

Sonraki bir paralel bölgenin kullanıyorsa unutmayın **num_threads** iş parçacıklarını garanti sonucunu alt sınırı üzerinde belirli sayıda istek yan tümcesini **omp_get_max_threads** hiçbir uzun tutar.

**Omp_get_max_threads** işlevin dönüş değeri, dinamik olarak izleyen bir paralel bölgenin oluşturulmuş takım tüm iş parçacıkları için yeterli depolama alanı ayırmak için kullanılabilir.

## <a name="cross-references"></a>Başvuruları çapraz:

- **omp_get_num_threads** çalışması için bkz: [bölümü 3.1.2](../../parallel/openmp/3-1-2-omp-get-num-threads-function.md) 37 sayfasında.

- **omp_set_num_threads** çalışması için bkz: [bölümü 3.1.1](../../parallel/openmp/3-1-1-omp-set-num-threads-function.md) 36 sayfasında.

- **omp_set_dynamic** çalışması için bkz: [bölümü 3.1.7](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md) sayfasında 39.

- **num_threads** yan tümcesi bkz [bölümü 2.3](../../parallel/openmp/2-3-parallel-construct.md) 8 sayfasında.