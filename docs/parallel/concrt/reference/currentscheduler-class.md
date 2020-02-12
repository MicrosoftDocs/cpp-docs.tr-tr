---
title: CurrentScheduler Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CurrentScheduler
- CONCRT/concurrency::CurrentScheduler
- CONCRT/concurrency::CurrentScheduler::Create
- CONCRT/concurrency::CurrentScheduler::CreateScheduleGroup
- CONCRT/concurrency::CurrentScheduler::Detach
- CONCRT/concurrency::CurrentScheduler::Get
- CONCRT/concurrency::CurrentScheduler::GetNumberOfVirtualProcessors
- CONCRT/concurrency::CurrentScheduler::GetPolicy
- CONCRT/concurrency::CurrentScheduler::Id
- CONCRT/concurrency::CurrentScheduler::IsAvailableLocation
- CONCRT/concurrency::CurrentScheduler::RegisterShutdownEvent
- CONCRT/concurrency::CurrentScheduler::ScheduleTask
helpviewer_keywords:
- CurrentScheduler class
ms.assetid: 31c20e0e-4cdf-49b4-8220-d726130aad2b
ms.openlocfilehash: 6bf61af9ff55722553353a045c87501dbd27fad9
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77143072"
---
# <a name="currentscheduler-class"></a>CurrentScheduler Sınıfı

Çağıran bağlamla ilişkili geçerli Zamanlayıcı için bir soyutlama temsil eder.

## <a name="syntax"></a>Sözdizimi

```cpp
class CurrentScheduler;
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Oluşturma](#create)|Davranışı `_Policy` parametresi tarafından tanımlanan ve bunu çağıran bağlama bağlayan yeni bir zamanlayıcı oluşturur. Yeni oluşturulan Zamanlayıcı, çağıran bağlam için geçerli Zamanlayıcı olur.|
|[CreateScheduleGroup](#createschedulegroup)|Fazla Yüklendi. Çağırma bağlamıyla ilişkili Zamanlayıcı içinde yeni bir zamanlama grubu oluşturur. `_Placement` parametresini alan sürüm, yeni oluşturulan zamanlama grubundaki görevlerin Bu parametre tarafından belirtilen konumda yürütülmeye dahil edilmesine neden olur.|
|[Detach](#detach)|Geçerli zamanlayıcıyı çağıran bağlamdan ayırır ve varsa, önceden eklenmiş olan zamanlayıcıyı geçerli Zamanlayıcı olarak geri yükler. Bu yöntem çağrıldıktan sonra, çağıran bağlam daha önce `CurrentScheduler::Create` veya `Scheduler::Attach` yöntemi kullanılarak bağlama eklenmiş olan Zamanlayıcı tarafından yönetilir.|
|[Get](#get)|Geçerli Zamanlayıcı olarak da adlandırılan çağırma bağlamıyla ilişkili Scheduler 'a bir işaretçi döndürür.|
|[GetNumberOfVirtualProcessors](#getnumberofvirtualprocessors)|Çağıran bağlamla ilişkili Zamanlayıcı için geçerli sanal işlemci sayısını döndürür.|
|[GetPolicy](#getpolicy)|Geçerli Scheduler 'ın birlikte oluşturulduğu ilkenin bir kopyasını döndürür.|
|[Kimlik](#id)|Geçerli Zamanlayıcı için benzersiz bir tanımlayıcı döndürür.|
|[IsAvailableLocation](#isavailablelocation)|Belirli bir konumun geçerli Scheduler 'da kullanılabilir olup olmadığını belirler.|
|[RegisterShutdownEvent](#registershutdownevent)|Geçerli bağlamla ilişkilendirilen Zamanlayıcı kapandığı ve kendisi yok edildiğinde `_ShutdownEvent` parametresinde geçirilen Windows olay tanıtıcısına neden olur. Olaya işaret edilen zaman, Scheduler 'a zamanlanan tüm işler tamamlanmıştır. Birden çok kapanmaya yönelik olay, bu yöntem kullanılarak kaydedilebilir.|
|[ScheduleTask](#scheduletask)|Fazla Yüklendi. Çağırma bağlamıyla ilişkili Zamanlayıcı içinde bir hafif görevi zamanlar. Hafif görev, çalışma zamanı tarafından belirlenen bir zamanlama grubuna yerleştirilir. `_Placement` parametresini alan sürüm, görevin belirtilen konumda yürütülerek aşağı doğru kaydırılmasına neden olur.|

## <a name="remarks"></a>Açıklamalar

Çağıran bağlamla ilişkili Zamanlayıcı (bkz. [Zamanlayıcı](scheduler-class.md)) yoksa, `CurrentScheduler` sınıftaki birçok yöntem, işlemin varsayılan Zamanlayıcı ' ya ek olarak sonuçlanır. Bu Ayrıca, bu tür bir çağrı sırasında işlemin varsayılan Scheduler ' un oluşturulduğunu da gösterebilir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CurrentScheduler`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** concrt. h

