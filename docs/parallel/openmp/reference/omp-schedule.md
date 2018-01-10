---
title: OMP_SCHEDULE | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: OMP_SCHEDULE
dev_langs: C++
helpviewer_keywords: OMP_SCHEDULE OpenMP environment variable
ms.assetid: 2295a801-e584-4d2f-826f-7ca4c88846a6
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8aa1406b490128657da19f7c48c958d382850d96
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="ompschedule"></a>OMP_SCHEDULE
Davranışını değiştiren [zamanlama](../../../parallel/openmp/reference/schedule.md) yan tümcesi olduğunda `schedule(runtime)` içinde belirtilen bir `for` veya `parallel for` yönergesi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
set OMP_SCHEDULE[=type[,size]]  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Burada,  
  
 `size`(isteğe bağlı)  
 Yineleme boyutunu belirtir. `size`pozitif bir tamsayı olmalıdır. Varsayılan zaman dışında 1'dir `type` statiktir. Geçersiz olduğunda `type` olan `runtime`.  
  
 `type`  
 Zamanlama türü:  
  
-   `dynamic`  
  
-   `guided`  
  
-   `runtime`  
  
-   `static`  
  
## <a name="remarks"></a>Açıklamalar  
 Varsayılan değer OpenMP standart Visual C++ uygulamasında `OMP_SCHEDULE=static,0`.  
  
 Daha fazla bilgi için bkz: [4.1 OMP_SCHEDULE](../../../parallel/openmp/4-1-omp-schedule.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki komut kümelerini **OMP_SCHEDULE** ortam değişkeni:  
  
```  
set OMP_SCHEDULE="guided,2"  
```  
  
 Aşağıdaki komut geçerli ayarını görüntüler **OMP_SCHEDULE** ortam değişkeni:  
  
```  
set OMP_SCHEDULE  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Ortam Değişkenleri](../../../parallel/openmp/reference/openmp-environment-variables.md)