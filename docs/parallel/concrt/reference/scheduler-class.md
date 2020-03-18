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
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/16/2020
ms.locfileid: "79422117"
---
# <a name="scheduler-class"></a>Zamanlayıcı Sınıfı

Eşzamanlılık Çalışma Zamanı Zamanlayıcı için bir soyutlama temsil eder.

## <a name="syntax"></a>Sözdizimi

```cpp
class Scheduler;
```

## <a name="members"></a>Üyeler

### <a name="protected-constructors"></a>Korumalı Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[Scheduler](#ctor)|`Scheduler` sınıfının bir nesnesi yalnızca Fabrika yöntemleri kullanılarak veya örtük olarak oluşturulabilir.|
|[~ Scheduler yıkıcısı](#dtor)|`Scheduler` sınıfının bir nesnesi, kendisine yapılan tüm dış başvurular mevcut olduğunda örtük olarak yok edilir.|

### <a name="public-methods"></a>Genel Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[Attach](#attach)|Zamanlayıcıyı çağıran bağlama iliştirir. Bu yöntem çağrıldıktan sonra, çağıran bağlam Zamanlayıcı tarafından yönetilir ve Zamanlayıcı geçerli Zamanlayıcı olur.|
|[Oluşturma](#create)|Davranışı `_Policy` parametresi tarafından tanımlanan yeni bir zamanlayıcı oluşturur, Scheduler 'a bir başlangıç başvurusu koyar ve ona bir işaretçi döndürür.|
|[CreateScheduleGroup](#createschedulegroup)|Aşırı yüklendi. Zamanlayıcı içinde yeni bir zamanlama grubu oluşturur. `_Placement` parametresini alan sürüm, yeni oluşturulan zamanlama grubundaki görevlerin Bu parametre tarafından belirtilen konumda yürütülmeye dahil edilmesine neden olur.|
|[GetNumberOfVirtualProcessors](#getnumberofvirtualprocessors)|Zamanlayıcı için geçerli sanal işlemci sayısını döndürür.|
|[GetPolicy](#getpolicy)|Scheduler 'ın ile oluşturulduğu ilkenin bir kopyasını döndürür.|
|[Kimlik](#id)|Zamanlayıcı için benzersiz bir tanımlayıcı döndürür.|
|[IsAvailableLocation](#isavailablelocation)|Belirli bir konumun Scheduler 'da kullanılabilir olup olmadığını belirler.|
|[Başvuru](#reference)|Zamanlayıcı başvuru sayısını artırır.|
|[RegisterShutdownEvent](#registershutdownevent)|Zamanlayıcı kapandığında ve kendisini yok eder `_Event` parametresinde geçirilen Windows olay tanıtıcısına neden olur. Olaya işaret edilen zaman, Scheduler 'a zamanlanan tüm işler tamamlanmıştır. Birden çok kapanmaya yönelik olay, bu yöntem kullanılarak kaydedilebilir.|
|[Sürüm](#release)|Zamanlayıcı başvuru sayısını azaltır.|
|[ResetDefaultSchedulerPolicy](#resetdefaultschedulerpolicy)|Varsayılan zamanlayıcı ilkesini çalışma zamanı varsayılan ayarlarına sıfırlar. Varsayılan bir Zamanlayıcı oluşturulduğunda, çalışma zamanı varsayılan ilke ayarlarını kullanır.|
|[ScheduleTask](#scheduletask)|Aşırı yüklendi. Zamanlayıcı içinde bir hafif görevi zamanlar. Hafif görev, çalışma zamanı tarafından belirlenen bir zamanlama grubuna yerleştirilir. `_Placement` parametresini alan sürüm, görevin belirtilen konumda yürütülerek aşağı doğru kaydırılmasına neden olur.|
|[SetDefaultSchedulerPolicy](#setdefaultschedulerpolicy)|Varsayılan zamanlayıcıyı oluşturmak için Kullanıcı tanımlı bir ilkenin kullanılmasına izin verir. Bu yöntem yalnızca işlem içinde varsayılan Zamanlayıcı yoksa çağrılabilir. Varsayılan bir ilke ayarlandıktan sonra, `SetDefaultSchedulerPolicy` veya [ResetDefaultSchedulerPolicy](#resetdefaultschedulerpolicy) yöntemine bir sonraki geçerli çağrıya kadar yürürlükte kalır.|

## <a name="remarks"></a>Açıklamalar

Eşzamanlılık Çalışma Zamanı Zamanlayıcı, uygulamanız tarafından kuyruğa alınan işleri yürütmek için iş parçacığı gibi işletim sistemi yürütme bağlamlarına eşlenen yürütme bağlamlarını kullanır. Dilediğiniz zaman, bir Scheduler 'ın eşzamanlılık düzeyi, Kaynak Yöneticisi tarafından kendisine verilen sanal işlemci sayısına eşittir. Sanal işlemci bir işleme kaynağı için soyutlamadır ve temel alınan sistemdeki bir donanım iş parçacığına eşlenir. Belirli bir zamanda sanal işlemcide yalnızca tek bir Zamanlayıcı bağlamı çalıştırılabilir.

Eşzamanlılık Çalışma Zamanı paralel çalışmayı yürütmek için işlem başına varsayılan bir Zamanlayıcı oluşturacaktır. Ayrıca, kendi Zamanlayıcı örneklerinizi oluşturabilir ve bu sınıfı kullanarak değiştirebilirsiniz.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`Scheduler`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** concrt. h

**Ad alanı:** eşzamanlılık

## <a name="attach"></a>Ekleme

Zamanlayıcıyı çağıran bağlama iliştirir. Bu yöntem çağrıldıktan sonra, çağıran bağlam Zamanlayıcı tarafından yönetilir ve Zamanlayıcı geçerli Zamanlayıcı olur.

```cpp
virtual void Attach() = 0;
```

### <a name="remarks"></a>Açıklamalar

Zamanlayıcı eklemek Scheduler 'a dolaylı olarak bir başvuru koyar.

Gelecekte bir noktada, Scheduler 'ın kapanmasına izin vermek için [CurrentScheduler::D etach](currentscheduler-class.md#detach) yöntemini çağırmanız gerekir.

Bu yöntem, farklı bir zamanlayıcıya zaten bağlı olan bir içerikten çağrılırsa, mevcut Zamanlayıcı önceki Zamanlayıcı olarak hatırlanır ve yeni oluşturulan Zamanlayıcı geçerli Zamanlayıcı olur. `CurrentScheduler::Detach` yöntemini sonraki bir noktada çağırdığınızda, önceki Zamanlayıcı geçerli Zamanlayıcı olarak geri yüklenir.

Bu Zamanlayıcı çağıran bağlamın geçerli Scheduler ise, bu yöntem [improper_scheduler_attach](improper-scheduler-attach-class.md) bir özel durum oluşturur.

## <a name="create"></a>Oluşturma

Davranışı `_Policy` parametresi tarafından tanımlanan yeni bir zamanlayıcı oluşturur, Scheduler 'a bir başlangıç başvurusu koyar ve ona bir işaretçi döndürür.

```cpp
static Scheduler* __cdecl Create(const SchedulerPolicy& _Policy);
```

### <a name="parameters"></a>Parametreler

*_Policy*<br/>
Yeni oluşturulan Scheduler 'un davranışını açıklayan Zamanlayıcı İlkesi.

### <a name="return-value"></a>Dönüş Değeri

Yeni oluşturulan Scheduler için bir işaretçi. Bu `Scheduler` nesnesi, üzerine yerleştirilmiş bir başlangıç başvuru sayısına sahiptir.

### <a name="remarks"></a>Açıklamalar

`Create` yöntemiyle bir Zamanlayıcı oluşturulduktan sonra, ilk başvuru sayısını kaldırmak ve Scheduler 'ın kapatılmasını sağlamak için gelecekte bir noktada `Release` yöntemini çağırmanız gerekir.

Bu yöntemle oluşturulan bir zamanlayıcı, çağıran bağlama bağlı değil. [Attach](#attach) yöntemi kullanılarak bir bağlama eklenebilir.

Bu yöntem [scheduler_resource_allocation_error](scheduler-resource-allocation-error-class.md) ve [invalid_scheduler_policy_value](invalid-scheduler-policy-value-class.md)dahil olmak üzere çeşitli özel durumlar oluşturabilir.

## <a name="createschedulegroup"></a>CreateScheduleGroup

Zamanlayıcı içinde yeni bir zamanlama grubu oluşturur. `_Placement` parametresini alan sürüm, yeni oluşturulan zamanlama grubundaki görevlerin Bu parametre tarafından belirtilen konumda yürütülmeye dahil edilmesine neden olur.

```cpp
virtual ScheduleGroup* CreateScheduleGroup() = 0;

virtual ScheduleGroup* CreateScheduleGroup(location& _Placement) = 0;
```

### <a name="parameters"></a>Parametreler

*_Placement*<br/>
Zamanlama grubundaki görevlerin ' de yürütmeye yaklaşmasına neden olacak bir konuma başvuru.

### <a name="return-value"></a>Dönüş Değeri

Yeni oluşturulan zamanlama grubuna yönelik bir işaretçi. Bu `ScheduleGroup` nesnesi, üzerine yerleştirilmiş bir başlangıç başvuru sayısına sahiptir.

### <a name="remarks"></a>Açıklamalar

İş planlaması yapıldığında, bir zamanlama grubundaki [Release](schedulegroup-class.md#release) metodunu çağırmanız gerekir. Sıraya alınan tüm işler tamamlandığında Zamanlayıcı, zamanlama grubunu yok eder.

Bu Scheduler 'ı açıkça oluşturduysanız, Zamanlayıcıdaki başvurularınızı serbest bırakmadan önce, içindeki zamanlama gruplarına tüm başvuruları serbest bırakmanız gerektiğini unutmayın.

## <a name="getnumberofvirtualprocessors"></a>GetNumberOfVirtualProcessors

Zamanlayıcı için geçerli sanal işlemci sayısını döndürür.

```cpp
virtual unsigned int GetNumberOfVirtualProcessors() const = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Zamanlayıcı için geçerli sanal işlemci sayısı.

## <a name="getpolicy"></a>GetPolicy

Scheduler 'ın ile oluşturulduğu ilkenin bir kopyasını döndürür.

```cpp
virtual SchedulerPolicy GetPolicy() const = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Scheduler 'ın ile oluşturulduğu ilkenin bir kopyası.

## <a name="id"></a>Numarasını

Zamanlayıcı için benzersiz bir tanımlayıcı döndürür.

```cpp
virtual unsigned int Id() const = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Zamanlayıcı için benzersiz bir tanımlayıcı.

## <a name="isavailablelocation"></a>IsAvailableLocation

Belirli bir konumun Scheduler 'da kullanılabilir olup olmadığını belirler.

```cpp
virtual bool IsAvailableLocation(const location& _Placement) const = 0;
```

### <a name="parameters"></a>Parametreler

*_Placement*<br/>
Scheduler 'ı sorgulayan konuma bir başvuru.

### <a name="return-value"></a>Dönüş Değeri

`_Placement` bağımsız değişkeni tarafından belirtilen konumun Zamanlayıcı üzerinde olup olmadığına ilişkin bir gösterge.

### <a name="remarks"></a>Açıklamalar

Dönüş değerinin, belirtilen konumun kullanılabilir olup olmadığına ilişkin anlık örnekleme olduğunu unutmayın. Birden çok zamanlayıcılar mevcut olduğunda, dinamik kaynak yönetimi herhangi bir noktada zamanlayıcılar 'ten kaynak ekleyebilir veya buradan kaynak alabilir. Bu durum, belirtilen konumun kullanılabilirliği değiştirebilmelidir.

## <a name="reference"></a>Başvurunun

Zamanlayıcı başvuru sayısını artırır.

```cpp
virtual unsigned int Reference() = 0 ;
```

### <a name="return-value"></a>Dönüş Değeri

Yeni artan başvuru sayısı.

### <a name="remarks"></a>Açıklamalar

Bu genellikle, oluşturma için Scheduler 'ın ömrünü yönetmek için kullanılır. Bir Scheduler 'ın başvuru sayısı sıfır olduğunda, Scheduler 'daki tüm çalışmalar tamamlandıktan sonra Zamanlayıcı kapanır ve yapısını kaldırır.

`Reference` yöntemi çağrılmadan önce başvuru sayısı sıfır ise ve Zamanlayıcı tarafından sahip olmayan bir içerikten çağrı yapılırsa Yöntem [improper_scheduler_reference](improper-scheduler-reference-class.md) bir özel durum oluşturur.

## <a name="registershutdownevent"></a>RegisterShutdownEvent

Zamanlayıcı kapandığında ve kendisini yok eder `_Event` parametresinde geçirilen Windows olay tanıtıcısına neden olur. Olaya işaret edilen zaman, Scheduler 'a zamanlanan tüm işler tamamlanmıştır. Birden çok kapanmaya yönelik olay, bu yöntem kullanılarak kaydedilebilir.

```cpp
virtual void RegisterShutdownEvent(HANDLE _Event) = 0;
```

### <a name="parameters"></a>Parametreler

*_Event*<br/>
Zamanlayıcı kapandığında çalışma zamanı tarafından işaret edilecek ve kendisini yok eden bir Windows olay nesnesi tutamacı.

## <a name="release"></a>Yayın

Zamanlayıcı başvuru sayısını azaltır.

```cpp
virtual unsigned int Release() = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Yeni küçültülenen başvuru sayısı.

### <a name="remarks"></a>Açıklamalar

Bu genellikle, oluşturma için Scheduler 'ın ömrünü yönetmek için kullanılır. Bir Scheduler 'ın başvuru sayısı sıfır olduğunda, Scheduler 'daki tüm çalışmalar tamamlandıktan sonra Zamanlayıcı kapanır ve yapısını kaldırır.

## <a name="resetdefaultschedulerpolicy"></a>ResetDefaultSchedulerPolicy

Varsayılan zamanlayıcı ilkesini çalışma zamanı varsayılan ayarlarına sıfırlar. Varsayılan bir Zamanlayıcı oluşturulduğunda, çalışma zamanı varsayılan ilke ayarlarını kullanır.

```cpp
static void __cdecl ResetDefaultSchedulerPolicy();
```

### <a name="remarks"></a>Açıklamalar

Bu yöntem, işlem içinde varsayılan bir Zamanlayıcı varken çağrılabilir. Var olan varsayılan Scheduler 'ın ilkesini etkilemez. Ancak, varsayılan Zamanlayıcı kapatılmaya çalışıyorsa ve sonraki bir noktada yeni bir varsayılan değer oluşturulacaksa, yeni zamanlayıcı çalışma zamanı varsayılan ilke ayarlarını kullanır.

## <a name="ctor"></a>Leyiciyi

`Scheduler` sınıfının bir nesnesi yalnızca Fabrika yöntemleri kullanılarak veya örtük olarak oluşturulabilir.

```cpp
Scheduler();
```

### <a name="remarks"></a>Açıklamalar

İşlem ' varsayılan Zamanlayıcı, bir Scheduler 'ın çağırma bağlamına eklenmesini gerektiren birçok çalışma zamanı işlevini kullandığınızda örtülü olarak oluşturulur. `CurrentScheduler` sınıfı ve PPL ve aracılar katmanlarının özellikleri içindeki yöntemler genellikle örtük ek gerçekleştirir.

Ayrıca, `CurrentScheduler::Create` yöntemi veya `Scheduler::Create` yöntemi aracılığıyla açıkça bir Zamanlayıcı oluşturabilirsiniz.

## <a name="dtor"></a>~ Scheduler

`Scheduler` sınıfının bir nesnesi, kendisine yapılan tüm dış başvurular mevcut olduğunda örtük olarak yok edilir.

```cpp
virtual ~Scheduler();
```

## <a name="scheduletask"></a>ScheduleTask

Zamanlayıcı içinde bir hafif görevi zamanlar. Hafif görev, çalışma zamanı tarafından belirlenen bir zamanlama grubuna yerleştirilir. `_Placement` parametresini alan sürüm, görevin belirtilen konumda yürütülerek aşağı doğru kaydırılmasına neden olur.

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

## <a name="setdefaultschedulerpolicy"></a>SetDefaultSchedulerPolicy

Varsayılan zamanlayıcıyı oluşturmak için Kullanıcı tanımlı bir ilkenin kullanılmasına izin verir. Bu yöntem yalnızca işlem içinde varsayılan Zamanlayıcı yoksa çağrılabilir. Varsayılan bir ilke ayarlandıktan sonra, `SetDefaultSchedulerPolicy` veya [ResetDefaultSchedulerPolicy](#resetdefaultschedulerpolicy) yöntemine bir sonraki geçerli çağrıya kadar yürürlükte kalır.

```cpp
static void __cdecl SetDefaultSchedulerPolicy(const SchedulerPolicy& _Policy);
```

### <a name="parameters"></a>Parametreler

*_Policy*<br/>
Varsayılan Zamanlayıcı İlkesi olarak ayarlanacak ilke.

### <a name="remarks"></a>Açıklamalar

İşlem içinde varsayılan bir Zamanlayıcı zaten mevcut olduğunda `SetDefaultSchedulerPolicy` yöntemi çağrılırsa, çalışma zamanı bir [default_scheduler_exists](default-scheduler-exists-class.md) özel durumu oluşturur.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)<br/>
[Zamanlayıcı Sınıfı](scheduler-class.md)<br/>
[PolicyElementKey](concurrency-namespace-enums.md)<br/>
[Görev Zamanlayıcı](../../../parallel/concrt/task-scheduler-concurrency-runtime.md)
