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
ms.openlocfilehash: 3f74f9d8f4f4bcff90c1b8204851814adfe84a4f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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