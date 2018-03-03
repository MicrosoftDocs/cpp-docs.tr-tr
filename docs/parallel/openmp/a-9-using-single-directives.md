---
title: "A.9 kullanma tek yönergeleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: 0c0f9495-5794-4db9-883b-a12e3a9f1328
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 11d41d62448d41d7a11ef747e65cc6ac47e4bd7f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="a9---using-single-directives"></a>A.9   single Yönergelerini Kullanma
Aşağıdaki örnekte gösterilmiştir `single` yönergesi ([bölüm 2.4.3](../../parallel/openmp/2-4-3-single-construct.md) sayfasında 15). Örnekte, yalnızca bir iş parçacığı (karşılaştığı genellikle ilk iş parçacığı `single` yönergesi) ilerleme iletisi yazdırır. Hangi iş parçacığı çalıştırır gibi kullanıcı varsayımlar yapmamalısınız `single` bölümü. Diğer tüm iş parçacıklarının atlar `single` bölümünde ve sonunda engeli Durdur `single` oluşturun. Başka bir iş parçacığı iş parçacığını yürütmek için beklemeden geçebilmeniz `single` bölümünde, bir `nowait` yan tümcesi belirtilebilir `single` yönergesi.  
  
```  
#pragma omp parallel  
{  
    #pragma omp single  
        printf_s("Beginning work1.\n");  
    work1();  
    #pragma omp single  
        printf_s("Finishing work1.\n");  
    #pragma omp single nowait  
        printf_s("Finished work1 and beginning work2.\n");  
    work2();  
}  
```