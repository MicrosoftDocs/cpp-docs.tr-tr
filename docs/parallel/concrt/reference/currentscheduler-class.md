---
title: CurrentScheduler sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- CurrentScheduler class
ms.assetid: 31c20e0e-4cdf-49b4-8220-d726130aad2b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 27c295f1cf8c6d02721a999c46ce02d961cc3702
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46419028"
---
# <a name="currentscheduler-class"></a>CurrentScheduler Sınıfı

Arama bağlamı ile ilişkili geçerli Zamanlayıcı için bir soyutlamayı temsil eder.

## <a name="syntax"></a>Sözdizimi

```
class CurrentScheduler;
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Oluşturma](#create)|Davranışı, tarafından açıklanmıştır yeni bir zamanlayıcı oluşturur `_Policy` parametresi ve çağrı bağlamına ekler. Yeni oluşturulan Zamanlayıcı arama bağlamı için geçerli Zamanlayıcı olur.|
|[CreateScheduleGroup](#createschedulegroup)|Fazla Yüklendi. Arama bağlamı ile ilişkili Zamanlayıcı içindeki yeni bir zamanlama grubu oluşturur. Parametre sürüm `_Placement` görevleri bu parametre tarafından belirtilen konumda yürütme doğru güçlü eğilimi nedeniyle için yeni oluşturulan aynı zamanlama grubundaki neden olur.|
|[Detach](#detach)|Arama bağlamı geçerli Zamanlayıcı ayırır ve varsa geçerli Zamanlayıcı olarak daha önce eklenen Zamanlayıcı geri yükler. Bu yöntemin dönüşünün ardından çağıran bağlamını ardından kullanarak bağlamı için daha önce eklendi Zamanlayıcı tarafından yönetilir `CurrentScheduler::Create` veya `Scheduler::Attach` yöntemi.|
|[Al](#get)|Geçerli bir zamanlayıcı da bilinir arama bağlamı ilişkili Zamanlayıcı bir işaretçi döndürür.|
|[GetNumberOfVirtualProcessors](#getnumberofvirtualprocessors)|Geçerli sanal işlemci sayısını, çağrı bağlamla ilişkili Zamanlayıcı döndürür.|
|[GetPolicy](#getpolicy)|Geçerli Zamanlayıcı ile oluşturulan ilkeyi bir kopyasını döndürür.|
|[Kimliği](#id)|Geçerli Zamanlayıcı için benzersiz bir tanımlayıcı döndürür.|
|[Isavailablelocation](#isavailablelocation)|Belirli bir konuma geçerli Zamanlayıcı üzerinde kullanılabilir olup olmadığını belirler.|
|[RegisterShutdownEvent](#registershutdownevent)|Windows olay işleyici geçirilen nedenleri `_ShutdownEvent` parametresi geçerli bağlam ile ilişkili Zamanlayıcı kapanır ve kendisini yok eder, sinyal. Olay sinyalini zaman, Zamanlayıcı için zamanlanan tüm iş tamamlanmıştır. Birden fazla kapatma olayları, bu yöntem kullanılarak kaydedilebilir.|
|[ScheduleTask](#scheduletask)|Fazla Yüklendi. Çağrı bağlamla ilişkili Zamanlayıcı hafif bir görevi zamanlar. Çalışma zamanı tarafından belirlenen bir zamanlama grubundaki hafif görev yerleştirilir. Parametre sürüm `_Placement` görevi belirtilen konumda yürütme doğru güçlü eğilimi nedeniyle neden olur.|

## <a name="remarks"></a>Açıklamalar

Hiçbir Zamanlayıcı ise (bkz [Zamanlayıcı](scheduler-class.md)) içinde birçok yöntem çağrı bağlamla ilişkili `CurrentScheduler` sınıf ek işlem varsayılan Zamanlayıcı neden olur. Bu işlem varsayılan Zamanlayıcı böyle bir çağrı sırasında oluşturduğunuz ayrıca olabileceğidir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CurrentScheduler`

