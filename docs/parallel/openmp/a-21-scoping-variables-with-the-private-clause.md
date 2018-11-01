---
title: A.21   private Yan Tümceli Kapsama Değişkenleri
ms.date: 11/04/2016
ms.assetid: 7cdb4a7f-af24-44ac-9d33-e43840bc8f3d
ms.openlocfilehash: 4217bcc3911ded88b9385695c8c0ac851fceae9e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50616137"
---
# <a name="a21---scoping-variables-with-the-private-clause"></a>A.21   private Yan Tümceli Kapsama Değişkenleri

Değerlerini `i` ve `j` paralel bölgeden Çıkışta aşağıdaki örnekte tanımlanmamış:

```
int i, j;
i = 1;
j = 2;
#pragma omp parallel private(i) firstprivate(j)
{
  i = 3;
  j = j + 2;
}
printf_s("%d %d\n", i, j);
```

Daha fazla bilgi için `private` yan tümcesi bkz [bölümü 2.7.2.1](../../parallel/openmp/2-7-2-1-private.md) sayfasında 25.