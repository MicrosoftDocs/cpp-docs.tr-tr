---
title: CAtlModuleT sınıfı
ms.date: 11/04/2016
f1_keywords:
- CAtlModuleT
- ATLBASE/ATL::CAtlModuleT
- ATLBASE/ATL::CAtlModuleT::CAtlModuleT
- ATLBASE/ATL::CAtlModuleT::InitLibId
- ATLBASE/ATL::CAtlModuleT::RegisterAppId
- ATLBASE/ATL::CAtlModuleT::RegisterServer
- ATLBASE/ATL::CAtlModuleT::UnregisterAppId
- ATLBASE/ATL::CAtlModuleT::UnregisterServer
- ATLBASE/ATL::CAtlModuleT::UpdateRegistryAppId
helpviewer_keywords:
- CAtlModuleT class
ms.assetid: 9b74d02f-9117-47b1-a05e-c5945f83dd2b
ms.openlocfilehash: 2cd207038a92b944bf95575f0e0c820b8f09d615
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57272054"
---
# <a name="catlmodulet-class"></a>CAtlModuleT sınıfı

Bu sınıf bir ATL modül uygular.

## <a name="syntax"></a>Sözdizimi

```
template <class T>
class ATL_NO_VTABLE CAtlModuleT : public CAtlModule
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Sınıfınıza türetilen `CAtlModuleT`.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CAtlModuleT::CAtlModuleT](#catlmodulet)|Oluşturucu.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CAtlModuleT::InitLibId](#initlibid)|Geçerli modül GUID'i içeren veri üyesi başlatır.|
|[CAtlModuleT::RegisterAppId](#registerappid)|EXE kayıt defterine ekler.|
|[CAtlModuleT::RegisterServer](#registerserver)|Hizmet kayıt defterine ekler.|
|[CAtlModuleT::UnregisterAppId](#unregisterappid)|EXE kayıt defterinden kaldırır.|
|[CAtlModuleT::UnregisterServer](#unregisterserver)|Hizmet kayıt defterinden kaldırır.|
|[CAtlModuleT::UpdateRegistryAppId](#updateregistryappid)|Kayıt defterinde EXE bilgilerini güncelleştirir.|

## <a name="remarks"></a>Açıklamalar

`CAtlModuleT`, öğesinden türetilen [CAtlModule](../../atl/reference/catlmodule-class.md), bir yürütülebilir (EXE) ya da hizmet (EXE) ATL modülüne uygular. Windows başladığında arka planda çalışan bir Windows uygulaması hizmeti modülü iken bir çalıştırılabilir modüle bir yerel, işlem dışı sunucusudur.

`CAtlModuleT` başlatma, kaydetme ve modülün kaydını kaldırmak için destek sağlar.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[_ATL_MODULE](atl-typedefs.md#_atl_module)

[CAtlModule](../../atl/reference/catlmodule-class.md)

`CAtlModuleT`

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlbase.h

##  <a name="catlmodulet"></a>  CAtlModuleT::CAtlModuleT

Oluşturucu.

```
CAtlModuleT() throw();
```

### <a name="remarks"></a>Açıklamalar

Çağrıları [CAtlModuleT::InitLibId](#initlibid).

##  <a name="initlibid"></a>  CAtlModuleT::InitLibId

Geçerli modül GUID'i içeren veri üyesi başlatır.

```
static void InitLibId() throw();
```

### <a name="remarks"></a>Açıklamalar

Oluşturucu tarafından adlandırılan [CAtlModuleT::CAtlModuleT](#catlmodulet).

##  <a name="registerappid"></a>  CAtlModuleT::RegisterAppId

EXE kayıt defterine ekler.

```
HRESULT RegisterAppId() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

##  <a name="registerserver"></a>  CAtlModuleT::RegisterServer

Hizmet kayıt defterine ekler.

```
HRESULT RegisterServer(
    BOOL bRegTypeLib = FALSE,
    const CLSID* pCLSID = NULL) throw();
```

### <a name="parameters"></a>Parametreler

*bRegTypeLib*<br/>
Tür kitaplığı kayıtlı olması ise TRUE. Varsayılan değer FALSE olur.

*pCLSID*<br/>
CLSID işaret kaydedilecek nesne. NULL (varsayılan değer), nesne eşlemesindeki tüm nesneleri kayıtlı değilse.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

##  <a name="unregisterappid"></a>  CAtlModuleT::UnregisterAppId

EXE kayıt defterinden kaldırır.

```
HRESULT UnregisterAppId() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

##  <a name="unregisterserver"></a>  CAtlModuleT::UnregisterServer

Hizmet kayıt defterinden kaldırır.

```
HRESULT UnregisterServer(
    BOOL bUnRegTypeLib,
    const CLSID* pCLSID = NULL) throw();
```

### <a name="parameters"></a>Parametreler

*bUnRegTypeLib*<br/>
Tür kitaplığı da silinmesine izin ise TRUE.

*pCLSID*<br/>
CLSID işaret silinmesine izin nesnesi. NULL (varsayılan değer), nesne eşlemesindeki tüm nesneleri kaydı silinecek durumunda.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

##  <a name="updateregistryappid"></a>  CAtlModuleT::UpdateRegistryAppId

Kayıt defterinde EXE bilgilerini güncelleştirir.

```
static HRESULT WINAPI UpdateRegistryAppId(BOOL /* bRegister*/) throw();
```

### <a name="parameters"></a>Parametreler

*bRegister*<br/>
Ayrılmış.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

## <a name="see-also"></a>Ayrıca bkz.

[CAtlModule Sınıfı](../../atl/reference/catlmodule-class.md)<br/>
[Sınıfına genel bakış](../../atl/atl-class-overview.md)<br/>
[Modül sınıfları](../../atl/atl-module-classes.md)
