---
title: concurrency Ad Alanı
ms.date: 11/04/2016
f1_keywords:
- concurrent_priority_queue/concurrency
- agents/concurrency
- concurrent_vector/concurrency
- concrt/concurrency
- internal_split_ordered_list/concurrency
- concurrent_queue/concurrency
- pplcancellation_token/concurrency
- pplinterface/concurrency
- ppltasks/concurrency
- ppl/concurrency
- concurrent_unordered_map/concurrency
- concrtrm/concurrency
- concurrent_unordered_set/concurrency
- pplconcrt/concurrency
- internal_concurrent_hash/concurrency
helpviewer_keywords:
- Concurrency namespace
ms.assetid: f1d33ca2-679b-4442-b140-22a9d9df61d1
ms.openlocfilehash: f710ead679484c41b006566a711a03ba153201ec
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87230382"
---
# <a name="concurrency-namespace"></a>concurrency Ad Alanı

`Concurrency`Ad alanı, C++ için eşzamanlı bir programlama çerçevesi olan eşzamanlılık çalışma zamanı erişim sağlayan sınıfları ve işlevleri sağlar. Daha fazla bilgi için bkz. [Eşzamanlılık çalışma zamanı](../../../parallel/concrt/concurrency-runtime.md).

## <a name="syntax"></a>Sözdizimi

```cpp
namespace concurrency;
```

## <a name="members"></a>Üyeler

### <a name="typedefs"></a>Tür tanımları

|Ad|Açıklama|
|----------|-----------------|
|`runtime_object_identity`|Her ileti örneği, kopyalandığı ve mesajlaşma bileşenleri arasında geçirildiği için onu izleyen bir kimliğe sahiptir. İleti nesnesinin adresi olamaz.|
|`task_status`|Görevin Terminal durumunu temsil eden bir tür. Geçerli değerler `completed` ve ' dir `canceled` .|
|`TaskProc`|Görevin bir öğesel soyutlaması, olarak tanımlanır `void (__cdecl * TaskProc)(void *)` . Bir `TaskProc` görevin gövdesini çağırmak için bir çağırılır.|
|`TaskProc_t`|Görevin bir öğesel soyutlaması, olarak tanımlanır `void (__cdecl * TaskProc_t)(void *)` . Bir `TaskProc` görevin gövdesini çağırmak için bir çağırılır.|

### <a name="classes"></a>Sınıflar

