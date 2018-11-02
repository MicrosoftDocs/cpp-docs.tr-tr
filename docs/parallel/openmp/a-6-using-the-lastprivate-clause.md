---
title: A.6   lastprivate Yan Tümcesini Kullanma
ms.date: 11/04/2016
ms.assetid: cf3bf0cc-aa46-4e44-9433-e2969e3be2c1
ms.openlocfilehash: 7d5ba1413827590b7fb3afa0847b9aa1da3c41e1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50579812"
---
# <a name="a6---using-the-lastprivate-clause"></a>A.6   lastprivate Yan Tümcesini Kullanma

Bazı durumlarda doğru yürütme son yineleme döngüsü bir değişkene atar değere bağlıdır. Programlara tür bağımsız değişkenleri olarak tüm değişkenleri listelemelidir bir `lastprivate` yan tümcesi ([bölümü 2.7.2.3](../../parallel/openmp/2-7-2-3-lastprivate.md) sayfasında 27) değişkenlerin değerleri, döngü sırayla yürütülen aynı olacak şekilde.

```
#pragma omp parallel
{
   #pragma omp for lastprivate(i)
      for (i=0; i<n-1; i++)
         a[i] = b[i] + b[i+1];
}
a[i]=b[i];
```

Yukarıdaki örnekte, değerini `i` paralel bölgenin sonunda eşit olacaktır `n-1`, sıralı bir durumda gibi.