## <a name="requirements"></a>Gereksinimler

**Başlık:** concrt.h

**Namespace:** eşzamanlılık

##  <a name="create"></a> Oluşturma

Davranışı, tarafından açıklanmıştır yeni bir zamanlayıcı oluşturur `_Policy` parametresi ve çağrı bağlamına ekler. Yeni oluşturulan Zamanlayıcı arama bağlamı için geçerli Zamanlayıcı olur.

```
static void __cdecl Create(const SchedulerPolicy& _Policy);
```

### <a name="parameters"></a>Parametreler

*_İlkesi*<br/>
Yeni oluşturulan Zamanlayıcı davranışını tanımlayan Zamanlayıcı ilke.

### <a name="remarks"></a>Açıklamalar

Zamanlayıcı ek arama bağlamı için bir başvuru sayısı zamanlayıcıda örtük olarak yerleştirir.

Bir Zamanlayıcı ile oluşturulduktan sonra `Create` yöntemini çağırmalıdır [CurrentScheduler::Detach](#detach) gelecekte Zamanlayıcısı'nı kapatmak izin vermek üzere belirli bir noktada yöntemi.

Bu yöntem için farklı bir zamanlayıcı zaten eklenmiş bir bağlamdan çağrılırsa, var olan bir zamanlayıcı önceki Zamanlayıcı hatırlanır ve yeni oluşturulan Zamanlayıcı geçerli Zamanlayıcı olur. Çağırdığınızda `CurrentScheduler::Detach` önceki Zamanlayıcı daha sonraki bir noktada yöntemi geçerli Zamanlayıcı geri yüklenir.

Bu yöntem, özel durumlar dahil olmak üzere, çeşitli oluşturabilecek [scheduler_resource_allocation_error](scheduler-resource-allocation-error-class.md) ve [invalid_scheduler_policy_value](invalid-scheduler-policy-value-class.md).

##  <a name="createschedulegroup"></a> CreateScheduleGroup

Arama bağlamı ile ilişkili Zamanlayıcı içindeki yeni bir zamanlama grubu oluşturur. Parametre sürüm `_Placement` görevleri bu parametre tarafından belirtilen konumda yürütme doğru güçlü eğilimi nedeniyle için yeni oluşturulan aynı zamanlama grubundaki neden olur.

```
static ScheduleGroup* __cdecl CreateScheduleGroup();

static ScheduleGroup* __cdecl CreateScheduleGroup(location& _Placement);
```

### <a name="parameters"></a>Parametreler

*Y_erleştirme*<br/>
Burada aynı zamanlama grubundaki görevlerin sırasında yürütülen doğru güçlü eğilimi nedeniyle bir konuma başvuru.

### <a name="return-value"></a>Dönüş Değeri

Yeni oluşturulan zamanlama grubu için bir işaretçi. Bu `ScheduleGroup` nesnesi üzerinde yerleştirilen bir ilk başvuru sayısını sahiptir.

### <a name="remarks"></a>Açıklamalar

Bu yöntem oluşturulan ve/veya şu anda çağrı bağlamla ilişkili hiçbir Zamanlayıcı ise çağrı bağlamına iliştirilemez. işlem varsayılan Zamanlayıcı neden olur.

Çağırmanız gerekir [yayın](schedulegroup-class.md#release) zamanlama iş tamamlandığında bir zamanlama grubu yöntemi. Zamanlayıcı zamanlamasını yok etmek için tüm işi kuyruğa atılmış grubu tamamlandı.

Bu zamanlayıcı açıkça oluşturduysanız, geçerli bağlamdan ayırıp başvurunuz Zamanlayıcı üzerinde yayımlamadan önce içinde gruplar zamanlamak için tüm başvurularını serbest bırakmalısınız unutmayın.

##  <a name="detach"></a> Ayırma

Arama bağlamı geçerli Zamanlayıcı ayırır ve varsa geçerli Zamanlayıcı olarak daha önce eklenen Zamanlayıcı geri yükler. Bu yöntemin dönüşünün ardından çağıran bağlamını ardından kullanarak bağlamı için daha önce eklendi Zamanlayıcı tarafından yönetilir `CurrentScheduler::Create` veya `Scheduler::Attach` yöntemi.

```
static void __cdecl Detach();
```

### <a name="remarks"></a>Açıklamalar

`Detach` Yöntemi Zamanlayıcıdan örtük bir başvuru sayısı kaldırır.

Çağrı bağlamına iliştirilemez hiçbir Zamanlayıcı ise, bu yöntemin çağrılması sonuçlanır bir [scheduler_not_attached](scheduler-not-attached-class.md) oluşturulan özel durum.

Bir bağlamından bu yöntemi çağırmak için iç ve yönetilen bir zamanlayıcı ya da başka bir yöntem kullanılarak bağlı bir bağlam [Scheduler::Attach](scheduler-class.md#attach) veya [CurrentScheduler::Create](#create) yöntemleri sonuçlanır bir [improper_scheduler_detach](improper-scheduler-detach-class.md) oluşturulan özel durum.

##  <a name="get"></a> Al

Geçerli bir zamanlayıcı da bilinir arama bağlamı ilişkili Zamanlayıcı bir işaretçi döndürür.

```
static Scheduler* __cdecl Get();
```

### <a name="return-value"></a>Dönüş Değeri

(Geçerli Zamanlayıcı) çağrı bağlamla ilişkili Zamanlayıcı işaretçisi.

### <a name="remarks"></a>Açıklamalar

Bu yöntem oluşturulan ve/veya şu anda çağrı bağlamla ilişkili hiçbir Zamanlayıcı ise çağrı bağlamına iliştirilemez. işlem varsayılan Zamanlayıcı neden olur. Ek başvuru yerleştirildiği `Scheduler` bu yöntem tarafından döndürülen nesne.

##  <a name="getnumberofvirtualprocessors"></a> GetNumberOfVirtualProcessors

Geçerli sanal işlemci sayısını, çağrı bağlamla ilişkili Zamanlayıcı döndürür.

```
static unsigned int __cdecl GetNumberOfVirtualProcessors();
```

### <a name="return-value"></a>Dönüş Değeri

Bir zamanlayıcı geçerli için zamanlayıcıda sanal işlemcilerin sayısı arama bağlamı ile ilişkili ise; Aksi takdirde, değeri `-1`.

### <a name="remarks"></a>Açıklamalar

Arama bağlamı zaten bir Zamanlayıcı ile ilişkili değilse, bu yöntem Zamanlayıcı ek neden olmaz.

Bu yöntemin dönüş değeri bir anlık örnekleme çağrı bağlamla ilişkili Zamanlayıcı için sanal işlemcilerin sayısı, ' dir. Bu değer, döndürülen şu eski olabilir.

##  <a name="getpolicy"></a> İlke alma

Geçerli Zamanlayıcı ile oluşturulan ilkeyi bir kopyasını döndürür.

```
static SchedulerPolicy __cdecl GetPolicy();
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli Zamanlayıcı ile oluşturulan ilkeyi bir kopyası.

### <a name="remarks"></a>Açıklamalar

Bu yöntem oluşturulan ve/veya şu anda çağrı bağlamla ilişkili hiçbir Zamanlayıcı ise çağrı bağlamına iliştirilemez. işlem varsayılan Zamanlayıcı neden olur.

##  <a name="id"></a> Kimliği

Geçerli Zamanlayıcı için benzersiz bir tanımlayıcı döndürür.

```
static unsigned int __cdecl Id();
```

### <a name="return-value"></a>Dönüş Değeri

Bir zamanlayıcı çağıran bağlamını, bu Zamanlayıcı için benzersiz bir tanımlayıcı ile ilişkili ise; Aksi takdirde, değeri `-1`.

### <a name="remarks"></a>Açıklamalar

Arama bağlamı zaten bir Zamanlayıcı ile ilişkili değilse, bu yöntem Zamanlayıcı ek neden olmaz.

##  <a name="isavailablelocation"></a> Isavailablelocation

Belirli bir konuma geçerli Zamanlayıcı üzerinde kullanılabilir olup olmadığını belirler.

```
static bool __cdecl IsAvailableLocation(const location& _Placement);
```

### <a name="parameters"></a>Parametreler

*Y_erleştirme*<br/>
Konumun geçerli Zamanlayıcı hakkında sorgulamak için bir başvuru.

### <a name="return-value"></a>Dönüş Değeri

Bir gösterge olup olmadığına göre konumu belirtilen `_Placement` bağımsız değişkeni geçerli bir zamanlayıcı üzerinde kullanılabilir.

### <a name="remarks"></a>Açıklamalar

Arama bağlamı zaten bir Zamanlayıcı ile ilişkili değilse, bu yöntem Zamanlayıcı ek neden olmaz.

Dönüş değeri, belirtilen konuma olup anlık bir örnekleme olduğuna dikkat edin. Birden çok zamanlayıcılar saklanacaktır dinamik kaynak yönetimi ekleyebilir veya herhangi bir noktada zamanlayıcılar gelen kaynakları çıkardığınız. Bu olacağını, belirtilen konuma kullanılabilirlik değiştirebilirsiniz.

##  <a name="registershutdownevent"></a> RegisterShutdownEvent

Windows olay işleyici geçirilen nedenleri `_ShutdownEvent` parametresi geçerli bağlam ile ilişkili Zamanlayıcı kapanır ve kendisini yok eder, sinyal. Olay sinyalini zaman, Zamanlayıcı için zamanlanan tüm iş tamamlanmıştır. Birden fazla kapatma olayları, bu yöntem kullanılarak kaydedilebilir.

```
static void __cdecl RegisterShutdownEvent(HANDLE _ShutdownEvent);
```

### <a name="parameters"></a>Parametreler

*_ShutdownEvent*<br/>
Geçerli bağlam ile ilişkili Zamanlayıcı kapanır ve kendisini yok eder bağlandığınızda çalışma zamanı tarafından sinyal Windows olay nesnesi için bir tanıtıcı.

### <a name="remarks"></a>Açıklamalar

Çağrı bağlamına iliştirilemez hiçbir Zamanlayıcı ise, bu yöntemin çağrılması sonuçlanır bir [scheduler_not_attached](scheduler-not-attached-class.md) oluşturulan özel durum.

##  <a name="scheduletask"></a> ScheduleTask

Çağrı bağlamla ilişkili Zamanlayıcı hafif bir görevi zamanlar. Çalışma zamanı tarafından belirlenen bir zamanlama grubundaki hafif görev yerleştirilir. Parametre sürüm `_Placement` görevi belirtilen konumda yürütme doğru güçlü eğilimi nedeniyle neden olur.

```
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
İşlev gövdesi basit görev gerçekleştirmek için yürütmek için bir işaretçi.

*_Veri*<br/>
Void bir işaretçi verilere gövdesi bir görev için bir parametre olarak geçirilir.

*Y_erleştirme*<br/>
Burada basit görev sırasında yürütülen doğru güçlü eğilimi nedeniyle bir konuma başvuru.

### <a name="remarks"></a>Açıklamalar

Bu yöntem oluşturulan ve/veya şu anda çağrı bağlamla ilişkili hiçbir Zamanlayıcı ise çağrı bağlamına iliştirilemez. işlem varsayılan Zamanlayıcı neden olur.

## <a name="see-also"></a>Ayrıca Bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)<br/>
[Zamanlayıcı Sınıfı](scheduler-class.md)<br/>
[PolicyElementKey](concurrency-namespace-enums.md)<br/>
[Görev Zamanlayıcısı](../../../parallel/concrt/task-scheduler-concurrency-runtime.md)

