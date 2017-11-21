---
title: "Num_threads yan tümcesi A.28 kullanımını | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 26238da1-902c-49b4-9559-0fbc9eaf7f36
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: be3da02ea7938b96da16a763111139c4f69335ec
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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