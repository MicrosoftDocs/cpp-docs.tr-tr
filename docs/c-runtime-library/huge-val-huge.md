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
ms.openlocfilehash: e6e3ec4c59ad22510233289d901fd3a89cb0d257
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57743175"
---
# <a name="hugeval-huge"></a>HUGE_VAL, _HUGE

## <a name="syntax"></a>Sözdizimi

```
#include <math.h>
```

## <a name="remarks"></a>Açıklamalar

`HUGE_VAL` gösterilebilir en büyük çift değer olacaktır. Bu değer, bir hata oluştuğunda birçok çalışma zamanı matematik işlevleri tarafından döndürülür. Bazı işlevler için-`HUGE_VAL` döndürülür. `HUGE_VAL` olarak tanımlanan `_HUGE`, ancak çalışma zamanı matematik işlevleri dönüş `HUGE_VAL`. Ayrıca kullanmalısınız `HUGE_VAL` tutarlılık için kod.

## <a name="see-also"></a>Ayrıca bkz.

[Global Sabitler](../c-runtime-library/global-constants.md)
