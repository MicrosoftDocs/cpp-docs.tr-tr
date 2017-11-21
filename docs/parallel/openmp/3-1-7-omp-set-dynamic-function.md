---
title: "3.1.7 omp_set_dynamic işlevi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 1fba961b-b82c-4a1e-ab0f-e4be826e50ab
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 1569235e807fb8e6981c45d7547cae7bd6f70c56
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="317-ompsetdynamic-function"></a>3.1.7 omp_set_dynamic İşlevi
**Omp_set_dynamic** işlevini etkinleştirir veya paralel bölgeler yürütme için kullanılabilir iş parçacığı sayısını dinamik olarak ayarlamayı devre dışı bırakır. Biçimi aşağıdaki gibidir:  
  
```  
#include <omp.h>  
void omp_set_dynamic(int dynamic_threads);  
```  
  
 Varsa *dynamic_threads* değerlendirir sıfır olmayan bir değere sonraki paralel bölgeler yürütmek için kullanılan iş parçacığı sayısını otomatik olarak en iyi sistem kaynaklarını kullanmak için çalışma zamanı ortamı tarafından ayarlanması. Sonuç olarak kullanıcı tarafından belirtilen iş parçacığı sayısı en fazla iş parçacığı sayısıdır. Paralel bir bölge yürütme takım içindeki iş parçacığı sayısı, paralel bölge boyunca sabit kalır ve tarafından bildirilen **omp_get_num_threads** işlevi.  
  
 Varsa *dynamic_threads* değerlendirir 0 olarak dinamik ayarlama devre dışı bırakılır.  
  
 Bu işlev bir program bölümünden çağrıldığında yukarıda açıklanan etkilere sahiptir nerede **omp_in_parallel** işlevi sıfır döndürür. Program bir kısmına çağrılıp çağrılmayacağını nerede **omp_in_parallel** işlevi sıfır olmayan bir değer döndürür, bu işlevin davranışı tanımlı değil.  
  
 Çağrı **omp_set_dynamic** üzerinden önceliğe sahip **omp_dynamıc** ortam değişkeni.  
  
 İş parçacığı dinamik düzeltilmesi için uygulama tanımlı varsayılandır. Sonuç olarak, iş parçacıkları doğru yürütme için belirli sayıda bağlı kullanıcı kodları açıkça dinamik iş parçacığı devre dışı bırakmanız gerekir. Uygulamaları iş parçacığı sayısını dinamik olarak ayarlamasını olanağı sağlamak için gerekli değildir, ancak tüm platformlarda taşınabilirlik desteklemek için arabirim sağlamak için gereklidir.  
  
## <a name="cross-references"></a>Çapraz referanslar:  
  
-   **omp_get_num_threads** işlev, bkz: [bölüm 3.1.2](../../parallel/openmp/3-1-2-omp-get-num-threads-function.md) sayfasında 37'si.  
  
-   **Omp_dynamıc** ortam değişkeni, bkz: [bölüm 4.3](../../parallel/openmp/4-3-omp-dynamic.md) sayfasında 49.  
  
-   **omp_in_parallel** işlev, bkz: [bölüm 3.1.6](../../parallel/openmp/3-1-6-omp-in-parallel-function.md) sayfasında 38.