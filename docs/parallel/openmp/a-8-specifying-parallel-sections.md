---
title: A.8   Paralel Bölümleri Belirtme
ms.date: 11/04/2016
ms.assetid: cf399304-121e-4c07-9829-47e0dbc2ef10
ms.openlocfilehash: 81eaed920e77b23052ac58c2d0e18fee83c00565
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50461444"
---
# <a name="a8---specifying-parallel-sections"></a>A.8   Paralel Bölümleri Belirtme

Aşağıdaki örnekte, (için [bölümü 2.4.2](../../parallel/openmp/2-4-2-sections-construct.md) sayfasında 14) işlevleri *xaxis*, *yaxis*, ve *zaxis* eşzamanlı olarak yürütülebilir. İlk `section` yönergesi, isteğe bağlıdır.  Unutmayın tüm `section` sözcük kapsamı içinde görünür gereken yönergeleri `parallel sections` oluşturun.

```
#pragma omp parallel sections
{
    #pragma omp section
        xaxis();
    #pragma omp section
        yaxis();
    #pragma omp section
        zaxis();
}
```