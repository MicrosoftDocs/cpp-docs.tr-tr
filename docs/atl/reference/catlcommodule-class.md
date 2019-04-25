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
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62247197"
---
# <a name="catlcommodule-class"></a>CAtlComModule sınıfı

Bu sınıf, bir COM sunucusu modülü uygular.

## <a name="syntax"></a>Sözdizimi

```
class CAtlComModule : public _ATL_COM_MODULE
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CAtlComModule::CAtlComModule](#catlcommodule)|Oluşturucu.|
|[CAtlComModule:: ~ CAtlComModule](#dtor)|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CAtlComModule::RegisterServer](#registerserver)|Nesne eşlemesindeki her nesnenin sistem kayıt defterini güncelleştirmek için bu yöntemi çağırın.|
|[CAtlComModule::RegisterTypeLib](#registertypelib)|Tür kitaplığını kaydetmek için bu yöntemi çağırın.|
|[CAtlComModule::UnregisterServer](#unregisterserver)|Nesne eşlemesindeki her nesnenin kaydını silmek için bu yöntemi çağırın.|
|[CAtlComModule::UnRegisterTypeLib](#unregistertypelib)|Bir tür kitaplığının kaydını silmek için bu yöntemi çağırın.|

## <a name="remarks"></a>Açıklamalar

`CAtlComModule` Modülün bileşenlerine erişmek bir istemci sağlayan bir COM sunucusu modülü uygular.

Bu sınıf artık kullanılmıyor değiştirir [CComModule](../../atl/reference/ccommodule-class.md) ATL'ın önceki sürümlerinde kullanılan sınıf Bkz: [ATL modül sınıfları](../../atl/atl-module-classes.md) daha fazla ayrıntı için.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[_ATL_COM_MODULE](atl-typedefs.md#_atl_com_module)

`CAtlComModule`

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlbase.h

##  <a name="catlcommodule"></a>  CAtlComModule::CAtlComModule

Oluşturucu.

```
CAtlComModule() throw();
```

### <a name="remarks"></a>Açıklamalar

Modül başlatır.

##  <a name="dtor"></a>  CAtlComModule:: ~ CAtlComModule

Yıkıcı.

```
~CAtlComModule();
```

### <a name="remarks"></a>Açıklamalar

Tüm sınıf üreteçlerini serbest bırakır.

##  <a name="registerserver"></a>  CAtlComModule::RegisterServer

Nesne eşlemesindeki her nesnenin sistem kayıt defterini güncelleştirmek için bu yöntemi çağırın.

```
HRESULT RegisterServer(BOOL bRegTypeLib = FALSE, const CLSID* pCLSID = NULL);
```

### <a name="parameters"></a>Parametreler

*bRegTypeLib*<br/>
Tür kitaplığı kayıtlı olması ise TRUE. Varsayılan değer FALSE olur.

*pCLSID*<br/>
CLSID işaret kaydedilecek nesne. NULL (varsayılan değer), nesne eşlemesindeki tüm nesneleri kayıtlı değilse.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

### <a name="remarks"></a>Açıklamalar

Genel işlev çağrıları [AtlComModuleRegisterServer](server-registration-global-functions.md#atlcommoduleregisterserver).

##  <a name="registertypelib"></a>  CAtlComModule::RegisterTypeLib

Tür kitaplığını kaydetmek için bu yöntemi çağırın.

```
HRESULT RegisterTypeLib(LPCTSTR lpszIndex);
HRESULT RegisterTypeLib();
```

### <a name="parameters"></a>Parametreler

*lpszIndex*<br/>
Biçim dizesinde "\\\N", burada N tamsayı TYPELIB kaynak dizinidir.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

### <a name="remarks"></a>Açıklamalar

Bir tür kitaplığı hakkında bilgi için sistem kayıt defterine ekler. Modül örneğinin birden fazla tür kitaplığı içeriyorsa, hangi tür kitaplığı kullanılması gerektiğini belirtmek için bu yöntem ilk sürümünü kullanın.

##  <a name="unregisterserver"></a>  CAtlComModule::UnregisterServer

Nesne eşlemesindeki her nesnenin kaydını silmek için bu yöntemi çağırın.

```
HRESULT UnregisterServer(
    BOOL bRegTypeLib = FALSE,
    const CLSID* pCLSID = NULL);
```

### <a name="parameters"></a>Parametreler

*bRegTypeLib*<br/>
Tür kitaplığı kaydı olması gerekiyorsa TRUE. Varsayılan değer FALSE olur.

*pCLSID*<br/>
CLSID işaret silinmesine izin nesnesi. NULL (varsayılan değer), nesne eşlemesindeki tüm nesneleri kaydı silinecek durumunda.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

### <a name="remarks"></a>Açıklamalar

Genel işlev çağrıları [AtlComModuleUnregisterServer](server-registration-global-functions.md#atlcommoduleunregisterserver).

##  <a name="unregistertypelib"></a>  CAtlComModule::UnRegisterTypeLib

Bir tür kitaplığının kaydını silmek için bu yöntemi çağırın.

```
HRESULT UnRegisterTypeLib(LPCTSTR lpszIndex);
HRESULT UnRegisterTypeLib();
```

### <a name="parameters"></a>Parametreler

*lpszIndex*<br/>
Biçim dizesinde "\\\N", burada N tamsayı TYPELIB kaynak dizinidir.

### <a name="remarks"></a>Açıklamalar

Bir tür kitaplığı hakkında bilgi için sistem kayıt defterinden kaldırır. Modül örneğinin birden fazla tür kitaplığı içeriyorsa, hangi tür kitaplığı kullanılması gerektiğini belirtmek için bu yöntem ilk sürümünü kullanın.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

## <a name="see-also"></a>Ayrıca bkz.

[_ATL_COM_MODULE](atl-typedefs.md#_atl_com_module)<br/>
[Sınıfına genel bakış](../../atl/atl-class-overview.md)
