---
title: task Sınıfı (Eşzamanlılık Çalışma Zamanı)
ms.date: 07/30/2019
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
ms.openlocfilehash: d42c7fbd3e065fc295027b7c56e207b2a49221bb
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81358729"
---
# <a name="task-class-concurrency-runtime"></a>task Sınıfı (Eşzamanlılık Çalışma Zamanı)

Paralel Desenler Kitaplığı (PPL) `task` sınıfı. Nesne, `task` Eşzamanlılık Çalışma Süresi'nde paralel algoritmalar tarafından üretilen diğer görevlerle ve paralel çalışmayla eş zamanlı ve eş zamanlı olarak yürütülebilen çalışmayı temsil eder. Başarılı bir şekilde `_ResultType` tamamlanması nda bir tür sonucu üretir. Tür `task<void>` görevleri sonuç üretmez. Bir görev, diğer görevlerden bağımsız olarak beklenebilir ve iptal edilebilir. Devamı ve birleştirme `then` `when_all`ve seçim `when_any`kalıpları kullanılarak diğer görevlerle de oluşturulabilir. Bir görev nesnesi yeni bir değişkene atandığında, `std::shared_ptr`davranış; başka bir deyişle, her iki nesne de aynı temel görevi temsil eder.

## <a name="syntax"></a>Sözdizimi

```cpp
template <>
class task<void>;

template<typename _ResultType>
class task;
```

### <a name="parameters"></a>Parametreler

*_ResultType*<br/>
Görevin ürettiği sonucun türü.

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Genel Typedefs

