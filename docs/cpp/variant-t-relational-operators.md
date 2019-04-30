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
ms.openlocfilehash: e0d26247868440f47c73422510ac0e998f8e8dee
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62403301"
---
# <a name="variantt-relational-operators"></a>_variant_t İlişkisel İşleçleri

**Microsoft'a özgü**

Karşılaştırabilirsiniz `_variant_t` eşitlik ve eşitsizlik için nesneleri.

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
A `VARIANT` ile Karşılaştırılacak `_variant_t` nesne.

*pSrc*<br/>
İşaretçi `VARIANT` ile Karşılaştırılacak `_variant_t` nesne.

## <a name="return-value"></a>Dönüş Değeri

Döndürür **true** karşılaştırma tutuyorsa **false** Aksi takdirde.

## <a name="remarks"></a>Açıklamalar

Karşılaştıran bir `_variant_t` nesnesi ile bir `VARIANT`, eşitlik ve eşitsizlik için test etme.

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[_variant_t Sınıfı](../cpp/variant-t-class.md)