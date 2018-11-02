---
title: _variant_t::ChangeType
ms.date: 11/04/2016
f1_keywords:
- _variant_t::ChangeType
- _variant_t.ChangeType
helpviewer_keywords:
- ChangeType method [C++]
- VARIANT object [C++], ChangeType
- VARIANT object
ms.assetid: 829d2eeb-3338-4a88-9dce-0ca145f47aac
ms.openlocfilehash: 319c4fde808932e86021ee59b051261c43ca2edd
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50471246"
---
# <a name="varianttchangetype"></a>_variant_t::ChangeType

**Microsoft'a özgü**

Değişiklikleri türde `_variant_t` belirtilen nesneye `VARTYPE`.

## <a name="syntax"></a>Sözdizimi

```
void ChangeType(
   VARTYPE vartype,
   const _variant_t* pSrc = NULL
);
```

#### <a name="parameters"></a>Parametreler

*VarType*<br/>
`VARTYPE` Bu `_variant_t` nesne.

*pSrc*<br/>
Bir işaretçi `_variant_t` dönüştürülecek nesne. Bu değer NULL ise, yerinde dönüştürme yapılır.

## <a name="remarks"></a>Açıklamalar

Bu üye işlevi dönüştürür bir `_variant_t` belirtilen nesnede `VARTYPE`. Varsa *pSrc* NULL ise dönüştürme yerine, aksi takdirde bu yapılır `_variant_t` nesne kopyalandığına *pSrc* ve sonra dönüştürülür.

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[_variant_t Sınıfı](../cpp/variant-t-class.md)