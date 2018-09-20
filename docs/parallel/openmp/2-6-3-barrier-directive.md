---
title: 2.6.3 barrier yönergesi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 4485a3d7-533f-4fec-8128-a131bec7fa16
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8654534143e6feed06e93406c8fe03983ee9c2fc
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46429155"
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