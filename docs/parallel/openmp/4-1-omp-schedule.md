---
title: 4.1 OMP_SCHEDULE | Microsoft Docs
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
ms.assetid: d0dce411-2351-4ee9-a1cc-c0322a58b65c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 330e5ea576e3cd779a7c17c21d00b6459f5e7043
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="41-ompschedule"></a>4.1 OMP_SCHEDULE
**OMP_SCHEDULE** yalnızca geçerli **için** ve **için paralel** zamanlama türü olan yönergeleri **çalışma zamanı**. Tanınan zamanlama türlerinden herhangi birini ve isteğe bağlı bir için bu ortam değişkenini ayarlayarak çalışma zamanında tür döngüler zamanlama türü ve Öbek boyutu ayarlanabilir *chunk_size*.  
  
 İçin **için** ve **için paralel** dışındaki bir zamanlama türü olan yönergeleri **çalışma zamanı**, **OMP_SCHEDULE** göz ardı edilir. Bu ortam değişkeni için varsayılan değer uygulaması tanımlanır. Varsa isteğe bağlı *chunk_size* ayarlanmış, değer pozitif olmalıdır. Varsa *chunk_size* ayarlanmazsa 1 değeri kabul edilir, hariç durumunda bir **statik** zamanlama. İçin bir **statik** zamanlama, varsayılan öbek boyutu döngüsünü uygulanan iş parçacığı sayısı bölü döngü yineleme alanına ayarlanır.  
  
 Örnek:  
  
```  
setenv OMP_SCHEDULE "guided,4"  
setenv OMP_SCHEDULE "dynamic"  
```  
  
## <a name="cross-references"></a>Çapraz referanslar:  
  
-   **için** yönerge, bkz: [bölüm 2.4.1](../../parallel/openmp/2-4-1-for-construct.md) sayfasında 11.  
  
-   **Paralel için** yönerge, bkz: [bölüm 2.5.1](../../parallel/openmp/2-5-1-parallel-for-construct.md) sayfasında 16.