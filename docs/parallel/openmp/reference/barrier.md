---
title: engel | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- barrier
dev_langs:
- C++
helpviewer_keywords:
- barrier OpenMP directive
ms.assetid: 5c73ad4f-c768-443a-8f9e-4fd8bc2253c7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c220106d62bf65505c9c5b48085a9ee3e67fe0cb
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46415037"
---
# <a name="barrier"></a>barrier

Takım tüm iş parçacıklarının eşitler; tüm iş parçacıklarının engeli yürütene kadar tüm iş parçacıklarının engeli duraklatın.

## <a name="syntax"></a>Sözdizimi

```
#pragma omp barrier
```

## <a name="remarks"></a>Açıklamalar

`barrier` Yönergesi yok OpenMP yan tümceleri destekler.

Daha fazla bilgi için [2.6.3 barrier yönergesi](../../../parallel/openmp/2-6-3-barrier-directive.md).

## <a name="example"></a>Örnek

Nasıl kullanılacağını gösteren bir örnek `barrier`, bkz: [ana](../../../parallel/openmp/reference/master.md).

## <a name="see-also"></a>Ayrıca Bkz.

[Yönergeler](../../../parallel/openmp/reference/openmp-directives.md)