---
title: "Paralel bölgeleri kullanma A.3 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 575216a1-960a-47f7-9c82-7f660291fcfe
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: ba7ef5332611a9a6a66a0a0ec5a51461436ef453
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="a3---using-parallel-regions"></a>A.3   Paralel Bölgeleri Kullanma
`parallel` Yönergesi ([bölüm 2.3](../../parallel/openmp/2-3-parallel-construct.md) sayfasında 8) çizgisi kaba paralel programlarda kullanılabilir. Aşağıdaki örnekte, her iş parçacığı paralel bölgede hangi kısmının genel dizi karar `x` , üzerinde çalışmak için iş parçacığı numarasına göre:  
  
```  
#pragma omp parallel shared(x, npoints) private(iam, np, ipoints)  
{  
    iam = omp_get_thread_num();  
    np =  omp_get_num_threads();  
    ipoints = npoints / np;  
    subdomain(x, iam, ipoints);  
}  
```