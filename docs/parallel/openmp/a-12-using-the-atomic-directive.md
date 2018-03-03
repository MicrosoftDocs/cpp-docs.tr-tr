---
title: "Atomik yönergesi kullanarak A.12 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: d3ba3c87-413d-4efa-8a45-8a7f28ab0164
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9aa619d9bbe635a41d15a39d6c05780a4416520e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="a12---using-the-atomic-directive"></a>A.12   atomic Yönergesini Kullanma
Aşağıdaki örnek yarış durumları ortadan kaldırır (bir öğesinin eşzamanlı güncelleştirmeleri *x* birden çok iş parçacığı tarafından) kullanarak `atomic` yönergesi ([bölüm 2.6.4](../../parallel/openmp/2-6-4-atomic-construct.md) sayfasında 19):  
  
```  
#pragma omp parallel for shared(x, y, index, n)  
    for (i=0; i<n; i++)   
    {  
        #pragma omp atomic  
            x[index[i]] += work1(i);  
        y[i] += work2(i);  
    }  
```  
  
 Kullanmanın avantajı `atomic` Bu örnekte yönergesidir iki farklı öğeler paralel olarak gerçekleşecek şekilde x güncelleştirmeler sağlar. Varsa bir `critical` yönergesi ([bölüm 2.6.2](../../parallel/openmp/2-6-2-critical-construct.md) sayfasında 18) tüm güncelleştirmeleri sonra öğelerine bunun yerine, kullanılan *x* seri olarak (içinde hiçbir sipariş garanti rağmen) yürütülmesi.  
  
 Unutmayın `atomic` yönergesi hemen ardından yalnızca C veya C++ deyimi için geçerlidir.  Sonuç olarak, öğeleri *y* Bu örnekte otomatik olarak güncelleştirilmez.