|Ad|Açıklama|
|----------|-----------------|
|[affinity_partitioner sınıfı](affinity-partitioner-class.md)|`affinity_partitioner`Sınıfı, `static_partitioner` sınıfa benzerdir, ancak alt aralıkları çalışan iş parçacıklarıyla eşleme seçeneği tarafından önbellek benzeşimini geliştirir. Bir döngü aynı veri kümesi üzerinde yeniden yürütüldüğünde ve veriler önbelleğe sığıyorsa performansı önemli ölçüde iyileştirebilir. Aynı `affinity_partitioner` nesne, veri konumundan faydalanmak için belirli bir veri kümesi üzerinde yürütülen paralel bir döngünün sonraki yinelemeleriyle birlikte kullanılmalıdır.|
|[Aracı sınıfı](agent-class.md)|Tüm bağımsız aracılar için temel sınıf olarak kullanılması amaçlanan bir sınıf. Diğer aracılardan durumu gizlemek ve ileti geçirme kullanılarak etkileşim kurmak için kullanılır.|
|[auto_partitioner Sınıfı](auto-partitioner-class.md)|`auto_partitioner`Sınıfı varsayılan yöntemi temsil eder `parallel_for` `parallel_for_each` ve `parallel_transform` üzerinde yineleme aralığını bölümlemek için kullanın. Bu bölümleme yöntemi, yük dengeleme için Aralık çalmasını ve yineleme başına iptali kullanır.|
|[bad_target sınıfı](bad-target-class.md)|Bu sınıf, bir ileti bloğuna gerçekleştirilen işlem için geçersiz olan bir hedefe işaretçi verildiğinde oluşan bir özel durumu açıklar.|
|[Call sınıfı](call-class.md)|İleti `call` bloğu, bir `target_block` ileti alırken belirtilen bir işlevi çağıran birden çok kaynaktır.|
|[cancellation_token sınıfı](cancellation-token-class.md)|`cancellation_token`Sınıfı, bir işlemin iptal edilip edilmeyeceğini belirleme yeteneğini temsil eder. Belirli bir belirteç `task_group` , bir, `structured_task_group` veya `task` örtülü iptal sağlamak için ilişkilendirilebilir. Ayrıca, iptal için yoklanabilir veya varsa ve ilişkili bir geri çağırma `cancellation_token_source` işlemi iptal edilir.|
|[cancellation_token_registration sınıfı](cancellation-token-registration-class.md)|`cancellation_token_registration`Sınıfı, bir geri çağırma bildirimini temsil eder `cancellation_token` . `register`Bir üzerinde yöntemi, `cancellation_token` İptalin ne zaman yapıldığını belirten bir bildirim almak için kullanıldığında, `cancellation_token_registration` çağıran belirli bir geri çağırma işlemini daha sonra metodun kullanımı ile isteyebilmesi için bir nesne geri aramaya bir tanıtıcı olarak döndürülür `deregister` .|
|[cancellation_token_source sınıfı](cancellation-token-source-class.md)|`cancellation_token_source`Sınıfı, bazı iptal edilebilen işlemleri iptal etme yeteneğini temsil eder.|
|[seçim sınıfı](choice-class.md)|`choice`İleti bloğu, bir kaynak kümesiyle denetim akışı etkileşimini temsil eden çok kaynaklı, tek hedef bir bloğudur. Seçim bloğu, birden fazla kaynağın bir ileti oluşturmasını ve iletiyi üreten kaynağın dizinini yaymasını bekler.|
|[combinable Sınıfı](combinable-class.md)|`combinable<T>`Nesne, paralel algoritmalar sırasında kilit içermeyen iş parçacığı yerel alt hesaplamaları gerçekleştirmek için, verilerin iş parçacığına özel kopyalarını sağlamak üzere tasarlanmıştır. Paralel işlemin sonunda, iş parçacığı özel alt hesaplamaları daha sonra nihai bir sonuçla birleştirilebilir. Bu sınıf, paylaşılan bir değişken yerine kullanılabilir ve bu paylaşılan değişkende çok fazla çekişme olmaması durumunda performans iyileştirmesine neden olabilir.|
|[concurrent_priority_queue sınıfı](concurrent-priority-queue-class.md)|`concurrent_priority_queue`Sınıfı, birden çok iş parçacığının aynı anda gönderim ve pop öğelerine izin veren bir kapsayıcıdır. Öğelerin, bir şablon bağımsız değişkeni olarak sağlanan bir functor tarafından belirlendiği öncelik sırasına göre belirlenir.|
|[concurrent_queue sınıfı](concurrent-queue-class.md)|`concurrent_queue`Sınıfı, öğeleri için ilk ın, ilk çıkar erişimine izin veren bir dizi kapsayıcı sınıfıdır. Ve gibi sınırlı sayıda eşzamanlılık güvenli işlem kümesi sunar `push` `try_pop` .|
|[concurrent_unordered_map sınıfı](concurrent-unordered-map-class.md)|`concurrent_unordered_map`Sınıfı, türündeki değişen uzunluktaki öğelerin sırasını denetleyen eşzamanlılık açısından güvenli bir kapsayıcıdır `std::pair<const K, _Element_type>` . Dizi eşzamanlılık açısından güvenli ekleme, öğe erişimi, yineleyici erişimi ve yineleyici çapraz geçiş işlemlerine olanak sağlayan bir şekilde temsil edilir.|
|[concurrent_unordered_multimap sınıfı](concurrent-unordered-multimap-class.md)|`concurrent_unordered_multimap`Sınıfı, türündeki değişen uzunluktaki öğelerin sırasını denetleyen eşzamanlılık açısından güvenli bir kapsayıcıdır `std::pair<const K, _Element_type>` . Dizi eşzamanlılık açısından güvenli ekleme, öğe erişimi, yineleyici erişimi ve yineleyici çapraz geçiş işlemlerine olanak sağlayan bir şekilde temsil edilir.|
|[concurrent_unordered_multiset sınıfı](concurrent-unordered-multiset-class.md)|`concurrent_unordered_multiset`Sınıfı, K türünde bir dizi öğenin değişen uzunluklu bir dizisini denetleyen eşzamanlılık açısından güvenli bir kapsayıcıdır. Dizi eşzamanlılık açısından güvenli ekleme, öğe erişimi, yineleyici erişimi ve yineleyici çapraz geçiş işlemlerine olanak sağlayan bir şekilde temsil edilir.|
|[concurrent_unordered_set sınıfı](concurrent-unordered-set-class.md)|`concurrent_unordered_set`Sınıfı, K türünde bir dizi öğenin değişen uzunluklu bir dizisini denetleyen eşzamanlılık açısından güvenli bir kapsayıcıdır. Dizi eşzamanlılık açısından güvenli ekleme, öğe erişimi, yineleyici erişimi ve yineleyici çapraz geçiş işlemlerine olanak sağlayan bir şekilde temsil edilir.|
|[concurrent_vector sınıfı](concurrent-vector-class.md)|`concurrent_vector`Sınıfı herhangi bir öğeye rastgele erişime izin veren bir dizi kapsayıcı sınıfıdır. Eşzamanlılık açısından güvenli ekleme, öğe erişimi, yineleyici erişimi ve yineleyici çapraz geçiş işlemlerine izin vermez.|
|[Bağlam sınıfı](context-class.md)|Yürütme bağlamı için bir soyutlama temsil eder.|
|[context_self_unblock sınıfı](context-self-unblock-class.md)|Bu sınıf, `Unblock` bir `Context` nesne yöntemi aynı içerikten çağrıldığında oluşturulan bir özel durumu açıklar. Bu, belirli bir bağlam tarafından onun engellemesini kaldırmak için bir girişim olduğunu gösterir.|
|[context_unblock_unbalanced sınıfı](context-unblock-unbalanced-class.md)|Bu sınıf, `Block` `Unblock` bir nesnenin ve yöntemlerine yapılan çağrılar `Context` düzgün şekilde eşleştirilmediğinde oluşan bir özel durum tanımlar.|
|[critical_section sınıfı](critical-section-class.md)|Eşzamanlılık Çalışma Zamanı açıkça farkında olan, yer olmayan bir mutex.|
|[CurrentScheduler sınıfı](currentscheduler-class.md)|Çağıran bağlamla ilişkili geçerli Zamanlayıcı için bir soyutlama temsil eder.|
|[default_scheduler_exists sınıfı](default-scheduler-exists-class.md)|Bu sınıf, `Scheduler::SetDefaultSchedulerPolicy` işlem içinde varsayılan bir Zamanlayıcı zaten varken yöntemi çağrıldığında oluşturulan bir özel durumu açıklar.|
|[Event sınıfı](event-class.md)|Eşzamanlılık Çalışma Zamanı açıkça farkında olan el ile sıfırlama olayı.|
|[improper_lock sınıfı](improper-lock-class.md)|Bu sınıf, bir kilit yanlış edinildiği zaman oluşturulan bir özel durum tanımlar.|
|[improper_scheduler_attach sınıfı](improper-scheduler-attach-class.md)|Bu sınıf, `Attach` yöntemi `Scheduler` zaten geçerli bağlama eklenmiş bir nesne üzerinde çağrıldığında oluşturulan bir özel durumu açıklar.|
|[improper_scheduler_detach sınıfı](improper-scheduler-detach-class.md)|Bu sınıf, `CurrentScheduler::Detach` bir nesne yöntemi kullanılarak herhangi bir Scheduler 'a eklenmemiş bir bağlamda yöntemi çağrıldığında oluşturulan bir özel durumu açıklar `Attach` `Scheduler` .|
|[improper_scheduler_reference sınıfı](improper-scheduler-reference-class.md)|Bu sınıf `Reference` `Scheduler` , bu Scheduler 'ın parçası olmayan bir bağlamdan, yöntemi kapanmakta olan bir nesne üzerinde çağrıldığında oluşturulan bir özel durumu açıklar.|
|[invalid_link_target sınıfı](invalid-link-target-class.md)|Bu sınıf, `link_target` bir mesajlaşma bloğunun yöntemi çağrıldığında ve mesajlaşma bloğu hedefle bağlantı kuramadı durumunda oluşturulan bir özel durumu açıklar. Bu, mesajlaşma bloğunun izin verdiği bağlantı sayısını aşmanın veya belirli bir hedefin aynı kaynağa iki kez bağlantı kurmaya çalıştığı sonuç olabilir.|
|[invalid_multiple_scheduling sınıfı](invalid-multiple-scheduling-class.md)|Bu sınıf `task_handle` `run` `task_group` `structured_task_group` , veya yöntemlerine aradaki bir çağrı olmadan bir veya nesnesinin yöntemi kullanılarak bir nesne birden çok kez zamanlandığında oluşturulan bir `wait` özel durumu açıklar `run_and_wait` .|
|[invalid_operation sınıfı](invalid-operation-class.md)|Bu sınıf, Eşzamanlılık Çalışma Zamanı tarafından oluşturulan başka bir özel durum türü tarafından daha doğru bir şekilde açıklanmayan geçersiz bir işlem gerçekleştirildiğinde oluşturulan bir özel durumu açıklar.|
|[invalid_oversubscribe_operation sınıfı](invalid-oversubscribe-operation-class.md)|Bu sınıf, `Context::Oversubscribe` yöntemi parametresi `_BeginOversubscription` **`false`** `Context::Oversubscribe` olarak ayarlanmış bir yönteme önceki bir çağrı olmadan olarak `_BeginOversubscription` çağrıldığında oluşturulan **`true`** bir özel durumu açıklar.|
|[invalid_scheduler_policy_key sınıfı](invalid-scheduler-policy-key-class.md)|Bu sınıf, bir nesne oluşturucusuna geçersiz veya bilinmeyen bir anahtar geçirildiğinde oluşturulan bir özel durumu açıklar `SchedulerPolicy` veya `SetPolicyValue` bir nesnenin yöntemi, yöntemi gibi `SchedulerPolicy` diğer yollarla değiştirilmesi gereken bir anahtarı geçirmez `SetConcurrencyLimits` .|
|[invalid_scheduler_policy_thread_specification sınıfı](invalid-scheduler-policy-thread-specification-class.md)|Bu sınıf, bir nesnenin eşzamanlılık sınırlarını ayarlamak için bir girişimde bulunulduğunda, `SchedulerPolicy` anahtarın değeri anahtarın değerinden küçükse oluşan bir özel durum tanımlar `MinConcurrency` `MaxConcurrency` .|
|[invalid_scheduler_policy_value sınıfı](invalid-scheduler-policy-value-class.md)|Bu sınıf, bir nesnenin ilke anahtarı `SchedulerPolicy` Bu anahtar için geçersiz bir değere ayarlandığında oluşturulan bir özel durumu açıklar.|
|[ISource Sınıfı](isource-class.md)|`ISource`Sınıfı, tüm kaynak blokları için arabirimidir. Kaynak blokları iletileri `ITarget` bloklara yayar.|
|[IComparer sınıfı](itarget-class.md)|`ITarget`Sınıfı tüm hedef bloklara yönelik arabirimdir. Hedef bloklar bunlara bloklar tarafından sunulan iletileri tüketir `ISource` .|
|[JOIN sınıfı](join-class.md)|Bir `join` mesajlaşma bloğu, `propagator_block` kaynaklarından her birinden gelen iletileri birlikte birleştiren tek hedef ve çok kaynaklı bir kaynaktır `T` .|
|[location Sınıfı](location-class.md)|Donanımda fiziksel bir konumun soyutlaması.|
|[ileti sınıfı](message-class.md)|İleti blokları arasında geçilen veri yükünü içeren temel ileti zarfı.|
|[message_not_found sınıfı](message-not-found-class.md)|Bu sınıf, bir ileti bloğu istenen iletiyi bulamadığında oluşan bir özel durum tanımlar.|
|[message_processor Sınıfı](message-processor-class.md)|`message_processor`Sınıfı, nesneleri işlemek için soyut temel sınıftır `message` . İleti sıralaması hakkında garanti yoktur.|
|[missing_wait sınıfı](missing-wait-class.md)|Bu sınıf `task_group` `structured_task_group` , nesnenin yıkıcının yürütüldüğü sırada bir veya nesnesine hala zamanlanan görevler olduğunda oluşturulan bir özel durumu açıklar. Bu özel durum, bir özel durumun sonucu olarak bir yığın geri sarma işlemi nedeniyle yok edici olursa hiçbir durum oluşturulmaz.|
|[multi_link_registry sınıfı](multi-link-registry-class.md)|`multi_link_registry`Nesnesi, `network_link_registry` birden çok kaynak bloğunu veya birden çok hedef bloğu yöneten bir nesnesidir.|
|[multitype_join sınıfı](multitype-join-class.md)|`multitype_join`Mesajlaşma bloğu, kaynaklarından her birinin farklı türlerindeki iletileri birleştiren ve hedeflerine Birleşik iletilerin bir listesini sunan çok kaynaklı, tek hedef mesajlaşma bloğudur.|
|[nested_scheduler_missing_detach sınıfı](nested-scheduler-missing-detach-class.md)|Bu sınıf, Eşzamanlılık Çalışma Zamanı bir özel durum tanımlar ve bu, `CurrentScheduler::Detach` yöntemi, nesne yöntemi kullanılarak ikinci bir Scheduler 'a eklenmiş bir bağlamda yöntemi çağırmak için ihmal ettiğiniz algılandığında oluşur `Attach` `Scheduler` .|
|[network_link_registry sınıfı](network-link-registry-class.md)|`network_link_registry`Soyut temel sınıf, kaynak ve hedef bloklar arasındaki bağlantıları yönetir.|
|[operation_timed_out sınıfı](operation-timed-out-class.md)|Bu sınıf, bir işlem zaman aşımına uğramışsa oluşturulan özel durumu açıklar.|
|[ordered_message_processor sınıfı](ordered-message-processor-class.md)|`ordered_message_processor` `message_processor` İleti bloklarının iletileri alındıkları sırada işlemesini sağlayan bir ' dir.|
|[overwrite_buffer sınıfı](overwrite-buffer-class.md)|`overwrite_buffer`İleti bloğu, `propagator_block` aynı anda tek bir ileti depolayan çok hedefli, çok kaynaklı ve sıralı bir kaynaktır. Yeni iletiler üzerine yazılır.|
|[progress_reporter sınıfı](progress-reporter-class.md)|Progress Reporter sınıfı, belirli bir türdeki ilerleme bildirimlerinin raporlanmasını sağlar. Her progress_reporter nesnesi belirli bir zaman uyumsuz eyleme veya işleme bağlanır.|
|[propagator_block sınıfı](propagator-block-class.md)|`propagator_block`Sınıfı, hem kaynak hem de hedef olan ileti blokları için soyut bir temel sınıftır. Hem hem de sınıflarının işlevlerini birleştirir `source_block` `target_block` .|
|[reader_writer_lock sınıfı](reader-writer-lock-class.md)|Yalnızca yerel olarak dönen bir yazıcı tercihi kuyruğu tabanlı okuyucu-yazıcı kilidi. Kilit, sürekli bir yazıcı yüklemesi altında yazıcılara ve başlangıç okuyucularına ilk çıkar (FıFO) erişimi verir.|
|[ScheduleGroup sınıfı](schedulegroup-class.md)|Bir zamanlama grubu için bir soyutlama temsil eder. Zamanlama grupları, farklı bir gruba geçmeden önce aynı grupta başka bir görevi yürüterek veya aynı NUMA düğümündeki veya fiziksel yuvada aynı grup içinde birden çok öğe yürütülerek, zamana bağlı birlikte, aynı grupta daha fazla bir görev yürütülerek bir dizi ilgili işi düzenler.|
|[Zamanlayıcı sınıfı](scheduler-class.md)|Eşzamanlılık Çalışma Zamanı Zamanlayıcı için bir soyutlama temsil eder.|
|[scheduler_not_attached sınıfı](scheduler-not-attached-class.md)|Bu sınıf, bir Scheduler 'ın geçerli içeriğe eklenmesini gerektiren bir işlem gerçekleştirildiğinde oluşan bir özel durum tanımlar ve biri değildir.|
|[scheduler_resource_allocation_error sınıfı](scheduler-resource-allocation-error-class.md)|Bu sınıf, Eşzamanlılık Çalışma Zamanı kritik bir kaynak alma hatası nedeniyle oluşan bir özel durumu açıklar.|
|[scheduler_worker_creation_error sınıfı](scheduler-worker-creation-error-class.md)|Bu sınıf, Eşzamanlılık Çalışma Zamanı bir çalışan yürütme bağlamı oluşturma hatası nedeniyle oluşan bir özel durumu açıklar.|
|[SchedulerPolicy Sınıfı](schedulerpolicy-class.md)|Sınıfı, bir `SchedulerPolicy` Zamanlayıcı örneğinin davranışını denetleyen her ilke öğesi için bir olan anahtar/değer çiftleri kümesi içerir.|
|[simple_partitioner sınıfı](simple-partitioner-class.md)|`simple_partitioner`Sınıfı, tarafından tarafından yineleyen aralığın statik bir bölümlemesini temsil eder `parallel_for` . Bölümleyici, aralığı parçalara böler, her öbek en az öbek boyutu tarafından belirtilen yineleme sayısına sahiptir.|
|[single_assignment sınıfı](single-assignment-class.md)|Bir `single_assignment` mesajlaşma bloğu, `propagator_block` tek bir kez yazılabilir bir çoklu kaynak olan çok kaynaklı, çok kaynaklı, sıralı bir `message` .|
|[single_link_registry sınıfı](single-link-registry-class.md)|`single_link_registry`Nesnesi `network_link_registry` yalnızca tek bir kaynağı veya hedef bloğu yöneten bir nesnesidir.|
|[source_block sınıfı](source-block-class.md)|`source_block`Sınıfı, yalnızca kaynak blokları için soyut bir temel sınıftır. Sınıfı, temel bağlantı yönetimi işlevlerinin yanı sıra ortak hata denetimleri sağlar.|
|[source_link_manager sınıfı](source-link-manager-class.md)|`source_link_manager`Nesne, ileti bloğu ağ bağlantılarını `ISource` bloklara yönetir.|
|[static_partitioner sınıfı](static-partitioner-class.md)|`static_partitioner`Sınıfı, tarafından tarafından yineleyen aralığın statik bir bölümlemesini temsil eder `parallel_for` . Bölümleyici, temel alınan Scheduler 'da bulunan çalışanlar olduğundan, aralığı çok sayıda parçalara ayırır.|
|[structured_task_group sınıfı](structured-task-group-class.md)|`structured_task_group`Sınıfı, paralel çalışmanın yüksek yapılandırılmış bir koleksiyonunu temsil eder. Tek tek paralel görevleri bir `structured_task_group` using nesnelerine sıraya alabilir `task_handle` ve bunların tamamlanmasını bekleyebilir ya da yürütmeyi bitirmeden önce görev grubunu iptal edebilirsiniz. Bu, yürütmeye başlamış olmayan tüm görevleri iptal eder.|
|[target_block sınıfı](target-block-class.md)|`target_block`Sınıfı, temel bağlantı yönetim işlevselliği ve yalnızca hedef bloklar için hata denetimi sağlayan bir soyut temel sınıftır.|
|[Task sınıfı (Eşzamanlılık Çalışma Zamanı)](task-class.md)|Paralel Desenler kitaplığı (PPL) `task` sınıfı. Bir `task` nesnesi, zaman uyumsuz olarak yürütülebilecek çalışmayı ve eşzamanlılık çalışma zamanı diğer görevlerle aynı anda ve paralel algoritmalar tarafından üretilen paralel çalışmayı temsil eder. `_ResultType`Başarıyla tamamlanmasıyla ilgili bir sonuç üretir. Tür görevleri `task<void>` sonuç üretmez. Bir görev, diğer görevlerden bağımsız olarak bekleve iptal edilebilir. Ayrıca, devamlılıklar ( `then` ) ve JOIN () ve Choice () desenleri kullanılarak diğer görevlerle da oluşturulabilir `when_all` `when_any` .|
|[task_canceled sınıfı](task-canceled-class.md)|Bu sınıf, geçerli görevin iptal edilmeye zorlamak için PPL görev katmanı tarafından oluşturulan bir özel durumu açıklar. Ayrıca `get()` , iptal edilen bir görev için [görev](task-class.md)üzerindeki yöntemi tarafından da oluşturulur.|
|[task_completion_event sınıfı](task-completion-event-class.md)|Sınıfı, bir `task_completion_event` koşul karşılanana kadar bir görevin yürütülmesini ertelemenize veya dış bir olaya yanıt olarak bir görev başlatmanıza olanak sağlar.|
|[task_continuation_context sınıfı](task-continuation-context-class.md)|`task_continuation_context`Sınıfı, bir devamlılığın nerede yürütülmesini istediğinizi belirtmenize olanak tanır. Bu sınıfı yalnızca UWP uygulamasından kullanmak faydalıdır. Windows Çalışma Zamanı olmayan uygulamalar için, görev devamlılığın yürütme bağlamı, çalışma zamanı tarafından belirlenir ve yapılandırılamaz.|
|[task_group sınıfı](task-group-class.md)|`task_group`Sınıfı, beklemiş veya iptal edilebilir bir paralel çalışma koleksiyonunu temsil eder.|
|[task_handle Sınıfı](task-handle-class.md)|`task_handle`Sınıfı, tek bir paralel iş öğesini temsil eder. Bir iş parçasını yürütmek için gereken yönergeleri ve verileri saklar.|
|[task_options Sınıfı (Eşzamanlılık Çalışma Zamanı)](task-options-class-concurrency-runtime.md)|Bir görev oluşturmak için izin verilen seçenekleri temsil eder|
|[Timer sınıfı](timer-class.md)|`timer`İleti bloğu, belirli `source_block` bir süre geçtikten sonra veya belirli aralıklarla hedefine bir ileti gönderebilen tek hedeftir.|
|[Transformatör sınıfı](transformer-class.md)|Bir `transformer` mesajlaşma bloğu, tek bir `propagator_block` türden iletileri kabul edebilecek ve farklı türde sınırsız sayıda iletiyi depolayan bir tek hedeftir, birden çok kaynaktır.|
|[unbounded_buffer sınıfı](unbounded-buffer-class.md)|`unbounded_buffer`İleti bloğu, `propagator_block` sınırsız sayıda iletiyi depolayan çok kaynaklı ve çok kaynaklı, sıralı bir kaynaktır.|
|[unsupported_os sınıfı](unsupported-os-class.md)|Bu sınıf, desteklenmeyen bir işletim sistemi kullanıldığında oluşturulan bir özel durumu açıklar.|

