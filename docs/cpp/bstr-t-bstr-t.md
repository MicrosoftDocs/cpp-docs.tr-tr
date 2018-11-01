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
ms.openlocfilehash: 70678b0be8b25bf3ee883630caa26598e5e31089
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50450082"
---
# <a name="bstrtbstrt"></a>_bstr_t::_bstr_t

**Microsoft'a özgü**

Oluşturur bir `_bstr_t` nesne.

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
A `_bstr_t` kopyalanacak nesne.

*S2*<br/>
Çok baytlı bir dize.

*S3*<br/>
Unicode dizesi

*var*<br/>
A [_variant_t](../cpp/variant-t-class.md) nesne.

*BSTR*<br/>
Varolan bir `BSTR` nesnesi.

*fCopy*<br/>
FALSE ise *bstr* bağımsız değişkeni, yeni nesneye çağırarak bir kopyası oluşturmadan takılı `SysAllocString`.

## <a name="remarks"></a>Açıklamalar

Aşağıdaki tabloda açıklanmıştır `_bstr_t` oluşturucular.

|Oluşturucu|Açıklama|
|-----------------|-----------------|
|`_bstr_t( )`|Varsayılan yapıları `_bstr_t` null yalıtan nesne `BSTR` nesne.|
|`_bstr_t( _bstr_t&`  `s1`  `)`|Oluşturur bir `_bstr_t` başka bir kopya olarak nesnesi.<br /><br /> Bu bir *yüzeysel* kapsüllenmiş başvuru sayısını artırır kopya `BSTR` yeni bir tane oluşturmak yerine nesne.|
|`_bstr_t( char*`  `s2`  `)`|Oluşturur bir `_bstr_t` çağırarak `SysAllocString` yeni bir `BSTR` nesnesi ve ardından kapsüller.<br /><br /> Bu oluşturucu, ilk çok baytlı Unicode dönüştürme gerçekleştirir.|
|`_bstr_t( wchar_t*`  `s3`  `)`|Oluşturur bir `_bstr_t` çağırarak `SysAllocString` yeni bir `BSTR` nesnesi ve ardından kapsüller.|
|`_bstr_t( _variant_t&`  `var`  `)`|Oluşturur bir `_bstr_t` nesnesinden bir `_variant_t` ilk alarak nesne bir `BSTR` kapsüllenmiş değişken nesnesinden nesne.|
|`_bstr_t( BSTR`  `bstr` `, bool`  `fCopy`  `)`|Oluşturur bir `_bstr_t` mevcut bir nesne `BSTR` (başlangıcı yerine sonundan bir `wchar_t*` dize). Varsa *fCopy* yanlışsa, sağlanan `BSTR` ile yeni bir kopya yapmadan yeni nesneye iliştirilmiş `SysAllocString`.<br /><br /> Bu oluşturucu şifreleyebilir ve sahipliğini almak için tür kitaplığı üstbilgi sarmalayıcı işlevleri tarafından kullanılır bir `BSTR` bir arabirim yöntemi tarafından döndürülür.|

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[_bstr_t Sınıfı](../cpp/bstr-t-class.md)<br/>
[_variant_t Sınıfı](../cpp/variant-t-class.md)