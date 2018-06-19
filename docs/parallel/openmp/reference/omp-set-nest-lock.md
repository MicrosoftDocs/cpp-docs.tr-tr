---
title: omp_set_nest_lock | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- omp_set_nest_lock
dev_langs:
- C++
helpviewer_keywords:
- omp_set_nest_lock OpenMP function
ms.assetid: b98ed889-ff8e-4217-a3e9-3993ed8699af
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e49a63fc4bc8d31583478ee6f61fe7b374bb9f0b
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33691020"
---
# <a name="ompsetnestlock"></a>omp_set_nest_lock
Kilit kullanılabilir oluncaya kadar blokları yürütme iş parçacığı.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
void omp_set_nest_lock(  
   omp_nest_lock_t *lock  
);  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Burada,  
  
 `lock`  
 Türünde bir değişken [omp_nest_lock_t](../../../parallel/openmp/reference/omp-nest-lock-t.md) , başlatılmış ile [omp_init_nest_lock](../../../parallel/openmp/reference/omp-init-nest-lock.md).  
  
## <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için bkz: [3.2.3 omp_set_lock ve omp_set_nest_lock işlevleri](../../../parallel/openmp/3-2-3-omp-set-lock-and-omp-set-nest-lock-functions.md).  
  
## <a name="examples"></a>Örnekler  
 Bkz: [omp_init_nest_lock](../../../parallel/openmp/reference/omp-init-nest-lock.md) kullanma örneği için `omp_set_nest_lock`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İşlevler](../../../parallel/openmp/reference/openmp-functions.md)