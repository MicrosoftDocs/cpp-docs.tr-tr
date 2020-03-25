---
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
ms.openlocfilehash: 3792ed4d0fcd86c4a4e846771c450413fda130b5
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80187771"
---
# <a name="_variant_tattach"></a>_variant_t::Attach

**Microsoft 'a özgü**

**_Variant_t** nesnesine bir `VARIANT` nesnesi ekler.

## <a name="syntax"></a>Sözdizimi

```
void Attach(VARIANT& varSrc);
```

#### <a name="parameters"></a>Parametreler

*varSrc*<br/>
Bu **_variant_t** nesnesine eklenecek `VARIANT` nesnesi.

## <a name="remarks"></a>Açıklamalar

`VARIANT` sahipliğini, kapsülleyerek alır. Bu üye işlevi, mevcut tüm kapsüllenmiş `VARIANT`serbest bırakır, sonra sağlanan `VARIANT`kopyalar ve `VARTYPE` kaynakların yalnızca **_variant_t** yıkıcısı tarafından yayınlandığından emin olmak için VT_EMPTY olarak ayarlar.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[_variant_t Sınıfı](../cpp/variant-t-class.md)
