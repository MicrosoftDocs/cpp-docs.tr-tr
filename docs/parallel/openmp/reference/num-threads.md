---
title: num_threads | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- num_threads
dev_langs:
- C++
helpviewer_keywords:
- num_threads OpenMP clause
ms.assetid: 09a56fc8-25c7-43e4-bbb5-71cb955d0b93
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e7dd57950d083c4f89ee2aa5962ad1e07a55a9a8
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
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
  
 `num_threads` Aşağıdaki yönergeleri için geçerlidir:  
  
-   [parallel](../../../parallel/openmp/reference/parallel.md)  
  
-   [for](../../../parallel/openmp/reference/for-openmp.md)  
  
-   [Bölümler](../../../parallel/openmp/reference/sections-openmp.md)  
  
 Daha fazla bilgi için bkz: [2.3 parallel yapı](../../../parallel/openmp/2-3-parallel-construct.md).  
  
## <a name="example"></a>Örnek  
 Bkz: [paralel](../../../parallel/openmp/reference/parallel.md) kullanma örneği için `num_threads` yan tümcesi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yan Tümceler](../../../parallel/openmp/reference/openmp-clauses.md)