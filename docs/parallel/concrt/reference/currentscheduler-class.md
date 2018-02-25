---
title: "CurrentScheduler sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d973b9ad7c5c7f81b5db85b3f8c5ccc49b5049b0
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="currentscheduler-class"></a>CurrentScheduler Sınıfı
Bir Özet arama bağlamla ilişkili geçerli Zamanlayıcı temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
class CurrentScheduler;
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[Oluşturma](#create)|Tarafından davranışı açıklanan yeni bir zamanlayıcı oluşturur `_Policy` parametre ve arama bağlamına ekler. Yeni oluşturulan Zamanlayıcı arama bağlamı için geçerli Zamanlayıcı olur.|  
|[CreateScheduleGroup](#createschedulegroup)|Fazla Yüklendi. Arama bağlamla ilişkili Zamanlayıcı içinde yeni bir zamanlama grubu oluşturur. Parametresi alan sürüm `_Placement` görevleri bu parametresi tarafından belirtilen konumda yürütme doğrultusunda ağırlıklı için yeni oluşturulan zamanlama grubundaki neden olur.|  
|[Detach](#detach)|Arama bağlamından geçerli Zamanlayıcı ayırır ve varsa, daha önce eklenen Zamanlayıcısı geçerli Zamanlayıcı olarak geri yükler. Bu yöntem döndükten sonra çağıran bağlamını sonra kullanarak içeriği önceden iliştirilmiş zamanlayıcısı tarafından yönetilen `CurrentScheduler::Create` veya `Scheduler::Attach` yöntemi.|  
|[Get](#get)|Bir işaretçi geçerli Zamanlayıcı da adlandırılan çağıran bağlamını ilişkili Zamanlayıcı döndürür.|  
|[GetNumberOfVirtualProcessors](#getnumberofvirtualprocessors)|Arama bağlamla ilişkili Zamanlayıcı için geçerli sanal işlemci sayısını döndürür.|  
|[GetPolicy](#getpolicy)|Geçerli Zamanlayıcı ile oluşturulduğundan İlkesi kopyasını döndürür.|  
|[Id](#id)|Geçerli Zamanlayıcı için benzersiz bir tanımlayıcı döndürür.|  
|[IsAvailableLocation](#isavailablelocation)|Belirtilen konum geçerli Zamanlayıcı üzerinde kullanılabilir olup olmadığını belirler.|  
|[RegisterShutdownEvent](#registershutdownevent)|Windows olay işleyici geçirilen nedenler `_ShutdownEvent` geçerli bağlamla ilişkili Zamanlayıcı kapanır ve kendisini bozar bildirilmesini parametresi. Olay işaret zamanında Zamanlayıcı için zamanlanan tüm iş tamamlanır. Birden fazla kapatma olayları bu yöntemle kaydedilebilir.|  
|[ScheduleTask](#scheduletask)|Fazla Yüklendi. Arama bağlamla ilişkili Zamanlayıcı içinde hafif görev zamanlar. Hafif görev çalışma zamanı tarafından belirlenen bir zamanlama grubunda yer alır. Parametresi alan sürüm `_Placement` görev belirtilen konumda yürütme doğrultusunda ağırlıklı neden olur.|  
  
## <a name="remarks"></a>Açıklamalar  
 Hiçbir Zamanlayıcı ise (bkz [Zamanlayıcı](scheduler-class.md)) içinde birçok yöntemlerini çağıran bağlamını ilişkili `CurrentScheduler` sınıfı, işlem varsayılan Zamanlayıcı ekinde sonuçlanır. Bu işlem varsayılan Zamanlayıcı böyle bir çağrı sırasında oluşturduğunuz ayrıca olabileceğidir.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `CurrentScheduler`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** concrt.h  
  
 **Namespace:** eşzamanlılık  
  
##  <a name="create">Oluşturma</a> 

 Tarafından davranışı açıklanan yeni bir zamanlayıcı oluşturur `_Policy` parametre ve arama bağlamına ekler. Yeni oluşturulan Zamanlayıcı arama bağlamı için geçerli Zamanlayıcı olur.  
  
```
static void __cdecl Create(const SchedulerPolicy& _Policy);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Policy`  
 Yeni oluşturulan Zamanlayıcı davranışını tanımlayan Zamanlayıcı ilke.  
  
### <a name="remarks"></a>Açıklamalar  
 Zamanlayıcı ek arama bağlamı için bir başvuru sayısı zamanlayıcıda örtük olarak yerleştirir.  
  
 Bir Zamanlayıcı ile oluşturulduktan sonra `Create` yöntemi, çağırmalıdır [CurrentScheduler::Detach](#detach) , gelecekte Zamanlayıcısı'nı kapatmak izin vermek üzere belirli bir noktada yöntemi.  
  
 Bu yöntem için farklı bir zamanlayıcı zaten eklenmiş bir bağlamından çağrılırsa, varolan Zamanlayıcı önceki Zamanlayıcı hatırlanan ve yeni oluşturulan Zamanlayıcı geçerli Zamanlayıcı olur. Çağırdığınızda `CurrentScheduler::Detach` önceki Zamanlayıcı sonraki bir zamanda yöntemi geçerli Zamanlayıcı geri.  
  
 Bu yöntemi özel durumlar dahil olmak üzere, çeşitli atabilirsiniz [scheduler_resource_allocation_error](scheduler-resource-allocation-error-class.md) ve [invalid_scheduler_policy_value](invalid-scheduler-policy-value-class.md).  
  
##  <a name="createschedulegroup"></a> CreateScheduleGroup 

 Arama bağlamla ilişkili Zamanlayıcı içinde yeni bir zamanlama grubu oluşturur. Parametresi alan sürüm `_Placement` görevleri bu parametresi tarafından belirtilen konumda yürütme doğrultusunda ağırlıklı için yeni oluşturulan zamanlama grubundaki neden olur.  
  
```
static ScheduleGroup* __cdecl CreateScheduleGroup();

static ScheduleGroup* __cdecl CreateScheduleGroup(location& _Placement);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Placement`  
 Burada zamanlama grup içindeki görevleri adresindeki yürütme doğrultusunda ağırlıklı bir konuma başvuru.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yeni oluşturulan zamanlama grup için bir işaretçi. Bu `ScheduleGroup` nesnesi üzerinde yerleştirilen bir ilk başvuru sayısı sahiptir.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem oluşturulan ve/veya şu anda arama bağlamla ilişkili hiçbir Zamanlayıcı ise arama bağlamına bağlı işlem varsayılan Zamanlayıcı neden olur.  
  
 Çağırmanız gerekir [sürüm](schedulegroup-class.md#release) zamanlama işi bittiğinde zamanlama grubunda yöntemi. Zamanlayıcı zamanlama silecektir tüm iş kuyruğa sırasında grubu tamamlandı.  
  
 Bu zamanlayıcı açıkça oluşturduysanız, geçerli bağlamdan ayırma tarafından başvuru Zamanlayıcı üzerinde bırakmadan önce içinde gruplar zamanlamak için tüm başvurularını serbest bırakmalısınız unutmayın.  
  
##  <a name="detach"></a> Ayırma 

 Arama bağlamından geçerli Zamanlayıcı ayırır ve varsa, daha önce eklenen Zamanlayıcısı geçerli Zamanlayıcı olarak geri yükler. Bu yöntem döndükten sonra çağıran bağlamını sonra kullanarak içeriği önceden iliştirilmiş zamanlayıcısı tarafından yönetilen `CurrentScheduler::Create` veya `Scheduler::Attach` yöntemi.  
  
```
static void __cdecl Detach();
```  
  
### <a name="remarks"></a>Açıklamalar  
 `Detach` Yöntemi dolaylı bir başvuru sayısı Zamanlayıcısı'ndan kaldırır.  
  
 Arama bağlamına bağlı hiçbir Zamanlayıcı varsa, bu yöntemi çağırmadan sonuçlanır bir [scheduler_not_attached](scheduler-not-attached-class.md) oluşturulan özel durum.  
  
 İç ağa ve bir zamanlayıcı veya başka bir yöntem kullanarak iliştirilmiş bir bağlam tarafından yönetilen bir bağlamından bu yöntemi çağırmadan [Scheduler::Attach](scheduler-class.md#attach) veya [CurrentScheduler::Create](#create) yöntemleri sonuçlanır bir [improper_scheduler_detach](improper-scheduler-detach-class.md) oluşturulan özel durum.  
  
##  <a name="get"></a> Al 

 Bir işaretçi geçerli Zamanlayıcı da adlandırılan çağıran bağlamını ilişkili Zamanlayıcı döndürür.  
  
```
static Scheduler* __cdecl Get();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Çağıran bağlamını (geçerli Zamanlayıcı) ile ilişkili Zamanlayıcı için bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem oluşturulan ve/veya şu anda arama bağlamla ilişkili hiçbir Zamanlayıcı ise arama bağlamına bağlı işlem varsayılan Zamanlayıcı neden olur. Hiçbir ek başvurusu yerleştirildiği `Scheduler` bu yöntem tarafından döndürülen nesne.  
  
##  <a name="getnumberofvirtualprocessors"></a> GetNumberOfVirtualProcessors 

 Arama bağlamla ilişkili Zamanlayıcı için geçerli sanal işlemci sayısını döndürür.  
  
```
static unsigned int __cdecl GetNumberOfVirtualProcessors();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir zamanlayıcı çağıran bağlamını, bu Zamanlayıcı için sanal işlemcilerin sayısı ile ilişkili ise; Aksi takdirde, değer `-1`.  
  
### <a name="remarks"></a>Açıklamalar  
 Çağıran bağlamını zaten bir Zamanlayıcı ile ilişkili değilse bu yöntem Zamanlayıcı ek yol açmaz.  
  
 Bu yöntemden dönüş değeri arama bağlamla ilişkili Zamanlayıcı için sanal işlemci sayısının anlık bir örnekleme değeridir. Bu değer, döndürülmeden şu anda eski olabilir.  
  
##  <a name="getpolicy"></a> GetPolicy 

 Geçerli Zamanlayıcı ile oluşturulduğundan İlkesi kopyasını döndürür.  
  
```
static SchedulerPolicy __cdecl GetPolicy();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İlkeyi bir kopyasını, geçerli Zamanlayıcı ile oluşturuldu.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem oluşturulan ve/veya şu anda arama bağlamla ilişkili hiçbir Zamanlayıcı ise arama bağlamına bağlı işlem varsayılan Zamanlayıcı neden olur.  
  
##  <a name="id"></a> Kimliği 

 Geçerli Zamanlayıcı için benzersiz bir tanımlayıcı döndürür.  
  
```
static unsigned int __cdecl Id();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir zamanlayıcı çağıran bağlamını, bu Zamanlayıcı için benzersiz bir tanımlayıcı ile ilişkili ise; Aksi takdirde, değer `-1`.  
  
### <a name="remarks"></a>Açıklamalar  
 Çağıran bağlamını zaten bir Zamanlayıcı ile ilişkili değilse bu yöntem Zamanlayıcı ek yol açmaz.  
  
##  <a name="isavailablelocation"></a> Isavailablelocation 

 Belirtilen konum geçerli Zamanlayıcı üzerinde kullanılabilir olup olmadığını belirler.  
  
```
static bool __cdecl IsAvailableLocation(const location& _Placement);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Placement`  
 Konumun hakkında geçerli Zamanlayıcı sorgulamak için bir başvuru.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Konumun belirttiği olup olmadığına ilişkin bir gösterge `_Placement` bağımsız değişkeni geçerli Zamanlayıcı üzerinde kullanılabilir.  
  
### <a name="remarks"></a>Açıklamalar  
 Çağıran bağlamını zaten bir Zamanlayıcı ile ilişkili değilse bu yöntem Zamanlayıcı ek yol açmaz.  
  
 Dönüş değeri bir anlık örnekleme belirtilen konum kullanılabilir olup olmadığını unutmayın. Birden çok zamanlayıcılar varlığında dinamik kaynak yönetimi ekleyebilir veya kaynakları herhangi bir noktada zamanlayıcılar gelen çıkardığınız. Bu olacağını, belirtilen konum kullanılabilirlik değiştirebilirsiniz.  
  
##  <a name="registershutdownevent"></a> RegisterShutdownEvent 

 Windows olay işleyici geçirilen nedenler `_ShutdownEvent` geçerli bağlamla ilişkili Zamanlayıcı kapanır ve kendisini bozar bildirilmesini parametresi. Olay işaret zamanında Zamanlayıcı için zamanlanan tüm iş tamamlanır. Birden fazla kapatma olayları bu yöntemle kaydedilebilir.  
  
```
static void __cdecl RegisterShutdownEvent(HANDLE _ShutdownEvent);
```  
  
### <a name="parameters"></a>Parametreler  
 `_ShutdownEvent`  
 Geçerli bağlamla ilişkili Zamanlayıcı kapanır ve kendisini bozar bağlandığınızda çalışma zamanı tarafından işaret Windows olay nesnesi için bir tanıtıcı.  
  
### <a name="remarks"></a>Açıklamalar  
 Arama bağlamına bağlı hiçbir Zamanlayıcı varsa, bu yöntemi çağırmadan sonuçlanır bir [scheduler_not_attached](scheduler-not-attached-class.md) oluşturulan özel durum.  
  
##  <a name="scheduletask"></a> ScheduleTask 

 Arama bağlamla ilişkili Zamanlayıcı içinde hafif görev zamanlar. Hafif görev çalışma zamanı tarafından belirlenen bir zamanlama grubunda yer alır. Parametresi alan sürüm `_Placement` görev belirtilen konumda yürütme doğrultusunda ağırlıklı neden olur.  
  
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
 `_Proc`  
 İşlev gövdesi hafif görev gerçekleştirmek için bir işaretçi.  
  
 `_Data`  
 Görev gövdesi için parametre olarak geçirilen verileri void işaretçi.  
  
 `_Placement`  
 Burada hafif görev, yürütme doğru ağırlıklı bir konuma başvuru.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem oluşturulan ve/veya şu anda arama bağlamla ilişkili hiçbir Zamanlayıcı ise arama bağlamına bağlı işlem varsayılan Zamanlayıcı neden olur.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Namespace](concurrency-namespace.md)   
 [Zamanlayıcı sınıfı](scheduler-class.md)   
 [PolicyElementKey](concurrency-namespace-enums.md)   
 [Görev Zamanlayıcısı](../../../parallel/concrt/task-scheduler-concurrency-runtime.md)



