---
description: 'Daha fazla bilgi edinin: Catldllmodület sınıfı'
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
ms.openlocfilehash: b6b6f87fc77187b150824fcd67fae254eb6d8f57
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97147439"
---
# <a name="catldllmodulet-class"></a>Catldllmodület sınıfı

Bu sınıf, bir DLL 'in modülünü temsil eder.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class T>
class ATL_NO_VTABLE CAtlDllModuleT : public CAtlModuleT<T>
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Sınıfınız öğesinden türetilir `CAtlDllModuleT` .

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[Catldllmodület:: Catldllmodület](#catldllmodulet)|Oluşturucu.|
|[Catldllmodület:: ~ Catldllmodület](#dtor)|Yok edicisi.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Catldllmodület::D llCanUnloadNow](#dllcanunloadnow)|DLL 'in kaldırılacaksa test eder.|
|[Catldllmodület::D llGetClassObject](#dllgetclassobject)|Bir sınıf üreteci döndürür.|
|[Catldllmodület::D llMain](#dllmain)|İsteğe bağlı giriş, bir dinamik bağlantı kitaplığı (DLL) içine işaret.|
|[Catldllmodület::D llRegisterServer](#dllregisterserver)|DLL içindeki nesneler için sistem kayıt defterine giriş ekler.|
|[Catldllmodület::D llUnregisterServer](#dllunregisterserver)|DLL içindeki nesneler için sistem kayıt defterindeki girişleri kaldırır.|
|[Catldllmodület:: GetClassObject](#getclassobject)|Bir sınıf üreteci döndürür. [DllGetClassObject](#dllgetclassobject)tarafından çağrılır.|

## <a name="remarks"></a>Açıklamalar

`CAtlDllModuleT` bir dinamik bağlantı kitaplığı (DLL) modülünü temsil eder ve tüm DLL projeleri tarafından kullanılan işlevleri sağlar. [Catlmodület](../../atl/reference/catlmodulet-class.md) sınıfının bu özelleştirmesi kayıt desteğini içerir.

ATL 'deki modüller hakkında daha fazla bilgi için bkz. [ATL modül sınıfları](../../atl/atl-module-classes.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[_ATL_MODULE](atl-typedefs.md#_atl_module)

[CAtlModule](../../atl/reference/catlmodule-class.md)

[Catlmodület](../../atl/reference/catlmodulet-class.md)

`CAtlDllModuleT`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlbase. h

## <a name="catldllmoduletcatldllmodulet"></a><a name="catldllmodulet"></a> Catldllmodület:: Catldllmodület

Oluşturucu.

```cpp
CAtlDllModuleT() throw();
```

## <a name="catldllmoduletcatldllmodulet"></a><a name="dtor"></a> Catldllmodület:: ~ Catldllmodület

Yok edicisi.

```cpp
~CAtlDllModuleT() throw();
```

## <a name="catldllmoduletdllcanunloadnow"></a><a name="dllcanunloadnow"></a> Catldllmodület::D llCanUnloadNow

DLL 'in kaldırılacaksa test eder.

```cpp
HRESULT DllCanUnloadNow() throw();
```

### <a name="return-value"></a>Dönüş Değeri

DLL bellekten kaldırılacaksa S_OK döndürür veya S_FALSE.

## <a name="catldllmoduletdllgetclassobject"></a><a name="dllgetclassobject"></a> Catldllmodület::D llGetClassObject

Sınıf üreteci döndürür.

```cpp
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
*Riıd* tarafından tanımlanan arabirim işaretçisine yönelik bir işaretçi. Nesne bu arabirimi desteklemiyorsa, *PPV* null olarak ayarlanır.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

## <a name="catldllmoduletdllmain"></a><a name="dllmain"></a> Catldllmodület::D llMain

İsteğe bağlı giriş, bir dinamik bağlantı kitaplığı (DLL) içine işaret.

```cpp
BOOL WINAPI DllMain(DWORD dwReason, LPVOID /* lpReserved*/) throw();
```

### <a name="parameters"></a>Parametreler

*dwReason*<br/>
DLL_PROCESS_ATTACH olarak ayarlanırsa, DLL_THREAD_ATTACH ve DLL_THREAD_DETACH bildirim çağrıları devre dışı bırakılır.

*lpReserved*<br/>
Ayrılmış.

### <a name="return-value"></a>Dönüş Değeri

Her zaman TRUE döndürür.

### <a name="remarks"></a>Açıklamalar

DLL_THREAD_ATTACH ve DLL_THREAD_DETACH bildirim çağrılarını devre dışı bırakmak, çok sayıda dll içeren çok iş parçacıklı uygulamalar için faydalı bir iyileştirme olabilir. Bu, iş parçacığı oluşturma ve silme, dll 'Lerin ek/çıkarılabilir bu iş parçacığı düzeyi bildirimlerine ihtiyacı yoktur.

## <a name="catldllmoduletdllregisterserver"></a><a name="dllregisterserver"></a> Catldllmodület::D llRegisterServer

DLL içindeki nesneler için sistem kayıt defterine giriş ekler.

```cpp
HRESULT DllRegisterServer(BOOL bRegTypeLib = TRUE) throw();
```

### <a name="parameters"></a>Parametreler

*bRegTypeLib*<br/>
Tür kitaplığının kaydı varsa TRUE. Varsayılan değer TRUE 'dur.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

## <a name="catldllmoduletdllunregisterserver"></a><a name="dllunregisterserver"></a> Catldllmodület::D llUnregisterServer

DLL içindeki nesneler için sistem kayıt defterindeki girişleri kaldırır.

```cpp
HRESULT DllUnregisterServer(BOOL bUnRegTypeLib = TRUE) throw();
```

### <a name="parameters"></a>Parametreler

*bUnRegTypeLib*<br/>
Tür kitaplığının kayıt defterinden kaldırılması durumunda TRUE. Varsayılan değer TRUE 'dur.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

## <a name="catldllmoduletgetclassobject"></a><a name="getclassobject"></a> Catldllmodület:: GetClassObject

Belirtilen CLSID 'nin bir nesnesini oluşturur.

```cpp
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
*Riıd* tarafından tanımlanan arabirim işaretçisine yönelik bir işaretçi. Nesne bu arabirimi desteklemiyorsa, *PPV* null olarak ayarlanır.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, [Catldllmodület::D llgetclassobject](#dllgetclassobject) tarafından çağrılır ve geriye dönük uyumluluk için eklenmiştir.

## <a name="see-also"></a>Ayrıca bkz.

[Catlmodület sınıfı](../../atl/reference/catlmodulet-class.md)<br/>
[CAtlExeModuleT sınıfı](../../atl/reference/catlexemodulet-class.md)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)<br/>
[Modül sınıfları](../../atl/atl-module-classes.md)
