---
title: HUGE_VAL, _HUGE
ms.date: 11/04/2016
apiname:
- _HUGE
apilocation:
- msvcrt.dll
apitype: DLLExport
f1_keywords:
- _HUGE
- HUGE_VAL
helpviewer_keywords:
- _HUGE constant
- HUGE_VAL constant
- double value
ms.assetid: 3f044b45-02cd-46b2-b1de-87fd0441dd6a
ms.openlocfilehash: b1d9b099684d9671a60dd1afb1e6692e3c0d2a65
ms.sourcegitcommit: a1fad0a266b20b313364a74b16c9ac45d089b1e9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/11/2019
ms.locfileid: "54220484"
---
# <a name="hugeval-huge"></a>HUGE_VAL, _HUGE

## <a name="syntax"></a>Sözdizimi

```
#include <math.h>
```

## <a name="remarks"></a>Açıklamalar

`HUGE_VAL` gösterilebilir en büyük çift değer olacaktır. Bu değer, bir hata oluştuğunda birçok çalışma zamanı matematik işlevleri tarafından döndürülür. Bazı işlevler için-`HUGE_VAL` döndürülür. `HUGE_VAL` olarak tanımlanan `_HUGE`, ancak çalışma zamanı matematik işlevleri dönüş `HUGE_VAL`. Ayrıca kullanmalısınız `HUGE_VAL` tutarlılık için kod.

## <a name="see-also"></a>Ayrıca Bkz.

[Global Sabitler](../c-runtime-library/global-constants.md)