### <a name="structures"></a>Yapılar

|Ad|Açıklama|
|----------|-----------------|
|[DispatchState Yapısı](dispatchstate-structure.md)|`DispatchState`Yapı, durumu yöntemine aktarmak için kullanılır `IExecutionContext::Dispatch` . Bu, `Dispatch` yönteminin bir arabirimde çağrıldığı koşulları açıklar `IExecutionContext` .|
|[IExecutionContext Yapısı](iexecutioncontext-structure.md)|Belirli bir sanal işlemci üzerinde çalışabilen ve birlikte çalışan içerik anahtarlamalı bir yürütme bağlamına yönelik arabirim.|
|[IExecutionResource Yapısı](iexecutionresource-structure.md)|Donanım iş parçacığı için bir soyutlama.|
|[IResourceManager Yapısı](iresourcemanager-structure.md)|Eşzamanlılık Çalışma Zamanı Kaynak Yöneticisi arabirimi. Bu, zamanlayıcılar ile iletişim kuran arabirimdir Kaynak Yöneticisi.|
|[IScheduler Yapısı](ischeduler-structure.md)|Bir iş Scheduler soyutlaması için arabirim. Eşzamanlılık Çalışma Zamanı Kaynak Yöneticisi, iş zamanlayıcılar ile iletişim kurmak için bu arabirimi kullanır.|
|[ISchedulerProxy Yapısı](ischedulerproxy-structure.md)|Zamanlayıcılar tarafından kaynak ayırmayı anlaşmak için Eşzamanlılık Çalışma Zamanı Kaynak Yöneticisi iletişim kuran arabirim.|
|[IThreadProxy Yapısı](ithreadproxy-structure.md)|Yürütmenin iş parçacığı için bir soyutlama. `SchedulerType`Oluşturduğunuz Scheduler ilke anahtarına bağlı olarak Kaynak Yöneticisi, size düzenli bir Win32 iş parçacığı veya Kullanıcı modu zamanlanabilen (UMS) iş parçacığı tarafından desteklenen bir iş parçacığı proxy 'si verir. UMS iş parçacıkları, Windows 7 ve üzeri sürümleri ile 64 bit işletim sistemlerinde desteklenir.|
|[ITopologyExecutionResource Yapısı](itopologyexecutionresource-structure.md)|Kaynak Yöneticisi tarafından tanımlanan yürütme kaynağına yönelik arabirim.|
|[ITopologyNode Yapısı](itopologynode-structure.md)|Kaynak Yöneticisi tarafından tanımlanan bir topoloji düğümüne yönelik arabirim. Bir düğüm bir veya daha fazla yürütme kaynağı içeriyor.|
|[IUMSCompletionList Yapısı](iumscompletionlist-structure.md)|UMS tamamlama listesini temsil eder. Bir UMS iş parçacığı engellediğinde, başlangıçtaki iş parçacığı engellenirken temeldeki sanal işlemci kökünde zamanlanmak üzere bir karar vermek üzere Scheduler 'ın belirlenen zamanlama bağlamı gönderilir. Orijinal iş parçacığı kaldırılıyorsa, işletim sistemi bu arabirim aracılığıyla erişilebilen tamamlanma listesine sıraya alır. Zamanlayıcı, belirlenen zamanlama bağlamındaki veya iş için arama yaptığı başka bir yerde tamamlama listesini sorgulayabilir.|
|[IUMSScheduler Yapısı](iumsscheduler-structure.md)|Eşzamanlılık Çalışma Zamanı Kaynak Yöneticisi, Kullanıcı modu zamanlanabilen (UMS) iş parçacıklarını ele almak isteyen bir iş Zamanlayıcı soyutlaması için arabirim. Kaynak Yöneticisi, UMS iş parçacığı zamanlayıcılar ile iletişim kurmak için bu arabirimi kullanır. `IUMSScheduler`Arabirim `IScheduler` arabiriminden devralır.|
|[IUMSThreadProxy Yapısı](iumsthreadproxy-structure.md)|Yürütmenin iş parçacığı için bir soyutlama. Scheduler 'a Kullanıcı modu zamanlanabilen (UMS) iş parçacıkları verilmesini istiyorsanız, Zamanlayıcı İlkesi öğesi için değeri `SchedulerKind` olarak ayarlayın `UmsThreadDefault` ve `IUMSScheduler` arabirimini uygulayın. UMS iş parçacıkları yalnızca Windows 7 ve üzeri sürümü olan 64 bitlik işletim sistemlerinde desteklenir.|
|[IUMSUnblockNotification Yapısı](iumsunblocknotification-structure.md)|, Bir iş parçacığı proxy 'sinin, Scheduler 'ın belirlenen zamanlama bağlamına geri dönme ve tetiklediği Kaynak Yöneticisi bir bildirimi temsil eder ve zamanlanmaya hazırlanın. Bu arabirim, iş parçacığı proxy 'sinin ilişkili yürütme bağlamı yönteminden döndürülen bir kez yeniden `GetContext` zamanlanırsa geçersizdir.|
|[IVirtualProcessorRoot Yapısı](ivirtualprocessorroot-structure.md)|İş parçacığı proxy 'sinin yürütebileceği donanım iş parçacığı için bir soyutlama.|
|[scheduler_interface Yapısı](scheduler-interface-structure.md)|Zamanlayıcı arabirimi|
|[scheduler_ptr Yapısı (Eşzamanlılık Çalışma Zamanı)](scheduler-ptr-structure-concurrency-runtime.md)|Scheduler 'a yönelik bir işaretçi temsil eder. Bu sınıf, shared_ptr veya ham işaretçi kullanılarak yalnızca düz bir başvuru kullanılarak paylaşılan bir yaşam süresi belirtimine izin vermek için mevcuttur.|

