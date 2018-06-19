---
title: Lastprivate yan tümcesini kullanarak A.6 | Microsoft Docs
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
ms.openlocfilehash: eec6ddc46aab36671e767963e5aaf6e25c4d25cd
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33690549"
---
# <a name="a6---using-the-lastprivate-clause"></a>A.6   lastprivate Yan Tümcesini Kullanma
Bazen doğru yürütme son yineleme döngüsü bir değişkene atar değere bağlıdır. Programlara tür değişkenlerinin bağımsız değişken olarak listelenmelidir bir `lastprivate` yan tümcesi ([bölüm 2.7.2.3](../../parallel/openmp/2-7-2-3-lastprivate.md) sayfasında 27) böylece değişkenlerin değerleri zaman döngü sırayla yürütülen ile aynı olur.  
  
```  
#pragma omp parallel  
{  
   #pragma omp for lastprivate(i)  
      for (i=0; i<n-1; i++)  
         a[i] = b[i] + b[i+1];  
}  
a[i]=b[i];  
```  
  
 Değerini önceki örnekte `i` paralel bölge sonunda eşit olur `n-1`, gibi sıralı durumda.