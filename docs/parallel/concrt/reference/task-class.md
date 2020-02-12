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
ms.openlocfilehash: 3657dc54584b120304ccda13ed93b5a0e37bb4af
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77142624"
---
# <a name="task-class-concurrency-runtime"></a>task Sınıfı (Eşzamanlılık Çalışma Zamanı)

Paralel Desenler kitaplığı (PPL) `task` sınıfı. `task` nesnesi, Eşzamanlılık Çalışma Zamanı paralel algoritmalarla oluşturulan diğer görevlerle ve paralel çalışmalarla zaman uyumsuz ve aynı anda yürütülebilecek işi temsil eder. Başarıyla tamamlandığında `_ResultType` türünde bir sonuç üretir. `task<void>` görevler sonuç oluşturmaz. Bir görev, diğer görevlerden bağımsız olarak bekleve iptal edilebilir. Ayrıca, devamlılık (`then`) ve birleştirme (`when_all`) ve seçim (`when_any`) desenlerini kullanan diğer görevlerle de birleştirilebilir. Bir görev nesnesi yeni bir değişkene atandığında, davranış `std::shared_ptr`; diğer bir deyişle, her iki nesne de aynı temel görevi temsil eder.

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

### <a name="public-typedefs"></a>Ortak tür tanımları

