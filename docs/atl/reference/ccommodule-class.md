---
description: 'Daha fazla bilgi edinin: CComModule sınıfı'
title: CComModule sınıfı
ms.date: 08/19/2019
f1_keywords:
- CComModule
- ATLBASE/ATL::CComModule
- ATLBASE/ATL::CComModule::GetClassObject
- ATLBASE/ATL::CComModule::GetModuleInstance
- ATLBASE/ATL::CComModule::GetResourceInstance
- ATLBASE/ATL::CComModule::GetTypeLibInstance
- ATLBASE/ATL::CComModule::Init
- ATLBASE/ATL::CComModule::RegisterClassHelper
- ATLBASE/ATL::CComModule::RegisterClassObjects
- ATLBASE/ATL::CComModule::RegisterServer
- ATLBASE/ATL::CComModule::RegisterTypeLib
- ATLBASE/ATL::CComModule::RevokeClassObjects
- ATLBASE/ATL::CComModule::Term
- ATLBASE/ATL::CComModule::UnregisterClassHelper
- ATLBASE/ATL::CComModule::UnregisterServer
- ATLBASE/ATL::CComModule::UpdateRegistryClass
- ATLBASE/ATL::CComModule::UpdateRegistryFromResourceD
- ATLBASE/ATL::CComModule::UpdateRegistryFromResourceS
- ATLBASE/ATL::CComModule::m_csObjMap
- ATLBASE/ATL::CComModule::m_csTypeInfoHolder
- ATLBASE/ATL::CComModule::m_csWindowCreate
- ATLBASE/ATL::CComModule::m_hInst
- ATLBASE/ATL::CComModule::m_hInstResource
- ATLBASE/ATL::CComModule::m_hInstTypeLib
- ATLBASE/ATL::CComModule::m_pObjMap
helpviewer_keywords:
- CComModule class
- DLL modules [C++], ATL
ms.assetid: f5face2c-8fd8-40e6-9ec3-54ab74701769
ms.openlocfilehash: dd0ec6c6aa7d68374a90830b10815a9cbdd54aeb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97152028"
---
# <a name="ccommodule-class"></a>CComModule sınıfı

ATL 7,0 itibariyle `CComModule` kullanım dışıdır: daha fazla ayrıntı için bkz. [ATL modül sınıfları](../../atl/atl-module-classes.md) .

> [!IMPORTANT]
> Bu sınıf ve üyeleri Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Syntax

