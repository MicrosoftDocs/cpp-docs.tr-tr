---
title: task Sınıfı (Eşzamanlılık Çalışma Zamanı)
ms.date: 11/04/2016
f1_keywords:
- task
- PPLTASKS/concurrency::task
- PPLTASKS/concurrency::task::task
- PPLTASKS/concurrency::task::get
- PPLTASKS/concurrency::task::is_apartment_aware
- PPLTASKS/concurrency::task::is_done
- PPLTASKS/concurrency::task::scheduler
- PPLTASKS/concurrency::task::then
- PPLTASKS/concurrency::task::wait
helpviewer_keywords:
- task class
ms.assetid: cdc3a8c0-5cbe-45a0-b5d5-e9f81d94df1a
ms.openlocfilehash: 99676ac0fff9584cd8453562f8918f6cadd66666
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62385212"
---
# <a name="task-class-concurrency-runtime"></a>task Sınıfı (Eşzamanlılık Çalışma Zamanı)

Paralel Desen kitaplığı (PPL) `task` sınıfı. A `task` nesnesi zaman uyumsuz olarak ve diğer görevleri aynı anda yürütülebilecek ve Eşzamanlılık Çalışma zamanında paralel algoritmalar tarafından üretilen iş paralel çalışmayı temsil eder. Türünün bir sonucu üretir `_ResultType` başarıyla tamamlandığında. Görev türü `task<void>` hiç sonuç vermez. Bir görev beklenebilir ve diğer görevlerden bağımsız olarak iptal edildi. Devamlılıkları kullanarak başka görevlerle de oluşabilir ( `then`) ve birleştirme ( `when_all`) ve seçim ( `when_any`) desenleri.

## <a name="syntax"></a>Sözdizimi

```
template <typename T>
class task;

template <>
class task<void>;

template<typename _ReturnType>
class task;
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Görev nesnesi türü.

*_ReturnType*<br/>
Bu görevin sonuç türü.

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Genel Typedefler

|Ad|Açıklama|
|----------|-----------------|
|`result_type`|Sonuç türü, bu sınıfın bir nesnesi oluşturur.|

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[Görev](#ctor)|Fazla Yüklendi. Oluşturur bir `task` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[get](#get)|Fazla Yüklendi. Bu görevin ürettiği sonucu döndürür. Görev bir terminal durumunda değilse, durum, bir çağrı `get` görevin tamamlanmasını bekler. Bu yöntem bir görevde çağrıldığında bir değer döndürmeyen bir `result_type` , `void`.|
|[is_apartment_aware](#is_apartment_aware)|Görev bir Windows çalışma zamanı kaydırmayacağını belirler `IAsyncInfo` çıkarırsa veya böyle bir görevden gelen görevdir.|
|[is_done](#is_done)|Görevin tamamlanıp tamamlanmadığını belirler.|
|[scheduler](#scheduler)|Bu görev için Zamanlayıcıyı döndürür|
|[Ardından](#then)|Fazla Yüklendi. Bu göreve bir devamlılık görevi ekler.|
|[bekleme](#wait)|Bu görev bir terminal durumuna ulaşmasını bekler. Mümkündür `wait` tüm görevleri bağımlılıkları karşılanır ve bu zaten yürütme için bir arka plan çalışanı tarafından teslim alındı değil için görev satıriçi yürütülecek.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[operator!=](#operator_neq)|Fazla Yüklendi. İki olup olmadığını belirleyen `task` nesneleri farklı iç görevleri temsil eder.|
|[operator=](#operator_eq)|Fazla Yüklendi. Bir içeriğini değiştirir `task` başka bir nesne.|
|[operator==](#operator_eq_eq)|Fazla Yüklendi. İki olup olmadığını belirleyen `task` nesneleri aynı iç görevi temsil eder.|

## <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [görev Paralelliği](../../../parallel/concrt/task-parallelism-concurrency-runtime.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`task`

## <a name="requirements"></a>Gereksinimler

**Başlık:** ppltasks.h

**Namespace:** eşzamanlılık

##  <a name="get"></a> Al

Bu görevin ürettiği sonucu döndürür. Görev bir terminal durumunda değilse, durum, bir çağrı `get` görevin tamamlanmasını bekler. Bu yöntem bir görevde çağrıldığında bir değer döndürmeyen bir `result_type` , `void`.

```
_ReturnType get() const;

