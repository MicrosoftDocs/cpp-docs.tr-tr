---
title: A.24   private Yan Tümcesi Örneği
ms.date: 11/04/2016
ms.assetid: f90a5b49-81ff-4746-ae03-37bbd33f6c08
ms.openlocfilehash: facf5b953b26d284f6bfed4f35a9162f6d2bf212
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50552964"
---
# <a name="a24---example-of-the-private-clause"></a>A.24   private Yan Tümcesi Örneği

`private` Yan tümcesi ([bölümü 2.7.2.1](../../parallel/openmp/2-7-2-1-private.md) sayfasında 25) bir paralel bölgenin yalnızca dinamik kapsam bölgesi için değil, bölge sözcük kapsamı için etkili bulunmaktadır.  Bu nedenle, değişken kullanıldığı aşağıdaki örnekte *bir* içinde `for` yordamı döngüde *f* özel bir kopyası anlamına gelir *bir*, while bir kullanımı yordamı *g* genel başvuruyor *bir*.

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