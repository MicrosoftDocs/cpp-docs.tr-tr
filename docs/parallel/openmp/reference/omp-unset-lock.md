---
title: omp_unset_lock | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- omp_unset_lock
dev_langs:
- C++
helpviewer_keywords:
- omp_unset_lock OpenMP function
ms.assetid: 68fcb728-040b-4bad-979e-aaecb9097a4e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fe6d24c6d4fe6cd1df1eea6f0e575ff5c7947c56
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46417052"
---
# <a name="ompunsetlock"></a>omp_unset_lock

Bir kilidi serbest bırakır.

## <a name="syntax"></a>Sözdizimi

```
void omp_unset_lock(
   omp_lock_t *lock
);
```

### <a name="parameters"></a>Parametreler

*lock*<br/>
Türünde bir değişken [omp_lock_t](../../../parallel/openmp/reference/omp-lock-t.md) , başlatılan ile [omp_init_lock](../../../parallel/openmp/reference/omp-init-lock.md), iş parçacığı tarafından sahip olunan ve işlev yürütme.

## <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [3.2.4 omp_unset_lock ve omp_unset_nest_lock işlevleri](../../../parallel/openmp/3-2-4-omp-unset-lock-and-omp-unset-nest-lock-functions.md).

## <a name="example"></a>Örnek

Bkz: [omp_init_lock](../../../parallel/openmp/reference/omp-init-lock.md) kullanma örneği için `omp_unset_lock`.

## <a name="see-also"></a>Ayrıca Bkz.

[İşlevler](../../../parallel/openmp/reference/openmp-functions.md)