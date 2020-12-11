---
description: 'Hakkında daha fazla bilgi edinin: _variant_t:: _variant_t'
title: _variant_t::_variant_t
ms.date: 11/04/2016
f1_keywords:
- _variant_t::_variant_t
helpviewer_keywords:
- _variant_t class [C++], constructor
- _variant_t method [C++]
ms.assetid: a50e5b33-d4c6-4a26-8e7e-a0a25fd9895b
ms.openlocfilehash: e49f2cf42ce1d73cb18d280d335ed267cb11df3e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97161370"
---
# <a name="_variant_t_variant_t"></a>_variant_t::_variant_t

**Microsoft'a Özgü**

Bir `_variant_t` nesnesi oluşturur.

## <a name="syntax"></a>Sözdizimi

```
_variant_t( ) throw( );

_variant_t(
   const VARIANT& varSrc
);

_variant_t(
   const VARIANT* pVarSrc
);

_variant_t(
   const _variant_t& var_t_Src
);

_variant_t(
   VARIANT& varSrc,
   bool fCopy
);

_variant_t(
   short sSrc,
   VARTYPE vtSrc = VT_I2
);

_variant_t(
   long lSrc,
   VARTYPE vtSrc = VT_I4
);

_variant_t(
   float fltSrc
) throw( );

_variant_t(
   double dblSrc,
   VARTYPE vtSrc = VT_R8
);

_variant_t(
   const CY& cySrc
) throw( );

_variant_t(
   const _bstr_t& bstrSrc
);

_variant_t(
   const wchar_t *wstrSrc
);

_variant_t(
   const char* strSrc
);

_variant_t(
   IDispatch* pDispSrc,
   bool fAddRef = true
) throw( );

_variant_t(
   bool bSrc
) throw( );

_variant_t(
   IUnknown* pIUknownSrc,
   bool fAddRef = true
) throw( );

_variant_t(
   const DECIMAL& decSrc
) throw( );

_variant_t(
   BYTE bSrc
) throw( );

variant_t(
   char cSrc
) throw();

_variant_t(
   unsigned short usSrc
) throw();

_variant_t(
   unsigned long ulSrc
) throw();

_variant_t(
   int iSrc
) throw();

_variant_t(
   unsigned int uiSrc
) throw();

_variant_t(
   __int64 i8Src
) throw();

_variant_t(
   unsigned __int64 ui8Src
) throw();
```

#### <a name="parameters"></a>Parametreler

*varSrc*<br/>
`VARIANT`Yeni nesneye kopyalanacak bir nesne `_variant_t` .

*pVarSrc*<br/>
`VARIANT`Yeni nesneye kopyalanacak bir nesne işaretçisi `_variant_t` .

*var_t_Src*<br/>
`_variant_t`Yeni nesneye kopyalanacak bir nesne `_variant_t` .

*fCopy*<br/>
Varsa **`false`** , sağlanan `VARIANT` nesne yeni `_variant_t` bir kopyasını tarafından yeni bir kopya oluşturmadan eklenir `VariantCopy` .

*ISrc, sSrc*<br/>
Yeni nesneye kopyalanacak bir tamsayı değeri `_variant_t` .

*vtSrc*<br/>
`VARTYPE`Yeni `_variant_t` nesne için.

*fltSrc, dblSrc*<br/>
Yeni nesneye kopyalanacak sayısal değer `_variant_t` .

*cySrc*<br/>
`CY`Yeni nesneye kopyalanacak bir nesne `_variant_t` .

*bstrSrc*<br/>
`_bstr_t`Yeni nesneye kopyalanacak bir nesne `_variant_t` .

*strSrc, wstrSrc*<br/>
Yeni nesneye kopyalanacak bir dize `_variant_t` .

*bSrc*<br/>
**`bool`** Yeni nesneye kopyalanacak bir değer `_variant_t` .

*pIUknownSrc*<br/>
Yeni nesneye kapsüllenmesi için VT_UNKNOWN nesnesine yönelik COM arabirimi işaretçisi `_variant_t` .

*pDispSrc*<br/>
Yeni nesneye kapsüllenmesi için VT_DISPATCH nesnesine yönelik COM arabirimi işaretçisi `_variant_t` .

*Yaprak döken*<br/>
`DECIMAL`Yeni nesneye kopyalanacak bir değer `_variant_t` .

*bSrc*<br/>
`BYTE`Yeni nesneye kopyalanacak bir değer `_variant_t` .

*cSrc*<br/>
**`char`** Yeni nesneye kopyalanacak bir değer `_variant_t` .

*usSrc*<br/>
**`unsigned short`** Yeni nesneye kopyalanacak bir değer `_variant_t` .

*ulSrc*<br/>
**`unsigned long`** Yeni nesneye kopyalanacak bir değer `_variant_t` .

*iSrc*<br/>
**`int`** Yeni nesneye kopyalanacak bir değer `_variant_t` .

*uiSrc*<br/>
**`unsigned int`** Yeni nesneye kopyalanacak bir değer `_variant_t` .

*i8Src*<br/>
**`__int64`** Yeni nesneye kopyalanacak bir değer `_variant_t` .

