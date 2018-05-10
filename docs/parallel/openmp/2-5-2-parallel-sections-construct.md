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
ms.openlocfilehash: b6f7a84e322cb273733c6a724ee2563928df8362
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
---
# <a name="252-parallel-sections-construct"></a>2.5.2 parallel sections Yapısı
**Paralel bölümleri** yönergesi belirtmek için bir kısayol form sağlayan bir **paralel** içeren tek bir bölge **bölümleri** yönergesi. Semantiğini açıkça belirtilmesi için özdeş bir **paralel** hemen sonrasında yönergesi bir **bölümleri** yönergesi. Söz dizimi **paralel bölümleri** yönergesi aşağıdaki gibidir:  
  
```  
#pragma omp parallel sections  [clause[[,] clause] ...] new-line  
   {  
   [#pragma omp section new-line]  
      structured-block  
   [#pragma omp section new-linestructured-block  ]  
   ...  
}  
```  
  
 *Yan tümcesi* tarafından kabul yan tümceleri biri olabilir **paralel** ve **bölümleri** yönergeleri, dışında **nowait** yan tümcesi.  
  
## <a name="cross-references"></a>Çapraz referanslar:  
  
-   **Paralel** yönerge, bkz: [bölüm 2.3](../../parallel/openmp/2-3-parallel-construct.md) sayfasında 8.  
  
-   **bölümler** yönerge, bkz: [bölüm 2.4.2](../../parallel/openmp/2-4-2-sections-construct.md) sayfasında 14.