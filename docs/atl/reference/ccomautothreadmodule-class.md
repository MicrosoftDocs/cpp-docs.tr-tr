---
title: CComAutoThreadModule sınıfı
ms.date: 11/04/2016
f1_keywords:
- CComAutoThreadModule
- ATLBASE/ATL::CComAutoThreadModule
- ATLBASE/ATL::CreateInstance
- ATLBASE/ATL::GetDefaultThreads
- ATLBASE/ATL::Init
- ATLBASE/ATL::Lock
- ATLBASE/ATL::Unlock
- ATLBASE/ATL::dwThreadID
- ATLBASE/ATL::m_Allocator
- ATLBASE/ATL::m_nThreads
- ATLBASE/ATL::m_pApartments
helpviewer_keywords:
- CComAutoThreadModule class
- apartment model modules
ms.assetid: 13063ea5-a57e-4aac-97d3-227137262811
ms.openlocfilehash: 9b0fa685bf9a7de94b158bd62b00161c1b58562d
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57272002"
---
# <a name="ccomautothreadmodule-class"></a>CComAutoThreadModule sınıfı

ATL 7. 0'den itibaren `CComAutoThreadModule` artık kullanılmıyor: bkz [ATL modül sınıfları](../../atl/atl-module-classes.md) daha fazla ayrıntı için.

> [!IMPORTANT]
>  Bu sınıf ve üyelerine, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
template <class ThreadAllocator = CComSimpleThreadAllocator>
class CComAutoThreadModule : public CComModule
```

#### <a name="parameters"></a>Parametreler

*ThreadAllocator*<br/>
[in] İş parçacığı seçimi yönetme sınıfı. Varsayılan değer [CComSimpleThreadAllocator](../../atl/reference/ccomsimplethreadallocator-class.md).

## <a name="members"></a>Üyeler

### <a name="methods"></a>Yöntemler

|||
|-|-|
|[CreateInstance](#createinstance)|Bir iş parçacığı seçer ve ardından ilişkili grupta bir nesne oluşturur.|
|[GetDefaultThreads](#getdefaultthreads)|(Statik) Dinamik olarak işlemci sayısına göre modülü için iş parçacığı sayısını hesaplar.|
|[Init](#init)|Modülün iş parçacığı oluşturur.|
|[Kilit](#lock)|Modül ve geçerli iş parçacığı üzerinde kilit sayacını artırır.|
|[Kilit açma](#unlock)|Kilit sayısını azaltır ve geçerli iş parçacığı üzerinde modülü.|

### <a name="data-members"></a>Veri üyeleri

### <a name="data-members"></a>Veri üyeleri

|||
|-|-|
|[dwThreadID](#dwthreadid)|Geçerli iş parçacığının tanımlayıcısını içerir.|
|[m_Allocator](#m_allocator)|İş parçacığı seçimi yönetir.|
|[m_nThreads](#m_nthreads)|Modüldeki iş parçacığı sayısını içerir.|
|[m_pApartments](#m_papartments)|Modülün apartmanlar yönetir.|

## <a name="remarks"></a>Açıklamalar

> [!NOTE]
>  Bu sınıf tarafından değiştirilmiş eski [CAtlAutoThreadModule](../../atl/reference/catlautothreadmodule-class.md) ve [CAtlModule](../../atl/reference/catlmodule-class.md) türetilmiş sınıflar. Aşağıdaki bilgiler, ATL daha eski sürümleri ile kullanıma yöneliktir

`CComAutoThreadModule` öğesinden türetilen [CComModule](../../atl/reference/ccommodule-class.md) apartman modeli iş parçacığı havuza, COM sunucusu sağlar ve exe ve Windows Hizmetleri için uygulanacak. `CComAutoThreadModule` kullanan [CComApartment](../../atl/reference/ccomapartment-class.md) modüldeki her bir iş parçacığı için bir grup yönetmek için.

Modülünüzün öğesinden türetilen `CComAutoThreadModule` içinde birden çok apartmanlar nesneleri oluşturmak istediğinizde. Aynı zamanda içermelidir [DECLARE_CLASSFACTORY_AUTO_THREAD](aggregation-and-class-factory-macros.md#declare_classfactory_auto_thread) makrosu belirtmek için nesnenin sınıf tanımında [CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md) sınıf üreteci olarak.

Varsayılan olarak, ATL COM AppWizard (ATL projesi Sihirbazı'nda Visual Studio .NET), modülünden derleyeceği `CComModule`. Kullanılacak `CComAutoThreadModule`, sınıf tanımını değiştirin. Örneğin:

[!code-cpp[NVC_ATL_AxHost#2](../../atl/codesnippet/cpp/ccomautothreadmodule-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[_ATL_MODULE](atl-typedefs.md#_atl_module)

[CAtlModule](../../atl/reference/catlmodule-class.md)

`IAtlAutoThreadModule`

[CAtlModuleT](../../atl/reference/catlmodulet-class.md)

[CAtlAutoThreadModuleT](../../atl/reference/catlautothreadmodulet-class.md)

[CComModule](../../atl/reference/ccommodule-class.md)

`CComAutoThreadModule`

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlbase.h

##  <a name="createinstance"></a>  CComAutoThreadModule::CreateInstance

ATL 7. 0'den itibaren `CComAutoThreadModule` artık kullanılmıyor: bkz [ATL modül sınıfları](../../atl/atl-module-classes.md) daha fazla ayrıntı için.

```
HRESULT CreateInstance(
    void* pfnCreateInstance,
    REFIID riid,
    void** ppvObj);