void get() const;
```

### <a name="return-value"></a>Dönüş Değeri

Görev sonucu.

### <a name="remarks"></a>Açıklamalar

Görev iptal edilirse bir çağrı `get` oluşturmaz bir [task_canceled](task-canceled-class.md) özel durum. Görev farklı bir özel durum karşılaştıysa veya öncül bir görevden buna özel durum yayıldığı, görev, bir çağrı `get` o özel durum oluşturur.

> [!IMPORTANT]
>  Bir evrensel Windows Platformu (UWP) uygulaması çağırmayın [CONCURRENCY::Task:: wait](#wait) veya `get` ( `wait` çağrıları `get`) kodda kullanıcı arabirimi iş parçacığında çalışır. Aksi takdirde, çalışma zamanı oluşturur [concurrency::invalid_operation](invalid-operation-class.md) çünkü bu yöntem geçerli iş parçacığını engeller ve uygulamanın yanıt veremez duruma gelmesine neden olabilir. Ancak, çağırabilirsiniz `get` sonuç hemen kullanılabilir olduğundan, bir görev tabanlı devamlılık içinde öncül görevin sonucunu almak için yöntemi.

##  <a name="is_apartment_aware"></a> is_apartment_aware

Görev bir Windows çalışma zamanı kaydırmayacağını belirler `IAsyncInfo` çıkarırsa veya böyle bir görevden gelen görevdir.

```
bool is_apartment_aware() const;
```

### <a name="return-value"></a>Dönüş Değeri

**doğru** görev indirilirse bir `IAsyncInfo` çıkarırsa veya böyle bir görevden gelen görevdir **false** Aksi takdirde.

##  <a name="is_done"></a>  Task::is_done metodu (eşzamanlılık çalışma zamanı)

Görevin tamamlanıp tamamlanmadığını belirler.

```
bool is_done() const;
```

### <a name="return-value"></a>Dönüş Değeri

Görevi tamamlandı, true, false Aksi takdirde.

### <a name="remarks"></a>Açıklamalar

Görev tamamlandıysa veya (ile veya kullanıcı özel durum olmadan) iptal edildiyse işlev true döndürür.

##  <a name="operator_neq"></a> işleç! =

İki olup olmadığını belirleyen `task` nesneleri farklı iç görevleri temsil eder.

```
bool operator!= (const task<_ReturnType>& _Rhs) const;

bool operator!= (const task<void>& _Rhs) const;
```

### <a name="parameters"></a>Parametreler

*_Rhs*<br/>
Karşılaştır görevi.

### <a name="return-value"></a>Dönüş Değeri

**doğru** nesneler farklı arka plan görevlerine başvuruyorsa ve **false** Aksi takdirde.

##  <a name="operator_eq"></a> işleç =

Bir içeriğini değiştirir `task` başka bir nesne.

```
task& operator= (const task& _Other);

task& operator= (task&& _Other);
```

### <a name="parameters"></a>Parametreler

*_Diğer*<br/>
Kaynak `task` nesne.

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

Olarak `task` bir kopya atamasından sonra bu akıllı bir işaretçi gibi davranır `task` nesnelerini aynı gerçek görevi temsil eden `_Other` yapar.

##  <a name="operator_eq_eq"></a> işleç ==

İki olup olmadığını belirleyen `task` nesneleri aynı iç görevi temsil eder.

```
bool operator== (const task<_ReturnType>& _Rhs) const;

