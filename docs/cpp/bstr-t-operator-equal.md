---
description: 'Hakkında daha fazla bilgi edinin: _bstr_t:: operator ='
title: _bstr_t::operator =
ms.date: 11/04/2016
f1_keywords:
- _bstr_t::operator=
helpviewer_keywords:
- operator = [C++], bstr
- operator= [C++], bstr
ms.assetid: fb31bb1b-ce29-4388-b5fd-8dac830cf18a
ms.openlocfilehash: 78447048a45567df603acf3af0bc51cefbdb187d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97308789"
---
# <a name="_bstr_toperator-"></a>_bstr_t::operator =

**Microsoft'a Özgü**

Varolan bir nesneye yeni bir değer atar `_bstr_t` .

## <a name="syntax"></a>Sözdizimi

```
_bstr_t& operator=(const _bstr_t& s1) throw ( );
_bstr_t& operator=(const char* s2);
_bstr_t& operator=(const wchar_t* s3);
_bstr_t& operator=(const _variant_t& var);
```

#### <a name="parameters"></a>Parametreler

*S1*<br/>
`_bstr_t`Varolan bir nesneye atanacak nesne `_bstr_t` .

*S2*<br/>
Varolan bir nesneye atanacak çok baytlı bir dize `_bstr_t` .

*bekletmeden*<br/>
Varolan bir nesneye atanacak Unicode dizesi `_bstr_t` .

*l*<br/>
`_variant_t`Varolan bir nesneye atanacak nesne `_bstr_t` .

**SON Microsoft 'a özgü**

## <a name="example"></a>Örnek

Bkz. [_bstr_t:: Assign](../cpp/bstr-t-assign.md) **işleç =** kullanma örneği.

## <a name="see-also"></a>Ayrıca bkz.

[_bstr_t sınıfı](../cpp/bstr-t-class.md)
