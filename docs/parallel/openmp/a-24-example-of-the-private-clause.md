---
title: Özel yan tümcesinin A.24 örnek | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: f90a5b49-81ff-4746-ae03-37bbd33f6c08
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3f8d07f2d95b565077f5dfd78fdc4ff6edf30216
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33691394"
---
# <a name="a24---example-of-the-private-clause"></a>A.24   private Yan Tümcesi Örneği
`private` Yan tümcesi ([bölüm 2.7.2.1](../../parallel/openmp/2-7-2-1-private.md) sayfasında 25) paralel bölgesi yalnızca etkisi bölgenin dinamik kapsam için değil, bölge sözcük kapsamını için kullanılıyor.  Bu nedenle, değişkenin herhangi kullandığı aşağıdaki örnekte *bir* içinde `for` yordamı döngüde *f* özel bir kopyası anlamına gelir *bir*, çalışırken bir kullanımı yordamı *g* genel başvuruyor *bir*.  
  
```  
int a;  
  
void f(int n)   
{  
    a = 0;  
  
    #pragma omp parallel for private(a)  
    for (int i=1; i<n; i++)   
    {  
        a = i;  
        g(i, n);  
        d(a);     // Private copy of "a"  
        ...  
    }  
    ...  
  
void g(int k, int n)   
{  
    h(k,a); // The global "a", not the private "a" in f  
}  
```