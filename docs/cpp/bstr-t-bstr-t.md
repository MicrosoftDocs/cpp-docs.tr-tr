---
description: 'Hakkında daha fazla bilgi edinin: _bstr_t:: _bstr_t'
title: _bstr_t::_bstr_t
ms.date: 02/02/2021
f1_keywords:
- _bstr_t::_bstr_t
helpviewer_keywords:
- BSTR object
- _bstr_t method [C++]
- _bstr_t class
ms.openlocfilehash: 0e6913a45b1c4d542e495bc59bc5871f533a1573
ms.sourcegitcommit: c20734f18d3d49bb38b1628c68b53b54b3eeeb03
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/03/2021
ms.locfileid: "99522917"
---
# `_bstr_t::_bstr_t`

**Microsoft'a Özgü**

Bir `_bstr_t` nesnesi oluşturur.

## <a name="syntax"></a>Sözdizimi

```cpp
_bstr_t( ) throw( );
_bstr_t(
   const _bstr_t& s1
) throw( );
_bstr_t(
   const char* s2
);
_bstr_t(
   const wchar_t* s3
);
_bstr_t(
   const _variant_t& var
);
_bstr_t(
   BSTR bstr,
   bool fCopy
);
```

### <a name="parameters"></a>Parametreler

*`s1`*\
`_bstr_t`Kopyalanacak bir nesne.

*`s2`*\
Çok baytlı bir dize.

*`s3`*\
Unicode dizesi

*`var`*\
[_Variant_t](../cpp/variant-t-class.md) nesnesi.

*`bstr`*\
Varolan bir `BSTR` nesnesi.

*`fCopy`*\
İse **`false`** *`bstr`* bağımsız değişken, çağırarak bir kopya oluşturmadan yeni nesneye iliştirilir `SysAllocString` .

## <a name="remarks"></a>Açıklamalar

`_bstr_t`Sınıfı çeşitli oluşturucular sağlar:

`_bstr_t( )`\
`_bstr_t`Null nesneyi kapsülleyen varsayılan bir nesne oluşturur `BSTR` .

`_bstr_t( _bstr_t& s1 )`\
Bir `_bstr_t` nesneyi diğerinin kopyası olarak oluşturur. Bu Oluşturucu, yeni bir tane oluşturmak yerine, kapsüllenmiş nesnenin başvuru sayısını artıran *basit* bir kopya oluşturur `BSTR` .

`_bstr_t( char* s2 )`\
`_bstr_t` `SysAllocString` Yeni bir nesne oluşturmak için çağırarak bir nesne oluşturur `BSTR` ve sonra onu kapsüller. Bu Oluşturucu öncelikle Unicode dönüşümü çok baytlı bir biçimde gerçekleştirir.

`_bstr_t( wchar_t* s3 )`\
`_bstr_t` `SysAllocString` Yeni bir nesne oluşturmak için çağırarak bir nesne oluşturur `BSTR` ve sonra onu kapsüller.

`_bstr_t( _variant_t& var )`\
`_bstr_t` `_variant_t` Önce `BSTR` kapsüllenmiş nesneden bir nesne alarak nesnesinden bir nesne oluşturur `VARIANT` .

`_bstr_t( BSTR bstr, bool fCopy )`\
Varolan bir `_bstr_t` nesneden `BSTR` (bir dizenin aksine) bir nesne oluşturur `wchar_t*` . *`fCopy`* İse **`false`** , sağlanan, kullanarak yeni `BSTR` bir kopya oluşturmadan yeni nesneye iliştirilir `SysAllocString` . Bu Oluşturucu, tür kitaplığı başlıklarındaki sarmalayıcı işlevleri tarafından, bir `BSTR` arabirim yöntemi tarafından döndürülen bir öğesinin sahipliğini kapsüllemek ve sahipliğini almak için kullanılır.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[`_bstr_t` sınıfı](../cpp/bstr-t-class.md)\
[`_variant_t` sınıfı](../cpp/variant-t-class.md)