|Ad|Açıklama|
|----------|-----------------|
|`result_type`|Bu sınıfın bir nesnesinin oluşturduğu sonucun türü.|

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[görevinin](#ctor)|Fazla Yüklendi. `task` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[get](#get)|Fazla Yüklendi. Bu görevin ürettiği sonucu döndürür. Görev bir terminal durumunda değilse, `get` çağrısı görevin bitmesini bekler. Bu yöntem, `void``result_type` bir görevde çağrıldığında bir değer döndürmez.|
|[is_apartment_aware](#is_apartment_aware)|Görevin Windows Çalışma Zamanı `IAsyncInfo` arabirimini kaydırıp sarmadığını ya da bu türden bir görevden mi ait olduğunu belirler.|
|[is_done](#is_done)|Görevin tamamlanıp tamamlanmadığını belirler.|
|[leyiciyi](#scheduler)|Bu görev için zamanlayıcıyı döndürür|
|[ni](#then)|Fazla Yüklendi. Bu göreve bir devamlılık görevi ekler.|
|[bekleneceğini](#wait)|Bu görevin Terminal durumuna ulaşmasını bekler. Tüm görev bağımlılıkları karşılanmışsa ve bir arka plan çalışanı tarafından yürütülmek üzere henüz çekilmediğinde, görevin satır içi olarak yürütülmesi `wait` mümkündür.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[operator!=](#operator_neq)|Fazla Yüklendi. İki `task` nesnesinin farklı iç görevleri temsil ettiğini belirtir.|
|[işleç =](#operator_eq)|Fazla Yüklendi. Bir `task` nesnesinin içeriğini başkalarıyla değiştirir.|
|[işleç = =](#operator_eq_eq)|Fazla Yüklendi. İki `task` nesnesinin aynı dahili görevi temsil ettiğini belirtir.|

## <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [Görev Paralelliği](../../../parallel/concrt/task-parallelism-concurrency-runtime.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`task`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** ppltasks. h

**Ad alanı:** eşzamanlılık

## <a name="get"></a>Al

Bu görevin ürettiği sonucu döndürür. Görev bir terminal durumunda değilse, `get` çağrısı görevin bitmesini bekler. Bu yöntem, `void``result_type` bir görevde çağrıldığında bir değer döndürmez.

```cpp
_ResultType get() const;

void get() const;
```

### <a name="return-value"></a>Dönüş Değeri

Görevin sonucu.

### <a name="remarks"></a>Açıklamalar

Görev iptal edilirse, `get` çağrısı bir [task_canceled](task-canceled-class.md) özel durumu oluşturur. Görev farklı bir özel durumla karşılaştıysa veya bir öncül görevden buna bir özel durum yayıldıysa, `get` çağrısı bu özel durumu oluşturur.

> [!IMPORTANT]
> Evrensel Windows Platformu (UWP) uygulamasında, Kullanıcı arabirimi iş parçacığında çalışan kodda [concurrency:: task:: wait](#wait) veya `get` (`wait` çağrıları `get`) çağırmayın. Aksi takdirde, çalışma zamanı [eşzamanlılık:: invalid_operation](invalid-operation-class.md) atar çünkü bu yöntemler geçerli iş parçacığını engeller ve uygulamanın yanıt vermemesine neden olabilir. Ancak, sonuç hemen kullanılabilir olduğundan, öncül görevin sonucunu görev tabanlı devamlıya almak için `get` yöntemini çağırabilirsiniz.

## <a name="is_apartment_aware"></a>is_apartment_aware

Görevin Windows Çalışma Zamanı `IAsyncInfo` arabirimini kaydırıp sarmadığını ya da bu türden bir görevden mi ait olduğunu belirler.

```cpp
bool is_apartment_aware() const;
```

### <a name="return-value"></a>Dönüş Değeri

görev bir `IAsyncInfo` arabirimini saralmamışsa veya bu tür bir görevden bir alt çıkıntıdaysa **true** , aksi takdirde **false** .

## <a name="is_done"></a>Task:: is_done yöntemi (Eşzamanlılık Çalışma Zamanı)

Görevin tamamlanıp tamamlanmadığını belirler.

```cpp
bool is_done() const;
```

### <a name="return-value"></a>Dönüş Değeri

Görev tamamlanırsa true, aksi takdirde false.

### <a name="remarks"></a>Açıklamalar

Görev tamamlandığında veya iptal edildiğinde (Kullanıcı özel durumuyla veya olmadan), işlev true değerini döndürür.

## <a name="operator_neq"></a>işleç! =

İki `task` nesnesinin farklı iç görevleri temsil ettiğini belirtir.

```cpp
bool operator!= (const task<_ResultType>& _Rhs) const;

bool operator!= (const task<void>& _Rhs) const;
```

### <a name="parameters"></a>Parametreler

*_Rhs*<br/>
Karşılaştırılacak görev.

### <a name="return-value"></a>Dönüş Değeri

nesneler farklı temel görevlere başvuracaksa **true** , aksi takdirde **false** .

## <a name="operator_eq"></a>işleç =

Bir `task` nesnesinin içeriğini başkalarıyla değiştirir.

```cpp
task& operator= (const task& _Other);

task& operator= (task&& _Other);
```

### <a name="parameters"></a>Parametreler

*_Other*<br/>
Kaynak `task` nesnesi.

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

`task`, bir akıllı işaretçi gibi davrandıktan sonra, bir kopyalama atamasından sonra, bu `task` nesneler `_Other` tarafından aynı gerçek görevi temsil eder.

## <a name="operator_eq_eq"></a>işleç = =

İki `task` nesnesinin aynı dahili görevi temsil ettiğini belirtir.

```cpp
bool operator== (const task<_ResultType>& _Rhs) const;

bool operator== (const task<void>& _Rhs) const;
```

### <a name="parameters"></a>Parametreler

*_Rhs*<br/>
Karşılaştırılacak görev.

### <a name="return-value"></a>Dönüş Değeri

nesneler aynı temel göreve başvuracaksa **true** , aksi takdirde **false** .

## <a name="scheduler"></a>Task:: Scheduler yöntemi (Eşzamanlılık Çalışma Zamanı)

Bu görev için zamanlayıcıyı döndürür

```cpp
scheduler_ptr scheduler() const;
```

### <a name="return-value"></a>Dönüş Değeri

Zamanlayıcı işaretçisi

## <a name="ctor"></a>görevinin

`task` nesnesi oluşturur.

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

*Şı*<br/>
Görevin oluşturulması gereken parametrenin türü.

*_Param*<br/>
Görevin oluşturulması gereken parametre. Windows Çalışma Zamanı uygulamanızda görevler kullanıyorsanız, bu bir lambda, bir işlev nesnesi, `task_completion_event<result_type>` nesnesi veya bir Windows:: Foundation:: IAsyncInfo olabilir. Lambda veya işlev nesnesi `std::function<X(void)>`eşdeğer bir tür olmalıdır; burada X, Windows Çalışma Zamanı uygulamalarında `result_type`, `task<result_type>`veya bir Windows:: Foundation:: IAsyncInfo türünde bir değişken olabilir.

*_TaskOptions*<br/>
Görev seçenekleri iptal belirteci, Zamanlayıcı vb. içerir

*_Other*<br/>
Kaynak `task` nesnesi.

### <a name="remarks"></a>Açıklamalar

Bir `task` için varsayılan Oluşturucu yalnızca kapsayıcılar içinde görevlerin kullanılmasına izin vermek için vardır. Varsayılan olarak oluşturulmuş bir görev, kendisine geçerli bir görev atamaz kadar kullanılamaz. `get`, `wait` veya `then` gibi yöntemler, varsayılan olarak oluşturulmuş bir görevde çağrıldığında bir [invalid_argument](../../../standard-library/invalid-argument-class.md) özel durumu oluşturur.

Bir `task_completion_event` oluşturulan bir görev, görev tamamlanma olayı ayarlandığında tamamlanır (ve devamlılıkları olarak zamanlanır).

İptal belirteci alan oluşturucunun sürümü, belirtecin alındığı `cancellation_token_source` kullanılarak iptal edilebilir bir görev oluşturur. İptal belirteci olmadan oluşturulan görevler iptal edilemez.

Bir `Windows::Foundation::IAsyncInfo` arabiriminden oluşturulan veya bir `IAsyncInfo` arabirimini döndüren bir lambda, eklenen Windows Çalışma Zamanı zaman uyumsuz işlem veya Eylem tamamlandığında Terminal durumlarına ulaşacak olan görevlerdir. Benzer şekilde, bir lambda tarafından oluşturulan görevler, iç görev kendi Terminal durumuna ulaştığında bir `task<result_type>` döndürür ve lambda döndürüldüğünde değil, Terminal durumlarına ulaşın.

`task`, akıllı bir işaretçi gibi davranır ve değere göre geçiş yapmak için güvenlidir. Kilitlere gerek olmadan birden çok iş parçacığı tarafından erişilebilir.

Windows:: Foundation:: IAsyncInfo arabirimini alan Oluşturucu aşırı yüklemeleri veya böyle bir arabirim döndüren bir lambda yalnızca Windows Çalışma Zamanı uygulamalar tarafından kullanılabilir.

Daha fazla bilgi için bkz. [Görev Paralelliği](../../../parallel/concrt/task-parallelism-concurrency-runtime.md).

## <a name="then"></a>ni

Bu göreve bir devamlılık görevi ekler.

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
Bu görev tamamlandığında yürütülecek devamlılık işlevi. Bu devamlılık işlevi, `result_type` veya `task<result_type>`bir değişken olarak almalıdır; burada `result_type`, bu görevin ürettiği sonucun türüdür.

*_TaskOptions*<br/>
Görev seçenekleri iptal belirteci, Zamanlayıcı ve devamlılık bağlamını içerir. Varsayılan olarak, önceki 3 seçenek öncül görevden devralınır

*_CancellationToken*<br/>
Devamlılık göreviyle ilişkilendirilecek iptal belirteci. İptal belirteci olmadan oluşturulan bir devamlılık görevi, öncül görevinin belirtecini miras alacak.

*_ContinuationContext*<br/>
Devamlılığın nerede yürütüleceğini belirten bir değişken. Bu değişken yalnızca UWP uygulamasında kullanıldığında yararlıdır. Daha fazla bilgi için bkz. [task_continuation_context](task-continuation-context-class.md)

### <a name="return-value"></a>Dönüş Değeri

Yeni oluşturulan devamlılık görevi. Döndürülen görevin sonuç türü `_Func` tarafından belirlenir.

### <a name="remarks"></a>Açıklamalar

Bir Windows:: Foundation:: IAsyncInfo arabirimini döndüren bir lambda veya functor alan `then` aşırı yüklemeleri yalnızca Windows Çalışma Zamanı uygulamalar tarafından kullanılabilir.

Zaman uyumsuz iş oluşturmak için görev devamlılıklarını kullanma hakkında daha fazla bilgi için bkz. [Görev Paralelliği](../../../parallel/concrt/task-parallelism-concurrency-runtime.md).

## <a name="wait"></a>bekleneceğini

Bu görevin Terminal durumuna ulaşmasını bekler. Tüm görev bağımlılıkları karşılanmışsa ve bir arka plan çalışanı tarafından yürütülmek üzere henüz çekilmediğinde, görevin satır içi olarak yürütülmesi `wait` mümkündür.

```cpp
task_status wait() const;
```

### <a name="return-value"></a>Dönüş Değeri

`completed` veya `canceled`olabilen bir `task_status` değeri. Görev yürütme sırasında bir özel durumla karşılaşılırsa veya bir öncül görevden buna bir özel durum yayıldıysa, `wait` bu özel durumu oluşturur.

### <a name="remarks"></a>Açıklamalar

> [!IMPORTANT]
> Evrensel Windows Platformu (UWP) uygulamasında, Kullanıcı arabirimi iş parçacığında çalışan koddaki `wait` çağırmayın. Aksi takdirde, çalışma zamanı [eşzamanlılık:: invalid_operation](invalid-operation-class.md) oluşturur, çünkü bu yöntem geçerli iş parçacığını engeller ve uygulamanın yanıt vermemesine neden olabilir. Ancak, görev tabanlı devamlılık içinde öncül görevin sonucunu almak için [concurrency:: task:: Get](#get) yöntemini çağırabilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)
