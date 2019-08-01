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
ms.openlocfilehash: e0f876b3c0971e70763f36622fb72a3dea671461
ms.sourcegitcommit: 725e86dabe2901175ecc63261c3bf05802dddff4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/31/2019
ms.locfileid: "68682526"
---
# <a name="task-class-concurrency-runtime"></a>task Sınıfı (Eşzamanlılık Çalışma Zamanı)

Paralel Desenler kitaplığı (ppl) `task` sınıfı. Bir `task` nesnesi, eşzamanlılık çalışma zamanı zaman uyumsuz olarak yürütülebilen ve diğer görevlerle eşzamanlı olarak yürütülebilecek çalışmayı ve paralel algoritmalar tarafından üretilen paralel çalışmayı temsil eder. Başarıyla tamamlanmasıyla `_ResultType` ilgili bir sonuç üretir. Tür `task<void>` görevleri sonuç üretmez. Bir görev, diğer görevlerden bağımsız olarak bekleve iptal edilebilir. Ayrıca, devamlılıklar ( `then`) ve JOIN ( `when_all`) ve Choice `when_any`() desenleri kullanılarak diğer görevlerle da oluşturulabilir. Bir görev nesnesi yeni bir değişkene atandığında, davranışı ' dır `std::shared_ptr`; diğer bir deyişle, her iki nesne de aynı temel görevi temsil eder.

## <a name="syntax"></a>Sözdizimi

```
template <>
class task<void>;

template<typename _ResultType>
class task;
```

