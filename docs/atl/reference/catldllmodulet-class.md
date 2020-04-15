---
title: CAtlDllModuleT Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CAtlDllModuleT
- ATLBASE/ATL::CAtlDllModuleT
- ATLBASE/ATL::CAtlDllModuleT::CAtlDllModuleT
- ATLBASE/ATL::CAtlDllModuleT::DllCanUnloadNow
- ATLBASE/ATL::CAtlDllModuleT::DllGetClassObject
- ATLBASE/ATL::CAtlDllModuleT::DllMain
- ATLBASE/ATL::CAtlDllModuleT::DllRegisterServer
- ATLBASE/ATL::CAtlDllModuleT::DllUnregisterServer
- ATLBASE/ATL::CAtlDllModuleT::GetClassObject
helpviewer_keywords:
- CAtlDllModuleT class
ms.assetid: 351d5767-8257-4878-94be-45a85e31a72d
ms.openlocfilehash: 7a5f8e7e489c8e0d573569ac7c4a8fb63f652732
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81319008"
---
# <a name="catldllmodulet-class"></a>CAtlDllModuleT Sınıfı

Bu sınıf bir DLL için modülü temsil eder.

## <a name="syntax"></a>Sözdizimi

```
template <class T>
class ATL_NO_VTABLE CAtlDllModuleT : public CAtlModuleT<T>
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Sınıfınızdan `CAtlDllModuleT`türetilmiştir.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CAtlDllModuleT::CAtlDllModuleT](#catldllmodulet)|Oluşturucu.|
|[CAtlDllModuleT::~CAtlDllModuleT](#dtor)|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CAtlDllModuleT::DllCanUnloadNow](#dllcanunloadnow)|DLL'nin boşaltılap yüklenilemeyebileceğini sınayın.|
|[CAtlDllModuleT::DllGetClassObject](#dllgetclassobject)|Sınıf fabrikasını döndürür.|
|[CAtlDllModuleT::DllMain](#dllmain)|Dinamik bağlantı kitaplığına (DLL) isteğe bağlı giriş noktası.|
|[CAtlDllModuleT::DllRegisterServer](#dllregisterserver)|DLL'deki nesneler için sistem kayıt defterine girişler ekler.|
|[CAtlDllModuleT::DllUnregisterServer](#dllunregisterserver)|DLL'deki nesneler için sistem kayıt defterindeki girişleri kaldırır.|
|[CAtlDllModuleT::GetClassObject](#getclassobject)|Sınıf fabrikasını döndürür. [DllGetClassObject](#dllgetclassobject)tarafından çağrılan.|

## <a name="remarks"></a>Açıklamalar

`CAtlDllModuleT`dinamik bağlantı kitaplığı (DLL) modüllerini temsil eder ve tüm DLL projeleri tarafından kullanılan işlevleri sağlar. [CAtlModuleT](../../atl/reference/catlmodulet-class.md) sınıfının bu uzmanlığı kayıt için destek içerir.

ATL'deki modüller hakkında daha fazla bilgi için [ATL Modül Sınıfları'na](../../atl/atl-module-classes.md)bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[_ATL_MODULE](atl-typedefs.md#_atl_module)

[CAtlModülü](../../atl/reference/catlmodule-class.md)

[CAtlModuleT](../../atl/reference/catlmodulet-class.md)

`CAtlDllModuleT`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlbase.h

## <a name="catldllmoduletcatldllmodulet"></a><a name="catldllmodulet"></a>CAtlDllModuleT::CAtlDllModuleT

Oluşturucu.

```
CAtlDllModuleT() throw();
```

## <a name="catldllmoduletcatldllmodulet"></a><a name="dtor"></a>CAtlDllModuleT::~CAtlDllModuleT

Yıkıcı.

```
~CAtlDllModuleT() throw();
```

## <a name="catldllmoduletdllcanunloadnow"></a><a name="dllcanunloadnow"></a>CAtlDllModuleT::DllCanUnloadNow

DLL'nin boşaltılap yüklenilemeyebileceğini sınayın.

```
HRESULT DllCanUnloadNow() throw();
```

### <a name="return-value"></a>Dönüş Değeri

DLL boşaltılabilirse S_OK veya S_FALSE verir.

## <a name="catldllmoduletdllgetclassobject"></a><a name="dllgetclassobject"></a>CAtlDllModuleT::DllGetClassObject

Sınıf fabrikasını döndürür.

```
HRESULT DllGetClassObject(
    REFCLSID rclsid,
    REFIID riid,
    LPVOID* ppv) throw();
