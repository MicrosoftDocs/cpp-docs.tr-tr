---
title: 3.3.1 omp_get_wtime işlevi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 90188bd2-c53e-4398-8946-d3ecc92fa0f6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8ec022e9c7e27c848ef535481993dd18dc45f695
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46430780"
---
# <a name="331-ompgetwtime-function"></a>3.3.1 omp_get_wtime İşlevi

`omp_get_wtime` İşlevi döndürür çift duyarlıklı kayan noktalı değeri eşittir geçen duvar saati süresi içinde bazı "zamanda" geçmiş beri geçen saniye sayısı.  Gerçek "süresi geçmiş" isteğe bağlıdır, ancak uygulama programın yürütülmesi sırasında değiştirmemesi garanti edilir. Biçimi aşağıdaki gibidir:

```
#include <omp.h>
double omp_get_wtime(void);
```

Bu işlev, aşağıdaki örnekte gösterildiği gibi geçen süreleri ölçmek için kullanılacak beklenen:

```
double start;
double end;
start = omp_get_wtime();
... work to be timed ...
end = omp_get_wtime();
printf_s("Work took %f sec. time.\n", end-start);
```

Döndürülen süreleri, bir uygulamada katılan tüm iş parçacıkları arasında genel olarak tutarlı olması gerekmez yöneliktir tarafından "iş parçacığı başına saatleri" formundadır.