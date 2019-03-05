---
title: Kayıt defteri veri değişim makroları
ms.date: 11/04/2016
f1_keywords:
- atlplus/ATL::BEGIN_RDX_MAP
- atlplus/ATL::END_RDX_MAP
- atlplus/ATL::RDX_BINARY
- atlplus/ATL::RDX_CSTRING_TEXT
- atlplus/ATL::RDX_DWORD
- atlplus/ATL::RDX_TEXT
helpviewer_keywords:
- RegistryDataExchange function, macros
ms.assetid: c1bc5e79-2307-43d2-9d10-3a62ffadf473
ms.openlocfilehash: 69b823cbcd85ebaaeb05979283ea4f8fea80f4b6
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57290696"
---
# <a name="registry-data-exchange-macros"></a>Kayıt defteri veri değişim makroları

Bu makrolar, kayıt defteri veri değişimi işlemleri gerçekleştirir.

|||
|-|-|
|[BEGIN_RDX_MAP](#begin_rdx_map)|Kayıt defteri veri değişimi harita başlangıcını işaretler.|
|[END_RDX_MAP](#end_rdx_map)|Kayıt defteri veri değişimi harita sonunu işaretler.|
|[RDX_BINARY](#rdx_binary)|Belirtilen kayıt defteri girdisi türü bayt belirtilen üye değişkeni ile ilişkilendirir.|
|[RDX_CSTRING_TEXT](#rdx_cstring_text)|Belirtilen kayıt defteri girdisi türü CString belirtilen üye değişkeni ile ilişkilendirir.|
|[RDX_DWORD](#rdx_dword)|Belirtilen kayıt defteri girdisini DWORD türünün belirtilen üye değişkeni ile ilişkilendirir.|
|[RDX_TEXT](#rdx_text)|Belirtilen kayıt defteri girdisini TCHAR türü belirtilen üye değişkeni ile ilişkilendirir.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlplus.h

##  <a name="begin_rdx_map"></a>  BEGIN_RDX_MAP

Kayıt defteri veri değişimi harita başlangıcını işaretler.

```
BEGIN_RDX_MAP
```

### <a name="remarks"></a>Açıklamalar

Aşağıdaki makroları, kayıt defteri veri değişimi eşlemesi içinde okuyup girişleri sistem kayıt defterine yazmak için kullanılır:

|Makrosu|Açıklama|
|-----------|-----------------|
|[RDX_BINARY](#rdx_binary)|Belirtilen kayıt defteri girdisi türü bayt belirtilen üye değişkeni ile ilişkilendirir.|
|[RDX_DWORD](#rdx_dword)|Belirtilen kayıt defteri girdisini DWORD türünün belirtilen üye değişkeni ile ilişkilendirir.|
|[RDX_CSTRING_TEXT](#rdx_cstring_text)|Belirtilen kayıt defteri girdisi türü CString belirtilen üye değişkeni ile ilişkilendirir.|
|[RDX_TEXT](#rdx_text)|Belirtilen kayıt defteri girdisini TCHAR türü belirtilen üye değişkeni ile ilişkilendirir.|

Genel işlev [RegistryDataExchange](../../atl/reference/registry-and-typelib-global-functions.md#registrydataexchange), veya kodunuzu sistem kayıt defteri arasında veri değişimi gerektiğinde BEGIN_RDX_MAP ve END_RDX_MAP makroları tarafından oluşturulan aynı ada sahip bir üye işlevi kullanılmalıdır ve RDX eşlemesinde belirtilen değişkenler.

##  <a name="end_rdx_map"></a>  END_RDX_MAP

Kayıt defteri veri değişimi harita sonunu işaretler.

```
END_RDX_MAP
```

##  <a name="rdx_binary"></a>  RDX_BINARY

Belirtilen kayıt defteri girdisi türü bayt belirtilen üye değişkeni ile ilişkilendirir.

```
RDX_BINARY(
    rootkey,
    subkey,
    valuename,
    member,
    member_size )
```

### <a name="parameters"></a>Parametreler

*ROOTKEY*<br/>
Kayıt defteri anahtarı kökü.

*alt*<br/>
Kayıt defteri alt anahtarı.

*değer adı*<br/>
Kayıt defteri anahtarı.

*Üyesi*<br/>
Belirtilen kayıt defteri girişi ile ilişkilendirmek için üye değişkeni.

*member_size*<br/>
Üye değişkeni bayt cinsinden boyutu.

### <a name="remarks"></a>Açıklamalar

Bu makro, bir üye değişkeni bir belirli kayıt defteri girişi ile ilişkilendirilecek BEGIN_RDX_MAP ve END_RDX_MAP makroları ile birlikte kullanılır. Genel işlev [RegistryDataExchange](../../atl/reference/registry-and-typelib-global-functions.md#registrydataexchange), veya üye değişkenleri arasındaki sistem kayıt defteri veri değişim yapması BEGIN_RDX_MAP ve END_RDX_MAP makroları tarafından oluşturulan aynı ada sahip bir üye işlevi kullanılmalıdır RDX haritada.

##  <a name="rdx_cstring_text"></a>  RDX_CSTRING_TEXT

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

*ROOTKEY*<br/>
Kayıt defteri anahtarı kökü.

*alt*<br/>
Kayıt defteri alt anahtarı.

*değer adı*<br/>
Kayıt defteri anahtarı.

*Üyesi*<br/>
Belirtilen kayıt defteri girişi ile ilişkilendirmek için üye değişkeni.

*member_size*<br/>
Üye değişkeni bayt cinsinden boyutu.

### <a name="remarks"></a>Açıklamalar

Bu makro, bir üye değişkeni bir belirli kayıt defteri girişi ile ilişkilendirilecek BEGIN_RDX_MAP ve END_RDX_MAP makroları ile birlikte kullanılır. Genel işlev [RegistryDataExchange](../../atl/reference/registry-and-typelib-global-functions.md#registrydataexchange), veya üye değişkenleri arasındaki sistem kayıt defteri veri değişim yapması BEGIN_RDX_MAP ve END_RDX_MAP makroları tarafından oluşturulan aynı ada sahip bir üye işlevi kullanılmalıdır RDX haritada.

##  <a name="rdx_dword"></a>  RDX_DWORD

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

*ROOTKEY*<br/>
Kayıt defteri anahtarı kökü.

*alt*<br/>
Kayıt defteri alt anahtarı.

*değer adı*<br/>
Kayıt defteri anahtarı.

*Üyesi*<br/>
Belirtilen kayıt defteri girişi ile ilişkilendirmek için üye değişkeni.

*member_size*<br/>
Üye değişkeni bayt cinsinden boyutu.

### <a name="remarks"></a>Açıklamalar

Bu makro, bir üye değişkeni bir belirli kayıt defteri girişi ile ilişkilendirilecek BEGIN_RDX_MAP ve END_RDX_MAP makroları ile birlikte kullanılır. Genel işlev [RegistryDataExchange](../../atl/reference/registry-and-typelib-global-functions.md#registrydataexchange), veya üye değişkenleri arasındaki sistem kayıt defteri veri değişim yapması BEGIN_RDX_MAP ve END_RDX_MAP makroları tarafından oluşturulan aynı ada sahip bir üye işlevi kullanılmalıdır RDX haritada.

##  <a name="rdx_text"></a>  RDX_TEXT

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

*ROOTKEY*<br/>
Kayıt defteri anahtarı kökü.

*alt*<br/>
Kayıt defteri alt anahtarı.

*değer adı*<br/>
Kayıt defteri anahtarı.

*Üyesi*<br/>
Belirtilen kayıt defteri girişi ile ilişkilendirmek için üye değişkeni.

*member_size*<br/>
Üye değişkeni bayt cinsinden boyutu.

### <a name="remarks"></a>Açıklamalar

Bu makro, bir üye değişkeni bir belirli kayıt defteri girişi ile ilişkilendirilecek BEGIN_RDX_MAP ve END_RDX_MAP makroları ile birlikte kullanılır. Genel işlev [RegistryDataExchange](../../atl/reference/registry-and-typelib-global-functions.md#registrydataexchange), veya üye değişkenleri arasındaki sistem kayıt defteri veri değişim yapması BEGIN_RDX_MAP ve END_RDX_MAP makroları tarafından oluşturulan aynı ada sahip bir üye işlevi kullanılmalıdır RDX haritada.

## <a name="see-also"></a>Ayrıca bkz.

[Makroları](../../atl/reference/atl-macros.md)<br/>
[RegistryDataExchange](../../atl/reference/registry-and-typelib-global-functions.md#registrydataexchange)