*ui8Src*<br/>
Yeni nesneye kopyalanacak **işaretsiz bir __int64** değeri `_variant_t` .

## <a name="remarks"></a>Açıklamalar

- **_variant_t ()** Boş bir `_variant_t` nesne oluşturur `VT_EMPTY` .

- **_variant_t (değişken&** *varSrc***)** `_variant_t`Nesnenin kopyasından bir nesne oluşturur `VARIANT` .     Değişken türü korunur.

- **_variant_t (VARIANT** <strong>\*</strong> *pvarsrc***)** `_variant_t` nesnenin kopyasından bir nesne oluşturur `VARIANT` .     Değişken türü korunur.

- **_variant_t (_variant_t&** *var_t_Src***)** Başka bir `_variant_t` nesneden bir nesne oluşturur `_variant_t` .     Değişken türü korunur.

- **_variant_t (Variant&** *varSrc* **, bool** `fCopy` **)** `_variant_t` var olan bir nesneden bir nesne oluşturur `VARIANT` .       *FCopy* Ise **`false`** , **VARIANT** nesnesi yeni nesneye kopya oluşturmadan eklenir.

- **_variant_t (Short***SSRC* **, vartype** `vtSrc` **= VT_I2)** `_variant_t` bir tamsayı değerinden VT_I2 veya VT_BOOL türünde bir nesne oluşturur **`short`** .       `VARTYPE`E_INVALIDARG bir hata oluşur.

- **_variant_t (Long** `lSrc` **, vartype** `vtSrc` **= VT_I4)** `_variant_t` bir tamsayı değerinden VT_I4, VT_BOOL veya VT_ERROR türünde bir nesne oluşturur **`long`** .       `VARTYPE`E_INVALIDARG bir hata oluşur.

- **_variant_t (float** `fltSrc` **)** `_variant_t` sayısal değerden VT_R4 türünde bir nesne oluşturur **`float`** .    

- **_variant_t (Double** `dblSrc` **, vartype** `vtSrc` **= VT_R8)** sayısal bir `_variant_t` değerden VT_R8 veya VT_DATE türünde bir nesne oluşturur **`double`** .       `VARTYPE`E_INVALIDARG bir hata oluşur.

- **_variant_t (CY&** `cySrc` **)** `_variant_t` bir nesneden VT_CY türünde bir nesne oluşturur `CY` .    

- **_variant_t (_bstr_t&** `bstrSrc` **)** `_variant_t` bir nesneden VT_BSTR türünde bir nesne oluşturur `_bstr_t` .     Yeni bir `BSTR` tahsis edilir.

- **_variant_t (wchar_t** <strong>\*</strong> *wstrSrc*  **)** `_variant_t` , Unicode dizesinden VT_BSTR türünde bir nesne oluşturur. Yeni bir `BSTR` tahsis edilir.

- **_variant_t (Char** <strong>\*</strong> `strSrc` **)** `_variant_t` Bir dizeden VT_BSTR türünde bir nesne oluşturur.     Yeni bir `BSTR` tahsis edilir.

- **_variant_t (bool** `bSrc` **)** `_variant_t` bir değerden VT_BOOL türünde bir nesne oluşturur **`bool`** .    

- **_variant_t (IUnknown** <strong>\*</strong> `pIUknownSrc` **, bool** `fAddRef` **= true)** `_variant_t`Com arabirim işaretçisinden VT_UNKNOWN türünde bir nesne oluşturur.       `fAddRef`İse **`true`** , `AddRef` `Release` nesne yok edildiğinde gerçekleştirilecek çağrıya eşleştirmek için sağlanan arabirim İşaretçisinde çağrılır `_variant_t` . `Release`Sağlanan arabirim işaretçisi üzerinde arama yapmanız en iyisidir. `fAddRef`İse **`false`** , bu Oluşturucu sağlanan arabirim işaretçisinin sahipliğini alır; `Release` sağlanan arabirim işaretçisi üzerinde çağırmayın.

- **_variant_t (IDispatch** <strong>\*</strong> `pDispSrc` **, bool** `fAddRef` **= true)** `_variant_t`Com arabirim işaretçisinden VT_DISPATCH türünde bir nesne oluşturur.       `fAddRef`İse **`true`** , `AddRef` `Release` nesne yok edildiğinde gerçekleştirilecek çağrıya eşleştirmek için sağlanan arabirim İşaretçisinde çağrılır `_variant_t` . `Release`Sağlanan arabirim işaretçisi üzerinde arama yapmanız en iyisidir. `fAddRef`İse **`false`** , bu Oluşturucu sağlanan arabirim işaretçisinin sahipliğini alır; `Release` sağlanan arabirim işaretçisi üzerinde çağırmayın.

- **_variant_t (DECIMAL&** `decSrc` **)** `_variant_t` bir değerden VT_DECIMAL türünde bir nesne oluşturur `DECIMAL` .    

- **_variant_t (Byte** `bSrc` **)** `_variant_t` bir değerden türünde bir nesne oluşturur `VT_UI1` `BYTE` .    

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[_variant_t sınıfı](../cpp/variant-t-class.md)
