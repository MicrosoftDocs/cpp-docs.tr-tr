---
title: CComAutoThreadModule Sınıfı
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
ms.openlocfilehash: 391354c5672cf15c0286491619a13c6005493cfa
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81321060"
---
# <a name="ccomautothreadmodule-class"></a>CComAutoThreadModule Sınıfı

ATL 7.0 itibariyle, `CComAutoThreadModule` eskidir: daha fazla bilgi için [ATL Modül Sınıfları](../../atl/atl-module-classes.md) bakın.

> [!IMPORTANT]
> Bu sınıf ve üyeleri, Windows Runtime'da çalıştırılan uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
template <class ThreadAllocator = CComSimpleThreadAllocator>
class CComAutoThreadModule : public CComModule
```

#### <a name="parameters"></a>Parametreler

*ThreadAllocator*<br/>
[içinde] Sınıf yönetim iş parçacığı seçimi. Varsayılan değer [CComSimpleThreadAllocator'dur.](../../atl/reference/ccomsimplethreadallocator-class.md)

## <a name="members"></a>Üyeler

### <a name="methods"></a>Yöntemler

|||
|-|-|
|[Createınstance](#createinstance)|Bir iş parçacığı seçer ve sonra ilişkili dairede bir nesne oluşturur.|
|[DefaultThreads alın](#getdefaultthreads)|(Statik) Dinamik olarak işlemci sayısına göre modül için iş parçacığı sayısını hesaplar.|
|[ınit](#init)|Modülün iş parçacıklarını oluşturur.|
|[Kilit](#lock)|Modülve geçerli iş parçacığı üzerinde kilit sayısı artışlar.|
|[Kilidini](#unlock)|Modülve geçerli iş parçacığı üzerinde kilit sayısı crecrements.|

### <a name="data-members"></a>Veri Üyeleri

### <a name="data-members"></a>Veri Üyeleri

|||
|-|-|
|[dwThreadID](#dwthreadid)|Geçerli iş parçacığının tanımlayıcısını içerir.|
|[m_Allocator](#m_allocator)|İş parçacığı seçimini yönetir.|
|[m_nThreads](#m_nthreads)|Modüldeki iş parçacığı sayısını içerir.|
|[m_pApartments](#m_papartments)|Modülün dairelerini yönetir.|

## <a name="remarks"></a>Açıklamalar

> [!NOTE]
> [CAtlAutoThreadModule](../../atl/reference/catlautothreadmodule-class.md) ve [CAtlModule](../../atl/reference/catlmodule-class.md) türetilmiş sınıflar tarafından değiştirildikten sonra, bu sınıf eskimiştir. Aşağıdaki bilgiler ATL'nin eski sürümlerinde kullanım içindir.

`CComAutoThreadModule`EX'ler ve Windows hizmetleri için bir iş parçacığı havuzu, apartman modeli COM sunucusu uygulamak için [CComModule](../../atl/reference/ccommodule-class.md) türetilmiştir. `CComAutoThreadModule`modüldeki her iş parçacığı için bir daire yönetmek için [CComApartment](../../atl/reference/ccomapartment-class.md) kullanır.

Modülünüzden, `CComAutoThreadModule` birden çok dairede nesne oluşturmak istediğinizde türetin. [CComClassFactoryAutoThread'i](../../atl/reference/ccomclassfactoryautothread-class.md) sınıf fabrikası olarak belirtmek için nesnenizin sınıf tanımına [DECLARE_CLASSFACTORY_AUTO_THREAD](aggregation-and-class-factory-macros.md#declare_classfactory_auto_thread) makroeklemeniz de eklemelisiniz.

Varsayılan olarak, ATL COM AppWizard (Visual Studio .NET'teki ATL Proje `CComModule`Sihirbazı) modülünüzden . Kullanmak `CComAutoThreadModule`için, sınıf tanımını değiştirin. Örneğin:

[!code-cpp[NVC_ATL_AxHost#2](../../atl/codesnippet/cpp/ccomautothreadmodule-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[_ATL_MODULE](atl-typedefs.md#_atl_module)

[CAtlModülü](../../atl/reference/catlmodule-class.md)

`IAtlAutoThreadModule`

[CAtlModuleT](../../atl/reference/catlmodulet-class.md)

[Catlautothreadmodulet](../../atl/reference/catlautothreadmodulet-class.md)

[Ccommodule](../../atl/reference/ccommodule-class.md)

`CComAutoThreadModule`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlbase.h

## <a name="ccomautothreadmodulecreateinstance"></a><a name="createinstance"></a>CcomAutoThreadModule::CreateInstance

ATL 7.0 itibariyle, `CComAutoThreadModule` eskidir: daha fazla bilgi için [ATL Modül Sınıfları](../../atl/atl-module-classes.md) bakın.

```
HRESULT CreateInstance(
    void* pfnCreateInstance,
    REFIID riid,
    void** ppvObj);
