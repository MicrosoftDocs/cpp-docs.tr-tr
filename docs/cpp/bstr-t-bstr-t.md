---
description: 'Hakkında daha fazla bilgi edinin: _bstr_t:: _bstr_t'
title: _bstr_t::_bstr_t
ms.date: 11/04/2016
f1_keywords:
- _bstr_t::_bstr_t
helpviewer_keywords:
- BSTR object
- _bstr_t method [C++]
- _bstr_t class
ms.assetid: 116d994e-5a72-4351-afbe-866c80b4c165
ms.openlocfilehash: efc28b98ecbc6e22c2a78c89e46c08d94e6ce72d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97229424"
---
# <a name="_bstr_t_bstr_t"></a>_bstr_t::_bstr_t

**Microsoft'a Özgü**

Bir `_bstr_t` nesnesi oluşturur.

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
`_bstr_t`Kopyalanacak bir nesne.

*S2*<br/>
Çok baytlı bir dize.

*bekletmeden*<br/>
Unicode dizesi

*l*<br/>
[_Variant_t](../cpp/variant-t-class.md) nesnesi.

*bstr*<br/>
Varolan bir `BSTR` nesnesi.

*fCopy*<br/>
İse **`false`** , *BSTR* bağımsız değişkeni, çağırarak bir kopya oluşturmadan yeni nesneye iliştirilir `SysAllocString` .

## <a name="remarks"></a>Açıklamalar

Aşağıdaki tabloda `_bstr_t` oluşturucular açıklanmaktadır.

|Oluşturucu|Açıklama|
|-----------------|-----------------|
|`_bstr_t( )`|`_bstr_t`Null nesneyi kapsülleyen varsayılan bir nesne oluşturur `BSTR` .|
|`_bstr_t( _bstr_t&`  `s1`  `)`|Bir `_bstr_t` nesneyi diğerinin kopyası olarak oluşturur.<br /><br /> Bu, yeni bir tane oluşturmak yerine, kapsüllenmiş nesnenin başvuru sayısını artıran *basit* bir kopyadır `BSTR` .|
|`_bstr_t( char*`  `s2`  `)`|`_bstr_t` `SysAllocString` Yeni bir nesne oluşturmak için çağırarak bir nesne oluşturur `BSTR` ve sonra onu kapsüller.<br /><br /> Bu Oluşturucu öncelikle Unicode dönüşümü çok baytlı bir biçimde gerçekleştirir.|
|`_bstr_t( wchar_t*`  `s3`  `)`|`_bstr_t` `SysAllocString` Yeni bir nesne oluşturmak için çağırarak bir nesne oluşturur `BSTR` ve sonra onu kapsüller.|
|`_bstr_t( _variant_t&`  `var`  `)`|`_bstr_t` `_variant_t` Önce kapsüllenmiş VARIANT nesnesinden bir nesne alarak nesnesinden bir nesne oluşturur `BSTR` .|
|`_bstr_t( BSTR`  `bstr` `, bool`  `fCopy`  `)`|Varolan bir `_bstr_t` nesneden `BSTR` (bir dizenin aksine) bir nesne oluşturur `wchar_t*` . *FCopy* yanlış ise, sağlanan yeni `BSTR` bir kopyasını ile yeni bir kopya oluşturmadan bu nesne eklenir `SysAllocString` .<br /><br /> Bu Oluşturucu, tür kitaplığı başlıklarındaki sarmalayıcı işlevleri tarafından, bir `BSTR` arabirim yöntemi tarafından döndürülen bir öğesinin sahipliğini kapsüllemek ve sahipliğini almak için kullanılır.|

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[_bstr_t sınıfı](../cpp/bstr-t-class.md)<br/>
[_variant_t sınıfı](../cpp/variant-t-class.md)