bool operator== (const task<void>& _Rhs) const;
```

### <a name="parameters"></a>Parametreler

*_Rhs*<br/>
Karşılaştır görevi.

### <a name="return-value"></a>Dönüş Değeri

**doğru** nesneler aynı arka plan görevlerine başvuruyorsa ve **false** Aksi takdirde.

##  <a name="scheduler"></a>  Task::Scheduler metodu (eşzamanlılık çalışma zamanı)

Bu görev için Zamanlayıcıyı döndürür

```
scheduler_ptr scheduler() const;
```

### <a name="return-value"></a>Dönüş Değeri

Zamanlayıcı işaretçisi

##  <a name="ctor"></a> Görev

Oluşturur bir `task` nesne.

```
task();

template<typename T>
__declspec(
    noinline) explicit task(T _Param);

template<typename T>
__declspec(
    noinline) explicit task(T _Param, const task_options& _TaskOptions);

task(
    const task& _Other);

task(
    task&& _Other);
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Görevin kendisinden oluşturulacağı parametre türü.

*_Param*<br/>
İçinden görevin kendisinden oluşturulacağı parametre. Bu bir lambda, bir işlev nesnesi olabilir bir `task_completion_event<result_type>` nesne ya da Windows çalışma zamanı uygulamanızda görevler kullanıyorsanız bir Windows::Foundation:: ıasyncınfo. Lambda veya işlev nesnesi bir tür eşdeğeri olmalıdır `std::function<X(void)>`, burada X türünde bir değişken olabilir `result_type`, `task<result_type>`, veya Windows çalışma zamanı uygulamalarındaki bir Windows::Foundation:: ıasyncınfo.

*_TaskOptions*<br/>
Görev seçenekleri iptal belirteci, Zamanlayıcı vb. içerir.

*_Diğer*<br/>
Kaynak `task` nesne.

### <a name="remarks"></a>Açıklamalar

İçin varsayılan oluşturucu bir `task` yalnızca kapsayıcılarda kullanılacak görevlere izin vermek için bulunur. Geçerli bir görev atayıncaya kadar oluşturulmuş varsayılan görev kullanılamaz. Yöntemler gibi `get`, `wait` veya `then` oluşturmaz bir [invalid_argument](../../../standard-library/invalid-argument-class.md) bir varsayılan oluşturulmuş göreve çağrıldığında bir özel durum.

İçinden oluşturulan bir görev bir `task_completion_event` tamamlanır (ve devamlılıkları zamanlanır) görev tamamlama olayı ayarlandığında.

İptali belirteci alan oluşturucu sürümü kullanarak iptal edebilecek bir görev oluşturur `cancellation_token_source` belirtecin elde edildiği. Bir iptal belirteci olmadan oluşturulmuş görevler iptal edilebilir değildir.

Oluşturulan görevler bir `Windows::Foundation::IAsyncInfo` arabirimi veya döndüren bir lambda bir `IAsyncInfo` arabirimi, kapalı Windows çalışma zamanı zaman uyumsuz işlem veya eylem tamamlandığında terminal durumuna ulaşın. Benzer şekilde, döndüren bir lamdadan oluşturulan görevler bir `task<result_type>` iç görev terminal durumuna ulaştığında ve lamda döndürmediği zaman terminal durumuna ulaşın.

`task` Akıllı bir işaretçi gibi davranır ve değerine göre etrafından güvenlidir. Kilide gerek kalmadan birden çok iş parçacığı tarafından erişilebilir.

Bir Windows::Foundation:: ıasyncınfo arabirimi veya böyle bir arabirim döndüren bir lambda alan oluşturucu aşırı yüklemeleri yalnızca Windows çalışma zamanı uygulamaları için kullanılabilir.

Daha fazla bilgi için [görev Paralelliği](../../../parallel/concrt/task-parallelism-concurrency-runtime.md).

##  <a name="then"></a> Ardından

Bu göreve bir devamlılık görevi ekler.

