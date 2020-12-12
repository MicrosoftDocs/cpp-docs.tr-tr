---
description: 'Hakkında daha fazla bilgi edinin: _bstr_t Ilişkisel Işleçler'
title: _bstr_t İlişkisel İşleçleri
ms.date: 05/07/2019
f1_keywords:
- _bstr_t::operator>
- _bstr_t::operator==
- _bstr_t::operator>=
- _bstr_t::operator!=
- _bstr_t::operator<
- _bstr_t::operator<=
- _bstr_t::operator!
helpviewer_keywords:
- _bstr_t [C++]
ms.assetid: e153da72-37c3-4d8a-b8eb-730d65da64dd
ms.openlocfilehash: 3d34c83d9547bb9d52e43174cac2acd259717e76
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97308698"
---
# <a name="_bstr_t-relational-operators"></a>_bstr_t İlişkisel İşleçleri

**Microsoft'a Özgü**

İki `_bstr_t` nesneyi karşılaştırır.

## <a name="syntax"></a>Syntax

```
bool operator!( ) const throw( );
bool operator==(const _bstr_t& str) const throw( );
bool operator!=(const _bstr_t& str) const throw( );
bool operator<(const _bstr_t& str) const throw( );
bool operator>(const _bstr_t& str) const throw( );
bool operator<=(const _bstr_t& str) const throw( );
bool operator>=(const _bstr_t& str) const throw( );
```

## <a name="remarks"></a>Açıklamalar

Bu işleçler iki `_bstr_t` nesne lexıgrafik ile karşılaştırılır. İşleçler, **`true`** karşılaştırmalar, tersi durumda döndürülür **`false`** .

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[_bstr_t sınıfı](../cpp/bstr-t-class.md)
