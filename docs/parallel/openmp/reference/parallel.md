---
title: Paralel | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- parallel
dev_langs:
- C++
helpviewer_keywords:
- parallel OpenMP directive
ms.assetid: b8e90073-e85b-4d39-8ed8-0364441794fb
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9293a70ce0615adf1e40bcb19b1706d9e39d4cca
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="parallel"></a>parallel
Paralel olarak birden çok iş parçacığı tarafından yürütülen kod bir paralel bölge tanımlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
#pragma omp parallel [clauses]  
{  
   code_block  
}  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Burada,  
  
 `clause` (isteğe bağlı)  
 Sıfır veya daha çok yan tümceleri.  Tarafından desteklenen yan tümceleri bir listesi için Açıklamalar bölümüne bakın **paralel**.  
  
## <a name="remarks"></a>Açıklamalar  
 **Paralel** yönergesi aşağıdaki OpenMP yan tümceleri destekler:  
  
-   [copyin](../../../parallel/openmp/reference/copyin.md)  
  
-   [default](../../../parallel/openmp/reference/default-openmp.md)  
  
-   [firstprivate](../../../parallel/openmp/reference/firstprivate.md)  
  
-   [if](../../../parallel/openmp/reference/if-openmp.md)  
  
-   [num_threads](../../../parallel/openmp/reference/num-threads.md)  
  
-   [private](../../../parallel/openmp/reference/private-openmp.md)  
  
-   [reduction](../../../parallel/openmp/reference/reduction.md)  
  
-   [Paylaşılan](../../../parallel/openmp/reference/shared-openmp.md)  
  
 **Paralel** ile de kullanılabilir [bölümleri](../../../parallel/openmp/reference/sections-openmp.md) ve [için](../../../parallel/openmp/reference/for-openmp.md) yönergeleri.  
  
 Daha fazla bilgi için bkz: [2.3 parallel yapı](../../../parallel/openmp/2-3-parallel-construct.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, iş parçacığı sayısını ayarlayın ve paralel bölge tanımlamasına gösterilmektedir. Varsayılan olarak, iş parçacığı sayısını makinedeki mantıksal işlemci sayısına eşittir. Örneğin, hiper iş parçacığı etkin olan bir fiziksel işlemci sahip bir makine varsa, iki mantıksal işlemci ve bu nedenle, iki iş parçacığı olması.  
  
```  
// omp_parallel.cpp  
// compile with: /openmp   
#include <stdio.h>  
#include <omp.h>  
  
int main() {  
   #pragma omp parallel num_threads(4)  
   {  
      int i = omp_get_thread_num();  
      printf_s("Hello from thread %d\n", i);  
   }  
}  
```  
  
```Output  
Hello from thread 0  
Hello from thread 1  
Hello from thread 2  
Hello from thread 3  
```  
  
## <a name="comment"></a>Yorum  
 Çıkış sırası farklı makinelerde değişebilir unutmayın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yönergeler](../../../parallel/openmp/reference/openmp-directives.md)