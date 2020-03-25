---
title: _bstr_t::operator =
ms.date: 11/04/2016
f1_keywords:
- _bstr_t::operator=
helpviewer_keywords:
- operator = [C++], bstr
- operator= [C++], bstr
ms.assetid: fb31bb1b-ce29-4388-b5fd-8dac830cf18a
ms.openlocfilehash: 5b7f499dd84a67020232aab84966647378daadad
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80181076"
---
# <a name="_bstr_toperator-"></a>_bstr_t::operator =

**Microsoft 'a özgü**

Varolan bir `_bstr_t` nesnesine yeni bir değer atar.

## <a name="syntax"></a>Sözdizimi

```
_bstr_t& operator=(const _bstr_t& s1) throw ( );
_bstr_t& operator=(const char* s2);
_bstr_t& operator=(const wchar_t* s3);
_bstr_t& operator=(const _variant_t& var);
```

#### <a name="parameters"></a>Parametreler

*S1*<br/>
Var olan bir `_bstr_t` nesnesine atanacak `_bstr_t` nesnesi.

*S2*<br/>
Mevcut bir `_bstr_t` nesnesine atanacak çok baytlı bir dize.

*bekletmeden*<br/>
Varolan bir `_bstr_t` nesnesine atanacak Unicode dizesi.

*var*<br/>
Var olan bir `_bstr_t` nesnesine atanacak `_variant_t` nesnesi.

**SON Microsoft 'a özgü**

## <a name="example"></a>Örnek

Bkz. [_bstr_t:: Assign](../cpp/bstr-t-assign.md) **işleç =** kullanma örneği.

## <a name="see-also"></a>Ayrıca bkz.

[_bstr_t Sınıfı](../cpp/bstr-t-class.md)
