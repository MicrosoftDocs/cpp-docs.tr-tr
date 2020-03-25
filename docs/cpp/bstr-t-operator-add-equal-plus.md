---
title: _bstr_t::operator +=, +
ms.date: 11/04/2016
f1_keywords:
- _bstr_t::operator+
- _bstr_t::operator+=
helpviewer_keywords:
- += operator [C++], appending strings
- + operator [C++], _bstr_t objects
ms.assetid: d28316ce-c2c8-4a38-bdb3-44fa4e582c44
ms.openlocfilehash: b9eddca85d66f4978e1b33299ca655cd880cf45e
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80181154"
---
# <a name="_bstr_toperator--"></a>_bstr_t::operator +=, +

**Microsoft 'a özgü**

`_bstr_t` nesnenin sonuna karakterler ekler veya iki dizeyi birleştirir.

## <a name="syntax"></a>Sözdizimi

```
_bstr_t& operator+=( const _bstr_t& s1 );
_bstr_t operator+( const _bstr_t& s1 );
friend _bstr_t operator+( const char* s2, const _bstr_t& s1);
friend _bstr_t operator+( const wchar_t* s3, const _bstr_t& s1);
```

#### <a name="parameters"></a>Parametreler

*S1*<br/>
Bir `_bstr_t` nesnesi.

*S2*<br/>
Çok baytlı bir dize.

*bekletmeden*<br/>
Unicode dizesi.

## <a name="remarks"></a>Açıklamalar

Bu işleçler dize birleştirmesi gerçekleştirir:

- **işleç + = (** *S1* **)** *S1* `BSTR` Kapsüldeki karakterleri bu nesnenin Encapsulated `BSTR`sonuna ekler.

- **operator + (** *S1* **)** Bu nesnenin `BSTR` *S1*ile birleştirerek oluşturulan yeni `_bstr_t` döndürür.

- **+ işleci (** *S2* **&#124;** *S1* **)** *S1*' de kapsüllenmiş `BSTR` bir çok *baytlı dize,* Unicode 'a dönüştürülen bir çok baytlı dize birleştirerek oluşturulan yeni bir `_bstr_t` döndürür.

- **operator + (** *S3* **,** *S1* **)** *S1*içinde kapsüllenmiş `BSTR` bir Unicode dize *S3* ile birleştirerek oluşturulan yeni bir `_bstr_t` döndürür.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[_bstr_t Sınıfı](../cpp/bstr-t-class.md)
