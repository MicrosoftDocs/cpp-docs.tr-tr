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
ms.openlocfilehash: d0822dfc730cbbb64f8364e6fa8fe8bc7207f9f9
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81750734"
---
# <a name="_variant_tattach"></a>_variant_t::Attach

**Microsoft'a Özgü**

nesneyi `VARIANT` **_variant_t** nesneye bağlar.

## <a name="syntax"></a>Sözdizimi

```cpp
void Attach(VARIANT& varSrc);
```

#### <a name="parameters"></a>Parametreler

*varSrc*<br/>
Bu `VARIANT` **_variant_t** nesneye iliştirilecek bir nesne.

## <a name="remarks"></a>Açıklamalar

`VARIANT` Kapsülleyerek sahiplenir. Bu üye işlev, varolan `VARIANT`herhangi bir kapsüllenmiş `VARIANT`serbest bırakır, sonra verilen kopyalar , ve kaynakları nın sadece `VARTYPE` **_variant_t** yıkıcı tarafından serbest bırakılabilir emin olmak için VT_EMPTY ayarlar.

**END Microsoft Özel**

## <a name="see-also"></a>Ayrıca bkz.

[_variant_t Sınıfı](../cpp/variant-t-class.md)
