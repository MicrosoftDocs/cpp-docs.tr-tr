---
title: A.20   barrier Yönergelerini Bağlama
ms.date: 11/04/2016
ms.assetid: a3fdcc26-6873-429b-998e-de451401483b
ms.openlocfilehash: cf6f20a8539c47ca529af93e65f3a5fe244228d8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50652952"
---
# <a name="a20---binding-of-barrier-directives"></a>A.20   barrier Yönergelerini Bağlama

Yönerge bağlama için çağrı kurallarını bir **engel** yönergesi en yakın kapsayan bağlamak için `parallel` yönergesi. Yönerge bağlama hakkında daha fazla bilgi için bkz. [bölümü 2.8](../../parallel/openmp/2-8-directive-binding.md) sayfasında 32.

Aşağıdaki örnekte, çağrısından *ana* için *sub2* uyumlu olduğundan **engel** (içinde *sub3*) paralel bölgesiyle bağlar içinde *sub2*. Çağrısından *ana* için *Abon1* uyumlu olduğundan **engel** paralel bölgenin içinde alt yordam bağlar *sub2*.  Çağrısından *ana* için *sub3* uyumlu olduğundan **engel** için herhangi bir paralel bölgenin bağlamamasıdır ve göz ardı edilir. Ayrıca **engel** yalnızca takım iş parçacıkları kapsayan bir paralel bölgenin içinde oluşturulan tüm iş parçacıkları ve eşitler *Abon1*.

```
int main()
{
    sub1(2);
    sub2(2);
    sub3(2);
}

void sub1(int n)
{
    int i;
    #pragma omp parallel private(i) shared(n)
    {
        #pragma omp for
        for (i=0; i<n; i++)
            sub2(i);
    }
}

void sub2(int k)
{
     #pragma omp parallel shared(k)
     sub3(k);
}

void sub3(int n)
{
    work(n);
    #pragma omp barrier
    work(n);
}
```