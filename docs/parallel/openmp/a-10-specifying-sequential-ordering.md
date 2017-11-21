---
title: "Sıralı sıralama belirtme A.10 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 5c65a9b1-0fc5-4cad-a5a9-9ce10b25d25c
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 0718147c013ca09c67f3093820ee71b1cef32653
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="a10---specifying-sequential-ordering"></a>A.10   Ardışık Sıralamayı Belirtme
Bölümler sıralı ([bölüm 2.6.6](../../parallel/openmp/2-6-6-ordered-construct.md) sayfasında 22) sırayla paralel olarak yapılır iş çıktısı sıralama için kullanışlıdır. Sıralı bir düzende dizinler çıkışı aşağıdaki programı baskı:  
  
```  
#pragma omp for ordered schedule(dynamic)  
    for (i=lb; i<ub; i+=st)  
        work(i);  
void work(int k)  
{  
    #pragma omp ordered  
        printf_s(" %d", k);  
}  
```