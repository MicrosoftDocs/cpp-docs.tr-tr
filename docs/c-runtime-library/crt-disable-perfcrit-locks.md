---
title: _CRT_DISABLE_PERFCRIT_LOCKS | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- _CRT_DISABLE_PERFCRIT_LOCKS
- CRT_DISABLE_PERFCRIT_LOCKS
dev_langs:
- C++
helpviewer_keywords:
- CRT_DISABLE_PERFCRIT_LOCKS constant
- _CRT_DISABLE_PERFCRIT_LOCKS constant
ms.assetid: 36cc2d86-cdb1-4b2b-a03c-c0d3818e7c6f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bd01cbddac128e2369971d07320ff95986d822f9
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46053901"
---
# <a name="crtdisableperfcritlocks"></a>_CRT_DISABLE_PERFCRIT_LOCKS

Performans açısından kritik g/ç işlemlerinde kilitleme devre dışı bırakır.

## <a name="syntax"></a>Sözdizimi

```
#define _CRT_DISABLE_PERFCRIT_LOCKS
```

## <a name="remarks"></a>Açıklamalar

Bu sembol tanımlama miyim/O-bağlı programlarda tek iş parçacıklı bir tek iş parçacıklı g/ç modeli varsaymak tüm g/ç işlemleri zorlayarak performansını geliştirebilirsiniz. Daha fazla bilgi için [birden çok iş parçacıklı kitaplık performansı](../c-runtime-library/multithreaded-libraries-performance.md).

## <a name="see-also"></a>Ayrıca Bkz.

[Global Sabitler](../c-runtime-library/global-constants.md)