```

### <a name="parameters"></a>Parametreler

*rclsid*<br/>
Oluşturulacak nesnenin CLSID'si.

*Riid*<br/>
İstenen arabirimin IID'si.

*Ppv*<br/>
*riid*tarafından tanımlanan arabirim işaretçisine işaretçi. Nesne bu arabirimi desteklemiyorsa, *PPV* NULL olarak ayarlanır.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

## <a name="catldllmoduletdllmain"></a><a name="dllmain"></a>CAtlDllModuleT::DllMain

Dinamik bağlantı kitaplığına (DLL) isteğe bağlı giriş noktası.

```
BOOL WINAPI DllMain(DWORD dwReason, LPVOID /* lpReserved*/) throw();
```

### <a name="parameters"></a>Parametreler

*dwReason*<br/>
DLL_PROCESS_ATTACH olarak ayarlanmışsa, DLL_THREAD_ATTACH ve DLL_THREAD_DETACH bildirim çağrıları devre dışı bırakılır.

*lpReserved*<br/>
Ayrılmış.

### <a name="return-value"></a>Dönüş Değeri

Her zaman TRUE döndürür.

### <a name="remarks"></a>Açıklamalar

DLL_THREAD_ATTACH ve DLL_THREAD_DETACH bildirim çağrılarını devre dışı bırakmak, sık sık iş parçacığı oluşturan ve silen ve DL'leri bu ek/ayırma bildirimlerine ihtiyaç duymayan çok iş parçacığı uygulamaları için yararlı bir optimizasyon olabilir.

## <a name="catldllmoduletdllregisterserver"></a><a name="dllregisterserver"></a>CAtlDllModuleT::DllRegisterServer

DLL'deki nesneler için sistem kayıt defterine girişler ekler.

```
HRESULT DllRegisterServer(BOOL bRegTypeLib = TRUE) throw();
```

### <a name="parameters"></a>Parametreler

*bRegTypeLib*<br/>
Tür kitaplığı kaydedilecekse DOĞRU. Varsayılan değer TRUE'dur.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

## <a name="catldllmoduletdllunregisterserver"></a><a name="dllunregisterserver"></a>CAtlDllModuleT::DllUnregisterServer

DLL'deki nesneler için sistem kayıt defterindeki girişleri kaldırır.

```
HRESULT DllUnregisterServer(BOOL bUnRegTypeLib = TRUE) throw();
```

### <a name="parameters"></a>Parametreler

*bUnRegTypeLib*<br/>
Tür kitaplığı kayıt defterinden kaldırılacaksa DOĞRU. Varsayılan değer TRUE'dur.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

## <a name="catldllmoduletgetclassobject"></a><a name="getclassobject"></a>CAtlDllModuleT::GetClassObject

Belirtilen CLSID bir nesne oluşturur.

```
HRESULT GetClassObject(
    REFCLSID rclsid,
    REFIID riid,
    LPVOID* ppv) throw();
```

### <a name="parameters"></a>Parametreler

*rclsid*<br/>
Oluşturulacak nesnenin CLSID'si.

*Riid*<br/>
İstenen arabirimin IID'si.

*Ppv*<br/>
*riid*tarafından tanımlanan arabirim işaretçisine işaretçi. Nesne bu arabirimi desteklemiyorsa, *PPV* NULL olarak ayarlanır.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

### <a name="remarks"></a>Açıklamalar

Bu yöntem [CAtlDllModuleT::DllGetClassObject](#dllgetclassobject) tarafından adlandırılır ve geriye dönük uyumluluk için dahildir.

## <a name="see-also"></a>Ayrıca bkz.

[CAtlModuleT Sınıfı](../../atl/reference/catlmodulet-class.md)<br/>
[CAtlExeModuleT Sınıfı](../../atl/reference/catlexemodulet-class.md)<br/>
[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)<br/>
[Modül Sınıfları](../../atl/atl-module-classes.md)
