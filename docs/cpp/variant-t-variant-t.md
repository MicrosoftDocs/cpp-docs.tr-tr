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
ms.openlocfilehash: 59ec19adc66a72a7c98772db99aaab3eee4e3b2c
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="varianttvariantt"></a>_variant_t::_variant_t
**Microsoft özel**  
  
 Oluşturan bir `_variant_t` nesnesi.  
  
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
 A **değişken** yeni içine kopyalanacak nesne `_variant_t` nesne.  
  
 *pVarSrc*  
 İşaretçi bir **değişken** yeni içine kopyalanacak nesne `_variant_t` nesne.  
  
 *var_t_Src*  
 A `_variant_t` yeni içine kopyalanacak nesne `_variant_t` nesne.  
  
 `fCopy`  
 False ise, sağlanan **değişken** nesne yeni bağlı `_variant_t` tarafından yeni bir kopya yapmadan nesne **VariantCopy**.  
  
 *ISRC, sSrc*  
 Yeni içine kopyalanacak bir tamsayı değeri `_variant_t` nesnesi.  
  
 `vtSrc`  
 **VARTYPE** yeni `_variant_t` nesnesi.  
  
 *fltSrc, dblSrc*  
 Yeni içine kopyalanacak bir sayısal değer `_variant_t` nesnesi.  
  
 `cySrc`  
 A **CY** yeni içine kopyalanacak nesne `_variant_t` nesne.  
  
 `bstrSrc`  
 A `_bstr_t` yeni içine kopyalanacak nesne `_variant_t` nesne.  
  
 *strSrc, wstrSrc*  
 Yeni içine kopyalanacak bir dize `_variant_t` nesnesi.  
  
 `bSrc`  
 A `bool` yeni içine Kopyalanacak değer `_variant_t` nesnesi.  
  
 `pIUknownSrc`  
 COM arabirimi işaretçisi bir **VT_UNKNOWN** yeni içine saklanmasını nesne `_variant_t` nesne.  
  
 `pDispSrc`  
 COM arabirimi işaretçisi bir **VT_DISPATCH** yeni içine saklanmasını nesne `_variant_t` nesne.  
  
 `decSrc`  
 A **ondalık** yeni içine Kopyalanacak değer `_variant_t` nesnesi.  
  
 `bSrc`  
 A **bayt** yeni içine Kopyalanacak değer `_variant_t` nesnesi.  
  
 `cSrc`  
 A `char` yeni içine Kopyalanacak değer `_variant_t` nesnesi.  
  
 *usSrc*  
 A **kısa imzasız** yeni içine Kopyalanacak değer `_variant_t` nesnesi.  
  
 *ulSrc*  
 A `unsigned long` yeni içine Kopyalanacak değer `_variant_t` nesnesi.  
  
 `iSrc`  
 Bir `int` yeni içine Kopyalanacak değer `_variant_t` nesnesi.  
  
 *uiSrc*  
 Bir `unsigned int` yeni içine Kopyalanacak değer `_variant_t` nesnesi.  
  
 *i8Src*  
 Bir __**Int64** yeni içine Kopyalanacak değer `_variant_t` nesnesi.  
  
 *ui8Src*  
 Bir **imzasız __int64** yeni içine Kopyalanacak değer `_variant_t` nesnesi.  
  
## <a name="remarks"></a>Açıklamalar  
  
-   **_variant_t ()** boş bir yapıları `_variant_t` nesnesi `VT_EMPTY`.  
  
-   **_variant_t (değişken &***varSrc***)** oluşturan bir `_variant_t` bir kopyasını nesnesinden **değişken** nesnesi. Değişken türü korunur.  
  
-   **_variant_t (değişken\****pVarSrc***)** oluşturan bir `_variant_t` bir kopyasını nesnesinden **değişken** nesnesi.     Değişken türü korunur.  
  
-   **_variant_t (_variant_t &***var_t_Src***)** oluşturan bir `_variant_t` başka bir nesne `_variant_t` nesne.     Değişken türü korunur.  
  
-   **_variant_t (değişken &***varSrc* **, bool**`fCopy`**)** oluşturan bir `_variant_t` varolan bir nesne  **DEĞİŞKEN** nesnesi. Varsa `fCopy` olan **false**, **değişken** kopyasını yapmadan nesne yeni nesneye eklenir.  
  
