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
ms.openlocfilehash: f27dace61b0764962a78695c2a4c6b180b09d7a3
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57287912"
---
# <a name="scheduler-class"></a>Zamanlayıcı Sınıfı

Bir Özet için eşzamanlılık çalışma zamanı Zamanlayıcı temsil eder.

## <a name="syntax"></a>Sözdizimi

```
class Scheduler;
```

## <a name="members"></a>Üyeler

### <a name="protected-constructors"></a>Korumalı Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[Zamanlayıcı](#ctor)|Bir nesnenin `Scheduler` yalnızca Fabrika yöntemleri kullanılarak oluşturulan sınıfı olabilir ya da örtük olarak.|
|[~ Scheduler yok Edicisi](#dtor)|Bir nesnenin `Scheduler` sınıfı mevcut tüm dış başvuruları sona zaman örtük olarak yok.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Attach](#attach)|Zamanlayıcı için çağıran bağlamını ekler. Bu yöntemin dönüşünün ardından çağıran bağlamını Zamanlayıcı tarafından yönetilir ve geçerli Zamanlayıcı Zamanlayıcı olur.|
|[Oluşturma](#create)|Davranışı, tarafından açıklanmıştır yeni bir zamanlayıcı oluşturur `_Policy` parametresi, bir ilk başvuru zamanlayıcıda yerleştirir ve bir işaretçi döndürür.|
|[CreateScheduleGroup](#createschedulegroup)|Fazla Yüklendi. Zamanlayıcı içinde yeni bir zamanlama grubu oluşturur. Parametre sürüm `_Placement` görevleri bu parametre tarafından belirtilen konumda yürütme doğru güçlü eğilimi nedeniyle için yeni oluşturulan aynı zamanlama grubundaki neden olur.|
|[GetNumberOfVirtualProcessors](#getnumberofvirtualprocessors)|Geçerli sanal işlemci sayısı için Zamanlayıcıyı döndürür.|
|[GetPolicy](#getpolicy)|Zamanlayıcı ile oluşturulan ilkeyi bir kopyasını döndürür.|
|[Kimlik](#id)|Zamanlayıcı için benzersiz bir tanımlayıcı döndürür.|
|[Isavailablelocation](#isavailablelocation)|Belirli bir konuma Zamanlayıcı üzerinde kullanılabilir olup olmadığını belirler.|
|[Başvuru](#reference)|Zamanlayıcı başvuru sayısını artırır.|
|[RegisterShutdownEvent](#registershutdownevent)|Windows olay işleyici geçirilen nedenleri `_Event` Zamanlayıcı kapanır ve kendisini yok eder, sinyal parametresi. Olay sinyalini zaman, Zamanlayıcı için zamanlanan tüm iş tamamlanmıştır. Birden fazla kapatma olayları, bu yöntem kullanılarak kaydedilebilir.|
|[Sürüm](#release)|Zamanlayıcı başvuru sayısını azaltır.|
|[ResetDefaultSchedulerPolicy](#resetdefaultschedulerpolicy)|Varsayılan Zamanlayıcı ilkesini çalışma zamanı varsayılan ayarlarına sıfırlar. Varsayılan Zamanlayıcı oluşturulur, sonraki açışınızda, çalışma zamanı varsayılan ilke ayarlarını kullanın.|
|[ScheduleTask](#scheduletask)|Fazla Yüklendi. Zamanlayıcı hafif bir görevi zamanlar. Çalışma zamanı tarafından belirlenen bir zamanlama grubundaki hafif görev yerleştirilir. Parametre sürüm `_Placement` görevi belirtilen konumda yürütme doğru güçlü eğilimi nedeniyle neden olur.|
|[SetDefaultSchedulerPolicy](#setdefaultschedulerpolicy)|Varsayılan Zamanlayıcı oluşturmak için kullanılacak bir kullanıcı tanımlı ilke sağlar. Bu yöntem, hiçbir varsayılan Zamanlayıcı işlemde yalnızca mevcut olduğunda çağrılabilir. Varsayılan ilke olarak ayarlandıktan sonra yürürlükte ya da sonraki geçerli çağrı kadar kalır `SetDefaultSchedulerPolicy` veya [ResetDefaultSchedulerPolicy](#resetdefaultschedulerpolicy) yöntemi.|

## <a name="remarks"></a>Açıklamalar

Eşzamanlılık Çalışma zamanı Zamanlayıcısı'nı kullanan bir iş parçacığı gibi işletim sistemi yürütme bağlamları eşleyen yürütme bağlamları, işi yürütmek için kendisine uygulamanız tarafından sıraya alınan. Herhangi bir zamanda bir Zamanlayıcının eşzamanlılık düzeyi kaynak yöneticisi tarafından kendisine verilen sanal işlemci sayısına eşittir. Bir sanal işlemci için bir işlem kaynağı ve Haritalar ve alttaki sistemde bir donanım iş parçacığına bir soyutlamadır. Yalnızca tek bir zamanlayıcı bağlamı bir sanal işlemci üzerinde belirli bir zamanda çalıştırabilirsiniz.

Eşzamanlılık Çalışma zamanı, paralel iş yürütmek için varsayılan Zamanlayıcı işlem başına oluşturacaksınız. Buna ek olarak kendi Zamanlayıcı örnekleri oluşturmak ve bu sınıfı kullanarak işleme.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`Scheduler`

## <a name="requirements"></a>Gereksinimler

**Başlık:** concrt.h

**Namespace:** eşzamanlılık

##  <a name="attach"></a> Ekleme

Zamanlayıcı için çağıran bağlamını ekler. Bu yöntemin dönüşünün ardından çağıran bağlamını Zamanlayıcı tarafından yönetilir ve geçerli Zamanlayıcı Zamanlayıcı olur.

```
virtual void Attach() = 0;
```

### <a name="remarks"></a>Açıklamalar

Örtük olarak bir zamanlayıcı ekleme başvuru zamanlayıcıda yerleştirir.

Belirli bir noktada, gelecekte çağırmalıdır [CurrentScheduler::Detach](currentscheduler-class.md#detach) Zamanlayıcısı'nı kapatmak izin vermek için yöntemi.

Bu yöntem için farklı bir zamanlayıcı zaten eklenmiş bir bağlamdan çağrılırsa, var olan bir zamanlayıcı önceki Zamanlayıcı hatırlanır ve yeni oluşturulan Zamanlayıcı geçerli Zamanlayıcı olur. Çağırdığınızda `CurrentScheduler::Detach` önceki Zamanlayıcı daha sonraki bir noktada yöntemi geçerli Zamanlayıcı geri yüklenir.

Bu yöntemi bir [improper_scheduler_attach](improper-scheduler-attach-class.md) Bu zamanlayıcı çağrı bağlamının geçerli Zamanlayıcı ise özel durum.

##  <a name="create"></a> Oluşturma

Davranışı, tarafından açıklanmıştır yeni bir zamanlayıcı oluşturur `_Policy` parametresi, bir ilk başvuru zamanlayıcıda yerleştirir ve bir işaretçi döndürür.

```
static Scheduler* __cdecl Create(const SchedulerPolicy& _Policy);
```

### <a name="parameters"></a>Parametreler

*_İlkesi*<br/>
Zamanlayıcı ilke yeni oluşturulan Zamanlayıcı davranışını tanımlar.

### <a name="return-value"></a>Dönüş Değeri

Yeni oluşturulan bir zamanlayıcı işaretçisi. Bu `Scheduler` nesnesi üzerinde yerleştirilen bir ilk başvuru sayısını sahiptir.

### <a name="remarks"></a>Açıklamalar

Bir Zamanlayıcı ile oluşturulduktan sonra `Create` yöntemini çağırmalıdır `Release` gelecekte ilk başvuru sayısını kaldırmak ve kapatmak Zamanlayıcı izin vermek için belirli bir noktada yöntemi.

Bu yöntem ile oluşturulmuş bir zamanlayıcı çağrı bağlamına bağlı değil. Kullanarak bir bağlam eklenebilecek [iliştirme](#attach) yöntemi.

Bu yöntem, özel durumlar dahil olmak üzere, çeşitli oluşturabilecek [scheduler_resource_allocation_error](scheduler-resource-allocation-error-class.md) ve [invalid_scheduler_policy_value](invalid-scheduler-policy-value-class.md).

##  <a name="createschedulegroup"></a> CreateScheduleGroup

Zamanlayıcı içinde yeni bir zamanlama grubu oluşturur. Parametre sürüm `_Placement` görevleri bu parametre tarafından belirtilen konumda yürütme doğru güçlü eğilimi nedeniyle için yeni oluşturulan aynı zamanlama grubundaki neden olur.

```
virtual ScheduleGroup* CreateScheduleGroup() = 0;

virtual ScheduleGroup* CreateScheduleGroup(location& _Placement) = 0;
```

### <a name="parameters"></a>Parametreler

*Y_erleştirme*<br/>
Burada aynı zamanlama grubundaki görevlerin ağırlıklı sırasında yürütülen doğrultusunda bir konuma başvuru.

### <a name="return-value"></a>Dönüş Değeri

Yeni oluşturulan zamanlama grubu için bir işaretçi. Bu `ScheduleGroup` nesnesi üzerinde yerleştirilen bir ilk başvuru sayısını sahiptir.

### <a name="remarks"></a>Açıklamalar

Çağırmanız gerekir [yayın](schedulegroup-class.md#release) zamanlama iş tamamlandığında bir zamanlama grubu yöntemi. Zamanlayıcı zamanlamasını yok etmek için tüm işi kuyruğa atılmış grubu tamamlandı.

Bu zamanlayıcı açıkça oluşturduysanız, Zamanlayıcı üzerinde başvurularınızı yayımlamadan önce içinde gruplar zamanlamak için tüm başvurularını serbest bırakmalısınız unutmayın.

##  <a name="getnumberofvirtualprocessors"></a> GetNumberOfVirtualProcessors

Geçerli sanal işlemci sayısı için Zamanlayıcıyı döndürür.

```
virtual unsigned int GetNumberOfVirtualProcessors() const = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Zamanlayıcı için sanal işlemci sayısı.

##  <a name="getpolicy"></a> İlke alma

Zamanlayıcı ile oluşturulan ilkeyi bir kopyasını döndürür.

```
virtual SchedulerPolicy GetPolicy() const = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Zamanlayıcı ile oluşturulan ilkeyi bir kopyası.

##  <a name="id"></a> Kimliği

Zamanlayıcı için benzersiz bir tanımlayıcı döndürür.

```
virtual unsigned int Id() const = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Zamanlayıcı için benzersiz bir tanımlayıcı.

##  <a name="isavailablelocation"></a> Isavailablelocation

Belirli bir konuma Zamanlayıcı üzerinde kullanılabilir olup olmadığını belirler.

```
virtual bool IsAvailableLocation(const location& _Placement) const = 0;
```

### <a name="parameters"></a>Parametreler

*Y_erleştirme*<br/>
Zamanlayıcı hakkında sorgulamak için konumuna yönelik bir başvuru.

### <a name="return-value"></a>Dönüş Değeri

Bir gösterge olup olmadığına göre konumu belirtilen `_Placement` bağımsız değişken Zamanlayıcı üzerinde kullanılabilir.

### <a name="remarks"></a>Açıklamalar

Dönüş değeri, belirtilen konuma olup anlık bir örnekleme olduğuna dikkat edin. Birden çok zamanlayıcılar saklanacaktır dinamik kaynak yönetimi ekleyebilir veya herhangi bir noktada zamanlayıcılar gelen kaynakları çıkardığınız. Bu olacağını, belirtilen konuma kullanılabilirlik değiştirebilirsiniz.

##  <a name="reference"></a> Başvuru

Zamanlayıcı başvuru sayısını artırır.

```
virtual unsigned int Reference() = 0 ;
```

### <a name="return-value"></a>Dönüş Değeri

Yeni artan başvuru sayısı.

### <a name="remarks"></a>Açıklamalar

Bu, genellikle birleştirme için Zamanlayıcı ömrünü yönetmek için kullanılır. Ne zaman başvuru sayısı sıfıra Zamanlayıcı düştüğünde, Zamanlayıcı kapanır ve tüm iş Zamanlayıcısı destruct kendisini tamamlandı.

Yöntemi bir [improper_scheduler_reference](improper-scheduler-reference-class.md) çağırmadan önce başvuru sayısını özel durum `Reference` yöntemi sıfır ve Zamanlayıcı tarafından ait değil bir bağlamdan çağrı yapılır.

##  <a name="registershutdownevent"></a> RegisterShutdownEvent

Windows olay işleyici geçirilen nedenleri `_Event` Zamanlayıcı kapanır ve kendisini yok eder, sinyal parametresi. Olay sinyalini zaman, Zamanlayıcı için zamanlanan tüm iş tamamlanmıştır. Birden fazla kapatma olayları, bu yöntem kullanılarak kaydedilebilir.

```
virtual void RegisterShutdownEvent(HANDLE _Event) = 0;
```

### <a name="parameters"></a>Parametreler

*_Olay*<br/>
Zamanlayıcı kapanır ve kendisini yok eder bağlandığınızda çalışma zamanı tarafından sinyal Windows olay nesnesi için bir tanıtıcı.

##  <a name="release"></a> Yayın

Zamanlayıcı başvuru sayısını azaltır.

```
virtual unsigned int Release() = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Yeni indirildiği başvuru sayısı.

### <a name="remarks"></a>Açıklamalar

Bu, genellikle birleştirme için Zamanlayıcı ömrünü yönetmek için kullanılır. Ne zaman başvuru sayısı sıfıra Zamanlayıcı düştüğünde, Zamanlayıcı kapanır ve tüm iş Zamanlayıcısı destruct kendisini tamamlandı.

##  <a name="resetdefaultschedulerpolicy"></a> ResetDefaultSchedulerPolicy

Varsayılan Zamanlayıcı ilkesini çalışma zamanı varsayılan ayarlarına sıfırlar. Varsayılan Zamanlayıcı oluşturulur, sonraki açışınızda, çalışma zamanı varsayılan ilke ayarlarını kullanın.

```
static void __cdecl ResetDefaultSchedulerPolicy();
```

### <a name="remarks"></a>Açıklamalar

Varsayılan Zamanlayıcı işlem içinde bulunduğu sürece bu yöntem çağrılabilir. Var olan varsayılan Zamanlayıcı ilkesini etkilemez. Ancak, varsayılan Zamanlayıcı gibi kapatmaya ve yeni bir varsayılan bundan sonraki bir noktada oluşturulması, yeni Zamanlayıcı çalışma zamanı varsayılan ilkesi ayarlarını kullanmanız gerekir.

##  <a name="ctor"></a> Zamanlayıcı

Bir nesnenin `Scheduler` yalnızca Fabrika yöntemleri kullanılarak oluşturulan sınıfı olabilir ya da örtük olarak.

```
Scheduler();
```

### <a name="remarks"></a>Açıklamalar

İşlemin varsayılan Zamanlayıcı bir zamanlayıcı çağrı bağlamına bağlı olması gereken çalışma zamanı işlevlerin çoğunu yazılımınız örtük olarak oluşturulur. Yöntemlerinde `CurrentScheduler` sınıfı ve PPL ve aracıları katmanların özellikler genellikle örtük ek gerçekleştirir.

Bir zamanlayıcı açıkça ya da aracılığıyla da oluşturabilirsiniz `CurrentScheduler::Create` yöntemi veya `Scheduler::Create` yöntemi.

##  <a name="dtor"></a> ~ Scheduler

Bir nesnenin `Scheduler` sınıfı mevcut tüm dış başvuruları sona zaman örtük olarak yok.

```
virtual ~Scheduler();
```

##  <a name="scheduletask"></a> ScheduleTask

Zamanlayıcı hafif bir görevi zamanlar. Çalışma zamanı tarafından belirlenen bir zamanlama grubundaki hafif görev yerleştirilir. Parametre sürüm `_Placement` görevi belirtilen konumda yürütme doğru güçlü eğilimi nedeniyle neden olur.

```
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
İşlev gövdesi basit görev gerçekleştirmek için yürütmek için bir işaretçi.

*_Data*<br/>
Void bir işaretçi verilere gövdesi bir görev için bir parametre olarak geçirilir.

*Y_erleştirme*<br/>
Burada basit görev sırasında yürütülen doğru güçlü eğilimi nedeniyle bir konuma başvuru.

##  <a name="setdefaultschedulerpolicy"></a> SetDefaultSchedulerPolicy

Varsayılan Zamanlayıcı oluşturmak için kullanılacak bir kullanıcı tanımlı ilke sağlar. Bu yöntem, hiçbir varsayılan Zamanlayıcı işlemde yalnızca mevcut olduğunda çağrılabilir. Varsayılan ilke olarak ayarlandıktan sonra yürürlükte ya da sonraki geçerli çağrı kadar kalır `SetDefaultSchedulerPolicy` veya [ResetDefaultSchedulerPolicy](#resetdefaultschedulerpolicy) yöntemi.

```
static void __cdecl SetDefaultSchedulerPolicy(const SchedulerPolicy& _Policy);
```

### <a name="parameters"></a>Parametreler

*_İlkesi*<br/>
Varsayılan Zamanlayıcı ilke olarak ayarlanması için ilke.

### <a name="remarks"></a>Açıklamalar

Varsa `SetDefaultSchedulerPolicy` yöntemi çağrıldığında bir varsayılan Zamanlayıcı işlem içinde zaten mevcut olduğunda, çalışma zamanı bir [default_scheduler_exists](default-scheduler-exists-class.md) özel durum.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)<br/>
[Zamanlayıcı Sınıfı](scheduler-class.md)<br/>
[PolicyElementKey](concurrency-namespace-enums.md)<br/>
[Görev Zamanlayıcısı](../../../parallel/concrt/task-scheduler-concurrency-runtime.md)
