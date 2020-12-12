---
description: ': _Variant_t:: Attach hakkında daha fazla bilgi edinin'
title: _variant_t::Attach
ms.date: 11/04/2016
f1_keywords:
- _variant_t::Attach
- _variant_t.Attach
helpviewer_keywords:
- Attach method [C++]
- VARIANT object [C++], attach
- VARIANT object
ms.assetid: 2f02bd08-2306-4477-aa88-d2a5dee2b859
ms.openlocfilehash: de13b1e8138eb24971e52165ee84fc92d97ca3d9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97116658"
---
# <a name="_variant_tattach"></a>_variant_t::Attach

**Microsoft'a Özgü**

`VARIANT` **_Variant_t** nesnesine bir nesne iliştirir.

## <a name="syntax"></a>Sözdizimi

```cpp
void Attach(VARIANT& varSrc);
```

#### <a name="parameters"></a>Parametreler

*varSrc*<br/>
`VARIANT`Bu **_variant_t** nesnesine eklenecek bir nesne.

## <a name="remarks"></a>Açıklamalar

' Nin sahipliğini, `VARIANT` kapsülleyerek alır. Bu üye işlevi, var olan kapsüllenir `VARIANT` , ardından sağlanan ' ı kopyalar `VARIANT` ve `VARTYPE` kaynakların yalnızca **_variant_t** yıkıcısı tarafından yayınlanabilecek şekilde VT_EMPTY olarak ayarlar.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[_variant_t sınıfı](../cpp/variant-t-class.md)
