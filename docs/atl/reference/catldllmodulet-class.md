---
title: CAtlDllModuleT sınıfı
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
ms.openlocfilehash: be42915c6c2e941bc5fc1de78c5c7ac26ccca6e2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62247106"
---
# <a name="catldllmodulet-class"></a>CAtlDllModuleT sınıfı

Bu sınıf, bir DLL için modül temsil eder.

## <a name="syntax"></a>Sözdizimi

```
template <class T>
class ATL_NO_VTABLE CAtlDllModuleT : public CAtlModuleT<T>
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Sınıfınıza türetilen `CAtlDllModuleT`.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CAtlDllModuleT::CAtlDllModuleT](#catldllmodulet)|Oluşturucu.|
|[CAtlDllModuleT:: ~ CAtlDllModuleT](#dtor)|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CAtlDllModuleT::DllCanUnloadNow](#dllcanunloadnow)|DLL kaldırılabilip kaldırılamayacağını olmadığını sınar.|
|[CAtlDllModuleT::DllGetClassObject](#dllgetclassobject)|Bir sınıf üreteci döndürür.|
|[CAtlDllModuleT::DllMain](#dllmain)|Bir dinamik bağlantı kitaplığı (DLL) halinde isteğe bağlı bir giriş noktası.|
|[CAtlDllModuleT::DllRegisterServer](#dllregisterserver)|DLL içindeki nesneler için sistem kayıt defteri girdileri ekler.|
|[CAtlDllModuleT::DllUnregisterServer](#dllunregisterserver)|DLL içindeki nesneler için sistem kayıt defteri girdileri kaldırır.|
|[CAtlDllModuleT::GetClassObject](#getclassobject)|Bir sınıf üreteci döndürür. Tarafından çağrılan [DllGetClassObject](#dllgetclassobject).|

## <a name="remarks"></a>Açıklamalar

`CAtlDllModuleT` Modülü dinamik bağlantı kitaplığı (DLL) temsil eder ve tüm DLL projesi tarafından kullanılan işlevler sağlar. Bu alt uzmanlaşması [CAtlModuleT](../../atl/reference/catlmodulet-class.md) sınıfı kayıt için destek içerir.

ATL modüller hakkında daha fazla bilgi için bkz. [ATL modül sınıfları](../../atl/atl-module-classes.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[_ATL_MODULE](atl-typedefs.md#_atl_module)

[CAtlModule](../../atl/reference/catlmodule-class.md)

[CAtlModuleT](../../atl/reference/catlmodulet-class.md)

`CAtlDllModuleT`

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlbase.h

##  <a name="catldllmodulet"></a>  CAtlDllModuleT::CAtlDllModuleT

Oluşturucu.

```
CAtlDllModuleT() throw();
```

##  <a name="dtor"></a>  CAtlDllModuleT:: ~ CAtlDllModuleT

Yıkıcı.

```
~CAtlDllModuleT() throw();
```

##  <a name="dllcanunloadnow"></a>  CAtlDllModuleT::DllCanUnloadNow

DLL kaldırılabilip kaldırılamayacağını olmadığını sınar.

```
HRESULT DllCanUnloadNow() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Erişilemiyorsa, DLL kaldırılabilip kaldırılamayacağını S_OK veya S_FALSE döndürür.

##  <a name="dllgetclassobject"></a>  CAtlDllModuleT::DllGetClassObject

Sınıf üreteci döndürür.

```
HRESULT DllGetClassObject(
    REFCLSID rclsid,
    REFIID riid,
    LPVOID* ppv) throw();
```

### <a name="parameters"></a>Parametreler

*rclsid*<br/>
Oluşturulacak nesnenin CLSID.

*riid*<br/>
İstenen arabirim Laboratuvardaki.

*ppv*<br/>
Tarafından tanımlanan bir arabirim işaretçisi için bir işaretçi *riid*. Nesne bu arabirimi desteklemiyorsa *ppv* NULL olarak ayarlandı.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

##  <a name="dllmain"></a>  CAtlDllModuleT::DllMain

Bir dinamik bağlantı kitaplığı (DLL) halinde isteğe bağlı bir giriş noktası.

```
BOOL WINAPI DllMain(DWORD dwReason, LPVOID /* lpReserved*/) throw();
```

### <a name="parameters"></a>Parametreler

*dwReason*<br/>
DLL_PROCESS_ATTACH DllMain ve DLL_THREAD_ATTACH bildirim çağrıları kümesine devre dışı ise.

*lpReserved*<br/>
Ayrılmış.

### <a name="return-value"></a>Dönüş Değeri

Her zaman TRUE değerini döndürür.

### <a name="remarks"></a>Açıklamalar

DllMain devre dışı bırakma ve DLL_THREAD_ATTACH bildirim çağrıları birçok DLL'leri sahip birden çok iş parçacıklı uygulamalar için kullanışlı bir iyileştirme olabilir, sık oluşturun ve iş parçacıkları silin ve, dll, bu iş parçacığı düzeyinde bildirimleri gerekmez Ek/ayrılmayı.

##  <a name="dllregisterserver"></a>  CAtlDllModuleT::DllRegisterServer

DLL içindeki nesneler için sistem kayıt defteri girdileri ekler.

```
HRESULT DllRegisterServer(BOOL bRegTypeLib = TRUE) throw();
```

### <a name="parameters"></a>Parametreler

*bRegTypeLib*<br/>
Tür kitaplığı kayıtlı olması ise TRUE. Varsayılan değer True'dur.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

##  <a name="dllunregisterserver"></a>  CAtlDllModuleT::DllUnregisterServer

DLL içindeki nesneler için sistem kayıt defteri girdileri kaldırır.

```
HRESULT DllUnregisterServer(BOOL bUnRegTypeLib = TRUE) throw();
```

### <a name="parameters"></a>Parametreler

*bUnRegTypeLib*<br/>
Tür kitaplığı defterinden kaldırılacak ise TRUE. Varsayılan değer True'dur.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

##  <a name="getclassobject"></a>  CAtlDllModuleT::GetClassObject

Belirtilen CLSID'yi bir nesne oluşturur.

```
HRESULT GetClassObject(
    REFCLSID rclsid,
    REFIID riid,
    LPVOID* ppv) throw();
```

### <a name="parameters"></a>Parametreler

*rclsid*<br/>
Oluşturulacak nesnenin CLSID.

*riid*<br/>
İstenen arabirim Laboratuvardaki.

*ppv*<br/>
Tarafından tanımlanan bir arabirim işaretçisi için bir işaretçi *riid*. Nesne bu arabirimi desteklemiyorsa *ppv* NULL olarak ayarlandı.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

### <a name="remarks"></a>Açıklamalar

Bu yöntemi çağıran [CAtlDllModuleT::DllGetClassObject](#dllgetclassobject) ve geriye dönük uyumluluk için dahildir.

## <a name="see-also"></a>Ayrıca bkz.

[CAtlModuleT Sınıfı](../../atl/reference/catlmodulet-class.md)<br/>
[CAtlExeModuleT Sınıfı](../../atl/reference/catlexemodulet-class.md)<br/>
[Sınıfına genel bakış](../../atl/atl-class-overview.md)<br/>
[Modül sınıfları](../../atl/atl-module-classes.md)
