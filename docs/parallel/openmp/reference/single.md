---
title: tek | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- Single
dev_langs:
- C++
helpviewer_keywords:
- single OpenMP directive
ms.assetid: 85cf94fb-cb9c-4d82-8609-adffa9f552e1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2fadd4f9789dc834c1bae0477c828892fed94b5c
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46413373"
---
# <a name="single"></a>single

Kodun bir bölümünü tek bir iş parçacığı üzerinde mutlaka ana iş parçacığının yürütülmesi gereken belirtmenize olanak sağlar.

## <a name="syntax"></a>Sözdizimi

```
#pragma omp single [clauses] 
{
   code_block
}
```

#### <a name="parameters"></a>Parametreler

*Yan tümcesi*<br/>
(İsteğe bağlı) Sıfır veya daha fazla tümceciği. Tarafından desteklenen yan tümce listesi için Açıklamalar bölümüne bakın **tek**.

## <a name="remarks"></a>Açıklamalar

**Tek** yönergesi aşağıdaki OpenMP yan tümceleri destekler:

- [copyprivate](../../../parallel/openmp/reference/copyprivate.md)

- [firstprivate](../../../parallel/openmp/reference/firstprivate.md)

- [nowait](../../../parallel/openmp/reference/nowait.md)

- [private](../../../parallel/openmp/reference/private-openmp.md)

[Ana](../../../parallel/openmp/reference/master.md) yönergesi, kodun bir bölümünden yalnızca ana iş parçacığı üzerinde yapılmalıdır belirtmenize olanak sağlar.

Daha fazla bilgi için [2.4.3 tek oluşturmak](../../../parallel/openmp/2-4-3-single-construct.md).

## <a name="example"></a>Örnek

```cpp
// omp_single.cpp
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

int main() {
   #pragma omp parallel num_threads(2)
   {
      #pragma omp single
      // Only a single thread can read the input.
      printf_s("read input\n");

      // Multiple threads in the team compute the results.
      printf_s("compute results\n");

      #pragma omp single
      // Only a single thread can write the output.
      printf_s("write output\n");
    }
}
```

```Output
read input
compute results
compute results
write output
```

## <a name="see-also"></a>Ayrıca Bkz.

[Yönergeler](../../../parallel/openmp/reference/openmp-directives.md)