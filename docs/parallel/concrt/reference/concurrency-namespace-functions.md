---
title: eşzamanlılık ad alanı işlevleri
ms.date: 11/04/2016
f1_keywords:
- concrt/concurrency::Alloc
- concrt/concurrency::DisableTracing
- concrt/concurrency::EnableTracing
- concrtrm/concurrency::GetExecutionContextId
- concrtrm/concurrency::GetOSVersion
- concrtrm/concurrency::GetProcessorNodeCount
- concrtrm/concurrency::GetSchedulerId
- agents/concurrency::asend
- ppltasks/concurrency::cancel_current_task
- ppltasks/concurrency::create_async
- ppltasks/concurrency::create_task
- concurrent_vector/concurrency::internal_assign_iterators
- ppl/concurrency::interruption_point
- agents/concurrency::make_choice
- agents/concurrency::make_greedy_join
- ppl/concurrency::make_task
- ppl/concurrency::parallel_buffered_sort
- ppl/concurrency::parallel_for_each
- ppl/concurrency::parallel_invoke
- ppl/concurrency::parallel_reduce
- ppl/concurrency::parallel_sort
- agents/concurrency::receive
- ppl/concurrency::run_with_cancellation_token
- pplconcrt/concurrency::set_ambient_scheduler
- concrt/concurrency::set_task_execution_resources
- ppltasks/concurrency::task_from_exception
- ppltasks/concurrency::task_from_result
- concrt/concurrency::wait
- ppltasks/concurrency::when_all
- ppltasks/concurrency::when_any
ms.assetid: 520a6dff-9324-4df2-990d-302e3050af6a
ms.openlocfilehash: 15b265744640628425502706d69fd98a1c64bda2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374367"
---
# <a name="concurrency-namespace-functions"></a>eşzamanlılık ad alanı işlevleri

