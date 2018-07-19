---
title: _variant_t::_variant_t | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _variant_t::_variant_t
dev_langs:
- C++
helpviewer_keywords:
- _variant_t class [C++], constructor
- _variant_t method [C++]
ms.assetid: a50e5b33-d4c6-4a26-8e7e-a0a25fd9895b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 14386e737d136b91f8864eeaa182038b62df72e0
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2018
ms.locfileid: "37948046"
---
# <a name="varianttvariantt"></a>_variant_t::_variant_t
**Microsoft'a özgü**  
  
 Oluşturur bir `_variant_t` nesne.  
  
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
 *varSrc*  
 A `VARIANT` yeni içine kopyalanacak nesne `_variant_t` nesne.  
  
 *pVarSrc*  
 İşaretçi bir `VARIANT` yeni içine kopyalanacak nesne `_variant_t` nesne.  
  
 *var_t_Src*  
 A `_variant_t` yeni içine kopyalanacak nesne `_variant_t` nesne.  
  
 *fCopy*  
 Varsa **false**, sağlanan `VARIANT` nesne yeni bağlı `_variant_t` nesne tarafından yeni bir kopya yapmadan `VariantCopy`.  
  
 *ISRC, sSrc*  
 Yeni içine kopyalanacak bir tamsayı değeri `_variant_t` nesne.  
  
 *vtSrc*  
 `VARTYPE` Yeni `_variant_t` nesne.  
  
 *fltSrc, dblSrc*  
 Yeni içine kopyalanacak bir sayısal değer `_variant_t` nesne.  
  
 *cysrc &*  
 A `CY` yeni içine kopyalanacak nesne `_variant_t` nesne.  
  
 *bstrSrc*  
 A `_bstr_t` yeni içine kopyalanacak nesne `_variant_t` nesne.  
  
 *strSrc, wstrsrc &*  
 Yeni içine kopyalanacak bir dize `_variant_t` nesne.  
  
 *bSrc*  
 A **bool** yeni içine kopyalanacak değeri `_variant_t` nesne.  
  
 *pIUknownSrc*  
 COM arabirimi işaretçisini yeni saklanmasını VT_UNKNOWN nesnesine `_variant_t` nesne.  
  
 *pdispsrc &*  
 COM arabirimi işaretçisini yeni saklanmasını gt; vt_dıspatch & nesnesine `_variant_t` nesne.  
  
 *decSrc*  
 A `DECIMAL` yeni içine kopyalanacak değeri `_variant_t` nesne.  
  
 *bSrc*  
 A `BYTE` yeni içine kopyalanacak değeri `_variant_t` nesne.  
  
 *cSrc*  
 A **char** yeni içine kopyalanacak değeri `_variant_t` nesne.  
  
 *usSrc*  
 A **işaretsiz** yeni içine kopyalanacak değeri `_variant_t` nesne.  
  
 *ulSrc*  
 A **işaretsiz uzun** yeni içine kopyalanacak değeri `_variant_t` nesne.  
  
 *ISRC*  
 Bir **int** yeni içine kopyalanacak değeri `_variant_t` nesne.  
  
 *uiSrc*  
 Bir **işaretsiz int** yeni içine kopyalanacak değeri `_variant_t` nesne.  
  
 *i8Src*  
 Bir __**Int64** yeni içine kopyalanacak değeri `_variant_t` nesne.  
  
 *ui8Src*  
 Bir **unsigned __int64** yeni içine kopyalanacak değeri `_variant_t` nesne.  
  
## <a name="remarks"></a>Açıklamalar  
  
-   **_variant_t ()** boş yapıları `_variant_t` nesnesi `VT_EMPTY`.  
  
-   **_variant_t (değişken &***varSrc***)** oluşturan bir `_variant_t` nesnesinin bir kopyasını `VARIANT` nesne.     Değişken türü korunur.  
  
-   **_variant_t (değişken\****pVarSrc***)** oluşturan bir `_variant_t` nesnesinin bir kopyasını `VARIANT` nesne.     Değişken türü korunur.  
  
-   **_variant_t (_variant_t &***; var_t_src &***)** oluşturan bir `_variant_t` başka bir nesne `_variant_t` nesne.     Değişken türü korunur.  
  
-   **_variant_t (değişken &***varSrc* **, bool**`fCopy`**)** oluşturan bir `_variant_t` mevcut bir nesne `VARIANT` nesne.       Varsa `fCopy` olduğu **false**, **değişken** nesne yeni nesneye bir kopyası oluşturmadan eklenir.  
  
