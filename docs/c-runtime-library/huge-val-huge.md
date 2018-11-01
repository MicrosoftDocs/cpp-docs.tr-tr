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
ms.openlocfilehash: 96b05bc2f7b608c31a12493a4f1b71535b13dc4f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50630093"
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