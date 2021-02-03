---
description: 'Hakkında daha fazla bilgi edinin: _bstr_t ilişkisel işleçler'
title: _bstr_t ilişkisel işleçleri
ms.date: 02/02/2021
f1_keywords:
- _bstr_t::operator>
- _bstr_t::operator==
- _bstr_t::operator>=
- _bstr_t::operator!=
- _bstr_t::operator<
- _bstr_t::operator<=
helpviewer_keywords:
- _bstr_t relational operators[C++]
ms.openlocfilehash: eef66f8165fc1dfbb29730507ee8d3b996800b7b
ms.sourcegitcommit: c20734f18d3d49bb38b1628c68b53b54b3eeeb03
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/03/2021
ms.locfileid: "99522592"
---
# <a name="_bstr_t-relational-operators"></a>`_bstr_t` ilişkisel işleçler

**Microsoft'a Özgü**

İki `_bstr_t` nesneyi karşılaştırır.

## <a name="syntax"></a>Syntax

```cpp
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

[`_bstr_t` sınıfı](../cpp/bstr-t-class.md)
