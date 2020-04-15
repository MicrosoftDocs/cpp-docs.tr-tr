---
title: CAtlComModule Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CAtlComModule
- ATLBASE/ATL::CAtlComModule
- ATLBASE/ATL::CAtlComModule::CAtlComModule
- ATLBASE/ATL::CAtlComModule::RegisterServer
- ATLBASE/ATL::CAtlComModule::RegisterTypeLib
- ATLBASE/ATL::CAtlComModule::UnregisterServer
- ATLBASE/ATL::CAtlComModule::UnRegisterTypeLib
helpviewer_keywords:
- CAtlComModule class
ms.assetid: af5dd71a-a0d1-4a2e-9a24-154a03381c75
ms.openlocfilehash: 68fdb48edc9304d9d74df6f36bd208cfd35ff307
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81321476"
---
# <a name="catlcommodule-class"></a>CAtlComModule Sınıfı

Bu sınıf bir COM sunucu modülü uygular.

## <a name="syntax"></a>Sözdizimi

```
class CAtlComModule : public _ATL_COM_MODULE
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CAtlComModülü::CAtlComModule](#catlcommodule)|Oluşturucu.|
|[CAtlComModülü::~CAtlComModule](#dtor)|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CAtlComModule::RegisterServer](#registerserver)|Nesne eşlenindeki her nesne için sistem kayıt defterini güncelleştirmek için bu yöntemi çağırın.|
|[CAtlComModule::RegisterTypeLib](#registertypelib)|Tür kitaplığını kaydetmek için bu yöntemi arayın.|
|[CAtlComModule::UnregisterServer](#unregisterserver)|Nesne eşlenindeki her nesnenin kaydını çıkarmak için bu yöntemi çağırın.|
|[CAtlComModule::Kayıt DışıTypeLib](#unregistertypelib)|Tür kitaplığını niçin iptal etmek için bu yöntemi çağırın.|

## <a name="remarks"></a>Açıklamalar

`CAtlComModule`istemcinin modülün bileşenlerine erişmesine izin veren bir COM sunucu modülü uygular.

Bu sınıf, ATL'nin önceki sürümlerinde kullanılan eski [CComModule](../../atl/reference/ccommodule-class.md) sınıfının yerini alır. Daha fazla bilgi için [ATL Modül Sınıfları'na](../../atl/atl-module-classes.md) bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[_ATL_COM_MODULE](atl-typedefs.md#_atl_com_module)

`CAtlComModule`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlbase.h

## <a name="catlcommodulecatlcommodule"></a><a name="catlcommodule"></a>CAtlComModülü::CAtlComModule

Oluşturucu.

```
CAtlComModule() throw();
```

### <a name="remarks"></a>Açıklamalar

Modülü niçin başlatılmasını.

## <a name="catlcommodulecatlcommodule"></a><a name="dtor"></a>CAtlComModülü::~CAtlComModule

Yıkıcı.

```
~CAtlComModule();
```

### <a name="remarks"></a>Açıklamalar

Tüm sınıf fabrikalarını serbest eder.

## <a name="catlcommoduleregisterserver"></a><a name="registerserver"></a>CAtlComModule::RegisterServer

Nesne eşlenindeki her nesne için sistem kayıt defterini güncelleştirmek için bu yöntemi çağırın.

```
HRESULT RegisterServer(BOOL bRegTypeLib = FALSE, const CLSID* pCLSID = NULL);
```

### <a name="parameters"></a>Parametreler

*bRegTypeLib*<br/>
Tür kitaplığı kaydedilecekse DOĞRU. Varsayılan değer FALSE'dur.

*pCLSID*<br/>
Kaydedilecek nesnenin CLSID'sine işaret edin. NULL (varsayılan değer) varsa, nesne eşlemindeki tüm nesneler kaydedilir.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

### <a name="remarks"></a>Açıklamalar

Küresel fonksiyon [AtlComModuleRegisterServer](server-registration-global-functions.md#atlcommoduleregisterserver)çağırır.

## <a name="catlcommoduleregistertypelib"></a><a name="registertypelib"></a>CAtlComModule::RegisterTypeLib

Tür kitaplığını kaydetmek için bu yöntemi arayın.

```
HRESULT RegisterTypeLib(LPCTSTR lpszIndex);
HRESULT RegisterTypeLib();
```

### <a name="parameters"></a>Parametreler

*lpszIndex*<br/>
N'nin TYPELIB kaynağının tümseci dizini olduğu "\\\N" biçimindeki dize.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

### <a name="remarks"></a>Açıklamalar

Sistem kayıt defterine tür kitaplığı hakkında bilgi ekler. Modül örneği birden çok tür kitaplığı içeriyorsa, hangi tür kitaplığın kullanılması gerektiğini belirtmek için bu yöntemin ilk sürümünü kullanın.

## <a name="catlcommoduleunregisterserver"></a><a name="unregisterserver"></a>CAtlComModule::UnregisterServer

Nesne eşlenindeki her nesnenin kaydını çıkarmak için bu yöntemi çağırın.

```
HRESULT UnregisterServer(
    BOOL bRegTypeLib = FALSE,
    const CLSID* pCLSID = NULL);
```

### <a name="parameters"></a>Parametreler

*bRegTypeLib*<br/>
Tür kitaplığı kayıtsız olacaksa DOĞRU. Varsayılan değer FALSE'dur.

*pCLSID*<br/>
Nesnenin CLSID'sine kayıtsız kalmak için işaret. NULL (varsayılan değer) varsa, nesne eşlemindeki tüm nesneler kayıtsız kalır.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

### <a name="remarks"></a>Açıklamalar

Küresel fonksiyon [AtlComModuleUnregisterServer](server-registration-global-functions.md#atlcommoduleunregisterserver)çağırır.

## <a name="catlcommoduleunregistertypelib"></a><a name="unregistertypelib"></a>CAtlComModule::Kayıt DışıTypeLib

Tür kitaplığını niçin iptal etmek için bu yöntemi çağırın.

```
HRESULT UnRegisterTypeLib(LPCTSTR lpszIndex);
HRESULT UnRegisterTypeLib();
```

### <a name="parameters"></a>Parametreler

*lpszIndex*<br/>
N'nin TYPELIB kaynağının tümseci dizini olduğu "\\\N" biçimindeki dize.

### <a name="remarks"></a>Açıklamalar

Tür kitaplığı hakkındaki bilgileri sistem kayıt defterinden kaldırır. Modül örneği birden çok tür kitaplığı içeriyorsa, hangi tür kitaplığın kullanılması gerektiğini belirtmek için bu yöntemin ilk sürümünü kullanın.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

## <a name="see-also"></a>Ayrıca bkz.

[_ATL_COM_MODULE](atl-typedefs.md#_atl_com_module)<br/>
[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
