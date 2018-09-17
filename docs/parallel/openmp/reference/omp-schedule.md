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
ms.openlocfilehash: 8d873d29d5ac6de1073c1ba3f3065dd015cde1f5
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45720453"
---
# <a name="ompschedule"></a>OMP_SCHEDULE
Davranışını değiştiren [zamanlama](../../../parallel/openmp/reference/schedule.md) yan tümcesi olduğunda `schedule(runtime)` belirtilen bir `for` veya `parallel for` yönergesi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
set OMP_SCHEDULE[=type[,size]]  
```  
  
## <a name="arguments"></a>Arguments

*Boyutu*<br/>
(İsteğe bağlı) Yinelemeler boyutunu belirtir. `size` Pozitif bir tamsayı olmalıdır. Varsayılan değer 1, aşağıdakiler haricinde `type` statiktir. Geçersiz zaman `type` olduğu `runtime`.  
  
 `type`  
 Zamanlama türü:  
  
-   `dynamic`  
  
-   `guided`  
  
-   `runtime`  
  
-   `static`  
  
## <a name="remarks"></a>Açıklamalar  
 Varsayılan değer OpenMP standart Visual C++ uygulamasında `OMP_SCHEDULE=static,0`.  
  
 Daha fazla bilgi için [4.1 OMP_SCHEDULE](../../../parallel/openmp/4-1-omp-schedule.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki komut kümelerini **OMP_SCHEDULE** ortam değişkeni:  
  
```  
set OMP_SCHEDULE="guided,2"  
```  
  
 Aşağıdaki komut, geçerli ayarı görüntüler **OMP_SCHEDULE** ortam değişkeni:  
  
```  
set OMP_SCHEDULE  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Ortam Değişkenleri](../../../parallel/openmp/reference/openmp-environment-variables.md)