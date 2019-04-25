---
title: Eşzamanlılık ad alanı işlevleri
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
ms.openlocfilehash: 9cb726ccc475d6d08e036229d0d06089e3fac31c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62163747"
---
# <a name="concurrency-namespace-functions"></a>Eşzamanlılık ad alanı işlevleri

||||
|-|-|-|
|[Ayırma](#alloc)|[CreateResourceManager](#createresourcemanager)|[DisableTracing](#disabletracing)|
|[EnableTracing](#enabletracing)|[Ücretsiz](#free)|[GetExecutionContextId](#getexecutioncontextid)|
|[GetOSVersion](#getosversion)|[GetProcessorCount](#getprocessorcount)|[GetProcessorNodeCount](#getprocessornodecount)|
|[GetSchedulerId](#getschedulerid)|[Trace_agents_register_name](#trace_agents_register_name)|[asend](#asend)|
|[cancel_current_task](#cancel_current_task)|[Temizle](#clear)|[create_async](#create_async)|
|[create_task](#create_task)|[get_ambient_scheduler](#get_ambient_scheduler)|[internal_assign_iterators](#internal_assign_iterators)|
|[interruption_point](#interruption_point)|[is_current_task_group_canceling](#is_current_task_group_canceling)|[make_choice](#make_choice)|
|[make_greedy_join](#make_greedy_join)|[make_join](#make_join)|[make_task](#make_task)|
|[parallel_buffered_sort](#parallel_buffered_sort)|[parallel_for](#parallel_for)|[parallel_for_each](#parallel_for_each)|
|[parallel_invoke](#parallel_invoke)|[parallel_radixsort](#parallel_radixsort)|[parallel_reduce](#parallel_reduce)|
|[parallel_sort](#parallel_sort)|[parallel_transform](#parallel_transform)|[Alma](#receive)|
|[run_with_cancellation_token](#run_with_cancellation_token)|[Gönder](#send)|[set_ambient_scheduler](#set_ambient_scheduler)|
|[set_task_execution_resources](#set_task_execution_resources)|[değiştirme](#swap)|[task_from_exception](#task_from_exception)|
|[task_from_result](#task_from_result)|[try_receive](#try_receive)|[bekleme](#wait)|
|[when_all](#when_all)|[when_any](#when_any)|

##  <a name="alloc"></a>  Ayırma

Eşzamanlılık Çalışma zamanı önbelleğe alma ayırıcısını ' belirtilen boyut, bellek bloğu ayırır.

```
void* __cdecl Alloc(size_t _NumBytes);
```

### <a name="parameters"></a>Parametreler

*_NumBytes*<br/>
Ayrılacak bellek bayt sayısı.

### <a name="return-value"></a>Dönüş Değeri

Yeni ayrılan bellek işaretçisi.

### <a name="remarks"></a>Açıklamalar

Uygulamanızdaki senaryoları hakkında yararlı önbelleğe alma ayırıcısını kullanarak daha fazla bilgi için bkz. [Görev Zamanlayıcı](../../../parallel/concrt/task-scheduler-concurrency-runtime.md).

##  <a name="asend"></a>  asend

Hedef blok verileri yaymak için bir görevi zamanlar bir zaman uyumsuz gönderme işlemi.

```
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
Gönderilecek veri türü.

*_Trg*<br/>
Bir işaretçi veya başvuru veri gönderildiği hedef.

*_Data*<br/>
Gönderilecek verileri bir başvuru.

### <a name="return-value"></a>Dönüş Değeri

**doğru** yöntemi döndürülen önce iletiyi kabul edilirse **false** Aksi takdirde.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [ileti geçirme işlevleri](../../../parallel/concrt/message-passing-functions.md).

##  <a name="cancel_current_task"></a>  cancel_current_task

Şu anda yürütülmekte olan görevi iptal eder. Bu işlev görevin yürütülmesini durdurmak ve girmesine neden bir görevin gövdesinden çağrılabilir `canceled` durumu.

Gövdesinde değilseniz bu işlevin çağrılmasında desteklenen bir senaryo değil bir `task`. Bunun yapılması bir kilitlenme veya uygulamanızdaki bir takılma gibi tanımsız davranışa neden olur.

```
inline __declspec(noreturn) void __cdecl cancel_current_task();
```

##  <a name="clear"></a>  Temizle

Tüm yok etme eşzamanlı kuyruk temizler şu anda sıradaki öğeleri. Bu yöntem eşzamanlı güvenli değil.

```
template<typename T, class _Ax>
void concurrent_queue<T, _Ax>::clear();
```

### <a name="parameters"></a>Parametreler

*T*<br/>

*_Ax*<br/>

##  <a name="create_async"></a>  create_async

Bir kullanıcı tarafından sağlanan lambda veya işlev nesnesine bağlı bir Windows çalışma zamanı zaman uyumsuz bir yapı oluşturur. Dönüş türünü `create_async` herhangi biri `IAsyncAction^`, `IAsyncActionWithProgress<TProgress>^`, `IAsyncOperation<TResult>^`, veya `IAsyncOperationWithProgress<TResult, TProgress>^` yönteme geçirilen lambda'nın imzası göre.

```
template<typename _Function>
__declspec(noinline) auto create_async(const _Function& _Func)
    -> decltype(ref new details::_AsyncTaskGeneratorThunk<_Function>(_Func));
```

### <a name="parameters"></a>Parametreler

*_Function*<br/>
Yazın.

*_Func*<br/>
Windows çalışma zamanı zaman uyumsuz bir yapı oluşturulacağı lambda veya işlev nesnesi.

### <a name="return-value"></a>Dönüş Değeri

Iasyncaction tarafından temsil edilen zaman uyumsuz bir yapı ^, Iasyncactionwithprogress\<TProgress > ^, Iasyncoperation\<TResult > ^, veya Iasyncoperationwithprogress\<TResult, TProgress > ^. Döndürülen arabirim işleve geçirilen lambda imzası bağlıdır.

### <a name="remarks"></a>Açıklamalar

Lambda dönüş türü, yapı eylemi veya bir işlem olup olmadığını belirler.

Boş dönüş veren Lambda'lar Eylemler oluşturulmasına neden. Türünün bir sonucu veren Lambda'lar `TResult` TResult işlemlerini oluşturulmasına neden olur.

Lambda döndürebilir bir `task<TResult>` , uyumsuz işi kendi içinde saklayan veya zaman uyumsuz işi temsil eden görev zincirinin devamı niteliğindedir. Bu durumda, görevler zaman uyumsuz olarak yürütülen olduğundan lambdanın kendisi satır içinde olduğundan ve lambdanın dönüş türü tarafından döndürülen zaman uyumsuz bir yapı oluşturmak için sarmalanmamış olur `create_async`. Bu bir lambda, bir görev döndürür gelir\<void > Eylemler ve bir görev döndüren bir lambda oluşturulmasına neden olacak\<TResult > TResult işlemlerini oluşturulmasına neden olur.

Lambda ya da sıfır, bir veya iki bağımsız değişken alabilir. Geçerli bağımsız değişkenler `progress_reporter<TProgress>` ve `cancellation_token`, sipariş hem de kullanılıyorsa bu. Bağımsız değişkenler olmadan bir lambda, ilerleme durumunu raporlama yeteneği olmadan zaman uyumsuz bir yapı oluşturulmasına neden olur. Progress_reporter alan bir lambda\<TProgress > neden olacak `create_async` , TProgress türünde ilerleme raporları her zaman uyumsuz bir yapı döndürmesine `report` progress_reporter nesnesinin yöntemi çağrılır. Cancellation_token alan bir lambda iptalleri denetlemek için bu belirteci kullanın veya zaman uyumsuz yapının iptalinin, bu görevlerin iptaline neden oluşturduğu görevlere iletin.

Lambda veya işlev nesnesi gövdesi bir sonuç döndürürse (ve bir görev\<TResult >), sı MTA bağlamında bir görev çalışma zamanı, örtük olarak oluşturur için işlem içinde zaman uyumsuz olarak yürütülür. `IAsyncInfo::Cancel` Yöntemi örtülü görevin iptali neden olur.

Gövdesi lambda döndürür bir görev, lamba satır içi yürütülür ve türünde bir bağımsız değişken almak için lambda bildirmek `cancellation_token` oluştururken de bu belirteci ileterek lambda içinde oluşturma herhangi bir görevi iptal etme işlemini tetikleyebilir. Ayrıca `register_callback` yöntemi çağırdığınızda, bir geri çağırma çalışma zamanı için belirteçte `IAsyncInfo::Cancel` zaman uyumsuz işlem veya eylem üretilen...

Bu işlev, yalnızca Windows çalışma zamanı uygulamaları için kullanılabilir.

##  <a name="createresourcemanager"></a>  CreateResourceManager

Eşzamanlılık Çalışma zamanı Kaynak Yöneticisi'nin tekil örneğini temsil eden bir arabirim döndürür. Kaynak Yöneticisi birbirleriyle işbirliği istediğiniz planlayıcılar için kaynakları atamak ile sorumludur.

```
IResourceManager* __cdecl CreateResourceManager();
```

### <a name="return-value"></a>Dönüş Değeri

Bir `IResourceManager` arabirimi.

### <a name="remarks"></a>Açıklamalar

Bu yöntemi izleyen birden çok çağrı Kaynak Yöneticisi'nin aynı örneğini döndürür. Yöntemine yapılan her çağrı bir başvuru Kaynak Yöneticisi'nde saymak ve çağrısı ile eşleştirilmesi gerekir [Iresourcemanager::Release](iresourcemanager-structure.md) yöntemi zamanlayıcınız Kaynak Yöneticisi ile iletişim kurulurken.

[unsupported_os](unsupported-os-class.md) işletim sistemi eşzamanlılık çalışma zamanı tarafından desteklenmiyorsa oluşturulur.

##  <a name="create_task"></a>  create_task

Oluşturur [görev](task-class.md) nesne. `create_task` kullanılabilir herhangi bir görev oluşturucuyu kullandığınız. Kullanılmasına izin verdiğinden çok uygunluk açısından sağlanır `auto` görevler oluşturulurken anahtar sözcüğü.

```
template<typename T>
__declspec(noinline) auto create_task(T _Param, const task_options& _TaskOptions = task_options())
    -> task<typename details::_TaskTypeFromParam<T>::T>;

template<typename _ReturnType>
__declspec( noinline) task<_ReturnType> create_task(const task<_ReturnType>& _Task);
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Görevin kendisinden oluşturulacağı parametre türü.

*_ReturnType*<br/>
Yazın.

*_Param*<br/>
İçinden görevin kendisinden oluşturulacağı parametre. Bu bir lambda veya işlev nesnesi olabilir bir `task_completion_event` nesnesi, farklı `task` nesnesi veya bir Windows::Foundation:: ıasyncınfo arabirimi UWP uygulamanızda görevler kullanıyorsanız.

*_TaskOptions*<br/>
Görev seçenekleri.

*_Task*<br/>
Oluşturulacak görev.

### <a name="return-value"></a>Dönüş Değeri

Yeni bir görev türü `T`, yani içinden gösterilen `_Param`.

### <a name="remarks"></a>Açıklamalar

İlk aşırı yükleme, tek bir parametre alan bir görev Oluşturucusu gibi çalışır.

İkinci aşırı yükleme, yeni oluşturulan görevle sağlanan iptal belirtecini ilişkilendirir. Bu aşırı yüklemesini kullanıyorsanız, farklı bir geçmesine izin verilmez `task` ilk parametre olarak nesne.

Döndürülen görevin türü işlevin ilk parametresinden algılanır. Varsa `_Param` olduğu bir `task_completion_event<T>`, `task<T>`, veya her iki türü döndüren bir işlevse `T` veya `task<T>`, oluşturulan görev türü `task<T>`.

Bir UWP uygulamasında, `_Param` ıasyncoperation türünde\<T > ^ veya Windows::Foundation:: ıasyncoperationwithprogress\<T, P > ^, ya da bu türlerin birini döndüren bir işlevse, oluşturulan görev olacak tür `task<T>`. Varsa `_Param` ıasyncoperation ^ veya Windows::Foundation:: ıasyncactionwithprogress\<P > ^, ya da bu türlerin birini döndüren bir işlevse, oluşturulan görev türüdür `task<void>`.

##  <a name="disabletracing"></a>  DisableTracing

Eşzamanlılık Çalışma zamanında izleme devre dışı bırakır. ETW İzleme, varsayılan olarak kaydı olduğundan, bu işlev kullanım dışı bırakılmıştır.

```
__declspec(deprecated("Concurrency::DisableTracing is a deprecated function.")) _CRTIMP HRESULT __cdecl DisableTracing();
```

### <a name="return-value"></a>Dönüş Değeri

İzleme doğru bir şekilde devre dışı bırakılmışsa `S_OK` döndürülür. İzleme daha önce başlatılmadı ise `E_NOT_STARTED` döndürülür

##  <a name="enabletracing"></a>  EnableTracing

Eşzamanlılık Çalışma zamanında izleme sağlar. ETW İzleme şu anda varsayılan olarak etkin olduğundan, bu işlev kullanım dışı bırakılmıştır.

```
__declspec(deprecated("Concurrency::EnableTracing is a deprecated function.")) _CRTIMP HRESULT __cdecl EnableTracing();
```

### <a name="return-value"></a>Dönüş Değeri

İzleme doğru başlatılmışsa `S_OK` döndürülmüştür; Aksi takdirde `E_NOT_STARTED` döndürülür.

##  <a name="free"></a>  Ücretsiz

Tarafından önceden ayrılan bellek bloğunu serbest bırakır `Alloc` eşzamanlılık çalışma zamanı önbelleğe alma ayırıcısını için yöntemi.

```
void __cdecl Free(_Pre_maybenull_ _Post_invalid_ void* _PAllocation);
```

### <a name="parameters"></a>Parametreler

*_PAllocation*<br/>
Tarafından önceden ayrılan bellek işaretçisi `Alloc` serbest bırakılacak olan yöntem. Parametre `_PAllocation` değere ayarlanmış `NULL`, bu yöntem bunu yok sayıp hemen geri döner.

### <a name="remarks"></a>Açıklamalar

Uygulamanızdaki senaryoları hakkında yararlı önbelleğe alma ayırıcısını kullanarak daha fazla bilgi için bkz. [Görev Zamanlayıcı](../../../parallel/concrt/task-scheduler-concurrency-runtime.md).

##  <a name="get_ambient_scheduler"></a>  get_ambient_scheduler

```
inline std::shared_ptr<::Concurrency::scheduler_interface> get_ambient_scheduler();
```

### <a name="return-value"></a>Dönüş Değeri

##  <a name="getexecutioncontextid"></a>  GetExecutionContextId

Uygulayan bir yürütme bağlamına atanmış benzersiz bir tanımlayıcı döndürür `IExecutionContext` arabirimi.

```
unsigned int __cdecl GetExecutionContextId();
```

### <a name="return-value"></a>Dönüş Değeri

Bir yürütme bağlamı için benzersiz bir tanımlayıcı.

### <a name="remarks"></a>Açıklamalar

Geçirdiğiniz önce yürütme bağlamı için bir tanıtıcı elde etmek için bu yöntemi kullanın. bir `IExecutionContext` kaynak yöneticisi tarafından sağlanan yöntemlerden birini bir parametre olarak.

##  <a name="getosversion"></a>  GetOSVersion

İşletim sistemi sürümünü döndürür.

```
IResourceManager::OSVersion __cdecl GetOSVersion();
```

### <a name="return-value"></a>Dönüş Değeri

İşletim sistemini temsil eden numaralandırılmış değer.

### <a name="remarks"></a>Açıklamalar

[unsupported_os](unsupported-os-class.md) işletim sistemi eşzamanlılık çalışma zamanı tarafından desteklenmiyorsa oluşturulur.

##  <a name="getprocessorcount"></a>  GetProcessorCount

Temel sistemdeki donanım iş parçacıklarının sayısını döndürür.

```
unsigned int __cdecl GetProcessorCount();
```

### <a name="return-value"></a>Dönüş Değeri

Donanım iş parçacıklarının sayısı.

### <a name="remarks"></a>Açıklamalar

[unsupported_os](unsupported-os-class.md) işletim sistemi eşzamanlılık çalışma zamanı tarafından desteklenmiyorsa oluşturulur.

##  <a name="getprocessornodecount"></a>  GetProcessorNodeCount

Temel sistemdeki NUMA düğümlerinin veya işlemci paketlerinin sayısını döndürür.

```
unsigned int __cdecl GetProcessorNodeCount();
```

### <a name="return-value"></a>Dönüş Değeri

NUMA düğümlerinin veya işlemci paketlerinin sayısı.

### <a name="remarks"></a>Açıklamalar

Sistem İşlemci paketine göre birden fazla NUMA düşümü içeriyorsa, NUMA düğümü sayısı döndürülür, aksi halde işlemci paketleri sayısı döndürülür.

[unsupported_os](unsupported-os-class.md) işletim sistemi eşzamanlılık çalışma zamanı tarafından desteklenmiyorsa oluşturulur.

##  <a name="getschedulerid"></a>  GetSchedulerId

Uygulayan bir zamanlayıcı atanmış benzersiz bir tanımlayıcı döndürür `IScheduler` arabirimi.

```
unsigned int __cdecl GetSchedulerId();
```

### <a name="return-value"></a>Dönüş Değeri

Bir zamanlayıcı için benzersiz bir tanımlayıcı.

### <a name="remarks"></a>Açıklamalar

Scheduler için geçirdiğiniz önce bir tanımlayıcı elde etmek için bu yöntemi kullanın. bir `IScheduler` kaynak yöneticisi tarafından sağlanan yöntemlerden birini bir parametre olarak.

##  <a name="internal_assign_iterators"></a>  internal_assign_iterators

```
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

*ilk*<br/>

*Son*<br/>

##  <a name="interruption_point"></a>  interruption_point

İptali için bir kesinti noktası oluşturur. Bu durum, iptal burada bu işlev çağrılır bağlamında devam ediyorsa, o anda yürütülen paralel iş yürütülmesini durdurur bir iç özel durum oluşturur. İptal ediyor değil ise, işlev hiçbir şey yapmaz.

```
inline void interruption_point();
```

### <a name="remarks"></a>Açıklamalar

Tarafından oluşturulan iç iptal özel durum yakalamalısınız değil `interruption_point()` işlevi. Özel durum yakalandı ve çalışma zamanı tarafından işlenir ve bu yakalama programınızı anormal bir şekilde davranmasına neden olabilir.

##  <a name="is_current_task_group_canceling"></a>  is_current_task_group_canceling

Bir gösterge olup görev grubu, şu anda geçerli bağlamda satır içi yürütüyor etkin bir iptalin ortasında (veya kısa süre içinde olacaktır) döndürür. Satır içi geçerli bağlam üzerinde şu anda yürütülen görev grubu ise unutmayın `false` döndürülür.

```
bool __cdecl is_current_task_group_canceling();
```

### <a name="return-value"></a>Dönüş Değeri

**doğru** şu anda yürütülmekte olan görev grubunu iptal ediliyor durumunda **false** Aksi takdirde.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [iptal](../../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md#cancellation).

##  <a name="make_choice"></a>  make_choice

Oluşturur bir `choice` isteğe bağlı bir Mesajlaşma bloğundan `Scheduler` veya `ScheduleGroup` ve iki veya daha fazla giriş kaynağı.

```
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
İlk kaynağın mesaj engelleme türü.

*T2*<br/>
İkinci kaynağın mesaj engelleme türü.

*_PScheduler*<br/>
`Scheduler` İçinde Yayma görevi için nesne `choice` ileti bloğu zamanlandı.

*_Item1*<br/>
İlk kaynak.

*_Item2*<br/>
İkinci kaynak.

*_Öğeler*<br/>
Ek kaynaklar.

*_PScheduleGroup*<br/>
`ScheduleGroup` İçinde Yayma görevi için nesne `choice` ileti bloğu zamanlandı. `Scheduler` Kullanılan nesnesi zamanlama grubu tarafından belirtilir.

### <a name="return-value"></a>Dönüş Değeri

A `choice` iki veya daha fazla giriş kaynağı ile ileti bloğu.

##  <a name="make_greedy_join"></a>  make_greedy_join

Oluşturur bir `greedy multitype_join` isteğe bağlı bir Mesajlaşma bloğundan `Scheduler` veya `ScheduleGroup` ve iki veya daha fazla giriş kaynağı.

```
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
İlk kaynağın mesaj engelleme türü.

*T2*<br/>
İkinci kaynağın mesaj engelleme türü.

*_PScheduler*<br/>
`Scheduler` İçinde Yayma görevi için nesne `multitype_join` ileti bloğu zamanlandı.

*_Item1*<br/>
İlk kaynak.

*_Item2*<br/>
İkinci kaynak.

*_Öğeler*<br/>
Ek kaynaklar.

*_PScheduleGroup*<br/>
`ScheduleGroup` İçinde Yayma görevi için nesne `multitype_join` ileti bloğu zamanlandı. `Scheduler` Kullanılan nesnesi zamanlama grubu tarafından belirtilir.

### <a name="return-value"></a>Dönüş Değeri

A `greedy multitype_join` iki veya daha fazla giriş kaynağı ile ileti bloğu.

##  <a name="make_join"></a>  make_join

Oluşturur bir `non_greedy multitype_join` isteğe bağlı bir Mesajlaşma bloğundan `Scheduler` veya `ScheduleGroup` ve iki veya daha fazla giriş kaynağı.

```
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
İlk kaynağın mesaj engelleme türü.

*T2*<br/>
İkinci kaynağın mesaj engelleme türü.

*_PScheduler*<br/>
`Scheduler` İçinde Yayma görevi için nesne `multitype_join` ileti bloğu zamanlandı.

*_Item1*<br/>
İlk kaynak.

*_Item2*<br/>
İkinci kaynak.

*_Öğeler*<br/>
Ek kaynaklar.

*_PScheduleGroup*<br/>
`ScheduleGroup` İçinde Yayma görevi için nesne `multitype_join` ileti bloğu zamanlandı. `Scheduler` Kullanılan nesnesi zamanlama grubu tarafından belirtilir.

### <a name="return-value"></a>Dönüş Değeri

A `non_greedy multitype_join` iki veya daha fazla giriş kaynağı ile ileti bloğu.

##  <a name="make_task"></a>  make_task

Oluşturmak için Üreteç yöntemi bir `task_handle` nesne.

```
template <class _Function>
task_handle<_Function> make_task(const _Function& _Func);
```

### <a name="parameters"></a>Parametreler

*_Function*<br/>
Tarafından temsil edilen iş yürütme için çağrılacak işlev nesnesinin türü `task_handle` nesne.

*_Func*<br/>
Tarafından temsil edilen iş yürütme için çağrılacak işlev `task_handle` nesne. Bu bir lambda işlevse, bir işlev işaretçisine olabilir veya herhangi bir işlev çağrısı işleci imzalı sürümünü destekleyen nesne `void operator()()`.

### <a name="return-value"></a>Dönüş Değeri

A `task_handle` nesne.

### <a name="remarks"></a>Açıklamalar

Bu işlev oluşturmak ihtiyacınız olduğunda yararlıdır bir `task_handle` lambda functor true türünü bilmeden nesne oluşturmanıza izin verdiğinden sahip bir lambda ifadesi, nesne.

##  <a name="parallel_buffered_sort"></a>  parallel_buffered_sort

Belirtilen bir aralıktaki öğeleri azalmayan veya paralel bir ikili koşula göre belirtilen bir sıralama ölçütüne göre düzenler. Bu işlev anlam olarak benzerdir, `std::sort` ihtiyacı, tek farkı, karşılaştırma tabanlı kararsız, yerinde bir sıralama, `O(n)` ek alan ve varsayılan olarak başlatılması için sıralanan öğeleri gerektirir.

```
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
Olan giriş aralığındaki yineleyici türü.

*_Allocator*<br/>
C++ Standart Kitaplığı uyumlu bellek ayırıcı türü.

*_Function*<br/>
İkili karşılaştırıcı türü.

*_Begin*<br/>
Sıralanacak aralıktaki ilk öğenin konumunu bulan bir rasgele erişim yineleyicisi.

*_Bitiş*<br/>
Sıralanacak aralığın son öğesinde geçmiş konumu ele alan bir rasgele erişim yineleyicisi.

*_Alloc*<br/>
Bir C++ Standart Kitaplığı uyumlu bellek ayırıcısı örneği.

*_Func*<br/>
Sıralama, ardışık öğeleri tarafından karşılanması için karşılaştırma ölçütü tanımlayan bir kullanıcı tanımlı işlevin doğrulama nesnesi. İkili koşulu, iki bağımsız değişkeni alır ve döndürür **true** karşılanmazsa ve **false** koşullar karşılanırsa. Bu bir karşılaştırıcı işlevi, katı bir zayıf çiftlerini dizisindeki öğelerin sıralama dayatır gerekir.

*_Chunk_size*<br/>
Paralel yürütme için iki halinde bölme bir öbek depolayabilmek boyutu.

### <a name="remarks"></a>Açıklamalar

Tüm aşırı yüklemeler gerektiren `n * sizeof(T)` ek alan burada `n` sıralanacak, öğe sayısı ve `T` öğe türü. Çoğu durumda, üzerinde performansında bir gelişme parallel_buffered_sort gösterecektir [parallel_sort](concurrency-namespace-functions.md), ve kullanılabilir bellek varsa parallel_sort kullanmanız gerekir.

İkili bir karşılaştırıcı sağlamazsanız `std::less` işleci sağlamak öğe türü gerektiren varsayılan olarak kullanılan `operator<()`.

Bir ayırıcı türü veya örnek, C++ Standart Kitaplığı bellek ayırıcısı sağlamazsanız `std::allocator<T>` arabellek ayırmak için kullanılır.

Algoritma olan giriş aralığındaki iki öbeklere böler ve sırayla her bir öbeği Paralel yürütme için iki alt öbeklere böler. İsteğe bağlı bağımsız değişkeni `_Chunk_size` algoritmaya, işleme öbek boyutunu belirtmek için kullanılan < `_Chunk_size` seri olarak.

##  <a name="parallel_for"></a>  parallel_for

`parallel_for` bir dizi dizinleri üzerinden yinelenir ve her yineleme sırasında bir kullanıcı tarafından sağlanan işlev paralel olarak yürütür.

```
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
Her yinelemede, yürütülecek işlev türü.

*_Partitioner*<br/>
Sağlanan aralık bölümlemek için kullanılan bölümleyici türü.

*ilk*<br/>
Yinelemede dahil edilecek ilk dizini.

*Son*<br/>
Dizin bir önceki yinelemede eklenecek son dizini.

*_Step*<br/>
Gelen yineleme adım adım değeri `first` için `last`. Adım pozitif olmalıdır. [invalid_argument](../../../standard-library/invalid-argument-class.md) adım 1'den az ise oluşturulur.

*_Func*<br/>
Her yinelemede, yürütülecek işlev. Bu bir lambda ifadesi bir işlev işaretçisi olabilir veya herhangi bir işlev çağrısı işleci imzalı sürümünü destekleyen nesne `void operator()(_Index_type)`.

*_Part*<br/>
Bölümleyici nesnesine bir başvuru. Bağımsız değişken şunlardan biri olabilir `const` [auto_partitioner](auto-partitioner-class.md)`&`, `const` [static_partitioner](static-partitioner-class.md)`&`, `const` [simple_ bölümleyici](simple-partitioner-class.md) `&` veya [affinity_partitioner](affinity-partitioner-class.md) `&` varsa bir [affinity_partitioner](affinity-partitioner-class.md) nesnesi kullanılır, başvurusu const olmayan bir l-değeri olmalıdır algoritma durumu yeniden kullanmak gelecekteki döngüler için depolayabileceğiniz başvuru.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [paralel algoritmalar](../../../parallel/concrt/parallel-algorithms.md).

##  <a name="parallel_for_each"></a>  parallel_for_each

`parallel_for_each` paralel bir aralıktaki her öğeye belirtilen işlevi uygular. Anlamsal olarak eşdeğer olan `for_each` işlevi `std` ad alanı, bu yineleme öğeleri üzerinde paralel olarak gerçekleştirilir ve yineleme sırası belirtilmezse dışında. Bağımsız değişken `_Func` biçiminde bir işlev çağrısı işleci desteklemelidir `operator()(T)` burada parametre `T` üzerinden yinelenir kapsayıcı öğe türü.

```
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
Kapsayıcı yineleme yapmak için kullanılan yineleyici türü.

*_Function*<br/>
Aralıktaki her öğeye uygulanacak işlev türü.

*_Partitioner*<br/>
*ilk*<br/>
Paralel yineleme dahil edilecek ilk öğenin konumunu ele alan bir yineleyici.

*Son*<br/>
Paralel yineleme dahil edilecek bir son öğeden önceki öğenin konumunu ele alan bir yineleyici.

*_Func*<br/>
Aralıktaki her öğeye uygulanan kullanıcı tanımlı işlev nesnesi.

*_Part*<br/>
Bölümleyici nesnesine bir başvuru. Bağımsız değişken şunlardan biri olabilir `const` [auto_partitioner](auto-partitioner-class.md)`&`, `const` [static_partitioner](static-partitioner-class.md)`&`, `const` [simple_ bölümleyici](simple-partitioner-class.md) `&` veya [affinity_partitioner](affinity-partitioner-class.md) `&` varsa bir [affinity_partitioner](affinity-partitioner-class.md) nesnesi kullanılır, başvurusu const olmayan bir l-değeri olmalıdır algoritma durumu yeniden kullanmak gelecekteki döngüler için depolayabileceğiniz başvuru.

### <a name="remarks"></a>Açıklamalar

[auto_partitioner](auto-partitioner-class.md) açık bir bölümleyici olmadan aşırı yüklemesi kullanılır.

Rastgele desteklemeyen yineleyiciler erişim, yalnızca [auto_partitioner](auto-partitioner-class.md) desteklenir.

Daha fazla bilgi için [paralel algoritmalar](../../../parallel/concrt/parallel-algorithms.md).

##  <a name="parallel_invoke"></a>  parallel_invoke

Paralel ve blokları parametreler olarak yürütülen bitinceye kadar sağlanan işlev nesneleri yürütür. Her işlev nesnesi bir lambda ifadesi bir işlev işaretçisine olabilir veya imzaya sahip işlev çağrısı işleci destekleyen herhangi nesne `void operator()()`.

```
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
Paralel olarak yürütülecek ikinci işlev nesnesi.

*_Func3*<br/>
Paralel olarak yürütülecek üçüncü işlev nesnesi.

*_Func4*<br/>
Paralel olarak yürütülecek dördüncü işlev nesnesi.

*_Func5*<br/>
Paralel olarak yürütülecek beşinci işlev nesnesi.

*_Func6*<br/>
Paralel olarak yürütülecek altıncı işlev nesnesi.

*_Func7*<br/>
Paralel olarak yürütülecek yedinci işlev nesnesi.

*_Func8*<br/>
Paralel olarak yürütülecek sekizinci işlev nesnesi.

*_Func9*<br/>
Paralel olarak yürütülecek dokuzuncu işlev nesnesi.

*_Func10*<br/>
Paralel olarak yürütülecek onuncu işlev nesnesi.

### <a name="remarks"></a>Açıklamalar

Parametreleri, satır içi arama bağlamda yürütebilir gibi bir veya daha fazla işlev nesneleri, sağlanan unutmayın.

Bir veya daha fazla parametre olarak bu işleve geçirilen işlev nesneleri bir özel durum oluşturursa, çalışma zamanı kendi seçtiğiniz bir tür özel durumu seçin ve çağrı dışına yayan `parallel_invoke`.

Daha fazla bilgi için [paralel algoritmalar](../../../parallel/concrt/parallel-algorithms.md).

##  <a name="parallel_radixsort"></a>  parallel_radixsort

Belirtilen bir aralıktaki öğeleri, bir taban Sıralama algoritması kullanarak bir olmayan azalan düzenler. Bu öğeleri işaretsiz tamsayı benzeri anahtarlara sıralanacak yansıtabilirsiniz bir projeksiyon işlevi gerektiren tutarlı bir sıralama işlevdir. Varsayılan olarak başlatılması için sıralanan öğeleri gereklidir.

```
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
Olan giriş aralığındaki yineleyici türü.

*_Allocator*<br/>
C++ Standart Kitaplığı uyumlu bellek ayırıcı türü.

*_Function*<br/>
Projeksiyon işlev türü.

*_Begin*<br/>
Sıralanacak aralıktaki ilk öğenin konumunu bulan bir rasgele erişim yineleyicisi.

*_Bitiş*<br/>
Sıralanacak aralığın son öğesinde geçmiş konumu ele alan bir rasgele erişim yineleyicisi.

*_Alloc*<br/>
Bir C++ Standart Kitaplığı uyumlu bellek ayırıcısı örneği.

*_Proj_func*<br/>
Bir öğe bir tamsayı değerine dönüştürür bir projeksiyon kullanıcı tanımlı işlev nesnesi.

*_Chunk_size*<br/>
Paralel yürütme için iki halinde bölme bir öbek depolayabilmek boyutu.

### <a name="remarks"></a>Açıklamalar

Tüm aşırı yüklemeler gerektiren `n * sizeof(T)` ek alan burada `n` sıralanacak, öğe sayısı ve `T` öğe türü. İmzalı bir birli projeksiyon functor `I _Proj_func(T)` bir öğe verildiğinde bir anahtarı döndürmek için gerekli burada `T` öğe türü ve `I` işaretsiz bir tamsayı benzeri türüdür.

Bir projeksiyon işlevi sağlamazsanız, yalnızca öğe döndüren bir varsayılan yansıtma işlevi tam sayı türleri için kullanılır. İşlev öğesi bir tamsayı türü olmadığında bir projeksiyon işlevi değil. derlemeniz başarısız olur.

Bir ayırıcı türü veya örnek, C++ Standart Kitaplığı bellek ayırıcısı sağlamazsanız `std::allocator<T>` arabellek ayırmak için kullanılır.

Algoritma olan giriş aralığındaki iki öbeklere böler ve sırayla her bir öbeği Paralel yürütme için iki alt öbeklere böler. İsteğe bağlı bağımsız değişkeni `_Chunk_size` algoritmaya, işleme öbek boyutunu belirtmek için kullanılan < `_Chunk_size` seri olarak.

##  <a name="parallel_reduce"></a>  parallel_reduce

Art arda gelen kısmi toplamları tarafından belirtilen bir aralıktaki tüm öğelerin toplamını hesaplar veya benzer şekilde paralel olarak belirtilen bir ikili işlem toplam, dışındaki kullanımından elde edilen art arda gelen kısmi sonuçların sonucunu hesaplar. `parallel_reduce` anlamsal olarak benzer `std::accumulate`, ikili işlem ilişkilendirilebilir olmasını gerektirir ve bir başlangıç değeri yerine bir kimlik değeri gerektirir.

```
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
Giriş aralığındaki yineleyici türü.

*_Sym_reduce_fun*<br/>
Simetrik azaltma işlevi türü. Bu imzaya sahip bir işlev türü olmalıdır `_Reduce_type _Sym_fun(_Reduce_type, _Reduce_type)`burada _Reduce_type kimlik türü ve azaltma sonuç türü aynıdır. Üçüncü aşırı yükleme için bu çıkış türü ile tutarlı olmalıdır `_Range_reduce_fun`.

*_Reduce_type*<br/>
İnput öğesi türünden farklı olabilen, giriş için azaltacak türü. Kimlik değeri ve dönüş değeri bu türüne sahip.

*_Range_reduce_fun*<br/>
Aralık azaltma işlevi türü. Bu imzaya sahip bir işlev türü olmalıdır `_Reduce_type _Range_fun(_Forward_iterator, _Forward_iterator, _Reduce_type)`, _Reduce_type aynıdır kimlik türü ve azaltma sonuç türü.

*_Begin*<br/>
Azaltılmasına aralıktaki ilk öğeyi ele alan bir giriş yineleyici.

*_Bitiş*<br/>
Azaltılmasına aralığındaki son öğenin ötesinde bir konumu öğeyi ele alan giriş yineleyici.

*_Identity*<br/>
Kimlik değeri `_Identity` azaltma sonuç türü ile aynı türde ve aynı zamanda `value_type` birinci ve ikinci aşırı yüklemeleri için bir yineleyici. Üçüncü aşırı yükleme için kimlik değeri azaltma sonuç türünü aynı türe sahip olmalıdır, ancak farklı olabilir `value_type` yineleyici. Uygun bir değer olmalıdır şekilde aralık azaltma işleci `_Range_fun`, bir dizi türünde tek bir öğe için uygulandığında `value_type` ve kimlik değeri, davranacağını gibi bir cast türünü değerin türünden `value_type` kimlik türü.

*_Sym_fun*<br/>
Azaltma ikincide kullanılacak simetrik işlev. Açıklamalar için daha fazla bilgi için bkz.

*_Range_fun*<br/>
Azaltma ilk aşamasında kullanılacak işlev. Açıklamalar için daha fazla bilgi için bkz.

### <a name="return-value"></a>Dönüş Değeri

Azaltma sonucu.

### <a name="remarks"></a>Açıklamalar

Paralel azaltma gerçekleştirmek için temel alınan Zamanlayıcı için kullanılabilir olan çalışanların sayısını göre parçalara aralığı işlevi böler. Azaltma iki aşamada gerçekleşir, her bir öbeği içinde bir azaltma ilk aşamada gerçekleştirir ve her bir öbeği kısmi sonuçları arasında bir azalma ikinci aşaması gerçekleştirir.

İlk aşırı yükleme gerektiren yineleyicinin `value_type`, `T`, aynı kimlik değer türü olarak azaltma sonuç türü. Öğe türü T işleci sağlamalısınız `T T::operator + (T)` her öbek öğelerinde azaltmak için. İşleç ikinci aşamasında kullanılır.

İkinci aşırı yükleme de gerektiren yineleyicinin `value_type` azaltma sonuç türü yanı sıra kimlik değer türü olarak aynı olmalıdır. Sağlanan ikili işleç `_Sym_fun` ilk aşaması için başlangıç değeri kimlik değerine sahip iki azaltma aşamaları kullanılır.

Üçüncü aşırı yükleme için kimlik değeri türü aynı azaltma sonuç türü, ancak yineleyicinin olmalıdır `value_type` hem de farklı olabilir. Aralık azaltma işlevi `_Range_fun` kimlik değerine sahip ilk aşamada başlangıç değeri ve ikili fonksiyon kullanılan `_Sym_reduce_fun` sonuçları ikinci aşamasında sub uygulanır.

##  <a name="parallel_sort"></a>  parallel_sort

Belirtilen bir aralıktaki öğeleri azalmayan veya paralel bir ikili koşula göre belirtilen bir sıralama ölçütüne göre düzenler. Bu işlev anlam olarak benzerdir, `std::sort` karşılaştırma tabanlı kararsız, yerinde bir sıralama olması.

```
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
Olan giriş aralığındaki yineleyici türü.

*_Function*<br/>
İkili karşılaştırma functor türü.

*_Begin*<br/>
Sıralanacak aralıktaki ilk öğenin konumunu bulan bir rasgele erişim yineleyicisi.

*_Bitiş*<br/>
Sıralanacak aralığın son öğesinde geçmiş konumu ele alan bir rasgele erişim yineleyicisi.

*_Func*<br/>
Sıralama, ardışık öğeleri tarafından karşılanması için karşılaştırma ölçütü tanımlayan bir kullanıcı tanımlı işlevin doğrulama nesnesi. İkili koşulu, iki bağımsız değişkeni alır ve döndürür **true** karşılanmazsa ve **false** koşullar karşılanırsa. Bu bir karşılaştırıcı işlevi, katı bir zayıf çiftlerini dizisindeki öğelerin sıralama dayatır gerekir.

*_Chunk_size*<br/>
Paralel yürütme için iki halinde bölme bir öbek depolayabilmek boyutu.

### <a name="remarks"></a>Açıklamalar

İlk aşırı yükleme ikili karşılaştırıcı kullanan `std::less`.

İkinci aşırı kullanan imza olması gereken sağlanan ikili karşılaştırıcı `bool _Func(T, T)` burada `T` olan giriş aralığındaki öğelerin türü.

Algoritma olan giriş aralığındaki iki öbeklere böler ve sırayla her bir öbeği Paralel yürütme için iki alt öbeklere böler. İsteğe bağlı bağımsız değişkeni `_Chunk_size` algoritmaya, işleme öbek boyutunu belirtmek için kullanılan < `_Chunk_size` seri olarak.

##  <a name="parallel_transform"></a>  parallel_transform

Belirtilen işlev nesnesini bir kaynak aralıktaki her öğeye veya iki kaynak aralıktaki bir öğe çiftinin uygular ve işlev nesnenin dönüş değerlerini paralel bir hedef aralığına kopyalar. Bu işlev için anlamsal olarak eşdeğer `std::transform`.

```
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
Birinci veya yalnızca bir giriş yineleyici türü.

*_Output_iterator*<br/>
Çıkış yineleyici türü.

*_Unary_operator*<br/>
Giriş aralığındaki her öğeyi yürütülecek birli functor türü.

*_Input_iterator2*<br/>
İkinci bir giriş yineleyici türü.

*_Binary_operator*<br/>
İkili iki kaynak aralıktaki öğeleri üzerinde yürütülen ikili functor türü.

*_Partitioner*<br/>
*first1*<br/>
Birinci veya yalnızca kaynak aralığı üzerinde yapılacak ilk öğenin konumu ele alan giriş yineleyici.

*last1*<br/>
Bir önceki öğenin konumunu son öğesi ilk ya da yalnızca kaynak aralığı üzerinde yapılacak ele alan giriş yineleyici.

*_Result*<br/>
Hedef aralıktaki ilk öğenin konumunu bulan çıktı yineleyici.

*_Unary_op*<br/>
Kaynak aralıktaki her öğeye uygulanan kullanıcı tanımlı tekli işlev nesnesi.

*_Part*<br/>
Bölümleyici nesnesine bir başvuru. Bağımsız değişken şunlardan biri olabilir `const` [auto_partitioner](auto-partitioner-class.md)`&`, `const` [static_partitioner](static-partitioner-class.md)`&`, `const` [simple_ bölümleyici](simple-partitioner-class.md) `&` veya [affinity_partitioner](affinity-partitioner-class.md) `&` varsa bir [affinity_partitioner](affinity-partitioner-class.md) nesnesi kullanılır, başvurusu const olmayan bir l-değeri olmalıdır algoritma durumu yeniden kullanmak gelecekteki döngüler için depolayabileceğiniz başvuru.

*first2*<br/>
Üzerinde yapılacak ikinci kaynak aralıktaki ilk öğenin konumunu ele alan giriş yineleyici.

*_Binary_op*<br/>
İkili, için iki kaynak aralıktaki bir ileriye doğru sırada uygulanan kullanıcı tanımlı ikili fonksiyon nesnesi.

### <a name="return-value"></a>Dönüş Değeri

İşlev nesnesi tarafından dönüştürülmüş çıktı öğeleri alan hedef aralığın son öğesinde geçmiş konumu ele alan çıkış yineleyici.

### <a name="remarks"></a>Açıklamalar

[auto_partitioner](auto-partitioner-class.md) açık bölümleyici bağımsız değişken olmadan aşırı yüklemeleri için kullanılır.

Rastgele desteklemeyen yineleyiciler erişim, yalnızca [auto_partitioner](auto-partitioner-class.md) desteklenir.

Bağımsız değişken aşırı `_Unary_op` olan giriş aralığındaki her öğenin birli functor uygulayarak çıkış aralığına olan giriş aralığındaki dönüştürün. `_Unary_op` işlev çağrısı işleci imzayla desteklemelidir `operator()(T)` burada `T` üzerinden yinelenir aralığın değer türüdür.

Bağımsız değişken aşırı `_Binary_op` ilk olan giriş aralığındaki ve ikinci olan giriş aralığındaki bir öğeden bir öğe için ikili functor uygulayarak iki giriş aralık çıkış aralığına dönüştürün. `_Binary_op` işlev çağrısı işleci imzayla desteklemelidir `operator()(T, U)` burada `T`, `U` iki giriş Yineleyicilerin değer türleridir.

Daha fazla bilgi için [paralel algoritmalar](../../../parallel/concrt/parallel-algorithms.md).

##  <a name="receive"></a>  Alma

Genel Uygulama, tam olarak bir kaynaktan gelen veriler için bekleyin ve kabul edilen değerler filtrelemek bir bağlam izin vererek alırsınız.

```
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
Bir işaretçi veya başvuru, beklenen veri kaynağı.

*_Zaman aşımı*<br/>
Yöntemi için gereken en uzun süre, milisaniye cinsinden veriler için.

*_Filter_proc*<br/>
İletileri kabul edilip edilmeyeceğini belirleyen bir filtre işlevi.

### <a name="return-value"></a>Dönüş Değeri

Bir değer kaynağından, yük türü.

### <a name="remarks"></a>Açıklamalar

Parametre `_Timeout` sabiti dışında bir değere sahip `COOPERATIVE_TIMEOUT_INFINITE`, özel durum [operation_timed_out](operation-timed-out-class.md) bir ileti alındığında önce belirtilen sürede sona ererse oluşturulur. Sıfır uzunluk zaman aşımı istiyorsanız kullanmanız gerekir [try_receive](concurrency-namespace-functions.md) işlevi çağırmak yerine `receive` bir zaman aşımı ile `0` (sıfır), daha verimli olur ve zaman aşımları özel durumları oluşturmaz.

Daha fazla bilgi için [ileti geçirme işlevleri](../../../parallel/concrt/message-passing-functions.md).

##  <a name="run_with_cancellation_token"></a>  run_with_cancellation_token

Bir işlev nesnesi, belirli bir iptal belirteci bağlamında hemen ve eşzamanlı olarak yürütür.

```
template<typename _Function>
void run_with_cancellation_token(
    const _Function& _Func,
    cancellation_token _Ct);
```

### <a name="parameters"></a>Parametreler

*_Function*<br/>
Çağrılacak işlev nesnesinin türü.

*_Func*<br/>
Yürütülecek işlev nesnesi. Bu nesne, işlev çağrısı işleci void(void) imzası ile desteklemesi gerekir.

*_Ct*<br/>
İşlev nesnesi örtük iptalini denetleyen iptal belirteci. Kullanım `cancellation_token::none()` işlevi yürütme iptal ediliyor bir üst görev grubu örtük iptalden olasılığını olmadan istiyorsanız.

### <a name="remarks"></a>Açıklamalar

İşlev nesnesi herhangi bir kesinti noktası olur olduğunda tetiklenen `cancellation_token` iptal edilir. Açık belirteç `_Ct` bu yalıtmak `_Func` üst farklı bir belirteç veya hiçbir belirteç varsa üst iptal öğesinden.

##  <a name="send"></a>  Gönder

Hedef kabul eder veya iletiyi reddettiğinde kadar bekler, bir eş zamanlı gönderme işlemi.

```
template <class T>
bool send(_Inout_ ITarget<T>* _Trg, const T& _Data);

template <class T>
bool send(ITarget<T>& _Trg, const T& _Data);
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Yük türü.

*_Trg*<br/>
Bir işaretçi veya başvuru veri gönderildiği hedef.

*_Data*<br/>
Gönderilecek verileri bir başvuru.

### <a name="return-value"></a>Dönüş Değeri

**doğru** iletiyi kabul edildiyse **false** Aksi takdirde.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [ileti geçirme işlevleri](../../../parallel/concrt/message-passing-functions.md).

##  <a name="set_ambient_scheduler"></a>  set_ambient_scheduler

```
inline void set_ambient_scheduler(std::shared_ptr<::Concurrency::scheduler_interface> _Scheduler);
```

### <a name="parameters"></a>Parametreler

*_Scheduler*<br/>
Ayarlanacak ortam Zamanlayıcıyı.

##  <a name="set_task_execution_resources"></a>  set_task_execution_resources

Eşzamanlılık Çalışma zamanı iç çalışan iş parçacığı için belirtilen benzeşim tarafından kullanılan yürütme kaynakları kısıtlar.

Yalnızca Resource Manager oluşturulmadan önce arasında veya iki Resource Manager yaşam süreleri bu yöntemi çağırmak için geçerlidir. Kaynak Yöneticisi'ni çağırma sırasındaki yok sürece birden çok kez çağrılabilir. Benzeşim sınırı ayarladıktan sonra sonraki geçerli çağrı kadar devam eder `set_task_execution_resources` yöntemi.

Belirtilen benzeşim maskesi işlem benzeşim maskesi bir alt kümesi olması gerekmez. Gerekirse, process affınıty güncelleştirilecektir.

```
void __cdecl set_task_execution_resources(
    DWORD_PTR _ProcessAffinityMask);

void __cdecl set_task_execution_resources(
    unsigned short count,
    PGROUP_AFFINITY _PGroupAffinity);
```

### <a name="parameters"></a>Parametreler

*_ProcessAffinityMask*<br/>
Eşzamanlılık Çalışma zamanı çalışan iş parçacıkları sınırlı olacak benzeşim maskesi. Geçerli İşlemci grubu bir alt kümesi için eşzamanlılık çalışma zamanı sınırlamak isterseniz 64 donanım iş parçacıklarının daha büyük bir sistemde bu yöntemi kullanın. Genel olarak, 64 donanım iş parçacıklarının daha büyük makinelere benzeşim kısıtlamak için bir parametre olarak bir dizi grubu benzeşimleri kabul eden yöntemi sürümünü kullanmanız gerekir.

*Sayısı*<br/>
Sayısını `GROUP_AFFINITY` parametresi tarafından belirtilen dizideki girişler `_PGroupAffinity`.

*_PGroupAffinity*<br/>
Bir dizi `GROUP_AFFINITY` girdileri.

### <a name="remarks"></a>Açıklamalar

Yöntemi bir [invalid_operation](invalid-operation-class.md) bir Resource Manager çağrıldığında, zamanda mevcut değilse bir özel durum ve [invalid_argument](../../../standard-library/invalid-argument-class.md) benzeşim sonuç boş bir kümesi belirtilen özel durum kaynaklar.

Grup benzeşimleri bir dizi parametre olarak alan yöntemi sürümü, yalnızca kullanılan işletim sistemi sürümü Windows 7 veya üzeri olmalıdır. Aksi takdirde, bir [invalid_operation](invalid-operation-class.md) özel durumu oluşturulur.

Kaynak Yöneticisi için kısıtlı benzeşim yeniden değerlendirmek için bu yöntemi çağrıldıktan sonra process affınıty programlı şekilde değiştirme neden olmaz. Bu nedenle, tüm değişiklikleri benzeşim işlemek için bu yöntemi çağırmadan önce yapılmalıdır.

##  <a name="swap"></a>  değiştirme

İki öğeleri birbiriyle değiştirir `concurrent_vector` nesneleri.

```
template<typename T, class _Ax>
inline void swap(
    concurrent_vector<T, _Ax>& _A,
    concurrent_vector<T, _Ax>& _B);
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Eşzamanlı vektör içinde depolanan öğelerin veri türü.

*_Ax*<br/>
Eşzamanlı vektör ayırıcı türü.

*_A*<br/>
Öğeleri olan eş zamanlı vektör öğelerle için eş zamanlı vektör `_B`.

*_B*<br/>
Değiştirilecek öğeleri sağlayan eş zamanlı vektör veya öğeleri eş zamanlı vektör öğelerle ilişkili vektör `_A`.

### <a name="remarks"></a>Açıklamalar

Özel kapsayıcı sınıfı üzerinde bir algoritma şablon işlevi olan `concurrent_vector` üye işlevini yürütmek için `_A`. [concurrent_vector::swap](concurrent-vector-class.md#swap)( `_B`). İşlev şablonlarının kısmi derleyici tarafından sıralanması, örnekleri şunlardır. Şablon işlevleri şablonu işlev çağrısı ile eşleşen benzersiz değil bir şekilde aşırı yüklendiğinde, derleyici en özel şablon işlevi sürümü seçin. Şablon işlevinin genel bir sürümü `template <class T> void swap(T&, T&)`, algoritma sınıfı tarafından atama çalışır ve yavaş bir işlemdir. Her bir kapsayıcıdaki özelleştirilmiş bir sürüm olarak kapsayıcı sınıfı iç gösterimine ile çalışabilir daha hızlıdır.

Bu yöntem eşzamanlı güvenli değil. Bu yöntemi çağırdığınızda başka bir iş parçacıklarının eş zamanlı vektör birini üzerinde işlem gerçekleştirme emin olmanız gerekir.

##  <a name="task_from_exception"></a>  task_from_exception

```
template<typename _TaskType, typename _ExType>
task<_TaskType> task_from_exception(
    _ExType _Exception,
    const task_options& _TaskOptions = task_options());
```

### <a name="parameters"></a>Parametreler

*_TaskType*<br/>

*_ExType*<br/>

*_Özel*<br/>

*_TaskOptions*<br/>

### <a name="return-value"></a>Dönüş Değeri

##  <a name="task_from_result"></a>  task_from_result

```
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

##  <a name="trace_agents_register_name"></a>  Trace_agents_register_name

Ad ileti bloğu veya ETW İzleme Aracısı ile ilişkilendirir.

```
template <class T>
void Trace_agents_register_name(
    _Inout_ T* _PObject,
    _In_z_ const wchar_t* _Name);
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Nesne türü. Genellikle bir ileti bloğu ya da aracı budur.

*_PObject*<br/>
İzlemede adlı aracısı ve ileti bloğu için bir işaretçi.

*_Adı*<br/>
Verilen nesne adı.

##  <a name="try_receive"></a>  try_receive

Genel deneyin-alma uygulaması, tam olarak bir kaynaktan gelen veriler arayabilir ve kabul edilen değerler filtrelemek bir bağlam sağlar. Veriler hazır değilse, metodun döndüreceği **false**.

```
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
Bir işaretçi veya başvuru, beklenen veri kaynağı.

*_Değeri*<br/>
Sonuç yerleştirileceği bir konuma başvuru.

*_Filter_proc*<br/>
İletileri kabul edilip edilmeyeceğini belirleyen bir filtre işlevi.

### <a name="return-value"></a>Dönüş Değeri

A `bool` değeri belirten bir yük yerleştirilir olup olmadığını `_value`.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [ileti geçirme işlevleri](../../../parallel/concrt/message-passing-functions.md).

##  <a name="wait"></a>  bekleme

Belirtilen bir zaman miktarı için geçerli bağlam duraklatır.

```
void __cdecl wait(unsigned int _Milliseconds);
```

### <a name="parameters"></a>Parametreler

*_Milliseconds*<br/>
Geçerli bağlam için Duraklatılacak milisaniye sayısı. Varsa `_Milliseconds` parametresi değerine ayarlanırsa `0`, diğer çalıştırılabilir bağlamları yürütülmesine devam etmeden önce geçerli bağlam yield.

### <a name="remarks"></a>Açıklamalar

Eşzamanlılık Çalışma zamanı Zamanlayıcısı bağlam'da bu yöntemi çağrılırsa, temel alınan kaynakta çalıştırmak için farklı bir bağlama Zamanlayıcı bulabilirsiniz. Zamanlayıcı doğası gereği işbirliği yapan olduğundan, bu bağlamda tam olarak belirtilen milisaniye sayısını sonra devam edilemiyor. Zamanlayıcı Zamanlayıcı işbirliği içerisinde devamlılığı yield değil diğer görevleri çalıştırmakla meşgul ise, bekleme dönemi belirsiz olabilir.

##  <a name="when_all"></a>  when_all

Tüm bağımsız değişken olarak sağlanan görevleri başarıyla tamamladığında başarıyla tamamlanacak bir görev oluşturur.

```
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
Elde edilen görevle birleştirilecek öğe aralığındaki ilk öğenin konumu.

*_Bitiş*<br/>
Elde edilen görevle birleştirilecek öğe aralığı dışındaki ilk öğenin konumu.

*_TaskOptions*<br/>
`task_options` Nesne.

### <a name="return-value"></a>Dönüş Değeri

Tüm giriş görevleri başarıyla tamamladığında başarıyla tamamlanan bir görev. Giriş görevleri türündeyse `T`, bu işlevin çıktısı olacak bir `task<std::vector<T>>`. Giriş görevleri türündeyse `void` çıktı görevi de olacak bir `task<void>`.

### <a name="remarks"></a>Açıklamalar

`when_all` üretir engelleyici olmayan bir işlev, bir `task` sonuç olarak. Farklı [task::wait](task-class.md#wait), ASTA (ASTA uygulaması) iş parçacığında bir UWP uygulamasında bu işlevi çağırmak güvenlidir.

Görevlerden birini iptal edilir ya da bir özel durum oluşturur, döndürülen görev iptal edildi durumunda erkenden tamamlanır ve çağırırsanız, karşılaşıldıysa özel durum oluşturulur [task::get](task-class.md#get) veya `task::wait` o görevde.

Daha fazla bilgi için [görev Paralelliği](../../../parallel/concrt/task-parallelism-concurrency-runtime.md).

##  <a name="when_any"></a>  when_any

Ne zaman görevlerden herhangi birini sağlanan bağımsız değişkenler tamamladıkça başarıyla başarıyla tamamlanacak bir görev oluşturur.

```
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
Elde edilen görevle birleştirilecek öğe aralığındaki ilk öğenin konumu.

*_Bitiş*<br/>
Elde edilen görevle birleştirilecek öğe aralığı dışındaki ilk öğenin konumu.

*_TaskOptions*<br/>
*_CancellationToken*<br/>
Döndürülen görevin iptalini denetleyen iptal belirteci. Bir iptal belirteci sağlamazsanız, sonuçta elde edilen görev tamamlanmasına neden olan görevin iptal belirtecini alır.

### <a name="return-value"></a>Dönüş Değeri

Giriş görevleri herhangi biri başarıyla tamamlandığında başarıyla tamamlanan bir görev. Giriş görevleri türündeyse `T`, bu işlevin çıktısı olacak bir `task<std::pair<T, size_t>>>`, burada çiftin ilk öğesi Tamamlanan görevin sonucu ve ikinci öğe biten görevin dizinidir. Giriş görevleri türündeyse `void` çıkış bir `task<size_t>`, burada sonuç Tamamlanan görevin dizinidir.

### <a name="remarks"></a>Açıklamalar

`when_any` üretir engelleyici olmayan bir işlev, bir `task` sonuç olarak. Farklı [task::wait](task-class.md#wait), ASTA (ASTA uygulaması) iş parçacığında bir UWP uygulamasında bu işlevi çağırmak güvenlidir.

Daha fazla bilgi için [görev Paralelliği](../../../parallel/concrt/task-parallelism-concurrency-runtime.md).

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)
