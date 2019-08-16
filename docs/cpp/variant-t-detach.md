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
ms.openlocfilehash: 8426c80af04b2c0906af150ea3e91304335e9f69
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69500555"
---
# <a name="_variant_tdetach"></a>_variant_t::Detach

**Microsoft 'a özgü**

`VARIANT` Bu`_variant_t` nesneden kapsüllenmiş nesneyi ayırır.

## <a name="syntax"></a>Sözdizimi

```
VARIANT Detach( );
```

## <a name="return-value"></a>Dönüş Değeri

Encapsulated `VARIANT`.

## <a name="remarks"></a>Açıklamalar

Kapsülleri `VARIANT`ayıklar ve döndürür, sonra bu `_variant_t` nesneyi yok etmeden temizler. Bu üye işlevi, `VARIANT` ' `VARTYPE` ın kapsüllemesini kaldırır ve bu `_variant_t` nesnenin öğesini VT_EMPTY olarak ayarlar. Bu, `VARIANT` [VariantClear](/windows/win32/api/oleauto/nf-oleauto-variantclear) işlevini çağırarak döndürülen öğesini serbest bırakmanız gerekir.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[_variant_t Sınıfı](../cpp/variant-t-class.md)