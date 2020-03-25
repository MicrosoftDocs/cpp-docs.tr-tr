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
ms.openlocfilehash: e0d7ea1a0bcaf8329cff0cdfb0c01154f3c5a73b
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80187576"
---
# <a name="_variant_t-relational-operators"></a>_variant_t İlişkisel İşleçleri

**Microsoft 'a özgü**

Eşitlik veya eşitsizlik için iki `_variant_t` nesnesini karşılaştırın.

## <a name="syntax"></a>Sözdizimi

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
`_variant_t` nesnesiyle Karşılaştırılacak bir `VARIANT`.

*pSrc*<br/>
`_variant_t` nesnesiyle Karşılaştırılacak `VARIANT` işaretçisi.

## <a name="return-value"></a>Dönüş Değeri

Karşılaştırma tutuyorsa **true** , değilse **false** döndürür.

## <a name="remarks"></a>Açıklamalar

, Eşitlik veya eşitsizlik için test eden bir `_variant_t` nesnesini `VARIANT`karşılaştırır.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[_variant_t Sınıfı](../cpp/variant-t-class.md)
