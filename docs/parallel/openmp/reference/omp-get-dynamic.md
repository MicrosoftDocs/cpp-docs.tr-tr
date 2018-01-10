---
title: omp_get_dynamic | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: omp_get_dynamic
dev_langs: C++
helpviewer_keywords: omp_get_dynamic OpenMP function
ms.assetid: efa843c5-7266-4a75-8db3-22992663d9db
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2715b7b27871f6b6ee0449bf96b81bef727dd45b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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