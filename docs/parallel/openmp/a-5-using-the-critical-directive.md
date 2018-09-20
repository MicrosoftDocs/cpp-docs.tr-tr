---
title: A.5 critical yönergesini kullanma | Microsoft Docs
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
ms.openlocfilehash: 99f9ab513ae1df5a7e1e62cfefcefe404637c063
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46444573"
---
# <a name="a5---using-the-critical-directive"></a>A.5   critical Yönergesini Kullanma

Aşağıdaki örnek birkaç içerir `critical` yönergeleri ([bölümü 2.6.2](../../parallel/openmp/2-6-2-critical-construct.md) sayfasında 18). Örnekte, bir görev sıradan çıkarılan ve üzerinde çalıştığınız bir kuyruğa alma modeli gösterilmektedir. Aynı görevi kuyruktan çıkarma işlemlerini birden çok iş parçacığı karşı koruma sağlamak için sıradan çıkarmak işlemi olmalıdır bir `critical` bölümü. Bu örnekte iki kuyrukları bağımsız olduğundan, bunlar tarafından korunur `critical` yönergeleri farklı adlarla *xaxis* ve *yaxis*.

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