-   **_variant_t (kısa***sSrc* **, VARTYPE**`vtSrc`**VT_I2 =)** oluşturan bir `_variant_t` nesne türünün VT_I2 veya VT_BOOL bir **kısa** tamsayı değeri.       Diğer `VARTYPE` E_INVALIDARG hatayla sonuçlanır.  
  
-   **_variant_t (uzun** `lSrc` **, VARTYPE**`vtSrc`**VT_I4 =)** oluşturan bir `_variant_t` VT_I4, VT_BOOL veya gelen VT_ERROR türündeki nesne bir **uzun**  tamsayı değeri.       Diğer `VARTYPE` E_INVALIDARG hatayla sonuçlanır.  
  
-   **_variant_t (float**`fltSrc`**)** oluşturan bir `_variant_t` VT_R4 türünden nesnenin bir **float** sayısal değer.      
  
-   **_variant_t (çift** `dblSrc` **, VARTYPE**`vtSrc`**VT_R8 =)** oluşturan bir `_variant_t` VT_R8 veya gelen VT_DATE türündeki nesne bir **çift** sayısal değer.       Diğer `VARTYPE` E_INVALIDARG hatayla sonuçlanır.  
  
-   **_variant_t (CY &**`cySrc`**)** oluşturan bir `_variant_t` nesnesi türü alanından VT_CY bir `CY` nesne.      
  
-   **_variant_t (_bstr_t &**`bstrSrc`**)** oluşturan bir `_variant_t` nesnesi türü alanından VT_BSTR bir `_bstr_t` nesne.     Yeni bir `BSTR` ayrılır.  
  
-   **_variant_t (wchar_t \***  *; wstrsrc &***)** oluşturan bir `_variant_t` bir Unicode dize VT_BSTR türünden nesne.   Yeni bir `BSTR` ayrılır.  
  
-   **_variant_t (char\***`strSrc`**)** oluşturan bir `_variant_t` bir dizeden VT_BSTR türündeki nesne.     Yeni bir `BSTR` ayrılır.  
  
-   **_variant_t (bool**`bSrc`**)** oluşturan bir `_variant_t` nesnesi türü alanından VT_BOOL bir **bool** değeri.      
  
-   **_variant_t (IUnknown\***  `pIUknownSrc` **, bool**`fAddRef`**= true)** oluşturan bir `_variant_t` VT_UNKNOWN türünden bir COM arabirimi işaretçisini nesnenin .       Varsa `fAddRef` olan **true**, ardından `AddRef` çağrısı eşleştirmek için sağlanan arabirim işaretçisi olarak adlandırılan `Release` , gerçekleşir olduğunda `_variant_t` nesnesi yok edildiğinde. Size kalmıştır çağrılacak olan `Release` üzerinde sağlanan arabirim işaretçisi. Varsa `fAddRef` olduğu **false**, bu Oluşturucusu sağlanan arabirim işaretçisi sahipliğini alır; çağırmayın `Release` üzerinde sağlanan arabirim işaretçisi.  
  
-   **_variant_t (IDispatch\***  `pDispSrc` **, bool**`fAddRef`**= true)** oluşturan bir `_variant_t` gt; vt_dıspatch & bir COM arabiriminden türündeki nesne İşaretçi.       Varsa `fAddRef` olan **true**, ardından `AddRef` çağrısı eşleştirmek için sağlanan arabirim işaretçisi olarak adlandırılan `Release` , gerçekleşir olduğunda `_variant_t` nesnesi yok edildiğinde. Size kalmıştır çağrılacak olan `Release` üzerinde sağlanan arabirim işaretçisi. Varsa `fAddRef` olduğu **false**, bu Oluşturucusu sağlanan arabirim işaretçisi sahipliğini alır; çağırmayın `Release` üzerinde sağlanan arabirim işaretçisi.  
  
-   **_variant_t (ondalık &**`decSrc`**)** oluşturan bir `_variant_t` nesnesi türü alanından VT_DECIMAL bir `DECIMAL` değeri.      
  
-   **_variant_t (bayt**`bSrc`**)** oluşturan bir `_variant_t` türündeki nesne `VT_UI1` gelen bir `BYTE` değeri.      
  
 **END Microsoft özgü**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [_variant_t Sınıfı](../cpp/variant-t-class.md)