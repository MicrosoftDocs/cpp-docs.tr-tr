---
title: 2.5.1 Yapı için parallel
ms.date: 11/04/2016
ms.assetid: a233e7ed-2462-4f7a-9a5d-556ab9f363d8
ms.openlocfilehash: e74fa958a70fb10aadd39ccc6b4e56670bc072b0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50590339"
---
# <a name="251-parallel-for-construct"></a>2.5.1 Yapı için parallel

**İçin paralel** yönergesi olduğu için bir kısayol bir **paralel** içeren tek bir bölge **için** yönergesi. Söz dizimi **için paralel** yönerge aşağıdaki gibidir:

```
#pragma omp parallel for [clause[[,] clause] ...] new-linefor-loop
```

Bu yönerge yan tümcesinden sağlayan **paralel** yönergesi ve **için** dışında yönerge `nowait` aynı anlamlara ve kısıtlamalar yan tümcesi. Semantiği açıkça belirtilmesi için özdeş bir **paralel** yönergesi hemen arkasından bir **için** yönergesi.

## <a name="cross-references"></a>Başvuruları çapraz:

- **Paralel** yönergesine bakın [bölümü 2.3](../../parallel/openmp/2-3-parallel-construct.md) 8 sayfasında.

- **için** yönergesine bakın [bölümü 2.4.1](../../parallel/openmp/2-4-1-for-construct.md) sayfasında 11.

- Veri özniteliği yan tümcesi bkz [2.7.2 veri paylaşım öznitelik yan tümceleri](../../parallel/openmp/2-7-2-data-sharing-attribute-clauses.md) sayfasında 25.