**Ad alanı:** eşzamanlılık

## <a name="create"></a>Oluşturma

Davranışı `_Policy` parametresi tarafından tanımlanan ve bunu çağıran bağlama bağlayan yeni bir zamanlayıcı oluşturur. Yeni oluşturulan Zamanlayıcı, çağıran bağlam için geçerli Zamanlayıcı olur.

```cpp
static void __cdecl Create(const SchedulerPolicy& _Policy);
```

### <a name="parameters"></a>Parametreler

*_Policy*<br/>
Yeni oluşturulan Scheduler 'un davranışını açıklayan Zamanlayıcı İlkesi.

### <a name="remarks"></a>Açıklamalar

Zamanlayıcı eki, çağırma bağlamına dolaylı olarak bir başvuru sayısı koyar.

`Create` yöntemiyle bir Zamanlayıcı oluşturulduktan sonra, Scheduler 'ın kapanmasına izin vermek için gelecekteki bir noktada [CurrentScheduler::D etach](#detach) yöntemini çağırmanız gerekir.

Bu yöntem, farklı bir zamanlayıcıya zaten bağlı olan bir içerikten çağrılırsa, mevcut Zamanlayıcı önceki Zamanlayıcı olarak hatırlanır ve yeni oluşturulan Zamanlayıcı geçerli Zamanlayıcı olur. `CurrentScheduler::Detach` yöntemini sonraki bir noktada çağırdığınızda, önceki Zamanlayıcı geçerli Zamanlayıcı olarak geri yüklenir.

Bu yöntem [scheduler_resource_allocation_error](scheduler-resource-allocation-error-class.md) ve [invalid_scheduler_policy_value](invalid-scheduler-policy-value-class.md)dahil olmak üzere çeşitli özel durumlar oluşturabilir.

## <a name="createschedulegroup"></a>CreateScheduleGroup

Çağırma bağlamıyla ilişkili Zamanlayıcı içinde yeni bir zamanlama grubu oluşturur. `_Placement` parametresini alan sürüm, yeni oluşturulan zamanlama grubundaki görevlerin Bu parametre tarafından belirtilen konumda yürütülmeye dahil edilmesine neden olur.

```cpp
static ScheduleGroup* __cdecl CreateScheduleGroup();

static ScheduleGroup* __cdecl CreateScheduleGroup(location& _Placement);
```

### <a name="parameters"></a>Parametreler

*_Placement*<br/>
Zamanlama grubundaki görevlerin ' de yürütmeye doğru olacağı konuma bir başvuru.

### <a name="return-value"></a>Dönüş Değeri

Yeni oluşturulan zamanlama grubuna yönelik bir işaretçi. Bu `ScheduleGroup` nesnesi, üzerine yerleştirilmiş bir başlangıç başvuru sayısına sahiptir.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, şu anda çağıran bağlamla ilişkili bir Zamanlayıcı yoksa, işlemin varsayılan Zamanlayıcı oluşturulması ve/veya çağırma bağlamına iliştirilmesi ile sonuçlanır.

