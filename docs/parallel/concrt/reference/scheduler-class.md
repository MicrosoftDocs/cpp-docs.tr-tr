---
title: Zamanlayıcı sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- Scheduler class
ms.assetid: 34cf7961-048d-4852-8a5c-a32f823e3506
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 97abec33d5fa4b372bc26874fd37397a2b78bb29
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
---
# <a name="scheduler-class"></a>Zamanlayıcı Sınıfı
Bir Özet bir eşzamanlılık çalışma zamanı Zamanlayıcısı temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
class Scheduler;
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="protected-constructors"></a>Korumalı Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[Zamanlayıcı](#ctor)|Bir nesnenin `Scheduler` sınıfı için Fabrika yöntemleri kullanılarak oluşturulan yalnızca ya da örtük olarak.|  
|[~ Scheduler yok Edicisi](#dtor)|Bir nesnenin `Scheduler` sınıfı tüm dış başvuruları mevcut çalışmayı zaman örtük olarak yok.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[Attach](#attach)|Zamanlayıcı çağıran bağlamını ekler. Bu yöntem döndükten sonra çağıran bağlamını Zamanlayıcı tarafından yönetilir ve geçerli Zamanlayıcı Zamanlayıcı olur.|  
|[Oluşturma](#create)|Tarafından davranışı açıklanan yeni bir zamanlayıcı oluşturur `_Policy` parametresi, ilk başvuru zamanlayıcıda yerleştirir ve devre dışı bir işaretçi döndürür.|  
|[CreateScheduleGroup](#createschedulegroup)|Fazla Yüklendi. Zamanlayıcı içinde yeni bir zamanlama grubu oluşturur. Parametresi alan sürüm `_Placement` görevleri bu parametresi tarafından belirtilen konumda yürütme doğrultusunda ağırlıklı için yeni oluşturulan zamanlama grubundaki neden olur.|  
|[GetNumberOfVirtualProcessors](#getnumberofvirtualprocessors)|Sanal işlemcilerin sayısı için Zamanlayıcı'yı döndürür.|  
|[GetPolicy](#getpolicy)|Zamanlayıcı ile oluşturulduğundan İlkesi kopyasını döndürür.|  
|[Kimliği](#id)|Zamanlayıcı için benzersiz bir tanımlayıcı döndürür.|  
|[Isavailablelocation](#isavailablelocation)|Verilen bir konuma Zamanlayıcı üzerinde kullanılabilir olup olmadığını belirler.|  
|[Başvuru](#reference)|Zamanlayıcı başvurusu sayısını artırır.|  
|[RegisterShutdownEvent](#registershutdownevent)|Windows olay işleyici geçirilen nedenler `_Event` Zamanlayıcı kapanır ve kendisini bozar bildirilmesini parametresi. Olay işaret zamanında Zamanlayıcı için zamanlanan tüm iş tamamlanır. Birden fazla kapatma olayları bu yöntemle kaydedilebilir.|  
|[Sürüm](#release)|Azaltır Zamanlayıcı başvuru sayısı.|  
|[ResetDefaultSchedulerPolicy](#resetdefaultschedulerpolicy)|Varsayılan Zamanlayıcı ilke çalışma zamanı varsayılan olarak sıfırlar. Bir varsayılan Zamanlayıcısı'nı bir sonraki oluşturulduğunda, çalışma zamanı varsayılan ilke ayarlarını kullanır.|  
|[ScheduleTask](#scheduletask)|Fazla Yüklendi. Hafif Görev Zamanlayıcı içinde zamanlar. Hafif görev çalışma zamanı tarafından belirlenen bir zamanlama grubunda yer alır. Parametresi alan sürüm `_Placement` görev belirtilen konumda yürütme doğrultusunda ağırlıklı neden olur.|  
|[SetDefaultSchedulerPolicy](#setdefaultschedulerpolicy)|Varsayılan Zamanlayıcı oluşturmak için kullanılacak bir kullanıcı tanımlı ilke sağlar. Bu yöntem yalnızca varsayılan Zamanlayıcı işlemi içinde mevcut olduğunda çağrılabilir. Varsayılan bir ilke ayarladıktan sonra etkin ya da sonraki geçerli çağrısı kadar kalır `SetDefaultSchedulerPolicy` veya [ResetDefaultSchedulerPolicy](#resetdefaultschedulerpolicy) yöntemi.|  
  
## <a name="remarks"></a>Açıklamalar  
 İş yürütmek için kendisine uygulamanız tarafından sıraya alınan, işletim sistemi yürütme bağlamı, bir iş parçacığı gibi Eşle yürütme bağlamı eşzamanlılık çalışma zamanı Zamanlayıcısı'nı kullanır. Herhangi bir zamanda bir zamanlayıcı eşzamanlılık düzeyi için kaynak yöneticisi tarafından verilen sanal işlemci sayısına eşittir. Bir sanal işlemcinin bir işlem kaynağı ve temeldeki sistemi donanım parçacığında eşlenir bir soyutlamadır. Yalnızca tek Zamanlayıcı bağlamında bir sanal işlemcinin üzerinde belirli bir zamanda çalıştırabilirsiniz.  
  
 Eşzamanlılık Çalışma Zamanı paralel iş yürütmek için varsayılan Zamanlayıcı işlem başına oluşturur. Ayrıca kendi Zamanlayıcı örnekleri oluşturmak ve bu sınıfı kullanarak düzenleyebilirsiniz.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `Scheduler`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** concrt.h  
  
 **Namespace:** eşzamanlılık  
  
##  <a name="attach"></a> Ekleme 

 Zamanlayıcı çağıran bağlamını ekler. Bu yöntem döndükten sonra çağıran bağlamını Zamanlayıcı tarafından yönetilir ve geçerli Zamanlayıcı Zamanlayıcı olur.  
  
```
virtual void Attach() = 0;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bir zamanlayıcı örtük olarak ekleyerek bir başvuru zamanlayıcıda yerleştirir.  
  
 Belirli bir noktada gelecekte çağırmalısınız [CurrentScheduler::Detach](currentscheduler-class.md#detach) Zamanlayıcısı'nı kapatmak izin vermek üzere yöntemi.  
  
 Bu yöntem için farklı bir zamanlayıcı zaten eklenmiş bir bağlamından çağrılırsa, varolan Zamanlayıcı önceki Zamanlayıcı hatırlanan ve yeni oluşturulan Zamanlayıcı geçerli Zamanlayıcı olur. Çağırdığınızda `CurrentScheduler::Detach` önceki Zamanlayıcı sonraki bir zamanda yöntemi geçerli Zamanlayıcı geri.  
  
 Bu yöntemi özel durum oluşturacak bir [improper_scheduler_attach](improper-scheduler-attach-class.md) Bu zamanlayıcı çağıran bağlamını geçerli Zamanlayıcı ise özel durum.  
  
##  <a name="create"></a> Oluşturma 

 Tarafından davranışı açıklanan yeni bir zamanlayıcı oluşturur `_Policy` parametresi, ilk başvuru zamanlayıcıda yerleştirir ve devre dışı bir işaretçi döndürür.  
  
```
static Scheduler* __cdecl Create(const SchedulerPolicy& _Policy);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Policy`  
 Yeni oluşturulan Zamanlayıcı davranışını tanımlayan Zamanlayıcı ilke.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yeni oluşturulan bir zamanlayıcı için bir işaretçi. Bu `Scheduler` nesnesi üzerinde yerleştirilen bir ilk başvuru sayısı sahiptir.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir Zamanlayıcı ile oluşturulduktan sonra `Create` yöntemi, çağırmalıdır `Release` gelecekte ilk başvuru sayısı kaldırıp Zamanlayıcısı'nı kapatmak izin vermek için belirli bir noktada yöntemi.  
  
 Bu yöntem ile oluşturulan bir zamanlayıcı arama bağlamına bağlı değil. Kullanarak bir bağlam eklenebilecek [Attach](#attach) yöntemi.  
  
 Bu yöntemi özel durumlar dahil olmak üzere, çeşitli atabilirsiniz [scheduler_resource_allocation_error](scheduler-resource-allocation-error-class.md) ve [invalid_scheduler_policy_value](invalid-scheduler-policy-value-class.md).  
  
##  <a name="createschedulegroup"></a> CreateScheduleGroup 

 Zamanlayıcı içinde yeni bir zamanlama grubu oluşturur. Parametresi alan sürüm `_Placement` görevleri bu parametresi tarafından belirtilen konumda yürütme doğrultusunda ağırlıklı için yeni oluşturulan zamanlama grubundaki neden olur.  
  
```
virtual ScheduleGroup* CreateScheduleGroup() = 0;

virtual ScheduleGroup* CreateScheduleGroup(location& _Placement) = 0;
```  
  
### <a name="parameters"></a>Parametreler  
 `_Placement`  
 Zamanlama grup içindeki görevleri burada ağırlıklı adresindeki yürütme doğru bir konuma başvuru.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yeni oluşturulan zamanlama grup için bir işaretçi. Bu `ScheduleGroup` nesnesi üzerinde yerleştirilen bir ilk başvuru sayısı sahiptir.  
  
### <a name="remarks"></a>Açıklamalar  
 Çağırmanız gerekir [sürüm](schedulegroup-class.md#release) zamanlama işi bittiğinde zamanlama grubunda yöntemi. Zamanlayıcı zamanlama silecektir tüm iş kuyruğa sırasında grubu tamamlandı.  
  
 Bu zamanlayıcı açıkça oluşturduysanız, Zamanlayıcı, başvurular bırakmadan önce içinde gruplar zamanlamak için tüm başvurularını serbest bırakmalısınız unutmayın.  
  
##  <a name="getnumberofvirtualprocessors"></a> GetNumberOfVirtualProcessors 

 Sanal işlemcilerin sayısı için Zamanlayıcı'yı döndürür.  
  
```
virtual unsigned int GetNumberOfVirtualProcessors() const = 0;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sanal işlemciler Zamanlayıcı için geçerli sayısı.  
  
##  <a name="getpolicy"></a> GetPolicy 

 Zamanlayıcı ile oluşturulduğundan İlkesi kopyasını döndürür.  
  
```
virtual SchedulerPolicy GetPolicy() const = 0;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Zamanlayıcı ile oluşturulduğundan İlkesi kopyası.  
  
##  <a name="id"></a> Kimliği 

 Zamanlayıcı için benzersiz bir tanımlayıcı döndürür.  
  
```
virtual unsigned int Id() const = 0;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Zamanlayıcı için benzersiz bir tanımlayıcı.  
  
##  <a name="isavailablelocation"></a> Isavailablelocation 

 Verilen bir konuma Zamanlayıcı üzerinde kullanılabilir olup olmadığını belirler.  
  
```
virtual bool IsAvailableLocation(const location& _Placement) const = 0;
```  
  
### <a name="parameters"></a>Parametreler  
 `_Placement`  
 Konumun hakkında Zamanlayıcı sorgulamak için bir başvuru.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Konumun belirttiği olup olmadığına ilişkin bir gösterge `_Placement` bağımsız değişkeni Zamanlayıcı üzerinde kullanılabilir.  
  
### <a name="remarks"></a>Açıklamalar  
 Dönüş değeri bir anlık örnekleme belirtilen konum kullanılabilir olup olmadığını unutmayın. Birden çok zamanlayıcılar varlığında dinamik kaynak yönetimi ekleyebilir veya kaynakları herhangi bir noktada zamanlayıcılar gelen çıkardığınız. Bu olacağını, belirtilen konum kullanılabilirlik değiştirebilirsiniz.  
  
##  <a name="reference"></a> Başvuru 

 Zamanlayıcı başvurusu sayısını artırır.  
  
```
virtual unsigned int Reference() = 0 ;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yeni artırılır başvuru sayısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu, genellikle Zamanlayıcı oluşturma için kullanım ömrünü yönetmek için kullanılır. Ne zaman sıfıra Zamanlayıcı düştüğünde başvuru sayısı, Zamanlayıcı kapanacak ve destruct kendisini zamanlayıcıda tüm iş tamamlandı.  
  
 Yöntemi özel durum oluşturacak bir [improper_scheduler_reference](improper-scheduler-reference-class.md) önce arama başvuru sayısı, özel durum `Reference` yöntemi sıfır ve Zamanlayıcı tarafından sahiplenilmedi bağlamından çağrı yapılır.  
  
##  <a name="registershutdownevent"></a> RegisterShutdownEvent 

 Windows olay işleyici geçirilen nedenler `_Event` Zamanlayıcı kapanır ve kendisini bozar bildirilmesini parametresi. Olay işaret zamanında Zamanlayıcı için zamanlanan tüm iş tamamlanır. Birden fazla kapatma olayları bu yöntemle kaydedilebilir.  
  
```
virtual void RegisterShutdownEvent(HANDLE _Event) = 0;
```  
  
### <a name="parameters"></a>Parametreler  
 `_Event`  
 Zamanlayıcı kapanır ve kendisini bozar bağlandığınızda çalışma zamanı tarafından işaret Windows olay nesnesi için bir tanıtıcı.  
  
##  <a name="release"></a> Sürüm 

 Azaltır Zamanlayıcı başvuru sayısı.  
  
```
virtual unsigned int Release() = 0;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yeni indirildiği başvuru sayısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu, genellikle Zamanlayıcı oluşturma için kullanım ömrünü yönetmek için kullanılır. Ne zaman sıfıra Zamanlayıcı düştüğünde başvuru sayısı, Zamanlayıcı kapanacak ve destruct kendisini zamanlayıcıda tüm iş tamamlandı.  
  
##  <a name="resetdefaultschedulerpolicy"></a> ResetDefaultSchedulerPolicy 

 Varsayılan Zamanlayıcı ilke çalışma zamanı varsayılan olarak sıfırlar. Bir varsayılan Zamanlayıcısı'nı bir sonraki oluşturulduğunda, çalışma zamanı varsayılan ilke ayarlarını kullanır.  
  
```
static void __cdecl ResetDefaultSchedulerPolicy();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bir varsayılan Zamanlayıcı işlemi içinde varken bu yöntem çağrılamaz. Var olan varsayılan Zamanlayıcı İlkesi etkilemez. Ancak, varsayılan Zamanlayıcı kapatma sırasında ve yeni bir varsayılan bundan sonraki bir noktada oluşturulacak yeni Zamanlayıcı çalışma zamanı varsayılan ilke ayarları kullanırsınız.  
  
##  <a name="ctor"></a> Zamanlayıcı 

 Bir nesnenin `Scheduler` sınıfı için Fabrika yöntemleri kullanılarak oluşturulan yalnızca ya da örtük olarak.  
  
```
Scheduler();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Çağıran bağlamını eklenmesi için bir zamanlayıcı gerektiren çalışma zamanı işlevleri çoğunu kullanmasına, işlem varsayılan Zamanlayıcı örtük olarak oluşturulur. İçinde yöntemlerini `CurrentScheduler` sınıfı ve özellikleri PPL ve aracıları katmanların genellikle örtük eki gerçekleştirirsiniz.  
  
 Bir zamanlayıcı açıkça ya da aracılığıyla oluşturabilirsiniz `CurrentScheduler::Create` yöntemi veya `Scheduler::Create` yöntemi.  
  
##  <a name="dtor"></a> ~ Zamanlayıcı 

 Bir nesnenin `Scheduler` sınıfı tüm dış başvuruları mevcut çalışmayı zaman örtük olarak yok.  
  
```
virtual ~Scheduler();
```  
  
##  <a name="scheduletask"></a> ScheduleTask 

 Hafif Görev Zamanlayıcı içinde zamanlar. Hafif görev çalışma zamanı tarafından belirlenen bir zamanlama grubunda yer alır. Parametresi alan sürüm `_Placement` görev belirtilen konumda yürütme doğrultusunda ağırlıklı neden olur.  
  
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
 `_Proc`  
 İşlev gövdesi hafif görev gerçekleştirmek için bir işaretçi.  
  
 `_Data`  
 Görev gövdesi için parametre olarak geçirilen verileri void işaretçi.  
  
 `_Placement`  
 Burada hafif görev, yürütme doğru ağırlıklı bir konuma başvuru.  
  
##  <a name="setdefaultschedulerpolicy"></a> SetDefaultSchedulerPolicy 

 Varsayılan Zamanlayıcı oluşturmak için kullanılacak bir kullanıcı tanımlı ilke sağlar. Bu yöntem yalnızca varsayılan Zamanlayıcı işlemi içinde mevcut olduğunda çağrılabilir. Varsayılan bir ilke ayarladıktan sonra etkin ya da sonraki geçerli çağrısı kadar kalır `SetDefaultSchedulerPolicy` veya [ResetDefaultSchedulerPolicy](#resetdefaultschedulerpolicy) yöntemi.  
  
```
static void __cdecl SetDefaultSchedulerPolicy(const SchedulerPolicy& _Policy);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Policy`  
 Varsayılan Zamanlayıcı ilke olarak ayarlanması ilkesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa `SetDefaultSchedulerPolicy` yöntemi, bir varsayılan Zamanlayıcı işlemi içinde zaten mevcut olduğunda çağrılır, çalışma zamanı özel durum oluşturacak bir [default_scheduler_exists](default-scheduler-exists-class.md) özel durum.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Namespace](concurrency-namespace.md)   
 [Zamanlayıcı sınıfı](scheduler-class.md)   
 [PolicyElementKey](concurrency-namespace-enums.md)   
 [Görev Zamanlayıcısı](../../../parallel/concrt/task-scheduler-concurrency-runtime.md)



