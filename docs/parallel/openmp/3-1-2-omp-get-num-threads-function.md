---
title: 3.1.2 omp_get_num_threads işlevi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: bcdd76e2-d96b-4884-ac8f-e55fc0c42801
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: df01d571b67ff6d252d85128fcc8c1d26a6e94a9
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
---
# <a name="312-ompgetnumthreads-function"></a>3.1.2 omp_get_num_threads İşlevi
**Omp_get_num_threads** işlevi döndürür iş parçacığı sayısı şu anda içinden çağırıldığında paralel bölge yürütme takım. Biçimi aşağıdaki gibidir:  
  
```  
#include <omp.h>  
int omp_get_num_threads(void);  
```  
  
 **Num_threads** yan tümcesi **omp_set_num_threads** işlevini ve **OMP_NUM_THREADS** ortam değişkeni denetleyen bir takım içindeki iş parçacığı sayısı.  
  
 İş parçacığı sayısı kullanıcı tarafından açıkça ayarlanmadı, uygulama tanımlı varsayılandır. Bu işlev en yakın kapsayan bağlar **paralel** yönergesi. Bir program seri bir kısmı veya serileştirilir iç içe geçmiş bir paralel bölge çağırdıysanız, bu işlev 1 döndürür.  
  
## <a name="cross-references"></a>Çapraz referanslar:  
  
-   **OMP_NUM_THREADS** ortam değişkeni, bkz: [bölüm 4.2](../../parallel/openmp/4-2-omp-num-threads.md) sayfasında 48.  
  
-   **num_threads** yan tümcesi, bkz: [bölüm 2.3](../../parallel/openmp/2-3-parallel-construct.md) sayfasında 8.  
  
-   **Paralel** oluşturmak için bkz: [bölüm 2.3](../../parallel/openmp/2-3-parallel-construct.md) sayfasında 8.