---
title: "3.1.4 omp_get_thread_num işlevi | Microsoft Docs"
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
ms.assetid: 5220402b-c109-4b1f-ba79-002e93d08617
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b7b968d103631dafcdd2132cb749ae8feed30085
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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
  
-   `omp_get_num_threads`işlev, bkz: [bölüm 3.1.2](../../parallel/openmp/3-1-2-omp-get-num-threads-function.md) sayfasında 37'si.