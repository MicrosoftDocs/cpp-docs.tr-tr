---
title: OMP_NUM_THREADS | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: OMP_NUM_THREADS
dev_langs: C++
helpviewer_keywords: OMP_NUM_THREADS OpenMP environment variable
ms.assetid: 4b558124-1387-4c30-a6a5-ff5345a9ced6
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 2139ecfc719bd6e5836a67d9387b3ff2f4289bc6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="ompnumthreads"></a>OMP_NUM_THREADS
İş parçacığı sayısı tarafından geçersiz kılınmadığı sürece paralel bölgede ayarlar [omp_set_num_threads](../../../parallel/openmp/reference/omp-set-num-threads.md) veya [num_threads](../../../parallel/openmp/reference/num-threads.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
set OMP_NUM_THREADS[=num]  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Burada,  
  
 `num`  
 Paralel bölgede en fazla 64 Visual C++ uygulamasında istediğiniz iş parçacığı sayısı.  
  
## <a name="remarks"></a>Açıklamalar  
 **OMP_NUM_THREADS** ortam değişkeni geçersiz kılınmış tarafından [omp_set_num_threads](../../../parallel/openmp/reference/omp-set-num-threads.md) işlevi veya [num_threads](../../../parallel/openmp/reference/num-threads.md).  
  
 Varsayılan değer olan `num` Visual C++'da OpenMP standart hiper iş parçacığı CPU'ları da dahil olmak üzere, sanal işlemcilerin sayısı uygulamasıdır.  
  
 Daha fazla bilgi için bkz: [4.2 OMP_NUM_THREADS](../../../parallel/openmp/4-2-omp-num-threads.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki komut kümelerini **OMP_NUM_THREADS** ortam değişkeni 16:  
  
```  
set OMP_NUM_THREADS=16  
```  
  
 Aşağıdaki komut geçerli ayarını görüntüler **OMP_NUM_THREADS** ortam değişkeni:  
  
```  
set OMP_NUM_THREADS  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Ortam değişkenleri](../../../parallel/openmp/reference/openmp-environment-variables.md)