### <a name="enumerations"></a>Listelemeler

|Ad|Açıklama|
|----------|-----------------|
|[agent_status](concurrency-namespace-enums.md#agent_status)|Bir için geçerli durumlar `agent` .|
|[Agents_EventType](concurrency-namespace-enums.md#agents_eventtype)|Aracılar Kitaplığı tarafından sunulan izleme işlevi kullanılarak izlenebilir olay türleri|
|[ConcRT_EventType](concurrency-namespace-enums.md#concrt_eventtype)|Eşzamanlılık Çalışma Zamanı tarafından sunulan izleme işlevi kullanılarak izlenebilir olay türleri.|
|[Concrt_TraceFlags](concurrency-namespace-enums.md#concrt_traceflags)|Olay türleri için izleme bayrakları|
|[CriticalRegionType](concurrency-namespace-enums.md#criticalregiontype)|Bağlam içindeki kritik bölge türü.|
|[DynamicProgressFeedbackType](concurrency-namespace-enums.md#dynamicprogressfeedbacktype)|Zamanlayıcı `DynamicProgressFeedback` için kaynakların Scheduler 'dan toplanan istatistiksel bilgilere göre yeniden dengeleneceği ya da yalnızca arabirimdeki ve içindeki yöntemlere yapılan çağrılar aracılığıyla boşta durumuna geçen ve çıkan sanal işlemcilere bağlı olup olmadığını betimleyen bir ilke tarafından kullanılır `Activate` `Deactivate` `IVirtualProcessorRoot` . Kullanılabilir Zamanlayıcı ilkeleri hakkında daha fazla bilgi için bkz. [PolicyElementKey](concurrency-namespace-enums.md#policyelementkey).|
|[join_type](concurrency-namespace-enums.md#join_type)|Bir `join` mesajlaşma bloğunun türü.|
|[message_status](concurrency-namespace-enums.md#message_status)|Bir nesne için bir bloğa yönelik geçerli yanıtlar `message` .|
|[PolicyElementKey](concurrency-namespace-enums.md#policyelementkey)|Zamanlayıcı davranışının yönlerini açıklayan ilke anahtarları. Her ilke öğesi bir anahtar-değer çifti tarafından açıklanmıştır. Zamanlayıcı ilkeleri ve zamanlayıcılar üzerindeki etkileri hakkında daha fazla bilgi için bkz. [Görev Zamanlayıcı](../../../parallel/concrt/task-scheduler-concurrency-runtime.md).|
|[SchedulerType](concurrency-namespace-enums.md#schedulertype)|`SchedulerKind`İlke tarafından, Scheduler 'ın temel yürütme bağlamlarında kullanmasını gerektiren iş parçacıklarının türünü betimleyen kullanılır. Kullanılabilir Zamanlayıcı ilkeleri hakkında daha fazla bilgi için bkz. [PolicyElementKey](concurrency-namespace-enums.md#policyelementkey).|
|[SchedulingProtocolType](concurrency-namespace-enums.md#schedulingprotocoltype)|`SchedulingProtocol`Zamanlayıcı için hangi zamanlama algoritmasının kullanılacağını açıklayan ilke tarafından kullanılır. Kullanılabilir Zamanlayıcı ilkeleri hakkında daha fazla bilgi için bkz. [PolicyElementKey](concurrency-namespace-enums.md#policyelementkey).|
|[SwitchingProxyState](concurrency-namespace-enums.md#switchingproxystate)|Bir iş parçacığı proxy 'sinin içinde olduğu durumu belirtmek için kullanılır ve farklı bir iş parçacığı proxy 'sine bir işbirlikçi bağlamı anahtarı yürüttüyordur.|
|[task_group_status](concurrency-namespace-enums.md#task_group_status)|Bir veya nesnesinin yürütme durumunu açıklar `task_group` `structured_task_group` . Bu türden bir değer, bir görev grubuna zamanlanan görevlerin tamamlanmasını bekleyen çok sayıda yöntem tarafından döndürülür.|
|[WinRTInitializationType](concurrency-namespace-enums.md#winrtinitializationtype)|`WinRTInitialization`İlke tarafından, Windows 8 veya üzeri sürümü olan işletim sistemlerinde çalışan bir uygulama için zamanlayıcı iş parçacıklarında Windows çalışma zamanı başlatılıp başlatılmayacağını betimleyerek kullanılır. Kullanılabilir Zamanlayıcı ilkeleri hakkında daha fazla bilgi için bkz. [PolicyElementKey](concurrency-namespace-enums.md#policyelementkey).|

### <a name="functions"></a>İşlevler

|Ad|Açıklama|
|----------|-----------------|
|[Ayırma Işlevi](concurrency-namespace-functions.md#alloc)|Eşzamanlılık Çalışma Zamanı önbelleğe alma alt ayırıcılarından belirtilen boyuttaki bellek bloğunu ayırır.|
|[asend Işlevi](concurrency-namespace-functions.md#asend)|Fazla Yüklendi. Verileri hedef bloğuna yaymaya yönelik bir görevi zamanlayan zaman uyumsuz gönderme işlemi.|
|[cancel_current_task Işlevi](concurrency-namespace-functions.md#cancel_current_task)|Yürütülmekte olan görevi iptal eder. Bu işlev, görevin yürütülmesini iptal etmek için bir görevin gövdesinden çağrılabilir ve durumu girmeye neden olur `canceled` .<br /><br /> Bir ' ın gövdesinde değilseniz bu işlevi çağırmak için desteklenen bir senaryo değildir `task` . Bunun yapılması, uygulamanızda kilitlenme veya yanıt verme gibi tanımsız davranışlara neden olur.|
|[create_async Işlevi](concurrency-namespace-functions.md#create_async)|Kullanıcı tarafından sağlanan lambda veya işlev nesnesini temel alan Windows Çalışma Zamanı zaman uyumsuz yapı oluşturur. Öğesinin dönüş türü `create_async` `IAsyncAction^` , `IAsyncActionWithProgress<TProgress>^` `IAsyncOperation<TResult>^` `IAsyncOperationWithProgress<TResult, TProgress>^` yöntemine geçirilen lambda imzasına göre,,, veya ' den biridir.|
|[create_task Işlevi](concurrency-namespace-functions.md#create_task)|Fazla Yüklendi. Bir PPL [görev](task-class.md) nesnesi oluşturur. `create_task`, bir görev oluşturucusunu kullandığınız her yerde kullanılabilir. Görev oluştururken anahtar sözcüğünün kullanılmasına izin verdiğinden, genellikle kolaylık sağlaması için sağlanır **`auto`** .|
|[CreateResourceManager Işlevi](concurrency-namespace-functions.md#createresourcemanager)|Eşzamanlılık Çalışma Zamanı Kaynak Yöneticisi tek örneğini temsil eden bir arabirim döndürür. Kaynak Yöneticisi, kaynakların birbirleriyle birlikte çalışmak isteyen zamanlayıcılar 'ye atanmasından sorumludur.|
|[DisableTracing Işlevi](concurrency-namespace-functions.md#disabletracing)|Eşzamanlılık Çalışma Zamanı izlemeyi devre dışı bırakır. ETW izlemenin varsayılan olarak kaydı silindiğinden bu işlev kullanım dışıdır.|
|[EnableTracing Işlevi](concurrency-namespace-functions.md#enabletracing)|Eşzamanlılık Çalışma Zamanı izlemeye izin vermez. ETW izleme artık varsayılan olarak açık olduğundan bu işlev kullanım dışıdır.|
|[Free Işlevi](concurrency-namespace-functions.md#free)|Yöntemi tarafından daha önce ayrılmış bir bellek bloğunu `Alloc` Eşzamanlılık çalışma zamanı önbelleğe alma alt ayırıcısı 'na yayınlar.|
|[get_ambient_scheduler Işlevi (Eşzamanlılık Çalışma Zamanı)](concurrency-namespace-functions.md#get_ambient_scheduler)||
|[GetExecutionContextId Işlevi](concurrency-namespace-functions.md#getexecutioncontextid)|Arabirimi uygulayan bir yürütme bağlamına atanabilecek benzersiz bir tanımlayıcı döndürür `IExecutionContext` .|
|[GetOSVersion Işlevi](concurrency-namespace-functions.md#getosversion)|İşletim sistemi sürümünü döndürür.|
|[GetProcessorCount Işlevi](concurrency-namespace-functions.md#getprocessorcount)|Temel sistemdeki donanım iş parçacıklarının sayısını döndürür.|
|[GetProcessorNodeCount Işlevi](concurrency-namespace-functions.md#getprocessornodecount)|Temel sistemdeki NUMA düğümlerinin veya işlemci paketlerinin sayısını döndürür.|
|[GetSchedulerId Işlevi](concurrency-namespace-functions.md#getschedulerid)|Arabirimi uygulayan bir Scheduler 'a atanabilen benzersiz bir tanımlayıcı döndürür `IScheduler` .|
|[interruption_point Işlevi](concurrency-namespace-functions.md#interruption_point)|İptal için bir kesinti noktası oluşturur. Bu işlevin çağrıldığı bağlamda bir iptal işlemi devam ediyorsa, bu, şu anda yürütülen paralel çalışmanın yürütülmesini iptal eden bir iç özel durum oluşturur. İptal işlemi devam ediyorsa, işlev hiçbir şey yapmaz.|
|[is_current_task_group_canceling Işlevi](concurrency-namespace-functions.md#is_current_task_group_canceling)|Geçerli bağlamda şu anda yürütülmekte olan görev grubunun etkin bir iptal etme (veya kısa bir süre) üzerinde olup olmadığına ilişkin bir gösterge döndürür. Geçerli bağlamda şu anda bir görev grubu yürütülerek **`false`** döndürülmeyeceğini unutmayın.|
|[make_choice Işlevi](concurrency-namespace-functions.md#make_choice)|Fazla Yüklendi. `choice`İsteğe bağlı `Scheduler` veya `ScheduleGroup` iki veya daha fazla giriş kaynağından bir mesajlaşma bloğu oluşturur.|
|[make_greedy_join Işlevi](concurrency-namespace-functions.md#make_greedy_join)|Fazla Yüklendi. `greedy multitype_join`İsteğe bağlı `Scheduler` veya `ScheduleGroup` iki veya daha fazla giriş kaynağından bir mesajlaşma bloğu oluşturur.|
|[make_join Işlevi](concurrency-namespace-functions.md#make_join)|Fazla Yüklendi. `non_greedy multitype_join`İsteğe bağlı `Scheduler` veya `ScheduleGroup` iki veya daha fazla giriş kaynağından bir mesajlaşma bloğu oluşturur.|
|[make_task Işlevi](concurrency-namespace-functions.md#make_task)|Bir nesne oluşturmak için bir fabrika yöntemi `task_handle` .|
|[parallel_buffered_sort Işlevi](concurrency-namespace-functions.md#parallel_buffered_sort)|Fazla Yüklendi. Belirli bir aralıktaki öğeleri azalan düzende veya ikili koşul tarafından belirtilen bir sıralama ölçütüne göre paralel olarak düzenler. Bu işlev, daha `std::sort` fazla alana ihtiyaç duyması dışında karşılaştırma tabanlı, kararsız ve yerinde bir sıralama olduğundan anlam açısından benzerdir `O(n)` ve sıralanan öğeler için varsayılan başlatma gerektirir.|
|[parallel_for Işlevi](concurrency-namespace-functions.md#parallel_for)|Fazla Yüklendi. `parallel_for`bir dizi dizin üzerinde dolaşır ve paralel olarak her yinelemede Kullanıcı tarafından sağlanan bir işlevi yürütür.|
|[parallel_for_each Işlevi](concurrency-namespace-functions.md#parallel_for_each)|Fazla Yüklendi. `parallel_for_each`bir aralıktaki her öğeye, paralel olarak belirtilen bir işlev uygular. `for_each` `std` Öğe üzerindeki yineleme paralel olarak gerçekleştirilmesinin ve yinelemenin sırası belirlenmemesi dışında, ad alanındaki işleve anlamsal olarak eşdeğerdir. Bağımsız değişkeni, `_Func` `operator()(T)` parametrenin `T` yinelemekte olan kapsayıcının öğe türü olduğu formun işlev çağrısı işlecini desteklemelidir.|
|[parallel_invoke Işlevi](concurrency-namespace-functions.md#parallel_invoke)|Fazla Yüklendi. Parametre olarak sağlanan işlev nesnelerini paralel olarak yürütür ve yürütmeyi tamamlayana kadar blokları engeller. Her işlev nesnesi bir lambda ifadesi, işlev işaretçisi veya imza ile işlev çağrısı işlecini destekleyen herhangi bir nesne olabilir `void operator()()` .|
|[parallel_radixsort Işlevi](concurrency-namespace-functions.md#parallel_radixsort)|Fazla Yüklendi. Belirli bir aralıktaki öğeleri, bir taban x sıralama algoritmasını kullanarak azalan düzende düzenler. Bu bir yansıtma işlevi gerektiren bir kararlı sıralama işlevidir. Bu, öğeleri işaretsiz tamsayı benzeri anahtarlar halinde sıralamak için proje öğeleri olabilir. Sıralanan öğeler için varsayılan başlatma gereklidir.|
|[parallel_reduce Işlevi](concurrency-namespace-functions.md#parallel_reduce)|Fazla Yüklendi. Ardışık kısmi toplamları hesaplayarak, belirtilen aralıktaki tüm öğelerin toplamını hesaplar veya paralel olan belirli bir ikili işlemi kullanmaktan farklı şekilde elde edilen kısmi sonuçların sonucunu hesaplar. `parallel_reduce``std::accumulate`, ikili işlemin ilişkilendirilebilir olmasını gerektirdiğinden ve ilk değer yerine bir kimlik değeri gerektirdiğinden anlam olarak benzerdir.|
|[parallel_sort Işlevi](concurrency-namespace-functions.md#parallel_sort)|Fazla Yüklendi. Belirli bir aralıktaki öğeleri azalan düzende veya ikili koşul tarafından belirtilen bir sıralama ölçütüne göre paralel olarak düzenler. Bu işlev, `std::sort` karşılaştırma tabanlı, kararsız ve yerinde bir sıralama olmak üzere anlamsal olarak benzerdir.|
|[parallel_transform Işlevi](concurrency-namespace-functions.md#parallel_transform)|Fazla Yüklendi. Kaynak aralıktaki her öğeye veya iki kaynak aralığından bir öğe çiftine belirtilen bir işlev nesnesi uygular ve işlev nesnesinin dönüş değerlerini paralel olarak bir hedef aralığa kopyalar. Bu işlev, anlam ile eşdeğerdir `std::transform` .|
|[Receive Işlevi](concurrency-namespace-functions.md#receive)|Fazla Yüklendi. Bir bağlamın tam olarak bir kaynaktan veri beklemesi ve kabul edilen değerleri filtrelemesine olanak tanımak için genel bir alma uygulamasıdır.|
|[run_with_cancellation_token Işlevi](concurrency-namespace-functions.md#run_with_cancellation_token)|Bir işlev nesnesini, belirli bir iptal belirtecinin bağlamında hemen ve zaman uyumlu olarak yürütür.|
|[Send Işlevi](concurrency-namespace-functions.md#send)|Fazla Yüklendi. Hedefin iletiyi kabul etmesini veya reddetmesini bekleyen zaman uyumlu gönderme işlemi.|
|[set_ambient_scheduler Işlevi (Eşzamanlılık Çalışma Zamanı)](concurrency-namespace-functions.md#set_ambient_scheduler)||
|[set_task_execution_resources Işlevi](concurrency-namespace-functions.md#set_task_execution_resources)|Fazla Yüklendi. Eşzamanlılık Çalışma Zamanı iç çalışan iş parçacıkları tarafından kullanılan yürütme kaynaklarını belirtilen benzeşim kümesine kısıtlar.<br /><br /> Bu yöntemi yalnızca Kaynak Yöneticisi oluşturulmadan veya iki Kaynak Yöneticisi yaşam süresi arasında çağırmak için geçerlidir. Kaynak Yöneticisi, çağırma sırasında mevcut olmadığı sürece birden çok kez çağrılabilir. Benzeşim sınırı ayarlandıktan sonra, yönteme bir sonraki geçerli çağrıya kadar yürürlükte kalır `set_task_execution_resources` .<br /><br /> Belirtilen benzeşim maskesi, işlem benzeşimi maskesinin bir alt kümesi olmamalıdır. İşlem benzeşimi gerekirse güncelleştirilir.|
|[Swap Işlevi](concurrency-namespace-functions.md#swap)|İki nesnenin öğelerini değiş tokuş eder `concurrent_vector` .|
|[task_from_exception Işlevi (Eşzamanlılık Çalışma Zamanı)](concurrency-namespace-functions.md#task_from_exception)||
|[task_from_result Işlevi (Eşzamanlılık Çalışma Zamanı)](concurrency-namespace-functions.md#task_from_result)||
|[Trace_agents_register_name Işlevi](concurrency-namespace-functions.md#trace_agents_register_name)|Verilen adı ETW izlemesinde bulunan ileti bloğuna veya aracıya ilişkilendirir.|
|[try_receive Işlevi](concurrency-namespace-functions.md#try_receive)|Fazla Yüklendi. Bir bağlamın tam olarak bir kaynaktan verileri arayacağı ve kabul edilen değerleri filtrelemesine izin veren genel bir TRY-Receive uygulamasıdır. Veriler hazırsanız, yöntem false döndürür.|
|[wait Işlevi](concurrency-namespace-functions.md#wait)|Belirtilen süre boyunca geçerli bağlamı duraklatır.|
|[when_all Işlevi](concurrency-namespace-functions.md#when_all)|Bağımsız değişken olarak sağlanan tüm görevler başarıyla tamamlandığında başarıyla tamamlanacak bir görev oluşturur.|
|[when_any Işlevi](concurrency-namespace-functions.md#when_any)|Fazla Yüklendi. Bağımsız değişken olarak sağlanan görevlerden herhangi biri başarıyla tamamlandığında başarıyla tamamlanacak bir görev oluşturur.|

### <a name="operators"></a>İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[işleç! =](concurrency-namespace-operators.md#operator_neq)|`concurrent_vector`İşlecin sol tarafındaki nesnenin sağ taraftaki nesneye eşit olup olmadığını sınar `concurrent_vector` .|
|[işleç&&](concurrency-namespace-operators.md#operator_amp_amp)|Fazla Yüklendi. Bağımsız değişken olarak sağlanan görevlerin her ikisi de başarıyla tamamlandığında başarıyla tamamlanacak bir görev oluşturur.|
|[işleç&#124;&#124;](concurrency-namespace-operators.md#operator_lor)|Fazla Yüklendi. Bağımsız değişken olarak sağlanan görevlerden biri başarıyla tamamlandığında başarıyla tamamlanacak bir görev oluşturur.|
|[işleç<](concurrency-namespace-operators.md#operator_lt)|`concurrent_vector`İşlecin sol tarafındaki nesnenin sağ taraftaki nesneden daha az olup olmadığını sınar `concurrent_vector` .|
|[işleç<=](concurrency-namespace-operators.md#operator_lt_eq)|`concurrent_vector`İşlecin sol tarafındaki nesnenin sağ taraftaki nesneden küçük veya ona eşit olup olmadığını sınar `concurrent_vector` .|
|[işleç = =](concurrency-namespace-operators.md#operator_eq_eq)|`concurrent_vector`İşlecin sol tarafındaki nesnenin sağ taraftaki nesneye eşit olup olmadığını sınar `concurrent_vector` .|
|[işleç>](concurrency-namespace-operators.md#operator_gt)|`concurrent_vector`İşlecin sol tarafındaki nesnenin sağ taraftaki nesneden daha büyük olup olmadığını sınar `concurrent_vector` .|
|[işleç>=](concurrency-namespace-operators.md#operator_lt_eq)|`concurrent_vector`İşlecin sol tarafındaki nesnenin sağ taraftaki nesneden büyük veya ona eşit olup olmadığını sınar `concurrent_vector` .|

### <a name="constants"></a>Sabitler

|Ad|Açıklama|
|----------|-----------------|
|[AgentEventGuid](concurrency-namespace-constants1.md#agenteventguid)|Eşzamanlılık Çalışma Zamanı aracılar Kitaplığı tarafından tetiklenen ETW olaylarını açıklayan kategori GUID 'SI ({B9B5B78C-0713-4898-A21A-C67949DCED07}).|
|[ChoreEventGuid](concurrency-namespace-constants1.md#choreeventguid)|Doğrudan işlerini unutun veya görevlerle ilgili eşzamanlılık çalışma zamanı tarafından tetiklenen ETW olaylarını açıklayan kategori GUID 'si.|
|[ConcRT_ProviderGuid](concurrency-namespace-constants1.md#concrt_providerguid)|Eşzamanlılık Çalışma Zamanı için ETW sağlayıcısı GUID 'ı.|
|[CONCRT_RM_VERSION_1](concurrency-namespace-constants1.md#concrt_rm_version_1)|Visual Studio 2010 ' de tanımlanan Kaynak Yöneticisi arabiriminin desteğini gösterir.|
|[ConcRTEventGuid](concurrency-namespace-constants1.md#concrteventguid)|Başka bir kategori tarafından daha önce açıklanmayan Eşzamanlılık Çalışma Zamanı tarafından tetiklenen ETW olaylarını açıklayan kategori GUID 'SI.|
|[ContextEventGuid](concurrency-namespace-constants1.md#contexteventguid)|Bağlamlarla doğrudan ilgili olan Eşzamanlılık Çalışma Zamanı tarafından tetiklenen ETW olaylarını açıklayan kategori GUID 'SI.|
|[COOPERATIVE_TIMEOUT_INFINITE](concurrency-namespace-constants1.md#cooperative_timeout_infinite)|Bir bekleme süresinin asla zaman aşımına uğramayacağını gösteren değer.|
|[COOPERATIVE_WAIT_TIMEOUT](concurrency-namespace-constants1.md#cooperative_wait_timeout)|Bekleme süresinin zaman aşımına uğradığını belirten değer.|
|[INHERIT_THREAD_PRIORITY](concurrency-namespace-constants1.md#inherit_thread_priority)|`ContextPriority`Zamanlayıcı ' daki tüm bağlamların iş parçacığı önceliğinin, Scheduler 'ı oluşturan iş parçacığından aynı olması gerektiğini belirten, ilke anahtarı için özel değer.|
|[LockEventGuid](concurrency-namespace-constants1.md#lockeventguid)|Doğrudan kilitlerle ilgili Eşzamanlılık Çalışma Zamanı tarafından tetiklenen ETW olaylarını açıklayan kategori GUID 'SI.|
|[MaxExecutionResources](concurrency-namespace-constants1.md#maxexecutionresources)|İlke anahtarları ve için özel değer `MinConcurrency` `MaxConcurrency` . Diğer kısıtlamalar yokluğunda makinedeki donanım iş parçacığı sayısı varsayılan olarak belirlenmiştir.|
|[PPLParallelForeachEventGuid](concurrency-namespace-constants1.md#pplparallelforeacheventguid)|İşlevin kullanımıyla doğrudan ilgili Eşzamanlılık Çalışma Zamanı tarafından tetiklenen ETW olaylarını açıklayan kategori GUID 'SI `parallel_for_each` .|
|[PPLParallelForEventGuid](concurrency-namespace-constants1.md#pplparallelforeventguid)|İşlevin kullanımıyla doğrudan ilgili Eşzamanlılık Çalışma Zamanı tarafından tetiklenen ETW olaylarını açıklayan kategori GUID 'SI `parallel_for` .|
|[PPLParallelInvokeEventGuid](concurrency-namespace-constants1.md#pplparallelinvokeeventguid)|İşlevin kullanımıyla doğrudan ilgili Eşzamanlılık Çalışma Zamanı tarafından tetiklenen ETW olaylarını açıklayan kategori GUID 'SI `parallel_invoke` .|
|[ResourceManagerEventGuid](concurrency-namespace-constants1.md#resourcemanagereventguid)|Doğrudan Resource Manager ile ilgili olan Eşzamanlılık Çalışma Zamanı tarafından tetiklenen ETW olaylarını açıklayan kategori GUID 'SI.|
|[ScheduleGroupEventGuid](concurrency-namespace-constants1.md#schedulegroupeventguid)|Zamanlama gruplarıyla doğrudan ilgili Eşzamanlılık Çalışma Zamanı tarafından tetiklenen ETW olaylarını açıklayan kategori GUID 'SI.|
|[SchedulerEventGuid](concurrency-namespace-constants1.md#schedulereventguid)|Zamanlayıcı etkinliğiyle doğrudan ilgili Eşzamanlılık Çalışma Zamanı tarafından tetiklenen ETW olaylarını açıklayan kategori GUID 'SI.|
|[VirtualProcessorEventGuid](concurrency-namespace-constants1.md#virtualprocessoreventguid)|Sanal işlemcilerle doğrudan ilgili Eşzamanlılık Çalışma Zamanı tarafından tetiklenen ETW olaylarını açıklayan kategori GUID 'SI.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** Agents. h, concrt. h, concrtrm. h, concurrent_priority_queue. h, concurrent_queue. h, concurrent_unordered_map. h, concurrent_unordered_set. h, concurrent_vector. h, internal_concurrent_hash. h, internal_split_ordered_list. h, PPL. h, pplcancellation_token. h, pplconcrt. h, pplınterface. h, ppltasks. h

## <a name="see-also"></a>Ayrıca bkz.

[Başvuru](reference-concurrency-runtime.md)
