---
title: "Eşzamanlılık ad alanı numaralandırmaları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CONCRT/concurrency::Agents_EventType
- CONCRT/concurrency::Concrt_TraceFlags
- CONCRT/concurrency::CriticalRegionType
- CONCRT/concurrency::PolicyElementKey
- CONCRT/concurrency::SchedulerType
- CONCRT/concurrency::SwitchingProxyState
- CONCRT/concurrency::WinRTInitializationType
- CONCRT/concurrency::join_type
- CONCRT/concurrency::message_status Enumeration
dev_langs: C++
ms.assetid: a40e3b2d-ad21-4229-9880-2cfa84f7ab8f
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 4603b01f7daa4573035f57b520dcb1dc5d4eab66
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="concurrency-namespace-enums"></a>Eşzamanlılık ad alanı numaralandırmaları
||||  
|-|-|-|  
|[Agents_EventType](#agents_eventtype)|[ConcRT_EventType](#concrt_eventtype)|[Concrt_TraceFlags](#concrt_traceflags)|  
|[CriticalRegionType](#criticalregiontype)|[DynamicProgressFeedbackType](#dynamicprogressfeedbacktype)|[PolicyElementKey](#policyelementkey)|  
|[SchedulerType](#schedulertype)|[SchedulingProtocolType](#schedulingprotocoltype)|[SwitchingProxyState](#switchingproxystate)|  
|[Winrtınitializationtype](#winrtinitializationtype)|[agent_status](#agent_status)|[join_type](#join_type)|  
|[message_status](#message_status)|[task_group_status](#task_group_status)|  
  
##  <a name="agent_status"></a>agent_status numaralandırması  
 Geçerli durumunu bir `agent`.  
  
```
enum agent_status;
```  
### <a name="values"></a>Değerler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`agent_canceled`|`agent` İptal edildi.|  
|`agent_created`|`agent` Oluşturuldu, ancak henüz başlatılmamış.|  
|`agent_done`|`agent` İptal olmadan tamamlandı.|  
|`agent_runnable`|`agent` Başlatıldı, ancak deftere girilmediği kendi `run` yöntemi.|  
|`agent_started`|`agent` Başlatıldı.|  

### <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için bkz: [zaman uyumsuz aracılar](../../../parallel/concrt/asynchronous-agents.md).  

### <a name="requirements"></a>Gereksinimler  
 **Başlık:** concrt.h

##  <a name="agents_eventtype"></a>Agents_EventType numaralandırması  
 Aracılar Kitaplığı tarafından sunulan izleme işlevselliği kullanılarak izlenebilir olay türleri  
  
```
enum Agents_EventType;
```  

### <a name="values"></a>Değerler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`AGENTS_EVENT_CREATE`|Bir nesne oluşturulmasını gösteren bir olay türü|  
|`AGENTS_EVENT_DESTROY`|Bir nesne silme işlemini temsil eden olay türü|  
|`AGENTS_EVENT_END`|İşleme sonuç bazı temsil eden bir olay türü|  
|`AGENTS_EVENT_LINK`|İleti blokları bağlama temsil eden olay türü|  
|`AGENTS_EVENT_NAME`|Bir nesne adını temsil eden olay türü|  
|`AGENTS_EVENT_SCHEDULE`|Planlama işlemi temsil eden olay türü|  
|`AGENTS_EVENT_START`|İşleme başlatma bazı temsil eden bir olay türü|  
|`AGENTS_EVENT_UNLINK`|İleti blokları bağlantısını temsil eden olay türü|  

### <a name="requirements"></a>Gereksinimler  
 **Başlık:** concrt.h

##  <a name="concrt_eventtype"></a>ConcRT_EventType numaralandırması  
 Eşzamanlılık Çalışma zamanı tarafından sunulan izleme işlevselliği kullanılarak izlenebilir olay türleri.  
  
```
enum ConcRT_EventType;
```  
### <a name="values"></a>Değerler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`CONCRT_EVENT_ATTACH`|Bir zamanlayıcı ekleme işlemi temsil eden bir olay türü.|  
|`CONCRT_EVENT_BLOCK`|Engelleme bağlam işlemi temsil eden bir olay türü.|  
|`CONCRT_EVENT_DETACH`|Bir zamanlayıcı ayırma işlemi temsil eden bir olay türü.|  
|`CONCRT_EVENT_END`|Bir başlangıç/bitiş olay çifti başlangıcını işaretleyen bir olay türü.|  
|`CONCRT_EVENT_GENERIC`|Çeşitli olayları için kullanılan bir olay türü.|  
|`CONCRT_EVENT_IDLE`|Boşta olma bir bağlam işlemi temsil eden bir olay türü.|  
|`CONCRT_EVENT_START`|Bir başlangıç/bitiş olay çifti başlangıcını işaretleyen bir olay türü.|  
|`CONCRT_EVENT_UNBLOCK`|Bir bağlam engellemelerini kaldırma işlemi temsil eden bir olay türü.|  
|`CONCRT_EVENT_YIELD`|Oluşturan bağlam işlemi temsil eden bir olay türü.|  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** concrt.h **Namespace:** eşzamanlılık

##  <a name="concrt_traceflags"></a>Concrt_TraceFlags numaralandırması  
 Olay türleri için izleme bayrakları  
  
```
enum Concrt_TraceFlags;
```  
### <a name="values"></a>Değerler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`AgentEventFlag`||  
|`AllEventsFlag`||  
|`ContextEventFlag`||  
|`PPLEventFlag`||  
|`ResourceManagerEventFlag`||  
|`SchedulerEventFlag`||  
|`VirtualProcessorEventFlag`||

### <a name="requirements"></a>Gereksinimler  
 **Başlık:** concrt.h

##  <a name="criticalregiontype"></a>CriticalRegionType numaralandırması  
 Kritik bölgesinin bir bağlam türünü içindedir.  
  
```
enum CriticalRegionType;
```  
### <a name="values"></a>Değerler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`InsideCriticalRegion`|Bağlam içinde kritik bir bölge olduğunu gösterir. Bir kritik bölge Zaman içinde zaman uyumsuz suspensions Zamanlayıcısı'ndan gizlenir. Böyle bir askıya alma meydana, Resource Manager runnable haline gelir ve yalnızca Zamanlayıcı yeniden çağırma yerine sürdürmek iş parçacığı bekleyecek. Bu tür bir bölge içinde gerçekleştirilecek kilitleri onaylamadığından çok dikkatli olunmalıdır.|  
|`InsideHyperCriticalRegion`|Bağlam içinde kritik hyper bölge olduğunu gösterir. Bir kritik hyper bölge Zaman içinde zaman uyumlu ve zaman uyumsuz suspensions Zamanlayıcısı'ndan gizlenir. Engelleme gerçekleşir, Kaynak Yöneticisi'ni runnable haline gelir ve yalnızca Zamanlayıcı yeniden çağırma yerine sürdürmek iş parçacığı için bekleyeceği veya böyle bir askıya alma gerekir. Bu tür bir bölge dışında çalışan kodu ile hiçbir zaman bu tür bir bölge içinde gerçekleştirilecek kilitleri paylaşılması gerekir. Bunun yapılması, öngörülemeyen kilitlenmeye neden olur.|  
|`OutsideCriticalRegion`|Bağlam dışında herhangi bir kritik bölgeyi olduğunu gösterir.|  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** concrtrm.h 

##  <a name="dynamicprogressfeedbacktype"></a>DynamicProgressFeedbackType numaralandırması  
 Tarafından kullanılan `DynamicProgressFeedback` kaynakları Zamanlayıcı için istatistiksel bilgileri göre Zamanlayıcı'dan toplanan ya da yalnızca yeniden dengelenir olup olmadığını açıklamak için ilke temel alarak çağrılarıaracılığıylaboştadurumundakivegidensanalişlemciler`Activate` ve `Deactivate` yöntemlere `IVirtualProcessorRoot` arabirimi. Kullanılabilir Zamanlayıcı ilkeleri hakkında daha fazla bilgi için bkz: [PolicyElementKey](concurrency-namespace-enums.md).  
  
```
enum DynamicProgressFeedbackType;
```  
### <a name="values"></a>Değerler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`ProgressFeedbackDisabled`|Zamanlayıcı ilerleme durumu bilgileri toplayın değil. Dengelenmesi tabanlı yalnızca abonelik düzeyi temel alınan donanım iş parçacığı üzerinde gerçekleştirilir. Abonelik düzeyleri hakkında daha fazla bilgi için bkz: [Iexecutionresource::currentsubscriptionlevel](IExecutionResource-structure.md).<br /><br /> Bu değer çalışma zamanı tarafından kullanılmak üzere ayrılmış.|  
|`ProgressFeedbackEnabled`|Zamanlayıcı ilerleme durumu bilgilerini toplar ve kaynak yöneticisine geçirir. Kaynak Yöneticisi'ni Zamanlayıcı yanı sıra temel alınan donanım iş parçacığı abonelik düzeyi adına kaynakları yeniden dengelemeniz bu istatistik bilgileri yararlanacak olan. Abonelik düzeyleri hakkında daha fazla bilgi için bkz: [Iexecutionresource::currentsubscriptionlevel](IExecutionResource-structure.md).|  
##  <a name="join_type"></a>join_type numaralandırması  
 Türü bir `join` ileti bloğu.  
  
```
enum join_type;
```  
### <a name="values"></a>Değerler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`greedy`|Doyumsuz `join` ileti blokları hemen kabul bir ileti yayma bağlıdır. Bu daha verimli olur, ancak Canlı-kilitleme, ağ yapılandırmasına bağlı olarak olasılığı vardır.|  
|`non_greedy`|Doyumsuz olmayan `join` ileti blokları iletileri erteleyin deneyin ve tüm gelmedi sonra bunları kullanabilir. Bunlar, ancak daha yavaş çalışmaya garanti.|  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** agents.h  

##  <a name="message_status"></a>message_status numaralandırması  
 Geçerli yanıtlar bir teklifi için bir `message` bloğu için nesne.  
  
```
enum message_status;
```  
### <a name="values"></a>Değerler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`accepted`|Hedef ileti kabul edildi.|  
|`declined`|Hedef ileti kabul etmedi.|  
|`missed`|İleti kabul etmek hedef çalıştı, ancak artık kullanılabilir.|  
|`postponed`|Hedef ileti ertelendi.|  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** agents.h  

##  <a name="policyelementkey"></a>PolicyElementKey numaralandırması  
 İlke Zamanlayıcı davranışının açıklayan yönlerini anahtarları. Her ilke öğesi bir anahtar-değer çifti tarafından tanımlanır. Zamanlayıcılar Zamanlayıcı ilkeleri ve bunların etkisi hakkında daha fazla bilgi için bkz: [Görev Zamanlayıcı](../../../parallel/concrt/task-scheduler-concurrency-runtime.md).  
  
```
enum PolicyElementKey;
```  
### <a name="values"></a>Değerler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`ContextPriority`|Zamanlayıcı her bağlamda işletim sistemi iş parçacığı önceliği. Bu anahtar için değeri ayarlarsanız `INHERIT_THREAD_PRIORITY` Zamanlayıcı bağlamlarda Zamanlayıcı oluşturulan iş parçacığının önceliğini devralır.<br /><br /> Geçerli değerler: Windows için geçerli değerleri `SetThreadPriority` işlev ve özel değer`INHERIT_THREAD_PRIORITY`<br /><br /> Varsayılan değer:`THREAD_PRIORITY_NORMAL`|  
|`ContextStackSize`|Zamanlayıcı kilobayt cinsinden her bağlamda ayrılmış yığın boyutu.<br /><br /> Geçerli değerler: pozitif tamsayılar<br /><br /> Varsayılan değer: `0`, işlem varsayılan değer yığın boyutu için kullanılması gerektiğini belirten.|  
|`DynamicProgressFeedback`|Zamanlayıcı için kaynakları Zamanlayıcısı'ndan toplanmaz veya yalnızca temel alınan donanım iş parçacığı abonelik düzeyini temel istatistiksel bilgileri göre yeniden dengelenir olup olmadığını belirler. Daha fazla bilgi için bkz: [DynamicProgressFeedbackType](#dynamicprogressfeedbacktype).<br /><br /> Geçerli değerler: üye `DynamicProgressFeedbackType` numaralandırma, ya da `ProgressFeedbackEnabled` veya`ProgressFeedbackDisabled`<br /><br /> Varsayılan değer:`ProgressFeedbackEnabled`|  
|`LocalContextCacheSize`|Zaman `SchedulingProtocol` ilke anahtarı değerine ayarlanmış `EnhanceScheduleGroupLocality`, bu runnable bağlamları içinde sanal işlemci başına yerel kuyruğu önbelleğe alınmasına izin verilen en fazla sayısını belirtir. Bu tür bağlamları genellikle bunları runnable hale gelmesine neden sanal işlemci son-giren ilk çıkar (LIFO) sırayla çalışır. Bu ilke anahtar hiçbir zaman anlamına gelen sahip olduğuna dikkat edin `SchedulingProtocol` anahtarı değerine ayarlanmış `EnhanceForwardProgress`.<br /><br /> Geçerli değerler: negatif olmayan tamsayılar<br /><br /> Varsayılan değer:`8`|  
|`MaxConcurrency`|Düzey Zamanlayıcı tarafından istenen en fazla eşzamanlı. Kaynak Yöneticisi, başlangıçta bu kadar sanal işlemciye ayırmak çalışacaktır. Özel değerini [MaxExecutionResources](concurrency-namespace-constants1.md#maxexecutionresources) istenen eşzamanlılık düzeyi makinedeki donanım iş parçacığı sayısı ile aynı olduğunu gösterir. İçin belirtilen değer, `MinConcurrency` makinedeki donanım iş parçacığı sayısını değerinden daha büyük ve `MaxConcurrency` olarak belirtilen `MaxExecutionResources`, değeri `MaxConcurrency` için ayarlanmış eşleşecek şekilde tetiklenir `MinConcurrency`.<br /><br /> Geçerli değerler: pozitif tamsayılar ve özel değer`MaxExecutionResources`<br /><br /> Varsayılan değer:`MaxExecutionResources`|  
|`MaxPolicyElementKey`|En fazla ilke öğe anahtarı. Geçerli öğe anahtarı değil.|  
|`MinConcurrency`|Zamanlayıcı için kaynak yöneticisi tarafından sağlanmalıdır minimum eşzamanlılık düzeyi. Bir zamanlayıcı atanan sanal işlemcilerin sayısı, en hiçbir zaman geçer. Özel değerini [MaxExecutionResources](concurrency-namespace-constants1.md#maxexecutionresources) minimum eşzamanlılık düzeyi makinedeki donanım iş parçacığı sayısı ile aynı olduğunu gösterir. İçin belirtilen değer, `MaxConcurrency` makinedeki donanım iş parçacığı sayısını küçüktür ve `MinConcurrency` olarak belirtilen `MaxExecutionResources`, değeri `MinConcurrency` için ayarlanmış eşleşecek şekilde azaltıldığı `MaxConcurrency`.<br /><br /> Geçerli değerler: negatif olmayan tamsayılar ve özel değerini `MaxExecutionResources`. Eşzamanlılık Çalışma zamanı zamanlayıcılar, değer yapımı için kullanılan Zamanlayıcı ilkeleri için unutmayın `0` geçersiz.<br /><br /> Varsayılan değer:`1`|  
|`SchedulerKind`|Zamanlayıcı için temel alınan yürütme bağlamı yararlanacak olan iş parçacıkları türü. Daha fazla bilgi için bkz: [SchedulerType](#schedulertype).<br /><br /> Geçerli değerler: üye `SchedulerType` numaralandırma, örneğin,`ThreadScheduler`<br /><br /> Varsayılan değer: `ThreadScheduler`. Bu, Win32 parçacıkları tüm işletim sistemlerinde dönüşür.|  
|`SchedulingProtocol`|Zamanlama algoritmayı Zamanlayıcı tarafından kullanılacak açıklar. Daha fazla bilgi için bkz: [SchedulingProtocolType](#schedulingprotocoltype).<br /><br /> Geçerli değerler: üye `SchedulingProtocolType` numaralandırma, ya da `EnhanceScheduleGroupLocality` veya`EnhanceForwardProgress`<br /><br /> Varsayılan değer:`EnhanceScheduleGroupLocality`|  
|`TargetOversubscriptionFactor`|Donanım iş parçacığı başına sanal işlemciler belirsiz sayısı. Gerekirse, karşılamak kaynak yöneticisi tarafından hedef aşırı abonelik faktörü artırılabilir `MaxConcurrency` makine üzerinde donanım iş parçacığı ile.<br /><br /> Geçerli değerler: pozitif tamsayılar<br /><br /> Varsayılan değer:`1`|  
|`WinRTInitialization`||  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** concrt.h  

##  <a name="schedulertype"></a>SchedulerType numaralandırması  
 Tarafından kullanılan `SchedulerKind` Zamanlayıcı için temel alınan yürütme bağlamı kullanmalıdır iş parçacığı türünü tanımlamak için ilke. Kullanılabilir Zamanlayıcı ilkeleri hakkında daha fazla bilgi için bkz: [PolicyElementKey](concurrency-namespace-enums.md).  
  
```
enum SchedulerType;
``` 

### <a name="values"></a>Değerler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`ThreadScheduler`|Açık bir istekte normal Win32 iş parçacığı gösterir.|  
|`UmsThreadDefault`|Kullanıcı modu zamanlanabilir (UMS) iş parçacıklarının eşzamanlılık çalışma zamanı Visual Studio 2013'te desteklenmez. Kullanarak `UmsThreadDefault` için bir değer olarak `SchedulerType` ilkesi olmayan bir hata sonucu. Ancak, bu ilke ile oluşturulan bir zamanlayıcı Win32 iş parçacığı kullanma için varsayılan olur.|  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** concrt.h  
  
##  <a name="schedulingprotocoltype"></a>SchedulingProtocolType numaralandırması  
 Tarafından kullanılan `SchedulingProtocol` zamanlama algoritmayı Zamanlayıcı için yararlı olabilir açıklamak için ilke. Kullanılabilir Zamanlayıcı ilkeleri hakkında daha fazla bilgi için bkz: [PolicyElementKey](concurrency-namespace-enums.md).  
  
```
enum SchedulingProtocolType;
```  
### <a name="values"></a>Değerler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`EnhanceForwardProgress`|Zamanlayıcı hepsini zamanlama grupları aracılığıyla için her görevin yürütülmesinin ardından tercih eder. Engeli bağlamları genellikle bir ilk olarak ilk çıkar (FIFO) şekilde zamanlanır. Sanal işlemciler engeli bağlamları önbelleğe almaz.|  
|`EnhanceScheduleGroupLocality`|Zamanlayıcı, başka bir zamanlama gruba taşımadan önce geçerli zamanlama grubunda görevlerde çalışmaya devam etmek tercih eder. Engeli bağlamları sanal-işlemci önbelleğe alınır ve son-giren ilk çıkar (LIFO) biçimde, bunları engellemesini sanal işlemci genellikle zamanlanır.|  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** concrt.h  
 
##  <a name="switchingproxystate"></a>SwitchingProxyState numaralandırması  
 Bir iş parçacığı proxy bulunduğu durumu belirtmek için kullanılan, ne zaman, farklı iş parçacığı proxy işbirlikçi içerik anahtarına yürütüyor.  
  
```
enum SwitchingProxyState;
```  
### <a name="values"></a>Değerler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`Blocking`|Çağıran iş parçacığı işlevinizde engelleme ve özel olarak çağıran tarafından daha sonra yeniden çalıştırarak ve diğer eylemi gerçekleştirmeden kadar ait gösterir.|  
|`Idle`|Çağıran iş parçacığı Zamanlayıcı tarafından artık gerekli değildir ve Resource Manager döndürülen gösterir. Dağıtılan bağlamı artık kaynak yöneticisi tarafından kullanılan mümkün değildir.|  
|`Nesting`|Çağıran iş parçacığı alt Zamanlayıcı iç içe geçme ve çağıran tarafından farklı bir zamanlayıcı iliştirmek için gerekli olduğunu gösterir.|  

### <a name="remarks"></a>Açıklamalar  
 Türünde bir parametre `SwitchingProxyState` yönteme geçirilen `IThreadProxy::SwitchTo` Kaynak Yöneticisi'ni nasıl çağrıyı yapan iş parçacığı proxy ele istemek üzere.  
  
 Bu tür nasıl kullanıldığı hakkında daha fazla bilgi için bkz: [Ithreadproxy::switchto](ithreadproxy-structure.md#switchto).  
  
##  <a name="task_group_status"></a>task_group_status numaralandırması  
 Yürütme durumu açıklayan bir `task_group` veya `structured_task_group` nesnesi. Görevin tamamlanması için bir görev grubuna zamanlanmış bekleme çeşitli yöntemlerle bu türde bir değer döndürdü.  
  
```
enum task_group_status;
```  
### <a name="values"></a>Değerler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`canceled`|`task_group` Veya `structured_task_group` nesne iptal edildi. Bir veya daha fazla görev yürütülmedi.|  
|`completed`|Görevler sıraya alınan `task_group` veya `structured_task_group` nesnesi başarıyla tamamlandı.|  
|`not_complete`|Görevler sıraya alınan `task_group` nesne tamamlanmış değildir. Bu değer eşzamanlılık çalışma zamanı tarafından şu anda döndürülmez unutmayın.|  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** pplinterface.h  

##  <a name="winrtinitializationtype"></a>Winrtınitializationtype numaralandırması  
 Tarafından kullanılan `WinRTInitialization` olup olmadığını ve nasıl Windows çalışma zamanı sürümü Windows 8 işletim sistemlerinde çalışan bir uygulama için Zamanlayıcı iş parçacığı üzerinde başlatılmış veya daha yüksek olacak açıklamak için ilke. Kullanılabilir Zamanlayıcı ilkeleri hakkında daha fazla bilgi için bkz: [PolicyElementKey](concurrency-namespace-enums.md).  
  
```
enum WinRTInitializationType;
```  
### <a name="values"></a>Değerler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`DoNotInitializeWinRT`|Ne zaman uygulamanın sürümü Windows 8 işletim sistemlerinde çalışan veya üzeri, içinde Zamanlayıcı iş parçacıkları Windows çalışma zamanı başlatılamıyor değil.|  
|`InitializeWinRTAsMTA`|Uygulama sürümü Windows 8 işletim sistemlerinde çalıştırdığınızda veya Zamanlayıcı içinde her bir iş parçacığı sonraki ve Windows çalışma zamanı başlatılamıyor olduğunu bildirmek birden çok iş parçacıklı grup parçası olur.|  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** concrt.h  

## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Namespace](concurrency-namespace.md)
