---
title: CComModule Sınıfı
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
ms.openlocfilehash: 652c5f078ddbaf8d3e333f7003d6515a94dd8f83
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327754"
---
# <a name="ccommodule-class"></a>CComModule Sınıfı

7,0 `CComModule` TL itibariyle, amortismana uyrdu: daha fazla bilgi için [ATL Modül Sınıfları'na](../../atl/atl-module-classes.md) bakın.

> [!IMPORTANT]
> Bu sınıf ve üyeleri, Windows Runtime'da çalıştırılan uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
class CComModule : public _ATL_MODULE
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CcomModule::GetClassObject](#getclassobject)|Belirtilen bir CLSID nesnesi oluşturur. Sadece DL'ler için.|
|[CcomModule::GetModuleInstance](#getmoduleinstance)|`m_hInst` döndürür.|
|[CcomModule::GetResourceInstance](#getresourceinstance)|`m_hInstResource` döndürür.|
|[Ccommodule::GetTypeLibInstance](#gettypelibinstance)|`m_hInstTypeLib` döndürür.|
|[CComModule::Init](#init)|Veri üyelerini ilk olarak karşılar.|
|[CComModule::RegisterClassHelper](#registerclasshelper)|Bir nesnenin standart sınıf kaydını sistem kayıt defterine girer.|
|[CComModule::RegisterClassObjects](#registerclassobjects)|Sınıf nesnesini kaydeder. Sadece EXE'ler için.|
|[CcomModule::RegisterServer](#registerserver)|Nesne eşlenindeki her nesne için sistem kayıt defterini güncelleştirir.|
|[Ccommodule::RegisterTypeLib](#registertypelib)|Tür kitaplığını kaydeder.|
|[CComModule::RevokeClassObjects](#revokeclassobjects)|Sınıf nesnesini iptal eder. Sadece EXE'ler için.|
|[CcomModule::Dönem](#term)|Veri üyelerini serbest bırakır.|
|[CComModule::UnregisterClassHelper](#unregisterclasshelper)|Bir nesnenin standart sınıf kaydını sistem kayıt defterinden kaldırır.|
|[CComModule::UnregisterServer](#unregisterserver)|Nesne eşlemindeki her nesneyi kaydeder.|
|[CComModule::UpdateRegistryClass](#updateregistryclass)|Nesnenin standart sınıf kaydını kaydeder veya kaydeder.|
|[CComModule::UpdateRegistryFromResourceD](#updateregistryfromresourced)|Bir nesneyi kaydetmek veya kaydetmek için belirtilen kaynakta bulunan komut dosyasını çalıştırın.|
|[CComModule::UpdateRegistryFromResourceS](#updateregistryfromresources)|Statik olarak ATL Kayıt Defteri Bileşenine bağlanır. Bir nesneyi kaydetmek veya kaydetmek için belirtilen kaynakta bulunan komut dosyasını çalıştırın.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CComModülü::m_csObjMap](#m_csobjmap)|Nesne eşleme bilgilerine senkronize erişim sağlar.|
|[CComModülü::m_csTypeInfoHolder](#m_cstypeinfoholder)|Tür kitaplığı bilgilerine eşitlenmiş erişim sağlar.|
|[CComModülü::m_csWindowCreate](#m_cswindowcreate)|Pencere oluşturma sırasında kullanılan pencere sınıfı bilgilerine ve statik verilere senkronize erişim sağlar.|
|[CComModülü:m_hInst](#m_hinst)|Modül örneğinin tutamacını içerir.|
|[CComModülü::m_hInstResource](#m_hinstresource)|Varsayılan olarak, modül örneğinin tutamacını içerir.|
|[CComModülü::m_hInstTypeLib](#m_hinsttypelib)|Varsayılan olarak, modül örneğinin tutamacını içerir.|
|[CComModülü::m_pObjMap](#m_pobjmap)|Modül örneği tarafından tutulan nesne haritasına işaret edilir.|

## <a name="remarks"></a>Açıklamalar

> [!NOTE]
> Bu sınıf amortismana sokuldu ve ATL kod oluşturma sihirbazları artık [CAtlAutoThreadModule](../../atl/reference/catlautothreadmodule-class.md) ve [CAtlModule](../../atl/reference/catlmodule-class.md) türetilmiş sınıfları kullanıyor. Daha fazla bilgi için [ATL Modül Sınıfları'na](../../atl/atl-module-classes.md) bakın. Aşağıdaki bilgiler, ATL'nin eski sürümleriyle oluşturulan uygulamalarda kullanılmak üzeredir. `CComModule`hala geriye dönük yetenek için ATL bir parçasıdır.

`CComModule`istemcinin modülün bileşenlerine erişmesine izin veren bir COM sunucu modülü uygular. `CComModule`hem DLL (süreç içi) hem de EXE (yerel) modülleri destekler.

Bir `CComModule` örnek, sınıf nesnesi tanımları kümesini korumak için bir nesne eşlemi kullanır. Bu nesne eşlemi bir `_ATL_OBJMAP_ENTRY` dizi yapı olarak uygulanır ve aşağıdakiler için bilgiler içerir:

- Sistem kayıt defterine nesne açıklamaları girme ve kaldırma.

- Nesneleri bir sınıf fabrikası nda anında alma.

- Bir istemci ve bileşendeki kök nesne arasında iletişim kurma.

- Sınıf nesnelerinin yaşam boyu yönetimini gerçekleştirme.

ATL COM AppWizard'ı çalıştırdığınızda, sihirbaz `_Module`otomatik olarak `CComModule` ondan türetilen bir sinif veya bir sınıf oluşturur. ATL Proje Sihirbazı hakkında daha fazla bilgi için, [ATL Projesi Oluşturma](../../atl/reference/creating-an-atl-project.md)makalesine bakın.

Buna ek `CComModule`olarak, ATL [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md)sağlar , EXEs ve Windows hizmetleri için bir daire modeli modülü uygular. Modülünüzden, `CComAutoThreadModule` birden çok dairede nesne oluşturmak istediğinizde türetin.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[_ATL_MODULE](atl-typedefs.md#_atl_module)

[CAtlModülü](../../atl/reference/catlmodule-class.md)

[CAtlModuleT](../../atl/reference/catlmodulet-class.md)

`CComModule`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlbase.h

## <a name="ccommodulegetclassobject"></a><a name="getclassobject"></a>CcomModule::GetClassObject

ATL 7.0 itibariyle, `CComModule` eskidir: daha fazla bilgi için [ATL Modül Sınıfları](../../atl/atl-module-classes.md) bakın.

```
HRESULT GetClassObject(
    REFCLSID rclsid,
    REFIID riid,
    LPVOID* ppv) throw();
```

### <a name="parameters"></a>Parametreler

*rclsid*<br/>
[içinde] Oluşturulacak nesnenin CLSID'si.

*Riid*<br/>
[içinde] İstenen arabirimin IID'si.

*Ppv*<br/>
[çıkış] *riid*tarafından tanımlanan arabirim işaretçisine işaretçi. Nesne bu arabirimi desteklemiyorsa, *PPV* NULL olarak ayarlanır.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

Belirtilen CLSID bir nesne oluşturur ve bu nesneye bir arabirim işaretçisi alır.

`GetClassObject`yalnızca DL'ler için kullanılabilir.

## <a name="ccommodulegetmoduleinstance"></a><a name="getmoduleinstance"></a>CcomModule::GetModuleInstance

ATL 7.0 itibariyle, `CComModule` eskidir: daha fazla bilgi için [ATL Modül Sınıfları](../../atl/atl-module-classes.md) bakın.

```
HINSTANCE GetModuleInstance() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Bu modülü tanımlayan HINSTANCE.

### <a name="remarks"></a>Açıklamalar

[m_hInst](#m_hinst) veri üyesini döndürür.

## <a name="ccommodulegetresourceinstance"></a><a name="getresourceinstance"></a>CcomModule::GetResourceInstance

ATL 7.0 itibariyle, `CComModule` eskidir: daha fazla bilgi için [ATL Modül Sınıfları](../../atl/atl-module-classes.md) bakın.

```
HINSTANCE GetResourceInstance() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Bir HINSTANCE.

### <a name="remarks"></a>Açıklamalar

[m_hInstResource](#m_hinstresource) veri üyesini döndürür.

## <a name="ccommodulegettypelibinstance"></a><a name="gettypelibinstance"></a>Ccommodule::GetTypeLibInstance

ATL 7.0 itibariyle, `CComModule` eskidir: daha fazla bilgi için [ATL Modül Sınıfları](../../atl/atl-module-classes.md) bakın.

```
HINSTANCE GetTypeLibInstance() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Bir HINSTANCE.

### <a name="remarks"></a>Açıklamalar

[m_hInstTypeLib](#m_hinsttypelib) veri üyesini döndürür.

## <a name="ccommoduleinit"></a><a name="init"></a>CComModule::Init

ATL 7.0 itibariyle, `CComModule` eskidir: daha fazla bilgi için [ATL Modül Sınıfları](../../atl/atl-module-classes.md) bakın.

```
HRESULT Init(
    _ATL_OBJMAP_ENTRY* p,
    HINSTANCE h,
    const GUID* plibid = NULL) throw();
```

### <a name="parameters"></a>Parametreler

*P*<br/>
[içinde] Nesne eşleme girişleri dizisiiçin bir işaretçi.

*H*<br/>
[içinde] HINSTANCE geçti `DLLMain` veya `WinMain`.

*plibid*<br/>
[içinde] Projeyle ilişkili tür kitaplığı LIBID için bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

Tüm veri üyelerini ilk olarak karşılar.

## <a name="ccommodulem_csobjmap"></a><a name="m_csobjmap"></a>CComModülü::m_csObjMap

ATL 7.0 itibariyle, `CComModule` eskidir: daha fazla bilgi için [ATL Modül Sınıfları](../../atl/atl-module-classes.md) bakın.

```
CRITICAL_SECTION m_csObjMap;
```

### <a name="remarks"></a>Açıklamalar

Nesne eşlenine senkronize erişim sağlar.

## <a name="ccommodulem_cstypeinfoholder"></a><a name="m_cstypeinfoholder"></a>CComModülü::m_csTypeInfoHolder

ATL 7.0 itibariyle, `CComModule` eskidir: daha fazla bilgi için [ATL Modül Sınıfları](../../atl/atl-module-classes.md) bakın.

```
CRITICAL_SECTION m_csTypeInfoHolder;
```

### <a name="remarks"></a>Açıklamalar

Tür kitaplığına eşitlenmiş erişim sağlar.

## <a name="ccommodulem_cswindowcreate"></a><a name="m_cswindowcreate"></a>CComModülü::m_csWindowCreate

ATL 7.0 itibariyle, `CComModule` eskidir: daha fazla bilgi için [ATL Modül Sınıfları](../../atl/atl-module-classes.md) bakın.

```
CRITICAL_SECTION m_csWindowCreate;
```

### <a name="remarks"></a>Açıklamalar

Pencere sınıfı bilgilerine ve pencere oluşturma sırasında kullanılan statik verilere senkronize erişim sağlar.

## <a name="ccommodulem_hinst"></a><a name="m_hinst"></a>CComModülü:m_hInst

ATL 7.0 itibariyle, `CComModule` eskidir: daha fazla bilgi için [ATL Modül Sınıfları](../../atl/atl-module-classes.md) bakın.

```
HINSTANCE m_hInst;
```

### <a name="remarks"></a>Açıklamalar

Modül örneğinin tutamacını içerir.

[Init](#init) yöntemi, `m_hInst` geçirilen tutamak `DLLMain` için ayarlar veya `WinMain`.

## <a name="ccommodulem_hinstresource"></a><a name="m_hinstresource"></a>CComModülü::m_hInstResource

ATL 7.0 itibariyle, `CComModule` eskidir: daha fazla bilgi için [ATL Modül Sınıfları](../../atl/atl-module-classes.md) bakın.

```
HINSTANCE m_hInstResource;
```

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, modül örneğinin tutamacını içerir.

[Init](#init) yöntemi, `m_hInstResource` geçirilen tutamak `DLLMain` için ayarlar veya `WinMain`. Bir kaynağa `m_hInstResource` tanıtıcıyı açıkça ayarlayabilirsiniz.

[GetResourceInstance](#getresourceinstance) yöntemi, depolanan tanıtıcıyı `m_hInstResource`döndürür.

## <a name="ccommodulem_hinsttypelib"></a><a name="m_hinsttypelib"></a>CComModülü::m_hInstTypeLib

ATL 7.0 itibariyle, `CComModule` eskidir: daha fazla bilgi için [ATL Modül Sınıfları](../../atl/atl-module-classes.md) bakın.

```
HINSTANCE m_hInstTypeLib;
```

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, modül örneğinin tutamacını içerir.

[Init](#init) yöntemi, `m_hInstTypeLib` geçirilen tutamak `DLLMain` için ayarlar veya `WinMain`. Bir tür kitaplığı için tanıtıcı açıkça ayarlayabilirsiniz. `m_hInstTypeLib`

[GetTypeLibInstance](#gettypelibinstance) yöntemi depolanan tutamacı `m_hInstTypeLib`döndürür.

## <a name="ccommodulem_pobjmap"></a><a name="m_pobjmap"></a>CComModülü::m_pObjMap

ATL 7.0 itibariyle, `CComModule` eskidir: daha fazla bilgi için [ATL Modül Sınıfları](../../atl/atl-module-classes.md) bakın.

```
_ATL_OBJMAP_ENTRY* m_pObjMap;
```

### <a name="remarks"></a>Açıklamalar

Modül örneği tarafından tutulan nesne haritasına işaret edilir.

## <a name="ccommoduleregisterclasshelper"></a><a name="registerclasshelper"></a>CComModule::RegisterClassHelper

ATL 7.0 itibariyle, `CComModule` eskidir: daha fazla bilgi için [ATL Modül Sınıfları](../../atl/atl-module-classes.md) bakın.

```
ATL_DEPRECATED HRESULT RegisterClassHelper(
    const CLSID& clsid,
    LPCTSTR lpszProgID,
    LPCTSTR lpszVerIndProgID,
    UINT nDescID,
    DWORD dwFlags);
```

### <a name="parameters"></a>Parametreler

*Clsıd*<br/>
[içinde] Kaydedilecek nesnenin CLSID'si.

*lpszProgID*<br/>
[içinde] Nesneyle ilişkili ProgID.

*lpszVerIndProgID*<br/>
[içinde] Nesneyle ilişkili sürümden bağımsız ProgID.

*nDescID*<br/>
[içinde] Nesnenin açıklaması için bir dize kaynağının tanımlayıcısı.

*Dwflags*<br/>
[içinde] Kayıt defterine girmek için iş parçacığı modelini belirtir. Olası değerler THREADFLAGS_APARTMENT, THREADFLAGS_BOTH veya AUTPRXFLAG'dır.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

Bir nesnenin standart sınıf kaydını sistem kayıt defterine girer.

[UpdateRegistryClass](#updateregistryclass) yöntemi `RegisterClassHelper`çağırır.

## <a name="ccommoduleregisterclassobjects"></a><a name="registerclassobjects"></a>CComModule::RegisterClassObjects

ATL 7.0 itibariyle, `CComModule` eskidir: daha fazla bilgi için [ATL Modül Sınıfları](../../atl/atl-module-classes.md) bakın.

```
HRESULT RegisterClassObjects(DWORD dwClsContext, DWORD dwFlags) throw();
```

### <a name="parameters"></a>Parametreler

*dwClsBağlam*<br/>
[içinde] Sınıf nesnesinin çalıştırılacak olduğu bağlamı belirtir. Olası değerler CLSCTX_INPROC_SERVER, CLSCTX_INPROC_HANDLER veya CLSCTX_LOCAL_SERVER. Bu değerlerin açıklaması için Windows SDK'daki [CLSCTX](/windows/win32/api/wtypesbase/ne-wtypesbase-clsctx) bölümüne bakın.

*Dwflags*<br/>
[içinde] Sınıf nesnesine bağlantı türlerini belirler. Olası değerler REGCLS_SINGLEUSE, REGCLS_MULTIPLEUSE veya REGCLS_MULTI_SEPARATE. Bu değerlerin açıklaması için Windows SDK'daki [REGCLS'e](/windows/win32/api/combaseapi/ne-combaseapi-regcls) bakın.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

Diğer uygulamaların bağlanabilmesi için EXE sınıfı nesnesini OLE ile kaydeder. Bu yöntem yalnızca EX'ler için kullanılabilir.

## <a name="ccommoduleregisterserver"></a><a name="registerserver"></a>CcomModule::RegisterServer

ATL 7.0 itibariyle, `CComModule` eskidir: daha fazla bilgi için [ATL Modül Sınıfları](../../atl/atl-module-classes.md) bakın.

```
HRESULT RegisterServer(
    BOOL bRegTypeLib = FALSE,
    const CLSID* pCLSID = NULL) throw();
```

### <a name="parameters"></a>Parametreler

*bRegTypeLib*<br/>
[içinde] Tür kitaplığın kayıtlı olup olmayacağını gösterir. Varsayılan değer FALSE'dur.

*pCLSID*<br/>
[içinde] Kaydedilecek nesnenin CLSID'sine işaret edin. NULL (varsayılan değer) varsa, nesne eşlemindeki tüm nesneler kaydedilir.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

*pCLSID* parametreye bağlı olarak, sistem kayıt defterini tek bir sınıf nesnesi veya nesne eşlemedeki tüm nesneler için güncelleştirir.

*bRegTypeLib* TRUE ise, tür kitaplığı bilgileri de güncelleştirilir.

Nesne haritasına giriş innasıl eklendirileceksiniz hakkında bilgi için [OBJECT_ENTRY_AUTO](object-map-macros.md#object_entry_auto) bakın.

`RegisterServer`bir DLL veya `DLLRegisterServer` `/RegServer` komut satırı seçeneği `WinMain` ile bir EXE çalışması için otomatik olarak çağrılacaktır.

## <a name="ccommoduleregistertypelib"></a><a name="registertypelib"></a>Ccommodule::RegisterTypeLib

ATL 7.0 itibariyle, `CComModule` eskidir: daha fazla bilgi için [ATL Modül Sınıfları](../../atl/atl-module-classes.md) bakın.

```
HRESULT RegisterTypeLib() throw();
HRESULT RegisterTypeLib(LPCTSTR lpszIndex) throw();
```

### <a name="parameters"></a>Parametreler

*lpszIndex*<br/>
[içinde] TypeLIB kaynağının `N` insa dizini, biçiminde dize. `"\\N"`

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

Sistem kayıt defterine tür kitaplığı hakkında bilgi ekler.

Modül örneği birden çok tür kitaplığı içeriyorsa, hangi tür kitaplığın kullanılması gerektiğini belirtmek için bu yöntemin ikinci sürümünü kullanın.

## <a name="ccommodulerevokeclassobjects"></a><a name="revokeclassobjects"></a>CComModule::RevokeClassObjects

ATL 7.0 itibariyle, `CComModule` eskidir: daha fazla bilgi için [ATL Modül Sınıfları](../../atl/atl-module-classes.md) bakın.

```
HRESULT RevokeClassObjects() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

Sınıf nesnesini kaldırır. Bu yöntem yalnızca EX'ler için kullanılabilir.

## <a name="ccommoduleterm"></a><a name="term"></a>CcomModule::Dönem

ATL 7.0 itibariyle, `CComModule` eskidir: daha fazla bilgi için [ATL Modül Sınıfları](../../atl/atl-module-classes.md) bakın.

```
void Term() throw();
```

### <a name="remarks"></a>Açıklamalar

Tüm veri üyelerini serbest bırakır.

## <a name="ccommoduleunregisterclasshelper"></a><a name="unregisterclasshelper"></a>CComModule::UnregisterClassHelper

ATL 7.0 itibariyle, `CComModule` eskidir: daha fazla bilgi için [ATL Modül Sınıfları](../../atl/atl-module-classes.md) bakın.

```
ATL_DEPRECATED HRESULT UnregisterClassHelper(
    const CLSID& clsid,
    LPCTSTR lpszProgID,
    LPCTSTR lpszVerIndProgID);
```

### <a name="parameters"></a>Parametreler

*Clsıd*<br/>
[içinde] Nesnenin CLSID kayıtsız olmak.

*lpszProgID*<br/>
[içinde] Nesneyle ilişkili ProgID.

*lpszVerIndProgID*<br/>
[içinde] Nesneyle ilişkili sürümden bağımsız ProgID.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

Bir nesnenin standart sınıf kaydını sistem kayıt defterinden kaldırır.

[UpdateRegistryClass](#updateregistryclass) yöntemi `UnregisterClassHelper`çağırır.

## <a name="ccommoduleunregisterserver"></a><a name="unregisterserver"></a>CComModule::UnregisterServer

ATL 7.0 itibariyle, `CComModule` eskidir: daha fazla bilgi için [ATL Modül Sınıfları](../../atl/atl-module-classes.md) bakın.

```
HRESULT UnregisterServer(const CLSID* pCLSID = NULL) throw ();
inline HRESULT UnregisterServer(BOOL bUnRegTypeLib, const CLSID* pCLSID = NULL) throw ();
```

### <a name="parameters"></a>Parametreler

*bUnRegTypeLib*<br/>
TRUE ise, tür kitaplığı da kayıtsız.

*pCLSID*<br/>
Nesnenin CLSID'sine kayıtsız kalmak için işaret. NULL (varsayılan değer) varsa, nesne eşlemindeki tüm nesneler kayıtsız kalır.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

*pCLSID* parametreye bağlı olarak, tek bir sınıf nesnesinin veya nesne eşlemedeki tüm nesnelerin kaydını silintir.

`UnregisterServer`bir DLL veya `DLLUnregisterServer` `/UnregServer` komut satırı seçeneği `WinMain` ile bir EXE çalışması için otomatik olarak çağrılacaktır.

Nesne haritasına giriş innasıl eklendirileceksiniz hakkında bilgi için [OBJECT_ENTRY_AUTO](object-map-macros.md#object_entry_auto) bakın.

## <a name="ccommoduleupdateregistryclass"></a><a name="updateregistryclass"></a>CComModule::UpdateRegistryClass

ATL 7.0 itibariyle, `CComModule` eskidir: daha fazla bilgi için [ATL Modül Sınıfları](../../atl/atl-module-classes.md) bakın.

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

*Clsıd*<br/>
Kayıtlı veya kayıtsız olması nesnenin CLSID.

*lpszProgID*<br/>
Nesneyle ilişkili ProgID.

*lpszVerIndProgID*<br/>
Nesneyle ilişkili sürümden bağımsız ProgID.

*nDescID*<br/>
Nesnenin açıklaması için dize kaynağının tanımlayıcısı.

*szDesc*<br/>
Nesnenin açıklamasını içeren bir dize.

*Dwflags*<br/>
Kayıt defterine girmek için iş parçacığı modelini belirtir. Olası değerler THREADFLAGS_APARTMENT, THREADFLAGS_BOTH veya AUTPRXFLAG'dır.

*bKayıt*<br/>
Nesnenin kaydedilip kaydedilmemesi gerektiğini gösterir.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

*bRegister* TRUE ise, bu yöntem nesnenin standart sınıf kaydını sistem kayıt defterine girer.

*bRegister* FALSE ise, nesnenin kaydını kaldırır.

*bRegister*değerine bağlı olarak, `UpdateRegistryClass` [RegisterClassHelper veya UnregisterClassHelper](#registerclasshelper) aramaları. [UnregisterClassHelper](#unregisterclasshelper)

[DECLARE_REGISTRY](registry-macros.md#declare_registry) makrobelirterek, `UpdateRegistryClass` nesne haritanız işlendiğinde otomatik olarak çağrılacaktır.

## <a name="ccommoduleupdateregistryfromresourced"></a><a name="updateregistryfromresourced"></a>CComModule::UpdateRegistryFromResourceD

ATL 7.0 itibariyle, `CComModule` eskidir: daha fazla bilgi için [ATL Modül Sınıfları](../../atl/atl-module-classes.md) bakın.

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
[içinde] Kaynak adı.

*nResID*<br/>
[içinde] Kaynak kimliği.

*bKayıt*<br/>
[içinde] Nesnenin kaydedilip kaydedilmemesi gerektiğini gösterir.

*pMapEntries*<br/>
[içinde] Komut dosyasının değiştirilebilir parametreleri ile ilişkili değerleri depolama değiştirme eşlemi için bir işaretçi. ATL otomatik `%MODULE%`olarak kullanır. Ek değiştirilebilir parametreleri kullanmak için ayrıntılar için Açıklamalar'a bakın. Aksi takdirde, NULL varsayılan değerini kullanın.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

*lpszRes* veya *nResID*tarafından belirtilen kaynakta bulunan komut dosyasını çalıştırın.

*bRegister* TRUE ise, bu yöntem nesneyi sistem kayıt defterine kaydeder; aksi takdirde, nesneyi unregisters.

[DECLARE_REGISTRY_RESOURCE](registry-macros.md#declare_registry_resource) veya [DECLARE_REGISTRY_RESOURCEID](registry-macros.md#declare_registry_resourceid) makro belirterek, `UpdateRegistryFromResourceD` nesne haritanız işlendiğinde otomatik olarak çağrılacaktır.

> [!NOTE]
> Çalışma zamanında değiştirme değerlerini değiştirmek için DECLARE_REGISTRY_RESOURCE veya DECLARE_REGISTRY_RESOURCEID makrobelirtmeyin. Bunun yerine, her `_ATL_REGMAP_ENTRIES` girişin çalışma zamanında yer tutucuyu değiştirmek için bir değerle eşleştirilmiş değişken bir yer tutucu içerdiği bir dizi yapı oluşturun. Sonra `UpdateRegistryFromResourceD`arama , *pMapEntries* parametresi için dizi geçen. Bu, `_ATL_REGMAP_ENTRIES` yapılardaki tüm değiştirme değerlerini Kayıt Defteri'nin değiştirme haritasına ekler.

> [!NOTE]
> ATL Kayıt Defteri Bileşenine (Registrar) statik olarak bağlanmak için [bkz.](#updateregistryfromresources)

Değiştirilebilir parametreler ve komut dosyası hakkında daha fazla bilgi [için, ATL Kayıt Defteri Bileşeni (Registrar)](../../atl/atl-registry-component-registrar.md)makalesine bakın.

## <a name="ccommoduleupdateregistryfromresources"></a><a name="updateregistryfromresources"></a>CComModule::UpdateRegistryFromResourceS

ATL 7.0 itibariyle, `CComModule` eskidir: daha fazla bilgi için [ATL Modül Sınıfları](../../atl/atl-module-classes.md) bakın.

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
[içinde] Kaynak adı.

*nResID*<br/>
[içinde] Kaynak kimliği.

*bKayıt*<br/>
[içinde] Kaynak komut dosyasının kaydedilip kaydedilmemesi gerektiğini gösterir.

*pMapEntries*<br/>
[içinde] Komut dosyasının değiştirilebilir parametreleri ile ilişkili değerleri depolama değiştirme eşlemi için bir işaretçi. ATL otomatik `%MODULE%`olarak kullanır. Ek değiştirilebilir parametreleri kullanmak için ayrıntılar için Açıklamalar'a bakın. Aksi takdirde, NULL varsayılan değerini kullanın.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

ATL Kayıt Defteri Bileşeni `UpdateRegistryFromResourceS` (Registrar) statik bir bağlantı oluşturur dışında [UpdateRegistryFromResourceD](#updateregistryfromresourced) benzer.

`UpdateRegistryFromResourceS`*pch.h* 'nize (Visual Studio 2017 `#define _ATL_STATIC_REGISTRY` ve daha önce*stdafx.h)* eklemeniz koşuluyla, nesne haritanız işlendiğinde otomatik olarak çağrılacaktır.

> [!NOTE]
> Çalışma zamanında değiştirme değerlerini değiştirmek için [DECLARE_REGISTRY_RESOURCE](registry-macros.md#declare_registry_resource) veya [DECLARE_REGISTRY_RESOURCEID](registry-macros.md#declare_registry_resourceid) makro belirtmeyin. Bunun yerine, her `_ATL_REGMAP_ENTRIES` girişin çalışma zamanında yer tutucuyu değiştirmek için bir değerle eşleştirilmiş değişken bir yer tutucu içerdiği bir dizi yapı oluşturun. Sonra `UpdateRegistryFromResourceS`arama , *pMapEntries* parametresi için dizi geçen. Bu, `_ATL_REGMAP_ENTRIES` yapılardaki tüm değiştirme değerlerini Kayıt Defteri'nin değiştirme haritasına ekler.

Değiştirilebilir parametreler ve komut dosyası hakkında daha fazla bilgi [için, ATL Kayıt Defteri Bileşeni (Registrar)](../../atl/atl-registry-component-registrar.md)makalesine bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
