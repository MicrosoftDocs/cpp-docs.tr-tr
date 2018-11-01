---
title: 3.3.1 omp_get_wtime İşlevi
ms.date: 11/04/2016
ms.assetid: 90188bd2-c53e-4398-8946-d3ecc92fa0f6
ms.openlocfilehash: 544a1bc9a613a2888cb7c5e68e54fdfae1b1c333
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50460573"
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