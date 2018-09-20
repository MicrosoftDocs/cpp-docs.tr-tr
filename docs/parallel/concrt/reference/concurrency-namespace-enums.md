---
title: Eşzamanlılık ad alanı sabit listeleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
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
dev_langs:
- C++
ms.assetid: a40e3b2d-ad21-4229-9880-2cfa84f7ab8f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 69b11a78d1be76895b9687d1423df74c51fe3d39
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46416701"
---
# <a name="concurrency-namespace-enums"></a>Eşzamanlılık ad alanı sabit listeleri

||||
|-|-|-|
|[Agents_EventType](#agents_eventtype)|[ConcRT_EventType](#concrt_eventtype)|[Concrt_TraceFlags](#concrt_traceflags)|
|[CriticalRegionType](#criticalregiontype)|[DynamicProgressFeedbackType](#dynamicprogressfeedbacktype)|[PolicyElementKey](#policyelementkey)|
|[SchedulerType](#schedulertype)|[SchedulingProtocolType](#schedulingprotocoltype)|[SwitchingProxyState](#switchingproxystate)|
|[Winrtınitializationtype](#winrtinitializationtype)|[agent_status](#agent_status)|[join_type](#join_type)|
|[message_status](#message_status)|[task_group_status](#task_group_status)|

##  <a name="agent_status"></a>  agent_status numaralandırması

Geçerli durumları bir `agent`.

```
enum agent_status;
```
### <a name="values"></a>Değerler

|Ad|Açıklama|
|----------|-----------------|
|`agent_canceled`|`agent` İptal edildi.|
|`agent_created`|`agent` Oluşturuldu, ancak başlatılmadı.|
|`agent_done`|`agent` İptal olmadan bitti.|
|`agent_runnable`|`agent` Başlatıldı, ancak girilmedi kendi `run` yöntemi.|
|`agent_started`|`agent` Başlatıldı.|

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [zaman uyumsuz aracılar](../../../parallel/concrt/asynchronous-agents.md).

### <a name="requirements"></a>Gereksinimler

**Başlık:** concrt.h

##  <a name="agents_eventtype"></a>  Agents_EventType numaralandırması

Aracılar Kitaplığı tarafından sunulan izleme işlevselliği kullanılarak izlenebilir olay türleri

```
enum Agents_EventType;
```

### <a name="values"></a>Değerler

|Ad|Açıklama|
|----------|-----------------|
|`AGENTS_EVENT_CREATE`|Bir nesne oluşturmayı gösteren bir olay türü|
|`AGENTS_EVENT_DESTROY`|Nesne silme işlemini temsil eden bir olay türü|
|`AGENTS_EVENT_END`|İşleme sonuç bazı temsil eden bir olay türü|
|`AGENTS_EVENT_LINK`|İleti blokları bağlama temsil eden bir olay türü|
|`AGENTS_EVENT_NAME`|Bir nesnenin adını temsil eden bir olay türü|
|`AGENTS_EVENT_SCHEDULE`|Zamanlama bir işlemi temsil eden bir olay türü|
|`AGENTS_EVENT_START`|İşleme başlatma bazı temsil eden bir olay türü|
|`AGENTS_EVENT_UNLINK`|İleti blokları bağlantısını temsil eden bir olay türü|

### <a name="requirements"></a>Gereksinimler

**Başlık:** concrt.h

##  <a name="concrt_eventtype"></a>  ConcRT_EventType numaralandırması

Eşzamanlılık Çalışma zamanı tarafından sunulan izleme işlevselliği kullanılarak izlenebilir olay türleri.

```
enum ConcRT_EventType;
```
### <a name="values"></a>Değerler

|Ad|Açıklama|
|----------|-----------------|
|`CONCRT_EVENT_ATTACH`|Ekleme için bir zamanlayıcı eylemi temsil eden bir olay türü.|
|`CONCRT_EVENT_BLOCK`|Bir bağlam engelleme eylemi temsil eden bir olay türü.|
|`CONCRT_EVENT_DETACH`|Ayırma bir Zamanlayıcıdan eylemi temsil eden bir olay türü.|
|`CONCRT_EVENT_END`|Başlangıç/Bitiş olay çifti başlangıcını işaretleyen bir olay türü.|
|`CONCRT_EVENT_GENERIC`|Çeşitli olaylar için kullanılan bir olay türü.|
|`CONCRT_EVENT_IDLE`|Bir bağlamı olmak boşta işlemi temsil eden bir olay türü.|
|`CONCRT_EVENT_START`|Başlangıç/Bitiş olay çifti başlangıcını işaretleyen bir olay türü.|
|`CONCRT_EVENT_UNBLOCK`|Bir bağlamı kaldırma işlemi temsil eden bir olay türü.|
|`CONCRT_EVENT_YIELD`|Bir bağlam sonuçlanmıyor eylemi temsil eden bir olay türü.|

### <a name="requirements"></a>Gereksinimler

**Başlık:** concrt.h **Namespace:** eşzamanlılık

##  <a name="concrt_traceflags"></a>  Concrt_TraceFlags numaralandırması

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

##  <a name="criticalregiontype"></a>  CriticalRegionType numaralandırması

Kritik bölgesinin bir bağlam içinde türüdür.

```
enum CriticalRegionType;
```
### <a name="values"></a>Değerler

|Ad|Açıklama|
|----------|-----------------|
|`InsideCriticalRegion`|Bağlam içinde kritik bir bölgesi olduğunu gösterir. Bir kritik bölgesindeki olduğunda zaman uyumsuz askıya alma, Zamanlayıcıdan gizlidir. Böyle bir askıya alma gerçekleştirileceği, Resource Manager çalıştırılabilir duruma ve Zamanlayıcı tekrar çağırmak yerine yalnızca sürdürmek iş parçacığı için bekler. Böyle bir bölge içinde gerçekleştirilen kilitleri ile aşırı dikkatli olunması gerekir.|
|`InsideHyperCriticalRegion`|Bağlam içinde hyper-kritik bir bölge olduğunu gösterir. Bir hyper-kritik bölgesindeki zaman zaman uyumlu ve zaman uyumsuz askıya alma, Zamanlayıcıdan gizlidir. Engelleme gerçekleşir, çalıştırılabilir duruma ve Zamanlayıcı tekrar çağırmak yerine yalnızca sürdürmek iş parçacığı Kaynak Yöneticisi'ni bekleyecektir ya da böyle bir askıya alma gerekir. Böyle bir bölge dışında çalışan kodla hiçbir zaman bu tür bir bölge içinde gerçekleştirilen kilitleri paylaşılması gerekir. Bunun yapılması, öngörülemeyen kilitlenmeye neden olur.|
|`OutsideCriticalRegion`|Bağlam dışında herhangi bir kritik bölgesine olduğunu gösterir.|

### <a name="requirements"></a>Gereksinimler

**Başlık:** concrtrm.h

##  <a name="dynamicprogressfeedbacktype"></a>  DynamicProgressFeedbackType numaralandırması

Tarafından kullanılan `DynamicProgressFeedback` yapılançağrılararacılığıylaboştadurumunaiçinevedışınagidereksanalişlemcitemelistatistikselbilgilerigöreZamanlayıcı'dantoplananyadayalnızcaZamanlayıcıiçinkaynaklarıDengelenecekolmadığınıtanımlamakiçinilke`Activate` ve `Deactivate` yöntemlerde `IVirtualProcessorRoot` arabirimi. Kullanılabilir Zamanlayıcı ilkeleri hakkında daha fazla bilgi için bkz. [PolicyElementKey](concurrency-namespace-enums.md).

```
enum DynamicProgressFeedbackType;
```
### <a name="values"></a>Değerler

|Ad|Açıklama|
|----------|-----------------|
|`ProgressFeedbackDisabled`|Zamanlayıcı, ilerleme durumu bilgileri toplamak değil. Yeniden Dengeleme tabanlı yalnızca abonelik düzeyinde temel alınan donanım iş parçacığı üzerinde gerçekleştirilir. Abonelik düzeyleri hakkında daha fazla bilgi için bkz. [Iexecutionresource::currentsubscriptionlevel](IExecutionResource-structure.md).<br /><br /> Bu değer, çalışma zamanı tarafından kullanım için ayrılmıştır.|
|`ProgressFeedbackEnabled`|Zamanlayıcı ilerleme bilgilerini toplar ve resource Manager'a iletir. Kaynak Yöneticisi, temel alınan donanım iş parçacığı abonelik düzeyini yanı sıra Zamanlayıcı adına kaynakları yeniden dengelemek için bu istatistik bilgileri yararlanacaktır. Abonelik düzeyleri hakkında daha fazla bilgi için bkz. [Iexecutionresource::currentsubscriptionlevel](IExecutionResource-structure.md).|
##  <a name="join_type"></a>  join_type numaralandırması

Türü bir `join` ileti bloğu.

```
enum join_type;
```
### <a name="values"></a>Değerler

|Ad|Açıklama|
|----------|-----------------|
|`greedy`|Doyumsuz `join` ileti blokları hemen kabul yayma bağlı bir ileti. Bu daha verimlidir, ancak Canlı-LOCK, ağ yapılandırmasına bağlı olarak olasılığı vardır.|
|`non_greedy`|Doyumsuz olmayan `join` ileti blokları ileti erteleme deneyin ve tüm gelen sonra bunları tüketme. Bunlar, ancak daha yavaş çalışacak şekilde garanti edilir.|

### <a name="requirements"></a>Gereksinimler

**Başlık:** agents.h

##  <a name="message_status"></a>  message_status numaralandırması

Bir teklif için geçerli yanıtlar bir `message` bloğu için nesne.

```
enum message_status;
```
### <a name="values"></a>Değerler

|Ad|Açıklama|
|----------|-----------------|
|`accepted`|Hedef iletiyi kabul edildi.|
|`declined`|Hedef iletiyi kabul etmedi.|
|`missed`|Hedef iletiyi kabul denedi, ancak artık kullanılabilir.|
|`postponed`|Hedef iletiyi ertelendi.|

### <a name="requirements"></a>Gereksinimler

**Başlık:** agents.h

##  <a name="policyelementkey"></a>  PolicyElementKey numaralandırması

Zamanlayıcı davranış yönlerini açıklayan ilke anahtarları. Her ilke öğesi bir anahtar-değer çifti tarafından tanımlanır. Zamanlayıcılar hakkında Zamanlayıcı ilkeleri ve etkileri hakkında daha fazla bilgi için bkz. [Görev Zamanlayıcı](../../../parallel/concrt/task-scheduler-concurrency-runtime.md).

```
enum PolicyElementKey;
```
### <a name="values"></a>Değerler

|Ad|Açıklama|
|----------|-----------------|
|`ContextPriority`|Her bir bağlamda Zamanlayıcı işletim sistemi iş parçacığı önceliği. Bu anahtarı değerine ayarlanırsa `INHERIT_THREAD_PRIORITY` Zamanlayıcı bağlamlarda Zamanlayıcı oluşturulan iş parçacığı önceliği devralır.<br /><br /> Geçerli değerler: herhangi bir Windows için geçerli değerleri `SetThreadPriority` işlevi ve özel değeri `INHERIT_THREAD_PRIORITY`<br /><br /> Varsayılan değer: `THREAD_PRIORITY_NORMAL`|
|`ContextStackSize`|Zamanlayıcı kilobayt cinsinden her bağlamda ayrılmış yığın boyutu.<br /><br /> Geçerli değerler: pozitif tam sayılar<br /><br /> Varsayılan değer: `0`, işlem varsayılan değer yığın boyutu için kullanılmasını gösteren.|
|`DynamicProgressFeedback`|Kaynaklar için Zamanlayıcı Zamanlayıcıdan toplanan ya da yalnızca temel alınan donanım iş parçacıklarının abonelik düzeyine göre istatistiksel bilgi göre Dengelenecek olup olmadığını belirler. Daha fazla bilgi için [DynamicProgressFeedbackType](#dynamicprogressfeedbacktype).<br /><br /> Geçerli değerler: üyesi `DynamicProgressFeedbackType` numaralandırma, ya da `ProgressFeedbackEnabled` veya `ProgressFeedbackDisabled`<br /><br /> Varsayılan değer: `ProgressFeedbackEnabled`|
|`LocalContextCacheSize`|Zaman `SchedulingProtocol` ilke anahtarı değerine ayarlanmış `EnhanceScheduleGroupLocality`, bu çalıştırılabilir bağlamları içinde sanal işlemci başına yerel kuyruğu önbelleğe alınmasına izin verilen en yüksek sayısını belirtir. Böyle bağlamları genellikle bunları çalıştırılabilir duruma gelmesine neden olduğu sanal işlemci üzerinde son-giren ilk çıkar (LIFO) sırayla çalıştırın. Bu ilke anahtarı ne zaman hiçbir anlamı olan Not `SchedulingProtocol` anahtar değerine ayarlanmış `EnhanceForwardProgress`.<br /><br /> Geçerli değerler: negatif olmayan tamsayılar<br /><br /> Varsayılan değer: `8`|
|`MaxConcurrency`|En fazla eşzamanlılık düzeyi Zamanlayıcı tarafından istenen. Kaynak Yöneticisi, başlangıçta bu kadar sanal işlemci ayrılacak çalışacaktır. Özel değeri [MaxExecutionResources](concurrency-namespace-constants1.md#maxexecutionresources) istenen eşzamanlılık düzeyi aynı makineye donanım iş parçacığı sayısını gösterir. İçin belirtilen değer, `MinConcurrency` makinede donanım iş parçacıklarının sayısını büyüktür ve `MaxConcurrency` olarak belirtilen `MaxExecutionResources`, değeri `MaxConcurrency` için ayarlanmış eşleştirmek için yükseltilmiş `MinConcurrency`.<br /><br /> Geçerli değerler: pozitif tam sayılar ve özel değeri `MaxExecutionResources`<br /><br /> Varsayılan değer: `MaxExecutionResources`|
|`MaxPolicyElementKey`|En fazla ilke öğe anahtarı. Geçerli öğe anahtarı değil.|
|`MinConcurrency`|Zamanlayıcı kaynak yöneticisi tarafından sağlanmalıdır en düşük eşzamanlılık düzeyi. Bir zamanlayıcı için atanan sanal işlemcilerin sayısı alt sınırın altında hiçbir zaman geçer. Özel değeri [MaxExecutionResources](concurrency-namespace-constants1.md#maxexecutionresources) en düşük eşzamanlılık düzeyi aynı makineye donanım iş parçacığı sayısını gösterir. İçin belirtilen değer, `MaxConcurrency` makinede donanım iş parçacıklarının sayısını küçüktür ve `MinConcurrency` olarak belirtilen `MaxExecutionResources`, değeri `MinConcurrency` için ayarlanmış eşleştirmek için azaltıldığı `MaxConcurrency`.<br /><br /> Geçerli değerler: negatif olmayan tamsayılar ve özel değeri `MaxExecutionResources`. Eşzamanlılık Çalışma zamanı planlayıcıları değeri oluşumu için kullanılan Zamanlayıcı ilkeleri için unutmayın `0` geçersiz.<br /><br /> Varsayılan değer: `1`|
|`SchedulerKind`|Zamanlayıcı için temel yürütme bağlamları yararlanacaktır iş parçacığı türü. Daha fazla bilgi için [SchedulerType](#schedulertype).<br /><br /> Geçerli değerler: üyesi `SchedulerType` numaralandırma, örneğin, `ThreadScheduler`<br /><br /> Varsayılan değer: `ThreadScheduler`. Bu, tüm işletim sistemlerinde Win32 iş parçacığı dönüşür.|
|`SchedulingProtocol`|Zamanlama algoritmayı Zamanlayıcı tarafından kullanılacak açıklar. Daha fazla bilgi için [SchedulingProtocolType](#schedulingprotocoltype).<br /><br /> Geçerli değerler: üyesi `SchedulingProtocolType` numaralandırma, ya da `EnhanceScheduleGroupLocality` veya `EnhanceForwardProgress`<br /><br /> Varsayılan değer: `EnhanceScheduleGroupLocality`|
|`TargetOversubscriptionFactor`|Geçici donanım iş parçacığı başına sanal işlemcilerin sayısı. Hedef gecikmeyi faktör kaynak yöneticisi tarafından gerekirse karşılamak artırılabilir `MaxConcurrency` makinede donanım iş parçacıklarının ile.<br /><br /> Geçerli değerler: pozitif tam sayılar<br /><br /> Varsayılan değer: `1`|
|`WinRTInitialization`||

### <a name="requirements"></a>Gereksinimler

**Başlık:** concrt.h

##  <a name="schedulertype"></a>  SchedulerType numaralandırması

Tarafından kullanılan `SchedulerKind` Zamanlayıcı için temel yürütme bağlamları kullanmalıdır iş parçacıkları türünü tanımlamak için ilke. Kullanılabilir Zamanlayıcı ilkeleri hakkında daha fazla bilgi için bkz. [PolicyElementKey](concurrency-namespace-enums.md).

```
enum SchedulerType;
```

### <a name="values"></a>Değerler

|Ad|Açıklama|
|----------|-----------------|
|`ThreadScheduler`|Normal Win32 iş parçacığı açık bir istek gösterir.|
|`UmsThreadDefault`|Kullanıcı modunda zamanlanabilen (UMS) iş parçacığı eşzamanlılık çalışma zamanı Visual Studio 2013'te desteklenmez. Kullanarak `UmsThreadDefault` için bir değer olarak `SchedulerType` ilke içinde bir hata değil neden olur. Ancak, bu ilke ile oluşturulan bir zamanlayıcı Win32 iş parçacığı kullanımını varsayılan.|

### <a name="requirements"></a>Gereksinimler

**Başlık:** concrt.h

##  <a name="schedulingprotocoltype"></a>  SchedulingProtocolType numaralandırması

Tarafından kullanılan `SchedulingProtocol` Zamanlayıcı için zamanlama algoritmayı kullanılır tanımlamak için ilke. Kullanılabilir Zamanlayıcı ilkeleri hakkında daha fazla bilgi için bkz. [PolicyElementKey](concurrency-namespace-enums.md).

```
enum SchedulingProtocolType;
```
### <a name="values"></a>Değerler

|Ad|Açıklama|
|----------|-----------------|
|`EnhanceForwardProgress`|Zamanlama grupları aracılığıyla hepsini her görev yürütüldükten sonra Zamanlayıcı tercih. Engeli bağlamları genellikle bir ilk-giren ilk çıkar (FIFO) şekilde zamanlanır. Sanal işlemci engeli bağlamları önbelleğe alma işlemi.|
|`EnhanceScheduleGroupLocality`|Zamanlayıcı, başka bir zamanlama grubu için devam etmeden önce geçerli zamanlama grubu içinde görevler üzerinde çalışmaya devam etmeyi tercih eder. Engeli bağlamları sanal-işlemci önbelleğe alınır ve son olarak ilk çıkar (LIFO) biçiminde bunları engeli kaldırılmış olduğu sanal işlemci genellikle planlanır.|

### <a name="requirements"></a>Gereksinimler

**Başlık:** concrt.h

##  <a name="switchingproxystate"></a>  SwitchingProxyState numaralandırması

Bir iş parçacığı proxy'sini bulunduğu durumu belirtmek için kullanılan, ne zaman, bir ortak bağlam anahtara farklı iş parçacığı proxy yürütüyor.

```
enum SwitchingProxyState;
```
### <a name="values"></a>Değerler

|Ad|Açıklama|
|----------|-----------------|
|`Blocking`|Çağıran iş parçacığını işbirliği içerisinde devamlılığı engelliyor ve özel olarak çağıran tarafından daha sonra yeniden çalıştırmayı ve başka bir eylem gerçekleştirmek kadar ait gösterir.|
|`Idle`|Çağıran iş parçacığını Zamanlayıcı tarafından artık gerekli değildir ve Resource Manager'a döndürülen gösterir. Postasıdan bağlamı artık kaynak yöneticisi tarafından kullanılmasına mümkün değildir.|
|`Nesting`|Çağıran iş parçacığını alt Zamanlayıcı iç içe geçirme ve için farklı bir zamanlayıcı iliştirmek için arayan tarafından gerekli olduğunu gösterir.|

### <a name="remarks"></a>Açıklamalar

Türünde bir parametre `SwitchingProxyState` yönteme geçirilen `IThreadProxy::SwitchTo` kaynak yöneticisi nasıl çağrıyı yapan iş parçacığı proxy'sini işlemesi gerektiğini bildirin.

Bu tür nasıl kullanıldığı hakkında daha fazla bilgi için bkz. [Ithreadproxy::switchto](ithreadproxy-structure.md#switchto).

##  <a name="task_group_status"></a>  task_group_status numaralandırması

Yürütme durumunu açıklar bir `task_group` veya `structured_task_group` nesne. Bu türde bir değer tamamlamak için bir görev grubuna Zamanlanmış görevlerde bekleyen çok sayıda yöntem tarafından döndürülür.

```
enum task_group_status;
```
### <a name="values"></a>Değerler

|Ad|Açıklama|
|----------|-----------------|
|`canceled`|`task_group` Veya `structured_task_group` nesnesi iptal edildi. Bir veya daha fazla görev yürütülmemiş olabilir.|
|`completed`|Sıraya alınan görevler `task_group` veya `structured_task_group` nesne başarıyla tamamlandı.|
|`not_complete`|Sıraya alınan görevler `task_group` nesne tamamlanmadı. Bu değer şu anda eşzamanlılık çalışma zamanı tarafından döndürülmez unutmayın.|

### <a name="requirements"></a>Gereksinimler

**Başlık:** pplinterface.h

##  <a name="winrtinitializationtype"></a>  Winrtınitializationtype numaralandırması

Tarafından kullanılan `WinRTInitialization` görüntülenip görüntülenmeyeceğini ve nasıl Windows çalışma zamanı sürümü Windows 8 işletim sistemlerinde çalışan bir uygulama için Zamanlayıcı iş parçacıklarında başlatılmış veya üzeri başlatılacağını açıklamak için ilke. Kullanılabilir Zamanlayıcı ilkeleri hakkında daha fazla bilgi için bkz. [PolicyElementKey](concurrency-namespace-enums.md).

```
enum WinRTInitializationType;
```
### <a name="values"></a>Değerler

|Ad|Açıklama|
|----------|-----------------|
|`DoNotInitializeWinRT`|Windows çalışma zamanı zaman uygulama sürümü Windows 8 işletim sistemlerinde çalıştırılan veya üzeri Zamanlayıcı içindeki iş parçacıkları başlatmaz.|
|`InitializeWinRTAsMTA`|Uygulama sürümü Windows 8 işletim sistemlerinde çalıştırılan veya Zamanlayıcı içindeki her bir iş parçacığı sonraki ve Windows çalışma zamanı başlatma olduğunu bildirir, çok iş parçacıklı grubun bir parçası olur.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** concrt.h

## <a name="see-also"></a>Ayrıca Bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)
