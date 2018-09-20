---
title: A.6 lastprivate yan tümcesini kullanma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: cf3bf0cc-aa46-4e44-9433-e2969e3be2c1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 03d18d3aaf5c5d1cbe03282710ae4f4e2bb613f3
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46390585"
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