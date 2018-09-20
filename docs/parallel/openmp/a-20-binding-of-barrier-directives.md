---
title: A.20 barrier yönergelerini bağlama | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: a3fdcc26-6873-429b-998e-de451401483b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 628920caa6a122230f42394cc757e3abdb1874cd
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46381315"
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