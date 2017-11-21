---
title: "3.1.3 omp_get_max_threads işlevi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 5548897c-546e-4d19-b37b-a76f6b30a0a9
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: e021f0873aa94f53a1218a3278a744a0c7740e65
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="313-ompgetmaxthreads-function"></a>3.1.3 omp_get_max_threads İşlevi
**Omp_get_max_threads** işlevi, en az, paralel bir bölge olmadan, ekip oluşturmak için kullanılacak iş parçacığı sayısı kadar büyük olması garanti bir tamsayı döndürür bir **num_threads** yan tümcesi Bu noktada kodda karşılaştı için yoktu. Biçimi aşağıdaki gibidir:  
  
```  
#include <omp.h>  
int omp_get_max_threads(void);  
```  
  
 Aşağıdaki alt sınır değeri üzerinde yoğunlaştıracaklardır **omp_get_max_threads**:  
  
```  
  
threads-used-for-next-team  
 <= omp_get_max_threads  
  
```  
  
 Bir sonraki paralel bölgesi kullanıyorsa unutmayın **num_threads** iş parçacıklarını garanti sonucu çoğulluğun alt sınırı üzerinde belirli sayıda istek için yan tümceyi **omp_get_max_threads** uzun hiçbir ayrı tutma.  
  
 **Omp_get_max_threads** işlevin dönüş değeri, dinamik olarak sonraki paralel bölge biçimlendirilmiş ekibindeki tüm iş parçacıkları için yeterli depolama alanı ayırmak için kullanılabilir.  
  
## <a name="cross-references"></a>Çapraz referanslar:  
  
-   **omp_get_num_threads** işlev, bkz: [bölüm 3.1.2](../../parallel/openmp/3-1-2-omp-get-num-threads-function.md) sayfasında 37'si.  
  
-   **omp_set_num_threads** işlev, bkz: [bölüm 3.1.1](../../parallel/openmp/3-1-1-omp-set-num-threads-function.md) sayfasında 36.  
  
-   **omp_set_dynamic** işlev, bkz: [bölüm 3.1.7](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md) sayfasında 39.  
  
-   **num_threads** yan tümcesi, bkz: [bölüm 2.3](../../parallel/openmp/2-3-parallel-construct.md) sayfasında 8.