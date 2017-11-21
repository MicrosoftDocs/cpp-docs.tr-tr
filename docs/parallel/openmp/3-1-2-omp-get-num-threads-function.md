---
title: "3.1.2 omp_get_num_threads işlevi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: bcdd76e2-d96b-4884-ac8f-e55fc0c42801
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 7b832cd4e4e44706bbd4ffc63b5912f941bb0ca6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="312-ompgetnumthreads-function"></a>3.1.2 omp_get_num_threads İşlevi
**Omp_get_num_threads** işlevi döndürür iş parçacığı sayısı şu anda içinden çağırıldığında paralel bölge yürütme takım. Biçimi aşağıdaki gibidir:  
  
```  
#include <omp.h>  
int omp_get_num_threads(void);  
```  
  
 **Num_threads** yan tümcesi **omp_set_num_threads** işlevini ve **OMP_NUM_THREADS** ortam değişkeni denetleyen bir takım içindeki iş parçacığı sayısı.  
  
 İş parçacığı sayısı kullanıcı tarafından açıkça ayarlanmadı, uygulama tanımlı varsayılandır. Bu işlev en yakın kapsayan bağlar **paralel** yönergesi. Bir program seri bir kısmı veya serileştirilir iç içe geçmiş bir paralel bölge çağırdıysanız, bu işlev 1 döndürür.  
  
## <a name="cross-references"></a>Çapraz referanslar:  
  
-   **OMP_NUM_THREADS** ortam değişkeni, bkz: [bölüm 4.2](../../parallel/openmp/4-2-omp-num-threads.md) sayfasında 48.  
  
-   **num_threads** yan tümcesi, bkz: [bölüm 2.3](../../parallel/openmp/2-3-parallel-construct.md) sayfasında 8.  
  
-   **Paralel** oluşturmak için bkz: [bölüm 2.3](../../parallel/openmp/2-3-parallel-construct.md) sayfasında 8.