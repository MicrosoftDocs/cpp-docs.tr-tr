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
ms.openlocfilehash: b0692c9befaa6b7e787ada624dcbb56b074c9f9d
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80160469"
---
# <a name="_variant_tchangetype"></a>_variant_t::ChangeType

**Microsoft 'a özgü**

`_variant_t` nesnesinin türünü belirtilen `VARTYPE`değiştirir.

## <a name="syntax"></a>Sözdizimi

```
void ChangeType(
   VARTYPE vartype,
   const _variant_t* pSrc = NULL
);
```

#### <a name="parameters"></a>Parametreler

*vartype*<br/>
Bu `_variant_t` nesnesinin `VARTYPE`.

*pSrc*<br/>
Dönüştürülecek `_variant_t` nesnesine yönelik bir işaretçi. Bu değer NULL ise, dönüştürme yerinde yapılır.

## <a name="remarks"></a>Açıklamalar

Bu üye işlevi bir `_variant_t` nesnesini belirtilen `VARTYPE`dönüştürür. *PSrc* null ise, dönüştürme yerinde yapılır, aksi takdirde bu `_variant_t` nesnesi *pSrc* 'den kopyalanır ve sonra dönüştürülür.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[_variant_t Sınıfı](../cpp/variant-t-class.md)
