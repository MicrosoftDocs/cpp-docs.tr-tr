---
title: omp_unset_nest_lock | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- omp_unset_nest_lock
dev_langs:
- C++
helpviewer_keywords:
- omp_unset_nest_lock OpenMP function
ms.assetid: 1721d061-3f9c-45d7-b479-a665cd0a121d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 03ea941e793f8c3a9f40e0495442deb71b2ffa93
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46402726"
---
# <a name="ompunsetnestlock"></a>omp_unset_nest_lock

Nestable kilit serbest bırakır.

## <a name="syntax"></a>Sözdizimi

```
void omp_unset_nest_lock( 
   omp_nest_lock_t *lock 
);
```

### <a name="parameters"></a>Parametreler

*lock*<br/>
Türünde bir değişken [omp_nest_lock_t](../../../parallel/openmp/reference/omp-nest-lock-t.md) , başlatılan ile [omp_init_nest_lock](../../../parallel/openmp/reference/omp-init-nest-lock.md), iş parçacığı tarafından sahip olunan ve işlev yürütme.

## <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [3.2.4 omp_unset_lock ve omp_unset_nest_lock işlevleri](../../../parallel/openmp/3-2-4-omp-unset-lock-and-omp-unset-nest-lock-functions.md).

## <a name="example"></a>Örnek

Bkz: [omp_init_nest_lock](../../../parallel/openmp/reference/omp-init-nest-lock.md) kullanma örneği için `omp_unset_nest_lock`.

## <a name="see-also"></a>Ayrıca Bkz.

[İşlevler](../../../parallel/openmp/reference/openmp-functions.md)