---
title: Catldllmodület sınıfı
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
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/06/2020
ms.locfileid: "78863244"
---
# <a name="catldllmodulet-class"></a>Catldllmodület sınıfı

Bu sınıf, bir DLL 'in modülünü temsil eder.

## <a name="syntax"></a>Sözdizimi

```
template <class T>
class ATL_NO_VTABLE CAtlDllModuleT : public CAtlModuleT<T>
```

#### <a name="parameters"></a>Parametreler

*Şı*<br/>
Sınıfınız `CAtlDllModuleT`türetilir.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[Catldllmodület:: Catldllmodület](#catldllmodulet)|Oluşturucu.|
|[Catldllmodület:: ~ Catldllmodület](#dtor)|Yok edicisi.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[Catldllmodület::D llCanUnloadNow](#dllcanunloadnow)|DLL 'in kaldırılacaksa test eder.|
|[Catldllmodület::D llGetClassObject](#dllgetclassobject)|Bir sınıf üreteci döndürür.|
|[Catldllmodület::D llMain](#dllmain)|İsteğe bağlı giriş, bir dinamik bağlantı kitaplığı (DLL) içine işaret.|
|[Catldllmodület::D llRegisterServer](#dllregisterserver)|DLL içindeki nesneler için sistem kayıt defterine giriş ekler.|
|[Catldllmodület::D llUnregisterServer](#dllunregisterserver)|DLL içindeki nesneler için sistem kayıt defterindeki girişleri kaldırır.|
|[Catldllmodület:: GetClassObject](#getclassobject)|Bir sınıf üreteci döndürür. [DllGetClassObject](#dllgetclassobject)tarafından çağrılır.|

## <a name="remarks"></a>Açıklamalar

`CAtlDllModuleT`, bir dinamik bağlantı kitaplığı (DLL) modülünü temsil eder ve tüm DLL projeleri tarafından kullanılan işlevleri sağlar. [Catlmodület](../../atl/reference/catlmodulet-class.md) sınıfının bu özelleştirmesi kayıt desteğini içerir.

ATL 'deki modüller hakkında daha fazla bilgi için bkz. [ATL modül sınıfları](../../atl/atl-module-classes.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[_ATL_MODULE](atl-typedefs.md#_atl_module)

[CAtlModule](../../atl/reference/catlmodule-class.md)

[Catlmodület](../../atl/reference/catlmodulet-class.md)

`CAtlDllModuleT`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlbase. h

##  <a name="catldllmodulet"></a>Catldllmodület:: Catldllmodület

Oluşturucu.

```
CAtlDllModuleT() throw();
```

##  <a name="dtor"></a>Catldllmodület:: ~ Catldllmodület

Yok edicisi.

```
~CAtlDllModuleT() throw();
```

##  <a name="dllcanunloadnow"></a>Catldllmodület::D llCanUnloadNow

DLL 'in kaldırılacaksa test eder.

```
HRESULT DllCanUnloadNow() throw();
```

### <a name="return-value"></a>Dönüş Değeri

DLL bellekten kaldırılacaksa S_OK döndürür veya S_FALSE.

##  <a name="dllgetclassobject"></a>Catldllmodület::D llGetClassObject

Sınıf üreteci döndürür.

```
HRESULT DllGetClassObject(
    REFCLSID rclsid,
    REFIID riid,
    LPVOID* ppv) throw();
```

### <a name="parameters"></a>Parametreler

*rclsıd*<br/>
Oluşturulacak nesnenin CLSID değeri.

*riıd*<br/>
İstenen arabirimin IID 'si.

*PPV*<br/>
*Riıd*tarafından tanımlanan arabirim işaretçisine yönelik bir işaretçi. Nesne bu arabirimi desteklemiyorsa, *PPV* null olarak ayarlanır.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

##  <a name="dllmain"></a>Catldllmodület::D llMain

İsteğe bağlı giriş, bir dinamik bağlantı kitaplığı (DLL) içine işaret.

```
BOOL WINAPI DllMain(DWORD dwReason, LPVOID /* lpReserved*/) throw();
```

### <a name="parameters"></a>Parametreler

*dwReason*<br/>
DLL_PROCESS_ATTACH olarak ayarlanırsa, DLL_THREAD_ATTACH ve DLL_THREAD_DETACH bildirim çağrıları devre dışı bırakılır.

*lpReserved*<br/>
Ayrılamadı.

### <a name="return-value"></a>Dönüş Değeri

Her zaman TRUE döndürür.

### <a name="remarks"></a>Açıklamalar

DLL_THREAD_ATTACH ve DLL_THREAD_DETACH bildirim çağrılarını devre dışı bırakmak, çok sayıda dll içeren çok iş parçacıklı uygulamalar için faydalı bir iyileştirme olabilir. Bu, iş parçacığı oluşturma ve silme, dll 'Lerin ek/çıkarılabilir bu iş parçacığı düzeyi bildirimlerine ihtiyacı yoktur.

##  <a name="dllregisterserver"></a>Catldllmodület::D llRegisterServer

DLL içindeki nesneler için sistem kayıt defterine giriş ekler.

```
HRESULT DllRegisterServer(BOOL bRegTypeLib = TRUE) throw();
```

### <a name="parameters"></a>Parametreler

*bRegTypeLib*<br/>
Tür kitaplığının kaydı varsa TRUE. Varsayılan değer TRUE 'dur.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

##  <a name="dllunregisterserver"></a>Catldllmodület::D llUnregisterServer

DLL içindeki nesneler için sistem kayıt defterindeki girişleri kaldırır.

```
HRESULT DllUnregisterServer(BOOL bUnRegTypeLib = TRUE) throw();
```

### <a name="parameters"></a>Parametreler

*bUnRegTypeLib*<br/>
Tür kitaplığının kayıt defterinden kaldırılması durumunda TRUE. Varsayılan değer TRUE 'dur.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

##  <a name="getclassobject"></a>Catldllmodület:: GetClassObject

Belirtilen CLSID 'nin bir nesnesini oluşturur.

```
HRESULT GetClassObject(
    REFCLSID rclsid,
    REFIID riid,
    LPVOID* ppv) throw();
```

### <a name="parameters"></a>Parametreler

*rclsıd*<br/>
Oluşturulacak nesnenin CLSID değeri.

*riıd*<br/>
İstenen arabirimin IID 'si.

*PPV*<br/>
*Riıd*tarafından tanımlanan arabirim işaretçisine yönelik bir işaretçi. Nesne bu arabirimi desteklemiyorsa, *PPV* null olarak ayarlanır.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, [Catldllmodület::D llgetclassobject](#dllgetclassobject) tarafından çağrılır ve geriye dönük uyumluluk için eklenmiştir.

## <a name="see-also"></a>Ayrıca bkz.

[CAtlModuleT Sınıfı](../../atl/reference/catlmodulet-class.md)<br/>
[CAtlExeModuleT Sınıfı](../../atl/reference/catlexemodulet-class.md)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)<br/>
[Modül sınıfları](../../atl/atl-module-classes.md)
