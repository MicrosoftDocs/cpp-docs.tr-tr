---
title: F. Yeni özellikler ve açıklamalar sürüm 2.0
ms.date: 01/22/2019
ms.assetid: 0d4beb66-f2d5-468c-8cd3-4b00dcbab061
ms.openlocfilehash: 2e186bbc82f4f43e831dd05cdded2a9e946d1dd2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62362720"
---
# <a name="f-new-features-and-clarifications-in-version-20"></a>F. Yeni özellikler ve açıklamalar sürüm 2.0

Bu ekte, 1.0 sürümünden 2.0 sürümüne taşımada OpenMP C/C++ belirtimi yapılan önemli değişiklikler özetlenmektedir. Aşağıdaki öğeler belirtime eklenen yeni özellikler şunlardır:

- Virgül OpenMP izin [yönergeleri](2-directives.md#21-directive-format).

- Eklenen `num_threads` yan tümcesi. Bu yan tümce için iş parçacığı belirli sayıda istek açmasına olanak sağlar. bir [paralel yapı](2-directives.md#23-parallel-construct).

- [Threadprivate](2-directives.md#271-threadprivate-directive) yönergesi, blok kapsamı statik değişkenler kabul etmek için genişletilmişse.

- C99 değişken uzunluklu dizilerin kullanımı tam türleridir ve tüm türleri şunlardır: izin verilen, listelerini olduğu gibi herhangi bir yere belirtilebilir `private`, `firstprivate`, ve `lastprivate` yan tümceleri (bkz [bölümünde 2.7.2](2-directives.md#272-data-sharing-attribute-clauses)).

- Bir paralel bölgenin içinde özel bir değişken işaretlenebilir [özel](2-directives.md#2721-private) iç içe geçmiş bir yönergede.

- `copyprivate` Yan tümcesi eklendi. Bir değer diğer üyeleri, takımın bir üyesi yayınlamak için özel bir değişken kullanmak için bir mekanizma sağlar. Paylaşılan bir değişken sağlayan (örneğin, farklı bir değişken her düzeyde gerektiren özyineleme) zor olduğunda için paylaşılan bir değişken değeri kullanarak bir alternatiftir. [Copyprivate](2-directives.md#2728-copyprivate) yan tümcesi üzerinde yalnızca görüntülenebilir `single` yönergesi.

- Zamanlama rutinleri eklenmesi [omp_get_wtick](3-run-time-library-functions.md#332-omp_get_wtick-function) ve [omp_get_wtime](3-run-time-library-functions.md#331-omp_get_wtime-function) MPI yordamlara benzer. Bu işlevler, saat zamanlamaları duvar gereklidir.

- Bir ek listesini [uygulama tanımlı davranışlar](e-implementation-defined-behaviors-in-openmp-c-cpp.md) OpenMP C/C++'da eklendi. Bir uygulama tanımlamak ve bu gibi durumlarda davranışını belge için gereklidir.

- Aşağıdaki değişiklikleri açıklamak veya önceki C/C++ OpenMP API Belirtimi özelliklerini düzeltin sunar:

  - Olduğunu açıklamıştır davranışını [omp_set_nested](3-run-time-library-functions.md#319-omp_set_nested-function) ve [omp_set_dynamic](3-run-time-library-functions.md#317-omp_set_dynamic-function) olduğunda `omp_in_parallel` tanımlanmamış sıfır döndürür.

  - Açıklığa kavuşturuldu [yönerge iç içe](2-directives.md#29-directive-nesting) paralel iç içe kullanıldığında.

  - [Başlatma kilitleme](3-run-time-library-functions.md#321-omp_init_lock-and-omp_init_nest_lock-functions) ve [kilit yok etme](3-run-time-library-functions.md#322-omp_destroy_lock-and-omp_destroy_nest_lock-functions) bir paralel bölgenin içinde işlevler çağrılabilir.

  - Yeni örnekler eklenmiştir [ek A](a-examples.md).