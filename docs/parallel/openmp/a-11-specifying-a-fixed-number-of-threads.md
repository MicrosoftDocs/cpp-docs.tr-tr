---
title: "Sabit bir iş parçacığı sayısını belirtme A.11 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 1d06b142-4c35-44b8-994b-20f2aed5462b
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 5a397789958e229363f535ed9b39f83ed928cb6a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="a11---specifying-a-fixed-number-of-threads"></a>A.11   Sabit Sayıda İş Parçacığı Belirtme
Bazı programlar doğru şekilde yürütmek için iş parçacığı sabit, belirlenmiş sayısına bağlıdır.  İş parçacığı sayısını dinamik düzeltilmesi için varsayılan ayar uygulama tanımlı olduğundan, bu tür programların dinamik iş parçacığı özelliği devre dışı bırakma ve açıkça taşınabilirlik emin olmak için iş parçacığı sayısını ayarlamak seçebilirsiniz. Aşağıdaki örnek kullanarak bunu gösterilmektedir `omp_set_dynamic` ([bölüm 3.1.7](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md) 39 sayfasında), ve `omp_set_num_threads` ([bölüm 3.1.1](../../parallel/openmp/3-1-1-omp-set-num-threads-function.md) sayfasında 36):  
  
```  
omp_set_dynamic(0);  
omp_set_num_threads(16);  
#pragma omp parallel shared(x, npoints) private(iam, ipoints)  
{  
    if (omp_get_num_threads() != 16)   
      abort();  
    iam = omp_get_thread_num();  
    ipoints = npoints/16;  
    do_by_16(x, iam, ipoints);  
}  
```  
  
 Bu örnekte, yalnızca 16 iş parçacıkları tarafından yürütülürse programı doğru yürütür. Uygulama 16 iş parçacığı destekleme kapasitesine sahip değilse, bu örnek, uygulama tanımlı davranıştır.  
  
 Paralel bir bölge çalışan iş parçacıklarının sayısını ayarlama dinamik iş parçacığı bağımsız olarak paralel bir bölge sırasında sabit mi kaldığını unutmayın. Dinamik iş parçacığı mekanizması paralel bölge başlangıcında kullanılacak iş parçacıklarının sayısını belirler ve bölge boyunca sabit tutar.