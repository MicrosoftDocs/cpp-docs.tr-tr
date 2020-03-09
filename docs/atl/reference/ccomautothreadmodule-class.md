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
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/06/2020
ms.locfileid: "78866179"
---
# <a name="ccomautothreadmodule-class"></a>CComAutoThreadModule sınıfı

ATL 7,0 itibariyle `CComAutoThreadModule` artık kullanılmıyor: daha fazla ayrıntı için bkz. [ATL modül sınıfları](../../atl/atl-module-classes.md) .

> [!IMPORTANT]
>  Bu sınıf ve üyeleri Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
template <class ThreadAllocator = CComSimpleThreadAllocator>
class CComAutoThreadModule : public CComModule
```

#### <a name="parameters"></a>Parametreler

*Threadayırıcı*<br/>
'ndaki İş parçacığı seçimini yöneten sınıf. Varsayılan değer [Ccomsimplethreadayırıcı](../../atl/reference/ccomsimplethreadallocator-class.md)' dır.

## <a name="members"></a>Üyeler

### <a name="methods"></a>Yöntemler

|||
|-|-|
|[CreateInstance](#createinstance)|Bir iş parçacığı seçer ve ardından ilişkili grupta bir nesne oluşturur.|
|[GetDefaultThreads](#getdefaultthreads)|Se Modül için iş parçacığı sayısını işlemci sayısına göre dinamik olarak hesaplar.|
|[Init](#init)|Modülün iş parçacıklarını oluşturur.|
|[İne](#lock)|Modüldeki ve geçerli iş parçacığındaki kilit sayısını artırır.|
|[Kaldırın](#unlock)|Modüldeki ve geçerli iş parçacığındaki kilit sayısını azaltır.|

### <a name="data-members"></a>Veri üyeleri

### <a name="data-members"></a>Veri üyeleri

|||
|-|-|
|[dwThreadId](#dwthreadid)|Geçerli iş parçacığının tanımlayıcısını içerir.|
|[m_Allocator](#m_allocator)|İş parçacığı seçimini yönetir.|
|[m_nThreads](#m_nthreads)|Modüldeki iş parçacığı sayısını içerir.|
|[m_pApartments](#m_papartments)|Modülün apartmanları yönetir.|

## <a name="remarks"></a>Açıklamalar

> [!NOTE]
>  Bu sınıf artık kullanılmıyor, [CAtlAutoThreadModule](../../atl/reference/catlautothreadmodule-class.md) ve [CAtlModule](../../atl/reference/catlmodule-class.md) türetilmiş sınıfları tarafından değiştirildi. Aşağıdaki bilgiler, ATL 'nin eski sürümleriyle kullanım içindir.

`CComAutoThreadModule`, EXEs ve Windows Hizmetleri için iş parçacığı havuza alınmış, Apartman modeli COM sunucusu uygulamak üzere [CComModule](../../atl/reference/ccommodule-class.md) 'ten türetilir. `CComAutoThreadModule`, modüldeki her iş parçacığı için bir grubu yönetmek üzere [CComApartment](../../atl/reference/ccomapartment-class.md) kullanır.

Birden çok apartmanlarda nesne oluşturmak istediğinizde `CComAutoThreadModule` modülünüzü türetirsiniz. Ayrıca, sınıf fabrikası olarak [CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md) belirtmek için nesnenizin sınıf tanımına [declare_classfactory_auto_thread](aggregation-and-class-factory-macros.md#declare_classfactory_auto_thread) makrosunu da dahil etmeniz gerekir.

Varsayılan olarak, ATL COM AppWizard (Visual Studio .NET 'te ATL Proje Sihirbazı) `CComModule`modülünden türetilecektir. `CComAutoThreadModule`kullanmak için, sınıf tanımını değiştirin. Örnek:

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

##  <a name="createinstance"></a>CComAutoThreadModule:: CreateInstance

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

##  <a name="dwthreadid"></a>CComAutoThreadModule::d Wthreadıd

ATL 7,0 itibariyle `CComAutoThreadModule` artık kullanılmıyor: daha fazla ayrıntı için bkz. [ATL modül sınıfları](../../atl/atl-module-classes.md) .

```
DWORD dwThreadID;
```

### <a name="remarks"></a>Açıklamalar

Geçerli iş parçacığının tanımlayıcısını içerir.

##  <a name="getdefaultthreads"></a>CComAutoThreadModule:: GetDefaultThreads

ATL 7,0 itibariyle `CComAutoThreadModule` artık kullanılmıyor: daha fazla ayrıntı için bkz. [ATL modül sınıfları](../../atl/atl-module-classes.md) .

```
static int GetDefaultThreads();
```

### <a name="return-value"></a>Dönüş Değeri

EXE modülünde oluşturulacak iş parçacığı sayısı.

### <a name="remarks"></a>Açıklamalar

Bu statik işlev, işlemci sayısına göre, EXE modülü için en fazla iş parçacığı sayısını dinamik olarak hesaplar. Varsayılan olarak, bu dönüş değeri, iş parçacıklarını oluşturmak için [Init](#init) yöntemine geçirilir.

##  <a name="init"></a>CComAutoThreadModule:: Init

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
'ndaki HıNSTANCE `DLLMain` veya `WinMain`geçirildi.

*plibıd*<br/>
'ndaki Projeyle ilişkili tür kitaplığının LIBıD işaretçisi.

*nThreads*<br/>
'ndaki Oluşturulacak iş parçacığı sayısı. Varsayılan olarak, *nThreads* , [GetDefaultThreads](#getdefaultthreads)tarafından döndürülen değerdir.

### <a name="remarks"></a>Açıklamalar

Veri üyelerini başlatır ve *nThreads*tarafından belirtilen iş parçacığı sayısını oluşturur.

##  <a name="lock"></a>CComAutoThreadModule:: Lock

ATL 7,0 itibariyle `CComAutoThreadModule` artık kullanılmıyor: daha fazla ayrıntı için bkz. [ATL modül sınıfları](../../atl/atl-module-classes.md) .

```
LONG Lock();
```

### <a name="return-value"></a>Dönüş Değeri

Tanılama veya test için yararlı olabilecek bir değer.

### <a name="remarks"></a>Açıklamalar

Modül için kilit sayısında ve geçerli iş parçacığı için bir atomik artış gerçekleştirir. `CComAutoThreadModule`, modüle herhangi bir istemcinin erişip erişemeyeceğini öğrenmek için modül kilit sayısını kullanır. Geçerli iş parçacığındaki kilit sayısı istatistiksel amaçlar için kullanılır.

##  <a name="m_allocator"></a>CComAutoThreadModule:: m_Allocator

ATL 7,0 itibariyle `CComAutoThreadModule` artık kullanılmıyor: daha fazla ayrıntı için bkz. [ATL modül sınıfları](../../atl/atl-module-classes.md) .

```
ThreadAllocator  m_Allocator;
```

### <a name="remarks"></a>Açıklamalar

İş parçacığı seçimini yöneten nesne. Varsayılan olarak, `ThreadAllocator` sınıfı şablon parametresi [Ccomsimplethreadayırıcı](../../atl/reference/ccomsimplethreadallocator-class.md)' dır.

##  <a name="m_nthreads"></a>CComAutoThreadModule:: m_nThreads

ATL 7,0 itibariyle `CComAutoThreadModule` artık kullanılmıyor: daha fazla ayrıntı için bkz. [ATL modül sınıfları](../../atl/atl-module-classes.md) .

```
int m_nThreads;
```

### <a name="remarks"></a>Açıklamalar

EXE modülündeki iş parçacığı sayısını içerir. [Init](#init) çağrıldığında, `m_nThreads` *nThreads* parametre değerine ayarlanır. Her bir iş parçacığının ilişkili grubu bir [CComApartment](../../atl/reference/ccomapartment-class.md) nesnesi tarafından yönetilir.

##  <a name="m_papartments"></a>CComAutoThreadModule:: m_pApartments

ATL 7,0 itibariyle `CComAutoThreadModule` artık kullanılmıyor: daha fazla ayrıntı için bkz. [ATL modül sınıfları](../../atl/atl-module-classes.md) .

```
CComApartment* m_pApartments;
```

### <a name="remarks"></a>Açıklamalar

Her biri modüldeki bir grubu yöneten bir [CComApartment](../../atl/reference/ccomapartment-class.md) nesneleri dizisine işaret eder. Dizideki öğelerin sayısı [m_nThreads](#m_nthreads) üyesini temel alır.

##  <a name="unlock"></a>CComAutoThreadModule:: unlock

ATL 7,0 itibariyle `CComAutoThreadModule` artık kullanılmıyor: daha fazla ayrıntı için bkz. [ATL modül sınıfları](../../atl/atl-module-classes.md) .

```
LONG Unlock();
```

### <a name="return-value"></a>Dönüş Değeri

Tanılama veya test için yararlı olabilecek bir değer.

### <a name="remarks"></a>Açıklamalar

Modül için kilit sayısı ve geçerli iş parçacığı için bir atomik azalış gerçekleştirir. `CComAutoThreadModule`, modüle herhangi bir istemcinin erişip erişemeyeceğini öğrenmek için modül kilit sayısını kullanır. Geçerli iş parçacığındaki kilit sayısı istatistiksel amaçlar için kullanılır.

Modül kilit sayısı sıfıra ulaştığında modül bellekten kaldırılabilir.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa genel bakış](../../atl/atl-class-overview.md)<br/>
[Modül sınıfları](../../atl/atl-module-classes.md)
