---
title: _variant_t ilişkisel işleçleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _variant_t::operator==
- _variant_t::operator!=
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 95cb1ac663607f26c4f168c2e98910f5b41963c0
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46040178"
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