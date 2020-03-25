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
ms.openlocfilehash: 9737db6b77483fa55e1dad90b9464752cd8537a5
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80187745"
---
# <a name="_variant_tdetach"></a>_variant_t::Detach

**Microsoft 'a özgü**

Bu `_variant_t` nesnesinden kapsüllenmiş `VARIANT` nesnesini ayırır.

## <a name="syntax"></a>Sözdizimi

```
VARIANT Detach( );
```

## <a name="return-value"></a>Dönüş Değeri

Encapsulated `VARIANT`.

## <a name="remarks"></a>Açıklamalar

Kapsüllenmiş `VARIANT`ayıklar ve döndürür, sonra bu `_variant_t` nesnesini yok etmeden temizler. Bu üye işlevi, `VARIANT` kapsülden kaldırır ve bu `_variant_t` nesnesinin `VARTYPE` VT_EMPTY olarak ayarlar. Burada, [VariantClear](/windows/win32/api/oleauto/nf-oleauto-variantclear) işlevini çağırarak döndürülen `VARIANT` serbest bırakmanız gerekir.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[_variant_t Sınıfı](../cpp/variant-t-class.md)
