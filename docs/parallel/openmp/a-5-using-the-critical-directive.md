---
title: A.5   critical Yönergesini Kullanma
ms.date: 11/04/2016
ms.assetid: 14423018-25b9-4f98-92f2-34c9b0ac0ce0
ms.openlocfilehash: 82497d63acc057fbbcf26f585e42fc8611c08ec4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50545114"
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