---
title: 4.1 OMP_SCHEDULE | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: d0dce411-2351-4ee9-a1cc-c0322a58b65c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7e13332077a40e741f56b5602ac5197bbdfef071
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
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