---
title: _variant_t İlişkisel İşleçleri
ms.date: 11/04/2016
f1_keywords:
- _variant_t::operator==
- _variant_t::operator!=
helpviewer_keywords:
- '!= operator'
- relational operators [C++], _variant_t class
- operator!= [C++], variant
- operator!= [C++], relational operators
- operator != [C++], variant
- operator == [C++], variant
- operator== [C++], variant
- operator != [C++], relational operators
- == operator [C++], with specific Visual C++ objects
ms.assetid: 141bacb8-41a2-44dd-b3c0-4ad1f884f4ea
ms.openlocfilehash: 6e0296a2bf4ce97e41fdf6208c3dd1c6b91215dc
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87226951"
---
# <a name="_variant_t-relational-operators"></a>_variant_t İlişkisel İşleçleri

**Microsoft'a Özgü**

`_variant_t`Eşitlik veya eşitsizlik için iki nesneyi karşılaştırın.

## <a name="syntax"></a>Söz dizimi

```
bool operator==(
   const VARIANT& varSrc) const;
bool operator==(
   const VARIANT* pSrc) const;
bool operator!=(
   const VARIANT& varSrc) const;
bool operator!=(
   const VARIANT* pSrc) const;
```

#### <a name="parameters"></a>Parametreler

*varSrc*<br/>
`VARIANT`Nesnesiyle Karşılaştırılacak bir `_variant_t` .

*pSrc*<br/>
`VARIANT`Nesnesiyle Karşılaştırılacak öğesine işaretçisi `_variant_t` .

## <a name="return-value"></a>Dönüş Değeri

**`true`** Eğer Eğer karşılaştırmayla karşılaştırılmaları durumunda, döndürür **`false`** .

## <a name="remarks"></a>Açıklamalar

Bir `_variant_t` nesneyi `VARIANT` , eşitlik veya eşitsizlik için test bir ile karşılaştırır.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[_variant_t sınıfı](../cpp/variant-t-class.md)
