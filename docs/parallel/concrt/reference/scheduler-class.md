---
title: Zamanlayıcı Sınıfı
ms.date: 11/04/2016
f1_keywords:
- Scheduler
- CONCRT/concurrency::Scheduler
- CONCRT/concurrency::Scheduler::Scheduler
- CONCRT/concurrency::Scheduler::Attach
- CONCRT/concurrency::Scheduler::Create
- CONCRT/concurrency::Scheduler::CreateScheduleGroup
- CONCRT/concurrency::Scheduler::GetNumberOfVirtualProcessors
- CONCRT/concurrency::Scheduler::GetPolicy
- CONCRT/concurrency::Scheduler::Id
- CONCRT/concurrency::Scheduler::IsAvailableLocation
- CONCRT/concurrency::Scheduler::Reference
- CONCRT/concurrency::Scheduler::RegisterShutdownEvent
- CONCRT/concurrency::Scheduler::Release
- CONCRT/concurrency::Scheduler::ResetDefaultSchedulerPolicy
- CONCRT/concurrency::Scheduler::ScheduleTask
- CONCRT/concurrency::Scheduler::SetDefaultSchedulerPolicy
helpviewer_keywords:
- Scheduler class
ms.assetid: 34cf7961-048d-4852-8a5c-a32f823e3506
ms.openlocfilehash: 77ad876b8352ab1ae86fde622b05712ec5f2cea9
ms.sourcegitcommit: 19016630f9d35f365e9ba249e0f3617515d7ca33
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/20/2020
ms.locfileid: "92274710"
---
# <a name="scheduler-class"></a>Zamanlayıcı Sınıfı

Eşzamanlılık Çalışma Zamanı Zamanlayıcı için bir soyutlama temsil eder.

## <a name="syntax"></a>Sözdizimi

```cpp
class Scheduler;
```

## <a name="members"></a>Üyeler

