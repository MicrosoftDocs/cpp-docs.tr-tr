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
ms.openlocfilehash: 510267c7ab00fe22a93dc01342def5fc262ddb04
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62166224"
---
# <a name="varianttattach"></a>_variant_t::Attach

**Microsoft'a özgü**

Bağlanan bir `VARIANT` içine nesne **_variant_t** nesne.

## <a name="syntax"></a>Sözdizimi

```
void Attach(VARIANT& varSrc);
```

#### <a name="parameters"></a>Parametreler

*varSrc*<br/>
A `VARIANT` için eklenecek nesne **_variant_t** nesne.

## <a name="remarks"></a>Açıklamalar

Sahipliğini `VARIANT` , şifrelenmiş olarak. Bu üye işlevi herhangi kapsüllenmiş varolan yayımlar `VARIANT`, ardından sağlanan kopyalar `VARIANT`ve ayarlar, `VARTYPE` emin olmak için VT_EMPTY kaynaklarını tarafından yalnızca yayımlanabilecek **_variant_t** yıkıcı.

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[_variant_t Sınıfı](../cpp/variant-t-class.md)