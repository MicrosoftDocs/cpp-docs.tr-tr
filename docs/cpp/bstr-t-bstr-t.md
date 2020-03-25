---
title: _bstr_t::_bstr_t
ms.date: 11/04/2016
f1_keywords:
- _bstr_t::_bstr_t
helpviewer_keywords:
- BSTR object
- _bstr_t method [C++]
- _bstr_t class
ms.assetid: 116d994e-5a72-4351-afbe-866c80b4c165
ms.openlocfilehash: 3384da733586c828496a8728a0f5855f92eeec35
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80190475"
---
# <a name="_bstr_t_bstr_t"></a>_bstr_t::_bstr_t

**Microsoft 'a özgü**

`_bstr_t` nesnesi oluşturur.

## <a name="syntax"></a>Sözdizimi

```
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

#### <a name="parameters"></a>Parametreler

*S1*<br/>
Kopyalanacak `_bstr_t` nesne.

*S2*<br/>
Çok baytlı bir dize.

*bekletmeden*<br/>
Unicode dizesi

*var*<br/>
[_Variant_t](../cpp/variant-t-class.md) nesnesi.

*BSTR*<br/>
Varolan bir `BSTR` nesnesi.

*fCopy*<br/>
FALSE ise, *BSTR* bağımsız değişkeni, `SysAllocString`çağırarak bir kopya oluşturmadan yeni nesneye iliştirilir.

## <a name="remarks"></a>Açıklamalar

Aşağıdaki tablo `_bstr_t` oluşturucularını açıklar.

|Oluşturucu|Açıklama|
|-----------------|-----------------|
|`_bstr_t( )`|Null `BSTR` nesnesini kapsülleyen varsayılan bir `_bstr_t` nesnesi oluşturur.|
|`_bstr_t( _bstr_t&`  `s1`  `)`|Bir `_bstr_t` nesnesini diğerinin bir kopyası olarak oluşturur.<br /><br /> Bu, yeni bir tane oluşturmak yerine, kapsüllenmiş `BSTR` nesnesinin başvuru sayısını artıran *basit* bir kopyadır.|
|`_bstr_t( char*`  `s2`  `)`|Yeni bir `BSTR` nesnesi oluşturmak için `SysAllocString` çağırarak ve sonra bunu kapsülleyen bir `_bstr_t` nesnesi oluşturur.<br /><br /> Bu Oluşturucu öncelikle Unicode dönüşümü çok baytlı bir biçimde gerçekleştirir.|
|`_bstr_t( wchar_t*`  `s3`  `)`|Yeni bir `BSTR` nesnesi oluşturmak için `SysAllocString` çağırarak ve sonra bunu kapsülleyen bir `_bstr_t` nesnesi oluşturur.|
|`_bstr_t( _variant_t&`  `var`  `)`|Önce kapsüllenmiş VARIANT nesnesinden bir `BSTR` nesnesi alarak `_variant_t` nesnesinden bir `_bstr_t` nesnesi oluşturur.|
|`_bstr_t( BSTR``bstr` `, bool``fCopy``)`|Varolan bir `BSTR` (`wchar_t*` bir dizenin aksine) bir `_bstr_t` nesnesi oluşturur. *FCopy* yanlış ise, sağlanan `BSTR` yeni bir kopyasını `SysAllocString`ile yeni bir kopya oluşturmadan eklenir.<br /><br /> Bu Oluşturucu, tür kitaplığı başlıklarındaki sarmalayıcı işlevleri tarafından, bir arabirim yöntemi tarafından döndürülen bir `BSTR` kapsüllemek ve sahipliğini almak için kullanılır.|

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[_bstr_t Sınıfı](../cpp/bstr-t-class.md)<br/>
[_variant_t Sınıfı](../cpp/variant-t-class.md)
