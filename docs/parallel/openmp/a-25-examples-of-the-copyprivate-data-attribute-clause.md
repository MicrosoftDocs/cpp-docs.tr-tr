---
title: A.25 copyprivate veri özniteliği yan tümcesi örnekleri | Microsoft Docs
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
ms.openlocfilehash: 95d68c445c1c20e97725d869061027a9712c2462
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46413648"
---
# <a name="a25---examples-of-the-copyprivate-data-attribute-clause"></a>A.25   copyprivate Veri Özniteliği Yan Tümcesi Örnekleri

**Örnek 1:** `copyprivate` yan tümcesi ([bölümü 2.7.2.8](../../parallel/openmp/2-7-2-8-copyprivate.md) sayfasında 32) tüm özel değişkenler, diğer iş parçacıklarını örneklerine doğrudan tek bir iş parçacığı tarafından alınan değerleri yayın için kullanılabilir.

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

Rutin varsa *init* çağrılır seri bir bölgeden davranışını varlığını yönergeleri ile etkilenmez. Çağrısından sonra *get_values* yordam iş parçacığı tarafından yürütüldü, hiçbir iş parçacığı tarafından belirlenen özel nesneleri kadar yapısı bırakır *bir*, *b*, *x*, ve *y* tüm iş parçacıklarının okunan değerleri ile tanımlanan olur.

**Örnek 2:** aksine önceki örnekte, belirli bir iş parçacığına göre örneğin ana iş parçacığı okuma gerçekleştirilen varsayalım. Bu durumda, `copyprivate` yan tümcesi, doğrudan yayın yapmak için kullanılamaz, ancak paylaşılan geçici nesnelere erişim sağlamak için kullanılabilir.

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

**Örnek 3:** bir paralel bölgenin içinde gerekli kilit nesne sayısını kolayca girme önce belirlenemiyor olduğunu varsayalım. `copyprivate` Yan tümcesi, bir paralel bölgenin içinde atanan paylaşılan kilit nesneler erişim sağlamak için kullanılabilir.

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