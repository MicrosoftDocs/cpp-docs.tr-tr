---
title: Paralel | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- parallel
dev_langs:
- C++
helpviewer_keywords:
- parallel OpenMP directive
ms.assetid: b8e90073-e85b-4d39-8ed8-0364441794fb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1c8b1466eae343b6c644b6ecfbd919c3241259bf
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45705971"
---
# <a name="parallel"></a>parallel
Birden çok iş parçacığı paralel olarak yürütülen kodu bir paralel bölgenin tanımlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
#pragma omp parallel [clauses]  
{  
   code_block  
}  
```  
  
## <a name="arguments"></a>Arguments

*Yan tümcesi*<br/>
(İsteğe bağlı) Sıfır veya daha fazla tümceciği.  Tarafından desteklenen yan tümce listesi için Açıklamalar bölümüne bakın **paralel**.  
  
## <a name="remarks"></a>Açıklamalar  
 **Paralel** yönergesi aşağıdaki OpenMP yan tümceleri destekler:  
  
-   [copyin](../../../parallel/openmp/reference/copyin.md)  
  
-   [default](../../../parallel/openmp/reference/default-openmp.md)  
  
-   [firstprivate](../../../parallel/openmp/reference/firstprivate.md)  
  
-   [Eğer](../../../parallel/openmp/reference/if-openmp.md)  
  
-   [num_threads](../../../parallel/openmp/reference/num-threads.md)  
  
-   [private](../../../parallel/openmp/reference/private-openmp.md)  
  
-   [reduction](../../../parallel/openmp/reference/reduction.md)  
  
-   [Paylaşılan](../../../parallel/openmp/reference/shared-openmp.md)  
  
 **Paralel** ile de kullanılabilir [bölümleri](../../../parallel/openmp/reference/sections-openmp.md) ve [için](../../../parallel/openmp/reference/for-openmp.md) yönergeleri.  
  
 Daha fazla bilgi için [2.3 parallel yapı](../../../parallel/openmp/2-3-parallel-construct.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, iş parçacığı sayısını ayarlayın ve bir paralel bölgenin tanımlamak gösterilmektedir. Varsayılan olarak, iş parçacığı sayısı makinede mantıksal işlemci sayısı eşittir. Örneğin, bir makine hiper iş parçacıklı olan bir fiziksel işlemci ile varsa, iki mantıksal işlemciler ve bu nedenle, iki iş parçacığı olması.  
  
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