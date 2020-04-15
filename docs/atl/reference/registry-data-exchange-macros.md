---
title: Kayıt Defteri Veri Değişim Makroları
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
ms.openlocfilehash: a7d580e4907cec40f97c0cead616665fff7b8a01
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326066"
---
# <a name="registry-data-exchange-macros"></a>Kayıt Defteri Veri Değişim Makroları

Bu makrolar Kayıt Defteri Veri Alışverişi işlemlerini gerçekleştirir.

|||
|-|-|
|[BEGIN_RDX_MAP](#begin_rdx_map)|Kayıt Defteri Veri Alışverişi haritasının başlangıcını işaretler.|
|[END_RDX_MAP](#end_rdx_map)|Kayıt Defteri Veri Alışverişi haritasının sonunu işaretler.|
|[RDX_BINARY](#rdx_binary)|Belirtilen kayıt defteri girişini BYTE türünde belirli bir üye değişkenle ilişkilendirer.|
|[RDX_CSTRING_TEXT](#rdx_cstring_text)|Belirtilen kayıt defteri girişini CString türünün belirli bir üye değişkeniyle ilişkilendirer.|
|[RDX_DWORD](#rdx_dword)|Belirtilen kayıt defteri girişini DWORD türünün belirli bir üye değişkeniyle ilişkilendirin.|
|[RDX_TEXT](#rdx_text)|Belirtilen kayıt defteri girişini TCHAR türünün belirli bir üye değişkeniyle ilişkilendirin.|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlplus.h

## <a name="begin_rdx_map"></a><a name="begin_rdx_map"></a>BEGIN_RDX_MAP

Kayıt Defteri Veri Alışverişi haritasının başlangıcını işaretler.

```
BEGIN_RDX_MAP
```

### <a name="remarks"></a>Açıklamalar

Aşağıdaki makrolar, sistem kayıt defterindeki girişleri okumak ve yazmak için Kayıt Defteri Veri Alışverişi haritasında kullanılır:

|Makro|Açıklama|
|-----------|-----------------|
|[RDX_BINARY](#rdx_binary)|Belirtilen kayıt defteri girişini BYTE türünde belirli bir üye değişkenle ilişkilendirer.|
|[RDX_DWORD](#rdx_dword)|Belirtilen kayıt defteri girişini DWORD türünün belirli bir üye değişkeniyle ilişkilendirin.|
|[RDX_CSTRING_TEXT](#rdx_cstring_text)|Belirtilen kayıt defteri girişini CString türünün belirli bir üye değişkeniyle ilişkilendirer.|
|[RDX_TEXT](#rdx_text)|Belirtilen kayıt defteri girişini TCHAR türünün belirli bir üye değişkeniyle ilişkilendirin.|

Genel işlev [RegistryDataExchange](../../atl/reference/registry-and-typelib-global-functions.md#registrydataexchange)veya BEGIN_RDX_MAP ve END_RDX_MAP makroları tarafından oluşturulan aynı adıtaşıyan üye işlevi, kodunuzu sistem kayıt defteri ve RDX haritada belirtilen değişkenler arasında veri alışverişi gerektiğinde kullanılmalıdır.

## <a name="end_rdx_map"></a><a name="end_rdx_map"></a>END_RDX_MAP

Kayıt Defteri Veri Alışverişi haritasının sonunu işaretler.

```
END_RDX_MAP
```

## <a name="rdx_binary"></a><a name="rdx_binary"></a>RDX_BINARY

Belirtilen kayıt defteri girişini BYTE türünde belirli bir üye değişkenle ilişkilendirer.

```
RDX_BINARY(
    rootkey,
    subkey,
    valuename,
    member,
    member_size )
```

### <a name="parameters"></a>Parametreler

*rootkey*<br/>
Kayıt defteri anahtar kökü.

*Alt anahtarı*<br/>
Kayıt defteri alt anahtarı.

*Valuename*<br/>
Kayıt defteri anahtarı.

*Üye*<br/>
Belirtilen kayıt defteri girişi ile ilişkilendirmek için üye değişken.

*member_size*<br/>
Üye değişkenin baytboyutu.

### <a name="remarks"></a>Açıklamalar

Bu makro, üye değişkeni belirli bir kayıt defteri girişiyle ilişkilendirmek için BEGIN_RDX_MAP ve END_RDX_MAP makrolarla birlikte kullanılır. Genel işlev [RegistryDataExchange](../../atl/reference/registry-and-typelib-global-functions.md#registrydataexchange)veya BEGIN_RDX_MAP ve END_RDX_MAP makrolar tarafından oluşturulan aynı adıtaşıyan üye işlevi, sistem kayıt defteri ve RDX haritasında üye değişkenler arasında veri alışverişi gerçekleştirmek için kullanılmalıdır.

## <a name="rdx_cstring_text"></a><a name="rdx_cstring_text"></a>RDX_CSTRING_TEXT

Belirtilen kayıt defteri girişini CString türünün belirli bir üye değişkeniyle ilişkilendirer.

```
RDX_CSTRING_TEXT(
    rootkey,
    subkey,
    valuename,
    member,
    member_size )
```

### <a name="parameters"></a>Parametreler

*rootkey*<br/>
Kayıt defteri anahtar kökü.

*Alt anahtarı*<br/>
Kayıt defteri alt anahtarı.

*Valuename*<br/>
Kayıt defteri anahtarı.

*Üye*<br/>
Belirtilen kayıt defteri girişi ile ilişkilendirmek için üye değişken.

*member_size*<br/>
Üye değişkenin baytboyutu.

### <a name="remarks"></a>Açıklamalar

Bu makro, üye değişkeni belirli bir kayıt defteri girişiyle ilişkilendirmek için BEGIN_RDX_MAP ve END_RDX_MAP makrolarla birlikte kullanılır. Genel işlev [RegistryDataExchange](../../atl/reference/registry-and-typelib-global-functions.md#registrydataexchange)veya BEGIN_RDX_MAP ve END_RDX_MAP makrolar tarafından oluşturulan aynı adıtaşıyan üye işlevi, sistem kayıt defteri ve RDX haritasında üye değişkenler arasında veri alışverişi gerçekleştirmek için kullanılmalıdır.

## <a name="rdx_dword"></a><a name="rdx_dword"></a>RDX_DWORD

Belirtilen kayıt defteri girişini DWORD türünün belirli bir üye değişkeniyle ilişkilendirin.

```
RDX_DWORD(
    rootkey,
    subkey,
    valuename,
    member,
    member_size )
```

### <a name="parameters"></a>Parametreler

*rootkey*<br/>
Kayıt defteri anahtar kökü.

*Alt anahtarı*<br/>
Kayıt defteri alt anahtarı.

*Valuename*<br/>
Kayıt defteri anahtarı.

*Üye*<br/>
Belirtilen kayıt defteri girişi ile ilişkilendirmek için üye değişken.

*member_size*<br/>
Üye değişkenin baytboyutu.

### <a name="remarks"></a>Açıklamalar

Bu makro, üye değişkeni belirli bir kayıt defteri girişiyle ilişkilendirmek için BEGIN_RDX_MAP ve END_RDX_MAP makrolarla birlikte kullanılır. Genel işlev [RegistryDataExchange](../../atl/reference/registry-and-typelib-global-functions.md#registrydataexchange)veya BEGIN_RDX_MAP ve END_RDX_MAP makrolar tarafından oluşturulan aynı adıtaşıyan üye işlevi, sistem kayıt defteri ve RDX haritasında üye değişkenler arasında veri alışverişi gerçekleştirmek için kullanılmalıdır.

## <a name="rdx_text"></a><a name="rdx_text"></a>RDX_TEXT

Belirtilen kayıt defteri girişini TCHAR türünün belirli bir üye değişkeniyle ilişkilendirin.

```
RDX_TEXT(
    rootkey,
    subkey,
    valuename,
    member,
    member_size )
```

### <a name="parameters"></a>Parametreler

*rootkey*<br/>
Kayıt defteri anahtar kökü.

*Alt anahtarı*<br/>
Kayıt defteri alt anahtarı.

*Valuename*<br/>
Kayıt defteri anahtarı.

*Üye*<br/>
Belirtilen kayıt defteri girişi ile ilişkilendirmek için üye değişken.

*member_size*<br/>
Üye değişkenin baytboyutu.

### <a name="remarks"></a>Açıklamalar

Bu makro, üye değişkeni belirli bir kayıt defteri girişiyle ilişkilendirmek için BEGIN_RDX_MAP ve END_RDX_MAP makrolarla birlikte kullanılır. Genel işlev [RegistryDataExchange](../../atl/reference/registry-and-typelib-global-functions.md#registrydataexchange)veya BEGIN_RDX_MAP ve END_RDX_MAP makrolar tarafından oluşturulan aynı adıtaşıyan üye işlevi, sistem kayıt defteri ve RDX haritasında üye değişkenler arasında veri alışverişi gerçekleştirmek için kullanılmalıdır.

## <a name="see-also"></a>Ayrıca bkz.

[Makrolar](../../atl/reference/atl-macros.md)<br/>
[Kayıt DefteriDataExchange](../../atl/reference/registry-and-typelib-global-functions.md#registrydataexchange)
