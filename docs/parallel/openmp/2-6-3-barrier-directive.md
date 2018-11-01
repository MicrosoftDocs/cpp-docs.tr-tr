---
title: 2.6.3 barrier Yönergesi
ms.date: 11/04/2016
ms.assetid: 4485a3d7-533f-4fec-8128-a131bec7fa16
ms.openlocfilehash: 9079dce4b2a27e91e349fd0df8414d38cd245d2e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50637027"
---
# <a name="263-barrier-directive"></a>2.6.3 barrier Yönergesi

**Engel** yönergesi, bir takım tüm iş parçacıklarının eşitler. Diğer tüm bu noktaya ulaşıncaya kadar karşılaştığında, takımın her iş parçacığında bekler. Söz dizimi **engel** yönerge aşağıdaki gibidir:

```
#pragma omp barrier new-line
```

Takım tüm iş parçacıklarının engeli karşılaşılmış sonra takım içindeki her iş parçacığı paralel barrier yönergesi sonra deyim yürütmeye başlar. Dikkat edin çünkü **engel** yönergesi, bir C dili deyimi sözdizimi bir parçası olarak sahip değil, bir program içindeki yerleşimi bazı kısıtlamalar vardır. Bkz: [ek C](../../parallel/openmp/c-openmp-c-and-cpp-grammar.md) resmi dilbilgisi için. Aşağıdaki örnek bu kısıtlamaları gösterir.

```
/* ERROR - The barrier directive cannot be the immediate
*          substatement of an if statement
*/
if (x!=0)
   #pragma omp barrier
...

/* OK - The barrier directive is enclosed in a
*      compound statement.
*/
if (x!=0) {
   #pragma omp barrier
}
```