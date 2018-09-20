---
title: A.18 yönergeler için iç içe geçmiş | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: ae2b2e0b-ec94-43f8-928c-6d621b51f0df
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4a4e8a984a111d409e07d55c0c1f6e6adbed91e4
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46433575"
---
# <a name="a18---nested-for-directives"></a>A.18   Yönergeler için İç İçe Konulan

Aşağıdaki örnek, `for` yönerge iç içe ([bölümü 2.9](../../parallel/openmp/2-9-directive-nesting.md) sayfasında 33) uyumlu olduğundan iç ve dış `for` yönergeleri bağlamak için farklı paralel bölgeleri:

```
#pragma omp parallel default(shared)
{
    #pragma omp for
        for (i=0; i<n; i++)
        {
            #pragma omp parallel shared(i, n)
            {
                #pragma omp for
                    for (j=0; j<n; j++)
                        work(i, j);
            }
        }
}
```

Yukarıdaki örnekte aşağıdaki çeşitlemesi ayrıca büyük/küçük harf uyumludur:

```
#pragma omp parallel default(shared)
{
    #pragma omp for
        for (i=0; i<n; i++)
            work1(i, n);
}

void work1(int i, int n)
{
    int j;
    #pragma omp parallel default(shared)
    {
        #pragma omp for
            for (j=0; j<n; j++)
                work2(i, j);
    }
    return;
}
```