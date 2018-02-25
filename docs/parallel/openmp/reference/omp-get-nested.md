---
title: omp_get_nested | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- omp_get_nested
dev_langs:
- C++
helpviewer_keywords:
- omp_get_nested OpenMP function
ms.assetid: e9784847-516e-40d3-89f7-b8b6898d8667
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: df6a3fafdb749031ae5e55a58e1e26ccad76985c
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="ompgetnested"></a>omp_get_nested
İç içe geçmiş paralellik etkin olup olmadığını belirten bir değer döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
int omp_get_nested( );  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 Sıfır olmayan, iç içe geçmiş paralellik etkinleştirilir.  
  
## <a name="remarks"></a>Açıklamalar  
 İç içe geçmiş paralellik ile belirtilen [omp_set_nested](../../../parallel/openmp/reference/omp-set-nested.md) ve [OMP_NESTED](../../../parallel/openmp/reference/omp-nested.md).  
  
 Daha fazla bilgi için bkz: [3.1.10 omp_get_nested işlevi](../../../parallel/openmp/3-1-10-omp-get-nested-function.md).  
  
## <a name="example"></a>Örnek  
 Bkz: [omp_set_nested](../../../parallel/openmp/reference/omp-set-nested.md) kullanma örneği için `omp_get_nested`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İşlevler](../../../parallel/openmp/reference/openmp-functions.md)