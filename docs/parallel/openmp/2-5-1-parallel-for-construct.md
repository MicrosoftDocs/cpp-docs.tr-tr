---
title: "2.5.1 yapı için parallel | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: a233e7ed-2462-4f7a-9a5d-556ab9f363d8
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7dcd763b68a78e11c3c33bf3d750a26e88ad02ee
ms.sourcegitcommit: 9239c52c05e5cd19b6a72005372179587a47a8e4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/16/2018
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