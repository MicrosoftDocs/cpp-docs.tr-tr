---
title: OpenMP veri türleri
ms.date: 10/23/2018
f1_keywords:
- OpenMP data types
- omp_lock_t
- omp_nest_lock_t
helpviewer_keywords:
- OpenMP data types
- omp_lock_t OpenMP data type
- omp_nest_lock_t OpenMP data type
ms.assetid: cf1e1045-4d12-4d03-80b7-d5843b80ef85
ms.openlocfilehash: bacb48194015f8fd6c80a9868af06702deceab6f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50533776"
---
# <a name="openmp-data-types"></a>OpenMP veri türleri

OpenMP API çağrısında kullanılan veri türlerine bağlantılar sağlar.

Standart OpenMP Visual C++ uygulaması, aşağıdaki veri türlerini içerir.

|Veri türü|Açıklama|
|---------|-----------|
|[omp_lock_t](#omp-lock-t)|Bir kilit, kilit olup veya bir iş parçacığının bir kilidi sahibi, durumu tutan bir türü.|
|[omp_nest_lock_t](#omp-nest-lock-t)|Bir kilitleme hakkında bilgi aşağıdaki parçalarını birini tutan bir türü: kilit kullanılabilir ve iş parçacığı kimliğine sahip olan kilidi ve iç içe geçme sayı olup olmadığını.|

## <a name="omp-lock-t"></a>omp_lock_t

Bir kilit, kilit olup veya bir iş parçacığının bir kilidi sahibi, durumu tutan bir türü.

Aşağıdaki işlevler kullanım `omp_lock_t`:

- [omp_init_lock](openmp-functions.md#omp-init-lock)
- [omp_destroy_lock](openmp-functions.md#omp-destroy-lock)
- [omp_set_lock](openmp-functions.md#omp-set-lock)
- [omp_unset_lock](openmp-functions.md#omp-unset-lock)
- [omp_test_lock](openmp-functions.md#omp-test-lock)

Daha fazla bilgi için [3.2 kilit işlevleri](../../../parallel/openmp/3-2-lock-functions.md).

### <a name="example"></a>Örnek

Bkz: [omp_init_lock](openmp-functions.md#omp-init-lock) kullanma örneği için `omp_lock_t`.

## <a name="omp-nest-lock-t"></a>omp_nest_lock_t

Bir kilitleme hakkında bilgi aşağıdaki parçalarını tutan bir türü: kilit kullanılabilir ve iş parçacığı kimliğine sahip olan kilidi ve iç içe geçme sayı olup olmadığını.

Aşağıdaki işlevler kullanım `omp_nest_lock_t`:

- [omp_init_nest_lock](openmp-functions.md#omp-init-nest-lock)
- [omp_destroy_nest_lock](openmp-functions.md#omp-destroy-nest-lock)
- [omp_set_nest_lock](openmp-functions.md#omp-set-nest-lock)
- [omp_unset_nest_lock](openmp-functions.md#omp-unset-nest-lock)
- [omp_test_nest_lock](openmp-functions.md#omp-test-nest-lock)

Daha fazla bilgi için [3.2 kilit işlevleri](../../../parallel/openmp/3-2-lock-functions.md).

### <a name="example"></a>Örnek

Bkz: [omp_init_nest_lock](openmp-functions.md#omp-init-nest-lock) kullanma örneği için `omp_nest_lock_t`.