|Adı|Açıklama|
|----------|-----------------|
|`result_type`|Bu sınıfın bir nesnesinin ürettiği sonucun türü.|

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[Görev](#ctor)|Fazla Yüklendi. Bir `task` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[get](#get)|Fazla Yüklendi. Bu görevin ürettiği sonucu verir. Görev bir terminal durumunda değilse, görevin `get` tamamlanmasını bekleyen bir çağrı. Bu yöntem, bir görev de çağrıldığında `result_type` `void`bir değer döndürmez .|
|[is_apartment_aware](#is_apartment_aware)|Görevin bir Windows Runtime `IAsyncInfo` arabiriminin paketlerini açıp açmadığını veya böyle bir görevin soyundan gelip gelmediğini belirler.|
|[is_done](#is_done)|Görevin tamamlanıp tamamlanmayayaçıklandığını belirler.|
|[Zamanlayıcı](#scheduler)|Bu görev için zamanlayıcıyı döndürür|
|[Sonra](#then)|Fazla Yüklendi. Bu göreve bir devam görevi ekler.|
|[Bekle](#wait)|Bu görevin bir terminal durumuna ulaşmasını bekler. Tüm görevler `wait` inline yürütmek mümkündür, tüm görevler bağımlılıkları memnun ise ve zaten bir arka plan çalışanı tarafından yürütülmesi için alınmış değil.|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[işleç!=](#operator_neq)|Fazla Yüklendi. İki nesnenin `task` farklı iç görevleri temsil edip etmediğini belirler.|
|[işleç=](#operator_eq)|Fazla Yüklendi. Bir nesnenin içeriğini `task` başka bir nesneyle değiştirir.|
|[işleç==](#operator_eq_eq)|Fazla Yüklendi. İki `task` nesnenin aynı iç görevi temsil edip etmediğini belirler.|

## <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [Görev Paralelliği'ne](../../../parallel/concrt/task-parallelism-concurrency-runtime.md)bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`task`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** ppltasks.h

**Ad alanı:** eşzamanlılık

## <a name="get"></a><a name="get"></a>Al

Bu görevin ürettiği sonucu verir. Görev bir terminal durumunda değilse, görevin `get` tamamlanmasını bekleyen bir çağrı. Bu yöntem, bir görev de çağrıldığında `result_type` `void`bir değer döndürmez .

```cpp
_ResultType get() const;

void get() const;
```

### <a name="return-value"></a>Dönüş Değeri

Görevin sonucu.

### <a name="remarks"></a>Açıklamalar

Görev iptal edilirse, bir arama `get` [task_canceled](task-canceled-class.md) özel durum oluşturur. Görev farklı bir özel durumla karşılaşmışsa veya bir özel durum öncül bir `get` görevden ona yayılmışsa, bu özel durum atan bir çağrı yapılır.

> [!IMPORTANT]
> Evrensel Windows Platformu (UWP) uygulamasında, [eşzamanlılık::task::wait](#wait) `get` veya `wait` `get`( aramalar) kullanıcı arabirimi iş parçacığı üzerinde çalışan kodda aramayın. Aksi takdirde, çalışma zamanı [eşzamanlılık atar::invalid_operation,](invalid-operation-class.md) çünkü bu yöntemler geçerli iş parçacığı nı engeller ve uygulamanın yanıt vermemeye neden olabilir. Ancak, sonuç hemen `get` kullanılabilir olduğundan, görev tabanlı bir devamta öncül görevin sonucunu almak için yöntemi arayabilirsiniz.

## <a name="is_apartment_aware"></a><a name="is_apartment_aware"></a>is_apartment_aware

Görevin bir Windows Runtime `IAsyncInfo` arabiriminin paketlerini açıp açmadığını veya böyle bir görevin soyundan gelip gelmediğini belirler.

```cpp
bool is_apartment_aware() const;
```

### <a name="return-value"></a>Dönüş Değeri

**görev** bir `IAsyncInfo` arabirimi açarsa veya böyle bir görevin soyundan geliyorsa, **false** yanlış olur.

## <a name="taskis_done-method-concurrency-runtime"></a><a name="is_done"></a>görev::is_done Yöntemi (Eşzamanlı Çalışma Süresi)

Görevin tamamlanıp tamamlanmayayaçıklandığını belirler.

```cpp
bool is_done() const;
```

### <a name="return-value"></a>Dönüş Değeri

Görev tamamlanırsa doğru, aksi takdirde yanlış.

### <a name="remarks"></a>Açıklamalar

Görev tamamlanırsa veya iptal edilirse (kullanıcı istisnası olmadan veya olmasın) işlev doğru döndürür.

## <a name="operator"></a><a name="operator_neq"></a>işleç!=

İki nesnenin `task` farklı iç görevleri temsil edip etmediğini belirler.

```cpp
bool operator!= (const task<_ResultType>& _Rhs) const;

bool operator!= (const task<void>& _Rhs) const;
```

### <a name="parameters"></a>Parametreler

*_Rhs*<br/>
Karşılaştırılacak görev.

### <a name="return-value"></a>Dönüş Değeri

nesneler farklı temel görevlere başvuruyorsa **doğru** ve aksi takdirde **yanlış.**

## <a name="operator"></a><a name="operator_eq"></a>işleç=

Bir nesnenin içeriğini `task` başka bir nesneyle değiştirir.

```cpp
task& operator= (const task& _Other);

task& operator= (task&& _Other);
```

### <a name="parameters"></a>Parametreler

*_Other*<br/>
Kaynak `task` nesne.

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

Akıllı `task` işaretçi gibi davranışlarda olduğu gibi, `task` kopya atamadan sonra bu `_Other` nesneler, aynı fiili görevi temsil eder.

## <a name="operator"></a><a name="operator_eq_eq"></a>işleç==

İki `task` nesnenin aynı iç görevi temsil edip etmediğini belirler.

```cpp
bool operator== (const task<_ResultType>& _Rhs) const;

bool operator== (const task<void>& _Rhs) const;
```

### <a name="parameters"></a>Parametreler

*_Rhs*<br/>
Karşılaştırılacak görev.

### <a name="return-value"></a>Dönüş Değeri

nesneler aynı temel görevi ifade ediyorsa **doğru** ve aksi takdirde **yanlış.**

## <a name="taskscheduler-method-concurrency-runtime"></a><a name="scheduler"></a>görev::zamanlayıcı Yöntemi (Eşzamanlı Çalışma Süresi)

Bu görev için zamanlayıcıyı döndürür

```cpp
scheduler_ptr scheduler() const;
```

### <a name="return-value"></a>Dönüş Değeri

Zamanlayıcıya bir işaretçi

## <a name="task"></a><a name="ctor"></a>Görev

Bir `task` nesne inşa eder.

```cpp
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
Görevin oluşturulacak parametre türü.

*_Param*<br/>
Görevin oluşturulacak parametresi. Bu bir lambda, bir işlev `task_completion_event<result_type>` nesnesi, bir nesne veya windows olabilir::Temel::Windows Runtime uygulamanızdaki görevleri kullanıyorsanız IAsyncInfo. Lambda veya işlev `std::function<X(void)>`nesnesi, X'in bir tür `result_type`değişkeni `task<result_type>`olabileceği , veya Windows::Foundation::IAsyncInfo'nun Windows Runtime uygulamalarında eşdeğer olması gerekir.

*_TaskOptions*<br/>
Görev seçenekleri iptal jetonu, zamanlayıcı vb içerir

*_Other*<br/>
Kaynak `task` nesne.

### <a name="remarks"></a>Açıklamalar

A `task` için varsayılan oluşturucu yalnızca görevlerin kapsayıcılar içinde kullanılmasına izin vermek için kullanılabilir. Varsayılan olarak oluşturulmuş bir görev, siz ona geçerli bir görev atayana kadar kullanılamaz. Varsayılan olarak `get` `wait` oluşturulmuş `then` [bir](../../../standard-library/invalid-argument-class.md) göreve çağrıldığında invalid_argument bir özel durum oluşturur veya bu tür yöntemler.

Görev tamamlama olayı ayarlandığında, bir `task_completion_event` görev tamamlandı (ve devamı zamanlandırılır) oluşturuldu.

İptal belirteci alan oluşturucu sürümü, elde edilen belirteç kullanılarak `cancellation_token_source` iptal edilebilen bir görev oluşturur. İptal belirteci olmadan oluşturulan görevler iptal edilemez.

Arabirimden `Windows::Foundation::IAsyncInfo` veya bir lambda'dan `IAsyncInfo` oluşturulan görevler, ekteki Windows Runtime asynchronous işlemi veya eylemi tamamlandığında, bir arabirim interminal durumuna ulaşır. Benzer şekilde, iç görev, lambda `task<result_type>` döndüğünde değil, terminal durumuna ulaştığında, terminal durumuna ulaştığında bir erişim durumu döndüren bir lambda oluşturulan görevler.

`task`akıllı bir işaretçi gibi hareket eder ve değer e göre etrafında geçmek için güvenlidir. Kilitlere gerek kalmadan birden çok iş parçacığı tarafından erişilebilir.

Windows::Foundation::IAsyncInfo arabirimi veya böyle bir arabirimi döndüren bir lambda alan oluşturucu aşırı yükler yalnızca Windows Runtime uygulamaları için kullanılabilir.

Daha fazla bilgi için [Görev Paralelliği'ne](../../../parallel/concrt/task-parallelism-concurrency-runtime.md)bakın.

## <a name="then"></a><a name="then"></a>Sonra

Bu göreve bir devam görevi ekler.

```cpp
template<typename _Function>
__declspec(
    noinline) auto then(const _Function& _Func) const -> typename details::_ContinuationTypeTraits<_Function,
    _ResultType>::_TaskOfType;

template<typename _Function>
__declspec(
    noinline) auto then(const _Function& _Func,
    const task_options& _TaskOptions) const -> typename details::_ContinuationTypeTraits<_Function,
    _ResultType>::_TaskOfType;

template<typename _Function>
__declspec(
    noinline) auto then(const _Function& _Func,
    cancellation_token _CancellationToken,
    task_continuation_context _ContinuationContext) const -> typename details::_ContinuationTypeTraits<_Function,
    _ResultType>::_TaskOfType;

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
Bu görev tamamlandığında yürütülecek devam işlevi. Bu devam işlevi, bu görevin `result_type` ürettiği `task<result_type>`sonucun `result_type` türü olan veya bu değişkenin bir değişkenini girdi olarak almalıdır.

*_TaskOptions*<br/>
Görev seçenekleri iptal belirteci, zamanlayıcı ve devam bağlamını içerir. Varsayılan olarak eski 3 seçenek öncül görevden devralınır

*_CancellationToken*<br/>
Devam göreviyle ilişkilendirmek için iptal belirteci. İptal belirteci olmadan oluşturulan bir devam görevi, öncül görevinin belirteci devralır.

*_ContinuationContext*<br/>
Devamı yürütmek gerektiğini belirten bir değişken. Bu değişken yalnızca bir UWP uygulamasında kullanıldığında kullanışlıdır. Daha fazla bilgi için [task_continuation_context](task-continuation-context-class.md)

### <a name="return-value"></a>Dönüş Değeri

Yeni oluşturulan devam görevi. Döndürülen görevin sonuç türü, `_Func` hangi döndürür tarafından belirlenir.

### <a name="remarks"></a>Açıklamalar

Windows::Foundation::IAsyncInfo arabirimi döndüren bir lambda veya functor almak aşırı yükleri, `then` yalnızca Windows Runtime uygulamaları için kullanılabilir.

Eşkenar dört bir çalışma oluşturmak için görev devamlarının nasıl kullanılacağı hakkında daha fazla bilgi için Görev [Paralelliği'ne](../../../parallel/concrt/task-parallelism-concurrency-runtime.md)bakın.

## <a name="wait"></a><a name="wait"></a>Bekle

Bu görevin bir terminal durumuna ulaşmasını bekler. Tüm görevler `wait` inline yürütmek mümkündür, tüm görevler bağımlılıkları memnun ise ve zaten bir arka plan çalışanı tarafından yürütülmesi için alınmış değil.

```cpp
task_status wait() const;
```

### <a name="return-value"></a>Dönüş Değeri

Ya `task_status` da `completed` `canceled`olabilir bir değer . Yürütme sırasında bir özel durumla karşılaşılırsa veya bir özel durum öncül bir görevden ona yayılırsa, `wait` bu özel durum ortaya çıkar.

### <a name="remarks"></a>Açıklamalar

> [!IMPORTANT]
> Evrensel Windows Platformu (UWP) uygulamasında, `wait` kullanıcı arabirimi iş parçacığı üzerinde çalışan kodu çağırmayın. Aksi takdirde, çalışma zamanı [eşzamanlılık atar::invalid_operation](invalid-operation-class.md) çünkü bu yöntem geçerli iş parçacığı engeller ve uygulamanın yanıt vermiyor olmasına neden olabilir. Ancak, [eşzamanlılık çağırabilirsiniz::görev::görev](#get) tabanlı bir devamı nda öncül görevin sonucunu almak için yöntem almak.

## <a name="see-also"></a>Ayrıca bkz.

[concurrency Ad Alanı](concurrency-namespace.md)
