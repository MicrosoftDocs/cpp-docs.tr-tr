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
ms.openlocfilehash: c29ec07f9a912fb66adc391465885da8030cc466
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
 [Ortam değişkenleri](../../../parallel/openmp/reference/openmp-environment-variables.md)