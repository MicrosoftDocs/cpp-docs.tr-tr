---
description: 'Hakkında daha fazla bilgi edinin: _variant_t:: operator ='
title: _variant_t::operator =
ms.date: 11/04/2016
f1_keywords:
- _variant_t::operator=
helpviewer_keywords:
- operator= [C++], variant
- operator = [C++], variant
- = operator [C++], with specific Visual C++ objects
ms.assetid: 77622723-6e49-4dec-9e0f-fa74028f1a3c
ms.openlocfilehash: a304f0904f697ade7d04c6d12f375571a156e989
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97161474"
---
# <a name="_variant_toperator-"></a>_variant_t::operator =

**Microsoft'a Özgü**

## <a name="syntax"></a>Syntax

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

- **operator = (**  *varSrc*  **)** Varolan bir `VARIANT` `_variant_t` nesneye atar.

- **operator = (**  *pvarsrc*  **)** Varolan bir `VARIANT` `_variant_t` nesneye atar.

- **operator = (**  *var_t_Src*  **)** Varolan bir `_variant_t` nesneyi bir nesnesine atar `_variant_t` .

- **operator = (**  *SSRC*  **)** **`short`** Bir nesneye tamsayı değeri atar `_variant_t` .

- **operator = (** `lSrc` **)** **`long`** bir nesneye tamsayı değeri atar `_variant_t` .    

- **operator = (**  *fltsrc*  **)** **`float`** Bir nesneye sayısal değer atar `_variant_t` .

- **operator = (**  *dblsrc*  **)** **`double`** Bir nesneye sayısal değer atar `_variant_t` .

- **operator = (**  *cysrc*  **)** Nesnesine bir `CY` nesnesi atar `_variant_t` .

- **operator = (**  *bstrsrc*  **)** Nesnesine bir `BSTR` nesnesi atar `_variant_t` .

- **operator = (**  *wstrSrc*  **)** Bir nesneye Unicode dizesi atar `_variant_t` .

- **operator = (** `strSrc` **)** bir nesneye çok baytlı bir dize atar `_variant_t` .    

- **operator = (** `bSrc` **)** **`bool`** bir nesnesine bir değer atar `_variant_t` .  

- **operator = (**  *pdispsrc*  **)** Nesnesine bir `VT_DISPATCH` nesnesi atar `_variant_t` .

- **operator = (**  *piunknownsrc*  **)** Nesnesine bir `VT_UNKNOWN` nesnesi atar `_variant_t` .

- **operator = (**  *decsrc*  **)** Nesnesine bir `DECIMAL` değer atar `_variant_t` .

- **operator = (** `bSrc` **)** `BYTE` bir nesnesine bir değer atar `_variant_t` .  

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[_variant_t sınıfı](../cpp/variant-t-class.md)
