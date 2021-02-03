---
description: 'Hakkında daha fazla bilgi edinin: _bstr_t:: operator ='
title: _bstr_t::operator =
ms.date: 02/02/2021
f1_keywords:
- _bstr_t::operator=
helpviewer_keywords:
- operator = [C++], bstr
- operator= [C++], bstr
ms.openlocfilehash: d021ba013190ddee262b8644e16876401be846dc
ms.sourcegitcommit: c20734f18d3d49bb38b1628c68b53b54b3eeeb03
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/03/2021
ms.locfileid: "99522722"
---
# `_bstr_t::operator =`

**Microsoft'a Özgü**

Varolan bir nesneye yeni bir değer atar `_bstr_t` .

## <a name="syntax"></a>Sözdizimi

```cpp
_bstr_t& operator=(const _bstr_t& s1) throw ( );
_bstr_t& operator=(const char* s2);
_bstr_t& operator=(const wchar_t* s3);
_bstr_t& operator=(const _variant_t& var);
```

### <a name="parameters"></a>Parametreler

*`s1`*\
`_bstr_t`Varolan bir nesneye atanacak nesne `_bstr_t` .

*`s2`*\
Varolan bir nesneye atanacak çok baytlı bir dize `_bstr_t` .

*`s3`*\
Varolan bir nesneye atanacak Unicode dizesi `_bstr_t` .

*`var`*\
`_variant_t`Varolan bir nesneye atanacak nesne `_bstr_t` .

**SON Microsoft 'a özgü**

## <a name="example"></a>Örnek

Tarafından [`_bstr_t::Assign`](../cpp/bstr-t-assign.md) kullanılan bir örnek için bkz **`operator=`** ..

## <a name="see-also"></a>Ayrıca bkz.

[`_bstr_t` sınıfı](../cpp/bstr-t-class.md)
