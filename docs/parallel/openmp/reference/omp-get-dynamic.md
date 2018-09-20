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
ms.openlocfilehash: c2b5a285ef019cd1752b60065f7040d9a937ce38
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46389895"
---
# <a name="ompgetdynamic"></a>omp_get_dynamic

Çalışma zamanı tarafından ayarlanabilir izleyen bir paralel bölgenin içinde kullanılabilir iş parçacığı sayısını gösteren bir değer döndürür.

## <a name="syntax"></a>Sözdizimi

```
int omp_get_dynamic();
```

## <a name="return-value"></a>Dönüş Değeri

Sıfır olmayan iş parçacıkları yerleştirmenin dinamik ayarına etkinleştirilir.

## <a name="remarks"></a>Açıklamalar

İş parçacıkları yerleştirmenin dinamik ayarına belirtilirse [omp_set_dynamic](../../../parallel/openmp/reference/omp-set-dynamic.md) ve [omp_dynamıc](../../../parallel/openmp/reference/omp-dynamic.md).

Daha fazla bilgi için [3.1.7 omp_set_dynamic işlevi](../../../parallel/openmp/3-1-7-omp-set-dynamic-function.md).

## <a name="example"></a>Örnek

Bkz: [omp_set_dynamic](../../../parallel/openmp/reference/omp-set-dynamic.md) kullanma örneği için `omp_get_dynamic`.

## <a name="see-also"></a>Ayrıca Bkz.

[İşlevler](../../../parallel/openmp/reference/openmp-functions.md)