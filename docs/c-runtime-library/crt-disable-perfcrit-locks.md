---
title: _CRT_DISABLE_PERFCRIT_LOCKS
ms.date: 11/04/2016
f1_keywords:
- _CRT_DISABLE_PERFCRIT_LOCKS
- CRT_DISABLE_PERFCRIT_LOCKS
helpviewer_keywords:
- CRT_DISABLE_PERFCRIT_LOCKS constant
- _CRT_DISABLE_PERFCRIT_LOCKS constant
ms.assetid: 36cc2d86-cdb1-4b2b-a03c-c0d3818e7c6f
ms.openlocfilehash: b6f4d8dee5577e88aa59af9bff017aab0c7eef89
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57740258"
---
# <a name="crtdisableperfcritlocks"></a>_CRT_DISABLE_PERFCRIT_LOCKS

Performans açısından kritik g/ç işlemlerinde kilitleme devre dışı bırakır.

## <a name="syntax"></a>Sözdizimi

```
#define _CRT_DISABLE_PERFCRIT_LOCKS
```

## <a name="remarks"></a>Açıklamalar

Bu sembol tanımlama miyim/O-bağlı programlarda tek iş parçacıklı bir tek iş parçacıklı g/ç modeli varsaymak tüm g/ç işlemleri zorlayarak performansını geliştirebilirsiniz. Daha fazla bilgi için [birden çok iş parçacıklı kitaplık performansı](../c-runtime-library/multithreaded-libraries-performance.md).

## <a name="see-also"></a>Ayrıca bkz.

[Global Sabitler](../c-runtime-library/global-constants.md)