```

### <a name="parameters"></a>Parametreler

*pfnCreateInstance*<br/>
[in] Bir oluşturucu işlevi işaretçisi.

*riid*<br/>
[in] İstenen arabirim Laboratuvardaki.

*ppvObj*<br/>
[out] Tarafından tanımlanan bir arabirim işaretçisi için bir işaretçi *riid*. Nesne bu arabirimi desteklemiyorsa *ppvObj* NULL olarak ayarlandı.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değerini.

### <a name="remarks"></a>Açıklamalar

Bir iş parçacığı seçer ve ardından ilişkili grupta bir nesne oluşturur.

##  <a name="dwthreadid"></a>  CComAutoThreadModule::dwThreadID

ATL 7. 0'den itibaren `CComAutoThreadModule` artık kullanılmıyor: bkz [ATL modül sınıfları](../../atl/atl-module-classes.md) daha fazla ayrıntı için.

```
DWORD dwThreadID;
```

### <a name="remarks"></a>Açıklamalar

Geçerli iş parçacığının tanımlayıcısını içerir.

##  <a name="getdefaultthreads"></a>  CComAutoThreadModule::GetDefaultThreads

ATL 7. 0'den itibaren `CComAutoThreadModule` artık kullanılmıyor: bkz [ATL modül sınıfları](../../atl/atl-module-classes.md) daha fazla ayrıntı için.

```
static int GetDefaultThreads();
```

### <a name="return-value"></a>Dönüş Değeri

EXE modülünde oluşturulacak iş parçacığı sayısı.

### <a name="remarks"></a>Açıklamalar

Bu statik işlev işlemci sayısına göre bir EXE modülü için iş parçacığı sayısını dinamik olarak hesaplar. Varsayılan olarak, bu dönüş değeri için geçirilen [Init](#init) iş parçacığı oluşturmak için yöntemi.

##  <a name="init"></a>  CComAutoThreadModule::Init

ATL 7. 0'den itibaren `CComAutoThreadModule` artık kullanılmıyor: bkz [ATL modül sınıfları](../../atl/atl-module-classes.md) daha fazla ayrıntı için.

```
HRESULT Init(
    _ATL_OBJMAP_ENTRY* p,
    HINSTANCE h,
    const GUID* plibid = NULL,
    int nThreads = GetDefaultThreads());
