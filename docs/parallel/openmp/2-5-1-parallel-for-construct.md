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
ms.openlocfilehash: ef2732c4f8713466d282346ea240bd3c41886ce0
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
---
# <a name="251-parallel-for-construct"></a>2.5.1 Yapı için parallel
**İçin paralel** yönergesi olup bir kısayol bir **paralel** içeren tek bir bölge **için** yönergesi. Söz dizimi **için paralel** yönergesi aşağıdaki gibidir:  
  
```  
#pragma omp parallel for [clause[[,] clause] ...] new-linefor-loop  
```  
  
 Bu yönerge tüm yan tümcelerinde izin verir **paralel** yönergesi ve **için** yönerge dışında `nowait` ile aynı anlamı ve kısıtlamaları yan tümcesi. Semantiğini açıkça belirtilmesi için özdeş bir **paralel** hemen sonrasında yönergesi bir **için** yönergesi.  
  
## <a name="cross-references"></a>Çapraz referanslar:  
  
-   **Paralel** yönerge, bkz: [bölüm 2.3](../../parallel/openmp/2-3-parallel-construct.md) sayfasında 8.  
  
-   **için** yönerge, bkz: [bölüm 2.4.1](../../parallel/openmp/2-4-1-for-construct.md) sayfasında 11.  
  
-   Veri öznitelik yan tümceleri, bkz: [2.7.2 veri paylaşım öznitelik yan tümceleri](../../parallel/openmp/2-7-2-data-sharing-attribute-clauses.md) sayfasında 25.