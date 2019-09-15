---
title: HUGE_VAL, _HUGE
ms.date: 11/04/2016
api_name:
- _HUGE
api_location:
- msvcrt.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _HUGE
- HUGE_VAL
helpviewer_keywords:
- _HUGE constant
- HUGE_VAL constant
- double value
ms.assetid: 3f044b45-02cd-46b2-b1de-87fd0441dd6a
ms.openlocfilehash: 3a0469b7158e765b1b1c6f34cb01c0e90beb1401
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70940272"
---
# <a name="huge_val-_huge"></a>HUGE_VAL, _HUGE

## <a name="syntax"></a>Sözdizimi

```
#include <math.h>
```

## <a name="remarks"></a>Açıklamalar

`HUGE_VAL`en büyük gösterilemeyen Double değeridir. Bu değer, bir hata oluştuğunda birçok çalışma zamanı matematik işlevi tarafından döndürülür. Bazı işlevler için-`HUGE_VAL` döndürülür. `HUGE_VAL`olarak `_HUGE`tanımlanır, ancak çalışma zamanı matematik işlevleri döndürülür `HUGE_VAL`. Ayrıca, kodunuzda tutarlılık `HUGE_VAL` için kullanmanız gerekir.

## <a name="see-also"></a>Ayrıca bkz.

[Global Sabitler](../c-runtime-library/global-constants.md)