İş planlaması yapıldığında, bir zamanlama grubundaki [Release](schedulegroup-class.md#release) metodunu çağırmanız gerekir. Sıraya alınan tüm işler tamamlandığında Zamanlayıcı, zamanlama grubunu yok eder.

Bu Zamanlayıcı 'yı açık bir şekilde oluşturduysanız, geçerli bağlamı bundan ayırarak Zamanlayıcı üzerinde başvuru yapmadan önce, içindeki zamanlama gruplarına tüm başvuruları serbest bırakmanız gerektiğini unutmayın.

## <a name="detach"></a>Ayırmak

Geçerli zamanlayıcıyı çağıran bağlamdan ayırır ve varsa, önceden eklenmiş olan zamanlayıcıyı geçerli Zamanlayıcı olarak geri yükler. Bu yöntem çağrıldıktan sonra, çağıran bağlam daha önce `CurrentScheduler::Create` veya `Scheduler::Attach` yöntemi kullanılarak bağlama eklenmiş olan Zamanlayıcı tarafından yönetilir.

```cpp
static void __cdecl Detach();
```

### <a name="remarks"></a>Açıklamalar

`Detach` yöntemi, Scheduler 'dan bir başvuru sayısını örtülü olarak kaldırır.

Çağıran bağlama bağlı bir Zamanlayıcı yoksa, bu yöntemi çağırmak [scheduler_not_attached](scheduler-not-attached-class.md) bir özel durum oluşmasına neden olur.

Bu yöntemi bir Zamanlayıcı tarafından dahili ve yönetilen bir içerikten veya [Scheduler:: Attach](scheduler-class.md#attach) veya [CurrentScheduler:: Create](#create) yöntemlerinin dışında bir yöntem kullanılarak eklenmiş bir bağlamdan çağırmak, [improper_scheduler_detach](improper-scheduler-detach-class.md) bir özel durum oluşmasına neden olur.

## <a name="get"></a>Al

Geçerli Zamanlayıcı olarak da adlandırılan çağırma bağlamıyla ilişkili Scheduler 'a bir işaretçi döndürür.

```cpp
static Scheduler* __cdecl Get();
```

### <a name="return-value"></a>Dönüş Değeri

Çağırma bağlamıyla ilişkili Zamanlayıcı işaretçisi (geçerli Zamanlayıcı).

### <a name="remarks"></a>Açıklamalar

Bu yöntem, şu anda çağıran bağlamla ilişkili bir Zamanlayıcı yoksa, işlemin varsayılan Zamanlayıcı oluşturulması ve/veya çağırma bağlamına iliştirilmesi ile sonuçlanır. Bu yöntem tarafından döndürülen `Scheduler` nesnesine ek başvuru yerleştirilmemiş.

## <a name="getnumberofvirtualprocessors"></a>GetNumberOfVirtualProcessors

Çağıran bağlamla ilişkili Zamanlayıcı için geçerli sanal işlemci sayısını döndürür.

```cpp
static unsigned int __cdecl GetNumberOfVirtualProcessors();
```

### <a name="return-value"></a>Dönüş Değeri

Bir Zamanlayıcı çağıran bağlamla ilişkiliyse, bu Zamanlayıcı için geçerli sanal işlemci sayısı; Aksi takdirde değer `-1`.

### <a name="remarks"></a>Açıklamalar

Çağıran bağlam zaten bir zamanlayıcı ile ilişkili değilse, bu yöntem Zamanlayıcı eki ile sonuçlanmaz.

Bu yöntemden döndürülen değer, çağırma bağlamıyla ilişkili Scheduler için sanal işlemcilerin sayısının anlık örneklemesi olur. Bu değer, geri dönülen andan itibaren eski olabilir.

## <a name="getpolicy"></a>GetPolicy

Geçerli Scheduler 'ın birlikte oluşturulduğu ilkenin bir kopyasını döndürür.

```cpp
static SchedulerPolicy __cdecl GetPolicy();
```

### <a name="return-value"></a>Dönüş Değeri

İlkenin geçerli Scheduler ile oluşturulduğu bir kopyası.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, şu anda çağıran bağlamla ilişkili bir Zamanlayıcı yoksa, işlemin varsayılan Zamanlayıcı oluşturulması ve/veya çağırma bağlamına iliştirilmesi ile sonuçlanır.

## <a name="id"></a>Numarasını

Geçerli Zamanlayıcı için benzersiz bir tanımlayıcı döndürür.

```cpp
static unsigned int __cdecl Id();
```

### <a name="return-value"></a>Dönüş Değeri

Bir Zamanlayıcı çağıran bağlamla ilişkiliyse, bu Zamanlayıcı için benzersiz bir tanımlayıcı; Aksi takdirde değer `-1`.

### <a name="remarks"></a>Açıklamalar

Çağıran bağlam zaten bir zamanlayıcı ile ilişkili değilse, bu yöntem Zamanlayıcı eki ile sonuçlanmaz.

## <a name="isavailablelocation"></a>IsAvailableLocation

Belirli bir konumun geçerli Scheduler 'da kullanılabilir olup olmadığını belirler.

```cpp
static bool __cdecl IsAvailableLocation(const location& _Placement);
```

### <a name="parameters"></a>Parametreler

*_Placement*<br/>
Geçerli Scheduler ile ilgili sorgulama yapılacak konuma bir başvuru.

### <a name="return-value"></a>Dönüş Değeri

`_Placement` bağımsız değişkeni tarafından belirtilen konumun geçerli Zamanlayıcı üzerinde olup olmadığına ilişkin bir gösterge.

### <a name="remarks"></a>Açıklamalar

Çağıran bağlam zaten bir zamanlayıcı ile ilişkili değilse, bu yöntem Zamanlayıcı eki ile sonuçlanmaz.

Dönüş değerinin, belirtilen konumun kullanılabilir olup olmadığına ilişkin anlık örnekleme olduğunu unutmayın. Birden çok zamanlayıcılar mevcut olduğunda, dinamik kaynak yönetimi herhangi bir noktada zamanlayıcılar 'ten kaynak ekleyebilir veya buradan kaynak alabilir. Bu durum, belirtilen konumun kullanılabilirliği değiştirebilmelidir.

## <a name="registershutdownevent"></a>RegisterShutdownEvent

Geçerli bağlamla ilişkilendirilen Zamanlayıcı kapandığı ve kendisi yok edildiğinde `_ShutdownEvent` parametresinde geçirilen Windows olay tanıtıcısına neden olur. Olaya işaret edilen zaman, Scheduler 'a zamanlanan tüm işler tamamlanmıştır. Birden çok kapanmaya yönelik olay, bu yöntem kullanılarak kaydedilebilir.

```cpp
static void __cdecl RegisterShutdownEvent(HANDLE _ShutdownEvent);
```

### <a name="parameters"></a>Parametreler

*_ShutdownEvent*<br/>
Geçerli bağlamla ilişkilendirilen Zamanlayıcı kapandığı ve kendisini yok eden, çalışma zamanı tarafından sinyallendirilebilen bir Windows Event nesnesine yönelik bir tanıtıcıdır.

### <a name="remarks"></a>Açıklamalar

Çağıran bağlama bağlı bir Zamanlayıcı yoksa, bu yöntemi çağırmak [scheduler_not_attached](scheduler-not-attached-class.md) bir özel durum oluşmasına neden olur.

## <a name="scheduletask"></a>ScheduleTask

Çağırma bağlamıyla ilişkili Zamanlayıcı içinde bir hafif görevi zamanlar. Hafif görev, çalışma zamanı tarafından belirlenen bir zamanlama grubuna yerleştirilir. `_Placement` parametresini alan sürüm, görevin belirtilen konumda yürütülerek aşağı doğru kaydırılmasına neden olur.

```cpp
static void __cdecl ScheduleTask(
    TaskProc _Proc,
    _Inout_opt_ void* _Data);

static void __cdecl ScheduleTask(
    TaskProc _Proc,
    _Inout_opt_ void* _Data,
    location& _Placement);
```

### <a name="parameters"></a>Parametreler

*_Proc*<br/>
Hafif görevin gövdesini gerçekleştirmek için yürütülecek işleve yönelik bir işaretçi.

*_Data*<br/>
Görevin gövdesine parametre olarak geçirilecek verilerin void işaretçisi.

*_Placement*<br/>
Hafif bir görevin, üzerinde yürütülmesi için yüz aşağı olacağı bir konuma başvuru.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, şu anda çağıran bağlamla ilişkili bir Zamanlayıcı yoksa, işlemin varsayılan Zamanlayıcı oluşturulması ve/veya çağırma bağlamına iliştirilmesi ile sonuçlanır.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)<br/>
[Zamanlayıcı Sınıfı](scheduler-class.md)<br/>
[PolicyElementKey](concurrency-namespace-enums.md)<br/>
[Görev Zamanlayıcı](../../../parallel/concrt/task-scheduler-concurrency-runtime.md)
