---
title: "Eşzamanlılık ad alanı işlevleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
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
dev_langs:
- C++
ms.assetid: 520a6dff-9324-4df2-990d-302e3050af6a
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 66cf776e02d286b04c4fe9338d74d6a9db196a68
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="concurrency-namespace-functions"></a>Eşzamanlılık ad alanı işlevleri
||||  
|-|-|-|  
|[Alloc](#alloc)|[CreateResourceManager](#createresourcemanager)|[DisableTracing](#disabletracing)|  
|[EnableTracing](#enabletracing)|[Boş](#free)|[GetExecutionContextId](#getexecutioncontextid)|  
|[GetOSVersion](#getosversion)|[GetProcessorCount](#getprocessorcount)|[GetProcessorNodeCount](#getprocessornodecount)|  
|[GetSchedulerId](#getschedulerid)|[Trace_agents_register_name](#trace_agents_register_name)|[asend](#asend)|  
|[cancel_current_task](#cancel_current_task)|[Temizle](#clear)|[create_async](#create_async)|  
|[create_task](#create_task)|[get_ambient_scheduler](#get_ambient_scheduler)|[internal_assign_iterators](#internal_assign_iterators)|  
|[interruption_point](#interruption_point)|[is_current_task_group_canceling](#is_current_task_group_canceling)|[make_choice](#make_choice)|  
|[make_greedy_join](#make_greedy_join)|[make_join](#make_join)|[make_task](#make_task)|  
|[parallel_buffered_sort](#parallel_buffered_sort)|[parallel_for](#parallel_for)|[parallel_for_each](#parallel_for_each)|  
|[parallel_invoke](#parallel_invoke)|[parallel_radixsort](#parallel_radixsort)|[parallel_reduce](#parallel_reduce)|  
|[parallel_sort](#parallel_sort)|[parallel_transform](#parallel_transform)|[receive](#receive)|  
|[run_with_cancellation_token](#run_with_cancellation_token)|[Gönder](#send)|[set_ambient_scheduler](#set_ambient_scheduler)|  
|[set_task_execution_resources](#set_task_execution_resources)|[Değiştirme](#swap)|[task_from_exception](#task_from_exception)|  
|[task_from_result](#task_from_result)|[try_receive](#try_receive)|[bekleme](#wait)|  
|[when_all](#when_all)|[when_any](#when_any)|  
  
##  <a name="alloc"></a>  Ayırma  
 Bir eşzamanlılık çalışma zamanı önbelleğe alma Suballocator ' belirtilen boyut, bellek bloğu ayırır.  
  
```
void* __cdecl Alloc(size_t _NumBytes);
```  
  
### <a name="parameters"></a>Parametreler  
 `_NumBytes`  
 Ayrılacak bellek bayt sayısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yeni ayrılan bellek için bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 , Uygulamanızda senaryoları hakkında yararlı önbelleğe alma Suballocator kullanarak daha fazla bilgi için bkz: [Görev Zamanlayıcı](../../../parallel/concrt/task-scheduler-concurrency-runtime.md).  
  
##  <a name="asend"></a>  asend  
 Zaman uyumsuz bir hedef blok verileri yaymak için bir görev zamanlar işlemi gönderin.  
  
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
 `T`  
 Gönderilecek veri türü.  
  
 `_Trg`  
 Bir işaretçi veya veri gönderildiği hedefine başvuru.  
  
 `_Data`  
 Gönderilecek verileri referansı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true` yöntem döndürmeden önce iletiyi kabul edildiyse `false` Aksi takdirde.  
  
### <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için bkz: [ileti geçirme işlevleri](../../../parallel/concrt/message-passing-functions.md).  
  
##  <a name="cancel_current_task"></a>  cancel_current_task  
 Şu anda yürütülen görev iptal eder. Bu işlev Görev Yürütme iptal etmek ve girmek neden görevi gövdesi içinde çağrılabilir `canceled` durumu.  
  
 Gövdesi içinde değilse bu işlevi çağırmak için desteklenen bir senaryo değildir bir `task`. Bunun yapılması bir kilitlenme veya yanıt vermemesine uygulamanızda gibi tanımsız davranış neden olur.  
  
```
inline __declspec(noreturn) void __cdecl cancel_current_task();
```  
  
##  <a name="clear"></a>  Temizle  
 Herhangi bir yok etme sıranın eşzamanlı temizler şu anda sıradaki öğeleri. Bu yöntem eşzamanlılık uyumlu değil.  
  
```
template<typename T, class _Ax>
void concurrent_queue<T, _Ax>::clear();
```   
  
### <a name="parameters"></a>Parametreler  
 `T`  
 `_Ax`  
  
##  <a name="create_async"></a>  create_async  
 Bir kullanıcı tarafından sağlanan lambda veya işlev nesnesine bağlı bir Windows çalışma zamanı zaman uyumsuz yapısı oluşturur. Dönüş türü `create_async` aşağıdakilerden biri `IAsyncAction^`, `IAsyncActionWithProgress<TProgress>^`, `IAsyncOperation<TResult>^`, veya `IAsyncOperationWithProgress<TResult, TProgress>^` yönteme geçirilen lambda imza göre.  
  
```
template<typename _Function>
__declspec(noinline) auto create_async(const _Function& _Func)
    -> decltype(ref new details::_AsyncTaskGeneratorThunk<_Function>(_Func));
```  
  
### <a name="parameters"></a>Parametreler  
 `_Function`  
 `_Func`  
 Windows çalışma zamanı zaman uyumsuz yapı oluşturulacağı lambda veya işlev nesnesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir IAsyncAction tarafından temsil edilen bir zaman uyumsuz yapısıyla ^, IAsyncActionWithProgress\<TProgress > ^, IAsyncOperation\<TResult > ^, veya bir IAsyncOperationWithProgress\<TResult, TProgress > ^. Döndürülen arabirimi işlevdeki geçirilen lambda imza bağlıdır.  
  
### <a name="remarks"></a>Açıklamalar  
 Lambda dönüş türü yapısı bir eylemi veya işlemi olup olmadığını belirler.  
  
 Boş döndürmeleri lambdas Eylemler oluşturulmasına neden. Bir sonuç türü Lambda'lar `TResult` TResult işlemlerini oluşturulmasına neden.  
  
 Lambda aynı zamanda döndürebilir bir `task<TResult>` kendi içinde uyumsuz iş yalıtır veya zaman uyumsuz iş temsil eden görevi zinciri devamıdır. Bu durumda, zaman uyumsuz yürütme olanlar görevleridir yürütülen satır içi lambda olduğu ve lambda dönüş türü tarafından döndürülen zaman uyumsuz yapı üretmek için sarılmamış `create_async`. Bu bir lambda, bir görev döndürür gelir\<void > eylemleri ve bir görev döndürür bir lambda oluşturulmasına neden olacak\<TResult > TResult işlemlerini oluşturulmasına neden olur.  
  
 Lambda ya da sıfır, bir veya iki bağımsız değişken sürebilir. Geçerli bağımsız değişkenler `progress_reporter<TProgress>` ve `cancellation_token`sipariş her iki kullanılır bu. Bağımsız değişkenler olmadan bir lambda ilerleme durumu raporlama özelliği olmadan zaman uyumsuz bir yapı oluşturulmasına neden olur. Bir progress_reporter geçen lambda\<TProgress > neden olacak `create_async` türü TProgress ilerlemesi her zaman raporları bir zaman uyumsuz yapısıyla döndürülecek `report` progress_reporter nesnesinin yöntemi çağrılır. Bir cancellation_token geçen lambda iptalleri denetlemek için bu belirteci kullanın veya oluşturur ve böylece bu görevleri iptali zaman uyumsuz yapı iptaline neden görevlere geçirin.  
  
 Lambda veya işlev nesnesi gövdesi bir sonuç döndürürse (ve bir görev\<TResult >), lamdba zaman uyumsuz olarak bir görevin çalışma bağlamında MTA örtük olarak oluşturur için işlemi içinde yürütülür. `IAsyncInfo::Cancel` Yöntemi örtük görev iptali neden olur.  
  
 Gövdesi bir görevin, lamba lambda döndürür, satır içi yürütülürse ve türünde bir bağımsız değişken yapılacak lambda bildirme tarafından `cancellation_token` oluşturduğunuz lambda içinde oluşturduğunuz zaman içinde belirtecini geçirerek herhangi bir görevi iptali tetikleyebilir. De kullanabilirsiniz `register_callback` yöntemi çağırdığınızda bir geri çağırma çalışma zamanı neden belirtecine `IAsyncInfo::Cancel` üzerinde zaman uyumsuz işlemi veya eylem üretilen...  
  
 Bu işlev yalnızca Windows çalışma zamanı uygulamaları için kullanılabilir.  
  
##  <a name="createresourcemanager"></a>  CreateResourceManager  
 Eşzamanlılık Çalışma zamanı Kaynak Yöneticisi'nin singleton örneği temsil eden bir arabirim döndürür. Resource Manager kaynakları birbirleri ile işbirliği yapmak istediğiniz zamanlayıcılar atamak için sorumludur.  
  
```
IResourceManager* __cdecl CreateResourceManager();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir `IResourceManager` arabirimi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem için birden çok sonraki çağrılar Kaynak Yöneticisi'nin aynı örneği döndürür. Her çağrı yöntemi artışlarla Başvuru Kaynağı Yöneticisi sayısı ve çağrısıyla eşlenmesi gerekir [Iresourcemanager::Release](http://msdn.microsoft.com/en-us/5d1356ec-fbd3-4284-a361-1e9e20bbb522) , Zamanlayıcı yapıldığında yöntemi Resource Manager ile iletişim.  
  
 [unsupported_os](unsupported-os-class.md) işletim sistemi eşzamanlılık çalışma zamanı tarafından desteklenmiyorsa atılır.  
  
##  <a name="create_task"></a>  create_task  
 Bir PPL oluşturur [görev](http://msdn.microsoft.com/en-us/5389e8a5-5038-40b6-844a-55e9b58ad35f) nesnesi. `create_task` kullanılabilir herhangi bir yere görev Oluşturucusu kullanıldığını. Kullanılmasına izin verdiği için çoğunlukla kolaylık sağlamak için sağlanmıştır `auto` görevleri oluşturulurken anahtar sözcüğü.  
  
```
template<typename T>
__declspec(noinline) auto create_task(T _Param, const task_options& _TaskOptions = task_options())
    -> task<typename details::_TaskTypeFromParam<T>::T>;

template<typename _ReturnType>
__declspec( noinline) task<_ReturnType> create_task(const task<_ReturnType>& _Task);
```  
  
### <a name="parameters"></a>Parametreler  
 `T`  
 Görev oluşturulması için parametre türü.  
  
 `_ReturnType`  
 `_Param`  
 İçinden görevi oluşturulması, parametre. Bu bir lambda veya işlev nesnesi olabilir bir `task_completion_event` nesnesi, farklı bir `task` nesne veya UWP uygulamanızda görevleri kullanıyorsanız Windows::Foundation::IAsyncInfo arabirim.  
  
 `_TaskOptions`  
 `_Task`  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yeni bir görev türü `T`, yani gelen çıkarımı yapılan `_Param`.  
  
### <a name="remarks"></a>Açıklamalar  
 İlk aşırı tek bir parametre alan bir görev Oluşturucu gibi davranır.  
  
 İkinci aşırı yüklemesi olan yeni oluşturulan görev sağlanan iptal belirteci ilişkilendirir. Bu aşırı kullanırsanız, farklı bir geçmesine izin verilmez `task` nesnesi ilk parametre olarak.  
  
 Döndürülen görev türü, işlev için ilk parametresinden algılanır. Varsa `_Param` olan bir `task_completion_event<T>`, `task<T>`, veya her iki tür döndüren bir functor `T` veya `task<T>`, oluşturulan görev türü `task<T>`.  
  
 Bir UWP uygulamasında varsa `_Param` Windows::Foundation::IAsyncOperation türünde\<T > ^ veya Windows::Foundation:: ıasyncoperationwithprogress\<T, P > ^, ya da bu türlerinden birini döndürür functor, oluşturulan görev olacaktır türü `task<T>`. Varsa `_Param` Windows::Foundation::IAsyncAction türünde ^ veya Windows::Foundation::IAsyncActionWithProgress\<P > ^, ya da bu türlerinden birini döndürür functor, oluşturulan görev yazın sahip `task<void>`.  
  
##  <a name="disabletracing"></a>  DisableTracing  
 Eşzamanlılık Çalışma Zamanı'nda izleme devre dışı bırakır. ETW İzleme varsayılan olarak kaydı olmadığından bu işlev kullanım dışıdır.  
  
```
__declspec(deprecated("Concurrency::DisableTracing is a deprecated function.")) _CRTIMP HRESULT __cdecl DisableTracing();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İzleme doğru devre dışı bırakılmışsa `S_OK` döndürülür. İzleme önceden başlatılmadı, `E_NOT_STARTED` döndürülür  
  
##  <a name="enabletracing"></a>  EnableTracing  
 Eşzamanlılık Çalışma Zamanı'nda izlemeyi etkinleştirir. ETW İzleme artık varsayılan olarak açık olduğundan bu işlev kullanım dışıdır.  
  
```
__declspec(deprecated("Concurrency::EnableTracing is a deprecated function.")) _CRTIMP HRESULT __cdecl EnableTracing();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İzleme doğru başlatılmışsa `S_OK` döndürülen; Aksi takdirde, `E_NOT_STARTED` döndürülür.  
  
##  <a name="free">Boş</a>  
 Tarafından önceden ayrılmış bellek bloğu serbest `Alloc` eşzamanlılık çalışma zamanı Suballocator önbelleğe alma yöntemi.  
  
```
void __cdecl Free(_Pre_maybenull_ _Post_invalid_ void* _PAllocation);
```  
  
### <a name="parameters"></a>Parametreler  
 `_PAllocation`  
 Tarafından önceden ayrılmış bellek için bir işaretçi `Alloc` boşaltılacak olan yöntemi. Varsa parametresi `_PAllocation` değerine ayarlayın `NULL`, bu yöntemi yok sayın ve hemen döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 , Uygulamanızda senaryoları hakkında yararlı önbelleğe alma Suballocator kullanarak daha fazla bilgi için bkz: [Görev Zamanlayıcı](../../../parallel/concrt/task-scheduler-concurrency-runtime.md).  
  
##  <a name="get_ambient_scheduler"></a>  get_ambient_scheduler  
  
```
inline std::shared_ptr<::Concurrency::scheduler_interface> get_ambient_scheduler();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
##  <a name="getexecutioncontextid"></a>  GetExecutionContextId  
 Arabirimini uygulayan bir yürütme bağlamı atanmış benzersiz bir tanımlayıcı döndürür `IExecutionContext` arabirimi.  
  
```
unsigned int __cdecl GetExecutionContextId();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yürütme bağlamı için benzersiz bir tanımlayıcı.  
  
### <a name="remarks"></a>Açıklamalar  
 Geçirdiğiniz önce yürütme bağlamı için bir tanımlayıcı elde etmek için bu yöntemi kullanın bir `IExecutionContext` kaynak yöneticisi tarafından sunulan yöntemlerden herhangi birini bir parametre olarak arabirimi.  
  
##  <a name="getosversion"></a>  GetOSVersion  
 İşletim sistemi sürümünü döndürür.  
  
```
IResourceManager::OSVersion __cdecl GetOSVersion();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşletim sistemini temsil eden bir Enum değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 [unsupported_os](unsupported-os-class.md) işletim sistemi eşzamanlılık çalışma zamanı tarafından desteklenmiyorsa atılır.  
  
##  <a name="getprocessorcount"></a>  GetProcessorCount  
 Temel alınan sistemdeki donanım iş parçacığı sayısını döndürür.  
  
```
unsigned int __cdecl GetProcessorCount();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Donanım iş parçacığı sayısı.  
  
### <a name="remarks"></a>Açıklamalar  
 [unsupported_os](unsupported-os-class.md) işletim sistemi eşzamanlılık çalışma zamanı tarafından desteklenmiyorsa atılır.  
  
##  <a name="getprocessornodecount"></a>  GetProcessorNodeCount  
 Temel alınan sistemdeki NUMA düğümlerinin veya işlemci paketleri sayısını döndürür.  
  
```
unsigned int __cdecl GetProcessorNodeCount();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 NUMA düğümleri veya işlemci paket sayısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Sistem daha fazla NUMA düğümlerinden daha işlemci paketler içeriyorsa, NUMA düğüm sayısını döndürülür, aksi takdirde, işlemci paket sayısı döndürülür.  
  
 [unsupported_os](unsupported-os-class.md) işletim sistemi eşzamanlılık çalışma zamanı tarafından desteklenmiyorsa atılır.  
  
##  <a name="getschedulerid"></a>  GetSchedulerId  
 Arabirimini uygulayan bir zamanlayıcı atanmış benzersiz bir tanımlayıcı döndürür `IScheduler` arabirimi.  
  
```
unsigned int __cdecl GetSchedulerId();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir zamanlayıcı için benzersiz bir tanımlayıcı.  
  
### <a name="remarks"></a>Açıklamalar  
 Geçirdiğiniz önce bir tanımlayıcı, Zamanlayıcısı elde etmek için bu yöntemi kullanın bir `IScheduler` kaynak yöneticisi tarafından sunulan yöntemlerden herhangi birini bir parametre olarak arabirimi.  
  
##  <a name="internal_assign_iterators"></a>  internal_assign_iterators  
  
```
template<typename T, class _Ax>
template<class _I> 
void concurrent_vector<T, _Ax>::internal_assign_iterators(
   _I first,
   _I last);
```   
  
### <a name="parameters"></a>Parametreler  
 `T`  
 `_Ax`  
 `_I`  
 `first`  
 `last`  
  
##  <a name="interruption_point"></a>  interruption_point  
 İptal için bir kesinti noktası oluşturur. Burada bu işlev çağrılır bağlamda iptal ediyor, bu şu anda yürütülen paralel iş yürütme durdurur dahili bir özel durum atar. İptal ediyor değilse işlev hiçbir şey yapmaz.  
  
```
inline void interruption_point();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Tarafından oluşturulan iç iptal özel durum catch değil `interruption_point()` işlevi. Özel durum yakalandı ve çalışma zamanı tarafından işlenen ve onu yakalama anormal olarak davranacak şekilde programınızı neden olabilir.  
  
##  <a name="is_current_task_group_canceling"></a>  is_current_task_group_canceling  
 Görev olup olmadığını grubu, şu anda geçerli bağlamda satır içi yürütüyor, ilişkin bir gösterge ortasında etkin bir iptal (ya da kısa süre içinde olacaktır) döndürür. Satır içi geçerli bağlama göre şu anda yürütülmekte olan hiçbir görev grubu ise unutmayın `false` döndürülür.  
  
```
bool __cdecl is_current_task_group_canceling();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true` şu anda yürütülmekte olan görev grubunun iptal ediliyor, `false` Aksi takdirde.  
  
### <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için bkz: [iptal](../../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md#cancellation).  
  
##  <a name="make_choice"></a>  make_choice  
 Oluşturan bir `choice` isteğe bağlı bir Mesajlaşma bloğundan `Scheduler` veya `ScheduleGroup` ve iki veya daha fazla giriş kaynağı.  
  
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
 `T1`  
 İlk kaynak ileti blok türü.  
  
 `T2`  
 İkinci kaynağı ileti blok türü.  
  
 `_PScheduler`  
 `Scheduler` İçinde yayma görev için nesne `choice` ileti bloğu zamanlandı.  
  
 `_Item1`  
 İlk kaynak.  
  
 `_Item2`  
 İkinci kaynağı.  
  
 `_Items`  
 Ek kaynaklar.  
  
 `_PScheduleGroup`  
 `ScheduleGroup` İçinde yayma görev için nesne `choice` ileti bloğu zamanlandı. `Scheduler` Kullanılan nesnesi zamanlama grubu tarafından kapsanan.  
  
### <a name="return-value"></a>Dönüş Değeri  
 A `choice` iki veya daha fazla giriş kaynaklarıyla ileti bloğu.  
  
##  <a name="make_greedy_join"></a>  make_greedy_join  
 Oluşturan bir `greedy multitype_join` isteğe bağlı bir Mesajlaşma bloğundan `Scheduler` veya `ScheduleGroup` ve iki veya daha fazla giriş kaynağı.  
  
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
 `T1`  
 İlk kaynak ileti blok türü.  
  
 `T2`  
 İkinci kaynağı ileti blok türü.  
  
 `_PScheduler`  
 `Scheduler` İçinde yayma görev için nesne `multitype_join` ileti bloğu zamanlandı.  
  
 `_Item1`  
 İlk kaynak.  
  
 `_Item2`  
 İkinci kaynağı.  
  
 `_Items`  
 Ek kaynaklar.  
  
 `_PScheduleGroup`  
 `ScheduleGroup` İçinde yayma görev için nesne `multitype_join` ileti bloğu zamanlandı. `Scheduler` Kullanılan nesnesi zamanlama grubu tarafından kapsanan.  
  
### <a name="return-value"></a>Dönüş Değeri  
 A `greedy multitype_join` iki veya daha fazla giriş kaynaklarıyla ileti bloğu.  
  
##  <a name="make_join"></a>  make_join  
 Oluşturan bir `non_greedy multitype_join` isteğe bağlı bir Mesajlaşma bloğundan `Scheduler` veya `ScheduleGroup` ve iki veya daha fazla giriş kaynağı.  
  
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
 `T1`  
 İlk kaynak ileti blok türü.  
  
 `T2`  
 İkinci kaynağı ileti blok türü.  
  
 `_PScheduler`  
 `Scheduler` İçinde yayma görev için nesne `multitype_join` ileti bloğu zamanlandı.  
  
 `_Item1`  
 İlk kaynak.  
  
 `_Item2`  
 İkinci kaynağı.  
  
 `_Items`  
 Ek kaynaklar.  
  
 `_PScheduleGroup`  
 `ScheduleGroup` İçinde yayma görev için nesne `multitype_join` ileti bloğu zamanlandı. `Scheduler` Kullanılan nesnesi zamanlama grubu tarafından kapsanan.  
  
### <a name="return-value"></a>Dönüş Değeri  
 A `non_greedy multitype_join` iki veya daha fazla giriş kaynaklarıyla ileti bloğu.  
  
##  <a name="make_task"></a>  make_task  
 Oluşturmak için Üreteç yöntemi bir `task_handle` nesnesi.  
  
```
template <class _Function>
task_handle<_Function> make_task(const _Function& _Func);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Function`  
 Tarafından temsil edilen çalışma yürütmek için çağrılan işlev nesnesinin türü `task_handle` nesnesi.  
  
 `_Func`  
 Tarafından temsil edilen çalışma yürütmek için çağrılan işlev `task_handle` nesnesi. Bu, bir işlev için bir işaretçi bir lambda functor olabilir veya herhangi bir işlev çağırma işleci imzalı sürümünü destekleyen nesne `void operator()()`.  
  
### <a name="return-value"></a>Dönüş Değeri  
 A `task_handle` nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Oluşturmanız gerektiğinde bu işlevi kullanışlı bir `task_handle` lambda functor true türü bilmeden nesnesi oluşturmak izin verdiğinden lambda ifadesi ile nesne.  
  
##  <a name="parallel_buffered_sort"></a>  parallel_buffered_sort  
 Belirli bir aralık içinde öğeleri nondescending sırada ya da bir ikili karşılaştırma paralel tarafından belirtilen bir sıralama ölçütü göre düzenler. Bu işlev anlamsal olarak benzer `std::sort` gereksinim duyduğu dışında bir karşılaştırma tabanlı kararsız, yerinde sıralama aynıdır, `O(n)` ek alan ve varsayılan olarak başlatılması için sıralanan öğeleri gerektirir.  
  
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
 `_Random_iterator`  
 Giriş aralığı yineleyici türü.  
  
 `_Allocator`  
 C++ Standart Kitaplığı uyumlu bellek ayırıcısı türü.  
  
 `_Function`  
 İkili karşılaştırıcı türü.  
  
 `_Begin`  
 Sıralanacak ilk öğe konumu aralığında adresleme bir rastgele erişim yineleyici.  
  
 `_End`  
 Sıralanacak konumu bir aralıkta son öğesi geçmiş adresleme bir rastgele erişim yineleyici.  
  
 `_Alloc`  
 C++ Standart Kitaplığı uyumlu bellek ayırıcısı örneği.  
  
 `_Func`  
 Sıralama, art arda gelen öğeler tarafından karşılanması karşılaştırma ölçütü tanımlayan bir kullanıcı tanımlı koşul işlevinin nesnesi. İkili karşılaştırma iki bağımsız değişken alıp döndüren `true` yerine getirdiğinizde ve `false` uyulmadığını olduğunda. Bu karşılaştırıcı işlevi bir katı zayıf çiftleri dizisi diziden sıralama zorunlu tuttukları gerekir.  
  
 `_Chunk_size`  
 Paralel yürütme için iki şekilde bölmeniz bir öbek minimum boyutu.  
  
### <a name="remarks"></a>Açıklamalar  
 Tüm aşırı gerektiren `n * sizeof(T)` ek alan nerede `n` sıralanacak, öğe sayısı ve `T` öğe türü. Çoğu durumda, üzerinde bir geliştirme performans parallel_buffered_sort gösterecektir [parallel_sort](concurrency-namespace-functions.md), ve kullanılabilir bellek varsa parallel_sort kullanmanız gerekir.  
  
 İkili karşılaştırıcı belirtmezseniz `std::less` işleci sağlamak öğe türü gerektiren varsayılan olarak kullanılan `operator<()`.  
  
 Bir ayırıcı türü veya örnek, C++ Standart Kitaplığı bellek ayırıcısı belirtmezseniz `std::allocator<T>` arabellek ayırmak için kullanılır.  
  
 Algoritma giriş aralığı iki parçalara ayırır ve iki alt öbekleri Paralel yürütme için sırayla her bir öbeğin böler. İsteğe bağlı bağımsız değişkeni `_Chunk_size` algoritması, işleme öbek boyutunu belirtmek için kullanılan < `_Chunk_size` seri olarak.  
  
##  <a name="parallel_for"></a>  parallel_for  
 `parallel_for` dizinler aralığında tekrarlanan ve kullanıcı tarafından sağlanan bir işlev her yinelemesinde paralel olarak yürütür.  
  
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
 `_Index_type`  
 Yineleme için kullanılan dizin türü.  
  
 `_Function`  
 Her bir yineleme yürütülecek işlevi türü.  
  
 `_Partitioner`  
 Sağlanan aralığı bölümlemek için kullanılan bölümleyici türü.  
  
 `first`  
 Yineleme dahil edilecek ilk dizin.  
  
 `last`  
 Dizini bir yinelemede dahil edilecek son dizin geçti.  
  
 `_Step`  
 Gelen dolaşırken adım değeri `first` için `last`. Adım pozitif olmalıdır. [invalid_argument](../../../standard-library/invalid-argument-class.md) adım 1'den az ise oluşturulur.  
  
 `_Func`  
 Her bir yineleme yürütülecek işlev. Bu lambda ifadesi, bir işlev işaretçisi olabilir veya herhangi bir işlev çağırma işleci imzalı sürümünü destekleyen nesne `void operator()(_Index_type)`.  
  
 `_Part`  
 Bölümleyici nesneye başvuru. Bağımsız değişkeni şunlardan biri olabilir `const` [auto_partitioner](auto-partitioner-class.md)`&`, `const` [static_partitioner](static-partitioner-class.md)`&`, `const` [simple_ bölümleyici](simple-partitioner-class.md) `&` veya [affinity_partitioner](affinity-partitioner-class.md) `&` varsa bir [affinity_partitioner](affinity-partitioner-class.md) nesnesi kullanılır, başvuru bir const olmayan l-değeri olmalıdır algoritma yeniden kullanmayı gelecekteki döngüler durumu depolayabileceğiniz başvuru.  
  
### <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için bkz: [paralel algoritmalar](../../../parallel/concrt/parallel-algorithms.md).  
  
##  <a name="parallel_for_each"></a>  parallel_for_each  
 `parallel_for_each` Belirtilen işlev paralel bir aralıkta her öğesine uygular. Anlam olarak eşdeğerdir `for_each` işlevi `std` öğeleri üzerinden bu yineleme paralel olarak gerçekleştirilir ve yineleme sırasını belirtilmezse dışında ad. Bağımsız değişkeni `_Func` işlev çağırma işleci formun desteklemelidir `operator()(T)` burada parametresi `T` üzerinden yinelendiğinde kapsayıcı öğe türü değil.  
  
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
 `_Iterator`  
 Kapsayıcı yinelemek için kullanılan yineleyici türü.  
  
 `_Function`  
 Aralık içinde her öğeye uygulanan işlev türü.  
  
 `_Partitioner`  
 `first`  
 Paralel yineleme dahil edilecek ilk öğenin konumunu adresleme yineleyici.  
  
 `last`  
 Paralel yineleme dahil edilecek konumunu bir aşan son öğeden adresleme yineleyici.  
  
 `_Func`  
 Aralığın her bir öğesinde uygulanan bir kullanıcı tanımlı işlev nesnesi.  
  
 `_Part`  
 Bölümleyici nesneye başvuru. Bağımsız değişkeni şunlardan biri olabilir `const` [auto_partitioner](auto-partitioner-class.md)`&`, `const` [static_partitioner](static-partitioner-class.md)`&`, `const` [simple_ bölümleyici](simple-partitioner-class.md) `&` veya [affinity_partitioner](affinity-partitioner-class.md) `&` varsa bir [affinity_partitioner](affinity-partitioner-class.md) nesnesi kullanılır, başvuru bir const olmayan l-değeri olmalıdır algoritma yeniden kullanmayı gelecekteki döngüler durumu depolayabileceğiniz başvuru.  
  
### <a name="remarks"></a>Açıklamalar  
 [auto_partitioner](auto-partitioner-class.md) açık bir bölümleyici olmadan aşırı kullanılır.  
  
 Rastgele desteklemeyen yineleyiciler erişim, yalnızca [auto_partitioner](auto-partitioner-class.md) desteklenir.  
  
 Daha fazla bilgi için bkz: [paralel algoritmalar](../../../parallel/concrt/parallel-algorithms.md).  
  
##  <a name="parallel_invoke"></a>  parallel_invoke  
 Yürütme bitinceye kadar paralel ve blokları parametre olarak sağlanan işlev nesneleri yürütür. Her işlev nesnesi bir lambda ifadesi işlevi için bir işaretçi olabilir veya herhangi bir işlev çağırma işleci imzalı destekleyen nesne `void operator()()`.  
  
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
 `_Function1`  
 Paralel olarak yürütülecek ilk işlevi nesnenin türü.  
  
 `_Function2`  
 Paralel olarak yürütülecek ikinci işlevi nesnenin türü.  
  
 `_Function3`  
 Paralel olarak yürütülecek üçüncü işlevi nesnenin türü.  
  
 `_Function4`  
 Paralel olarak yürütülecek dördüncü işlevi nesnenin türü.  
  
 `_Function5`  
 Paralel olarak yürütülecek beşinci işlevi nesnenin türü.  
  
 `_Function6`  
 Paralel olarak yürütülecek altıncı işlevi nesnenin türü.  
  
 `_Function7`  
 Paralel olarak yürütülecek yedinci işlevi nesnenin türü.  
  
 `_Function8`  
 Paralel olarak yürütülecek sekizinci işlevi nesnenin türü.  
  
 `_Function9`  
 Paralel olarak yürütülecek dokuzuncu işlevi nesnenin türü.  
  
 `_Function10`  
 Paralel olarak yürütülecek onuncu işlevi nesnenin türü.  
  
 `_Func1`  
 Paralel olarak yürütülecek ilk işlevi nesne.  
  
 `_Func2`  
 Paralel olarak yürütülecek ikinci işlev nesnesi.  
  
 `_Func3`  
 Paralel olarak yürütülecek üçüncü işlev nesnesi.  
  
 `_Func4`  
 Paralel olarak yürütülecek dördüncü işlev nesnesi.  
  
 `_Func5`  
 Paralel olarak yürütülecek beşinci işlev nesnesi.  
  
 `_Func6`  
 Paralel olarak yürütülecek altıncı işlev nesnesi.  
  
 `_Func7`  
 Paralel olarak yürütülecek yedinci işlev nesnesi.  
  
 `_Func8`  
 Paralel olarak yürütülecek sekizinci işlev nesnesi.  
  
 `_Func9`  
 Paralel olarak yürütülecek dokuzuncu işlev nesnesi.  
  
 `_Func10`  
 Paralel olarak yürütülecek onuncu işlev nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Parametreleri satır içi üzerinde çağıran bağlamını yürütür gibi bir veya daha fazla işlevi nesnelerin sağlanan unutmayın.  
  
 Bir veya daha fazla parametre olarak bu işleve işlev nesneleri bir özel durum oluşturursa, çalışma zamanı kendi seçme bir tür özel durumu seçin ve çağrısı dışında yayılması `parallel_invoke`.  
  
 Daha fazla bilgi için bkz: [paralel algoritmalar](../../../parallel/concrt/parallel-algorithms.md).  
  
##  <a name="parallel_radixsort"></a>  parallel_radixsort  
 Belirli bir aralık içinde öğeleri algoritması sıralama sayı tabanını kullanarak bir olmayan azalan düzenler. İmzasız tamsayı benzeri anahtarlara sıralanacak öğeleri yansıtabilirsiniz projeksiyon işlevi gerektiren bir tutarlı sıralama işlevi budur. Varsayılan olarak başlatılması için sıralanan öğeleri gereklidir.  
  
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
 `_Random_iterator`  
 Giriş aralığı yineleyici türü.  
  
 `_Allocator`  
 C++ Standart Kitaplığı uyumlu bellek ayırıcısı türü.  
  
 `_Function`  
 Projeksiyon işlevi türü.  
  
 `_Begin`  
 Sıralanacak ilk öğe konumu aralığında adresleme bir rastgele erişim yineleyici.  
  
 `_End`  
 Sıralanacak konumu bir aralıkta son öğesi geçmiş adresleme bir rastgele erişim yineleyici.  
  
 `_Alloc`  
 C++ Standart Kitaplığı uyumlu bellek ayırıcısı örneği.  
  
 `_Proj_func`  
 Bir öğenin bir tam sayı değerine dönüştürür projeksiyon kullanıcı tanımlı işlev nesnesi.  
  
 `_Chunk_size`  
 Paralel yürütme için iki şekilde bölmeniz bir öbek minimum boyutu.  
  
### <a name="remarks"></a>Açıklamalar  
 Tüm aşırı gerektiren `n * sizeof(T)` ek alan nerede `n` sıralanacak, öğe sayısı ve `T` öğe türü. Birli projeksiyon functor imzalı `I _Proj_func(T)` bir öğe verildiğinde bir anahtar döndürmek için gerekli olduğu `T` öğe türü ve `I` bir işaretsiz tamsayı benzeri türüdür.  
  
 Projeksiyon işlevi belirtmezseniz, yalnızca öğe döndüren bir varsayılan projeksiyon işlevi tam sayı türleri için kullanılır. İşlev öğesi bir tamsayı türünde olmadığında projeksiyon işlevi değilse derlemek başarısız olur.  
  
 Bir ayırıcı türü veya örnek, C++ Standart Kitaplığı bellek ayırıcısı belirtmezseniz `std::allocator<T>` arabellek ayırmak için kullanılır.  
  
 Algoritma giriş aralığı iki parçalara ayırır ve iki alt öbekleri Paralel yürütme için sırayla her bir öbeğin böler. İsteğe bağlı bağımsız değişkeni `_Chunk_size` algoritması, işleme öbek boyutunu belirtmek için kullanılan < `_Chunk_size` seri olarak.  
  
##  <a name="parallel_reduce"></a>  parallel_reduce  
 Belirtilen aralıktaki tüm öğelerin toplamı, art arda kısmi toplamlarını bilgi işlem tarafından hesaplar veya benzer şekilde paralel olarak belirtilen bir ikili işlem toplam dışında kullanılarak elde edilen art arda kısmi sonuçlar sonucunu hesaplar. `parallel_reduce` anlam olarak benzer `std::accumulate`, ikili işlem ilişkilendirilebilir olmasını gerektirir ve bir başlangıç değeri yerine bir kimlik değeri gerektirir.  
  
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
 `_Forward_iterator`  
 Giriş aralığı yineleyici türü.  
  
 `_Sym_reduce_fun`  
 Simetrik azaltma işlevi türü. Bu işlev türü imzalı olmalıdır `_Reduce_type _Sym_fun(_Reduce_type, _Reduce_type)`, burada _Reduce_type kimlik türü ve azaltma sonuç türü aynıdır. Üçüncü aşırı yüklemesi için bu, çıktı türü ile tutarlı olmalıdır `_Range_reduce_fun`.  
  
 `_Reduce_type`  
 İnput öğesi türünden farklı olabilir için azaltır. giriş türü. Dönüş değeri ve kimlik değeri bu tür sahip.  
  
 `_Range_reduce_fun`  
 Aralık azaltma işlevi türü. Bu işlev türü imzalı olmalıdır `_Reduce_type _Range_fun(_Forward_iterator, _Forward_iterator, _Reduce_type)`, _Reduce_type aynıdır kimlik türü ve azaltma sonuç türü.  
  
 `_Begin`  
 Azaltılmasına aralığın ilk öğe adresleme giriş yineleyici.  
  
 `_End`  
 Azaltılmasına aralıktaki son öğenin ötesinde bir konuma öğeyi adresleme giriş yineleyici.  
  
 `_Identity`  
 Kimlik değerini `_Identity` azaltma sonuç türü ile aynı türde olduğundan ve ayrıca `value_type` birinci ve ikinci aşırı yineleyici. Üçüncü aşırı kimlik değeri azaltma sonuç türü aynı türde olması gerekir, ancak farklı olabilir `value_type` yineleyici. Uygun bir değere sahip olmalıdır şekilde aralık azaltma işleci `_Range_fun`, tek bir öğesi türü bir dizi uygulandığında `value_type` ve kimlik değeri davranır bir cast türünü türünden değerinin gibi `value_type` kimlik türü.  
  
 `_Sym_fun`  
 Azaltma saniye içinde kullanılan simetrik işlev. Açıklamalar için daha fazla bilgi için bkz.  
  
 `_Range_fun`  
 Azaltma, ilk aşamasında kullanılan işlev. Açıklamalar için daha fazla bilgi için bkz.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Azaltma sonuç.  
  
### <a name="remarks"></a>Açıklamalar  
 Paralel azaltma gerçekleştirmek için temel alınan Zamanlayıcı kullanılabilir çalışanları sayısına dayalı parçalara aralığı işlevi böler. Azaltma iki aşamada gerçekleşir, azaltma her öbek içinde ilk aşamayı gerçekleştirir ve her bir öbeğin kısmi sonuçlarından arasında azaltma İkinci aşama gerçekleştirir.  
  
 İlk aşırı gerektiren yineleyici 's `value_type`, `T`, aynı kimlik değeri türü olarak azaltma sonuç türü. Öğe türü T işleci sağlamalısınız `T T::operator + (T)` her bir öbeğin öğelerinde azaltmak için. Aynı işleci ikinci aşamasında kullanılır.  
  
 İkinci aşırı ayrıca gerektiren yineleyici 's `value_type` azaltma sonuç türü yanı sıra kimlik değeri türü aynı olmalıdır. Sağlanan ikili işleç `_Sym_fun` ilk aşaması için ilk değer olarak kimlik değeriyle hem azaltma aşamaları kullanılır.  
  
 Üçüncü aşırı yüklemesi için kimlik değeri türü aynı azaltma sonuç türü, ancak yineleyici'nın olmalıdır `value_type` hem de farklı olabilir. Aralık azaltma işlevi `_Range_fun` kimlik değeri ile ilk aşamada ilk değer ve ikili işlevi kullanılan `_Sym_reduce_fun` sonuçları ikinci aşamasında sub uygulanır.  
  
##  <a name="parallel_sort"></a>  parallel_sort  
 Belirli bir aralık içinde öğeleri nondescending sırada ya da bir ikili karşılaştırma paralel tarafından belirtilen bir sıralama ölçütü göre düzenler. Bu işlev anlamsal olarak benzer `std::sort` karşılaştırma tabanlı kararsız, yerinde bir sıralama olması.  
  
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
 `_Random_iterator`  
 Giriş aralığı yineleyici türü.  
  
 `_Function`  
 İkili karşılaştırma functor türü.  
  
 `_Begin`  
 Sıralanacak ilk öğe konumu aralığında adresleme bir rastgele erişim yineleyici.  
  
 `_End`  
 Sıralanacak konumu bir aralıkta son öğesi geçmiş adresleme bir rastgele erişim yineleyici.  
  
 `_Func`  
 Sıralama, art arda gelen öğeler tarafından karşılanması karşılaştırma ölçütü tanımlayan bir kullanıcı tanımlı koşul işlevinin nesnesi. İkili karşılaştırma iki bağımsız değişken alıp döndüren `true` yerine getirdiğinizde ve `false` uyulmadığını olduğunda. Bu karşılaştırıcı işlevi bir katı zayıf çiftleri dizisi diziden sıralama zorunlu tuttukları gerekir.  
  
 `_Chunk_size`  
 Paralel yürütme için iki şekilde bölmeniz bir öbek minimum boyutu.  
  
### <a name="remarks"></a>Açıklamalar  
 İlk aşırı kullanır ikili karşılaştırıcı `std::less`.  
  
 İkinci kullanan aşırı imza olmalıdır sağlanan ikili karşılaştırıcı `bool _Func(T, T)` burada `T` giriş aralığındaki öğelerin türü.  
  
 Algoritma giriş aralığı iki parçalara ayırır ve iki alt öbekleri Paralel yürütme için sırayla her bir öbeğin böler. İsteğe bağlı bağımsız değişkeni `_Chunk_size` algoritması, işleme öbek boyutunu belirtmek için kullanılan < `_Chunk_size` seri olarak.  
  
##  <a name="parallel_transform"></a>  parallel_transform  
 Belirtilen işlev nesnesi kaynak aralığı her bir öğe veya çiftlerini iki kaynak aralıklarından geçerlidir ve paralel bir hedef aralığı içine işlev nesnesinin dönüş değerleri kopyalar. Bu işlev anlam olarak eşdeğerdir `std::transform`.  
  
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
 `_Input_iterator1`  
 İlk ya da yalnızca giriş yineleyici türü.  
  
 `_Output_iterator`  
 Çıktı yineleyici türü.  
  
 `_Unary_operator`  
 Her öğe giriş aralığındaki üzerinde yürütülecek birli functor türü.  
  
 `_Input_iterator2`  
 İkinci giriş yineleyici türü.  
  
 `_Binary_operator`  
 İki kaynak aralıklarından öğelerde Eşli yürütülen ikili functor türü.  
  
 `_Partitioner`  
 `first1`  
 İlk ya da yalnızca kaynak aralığı üzerinde çalıştırılan ilk öğe konumu adresleme giriş yineleyici.  
  
 `last1`  
 Konumunda bir son öğeden geçmiş ilk ya da yalnızca kaynak aralığı üzerinde çalıştırılan adresleme giriş yineleyici.  
  
 `_Result`  
 İlk öğesi Hedef aralık konumu adresleme çıkış yineleyici.  
  
 `_Unary_op`  
 Kaynak aralığındaki her öğeye uygulanan birli kullanıcı tanımlı işlev nesnesi.  
  
 `_Part`  
 Bölümleyici nesneye başvuru. Bağımsız değişkeni şunlardan biri olabilir `const` [auto_partitioner](auto-partitioner-class.md)`&`, `const` [static_partitioner](static-partitioner-class.md)`&`, `const` [simple_ bölümleyici](simple-partitioner-class.md) `&` veya [affinity_partitioner](affinity-partitioner-class.md) `&` varsa bir [affinity_partitioner](affinity-partitioner-class.md) nesnesi kullanılır, başvuru bir const olmayan l-değeri olmalıdır algoritma yeniden kullanmayı gelecekteki döngüler durumu depolayabileceğiniz başvuru.  
  
 `first2`  
 İlk öğe konumu ikinci kaynak aralıktaki üzerinde çalıştırılan adresleme giriş yineleyici.  
  
 `_Binary_op`  
 İkili, iki kaynak aralıkları bir ileriye doğru sırada uygulanan bir kullanıcı tanımlı ikili işlev nesnesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşlev nesnesi tarafından dönüştürülmüş çıktı öğeleri alıyor Hedef aralık son öğe geçmiş konumu adresleme çıkış yineleyici.  
  
### <a name="remarks"></a>Açıklamalar  
 [auto_partitioner](auto-partitioner-class.md) açık bölümleyici bağımsız değişken olmadan aşırı yüklemeleri için kullanılır.  
  
 Rastgele desteklemeyen yineleyiciler erişim, yalnızca [auto_partitioner](auto-partitioner-class.md) desteklenir.  
  
 Bağımsız değişken almayan aşırı `_Unary_op` birli functor giriş aralığındaki her öğeye uygulayarak giriş aralığı çıktı aralığına dönüştürün. `_Unary_op` İşlev çağırma işleci imzayla desteklemelidir `operator()(T)` burada `T` üzerinden yinelendiğinde aralık değeri türü değil.  
  
 Bağımsız değişken almayan aşırı `_Binary_op` ilk giriş aralığı ve ikinci giriş aralığından bir öğe için bir öğe ikili functor uygulayarak iki giriş aralığı çıktı aralığına dönüştürün. `_Binary_op` İşlev çağırma işleci imzayla desteklemelidir `operator()(T, U)` nerede `T`, `U` iki giriş yineleyiciler değer türleridir.  
  
 Daha fazla bilgi için bkz: [paralel algoritmalar](../../../parallel/concrt/parallel-algorithms.md).  
  
##  <a name="receive"></a>  Alma  
 Bir genel uygulama, tam olarak bir kaynaktan veri bekleyin ve kabul edilen değerlerin filtrelemek bir bağlam izin vererek alırsınız.  
  
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
 `T`  
 Yük türü.  
  
 `_Src`  
 Bir işaretçi veya veri beklenen kaynağına başvuru.  
  
 `_Timeout`  
 Yöntemi için gereken en uzun süreyi milisaniye cinsinden veriler için.  
  
 `_Filter_proc`  
 İletileri kabul edilip edilmeyeceğini belirler bir filtre işlevi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir değer kaynağından, yük türü.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa parametresi `_Timeout` sabiti dışında bir değere sahip `COOPERATIVE_TIMEOUT_INFINITE`, özel durum [operation_timed_out](operation-timed-out-class.md) bir ileti alındığında önce belirtilen sürede sona ererse atılır. Sıfır uzunluk zaman aşımı istiyorsanız, kullanması gereken [try_receive](concurrency-namespace-functions.md) arama aksine işlevi `receive` bir zaman aşımı süresi ile `0` (sıfır), daha verimlidir ve zaman aşımlarını özel durumlar oluşturmadığını.  
  
 Daha fazla bilgi için bkz: [ileti geçirme işlevleri](../../../parallel/concrt/message-passing-functions.md).  
  
##  <a name="run_with_cancellation_token"></a>  run_with_cancellation_token  
 İşlev nesnesi, verilen iptal belirteci bağlamında hemen ve eşzamanlı olarak yürütür.  
  
```
template<typename _Function>
void run_with_cancellation_token(
    const _Function& _Func,
    cancellation_token _Ct);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Function`  
 Çağrılan işlev nesnesi türü.  
  
 `_Func`  
 Yürütülecek işlev nesnesi. Bu nesne void(void) imzası ile işlev çağırma işleci desteklemesi gerekir.  
  
 `_Ct`  
 İşlev nesnesi örtük iptaline kontrol edecek iptal belirteci. Kullanım `cancellation_token::none()` işlevi yürütme iptal ediliyor üst görev grubundan örtük iptal olasılığını olmadan istiyorsanız.  
  
### <a name="remarks"></a>Açıklamalar  
 İşlev nesnesi herhangi kesinti noktaları olacaktır ayarlandığında tetiklenen `cancellation_token` iptal edilir. Açık belirteci `_Ct` bu yalıtmak `_Func` üst belirteci yok ya da farklı bir belirteci varsa üst iptal gelen.  
  
##  <a name="send"></a>  Gönder  
 Zaman uyumlu bir hedef kabul eder ya da ileti reddettiğinde kadar bekler işlemi gönderin.  
  
```
template <class T>
bool send(_Inout_ ITarget<T>* _Trg, const T& _Data);

template <class T>
bool send(ITarget<T>& _Trg, const T& _Data);
```  
  
### <a name="parameters"></a>Parametreler  
 `T`  
 Yük türü.  
  
 `_Trg`  
 Bir işaretçi veya veri gönderildiği hedefine başvuru.  
  
 `_Data`  
 Gönderilecek verileri referansı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true` ileti kabul edildiyse `false` Aksi takdirde.  
  
### <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için bkz: [ileti geçirme işlevleri](../../../parallel/concrt/message-passing-functions.md).  
  
##  <a name="set_ambient_scheduler"></a>  set_ambient_scheduler  
  
```
inline void set_ambient_scheduler(std::shared_ptr<::Concurrency::scheduler_interface> _Scheduler);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Scheduler`  
  
##  <a name="set_task_execution_resources"></a>  set_task_execution_resources  
 Belirtilen benzeşim için eşzamanlılık çalışma zamanı iç çalışan iş parçacıkları tarafından kullanılan yürütme kaynakları kısıtlar.  
  
 Bu yöntemi yalnızca Resource Manager oluşturulmadan önce arasında veya iki Resource Manager yaşam süreleri çağırmak için geçerlidir. Kaynak Yöneticisi'ni çağırma aynı anda yok sürece birden çok kez çağrılabilir. Bir benzeşim sınırı ayarladıktan sonra onu sonraki geçerli çağrısı kadar sürdürür `set_task_execution_resources` yöntemi.  
  
 Sağlanan benzeşim maskesi bir alt işlem benzeşim maskesi olması gerekmez. İşlem benzeşimi gerekiyorsa güncelleştirilir.  
  
```
void __cdecl set_task_execution_resources(
    DWORD_PTR _ProcessAffinityMask);

void __cdecl set_task_execution_resources(
    unsigned short count,
    PGROUP_AFFINITY _PGroupAffinity);
```  
  
### <a name="parameters"></a>Parametreler  
 `_ProcessAffinityMask`  
 Eşzamanlılık Çalışma zamanı çalışan iş parçacığı için kısıtlı olacak benzeşim maskesi. Eşzamanlılık Çalışma zamanı geçerli işlemci grubunun bir alt sınırlamak istiyorsanız 64 donanım iş parçacığı daha büyük bir sistemde bu yöntemi kullanın. Genel olarak, Grup benzeşimleri dizisi makinelerde benzeşimi değerinden 64 donanım iş parçacığı ile kısıtlamak için bir parametre olarak kabul yöntemi sürümünü kullanmanız gerekir.  
  
 `count`  
 Sayısı `GROUP_AFFINITY` parametresi tarafından belirtilen dizi giriş `_PGroupAffinity`.  
  
 `_PGroupAffinity`  
 Bir dizi `GROUP_AFFINITY` girişleri.  
  
### <a name="remarks"></a>Açıklamalar  
 Yöntemi özel durum oluşturacak bir [invalid_operation](invalid-operation-class.md) Resource Manager bunu çağrıldığında, aynı anda varsa, özel durum ve bir [invalid_argument](../../../standard-library/invalid-argument-class.md) benzeşimi bir boş kümesinde sonuçları belirtilmişse özel durumu kaynaklar.  
  
 Grup benzeşim bir dizi parametre olarak alır yöntemi sürümü yalnızca kullanılan işletim sistemi sürümü Windows 7 veya üzeri olmalıdır. Aksi halde, bir [invalid_operation](invalid-operation-class.md) özel durumu oluşur.  
  
 Bu yöntemi çağrıldıktan sonra işlem benzeşimi programlı şekilde değiştirmek için sınırlı benzeşim yeniden değerlendirmek için Kaynak Yöneticisi'ni neden olmaz. Bu nedenle, bu yöntemi çağırmadan önce benzeşim işlemek için tüm değişiklikler yapılmalıdır.  
  
##  <a name="swap"></a>  Değiştirme  
 İki öğelerini alış verişleri `concurrent_vector` nesneleri.  
  
```
template<typename T, class _Ax>
inline void swap(
    concurrent_vector<T, _Ax>& _A,
    concurrent_vector<T, _Ax>& _B);
```  
  
### <a name="parameters"></a>Parametreler  
 `T`  
 Eşzamanlı vektörler depolanan öğelerin veri türü.  
  
 `_Ax`  
 Eşzamanlı vektörlerinin ayırıcı türü.  
  
 `_A`  
 Öğeleri olan eşzamanlı vektör olanlar değiştirilebilmesi için eş zamanlı vektör `_B`.  
  
 `_B`  
 Öğeleri takas için sağlama eşzamanlı vektör veya öğeleri olan eşzamanlı vektör olanlar değiştirilebilmesi için vektör `_A`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir algoritma özelleştirilmiş kapsayıcı sınıfını şablon işlevi olan `concurrent_vector` üye işlevini yürütmek için `_A`. [concurrent_vector::swap](concurrent-vector-class.md#swap)( `_B`). İşlev şablonlarının kısmi derleyici tarafından sıralaması örneğine bunlar. Şablon işlevleri işlev çağrısı şablonla eşleşmesi benzersiz değil şekilde aşırı zaman derleyici şablon işlevi en özelleştirilmiş sürümünü seçin. Genel bir şablon işlevi sürümü `template <class T> void swap(T&, T&)`, algoritma sınıfı tarafından atama çalışır ve yavaş bir işlemdir. Her bir kapsayıcıdaki özel sürüm kapsayıcı sınıfı iç gösterimi ile çalışabilirsiniz gibi daha hızlıdır.  
  
 Bu yöntem eşzamanlılık uyumlu değil. Bu yöntemi çağırdığınızda başka bir iş parçacığı eşzamanlı vektörlerinin birini işlemleri gerçekleştirme emin olmalısınız.  
  
##  <a name="task_from_exception"></a>  task_from_exception  
  
```
template<typename _TaskType, typename _ExType>
task<_TaskType> task_from_exception(
    _ExType _Exception,
    const task_options& _TaskOptions = task_options());
```  
  
### <a name="parameters"></a>Parametreler  
 `_TaskType`  
 `_ExType`  
 `_Exception`  
 `_TaskOptions`  
  
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
 `T`  
 `_Param`  
 `_TaskOptions`  
  
### <a name="return-value"></a>Dönüş Değeri  
  
##  <a name="trace_agents_register_name"></a>  Trace_agents_register_name  
 Verilen ada ileti bloğu veya ETW İzleme Aracısı ilişkilendirir.  
  
```
template <class T>
void Trace_agents_register_name(
    _Inout_ T* _PObject,
    _In_z_ const wchar_t* _Name);
```  
  
### <a name="parameters"></a>Parametreler  
 `T`  
 Nesnenin türü. Bu genellikle bir ileti bloğu ya da bir aracı olur.  
  
 `_PObject`  
 İleti bloğu veya izlemede adlı aracısı için bir işaretçi.  
  
 `_Name`  
 Belirtilen nesnenin adı.  
  
##  <a name="try_receive"></a>  try_receive  
 Genel try-alma uygulaması, tam olarak bir kaynaktan veriler arayabilir ve kabul edilen değerlerin filtrelemek bir bağlam sağlar. Veri hazır değilse yöntemi false döndürür.  
  
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
 `T`  
 Yük türü  
  
 `_Src`  
 Bir işaretçi veya veri beklenen kaynağına başvuru.  
  
 `_value`  
 Bir başvuru sonucu yerleştirileceği bir konuma.  
  
 `_Filter_proc`  
 İletileri kabul edilip edilmeyeceğini belirler bir filtre işlevi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 A `bool` değerini gösteren bir yük içinde yerleştirilen olup olmadığına bakılmaksızın `_value`.  
  
### <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için bkz: [ileti geçirme işlevleri](../../../parallel/concrt/message-passing-functions.md).  
  
##  <a name="wait"></a>  bekleme  
 Belirtilen bir süre için geçerli bağlam duraklatır.  
  
```
void __cdecl wait(unsigned int _Milliseconds);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Milliseconds`  
 Geçerli bağlam için duraklatılması milisaniye sayısı. Varsa `_Milliseconds` parametre değerine ayarlanmış `0`, geçerli bağlam devam etmeden önce diğer runnable bağlamları yürütülmesine verim.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem bir eşzamanlılık çalışma zamanı Zamanlayıcı bağlamda çağrılırsa, Zamanlayıcı temel alınan kaynak üzerinde çalıştırmak için farklı bir bağlam bulur. Zamanlayıcı doğası gereği işbirlikçi olduğundan bu bağlamda tam olarak belirtilen milisaniye sayısını sonra devam edilemiyor. Zamanlayıcı işlevinizde Zamanlayıcı verim olmayan diğer görevleri çalıştırmakla meşgul ise, bekleme süresi belirsiz olabilir.  
  
##  <a name="when_all"></a>  when_all  
 Tüm bağımsız değişkenler olarak verilen görevleri başarıyla tamamlandığında, başarılı bir şekilde tamamlanır bir görev oluşturur.  
  
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
 `_Iterator`  
 Giriş yineleyici türü.  
  
 `_Begin`  
 Sonuçta elde edilen göreve birleştirilecek öğeleri aralığını ilk öğe konumu.  
  
 `_End`  
 Sonuçta elde edilen göreve birleştirilecek öğeleri aralık ötesinde ilk öğe konumu.  
  
 `_TaskOptions`  
  
### <a name="return-value"></a>Dönüş Değeri  
 Tüm giriş görevleri başarıyla tamamlandığında başarıyla tamamlanan bir görev. Giriş görevleri türdeyse `T`, bu işlevin çıktı bir `task<std::vector<T>>`. Giriş görevleri türdeyse `void` çıkışı da bu durumda görev bir `task<void>`.  
  
### <a name="remarks"></a>Açıklamalar  
 `when_all` üreten engelleyici olmayan bir işlev bir `task` sonuç olarak. Farklı [task::wait](task-class.md#wait), ASTA (uygulama STA) iş parçacığı üzerinde bir UWP uygulamasında bu işlevi çağırmak güvenlidir.  
  
 Görevlerden birini iptal veya bir özel durum oluşturur, döndürülen görevi erken, iptal edilmiş durumda tamamlayacak ve encoutered, ise çağırırsanız özel durum oluşturulacak [task::get](task-class.md#get) veya `task::wait` bu görevde.  
  
 Daha fazla bilgi için bkz: [görev Paralelliği](../../../parallel/concrt/task-parallelism-concurrency-runtime.md).  
  
##  <a name="when_any"></a>  when_any  
 Bağımsız değişkenler tamamladıkça başarıyla görevlerden herhangi birini ne zaman sağlanan başarıyla tamamlanır bir görev oluşturur.  
  
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
 `_Iterator`  
 Giriş yineleyici türü.  
  
 `_Begin`  
 Sonuçta elde edilen göreve birleştirilecek öğeleri aralığını ilk öğe konumu.  
  
 `_End`  
 Sonuçta elde edilen göreve birleştirilecek öğeleri aralık ötesinde ilk öğe konumu.  
  
 `_TaskOptions`  
 `_CancellationToken`  
 Döndürülen görev iptali denetimleri iptal belirteci. Bir iptal belirteci belirtmezseniz, elde edilen görevi tamamlamak için neden olan görev iptal belirtecini alır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Ne zaman giriş görevlerden biri tamamlandı başarıyla tamamlanan bir görev. Giriş görevleri türdeyse `T`, bu işlevin çıktı bir `task<std::pair<T, size_t>>>`, burada çiftinin ilk öğe tamamlayan görev sonucunu ve tamamlandı görev dizinini ikinci öğedir. Giriş görevleri türdeyse `void` çıktısı bir `task<size_t>`sonucu tamamlayan görev dizinini eder.  
  
### <a name="remarks"></a>Açıklamalar  
 `when_any` üreten engelleyici olmayan bir işlev bir `task` sonuç olarak. Farklı [task::wait](task-class.md#wait), ASTA (uygulama STA) iş parçacığı üzerinde bir UWP uygulamasında bu işlevi çağırmak güvenlidir.  
  
 Daha fazla bilgi için bkz: [görev Paralelliği](../../../parallel/concrt/task-parallelism-concurrency-runtime.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Ad Alanı](concurrency-namespace.md)
