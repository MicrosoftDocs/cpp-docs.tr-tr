---
title: F. Yeni özellikler ve açıklamalar sürüm 2.0 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 0d4beb66-f2d5-468c-8cd3-4b00dcbab061
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d15cbbf60609208a200bd73536d0ebdc8a714f7e
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46373509"
---
# <a name="f-new-features-and-clarifications-in-version-20"></a>F. Yeni özellikler ve açıklamalar sürüm 2.0

Bu ekte, 1.0 sürümünden 2.0 sürümüne taşımada OpenMP C/C++ belirtimi yapılan önemli değişiklikler özetlenmektedir. Aşağıdaki öğeler belirtime eklenen yeni özellikler şunlardır:

- Virgül OpenMP yönergeleri verilir ([bölümü 2.1](../../parallel/openmp/2-1-directive-format.md) sayfasında 7).

- Eklenen `num_threads` yan tümcesi. Bu yan tümce paralel bir yapı için iş parçacıklarının belirli sayıda istek sağlar ([bölümü 2.3](../../parallel/openmp/2-3-parallel-construct.md) sayfasında 8).

- `threadprivate` Yönergesi, blok kapsamı statik değişkenler kabul etmek için genişletilmişse ([bölümü 2.7.1](../../parallel/openmp/2-7-1-threadprivate-directive.md) sayfasında 23).

- C99 değişken uzunluklu dizilerin kullanımı tam türleri ve bu nedenle herhangi bir yerde tam türlere izin verilir, örneğin listelerinde belirtilebilir `private`, `firstprivate`, ve `lastprivate` yan tümceleri ([bölümü 2.7.2](../../parallel/openmp/2-7-2-data-sharing-attribute-clauses.md) sayfasında 25).

- Özel bir değişken bir paralel bölgenin içinde iç içe geçmiş bir yönergesinde yeniden özel olarak işaretlenebilir ([bölümü 2.7.2.1](../../parallel/openmp/2-7-2-1-private.md) sayfasında 25).

- `copyprivate` Yan tümcesi eklendi. Bir değer diğer üyeleri, takımın bir üyesi yayınlamak için özel bir değişken kullanmak için bir mekanizma sağlar. Paylaşılan bir değişken sağlayan (örneğin, farklı bir değişken her düzeyde gerektiren özyineleme) zor olduğunda için paylaşılan bir değişken değeri kullanarak bir alternatiftir. `copyprivate` Yan tümcesi üzerinde yalnızca görüntülenebilir **tek** yönergesi ([bölümü 2.7.2.8](../../parallel/openmp/2-7-2-8-copyprivate.md) sayfasında 32).

- Zamanlama rutinleri eklenmesi `omp_get_wtick` ve `omp_get_wtime` MPI yordamlara benzer. Bu işlevler duvar saati zamanlamaları gerçekleştirmek için gerekli olan ([3.3.1 bölümünde](../../parallel/openmp/3-3-1-omp-get-wtime-function.md) sayfasında 44 ve [bölümü 3.3.2](../../parallel/openmp/3-3-2-omp-get-wtick-function.md) sayfasında 45).

- OpenMP C/C++'daki uygulama tanımlı davranışlar listesini içeren bir ek eklendi. Bir uygulama tanımlamak ve bu gibi durumlarda davranışını belge için gereklidir ([ek E](../../parallel/openmp/e-implementation-defined-behaviors-in-openmp-c-cpp.md) sayfasında 97).

- Aşağıdaki değişiklikleri açıklamak veya önceki C/C++ OpenMP API Belirtimi özelliklerini düzeltin sunar:

   - Olduğunu açıklamıştır davranışını `omp_set_nested` ve `omp_set_dynamic` olduğunda `omp_in_parallel` tanımlanmamış sıfır döndürür ([bölümü 3.1.7](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md) sayfasında 39 ve [bölümü 3.1.9](../../parallel/openmp/3-1-9-omp-set-nested-function.md) sayfasında 40).

   - Paralel iç içe kullanıldığında yönerge iç içe açıklığa kavuşturuldu ([bölümü 2.9](../../parallel/openmp/2-9-directive-nesting.md) sayfasında 33).

   - Kilit başlatma ve kilit yok etme işlevleri bir paralel bölgenin içinde çağrılabilir ([bölümü 3.2.1](../../parallel/openmp/3-2-1-omp-init-lock-and-omp-init-nest-lock-functions.md) sayfasında 42 ve [bölümü 3.2.2](../../parallel/openmp/3-2-2-omp-destroy-lock-and-omp-destroy-nest-lock-functions.md) sayfasında 42).

   - Yeni örnekler eklendi ([ek A](../../parallel/openmp/a-examples.md) sayfasında 51).