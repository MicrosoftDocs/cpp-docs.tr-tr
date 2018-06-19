---
title: Veri özniteliği yan tümcesi copyprivate A.25 örnekleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 7b1cb6a5-5691-4b95-b3ac-d7543ede6405
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c92d9ce6f22c2d53a2e65d7b67c22e4f080f162c
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33691696"
---
# <a name="a25---examples-of-the-copyprivate-data-attribute-clause"></a>A.25   copyprivate Veri Özniteliği Yan Tümcesi Örnekleri
**Örnek 1:** `copyprivate` yan tümcesi ([bölüm 2.7.2.8](../../parallel/openmp/2-7-2-8-copyprivate.md) sayfasında 32) diğer iş parçacıklarında özel değişkenleri tüm örnekleri için doğrudan tek bir iş parçacığı tarafından alınan değerleri yayınlamak için kullanılır.  
  
```  
float x, y;  
#pragma omp threadprivate(x, y)  
  
void init( )   
{  
    float a;  
    float b;  
  
    #pragma omp single copyprivate(a,b,x,y)  
    {  
        get_values(a,b,x,y);  
    }  
  
    use_values(a, b, x, y);  
}  
```  
  
 Rutin varsa *init* çağrılır bir seri bölgesinden davranışını yönergeleri varlığını tarafından etkilenmez. Çağrısından sonra *get_values* yordamı yürütüldü. bir iş parçacığı tarafından hiçbir iş parçacığı tarafından belirlenen özel nesneleri kadar yapı bırakır *bir*, *b*, *x*, ve *y* tüm iş parçacıkları, okunan değerleri ile tanımlanan haline gelir.  
  
 **Örnek 2:** aksine önceki örnekte, belirli, iş parçacığı tarafından deyin ana iş parçacığı okuma gerçekleştirilen varsayalım. Bu durumda, `copyprivate` yan tümcesi, doğrudan yayın yapmak için kullanılamaz, ancak geçici bir paylaşılan nesne erişim sağlamak için kullanılabilir.  
  
```  
float read_next( )   
{  
    float * tmp;  
    float return_val;  
  
    #pragma omp single copyprivate(tmp)  
    {  
        tmp = (float *) malloc(sizeof(float));  
    }  
  
    #pragma omp master  
    {  
        get_float( tmp );  
    }  
  
    #pragma omp barrier  
    return_val = *tmp;  
    #pragma omp barrier  
  
    #pragma omp single  
    {  
       free(tmp);  
    }  
  
    return return_val;  
}  
```  
  
 **Örnek 3:** paralel bir bölge içinde gerekli kilit nesne sayısı kolayca girme önce belirlenemiyor olduğunu varsayalım. `copyprivate` Yan tümcesi, paralel, bölge içinde ayrılmış paylaşılan kilit nesnelere erişimini sağlamak için kullanılabilir.  
  
```  
#include <omp.h>  
  
omp_lock_t *new_lock()  
{  
    omp_lock_t *lock_ptr;  
  
    #pragma omp single copyprivate(lock_ptr)  
    {  
        lock_ptr = (omp_lock_t *) malloc(sizeof(omp_lock_t));  
        omp_init_lock( lock_ptr );  
    }  
  
    return lock_ptr;  
}  
```