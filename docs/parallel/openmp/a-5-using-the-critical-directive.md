---
title: Kritik yönergesi kullanarak A.5 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 14423018-25b9-4f98-92f2-34c9b0ac0ce0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c1a41e9664faaca24b6708c737a044828eb460bd
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
---
# <a name="a5---using-the-critical-directive"></a>A.5   critical Yönergesini Kullanma
Aşağıdaki örnek, birkaç içerir `critical` yönergeleri ([bölüm 2.6.2](../../parallel/openmp/2-6-2-critical-construct.md) sayfasında 18). Örnek bir görev kuyruktan çıkarıldı ve üzerinde çalışılan queuing bir modeli gösterilmektedir. Aynı görevi kuyruktan alma birden çok iş parçacığı karşı koruma sağlamak için dequeuing işlemi olmalıdır bir `critical` bölümü. Bu örnekte iki sıraları bağımsız olduğundan, bunlar tarafından korunur `critical` farklı adlara sahip yönergeleri *xaxis* ve *yaxis*.  
  
```  
#pragma omp parallel shared(x, y) private(x_next, y_next)  
{  
    #pragma omp critical ( xaxis )  
        x_next = dequeue(x);  
    work(x_next);  
    #pragma omp critical ( yaxis )  
        y_next = dequeue(y);  
    work(y_next);  
}  
```