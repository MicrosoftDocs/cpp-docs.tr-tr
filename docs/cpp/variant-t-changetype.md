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
ms.openlocfilehash: c2283158856a6781ab2e12c51f4e2ad0e4f1d531
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81750720"
---
# <a name="_variant_tchangetype"></a>_variant_t::ChangeType

**Microsoft'a Özgü**

`_variant_t` Nesnenin türünü belirtilene `VARTYPE`göre değiştirir.

## <a name="syntax"></a>Sözdizimi

```cpp
void ChangeType(
   VARTYPE vartype,
   const _variant_t* pSrc = NULL
);
```

#### <a name="parameters"></a>Parametreler

*Vartype*<br/>
Bu `VARTYPE` `_variant_t` nesne için.

*pSrc*<br/>
Dönüştürülecek `_variant_t` nesneye işaretçi. Bu değer NULL ise, dönüştürme yerinde yapılır.

## <a name="remarks"></a>Açıklamalar

Bu üye işlev `_variant_t` bir nesneyi `VARTYPE`belirtilen nesneye dönüştürür. *pSrc* NULL ise, dönüştürme yerinde yapılır, `_variant_t` aksi takdirde bu nesne *pSrc* kopyalanır ve sonra dönüştürülür.

**END Microsoft Özel**

## <a name="see-also"></a>Ayrıca bkz.

[_variant_t Sınıfı](../cpp/variant-t-class.md)
