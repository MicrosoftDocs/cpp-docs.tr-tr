---
title: 2.5.1 yapı için parallel | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: a233e7ed-2462-4f7a-9a5d-556ab9f363d8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cfff3b0c17dd098b5d802af61a7ca1f81cb02845
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46373967"
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