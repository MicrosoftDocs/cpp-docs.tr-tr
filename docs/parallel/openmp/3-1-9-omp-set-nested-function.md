---
title: 3.1.9 omp_set_nested işlevi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: e4afc3aa-bb96-4314-9849-fd5df5f437d9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 68e5898b8b57814a152ca2ce9ced84a9df8190cc
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46414545"
---
# <a name="319-ompsetnested-function"></a>3.1.9 omp_set_nested İşlevi

**Omp_set_nested** işlevini etkinleştirir veya iç içe geçmiş paralellik devre dışı bırakır. Biçimi aşağıdaki gibidir:

```
#include <omp.h>
void omp_set_nested(int nested);
```

Varsa *iç içe geçmiş* iç içe geçmiş 0 olarak değerlendirilen paralellik devre dışıysa, varsayılan ve iç içe geçmiş paralel bölgeleri serileştirilmiş ve geçerli iş parçacığı tarafından yürütüldü. Varsa *iç içe geçmiş* hesaplar için sıfır dışında bir değeri, iç içe geçmiş paralellik etkin ve iç içe paralel bölgeleri, iç içe geçmiş takımlar oluşturmak için ek iş parçacığı dağıtma.

Bu işlev, bir program bölümünden çağrıldığında yukarıda açıklanan etkisi burada **omp_in_parallel** işlev, sıfır döndürür. Programın bir kısmını çağrılır, burada **omp_in_parallel** işlevi sıfır dışında bir değeri döndürür, bu işlevin davranış tanımlanmamıştır.

Bu çağrı, üzerinde önceliğe sahiptir. **OMP_NESTED** ortam değişkeni.

İç içe geçmiş paralellik etkinleştirildiğinde, uygulama tarafından tanımlanan iç içe geçmiş paralel bölgeleri yürütmek için kullanılan iş parçacıklarının sayısı. Sonuç olarak, OpenMP uyumlu uygulamaları, iç içe geçmiş paralellik etkin olsa bile, iç içe geçmiş paralel bölgeleri serileştirmek için izin verilir.

## <a name="cross-references"></a>Başvuruları çapraz:

- **OMP_NESTED** ortam değişkeni, bkz: [bölümü 4.4](../../parallel/openmp/4-4-omp-nested.md) 49 sayfasında.

- **omp_in_parallel** çalışması için bkz: [bölümü 3.1.6](../../parallel/openmp/3-1-6-omp-in-parallel-function.md) 38 sayfasında.