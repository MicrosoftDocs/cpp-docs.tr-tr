---
title: omp_get_num_procs | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- omp_get_num_procs
dev_langs:
- C++
helpviewer_keywords:
- omp_get_num_procs OpenMP function
ms.assetid: 14a10b8f-e59b-4211-a292-687648c9f760
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 74e4d224f28721e3849350e8f12010078edba4a5
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46437384"
---
# <a name="ompgetnumprocs"></a>omp_get_num_procs

İşlev çağrıldığında, kullanılabilir işlemci sayısını döndürür.

## <a name="syntax"></a>Sözdizimi

```
int omp_get_num_procs();
```

## <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [3.1.5 omp_get_num_procs işlevi](../../../parallel/openmp/3-1-5-omp-get-num-procs-function.md).

## <a name="example"></a>Örnek

```
// omp_get_num_procs.cpp
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

int main( )
{
    printf_s("%d\n", omp_get_num_procs( ));
    #pragma omp parallel
        #pragma omp master
        {
            printf_s("%d\n", omp_get_num_procs( ));
        }
}
```

```Output
// Expect the following output when the example is run on a two-processor machine:
2
2
```

## <a name="see-also"></a>Ayrıca Bkz.

[İşlevler](../../../parallel/openmp/reference/openmp-functions.md)