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
ms.openlocfilehash: 6a8f31e8db6f5ca5a680dd47b5d5391c84ce5025
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50498282"
---
# <a name="varianttoperator-"></a>_variant_t::operator =

**Microsoft'a özgü**

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

- **operator = (***varSrc***)** varolan atar `VARIANT` için bir `_variant_t` nesne.

- **operator = (***pVarSrc***)** varolan atar `VARIANT` için bir `_variant_t` nesne.

- **operator = (***; var_t_src &***)** varolan atar `_variant_t` nesnesini bir `_variant_t` nesne.    

- **operator = (***sSrc***)** atar bir **kısa** tamsayı değerini bir `_variant_t` nesne.

- **operator = (**`lSrc`**)** atar bir **uzun** tamsayı değerini bir `_variant_t` nesne.

- **operator = (***; fltsrc &***)** atar bir **float** sayısal değeri bir `_variant_t` nesne.

- **operator = (***; dblsrc &***)** atar bir **çift** sayısal değeri bir `_variant_t` nesne.

- **operator = (***cysrc &***)** atar bir `CY` nesnesini bir `_variant_t` nesne.

- **operator = (***bstrSrc***)** atar bir `BSTR` nesnesini bir `_variant_t` nesne.

- **operator = (***; wstrsrc &***)** atar bir Unicode dizesini bir `_variant_t` nesne.

- **operator = (**`strSrc`**)** çok baytlı bir string'e atar bir `_variant_t` nesne.

- **operator = (** `bSrc` **)** atar bir **bool** değerini bir `_variant_t` nesne.

- **operator = (***; pdispsrc &***)** atar bir `VT_DISPATCH` nesnesini bir `_variant_t` nesne.

- **operator = (***pıunknownsrc &***)** atar bir `VT_UNKNOWN` nesnesini bir `_variant_t` nesne.

- **operator = (***decSrc***)** atar bir `DECIMAL` değerini bir `_variant_t` nesne.

- **operator = (** `bSrc` **)** atar bir `BYTE` değerini bir `_variant_t` nesne.

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[_variant_t Sınıfı](../cpp/variant-t-class.md)