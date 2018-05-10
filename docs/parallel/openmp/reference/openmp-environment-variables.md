---
title: OpenMP ortam değişkenleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
dev_langs:
- C++
ms.assetid: 2178ce2b-ffa1-45ec-a455-64437711d15d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 02248b7725f2a4312f26984c798e7248463d2615
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
---
# <a name="openmp-environment-variables"></a>OpenMP Ortam Değişkenleri
OpenMP API çağrısında kullanılan ortam değişkenleri için bağlantılar sağlar.  
  
 Standart OpenMP Visual C++ uygulaması aşağıdaki ortam değişkenleri içerir. Bu ortam değişkenleri program başlangıcında okunur ve çalışma zamanında değerlerine değişiklikler göz ardı (örneğin, kullanarak [_putenv, _wputenv](../../../c-runtime-library/reference/putenv-wputenv.md)).  
  
|Ortam değişkeni|Açıklama|  
|--------------------------|-----------------|  
|[OMP_DYNAMIC](../../../parallel/openmp/reference/omp-dynamic.md)|Çalışma zamanı OpenMP paralel bir bölgede iş parçacığı sayısını ayarlayabilirsiniz olup olmadığını belirtir.|  
|[OMP_NESTED](../../../parallel/openmp/reference/omp-nested.md)|İç içe geçmiş paralellik etkin veya ile devre dışı sürece iç içe geçmiş paralellik, etkinleştirilip etkinleştirilmediğini belirtir `omp_set_nested`.|  
|[OMP_NUM_THREADS](../../../parallel/openmp/reference/omp-num-threads.md)|İş parçacığı sayısı tarafından geçersiz kılınmadığı sürece paralel bölgede ayarlar [omp_set_num_threads](../../../parallel/openmp/reference/omp-set-num-threads.md) veya [num_threads](../../../parallel/openmp/reference/num-threads.md).|  
|[OMP_SCHEDULE](../../../parallel/openmp/reference/omp-schedule.md)|Davranışını değiştiren [zamanlama](../../../parallel/openmp/reference/schedule.md) yan tümcesi olduğunda `schedule(runtime)` içinde belirtilen bir `for` veya `parallel for` yönergesi.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kitaplık Başvurusu](../../../parallel/openmp/reference/openmp-library-reference.md)