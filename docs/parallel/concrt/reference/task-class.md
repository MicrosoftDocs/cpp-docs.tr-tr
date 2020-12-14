---
description: 'Daha fazla bilgi edinin: task Class (Eşzamanlılık Çalışma Zamanı)'
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
ms.openlocfilehash: b16c7e8f7ae97b35731916d6834367c228ce867c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97188384"
---
# <a name="task-class-concurrency-runtime"></a>task Sınıfı (Eşzamanlılık Çalışma Zamanı)

Paralel Desenler kitaplığı (PPL) `task` sınıfı. Bir `task` nesnesi, eşzamanlılık çalışma zamanı zaman uyumsuz olarak yürütülebilen ve diğer görevlerle eşzamanlı olarak yürütülebilecek çalışmayı ve paralel algoritmalar tarafından üretilen paralel çalışmayı temsil eder. `_ResultType`Başarıyla tamamlanmasıyla ilgili bir sonuç üretir. Tür görevleri `task<void>` sonuç üretmez. Bir görev, diğer görevlerden bağımsız olarak bekleve iptal edilebilir. Ayrıca, devamlılıklar ( `then` ) ve JOIN () ve Choice () desenleri kullanılarak diğer görevlerle da oluşturulabilir `when_all` `when_any` . Bir görev nesnesi yeni bir değişkene atandığında, davranışı ' dır `std::shared_ptr` ; diğer bir deyişle, her iki nesne de aynı temel görevi temsil eder.

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
|[görevinin](#ctor)|Fazla Yüklendi. Bir `task` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Al](#get)|Fazla Yüklendi. Bu görevin ürettiği sonucu döndürür. Görev bir terminal durumunda değilse, için bir çağrısı `get` görevin bitmesini bekler. Bu yöntem, içeren bir görevde çağrıldığında bir değer döndürmez `result_type` **`void`** .|
|[is_apartment_aware](#is_apartment_aware)|Görevin bir Windows Çalışma Zamanı arabirimini kaydırıp sarmadığını `IAsyncInfo` ya da bu türden bir görevden mi ait olduğunu belirler.|
|[is_done](#is_done)|Görevin tamamlanıp tamamlanmadığını belirler.|
|[leyiciyi](#scheduler)|Bu görev için zamanlayıcıyı döndürür|
|[ni](#then)|Fazla Yüklendi. Bu göreve bir devamlılık görevi ekler.|
|[bekleneceğini](#wait)|Bu görevin Terminal durumuna ulaşmasını bekler. `wait`Tüm görev bağımlılıkları karşılanmışsa ve bir arka plan çalışanı tarafından yürütülmek üzere henüz çekilmediğinde, görevin satır içi yürütülmesi mümkündür.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[işleç! =](#operator_neq)|Fazla Yüklendi. İki `task` nesnenin farklı iç görevleri temsil ettiğini belirler.|
|[işleç =](#operator_eq)|Fazla Yüklendi. Bir `task` nesnenin içeriğini başka bir nesneyle değiştirir.|
|[işleç = =](#operator_eq_eq)|Fazla Yüklendi. İki `task` nesnenin aynı dahili görevi temsil ettiğini belirtir.|

## <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [Görev Paralelliği](../../../parallel/concrt/task-parallelism-concurrency-runtime.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`task`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** ppltasks. h

**Ad alanı:** eşzamanlılık

## <a name="get"></a><a name="get"></a> Al

Bu görevin ürettiği sonucu döndürür. Görev bir terminal durumunda değilse, için bir çağrısı `get` görevin bitmesini bekler. Bu yöntem, içeren bir görevde çağrıldığında bir değer döndürmez `result_type` **`void`** .

```cpp
_ResultType get() const;

void get() const;
```

### <a name="return-value"></a>Dönüş Değeri

Görevin sonucu.

### <a name="remarks"></a>Açıklamalar

Görev iptal edilirse, çağrısı `get` bir [task_canceled](task-canceled-class.md) özel durumu oluşturur. Görev farklı bir özel durumla karşılaşılırsa veya bir öncül görevden buna bir özel durum yayıldıysa, öğesine yapılan bir çağrı `get` o özel durumu oluşturur.

> [!IMPORTANT]
> Evrensel Windows Platformu (UWP) uygulamasında, [](#wait) `get` `wait` `get` Kullanıcı arabirimi iş parçacığında çalışan kodda concurrency:: task:: Wait veya (çağrılar) çağırmayın. Aksi takdirde, çalışma zamanı [eşzamanlılık:: invalid_operation](invalid-operation-class.md) atar çünkü bu yöntemler geçerli iş parçacığını engeller ve uygulamanın yanıt vermemesine neden olabilir. Ancak, `get` sonuç hemen kullanılabilir olduğundan, öncül görevin sonucunu görev tabanlı devamlıya almak için yöntemini çağırabilirsiniz.

## <a name="is_apartment_aware"></a><a name="is_apartment_aware"></a> is_apartment_aware

Görevin bir Windows Çalışma Zamanı arabirimini kaydırıp sarmadığını `IAsyncInfo` ya da bu türden bir görevden mi ait olduğunu belirler.

```cpp
bool is_apartment_aware() const;
```

### <a name="return-value"></a>Dönüş Değeri

**`true`** görev, bir `IAsyncInfo` arabirimi sarmalandırıp sarmadıysa veya bu tür bir görevden, **`false`** tersi durumda.

## <a name="taskis_done-method-concurrency-runtime"></a><a name="is_done"></a> Task:: is_done yöntemi (Eşzamanlılık Çalışma Zamanı)

Görevin tamamlanıp tamamlanmadığını belirler.

```cpp
bool is_done() const;
```

### <a name="return-value"></a>Dönüş Değeri

Görev tamamlanırsa true, aksi takdirde false.

### <a name="remarks"></a>Açıklamalar

Görev tamamlandığında veya iptal edildiğinde (Kullanıcı özel durumuyla veya olmadan), işlev true değerini döndürür.

## <a name="operator"></a><a name="operator_neq"></a> işleç! =

İki `task` nesnenin farklı iç görevleri temsil ettiğini belirler.

```cpp
bool operator!= (const task<_ResultType>& _Rhs) const;

bool operator!= (const task<void>& _Rhs) const;
```

### <a name="parameters"></a>Parametreler

*_Rhs*<br/>
Karşılaştırılacak görev.

### <a name="return-value"></a>Dönüş Değeri

**`true`** nesneler farklı temel görevlere başvurur ve **`false`** Aksi durumda.

## <a name="operator"></a><a name="operator_eq"></a> işleç =

Bir `task` nesnenin içeriğini başka bir nesneyle değiştirir.

```cpp
task& operator= (const task& _Other);

task& operator= (task&& _Other);
```

### <a name="parameters"></a>Parametreler

*_Other*<br/>
Kaynak `task` nesne.

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

Bir `task` kopyalama atamasından sonra, akıllı bir işaretçi gibi davrandığı gibi, bu `task` nesneler de aynı gerçek görevi temsil eder `_Other` .

## <a name="operator"></a><a name="operator_eq_eq"></a> işleç = =

İki `task` nesnenin aynı dahili görevi temsil ettiğini belirtir.

```cpp
bool operator== (const task<_ResultType>& _Rhs) const;

bool operator== (const task<void>& _Rhs) const;
```

### <a name="parameters"></a>Parametreler

*_Rhs*<br/>
Karşılaştırılacak görev.

### <a name="return-value"></a>Dönüş Değeri

**`true`** nesneler aynı temel görevi ifade eder ve **`false`** Aksi takdirde.

## <a name="taskscheduler-method-concurrency-runtime"></a><a name="scheduler"></a> Task:: Scheduler yöntemi (Eşzamanlılık Çalışma Zamanı)

Bu görev için zamanlayıcıyı döndürür

```cpp
scheduler_ptr scheduler() const;
```

### <a name="return-value"></a>Dönüş Değeri

Zamanlayıcı işaretçisi

## <a name="task"></a><a name="ctor"></a> görevinin

Bir `task` nesnesi oluşturur.

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
Görevin oluşturulması gereken parametrenin türü.

*_Param*<br/>
Görevin oluşturulması gereken parametre. Windows Çalışma Zamanı uygulamanızda görevler kullanıyorsanız, bu bir lambda, bir işlev nesnesi, bir `task_completion_event<result_type>` nesnesi veya bir Windows:: Foundation:: IAsyncInfo olabilir. Lambda veya işlev nesnesi ile eşdeğer bir tür olmalıdır `std::function<X(void)>` ; burada X `result_type` , `task<result_type>` Windows çalışma zamanı uygulamalarda, veya bir Windows:: Foundation:: IAsyncInfo türünde bir değişken olabilir.

*_TaskOptions*<br/>
Görev seçenekleri iptal belirteci, Zamanlayıcı vb. içerir

*_Other*<br/>
Kaynak `task` nesne.

### <a name="remarks"></a>Açıklamalar

İçin varsayılan Oluşturucu `task` yalnızca kapsayıcılar içinde görevlerin kullanılmasına izin vermek için vardır. Varsayılan olarak oluşturulmuş bir görev, kendisine geçerli bir görev atamaz kadar kullanılamaz. `get`Ya da gibi yöntemler, `wait` Varsayılan olarak `then` oluşturulmuş bir görevde çağrıldığında bir [invalid_argument](../../../standard-library/invalid-argument-class.md) özel durumu oluşturur.

`task_completion_event`Görev tamamlama olayı ayarlandığında, öğesinden oluşturulan bir görev tamamlanır (ve devamlılıkları zamanlandı).

İptal belirteci alan oluşturucunun sürümü, ' den elde edilen belirteç kullanılarak iptal edilebilir bir görev oluşturur `cancellation_token_source` . İptal belirteci olmadan oluşturulan görevler iptal edilemez.

Bir `Windows::Foundation::IAsyncInfo` arabirimden veya bir arabirim döndüren bir lambda tarafından oluşturulan görevler `IAsyncInfo` , iliştirilmiş Windows çalışma zamanı zaman uyumsuz işlem veya Eylem tamamlandığında, Terminal durumlarına ulaşmalıdır. Benzer şekilde, `task<result_type>` iç görev, lambda döndürüldüğünde değil, Terminal durumuna ulaştığında, bir lambda tarafından oluşturulan görevler.

`task` akıllı bir işaretçi gibi davranır ve değere göre geçiş yapmak için güvenlidir. Kilitlere gerek olmadan birden çok iş parçacığı tarafından erişilebilir.

Windows:: Foundation:: IAsyncInfo arabirimini alan Oluşturucu aşırı yüklemeleri veya böyle bir arabirim döndüren bir lambda yalnızca Windows Çalışma Zamanı uygulamalar tarafından kullanılabilir.

Daha fazla bilgi için bkz. [Görev Paralelliği](../../../parallel/concrt/task-parallelism-concurrency-runtime.md).

## <a name="then"></a><a name="then"></a> ni

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
Bu görev tamamlandığında yürütülecek devamlılık işlevi. Bu devamlılık işlevi `result_type` , ya da `task<result_type>` , `result_type` Bu görevin ürettiği sonuç türü olan bir veya değişkeni olarak alınmalıdır.

*_TaskOptions*<br/>
Görev seçenekleri iptal belirteci, Zamanlayıcı ve devamlılık bağlamını içerir. Varsayılan olarak, önceki 3 seçenek öncül görevden devralınır

*_CancellationToken*<br/>
Devamlılık göreviyle ilişkilendirilecek iptal belirteci. İptal belirteci olmadan oluşturulan bir devamlılık görevi, öncül görevinin belirtecini miras alacak.

*_ContinuationContext*<br/>
Devamlılığın nerede yürütüleceğini belirten bir değişken. Bu değişken yalnızca UWP uygulamasında kullanıldığında yararlıdır. Daha fazla bilgi için bkz. [task_continuation_context](task-continuation-context-class.md)

### <a name="return-value"></a>Dönüş Değeri

Yeni oluşturulan devamlılık görevi. Döndürülen görevin sonuç türü, ne `_Func` getirdiğinize göre belirlenir.

### <a name="remarks"></a>Açıklamalar

`then`Bir Windows:: Foundation:: IAsyncInfo arabirimini döndüren bir lambda veya functor alan aşırı yüklemeleri yalnızca Windows çalışma zamanı uygulamalar tarafından kullanılabilir.

Zaman uyumsuz iş oluşturmak için görev devamlılıklarını kullanma hakkında daha fazla bilgi için bkz. [Görev Paralelliği](../../../parallel/concrt/task-parallelism-concurrency-runtime.md).

## <a name="wait"></a><a name="wait"></a> bekleneceğini

Bu görevin Terminal durumuna ulaşmasını bekler. `wait`Tüm görev bağımlılıkları karşılanmışsa ve bir arka plan çalışanı tarafından yürütülmek üzere henüz çekilmediğinde, görevin satır içi yürütülmesi mümkündür.

```cpp
task_status wait() const;
```

### <a name="return-value"></a>Dönüş Değeri

`task_status`Ya da olabilecek bir değer `completed` `canceled` . Görev yürütme sırasında bir özel durumla karşılaşılırsa veya bir öncül görevden buna bir özel durum yayıldıysa, `wait` Bu özel durumu oluşturur.

### <a name="remarks"></a>Açıklamalar

> [!IMPORTANT]
> Evrensel Windows Platformu (UWP) uygulamasında, `wait` Kullanıcı arabirimi iş parçacığında çalışan kodda çağrı kullanmayın. Aksi takdirde, çalışma zamanı [eşzamanlılık:: invalid_operation](invalid-operation-class.md) oluşturur, çünkü bu yöntem geçerli iş parçacığını engeller ve uygulamanın yanıt vermemesine neden olabilir. Ancak, görev tabanlı devamlılık içinde öncül görevin sonucunu almak için [concurrency:: task:: Get](#get) yöntemini çağırabilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık ad alanı](concurrency-namespace.md)
