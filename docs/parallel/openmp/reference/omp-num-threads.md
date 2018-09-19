---
title: OMP_NUM_THREADS | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- OMP_NUM_THREADS
dev_langs:
- C++
helpviewer_keywords:
- OMP_NUM_THREADS OpenMP environment variable
ms.assetid: 4b558124-1387-4c30-a6a5-ff5345a9ced6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 39f45b9c81d5339b2b6afe4c77fdc9bac6b5d731
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46091172"
---
# <a name="ompnumthreads"></a>OMP_NUM_THREADS
İş parçacığı sayısı tarafından geçersiz kılınmadığı sürece paralel bölgenin içinde ayarlar [omp_set_num_threads](../../../parallel/openmp/reference/omp-set-num-threads.md) veya [num_threads](../../../parallel/openmp/reference/num-threads.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
set OMP_NUM_THREADS[=num]  
```  
  
### <a name="parameters"></a>Parametreler
  
*sayı*<br/>
Visual C++ uygulamasında 64 adede kadar bir paralel bölgenin içinde istediğiniz iş parçacığı sayısı.  
  
## <a name="remarks"></a>Açıklamalar  
 **OMP_NUM_THREADS** ortam değişkeni tarafından kılınabilir [omp_set_num_threads](../../../parallel/openmp/reference/omp-set-num-threads.md) işlevi ya da [num_threads](../../../parallel/openmp/reference/num-threads.md).  
  
 Varsayılan değer olan `num` Visual C++'da OpenMP standart hiper iş parçacıklı CPU dahil olmak üzere, sanal işlemcilerin sayısını uygulamasıdır.  
  
 Daha fazla bilgi için [4.2 OMP_NUM_THREADS](../../../parallel/openmp/4-2-omp-num-threads.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki komut kümelerini **OMP_NUM_THREADS** 16 ortam değişkeni:  
  
```  
set OMP_NUM_THREADS=16  
```  
  
 Aşağıdaki komut, geçerli ayarı görüntüler **OMP_NUM_THREADS** ortam değişkeni:  
  
```  
set OMP_NUM_THREADS  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Ortam Değişkenleri](../../../parallel/openmp/reference/openmp-environment-variables.md)