-   **_variant_t (kısa***sSrc* **, VARTYPE**`vtSrc`**VT_I2 =)** oluşturan bir `_variant_t` nesne türü `VT_I2` veya `VT_BOOL` gelen bir **kısa** tamsayı değeri.       Diğer **VARTYPE** sonuçlanan bir `E_INVALIDARG` hata.  
  
-   **_variant_t (uzun** `lSrc` **, VARTYPE**`vtSrc`**VT_I4 =)** oluşturan bir `_variant_t` nesne türü `VT_I4`, `VT_BOOL`, veya `VT_ERROR`gelen bir **uzun** tamsayı değeri.       Diğer **VARTYPE** sonuçlanan bir `E_INVALIDARG` hata.  
  
-   **_variant_t (float**`fltSrc`**)** oluşturan bir `_variant_t` nesne türü `VT_R4` gelen bir **float** sayısal değer.  
  
-   **_variant_t (çift** `dblSrc` **, VARTYPE**`vtSrc`**VT_R8 =)** oluşturan bir `_variant_t` nesne türü `VT_R8` veya `VT_DATE` bir gelen**çift** sayısal değer.       Diğer **VARTYPE** sonuçlanan bir `E_INVALIDARG` hata.  
  
-   **_variant_t (CY &**`cySrc`**)** oluşturan bir `_variant_t` nesne türü `VT_CY` gelen bir **CY** nesnesi.  
  
-   **_variant_t (_bstr_t &**`bstrSrc`**)** oluşturan bir `_variant_t` nesne türü `VT_BSTR` gelen bir `_bstr_t` nesnesi.     Yeni bir `BSTR` ayrılır.  
  
-   **_variant_t (wchar_t \***  *wstrSrc***)** oluşturan bir `_variant_t` nesne türü `VT_BSTR` bir Unicode dizeden.   Yeni bir `BSTR` ayrılır.  
  
-   **_variant_t (char\***`strSrc`**)** oluşturan bir `_variant_t` nesne türü `VT_BSTR` bir dizeden.     Yeni bir `BSTR` ayrılır.  
  
-   **_variant_t (bool**`bSrc`**)** oluşturan bir `_variant_t` nesne türü `VT_BOOL` gelen bir `bool` değeri.  
  
-   **_variant_t (IUnknown\***  `pIUknownSrc` **, bool**`fAddRef`**= true)** oluşturan bir `_variant_t` nesne türü **VT_UNKNOWN** gelen COM arabirimi işaretçisi. Varsa `fAddRef` olan **true**, ardından `AddRef` çağrısı eşleştirmek için sağlanan arabirim işaretçisi olarak adlandırılan **sürüm** , gerçekleşeceği zaman `_variant_t` nesne yok. Çağrı size olan **sürüm** sağlanan arabirim işaretçisi üzerinde. Varsa `fAddRef` olan **false**, sağlanan arabirim işaretçisi sahipliğini bu oluşturucuyu alır; çağırmayın **sürüm** sağlanan arabirim işaretçisi üzerinde.  
  
-   **_variant_t (IDispatch\***  `pDispSrc` **, bool**`fAddRef`**= true)** oluşturan bir `_variant_t` nesne türü **VT_DISPATCH** gelen COM arabirimi işaretçisi. Varsa `fAddRef` olan **true**, ardından `AddRef` çağrısı eşleştirmek için sağlanan arabirim işaretçisi olarak adlandırılan **sürüm** , gerçekleşeceği zaman `_variant_t` nesne yok. Çağrı size olan **sürüm** sağlanan arabirim işaretçisi üzerinde. Varsa **fAddRef** olan false, bu Oluşturucusu sağlanan arabirim işaretçisi sahipliğini alır; çağırmayın **sürüm** sağlanan arabirim işaretçisi üzerinde.  
  
-   **_variant_t (ondalık &**`decSrc`**)** oluşturan bir `_variant_t` nesne türü **VT_DECIMAL** gelen bir **ondalık** değeri.      
  
-   **_variant_t (bayt**`bSrc`**)** oluşturan bir `_variant_t` nesne türü `VT_UI1` gelen bir **bayt** değeri.  
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [_variant_t Sınıfı](../cpp/variant-t-class.md)