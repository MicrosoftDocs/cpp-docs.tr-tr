---
title: eşzamanlılık ad alanı sabit listeleri
ms.date: 11/04/2016
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
ms.assetid: a40e3b2d-ad21-4229-9880-2cfa84f7ab8f
ms.openlocfilehash: 716c2d03e6d1ff67566bd28e5931996ea2d400af
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77141314"
---
# <a name="concurrency-namespace-enums"></a>eşzamanlılık ad alanı sabit listeleri

||||
|-|-|-|
|[Agents_EventType](#agents_eventtype)|[ConcRT_EventType](#concrt_eventtype)|[Concrt_TraceFlags](#concrt_traceflags)|
|[CriticalRegionType](#criticalregiontype)|[DynamicProgressFeedbackType](#dynamicprogressfeedbacktype)|[PolicyElementKey](#policyelementkey)|
|[SchedulerType](#schedulertype)|[SchedulingProtocolType](#schedulingprotocoltype)|[SwitchingProxyState](#switchingproxystate)|
|[WinRTInitializationType](#winrtinitializationtype)|[agent_status](#agent_status)|[join_type](#join_type)|
|[message_status](#message_status)|[task_group_status](#task_group_status)|

## <a name="agent_status"></a>agent_status numaralandırması

`agent`için geçerli durumlar.

```cpp
enum agent_status;
```

### <a name="values"></a>Değerler

|Ad|Açıklama|
|----------|-----------------|
|`agent_canceled`|`agent` iptal edildi.|
|`agent_created`|`agent` oluşturuldu ancak başlatılmadı.|
|`agent_done`|`agent` iptal edilmeden tamamlandı.|
|`agent_runnable`|`agent` başlatıldı, ancak `run` yöntemi girilmedi.|
|`agent_started`|`agent` başlatıldı.|

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [zaman uyumsuz aracılar](../../../parallel/concrt/asynchronous-agents.md).

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** concrt. h

## <a name="agents_eventtype"></a>Agents_EventType numaralandırması

Aracılar Kitaplığı tarafından sunulan izleme işlevi kullanılarak izlenebilir olay türleri

```cpp
enum Agents_EventType;
```

### <a name="values"></a>Değerler

|Ad|Açıklama|
|----------|-----------------|
|`AGENTS_EVENT_CREATE`|Bir nesnenin oluşturulmasını temsil eden bir olay türü|
|`AGENTS_EVENT_DESTROY`|Bir nesnenin silinmesini temsil eden bir olay türü|
|`AGENTS_EVENT_END`|Bir işlemin sonucunun temsil eden bir olay türü|
|`AGENTS_EVENT_LINK`|İleti bloklarının bağlamasını temsil eden bir olay türü|
|`AGENTS_EVENT_NAME`|Bir nesnenin adını temsil eden bir olay türü|
|`AGENTS_EVENT_SCHEDULE`|Bir işlemin zamanlamasını temsil eden bir olay türü|
|`AGENTS_EVENT_START`|Bazı işlemleri başlatma işlemini temsil eden bir olay türü|
|`AGENTS_EVENT_UNLINK`|İleti bloklarının bağını kaldırmayı temsil eden bir olay türü|

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** concrt. h

## <a name="concrt_eventtype"></a>ConcRT_EventType numaralandırması

Eşzamanlılık Çalışma Zamanı tarafından sunulan izleme işlevi kullanılarak izlenebilir olay türleri.

```cpp
enum ConcRT_EventType;
```

### <a name="values"></a>Değerler

|Ad|Açıklama|
|----------|-----------------|
|`CONCRT_EVENT_ATTACH`|Bir Scheduler 'a ekleme Yasası temsil eden bir olay türü.|
|`CONCRT_EVENT_BLOCK`|Bağlam engelleme Yasası temsil eden bir olay türü.|
|`CONCRT_EVENT_DETACH`|Bir Scheduler 'dan ayırma Yasası temsil eden bir olay türü.|
|`CONCRT_EVENT_END`|Başlangıç/bitiş olay çiftinin başlangıcını işaretleyen bir olay türü.|
|`CONCRT_EVENT_GENERIC`|Çeşitli olaylar için kullanılan bir olay türü.|
|`CONCRT_EVENT_IDLE`|Bir bağlamın çalışmasını temsil eden bir olay türü.|
|`CONCRT_EVENT_START`|Başlangıç/bitiş olay çiftinin başlangıcını işaretleyen bir olay türü.|
|`CONCRT_EVENT_UNBLOCK`|Bir bağlamın engellemesini kaldırma Yasası temsil eden bir olay türü.|
|`CONCRT_EVENT_YIELD`|Bir içeriğin davranma durumunu temsil eden bir olay türü.|

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** concrt. h **ad alanı:** eşzamanlılık

## <a name="concrt_traceflags"></a>Concrt_TraceFlags numaralandırması

Olay türleri için izleme bayrakları

```cpp
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

**Üstbilgi:** concrt. h

## <a name="criticalregiontype"></a>Kritikregiontype numaralandırması

Bağlam içindeki kritik bölge türü.

```cpp
enum CriticalRegionType;
```

### <a name="values"></a>Değerler

|Ad|Açıklama|
|----------|-----------------|
|`InsideCriticalRegion`|İçeriğin kritik bir bölgenin içinde olduğunu gösterir. Kritik bir bölgenin içindeyken zaman uyumsuz getirilmesi, Scheduler 'dan gizlenir. Bu tür bir askıya alma işleminin gerçekleşmesi durumunda Kaynak Yöneticisi, iş parçacığının çalıştırılabilir hale gelmesini bekler ve Zamanlayıcı 'yı yeniden çağırmak yerine yalnızca bu uygulamayı sürdürür. Bu tür bir bölgenin içinde alınan kilitlerin çok fazla dikkatli olması gerekir.|
|`InsideHyperCriticalRegion`|Bağlamın bir Hyper-kritik bölgesi içinde olduğunu gösterir. Hiper kritik bir bölgenin içindeyken hem zaman uyumlu hem de zaman uyumsuz getirilmesi Zamanlayıcı 'dan gizlenir. Böyle bir askıya alma veya engelleme olması durumunda, Resource Manager iş parçacığının çalıştırılabilir hale gelmesini bekler ve Zamanlayıcı 'yı yeniden çağırmak yerine yalnızca bu uygulamayı sürdürür. Böyle bir bölge içinde alınan kilitler hiçbir şekilde bu bölge dışında çalışan kodla paylaşılmalıdır. Bunun yapılması öngörülemeyen kilitlenmeye neden olur.|
|`OutsideCriticalRegion`|İçeriğin herhangi bir kritik bölgenin dışında olduğunu gösterir.|

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** concrtrm. h

## <a name="dynamicprogressfeedbacktype"></a>DynamicProgressFeedbackType numaralandırması

Zamanlayıcı kaynaklarının, Scheduler 'dan toplanan istatistiksel bilgilere göre yeniden dengelenmesi veya yalnızca `IVirtualProcessorRoot` arabirimindeki `Activate` ve `Deactivate` yöntemlerine yapılan çağrılar aracılığıyla boşta durumuna geçme ve çıkış dışı olan sanal işlemcilere bağlı olup olmayacağını öğrenmek için `DynamicProgressFeedback` ilkesi tarafından kullanılır. Kullanılabilir Zamanlayıcı ilkeleri hakkında daha fazla bilgi için bkz. [PolicyElementKey](concurrency-namespace-enums.md).

```cpp
enum DynamicProgressFeedbackType;
```

### <a name="values"></a>Değerler

|Ad|Açıklama|
|----------|-----------------|
|`ProgressFeedbackDisabled`|Zamanlayıcı, ilerleme bilgilerini toplamaz. Yeniden dengeleme, yalnızca temel alınan donanım iş parçacığının abonelik düzeyine göre yapılır. Abonelik düzeyleri hakkında daha fazla bilgi için bkz. [IExecutionResource:: CurrentSubscriptionLevel](IExecutionResource-structure.md).<br /><br /> Bu değer, çalışma zamanı tarafından kullanılmak üzere ayrılmıştır.|
|`ProgressFeedbackEnabled`|Zamanlayıcı ilerleme bilgilerini toplar ve Resource Manager 'a geçirir. Resource Manager, temel alınan donanım iş parçacığının abonelik düzeyine ek olarak Zamanlayıcı adına kaynakları yeniden dengelemek için bu istatistiksel bilgileri kullanır. Abonelik düzeyleri hakkında daha fazla bilgi için bkz. [IExecutionResource:: CurrentSubscriptionLevel](IExecutionResource-structure.md).|

## <a name="join_type"></a>join_type numaralandırması

`join` mesajlaşma bloğunun türü.

```cpp
enum join_type;
```

### <a name="values"></a>Değerler

|Ad|Açıklama|
|----------|-----------------|
|`greedy`|Greedy `join` mesajlaşma blokları, yayma sonrasında bir iletiyi hemen kabul eder. Bu daha verimlidir, ancak ağ yapılandırmasına bağlı olarak dinamik kilitleme olasılığa sahiptir.|
|`non_greedy`|Doyumsuz olmayan `join` mesajlaşma blokları iletileri erteleyip tüm iletişim olduktan sonra bunları dener ve tüketir. Bunlar, çalışma garantisi, ancak daha yavaştır.|

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Agents. h

## <a name="message_status"></a>message_status numaralandırması

Bir blok için `message` nesnesi teklifine yönelik geçerli yanıtlar.

```cpp
enum message_status;
```

### <a name="values"></a>Değerler

|Ad|Açıklama|
|----------|-----------------|
|`accepted`|Hedef iletiyi kabul etti.|
|`declined`|Hedef iletiyi kabul etmedi.|
|`missed`|Hedef iletiyi kabul edilmeye çalıştı, ancak artık kullanılamıyor.|
|`postponed`|Hedef iletiyi erteleyen.|

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Agents. h

## <a name="policyelementkey"></a>PolicyElementKey numaralandırması

Zamanlayıcı davranışının yönlerini açıklayan ilke anahtarları. Her ilke öğesi bir anahtar-değer çifti tarafından açıklanmıştır. Zamanlayıcı ilkeleri ve zamanlayıcılar üzerindeki etkileri hakkında daha fazla bilgi için bkz. [Görev Zamanlayıcı](../../../parallel/concrt/task-scheduler-concurrency-runtime.md).

```cpp
enum PolicyElementKey;
```

### <a name="values"></a>Değerler

|Ad|Açıklama|
|----------|-----------------|
|`ContextPriority`|Zamanlayıcıdaki her bir bağlamın işletim sistemi iş parçacığı önceliği. Bu anahtar değere ayarlanmışsa `INHERIT_THREAD_PRIORITY` Scheduler 'daki bağlamlar, Scheduler 'ı oluşturan iş parçacığının önceliğini alır.<br /><br /> Geçerli değerler: Windows `SetThreadPriority` işlevi ve özel değer için geçerli değerlerden herhangi biri `INHERIT_THREAD_PRIORITY`<br /><br /> Varsayılan değer: `THREAD_PRIORITY_NORMAL`|
|`ContextStackSize`|Zamanlayıcıdaki her bir bağlamın kilobayt cinsinden ayrılmış yığın boyutu.<br /><br /> Geçerli değerler: pozitif tamsayılar<br /><br /> Varsayılan değer: `0`, yığın boyutu için işlemin varsayılan değerinin kullanıldığını belirtir.|
|`DynamicProgressFeedback`|Zamanlayıcı kaynaklarının, Scheduler 'dan toplanan istatistiksel bilgilere göre veya yalnızca temel alınan donanım iş parçacıklarının abonelik düzeyine göre yeniden dengelendirilip dengeedilmeyeceğini belirler. Daha fazla bilgi için bkz. [DynamicProgressFeedbackType](#dynamicprogressfeedbacktype).<br /><br /> Geçerli değerler: `DynamicProgressFeedbackType` numaralandırmanın bir üyesi, `ProgressFeedbackEnabled` veya `ProgressFeedbackDisabled`<br /><br /> Varsayılan değer: `ProgressFeedbackEnabled`|
|`LocalContextCacheSize`|`SchedulingProtocol` ilke anahtarı `EnhanceScheduleGroupLocality`değere ayarlandığında, sanal işlemci yerel sıraları başına önbellekte izin verilen en fazla çalıştırılabilir bağlam sayısını belirtir. Bu tür bağlamlar, genellikle sanal işlemcide çalıştırılabilir duruma gelmesine neden olan en son ilk çıkar (LıFO) sırasıyla çalıştırılır. Bu ilke anahtarının, `SchedulingProtocol` anahtarı değer `EnhanceForwardProgress`ayarlandığında hiçbir anlamı olmadığını unutmayın.<br /><br /> Geçerli değerler: negatif olmayan tamsayılar<br /><br /> Varsayılan değer: `8`|
|`MaxConcurrency`|Zamanlayıcı tarafından istenen en fazla eşzamanlılık düzeyi. Resource Manager, başlangıçta bu çok sayıda sanal işlemciyi ayırmaya çalışacaktır. [MaxExecutionResources](concurrency-namespace-constants1.md#maxexecutionresources) özel değeri, istenen eşzamanlılık düzeyinin makinedeki donanım iş parçacığı sayısıyla aynı olduğunu gösterir. `MinConcurrency` için belirtilen değer, makinedeki donanım iş parçacıklarının sayısından büyükse ve `MaxConcurrency` `MaxExecutionResources`olarak belirtilmişse, `MaxConcurrency` değeri `MinConcurrency`için ayarlanmış şekilde eşleşecek şekilde tetiklenir.<br /><br /> Geçerli değerler: pozitif tamsayılar ve özel değer `MaxExecutionResources`<br /><br /> Varsayılan değer: `MaxExecutionResources`|
|`MaxPolicyElementKey`|En yüksek ilke öğesi anahtarı. Geçerli bir öğe anahtarı değil.|
|`MinConcurrency`|Kaynak Yöneticisi tarafından Scheduler 'a sağlanması gereken en düşük eşzamanlılık düzeyi. Bir Scheduler 'a atanan sanal işlemcilerin sayısı, hiçbir şekilde en düşük değerin altına gitmeyecektir. [MaxExecutionResources](concurrency-namespace-constants1.md#maxexecutionresources) özel değeri, en düşük eşzamanlılık düzeyinin makinedeki donanım iş parçacığı sayısıyla aynı olduğunu gösterir. `MaxConcurrency` için belirtilen değer makinedeki donanım iş parçacıklarının sayısından küçükse ve `MinConcurrency` `MaxExecutionResources`olarak belirtilmişse, `MinConcurrency` değeri `MaxConcurrency`için ayarlanan değere indirgentirecektir.<br /><br /> Geçerli değerler: negatif olmayan tamsayılar ve `MaxExecutionResources`özel değeri. Eşzamanlılık Çalışma Zamanı zamanlayıcılar yapımı için kullanılan Zamanlayıcı ilkeleri için `0` değer geçersiz.<br /><br /> Varsayılan değer: `1`|
|`SchedulerKind`|Scheduler 'ın temel yürütme bağlamlarında kullanacağı iş parçacıklarının türü. Daha fazla bilgi için bkz. [SchedulerType](#schedulertype).<br /><br /> Geçerli değerler: `SchedulerType` numaralandırmanın bir üyesi, örneğin, `ThreadScheduler`<br /><br /> Varsayılan değer: `ThreadScheduler`. Bu, tüm işletim sistemlerindeki Win32 iş parçacıklarını çevirir.|
|`SchedulingProtocol`|Zamanlayıcı tarafından hangi zamanlama algoritmasının kullanılacağını açıklar. Daha fazla bilgi için bkz. [SchedulingProtocolType](#schedulingprotocoltype).<br /><br /> Geçerli değerler: `SchedulingProtocolType` numaralandırmanın bir üyesi, `EnhanceScheduleGroupLocality` veya `EnhanceForwardProgress`<br /><br /> Varsayılan değer: `EnhanceScheduleGroupLocality`|
|`TargetOversubscriptionFactor`|Donanım iş parçacığı başına belirsiz sanal işlemci sayısı. Hedef aşırı abonelik faktörü, gerekirse makinedeki donanım iş parçacıklarıyla `MaxConcurrency` karşılamak için Kaynak Yöneticisi tarafından artırılabilir.<br /><br /> Geçerli değerler: pozitif tamsayılar<br /><br /> Varsayılan değer: `1`|
|`WinRTInitialization`||

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** concrt. h

## <a name="schedulertype"></a>SchedulerType numaralandırması

`SchedulerKind` ilkesi tarafından, Scheduler 'ın temel yürütme bağlamlarında kullanmasını gereken iş parçacıklarının türünü betimleyen tarafından kullanılır. Kullanılabilir Zamanlayıcı ilkeleri hakkında daha fazla bilgi için bkz. [PolicyElementKey](concurrency-namespace-enums.md).

```cpp
enum SchedulerType;
```

### <a name="values"></a>Değerler

|Ad|Açıklama|
|----------|-----------------|
|`ThreadScheduler`|Normal Win32 iş parçacıklarının açık bir isteğini gösterir.|
|`UmsThreadDefault`|Kullanıcı modu zamanlanabilen (UMS) iş parçacıkları Visual Studio 2013 Eşzamanlılık Çalışma Zamanı desteklenmez. `SchedulerType` ilkesi için değer olarak `UmsThreadDefault` kullanmak bir hatayla sonuçlanmaz. Ancak, bu ilkeyle oluşturulan bir zamanlayıcı, varsayılan olarak Win32 iş parçacıklarını kullanmaktır.|

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** concrt. h

## <a name="schedulingprotocoltype"></a>SchedulingProtocolType numaralandırması

Zamanlayıcı için hangi zamanlama algoritmasının kullanılacağını açıklayan `SchedulingProtocol` ilkesi tarafından kullanılır. Kullanılabilir Zamanlayıcı ilkeleri hakkında daha fazla bilgi için bkz. [PolicyElementKey](concurrency-namespace-enums.md).

```cpp
enum SchedulingProtocolType;
```

### <a name="values"></a>Değerler

|Ad|Açıklama|
|----------|-----------------|
|`EnhanceForwardProgress`|Zamanlayıcı, her bir görevi yürütmeden sonra zamanlama grupları aracılığıyla hepsini bir kez kullanmayı tercih eder. Engellenmemiş bağlamlar genellikle ilk kez ilk çıkar (FıFO) biçimde zamanlanır. Sanal işlemciler engellenmemiş bağlamlara önbelleğe vermez.|
|`EnhanceScheduleGroupLocality`|Zamanlayıcı, başka bir zamanlama grubuna geçmeden önce geçerli zamanlama grubundaki görevler üzerinde çalışmaya devam etmeyi tercih eder. Engellenmemiş bağlamlar, sanal işlemci başına önbelleğe alınır ve tipik olarak, engellenmemiş sanal işlemci tarafından ilk kez son çıkar (LıFO) ile zamanlanır.|

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** concrt. h

## <a name="switchingproxystate"></a>SwitchingProxyState numaralandırması

Bir iş parçacığı proxy 'sinin içinde olduğu durumu belirtmek için kullanılır ve farklı bir iş parçacığı proxy 'sine bir işbirlikçi bağlamı anahtarı yürüttüyordur.

```cpp
enum SwitchingProxyState;
```

### <a name="values"></a>Değerler

|Ad|Açıklama|
|----------|-----------------|
|`Blocking`|Çağıran iş parçacığının, daha sonra yeniden çalışmaya ve başka eylem gerçekleştirmeye kadar çağırılmasının yanı sıra, çağıran iş parçacığının özel olarak engellendiğini belirtir.|
|`Idle`|Çağıran iş parçacığının Zamanlayıcı tarafından artık gerekli olmadığını ve Kaynak Yöneticisi döndürülmekte olduğunu gösterir. Dağıtılan bağlam artık Kaynak Yöneticisi tarafından kullanılamıyor.|
|`Nesting`|Çağıran iş parçacığının bir alt zamanlayıcıyı iç içe aldığını ve farklı bir Scheduler 'a iliştirmek için çağıranın gerekli olduğunu gösterir.|

### <a name="remarks"></a>Açıklamalar

Çağrıyı yapan iş parçacığı proxy 'sini nasıl değerlendirdiğini Kaynak Yöneticisi bildirmek için `IThreadProxy::SwitchTo` yöntemine `SwitchingProxyState` türünde bir parametre geçirilir.

Bu türün nasıl kullanıldığı hakkında daha fazla bilgi için bkz. [IThreadProxy:: SwitchTo](ithreadproxy-structure.md#switchto).

## <a name="task_group_status"></a>task_group_status numaralandırması

Bir `task_group` veya `structured_task_group` nesnesinin yürütme durumunu açıklar. Bu türden bir değer, bir görev grubuna zamanlanan görevlerin tamamlanmasını bekleyen çok sayıda yöntem tarafından döndürülür.

```cpp
enum task_group_status;
```

### <a name="values"></a>Değerler

|Ad|Açıklama|
|----------|-----------------|
|`canceled`|`task_group` veya `structured_task_group` nesnesi iptal edildi. Bir veya daha fazla görev yürütülmeyebilir.|
|`completed`|`task_group` veya `structured_task_group` nesnesine sıraya alınan görevler başarıyla tamamlandı.|
|`not_complete`|`task_group` nesnesine sıraya alınan görevler tamamlanmadı. Bu değerin Şu anda Eşzamanlılık Çalışma Zamanı tarafından döndürülmediğini unutmayın.|

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** pplınterface. h

## <a name="winrtinitializationtype"></a>WinRTInitializationType numaralandırması

`WinRTInitialization` ilkesi tarafından, Windows 8 veya üzeri sürümü olan işletim sistemlerinde çalışan bir uygulama için zamanlayıcı iş parçacıklarında ve Windows Çalışma Zamanı nasıl başlatılabileceğini açıklayan bir ilke tarafından kullanılır. Kullanılabilir Zamanlayıcı ilkeleri hakkında daha fazla bilgi için bkz. [PolicyElementKey](concurrency-namespace-enums.md).

```cpp
enum WinRTInitializationType;
```

### <a name="values"></a>Değerler

|Ad|Açıklama|
|----------|-----------------|
|`DoNotInitializeWinRT`|Uygulama, Windows 8 veya üzeri sürümü olan işletim sistemlerinde çalıştırıldığında, Zamanlayıcı içindeki iş parçacıkları Windows Çalışma Zamanı başlatmaz.|
|`InitializeWinRTAsMTA`|Uygulama, Windows 8 veya üzeri sürümü olan işletim sistemlerinde çalıştırıldığında, Zamanlayıcı içindeki her bir iş parçacığı Windows Çalışma Zamanı başlatır ve çok iş parçacıklı grubun bir parçası olduğunu bildirir.|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** concrt. h

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)
