---
title: "Kayıt defteri veri değişimi makroları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- atlplus/ATL::BEGIN_RDX_MAP
- atlplus/ATL::END_RDX_MAP
- atlplus/ATL::RDX_BINARY
- atlplus/ATL::RDX_CSTRING_TEXT
- atlplus/ATL::RDX_DWORD
- atlplus/ATL::RDX_TEXT
dev_langs:
- C++
helpviewer_keywords:
- RegistryDataExchange function, macros
ms.assetid: c1bc5e79-2307-43d2-9d10-3a62ffadf473
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0bc12c48ef628a42c309c44ce0fc37abda9b6690
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="registry-data-exchange-macros"></a>Kayıt defteri veri Exchange makroları
Bu makroları kayıt defteri veri değişimi işlemleri gerçekleştirir.  
  
|||  
|-|-|  
|[BEGIN_RDX_MAP](#begin_rdx_map)|Kayıt defteri veri değişimi harita başlangıcını işaretler.|  
|[END_RDX_MAP](#end_rdx_map)|Kayıt defteri veri değişimi harita sonunu işaretler.|  
|[RDX_BINARY](#rdx_binary)|Belirtilen kayıt defteri girdisini bayt türünde belirtilen üye değişkeni ile ilişkilendirir.|  
|[RDX_CSTRING_TEXT](#rdx_cstring_text)|Belirtilen kayıt defteri girdisi türü CString belirtilen üye değişkeni ile ilişkilendirir.|  
|[RDX_DWORD](#rdx_dword)|Belirtilen kayıt defteri girdisini DWORD türünün belirtilen üye değişkeni ile ilişkilendirir.|  
|[RDX_TEXT](#rdx_text)|Belirtilen kayıt defteri girdisini TCHAR türü belirtilen üye değişkeni ile ilişkilendirir.|  

## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlplus.h  
   
##  <a name="begin_rdx_map"></a>BEGIN_RDX_MAP  
 Kayıt defteri veri değişimi harita başlangıcını işaretler.  
  
```
BEGIN_RDX_MAP
```  
  
### <a name="remarks"></a>Açıklamalar  
 Aşağıdaki makroları içinde kayıt defteri veri değişimi harita okumak ve sistem kayıt defterinde girişler yazmak için kullanılır:  
  
|Makrosu|Açıklama|  
|-----------|-----------------|  
|[RDX_BINARY](#rdx_binary)|Belirtilen kayıt defteri girdisini bayt türünde belirtilen üye değişkeni ile ilişkilendirir.|  
|[RDX_DWORD](#rdx_dword)|Belirtilen kayıt defteri girdisini DWORD türünün belirtilen üye değişkeni ile ilişkilendirir.|  
|[RDX_CSTRING_TEXT](#rdx_cstring_text)|Belirtilen kayıt defteri girdisi türü CString belirtilen üye değişkeni ile ilişkilendirir.|  
|[RDX_TEXT](#rdx_text)|Belirtilen kayıt defteri girdisini TCHAR türü belirtilen üye değişkeni ile ilişkilendirir.|  
  
 Genel işlevin [RegistryDataExchange](../../atl/reference/registry-and-typelib-global-functions.md#registrydataexchange), veya üye işlevi tarafından oluşturulan aynı ada sahip `BEGIN_RDX_MAP` ve `END_RDX_MAP` makroları, kodunuzu sistem kayıt defteri arasında veri değişimi gerektiğinde kullanılmalıdır ve RDX eşlemesinde belirtilen değişkenleri.  
  
##  <a name="end_rdx_map"></a>END_RDX_MAP  
 Kayıt defteri veri değişimi harita sonunu işaretler.  
  
```
END_RDX_MAP
```  
  
##  <a name="rdx_binary"></a>RDX_BINARY  
 Belirtilen kayıt defteri girdisini bayt türünde belirtilen üye değişkeni ile ilişkilendirir.  
  
```
RDX_BINARY(
    rootkey, 
    subkey, 
    valuename, 
    member, 
    member_size )
```  
  
### <a name="parameters"></a>Parametreler  
 `rootkey`  
 Kayıt defteri anahtarı kökü.  
  
 `subkey`  
 Kayıt defteri alt anahtarı.  
  
 `valuename`  
 Kayıt defteri anahtarı.  
  
 `member`  
 Belirtilen kayıt defteri girişi ile ilişkilendirmek için üye değişkeni.  
  
 `member_size`  
 Üye değişkeni bayt cinsinden boyutu.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu makrosu ile birlikte kullanılan `BEGIN_RDX_MAP` ve `END_RDX_MAP` makroları bir üye değişkenine bir belirli kayıt defteri girdisi ile ilişkilendirilecek. Genel işlevin [RegistryDataExchange](../../atl/reference/registry-and-typelib-global-functions.md#registrydataexchange), veya üye işlevi tarafından oluşturulan aynı ada sahip `BEGIN_RDX_MAP` ve `END_RDX_MAP` makroları, sistem kayıt defteri ve üye arasında veri değişimi gerçekleştirmek için kullanılması gerekir RDX harita değişkenleri.  
  
##  <a name="rdx_cstring_text"></a>RDX_CSTRING_TEXT  
 Belirtilen kayıt defteri girdisi türü CString belirtilen üye değişkeni ile ilişkilendirir.  
  
```
RDX_CSTRING_TEXT(
    rootkey, 
    subkey, 
    valuename, 
    member, 
    member_size )
```  
  
### <a name="parameters"></a>Parametreler  
 `rootkey`  
 Kayıt defteri anahtarı kökü.  
  
 `subkey`  
 Kayıt defteri alt anahtarı.  
  
 `valuename`  
 Kayıt defteri anahtarı.  
  
 `member`  
 Belirtilen kayıt defteri girişi ile ilişkilendirmek için üye değişkeni.  
  
 `member_size`  
 Üye değişkeni bayt cinsinden boyutu.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu makrosu ile birlikte kullanılan `BEGIN_RDX_MAP` ve `END_RDX_MAP` makroları bir üye değişkenine bir belirli kayıt defteri girdisi ile ilişkilendirilecek. Genel işlevin [RegistryDataExchange](../../atl/reference/registry-and-typelib-global-functions.md#registrydataexchange), veya üye işlevi tarafından oluşturulan aynı ada sahip `BEGIN_RDX_MAP` ve `END_RDX_MAP` makroları, sistem kayıt defteri ve üye arasında veri değişimi gerçekleştirmek için kullanılması gerekir RDX harita değişkenleri.  
  
##  <a name="rdx_dword"></a>RDX_DWORD  
 Belirtilen kayıt defteri girdisini DWORD türünün belirtilen üye değişkeni ile ilişkilendirir.  
  
```
RDX_DWORD(
    rootkey, 
    subkey, 
    valuename, 
    member, 
    member_size )
```  
  
### <a name="parameters"></a>Parametreler  
 `rootkey`  
 Kayıt defteri anahtarı kökü.  
  
 `subkey`  
 Kayıt defteri alt anahtarı.  
  
 `valuename`  
 Kayıt defteri anahtarı.  
  
 `member`  
 Belirtilen kayıt defteri girişi ile ilişkilendirmek için üye değişkeni.  
  
 `member_size`  
 Üye değişkeni bayt cinsinden boyutu.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu makrosu ile birlikte kullanılan `BEGIN_RDX_MAP` ve `END_RDX_MAP` makroları bir üye değişkenine bir belirli kayıt defteri girdisi ile ilişkilendirilecek. Genel işlevin [RegistryDataExchange](../../atl/reference/registry-and-typelib-global-functions.md#registrydataexchange), veya üye işlevi tarafından oluşturulan aynı ada sahip `BEGIN_RDX_MAP` ve `END_RDX_MAP` makroları, sistem kayıt defteri ve üye arasında veri değişimi gerçekleştirmek için kullanılması gerekir RDX harita değişkenleri.  
  
##  <a name="rdx_text"></a>RDX_TEXT  
 Belirtilen kayıt defteri girdisini TCHAR türü belirtilen üye değişkeni ile ilişkilendirir.  
  
```
RDX_TEXT(
    rootkey, 
    subkey, 
    valuename, 
    member, 
    member_size )
```  
  
### <a name="parameters"></a>Parametreler  
 `rootkey`  
 Kayıt defteri anahtarı kökü.  
  
 `subkey`  
 Kayıt defteri alt anahtarı.  
  
 `valuename`  
 Kayıt defteri anahtarı.  
  
 `member`  
 Belirtilen kayıt defteri girişi ile ilişkilendirmek için üye değişkeni.  
  
 `member_size`  
 Üye değişkeni bayt cinsinden boyutu.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu makrosu ile birlikte kullanılan `BEGIN_RDX_MAP` ve `END_RDX_MAP` makroları bir üye değişkenine bir belirli kayıt defteri girdisi ile ilişkilendirilecek. Genel işlevin [RegistryDataExchange](../../atl/reference/registry-and-typelib-global-functions.md#registrydataexchange), veya üye işlevi tarafından oluşturulan aynı ada sahip `BEGIN_RDX_MAP` ve `END_RDX_MAP` makroları, sistem kayıt defteri ve üye arasında veri değişimi gerçekleştirmek için kullanılması gerekir RDX harita değişkenleri.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Makroları](../../atl/reference/atl-macros.md)   
 [RegistryDataExchange](../../atl/reference/registry-and-typelib-global-functions.md#registrydataexchange)