```

### <a name="parameters"></a>Parametreler

*pfnCreateInstance*<br/>
[içinde] Oluşturucu işlevi için bir işaretçi.

*Riid*<br/>
[içinde] İstenen arabirimin IID'si.

*ppvObj*<br/>
[çıkış] *riid*tarafından tanımlanan arabirim işaretçisine işaretçi. Nesne bu arabirimi desteklemiyorsa, *ppvObj* NULL olarak ayarlanır.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

Bir iş parçacığı seçer ve sonra ilişkili dairede bir nesne oluşturur.

## <a name="ccomautothreadmoduledwthreadid"></a><a name="dwthreadid"></a>CComAutoThreadModule::dwThreadID

ATL 7.0 itibariyle, `CComAutoThreadModule` eskidir: daha fazla bilgi için [ATL Modül Sınıfları](../../atl/atl-module-classes.md) bakın.

```
DWORD dwThreadID;
```

### <a name="remarks"></a>Açıklamalar

Geçerli iş parçacığının tanımlayıcısını içerir.

## <a name="ccomautothreadmodulegetdefaultthreads"></a><a name="getdefaultthreads"></a>CComAutoThreadModule::GetDefaultThreads

ATL 7.0 itibariyle, `CComAutoThreadModule` eskidir: daha fazla bilgi için [ATL Modül Sınıfları](../../atl/atl-module-classes.md) bakın.

```
static int GetDefaultThreads();
```

### <a name="return-value"></a>Dönüş Değeri

EXE modülünde oluşturulacak iş parçacığı sayısı.

### <a name="remarks"></a>Açıklamalar

Bu statik işlev, işlemci sayısına bağlı olarak EXE modülü için maksimum iş parçacığı sayısını dinamik olarak hesaplar. Varsayılan olarak, bu iade değeri iş parçacığı oluşturmak için [Init](#init) yöntemine geçirilir.

## <a name="ccomautothreadmoduleinit"></a><a name="init"></a>CComAutoThreadModule::Init

ATL 7.0 itibariyle, `CComAutoThreadModule` eskidir: daha fazla bilgi için [ATL Modül Sınıfları](../../atl/atl-module-classes.md) bakın.

```
HRESULT Init(
    _ATL_OBJMAP_ENTRY* p,
    HINSTANCE h,
    const GUID* plibid = NULL,
    int nThreads = GetDefaultThreads());
