---
title: "F Yeni özellikler ve açıklamalar sürüm 2.0 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: 0d4beb66-f2d5-468c-8cd3-4b00dcbab061
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b9a661f183816fec0f7a71c990f1508338100f4d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="f-new-features-and-clarifications-in-version-20"></a>F Yeni özellikler ve açıklamalar sürüm 2.0
Bu ekte sürüm 2.0 sürüm 1.0 taşımada OpenMP C/C++ belirtimi anahtar değişiklikler özetlenmektedir. Aşağıdaki öğeler belirtimine eklenen yeni özellikler şunlardır:  
  
-   Virgül OpenMP yönergeleri verilir ([bölüm 2.1](../../parallel/openmp/2-1-directive-format.md) sayfasında 7).  
  
-   Eklenmesi `num_threads` yan tümcesi. Bu yan tümce paralel bir yapı için iş parçacığı belirli sayıda istek sağlar ([bölüm 2.3](../../parallel/openmp/2-3-parallel-construct.md) sayfasında 8).  
  
-   `threadprivate` Yönergesi genişletilmişse statik blok kapsamı değişkenleri kabul etmek için ([bölüm 2.7.1](../../parallel/openmp/2-7-1-threadprivate-directive.md) sayfasında 23).  
  
-   C99 değişken uzunlukta diziler tam türleri ve bu nedenle herhangi bir yere tam türleri izin verilir, örneğin listelerinde belirtilebilir `private`, `firstprivate`, ve `lastprivate` yan tümceleri ([bölüm 2.7.2](../../parallel/openmp/2-7-2-data-sharing-attribute-clauses.md) sayfasında 25).  
  
-   Özel bir değişken paralel bir bölgede yeniden iç içe geçmiş yönergesinde özel olarak işaretlenebilir ([bölüm 2.7.2.1](../../parallel/openmp/2-7-2-1-private.md) sayfasında 25).  
  
-   `copyprivate` Yan tümcesi eklendi. Bir değer diğer üyeleri için bir ekibin üyesi yayınlamak için özel bir değişken kullanmak için bir mekanizma sağlar. Paylaşılan bir değişken sağlayan (örneğin, her düzeyde farklı değişken gerektiren özyineleme) zor olacaktır, paylaşılan bir değişken değeri bir alternatifidir. `copyprivate` Yan tümcesi üzerinde yalnızca görünebilir **tek** yönergesi ([bölüm 2.7.2.8](../../parallel/openmp/2-7-2-8-copyprivate.md) sayfasında 32).  
  
-   Zamanlama rutinleri eklenmesi `omp_get_wtick` ve `omp_get_wtime` MPI yordamları benzer. Bu işlevler duvar saati zamanlamaları gerçekleştirmek için gerekli olan ([bölüm 3.3.1](../../parallel/openmp/3-3-1-omp-get-wtime-function.md) sayfasında 44 ve [bölüm 3.3.2](../../parallel/openmp/3-3-2-omp-get-wtick-function.md) sayfasında 45).  
  
-   Uygulama tanımlı davranış OpenMP C/C++ listesini içeren bir ek eklendi. Bir uygulama tanımlamak ve bu gibi durumlarda davranışını belgelemek için gereklidir ([ek E](../../parallel/openmp/e-implementation-defined-behaviors-in-openmp-c-cpp.md) sayfasında 97).  
  
-   Açıklamak veya C/C++ için önceki OpenMP API belirtiminde özellikleri düzeltmek için aşağıdaki değişiklikleri sunar:  
  
    -   Olduğunu açıklamıştır davranışını `omp_set_nested` ve `omp_set_dynamic` zaman `omp_in_parallel` döndürür sıfır olmayan tanımlanmadı ([bölüm 3.1.7](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md) sayfasında 39 ve [bölüm 3.1.9](../../parallel/openmp/3-1-9-omp-set-nested-function.md) sayfasında 40).  
  
    -   İç içe geçmiş paralel kullanıldığında yönerge iç içe geçme açıklığa kavuşturuldu ([bölüm 2.9](../../parallel/openmp/2-9-directive-nesting.md) sayfasında 33).  
  
    -   Paralel bir bölgede kilit başlatma ve kilit yok etme işlevler çağrılabilir ([bölüm 3.2.1](../../parallel/openmp/3-2-1-omp-init-lock-and-omp-init-nest-lock-functions.md) sayfasında 42 ve [bölüm 3.2.2](../../parallel/openmp/3-2-2-omp-destroy-lock-and-omp-destroy-nest-lock-functions.md) sayfasında 42).  
  
    -   Yeni örnekler eklenmiştir ([ek A](../../parallel/openmp/a-examples.md) sayfasında 51).