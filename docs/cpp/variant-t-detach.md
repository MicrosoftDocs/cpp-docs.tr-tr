---
title: _variant_t::Detach
ms.date: 11/04/2016
f1_keywords:
- _variant_t::Detach
- _variant_t.Detach
helpviewer_keywords:
- VARIANT object [C++], detatch
- Detach method [C++]
- VARIANT object
ms.assetid: c348ac08-62cf-4657-a16f-974a79c12158
ms.openlocfilehash: 4b19e3c1615912550cdf1eb6a2b0b3f906ee4af9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50522336"
---
# <a name="varianttdetach"></a>_variant_t::Detach

**Microsoft'a özgü**

Kapsüllenmiş ayırır `VARIANT` bu nesneden `_variant_t` nesne.

## <a name="syntax"></a>Sözdizimi

```
VARIANT Detach( );
```

## <a name="return-value"></a>Dönüş Değeri

Kapsüllenmiş `VARIANT`.

## <a name="remarks"></a>Açıklamalar

Ayıklar ve döndürür kapsüllenmiş `VARIANT`, bu temizler `_variant_t` yok olmadan nesne. Bu üye işlevi kaldırır `VARIANT` kapsülleme ve kümeleri `VARTYPE` bu `_variant_t` VT_EMPTY nesnesine. Döndürülen yayın size olan `VARIANT` çağırarak [VariantClear](/previous-versions/windows/desktop/api/oleauto/nf-oleauto-variantclear) işlevi.

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[_variant_t Sınıfı](../cpp/variant-t-class.md)