---
description: 'Hakkında daha fazla bilgi edinin: _variant_t Ilişkisel Işleçler'
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
ms.openlocfilehash: 0a9c339bc67527e258c0d1f69060cde251c8adb9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97161435"
---
# <a name="_variant_t-relational-operators"></a>_variant_t İlişkisel İşleçleri

**Microsoft'a Özgü**

`_variant_t`Eşitlik veya eşitsizlik için iki nesneyi karşılaştırın.

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
