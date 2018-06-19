---
title: Atomik yönergesi kullanarak A.12 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: d3ba3c87-413d-4efa-8a45-8a7f28ab0164
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 719d7a9843a0759b5a5bd558e07a2004f9ef1543
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33691423"
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