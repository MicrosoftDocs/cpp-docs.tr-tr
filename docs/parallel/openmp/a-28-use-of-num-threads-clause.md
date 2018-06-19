---
title: Num_threads yan tümcesi A.28 kullanımını | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 26238da1-902c-49b4-9559-0fbc9eaf7f36
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 12289192d056acac684f28712ccf2aa1423b6c3e
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33689122"
---
# <a name="a28---use-of-numthreads-clause"></a>A.28   num_threads Yan Tümcesinin Kullanımı
Aşağıdaki örnekte gösterilmiştir `num_threads` yan tümcesi ([bölüm 2.3](../../parallel/openmp/2-3-parallel-construct.md) sayfasında 8). Paralel bölge en fazla 10 iş parçacığı ile yürütülür.  
  
```  
#include <omp.h>  
main()  
{  
    omp_set_dynamic(1);  
    ...  
    #pragma omp parallel num_threads(10)  
    {  
        ... parallel region ...  
    }  
}  
```