```
class CComModule : public _ATL_MODULE
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CComModule:: GetClassObject](#getclassobject)|Belirtilen bir CLSID 'nin bir nesnesini oluşturur. Yalnızca dll 'Ler için.|
|[CComModule:: GetModuleInstance](#getmoduleinstance)|`m_hInst` döndürür.|
|[CComModule:: GetResourceInstance](#getresourceinstance)|`m_hInstResource` döndürür.|
|[CComModule:: GetTypeLibInstance](#gettypelibinstance)|`m_hInstTypeLib` döndürür.|
|[CComModule:: Init](#init)|Veri üyelerini başlatır.|
|[CComModule:: RegisterClassHelper](#registerclasshelper)|Bir nesnenin standart sınıf kaydını sistem kayıt defterine girer.|
|[CComModule:: RegisterClassObjects](#registerclassobjects)|Sınıf nesnesini kaydeder. Yalnızca EXEs için.|
|[CComModule:: RegisterServer](#registerserver)|Nesne eşlemesindeki her nesne için sistem kayıt defterini güncelleştirir.|
|[CComModule:: RegisterTypeLib](#registertypelib)|Tür kitaplığını kaydeder.|
|[CComModule:: RevokeClassObjects](#revokeclassobjects)|Sınıf nesnesini iptal eder. Yalnızca EXEs için.|
|[CComModule:: Term](#term)|Veri üyelerini yayınlar.|
|[CComModule:: UnregisterClassHelper](#unregisterclasshelper)|Bir nesnenin standart sınıf kaydını sistem kayıt defterinden kaldırır.|
|[CComModule:: UnregisterServer](#unregisterserver)|Nesne eşlemesindeki her nesnenin kaydını siler.|
|[CComModule:: UpdateRegistryClass](#updateregistryclass)|Bir nesnenin standart sınıf kaydını kaydettirir veya kaydını siler.|
|[CComModule:: UpdateRegistryFromResourceD](#updateregistryfromresourced)|Bir nesneyi kaydetmek veya kaydını silmek için belirtilen bir kaynakta bulunan betiği çalıştırır.|
|[CComModule:: UpdateRegistryFromResourceS](#updateregistryfromresources)|ATL kayıt defteri bileşenine statik olarak bağlantılar. Bir nesneyi kaydetmek veya kaydını silmek için belirtilen bir kaynakta bulunan betiği çalıştırır.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CComModule:: m_csObjMap](#m_csobjmap)|Nesne eşleme bilgilerine eşitlenmiş erişimi sağlar.|
|[CComModule:: m_csTypeInfoHolder](#m_cstypeinfoholder)|Tür kitaplığı bilgilerine eşitlenmiş erişimi sağlar.|
|[CComModule:: m_csWindowCreate](#m_cswindowcreate)|Pencere oluşturma sırasında kullanılan Windows sınıf bilgilerine ve statik verilere eşitlenmiş erişimi sağlar.|
|[CComModule:: m_hInst](#m_hinst)|Modül örneğine yönelik tanıtıcıyı içerir.|
|[CComModule:: m_hInstResource](#m_hinstresource)|Varsayılan olarak, modül örneğine yönelik tanıtıcıyı içerir.|
|[CComModule:: m_hInstTypeLib](#m_hinsttypelib)|Varsayılan olarak, modül örneğine yönelik tanıtıcıyı içerir.|
|[CComModule:: m_pObjMap](#m_pobjmap)|Modül örneği tarafından tutulan nesne eşlemesini işaret eder.|

## <a name="remarks"></a>Açıklamalar

> [!NOTE]
> Bu sınıf kullanım dışıdır ve ATL kod oluşturma sihirbazları artık [CAtlAutoThreadModule](../../atl/reference/catlautothreadmodule-class.md) ve [CAtlModule](../../atl/reference/catlmodule-class.md) türetilmiş sınıflarını kullanır. Daha fazla bilgi için bkz. [ATL modül sınıfları](../../atl/atl-module-classes.md) . Aşağıdaki bilgiler, ATL 'nin eski sürümleriyle oluşturulan uygulamalarla kullanım içindir. `CComModule` , geriye doğru özellik için ATL 'nin bir parçası olmaya devam etmektedir.

`CComModule` bir COM sunucu modülünü uygular ve istemcinin modülün bileşenlerine erişmesine izin verir. `CComModule` Hem DLL (işlem içi) hem de EXE (yerel) modüllerini destekler.

Bir `CComModule` örnek, sınıf nesne tanımlarının bir kümesini sürdürmek için bir nesne eşlemesi kullanır. Bu nesne eşlemesi bir yapı dizisi olarak uygulanır `_ATL_OBJMAP_ENTRY` ve şunun için bilgiler içerir:

- Nesne açıklamalarını sistem kayıt defterine girme ve kaldırma.

- Bir sınıf fabrikası aracılığıyla nesneleri örnekleniyor.

- Bileşendeki bir istemciyle kök nesne arasında iletişim kurma.

- Sınıf nesnelerinin ömür yönetimi gerçekleştiriliyor.

ATL COM AppWizard 'ı çalıştırdığınızda sihirbaz, `_Module` genel bir örneği `CComModule` veya ondan türetilmiş bir sınıf otomatik olarak oluşturulur. ATL Proje Sihirbazı hakkında daha fazla bilgi için, [ATL projesi oluşturma](../../atl/reference/creating-an-atl-project.md)makalesine bakın.

, ATL 'nin yanı sıra, `CComModule` EXEs ve Windows Hizmetleri için bir Grup modeli modülü uygulayan [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md)de sağlar. `CComAutoThreadModule`Birden çok apartmanlarda nesne oluşturmak istediğiniz sırada modülünüzü türetebilirsiniz.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[_ATL_MODULE](atl-typedefs.md#_atl_module)

[CAtlModule](../../atl/reference/catlmodule-class.md)

[Catlmodület](../../atl/reference/catlmodulet-class.md)

`CComModule`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlbase. h

## <a name="ccommodulegetclassobject"></a><a name="getclassobject"></a> CComModule:: GetClassObject

ATL 7,0 itibariyle `CComModule` artık kullanılmıyor: daha fazla ayrıntı için bkz. [ATL modül sınıfları](../../atl/atl-module-classes.md) .

```
HRESULT GetClassObject(
    REFCLSID rclsid,
    REFIID riid,
    LPVOID* ppv) throw();
