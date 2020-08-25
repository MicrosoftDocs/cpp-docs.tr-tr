---
title: Kayıt defteri verileri Exchange makroları
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
ms.openlocfilehash: 507db77b525c526fe1cd47c7d75c34e15a6a0628
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88834550"
---
# <a name="registry-data-exchange-macros"></a>Kayıt defteri verileri Exchange makroları

Bu makrolar kayıt defteri verilerini değiştirme işlemleri gerçekleştirir.

|Ad|Açıklama|
|-|-|
|[BEGIN_RDX_MAP](#begin_rdx_map)|Kayıt defteri veri değişimi eşlemesinin başlangıcını işaretler.|
|[END_RDX_MAP](#end_rdx_map)|Kayıt defteri veri değişimi eşlemesinin sonunu işaretler.|
|[RDX_BINARY](#rdx_binary)|Belirtilen kayıt defteri girişini BYTE türünde belirtilen bir üye değişkeniyle ilişkilendirir.|
|[RDX_CSTRING_TEXT](#rdx_cstring_text)|Belirtilen kayıt defteri girişini CString türünde belirtilen bir üye değişkeniyle ilişkilendirir.|
|[RDX_DWORD](#rdx_dword)|Belirtilen kayıt defteri girişini DWORD türünde belirtilen bir üye değişkeniyle ilişkilendirir.|
|[RDX_TEXT](#rdx_text)|Belirtilen kayıt defteri girişini TCHAR türünde belirtilen bir üye değişkeniyle ilişkilendirir.|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlplus. h

## <a name="begin_rdx_map"></a><a name="begin_rdx_map"></a> BEGIN_RDX_MAP

Kayıt defteri veri değişimi eşlemesinin başlangıcını işaretler.

```
BEGIN_RDX_MAP
```

### <a name="remarks"></a>Açıklamalar

Aşağıdaki makrolar, kayıt defteri veri değişim haritasında sistem kayıt defterindeki girdileri okumak ve yazmak için kullanılır:

|Makroya|Açıklama|
|-----------|-----------------|
|[RDX_BINARY](#rdx_binary)|Belirtilen kayıt defteri girişini BYTE türünde belirtilen bir üye değişkeniyle ilişkilendirir.|
|[RDX_DWORD](#rdx_dword)|Belirtilen kayıt defteri girişini DWORD türünde belirtilen bir üye değişkeniyle ilişkilendirir.|
|[RDX_CSTRING_TEXT](#rdx_cstring_text)|Belirtilen kayıt defteri girişini CString türünde belirtilen bir üye değişkeniyle ilişkilendirir.|
|[RDX_TEXT](#rdx_text)|Belirtilen kayıt defteri girişini TCHAR türünde belirtilen bir üye değişkeniyle ilişkilendirir.|

Kayıt defteri \ [genel işlevi veya](../../atl/reference/registry-and-typelib-global-functions.md#registrydataexchange)BEGIN_RDX_MAP ve END_RDX_MAP makroları tarafından oluşturulan aynı ada sahip üye işlevi, kodunuzun sistem kayıt defteri ile RDX eşlemesinde belirtilen değişkenler arasında veri alışverişi yapması gerektiğinde kullanılmalıdır.

## <a name="end_rdx_map"></a><a name="end_rdx_map"></a> END_RDX_MAP

Kayıt defteri veri değişimi eşlemesinin sonunu işaretler.

```
END_RDX_MAP
```

## <a name="rdx_binary"></a><a name="rdx_binary"></a> RDX_BINARY

Belirtilen kayıt defteri girişini BYTE türünde belirtilen bir üye değişkeniyle ilişkilendirir.

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

*anahtarın*<br/>
Kayıt defteri alt anahtarı.

*ValueName*<br/>
Kayıt defteri anahtarı.

*üyesidir*<br/>
Belirtilen kayıt defteri girdisiyle ilişkilendirilecek üye değişkeni.

*member_size*<br/>
Üye değişkeninin bayt cinsinden boyutu.

### <a name="remarks"></a>Açıklamalar

Bu makro, bir üye değişkenini belirli bir kayıt defteri girdisiyle ilişkilendirmek için BEGIN_RDX_MAP ve END_RDX_MAP makrolarıyla birlikte kullanılır. [RegistryDataExchange](../../atl/reference/registry-and-typelib-global-functions.md#registrydataexchange)genel işlevi veya BEGIN_RDX_MAP ve END_RDX_MAP makroları tarafından oluşturulan aynı adın üye işlevi, sistem kayıt defteri ile RDX eşlemesindeki üye değişkenleri arasında veri alışverişi gerçekleştirmek için kullanılmalıdır.

## <a name="rdx_cstring_text"></a><a name="rdx_cstring_text"></a> RDX_CSTRING_TEXT

Belirtilen kayıt defteri girişini CString türünde belirtilen bir üye değişkeniyle ilişkilendirir.

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

*anahtarın*<br/>
Kayıt defteri alt anahtarı.

*ValueName*<br/>
Kayıt defteri anahtarı.

*üyesidir*<br/>
Belirtilen kayıt defteri girdisiyle ilişkilendirilecek üye değişkeni.

*member_size*<br/>
Üye değişkeninin bayt cinsinden boyutu.

### <a name="remarks"></a>Açıklamalar

Bu makro, bir üye değişkenini belirli bir kayıt defteri girdisiyle ilişkilendirmek için BEGIN_RDX_MAP ve END_RDX_MAP makrolarıyla birlikte kullanılır. [RegistryDataExchange](../../atl/reference/registry-and-typelib-global-functions.md#registrydataexchange)genel işlevi veya BEGIN_RDX_MAP ve END_RDX_MAP makroları tarafından oluşturulan aynı adın üye işlevi, sistem kayıt defteri ile RDX eşlemesindeki üye değişkenleri arasında veri alışverişi gerçekleştirmek için kullanılmalıdır.

## <a name="rdx_dword"></a><a name="rdx_dword"></a> RDX_DWORD

Belirtilen kayıt defteri girişini DWORD türünde belirtilen bir üye değişkeniyle ilişkilendirir.

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

*anahtarın*<br/>
Kayıt defteri alt anahtarı.

*ValueName*<br/>
Kayıt defteri anahtarı.

*üyesidir*<br/>
Belirtilen kayıt defteri girdisiyle ilişkilendirilecek üye değişkeni.

*member_size*<br/>
Üye değişkeninin bayt cinsinden boyutu.

### <a name="remarks"></a>Açıklamalar

Bu makro, bir üye değişkenini belirli bir kayıt defteri girdisiyle ilişkilendirmek için BEGIN_RDX_MAP ve END_RDX_MAP makrolarıyla birlikte kullanılır. [RegistryDataExchange](../../atl/reference/registry-and-typelib-global-functions.md#registrydataexchange)genel işlevi veya BEGIN_RDX_MAP ve END_RDX_MAP makroları tarafından oluşturulan aynı adın üye işlevi, sistem kayıt defteri ile RDX eşlemesindeki üye değişkenleri arasında veri alışverişi gerçekleştirmek için kullanılmalıdır.

## <a name="rdx_text"></a><a name="rdx_text"></a> RDX_TEXT

Belirtilen kayıt defteri girişini TCHAR türünde belirtilen bir üye değişkeniyle ilişkilendirir.

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

*anahtarın*<br/>
Kayıt defteri alt anahtarı.

*ValueName*<br/>
Kayıt defteri anahtarı.

*üyesidir*<br/>
Belirtilen kayıt defteri girdisiyle ilişkilendirilecek üye değişkeni.

*member_size*<br/>
Üye değişkeninin bayt cinsinden boyutu.

### <a name="remarks"></a>Açıklamalar

Bu makro, bir üye değişkenini belirli bir kayıt defteri girdisiyle ilişkilendirmek için BEGIN_RDX_MAP ve END_RDX_MAP makrolarıyla birlikte kullanılır. [RegistryDataExchange](../../atl/reference/registry-and-typelib-global-functions.md#registrydataexchange)genel işlevi veya BEGIN_RDX_MAP ve END_RDX_MAP makroları tarafından oluşturulan aynı adın üye işlevi, sistem kayıt defteri ile RDX eşlemesindeki üye değişkenleri arasında veri alışverişi gerçekleştirmek için kullanılmalıdır.

## <a name="see-also"></a>Ayrıca bkz.

[Makrolar](../../atl/reference/atl-macros.md)<br/>
[RegistryDataExchange](../../atl/reference/registry-and-typelib-global-functions.md#registrydataexchange)
