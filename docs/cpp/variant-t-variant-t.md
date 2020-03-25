---
title: _variant_t::_variant_t
ms.date: 11/04/2016
f1_keywords:
- _variant_t::_variant_t
helpviewer_keywords:
- _variant_t class [C++], constructor
- _variant_t method [C++]
ms.assetid: a50e5b33-d4c6-4a26-8e7e-a0a25fd9895b
ms.openlocfilehash: fff116ef04967a1887eaa075d92d3ea0283d5427
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80187537"
---
# <a name="_variant_t_variant_t"></a>_variant_t::_variant_t

**Microsoft 'a özgü**

`_variant_t` nesnesi oluşturur.

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
Yeni `_variant_t` nesnesine kopyalanacak `VARIANT` nesnesi.

*pVarSrc*<br/>
Yeni `_variant_t` nesnesine kopyalanacak `VARIANT` nesnesine yönelik işaretçi.

*var_t_Src*<br/>
Yeni `_variant_t` nesnesine kopyalanacak `_variant_t` nesnesi.

*fCopy*<br/>
**False**ise, belirtilen `VARIANT` nesnesi yeni `_variant_t` nesnesine `VariantCopy`tarafından yeni bir kopya oluşturmadan eklenir.

*ISrc, sSrc*<br/>
Yeni `_variant_t` nesnesine kopyalanacak bir tamsayı değeri.

*vtSrc*<br/>
Yeni `_variant_t` nesnesinin `VARTYPE`.

*fltSrc, dblSrc*<br/>
Yeni `_variant_t` nesnesine kopyalanacak sayısal bir değer.

*cySrc*<br/>
Yeni `_variant_t` nesnesine kopyalanacak `CY` nesnesi.

*bstrSrc*<br/>
Yeni `_variant_t` nesnesine kopyalanacak `_bstr_t` nesnesi.

*strSrc, wstrSrc*<br/>
Yeni `_variant_t` nesnesine kopyalanacak bir dize.

*bSrc*<br/>
Yeni `_variant_t` nesnesine kopyalanacak bir **bool** değeri.

*pIUknownSrc*<br/>
Yeni `_variant_t` nesnesine kapsüllenmesi için VT_UNKNOWN nesnesine yönelik COM arabirimi işaretçisi.

*pDispSrc*<br/>
Yeni `_variant_t` nesnesine kapsüllenmesi için VT_DISPATCH nesnesine yönelik COM arabirimi işaretçisi.

*Yaprak döken*<br/>
Yeni `_variant_t` nesnesine kopyalanacak `DECIMAL` değeri.

*bSrc*<br/>
Yeni `_variant_t` nesnesine kopyalanacak `BYTE` değeri.

*cSrc*<br/>
Yeni `_variant_t` nesnesine kopyalanacak bir **char** değeri.

*usSrc*<br/>
Yeni `_variant_t` nesnesine kopyalanacak **işaretsiz kısa** değer.

*ulSrc*<br/>
Yeni `_variant_t` nesnesine kopyalanacak **işaretsiz Long** değeri.

*iSrc*<br/>
Yeni `_variant_t` nesnesine kopyalanacak bir **int** değeri.

*uiSrc*<br/>
Yeni `_variant_t` nesnesine kopyalanacak **işaretsiz bir int** değeri.

*i8Src*<br/>
Yeni `_variant_t` nesnesine kopyalanacak **__int64** değeri.

*ui8Src*<br/>
Yeni `_variant_t` nesnesine kopyalanacak **işaretsiz bir __int64** değeri.

## <a name="remarks"></a>Açıklamalar

- **_variant_t ()** Boş bir `_variant_t` nesnesi oluşturur `VT_EMPTY`.

- **_variant_t (değişken &** *varSrc* **)** `VARIANT` nesnesinin bir kopyasından `_variant_t` nesnesi oluşturur. Değişken türü korunur.

- **_variant_t (değişken** <strong>\*</strong> *pvarsrc* **)** `VARIANT` nesnesinin bir kopyasından `_variant_t` nesnesi oluşturur. Değişken türü korunur.

- **_variant_t (_variant_t &** *var_t_Src* **)** Başka bir `_variant_t` nesnesinden `_variant_t` nesnesi oluşturur. Değişken türü korunur.