```

### <a name="parameters"></a>Parametreler

*rclsıd*<br/>
'ndaki Oluşturulacak nesnenin CLSID değeri.

*riıd*<br/>
'ndaki İstenen arabirimin IID 'si.

*PPV*<br/>
dışı *Riıd* tarafından tanımlanan arabirim işaretçisine yönelik bir işaretçi. Nesne bu arabirimi desteklemiyorsa, *PPV* null olarak ayarlanır.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

Belirtilen CLSID 'nin bir nesnesini oluşturur ve bu nesneye bir arabirim işaretçisi alır.

`GetClassObject` yalnızca dll 'Ler tarafından kullanılabilir.

## <a name="ccommodulegetmoduleinstance"></a><a name="getmoduleinstance"></a> CComModule:: GetModuleInstance

ATL 7,0 itibariyle `CComModule` artık kullanılmıyor: daha fazla ayrıntı için bkz. [ATL modül sınıfları](../../atl/atl-module-classes.md) .

```
HINSTANCE GetModuleInstance() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Bu modülü tanımlayan HıNSTANCE.

### <a name="remarks"></a>Açıklamalar

[M_hInst](#m_hinst) veri üyesini döndürür.

## <a name="ccommodulegetresourceinstance"></a><a name="getresourceinstance"></a> CComModule:: GetResourceInstance

ATL 7,0 itibariyle `CComModule` artık kullanılmıyor: daha fazla ayrıntı için bkz. [ATL modül sınıfları](../../atl/atl-module-classes.md) .

```
HINSTANCE GetResourceInstance() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Bir HıNSTANCE.

### <a name="remarks"></a>Açıklamalar

[M_hInstResource](#m_hinstresource) veri üyesini döndürür.

## <a name="ccommodulegettypelibinstance"></a><a name="gettypelibinstance"></a> CComModule:: GetTypeLibInstance

ATL 7,0 itibariyle `CComModule` artık kullanılmıyor: daha fazla ayrıntı için bkz. [ATL modül sınıfları](../../atl/atl-module-classes.md) .

```
HINSTANCE GetTypeLibInstance() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Bir HıNSTANCE.

### <a name="remarks"></a>Açıklamalar

[M_hInstTypeLib](#m_hinsttypelib) veri üyesini döndürür.

## <a name="ccommoduleinit"></a><a name="init"></a> CComModule:: Init

ATL 7,0 itibariyle `CComModule` artık kullanılmıyor: daha fazla ayrıntı için bkz. [ATL modül sınıfları](../../atl/atl-module-classes.md) .

```
HRESULT Init(
    _ATL_OBJMAP_ENTRY* p,
    HINSTANCE h,
    const GUID* plibid = NULL) throw();
```

### <a name="parameters"></a>Parametreler

*Lama*<br/>
'ndaki Nesne eşleme girdileri dizisine yönelik bir işaretçi.

*h*<br/>
'ndaki Ya da öğesine geçirilen HıNSTANCE `DLLMain` `WinMain` .

*plibıd*<br/>
'ndaki Projeyle ilişkili tür kitaplığının LIBıD işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

Tüm veri üyelerini başlatır.

## <a name="ccommodulem_csobjmap"></a><a name="m_csobjmap"></a> CComModule:: m_csObjMap

ATL 7,0 itibariyle `CComModule` artık kullanılmıyor: daha fazla ayrıntı için bkz. [ATL modül sınıfları](../../atl/atl-module-classes.md) .

```
CRITICAL_SECTION m_csObjMap;
```

### <a name="remarks"></a>Açıklamalar

Nesne haritasına eşitlenmiş erişimi sağlar.

## <a name="ccommodulem_cstypeinfoholder"></a><a name="m_cstypeinfoholder"></a> CComModule:: m_csTypeInfoHolder

ATL 7,0 itibariyle `CComModule` artık kullanılmıyor: daha fazla ayrıntı için bkz. [ATL modül sınıfları](../../atl/atl-module-classes.md) .

```
CRITICAL_SECTION m_csTypeInfoHolder;
```

### <a name="remarks"></a>Açıklamalar

Tür kitaplığına eşitlenmiş erişimi sağlar.

## <a name="ccommodulem_cswindowcreate"></a><a name="m_cswindowcreate"></a> CComModule:: m_csWindowCreate

ATL 7,0 itibariyle `CComModule` artık kullanılmıyor: daha fazla ayrıntı için bkz. [ATL modül sınıfları](../../atl/atl-module-classes.md) .

```
CRITICAL_SECTION m_csWindowCreate;
```

### <a name="remarks"></a>Açıklamalar

Pencere sınıfı bilgilerine ve pencere oluşturma sırasında kullanılan statik verilere eşitlenmiş erişimi sağlar.

## <a name="ccommodulem_hinst"></a><a name="m_hinst"></a> CComModule:: m_hInst

ATL 7,0 itibariyle `CComModule` artık kullanılmıyor: daha fazla ayrıntı için bkz. [ATL modül sınıfları](../../atl/atl-module-classes.md) .

```
HINSTANCE m_hInst;
```

### <a name="remarks"></a>Açıklamalar

Modül örneğine yönelik tanıtıcıyı içerir.

[Init](#init) yöntemi, `m_hInst` veya öğesine geçirilen tanıtıcıyı ayarlar `DLLMain` `WinMain` .

## <a name="ccommodulem_hinstresource"></a><a name="m_hinstresource"></a> CComModule:: m_hInstResource

ATL 7,0 itibariyle `CComModule` artık kullanılmıyor: daha fazla ayrıntı için bkz. [ATL modül sınıfları](../../atl/atl-module-classes.md) .

```
HINSTANCE m_hInstResource;
```

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, modül örneğine yönelik tanıtıcıyı içerir.

[Init](#init) yöntemi, `m_hInstResource` veya öğesine geçirilen tanıtıcıyı ayarlar `DLLMain` `WinMain` . `m_hInstResource`Tanıtıcıya açıkça bir kaynak olarak ayarlayabilirsiniz.

[GetResourceInstance](#getresourceinstance) yöntemi içinde depolanan tanıtıcıyı döndürür `m_hInstResource` .

## <a name="ccommodulem_hinsttypelib"></a><a name="m_hinsttypelib"></a> CComModule:: m_hInstTypeLib

ATL 7,0 itibariyle `CComModule` artık kullanılmıyor: daha fazla ayrıntı için bkz. [ATL modül sınıfları](../../atl/atl-module-classes.md) .

```
HINSTANCE m_hInstTypeLib;
```

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, modül örneğine yönelik tanıtıcıyı içerir.

[Init](#init) yöntemi, `m_hInstTypeLib` veya öğesine geçirilen tanıtıcıyı ayarlar `DLLMain` `WinMain` . `m_hInstTypeLib`Tanıtıcı olarak bir tür kitaplığına açıkça ayarlayabilirsiniz.

[GetTypeLibInstance](#gettypelibinstance) yöntemi içinde depolanan tanıtıcıyı döndürür `m_hInstTypeLib` .

## <a name="ccommodulem_pobjmap"></a><a name="m_pobjmap"></a> CComModule:: m_pObjMap

ATL 7,0 itibariyle `CComModule` artık kullanılmıyor: daha fazla ayrıntı için bkz. [ATL modül sınıfları](../../atl/atl-module-classes.md) .

```
_ATL_OBJMAP_ENTRY* m_pObjMap;
```

### <a name="remarks"></a>Açıklamalar

Modül örneği tarafından tutulan nesne eşlemesini işaret eder.

## <a name="ccommoduleregisterclasshelper"></a><a name="registerclasshelper"></a> CComModule:: RegisterClassHelper

ATL 7,0 itibariyle `CComModule` artık kullanılmıyor: daha fazla ayrıntı için bkz. [ATL modül sınıfları](../../atl/atl-module-classes.md) .

```
ATL_DEPRECATED HRESULT RegisterClassHelper(
    const CLSID& clsid,
    LPCTSTR lpszProgID,
    LPCTSTR lpszVerIndProgID,
    UINT nDescID,
    DWORD dwFlags);
```

### <a name="parameters"></a>Parametreler

*in*<br/>
'ndaki Kaydedilecek nesnenin CLSID 'SI.

*lpszProgID*<br/>
'ndaki Nesneyle ilişkili ProgID.

*lpszVerIndProgID*<br/>
'ndaki Nesneyle ilişkili sürümden bağımsız ProgID.

*Ndescıd*<br/>
'ndaki Nesnenin açıklamasına yönelik bir dize kaynağının tanımlayıcısı.

*dwFlags*<br/>
'ndaki Kayıt defterine girilecek iş parçacığı modelini belirtir. Olası değerler THREADFLAGS_APARTMENT, THREADFLAGS_BOTH veya AUTPRXFLAG.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

Bir nesnenin standart sınıf kaydını sistem kayıt defterine girer.

[UpdateRegistryClass](#updateregistryclass) yöntemi çağırır `RegisterClassHelper` .

## <a name="ccommoduleregisterclassobjects"></a><a name="registerclassobjects"></a> CComModule:: RegisterClassObjects

ATL 7,0 itibariyle `CComModule` artık kullanılmıyor: daha fazla ayrıntı için bkz. [ATL modül sınıfları](../../atl/atl-module-classes.md) .

```
HRESULT RegisterClassObjects(DWORD dwClsContext, DWORD dwFlags) throw();
```

### <a name="parameters"></a>Parametreler

*dwClsContext*<br/>
'ndaki Sınıf nesnesinin çalıştırılacağı bağlamı belirtir. Olası değerler CLSCTX_INPROC_SERVER, CLSCTX_INPROC_HANDLER veya CLSCTX_LOCAL_SERVER. Bu değerlerin bir açıklaması için Windows SDK bkz. [clsctx](/windows/win32/api/wtypesbase/ne-wtypesbase-clsctx) .

*dwFlags*<br/>
'ndaki Sınıf nesnesine bağlantı türlerini belirler. Olası değerler REGCLS_SINGLEUSE, REGCLS_MULTIPLEUSE veya REGCLS_MULTI_SEPARATE. Bu değerlerin bir açıklaması için Windows SDK [regcls](/windows/win32/api/combaseapi/ne-combaseapi-regcls) bölümüne bakın.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

Diğer uygulamaların bağlanabilmesi için, OLE ile bir EXE sınıfı nesnesi kaydeder. Bu yöntem yalnızca EXEs tarafından kullanılabilir.

## <a name="ccommoduleregisterserver"></a><a name="registerserver"></a> CComModule:: RegisterServer

ATL 7,0 itibariyle `CComModule` artık kullanılmıyor: daha fazla ayrıntı için bkz. [ATL modül sınıfları](../../atl/atl-module-classes.md) .

```
HRESULT RegisterServer(
    BOOL bRegTypeLib = FALSE,
    const CLSID* pCLSID = NULL) throw();
```

### <a name="parameters"></a>Parametreler

*bRegTypeLib*<br/>
'ndaki Tür kitaplığının kaydedilip edilmeyeceğini belirtir. Varsayılan değer FALSE 'dur.

*pCLSID*<br/>
'ndaki Kaydedilecek nesnenin CLSID değerini gösterir. NULL ise (varsayılan değer), nesne haritadaki tüm nesneler kaydedilir.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

*PCLSID* parametresine bağlı olarak, tek bir sınıf nesnesi veya nesne eşlemesindeki tüm nesneler için sistem kayıt defterini güncelleştirir.

*BRegTypeLib* değeri true ise, tür kitaplığı bilgileri de güncelleştirilir.

Nesne haritasına giriş ekleme hakkında bilgi için bkz. [OBJECT_ENTRY_AUTO](object-map-macros.md#object_entry_auto) .

`RegisterServer` , `DLLRegisterServer` BIR DLL için veya `WinMain` komut satırı SEÇENEĞIYLE bir exe çalıştırması tarafından otomatik olarak çağrılır `/RegServer` .

## <a name="ccommoduleregistertypelib"></a><a name="registertypelib"></a> CComModule:: RegisterTypeLib

ATL 7,0 itibariyle `CComModule` artık kullanılmıyor: daha fazla ayrıntı için bkz. [ATL modül sınıfları](../../atl/atl-module-classes.md) .

```
HRESULT RegisterTypeLib() throw();
HRESULT RegisterTypeLib(LPCTSTR lpszIndex) throw();
```

### <a name="parameters"></a>Parametreler

*lpszIndex*<br/>
'ndaki Biçiminde dize `"\\N"` , `N` TYPELIB kaynağının tamsayı dizinidir.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

Bir tür kitaplığı hakkında bilgileri sistem kayıt defterine ekler.

Modül örneği birden çok tür kitaplığı içeriyorsa, hangi tür kitaplığının kullanılması gerektiğini belirtmek için bu yöntemin ikinci sürümünü kullanın.

## <a name="ccommodulerevokeclassobjects"></a><a name="revokeclassobjects"></a> CComModule:: RevokeClassObjects

ATL 7,0 itibariyle `CComModule` artık kullanılmıyor: daha fazla ayrıntı için bkz. [ATL modül sınıfları](../../atl/atl-module-classes.md) .

```
HRESULT RevokeClassObjects() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

Sınıf nesnesini kaldırır. Bu yöntem yalnızca EXEs tarafından kullanılabilir.

## <a name="ccommoduleterm"></a><a name="term"></a> CComModule:: Term

ATL 7,0 itibariyle `CComModule` artık kullanılmıyor: daha fazla ayrıntı için bkz. [ATL modül sınıfları](../../atl/atl-module-classes.md) .

```cpp
void Term() throw();
```

### <a name="remarks"></a>Açıklamalar

Tüm veri üyelerini yayınlar.

## <a name="ccommoduleunregisterclasshelper"></a><a name="unregisterclasshelper"></a> CComModule:: UnregisterClassHelper

ATL 7,0 itibariyle `CComModule` artık kullanılmıyor: daha fazla ayrıntı için bkz. [ATL modül sınıfları](../../atl/atl-module-classes.md) .

```
ATL_DEPRECATED HRESULT UnregisterClassHelper(
    const CLSID& clsid,
    LPCTSTR lpszProgID,
    LPCTSTR lpszVerIndProgID);
```

### <a name="parameters"></a>Parametreler

*in*<br/>
'ndaki Kaydı kaldırılacak nesnenin CLSID değeri.

*lpszProgID*<br/>
'ndaki Nesneyle ilişkili ProgID.

*lpszVerIndProgID*<br/>
'ndaki Nesneyle ilişkili sürümden bağımsız ProgID.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

Bir nesnenin standart sınıf kaydını sistem kayıt defterinden kaldırır.

[UpdateRegistryClass](#updateregistryclass) yöntemi çağırır `UnregisterClassHelper` .

## <a name="ccommoduleunregisterserver"></a><a name="unregisterserver"></a> CComModule:: UnregisterServer

ATL 7,0 itibariyle `CComModule` artık kullanılmıyor: daha fazla ayrıntı için bkz. [ATL modül sınıfları](../../atl/atl-module-classes.md) .

```
HRESULT UnregisterServer(const CLSID* pCLSID = NULL) throw ();
inline HRESULT UnregisterServer(BOOL bUnRegTypeLib, const CLSID* pCLSID = NULL) throw ();
```

### <a name="parameters"></a>Parametreler

*bUnRegTypeLib*<br/>
TRUE ise tür kitaplığının de kaydı silindi.

*pCLSID*<br/>
Kaydı kaldırılacak nesnenin CLSID değerini gösterir. NULL ise (varsayılan değer), nesne eşlemesindeki tüm nesnelerin kaydı silinir.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

*PCLSID* parametresine bağlı olarak, tek bir sınıf nesnesinin veya nesne eşlemesindeki tüm nesnelerin kaydını siler.

`UnregisterServer` , `DLLUnregisterServer` BIR DLL için veya `WinMain` komut satırı SEÇENEĞIYLE bir exe çalıştırması tarafından otomatik olarak çağrılır `/UnregServer` .

Nesne haritasına giriş ekleme hakkında bilgi için bkz. [OBJECT_ENTRY_AUTO](object-map-macros.md#object_entry_auto) .

## <a name="ccommoduleupdateregistryclass"></a><a name="updateregistryclass"></a> CComModule:: UpdateRegistryClass

ATL 7,0 itibariyle `CComModule` artık kullanılmıyor: daha fazla ayrıntı için bkz. [ATL modül sınıfları](../../atl/atl-module-classes.md) .

```
ATL_DEPRECATED HRESULT UpdateRegistryClass(
    const CLSID& clsid,
    LPCTSTR lpszProgID,
    LPCTSTR lpszVerIndProgID,
    UINT nDescID,
    DWORD dwFlags,
    BOOL bRegister);

ATL_DEPRECATED HRESULT UpdateRegistryClass(
    const CLSID& clsid,
    LPCTSTR lpszProgID,
    LPCTSTR lpszVerIndProgID,
    LPCTSTR szDesc,
    DWORD dwFlags,
    BOOL bRegister);
```

### <a name="parameters"></a>Parametreler

*in*<br/>
Kaydedilecek veya kaydı kaldırılacak nesnenin CLSID değeri.

*lpszProgID*<br/>
Nesneyle ilişkili ProgID.

*lpszVerIndProgID*<br/>
Nesneyle ilişkili sürümden bağımsız ProgID.

*Ndescıd*<br/>
Nesnenin açıklamasına yönelik dize kaynağının tanımlayıcısı.

*szDesc*<br/>
Nesnenin açıklamasını içeren bir dize.

*dwFlags*<br/>
Kayıt defterine girilecek iş parçacığı modelini belirtir. Olası değerler THREADFLAGS_APARTMENT, THREADFLAGS_BOTH veya AUTPRXFLAG.

*bRegister*<br/>
Nesnenin kaydedilip edilmeyeceğini belirtir.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

*BRegister* true ise, bu yöntem nesnenin standart sınıf kaydını sistem kayıt defterine girer.

*BRegister* yanlış ise, nesnenin kaydını kaldırır.

*BRegister* değerine bağlı olarak, `UpdateRegistryClass` [RegisterClassHelper](#registerclasshelper) ya da [UnregisterClassHelper](#unregisterclasshelper)' ı çağırır.

[DECLARE_REGISTRY](registry-macros.md#declare_registry) makrosunu belirterek, `UpdateRegistryClass` nesne haritanız işlendiğinde otomatik olarak çağrılacaktır.

## <a name="ccommoduleupdateregistryfromresourced"></a><a name="updateregistryfromresourced"></a> CComModule:: UpdateRegistryFromResourceD

ATL 7,0 itibariyle `CComModule` artık kullanılmıyor: daha fazla ayrıntı için bkz. [ATL modül sınıfları](../../atl/atl-module-classes.md) .

```
virtual HRESULT UpdateRegistryFromResourceD(
    LPCTSTR lpszRes,
    BOOL bRegister,
    struct _ATL_REGMAP_ENTRY* pMapEntries = NULL) throw();

virtual HRESULT UpdateRegistryFromResourceD(
    UINT nResID,
    BOOL bRegister,
    struct _ATL_REGMAP_ENTRY* pMapEntries = NULL) throw ();
```

### <a name="parameters"></a>Parametreler

*lpszRes*<br/>
'ndaki Bir kaynak adı.

*Nresd*<br/>
'ndaki Kaynak KIMLIĞI.

*bRegister*<br/>
'ndaki Nesnenin kaydedilip edilmeyeceğini belirtir.

*pMapEntries*<br/>
'ndaki Değiştirme eşlemesi için, betikle değiştirilebilen parametrelerle ilişkili değerleri depolayan bir işaretçi. ATL otomatik olarak kullanır `%MODULE%` . Ek değiştirilebilen parametreleri kullanmak için Ayrıntılar için açıklamalara bakın. Aksi takdirde, NULL varsayılan değerini kullanın.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

*LpszRes* veya *nresd* tarafından belirtilen kaynakta bulunan betiği çalıştırır.

*BRegister* true ise, bu yöntem nesneyi sistem kayıt defterine kaydeder; Aksi takdirde, nesnesinin kaydını siler.

[DECLARE_REGISTRY_RESOURCE](registry-macros.md#declare_registry_resource) veya [DECLARE_REGISTRY_RESOURCEID](registry-macros.md#declare_registry_resourceid) makrosunu belirterek, `UpdateRegistryFromResourceD` nesne haritanız işlendiğinde otomatik olarak çağrılacaktır.

> [!NOTE]
> Çalışma zamanında değiştirme değerlerini yerine koymak için DECLARE_REGISTRY_RESOURCE veya DECLARE_REGISTRY_RESOURCEID makrosunu belirtmeyin. Bunun yerine, `_ATL_REGMAP_ENTRIES` her girdinin çalışma zamanında yer tutucuyu değiştirecek bir değerle eşleştirilmiş bir değişken yer tutucusu içerdiği bir yapı dizisi oluşturun. Sonra `UpdateRegistryFromResourceD` , *pMapEntries* parametresi için diziyi geçirerek çağırın. Bu, yapılardaki tüm değiştirme değerlerini kayıt `_ATL_REGMAP_ENTRIES` sahibinin değiştirme eşlemesine ekler.

> [!NOTE]
> ATL kayıt defteri bileşeni (kaydedici) statik olarak bağlamak için bkz. [UpdateRegistryFromResourceS](#updateregistryfromresources).

Değiştirilebilir parametreler ve betik oluşturma hakkında daha fazla bilgi için, [atl kayıt defteri bileşeni (kaydedici)](../../atl/atl-registry-component-registrar.md)makalesine bakın.

## <a name="ccommoduleupdateregistryfromresources"></a><a name="updateregistryfromresources"></a> CComModule:: UpdateRegistryFromResourceS

ATL 7,0 itibariyle `CComModule` artık kullanılmıyor: daha fazla ayrıntı için bkz. [ATL modül sınıfları](../../atl/atl-module-classes.md) .

```
virtual HRESULT UpdateRegistryFromResourceS(
    LPCTSTR lpszRes,
    BOOL bRegister,
    struct _ATL_REGMAP_ENTRY* pMapEntries = NULL) throw();

virtual HRESULT UpdateRegistryFromResourceS(
    UINT nResID,
    BOOL bRegister,
    struct _ATL_REGMAP_ENTRY* pMapEntries = NULL) throw();
```

### <a name="parameters"></a>Parametreler

*lpszRes*<br/>
'ndaki Bir kaynak adı.

*Nresd*<br/>
'ndaki Kaynak KIMLIĞI.

*bRegister*<br/>
'ndaki Kaynak betiğin kaydedilip edilmeyeceğini belirtir.

*pMapEntries*<br/>
'ndaki Değiştirme eşlemesi için, betikle değiştirilebilen parametrelerle ilişkili değerleri depolayan bir işaretçi. ATL otomatik olarak kullanır `%MODULE%` . Ek değiştirilebilen parametreleri kullanmak için Ayrıntılar için açıklamalara bakın. Aksi takdirde, NULL varsayılan değerini kullanın.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

[UpdateRegistryFromResourceD](#updateregistryfromresourced) benzerı `UpdateRegistryFromResourceS` , atl kayıt defteri bileşeni (kaydedici) için statik bir bağlantı oluşturur.

`UpdateRegistryFromResourceS` , nesne haritanız işlendiğinde otomatik olarak çağrılacaktır, bu, `#define _ATL_STATIC_REGISTRY` *pch. h* 'Nize (Visual Studio 2017 ve önceki sürümlerde *stdadfx. h* ) eklemenizi sağlar.

> [!NOTE]
> Çalışma zamanında değiştirme değerlerini yerine koymak için [DECLARE_REGISTRY_RESOURCE](registry-macros.md#declare_registry_resource) veya [DECLARE_REGISTRY_RESOURCEID](registry-macros.md#declare_registry_resourceid) makrosunu belirtmeyin. Bunun yerine, `_ATL_REGMAP_ENTRIES` her girdinin çalışma zamanında yer tutucuyu değiştirecek bir değerle eşleştirilmiş bir değişken yer tutucusu içerdiği bir yapı dizisi oluşturun. Sonra `UpdateRegistryFromResourceS` , *pMapEntries* parametresi için diziyi geçirerek çağırın. Bu, yapılardaki tüm değiştirme değerlerini kayıt `_ATL_REGMAP_ENTRIES` sahibinin değiştirme eşlemesine ekler.

Değiştirilebilir parametreler ve betik oluşturma hakkında daha fazla bilgi için, [atl kayıt defteri bileşeni (kaydedici)](../../atl/atl-registry-component-registrar.md)makalesine bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa genel bakış](../../atl/atl-class-overview.md)
