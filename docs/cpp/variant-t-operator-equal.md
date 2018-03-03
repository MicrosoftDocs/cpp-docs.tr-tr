---
title: _variant_t::operator = | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _variant_t::operator=
dev_langs:
- C++
helpviewer_keywords:
- operator= [C++], variant
- operator = [C++], variant
- = operator [C++], with specific Visual C++ objects
ms.assetid: 77622723-6e49-4dec-9e0f-fa74028f1a3c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 88998f18c750e064ee8eae254ca7ee4487be7176
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="varianttoperator-"></a>_variant_t::operator =
**Microsoft özel**  
  
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
  
-   **işleç = (***varSrc***)** varolan atar **değişken** için bir `_variant_t` nesnesi.  
  
-   **işleç = (***pVarSrc***)** varolan atar **değişken** için bir `_variant_t` nesnesi.  
  
-   **işleç = (***var_t_Src***)** varolan atar `_variant_t` nesnesine bir `_variant_t` nesnesi.  
  
-   **işleç = (***sSrc***)** atayan bir **kısa** tamsayı değerine bir `_variant_t` nesnesi.  
  
-   **işleç = (**`lSrc`**)** atayan bir **uzun** tamsayı değerine bir `_variant_t` nesnesi.  
  
-   **işleç = (***fltSrc***)** atar bir **float** sayısal değer için bir `_variant_t` nesnesi.  
  
-   **işleç = (***dblSrc***)** atar bir **çift** sayısal değer için bir `_variant_t` nesnesi.  
  
-   **işleç = (***cySrc***)** atayan bir **CY** nesnesine bir `_variant_t` nesnesi.  
  
-   **işleç = (***bstrSrc***)** atayan bir `BSTR` nesnesine bir `_variant_t` nesnesi.  
  
-   **işleç = (***wstrSrc***)** bir UNICODE dizesi atar bir `_variant_t` nesnesi.  
  
-   **işleç = (**`strSrc`**)** birden çok baytlı dizeye atar bir `_variant_t` nesnesi.  
  
-   **işleç = (** `bSrc` **)** atayan bir `bool` değeri bir `_variant_t` nesnesi.  
  
-   **işleç = (***pDispSrc***)** atayan bir **VT_DISPATCH** nesnesine bir `_variant_t` nesnesi.  
  
-   **işleç = (***pIUnknownSrc***)** atayan bir **VT_UNKNOWN** nesnesine bir `_variant_t` nesnesi.  
  
-   **işleç = (***decSrc***)** atayan bir **ondalık** değeri bir `_variant_t` nesnesi.  
  
-   **işleç = (** `bSrc` **)** atayan bir **bayt** değeri bir `_variant_t` nesnesi.  
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [_variant_t Sınıfı](../cpp/variant-t-class.md)