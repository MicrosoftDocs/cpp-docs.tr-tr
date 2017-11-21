---
title: "Lastprivate yan tümcesini kullanarak A.6 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: cf3bf0cc-aa46-4e44-9433-e2969e3be2c1
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: e35ad34ce3bd1f97a58273522520d6ab67710505
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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