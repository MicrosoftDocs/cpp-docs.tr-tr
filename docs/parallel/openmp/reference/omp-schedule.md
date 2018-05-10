---
title: OMP_SCHEDULE | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- OMP_SCHEDULE
dev_langs:
- C++
helpviewer_keywords:
- OMP_SCHEDULE OpenMP environment variable
ms.assetid: 2295a801-e584-4d2f-826f-7ca4c88846a6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5052aaadc673e38a844ea5b0d1e11ff3a96f3fbe
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
---
# <a name="ompschedule"></a>OMP_SCHEDULE
Davranışını değiştiren [zamanlama](../../../parallel/openmp/reference/schedule.md) yan tümcesi olduğunda `schedule(runtime)` içinde belirtilen bir `for` veya `parallel for` yönergesi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
set OMP_SCHEDULE[=type[,size]]  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Burada,  
  
 `size` (isteğe bağlı)  
 Yineleme boyutunu belirtir. `size` Pozitif bir tamsayı olmalıdır. Varsayılan zaman dışında 1'dir `type` statiktir. Geçersiz olduğunda `type` olan `runtime`.  
  
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