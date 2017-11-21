---
title: "2.5.2 parallel sections yapısı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 94220e27-14f8-465c-bd8d-eb960b4b5dee
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 086552c72e37822920e0afa213c7966befa052f7
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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