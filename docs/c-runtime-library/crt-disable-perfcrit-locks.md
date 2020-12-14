---
description: 'Hakkında daha fazla bilgi edinin: _CRT_DISABLE_PERFCRIT_LOCKS'
title: _CRT_DISABLE_PERFCRIT_LOCKS
ms.date: 11/04/2016
f1_keywords:
- _CRT_DISABLE_PERFCRIT_LOCKS
- CRT_DISABLE_PERFCRIT_LOCKS
helpviewer_keywords:
- CRT_DISABLE_PERFCRIT_LOCKS constant
- _CRT_DISABLE_PERFCRIT_LOCKS constant
ms.assetid: 36cc2d86-cdb1-4b2b-a03c-c0d3818e7c6f
ms.openlocfilehash: b96e29fad635ac9e7f3d622ace3c43bb26c8805a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97195690"
---
# <a name="_crt_disable_perfcrit_locks"></a>_CRT_DISABLE_PERFCRIT_LOCKS

G/ç işlemlerinde performans açısından kritik kilitlemeyi devre dışı bırakır.

## <a name="syntax"></a>Syntax

```
#define _CRT_DISABLE_PERFCRIT_LOCKS
```

## <a name="remarks"></a>Açıklamalar

Bu sembolün tanımlanması, tüm g/ç işlemlerini tek iş parçacıklı g/ç modelinin kabul etmek üzere zorlayarak, tek iş parçacıklı g/ç ile bağlantılı programlardaki performansı iyileştirebilir. Daha fazla bilgi için bkz. çok [Iş parçacıklı kitaplıklar performansı](../c-runtime-library/multithreaded-libraries-performance.md).

## <a name="see-also"></a>Ayrıca bkz.

[Global sabitler](../c-runtime-library/global-constants.md)
