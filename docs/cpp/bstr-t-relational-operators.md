---
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
ms.openlocfilehash: 57a9379be6d90cfb574ea0dcc033692762c47990
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2019
ms.locfileid: "65222240"
---
# <a name="bstrt-relational-operators"></a>_bstr_t İlişkisel İşleçleri

**Microsoft'a özgü**

İki karşılaştırır `_bstr_t` nesneleri.

## <a name="syntax"></a>Sözdizimi

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

Bu işleçler karşılaştırabilirsiniz `_bstr_t` sözlüksel nesnelerini. İşleçler TRUE döndürür. karşılaştırmayı tutarsanız, aksi takdirde false değerini döndürür.

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[_bstr_t Sınıfı](../cpp/bstr-t-class.md)