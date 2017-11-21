---
title: "Threadprivate yönergesi kullanarak A.26 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 6eda76c2-c4f1-4208-a900-e0ea98a53eca
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: f6c24a3c00dad6e196d015518071978884260c93
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="a26---using-the-threadprivate-directive"></a>A.26   threadprivate Yönergesini Kullanma
Aşağıdaki örnekler nasıl kullanılacağını göstermektedir `threadprivate` yönergesi ([bölüm 2.7.1](../../parallel/openmp/2-7-1-threadprivate-directive.md) sayfasında 23) ayrı bir sayaç her iş parçacığı vermek için.  
  
 **Örnek 1:**  
  
```  
int counter = 0;  
#pragma omp threadprivate(counter)  
  
int sub()  
{  
    counter++;  
    return(counter);  
}  
```  
  
 **Örnek 2:**  
  
```  
int sub()  
{  
    static int counter = 0;  
    #pragma omp threadprivate(counter)  
    counter++;  
    return(counter);  
}  
```