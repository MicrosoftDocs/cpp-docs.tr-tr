---
description: 'Hakkında daha fazla bilgi edinin: _variant_t::D etach'
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
ms.openlocfilehash: 502903f73f9b149a5f85a6eb1be44687aab20664
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97204699"
---
# <a name="_variant_tdetach"></a>_variant_t::Detach

**Microsoft'a Özgü**

`VARIANT`Bu nesneden kapsüllenmiş nesneyi ayırır `_variant_t` .

## <a name="syntax"></a>Syntax

```
VARIANT Detach( );
```

## <a name="return-value"></a>Dönüş Değeri

Encapsulated `VARIANT` .

## <a name="remarks"></a>Açıklamalar

Kapsülleri ayıklar ve döndürür `VARIANT` , sonra bu `_variant_t` nesneyi yok etmeden temizler. Bu üye işlevi, `VARIANT` ' ın kapsüllemesini kaldırır ve `VARTYPE` Bu `_variant_t` nesnenin öğesini VT_EMPTY olarak ayarlar. Bu, `VARIANT` [VariantClear](/windows/win32/api/oleauto/nf-oleauto-variantclear) işlevini çağırarak döndürülen öğesini serbest bırakmanız gerekir.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[_variant_t sınıfı](../cpp/variant-t-class.md)
