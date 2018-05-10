---
title: 3.1.4 omp_get_thread_num işlevi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 5220402b-c109-4b1f-ba79-002e93d08617
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fad749b91470f7834169fe8ed734f1d627aa228e
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
---
# <a name="314-ompgetthreadnum-function"></a>3.1.4 omp_get_thread_num İşlevi
`omp_get_thread_num` İşlevi iş parçacığı sayısı, kendi takım içindeki işlevi yürütme iş parçacığı döndürür. 0 arasında iş parçacığı sayısı kalıyor ve **omp_get_num_threads()**-1, (dahil) arasındadır. Takım ana iş parçacığı 0 parçacığıdır.  
  
 Biçimi aşağıdaki gibidir:  
  
```  
#include <omp.h>  
int omp_get_thread_num(void);  
```  
  
 Bir seri bölgesinden çağrıldıklarında `omp_get_thread_num` 0 döndürür. Bu işlev, serileştirilen iç içe geçmiş bir paralel bölge içinde çağrılır, 0 döndürür.  
  
## <a name="cross-references"></a>Çapraz referanslar:  
  
-   `omp_get_num_threads` işlev, bkz: [bölüm 3.1.2](../../parallel/openmp/3-1-2-omp-get-num-threads-function.md) sayfasında 37'si.