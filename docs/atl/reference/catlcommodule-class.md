---
title: CAtlComModule sınıfı
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
ms.openlocfilehash: 09adcb33ca9e6f8524063130d6aedca044d6ecb5
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/16/2020
ms.locfileid: "79418085"
---
# <a name="catlcommodule-class"></a>CAtlComModule sınıfı

Bu sınıf bir COM sunucu modülünü uygular.

## <a name="syntax"></a>Sözdizimi

```
class CAtlComModule : public _ATL_COM_MODULE
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Genel Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CAtlComModule:: CAtlComModule](#catlcommodule)|Oluşturucu.|
|[CAtlComModule:: ~ CAtlComModule](#dtor)|Yok edicisi.|

### <a name="public-methods"></a>Genel Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CAtlComModule:: RegisterServer](#registerserver)|Nesne eşlemesindeki her bir nesne için sistem kayıt defterini güncelleştirmek için bu yöntemi çağırın.|
|[CAtlComModule:: RegisterTypeLib](#registertypelib)|Bir tür kitaplığını kaydetmek için bu yöntemi çağırın.|
|[CAtlComModule:: UnregisterServer](#unregisterserver)|Nesne eşlemesindeki her nesnenin kaydını silmek için bu yöntemi çağırın.|
|[CAtlComModule:: UnRegisterTypeLib](#unregistertypelib)|Bir tür kitaplığının kaydını silmek için bu yöntemi çağırın.|

## <a name="remarks"></a>Açıklamalar

`CAtlComModule` bir COM sunucu modülünü uygular ve istemcinin modülün bileşenlerine erişmesine izin verir.

Bu sınıf, ATL 'nin önceki sürümlerinde kullanılan eski [CComModule](../../atl/reference/ccommodule-class.md) sınıfının yerini alır. Daha fazla ayrıntı için bkz. [ATL modül sınıfları](../../atl/atl-module-classes.md) .

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[_ATL_COM_MODULE](atl-typedefs.md#_atl_com_module)

`CAtlComModule`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlbase. h

##  <a name="catlcommodule"></a>CAtlComModule:: CAtlComModule

Oluşturucu.

```
CAtlComModule() throw();
```

### <a name="remarks"></a>Açıklamalar

Modülünü başlatır.

##  <a name="dtor"></a>CAtlComModule:: ~ CAtlComModule

Yok edicisi.

```
~CAtlComModule();
```

### <a name="remarks"></a>Açıklamalar

Tüm sınıf fabrikalarını serbest bırakır.

##  <a name="registerserver"></a>CAtlComModule:: RegisterServer

Nesne eşlemesindeki her bir nesne için sistem kayıt defterini güncelleştirmek için bu yöntemi çağırın.

```
HRESULT RegisterServer(BOOL bRegTypeLib = FALSE, const CLSID* pCLSID = NULL);
```

### <a name="parameters"></a>Parametreler

*bRegTypeLib*<br/>
Tür kitaplığının kaydı varsa TRUE. Varsayılan değer FALSE 'dur.

*pCLSID*<br/>
Kaydedilecek nesnenin CLSID değerini gösterir. NULL ise (varsayılan değer), nesne haritadaki tüm nesneler kaydedilir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

### <a name="remarks"></a>Açıklamalar

[AtlComModuleRegisterServer](server-registration-global-functions.md#atlcommoduleregisterserver)genel işlevini çağırır.

##  <a name="registertypelib"></a>CAtlComModule:: RegisterTypeLib

Bir tür kitaplığını kaydetmek için bu yöntemi çağırın.

```
HRESULT RegisterTypeLib(LPCTSTR lpszIndex);
HRESULT RegisterTypeLib();
```

### <a name="parameters"></a>Parametreler

*lpszIndex*<br/>
"\\\n" biçiminde dize, burada N, TYPELIB kaynağının tamsayı dizinidir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

### <a name="remarks"></a>Açıklamalar

Bir tür kitaplığı hakkında bilgileri sistem kayıt defterine ekler. Modül örneği birden çok tür kitaplığı içeriyorsa, hangi tür kitaplığının kullanılması gerektiğini belirtmek için bu yöntemin ilk sürümünü kullanın.

##  <a name="unregisterserver"></a>CAtlComModule:: UnregisterServer

Nesne eşlemesindeki her nesnenin kaydını silmek için bu yöntemi çağırın.

```
HRESULT UnregisterServer(
    BOOL bRegTypeLib = FALSE,
    const CLSID* pCLSID = NULL);
```

### <a name="parameters"></a>Parametreler

*bRegTypeLib*<br/>
Tür kitaplığının kaydı kaldırılacak ise TRUE. Varsayılan değer FALSE 'dur.

*pCLSID*<br/>
Kaydı kaldırılacak nesnenin CLSID değerini gösterir. NULL ise (varsayılan değer), nesne eşlemesindeki tüm nesnelerin kaydı silinir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

### <a name="remarks"></a>Açıklamalar

[AtlComModuleUnregisterServer](server-registration-global-functions.md#atlcommoduleunregisterserver)genel işlevini çağırır.

##  <a name="unregistertypelib"></a>CAtlComModule:: UnRegisterTypeLib

Bir tür kitaplığının kaydını silmek için bu yöntemi çağırın.

```
HRESULT UnRegisterTypeLib(LPCTSTR lpszIndex);
HRESULT UnRegisterTypeLib();
```

### <a name="parameters"></a>Parametreler

*lpszIndex*<br/>
"\\\n" biçiminde dize, burada N, TYPELIB kaynağının tamsayı dizinidir.

### <a name="remarks"></a>Açıklamalar

Bir tür kitaplığı hakkındaki bilgileri sistem kayıt defterinden kaldırır. Modül örneği birden çok tür kitaplığı içeriyorsa, hangi tür kitaplığının kullanılması gerektiğini belirtmek için bu yöntemin ilk sürümünü kullanın.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

## <a name="see-also"></a>Ayrıca bkz.

[_ATL_COM_MODULE](atl-typedefs.md#_atl_com_module)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)
