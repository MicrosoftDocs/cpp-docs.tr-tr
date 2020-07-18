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
ms.openlocfilehash: 2eb5b908d66b221e9efae20ba04e2963805798ab
ms.sourcegitcommit: e15b46ea7888dbdd7e0bb47da76aeed680c3c1f3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/17/2020
ms.locfileid: "86446612"
---
# <a name="concurrency-namespace-functions"></a>eşzamanlılık ad alanı işlevleri

||||
|-|-|-|
|[Tahsis](#alloc)|[CreateResourceManager](#createresourcemanager)|[DisableTracing](#disabletracing)|
|[EnableTracing](#enabletracing)|[Ücretsiz](#free)|[GetExecutionContextId](#getexecutioncontextid)|
|[GetOSVersion](#getosversion)|[GetProcessorCount](#getprocessorcount)|[GetProcessorNodeCount](#getprocessornodecount)|
|[GetSchedulerId](#getschedulerid)|[Trace_agents_register_name](#trace_agents_register_name)|[asend](#asend)|
|[cancel_current_task](#cancel_current_task)|[lediğiniz](#clear)|[create_async](#create_async)|
|[create_task](#create_task)|[get_ambient_scheduler](#get_ambient_scheduler)|[internal_assign_iterators](#internal_assign_iterators)|
|[interruption_point](#interruption_point)|[is_current_task_group_canceling](#is_current_task_group_canceling)|[make_choice](#make_choice)|
|[make_greedy_join](#make_greedy_join)|[make_join](#make_join)|[make_task](#make_task)|
|[parallel_buffered_sort](#parallel_buffered_sort)|[parallel_for](#parallel_for)|[parallel_for_each](#parallel_for_each)|
|[parallel_invoke](#parallel_invoke)|[parallel_radixsort](#parallel_radixsort)|[parallel_reduce](#parallel_reduce)|
|[parallel_sort](#parallel_sort)|[parallel_transform](#parallel_transform)|[alamıyorum](#receive)|
|[run_with_cancellation_token](#run_with_cancellation_token)|[Gönder](#send)|[set_ambient_scheduler](#set_ambient_scheduler)|
|[set_task_execution_resources](#set_task_execution_resources)|[Kur](#swap)|[task_from_exception](#task_from_exception)|
|[task_from_result](#task_from_result)|[try_receive](#try_receive)|[bekleneceğini](#wait)|
|[when_all](#when_all)|[when_any](#when_any)|

## <a name="alloc"></a><a name="alloc"></a>Tahsis

Eşzamanlılık Çalışma Zamanı önbelleğe alma alt ayırıcılarından belirtilen boyuttaki bellek bloğunu ayırır.

```cpp
void* __cdecl Alloc(size_t _NumBytes);
```

### <a name="parameters"></a>Parametreler

*_NumBytes*<br/>
Ayrılacak bellek bayt sayısı.

### <a name="return-value"></a>Dönüş Değeri

Yeni ayrılan belleğe yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Uygulamanızdaki hangi senaryolar önbelleğe alma alt ayırıcısını kullanarak yararlanabilir hakkında daha fazla bilgi için bkz. [Görev Zamanlayıcı](../../../parallel/concrt/task-scheduler-concurrency-runtime.md).

## <a name="asend"></a><a name="asend"></a>asend

Verileri hedef bloğuna yaymaya yönelik bir görevi zamanlayan zaman uyumsuz gönderme işlemi.

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
Verilerin gönderildiği hedefe yönelik bir işaretçi veya başvuru.

*_Data*<br/>
Gönderilecek verilere bir başvuru.

### <a name="return-value"></a>Dönüş Değeri

ileti döndürülen yöntemin önüne kabul edildiyse **true** , aksi takdirde **false** .

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [Ileti geçirme işlevleri](../../../parallel/concrt/message-passing-functions.md).

## <a name="cancel_current_task"></a><a name="cancel_current_task"></a>cancel_current_task

Yürütülmekte olan görevi iptal eder. Bu işlev, görevin yürütülmesini iptal etmek için bir görevin gövdesinden çağrılabilir ve durumu girmeye neden olur `canceled` .

Bir ' ın gövdesinde değilseniz bu işlevi çağırmak için desteklenen bir senaryo değildir `task` . Bunun yapılması, uygulamanızda kilitlenme veya yanıt verme gibi tanımsız davranışlara neden olur.

```cpp
inline __declspec(noreturn) void __cdecl cancel_current_task();
```

## <a name="clear"></a><a name="clear"></a>lediğiniz

Şu anda sıraya alınmış öğelerin yok edilirken, eşzamanlı kuyruğu temizler. Bu yöntem eşzamanlılık açısından güvenli değildir.

```cpp
template<typename T, class _Ax>
void concurrent_queue<T, _Ax>::clear();
```

### <a name="parameters"></a>Parametreler

*T*<br/>

*_Ax*<br/>

## <a name="create_async"></a><a name="create_async"></a>create_async

Kullanıcı tarafından sağlanan lambda veya işlev nesnesini temel alan Windows Çalışma Zamanı zaman uyumsuz yapı oluşturur. Öğesinin dönüş türü `create_async` `IAsyncAction^` , `IAsyncActionWithProgress<TProgress>^` `IAsyncOperation<TResult>^` `IAsyncOperationWithProgress<TResult, TProgress>^` yöntemine geçirilen lambda imzasına göre,,, veya ' den biridir.

```cpp
template<typename _Function>
__declspec(noinline) auto create_async(const _Function& _Func)
    -> decltype(ref new details::_AsyncTaskGeneratorThunk<_Function>(_Func));
```

### <a name="parameters"></a>Parametreler

*_Function*<br/>
Türüyle.

*_Func*<br/>
Windows Çalışma Zamanı zaman uyumsuz yapının oluşturulacağı lambda veya işlev nesnesi.

### <a name="return-value"></a>Dönüş Değeri

IAsyncAction ^, IAsyncActionWithProgress \<TProgress> ^, IAsyncOperation \<TResult> ^ veya IAsyncOperationWithProgress ^ tarafından temsil edilen zaman uyumsuz bir yapı \<TResult, TProgress> . Döndürülen arabirim, işleve geçirilen lambdanın imzasına bağlıdır.

### <a name="remarks"></a>Açıklamalar

Lambdanın dönüş türü, yapının bir eylem mi yoksa bir işlem mi olduğunu belirler.

Void döndüren Lambdalar, eylemlerin oluşturulmasına neden olur. Türün sonucunu döndüren Lambdalar `TResult` , TResult işlemlerinin oluşturulmasına neden olur.

Lambda Ayrıca, `task<TResult>` zaman uyumsuz çalışmayı kendi içinde kapsülleyen veya zaman uyumsuz çalışmayı temsil eden bir görev zincirinin devamlılığı olan bir de döndürebilir. Bu durumda, görevler zaman uyumsuz olarak yürütülenler olduğundan ve lambda dönüş türü tarafından döndürülen zaman uyumsuz yapının oluşturulması için sarmalanmadığı için lambdanın kendisi satır içi yürütülür `create_async` . Bu, bir görevi döndüren bir Lambda \<void> , eylemlerin oluşturulmasına neden olur ve bir görevi döndüren bir lambda, \<TResult> TResult işlemlerinin oluşturulmasına neden olur.

Lambda sıfır, bir veya iki bağımsız değişken alabilir. Geçerli bağımsız değişkenler `progress_reporter<TProgress>` , ve `cancellation_token` her ikisi de kullanılırsa, bu sırayla. Bağımsız değişken içermeyen bir lambda, ilerleme raporlaması yeteneği olmadan zaman uyumsuz bir yapı oluşturulmasına neden olur. Progress_reporter alan bir lambda, \<TProgress> `create_async` progress_reporter nesnesinin yöntemi her çağrıldığında TProgress türünde ilerlemeyi raporlayan zaman uyumsuz bir yapı döndürmesine neden olur `report` . Cancellation_token alan bir lambda, iptal işlemini denetlemek için bu belirteci kullanabilir veya zaman uyumsuz yapının iptalinin bu görevlerin iptaline neden olması için onu oluşturduğu görevlere geçirebilir.

Lambda veya işlev nesnesinin gövdesi bir sonuç döndürürse (bir görev değil \<TResult> ), lamdba, çalışma zamanının örtülü olarak oluşturduğu bir görevin bağlamında, Işlem MTA içinde zaman uyumsuz olarak yürütülür. `IAsyncInfo::Cancel`Yöntemi örtük görevin iptaline neden olur.

Lambda gövdesi bir görev döndürürse, lambda satır içi yürütülür ve ' ı türünde bir bağımsız değişken almak üzere lambda bildirerek, `cancellation_token` söz konusu belirteci oluştururken bu belirteci geçirerek lambda içinde oluşturduğunuz görevlerin iptalini tetikleyebilirsiniz. Ayrıca, `register_callback` `IAsyncInfo::Cancel` zaman uyumsuz işlem veya oluşturulan eylem üzerinde çağrı yaptığınızda çalışma zamanının bir geri çağırma çağırmasını sağlamak için belirtecindeki yöntemi de kullanabilirsiniz.

Bu işlev yalnızca Windows Çalışma Zamanı uygulamalar tarafından kullanılabilir.

## <a name="createresourcemanager"></a><a name="createresourcemanager"></a>CreateResourceManager

Eşzamanlılık Çalışma Zamanı Kaynak Yöneticisi tek örneğini temsil eden bir arabirim döndürür. Kaynak Yöneticisi, kaynakların birbirleriyle birlikte çalışmak isteyen zamanlayıcılar 'ye atanmasından sorumludur.

```cpp
IResourceManager* __cdecl CreateResourceManager();
```

### <a name="return-value"></a>Dönüş Değeri

Bir `IResourceManager` arabirim.

### <a name="remarks"></a>Açıklamalar

Bu yöntem için birden çok sonraki çağrı Kaynak Yöneticisi aynı örneğini döndürür. Yöntemine yapılan her çağrı Kaynak Yöneticisi bir başvuru sayısını artırır ve Scheduler 'ı Kaynak Yöneticisi ile iletişim kurarken [IResourceManager:: Release](iresourcemanager-structure.md) yöntemine yapılan bir çağrıyla eşleşmesi gerekir.

[unsupported_os](unsupported-os-class.md) , işletim sistemi Eşzamanlılık çalışma zamanı tarafından desteklenmiyorsa oluşturulur.

## <a name="create_task"></a><a name="create_task"></a>create_task

Bir PPL [görev](task-class.md) nesnesi oluşturur. `create_task`, bir görev oluşturucusunu kullandığınız her yerde kullanılabilir. Görev oluştururken anahtar sözcüğünün kullanılmasına izin verdiğinden, genellikle kolaylık sağlaması için sağlanır `auto` .

```cpp
template<typename T>
__declspec(noinline) auto create_task(T _Param, const task_options& _TaskOptions = task_options())
    -> task<typename details::_TaskTypeFromParam<T>::T>;

template<typename _ReturnType>
__declspec( noinline) task<_ReturnType> create_task(const task<_ReturnType>& _Task);
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Görevin oluşturulması gereken parametrenin türü.

*_ReturnType*<br/>
Türüyle.

*_Param*<br/>
Görevin oluşturulması gereken parametre. UWP uygulamanızda görevler kullanıyorsanız, bu bir lambda veya işlev nesnesi, bir `task_completion_event` nesne, farklı bir `task` nesne veya bir Windows:: Foundation:: IAsyncInfo arabirimi olabilir.

*_TaskOptions*<br/>
Görev seçenekleri.

*_Task*<br/>
Oluşturulacak görev.

### <a name="return-value"></a>Dönüş Değeri

' Den çıkarılan yeni bir görev türü `T` `_Param` .

### <a name="remarks"></a>Açıklamalar

İlk aşırı yükleme tek bir parametre alan bir görev oluşturucusu gibi davranır.

İkinci aşırı yükleme, belirtilen iptal belirtecini yeni oluşturulan görevle ilişkilendirir. Bu aşırı yüklemeyi kullanırsanız, ilk parametre olarak farklı bir nesneyi geçirmeye izin verilmez `task` .

Döndürülen görevin türü, işlevin ilk parametresinden itibaren algılanır. `_Param`Bir `task_completion_event<T>` , bir veya ya `task<T>` da ya da türü döndüren bir functor ise `T` , `task<T>` oluşturulan görevin türü olur `task<T>` .

UWP uygulamasında, `_Param` Windows:: Foundation:: IAsyncOperation \<T> ^ veya Windows:: Foundation:: IAsyncOperationWithProgress \<T,P> ^ ya da bu türlerden birini döndüren bir functor türünde ise oluşturulan görev türü olur `task<T>` . `_Param`Windows:: Foundation:: IAsyncAction ^ veya Windows:: Foundation:: IAsyncActionWithProgress ^ ya da \<P> Bu türlerden birini döndüren bir functor türünde ise oluşturulan görevin türü olacaktır `task<void>` .

## <a name="disabletracing"></a><a name="disabletracing"></a>DisableTracing

Eşzamanlılık Çalışma Zamanı izlemeyi devre dışı bırakır. ETW izlemenin varsayılan olarak kaydı silindiğinden bu işlev kullanım dışıdır.

```cpp
__declspec(deprecated("Concurrency::DisableTracing is a deprecated function.")) _CRTIMP HRESULT __cdecl DisableTracing();
```

### <a name="return-value"></a>Dönüş Değeri

İzleme doğru şekilde devre dışı bırakılmışsa, `S_OK` döndürülür. İzleme daha önce başlatıldıysa, `E_NOT_STARTED` döndürülür

## <a name="enabletracing"></a><a name="enabletracing"></a>EnableTracing

Eşzamanlılık Çalışma Zamanı izlemeye izin vermez. ETW izleme artık varsayılan olarak açık olduğundan bu işlev kullanım dışıdır.

```cpp
__declspec(deprecated("Concurrency::EnableTracing is a deprecated function.")) _CRTIMP HRESULT __cdecl EnableTracing();
```

### <a name="return-value"></a>Dönüş Değeri

İzleme doğru başlatılmışsa, `S_OK` döndürülür; Aksi takdirde `E_NOT_STARTED` döndürülür.

## <a name="free"></a><a name="free"></a>Süz

Yöntemi tarafından daha önce ayrılmış bir bellek bloğunu `Alloc` Eşzamanlılık çalışma zamanı önbelleğe alma alt ayırıcısı 'na yayınlar.

```cpp
void __cdecl Free(_Pre_maybenull_ _Post_invalid_ void* _PAllocation);
```

### <a name="parameters"></a>Parametreler

*_PAllocation*<br/>
Serbest bırakılabilen yöntemi tarafından daha önce ayrılan belleğe yönelik işaretçi `Alloc` . Parametresi `_PAllocation` değerine ayarlandıysa `NULL` , bu yöntem onu yoksayar ve hemen döndürülür.

### <a name="remarks"></a>Açıklamalar

Uygulamanızdaki hangi senaryolar önbelleğe alma alt ayırıcısını kullanarak yararlanabilir hakkında daha fazla bilgi için bkz. [Görev Zamanlayıcı](../../../parallel/concrt/task-scheduler-concurrency-runtime.md).

## <a name="get_ambient_scheduler"></a><a name="get_ambient_scheduler"></a>get_ambient_scheduler

```cpp
inline std::shared_ptr<::Concurrency::scheduler_interface> get_ambient_scheduler();
```

### <a name="return-value"></a>Dönüş Değeri

## <a name="getexecutioncontextid"></a><a name="getexecutioncontextid"></a>GetExecutionContextId

Arabirimi uygulayan bir yürütme bağlamına atanabilecek benzersiz bir tanımlayıcı döndürür `IExecutionContext` .

```cpp
unsigned int __cdecl GetExecutionContextId();
```

### <a name="return-value"></a>Dönüş Değeri

Yürütme bağlamı için benzersiz bir tanımlayıcı.

### <a name="remarks"></a>Açıklamalar

Bir `IExecutionContext` arabirimi kaynak yöneticisi tarafından sunulan yöntemlerin hiçbirine bir parametre olarak geçirmeden önce yürütme içeriğiniz için bir tanımlayıcı elde etmek üzere bu yöntemi kullanın.

## <a name="getosversion"></a><a name="getosversion"></a>GetOSVersion

İşletim sistemi sürümünü döndürür.

```cpp
IResourceManager::OSVersion __cdecl GetOSVersion();
```

### <a name="return-value"></a>Dönüş Değeri

İşletim sistemini temsil eden numaralandırılmış bir değer.

### <a name="remarks"></a>Açıklamalar

[unsupported_os](unsupported-os-class.md) , işletim sistemi Eşzamanlılık çalışma zamanı tarafından desteklenmiyorsa oluşturulur.

## <a name="getprocessorcount"></a><a name="getprocessorcount"></a>GetProcessorCount

Temel sistemdeki donanım iş parçacıklarının sayısını döndürür.

```cpp
unsigned int __cdecl GetProcessorCount();
```

### <a name="return-value"></a>Dönüş Değeri

Donanım iş parçacıklarının sayısı.

### <a name="remarks"></a>Açıklamalar

[unsupported_os](unsupported-os-class.md) , işletim sistemi Eşzamanlılık çalışma zamanı tarafından desteklenmiyorsa oluşturulur.

## <a name="getprocessornodecount"></a><a name="getprocessornodecount"></a>GetProcessorNodeCount

Temel sistemdeki NUMA düğümlerinin veya işlemci paketlerinin sayısını döndürür.

```cpp
unsigned int __cdecl GetProcessorNodeCount();
```

### <a name="return-value"></a>Dönüş Değeri

NUMA düğümlerinin veya işlemci paketlerinin sayısı.

### <a name="remarks"></a>Açıklamalar

Sistem işlemci paketlerinden daha fazla NUMA düğümü içeriyorsa, NUMA düğümlerinin sayısı döndürülür, aksi takdirde işlemci paketlerinin sayısı döndürülür.

[unsupported_os](unsupported-os-class.md) , işletim sistemi Eşzamanlılık çalışma zamanı tarafından desteklenmiyorsa oluşturulur.

## <a name="getschedulerid"></a><a name="getschedulerid"></a>GetSchedulerId

Arabirimi uygulayan bir Scheduler 'a atanabilen benzersiz bir tanımlayıcı döndürür `IScheduler` .

```cpp
unsigned int __cdecl GetSchedulerId();
```

### <a name="return-value"></a>Dönüş Değeri

Zamanlayıcı için benzersiz bir tanımlayıcı.

### <a name="remarks"></a>Açıklamalar

Bir `IScheduler` arabirimi, kaynak yöneticisi tarafından sunulan yöntemlerin herhangi birine bir parametre olarak geçirmeden önce Scheduler için bir tanımlayıcı elde etmek üzere bu yöntemi kullanın.

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

*adı*<br/>

*soyadına*<br/>

## <a name="interruption_point"></a><a name="interruption_point"></a>interruption_point

İptal için bir kesinti noktası oluşturur. Bu işlevin çağrıldığı bağlamda bir iptal işlemi devam ediyorsa, bu, şu anda yürütülen paralel çalışmanın yürütülmesini iptal eden bir iç özel durum oluşturur. İptal işlemi devam ediyorsa, işlev hiçbir şey yapmaz.

```cpp
inline void interruption_point();
```

### <a name="remarks"></a>Açıklamalar

İşlev tarafından oluşturulan iç iptal özel durumunu yakalamayın `interruption_point()` . Özel durum, çalışma zamanı tarafından yakalanacaktır ve işlenir ve bu, programın anormal davranmasına neden olabilir.

## <a name="is_current_task_group_canceling"></a><a name="is_current_task_group_canceling"></a>is_current_task_group_canceling

Geçerli bağlamda şu anda yürütülmekte olan görev grubunun etkin bir iptal etme (veya kısa bir süre) üzerinde olup olmadığına ilişkin bir gösterge döndürür. Geçerli bağlamda şu anda bir görev grubu yürütülerek `false` döndürülmeyeceğini unutmayın.

```cpp
bool __cdecl is_current_task_group_canceling();
```

### <a name="return-value"></a>Dönüş Değeri

Şu anda yürütülmekte olan görev grubu iptal edildiğinde **true** , aksi takdirde **false** .

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [iptal](../../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md#cancellation).

## <a name="make_choice"></a><a name="make_choice"></a>make_choice

`choice`İsteğe bağlı `Scheduler` veya `ScheduleGroup` iki veya daha fazla giriş kaynağından bir mesajlaşma bloğu oluşturur.

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
İlk kaynağın ileti engelleme türü.

*T2*<br/>
İkinci kaynağın ileti blok türü.

*_PScheduler*<br/>
`Scheduler` `choice` Mesajlaşma bloğunun yayma görevinin zamanlandığı nesne.

*_Item1*<br/>
İlk kaynak.

*_Item2*<br/>
İkinci kaynak.

*_Items*<br/>
Ek kaynaklar.

*_PScheduleGroup*<br/>
`ScheduleGroup` `choice` Mesajlaşma bloğunun yayma görevinin zamanlandığı nesne. `Scheduler`Kullanılan nesne, zamanlama grubu tarafından kapsanıyor.

### <a name="return-value"></a>Dönüş Değeri

`choice`İki veya daha fazla giriş kaynağına sahip bir ileti bloğu.

## <a name="make_greedy_join"></a><a name="make_greedy_join"></a>make_greedy_join

`greedy multitype_join`İsteğe bağlı `Scheduler` veya `ScheduleGroup` iki veya daha fazla giriş kaynağından bir mesajlaşma bloğu oluşturur.

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
İlk kaynağın ileti engelleme türü.

*T2*<br/>
İkinci kaynağın ileti blok türü.

*_PScheduler*<br/>
`Scheduler` `multitype_join` Mesajlaşma bloğunun yayma görevinin zamanlandığı nesne.

*_Item1*<br/>
İlk kaynak.

*_Item2*<br/>
İkinci kaynak.

*_Items*<br/>
Ek kaynaklar.

*_PScheduleGroup*<br/>
`ScheduleGroup` `multitype_join` Mesajlaşma bloğunun yayma görevinin zamanlandığı nesne. `Scheduler`Kullanılan nesne, zamanlama grubu tarafından kapsanıyor.

### <a name="return-value"></a>Dönüş Değeri

`greedy multitype_join`İki veya daha fazla giriş kaynağına sahip bir ileti bloğu.

## <a name="make_join"></a><a name="make_join"></a>make_join

`non_greedy multitype_join`İsteğe bağlı `Scheduler` veya `ScheduleGroup` iki veya daha fazla giriş kaynağından bir mesajlaşma bloğu oluşturur.

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
İlk kaynağın ileti engelleme türü.

*T2*<br/>
İkinci kaynağın ileti blok türü.

*_PScheduler*<br/>
`Scheduler` `multitype_join` Mesajlaşma bloğunun yayma görevinin zamanlandığı nesne.

*_Item1*<br/>
İlk kaynak.

*_Item2*<br/>
İkinci kaynak.

*_Items*<br/>
Ek kaynaklar.

*_PScheduleGroup*<br/>
`ScheduleGroup` `multitype_join` Mesajlaşma bloğunun yayma görevinin zamanlandığı nesne. `Scheduler`Kullanılan nesne, zamanlama grubu tarafından kapsanıyor.

### <a name="return-value"></a>Dönüş Değeri

`non_greedy multitype_join`İki veya daha fazla giriş kaynağına sahip bir ileti bloğu.

## <a name="make_task"></a><a name="make_task"></a>make_task

Bir nesne oluşturmak için bir fabrika yöntemi `task_handle` .

```cpp
template <class _Function>
task_handle<_Function> make_task(const _Function& _Func);
```

### <a name="parameters"></a>Parametreler

*_Function*<br/>
Nesne tarafından temsil edilen işi yürütmek için çağrılacak işlev nesnesinin türü `task_handle` .

*_Func*<br/>
Nesne tarafından temsil edilen işi yürütmek için çağrılacak işlev `task_handle` . Bu bir lambda functor, bir işlev işaretçisi veya imza ile işlev çağrısı işlecinin bir sürümünü destekleyen herhangi bir nesne olabilir `void operator()()` .

### <a name="return-value"></a>Dönüş Değeri

Bir `task_handle` nesnesi.

### <a name="remarks"></a>Açıklamalar

Bu işlev yararlı bir lambda ifadesi içeren bir nesne oluşturmanız gerektiğinde yararlıdır `task_handle` , çünkü nesneyi lambdaya doğru türünü bilmeden oluşturmanıza izin verir.

## <a name="parallel_buffered_sort"></a><a name="parallel_buffered_sort"></a>parallel_buffered_sort

Belirli bir aralıktaki öğeleri azalan düzende veya ikili koşul tarafından belirtilen bir sıralama ölçütüne göre paralel olarak düzenler. Bu işlev, daha `std::sort` fazla alana ihtiyaç duyması dışında karşılaştırma tabanlı, kararsız ve yerinde bir sıralama olduğundan anlam açısından benzerdir `O(n)` ve sıralanan öğeler için varsayılan başlatma gerektirir.

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
Giriş aralığının Yineleyici türü.

*_Allocator*<br/>
C++ standart kitaplığı ile uyumlu bir bellek ayırıcı türü.

*_Function*<br/>
İkili karşılaştırıcısı türü.

*_Begin*<br/>
Sıralanacak aralıktaki ilk öğenin konumunu ele alarak rastgele erişimli bir yineleyici.

*_End*<br/>
Sıralanacak aralıktaki son öğeden sonraki konumu ele alarak rastgele erişimli bir yineleyici.

*_Alloc*<br/>
C++ standart kitaplığı uyumlu bellek ayırıcı örneği.

*_Func*<br/>
Sıralamada birbirini izleyen öğeler tarafından karşılanması gereken karşılaştırma ölçütünü tanımlayan Kullanıcı tanımlı koşul işlevi nesnesi. İkili koşul iki bağımsız değişken alır ve memnun olmadığında **true** ve **false** değeri döndürür. Bu karşılaştırıcı işlevi, dizideki öğe çiftlerine katı bir zayıf sıralama getirmelidir.

*_Chunk_size*<br/>
Paralel yürütme için ikiye bölünecek bir öbekin en büyük boyutu.

### <a name="remarks"></a>Açıklamalar

Tüm aşırı yüklemeler `n * sizeof(T)` ek alan gerektirir, burada `n` sıralanacak öğelerin sayısı ve `T` öğe türüdür. Çoğu durumda parallel_buffered_sort [parallel_sort](concurrency-namespace-functions.md)üzerinde performans artışı gösterecektir ve kullanılabilir belleğinizin varsa parallel_sort üzerinde kullanmanız gerekir.

Bir ikili karşılaştırıcı sağlamazsanız `std::less` , varsayılan olarak işleç sağlamak için öğe türünün gerekli olduğu bir işleç kullanılır `operator<()` .

Ayırıcı türü veya örneği belirtmezseniz, arabelleği ayırmak için C++ standart kitaplığı bellek ayırıcısı `std::allocator<T>` kullanılır.

Algoritma, giriş aralığını iki parçalara böler ve çok büyük bir şekilde, her öbeği paralel yürütme için iki alt parçalara ayırır. İsteğe bağlı bağımsız değişken, `_Chunk_size` < seri hale göre boyut öbeklerinin işleyeceği algoritmayı belirtmek için kullanılabilir `_Chunk_size` .

## <a name="parallel_for"></a><a name="parallel_for"></a>parallel_for

`parallel_for`bir dizi dizin üzerinde dolaşır ve paralel olarak her yinelemede Kullanıcı tarafından sağlanan bir işlevi yürütür.

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
Yineleme için kullanılan dizinin türü.

*_Function*<br/>
Her yinelemede yürütülecek işlevin türü.

*_Partitioner*<br/>
Sağlanan aralığı bölümlemek için kullanılan bölümleyici 'nin türü.

*adı*<br/>
Yinelemeye dahil edilecek ilk dizin.

*soyadına*<br/>
Dizinde, yinelemeye dahil edilecek son dizinden bir dizin.

*_Step*<br/>
' Den ' a yineleirken adımın değeri `first` `last` . Adım pozitif olmalıdır. Adım 1 ' den küçükse [invalid_argument](../../../standard-library/invalid-argument-class.md) atılır.

*_Func*<br/>
Her yinelemede yürütülecek işlev. Bu bir lambda ifadesi, bir işlev işaretçisi veya imza ile işlev çağrısı işlecinin bir sürümünü destekleyen herhangi bir nesne olabilir `void operator()(_Index_type)` .

*_Part*<br/>
Bölümleyici nesnesine bir başvuru. Bağımsız değişken `const` [auto_partitioner](auto-partitioner-class.md) `&` , `const` [static_partitioner](static-partitioner-class.md) `&` , `const` [simple_partitioner](simple-partitioner-class.md) `&` veya [affinity_partitioner](affinity-partitioner-class.md) bir `&` [affinity_partitioner](affinity-partitioner-class.md) nesnesi kullanılırsa, bu başvuru const olmayan bir l-değer başvurusu olmalıdır ve bu sayede algoritma, daha sonra yeniden kullanmak üzere Gelecekteki döngülerde durum depolayabilirler.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [paralel algoritmalar](../../../parallel/concrt/parallel-algorithms.md).

## <a name="parallel_for_each"></a><a name="parallel_for_each"></a>parallel_for_each

`parallel_for_each`bir aralıktaki her öğeye, paralel olarak belirtilen bir işlev uygular. `for_each` `std` Öğe üzerindeki yineleme paralel olarak gerçekleştirilmesinin ve yinelemenin sırası belirlenmemesi dışında, ad alanındaki işleve anlamsal olarak eşdeğerdir. Bağımsız değişkeni, `_Func` `operator()(T)` parametrenin `T` yinelemekte olan kapsayıcının öğe türü olduğu formun işlev çağrısı işlecini desteklemelidir.

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
Kapsayıcının üzerinde yinelemek için kullanılan yineleyicinin türü.

*_Function*<br/>
Aralık içindeki her öğeye uygulanacak işlevin türü.

*_Partitioner*<br/>
*adı*<br/>
Paralel yinelemeye dahil edilecek ilk öğenin konumunu ele alan bir yineleyici.

*soyadına*<br/>
Paralel yinelemeye dahil edilecek son öğeden önceki konumu ele alan bir yineleyici.

*_Func*<br/>
Aralıktaki her öğeye uygulanan Kullanıcı tanımlı bir işlev nesnesi.

*_Part*<br/>
Bölümleyici nesnesine bir başvuru. Bağımsız değişken `const` [auto_partitioner](auto-partitioner-class.md) `&` , `const` [static_partitioner](static-partitioner-class.md) `&` , `const` [simple_partitioner](simple-partitioner-class.md) `&` veya [affinity_partitioner](affinity-partitioner-class.md) bir `&` [affinity_partitioner](affinity-partitioner-class.md) nesnesi kullanılırsa, bu başvuru const olmayan bir l-değer başvurusu olmalıdır ve bu sayede algoritma, daha sonra yeniden kullanmak üzere Gelecekteki döngülerde durum depolayabilirler.

### <a name="remarks"></a>Açıklamalar

[auto_partitioner](auto-partitioner-class.md) , açık bir bölümleyici olmadan aşırı yükleme için kullanılacaktır.

Rastgele erişimi desteklemeyen yineleyiciler için yalnızca [auto_partitioner](auto-partitioner-class.md) desteklenir.

Daha fazla bilgi için bkz. [paralel algoritmalar](../../../parallel/concrt/parallel-algorithms.md).

## <a name="parallel_invoke"></a><a name="parallel_invoke"></a>parallel_invoke

Parametre olarak sağlanan işlev nesnelerini paralel olarak yürütür ve yürütmeyi tamamlayana kadar blokları engeller. Her işlev nesnesi bir lambda ifadesi, işlev işaretçisi veya imza ile işlev çağrısı işlecini destekleyen herhangi bir nesne olabilir `void operator()()` .

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

Parametre olarak sağlanan işlev nesnelerinin bir veya daha fazlası, çağıran bağlamda satır içi yürütebileceğini unutmayın.

Bu işleve parametre olarak geçirilen bir veya daha fazla işlev nesnesi bir özel durum oluşturursa, çalışma zamanı bu tür bir özel durum seçer ve çağrının dışına yayılır `parallel_invoke` .

Daha fazla bilgi için bkz. [paralel algoritmalar](../../../parallel/concrt/parallel-algorithms.md).

## <a name="parallel_radixsort"></a><a name="parallel_radixsort"></a>parallel_radixsort

Belirli bir aralıktaki öğeleri, bir taban x sıralama algoritmasını kullanarak azalan düzende düzenler. Bu bir yansıtma işlevi gerektiren bir kararlı sıralama işlevidir. Bu, öğeleri işaretsiz tamsayı benzeri anahtarlar halinde sıralamak için proje öğeleri olabilir. Sıralanan öğeler için varsayılan başlatma gereklidir.

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
Giriş aralığının Yineleyici türü.

*_Allocator*<br/>
C++ standart kitaplığı ile uyumlu bir bellek ayırıcı türü.

*_Function*<br/>
Projeksiyon işlevinin türü.

*_Begin*<br/>
Sıralanacak aralıktaki ilk öğenin konumunu ele alarak rastgele erişimli bir yineleyici.

*_End*<br/>
Sıralanacak aralıktaki son öğeden sonraki konumu ele alarak rastgele erişimli bir yineleyici.

*_Alloc*<br/>
C++ standart kitaplığı uyumlu bellek ayırıcı örneği.

*_Proj_func*<br/>
Bir öğeyi integral değere dönüştüren Kullanıcı tanımlı projeksiyon işlevi nesnesi.

*_Chunk_size*<br/>
Paralel yürütme için ikiye bölünecek bir öbekin en büyük boyutu.

### <a name="remarks"></a>Açıklamalar

Tüm aşırı yüklemeler `n * sizeof(T)` ek alan gerektirir, burada `n` sıralanacak öğelerin sayısı ve `T` öğe türüdür. İmza ile birli projeksiyonu, bir `I _Proj_func(T)` öğe verildiğinde bir anahtar döndürmek için gereklidir, burada `T` öğe türü ve `I` işaretsiz tamsayı benzeri bir tür.

Bir izdüşüm işlevi belirtmezseniz, yalnızca öğeyi döndüren bir varsayılan projeksiyon işlevi integral türler için kullanılır. Öğe, projeksiyon işlevi yokluğunda bir integral türü değilse, işlev derlenmeyecektir.

Ayırıcı türü veya örneği belirtmezseniz, arabelleği ayırmak için C++ standart kitaplığı bellek ayırıcısı `std::allocator<T>` kullanılır.

Algoritma, giriş aralığını iki parçalara böler ve çok büyük bir şekilde, her öbeği paralel yürütme için iki alt parçalara ayırır. İsteğe bağlı bağımsız değişken, `_Chunk_size` < seri hale göre boyut öbeklerinin işleyeceği algoritmayı belirtmek için kullanılabilir `_Chunk_size` .

## <a name="parallel_reduce"></a><a name="parallel_reduce"></a>parallel_reduce

Ardışık kısmi toplamları hesaplayarak, belirtilen aralıktaki tüm öğelerin toplamını hesaplar veya paralel olan belirli bir ikili işlemi kullanmaktan farklı şekilde elde edilen kısmi sonuçların sonucunu hesaplar. `parallel_reduce``std::accumulate`, ikili işlemin ilişkilendirilebilir olmasını gerektirdiğinden ve ilk değer yerine bir kimlik değeri gerektirdiğinden anlam olarak benzerdir.

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
Giriş aralığının Yineleyici türü.

*_Sym_reduce_fun*<br/>
Simetrik azaltma işlevinin türü. Bu, `_Reduce_type _Sym_fun(_Reduce_type, _Reduce_type)` _Reduce_type kimlik türüyle aynı ve azaltmanın sonuç türü ile aynı olan imzaya sahip bir işlev türü olmalıdır. Üçüncü aşırı yükleme için, bu çıkış türü ile tutarlı olmalıdır `_Range_reduce_fun` .

*_Reduce_type*<br/>
Girişin azaltılacağı tür, giriş öğesi türünden farklı olabilir. Dönüş değeri ve kimlik değeri bu türe sahip olacaktır.

*_Range_reduce_fun*<br/>
Aralık azaltma işlevinin türü. Bu, imza içeren bir işlev türü olmalıdır `_Reduce_type _Range_fun(_Forward_iterator, _Forward_iterator, _Reduce_type)` , _Reduce_type kimlik türüyle aynı ve azaltmanın sonuç türü ile aynı.

*_Begin*<br/>
Azaltmak için aralıktaki ilk öğeyi ele almak için bir giriş Yineleyici.

*_End*<br/>
İçindeki son öğenin ötesinde bir konum olan öğeyi ele alan bir giriş Yineleyici.

*_Identity*<br/>
Kimlik değeri, `_Identity` azaltmanın sonuç türü ile aynı türde ve ayrıca `value_type` Birinci ve ikinci aşırı yüklemeler için yineleyicinin. Üçüncü aşırı yüklemede kimlik değeri, azaltmanın sonuç türüyle aynı türde olmalıdır, ancak yineleyicinin içinden farklı olabilir `value_type` . Aralık azaltma işlecinin `_Range_fun` , türünde tek bir öğe türüne uygulandığında `value_type` ve kimlik değeri türünden kimlik türüne değer dönüştürme gibi davranması gibi uygun bir değere sahip olması gerekir `value_type` .

*_Sym_fun*<br/>
Azaltmanın ikinci kısmında kullanılacak simetrik işlev. Daha fazla bilgi için açıklamalar bölümüne bakın.

*_Range_fun*<br/>
Azaltmanın ilk aşamasında kullanılacak işlev. Daha fazla bilgi için açıklamalar bölümüne bakın.

### <a name="return-value"></a>Dönüş Değeri

Azaltmanın sonucu.

### <a name="remarks"></a>Açıklamalar

Paralel bir azaltma gerçekleştirmek için işlev, temeldeki Scheduler tarafından kullanılabilen çalışan sayısına göre aralığı parçalara ayırır. Azalma iki aşamada gerçekleşir, ilk aşama her bir öbek içinde bir azaltma gerçekleştirir ve ikinci aşama her öbekten oluşan kısmi sonuçlar arasında bir azaltma gerçekleştirir.

İlk aşırı yükleme, yineleyicinin, `value_type` `T` kimlik değer türü ile aynı ve azaltma sonuç türü ile aynı olmasını gerektirir. Öğe türü T, `T T::operator + (T)` her öbekteki öğeleri azaltmak için işlecini sağlamalıdır. Aynı işleç ikinci aşamada de kullanılır.

İkinci aşırı yükleme, yineleyicinin `value_type` kimlik değer türü ile aynı ve azaltma sonuç türü ile aynı olmasını gerektirir. Sağlanan ikili işleç, `_Sym_fun` birinci aşamanın ilk değeri olarak kimlik değeri ile her iki azaltma aşamasında kullanılır.

Üçüncü aşırı yüklemede, kimlik değer türü, azaltma sonucu türüyle aynı olmalıdır, ancak Yineleyici `value_type` her ikisiyle farklı olabilir. Aralık azaltma işlevi `_Range_fun` ilk aşamada kimlik değeri ilk değer olarak kullanılır ve ikili işlev `_Sym_reduce_fun` İkinci aşamadaki alt sonuçlara uygulanır.

## <a name="parallel_sort"></a><a name="parallel_sort"></a>parallel_sort

Belirli bir aralıktaki öğeleri azalan düzende veya ikili koşul tarafından belirtilen bir sıralama ölçütüne göre paralel olarak düzenler. Bu işlev, `std::sort` karşılaştırma tabanlı, kararsız ve yerinde bir sıralama olmak üzere anlamsal olarak benzerdir.

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
Giriş aralığının Yineleyici türü.

*_Function*<br/>
İkili karşılaştırma functor türü.

*_Begin*<br/>
Sıralanacak aralıktaki ilk öğenin konumunu ele alarak rastgele erişimli bir yineleyici.

*_End*<br/>
Sıralanacak aralıktaki son öğeden sonraki konumu ele alarak rastgele erişimli bir yineleyici.

*_Func*<br/>
Sıralamada birbirini izleyen öğeler tarafından karşılanması gereken karşılaştırma ölçütünü tanımlayan Kullanıcı tanımlı koşul işlevi nesnesi. İkili koşul iki bağımsız değişken alır ve memnun olmadığında **true** ve **false** değeri döndürür. Bu karşılaştırıcı işlevi, dizideki öğe çiftlerine katı bir zayıf sıralama getirmelidir.

*_Chunk_size*<br/>
Paralel yürütme için ikiye bölünecek en küçük bir öbek boyutu.

### <a name="remarks"></a>Açıklamalar

İlk aşırı yükleme ikili karşılaştırıcısı kullanır `std::less` .

İkinci aşırı yüklenmiş, `bool _Func(T, T)` `T` giriş aralığındaki öğelerin türü olan imzaya sahip olması gereken, sağlanan ikili karşılaştırıcısı ' nı kullanır.

Algoritma, giriş aralığını iki parçalara böler ve çok büyük bir şekilde, her öbeği paralel yürütme için iki alt parçalara ayırır. İsteğe bağlı bağımsız değişken, `_Chunk_size` < seri hale göre boyut öbeklerinin işleyeceği algoritmayı belirtmek için kullanılabilir `_Chunk_size` .

## <a name="parallel_transform"></a><a name="parallel_transform"></a>parallel_transform

Kaynak aralıktaki her öğeye veya iki kaynak aralığından bir öğe çiftine belirtilen bir işlev nesnesi uygular ve işlev nesnesinin dönüş değerlerini paralel olarak bir hedef aralığa kopyalar. Bu işlev, anlam ile eşdeğerdir `std::transform` .

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
Birinci veya tek giriş yineleyicisinin türü.

*_Output_iterator*<br/>
Çıkış yineleyicisinin türü.

*_Unary_operator*<br/>
Giriş aralığındaki her öğe üzerinde yürütülecek birli funın türü.

*_Input_iterator2*<br/>
İkinci giriş yineleyicisinin türü.

*_Binary_operator*<br/>
İki kaynak aralığından öğeler üzerinde ikili bir şekilde yürütülen ikili functor türü.

*_Partitioner*<br/>
*first1*<br/>
Üzerinde çalıştırılacak ilk veya tek kaynak aralıktaki ilk öğenin konumunu ele alan bir giriş Yineleyici.

*last1*<br/>
Üzerinde çalıştırılacak ilk veya tek kaynak aralıktaki son öğeden önceki konumu ele alan bir giriş Yineleyici.

*_Result*<br/>
Hedef aralıktaki ilk öğenin konumunu ele alarak çıkış Yineleyici.

*_Unary_op*<br/>
Kaynak aralıktaki her öğeye uygulanan Kullanıcı tanımlı birli işlev nesnesi.

*_Part*<br/>
Bölümleyici nesnesine bir başvuru. Bağımsız değişken `const` [auto_partitioner](auto-partitioner-class.md) `&` , `const` [static_partitioner](static-partitioner-class.md) `&` , `const` [simple_partitioner](simple-partitioner-class.md) `&` veya [affinity_partitioner](affinity-partitioner-class.md) bir `&` [affinity_partitioner](affinity-partitioner-class.md) nesnesi kullanılırsa, bu başvuru const olmayan bir l-değer başvurusu olmalıdır ve bu sayede algoritma, daha sonra yeniden kullanmak üzere Gelecekteki döngülerde durum depolayabilirler.

*first2*<br/>
Üzerinde çalıştırılacak ikinci kaynak aralıktaki ilk öğenin konumunu ele alan bir giriş Yineleyici.

*_Binary_op*<br/>
İki kaynak aralığına, bir iletme sırasında ikili olarak uygulanan, Kullanıcı tanımlı bir ikili işlev nesnesi.

### <a name="return-value"></a>Dönüş Değeri

İşlev nesnesi tarafından dönüştürülen çıkış öğelerini alan hedef aralıktaki son öğeden önceki konumu ele alan bir çıkış Yineleyici.

### <a name="remarks"></a>Açıklamalar

[auto_partitioner](auto-partitioner-class.md) , açık bir bölümleyici bağımsız değişkeni olmayan aşırı yüklemeler için kullanılacaktır.

Rastgele erişimi desteklemeyen yineleyiciler için yalnızca [auto_partitioner](auto-partitioner-class.md) desteklenir.

Bağımsız değişkenini alan aşırı yüklemeler, giriş aralığındaki `_Unary_op` her bir öğeye birli functor uygulayarak giriş aralığını çıkış aralığına dönüştürür. `_Unary_op`, `operator()(T)` `T` yinelemekte olan aralığın değer türü olan imzaya sahip işlev çağrısı işlecini desteklemelidir.

Bağımsız değişkenini alan aşırı yüklemeler, `_Binary_op` birinci giriş aralığından bir öğeye ve ikinci giriş aralığından bir öğeden bir öğe olan ikili functor 'u uygulayarak çıkış aralığına iki giriş aralığı dönüştürür. `_Binary_op`imza ile işlev çağrısı işlecini desteklemesi gerekir `operator()(T, U)` , bu `T` `U` iki giriş yineleyicilerinin değer türleridir.

Daha fazla bilgi için bkz. [paralel algoritmalar](../../../parallel/concrt/parallel-algorithms.md).

## <a name="receive"></a><a name="receive"></a>alamıyorum

Bir bağlamın tam olarak bir kaynaktan veri beklemesi ve kabul edilen değerleri filtrelemesine olanak tanımak için genel bir alma uygulamasıdır.

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
Verilerin beklenildiği kaynağa yönelik bir işaretçi veya başvuru.

*_Timeout*<br/>
Yöntemin veriler için gereken en uzun süre (milisaniye cinsinden).

*_Filter_proc*<br/>
İletilerin kabul edilip edilmeyeceğini belirleyen bir filtre işlevi.

### <a name="return-value"></a>Dönüş Değeri

Yük türünün kaynağından alınan bir değer.

### <a name="remarks"></a>Açıklamalar

Parametrenin `_Timeout` sabiti dışında bir değeri varsa `COOPERATIVE_TIMEOUT_INFINITE` , bir ileti alınmadan önce belirtilen süre dolarsa, özel durum [operation_timed_out](operation-timed-out-class.md) oluşturulur. Sıfır uzunlukta bir zaman aşımı istiyorsanız, [try_receive](concurrency-namespace-functions.md) `receive` `0` daha verimli olduğu ve zaman aşımları üzerinde özel durumlar oluşturmadığından, bir zaman aşımı (sıfır) ile çağırmak yerine try_receive işlevini kullanmanız gerekir.

Daha fazla bilgi için bkz. [Ileti geçirme işlevleri](../../../parallel/concrt/message-passing-functions.md).

## <a name="run_with_cancellation_token"></a><a name="run_with_cancellation_token"></a>run_with_cancellation_token

Bir işlev nesnesini, belirli bir iptal belirtecinin bağlamında hemen ve zaman uyumlu olarak yürütür.

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
Yürütülecek işlev nesnesi. Bu nesne, void (void) imzasına sahip işlev çağrısı işlecini desteklemelidir.

*_Ct*<br/>
İşlev nesnesinin örtük iptalini denetleyen iptal belirteci. `cancellation_token::none()`Bir üst görev grubundan bir örtük iptal etme olanağı olmadan işlevin yürütmesini istiyorsanız kullanın.

### <a name="remarks"></a>Açıklamalar

İşlev nesnesindeki kesinti noktaları, iptal edildiğinde tetiklenecektir `cancellation_token` . Açık belirteç, `_Ct` `_Func` üst öğenin farklı bir belirteci varsa veya belirteci yoksa, bu üst iptalden yalıtılacaktır.

## <a name="send"></a><a name="send"></a>Gönder

Hedefin iletiyi kabul etmesini veya reddetmesini bekleyen zaman uyumlu gönderme işlemi.

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
Verilerin gönderildiği hedefe yönelik bir işaretçi veya başvuru.

*_Data*<br/>
Gönderilecek verilere bir başvuru.

### <a name="return-value"></a>Dönüş Değeri

ileti kabul edildiyse **true** , aksi takdirde **false** .

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [Ileti geçirme işlevleri](../../../parallel/concrt/message-passing-functions.md).

## <a name="set_ambient_scheduler"></a><a name="set_ambient_scheduler"></a>set_ambient_scheduler

```cpp
inline void set_ambient_scheduler(std::shared_ptr<::Concurrency::scheduler_interface> _Scheduler);
```

### <a name="parameters"></a>Parametreler

*_Scheduler*<br/>
Ayarlanacak çevresel Zamanlayıcı.

## <a name="set_task_execution_resources"></a><a name="set_task_execution_resources"></a>set_task_execution_resources

Eşzamanlılık Çalışma Zamanı iç çalışan iş parçacıkları tarafından kullanılan yürütme kaynaklarını belirtilen benzeşim kümesine kısıtlar.

Bu yöntemi yalnızca Kaynak Yöneticisi oluşturulmadan veya iki Kaynak Yöneticisi yaşam süresi arasında çağırmak için geçerlidir. Kaynak Yöneticisi, çağırma sırasında mevcut olmadığı sürece birden çok kez çağrılabilir. Benzeşim sınırı ayarlandıktan sonra, yönteme bir sonraki geçerli çağrıya kadar yürürlükte kalır `set_task_execution_resources` .

Belirtilen benzeşim maskesi, işlem benzeşimi maskesinin bir alt kümesi olmamalıdır. İşlem benzeşimi gerekirse güncelleştirilir.

```cpp
void __cdecl set_task_execution_resources(
    DWORD_PTR _ProcessAffinityMask);

void __cdecl set_task_execution_resources(
    unsigned short count,
    PGROUP_AFFINITY _PGroupAffinity);
```

### <a name="parameters"></a>Parametreler

*_ProcessAffinityMask*<br/>
Eşzamanlılık Çalışma Zamanı çalışan iş parçacıklarının kısıtlanması gereken benzeşim maskesi. Bu yöntemi, 64 ' den fazla donanım iş parçacığından yalnızca Eşzamanlılık Çalışma Zamanı, geçerli işlemci grubunun bir alt kümesiyle sınırlamak istiyorsanız kullanın. Genel olarak, 64 ' den fazla donanım iş parçacığından oluşan makinelerde benzeşimi kısıtlamak için bir parametre olarak bir grup benzeşiminin dizisini kabul eden yönteminin sürümünü kullanmanız gerekir.

*biriktirme*<br/>
`GROUP_AFFINITY`Parametre tarafından belirtilen dizideki girdi sayısı `_PGroupAffinity` .

*_PGroupAffinity*<br/>
Girdilerden oluşan dizi `GROUP_AFFINITY` .

### <a name="remarks"></a>Açıklamalar

Bir Kaynak Yöneticisi çağrıldığında Yöntem bir [invalid_operation](invalid-operation-class.md) özel durum oluşturur ve belirtilen benzeşim boş bir kaynak kümesiyle sonuçlanırsa bir [invalid_argument](../../../standard-library/invalid-argument-class.md) özel durumu oluşturulur.

Bir parametre olarak grup benzeşimleri dizisi alan yöntemin sürümü, yalnızca Windows 7 veya üzeri sürümü olan işletim sistemlerinde kullanılmalıdır. Aksi takdirde, [invalid_operation](invalid-operation-class.md) bir özel durum oluşturulur.

Bu yöntem çağrıldıktan sonra işlem benzeşimini programlı bir şekilde değiştirmek Kaynak Yöneticisi, sınırlandırıldığı benzeşimi yeniden değerlendirmeye neden olmaz. Bu nedenle, bu yöntem çağrılmadan önce işlem benzeşimine yapılan tüm değişiklikler yapılmalıdır.

## <a name="swap"></a><a name="swap"></a>Kur

İki nesnenin öğelerini değiş tokuş eder `concurrent_vector` .

```cpp
template<typename T, class _Ax>
inline void swap(
    concurrent_vector<T, _Ax>& _A,
    concurrent_vector<T, _Ax>& _B);
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Eşzamanlı vektörde depolanan öğelerin veri türü.

*_Ax*<br/>
Eşzamanlı vektörün ayırıcı türü.

*_A*<br/>
Öğeleri eşzamanlı vektörle birlikte değiş tokuş edilecek eşzamanlı vektör `_B` .

*_B*<br/>
Değiştirilecek öğeleri sağlayan eşzamanlı vektör veya öğeleri eşzamanlı vektörle değiş tokuş edilecek vektör `_A` .

### <a name="remarks"></a>Açıklamalar

Şablon işlevi, `concurrent_vector` üye işlevini yürütmek için kapsayıcı sınıfı üzerinde özelleştirilmiş bir algoritmadır `_A` . [concurrent_vector:: Swap](concurrent-vector-class.md#swap)( `_B` ). Bunlar, derleyici tarafından işlev şablonlarının Kısmi sıralama örnekleridir. Şablon işlevleri, işlev çağrısı ile şablonla eşleşen bir şekilde aşırı yüklendiğinde, derleyici şablon işlevinin en özelleştirilmiş sürümünü seçer. Algoritma sınıfındaki şablon işlevinin genel sürümü `template <class T> void swap(T&, T&)` atama ile çalışır ve yavaş bir işlemdir. Kapsayıcı sınıfının iç temsili ile çalışabildiğinden, her kapsayıcıda özelleştirilmiş sürüm çok daha hızlıdır.

Bu yöntem eşzamanlılık açısından güvenli değildir. Bu yöntemi çağırdığınızda eşzamanlı vektörden başka iş parçacıklarının işlem gerçekleştirmemesini sağlamalısınız.

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

Verilen adı ETW izlemesinde bulunan ileti bloğuna veya aracıya ilişkilendirir.

```cpp
template <class T>
void Trace_agents_register_name(
    _Inout_ T* _PObject,
    _In_z_ const wchar_t* _Name);
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Nesnenin türü. Bu genellikle bir ileti bloğu veya bir aracıdır.

*_PObject*<br/>
İzleme içinde adlandırılmakta olan ileti bloğu veya aracısına yönelik bir işaretçi.

*_Name*<br/>
Verilen nesnenin adı.

## <a name="try_receive"></a><a name="try_receive"></a>try_receive

Bir bağlamın tam olarak bir kaynaktan verileri arayacağı ve kabul edilen değerleri filtrelemesine izin veren genel bir TRY-Receive uygulamasıdır. Veriler hazırsanız, yöntem **false**döndürür.

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
Verilerin beklenildiği kaynağa yönelik bir işaretçi veya başvuru.

*_value*<br/>
Sonucun yerleştirileceği konuma bir başvuru.

*_Filter_proc*<br/>
İletilerin kabul edilip edilmeyeceğini belirleyen bir filtre işlevi.

### <a name="return-value"></a>Dönüş Değeri

`bool`Bir yükün yerleştirilmiş olup olmadığını gösteren bir değer `_value` .

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [Ileti geçirme işlevleri](../../../parallel/concrt/message-passing-functions.md).

## <a name="wait"></a><a name="wait"></a>bekleneceğini

Belirtilen süre boyunca geçerli bağlamı duraklatır.

```cpp
void __cdecl wait(unsigned int _Milliseconds);
```

### <a name="parameters"></a>Parametreler

*_Milliseconds*<br/>
Geçerli bağlamın için duraklatıldığı milisaniye sayısı. `_Milliseconds`Parametresi değerine ayarlandıysa `0` , devam etmeden önce geçerli bağlam yürütmeyi diğer çalıştırılabilir bağlamlara getirmelidir.

### <a name="remarks"></a>Açıklamalar

Bu yöntem Eşzamanlılık Çalışma Zamanı Zamanlayıcı bağlamında çağrılırsa Zamanlayıcı, temel alınan kaynakta çalıştırmak için farklı bir bağlam bulur. Zamanlayıcı doğası içinde anlaşmakta olduğundan, bu bağlam belirtilen milisaniye sayısından tam olarak sürdürülemez. Zamanlayıcı, Scheduler 'a uygun olmayan başka görevler yürütülerek, bekleme süresi sınırsız olabilir.

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
Ortaya çıkan görevde birleştirilecek öğe aralığındaki ilk öğenin konumu.

*_End*<br/>
Ortaya çıkan görevde birleştirilecek öğe aralığının ötesinde ilk öğenin konumu.

*_TaskOptions*<br/>
`task_options` nesnesi.

### <a name="return-value"></a>Dönüş Değeri

Tüm giriş görevleri başarıyla tamamlandığında başarıyla tamamlanan bir görev. Giriş görevleri tür ise `T` , bu işlevin çıktısı bir olur `task<std::vector<T>>` . Giriş görevleri tür ise, `void` çıkış görevi de olur `task<void>` .

### <a name="remarks"></a>Açıklamalar

`when_all`, sonucu olarak bir oluşturan engelleyici olmayan bir işlevdir `task` . [Task:: wait](task-class.md#wait)komutundan farklı olarak, bu IşLEVI ASTA (Application STA) Iş parçacığında UWP uygulamasında çağırmak güvenlidir.

Görevlerden biri iptal edildiğinde veya bir özel durum oluşturursa, döndürülen görev erken tamamlanır, iptal edildi durumunda ve bir durum oluşursa, [görev:: Get](task-class.md#get) veya bu görevde bir istisna olursa özel durum oluşturulur `task::wait` .

Daha fazla bilgi için bkz. [Görev Paralelliği](../../../parallel/concrt/task-parallelism-concurrency-runtime.md).

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
Ortaya çıkan görevde birleştirilecek öğe aralığındaki ilk öğenin konumu.

*_End*<br/>
Ortaya çıkan görevde birleştirilecek öğe aralığının ötesinde ilk öğenin konumu.

*_TaskOptions*<br/>
*_CancellationToken*<br/>
Döndürülen görevin iptalini denetleyen iptal belirteci. İptal belirteci sağlamazsanız, sonuçta elde edilen görev, görevin tamamlanmasını neden olan iptal belirtecini alır.

### <a name="return-value"></a>Dönüş Değeri

Giriş görevlerinden herhangi biri başarıyla tamamlandığında başarıyla tamamlanan bir görev. Giriş görevleri tür ise `T` , bu işlevin çıktısı bir olur `task<std::pair<T, size_t>>>` . burada, çiftin ilk öğesi tamamlanma görevinin sonucu olur ve ikinci öğe, tamamlanmış görevin dizinidir. Giriş görevleri, `void` Çıkış bir ise `task<size_t>` , sonuç tamamlanma görevinin dizinidir.

### <a name="remarks"></a>Açıklamalar

`when_any`, sonucu olarak bir oluşturan engelleyici olmayan bir işlevdir `task` . [Task:: wait](task-class.md#wait)komutundan farklı olarak, bu IşLEVI ASTA (Application STA) Iş parçacığında UWP uygulamasında çağırmak güvenlidir.

Daha fazla bilgi için bkz. [Görev Paralelliği](../../../parallel/concrt/task-parallelism-concurrency-runtime.md).

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık ad alanı](concurrency-namespace.md)
