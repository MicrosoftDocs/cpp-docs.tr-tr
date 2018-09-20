---
title: num_threads | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- num_threads
dev_langs:
- C++
helpviewer_keywords:
- num_threads OpenMP clause
ms.assetid: 09a56fc8-25c7-43e4-bbb5-71cb955d0b93
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 27e39d7db36c121add3598387de52ecb878059b5
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46405274"
---
# <a name="numthreads"></a>num_threads

Bir iş parçacığı takıma iş parçacığı sayısını ayarlar.

## <a name="syntax"></a>Sözdizimi

```
num_threads(num)
```

### <a name="parameters"></a>Parametreler

*sayı*<br/>
İş parçacığı sayısı

## <a name="remarks"></a>Açıklamalar

`num_threads` Yan tümcesi ile aynı işlevlere sahip [omp_set_num_threads](../../../parallel/openmp/reference/omp-set-num-threads.md) işlevi.

`num_threads` Aşağıdaki yönergeleri için geçerlidir:

- [parallel](../../../parallel/openmp/reference/parallel.md)

- [for](../../../parallel/openmp/reference/for-openmp.md)

- [Bölümleri](../../../parallel/openmp/reference/sections-openmp.md)

Daha fazla bilgi için [2.3 parallel yapı](../../../parallel/openmp/2-3-parallel-construct.md).

## <a name="example"></a>Örnek

Bkz: [paralel](../../../parallel/openmp/reference/parallel.md) kullanma örneği için `num_threads` yan tümcesi.

## <a name="see-also"></a>Ayrıca Bkz.

[Yan Tümceler](../../../parallel/openmp/reference/openmp-clauses.md)