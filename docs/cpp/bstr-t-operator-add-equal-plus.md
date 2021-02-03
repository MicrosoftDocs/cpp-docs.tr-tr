---
description: 'Hakkında daha fazla bilgi edinin: _bstr_t:: operator + =, _bstr_t:: operator +'
title: '_bstr_t:: operator + =, _bstr_t:: operator +'
ms.date: 02/02/2021
f1_keywords:
- _bstr_t::operator+
- _bstr_t::operator+=
helpviewer_keywords:
- += operator [C++], appending strings
- + operator [C++], _bstr_t objects
ms.openlocfilehash: 44a525891ee072ea797026bd022ecae7b62fd6d1
ms.sourcegitcommit: c20734f18d3d49bb38b1628c68b53b54b3eeeb03
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/03/2021
ms.locfileid: "99522527"
---
# <a name="_bstr_toperator--_bstr_toperator-"></a>`_bstr_t::operator +=`, `_bstr_t::operator +`

**Microsoft'a Özgü**

Nesnenin sonuna karakter ekler `_bstr_t` veya iki dizeyi birleştirir.

## <a name="syntax"></a>Sözdizimi

```cpp
_bstr_t& operator+=( const _bstr_t& s1 );
_bstr_t operator+( const _bstr_t& s1 );
friend _bstr_t operator+( const char* s2, const _bstr_t& s1);
friend _bstr_t operator+( const wchar_t* s3, const _bstr_t& s1);
```

### <a name="parameters"></a>Parametreler

*`s1`*\
Bir `_bstr_t` nesnesi.

*`s2`*\
Çok baytlı bir dize.

*`s3`*\
Unicode dizesi.

## <a name="remarks"></a>Açıklamalar

Bu işleçler dize birleştirmesi gerçekleştirir:

- `operator+=( s1 )` Kapsüllendiği karakterleri `BSTR` *`s1`* Bu nesnenin Kapsüllenen sonuna ekler `BSTR` .

- `operator+( s1 )``_bstr_t`Bu nesnenin ve içindeki öğesinin bitiştirerek biçimlendirilmiş yeni olanı döndürür `BSTR` *`s1`* .

- `operator+( s2, s1 )``_bstr_t`Çok baytlı bir dizeyi birleştirerek *`s2`* , Unicode 'a dönüştürülüp, `BSTR` içinde kapsüllenmiş olan yeni bir döndürür *`s1`* .

- `operator+( s3, s1 )``_bstr_t`Unicode dizesini *`s3`* ve kapsüllenmiş ' i birleştirerek biçimlendirilmiş yeni bir döndürür `BSTR` *`s1`* .

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[`_bstr_t` sınıfı](../cpp/bstr-t-class.md)
