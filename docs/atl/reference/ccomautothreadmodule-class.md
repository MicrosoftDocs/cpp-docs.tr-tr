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
ms.openlocfilehash: 405b05548cda2b2d379b849d9278293b8d747d2e
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88833796"
---
# <a name="ccomautothreadmodule-class"></a>CComAutoThreadModule sınıfı

ATL 7,0 itibariyle `CComAutoThreadModule` artık kullanılmıyor: daha fazla ayrıntı için bkz. [ATL modül sınıfları](../../atl/atl-module-classes.md) .

> [!IMPORTANT]
> Bu sınıf ve üyeleri Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Söz dizimi

```
template <class ThreadAllocator = CComSimpleThreadAllocator>
class CComAutoThreadModule : public CComModule
```

#### <a name="parameters"></a>Parametreler

*Threadayırıcı*<br/>
'ndaki İş parçacığı seçimini yöneten sınıf. Varsayılan değer [Ccomsimplethreadayırıcı](../../atl/reference/ccomsimplethreadallocator-class.md)' dır.

## <a name="members"></a>Üyeler

### <a name="methods"></a>Yöntemler

|İşlev|Açıklama|
|-|-|
|[CreateInstance](#createinstance)|Bir iş parçacığı seçer ve ardından ilişkili grupta bir nesne oluşturur.|
|[GetDefaultThreads](#getdefaultthreads)|Se Modül için iş parçacığı sayısını işlemci sayısına göre dinamik olarak hesaplar.|
|[Dengeleyici](#init)|Modülün iş parçacıklarını oluşturur.|
|[İne](#lock)|Modüldeki ve geçerli iş parçacığındaki kilit sayısını artırır.|
|[Kaldırın](#unlock)|Modüldeki ve geçerli iş parçacığındaki kilit sayısını azaltır.|

### <a name="data-members"></a>Veri üyeleri

|Veri üyesi|Açıklama|
|-|-|
|[dwThreadId](#dwthreadid)|Geçerli iş parçacığının tanımlayıcısını içerir.|
|[m_Allocator](#m_allocator)|İş parçacığı seçimini yönetir.|
|[m_nThreads](#m_nthreads)|Modüldeki iş parçacığı sayısını içerir.|
|[m_pApartments](#m_papartments)|Modülün apartmanları yönetir.|

## <a name="remarks"></a>Açıklamalar

> [!NOTE]
> Bu sınıf artık kullanılmıyor, [CAtlAutoThreadModule](../../atl/reference/catlautothreadmodule-class.md) ve [CAtlModule](../../atl/reference/catlmodule-class.md) türetilmiş sınıfları tarafından değiştirildi. Aşağıdaki bilgiler, ATL 'nin eski sürümleriyle kullanım içindir.

`CComAutoThreadModule` , EXEs ve Windows Hizmetleri için iş parçacığı tarafından havuza alınmış bir Grup modeli COM sunucusu uygulamak üzere [CComModule](../../atl/reference/ccommodule-class.md) ' den türetilir. `CComAutoThreadModule` modüldeki her iş parçacığı için bir grubu yönetmek üzere [CComApartment](../../atl/reference/ccomapartment-class.md) kullanır.

`CComAutoThreadModule`Birden çok apartmanlarda nesne oluşturmak istediğiniz sırada modülünüzü türetebilirsiniz. Ayrıca, sınıf fabrikası olarak [CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md) belirtmek için nesnenizin sınıf tanımına [declare_classfactory_auto_thread](aggregation-and-class-factory-macros.md#declare_classfactory_auto_thread) makrosunu da dahil etmeniz gerekir.

Varsayılan olarak, ATL COM AppWizard (Visual Studio .NET içindeki ATL Proje Sihirbazı), modülünüzü sınıfından türetecektir `CComModule` . Kullanmak için `CComAutoThreadModule` , sınıf tanımını değiştirin. Örnek:

[!code-cpp[NVC_ATL_AxHost#2](../../atl/codesnippet/cpp/ccomautothreadmodule-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[_ATL_MODULE](atl-typedefs.md#_atl_module)

[CAtlModule](../../atl/reference/catlmodule-class.md)

`IAtlAutoThreadModule`

[Catlmodület](../../atl/reference/catlmodulet-class.md)

[Catlautothreadmodület](../../atl/reference/catlautothreadmodulet-class.md)

[CComModule](../../atl/reference/ccommodule-class.md)

`CComAutoThreadModule`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlbase. h

## <a name="ccomautothreadmodulecreateinstance"></a><a name="createinstance"></a> CComAutoThreadModule:: CreateInstance

ATL 7,0 itibariyle `CComAutoThreadModule` artık kullanılmıyor: daha fazla ayrıntı için bkz. [ATL modül sınıfları](../../atl/atl-module-classes.md) .

```
HRESULT CreateInstance(
    void* pfnCreateInstance,
    REFIID riid,
    void** ppvObj);
```

### <a name="parameters"></a>Parametreler

*Pfncreateınstance*<br/>
'ndaki Oluşturucu işlevine yönelik bir işaretçi.

*riıd*<br/>
'ndaki İstenen arabirimin IID 'si.

*ppvObj*<br/>
dışı *Riıd*tarafından tanımlanan arabirim işaretçisine yönelik bir işaretçi. Nesne bu arabirimi desteklemiyorsa, *ppvObj* null olarak ayarlanır.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

Bir iş parçacığı seçer ve ardından ilişkili grupta bir nesne oluşturur.

## <a name="ccomautothreadmoduledwthreadid"></a><a name="dwthreadid"></a> CComAutoThreadModule::d Wthreadıd

ATL 7,0 itibariyle `CComAutoThreadModule` artık kullanılmıyor: daha fazla ayrıntı için bkz. [ATL modül sınıfları](../../atl/atl-module-classes.md) .

```
DWORD dwThreadID;
```

### <a name="remarks"></a>Açıklamalar

Geçerli iş parçacığının tanımlayıcısını içerir.

## <a name="ccomautothreadmodulegetdefaultthreads"></a><a name="getdefaultthreads"></a> CComAutoThreadModule:: GetDefaultThreads

ATL 7,0 itibariyle `CComAutoThreadModule` artık kullanılmıyor: daha fazla ayrıntı için bkz. [ATL modül sınıfları](../../atl/atl-module-classes.md) .

```
static int GetDefaultThreads();
```

### <a name="return-value"></a>Dönüş Değeri

EXE modülünde oluşturulacak iş parçacığı sayısı.

### <a name="remarks"></a>Açıklamalar

Bu statik işlev, işlemci sayısına göre, EXE modülü için en fazla iş parçacığı sayısını dinamik olarak hesaplar. Varsayılan olarak, bu dönüş değeri, iş parçacıklarını oluşturmak için [Init](#init) yöntemine geçirilir.

## <a name="ccomautothreadmoduleinit"></a><a name="init"></a> CComAutoThreadModule:: Init

ATL 7,0 itibariyle `CComAutoThreadModule` artık kullanılmıyor: daha fazla ayrıntı için bkz. [ATL modül sınıfları](../../atl/atl-module-classes.md) .

```
HRESULT Init(
    _ATL_OBJMAP_ENTRY* p,
    HINSTANCE h,
    const GUID* plibid = NULL,
    int nThreads = GetDefaultThreads());
```

### <a name="parameters"></a>Parametreler

*Lama*<br/>
'ndaki Nesne eşleme girdileri dizisine yönelik bir işaretçi.

*olsun*<br/>
'ndaki Ya da öğesine geçirilen HıNSTANCE `DLLMain` `WinMain` .

*plibıd*<br/>
'ndaki Projeyle ilişkili tür kitaplığının LIBıD işaretçisi.

*nThreads*<br/>
'ndaki Oluşturulacak iş parçacığı sayısı. Varsayılan olarak, *nThreads* , [GetDefaultThreads](#getdefaultthreads)tarafından döndürülen değerdir.

### <a name="remarks"></a>Açıklamalar

Veri üyelerini başlatır ve *nThreads*tarafından belirtilen iş parçacığı sayısını oluşturur.

## <a name="ccomautothreadmodulelock"></a><a name="lock"></a> CComAutoThreadModule:: Lock

ATL 7,0 itibariyle `CComAutoThreadModule` artık kullanılmıyor: daha fazla ayrıntı için bkz. [ATL modül sınıfları](../../atl/atl-module-classes.md) .

```
LONG Lock();
```

### <a name="return-value"></a>Dönüş Değeri

Tanılama veya test için yararlı olabilecek bir değer.

### <a name="remarks"></a>Açıklamalar

Modül için kilit sayısında ve geçerli iş parçacığı için bir atomik artış gerçekleştirir. `CComAutoThreadModule` , herhangi bir istemcinin modüle erişip erişemeyeceğini anlamak için modül kilit sayısını kullanır. Geçerli iş parçacığındaki kilit sayısı istatistiksel amaçlar için kullanılır.

## <a name="ccomautothreadmodulem_allocator"></a><a name="m_allocator"></a> CComAutoThreadModule:: m_Allocator

ATL 7,0 itibariyle `CComAutoThreadModule` artık kullanılmıyor: daha fazla ayrıntı için bkz. [ATL modül sınıfları](../../atl/atl-module-classes.md) .

```
ThreadAllocator  m_Allocator;
```

### <a name="remarks"></a>Açıklamalar

İş parçacığı seçimini yöneten nesne. Varsayılan olarak, `ThreadAllocator` sınıf şablonu parametresi [Ccomsimplethreadayırıcı](../../atl/reference/ccomsimplethreadallocator-class.md)' dır.

## <a name="ccomautothreadmodulem_nthreads"></a><a name="m_nthreads"></a> CComAutoThreadModule:: m_nThreads

ATL 7,0 itibariyle `CComAutoThreadModule` artık kullanılmıyor: daha fazla ayrıntı için bkz. [ATL modül sınıfları](../../atl/atl-module-classes.md) .

```
int m_nThreads;
```

### <a name="remarks"></a>Açıklamalar

EXE modülündeki iş parçacığı sayısını içerir. [Init](#init) çağrıldığında, `m_nThreads` *nThreads* parametre değerine ayarlanır. Her bir iş parçacığının ilişkili grubu bir [CComApartment](../../atl/reference/ccomapartment-class.md) nesnesi tarafından yönetilir.

## <a name="ccomautothreadmodulem_papartments"></a><a name="m_papartments"></a> CComAutoThreadModule:: m_pApartments

ATL 7,0 itibariyle `CComAutoThreadModule` artık kullanılmıyor: daha fazla ayrıntı için bkz. [ATL modül sınıfları](../../atl/atl-module-classes.md) .

```
CComApartment* m_pApartments;
```

### <a name="remarks"></a>Açıklamalar

Her biri modüldeki bir grubu yöneten bir [CComApartment](../../atl/reference/ccomapartment-class.md) nesneleri dizisine işaret eder. Dizideki öğelerin sayısı [m_nThreads](#m_nthreads) üyesini temel alır.

## <a name="ccomautothreadmoduleunlock"></a><a name="unlock"></a> CComAutoThreadModule:: unlock

ATL 7,0 itibariyle `CComAutoThreadModule` artık kullanılmıyor: daha fazla ayrıntı için bkz. [ATL modül sınıfları](../../atl/atl-module-classes.md) .

```
LONG Unlock();
```

### <a name="return-value"></a>Dönüş Değeri

Tanılama veya test için yararlı olabilecek bir değer.

### <a name="remarks"></a>Açıklamalar

Modül için kilit sayısı ve geçerli iş parçacığı için bir atomik azalış gerçekleştirir. `CComAutoThreadModule` , herhangi bir istemcinin modüle erişip erişemeyeceğini anlamak için modül kilit sayısını kullanır. Geçerli iş parçacığındaki kilit sayısı istatistiksel amaçlar için kullanılır.

Modül kilit sayısı sıfıra ulaştığında modül bellekten kaldırılabilir.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa genel bakış](../../atl/atl-class-overview.md)<br/>
[Modül sınıfları](../../atl/atl-module-classes.md)