```

### <a name="parameters"></a>Parametreler

*P*<br/>
[içinde] Nesne eşleme girişleri dizisiiçin bir işaretçi.

*H*<br/>
[içinde] HINSTANCE geçti `DLLMain` veya `WinMain`.

*plibid*<br/>
[içinde] Projeyle ilişkili tür kitaplığı LIBID için bir işaretçi.

*nThreads*<br/>
[içinde] Oluşturulacak iş parçacığı sayısı. Varsayılan olarak, *nThreads* [GetDefaultThreads tarafından döndürülen değerdir.](#getdefaultthreads)

### <a name="remarks"></a>Açıklamalar

Veri üyelerini ilk olarak karşılar ve *nThreads*tarafından belirtilen iş parçacığı sayısını oluşturur.

## <a name="ccomautothreadmodulelock"></a><a name="lock"></a>CcomAutoThreadModule::Kilit

ATL 7.0 itibariyle, `CComAutoThreadModule` eskidir: daha fazla bilgi için [ATL Modül Sınıfları](../../atl/atl-module-classes.md) bakın.

```
LONG Lock();
```

### <a name="return-value"></a>Dönüş Değeri

Tanılama veya test için yararlı olabilecek bir değer.

### <a name="remarks"></a>Açıklamalar

Modül ve geçerli iş parçacığı için kilit sayısı üzerinde atomik bir artış gerçekleştirir. `CComAutoThreadModule`istemcilerin modüle erişip erişmediğini belirlemek için modül kilidi sayısını kullanır. Geçerli iş parçacığı nın kilit sayısı istatistiksel amaçlar için kullanılır.

## <a name="ccomautothreadmodulem_allocator"></a><a name="m_allocator"></a>CComAutoThreadModule::m_Allocator

ATL 7.0 itibariyle, `CComAutoThreadModule` eskidir: daha fazla bilgi için [ATL Modül Sınıfları](../../atl/atl-module-classes.md) bakın.

```
ThreadAllocator  m_Allocator;
```

### <a name="remarks"></a>Açıklamalar

İş parçacığı seçimini yöneten nesne. Varsayılan olarak, `ThreadAllocator` sınıf şablonparametresi [CComSimpleThreadAllocator](../../atl/reference/ccomsimplethreadallocator-class.md)olduğunu.

## <a name="ccomautothreadmodulem_nthreads"></a><a name="m_nthreads"></a>CComAutoThreadModule::m_nThreads

ATL 7.0 itibariyle, `CComAutoThreadModule` eskidir: daha fazla bilgi için [ATL Modül Sınıfları](../../atl/atl-module-classes.md) bakın.

```
int m_nThreads;
```

### <a name="remarks"></a>Açıklamalar

EXE modülündeki iş parçacığı sayısını içerir. [Init](#init) çağrıldığında, `m_nThreads` *nThreads* parametre değerine ayarlanır. Her iş parçacığının ilişkili dairesi bir [CComApartment](../../atl/reference/ccomapartment-class.md) nesnesi tarafından yönetilir.

## <a name="ccomautothreadmodulem_papartments"></a><a name="m_papartments"></a>CComAutoThreadModule::m_pApartments

ATL 7.0 itibariyle, `CComAutoThreadModule` eskidir: daha fazla bilgi için [ATL Modül Sınıfları](../../atl/atl-module-classes.md) bakın.

```
CComApartment* m_pApartments;
```

### <a name="remarks"></a>Açıklamalar

Her biri modülde bir daire yöneten [CComApartment](../../atl/reference/ccomapartment-class.md) nesnelerin bir dizi puan. Dizideki öğe sayısı [m_nThreads](#m_nthreads) üyeye dayanır.

## <a name="ccomautothreadmoduleunlock"></a><a name="unlock"></a>CcomAutoThreadModule::Kilidini

ATL 7.0 itibariyle, `CComAutoThreadModule` eskidir: daha fazla bilgi için [ATL Modül Sınıfları](../../atl/atl-module-classes.md) bakın.

```
LONG Unlock();
```

### <a name="return-value"></a>Dönüş Değeri

Tanılama veya test için yararlı olabilecek bir değer.

### <a name="remarks"></a>Açıklamalar

Modül ve geçerli iş parçacığı için kilit sayısı üzerinde atomik bir decrement gerçekleştirir. `CComAutoThreadModule`istemcilerin modüle erişip erişmediğini belirlemek için modül kilidi sayısını kullanır. Geçerli iş parçacığı nın kilit sayısı istatistiksel amaçlar için kullanılır.

Modül kilidi sayısı sıfıra ulaştığında, modül boşaltılabilir.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)<br/>
[Modül Sınıfları](../../atl/atl-module-classes.md)
