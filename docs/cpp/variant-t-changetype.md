---
description: 'Hakkında daha fazla bilgi edinin: _variant_t:: ChangeType'
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
ms.openlocfilehash: 32ce43f1d9afb388c97e5271927113c71d31bb92
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97116632"
---
# <a name="_variant_tchangetype"></a>_variant_t::ChangeType

**Microsoft'a Özgü**

`_variant_t`Nesnenin türünü gösterilen şekilde değiştirir `VARTYPE` .

## <a name="syntax"></a>Sözdizimi

```cpp
void ChangeType(
   VARTYPE vartype,
   const _variant_t* pSrc = NULL
);
```

#### <a name="parameters"></a>Parametreler

*vartype*<br/>
`VARTYPE`Bu nesne için `_variant_t` .

*pSrc*<br/>
Dönüştürülecek nesneye yönelik bir işaretçi `_variant_t` . Bu değer NULL ise, dönüştürme yerinde yapılır.

## <a name="remarks"></a>Açıklamalar

Bu üye işlevi, bir `_variant_t` nesneyi belirtilen öğesine dönüştürür `VARTYPE` . *PSrc* null ise, dönüştürme yerinde yapılır, aksi takdirde bu `_variant_t` nesne *pSrc* 'den kopyalanır ve sonra dönüştürülür.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[_variant_t sınıfı](../cpp/variant-t-class.md)
