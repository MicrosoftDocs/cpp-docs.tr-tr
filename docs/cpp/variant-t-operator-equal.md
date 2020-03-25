---
title: _variant_t::operator =
ms.date: 11/04/2016
f1_keywords:
- _variant_t::operator=
helpviewer_keywords:
- operator= [C++], variant
- operator = [C++], variant
- = operator [C++], with specific Visual C++ objects
ms.assetid: 77622723-6e49-4dec-9e0f-fa74028f1a3c
ms.openlocfilehash: 402251592a87b723d75fd1b2cd0786be7b17dbfc
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80187628"
---
# <a name="_variant_toperator-"></a>_variant_t::operator =

**Microsoft 'a özgü**

## <a name="syntax"></a>Sözdizimi

```
_variant_t& operator=(
   const VARIANT& varSrc
);

_variant_t& operator=(
   const VARIANT* pVarSrc
);

_variant_t& operator=(
   const _variant_t& var_t_Src
);

_variant_t& operator=(
   short sSrc
);

_variant_t& operator=(
   long lSrc
);

_variant_t& operator=(
   float fltSrc
);

_variant_t& operator=(
   double dblSrc
);

_variant_t& operator=(
   const CY& cySrc
);

_variant_t& operator=(
   const _bstr_t& bstrSrc
);

_variant_t& operator=(
   const wchar_t* wstrSrc
);

_variant_t& operator=(
   const char* strSrc
);

_variant_t& operator=(
   IDispatch* pDispSrc
);

_variant_t& operator=(
   bool bSrc
);

_variant_t& operator=(
   IUnknown* pSrc
);

_variant_t& operator=(
   const DECIMAL& decSrc
);

_variant_t& operator=(
   BYTE bSrc
);

_variant_t& operator=(
   char cSrc
);

_variant_t& operator=(
   unsigned short usSrc
);

_variant_t& operator=(
   unsigned long ulSrc
);

_variant_t& operator=(
   int iSrc
);

_variant_t& operator=(
   unsigned int uiSrc
);

_variant_t& operator=(
   __int64 i8Src
);

_variant_t& operator=(
   unsigned __int64 ui8Src
);
```

## <a name="remarks"></a>Açıklamalar

İşleç, `_variant_t` nesnesine yeni bir değer atar:

- **operator = (**  *varSrc*  **)** Var olan bir `VARIANT` `_variant_t` nesnesine atar.

- **operator = (**  *pvarsrc*  **)** Var olan bir `VARIANT` `_variant_t` nesnesine atar.

- **operator = (**  *var_t_Src*  **)** Var olan bir `_variant_t` nesnesini bir `_variant_t` nesnesine atar.

- **operator = (** *SSRC* **)** `_variant_t` nesnesine bir **kısa** tamsayı değeri atar.

- **operator = (** `lSrc` **)** `_variant_t` nesnesine **uzun** bir tamsayı değeri atar.

- **operator = (** *fltsrc* **)** `_variant_t` nesnesine bir **float** sayısal değeri atar.

- **operator = (** *dblsrc* **)** `_variant_t` nesnesine bir **Double** sayısal değer atar.

- **operator = (**  *cysrc*  **)** Bir `CY` nesnesini `_variant_t` nesnesine atar.

- **operator = (**  *bstrsrc*  **)** Bir `BSTR` nesnesini `_variant_t` nesnesine atar.

- **operator = (**  *wstrSrc*  **)** `_variant_t` nesnesine bir Unicode dizesi atar.

- **operator = (** `strSrc` **)** `_variant_t` nesnesine çok baytlı bir dize atar.

- **operator = (** `bSrc` **)** `_variant_t` nesnesine bir **bool** değeri atar.

- **operator = (**  *pdispsrc*  **)** Bir `VT_DISPATCH` nesnesini `_variant_t` nesnesine atar.

- **operator = (**  *piunknownsrc*  **)** Bir `VT_UNKNOWN` nesnesini `_variant_t` nesnesine atar.

- **operator = (** *decsrc* **)** `_variant_t` nesnesine bir `DECIMAL` değeri atar.

- **operator = (** `bSrc` **)** `_variant_t` nesnesine bir `BYTE` değeri atar.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[_variant_t Sınıfı](../cpp/variant-t-class.md)
