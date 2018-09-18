---
title: _variant_t::ChangeType | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _variant_t::ChangeType
- _variant_t.ChangeType
dev_langs:
- C++
helpviewer_keywords:
- ChangeType method [C++]
- VARIANT object [C++], ChangeType
- VARIANT object
ms.assetid: 829d2eeb-3338-4a88-9dce-0ca145f47aac
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5a2883cba0d04bbed38ec44e8d00fdab0d4d5695
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46021050"
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