---
title: _bstr_t::operator =
ms.date: 11/04/2016
f1_keywords:
- _bstr_t::operator=
helpviewer_keywords:
- operator = [C++], bstr
- operator= [C++], bstr
ms.assetid: fb31bb1b-ce29-4388-b5fd-8dac830cf18a
ms.openlocfilehash: 97f0100d8a34253f3a1375d34b887d3d31a77f43
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62350877"
---
# <a name="bstrtoperator-"></a>_bstr_t::operator =

**Microsoft'a özgü**

Mevcut bir yeni bir değer atar `_bstr_t` nesne.

## <a name="syntax"></a>Sözdizimi

```
_bstr_t& operator=(const _bstr_t& s1) throw ( );
_bstr_t& operator=(const char* s2);
_bstr_t& operator=(const wchar_t* s3);
_bstr_t& operator=(const _variant_t& var);
```

#### <a name="parameters"></a>Parametreler

*s1*<br/>
A `_bstr_t` varolan atanacak nesne `_bstr_t` nesne.

*s2*<br/>
Mevcut bir atanacak çok baytlı bir dize `_bstr_t` nesne.

*S3*<br/>
Mevcut bir atanacak bir Unicode dize `_bstr_t` nesne.

*var*<br/>
A `_variant_t` varolan atanacak nesne `_bstr_t` nesne.

**END Microsoft özgü**

## <a name="example"></a>Örnek

Bkz: [_bstr_t::Assign](../cpp/bstr-t-assign.md) kullanma örneği için **işleç =**.

## <a name="see-also"></a>Ayrıca bkz.

[_bstr_t Sınıfı](../cpp/bstr-t-class.md)