```

### <a name="parameters"></a>Parametreler

*p*<br/>
[in] Bir nesne eşleme girişleri dizisine bir işaretçi.

*h*<br/>
[in] Geçirilen HINSTANCE `DLLMain` veya `WinMain`.

*plibid*<br/>
[in] Projeyle ilişkili tür kitaplığının Kitaplık kimliği için bir işaretçi.

*nThreads*<br/>
[in] Oluşturulacak iş parçacığı sayısı. Varsayılan olarak, *nThreads* tarafından döndürülen değer [GetDefaultThreads](#getdefaultthreads).

### <a name="remarks"></a>Açıklamalar

Veri üyeleri başlatılır ve tarafından belirtilen iş parçacığı sayısını oluşturur *nThreads*.

##  <a name="lock"></a>  CComAutoThreadModule::Lock

ATL 7. 0'den itibaren `CComAutoThreadModule` artık kullanılmıyor: bkz [ATL modül sınıfları](../../atl/atl-module-classes.md) daha fazla ayrıntı için.

```
LONG Lock();
```

### <a name="return-value"></a>Dönüş Değeri

Tanılama için kullanışlı veya test olabilir bir değer.

### <a name="remarks"></a>Açıklamalar

Atomik bir artış ve geçerli iş parçacığı modülü için kilit sayacını gerçekleştirir. `CComAutoThreadModule` Modülün kilit sayacını istemciler modülü eriştiğiniz olup olmadığını belirlemek için kullanır. Geçerli iş parçacığı üzerinde kilit sayacını İstatistiksel amaçlar için kullanılır.

##  <a name="m_allocator"></a>  CComAutoThreadModule::m_Allocator

ATL 7. 0'den itibaren `CComAutoThreadModule` artık kullanılmıyor: bkz [ATL modül sınıfları](../../atl/atl-module-classes.md) daha fazla ayrıntı için.

```
ThreadAllocator  m_Allocator;
```

### <a name="remarks"></a>Açıklamalar

İş parçacığı seçimi yönetme nesne. Varsayılan olarak, `ThreadAllocator` sınıf şablonu parametresi [CComSimpleThreadAllocator](../../atl/reference/ccomsimplethreadallocator-class.md).

##  <a name="m_nthreads"></a>  CComAutoThreadModule::m_nThreads

ATL 7. 0'den itibaren `CComAutoThreadModule` artık kullanılmıyor: bkz [ATL modül sınıfları](../../atl/atl-module-classes.md) daha fazla ayrıntı için.

```
int m_nThreads;
```

### <a name="remarks"></a>Açıklamalar

EXE modülündeki iş parçacığı sayısını içerir. Zaman [Init](#init) çağrıldığında `m_nThreads` ayarlanır *nThreads* parametre değeri. Her iş parçacığının ilişkili grup tarafından yönetilen bir [CComApartment](../../atl/reference/ccomapartment-class.md) nesne.

##  <a name="m_papartments"></a>  CComAutoThreadModule::m_pApartments

ATL 7. 0'den itibaren `CComAutoThreadModule` artık kullanılmıyor: bkz [ATL modül sınıfları](../../atl/atl-module-classes.md) daha fazla ayrıntı için.

```
CComApartment* m_pApartments;
```

### <a name="remarks"></a>Açıklamalar

İşaret dizilerine [CComApartment](../../atl/reference/ccomapartment-class.md) nesneleri, her biri bir grupta modülü yönetir. Dizideki öğelerin sayısını temel alır [m_nThreads](#m_nthreads) üyesi.

##  <a name="unlock"></a>  CComAutoThreadModule::Unlock

ATL 7. 0'den itibaren `CComAutoThreadModule` artık kullanılmıyor: bkz [ATL modül sınıfları](../../atl/atl-module-classes.md) daha fazla ayrıntı için.

```
LONG Unlock();
```

### <a name="return-value"></a>Dönüş Değeri

Tanılama için kullanışlı veya test olabilir bir değer.

### <a name="remarks"></a>Açıklamalar

Atomik bir azaltma ve geçerli iş parçacığı modülü için kilit sayacını gerçekleştirir. `CComAutoThreadModule` Modülün kilit sayacını istemciler modülü eriştiğiniz olup olmadığını belirlemek için kullanır. Geçerli iş parçacığı üzerinde kilit sayacını İstatistiksel amaçlar için kullanılır.

Modülün kilit sayacını sıfır ulaştığında, modül kaldırılamıyor.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfına genel bakış](../../atl/atl-class-overview.md)<br/>
[Modül sınıfları](../../atl/atl-module-classes.md)