```
template<typename _Function>
__declspec(
    noinline) auto then(const _Function& _Func) const -> typename details::_ContinuationTypeTraits<_Function,
    _ReturnType>::_TaskOfType;

template<typename _Function>
__declspec(
    noinline) auto then(const _Function& _Func,
    const task_options& _TaskOptions) const -> typename details::_ContinuationTypeTraits<_Function,
    _ReturnType>::_TaskOfType;

template<typename _Function>
__declspec(
    noinline) auto then(const _Function& _Func,
    cancellation_token _CancellationToken,
    task_continuation_context _ContinuationContext) const -> typename details::_ContinuationTypeTraits<_Function,
    _ReturnType>::_TaskOfType;

template<typename _Function>
__declspec(
    noinline) auto then(const _Function& _Func,
    const task_options& _TaskOptions = task_options()) const -> typename details::_ContinuationTypeTraits<_Function,
    void>::_TaskOfType;

template<typename _Function>
__declspec(
    noinline) auto then(const _Function& _Func,
    cancellation_token _CancellationToken,
    task_continuation_context _ContinuationContext) const -> typename details::_ContinuationTypeTraits<_Function,
    void>::_TaskOfType;
```

### <a name="parameters"></a>Parametreler

*_Function*<br/>
Bu görev tarafından çağrılacak işlev nesnesinin türü.

*_Func*<br/>
Bu görev tamamlandığında yürütülecek devam işlevi. Bu devamlılık işlevi olarak almalıdır değişkenini giriş `result_type` veya `task<result_type>`burada `result_type` bu görevin ürettiği sonuç türüdür.

*_TaskOptions*<br/>
Görev seçenekleri iptal belirteci, Zamanlayıcı ve devam bağlamını içerir. Varsayılan olarak önceki 3 seçenek öncül görevden devralınır.

*_CancellationToken*<br/>
Devam göreviyle ilişkilendirilecek iptal belirteci. Bir iptal belirteci olmadan oluşturulan bir devamlılık görevi, öncül görevinin belirtecini devralır.

*_ContinuationContext*<br/>
Devamlılığın nerede yürütülmesi belirten bir değişken. Bu değişken, yalnızca bir UWP uygulamasında kullanıldığında yararlıdır. Daha fazla bilgi için [task_continuation_context](task-continuation-context-class.md)

### <a name="return-value"></a>Dönüş Değeri

Yeni oluşturulan devam görevi. Döndürülen görevin sonuç türü ne tarafından belirlenir `_Func` döndürür.

### <a name="remarks"></a>Açıklamalar

Aşırı Yüklemeleri `then` bir lambda veya bir Windows::Foundation:: ıasyncınfo arabirimi döndüren bir functor, yalnızca Windows çalışma zamanı uygulamaları için kullanılabilir.

Zaman uyumsuz çalışma oluşturmak için görev devamlılıklarının kullanma hakkında daha fazla bilgi için bkz. [görev Paralelliği](../../../parallel/concrt/task-parallelism-concurrency-runtime.md).

##  <a name="wait"></a> bekleme

Bu görev bir terminal durumuna ulaşmasını bekler. Mümkündür `wait` tüm görevleri bağımlılıkları karşılanır ve bu zaten yürütme için bir arka plan çalışanı tarafından teslim alındı değil için görev satıriçi yürütülecek.

```
task_status wait() const;
```

### <a name="return-value"></a>Dönüş Değeri

A `task_status` olabilecek değeri `completed` veya `canceled`. Görev yürütme sırasında bir özel durumla karşılaştı veya öncül bir görevden buna özel durum yayıldığı `wait` o özel durum oluşturur.

### <a name="remarks"></a>Açıklamalar

> [!IMPORTANT]
>  Bir evrensel Windows Platformu (UWP) uygulaması çağırmayın `wait` kodda kullanıcı arabirimi iş parçacığında çalışır. Aksi takdirde, çalışma zamanı oluşturur [concurrency::invalid_operation](invalid-operation-class.md) çünkü bu yöntem geçerli iş parçacığını engeller ve uygulamanın yanıt veremez duruma gelmesine neden olabilir. Ancak, çağırabilirsiniz [CONCURRENCY::Task:: get](#get) görev tabanlı devamlılık içinde öncül görevin sonucunu almak için yöntemi.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)
