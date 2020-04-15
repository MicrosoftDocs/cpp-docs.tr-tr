---
title: CAtlModuleT Sınıfı
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
ms.openlocfilehash: bf64c073249b7426fafb430a708573d9d06d11fd
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81321419"
---
# <a name="catlmodulet-class"></a>CAtlModuleT Sınıfı

Bu sınıf bir ATL modülü uygular.

## <a name="syntax"></a>Sözdizimi

```
template <class T>
class ATL_NO_VTABLE CAtlModuleT : public CAtlModule
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Sınıfınızdan `CAtlModuleT`türetilmiştir.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CAtlModuleT::CAtlModuleT](#catlmodulet)|Oluşturucu.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CAtlModuleT::InitLibId](#initlibid)|Geçerli modülün GUID'ini içeren veri üyesini başolarak karşılar.|
|[CAtlModuleT::RegisterAppId](#registerappid)|EXE'yi kayıt defterine ekler.|
|[CAtlModuleT::RegisterServer](#registerserver)|Hizmeti kayıt defterine ekler.|
|[CAtlModuleT::Kayıt DışıAppId](#unregisterappid)|EXE'yi kayıt defterinden kaldırır.|
|[CAtlModuleT::Kayıt DışıSunucu](#unregisterserver)|Hizmeti kayıt defterinden kaldırır.|
|[CAtlModuleT::UpdateRegistryAppId](#updateregistryappid)|Kayıt defterindeki EXE bilgilerini güncelleştirir.|

## <a name="remarks"></a>Açıklamalar

`CAtlModuleT`, [CAtlModule](../../atl/reference/catlmodule-class.md)türetilmiştir, bir Yürütülebilir (EXE) veya Hizmet (EXE) ATL modülü uygular. Yürütülebilir modül yerel, işlem dışı bir sunucudur, hizmet modülü ise Windows başlatıldığında arka planda çalışan bir Windows uygulamasıdır.

`CAtlModuleT`modülün başlatılması, kaydedilmesi ve kaydının silinmesi için destek sağlar.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[_ATL_MODULE](atl-typedefs.md#_atl_module)

[CAtlModülü](../../atl/reference/catlmodule-class.md)

`CAtlModuleT`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlbase.h

## <a name="catlmoduletcatlmodulet"></a><a name="catlmodulet"></a>CAtlModuleT::CAtlModuleT

Oluşturucu.

```
CAtlModuleT() throw();
```

### <a name="remarks"></a>Açıklamalar

[CAtlModuleT çağırır::InitLibId](#initlibid).

## <a name="catlmoduletinitlibid"></a><a name="initlibid"></a>CAtlModuleT::InitLibId

Geçerli modülün GUID'ini içeren veri üyesini başolarak karşılar.

```
static void InitLibId() throw();
```

### <a name="remarks"></a>Açıklamalar

Yapıcı [CAtlModuleT tarafından çağrılan::CAtlModuleT](#catlmodulet).

## <a name="catlmoduletregisterappid"></a><a name="registerappid"></a>CAtlModuleT::RegisterAppId

EXE'yi kayıt defterine ekler.

```
HRESULT RegisterAppId() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

## <a name="catlmoduletregisterserver"></a><a name="registerserver"></a>CAtlModuleT::RegisterServer

Hizmeti kayıt defterine ekler.

```
HRESULT RegisterServer(
    BOOL bRegTypeLib = FALSE,
    const CLSID* pCLSID = NULL) throw();
```

### <a name="parameters"></a>Parametreler

*bRegTypeLib*<br/>
Tür kitaplığı kaydedilecekse DOĞRU. Varsayılan değer FALSE'dur.

*pCLSID*<br/>
Kaydedilecek nesnenin CLSID'sine işaret edin. NULL (varsayılan değer) varsa, nesne eşlemindeki tüm nesneler kaydedilir.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

## <a name="catlmoduletunregisterappid"></a><a name="unregisterappid"></a>CAtlModuleT::Kayıt DışıAppId

EXE'yi kayıt defterinden kaldırır.

```
HRESULT UnregisterAppId() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

## <a name="catlmoduletunregisterserver"></a><a name="unregisterserver"></a>CAtlModuleT::Kayıt DışıSunucu

Hizmeti kayıt defterinden kaldırır.

```
HRESULT UnregisterServer(
    BOOL bUnRegTypeLib,
    const CLSID* pCLSID = NULL) throw();
```

### <a name="parameters"></a>Parametreler

*bUnRegTypeLib*<br/>
Tür kitaplığı da kayıt dışı olacaksa DOĞRU.

*pCLSID*<br/>
Nesnenin CLSID'sine kayıtsız kalmak için işaret. NULL (varsayılan değer) varsa, nesne eşlemindeki tüm nesneler kayıtsız kalır.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

## <a name="catlmoduletupdateregistryappid"></a><a name="updateregistryappid"></a>CAtlModuleT::UpdateRegistryAppId

Kayıt defterindeki EXE bilgilerini güncelleştirir.

```
static HRESULT WINAPI UpdateRegistryAppId(BOOL /* bRegister*/) throw();
```

### <a name="parameters"></a>Parametreler

*bKayıt*<br/>
Ayrılmış.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

## <a name="see-also"></a>Ayrıca bkz.

[CAtlModule Sınıfı](../../atl/reference/catlmodule-class.md)<br/>
[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)<br/>
[Modül Sınıfları](../../atl/atl-module-classes.md)
