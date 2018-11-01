---
title: 4.1 OMP_SCHEDULE
ms.date: 11/04/2016
ms.assetid: d0dce411-2351-4ee9-a1cc-c0322a58b65c
ms.openlocfilehash: 4731299a4f7203dd01f660ea25bf2f5b58060630
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50432701"
---
# <a name="41-ompschedule"></a>4.1 OMP_SCHEDULE

**OMP_SCHEDULE** yalnızca geçerli **için** ve **için paralel** zamanlama türü olan yönergeleri **çalışma zamanı**. Zamanlama türü ve Öbek boyutu tüm döngüler için tanınan bir zamanlama türlerinden herhangi birini ve isteğe bağlı bu ortam değişkenini ayarlayarak çalışma zamanında ayarlanabilir *chunk_size*.

İçin **için** ve **için paralel** dışındaki bir zamanlama türü olan yönergeleri **çalışma zamanı**, **OMP_SCHEDULE** göz ardı edilir. Bu ortam değişkeni için varsayılan değer uygulama tarafından tanımlanır. İsteğe bağlı *chunk_size* ayarlanmış, değeri pozitif olmalıdır. Varsa *chunk_size* ayarlanmazsa 1 değeri kabul edilir, dışındaki durumunda bir **statik** zamanlama. İçin bir **statik** zamanlama varsayılan öbek boyutu döngü için uygulanan bir iş parçacığı sayısını bölü döngü yineleme alanına ayarlanır.

Örnek:

```
setenv OMP_SCHEDULE "guided,4"
setenv OMP_SCHEDULE "dynamic"
```

## <a name="cross-references"></a>Başvuruları çapraz:

- **için** yönergesine bakın [bölümü 2.4.1](../../parallel/openmp/2-4-1-for-construct.md) sayfasında 11.

- **için paralel** yönergesine bakın [bölümü 2.5.1](../../parallel/openmp/2-5-1-parallel-for-construct.md) sayfasında 16.