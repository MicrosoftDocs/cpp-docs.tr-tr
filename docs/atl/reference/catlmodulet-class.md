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
ms.openlocfilehash: b07e60265570e66337a2d13007e9ad57c6f369e4
ms.sourcegitcommit: 2bc15c5b36372ab01fa21e9bcf718fa22705814f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/27/2020
ms.locfileid: "82167870"
---
# <a name="catlmodulet-class"></a>CAtlModuleT Sınıfı

Bu sınıf, ATL modülünü uygular.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class T>
class ATL_NO_VTABLE CAtlModuleT : public CAtlModule
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Sınıfınız öğesinden `CAtlModuleT`türetilir.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[Catlmodület:: Catlmodület](#catlmodulet)|Oluşturucu.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[Catlmodület:: InitLibId](#initlibid)|Geçerli modülün GUID 'sini içeren veri üyesini başlatır.|
|[Catlmodület:: Registerappıd](#registerappid)|EXE 'yi kayıt defterine ekler.|
|[Catlmodület:: RegisterServer](#registerserver)|Hizmeti kayıt defterine ekler.|
|[Catlmodület:: Unregisterappıd](#unregisterappid)|EXE 'yi kayıt defterinden kaldırır.|
|[Catlmodület:: UnregisterServer](#unregisterserver)|Hizmeti kayıt defterinden kaldırır.|
|[Catlmodület:: Updateregıstryappid](#updateregistryappid)|Kayıt defterindeki EXE bilgilerini güncelleştirir.|

## <a name="remarks"></a>Açıklamalar

`CAtlModuleT`, [CAtlModule](../../atl/reference/catlmodule-class.md)'ten türetilmiş bir ÇALıŞTıRıLABILIR (exe) veya HIZMET (exe) atl modülü uygular. Yürütülebilir bir modül, yerel, işlem dışı bir sunucusudur, ancak hizmet modülü Windows başladığında arka planda çalışan bir Windows uygulamasıdır.

`CAtlModuleT`modülün başlatılması, kaydedilmesi ve kaydının kaydı için destek sağlar.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[_ATL_MODULE](atl-typedefs.md#_atl_module)

[CAtlModule](../../atl/reference/catlmodule-class.md)

`CAtlModuleT`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlbase. h

## <a name="catlmoduletcatlmodulet"></a><a name="catlmodulet"></a>Catlmodület:: Catlmodület

Oluşturucu.

```cpp
CAtlModuleT() throw();
```

### <a name="remarks"></a>Açıklamalar

[Catlmodület:: InitLibId](#initlibid)çağırır.

## <a name="catlmoduletinitlibid"></a><a name="initlibid"></a>Catlmodület:: InitLibId

Geçerli modülün GUID 'sini içeren veri üyesini başlatır.

```cpp
static void InitLibId() throw();
```

### <a name="remarks"></a>Açıklamalar

[Catlmodület:: catlmodület](#catlmodulet)Oluşturucusu tarafından çağırılır.

## <a name="catlmoduletregisterappid"></a><a name="registerappid"></a>Catlmodület:: Registerappıd

EXE 'yi kayıt defterine ekler.

```cpp
HRESULT RegisterAppId() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

## <a name="catlmoduletregisterserver"></a><a name="registerserver"></a>Catlmodület:: RegisterServer

Hizmeti kayıt defterine ekler.

```cpp
HRESULT RegisterServer(
    BOOL bRegTypeLib = FALSE,
    const CLSID* pCLSID = NULL) throw();
```

### <a name="parameters"></a>Parametreler

*bRegTypeLib*<br/>
Tür kitaplığının kaydı varsa TRUE. Varsayılan değer FALSE 'dur.

*pCLSID*<br/>
Kaydedilecek nesnenin CLSID değerini gösterir. NULL ise (varsayılan değer), nesne haritadaki tüm nesneler kaydedilir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

## <a name="catlmoduletunregisterappid"></a><a name="unregisterappid"></a>Catlmodület:: Unregisterappıd

EXE 'yi kayıt defterinden kaldırır.

```cpp
HRESULT UnregisterAppId() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

## <a name="catlmoduletunregisterserver"></a><a name="unregisterserver"></a>Catlmodület:: UnregisterServer

Hizmeti kayıt defterinden kaldırır.

```cpp
HRESULT UnregisterServer(
    BOOL bUnRegTypeLib,
    const CLSID* pCLSID = NULL) throw();
```

### <a name="parameters"></a>Parametreler

*bUnRegTypeLib*<br/>
Tür kitaplığının de kaydı kaldırılacak ise TRUE.

*pCLSID*<br/>
Kaydı kaldırılacak nesnenin CLSID değerini gösterir. NULL ise (varsayılan değer), nesne eşlemesindeki tüm nesnelerin kaydı silinir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

## <a name="catlmoduletupdateregistryappid"></a><a name="updateregistryappid"></a>Catlmodület:: Updateregıstryappid

Kayıt defterindeki EXE bilgilerini güncelleştirir.

```cpp
static HRESULT WINAPI UpdateRegistryAppId(BOOL /* bRegister*/) throw();
```

### <a name="parameters"></a>Parametreler

*bRegister*<br/>
Ayrılmış.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

## <a name="see-also"></a>Ayrıca bkz.

[CAtlModule Sınıfı](../../atl/reference/catlmodule-class.md)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)<br/>
[Modül sınıfları](../../atl/atl-module-classes.md)
