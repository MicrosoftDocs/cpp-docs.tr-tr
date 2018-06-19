---
title: omp_get_dynamic | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- omp_get_dynamic
dev_langs:
- C++
helpviewer_keywords:
- omp_get_dynamic OpenMP function
ms.assetid: efa843c5-7266-4a75-8db3-22992663d9db
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d97cae8091f88c283412b36ef757b03c72f7580d
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33691280"
---
# <a name="ompgetdynamic"></a>omp_get_dynamic
Çalışma zamanı tarafından ayarlanabilir sonraki paralel bölgede kullanılabilir iş parçacığı sayısını belirten bir değer döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
int omp_get_dynamic();  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 Sıfır olmayan iş parçacıklarının dinamik ayarlama etkinleştirilir.  
  
## <a name="remarks"></a>Açıklamalar  
 İş parçacığı dinamik ayarlama ile belirtilen [omp_set_dynamic](../../../parallel/openmp/reference/omp-set-dynamic.md) ve [omp_dynamıc](../../../parallel/openmp/reference/omp-dynamic.md).  
  
 Daha fazla bilgi için bkz: [3.1.7 omp_set_dynamic işlevi](../../../parallel/openmp/3-1-7-omp-set-dynamic-function.md).  
  
## <a name="example"></a>Örnek  
 Bkz: [omp_set_dynamic](../../../parallel/openmp/reference/omp-set-dynamic.md) kullanma örneği için `omp_get_dynamic`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İşlevler](../../../parallel/openmp/reference/openmp-functions.md)