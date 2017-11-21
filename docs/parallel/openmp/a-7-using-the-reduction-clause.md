---
title: "Azaltma yan tümcesini kullanarak A.7 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: e71e65bc-a25c-4f02-b507-66b52bf950a4
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: a7d5d4ba613a0343068e31d3cfa1baae13e4da53
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="a7---using-the-reduction-clause"></a>A.7   reduction Yan Tümcesini Kullanma
Aşağıdaki örnek, azaltma yan tümcesi gösterir ([bölüm 2.7.2.6](../../parallel/openmp/2-7-2-6-reduction.md) sayfasında 28):  
  
```  
#pragma omp parallel for private(i) shared(x, y, n) \  
                         reduction(+: a, b)  
    for (i=0; i<n; i++) {  
        a = a + x[i];  
        b = b + y[i];  
    }  
```