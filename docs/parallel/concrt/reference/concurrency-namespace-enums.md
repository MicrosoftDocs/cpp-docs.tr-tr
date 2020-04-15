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
ms.openlocfilehash: e3a943ed52ce9653086203713bb98331f809314d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372719"
---
# <a name="concurrency-namespace-enums"></a>eşzamanlılık ad alanı sabit listeleri

||||
|-|-|-|
|[Agents_EventType](#agents_eventtype)|[ConcRT_EventType](#concrt_eventtype)|[Concrt_TraceFlags](#concrt_traceflags)|
|[KritikRegionType](#criticalregiontype)|[DynamicProgressFeedbackType](#dynamicprogressfeedbacktype)|[PolicyElementKey](#policyelementkey)|
|[SchedulerType](#schedulertype)|[ZamanlamaProtokolTipi](#schedulingprotocoltype)|[AnahtarlamaProxyState](#switchingproxystate)|
|[WinRTInitializationType](#winrtinitializationtype)|[agent_status](#agent_status)|[join_type](#join_type)|
|[message_status](#message_status)|[task_group_status](#task_group_status)|

## <a name="agent_status-enumeration"></a><a name="agent_status"></a>agent_status Numaralandırma

Bir `agent`için geçerli durumlar .

```cpp
enum agent_status;
```

### <a name="values"></a>Değerler

|Adı|Açıklama|
|----------|-----------------|
|`agent_canceled`|İptal `agent` edildi.|
|`agent_created`|Oluşturuldu, `agent` ancak başlatılmamadı.|
|`agent_done`|İptal `agent` edilmeden bitti.|
|`agent_runnable`|Başlatıldı, `agent` ancak yöntemi girilemedi. `run`|
|`agent_started`|Başladı. `agent`|

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [Bkz.](../../../parallel/concrt/asynchronous-agents.md)

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** concrt.h

## <a name="agents_eventtype-enumeration"></a><a name="agents_eventtype"></a>Agents_EventType Numaralandırma

Aracılar Kitaplığı tarafından sunulan izleme işlevleri kullanılarak izlenebilecek olay türleri

```cpp
enum Agents_EventType;
```

### <a name="values"></a>Değerler

|Adı|Açıklama|
|----------|-----------------|
|`AGENTS_EVENT_CREATE`|Nesnenin oluşturulmasını temsil eden bir olay türü|
|`AGENTS_EVENT_DESTROY`|Nesnenin silinmesini temsil eden bir olay türü|
|`AGENTS_EVENT_END`|Bazı işlemlerin sonucunu temsil eden bir olay türü|
|`AGENTS_EVENT_LINK`|İleti bloklarının bağlantısını temsil eden bir olay türü|
|`AGENTS_EVENT_NAME`|Bir nesnenin adını temsil eden bir olay türü|
|`AGENTS_EVENT_SCHEDULE`|Bir işlemin zamanlamasını temsil eden bir olay türü|
|`AGENTS_EVENT_START`|Bazı işlemlerin başlatılmasını temsil eden bir olay türü|
|`AGENTS_EVENT_UNLINK`|İleti bloklarının bağlantısızlığı temsil eden bir olay türü|

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** concrt.h

## <a name="concrt_eventtype-enumeration"></a><a name="concrt_eventtype"></a>ConcRT_EventType Numaralandırma

Eşzamanlılık Çalışma Zamanı tarafından sunulan izleme işlevini kullanarak izlenebilecek olay türleri.

```cpp
enum ConcRT_EventType;
```

### <a name="values"></a>Değerler

|Adı|Açıklama|
|----------|-----------------|
|`CONCRT_EVENT_ATTACH`|Zamanlayıcıya iliştirme eylemini temsil eden bir olay türü.|
|`CONCRT_EVENT_BLOCK`|Bağlam engelleme eylemini temsil eden bir olay türü.|
|`CONCRT_EVENT_DETACH`|Zamanlayıcıdan ayırma eylemini temsil eden bir olay türü.|
|`CONCRT_EVENT_END`|Başlangıç/bitiş olay çiftinin başlangıcını işaretleyen bir olay türü.|
|`CONCRT_EVENT_GENERIC`|Çeşitli olaylar için kullanılan bir olay türü.|
|`CONCRT_EVENT_IDLE`|Bir bağlamın boşta kalma eylemini temsil eden bir olay türü.|
|`CONCRT_EVENT_START`|Başlangıç/bitiş olay çiftinin başlangıcını işaretleyen bir olay türü.|
|`CONCRT_EVENT_UNBLOCK`|Bir bağlamın engelini kaldırma eylemini temsil eden bir olay türü.|
|`CONCRT_EVENT_YIELD`|Bir bağlamın içeriğini temsil eden olay türü.|

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** concrt.h **Namespace:** eşzamanlılık

## <a name="concrt_traceflags-enumeration"></a><a name="concrt_traceflags"></a>Concrt_TraceFlags Numaralandırma

Olay türleri için bayrakları izleme

```cpp
enum Concrt_TraceFlags;
```

### <a name="values"></a>Değerler

|Adı|Açıklama|
|----------|-----------------|
|`AgentEventFlag`||
|`AllEventsFlag`||
|`ContextEventFlag`||
|`PPLEventFlag`||
|`ResourceManagerEventFlag`||
|`SchedulerEventFlag`||
|`VirtualProcessorEventFlag`||

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** concrt.h

## <a name="criticalregiontype-enumeration"></a><a name="criticalregiontype"></a>KritikRegionType Numaralandırma

Bir bağlamın içinde bulunduğu kritik bölge türü.

```cpp
enum CriticalRegionType;
```

### <a name="values"></a>Değerler

|Adı|Açıklama|
|----------|-----------------|
|`InsideCriticalRegion`|Bağlamın kritik bir bölgenin içinde olduğunu gösterir. Kritik bir bölgenin içindeyken, eşzamanlı süspansiyonlar zamanlayıcıdan gizlenir. Böyle bir askıya alma gerçekleşirse, Kaynak Yöneticisi iş parçacığının çalıştırılabilir olmasını bekler ve zamanlayıcıyı yeniden çağırmak yerine yeniden devam ettirebilir. Böyle bir bölgede alınan herhangi bir kilitler son derece dikkatli alınmalıdır.|
|`InsideHyperCriticalRegion`|Bağlamın hiper kritik bir bölgenin içinde olduğunu gösterir. Hiper kritik bir bölgenin içindeyken, hem senkron hem de eşzamanlı süspansiyonlar zamanlayıcıdan gizlenir. Böyle bir askıya alma veya engelleme gerçekleşirse, kaynak yöneticisi iş parçacığının çalıştırılabilir olmasını bekler ve zamanlayıcıyı yeniden çağırmak yerine yeniden devam ettirebilir. Böyle bir bölgenin içinde alınan kilitler, böyle bir bölgenin dışında çalışan kodlarla asla paylaşılmamamalıdır. Bunu yapmak öngörülemeyen kilitlenme neden olur.|
|`OutsideCriticalRegion`|Bağlamın herhangi bir kritik bölgenin dışında olduğunu gösterir.|

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** concrtrm.h

## <a name="dynamicprogressfeedbacktype-enumeration"></a><a name="dynamicprogressfeedbacktype"></a>DynamicProgressFeedbackType Numaralandırma

Zamanlayıcıiçin kaynakların zamanlayıcıdan toplanan istatistiksel bilgilere göre mi yoksa `IVirtualProcessorRoot` yalnızca boşta duruma girip çıkan sanal işlemcilere dayalı olarak mı `Activate` `Deactivate` yeniden dengelenecek ve arabirimdeki aramalar yoluyla yeniden dengelenip dinletmeyeceğini açıklamak için ilke tarafından kullanılır. `DynamicProgressFeedback` Kullanılabilir zamanlayıcı ilkeleri hakkında daha fazla bilgi için [PolicyElementKey'e](concurrency-namespace-enums.md)bakın.

```cpp
enum DynamicProgressFeedbackType;
```

### <a name="values"></a>Değerler

|Adı|Açıklama|
|----------|-----------------|
|`ProgressFeedbackDisabled`|Zamanlayıcı ilerleme bilgilerini toplamaz. Yeniden dengeleme yalnızca temel donanım iş parçacığının abonelik düzeyine göre yapılır. Abonelik düzeyleri hakkında daha fazla bilgi için [bkz: IExecutionResource::CurrentSubscriptionLevel](IExecutionResource-structure.md).<br /><br /> Bu değer çalışma süresine göre kullanılmak üzere ayrılmıştır.|
|`ProgressFeedbackEnabled`|Zamanlayıcı ilerleme bilgilerini toplar ve kaynak yöneticisine aktarın. Kaynak yöneticisi, temel donanım iş parçacığının abonelik düzeyine ek olarak zamanlayıcı adına kaynakları yeniden dengelemek için bu istatistiksel bilgileri kullanır. Abonelik düzeyleri hakkında daha fazla bilgi için [bkz: IExecutionResource::CurrentSubscriptionLevel](IExecutionResource-structure.md).|

## <a name="join_type-enumeration"></a><a name="join_type"></a>join_type Numaralandırma

`join` İleti bloğu türü.

```cpp
enum join_type;
```

### <a name="values"></a>Değerler

|Adı|Açıklama|
|----------|-----------------|
|`greedy`|Açgözlü `join` mesajlaşma blokları hemen yayılma üzerine bir ileti kabul. Bu daha verimlidir, ancak ağ yapılandırması bağlı olarak canlı kilit olasılığı vardır.|
|`non_greedy`|Açgözlü olmayan `join` mesajlaşma blokları iletileri erteler ve tüm geldikten sonra bunları tüketmeye çalışır. Bu çalışmak için garanti, ama daha yavaş.|

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** agents.h

## <a name="message_status-enumeration"></a><a name="message_status"></a>message_status Numaralandırma

Bir `message` nesneye bir nesne teklifi için geçerli yanıtlar.

```cpp
enum message_status;
```

### <a name="values"></a>Değerler

|Adı|Açıklama|
|----------|-----------------|
|`accepted`|Hedef iletiyi kabul etti.|
|`declined`|Hedef iletiyi kabul etmedi.|
|`missed`|Hedef iletiyi kabul etmeye çalıştı, ancak artık kullanılanındeğildi.|
|`postponed`|Hedef mesajı erteledi.|

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** agents.h

## <a name="policyelementkey-enumeration"></a><a name="policyelementkey"></a>PolicyElementKey Numaralandırma

Zamanlayıcı davranışının yönlerini açıklayan ilke anahtarları. Her ilke öğesi bir anahtar değer çifti tarafından açıklanır. Zamanlayıcı ilkeleri ve bunların zamanlayıcılar üzerindeki etkileri hakkında daha fazla bilgi için [Görev Zamanlayıcısı'na](../../../parallel/concrt/task-scheduler-concurrency-runtime.md)bakın.

```cpp
enum PolicyElementKey;
```

### <a name="values"></a>Değerler

|Adı|Açıklama|
|----------|-----------------|
|`ContextPriority`|Zamanlayıcıdaki her bağlamın işletim sistemi iş parçacığı önceliği. Bu anahtar değere `INHERIT_THREAD_PRIORITY` ayarlanırsa, zamanlayıcıdaki bağlamlar zamanlayıcıyı oluşturan iş parçacığının önceliğini devralır.<br /><br /> Geçerli değerler : Windows `SetThreadPriority` işlevi ve özel değer için geçerli değerlerden herhangi biri`INHERIT_THREAD_PRIORITY`<br /><br /> Varsayılan değer :`THREAD_PRIORITY_NORMAL`|
|`ContextStackSize`|Kilobaytolarak zamanlayıcıdaki her bağlamın ayrılmış yığın boyutu.<br /><br /> Geçerli değerler : Pozitif tamsayılar<br /><br /> Varsayılan değer `0`: , işlemin yığın boyutu için varsayılan değerinin kullanılacağını gösterir.|
|`DynamicProgressFeedback`|Zamanlayıcıiçin kaynakların zamanlayıcıdan toplanan istatistiksel bilgilere göre mi yoksa yalnızca temel donanım iş parçacıklarının abonelik düzeyine göre mi yeniden dengeleneceklerini belirler. Daha fazla bilgi için Bkz. [DynamicProgressFeedbackType](#dynamicprogressfeedbacktype).<br /><br /> Geçerli değerler : Numaralandırmanın `DynamicProgressFeedbackType` bir üyesi, ya da `ProgressFeedbackEnabled``ProgressFeedbackDisabled`<br /><br /> Varsayılan değer :`ProgressFeedbackEnabled`|
|`LocalContextCacheSize`|İlke `SchedulingProtocol` anahtarı değere `EnhanceScheduleGroupLocality`ayarlandığında, bu, sanal işlemci yerel kuyrukları başına önbelleğe alınmasına izin verilen en fazla çalıştırılabilir bağlam sayısını belirtir. Bu tür bağlamlar genellikle, sanal işlemcide çalıştırılabilir hale gelmesine neden olan ilk çıkışson sırada (LIFO) çalışır. Anahtar değere `EnhanceForwardProgress`ayarlandığında bu `SchedulingProtocol` ilke anahtarının hiçbir anlamı olmadığını unutmayın.<br /><br /> Geçerli değerler : Negatif olmayan tümseler<br /><br /> Varsayılan değer :`8`|
|`MaxConcurrency`|Zamanlayıcı tarafından istenen maksimum eşzamanlılık düzeyi. Kaynak yöneticisi başlangıçta bu kadar çok sanal işlemci ayırmaya çalışacaktır. [MaxExecutionResources](concurrency-namespace-constants1.md#maxexecutionresources) özel değeri, istenen eşzamanlılık düzeyinin makinedeki donanım iş parçacığı sayısıyla aynı olduğunu gösterir. Belirtilen `MinConcurrency` değer makinedeki donanım iş parçacığı sayısından büyükse `MaxConcurrency` ve `MaxExecutionResources`" için `MaxConcurrency` değer, ayarlanana `MinConcurrency`uyacak şekilde yükseltilir.<br /><br /> Geçerli değerler : Pozitif tamsayılar ve özel değer`MaxExecutionResources`<br /><br /> Varsayılan değer :`MaxExecutionResources`|
|`MaxPolicyElementKey`|Maksimum ilke öğesi anahtarı. Geçerli bir öğe anahtarı değil.|
|`MinConcurrency`|Kaynak yöneticisi tarafından zamanlayıcıya sağlanacak minimum eşzamanlılık düzeyi. Zamanlayıcıya atanan sanal işlemci sayısı hiçbir zaman minimumun altına inmez. Özel değer [MaxExecutionResources](concurrency-namespace-constants1.md#maxexecutionresources) minimum eşzamanlılık düzeyi makinedeki donanım iş parçacığı sayısı ile aynı olduğunu gösterir. `MaxConcurrency` Belirtilen değer makinedeki donanım iş parçacığı sayısından daha `MinConcurrency` azsa `MaxExecutionResources`ve " `MinConcurrency` değeri, için `MaxConcurrency`ayarlanana uyacak şekilde indirilir.<br /><br /> Geçerli değerler : Negatif olmayan tümsalar `MaxExecutionResources`ve özel değer . EşzamanlıÇalışma zamanı zamanlayıcılarının yapımı için kullanılan zamanlayıcı ilkeleri için `0` değerin geçersiz olduğunu unutmayın.<br /><br /> Varsayılan değer :`1`|
|`SchedulerKind`|Zamanlayıcının temel yürütme bağlamları için kullanabileceği iş parçacığı türü. Daha fazla bilgi için [Bkz. SchedulerType.](#schedulertype)<br /><br /> Geçerli değerler : Numaralandırmanın `SchedulerType` bir üyesi, örneğin,`ThreadScheduler`<br /><br /> Varsayılan değer `ThreadScheduler`: . Bu, tüm işletim sistemlerinde Win32 iş parçacığı anlamına gelir.|
|`SchedulingProtocol`|Zamanlama algoritmasının zamanlayıcı tarafından kullanılacağını açıklar. Daha fazla bilgi için Bkz. [SchedulingProtocolType](#schedulingprotocoltype).<br /><br /> Geçerli değerler : Numaralandırmanın `SchedulingProtocolType` bir üyesi, ya da `EnhanceScheduleGroupLocality``EnhanceForwardProgress`<br /><br /> Varsayılan değer :`EnhanceScheduleGroupLocality`|
|`TargetOversubscriptionFactor`|Donanım iş parçacığı başına geçici sanal işlemci sayısı. Hedef fazla abonelik faktörü, gerekirse makinedeki donanım iş `MaxConcurrency` parçacığı ile tatmin etmek için Kaynak Yöneticisi tarafından artırılabilir.<br /><br /> Geçerli değerler : Pozitif tamsayılar<br /><br /> Varsayılan değer :`1`|
|`WinRTInitialization`||

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** concrt.h

## <a name="schedulertype-enumeration"></a><a name="schedulertype"></a>SchedulerTip Numaralandırma

İlke `SchedulerKind` tarafından, zamanlamanın alttaki yürütme bağlamları için kullanması gereken iş parçacığı türünü açıklamak için kullanılır. Kullanılabilir zamanlayıcı ilkeleri hakkında daha fazla bilgi için [PolicyElementKey'e](concurrency-namespace-enums.md)bakın.

```cpp
enum SchedulerType;
```

### <a name="values"></a>Değerler

|Adı|Açıklama|
|----------|-----------------|
|`ThreadScheduler`|Normal Win32 iş parçacıklarının açık bir isteğini gösterir.|
|`UmsThreadDefault`|Visual Studio 2013'teki Eşzamanlılık Çalışma Süresi'nde kullanıcı modu programlanabilir (UMS) iş parçacıkları desteklenmez. İlke `UmsThreadDefault` `SchedulerType` için bir değer olarak kullanmak bir hataya neden olmaz. Ancak, bu ilke ile oluşturulan bir zamanlayıcı Win32 iş parçacığı kullanarak varsayılan olacaktır.|

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** concrt.h

## <a name="schedulingprotocoltype-enumeration"></a><a name="schedulingprotocoltype"></a>ZamanlamaProtokolTipi Numaralandırma

Zamanlayıcı `SchedulingProtocol` için hangi zamanlama algoritmasının kullanılacağını açıklamak için ilke tarafından kullanılır. Kullanılabilir zamanlayıcı ilkeleri hakkında daha fazla bilgi için [PolicyElementKey'e](concurrency-namespace-enums.md)bakın.

```cpp
enum SchedulingProtocolType;
```

### <a name="values"></a>Değerler

|Adı|Açıklama|
|----------|-----------------|
|`EnhanceForwardProgress`|Zamanlayıcı, her görevi çalıştırdıktan sonra zamanlama grupları arasında yuvarla-robin tercih eder. Engellenmemiş bağlamlar genellikle ilk ilk çıkış (FIFO) şekilde zamanlanır. Sanal işlemciler engellenmemiş bağlamları önbelleğe vermez.|
|`EnhanceScheduleGroupLocality`|Zamanlayıcı, başka bir zamanlama grubuna geçmeden önce geçerli zamanlama grubu içindeki görevler üzerinde çalışmaya devam etmeyi tercih eder. Engellenmemiş bağlamlar sanal işlemci başına önbelleğe alınır ve genellikle engellerini kaldıran sanal işlemci tarafından ilk son (LIFO) şeklinde zamanlanır.|

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** concrt.h

## <a name="switchingproxystate-enumeration"></a><a name="switchingproxystate"></a>SwitchingProxyState Numaralandırma

İş parçacığı proxy'sinin içinde olduğu durumu belirtmek için kullanılır, işbirlikli bir bağlam proxy'sine geçiş yaparken.

```cpp
enum SwitchingProxyState;
```

### <a name="values"></a>Değerler

|Adı|Açıklama|
|----------|-----------------|
|`Blocking`|Arama iş parçacığının işbirliği içinde engellendiğini ve daha sonra yeniden çalışana ve başka bir eylem gerçekleştirene kadar yalnızca arayanın sahip olması gerektiğini gösterir.|
|`Idle`|Arama iş parçacığının artık zamanlayıcı tarafından gerekli olmadığını ve Kaynak Yöneticisi'ne döndürülmekte olduğunu gösterir. Gönderilen bağlam artık Kaynak Yöneticisi tarafından kullanılamaz.|
|`Nesting`|Arama iş parçacığının bir alt zamanlayıcıyı iç içe geçirerek farklı bir zamanlayıcıya eklemek için arayanın gerekli olduğunu gösterir.|

### <a name="remarks"></a>Açıklamalar

Kaynak Yöneticisi'ne `SwitchingProxyState` aramayı yapan iş `IThreadProxy::SwitchTo` parçacığı proxy'sinin nasıl işlenirse nasıl davranılsüreceğini öğretmek için yönteme bir tür parametresi geçirilir.

Bu türün nasıl kullanıldığı hakkında daha fazla bilgi için [Bkz. IThreadProxy::SwitchTo](ithreadproxy-structure.md#switchto).

## <a name="task_group_status-enumeration"></a><a name="task_group_status"></a>task_group_status Numaralandırma

Bir `task_group` veya `structured_task_group` nesnenin yürütme durumunu açıklar. Bu tür bir değer, tamamlanması gereken bir görev grubuna zamanlanan görevleri bekleyen çok sayıda yöntemle döndürülür.

```cpp
enum task_group_status;
```

### <a name="values"></a>Değerler

|Adı|Açıklama|
|----------|-----------------|
|`canceled`|Nesne `task_group` `structured_task_group` veya nesne iptal edildi. Bir veya daha fazla görev yürütülmemiş olabilir.|
|`completed`|Başarılı bir şekilde `task_group` tamamlanan `structured_task_group` veya nesneye sıralanmış görevler.|
|`not_complete`|`task_group` Nesneye sıralanmış görevler tamamlanmadı. Bu değerin Eşzamanlı Çalışma Zamanı tarafından şu anda döndürülmediğini unutmayın.|

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** pplinterface.h

## <a name="winrtinitializationtype-enumeration"></a><a name="winrtinitializationtype"></a>WinRTInitializationTip Numaralandırma

`WinRTInitialization` Windows 8 veya daha yüksek sürüm işletim sistemlerinde çalışan bir uygulama için Windows Runtime'ın zamanlayıcı iş parçacıklarında başharfe mi ve nasıl başharfe verilip verilmeyeceğini açıklamak için ilke tarafından kullanılır. Kullanılabilir zamanlayıcı ilkeleri hakkında daha fazla bilgi için [PolicyElementKey'e](concurrency-namespace-enums.md)bakın.

```cpp
enum WinRTInitializationType;
```

### <a name="values"></a>Değerler

|Adı|Açıklama|
|----------|-----------------|
|`DoNotInitializeWinRT`|Uygulama Windows 8 veya daha yüksek sürüme sahip işletim sistemlerinde çalıştırıldığında, zamanlayıcıiçindeki iş parçacıkları Windows Runtime'ı başlatmaz.|
|`InitializeWinRTAsMTA`|Uygulama Windows 8 veya daha yüksek sürüme sahip işletim sistemlerinde çalıştırıldığında, zamanlayıcıiçindeki her iş parçacığı Windows Runtime'ı başlattı ve çok iş parçacığı yla dolu dairenin bir parçası olduğunu beyan eder.|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** concrt.h

## <a name="see-also"></a>Ayrıca bkz.

[concurrency Ad Alanı](concurrency-namespace.md)
