---
title: omp_destroy_lock | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- omp_destroy_lock
dev_langs:
- C++
helpviewer_keywords:
- omp_destroy_lock OpenMP function
ms.assetid: b73ab036-b76f-4e42-82ff-c89db2edf7c0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 22ee3b0f262742223c57149d7e828a58910223fe
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46400139"
---
# <a name="ompdestroylock"></a>omp_destroy_lock

Kilit başlamasını iptal eder.

## <a name="syntax"></a>Sözdizimi

```
void omp_destroy_lock(
   omp_lock_t *lock
);
```

### <a name="parameters"></a>Parametreler

*lock*<br/>
Türünde bir değişken [omp_lock_t](../../../parallel/openmp/reference/omp-lock-t.md) , başlatılan ile [omp_init_lock](../../../parallel/openmp/reference/omp-init-lock.md).

## <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [3.2.2 omp_destroy_lock ve omp_destroy_nest_lock işlevleri](../../../parallel/openmp/3-2-2-omp-destroy-lock-and-omp-destroy-nest-lock-functions.md).

## <a name="example"></a>Örnek

Bkz: [omp_init_lock](../../../parallel/openmp/reference/omp-init-lock.md) kullanma örneği için `omp_destroy_lock`.

## <a name="see-also"></a>Ayrıca Bkz.

[İşlevler](../../../parallel/openmp/reference/openmp-functions.md)