### <a name="protected-constructors"></a>Korumalı Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[Scheduler](#ctor)|Sınıfının bir nesnesi `Scheduler` yalnızca Fabrika yöntemleri kullanılarak veya örtük olarak oluşturulabilir.|
|[~ Scheduler yıkıcısı](#dtor)|Sınıfın bir nesnesi, `Scheduler` kendisine yapılan tüm dış başvurular mevcut olduğunda örtük olarak yok edilir.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[İliştir](#attach)|Zamanlayıcıyı çağıran bağlama iliştirir. Bu yöntem çağrıldıktan sonra, çağıran bağlam Zamanlayıcı tarafından yönetilir ve Zamanlayıcı geçerli Zamanlayıcı olur.|
|[Oluştur](#create)|Davranışı parametresi tarafından tanımlanan yeni bir zamanlayıcı oluşturur `_Policy` , Scheduler 'a bir başlangıç başvurusu koyar ve ona bir işaretçi döndürür.|
|[CreateScheduleGroup](#createschedulegroup)|Fazla Yüklendi. Zamanlayıcı içinde yeni bir zamanlama grubu oluşturur. Parametresini alan sürüm, `_Placement` Yeni oluşturulan zamanlama grubundaki görevlerin Bu parametre tarafından belirtilen konumda yürütülmeye yaklaşmasına neden olur.|
|[GetNumberOfVirtualProcessors](#getnumberofvirtualprocessors)|Zamanlayıcı için geçerli sanal işlemci sayısını döndürür.|
|[GetPolicy](#getpolicy)|Scheduler 'ın ile oluşturulduğu ilkenin bir kopyasını döndürür.|
|[Id](#id)|Zamanlayıcı için benzersiz bir tanımlayıcı döndürür.|
|[IsAvailableLocation](#isavailablelocation)|Belirli bir konumun Scheduler 'da kullanılabilir olup olmadığını belirler.|
|[Başvuru](#reference)|Zamanlayıcı başvuru sayısını artırır.|
|[RegisterShutdownEvent](#registershutdownevent)|`_Event`Zamanlayıcı kapandığında ve kendi kendine yok edildiğinde, parametrede geçirilen Windows olay tanıtıcısına neden olur. Olaya işaret edilen zaman, Scheduler 'a zamanlanan tüm işler tamamlanmıştır. Birden çok kapanmaya yönelik olay, bu yöntem kullanılarak kaydedilebilir.|
|[Sürüm](#release)|Zamanlayıcı başvuru sayısını azaltır.|
|[ResetDefaultSchedulerPolicy](#resetdefaultschedulerpolicy)|Varsayılan zamanlayıcı ilkesini çalışma zamanı varsayılan ayarlarına sıfırlar. Varsayılan bir Zamanlayıcı oluşturulduğunda, çalışma zamanı varsayılan ilke ayarlarını kullanır.|
|[ScheduleTask](#scheduletask)|Fazla Yüklendi. Zamanlayıcı içinde bir hafif görevi zamanlar. Hafif görev, çalışma zamanı tarafından belirlenen bir zamanlama grubuna yerleştirilir. Parametresini alan sürüm, `_Placement` görevin belirtilen konumda yürütülmeye yaklaşmasına neden olur.|
|[SetDefaultSchedulerPolicy](#setdefaultschedulerpolicy)|Varsayılan zamanlayıcıyı oluşturmak için Kullanıcı tanımlı bir ilkenin kullanılmasına izin verir. Bu yöntem yalnızca işlem içinde varsayılan Zamanlayıcı yoksa çağrılabilir. Varsayılan bir ilke ayarlandıktan sonra, ya da ResetDefaultSchedulerPolicy yöntemine bir sonraki geçerli çağrıya kadar yürürlükte kalır `SetDefaultSchedulerPolicy` . [ResetDefaultSchedulerPolicy](#resetdefaultschedulerpolicy)|

## <a name="remarks"></a>Açıklamalar

Eşzamanlılık Çalışma Zamanı Zamanlayıcı, uygulamanız tarafından kuyruğa alınan işleri yürütmek için iş parçacığı gibi işletim sistemi yürütme bağlamlarına eşlenen yürütme bağlamlarını kullanır. Dilediğiniz zaman, bir Scheduler 'ın eşzamanlılık düzeyi, Kaynak Yöneticisi tarafından kendisine verilen sanal işlemci sayısına eşittir. Sanal işlemci bir işleme kaynağı için soyutlamadır ve temel alınan sistemdeki bir donanım iş parçacığına eşlenir. Belirli bir zamanda sanal işlemcide yalnızca tek bir Zamanlayıcı bağlamı çalıştırılabilir.

Eşzamanlılık Çalışma Zamanı paralel çalışmayı yürütmek için işlem başına varsayılan bir Zamanlayıcı oluşturacaktır. Ayrıca, kendi Zamanlayıcı örneklerinizi oluşturabilir ve bu sınıfı kullanarak değiştirebilirsiniz.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`Scheduler`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** concrt. h

**Ad alanı:** eşzamanlılık

## <a name="attach"></a><a name="attach"></a> Ekleme

Zamanlayıcıyı çağıran bağlama iliştirir. Bu yöntem çağrıldıktan sonra, çağıran bağlam Zamanlayıcı tarafından yönetilir ve Zamanlayıcı geçerli Zamanlayıcı olur.

```cpp
virtual void Attach() = 0;
```

### <a name="remarks"></a>Açıklamalar

Zamanlayıcı eklemek Scheduler 'a dolaylı olarak bir başvuru koyar.

Gelecekte bir noktada, Scheduler 'ın kapanmasına izin vermek için [CurrentScheduler::D etach](currentscheduler-class.md#detach) yöntemini çağırmanız gerekir.

Bu yöntem, farklı bir zamanlayıcıya zaten bağlı olan bir içerikten çağrılırsa, mevcut Zamanlayıcı önceki Zamanlayıcı olarak hatırlanır ve yeni oluşturulan Zamanlayıcı geçerli Zamanlayıcı olur. `CurrentScheduler::Detach`Yöntemi sonraki bir noktada çağırdığınızda, önceki Zamanlayıcı geçerli Zamanlayıcı olarak geri yüklenir.

Bu Zamanlayıcı çağıran bağlamın geçerli Scheduler ise, bu yöntem [improper_scheduler_attach](improper-scheduler-attach-class.md) bir özel durum oluşturur.

## <a name="create"></a><a name="create"></a> Oluşturma

Davranışı parametresi tarafından tanımlanan yeni bir zamanlayıcı oluşturur `_Policy` , Scheduler 'a bir başlangıç başvurusu koyar ve ona bir işaretçi döndürür.

```cpp
static Scheduler* __cdecl Create(const SchedulerPolicy& _Policy);
```

### <a name="parameters"></a>Parametreler

*_Policy*<br/>
Yeni oluşturulan Scheduler 'un davranışını açıklayan Zamanlayıcı İlkesi.

### <a name="return-value"></a>Dönüş Değeri

Yeni oluşturulan Scheduler için bir işaretçi. Bu `Scheduler` nesnenin kendisine yerleştirilmiş bir başlangıç başvuru sayısı vardır.

### <a name="remarks"></a>Açıklamalar

Yöntemiyle bir Zamanlayıcı oluşturulduktan sonra `Create` , `Release` ilk başvuru sayısını kaldırmak ve Scheduler 'ın kapanmasına izin vermek için gelecekteki bir noktada yöntemini çağırmanız gerekir.

Bu yöntemle oluşturulan bir zamanlayıcı, çağıran bağlama bağlı değil. [Attach](#attach) yöntemi kullanılarak bir bağlama eklenebilir.

Bu yöntem [scheduler_resource_allocation_error](scheduler-resource-allocation-error-class.md) ve [invalid_scheduler_policy_value](invalid-scheduler-policy-value-class.md)dahil olmak üzere çeşitli özel durumlar oluşturabilir.

## <a name="createschedulegroup"></a><a name="createschedulegroup"></a> CreateScheduleGroup

Zamanlayıcı içinde yeni bir zamanlama grubu oluşturur. Parametresini alan sürüm, `_Placement` Yeni oluşturulan zamanlama grubundaki görevlerin Bu parametre tarafından belirtilen konumda yürütülmeye yaklaşmasına neden olur.

```cpp
virtual ScheduleGroup* CreateScheduleGroup() = 0;

virtual ScheduleGroup* CreateScheduleGroup(location& _Placement) = 0;
```

### <a name="parameters"></a>Parametreler

*_Placement*<br/>
Zamanlama grubundaki görevlerin ' de yürütmeye yaklaşmasına neden olacak bir konuma başvuru.

### <a name="return-value"></a>Dönüş Değeri

Yeni oluşturulan zamanlama grubuna yönelik bir işaretçi. Bu `ScheduleGroup` nesnenin kendisine yerleştirilmiş bir başlangıç başvuru sayısı vardır.

### <a name="remarks"></a>Açıklamalar

İş planlaması yapıldığında, bir zamanlama grubundaki [Release](schedulegroup-class.md#release) metodunu çağırmanız gerekir. Sıraya alınan tüm işler tamamlandığında Zamanlayıcı, zamanlama grubunu yok eder.

Bu Scheduler 'ı açıkça oluşturduysanız, Zamanlayıcıdaki başvurularınızı serbest bırakmadan önce, içindeki zamanlama gruplarına tüm başvuruları serbest bırakmanız gerektiğini unutmayın.

## <a name="getnumberofvirtualprocessors"></a><a name="getnumberofvirtualprocessors"></a> GetNumberOfVirtualProcessors

Zamanlayıcı için geçerli sanal işlemci sayısını döndürür.

```cpp
virtual unsigned int GetNumberOfVirtualProcessors() const = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Zamanlayıcı için geçerli sanal işlemci sayısı.

## <a name="getpolicy"></a><a name="getpolicy"></a> GetPolicy

Scheduler 'ın ile oluşturulduğu ilkenin bir kopyasını döndürür.

```cpp
virtual SchedulerPolicy GetPolicy() const = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Scheduler 'ın ile oluşturulduğu ilkenin bir kopyası.

## <a name="id"></a><a name="id"></a> Numarasını

Zamanlayıcı için benzersiz bir tanımlayıcı döndürür.

```cpp
virtual unsigned int Id() const = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Zamanlayıcı için benzersiz bir tanımlayıcı.

## <a name="isavailablelocation"></a><a name="isavailablelocation"></a> IsAvailableLocation

Belirli bir konumun Scheduler 'da kullanılabilir olup olmadığını belirler.

```cpp
virtual bool IsAvailableLocation(const location& _Placement) const = 0;
```

### <a name="parameters"></a>Parametreler

*_Placement*<br/>
Scheduler 'ı sorgulayan konuma bir başvuru.

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişken tarafından belirtilen konumun Scheduler 'da kullanılıp kullanılmadığını belirtir `_Placement` .

### <a name="remarks"></a>Açıklamalar

Dönüş değerinin, belirtilen konumun kullanılabilir olup olmadığına ilişkin anlık örnekleme olduğunu unutmayın. Birden çok zamanlayıcılar mevcut olduğunda, dinamik kaynak yönetimi herhangi bir noktada zamanlayıcılar 'ten kaynak ekleyebilir veya buradan kaynak alabilir. Bu durum, belirtilen konumun kullanılabilirliği değiştirebilmelidir.

## <a name="reference"></a><a name="reference"></a> Başvurunun

Zamanlayıcı başvuru sayısını artırır.

```cpp
virtual unsigned int Reference() = 0 ;
```

### <a name="return-value"></a>Dönüş Değeri

Yeni artan başvuru sayısı.

### <a name="remarks"></a>Açıklamalar

Bu genellikle, oluşturma için Scheduler 'ın ömrünü yönetmek için kullanılır. Bir Scheduler 'ın başvuru sayısı sıfır olduğunda, Scheduler 'daki tüm çalışmalar tamamlandıktan sonra Zamanlayıcı kapanır ve yapısını kaldırır.

Yöntemi çağrılmadan önce başvuru sayısı [improper_scheduler_reference](improper-scheduler-reference-class.md) `Reference` sıfır ise ve Zamanlayıcı tarafından sahip olmayan bir içerikten çağrı yapılırsa Yöntem improper_scheduler_reference bir özel durum oluşturur.

## <a name="registershutdownevent"></a><a name="registershutdownevent"></a> RegisterShutdownEvent

`_Event`Zamanlayıcı kapandığında ve kendi kendine yok edildiğinde, parametrede geçirilen Windows olay tanıtıcısına neden olur. Olaya işaret edilen zaman, Scheduler 'a zamanlanan tüm işler tamamlanmıştır. Birden çok kapanmaya yönelik olay, bu yöntem kullanılarak kaydedilebilir.

```cpp
virtual void RegisterShutdownEvent(HANDLE _Event) = 0;
```

### <a name="parameters"></a>Parametreler

*_Event*<br/>
Zamanlayıcı kapandığında çalışma zamanı tarafından işaret edilecek ve kendisini yok eden bir Windows olay nesnesi tutamacı.

## <a name="release"></a><a name="release"></a> Yayın

Zamanlayıcı başvuru sayısını azaltır.

```cpp
virtual unsigned int Release() = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Yeni küçültülenen başvuru sayısı.

### <a name="remarks"></a>Açıklamalar

Bu genellikle, oluşturma için Scheduler 'ın ömrünü yönetmek için kullanılır. Bir Scheduler 'ın başvuru sayısı sıfır olduğunda, Scheduler 'daki tüm çalışmalar tamamlandıktan sonra Zamanlayıcı kapanır ve yapısını kaldırır.

## <a name="resetdefaultschedulerpolicy"></a><a name="resetdefaultschedulerpolicy"></a> ResetDefaultSchedulerPolicy

Varsayılan zamanlayıcı ilkesini çalışma zamanı varsayılan ayarlarına sıfırlar. Varsayılan bir Zamanlayıcı oluşturulduğunda, çalışma zamanı varsayılan ilke ayarlarını kullanır.

```cpp
static void __cdecl ResetDefaultSchedulerPolicy();
```

### <a name="remarks"></a>Açıklamalar

Bu yöntem, işlem içinde varsayılan bir Zamanlayıcı varken çağrılabilir. Var olan varsayılan Scheduler 'ın ilkesini etkilemez. Ancak, varsayılan Zamanlayıcı kapatılmaya çalışıyorsa ve sonraki bir noktada yeni bir varsayılan değer oluşturulacaksa, yeni zamanlayıcı çalışma zamanı varsayılan ilke ayarlarını kullanır.

## <a name="scheduler"></a><a name="ctor"></a> Leyiciyi

Sınıfının bir nesnesi `Scheduler` yalnızca Fabrika yöntemleri kullanılarak veya örtük olarak oluşturulabilir.

```cpp
Scheduler();
```

### <a name="remarks"></a>Açıklamalar

İşlem ' varsayılan Zamanlayıcı, bir Scheduler 'ın çağırma bağlamına eklenmesini gerektiren birçok çalışma zamanı işlevini kullandığınızda örtülü olarak oluşturulur. `CurrentScheduler`PPL ve Agents katmanlarının sınıf ve özellikleri içindeki yöntemler genellikle örtük ek gerçekleştirir.

Ayrıca, yöntemi ya da yöntemi aracılığıyla açıkça bir Zamanlayıcı oluşturabilirsiniz `CurrentScheduler::Create` `Scheduler::Create` .

## <a name="scheduler"></a><a name="dtor"></a> ~ Scheduler

Sınıfın bir nesnesi, `Scheduler` kendisine yapılan tüm dış başvurular mevcut olduğunda örtük olarak yok edilir.

```cpp
virtual ~Scheduler();
```

## <a name="scheduletask"></a><a name="scheduletask"></a> ScheduleTask

Zamanlayıcı içinde bir hafif görevi zamanlar. Hafif görev, çalışma zamanı tarafından belirlenen bir zamanlama grubuna yerleştirilir. Parametresini alan sürüm, `_Placement` görevin belirtilen konumda yürütülmeye yaklaşmasına neden olur.

```cpp
virtual void ScheduleTask(
    TaskProc _Proc,
    _Inout_opt_ void* _Data) = 0;

virtual void ScheduleTask(
    TaskProc _Proc,
    _Inout_opt_ void* _Data,
    location& _Placement) = 0;
```

### <a name="parameters"></a>Parametreler

*_Proc*<br/>
Hafif görevin gövdesini gerçekleştirmek için yürütülecek işleve yönelik bir işaretçi.

*_Data*<br/>
Görevin gövdesine parametre olarak geçirilecek verilerin void işaretçisi.

*_Placement*<br/>
Hafif bir görevin, üzerinde yürütülmesi için yüz aşağı olacağı bir konuma başvuru.

## <a name="setdefaultschedulerpolicy"></a><a name="setdefaultschedulerpolicy"></a> SetDefaultSchedulerPolicy

Varsayılan zamanlayıcıyı oluşturmak için Kullanıcı tanımlı bir ilkenin kullanılmasına izin verir. Bu yöntem yalnızca işlem içinde varsayılan Zamanlayıcı yoksa çağrılabilir. Varsayılan bir ilke ayarlandıktan sonra, ya da ResetDefaultSchedulerPolicy yöntemine bir sonraki geçerli çağrıya kadar yürürlükte kalır `SetDefaultSchedulerPolicy` . [ResetDefaultSchedulerPolicy](#resetdefaultschedulerpolicy)

```cpp
static void __cdecl SetDefaultSchedulerPolicy(const SchedulerPolicy& _Policy);
```

### <a name="parameters"></a>Parametreler

*_Policy*<br/>
Varsayılan Zamanlayıcı İlkesi olarak ayarlanacak ilke.

### <a name="remarks"></a>Açıklamalar

Yöntemi, `SetDefaultSchedulerPolicy` işlem içinde varsayılan bir Zamanlayıcı zaten varken çağrılırsa, çalışma zamanı [default_scheduler_exists](default-scheduler-exists-class.md) bir özel durum oluşturur.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık ad alanı](concurrency-namespace.md)<br/>
[Zamanlayıcı sınıfı](scheduler-class.md)<br/>
[PolicyElementKey](concurrency-namespace-enums.md)<br/>
[Görev Zamanlayıcı](../../../parallel/concrt/task-scheduler-concurrency-runtime.md)
