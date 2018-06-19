---
title: omp_get_nested | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- omp_get_nested
dev_langs:
- C++
helpviewer_keywords:
- omp_get_nested OpenMP function
ms.assetid: e9784847-516e-40d3-89f7-b8b6898d8667
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 59900f0a1aba1cbc3bacc5cd1d8832e60aebe30b
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33686886"
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