- **_variant_t (değişken &** *varSrc* **, bool**`fCopy` **)** Varolan bir `VARIANT` nesnesinden `_variant_t` nesnesi oluşturur. *FCopy* **yanlış**ise, **değişken** nesne yeni nesneye bir kopya oluşturmadan eklenir.

- **_variant_t (kısa***SSRC* **, vartype**`vtSrc` **= VT_I2)** **Kısa** bir tamsayı değerinden VT_I2 veya VT_BOOL türünde bir `_variant_t` nesnesi oluşturur. Diğer `VARTYPE`, bir E_INVALIDARG hatasına neden olur.

- **_variant_t (uzun**`lSrc` **, VARTYPE**`vtSrc` **= VT_I4)** **Uzun** bir tamsayı değerinden VT_I4, VT_BOOL veya VT_ERROR türünde bir `_variant_t` nesnesi oluşturur. Diğer `VARTYPE`, bir E_INVALIDARG hatasına neden olur.

- **_variant_t (float**`fltSrc` **)** **Kayan** sayısal değerden VT_R4 türünde bir `_variant_t` nesnesi oluşturur.

- **_variant_t (çift**`dblSrc` **, VARTYPE**`vtSrc` **= VT_R8)** **Çift** sayısal değerden VT_R8 veya VT_DATE türünde bir `_variant_t` nesnesi oluşturur. Diğer `VARTYPE`, bir E_INVALIDARG hatasına neden olur.

- **_variant_t (&** `cySrc` **)** `CY` nesnesinden VT_CY türünde bir `_variant_t` nesnesi oluşturur.

- **_variant_t (_bstr_t &** `bstrSrc` **)** `_bstr_t` nesnesinden VT_BSTR türünde bir `_variant_t` nesnesi oluşturur. Yeni bir `BSTR` ayrıldı.

- **_variant_t (wchar_t** <strong>\*</strong> *wstrSrc*  **)** Unicode dizesinden VT_BSTR türünde bir `_variant_t` nesnesi oluşturur. Yeni bir `BSTR` ayrıldı.

- **_variant_t (char** <strong>\*</strong>`strSrc` **)** Bir dizeden VT_BSTR türünde bir `_variant_t` nesnesi oluşturur. Yeni bir `BSTR` ayrıldı.

- **_variant_t (bool**`bSrc` **)** **Bool** değerden VT_BOOL türünde bir `_variant_t` nesnesi oluşturur.

- **_variant_t (ıunknown** <strong>\*</strong>`pIUknownSrc` **, bool**`fAddRef` **= true)** COM arabirim işaretçisinden VT_UNKNOWN türünde bir `_variant_t` nesnesi oluşturur. `fAddRef` **true**ise, `_variant_t` nesnesi yok edildiğinde gerçekleşen `Release` çağrısıyla eşleşmesi için sağlanan arabirim işaretçisinde `AddRef` çağırılır. Sağlanan arabirim İşaretçisinde `Release` çağırmak size bağlıdır. `fAddRef` **false**ise, bu Oluşturucu sağlanan arabirim işaretçisinin sahipliğini alır; sağlanan arabirim İşaretçisinde `Release` çağırmayın.

- **_variant_t (ıdispatch** <strong>\*</strong>`pDispSrc` **, bool**`fAddRef` **= true)** COM arabirim işaretçisinden VT_DISPATCH türünde bir `_variant_t` nesnesi oluşturur. `fAddRef` **true**ise, `_variant_t` nesnesi yok edildiğinde gerçekleşen `Release` çağrısıyla eşleşmesi için sağlanan arabirim işaretçisinde `AddRef` çağırılır. Sağlanan arabirim İşaretçisinde `Release` çağırmak size bağlıdır. `fAddRef` **false**ise, bu Oluşturucu sağlanan arabirim işaretçisinin sahipliğini alır; sağlanan arabirim İşaretçisinde `Release` çağırmayın.

- **_variant_t (DECIMAL &** `decSrc` **)** `DECIMAL` değerden VT_DECIMAL türünde bir `_variant_t` nesnesi oluşturur.

- **_variant_t (bayt**`bSrc` **)** `BYTE` değerden `VT_UI1` türünde bir `_variant_t` nesnesi oluşturur.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[_variant_t Sınıfı](../cpp/variant-t-class.md)
