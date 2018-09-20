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
ms.openlocfilehash: 20a7378ba7e7f6dcec55cfe265dd0873bdc1fd38
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46371959"
---
# <a name="ompgetnested"></a>omp_get_nested

İç içe geçmiş paralellik etkin olup olmadığını gösteren bir değer döndürür.

## <a name="syntax"></a>Sözdizimi

```
int omp_get_nested( );
```

## <a name="return-value"></a>Dönüş Değeri

Sıfır olmayan, iç içe geçmiş paralellik etkinse.

## <a name="remarks"></a>Açıklamalar

İç içe geçmiş paralellik belirtilirse [omp_set_nested](../../../parallel/openmp/reference/omp-set-nested.md) ve [OMP_NESTED](../../../parallel/openmp/reference/omp-nested.md).

Daha fazla bilgi için [3.1.10 omp_get_nested işlevi](../../../parallel/openmp/3-1-10-omp-get-nested-function.md).

## <a name="example"></a>Örnek

Bkz: [omp_set_nested](../../../parallel/openmp/reference/omp-set-nested.md) kullanma örneği için `omp_get_nested`.

## <a name="see-also"></a>Ayrıca Bkz.

[İşlevler](../../../parallel/openmp/reference/openmp-functions.md)