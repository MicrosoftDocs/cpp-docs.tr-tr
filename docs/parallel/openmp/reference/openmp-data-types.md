---
title: OpenMP veri türleri | Microsoft Docs
ms.custom: ''
ms.date: 10/23/2018
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- OpenMP data types
- omp_lock_t
- omp_nest_lock_t
dev_langs:
- C++
helpviewer_keywords:
- OpenMP data types
- omp_lock_t OpenMP data type
- omp_nest_lock_t OpenMP data type
ms.assetid: cf1e1045-4d12-4d03-80b7-d5843b80ef85
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 254dffebc258867088f738b10a11bf48d31bd0a4
ms.sourcegitcommit: c045c3a7e9f2c7e3e0de5b7f9513e41d8b6d19b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2018
ms.locfileid: "49990077"
---
# <a name="openmp-data-types"></a>OpenMP Veri Türleri

OpenMP API çağrısında kullanılan veri türlerine bağlantılar sağlar.

Standart OpenMP Visual C++ uygulaması, aşağıdaki veri türlerini içerir.

Veri türü                           | Açıklama
----------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
[omp_lock_t](#omp-lock-t)           | Bir kilit, kilit olup veya bir iş parçacığının bir kilidi sahibi, durumu tutan bir türü.
[omp_nest_lock_t](#omp-nest-lock-t) | Bir kilitleme hakkında bilgi aşağıdaki parçalarını birini tutan bir türü: kilit kullanılabilir ve iş parçacığı kimliğine sahip olan kilidi ve iç içe geçme sayı olup olmadığını.

## <a name="omp-lock-t"></a>omp_lock_t

Bir kilit, kilit olup veya bir iş parçacığının bir kilidi sahibi, durumu tutan bir türü.

Aşağıdaki işlevler kullanım `omp_lock_t`:

- [omp_init_lock](../../../parallel/openmp/reference/omp-init-lock.md)
- [omp_destroy_lock](../../../parallel/openmp/reference/omp-destroy-lock.md)
- [omp_set_lock](../../../parallel/openmp/reference/omp-set-lock.md)
- [omp_unset_lock](../../../parallel/openmp/reference/omp-unset-lock.md)
- [omp_test_lock](../../../parallel/openmp/reference/omp-test-lock.md)

Daha fazla bilgi için [3.2 kilit işlevleri](../../../parallel/openmp/3-2-lock-functions.md).

### <a name="example"></a>Örnek

Bkz: [omp_init_lock](../../../parallel/openmp/reference/omp-init-lock.md) kullanma örneği için `omp_lock_t`.

## <a name="omp-nest-lock-t"></a>omp_nest_lock_t

Bir kilitleme hakkında bilgi aşağıdaki parçalarını tutan bir türü: kilit kullanılabilir ve iş parçacığı kimliğine sahip olan kilidi ve iç içe geçme sayı olup olmadığını.

Aşağıdaki işlevler kullanım `omp_nest_lock_t`:

- [omp_init_nest_lock](../../../parallel/openmp/reference/omp-init-nest-lock.md)
- [omp_destroy_nest_lock](../../../parallel/openmp/reference/omp-destroy-nest-lock.md)
- [omp_set_nest_lock](../../../parallel/openmp/reference/omp-set-nest-lock.md)
- [omp_unset_nest_lock](../../../parallel/openmp/reference/omp-unset-nest-lock.md)
- [omp_test_nest_lock](../../../parallel/openmp/reference/omp-test-nest-lock.md)

Daha fazla bilgi için [3.2 kilit işlevleri](../../../parallel/openmp/3-2-lock-functions.md).

### <a name="example"></a>Örnek

Bkz: [omp_init_nest_lock](../../../parallel/openmp/reference/omp-init-nest-lock.md) kullanma örneği için `omp_nest_lock_t`.
