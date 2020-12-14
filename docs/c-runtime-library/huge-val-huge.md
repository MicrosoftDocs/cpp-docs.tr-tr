---
description: 'Hakkında daha fazla bilgi edinin: HUGE_VAL _HUGE'
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
ms.openlocfilehash: c4109b61b9af65681ca2a006a3839e3d0338fa73
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97253149"
---
# <a name="huge_val-_huge"></a>HUGE_VAL, _HUGE

## <a name="syntax"></a>Syntax

```
#include <math.h>
```

## <a name="remarks"></a>Açıklamalar

`HUGE_VAL` en büyük gösterilemeyen Double değeridir. Bu değer, bir hata oluştuğunda birçok çalışma zamanı matematik işlevi tarafından döndürülür. Bazı işlevler için- `HUGE_VAL` döndürülür. `HUGE_VAL` olarak tanımlanır `_HUGE` , ancak çalışma zamanı matematik işlevleri döndürülür `HUGE_VAL` . Ayrıca, `HUGE_VAL` kodunuzda tutarlılık için kullanmanız gerekir.

## <a name="see-also"></a>Ayrıca bkz.

[Global sabitler](../c-runtime-library/global-constants.md)
