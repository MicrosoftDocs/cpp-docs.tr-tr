---
title: "OpenMP işlevleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: a55a2e5c-a260-44ee-bbd6-de7e2351b384
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: caa41947f43189f52333106f80cce6f58b921f8f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="openmp-functions"></a>OpenMP İşlevleri
OpenMP API çağrısında kullanılan işlevler için bağlantılar sağlar.  
  
 Standart OpenMP Visual C++ uygulaması aşağıdaki işlevleri içerir.  
  
|İşlev|Açıklama|  
|--------------|-----------------|  
|[omp_destroy_lock](../../../parallel/openmp/reference/omp-destroy-lock.md)|Kilit uninitializes.|  
|[omp_destroy_nest_lock](../../../parallel/openmp/reference/omp-destroy-nest-lock.md)|Nestable kilit uninitializes.|  
|[omp_get_dynamic](../../../parallel/openmp/reference/omp-get-dynamic.md)|Çalışma zamanı tarafından ayarlanabilir sonraki paralel bölgede kullanılabilir iş parçacığı sayısını belirten bir değer döndürür.|  
|[omp_get_max_threads](../../../parallel/openmp/reference/omp-get-max-threads.md)|Eşit veya bundan büyük bir paralel bölge olmadan, kullanılabilir olacak iş parçacığı sayısı bir tamsayı döndürür [num_threads](../../../parallel/openmp/reference/num-threads.md) bu noktada kodda tanımlanmadı.|  
|[omp_get_nested](../../../parallel/openmp/reference/omp-get-nested.md)|İç içe geçmiş paralellik etkin olup olmadığını belirten bir değer döndürür.|  
|[omp_get_num_procs](../../../parallel/openmp/reference/omp-get-num-procs.md)|İşlevi çağrıldığında kullanılabilir işlemci sayısını döndürür.|  
|[omp_get_num_threads](../../../parallel/openmp/reference/omp-get-num-threads.md)|İş parçacığı sayısını paralel bölgede döndürür.|  
|[omp_get_thread_num](../../../parallel/openmp/reference/omp-get-thread-num.md)|Kendi iş parçacığı ekibi içinde iş parçacığının iş parçacığı sayısını döndürür.|  
|[omp_get_wtick](../../../parallel/openmp/reference/omp-get-wtick.md)|İşlemci saat vuruşlarını saniye sayısını döndürür.|  
|[omp_get_wtime](../../../parallel/openmp/reference/omp-get-wtime.md)|Bazı noktasından bir değer süreyi saniye cinsinden geçen döndürür.|  
|[omp_in_parallel](../../../parallel/openmp/reference/omp-in-parallel.md)|Paralel bir bölge içinde çağrıldıklarında sıfır olmayan bir değer döndürür.|  
|[omp_init_lock](../../../parallel/openmp/reference/omp-init-lock.md)|Basit bir kilit başlatır.|  
|[omp_init_nest_lock](../../../parallel/openmp/reference/omp-init-nest-lock.md)|Kilit başlatır.|  
|[omp_set_dynamic](../../../parallel/openmp/reference/omp-set-dynamic.md)|Çalışma zamanı tarafından düzenlenip düzenlenmediğini sonraki paralel bölgede kullanılabilir iş parçacığı sayısını gösterir.|  
|[omp_set_lock](../../../parallel/openmp/reference/omp-set-lock.md)|Kilit kullanılabilir oluncaya kadar blokları yürütme iş parçacığı.|  
|[omp_set_nest_lock](../../../parallel/openmp/reference/omp-set-nest-lock.md)|Kilit kullanılabilir oluncaya kadar blokları yürütme iş parçacığı.|  
|[omp_set_nested](../../../parallel/openmp/reference/omp-set-nested.md)|İç içe geçmiş paralellik etkinleştirir.|  
|[omp_set_num_threads](../../../parallel/openmp/reference/omp-set-num-threads.md)|İş parçacığı sayısını sonraki paralel bölgelerde tarafından geçersiz kılınmadığı sürece ayarlar bir [num_threads](../../../parallel/openmp/reference/num-threads.md) yan tümcesi.|  
|[omp_test_lock](../../../parallel/openmp/reference/omp-test-lock.md)|Kilit ayarlamaya çalışır, ancak iş parçacığı engellemez.|  
|[omp_test_nest_lock](../../../parallel/openmp/reference/omp-test-nest-lock.md)|Nestable kilit ayarlamaya çalışır, ancak iş parçacığı engellemez.|  
|[omp_unset_lock](../../../parallel/openmp/reference/omp-unset-lock.md)|Bir kilidi serbest bırakır.|  
|[omp_unset_nest_lock](../../../parallel/openmp/reference/omp-unset-nest-lock.md)|Nestable bir kilidi serbest bırakır.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kitaplık Başvurusu](../../../parallel/openmp/reference/openmp-library-reference.md)