||||
|-|-|-|
|[Ayırma](#alloc)|[CreateResourceManager](#createresourcemanager)|[Devre dışı](#disabletracing)|
|[Etkinleştirme](#enabletracing)|[Ücretsiz](#free)|[Alma YürütmeBağlamid](#getexecutioncontextid)|
|[GetOSVersion](#getosversion)|[İşlemci Sayısı'nı Alın](#getprocessorcount)|[İşlemciNodeSayısı](#getprocessornodecount)|
|[GetSchedulerId](#getschedulerid)|[Trace_agents_register_name](#trace_agents_register_name)|[asend](#asend)|
|[cancel_current_task](#cancel_current_task)|[Temizleyin](#clear)|[create_async](#create_async)|
|[create_task](#create_task)|[get_ambient_scheduler](#get_ambient_scheduler)|[internal_assign_iterators](#internal_assign_iterators)|
|[interruption_point](#interruption_point)|[is_current_task_group_canceling](#is_current_task_group_canceling)|[make_choice](#make_choice)|
|[make_greedy_join](#make_greedy_join)|[make_join](#make_join)|[make_task](#make_task)|
|[parallel_buffered_sort](#parallel_buffered_sort)|[parallel_for](#parallel_for)|[parallel_for_each](#parallel_for_each)|
|[Parallel_invoke](#parallel_invoke)|[parallel_radixsort](#parallel_radixsort)|[parallel_reduce](#parallel_reduce)|
|[parallel_sort](#parallel_sort)|[parallel_transform](#parallel_transform)|[Almak](#receive)|
|[run_with_cancellation_token](#run_with_cancellation_token)|[Gönder](#send)|[set_ambient_scheduler](#set_ambient_scheduler)|
|[set_task_execution_resources](#set_task_execution_resources)|[Takas](#swap)|[task_from_exception](#task_from_exception)|
|[task_from_result](#task_from_result)|[try_receive](#try_receive)|[Bekle](#wait)|
|[when_all](#when_all)|[when_any](#when_any)|

## <a name="alloc"></a><a name="alloc"></a>Ayırma

Eşzamanlıçalışma Süresi Önbelleğe Alma Alt Ayırıcısı'ndan belirtilen boyutun bellek bloğunu ayırır.

```cpp
void* __cdecl Alloc(size_t _NumBytes);
```

### <a name="parameters"></a>Parametreler

*_NumBytes*<br/>
Ayrılacak bellek baytlarının sayısı.

### <a name="return-value"></a>Dönüş Değeri

Yeni ayrılan belleğe işaretçi.

### <a name="remarks"></a>Açıklamalar

Uygulamanızdaki hangi senaryoların Önbelleğe Alma Alt Ayırıcısı'nı kullanmanın yararına olabileceği hakkında daha fazla bilgi için [Görev Zamanlayıcısı'na](../../../parallel/concrt/task-scheduler-concurrency-runtime.md)bakın.

## <a name="asend"></a><a name="asend"></a>asend

Verileri hedef bloğa yaymak için bir görev zamanlayan asynchronous gönderme işlemi.

```cpp
template <class T>
bool asend(
    _Inout_ ITarget<T>* _Trg,
    const T& _Data);

template <class T>
bool asend(
    ITarget<T>& _Trg,
    const T& _Data);
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Gönderilecek verilerin türü.

*_Trg*<br/>
Verilerin gönderildiği hedefe bir işaretçi veya başvuru.

*_Data*<br/>
Gönderilecek verilere bir başvuru.

### <a name="return-value"></a>Dönüş Değeri

yöntem döndürülmeden önce ileti kabul edildiyse **doğru,** aksi takdirde **yanlış.**

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [İleti Geçme İşlevlerini](../../../parallel/concrt/message-passing-functions.md)görün.

## <a name="cancel_current_task"></a><a name="cancel_current_task"></a>cancel_current_task

Şu anda yürütülen görevi iptal eder. Bu işlev, görevin yürütülmesini iptal etmek ve `canceled` duruma girmesine neden olmak için görevin gövdesi içinden çağrılabilir.

Eğer bir ' nin gövdesi içinde değilseniz, bu işlevi `task`aramak için desteklenen bir senaryo değildir. Bunu yapmak, uygulamanızda kilitlenme veya askıda kalma gibi tanımlanmamış davranışlara neden olur.

```cpp
inline __declspec(noreturn) void __cdecl cancel_current_task();
```

## <a name="clear"></a><a name="clear"></a>Temizleyin

Eşzamanlı sırayı temizler ve şu anda sırada bulunan öğeleri yok eder. Bu yöntem eşzamanlılık güvenli değildir.

```cpp
template<typename T, class _Ax>
void concurrent_queue<T, _Ax>::clear();
```

### <a name="parameters"></a>Parametreler

*T*<br/>

*_Ax*<br/>

## <a name="create_async"></a><a name="create_async"></a>create_async

Kullanıcı tarafından sağlanan lambda veya işlev nesnesi temel alınca windows runtime asynchronous yapısı oluşturur. `create_async` İade türü ya da `IAsyncAction^`bir `IAsyncActionWithProgress<TProgress>^` `IAsyncOperation<TResult>^`, `IAsyncOperationWithProgress<TResult, TProgress>^` , , veya lambda imzasına dayalı yönteme geçti.

```cpp
template<typename _Function>
__declspec(noinline) auto create_async(const _Function& _Func)
    -> decltype(ref new details::_AsyncTaskGeneratorThunk<_Function>(_Func));
```

### <a name="parameters"></a>Parametreler

*_Function*<br/>
Türü.

*_Func*<br/>
Windows Runtime asynchronous yapısı oluşturmak için lambda veya işlev nesnesi.

### <a name="return-value"></a>Dönüş Değeri

Bir IAsyncAction^, IAsyncActionWithProgress\<TProgress>^, IAsyncOperation\<TResult>^veya bir IAsyncOperationWithProgress\<TResult, TProgress>^. Döndürülen arayüz, işleve geçen lambda'nın imzasına bağlıdır.

### <a name="remarks"></a>Açıklamalar

Lambda'nın dönüş türü, yapının bir eylem mi yoksa bir işlem mi olduğunu belirler.

Void dönen lambdas eylemlerin yaratılmasına neden olur. Tip `TResult` sonucu nu döndüren lambdas, TResult işlemlerinin oluşturulmasına neden olur.

Lambda da kendi `task<TResult>` içinde aysnchronous iş kapsüller ya da asynchronous iş temsil eden görevler zincirinin devamı bir dönüş olabilir. Bu durumda, lambda kendisi satır satırda yürütülür, çünkü görevleri eşzamanlı olarak yürütmek olanlar, ve lambda dönüş türü tarafından `create_async`döndürülen asynchronous yapı üretmek için unwrapped olduğunu . Bu, bir görev\<geçersizliğini döndüren bir lambda'nın eylemlerin oluşturulmasına>\<ve TResult> bir görevi döndüren bir lambda'nın TResult işlemlerinin oluşturulmasına neden olacağı anlamına gelir.

Lambda ya sıfır, bir ya da iki argüman alabilir. Geçerli bağımsız `progress_reporter<TProgress>` değişkenler ve `cancellation_token`, her ikisi de kullanılırsa bu sırada. Bağımsız bir lambda ilerleme raporlama yeteneği olmadan bir eşzamanlı yapı oluşturulmasına neden olur. TProgress> progress_reporter\<alan bir lambda, progress_reporter nesnenin `create_async` `report` yöntemi çağrıldığında tprogress türünün ilerlemesini bildiren bir eşzamanlı yapının döndürülmesine neden olur. cancellation_token alan bir lambda, iptal olup olmadığını kontrol etmek için bu belirteci kullanabilir veya asenkron yapının iptalinin bu görevlerin iptaline neden olacak şekilde oluşturduğu görevlere geçirebilir.

Lambda veya işlev nesnesinin gövdesi bir sonucu döndürürse (ve bir görev\<TResult> değilse), lamdba, Runtime'ın dolaylı olarak oluşturduğu bir görev bağlamında mta işlemi içinde eşit olarak yürütülür. Yöntem, `IAsyncInfo::Cancel` örtülü görevin iptaline neden olur.

Lambda gövdesi bir görevi iade ederse, lamba satır içi yürütür ve lambda'yı bir `cancellation_token` tür argümanı almaya beyan ederek, lambda içinde oluşturduğunuz herhangi bir görevin iptalini, oluşturduğunuz zaman bu belirteci geçirerek tetikleyebilirsiniz. Ayrıca, üretilen `register_callback` async işlemini veya eylemi çağırdığınızda `IAsyncInfo::Cancel` Runtime'ın geri arama sını çağırmak için belirteçteki yöntemi de kullanabilirsiniz...

Bu işlev yalnızca Windows Runtime uygulamaları için kullanılabilir.

## <a name="createresourcemanager"></a><a name="createresourcemanager"></a>CreateResourceManager

EşzamanlıLık Runtime Kaynak Yöneticisi'nin singleton örneğini temsil eden bir arabirim döndürür. Kaynak Yöneticisi, birbirleriyle işbirliği yapmak isteyen zamanlayıcılara kaynak atamaktan sorumludur.

```cpp
IResourceManager* __cdecl CreateResourceManager();
```

### <a name="return-value"></a>Dönüş Değeri

Bir `IResourceManager` arayüz.

### <a name="remarks"></a>Açıklamalar

Bu yönteme sonraki birden çok çağrı, Kaynak Yöneticisi'nin aynı örneğini döndürecektir. Yönteme yapılan her çağrı Kaynak Yöneticisi'ne bir başvuru sayısı verir ve [iResourceManager'a](iresourcemanager-structure.md) yapılan bir çağrıyla eşleşmelidir::Zamanlayıcınız Kaynak Yöneticisi ile iletişim ilerlediğinde yayın yöntemi.

İşletim sistemi EşzamanlıLık Çalışma Zamanı tarafından desteklenmiyorsa [unsupported_os](unsupported-os-class.md) atılır.

## <a name="create_task"></a><a name="create_task"></a>create_task

PPL [görev](task-class.md) nesnesi oluşturur. `create_task`bir görev oluşturucu kullanmış olurdu her yerde kullanılabilir. Görevler oluştururken `auto` anahtar kelimenin kullanımına izin verdiği için, çoğunlukla kolaylık sağlamak için sağlanır.

```cpp
template<typename T>
__declspec(noinline) auto create_task(T _Param, const task_options& _TaskOptions = task_options())
    -> task<typename details::_TaskTypeFromParam<T>::T>;

template<typename _ReturnType>
__declspec( noinline) task<_ReturnType> create_task(const task<_ReturnType>& _Task);
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Görevin oluşturulacak parametre türü.

*_ReturnType*<br/>
Türü.

*_Param*<br/>
Görevin oluşturulacak parametresi. Bu bir lambda veya işlev `task_completion_event` nesnesi, `task` bir nesne, farklı bir nesne veya bir Windows olabilir::Temel::UWP uygulamanızdaki görevleri kullanıyorsanız IAsyncInfo arabirimi.

*_TaskOptions*<br/>
Görev seçenekleri.

*_Task*<br/>
Oluşturulacak görev.

### <a name="return-value"></a>Dönüş Değeri

Türünün `T`yeni bir görevi, bu. `_Param`

### <a name="remarks"></a>Açıklamalar

İlk aşırı yükleme, tek bir parametre alan bir görev oluşturucusu gibi olur.

İkinci aşırı yükleme, yeni oluşturulan görevle sağlanan iptal belirteciyle ilişkilendirir. Bu aşırı yükü kullanırsanız, ilk parametre `task` olarak farklı bir nesnede geçmenize izin verilmez.

Döndürülen görevin türü, ilk parametreden işleve çıkarılır. Bir `_Param` `task_completion_event<T>`ise, `task<T>`a , veya bir functor ya tür `T` veya `task<T>`döndürür, oluşturulan görevtürü . `task<T>`

Bir UWP uygulamasında, `_Param` Windows:::IAsyncOperation\<T>^ veya Windows::Foundation::IAsyncOperationWithProgress\<T,P>^veya bu türlerden birini döndüren bir functor türünde yse, oluşturulan görev türünde `task<T>`olacaktır. Windows `_Param` türünden ise::Foundation::IAsyncAction^ veya Windows::Foundation::IAsyncActionWithProgress\<P>^veya bu türlerden birini döndüren `task<void>`bir functor varsa, oluşturulan görev türüne sahip olacaktır.

## <a name="disabletracing"></a><a name="disabletracing"></a>Devre dışı

Eşzamanlılık Çalışma Zamanı'nda izlemeyi devre dışı katıyor. ETW izleme varsayılan olarak kayıt dışı olduğundan bu işlev amortismana kaydedilir.

```cpp
__declspec(deprecated("Concurrency::DisableTracing is a deprecated function.")) _CRTIMP HRESULT __cdecl DisableTracing();
```

### <a name="return-value"></a>Dönüş Değeri

İzleme doğru devre dışı `S_OK` bırakılmışsa, döndürülür. İzleme daha önce başlatılmamışsa, `E_NOT_STARTED` döndürülür

## <a name="enabletracing"></a><a name="enabletracing"></a>Etkinleştirme

Eşzamanlılık Çalışma Zamanında izleme sağlar. ETW izleme artık varsayılan olarak açık olduğundan bu işlev amortismana sokuldu.

```cpp
__declspec(deprecated("Concurrency::EnableTracing is a deprecated function.")) _CRTIMP HRESULT __cdecl EnableTracing();
```

### <a name="return-value"></a>Dönüş Değeri

İzleme doğru başlatıldıysa, `S_OK` döndürülür; aksi `E_NOT_STARTED` takdirde döndürülür.

## <a name="free"></a><a name="free"></a>Ücret -siz

`Alloc` Yöntem tarafından daha önce EşzamanlıÇalışma Süresi Önyor Alt Ayırıcısına ayrılan bir bellek bloğu salgılar.

```cpp
void __cdecl Free(_Pre_maybenull_ _Post_invalid_ void* _PAllocation);
```

### <a name="parameters"></a>Parametreler

*_PAllocation*<br/>
Serbest bırakılacak `Alloc` yöntem tarafından daha önce ayrılan bellek işaretçisi. Parametre `_PAllocation` değere `NULL`ayarlanırsa, bu yöntem bunu yoksayarlar ve hemen geri döner.

### <a name="remarks"></a>Açıklamalar

Uygulamanızdaki hangi senaryoların Önbelleğe Alma Alt Ayırıcısı'nı kullanmanın yararına olabileceği hakkında daha fazla bilgi için [Görev Zamanlayıcısı'na](../../../parallel/concrt/task-scheduler-concurrency-runtime.md)bakın.

## <a name="get_ambient_scheduler"></a><a name="get_ambient_scheduler"></a>get_ambient_scheduler

```cpp
inline std::shared_ptr<::Concurrency::scheduler_interface> get_ambient_scheduler();
```

### <a name="return-value"></a>Dönüş Değeri

## <a name="getexecutioncontextid"></a><a name="getexecutioncontextid"></a>Alma YürütmeBağlamid

`IExecutionContext` Arabirimi uygulayan bir yürütme bağlamına atanabilecek benzersiz bir tanımlayıcı döndürür.

```cpp
unsigned int __cdecl GetExecutionContextId();
```

### <a name="return-value"></a>Dönüş Değeri

Yürütme bağlamı için benzersiz bir tanımlayıcı.

### <a name="remarks"></a>Açıklamalar

Kaynak Yöneticisi tarafından sunulan yöntemlerden herhangi biri için bir `IExecutionContext` arabirim parametre olarak geçmeden önce yürütme bağlamınız için bir tanımlayıcı elde etmek için bu yöntemi kullanın.

## <a name="getosversion"></a><a name="getosversion"></a>GetOSVersion

İşletim sistemi sürümünü döndürür.

```cpp
IResourceManager::OSVersion __cdecl GetOSVersion();
```

### <a name="return-value"></a>Dönüş Değeri

İşletim sistemini temsil eden numaralandırılmış bir değer.

### <a name="remarks"></a>Açıklamalar

İşletim sistemi EşzamanlıLık Çalışma Zamanı tarafından desteklenmiyorsa [unsupported_os](unsupported-os-class.md) atılır.

## <a name="getprocessorcount"></a><a name="getprocessorcount"></a>İşlemci Sayısı'nı Alın

Altta yatan sistemdeki donanım iş parçacığı sayısını verir.

```cpp
unsigned int __cdecl GetProcessorCount();
```

### <a name="return-value"></a>Dönüş Değeri

Donanım iş parçacığı sayısı.

### <a name="remarks"></a>Açıklamalar

İşletim sistemi EşzamanlıLık Çalışma Zamanı tarafından desteklenmiyorsa [unsupported_os](unsupported-os-class.md) atılır.

## <a name="getprocessornodecount"></a><a name="getprocessornodecount"></a>İşlemciNodeSayısı

Temel sistemdeki NUMA düğümlerinin veya işlemci paketlerinin sayısını verir.

```cpp
unsigned int __cdecl GetProcessorNodeCount();
```

### <a name="return-value"></a>Dönüş Değeri

NUMA düğümlerinin veya işlemci paketlerinin sayısı.

### <a name="remarks"></a>Açıklamalar

Sistem işlemci paketlerinden daha fazla NUMA düğümü içeriyorsa, NUMA düğümlerinin sayısı döndürülür, aksi takdirde işlemci paketlerinin sayısı döndürülür.

İşletim sistemi EşzamanlıLık Çalışma Zamanı tarafından desteklenmiyorsa [unsupported_os](unsupported-os-class.md) atılır.

## <a name="getschedulerid"></a><a name="getschedulerid"></a>GetSchedulerId

`IScheduler` Arabirimi uygulayan bir zamanlayıcıya atanabilecek benzersiz bir tanımlayıcı döndürür.

```cpp
unsigned int __cdecl GetSchedulerId();
```

### <a name="return-value"></a>Dönüş Değeri

Zamanlayıcı için benzersiz bir tanımlayıcı.

### <a name="remarks"></a>Açıklamalar

Kaynak Yöneticisi tarafından sunulan yöntemlerden herhangi biri için bir `IScheduler` arabirim parametre olarak geçmeden önce zamanlayıcınız için bir tanımlayıcı elde etmek için bu yöntemi kullanın.

## <a name="internal_assign_iterators"></a><a name="internal_assign_iterators"></a>internal_assign_iterators

```cpp
template<typename T, class _Ax>
template<class _I>
void concurrent_vector<T, _Ax>::internal_assign_iterators(
   _I first,
   _I last);
```

### <a name="parameters"></a>Parametreler

*T*<br/>

*_Ax*<br/>

*_I*<br/>

*Ilk*<br/>

*Son*<br/>

## <a name="interruption_point"></a><a name="interruption_point"></a>interruption_point

İptal için bir kesinti noktası oluşturur. Bu işlevin çağrıldığı bağlamda bir iptal devam ediyorsa, bu, şu anda yürütülen paralel çalışmanın yürütülmesini iptal eden bir iç özel durum oluşturur. İptal işlemi devam etmiyorsa, işlev hiçbir şey yapmaz.

```cpp
inline void interruption_point();
```

### <a name="remarks"></a>Açıklamalar

İşlev tarafından atılan dahili iptal `interruption_point()` istisnasını yakalamamalısınız. Özel durum yakalanır ve çalışma zamanı tarafından ele alınır ve yakalamak programınızın anormal şekilde çalışmasına neden olabilir.

## <a name="is_current_task_group_canceling"></a><a name="is_current_task_group_canceling"></a>is_current_task_group_canceling

Geçerli bağlamda satır adı yürütmekte olan görev grubunun etkin bir iptalin ortasında olup olmadığını (veya kısa süre içinde mi olacağını) gösteren bir gösterge verir. Geçerli bağlamda satır adı yürütülen bir görev grubu `false` yoksa döndürüleceğini unutmayın.

```cpp
bool __cdecl is_current_task_group_canceling();
```

### <a name="return-value"></a>Dönüş Değeri

**true** şu anda yürütülmakta olan görev grubu iptal ediyorsa, aksi takdirde **yanlış.**

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [İptal](../../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md#cancellation)'e bakın.

## <a name="make_choice"></a><a name="make_choice"></a>make_choice

İsteğe `choice` bağlı `Scheduler` veya iki veya `ScheduleGroup` daha fazla giriş kaynağından bir ileti bloğu oluşturuyor.

```cpp
template<typename T1, typename T2, typename... Ts>
choice<std::tuple<T1, T2, Ts...>> make_choice(
    Scheduler& _PScheduler,
    T1  _Item1,
    T2  _Item2,
    Ts... _Items);

template<typename T1, typename T2, typename... Ts>
choice<std::tuple<T1, T2, Ts...>> make_choice(
    ScheduleGroup& _PScheduleGroup,
    T1  _Item1,
    T2  _Item2,
    Ts... _Items);

template<typename T1, typename T2, typename... Ts>
choice<std::tuple<T1, T2, Ts...>> make_choice(
    T1  _Item1,
    T2  _Item2,
    Ts... _Items);
```

### <a name="parameters"></a>Parametreler

*T1*<br/>
İlk kaynağın ileti bloğu türü.

*T2*<br/>
İkinci kaynağın ileti bloğu türü.

*_PScheduler*<br/>
İleti `Scheduler` bloğu için yayılma görevinin `choice` zamanlandığı nesne.

*_Item1*<br/>
İlk kaynak.

*_Item2*<br/>
İkinci kaynak.

*_Items*<br/>
Ek kaynaklar.

*_PScheduleGroup*<br/>
İleti `ScheduleGroup` bloğu için yayılma görevinin `choice` zamanlandığı nesne. Kullanılan `Scheduler` nesne zamanlama grubu tarafından ima edilir.

### <a name="return-value"></a>Dönüş Değeri

İki `choice` veya daha fazla giriş kaynağı içeren bir ileti bloğu.

## <a name="make_greedy_join"></a><a name="make_greedy_join"></a>make_greedy_join

İsteğe `greedy multitype_join` bağlı `Scheduler` veya iki veya `ScheduleGroup` daha fazla giriş kaynağından bir ileti bloğu oluşturuyor.

```cpp
template<typename T1, typename T2, typename... Ts>
multitype_join<std::tuple<T1, T2, Ts...>,greedy> make_greedy_join(
    Scheduler& _PScheduler,
    T1 _Item1,
    T2 _Item2,
    Ts... _Items);

template<typename T1, typename T2, typename... Ts>
multitype_join<std::tuple<T1, T2, Ts...>, greedy> make_greedy_join(
    ScheduleGroup& _PScheduleGroup,
    T1 _Item1,
    T2 _Item2,
    Ts... _Items);

template<typename T1, typename T2, typename... Ts>
multitype_join<std::tuple<T1, T2, Ts...>, greedy> make_greedy_join(
    T1 _Item1,
    T2 _Items,
    Ts... _Items);
```

### <a name="parameters"></a>Parametreler

*T1*<br/>
İlk kaynağın ileti bloğu türü.

*T2*<br/>
İkinci kaynağın ileti bloğu türü.

*_PScheduler*<br/>
İleti `Scheduler` bloğu için yayılma görevinin `multitype_join` zamanlandığı nesne.

*_Item1*<br/>
İlk kaynak.

*_Item2*<br/>
İkinci kaynak.

*_Items*<br/>
Ek kaynaklar.

*_PScheduleGroup*<br/>
İleti `ScheduleGroup` bloğu için yayılma görevinin `multitype_join` zamanlandığı nesne. Kullanılan `Scheduler` nesne zamanlama grubu tarafından ima edilir.

### <a name="return-value"></a>Dönüş Değeri

İki `greedy multitype_join` veya daha fazla giriş kaynağı içeren bir ileti bloğu.

## <a name="make_join"></a><a name="make_join"></a>make_join

İsteğe `non_greedy multitype_join` bağlı `Scheduler` veya iki veya `ScheduleGroup` daha fazla giriş kaynağından bir ileti bloğu oluşturuyor.

```cpp
template<typename T1, typename T2, typename... Ts>
multitype_join<std::tuple<T1, T2, Ts...>>
    make_join(
Scheduler& _PScheduler,
    T1 _Item1,
    T2 _Item2,
    Ts... _Items);

template<typename T1, typename T2, typename... Ts>
multitype_join<std::tuple<T1, T2, Ts...>> make_join(
ScheduleGroup& _PScheduleGroup,
    T1 _Item1,
    T2 _Item2,
    Ts... _Items);

template<typename T1, typename T2, typename... Ts>
multitype_join<std::tuple<T1, T2, Ts...>> make_join(
    T1 _Item1,
    T2 _Item2,
    Ts... _Items);
```

### <a name="parameters"></a>Parametreler

*T1*<br/>
İlk kaynağın ileti bloğu türü.

*T2*<br/>
İkinci kaynağın ileti bloğu türü.

*_PScheduler*<br/>
İleti `Scheduler` bloğu için yayılma görevinin `multitype_join` zamanlandığı nesne.

*_Item1*<br/>
İlk kaynak.

*_Item2*<br/>
İkinci kaynak.

*_Items*<br/>
Ek kaynaklar.

*_PScheduleGroup*<br/>
İleti `ScheduleGroup` bloğu için yayılma görevinin `multitype_join` zamanlandığı nesne. Kullanılan `Scheduler` nesne zamanlama grubu tarafından ima edilir.

### <a name="return-value"></a>Dönüş Değeri

İki `non_greedy multitype_join` veya daha fazla giriş kaynağı içeren bir ileti bloğu.

## <a name="make_task"></a><a name="make_task"></a>make_task

Nesne oluşturmak için `task_handle` bir fabrika yöntemi.

```cpp
template <class _Function>
task_handle<_Function> make_task(const _Function& _Func);
```

### <a name="parameters"></a>Parametreler

*_Function*<br/>
Nesne tarafından temsil edilen işi yürütmek için çağrılacak işlev `task_handle` nesnesinin türü.

*_Func*<br/>
`task_handle` Nesne tarafından temsil edilen işi yürütmek için çağrılacak işlev. Bu bir lambda functor, bir işlev için bir işaretçi veya imza `void operator()()`ile işlev çağrı işlecinin bir sürümünü destekleyen herhangi bir nesne olabilir.

### <a name="return-value"></a>Dönüş Değeri

Bir `task_handle` nesnesi.

### <a name="remarks"></a>Açıklamalar

Bu işlev, lambda funktörünün gerçek türünü bilmeden nesneyi oluşturmanıza olanak sağladığından lambda ifadesi olan bir `task_handle` nesne oluşturmanız gerektiğinde kullanışlıdır.

## <a name="parallel_buffered_sort"></a><a name="parallel_buffered_sort"></a>parallel_buffered_sort

Belirli bir aralıktaki öğeleri alçalan olmayan bir sıraya veya ikili yüklem tarafından belirtilen bir sıralama ölçütüne göre paralel olarak düzenler. Bu işlev, ek alana `std::sort` ihtiyacı `O(n)` olmadığı dışında karşılaştırma tabanlı, kararsız, yerinde sıralanmış olması ve sıralanan öğeler için varsayılan başlatma gerektirmesi anlamsal olarak benzerdir.

```cpp
template<typename _Random_iterator>
inline void parallel_buffered_sort(
    const _Random_iterator& _Begin,
    const _Random_iterator& _End);

template<typename _Allocator,
    typename _Random_iterator>
inline void parallel_buffered_sort(
    const _Random_iterator& _Begin,
    const _Random_iterator& _End);

template<typename _Allocator,
    typename _Random_iterator>
inline void parallel_buffered_sort(
    const _Allocator& _Alloc,
    const _Random_iterator& _Begin,
    const _Random_iterator& _End);

template<typename _Random_iterator,
    typename _Function>
inline void parallel_buffered_sort(
    const _Random_iterator& _Begin,
    const _Random_iterator& _End,
    const _Function& _Func,
    const size_t _Chunk_size = 2048);

template<typename _Allocator,
    typename _Random_iterator,
    typename _Function>
inline void parallel_buffered_sort(
    const _Random_iterator& _Begin,
    const _Random_iterator& _End,
    const _Function& _Func,
    const size_t _Chunk_size = 2048);

template<typename _Allocator,
    typename _Random_iterator,
    typename _Function>
inline void parallel_buffered_sort(
    const _Allocator& _Alloc,
    const _Random_iterator& _Begin,
    const _Random_iterator& _End,
    const _Function& _Func,
    const size_t _Chunk_size = 2048);
```

### <a name="parameters"></a>Parametreler

*_Random_iterator*<br/>
Giriş aralığının yineleyici türü.

*_Allocator*<br/>
C++ Standart Kitaplığı uyumlu bellek ayırıcısının türü.

*_Function*<br/>
İkili karşılaştırıcının türü.

*_Begin*<br/>
Sıralanacak aralıktaki ilk öğenin konumunu ele alan rasgele erişim yineleyici.

*_End*<br/>
Sıralanacak aralıktaki son öğeyi bir geçmiş pozisyonadrese leyen rasgele erişim yineleyici.

*_Alloc*<br/>
C++ Standart Kitaplık uyumlu bellek ayırıcısının bir örneği.

*_Func*<br/>
Sıralamada birbirini izleyen öğeler tarafından karşılanacak karşılaştırma ölçütlerini tanımlayan kullanıcı tanımlı yüklem işlev nesnesi. İkili yüklem iki bağımsız değişken alır ve tatmin olduğunda **doğru** **ve** doğru olmadığında doğru döndürür. Bu karşılaştırıcı işlev, dizideki öğe çiftlerine katı bir zayıf sıralama dayatmalıdır.

*_Chunk_size*<br/>
Paralel yürütme için ikiye bölünecek bir parçanın mimimum boyutu.

### <a name="remarks"></a>Açıklamalar

Tüm aşırı `n * sizeof(T)` yüklemeler ek `n` alan gerektirir, sıralanacak öğe `T` sayısı ve öğe türü. Çoğu durumda parallel_buffered_sort [parallel_sort](concurrency-namespace-functions.md)üzerinde performans bir iyileşme gösterir ve bellek varsa parallel_sort üzerinde kullanmalısınız.

Eğer bir ikili karşılaştırıcı `std::less` sağlamazsanız, işleci `operator<()`sağlamak için eleman türünü gerektiren varsayılan olarak kullanılır.

Bir ayırıcı türü veya örneği sağlamazsanız, arabelleği `std::allocator<T>` ayırmak için C++ Standart Kitaplık bellek ayırıcısı kullanılır.

Algoritma giriş aralığını iki parçaya böler ve birbirini izleyen olarak her bir parçayı paralel olarak yürütülmesi için iki alt parçaya böler. İsteğe `_Chunk_size` bağlı bağımsız değişken, algoritmaya boyut < parçalarını `_Chunk_size` < işlemesi gerektiğini belirtmek için kullanılabilir.

## <a name="parallel_for"></a><a name="parallel_for"></a>parallel_for

`parallel_for`bir dizi endeks üzerinde yineleme ler ve kullanıcı tarafından sağlanan her yinelemede paralel olarak sağlanan bir işlevi yürütür.

```cpp
template <typename _Index_type, typename _Function, typename _Partitioner>
void parallel_for(
    _Index_type first,
    _Index_type last,
    _Index_type _Step,
    const _Function& _Func,
    _Partitioner&& _Part);

template <typename _Index_type, typename _Function>
void parallel_for(
    _Index_type first,
    _Index_type last,
    _Index_type _Step,
    const _Function& _Func);

template <typename _Index_type, typename _Function>
void parallel_for(
    _Index_type first,
    _Index_type last,
    const _Function& _Func,
    const auto_partitioner& _Part = auto_partitioner());

template <typename _Index_type, typename _Function>
void parallel_for(
    _Index_type first,
    _Index_type last,
    const _Function& _Func,
    const static_partitioner& _Part);

template <typename _Index_type, typename _Function>
void parallel_for(
    _Index_type first,
    _Index_type last,
    const _Function& _Func,
    const simple_partitioner& _Part);

template <typename _Index_type, typename _Function>
void parallel_for(
    _Index_type first,
    _Index_type last,
    const _Function& _Func,
    affinity_partitioner& _Part);
```

### <a name="parameters"></a>Parametreler

*_Index_type*<br/>
Yineleme için kullanılan dizin türü.

*_Function*<br/>
Her yinelemede yürütülecek işlevin türü.

*_Partitioner*<br/>
Sağlanan aralığı bölmek için kullanılan bölümleyici türü.

*Ilk*<br/>
Yinelemeye dahil edilecek ilk dizin.

*Son*<br/>
Yinelemeye dahil edilecek son dizin bir geçmiş dizin.

*_Step*<br/>
'ye `first` yinelenirken adım atmak `last`üzere olan değer Adım olumlu olmalı. [adım](../../../standard-library/invalid-argument-class.md) 1'den küçükse invalid_argument atılır.

*_Func*<br/>
Her yinelemede yürütülecek işlev. Bu bir lambda ifadesi, bir işlev işaretçisi veya imza `void operator()(_Index_type)`ile işlev çağrı işlecinin bir sürümünü destekleyen herhangi bir nesne olabilir.

*_Part*<br/>
Bölümleyici nesneye bir başvuru. Bağımsız `const` [değişken, auto_partitioner,](auto-partitioner-class.md)`&` `const` [static_partitioner,](static-partitioner-class.md)`&` `const` [simple_partitioner](simple-partitioner-class.md) `&` veya [affinity_partitioner](affinity-partitioner-class.md) `&` bir [affinity_partitioner](affinity-partitioner-class.md) nesnesi kullanılıyorsa, algoritmanın gelecekteki döngülerin yeniden kullanılabildiği durumu depolayabilmesi için başvurunun const olmayan bir l-değer başvurusu olması gerekir.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [Paralel Algoritmalar'a](../../../parallel/concrt/parallel-algorithms.md)bakın.

## <a name="parallel_for_each"></a><a name="parallel_for_each"></a>parallel_for_each

`parallel_for_each`bir aralıktaki her öğeye paralel olarak belirtilen bir işlev uygular. Ad alanındaki `for_each` işleve `std` semantik olarak eşdeğerdir, ancak öğeler üzerinde yineleme paralel olarak gerçekleştirilir ve yineleme sırası belirtilmemiştir. Bağımsız `_Func` değişken, parametrenin `T` üzerinde `operator()(T)` titreyen kapsayıcının madde türü olduğu formun işlev çağrı işlecinindesteklenmesi gerekir.

```cpp
template <typename _Iterator, typename _Function>
void parallel_for_each(
    _Iterator first,
    _Iterator last,
    const _Function& _Func);

template <typename _Iterator, typename _Function, typename _Partitioner>
void parallel_for_each(
    _Iterator first,
    _Iterator last,
    const _Function& _Func,
    _Partitioner&& _Part);
```

### <a name="parameters"></a>Parametreler

*_Iterator*<br/>
Kapsayıcıüzerinde yinelemek için kullanılan yineleyicinin türü.

*_Function*<br/>
Aralıktaki her öğeye uygulanacak işlevin türü.

*_Partitioner*<br/>
*Ilk*<br/>
Paralel yinelemeye dahil edilecek ilk öğenin konumunu ele alan bir yineleyici.

*Son*<br/>
Paralel yinelemeye eklenecek son öğeyi bir geçmiş konuma hitap eden bir yineleyici.

*_Func*<br/>
Aralıktaki her öğeye uygulanan kullanıcı tanımlı bir işlev nesnesi.

*_Part*<br/>
Bölümleyici nesneye bir başvuru. Bağımsız `const` [değişken, auto_partitioner,](auto-partitioner-class.md)`&` `const` [static_partitioner,](static-partitioner-class.md)`&` `const` [simple_partitioner](simple-partitioner-class.md) `&` veya [affinity_partitioner](affinity-partitioner-class.md) `&` bir [affinity_partitioner](affinity-partitioner-class.md) nesnesi kullanılıyorsa, algoritmanın gelecekteki döngülerin yeniden kullanılabildiği durumu depolayabilmesi için başvurunun const olmayan bir l-değer başvurusu olması gerekir.

### <a name="remarks"></a>Açıklamalar

[auto_partitioner](auto-partitioner-class.md) açık bir bölümleyici olmadan aşırı yük için kullanılacaktır.

Rasgele erişimi desteklemeyen yineleyiciler için yalnızca [auto_partitioner](auto-partitioner-class.md) desteklenir.

Daha fazla bilgi için [Paralel Algoritmalar'a](../../../parallel/concrt/parallel-algorithms.md)bakın.

## <a name="parallel_invoke"></a><a name="parallel_invoke"></a>Parallel_invoke

Verilen işlev nesnelerini paralel olarak parametreler olarak yürütür ve yürütmetamamlanana kadar engeller. Her işlev nesnesi bir lambda ifadesi, bir işlev işaretçisi veya `void operator()()`imza ile işlev çağrı işleci destekleyen herhangi bir nesne olabilir.

```cpp
template <typename _Function1, typename _Function2>
void parallel_invoke(
    const _Function1& _Func1,
    const _Function2& _Func2);

template <typename _Function1, typename _Function2, typename _Function3>
void parallel_invoke(
    const _Function1& _Func1,
    const _Function2& _Func2,
    const _Function3& _Func3);

template <typename _Function1,
    typename _Function2,
    typename _Function3,
    typename _Function4>
void parallel_invoke(
    const _Function1& _Func1,
    const _Function2& _Func2,
    const _Function3& _Func3,
    const _Function4& _Func4);

template <typename _Function1,
    typename _Function2,
    typename _Function3,
    typename _Function4,
    typename _Function5>
void parallel_invoke(
    const _Function1& _Func1,
    const _Function2& _Func2,
    const _Function3& _Func3,
    const _Function4& _Func4,
    const _Function5& _Func5);

template <typename _Function1,
    typename _Function2,
    typename _Function3,
    typename _Function4,
    typename _Function5,
    typename _Function6>
void parallel_invoke(
    const _Function1& _Func1,
    const _Function2& _Func2,
    const _Function3& _Func3,
    const _Function4& _Func4,
    const _Function5& _Func5,
    const _Function6& _Func6);

template <typename _Function1,
    typename _Function2,
    typename _Function3,
    typename _Function4,
    typename _Function5,
    typename _Function6,
    typename _Function7>
void parallel_invoke(
    const _Function1& _Func1,
    const _Function2& _Func2,
    const _Function3& _Func3,
    const _Function4& _Func4,
    const _Function5& _Func5,
    const _Function6& _Func6,
    const _Function7& _Func7);

template <typename _Function1,
    typename _Function2,
    typename _Function3,
    typename _Function4,
    typename _Function5,
    typename _Function6,
    typename _Function7,
    typename _Function8>
void parallel_invoke(
    const _Function1& _Func1,
    const _Function2& _Func2,
    const _Function3& _Func3,
    const _Function4& _Func4,
    const _Function5& _Func5,
    const _Function6& _Func6,
    const _Function7& _Func7,
    const _Function8& _Func8);

template <typename _Function1,
    typename _Function2,
    typename _Function3,
    typename _Function4,
    typename _Function5,
    typename _Function6,
    typename _Function7,
    typename _Function8,
    typename _Function9>
void parallel_invoke(
    const _Function1& _Func1,
    const _Function2& _Func2,
    const _Function3& _Func3,
    const _Function4& _Func4,
    const _Function5& _Func5,
    const _Function6& _Func6,
    const _Function7& _Func7,
    const _Function8& _Func8,
    const _Function9& _Func9);

template <typename _Function1,
    typename _Function2,
    typename _Function3,
    typename _Function4,
    typename _Function5,
    typename _Function6,
    typename _Function7,
    typename _Function8,
    typename _Function9,
    typename _Function10>
void parallel_invoke(
    const _Function1& _Func1,
    const _Function2& _Func2,
    const _Function3& _Func3,
    const _Function4& _Func4,
    const _Function5& _Func5,
    const _Function6& _Func6,
    const _Function7& _Func7,
    const _Function8& _Func8,
    const _Function9& _Func9,
    const _Function10& _Func10);
```

### <a name="parameters"></a>Parametreler

*_Function1*<br/>
Paralel olarak yürütülecek ilk işlev nesnesinin türü.

*_Function2*<br/>
Paralel olarak yürütülecek ikinci işlev nesnesinin türü.

*_Function3*<br/>
Paralel olarak yürütülecek üçüncü işlev nesnesinin türü.

*_Function4*<br/>
Paralel olarak yürütülecek dördüncü işlev nesnesinin türü.

*_Function5*<br/>
Paralel olarak yürütülecek beşinci işlev nesnesinin türü.

*_Function6*<br/>
Paralel olarak yürütülecek altıncı işlev nesnesinin türü.

*_Function7*<br/>
Paralel olarak yürütülecek yedinci işlev nesnesinin türü.

*_Function8*<br/>
Paralel olarak yürütülecek sekizinci işlev nesnesinin türü.

*_Function9*<br/>
Paralel olarak yürütülecek dokuzuncu işlev nesnesinin türü.

*_Function10*<br/>
Paralel olarak yürütülecek onuncu işlev nesnesinin türü.

*_Func1*<br/>
Paralel olarak yürütülecek ilk işlev nesnesi.

*_Func2*<br/>
İkinci işlev nesnesi paralel olarak yürütülecek.

*_Func3*<br/>
Üçüncü işlev nesnesi paralel olarak yürütülecek.

*_Func4*<br/>
Dördüncü işlev nesnesi paralel olarak yürütülecek.

*_Func5*<br/>
Paralel olarak yürütülecek beşinci işlev nesnesi.

*_Func6*<br/>
Paralel olarak yürütülecek altıncı işlev nesnesi.

*_Func7*<br/>
Yedinci işlev nesnesi paralel olarak yürütülecek.

*_Func8*<br/>
Paralel olarak yürütülecek sekizinci işlev nesnesi.

*_Func9*<br/>
Paralel olarak yürütülecek dokuzuncu işlev nesnesi.

*_Func10*<br/>
Onuncu işlev nesnesi paralel olarak yürütülecek.

### <a name="remarks"></a>Açıklamalar

Parametreler olarak sağlanan işlev nesnelerinden birinin veya birkaçının çağrı bağlamında satır satır yürütebileceğini unutmayın.

Bu işleviçin parametre olarak geçirilen işlev nesnelerinden biri veya birkaçı bir özel durum oluşturursa, çalışma zamanı kendi seçtiği `parallel_invoke`bir özel durum seçip çağrının dışına yayacaktır.

Daha fazla bilgi için [Paralel Algoritmalar'a](../../../parallel/concrt/parallel-algorithms.md)bakın.

## <a name="parallel_radixsort"></a><a name="parallel_radixsort"></a>parallel_radixsort

Radix sıralama algoritması kullanarak, belirli bir aralıktaki öğeleri alçalmayan bir sıraya dizir. Bu, öğeleri imzasız tamsayı benzeri anahtarlara sıralanabilecek bir projeksiyon işlevi gerektiren kararlı bir sıralama işlevidir. Sıralanan öğeler için varsayılan başlatma gereklidir.

```cpp
template<typename _Random_iterator>
inline void parallel_radixsort(
    const _Random_iterator& _Begin,
    const _Random_iterator& _End);

template<typename _Allocator, typename _Random_iterator>
inline void parallel_radixsort(
    const _Random_iterator& _Begin,
    const _Random_iterator& _End);

template<typename _Allocator, typename _Random_iterator>
inline void parallel_radixsort(
    const _Allocator& _Alloc,
    const _Random_iterator& _Begin,
    const _Random_iterator& _End);

template<typename _Random_iterator, typename _Function>
inline void parallel_radixsort(
    const _Random_iterator& _Begin,
    const _Random_iterator& _End,
    const _Function& _Proj_func,
    const size_t _Chunk_size = 256* 256);

template<typename _Allocator, typename _Random_iterator,
    typename _Function>
inline void parallel_radixsort(
    const _Random_iterator& _Begin,
    const _Random_iterator& _End,
    const _Function& _Proj_func,
    const size_t _Chunk_size = 256* 256);

template<typename _Allocator,
    typename _Random_iterator,
    typename _Function>
inline void parallel_radixsort(
    const _Allocator& _Alloc,
    const _Random_iterator& _Begin,
    const _Random_iterator& _End,
    const _Function& _Proj_func,
    const size_t _Chunk_size = 256* 256);
```

### <a name="parameters"></a>Parametreler

*_Random_iterator*<br/>
Giriş aralığının yineleyici türü.

*_Allocator*<br/>
C++ Standart Kitaplığı uyumlu bellek ayırıcısının türü.

*_Function*<br/>
Projeksiyon işlevinin türü.

*_Begin*<br/>
Sıralanacak aralıktaki ilk öğenin konumunu ele alan rasgele erişim yineleyici.

*_End*<br/>
Sıralanacak aralıktaki son öğeyi bir geçmiş pozisyonadrese leyen rasgele erişim yineleyici.

*_Alloc*<br/>
C++ Standart Kitaplık uyumlu bellek ayırıcısının bir örneği.

*_Proj_func*<br/>
Bir öğeyi integral değerine dönüştüren kullanıcı tanımlı projeksiyon işlevi nesnesi.

*_Chunk_size*<br/>
Paralel yürütme için ikiye bölünecek bir parçanın mimimum boyutu.

### <a name="remarks"></a>Açıklamalar

Tüm aşırı `n * sizeof(T)` yüklemeler ek `n` alan gerektirir, sıralanacak öğe `T` sayısı ve öğe türü. Bir öğe türü `I _Proj_func(T)` `T` `I` ve imzasız tamsayı benzeri bir tür olduğu bir öğe verildiğinde bir anahtar döndürmek için imza ile unary projeksiyon functor gereklidir.

Bir projeksiyon işlevi sağlamazsanız, integral türleri için öğeyi yalnızca döndüren varsayılan bir projeksiyon işlevi kullanılır. Öğe bir projeksiyon işlevi yokluğunda ayrılmaz bir tür değilse işlev derlemek için başarısız olur.

Bir ayırıcı türü veya örneği sağlamazsanız, arabelleği `std::allocator<T>` ayırmak için C++ Standart Kitaplık bellek ayırıcısı kullanılır.

Algoritma giriş aralığını iki parçaya böler ve birbirini izleyen olarak her bir parçayı paralel olarak yürütülmesi için iki alt parçaya böler. İsteğe `_Chunk_size` bağlı bağımsız değişken, algoritmaya boyut < parçalarını `_Chunk_size` < işlemesi gerektiğini belirtmek için kullanılabilir.

## <a name="parallel_reduce"></a><a name="parallel_reduce"></a>parallel_reduce

Birbirini izleyen kısmi toplamları hesaplayarak belirli bir aralıktaki tüm öğelerin toplamını hesaplar veya benzer şekilde toplam dışında belirli bir ikili işlemden elde edilen ardışık kısmi sonuçların sonucunu paralel olarak hesaplar. `parallel_reduce`anlamsal olarak benzerdir `std::accumulate`, ancak ikili işlemin birleştirici olmasını gerektirir ve başlangıç değeri yerine bir kimlik değeri gerektirir.

```cpp
template<typename _Forward_iterator>
inline typename std::iterator_traits<_Forward_iterator>::value_type parallel_reduce(
    _Forward_iterator _Begin,
    _Forward_iterator _End,
    const typename std::iterator_traits<_Forward_iterator>::value_type& _Identity);

template<typename _Forward_iterator, typename _Sym_reduce_fun>
inline typename std::iterator_traits<_Forward_iterator>::value_type parallel_reduce(
    _Forward_iterator _Begin,
    _Forward_iterator _End,
    const typename std::iterator_traits<_Forward_iterator>::value_type& _Identity,
    _Sym_reduce_fun _Sym_fun);

template<typename _Reduce_type,
    typename _Forward_iterator,
    typename _Range_reduce_fun,
    typename _Sym_reduce_fun>
inline _Reduce_type parallel_reduce(
    _Forward_iterator _Begin,
    _Forward_iterator _End,
    const _Reduce_type& _Identity,
    const _Range_reduce_fun& _Range_fun,
    const _Sym_reduce_fun& _Sym_fun);
```

### <a name="parameters"></a>Parametreler

*_Forward_iterator*<br/>
Giriş aralığının yineleyici türü.

*_Sym_reduce_fun*<br/>
Simetrik azaltma fonksiyonunun türü. Bu, _Reduce_type kimlik türü `_Reduce_type _Sym_fun(_Reduce_type, _Reduce_type)`ve azaltma nın sonuç türüyle aynı olduğu imzalı bir işlev türü olmalıdır. Üçüncü aşırı yük için, bu çıkış türü `_Range_reduce_fun`ile tutarlı olmalıdır.

*_Reduce_type*<br/>
Giriş öğesi türünden farklı olabilecek giriş türü. İade değeri ve kimlik değeri bu türe sahiptir.

*_Range_reduce_fun*<br/>
Aralık azaltma işlevinin türü. Bu imza `_Reduce_type _Range_fun(_Forward_iterator, _Forward_iterator, _Reduce_type)`ile bir işlev türü olmalıdır, _Reduce_type kimlik türü ve azaltma sonuç türü ile aynıdır.

*_Begin*<br/>
Aralıktaki ilk öğeyi ele alan bir giriş yineleyicisi azaltılabilir.

*_End*<br/>
Azaltılacak aralıktaki son öğenin ötesinde ki bir konum olan öğeyi ele alan bir giriş yineleyici.

*_Identity*<br/>
Kimlik değeri, `_Identity` azaltmanın sonuç türüyle ve birinci ve `value_type` ikinci aşırı yüklemeler için yine yinelemenin sonucuyla aynı türdendir. Üçüncü aşırı yük için kimlik değeri, azaltmanın sonuç türüyle aynı türe sahip `value_type` olmalıdır, ancak yineleyicinin binden farklı olabilir. Bu, aralık azaltma işlecinin, `_Range_fun`tek bir tür `value_type` öğesi ve kimlik değeri aralığına uygulandığında, türden `value_type` kimlik türüne değer dökümü gibi bir şekilde çalışması gibi uygun bir değere sahip olmalıdır.

*_Sym_fun*<br/>
Azaltmanın ikinci sinde kullanılacak simetrik fonksiyon. Daha fazla bilgi için Açıklamalar'a bakın.

*_Range_fun*<br/>
Azaltmanın ilk aşamasında kullanılacak işlev. Daha fazla bilgi için Açıklamalar'a bakın.

### <a name="return-value"></a>Dönüş Değeri

Azaltma nın sonucu.

### <a name="remarks"></a>Açıklamalar

Paralel bir azaltma gerçekleştirmek için, işlev, altprogramcının kullanabileceği çalışan sayısına bağlı olarak aralığı parçalara böler. Azaltma iki aşamada gerçekleşir, ilk aşama her yığın içinde bir azalma gerçekleştirir ve ikinci aşama her yığın kısmi sonuçlar arasında bir azalma gerçekleştirir.

İlk aşırı `value_type`yük, yinelemenin , `T`kimlik değeri türüyle ve azaltma sonuç türüyle aynı olmasını gerektirir. T öğesi, her bir `T T::operator + (T)` yığındaki öğeleri azaltmak için işleci sağlamalıdır. Aynı işleç ikinci aşamada da kullanılır.

İkinci aşırı yük, yinelemenin kimlik değeri `value_type` türüyle ve azaltma sonuç türüyle aynı olmasını da gerektirir. Sağlanan ikili işleç, `_Sym_fun` ilk aşamanın başlangıç değeri olarak kimlik değeri yle birlikte her iki azaltma aşamasında da kullanılır.

Üçüncü aşırı yükleme için kimlik değeri türü azaltma sonucu türüyle aynı olmalıdır, ancak `value_type` yineleyicininki her ikisinden de farklı olabilir. Aralık azaltma `_Range_fun` işlevi ilk aşamada kimlik değeri ilk değer olarak kullanılır ve `_Sym_reduce_fun` ikili işlev ikinci aşamada alt sonuçlara uygulanır.

## <a name="parallel_sort"></a><a name="parallel_sort"></a>parallel_sort

Belirli bir aralıktaki öğeleri alçalan olmayan bir sıraya veya ikili yüklem tarafından belirtilen bir sıralama ölçütüne göre paralel olarak düzenler. Bu işlev, karşılaştırma tabanlı, kararsız, yerinde sıralama olması anlamsal olarak benzer. `std::sort`

```cpp
template<typename _Random_iterator>
inline void parallel_sort(
    const _Random_iterator& _Begin,
    const _Random_iterator& _End);

template<typename _Random_iterator,typename _Function>
inline void parallel_sort(
    const _Random_iterator& _Begin,
    const _Random_iterator& _End,
    const _Function& _Func,
    const size_t _Chunk_size = 2048);
```

### <a name="parameters"></a>Parametreler

*_Random_iterator*<br/>
Giriş aralığının yineleyici türü.

*_Function*<br/>
İkili karşılaştırma functor türü.

*_Begin*<br/>
Sıralanacak aralıktaki ilk öğenin konumunu ele alan rasgele erişim yineleyici.

*_End*<br/>
Sıralanacak aralıktaki son öğeyi bir geçmiş pozisyonadrese leyen rasgele erişim yineleyici.

*_Func*<br/>
Sıralamada birbirini izleyen öğeler tarafından karşılanacak karşılaştırma ölçütlerini tanımlayan kullanıcı tanımlı yüklem işlev nesnesi. İkili yüklem iki bağımsız değişken alır ve tatmin olduğunda **doğru** **ve** doğru olmadığında doğru döndürür. Bu karşılaştırıcı işlev, dizideki öğe çiftlerine katı bir zayıf sıralama dayatmalıdır.

*_Chunk_size*<br/>
Paralel yürütme için ikiye bölünecek bir öycünün minimum boyutu.

### <a name="remarks"></a>Açıklamalar

İlk aşırı yük ikili karşılaştırıcı `std::less`kullanır.

Aşırı yüklenen ikinci, giriş aralığındaki öğelerin türü `bool _Func(T, T)` olan `T` imzaya sahip olması gereken sağlanan ikili karşılaştırıcıyı kullanır.

Algoritma giriş aralığını iki parçaya böler ve birbirini izleyen olarak her bir parçayı paralel olarak yürütülmesi için iki alt parçaya böler. İsteğe `_Chunk_size` bağlı bağımsız değişken, algoritmaya boyut < parçalarını `_Chunk_size` < işlemesi gerektiğini belirtmek için kullanılabilir.

## <a name="parallel_transform"></a><a name="parallel_transform"></a>parallel_transform

Kaynak aralığındaki her öğeye veya iki kaynak aralığından bir öğe çiftine belirtilen işlev nesnesini uygular ve işlev nesnesinin dönüş değerlerini paralel olarak bir hedef aralığına kopyalar. Bu işlevsel anlamsal olarak `std::transform`.

```cpp
template <typename _Input_iterator1,
    typename _Output_iterator,
    typename _Unary_operator>
_Output_iterator parallel_transform(
    _Input_iterator1 first1,
    _Input_iterator1 last1,
    _Output_iterator _Result,
    const _Unary_operator& _Unary_op,
    const auto_partitioner& _Part = auto_partitioner());

template <typename _Input_iterator1,
    typename _Output_iterator,
    typename _Unary_operator>
_Output_iterator parallel_transform(
    _Input_iterator1 first1,
    _Input_iterator1 last1,
    _Output_iterator _Result,
    const _Unary_operator& _Unary_op,
    const static_partitioner& _Part);

template <typename _Input_iterator1,
    typename _Output_iterator,
    typename _Unary_operator>
_Output_iterator parallel_transform(
    _Input_iterator1 first1,
    _Input_iterator1 last1,
    _Output_iterator _Result,
    const _Unary_operator& _Unary_op,
    const simple_partitioner& _Part);

template <typename _Input_iterator1,
    typename _Output_iterator,
    typename _Unary_operator>
_Output_iterator parallel_transform(
    _Input_iterator1 first1,
    _Input_iterator1 last1,
    _Output_iterator _Result,
    const _Unary_operator& _Unary_op,
    affinity_partitioner& _Part);

template <typename _Input_iterator1,
    typename _Input_iterator2,
    typename _Output_iterator,
    typename _Binary_operator,
    typename _Partitioner>
_Output_iterator parallel_transform(
    _Input_iterator1 first1,
    _Input_iterator1 last1,
    _Input_iterator2
first2,
    _Output_iterator _Result,
    const _Binary_operator& _Binary_op,
    _Partitioner&& _Part);

template <typename _Input_iterator1,
    typename _Input_iterator2,
    typename _Output_iterator,
    typename _Binary_operator>
_Output_iterator parallel_transform(
    _Input_iterator1 first1,
    _Input_iterator1 last1,
    _Input_iterator2
first2,
    _Output_iterator _Result,
    const _Binary_operator& _Binary_op);
```

### <a name="parameters"></a>Parametreler

*_Input_iterator1*<br/>
İlk veya tek giriş yineleyicitürü.

*_Output_iterator*<br/>
Çıktı yineleyicisinin türü.

*_Unary_operator*<br/>
Giriş aralığındaki her öğe üzerinde yürütülecek unary functor türü.

*_Input_iterator2*<br/>
İkinci giriş yineleyicitürü.

*_Binary_operator*<br/>
İkili functor türü iki kaynak aralığından elemanlar üzerinde çift yönlü yürütülür.

*_Partitioner*<br/>
*ilk1*<br/>
İşletilecek ilk veya tek kaynak aralığındaki ilk öğenin konumunu ele alan bir giriş yineleyici.

*son1*<br/>
İşletilecek ilk veya tek kaynak aralığındaki son öğeyi bir geçmiş pozisyona hitap eden bir giriş yineleyici.

*_Result*<br/>
Hedef aralıktaki ilk öğenin konumunu ele alan bir çıktı yineleyicisi.

*_Unary_op*<br/>
Kaynak aralığındaki her öğeye uygulanan kullanıcı tanımlı unary işlev nesnesi.

*_Part*<br/>
Bölümleyici nesneye bir başvuru. Bağımsız `const` [değişken, auto_partitioner,](auto-partitioner-class.md)`&` `const` [static_partitioner,](static-partitioner-class.md)`&` `const` [simple_partitioner](simple-partitioner-class.md) `&` veya [affinity_partitioner](affinity-partitioner-class.md) `&` bir [affinity_partitioner](affinity-partitioner-class.md) nesnesi kullanılıyorsa, algoritmanın gelecekteki döngülerin yeniden kullanılabildiği durumu depolayabilmesi için başvurunun const olmayan bir l-değer başvurusu olması gerekir.

*ilk2*<br/>
İşletilecek ikinci kaynak aralığındaki ilk öğenin konumunu ele alan bir giriş yineleyici.

*_Binary_op*<br/>
İki kaynak aralığına forward sırasına göre çift yönlü olarak uygulanan kullanıcı tanımlı ikili işlev nesnesi.

### <a name="return-value"></a>Dönüş Değeri

İşlev nesnesi tarafından dönüştürülmüş çıkış öğelerini alan hedef aralıktaki son öğeyi bir geçmiş konuma hitap eden bir çıktı yineleyicisi.

### <a name="remarks"></a>Açıklamalar

[auto_partitioner](auto-partitioner-class.md) açık bir bölümleyici bağımsız değişken olmadan aşırı yüklemeler için kullanılacaktır.

Rasgele erişimi desteklemeyen yineleyiciler için yalnızca [auto_partitioner](auto-partitioner-class.md) desteklenir.

Bağımsız değişkeni `_Unary_op` alan aşırı yükler, giriş aralığındaki her öğeye unary functor uygulayarak giriş aralığını çıkış aralığına dönüştürür. `_Unary_op`üzerinde titreedilen aralığın `T` değer türü olan imza `operator()(T)` ile işlev çağrı işleci desteklemesi gerekir.

Bağımsız değişkeni `_Binary_op` alan aşırı yükler, ikili functor'ı ilk giriş aralığından bir elemana ve ikinci giriş aralığından bir öğeye uygulayarak iki giriş aralığını çıkış aralığına dönüştürür. `_Binary_op`iki giriş yineleyicisinin `operator()(T, U)` değer `T` `U` türleri olan imza ile işlev çağrı işleci desteklemesi gerekir.

Daha fazla bilgi için [Paralel Algoritmalar'a](../../../parallel/concrt/parallel-algorithms.md)bakın.

## <a name="receive"></a><a name="receive"></a>Almak

Genel bir uygulama almak, bir bağlam tam olarak bir kaynaktan veri beklemek ve kabul edilen değerleri filtrelemek için izin verir.

```cpp
template <class T>
T receive(
    _Inout_ ISource<T>* _Src,
    unsigned int _Timeout = COOPERATIVE_TIMEOUT_INFINITE);

template <class T>
T receive(
    _Inout_ ISource<T>* _Src,
    typename ITarget<T>::filter_method const& _Filter_proc,
    unsigned int _Timeout = COOPERATIVE_TIMEOUT_INFINITE);

template <class T>
T receive(
    ISource<T>& _Src,
    unsigned int _Timeout = COOPERATIVE_TIMEOUT_INFINITE);

template <class T>
T receive(
    ISource<T>& _Src,
    typename ITarget<T>::filter_method const& _Filter_proc,
    unsigned int _Timeout = COOPERATIVE_TIMEOUT_INFINITE);
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Yük türü.

*_Src*<br/>
Verilerin beklendiği kaynağa bir işaretçi veya başvuru.

*_Timeout*<br/>
Yöntemin veriler için milisaniye cinsinden olması gereken maksimum süre.

*_Filter_proc*<br/>
İletilerin kabul edilip edilmemesi gerektiğini belirleyen bir filtre işlevi.

### <a name="return-value"></a>Dönüş Değeri

Kaynaktan, yük türünden bir değer.

### <a name="remarks"></a>Açıklamalar

Parametrenin `_Timeout` sabitten `COOPERATIVE_TIMEOUT_INFINITE`başka bir değeri varsa, ileti alınmadan önce belirtilen süre dolduğunda, özel durum [operation_timed_out](operation-timed-out-class.md) atılır. Sıfır uzunlukta bir zaman alabilmesini istiyorsanız, daha verimli olduğu `receive` ve zaman `0` adabına özel durumlar atmaması nedeniyle (sıfır) bir zaman aramadan aramanın aksine [try_receive](concurrency-namespace-functions.md) işlevini kullanmalısınız.

Daha fazla bilgi için [İleti Geçme İşlevlerini](../../../parallel/concrt/message-passing-functions.md)görün.

## <a name="run_with_cancellation_token"></a><a name="run_with_cancellation_token"></a>run_with_cancellation_token

Belirli bir iptal belirteci bağlamında bir işlev nesnesini hemen ve eşzamanlı olarak yürütür.

```cpp
template<typename _Function>
void run_with_cancellation_token(
    const _Function& _Func,
    cancellation_token _Ct);
```

### <a name="parameters"></a>Parametreler

*_Function*<br/>
Çağrılacak işlev nesnesinin türü.

*_Func*<br/>
Yürütülecek işlev nesnesi. Bu nesne void (void) bir imza ile işlev çağrı işleci desteklenmelidir.

*_Ct*<br/>
İşlev nesnesinin örtülü iptalini kontrol edecek iptal belirteci. İşlevin yürütmesini, bir üst görev grubundan örtülü iptal etme olasılığı olmadan yürütmek istiyorsanız kullanın. `cancellation_token::none()`

### <a name="remarks"></a>Açıklamalar

İşlev nesnesindeki herhangi bir kesinti `cancellation_token` noktası iptal edildiğinde tetiklenir. Açık belirteç, `_Ct` `_Func` ebeveynin farklı bir belirteci veya belirteci yoksa bunu üst iptalden yalıtacaktır.

## <a name="send"></a><a name="send"></a>Gönder

Hedef iletiyi kabul edene veya reddedene kadar bekleyen eşzamanlı gönderme işlemi.

```cpp
template <class T>
bool send(_Inout_ ITarget<T>* _Trg, const T& _Data);

template <class T>
bool send(ITarget<T>& _Trg, const T& _Data);
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Yük türü.

*_Trg*<br/>
Verilerin gönderildiği hedefe bir işaretçi veya başvuru.

*_Data*<br/>
Gönderilecek verilere bir başvuru.

### <a name="return-value"></a>Dönüş Değeri

mesaj kabul edildiyse **doğru,** aksi takdirde **yanlış.**

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [İleti Geçme İşlevlerini](../../../parallel/concrt/message-passing-functions.md)görün.

## <a name="set_ambient_scheduler"></a><a name="set_ambient_scheduler"></a>set_ambient_scheduler

```cpp
inline void set_ambient_scheduler(std::shared_ptr<::Concurrency::scheduler_interface> _Scheduler);
```

### <a name="parameters"></a>Parametreler

*_Scheduler*<br/>
Ayarlanacak ortam zamanlayıcısı.

## <a name="set_task_execution_resources"></a><a name="set_task_execution_resources"></a>set_task_execution_resources

Eşzamanlılık Runtime iç iş parçacığı tarafından kullanılan yürütme kaynaklarını belirtilen afinite kümesiyle kısıtlar.

Bu yöntemi yalnızca Kaynak Yöneticisi oluşturulmadan önce veya iki Kaynak Yöneticisi yaşam süresi arasında aramak geçerlidir. Kaynak Yöneticisi çağırma sırasında bulunmadığı sürece birden çok kez çağrılabilir. Bir yakınlık sınırı ayarlandıktan sonra, `set_task_execution_resources` yönteme bir sonraki geçerli çağrıya kadar geçerli kalır.

Verilen yakınlık maskesi, işlem afiyet maskesinin bir alt kümesi olmamalıdır. Gerekirse işlem yakınlığı güncellenecektir.

```cpp
void __cdecl set_task_execution_resources(
    DWORD_PTR _ProcessAffinityMask);

void __cdecl set_task_execution_resources(
    unsigned short count,
    PGROUP_AFFINITY _PGroupAffinity);
```

### <a name="parameters"></a>Parametreler

*_ProcessAffinityMask*<br/>
Eşzamanlı Çalışma Zamanı çalışma iş parçacıklarının sınırlandırılacak olan yakınlık maskesi. Bu yöntemi, yalnızca Eşzamanlılık Çalışma Süresini geçerli işlemci grubunun bir alt kümesiyle sınırlamak istiyorsanız, 64'ten büyük donanım iş parçacığına sahip bir sistemde kullanın. Genel olarak, 64'ten büyük donanım iş parçacığıolan makinelerdeki yakınlığı kısıtlamak için bir dizi grup yakınlığını parametre olarak kabul eden yöntemin sürümünü kullanmanız gerekir.

*Sayısı*<br/>
Parametre `_PGroupAffinity` `GROUP_AFFINITY` tarafından belirtilen dizideki giriş sayısı.

*_PGroupAffinity*<br/>
Bir dizi `GROUP_AFFINITY` giriş.

### <a name="remarks"></a>Açıklamalar

Kaynak Yöneticisi çağrıldığı anda varsa yöntem [invalid_operation](invalid-operation-class.md) bir özel durum ve afiyet in boş bir kaynak kümesiyle sonuçlanırsa [invalid_argument](../../../standard-library/invalid-argument-class.md) bir özel durum oluşturur.

Bir parametre olarak grup yakınlıkları bir dizi alır yöntemin sürümü yalnızca sürüm Windows 7 veya daha yüksek işletim sistemlerinde kullanılmalıdır. Aksi takdirde, [invalid_operation](invalid-operation-class.md) bir özel durum atılır.

Bu yöntem çağrıldıktan sonra işlem yakınlığını programlı bir şekilde değiştirmek, Kaynak Yöneticisi'nin kısıtlandığı yakınlığı yeniden değerlendirmesine neden olmaz. Bu nedenle, bu yöntemi aramadan önce işlem yakınlığı tüm değişiklikler yapılmalıdır.

## <a name="swap"></a><a name="swap"></a>Takas

İki `concurrent_vector` nesnenin öğelerini değiştirir.

```cpp
template<typename T, class _Ax>
inline void swap(
    concurrent_vector<T, _Ax>& _A,
    concurrent_vector<T, _Ax>& _B);
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Eşzamanlı vektörlerde depolanan öğelerin veri türü.

*_Ax*<br/>
Eşzamanlı vektörlerin ayırıcı türü.

*_A*<br/>
Elementleri eşzamanlı vektörünkilerle değiş tokuş edilecek eşzamanlı `_B`vektör.

*_B*<br/>
Değiştirilecek öğeleri sağlayan eşzamanlı vektör veya öğeleri eşzamanlı vektörünkilerle değiştirilecek olan vektör. `_A`

### <a name="remarks"></a>Açıklamalar

Şablon işlevi, üye işlevi `concurrent_vector` `_A`yürütmek için kapsayıcı sınıfında uzmanlaşmış bir algoritmadır. [concurrent_vector::swap](concurrent-vector-class.md#swap) `_B`( ). Bunlar, işlev şablonlarının derleyici tarafından kısmi sıralanması örnekleridir. Şablon işlevleri, şablonun işlev çağrısıyla eşleşmesi benzersiz olmayacak şekilde aşırı yüklendiğinde, derleyici şablon işlevinin en özel sürümünü seçer. Şablon işlevinin genel sürümü, `template <class T> void swap(T&, T&)`algoritma sınıfında atama ile çalışır ve yavaş bir işlemdir. Kapsayıcı sınıfının iç gösterimi ile çalışabilir gibi her kapsayıcıda özelleştirilmiş sürümü çok daha hızlıdır.

Bu yöntem eşzamanlılık güvenli değildir. Bu yöntemi aradığınızda eşzamanlı vektörlerden herhangi birinde başka iş parçacığı nın işlem gerçekleştirmediğinden emin olmalısınız.

## <a name="task_from_exception"></a><a name="task_from_exception"></a>task_from_exception

```cpp
template<typename _TaskType, typename _ExType>
task<_TaskType> task_from_exception(
    _ExType _Exception,
    const task_options& _TaskOptions = task_options());
```

### <a name="parameters"></a>Parametreler

*_TaskType*<br/>

*_ExType*<br/>

*_Exception*<br/>

*_TaskOptions*<br/>

### <a name="return-value"></a>Dönüş Değeri

## <a name="task_from_result"></a><a name="task_from_result"></a>task_from_result

```cpp
template<typename T>
task<T> task_from_result(
    T _Param,
    const task_options& _TaskOptions = task_options());

inline task<bool> task_from_result(ool _Param);

inline task<void> task_from_result(
    const task_options& _TaskOptions = task_options());
```

### <a name="parameters"></a>Parametreler

*T*<br/>

*_Param*<br/>

*_TaskOptions*<br/>

### <a name="return-value"></a>Dönüş Değeri

## <a name="trace_agents_register_name"></a><a name="trace_agents_register_name"></a>Trace_agents_register_name

Verilen adı ETW izlemedeki ileti bloğuna veya aracısına yapıştırın.

```cpp
template <class T>
void Trace_agents_register_name(
    _Inout_ T* _PObject,
    _In_z_ const wchar_t* _Name);
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Nesnenin türü. Bu genellikle bir ileti bloğu veya aracıdır.

*_PObject*<br/>
İzde adı geçen ileti bloğu veya aracısına işaretçi.

*_Name*<br/>
Verilen nesnenin adı.

## <a name="try_receive"></a><a name="try_receive"></a>try_receive

Bir bağlamın tam olarak tek bir kaynaktan veri aramasına ve kabul edilen değerleri filtrelemesine olanak tanıyan genel bir try-receive uygulaması. Veriler hazır değilse, yöntem **yanlış**döndürecek.

```cpp
template <class T>
bool try_receive(_Inout_ ISource<T>* _Src, T& _value);

template <class T>
bool try_receive(
    _Inout_ ISource<T>* _Src,
    T& _value,
    typename ITarget<T>::filter_method const& _Filter_proc);

template <class T>
bool try_receive(ISource<T>& _Src, T& _value);

template <class T>
bool try_receive(
    ISource<T>& _Src,
    T& _value,
    typename ITarget<T>::filter_method const& _Filter_proc);
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Yük türü

*_Src*<br/>
Verilerin beklendiği kaynağa bir işaretçi veya başvuru.

*_value*<br/>
Sonucun yerleştirileceği konuma başvuru.

*_Filter_proc*<br/>
İletilerin kabul edilip edilmemesi gerektiğini belirleyen bir filtre işlevi.

### <a name="return-value"></a>Dönüş Değeri

Yükün `bool` `_value`yerleştirilip yerleştirilmediğini belirten bir değer.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [İleti Geçme İşlevlerini](../../../parallel/concrt/message-passing-functions.md)görün.

## <a name="wait"></a><a name="wait"></a>Bekle

Geçerli bağlamı belirli bir süre duraklatıyor.

```cpp
void __cdecl wait(unsigned int _Milliseconds);
```

### <a name="parameters"></a>Parametreler

*_Milliseconds*<br/>
Geçerli bağlamın duraklatmalı milisaniye sayısı. `_Milliseconds` Parametre değere `0`ayarlanmışsa, geçerli bağlam devam etmeden önce diğer çalıştırılabilen bağlamlara yürütme sağlamalıdır.

### <a name="remarks"></a>Açıklamalar

Bu yöntem Eşzamanlılık Çalışma Zamanı zamanlayıcısı bağlamında çağrılırsa, zamanlayıcı temel kaynakta çalışacak farklı bir bağlam bulur. Zamanlayıcı doğada işbirliği olduğundan, bu bağlam tam olarak belirtilen milisaniye sayısından sonra devam edemez. Zamanlayıcı, zamanlamacıya işbirliği içinde verim vermeyen diğer görevleri yürütmekle meşgulse, bekleme süresi belirsiz olabilir.

## <a name="when_all"></a><a name="when_all"></a>when_all

Bağımsız değişken olarak sağlanan tüm görevler başarıyla tamamlandığında başarıyla tamamlanacak bir görev oluşturur.

```cpp
template <typename _Iterator>
auto when_all(
    _Iterator _Begin,
    _Iterator _End,
    const task_options& _TaskOptions = task_options()) ->
    decltype (details::_WhenAllImpl<typename std::iterator_traits<_Iterator>::value_type::result_type,
    _Iterator>::_Perform(_TaskOptions, _Begin,  _End));
```

### <a name="parameters"></a>Parametreler

*_Iterator*<br/>
Giriş yineleyicisinin türü.

*_Begin*<br/>
Eleman lar aralığındaki ilk öğenin konumu, elde edilen göreve birleştirilir.

*_End*<br/>
İlk öğenin, ortaya çıkan göreve birleştirilmesi gereken öğe aralığının ötesindeki konumu.

*_TaskOptions*<br/>
`task_options` nesnesi.

### <a name="return-value"></a>Dönüş Değeri

Tüm giriş görevleri başarıyla tamamlandığında başarıyla tamamlayan bir görev. Giriş görevleri türde `T`ise, bu işlevin çıktısı `task<std::vector<T>>`. Giriş görevleri tür `void` varsa çıktı görevi de bir `task<void>`.

### <a name="remarks"></a>Açıklamalar

`when_all`sonucu olarak bir üreten olmayan `task` bir engelleme işlevidir. [Görev aksine::bekleyin](task-class.md#wait), ASTA (Application STA) iş parçacığı üzerinde bir UWP uygulamasında bu işlevi aramak için güvenlidir.

Görevlerden biri iptal edilirse veya özel durum atarsa, döndürülen görev iptal edilen durumda erken tamamlanır ve görev::get [task::get](task-class.md#get) veya `task::wait` bu görevde çağırırsanız, özel durum, oluşursa, atılır.

Daha fazla bilgi için [Görev Paralelliği'ne](../../../parallel/concrt/task-parallelism-concurrency-runtime.md)bakın.

## <a name="when_any"></a><a name="when_any"></a>when_any

Bağımsız değişken olarak sağlanan görevlerden herhangi biri başarıyla tamamlandığında başarıyla tamamlanacak bir görev oluşturur.

```cpp
template<typename _Iterator>
auto when_any(
    _Iterator _Begin,
    _Iterator _End,
    const task_options& _TaskOptions = task_options())
    -> decltype (
        details::_WhenAnyImpl<
            typename std::iterator_traits<_Iterator>::value_type::result_type,
            _Iterator>::_Perform(_TaskOptions, _Begin, _End));

template<typename _Iterator>
auto when_any(
    _Iterator _Begin,
    _Iterator _End,
    cancellation_token _CancellationToken)
       -> decltype (
           details::_WhenAnyImpl<
               typename std::iterator_traits<_Iterator>::value_type::result_type,
               _Iterator>::_Perform(_CancellationToken._GetImplValue(), _Begin, _End));
```

### <a name="parameters"></a>Parametreler

*_Iterator*<br/>
Giriş yineleyicisinin türü.

*_Begin*<br/>
Eleman lar aralığındaki ilk öğenin konumu, elde edilen göreve birleştirilir.

*_End*<br/>
İlk öğenin, ortaya çıkan göreve birleştirilmesi gereken öğe aralığının ötesindeki konumu.

*_TaskOptions*<br/>
*_CancellationToken*<br/>
İade edilen görevin iptalini kontrol eden iptal belirteci. İptal belirteci sağlamazsanız, ortaya çıkan görev, tamamlanmasına neden olan görevin iptal jetonunu alır.

### <a name="return-value"></a>Dönüş Değeri

Giriş görevlerinden herhangi biri başarıyla tamamlandığında başarıyla tamamlayan bir görev. Giriş görevleri türdeise, `T`bu işlevin çıktısı, `task<std::pair<T, size_t>>>`çiftin ilk öğesinin tamamlanan görevin sonucu olduğu ve ikinci öğenin tamamlanan görevin dizini olduğu bir iştiraki olacaktır. Giriş görevleri tür `void` varsa çıktı, sonuç `task<size_t>`tamamlanan görevin dizini olduğu bir.

### <a name="remarks"></a>Açıklamalar

`when_any`sonucu olarak bir üreten olmayan `task` bir engelleme işlevidir. [Görev aksine::bekleyin](task-class.md#wait), ASTA (Application STA) iş parçacığı üzerinde bir UWP uygulamasında bu işlevi aramak için güvenlidir.

Daha fazla bilgi için [Görev Paralelliği'ne](../../../parallel/concrt/task-parallelism-concurrency-runtime.md)bakın.

## <a name="see-also"></a>Ayrıca bkz.

[concurrency Ad Alanı](concurrency-namespace.md)