#### <a name="parameters"></a>Parametreler

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
|[görevinin](#ctor)|Fazla Yüklendi. Bir `task` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[get](#get)|Fazla Yüklendi. Bu görevin ürettiği sonucu döndürür. Görev bir terminal durumunda değilse, için `get` bir çağrısı görevin bitmesini bekler. Bu yöntem `result_type` , `void`içeren bir görevde çağrıldığında bir değer döndürmez.|
|[is_apartment_aware](#is_apartment_aware)|Görevin bir Windows çalışma zamanı `IAsyncInfo` arabirimini kaydırıp sarmadığını ya da bu türden bir görevden mi ait olduğunu belirler.|
|[is_done](#is_done)|Görevin tamamlanıp tamamlanmadığını belirler.|
|[scheduler](#scheduler)|Bu görev için zamanlayıcıyı döndürür|
|[ni](#then)|Fazla Yüklendi. Bu göreve bir devamlılık görevi ekler.|
|[bekleneceğini](#wait)|Bu görevin Terminal durumuna ulaşmasını bekler. Tüm görev bağımlılıkları karşılanmışsa ve bir arka plan çalışanı tarafından yürütülmek üzere henüz çekilmediğinde, görevin satır içi yürütülmesi mümkündür `wait` .|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[operator!=](#operator_neq)|Fazla Yüklendi. İki `task` nesnenin farklı iç görevleri temsil ettiğini belirler.|
|[operator=](#operator_eq)|Fazla Yüklendi. Bir `task` nesnenin içeriğini başka bir nesneyle değiştirir.|
|[operator==](#operator_eq_eq)|Fazla Yüklendi. İki `task` nesnenin aynı dahili görevi temsil ettiğini belirtir.|

## <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [Görev Paralelliği](../../../parallel/concrt/task-parallelism-concurrency-runtime.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`task`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** ppltasks. h

**Ad alanı:** eşzamanlılık

##  <a name="get"></a>Al

Bu görevin ürettiği sonucu döndürür. Görev bir terminal durumunda değilse, için `get` bir çağrısı görevin bitmesini bekler. Bu yöntem `result_type` , `void`içeren bir görevde çağrıldığında bir değer döndürmez.

```
_ResultType get() const;

void get() const;
```

### <a name="return-value"></a>Dönüş Değeri

Görevin sonucu.

### <a name="remarks"></a>Açıklamalar

Görev iptal edilirse, öğesine `get` yapılan bir çağrı, bir [task_canceled](task-canceled-class.md) özel durumu oluşturur. Görev farklı bir özel durumla karşılaşılırsa veya bir öncül görevden buna bir özel durum yayıldıysa, öğesine `get` yapılan bir çağrı o özel durumu oluşturur.

> [!IMPORTANT]
>  Evrensel Windows platformu (UWP) uygulamasında, Kullanıcı arabirimi iş parçacığında çalışan kodda [concurrency:: task:: wait](#wait) `get` veya `wait` ( `get`çağrılar) çağırmayın. Aksi takdirde, çalışma zamanı [eşzamanlılık:: invalid_operation](invalid-operation-class.md) atar çünkü bu yöntemler geçerli iş parçacığını engeller ve uygulamanın yanıt vermemesine neden olabilir. Ancak, sonuç hemen kullanılabilir olduğundan `get` , öncül görevin sonucunu görev tabanlı devamlıya almak için yöntemini çağırabilirsiniz.

##  <a name="is_apartment_aware"></a> is_apartment_aware

Görevin bir Windows çalışma zamanı `IAsyncInfo` arabirimini kaydırıp sarmadığını ya da bu türden bir görevden mi ait olduğunu belirler.

```
bool is_apartment_aware() const;
```

### <a name="return-value"></a>Dönüş Değeri

görev bir `IAsyncInfo` arabirimi sarıp sarmamışsa ya da bu türden bir görevden diğerine eşitse true, aksi durumda **false** .

##  <a name="is_done"></a>Task:: is_done yöntemi (Eşzamanlılık Çalışma Zamanı)

Görevin tamamlanıp tamamlanmadığını belirler.

```
bool is_done() const;
```

### <a name="return-value"></a>Dönüş Değeri

Görev tamamlanırsa true, aksi takdirde false.

### <a name="remarks"></a>Açıklamalar

Görev tamamlandığında veya iptal edildiğinde (Kullanıcı özel durumuyla veya olmadan), işlev true değerini döndürür.

##  <a name="operator_neq"></a>işleç! =

İki `task` nesnenin farklı iç görevleri temsil ettiğini belirler.

```
bool operator!= (const task<_ResultType>& _Rhs) const;

bool operator!= (const task<void>& _Rhs) const;
```

### <a name="parameters"></a>Parametreler

*_Rhs*<br/>
Karşılaştırılacak görev.

### <a name="return-value"></a>Dönüş Değeri

nesneler farklı temel görevlere başvuracaksa **true** , aksi takdirde **false** .

##  <a name="operator_eq"></a>işleç =

Bir `task` nesnenin içeriğini başka bir nesneyle değiştirir.

```
task& operator= (const task& _Other);

task& operator= (task&& _Other);
```

### <a name="parameters"></a>Parametreler

*_Diğer*<br/>
Kaynak `task` nesne.

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

Bir `task` kopyalama atamasından sonra, akıllı bir işaretçi gibi `_Other` davrandığı gibi `task` , bu nesneler de aynı gerçek görevi temsil eder.

##  <a name="operator_eq_eq"></a>işleç = =

İki `task` nesnenin aynı dahili görevi temsil ettiğini belirtir.

```
bool operator== (const task<_ResultType>& _Rhs) const;

bool operator== (const task<void>& _Rhs) const;
```

### <a name="parameters"></a>Parametreler

*_Rhs*<br/>
Karşılaştırılacak görev.

### <a name="return-value"></a>Dönüş Değeri

nesneler aynı temel göreve başvuracaksa **true** , aksi takdirde **false** .

##  <a name="scheduler"></a>Task:: Scheduler yöntemi (Eşzamanlılık Çalışma Zamanı)

Bu görev için zamanlayıcıyı döndürür

```
scheduler_ptr scheduler() const;
```

### <a name="return-value"></a>Dönüş Değeri

Zamanlayıcı işaretçisi

##  <a name="ctor"></a>görevinin

Bir `task` nesnesi oluşturur.

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

*ŞI*<br/>
Görevin oluşturulması gereken parametrenin türü.

*_Param*<br/>
Görevin oluşturulması gereken parametre. Windows çalışma zamanı uygulamanızda görevler kullanıyorsanız, bu bir lambda, bir işlev `task_completion_event<result_type>` nesnesi, bir nesnesi veya bir Windows:: Foundation:: IAsyncInfo olabilir. Lambda veya işlev nesnesi ile `std::function<X(void)>`eşdeğer bir tür olmalıdır; burada X, Windows çalışma zamanı uygulamalarda, `task<result_type>`veya bir Windows: `result_type`: Foundation:: IAsyncInfo türünde bir değişken olabilir.

*_TaskOptions*<br/>
Görev seçenekleri iptal belirteci, Zamanlayıcı vb. içerir

*_Diğer*<br/>
Kaynak `task` nesne.

### <a name="remarks"></a>Açıklamalar

İçin `task` varsayılan Oluşturucu yalnızca kapsayıcılar içinde görevlerin kullanılmasına izin vermek için vardır. Varsayılan olarak oluşturulmuş bir görev, kendisine geçerli bir görev atamaz kadar kullanılamaz. Ya `get` `wait` da gibi yöntemler, varsayılan olarak oluşturulmuş bir görevde çağrıldığında bir [invalid_argument](../../../standard-library/invalid-argument-class.md) özel durumu oluşturur. `then`

Görev tamamlama olayı ayarlandığında, öğesinden oluşturulan `task_completion_event` bir görev tamamlanır (ve devamlılıkları zamanlandı).

İptal belirteci alan oluşturucunun sürümü, ' den elde edilen belirteç kullanılarak `cancellation_token_source` iptal edilebilir bir görev oluşturur. İptal belirteci olmadan oluşturulan görevler iptal edilemez.

Bir `Windows::Foundation::IAsyncInfo` arabirimden veya bir `IAsyncInfo` arabirim döndüren bir lambda tarafından oluşturulan görevler, iliştirilmiş Windows çalışma zamanı zaman uyumsuz işlem veya Eylem tamamlandığında, Terminal durumlarına ulaşmalıdır. Benzer şekilde, iç görev, lamdadan döndürüldüğünde değil, `task<result_type>` Terminal durumuna ulaştığında, bir lamdadan tarafından oluşturulan görevler.

`task`akıllı bir işaretçi gibi davranır ve değere göre geçiş yapmak için güvenlidir. Kilitlere gerek olmadan birden çok iş parçacığı tarafından erişilebilir.

Windows:: Foundation:: IAsyncInfo arabirimini alan Oluşturucu aşırı yüklemeleri veya böyle bir arabirim döndüren bir lambda yalnızca Windows Çalışma Zamanı uygulamalar tarafından kullanılabilir.

Daha fazla bilgi için bkz. [Görev Paralelliği](../../../parallel/concrt/task-parallelism-concurrency-runtime.md).

##  <a name="then"></a>ni

Bu göreve bir devamlılık görevi ekler.

```
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
Bu görev tamamlandığında yürütülecek devamlılık işlevi. Bu devamlılık işlevi, ya da `result_type` , `result_type` bu görevin ürettiği sonuç `task<result_type>`türü olan bir veya değişkeni olarak alınmalıdır.

*_TaskOptions*<br/>
Görev seçenekleri iptal belirteci, Zamanlayıcı ve devamlılık bağlamını içerir. Varsayılan olarak, önceki 3 seçenek öncül görevden devralınır

*_CancellationToken*<br/>
Devamlılık göreviyle ilişkilendirilecek iptal belirteci. İptal belirteci olmadan oluşturulan bir devamlılık görevi, öncül görevinin belirtecini miras alacak.

*_ContinuationContext*<br/>
Devamlılığın nerede yürütüleceğini belirten bir değişken. Bu değişken yalnızca UWP uygulamasında kullanıldığında yararlıdır. Daha fazla bilgi için bkz. [task_continuation_context](task-continuation-context-class.md)

### <a name="return-value"></a>Dönüş Değeri

Yeni oluşturulan devamlılık görevi. Döndürülen görevin sonuç türü, ne `_Func` getirdiğinize göre belirlenir.

### <a name="remarks"></a>Açıklamalar

Bir Windows: `then` : Foundation:: IAsyncInfo arabirimini döndüren bir lambda veya functor alan aşırı yüklemeleri yalnızca Windows çalışma zamanı uygulamalar tarafından kullanılabilir.

Zaman uyumsuz iş oluşturmak için görev devamlılıklarını kullanma hakkında daha fazla bilgi için bkz. [Görev Paralelliği](../../../parallel/concrt/task-parallelism-concurrency-runtime.md).

##  <a name="wait"></a>bekleneceğini

Bu görevin Terminal durumuna ulaşmasını bekler. Tüm görev bağımlılıkları karşılanmışsa ve bir arka plan çalışanı tarafından yürütülmek üzere henüz çekilmediğinde, görevin satır içi yürütülmesi mümkündür `wait` .

```
task_status wait() const;
```

### <a name="return-value"></a>Dönüş Değeri

Ya `task_status` da`canceled`olabilecek bir değer. `completed` Görev yürütme sırasında bir özel durumla karşılaşılırsa veya bir öncül görevden buna bir özel durum yayıldıysa, `wait` bu özel durumu oluşturur.

### <a name="remarks"></a>Açıklamalar

> [!IMPORTANT]
>  Evrensel Windows platformu (UWP) uygulamasında, Kullanıcı arabirimi iş parçacığında çalışan `wait` kodda çağrı kullanmayın. Aksi takdirde, çalışma zamanı [eşzamanlılık:: invalid_operation](invalid-operation-class.md) atar çünkü bu yöntem geçerli iş parçacığını engeller ve uygulamanın yanıt vermemesine neden olabilir. Ancak, görev tabanlı devamlılık içinde öncül görevin sonucunu almak için [concurrency:: task:: Get](#get) yöntemini çağırabilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)
