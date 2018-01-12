---
title: num_threads | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: num_threads
dev_langs: C++
helpviewer_keywords: num_threads OpenMP clause
ms.assetid: 09a56fc8-25c7-43e4-bbb5-71cb955d0b93
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7289a843c33fbc9ba23d6006997dea8e09ba7c79
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="numthreads"></a>num_threads
İş parçacığı sayısı, iş parçacığı ekip olarak ayarlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
num_threads(num)  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Burada,  
  
 `num`  
 İş parçacığı sayısı  
  
## <a name="remarks"></a>Açıklamalar  
 `num_threads` Yan tümcesine sahip ile aynı işlevselliği [omp_set_num_threads](../../../parallel/openmp/reference/omp-set-num-threads.md) işlevi.  
  
 `num_threads`Aşağıdaki yönergeleri için geçerlidir:  
  
-   [parallel](../../../parallel/openmp/reference/parallel.md)  
  
-   [for](../../../parallel/openmp/reference/for-openmp.md)  
  
-   [bölümler](../../../parallel/openmp/reference/sections-openmp.md)  
  
 Daha fazla bilgi için bkz: [2.3 parallel yapı](../../../parallel/openmp/2-3-parallel-construct.md).  
  
## <a name="example"></a>Örnek  
 Bkz: [paralel](../../../parallel/openmp/reference/parallel.md) kullanma örneği için `num_threads` yan tümcesi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yan Tümceler](../../../parallel/openmp/reference/openmp-clauses.md)