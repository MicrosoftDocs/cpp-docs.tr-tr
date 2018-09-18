---
title: varsa (OpenMP) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- if
dev_langs:
- C++
helpviewer_keywords:
- if OpenMP clause
ms.assetid: db5940b6-2414-4bf8-934d-3edd8393c0f8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 83e1920ab2cb44815e9547e4f7f4a07999c1c588
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46020959"
---
# <a name="if-openmp"></a>if (OpenMP)
Bir döngü paralel veya seri gerçekleştirilip gerçekleştirilmeyeceğini belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
if(expression)  
```  
  
### <a name="parameters"></a>Parametreler
  
*İfade*<br/>
True (sıfırdan farklı) olarak değerlendirilirse, paralel olarak yürütmek için bir paralel bölgenin içinde kod neden bir tam sayı ifade. İfade false (sıfır) olarak değerlendirilirse, paralel bölgenin içinde seri (tek bir iş parçacığı tarafından) yürütülür.  
  
## <a name="remarks"></a>Açıklamalar  
 `if` Aşağıdaki yönergeleri için geçerlidir:  
  
-   [parallel](../../../parallel/openmp/reference/parallel.md)  
  
-   [for](../../../parallel/openmp/reference/for-openmp.md)  
  
-   [Bölümleri](../../../parallel/openmp/reference/sections-openmp.md)  
  
 Daha fazla bilgi için [2.3 parallel yapı](../../../parallel/openmp/2-3-parallel-construct.md).  
  
## <a name="example"></a>Örnek  
  
```  
// omp_if.cpp  
// compile with: /openmp  
#include <stdio.h>  
#include <omp.h>  
  
void test(int val)  
{  
    #pragma omp parallel if (val)  
    if (omp_in_parallel())  
    {  
        #pragma omp single  
        printf_s("val = %d, parallelized with %d threads\n",  
                 val, omp_get_num_threads());  
    }  
    else  
    {  
        printf_s("val = %d, serialized\n", val);  
    }  
}  
  
int main( )  
{  
    omp_set_num_threads(2);  
    test(0);  
    test(2);  
}  
```  
  
```Output  
val = 0, serialized  
val = 2, parallelized with 2 threads  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yan Tümceler](../../../parallel/openmp/reference/openmp-clauses.md)