---
title: 2.5.2 parallel sections yapısı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 94220e27-14f8-465c-bd8d-eb960b4b5dee
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 073d0561fe4bfbb96ed88681a077da6fc985c963
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46402336"
---
# <a name="252-parallel-sections-construct"></a>2.5.2 parallel sections Yapısı

**Paralel bölümleri** yönergesi belirtmek için bir kısayol form sağlar bir **paralel** içeren tek bir bölge **bölümleri** yönergesi. Semantiği açıkça belirtilmesi için özdeş bir **paralel** yönergesi hemen arkasından bir **bölümleri** yönergesi. Söz dizimi **paralel bölümleri** yönerge aşağıdaki gibidir:

```
#pragma omp parallel sections  [clause[[,] clause] ...] new-line
   {
   [#pragma omp section new-line]
      structured-block
   [#pragma omp section new-linestructured-block  ]
   ...
}
```

*Yan tümcesi* kabul eden yan tümceleri herhangi birini **paralel** ve **bölümleri** yönergeleri dışında **nowait** yan tümcesi.

## <a name="cross-references"></a>Başvuruları çapraz:

- **Paralel** yönergesine bakın [bölümü 2.3](../../parallel/openmp/2-3-parallel-construct.md) 8 sayfasında.

- **bölümler** yönergesine bakın [bölümü 2.4.2](../../parallel/openmp/2-4-2-sections-construct.md) sayfasında 14.