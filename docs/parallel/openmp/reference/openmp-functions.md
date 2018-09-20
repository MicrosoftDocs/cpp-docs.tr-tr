---
title: OpenMP işlevleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
dev_langs:
- C++
ms.assetid: a55a2e5c-a260-44ee-bbd6-de7e2351b384
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a5daa7737f63df437f31f349a85811befe0c8f5b
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46425606"
---
# <a name="openmp-functions"></a>OpenMP İşlevleri

OpenMP API çağrısında kullanılan işlevlere bağlantılar sağlar.

Standart OpenMP Visual C++ uygulaması, aşağıdaki işlevleri içerir.

|İşlev|Açıklama|
|--------------|-----------------|
|[omp_destroy_lock](../../../parallel/openmp/reference/omp-destroy-lock.md)|Kilit başlamasını iptal eder.|
|[omp_destroy_nest_lock](../../../parallel/openmp/reference/omp-destroy-nest-lock.md)|Nestable kilit başlamasını iptal eder.|
|[omp_get_dynamic](../../../parallel/openmp/reference/omp-get-dynamic.md)|Çalışma zamanı tarafından ayarlanabilir izleyen bir paralel bölgenin içinde kullanılabilir iş parçacığı sayısını gösteren bir değer döndürür.|
|[omp_get_max_threads](../../../parallel/openmp/reference/omp-get-max-threads.md)|Bir paralel bölgenin olmadan, kullanılabilir hale gelir, iş parçacığı sayısından büyük veya ona eşit bir tamsayı döndürür [num_threads](../../../parallel/openmp/reference/num-threads.md) o noktada kod tanımlanmadı.|
|[omp_get_nested](../../../parallel/openmp/reference/omp-get-nested.md)|İç içe geçmiş paralellik etkin olup olmadığını gösteren bir değer döndürür.|
|[omp_get_num_procs](../../../parallel/openmp/reference/omp-get-num-procs.md)|İşlev çağrıldığında, kullanılabilir işlemci sayısını döndürür.|
|[omp_get_num_threads](../../../parallel/openmp/reference/omp-get-num-threads.md)|Paralel bölgenin içinde iş parçacıklarının sayısını döndürür.|
|[omp_get_thread_num](../../../parallel/openmp/reference/omp-get-thread-num.md)|Kendi iş parçacığı takım içinde iş parçacığının iş parçacığı sayısını döndürür.|
|[omp_get_wtick](../../../parallel/openmp/reference/omp-get-wtick.md)|İşlemci saatin tik takları saniye sayısını döndürür.|
|[omp_get_wtime](../../../parallel/openmp/reference/omp-get-wtime.md)|Belirli bir noktada bir değer süresini saniye cinsinden geçen döndürür.|
|[omp_in_parallel](../../../parallel/openmp/reference/omp-in-parallel.md)|Bir paralel bölgenin içinde çağrılırsa sıfır döndürür.|
|[omp_init_lock](../../../parallel/openmp/reference/omp-init-lock.md)|Basit bir kilit başlatır.|
|[omp_init_nest_lock](../../../parallel/openmp/reference/omp-init-nest-lock.md)|Kilit başlatır.|
|[omp_set_dynamic](../../../parallel/openmp/reference/omp-set-dynamic.md)|Sonraki bir paralel bölgenin içinde kullanılabilir iş parçacığı sayısını çalışma zamanı tarafından düzenlenip düzenlenmediğini gösterir.|
|[omp_set_lock](../../../parallel/openmp/reference/omp-set-lock.md)|Kilit kullanılabilir oluncaya kadar blokları yürütme iş parçacığı.|
|[omp_set_nest_lock](../../../parallel/openmp/reference/omp-set-nest-lock.md)|Kilit kullanılabilir oluncaya kadar blokları yürütme iş parçacığı.|
|[omp_set_nested](../../../parallel/openmp/reference/omp-set-nested.md)|İç içe geçmiş paralellik etkinleştirir.|
|[omp_set_num_threads](../../../parallel/openmp/reference/omp-set-num-threads.md)|İş parçacığı sayısı tarafından geçersiz kılınmadığı sürece sonraki paralel bölgelerde ayarlar bir [num_threads](../../../parallel/openmp/reference/num-threads.md) yan tümcesi.|
|[omp_test_lock](../../../parallel/openmp/reference/omp-test-lock.md)|Kilit ayarlamaya çalışır, ancak yürütme iş parçacığını engellemez.|
|[omp_test_nest_lock](../../../parallel/openmp/reference/omp-test-nest-lock.md)|Nestable kilit ayarlamaya çalışır ancak yürütme iş parçacığını engellemez.|
|[omp_unset_lock](../../../parallel/openmp/reference/omp-unset-lock.md)|Bir kilidi serbest bırakır.|
|[omp_unset_nest_lock](../../../parallel/openmp/reference/omp-unset-nest-lock.md)|Nestable kilit serbest bırakır.|

## <a name="see-also"></a>Ayrıca Bkz.

[Kitaplık Başvurusu](../../../parallel/openmp/reference/openmp-library-reference.md)