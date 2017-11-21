---
title: "3.1.1 omp_set_num_threads işlevi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: b94cf2b5-8011-4a3b-ba56-676982642857
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 568f01aacd361437929606307186bb7cd2eaad7c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="311-ompsetnumthreads-function"></a>3.1.1 omp_set_num_threads İşlevi
`omp_set_num_threads` İşlevi belirtmeyin sonraki paralel bölgeler için kullanılacak iş parçacıklarının varsayılan sayısını ayarlar bir `num_threads` yan tümcesi. Biçimi aşağıdaki gibidir:  
  
```  
#include <omp.h>  
void omp_set_num_threads(int num_threads);  
```  
  
 Parametresinin değeri *num_threads* pozitif bir tamsayı olmalıdır. İş parçacığı sayısını dinamik olarak ayarlamayı etkinleştirilip etkinleştirilmediği bağlı etkisini bağlıdır. Kuralları arasındaki etkileşimi hakkında kapsamlı bir kümesini için `omp_set_num_threads` işlevi ve iş parçacığı, dinamik ayarlama bölüm 2.3 sayfa 8 başlığına bakın.  
  
 Bu işlev bir program bölümünden çağrıldığında yukarıda açıklanan etkilere sahiptir nerede `omp_in_parallel` işlevi sıfır döndürür. Program bir kısmına çağrılıp çağrılmayacağını nerede `omp_in_parallel` işlevi sıfır olmayan bir değer döndürür, bu işlevin davranışı tanımlı değil.  
  
 Bu çağrı üzerinden önceliğe sahip `OMP_NUM_THREADS` ortam değişkeni. Çağırarak gerçekleştirilebilir iş parçacığı sayısı için varsayılan değer `omp_set_num_threads` veya ayarlayarak `OMP_NUM_THREADS` ortam değişkeni açıkça geçersiz tek bir **paralel** belirterek yönergesi `num_threads` yan tümcesi.  
  
## <a name="cross-references"></a>Çapraz referanslar:  
  
-   `omp_set_dynamic`işlev, bkz: [bölüm 3.1.7](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md) sayfasında 39.  
  
-   `omp_get_dynamic`işlev, bkz: [bölüm 3.1.8](../../parallel/openmp/3-1-8-omp-get-dynamic-function.md) sayfasında 40.  
  
-   `OMP_NUM_THREADS`ortam değişkeni, bkz: [bölüm 4.2](../../parallel/openmp/4-2-omp-num-threads.md) sayfa 48 ve bölüm 2.3 sayfasında 8.  
  
-   `num_threads`yan tümcesi, bkz: [bölüm 2.3](../../parallel/openmp/2-3-parallel-construct.md) sayfasında 8