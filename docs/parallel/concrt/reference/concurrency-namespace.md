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
ms.openlocfilehash: 5449362454c5899e544ed370f13d28471a59bd13
ms.sourcegitcommit: b8c22e6d555cf833510753cba7a368d57e5886db
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76821850"
---
# <a name="concurrency-namespace"></a>concurrency Ad Alanı

`Concurrency` ad alanı, için C++eşzamanlı bir programlama çerçevesi olan eşzamanlılık çalışma zamanı size erişim sağlayan sınıfları ve işlevleri sağlar. Daha fazla bilgi için bkz. [Eşzamanlılık çalışma zamanı](../../../parallel/concrt/concurrency-runtime.md).

## <a name="syntax"></a>Sözdizimi

```
namespace concurrency;
```

## <a name="members"></a>Üyeler

### <a name="typedefs"></a>Tür tanımları

|Name|Açıklama|
|----------|-----------------|
|`runtime_object_identity`|Her ileti örneği, kopyalandığı ve mesajlaşma bileşenleri arasında geçirildiği için onu izleyen bir kimliğe sahiptir. İleti nesnesinin adresi olamaz.|
|`task_status`|Görevin Terminal durumunu temsil eden bir tür. Geçerli değerler `completed` ve `canceled`.|
|`TaskProc`|`void (__cdecl * TaskProc)(void *)`olarak tanımlanan, bir görevin bir öğesel soyutlaması. Bir görevin gövdesini çağırmak için bir `TaskProc` çağırılır.|
|`TaskProc_t`|`void (__cdecl * TaskProc_t)(void *)`olarak tanımlanan, bir görevin bir öğesel soyutlaması. Bir görevin gövdesini çağırmak için bir `TaskProc` çağırılır.|

### <a name="classes"></a>Sınıflar

|Name|Açıklama|
|----------|-----------------|
|[affinity_partitioner Sınıfı](affinity-partitioner-class.md)|`affinity_partitioner` sınıfı `static_partitioner` sınıfına benzerdir, ancak alt aralıkları çalışan iş parçacıklarıyla eşleme seçeneği tarafından önbellek benzeşimini geliştirir. Bir döngü aynı veri kümesi üzerinde yeniden yürütüldüğünde ve veriler önbelleğe sığıyorsa performansı önemli ölçüde iyileştirebilir. Aynı `affinity_partitioner` nesnesinin, veri konumundan faydalanmak için belirli bir veri kümesi üzerinde yürütülen paralel bir döngünün sonraki yinelemeleriyle birlikte kullanılması gerektiğini unutmayın.|
|[agent Sınıfı](agent-class.md)|Tüm bağımsız aracılar için temel sınıf olarak kullanılması amaçlanan bir sınıf. Diğer aracılardan durumu gizlemek ve ileti geçirme kullanılarak etkileşim kurmak için kullanılır.|
|[auto_partitioner Sınıfı](auto-partitioner-class.md)|`auto_partitioner` sınıfı varsayılan yöntemi temsil eder `parallel_for`, `parallel_for_each` ve `parallel_transform` üzerinde yineleme aralığını bölümlemek için kullanılır. Bu yöntem, yük dengeleme için employes aralığı çalmasını ve yineleme başına iptalinin nasıl bölümlenmesini sağlayacak.|
|[bad_target Sınıfı](bad-target-class.md)|Bu sınıf, bir ileti bloğuna gerçekleştirilen işlem için geçersiz olan bir hedefe işaretçi verildiğinde oluşan bir özel durumu açıklar.|
|[call Sınıfı](call-class.md)|`call` mesajlaşma bloğu, bir ileti alırken belirtilen bir işlevi çağıran çok kaynaklı ve sıralı bir `target_block`.|
|[cancellation_token Sınıfı](cancellation-token-class.md)|`cancellation_token` sınıfı, bazı bir işlemin iptal edilip edilmeyeceğini belirleme yeteneğini temsil eder. Belirli bir belirteç, örtük iptal sağlamak için bir `task_group`, `structured_task_group`veya `task` ilişkilendirilebilir. Ayrıca, iptal için yoklanabilir ya da ilişkili `cancellation_token_source` iptal edildiğinde, ve için kayıtlı bir geri çağırma olur.|
|[cancellation_token_registration Sınıfı](cancellation-token-registration-class.md)|`cancellation_token_registration` sınıfı, bir `cancellation_token`geri çağırma bildirimini temsil eder. Bir `cancellation_token` `register` yöntemi iptal gerçekleştiğinde bildirim almak için kullanıldığında, çağıranın `deregister` yönteminin kullanımı ile belirli bir geri çağırma işlemini istemesi için geri çağırmada tanıtıcı olarak bir `cancellation_token_registration` nesnesi döndürülür.|
|[cancellation_token_source Sınıfı](cancellation-token-source-class.md)|`cancellation_token_source` sınıfı, bazı iptal edilebilen işlemleri iptal etme yeteneğini temsil eder.|
|[choice Sınıfı](choice-class.md)|`choice` mesajlaşma bloğu, bir kaynak kümesiyle denetim akışı etkileşimini temsil eden çok kaynaklı, tek hedef bir bloğudur. Seçim bloğu, birden fazla kaynağın bir ileti oluşturmasını ve iletiyi üreten kaynağın dizinini yaymasını bekler.|
|[combinable Sınıfı](combinable-class.md)|`combinable<T>` nesnesi, paralel algoritmalar sırasında kilit içermeyen iş parçacığı yerel alt hesaplamalar gerçekleştirmek için verilerin iş parçacığı özel kopyalarını sağlamaya yöneliktir. Paralel işlemin sonunda, iş parçacığı özel alt hesaplamaları daha sonra nihai bir sonuçla birleştirilebilir. Bu sınıf, paylaşılan bir değişken yerine kullanılabilir ve bu paylaşılan değişkende çok fazla çekişme olmaması durumunda performans iyileştirmesine neden olabilir.|
|[concurrent_priority_queue Sınıfı](concurrent-priority-queue-class.md)|`concurrent_priority_queue` sınıfı, birden çok iş parçacığının aynı anda gönderim ve pop öğelerine izin veren bir kapsayıcıdır. Öğelerin, bir şablon bağımsız değişkeni olarak sağlanan bir functor tarafından belirlendiği öncelik sırasına göre belirlenir.|
|[concurrent_queue Sınıfı](concurrent-queue-class.md)|`concurrent_queue` sınıfı, öğeleri için ilk ın, ilk çıkar erişimine izin veren bir dizi kapsayıcı sınıfıdır. `push` ve `try_pop`gibi sınırlı sayıda eşzamanlılık güvenli işlem kümesi sunar.|
|[concurrent_unordered_map Sınıfı](concurrent-unordered-map-class.md)|`concurrent_unordered_map` sınıfı, `std::pair<const K, _Element_type>`türündeki çeşitli uzunluktaki öğeleri denetleyen eşzamanlılık açısından güvenli bir kapsayıcıdır. Dizi eşzamanlılık açısından güvenli ekleme, öğe erişimi, yineleyici erişimi ve yineleyici çapraz geçiş işlemlerine olanak sağlayan bir şekilde temsil edilir.|
|[concurrent_unordered_multimap Sınıfı](concurrent-unordered-multimap-class.md)|`concurrent_unordered_multimap` sınıfı, `std::pair<const K, _Element_type>`türündeki çeşitli uzunluktaki öğeleri denetleyen eşzamanlılık açısından güvenli bir kapsayıcıdır. Dizi eşzamanlılık açısından güvenli ekleme, öğe erişimi, yineleyici erişimi ve yineleyici çapraz geçiş işlemlerine olanak sağlayan bir şekilde temsil edilir.|
|[concurrent_unordered_multiset Sınıfı](concurrent-unordered-multiset-class.md)|`concurrent_unordered_multiset` sınıfı, K türü öğelerin değişen uzunluklu bir dizisini denetleyen eşzamanlılık açısından güvenli bir kapsayıcıdır. Dizi eşzamanlılık açısından güvenli ekleme, öğe erişimi, yineleyici erişimi ve yineleyici çapraz geçiş işlemlerine olanak sağlayan bir şekilde temsil edilir.|
|[concurrent_unordered_set Sınıfı](concurrent-unordered-set-class.md)|`concurrent_unordered_set` sınıfı, K türü öğelerin değişen uzunluklu bir dizisini denetleyen eşzamanlılık açısından güvenli bir kapsayıcıdır. Dizi eşzamanlılık açısından güvenli ekleme, öğe erişimi, yineleyici erişimi ve yineleyici çapraz geçiş işlemlerine olanak sağlayan bir şekilde temsil edilir.|
|[concurrent_vector Sınıfı](concurrent-vector-class.md)|`concurrent_vector` sınıfı, herhangi bir öğeye rastgele erişime izin veren bir dizi kapsayıcı sınıfıdır. Eşzamanlılık açısından güvenli ekleme, öğe erişimi, yineleyici erişimi ve yineleyici çapraz geçiş işlemlerine izin vermez.|
|[Bağlam Sınıfı](context-class.md)|Yürütme bağlamı için bir soyutlama temsil eder.|
|[context_self_unblock Sınıfı](context-self-unblock-class.md)|Bu sınıf, bir `Context` nesnesinin `Unblock` yöntemi aynı içerikten çağrıldığında oluşturulan bir özel durumu açıklar. Bu, belirli bir bağlam tarafından onun engellemesini kaldırmak için bir girişim olduğunu gösterir.|
|[context_unblock_unbalanced Sınıfı](context-unblock-unbalanced-class.md)|Bu sınıf, bir `Context` nesnesinin `Block` ve `Unblock` yöntemlerine yapılan çağrılar düzgün şekilde eşleştirilmediğinde oluşan bir özel durumu açıklar.|
|[critical_section Sınıfı](critical-section-class.md)|Eşzamanlılık Çalışma Zamanı açıkça farkında olan, yer olmayan bir mutex.|
|[CurrentScheduler Sınıfı](currentscheduler-class.md)|Çağıran bağlamla ilişkili geçerli Zamanlayıcı için bir soyutlama temsil eder.|
|[default_scheduler_exists Sınıfı](default-scheduler-exists-class.md)|Bu sınıf, işlem içinde varsayılan bir Zamanlayıcı zaten varken `Scheduler::SetDefaultSchedulerPolicy` yöntemi çağrıldığında oluşturulan bir özel durumu açıklar.|
|[event Sınıfı](event-class.md)|Eşzamanlılık Çalışma Zamanı açıkça farkında olan el ile sıfırlama olayı.|
|[improper_lock Sınıfı](improper-lock-class.md)|Bu sınıf, bir kilit yanlış edinildiği zaman oluşturulan bir özel durum tanımlar.|
|[improper_scheduler_attach Sınıfı](improper-scheduler-attach-class.md)|Bu sınıf, `Attach` yöntemi geçerli bağlama zaten eklenmiş olan bir `Scheduler` nesnesi üzerinde çağrıldığında oluşturulan bir özel durumu açıklar.|
|[improper_scheduler_detach Sınıfı](improper-scheduler-detach-class.md)|Bu sınıf, bir `Scheduler` nesnesinin `Attach` yöntemi kullanılarak herhangi bir Scheduler 'a eklenmemiş bir bağlamda `CurrentScheduler::Detach` yöntemi çağrıldığında oluşturulan bir özel durumu açıklar.|
|[improper_scheduler_reference Sınıfı](improper-scheduler-reference-class.md)|Bu sınıf, `Reference` yöntemi, bu Scheduler 'ın parçası olmayan bir bağlamdan kapatılmakta olan bir `Scheduler` nesnesi üzerinde çağrıldığında oluşturulan bir özel durumu açıklar.|
|[invalid_link_target Sınıfı](invalid-link-target-class.md)|Bu sınıf, bir mesajlaşma bloğunun `link_target` yöntemi çağrıldığında ve mesajlaşma bloğu hedefle bağlantı kuramıyor durumunda oluşturulan bir özel durumu açıklar. Bu, mesajlaşma bloğunun izin verdiği bağlantı sayısını aşmanın veya belirli bir hedefin aynı kaynağa iki kez bağlantı kurmaya çalıştığı sonuç olabilir.|
|[invalid_multiple_scheduling Sınıfı](invalid-multiple-scheduling-class.md)|Bu sınıf, `wait` veya `run_and_wait` yöntemlerine aradaki bir çağrı olmadan bir `task_group` veya `structured_task_group` nesnesinin `run` yöntemi kullanılarak birden çok kez zamanlan`task_handle` dığında oluşturulan bir özel durumu açıklar.|
|[invalid_operation Sınıfı](invalid-operation-class.md)|Bu sınıf, Eşzamanlılık Çalışma Zamanı tarafından oluşturulan başka bir özel durum türü tarafından daha doğru bir şekilde açıklanmayan geçersiz bir işlem gerçekleştirildiğinde oluşturulan bir özel durumu açıklar.|
|[invalid_oversubscribe_operation Sınıfı](invalid-oversubscribe-operation-class.md)|Bu sınıf, `_BeginOversubscription` parametresi `true`olarak ayarlanan `Context::Oversubscribe` yöntemine önceki bir çağrı olmadan `false` olarak ayarlanan `_BeginOversubscription` parametresi ile çağrıldığında `Context::Oversubscribe` oluşturulan bir özel durumu açıklar.|
|[invalid_scheduler_policy_key Sınıfı](invalid-scheduler-policy-key-class.md)|Bu sınıf, `SchedulerPolicy` nesne oluşturucusuna geçersiz veya bilinmeyen bir anahtar geçirildiğinde oluşturulan bir özel durumu açıklar veya bir `SchedulerPolicy` nesnesinin `SetPolicyValue` yöntemine `SetConcurrencyLimits` yöntemi gibi diğer yollarla değiştirilmesi gereken bir anahtar geçirilir.|
|[invalid_scheduler_policy_thread_specification Sınıfı](invalid-scheduler-policy-thread-specification-class.md)|Bu sınıf, bir `SchedulerPolicy` nesnesinin eşzamanlılık sınırlarını ayarlamak için bir girişimde bulunulduğunda bir özel durum tanımlar ve `MinConcurrency` anahtarı değeri `MaxConcurrency` anahtarının değerinden daha az olur.|
|[invalid_scheduler_policy_value Sınıfı](invalid-scheduler-policy-value-class.md)|Bu sınıf, bir `SchedulerPolicy` nesnesinin ilke anahtarı bu anahtar için geçersiz bir değere ayarlandığında oluşturulan bir özel durumu açıklar.|
|[ISource Sınıfı](isource-class.md)|`ISource` sınıfı tüm kaynak blokları için arabirimidir. Kaynak blokları iletileri `ITarget` bloklara yayar.|
|[ITarget Sınıfı](itarget-class.md)|`ITarget` sınıfı tüm hedef blokların arabirimidir. Hedef bloklar, `ISource` blokları tarafından bunlara sunulan iletileri tüketir.|
|[join Sınıfı](join-class.md)|`join` mesajlaşma bloğu, kaynaklarından her birinden `T` türündeki iletileri birleştiren tek hedef, çok kaynaklı ve sıralı `propagator_block`.|
|[location Sınıfı](location-class.md)|Donanımda fiziksel bir konumun soyutlaması.|
|[message Sınıfı](message-class.md)|İleti blokları arasında geçilen veri yükünü içeren temel ileti zarfı.|
|[message_not_found Sınıfı](message-not-found-class.md)|Bu sınıf, bir ileti bloğu istenen iletiyi bulamadığında oluşan bir özel durum tanımlar.|
|[message_processor Sınıfı](message-processor-class.md)|`message_processor` sınıfı, `message` nesnelerinin işlenmesine yönelik soyut temel sınıftır. İleti sıralaması hakkında garanti yoktur.|
|[missing_wait Sınıfı](missing-wait-class.md)|Bu sınıf, nesnenin yıkıcının yürütüldüğü sırada bir `task_group` veya `structured_task_group` nesnesine hala zamanlanan görevler olduğunda oluşturulan bir özel durumu açıklar. Bu özel durum, bir özel durumun sonucu olarak bir yığın geri sarma işlemi nedeniyle yok edici olursa hiçbir durum oluşturulmaz.|
|[multi_link_registry Sınıfı](multi-link-registry-class.md)|`multi_link_registry` nesnesi, birden çok kaynak bloğunu veya birden çok hedef bloğu yöneten bir `network_link_registry`.|
|[multitype_join Sınıfı](multitype-join-class.md)|`multitype_join` mesajlaşma bloğu, kaynaklarından her birinin farklı türlerindeki iletileri birleştiren ve hedeflerine Birleşik iletilerin bir listesini sunan çok kaynaklı, tek hedef mesajlaşma bloğudur.|
|[nested_scheduler_missing_detach Sınıfı](nested-scheduler-missing-detach-class.md)|Bu sınıf, Eşzamanlılık Çalışma Zamanı bir özel durum tanımlar ve bu, `Scheduler` nesnesinin `Attach` yöntemini kullanarak ikinci bir Scheduler 'a eklenmiş bir bağlamda `CurrentScheduler::Detach` yöntemini çağırmak için ihmal edileceğini algıladığında oluşur.|
|[network_link_registry Sınıfı](network-link-registry-class.md)|`network_link_registry` soyut temel sınıfı, kaynak ve hedef bloklar arasındaki bağlantıları yönetir.|
|[operation_timed_out Sınıfı](operation-timed-out-class.md)|Bu sınıf, bir işlem zaman aşımına uğramışsa oluşturulan özel durumu açıklar.|
|[ordered_message_processor Sınıfı](ordered-message-processor-class.md)|`ordered_message_processor` ileti bloklarının iletileri alındıkları sırada işlemesini sağlayan bir `message_processor`.|
|[overwrite_buffer Sınıfı](overwrite-buffer-class.md)|`overwrite_buffer` mesajlaşma bloğu, aynı anda tek bir iletiyi depolayan çok hedefli, çok kaynaklı ve sıralı `propagator_block`. Yeni iletiler üzerine yazılır.|
|[progress_reporter Sınıfı](progress-reporter-class.md)|Progress Reporter sınıfı, belirli bir türdeki ilerleme bildirimlerinin raporlanmasını sağlar. Her progress_reporter nesnesi belirli bir zaman uyumsuz eyleme veya işleme bağlanır.|
|[propagator_block Sınıfı](propagator-block-class.md)|`propagator_block` sınıfı, hem kaynak hem de hedef olan ileti blokları için soyut bir temel sınıftır. Hem `source_block` hem de `target_block` sınıflarının işlevlerini birleştirir.|
|[reader_writer_lock Sınıfı](reader-writer-lock-class.md)|Yalnızca yerel olarak dönen bir yazıcı tercihi kuyruğu tabanlı okuyucu-yazıcı kilidi. Kilit, sürekli bir yazıcı yüklemesi altında yazıcılara ve başlangıç okuyucularına ilk çıkar (FıFO) erişimi verir.|
|[ScheduleGroup Sınıfı](schedulegroup-class.md)|Bir zamanlama grubu için bir soyutlama temsil eder. Zamanlama grupları, farklı bir gruba geçmeden önce aynı grupta başka bir görevi yürüterek veya aynı grupta aynı grup içinde birden çok öğe yürütülerek, zamana bağlı birlikte, aynı grupta daha fazla görev yürütülerek bir ilgili iş kümesini düzenler. NUMA düğümü veya fiziksel yuva.|
|[Zamanlayıcı Sınıfı](scheduler-class.md)|Eşzamanlılık Çalışma Zamanı Zamanlayıcı için bir soyutlama temsil eder.|
|[scheduler_not_attached Sınıfı](scheduler-not-attached-class.md)|Bu sınıf, bir Scheduler 'ın geçerli içeriğe eklenmesini gerektiren bir işlem gerçekleştirildiğinde oluşan bir özel durum tanımlar ve biri değildir.|
|[scheduler_resource_allocation_error Sınıfı](scheduler-resource-allocation-error-class.md)|Bu sınıf, Eşzamanlılık Çalışma Zamanı kritik bir kaynak alma hatası nedeniyle oluşan bir özel durumu açıklar.|
|[scheduler_worker_creation_error Sınıfı](scheduler-worker-creation-error-class.md)|Bu sınıf, Eşzamanlılık Çalışma Zamanı bir çalışan yürütme bağlamı oluşturma hatası nedeniyle oluşan bir özel durumu açıklar.|
|[SchedulerPolicy Sınıfı](schedulerpolicy-class.md)|`SchedulerPolicy` sınıfı, bir Zamanlayıcı örneğinin davranışını denetleyen her ilke öğesi için bir olan anahtar/değer çiftleri kümesi içerir.|
|[simple_partitioner Sınıfı](simple-partitioner-class.md)|`simple_partitioner` sınıfı, `parallel_for`tarafından yineleyen aralığın statik bir bölümlemesini temsil eder. Bölümleyici, aralığı parçalara böler, her öbek en az öbek boyutu tarafından belirtilen yineleme sayısına sahiptir.|
|[single_assignment Sınıfı](single-assignment-class.md)|`single_assignment` mesajlaşma bloğu, tek bir kez yazılabilir `message`saklayabilen çok hedefli, çok kaynaklı ve sıralı `propagator_block`.|
|[single_link_registry Sınıfı](single-link-registry-class.md)|`single_link_registry` nesnesi yalnızca tek bir kaynak veya hedef bloğu yöneten bir `network_link_registry`.|
|[source_block Sınıfı](source-block-class.md)|`source_block` sınıfı, yalnızca kaynak blokları için soyut bir temel sınıftır. Sınıfı, temel bağlantı yönetimi işlevlerinin yanı sıra ortak hata denetimleri sağlar.|
|[source_link_manager Sınıfı](source-link-manager-class.md)|`source_link_manager` nesnesi, `ISource` bloklara yönelik ileti bloğu ağ bağlantılarını yönetir.|
|[static_partitioner Sınıfı](static-partitioner-class.md)|`static_partitioner` sınıfı, `parallel_for`tarafından yineleyen aralığın statik bir bölümlemesini temsil eder. Bölümleyici, zayıf Zamanlayıcı tarafından kullanılabilen çalışanlar olduğundan, aralığı çok sayıda parçalara ayırır.|
|[structured_task_group Sınıfı](structured-task-group-class.md)|`structured_task_group` sınıfı, paralel çalışmanın yüksek yapılandırılmış bir koleksiyonunu temsil eder. Tek tek paralel görevleri `task_handle` nesneleri kullanarak bir `structured_task_group` kuyruğa alabilir ve bunların tamamlanmasını bekleyebilir veya yürütmeyi bitirmeden önce görev grubunu iptal edebilirsiniz. Bu, yürütmeyi başlamamış olan tüm görevleri iptal eder.|
|[target_block Sınıfı](target-block-class.md)|`target_block` sınıfı, temel bağlantı yönetim işlevselliği ve yalnızca hedef bloklar için hata denetimi sağlayan bir soyut temel sınıftır.|
|[task Sınıfı (Eşzamanlılık Çalışma Zamanı)](task-class.md)|Paralel Desenler kitaplığı (PPL) `task` sınıfı. `task` nesnesi, zaman uyumsuz olarak yürütülebilecek çalışmayı ve Eşzamanlılık Çalışma Zamanı paralel algoritmalarla oluşturulan diğer görevlerle aynı anda diğer görevleri ve paralel çalışmayı temsil eder. Başarıyla tamamlandığında `_ResultType` türünde bir sonuç üretir. `task<void>` görevler sonuç oluşturmaz. Bir görev, diğer görevlerden bağımsız olarak bekleve iptal edilebilir. Ayrıca, devamlılık (`then`) ve birleştirme (`when_all`) ve seçim (`when_any`) desenlerini kullanan diğer görevlerle de birleştirilebilir.|
|[task_canceled Sınıfı](task-canceled-class.md)|Bu sınıf, geçerli görevin iptal edilmeye zorlamak için PPL görev katmanı tarafından oluşturulan bir özel durumu açıklar. Ayrıca, iptal edilen bir görev için [görev](task-class.md)üzerinde `get()` yöntemi tarafından da oluşturulur.|
|[task_completion_event Sınıfı](task-completion-event-class.md)|`task_completion_event` sınıfı, bir koşul karşılanana kadar bir görevin yürütülmesini ertelemenize veya dış bir olaya yanıt olarak bir görev başlatmanıza olanak sağlar.|
|[task_continuation_context Sınıfı](task-continuation-context-class.md)|`task_continuation_context` sınıfı, bir devamlılığın nerede yürütülmesini istediğinizi belirtmenize olanak tanır. Bu sınıfı yalnızca UWP uygulamasından kullanmak faydalıdır. Windows Çalışma Zamanı olmayan uygulamalar için, görev devamlılığın yürütme bağlamı, çalışma zamanı tarafından belirlenir ve yapılandırılamaz.|
|[task_group Sınıfı](task-group-class.md)|`task_group` sınıfı, beklemiş veya iptal edilebilir bir paralel çalışma koleksiyonunu temsil eder.|
|[task_handle Sınıfı](task-handle-class.md)|`task_handle` sınıfı, tek bir paralel iş öğesini temsil eder. Bir iş parçasını yürütmek için gereken yönergeleri ve verileri saklar.|
|[task_options Sınıfı (Eşzamanlılık Çalışma Zamanı)](task-options-class-concurrency-runtime.md)|Bir görev oluşturmak için izin verilen seçenekleri temsil eder|
|[timer Sınıfı](timer-class.md)|`timer` mesajlaşma bloğu, belirli bir süre geçtikten sonra veya belirli aralıklarla hedefine bir ileti gönderebilen tek hedef `source_block`.|
|[transformer Sınıfı](transformer-class.md)|`transformer` mesajlaşma bloğu, tek bir türde iletileri kabul edebilecek ve farklı bir türden sınırsız sayıda ileti saklayabilen tek hedefli, çok kaynaklı ve sıralı `propagator_block`.|
|[unbounded_buffer Sınıfı](unbounded-buffer-class.md)|`unbounded_buffer` mesajlaşma bloğu, sınırsız sayıda iletiyi depolayan çok hedefli, çok kaynaklı ve sıralı `propagator_block`.|
|[unsupported_os Sınıfı](unsupported-os-class.md)|Bu sınıf, desteklenmeyen bir işletim sistemi kullanıldığında oluşturulan bir özel durumu açıklar.|

### <a name="structures"></a>Yapılar

|Name|Açıklama|
|----------|-----------------|
|[DispatchState Yapısı](dispatchstate-structure.md)|`DispatchState` yapısı, durumu `IExecutionContext::Dispatch` yöntemine aktarmak için kullanılır. `Dispatch` yönteminin bir `IExecutionContext` arabiriminde çağrıldığı koşulları açıklar.|
|[IExecutionContext Yapısı](iexecutioncontext-structure.md)|Belirli bir sanal işlemci üzerinde çalışabilen ve birlikte çalışan içerik anahtarlamalı bir yürütme bağlamına yönelik arabirim.|
|[IExecutionResource Yapısı](iexecutionresource-structure.md)|Donanım iş parçacığı için bir soyutlama.|
|[IResourceManager Yapısı](iresourcemanager-structure.md)|Eşzamanlılık Çalışma Zamanı Kaynak Yöneticisi arabirimi. Bu, zamanlayıcılar ile iletişim kuran arabirimdir Kaynak Yöneticisi.|
|[IScheduler Yapısı](ischeduler-structure.md)|Bir iş Scheduler soyutlaması için arabirim. Eşzamanlılık Çalışma Zamanı Kaynak Yöneticisi, iş zamanlayıcılar ile iletişim kurmak için bu arabirimi kullanır.|
|[ISchedulerProxy Yapısı](ischedulerproxy-structure.md)|Zamanlayıcılar tarafından kaynak ayırmayı anlaşmak için Eşzamanlılık Çalışma Zamanı Kaynak Yöneticisi iletişim kuran arabirim.|
|[IThreadProxy Yapısı](ithreadproxy-structure.md)|Yürütmenin iş parçacığı için bir soyutlama. Oluşturduğunuz Scheduler `SchedulerType` ilke anahtarına bağlı olarak, Kaynak Yöneticisi, size düzenli bir Win32 iş parçacığı veya Kullanıcı modu zamanlanabilen (UMS) iş parçacığı tarafından desteklenen bir iş parçacığı proxy 'si verir. UMS iş parçacıkları, Windows 7 ve üzeri sürümleri ile 64 bit işletim sistemlerinde desteklenir.|
|[ITopologyExecutionResource Yapısı](itopologyexecutionresource-structure.md)|Kaynak Yöneticisi tarafından tanımlanan yürütme kaynağına yönelik arabirim.|
|[ITopologyNode Yapısı](itopologynode-structure.md)|Kaynak Yöneticisi tarafından tanımlanan bir topoloji düğümüne yönelik arabirim. Bir düğüm bir veya daha fazla yürütme kaynağı içeriyor.|
|[IUMSCompletionList Yapısı](iumscompletionlist-structure.md)|UMS tamamlama listesini temsil eder. Bir UMS iş parçacığı engellediğinde, başlangıçtaki iş parçacığı engellenirken temeldeki sanal işlemci kökünde zamanlanmak üzere bir karar vermek üzere Scheduler 'ın belirlenen zamanlama bağlamı gönderilir. Orijinal iş parçacığı kaldırılıyorsa, işletim sistemi bu arabirim aracılığıyla erişilebilen tamamlanma listesine sıraya alır. Zamanlayıcı, belirlenen zamanlama bağlamındaki veya iş için arama yaptığı başka bir yerde tamamlama listesini sorgulayabilir.|
|[IUMSScheduler Yapısı](iumsscheduler-structure.md)|Eşzamanlılık Çalışma Zamanı Kaynak Yöneticisi, Kullanıcı modu zamanlanabilen (UMS) iş parçacıklarını ele almak isteyen bir iş Zamanlayıcı soyutlaması için arabirim. Kaynak Yöneticisi, UMS iş parçacığı zamanlayıcılar ile iletişim kurmak için bu arabirimi kullanır. `IUMSScheduler` arabirimi `IScheduler` arabiriminden devralır.|
|[IUMSThreadProxy Yapısı](iumsthreadproxy-structure.md)|Yürütmenin iş parçacığı için bir soyutlama. Scheduler 'a Kullanıcı modu zamanlanabilen (UMS) iş parçacıkları verilmesini istiyorsanız Zamanlayıcı İlkesi öğesi `SchedulerKind` değerini `UmsThreadDefault`olarak ayarlayın ve `IUMSScheduler` arabirimini uygulayın. UMS iş parçacıkları yalnızca Windows 7 ve üzeri sürümü olan 64 bitlik işletim sistemlerinde desteklenir.|
|[IUMSUnblockNotification Yapısı](iumsunblocknotification-structure.md)|, Bir iş parçacığı proxy 'sinin, Scheduler 'ın belirlenen zamanlama bağlamına geri dönme ve tetiklediği Kaynak Yöneticisi bir bildirimi temsil eder ve zamanlanmaya hazırlanın. Bu arabirim, iş parçacığı proxy 'sinin ilişkili yürütme bağlamı `GetContext` yönteminden döndürülen bir kez yeniden zamanlanırsa geçersizdir.|
|[IVirtualProcessorRoot Yapısı](ivirtualprocessorroot-structure.md)|İş parçacığı proxy 'sinin yürütebileceği donanım iş parçacığı için bir soyutlama.|
|[scheduler_interface Yapısı](scheduler-interface-structure.md)|Zamanlayıcı arabirimi|
|[scheduler_ptr Yapısı (Eşzamanlılık Çalışma Zamanı)](scheduler-ptr-structure-concurrency-runtime.md)|Scheduler 'a yönelik bir işaretçi temsil eder. Bu sınıf, shared_ptr veya ham işaretçi kullanılarak yalnızca düz bir başvuru kullanılarak paylaşılan bir yaşam süresi belirtimine izin vermek için mevcuttur.|

### <a name="enumerations"></a>Listelemeler

|Name|Açıklama|
|----------|-----------------|
|[agent_status](concurrency-namespace-enums.md#agent_status)|`agent`için geçerli durumlar.|
|[Agents_EventType](concurrency-namespace-enums.md#agents_eventtype)|Aracılar Kitaplığı tarafından sunulan izleme işlevi kullanılarak izlenebilir olay türleri|
|[ConcRT_EventType](concurrency-namespace-enums.md#concrt_eventtype)|Eşzamanlılık Çalışma Zamanı tarafından sunulan izleme işlevi kullanılarak izlenebilir olay türleri.|
|[Concrt_TraceFlags](concurrency-namespace-enums.md#concrt_traceflags)|Olay türleri için izleme bayrakları|
|[CriticalRegionType](concurrency-namespace-enums.md#criticalregiontype)|Bağlam içindeki kritik bölge türü.|
|[DynamicProgressFeedbackType](concurrency-namespace-enums.md#dynamicprogressfeedbacktype)|Zamanlayıcı kaynaklarının, Scheduler 'dan toplanan istatistiksel bilgilere göre yeniden dengelenmesi veya yalnızca `IVirtualProcessorRoot` arabirimindeki `Activate` ve `Deactivate` yöntemlerine yapılan çağrılar aracılığıyla boşta durumuna geçme ve çıkış dışı olan sanal işlemcilere bağlı olup olmayacağını öğrenmek için `DynamicProgressFeedback` ilkesi tarafından kullanılır. Kullanılabilir Zamanlayıcı ilkeleri hakkında daha fazla bilgi için bkz. [PolicyElementKey](concurrency-namespace-enums.md#policyelementkey).|
|[join_type](concurrency-namespace-enums.md#join_type)|`join` mesajlaşma bloğunun türü.|
|[message_status](concurrency-namespace-enums.md#message_status)|Bir blok için `message` nesnesi teklifine yönelik geçerli yanıtlar.|
|[PolicyElementKey](concurrency-namespace-enums.md#policyelementkey)|Zamanlayıcı davranışının yönlerini açıklayan ilke anahtarları. Her ilke öğesi bir anahtar-değer çifti tarafından açıklanmıştır. Zamanlayıcı ilkeleri ve zamanlayıcılar üzerindeki etkileri hakkında daha fazla bilgi için bkz. [Görev Zamanlayıcı](../../../parallel/concrt/task-scheduler-concurrency-runtime.md).|
|[SchedulerType](concurrency-namespace-enums.md#schedulertype)|`SchedulerKind` ilkesi tarafından, Scheduler 'ın temel yürütme bağlamlarında kullanmasını gereken iş parçacıklarının türünü betimleyen tarafından kullanılır. Kullanılabilir Zamanlayıcı ilkeleri hakkında daha fazla bilgi için bkz. [PolicyElementKey](concurrency-namespace-enums.md#policyelementkey).|
|[SchedulingProtocolType](concurrency-namespace-enums.md#schedulingprotocoltype)|Zamanlayıcı için hangi zamanlama algoritmasının kullanılacağını açıklayan `SchedulingProtocol` ilkesi tarafından kullanılır. Kullanılabilir Zamanlayıcı ilkeleri hakkında daha fazla bilgi için bkz. [PolicyElementKey](concurrency-namespace-enums.md#policyelementkey).|
|[SwitchingProxyState](concurrency-namespace-enums.md#switchingproxystate)|Bir iş parçacığı proxy 'sinin içinde olduğu durumu belirtmek için kullanılır ve farklı bir iş parçacığı proxy 'sine bir işbirlikçi bağlamı anahtarı yürüttüyordur.|
|[task_group_status](concurrency-namespace-enums.md#task_group_status)|Bir `task_group` veya `structured_task_group` nesnesinin yürütme durumunu açıklar. Bu türden bir değer, bir görev grubuna zamanlanan görevlerin tamamlanmasını bekleyen çok sayıda yöntem tarafından döndürülür.|
|[WinRTInitializationType](concurrency-namespace-enums.md#winrtinitializationtype)|`WinRTInitialization` ilkesi tarafından, Windows 8 veya üzeri sürümü olan işletim sistemlerinde çalışan bir uygulama için zamanlayıcı iş parçacıklarında ve Windows Çalışma Zamanı nasıl başlatılabileceğini açıklayan bir ilke tarafından kullanılır. Kullanılabilir Zamanlayıcı ilkeleri hakkında daha fazla bilgi için bkz. [PolicyElementKey](concurrency-namespace-enums.md#policyelementkey).|

### <a name="functions"></a>İşlevler

|Name|Açıklama|
|----------|-----------------|
|[Ayırma Işlevi](concurrency-namespace-functions.md#alloc)|Eşzamanlılık Çalışma Zamanı önbelleğe alma alt ayırıcılarından belirtilen boyuttaki bellek bloğunu ayırır.|
|[asend Işlevi](concurrency-namespace-functions.md#asend)|Aşırı yüklendi. Verileri hedef bloğuna yaymaya yönelik bir görevi zamanlayan zaman uyumsuz gönderme işlemi.|
|[cancel_current_task Işlevi](concurrency-namespace-functions.md#cancel_current_task)|Yürütülmekte olan görevi iptal eder. Bu işlev, görevin yürütülmesini iptal etmek ve görevin `canceled` durumuna girmesine neden olmak için bir görev gövdesinin içinden çağrılabilir.<br /><br /> Bir `task`gövdesinde değilseniz bu işlevi çağırmak için desteklenen bir senaryo değildir. Bunun yapılması, uygulamanızda kilitlenme veya askıda kalma gibi tanımsız davranışlara neden olur.|
|[create_async Işlevi](concurrency-namespace-functions.md#create_async)|Kullanıcı tarafından sağlanan lambda veya işlev nesnesini temel alan Windows Çalışma Zamanı zaman uyumsuz yapı oluşturur. `create_async` dönüş türü, yönteme geçirilen lambda imzasına göre `IAsyncAction^`, `IAsyncActionWithProgress<TProgress>^`, `IAsyncOperation<TResult>^`veya `IAsyncOperationWithProgress<TResult, TProgress>^` biridir.|
|[create_task Işlevi](concurrency-namespace-functions.md#create_task)|Aşırı yüklendi. Bir PPL [görev](task-class.md) nesnesi oluşturur. `create_task`, görev oluşturucusunu kullandığınız her yerde kullanılabilir. Görevleri oluştururken `auto` anahtar sözcüğünün kullanılmasına izin verdiğinden, genellikle kolaylık sağlaması için sağlanır.|
|[CreateResourceManager Işlevi](concurrency-namespace-functions.md#createresourcemanager)|Eşzamanlılık Çalışma Zamanı Kaynak Yöneticisi tek örneğini temsil eden bir arabirim döndürür. Kaynak Yöneticisi, kaynakların birbirleriyle birlikte çalışmak isteyen zamanlayıcılar 'ye atanmasından sorumludur.|
|[DisableTracing Işlevi](concurrency-namespace-functions.md#disabletracing)|Eşzamanlılık Çalışma Zamanı izlemeyi devre dışı bırakır. ETW izlemenin varsayılan olarak kaydı silindiğinden bu işlev kullanım dışıdır.|
|[EnableTracing Işlevi](concurrency-namespace-functions.md#enabletracing)|Eşzamanlılık Çalışma Zamanı izlemeye izin vermez. ETW izleme artık varsayılan olarak açık olduğundan bu işlev kullanım dışıdır.|
|[Free Işlevi](concurrency-namespace-functions.md#free)|`Alloc` yöntemi tarafından daha önce ayrılmış bir bellek bloğunu Eşzamanlılık Çalışma Zamanı önbelleğe alma alt ayırıcıya yayınlar.|
|[get_ambient_scheduler Işlevi (Eşzamanlılık Çalışma Zamanı)](concurrency-namespace-functions.md#get_ambient_scheduler)||
|[GetExecutionContextId Function](concurrency-namespace-functions.md#getexecutioncontextid)|`IExecutionContext` arabirimini uygulayan bir yürütme bağlamına atanabileceği benzersiz bir tanımlayıcı döndürür.|
|[GetOSVersion Işlevi](concurrency-namespace-functions.md#getosversion)|İşletim sistemi sürümünü döndürür.|
|[GetProcessorCount Işlevi](concurrency-namespace-functions.md#getprocessorcount)|Temel sistemdeki donanım iş parçacıklarının sayısını döndürür.|
|[GetProcessorNodeCount Function](concurrency-namespace-functions.md#getprocessornodecount)|Temel sistemdeki NUMA düğümlerinin veya işlemci paketlerinin sayısını döndürür.|
|[GetSchedulerId Function](concurrency-namespace-functions.md#getschedulerid)|`IScheduler` arabirimini uygulayan bir Scheduler 'a atanabilen benzersiz bir tanımlayıcı döndürür.|
|[interruption_point Işlevi](concurrency-namespace-functions.md#interruption_point)|İptal için bir kesinti noktası oluşturur. Bu işlevin çağrıldığı bağlamda bir iptal işlemi devam ediyorsa, bu, şu anda yürütülen paralel çalışmanın yürütülmesini iptal eden bir iç özel durum oluşturur. İptal işlemi devam ediyorsa, işlev hiçbir şey yapmaz.|
|[is_current_task_group_canceling Function](concurrency-namespace-functions.md#is_current_task_group_canceling)|Geçerli bağlamda şu anda yürütülmekte olan görev grubunun etkin bir iptal etme (veya kısa bir süre) üzerinde olup olmadığına ilişkin bir gösterge döndürür. Şu anda geçerli bağlamda satır içinde yürütülmekte olan bir görev grubu yoksa `false` döndürüleceğini unutmayın.|
|[make_choice Işlevi](concurrency-namespace-functions.md#make_choice)|Aşırı yüklendi. İsteğe bağlı bir `Scheduler` veya `ScheduleGroup` ve iki veya daha fazla giriş kaynağından bir `choice` mesajlaşma bloğu oluşturur.|
|[make_greedy_join Function](concurrency-namespace-functions.md#make_greedy_join)|Aşırı yüklendi. İsteğe bağlı bir `Scheduler` veya `ScheduleGroup` ve iki veya daha fazla giriş kaynağından bir `greedy multitype_join` mesajlaşma bloğu oluşturur.|
|[make_join Işlevi](concurrency-namespace-functions.md#make_join)|Aşırı yüklendi. İsteğe bağlı bir `Scheduler` veya `ScheduleGroup` ve iki veya daha fazla giriş kaynağından bir `non_greedy multitype_join` mesajlaşma bloğu oluşturur.|
|[make_task Işlevi](concurrency-namespace-functions.md#make_task)|`task_handle` nesnesi oluşturmak için bir fabrika yöntemi.|
|[parallel_buffered_sort Işlevi](concurrency-namespace-functions.md#parallel_buffered_sort)|Aşırı yüklendi. Belirli bir aralıktaki öğeleri azalan düzene göre veya bir ikili koşul tarafından belirtilen bir sıralama ölçütüne göre paralel olarak düzenler. Bu işlev, `O(n)` ek alana ihtiyaç duyması ve sıralanan öğeler için varsayılan başlatma yapılması dışında, karşılaştırma tabanlı, kararsız, yerinde bir sıralama olduğundan `std::sort` anlam bakımından benzerdir.|
|[parallel_for Işlevi](concurrency-namespace-functions.md#parallel_for)|Aşırı yüklendi. `parallel_for`, bir dizi dizin üzerinde yinelenir ve paralel olarak her yinelemede Kullanıcı tarafından sağlanan bir işlevi yürütür.|
|[parallel_for_each Işlevi](concurrency-namespace-functions.md#parallel_for_each)|Aşırı yüklendi. `parallel_for_each`, bir aralıktaki her öğeye paralel olarak belirtilen bir işlevi uygular. Öğelerin üzerinde yineleme paralel olarak gerçekleştirilmesinin ve yinelemenin sırası belirtilmemesi dışında, `std` ad alanındaki `for_each` işlevine anlamsal olarak eşdeğerdir. `_Func` bağımsız değişkeni, `T` parametresinin, üzerinde yinelemekte olan kapsayıcının öğe türü olduğu `operator()(T)` formun bir işlev çağrısı işlecini desteklemesi gerekir.|
|[parallel_invoke Işlevi](concurrency-namespace-functions.md#parallel_invoke)|Aşırı yüklendi. Parametre olarak sağlanan işlev nesnelerini paralel olarak yürütür ve yürütmeyi tamamlayana kadar blokları engeller. Her işlev nesnesi bir lambda ifadesi, işlev işaretçisi veya imza `void operator()()`işlev çağrısı işlecini destekleyen herhangi bir nesne olabilir.|
|[parallel_radixsort Işlevi](concurrency-namespace-functions.md#parallel_radixsort)|Aşırı yüklendi. Belirli bir aralıktaki öğeleri, bir taban x sıralama algoritmasını kullanarak azalan düzende düzenler. Bu bir yansıtma işlevi gerektiren bir kararlı sıralama işlevidir. Bu, öğeleri işaretsiz tamsayı benzeri anahtarlar halinde sıralamak için proje öğeleri olabilir. Sıralanan öğeler için varsayılan başlatma gereklidir.|
|[parallel_reduce Işlevi](concurrency-namespace-functions.md#parallel_reduce)|Aşırı yüklendi. Ardışık kısmi toplamları hesaplayarak, belirtilen aralıktaki tüm öğelerin toplamını hesaplar veya paralel olan belirli bir ikili işlemi kullanmaktan farklı şekilde elde edilen kısmi sonuçların sonucunu hesaplar. `parallel_reduce`, ikili işlemin ilişkilendirilebilir olmasını gerektirdiğinden ve ilk değer yerine bir kimlik değeri gerektirdiğinden `std::accumulate`anlam açısından benzerdir.|
|[parallel_sort Işlevi](concurrency-namespace-functions.md#parallel_sort)|Aşırı yüklendi. Belirli bir aralıktaki öğeleri azalan düzene göre veya bir ikili koşul tarafından belirtilen bir sıralama ölçütüne göre paralel olarak düzenler. Bu işlev, karşılaştırma tabanlı, kararsız ve yerinde bir sıralama olduğundan `std::sort` anlam bakımından benzerdir.|
|[parallel_transform Işlevi](concurrency-namespace-functions.md#parallel_transform)|Aşırı yüklendi. Kaynak aralıktaki her öğeye veya iki kaynak aralığından bir öğe çiftine belirtilen bir işlev nesnesi uygular ve işlev nesnesinin dönüş değerlerini paralel olarak bir hedef aralığa kopyalar. Bu işlev, `std::transform`anlam olarak eşdeğerdir.|
|[Receive Işlevi](concurrency-namespace-functions.md#receive)|Aşırı yüklendi. Bir bağlamın tam olarak bir kaynaktan veri beklemesi ve kabul edilen değerleri filtrelemesine olanak tanımak için genel bir alma uygulamasıdır.|
|[run_with_cancellation_token Function](concurrency-namespace-functions.md#run_with_cancellation_token)|Bir işlev nesnesini, belirli bir iptal belirtecinin bağlamında hemen ve zaman uyumlu olarak yürütür.|
|[Send Işlevi](concurrency-namespace-functions.md#send)|Aşırı yüklendi. Hedefin iletiyi kabul etmesini veya reddetmesini bekleyen zaman uyumlu gönderme işlemi.|
|[set_ambient_scheduler Işlevi (Eşzamanlılık Çalışma Zamanı)](concurrency-namespace-functions.md#set_ambient_scheduler)||
|[set_task_execution_resources Function](concurrency-namespace-functions.md#set_task_execution_resources)|Aşırı yüklendi. Eşzamanlılık Çalışma Zamanı iç çalışan iş parçacıkları tarafından kullanılan yürütme kaynaklarını belirtilen benzeşim kümesine kısıtlar.<br /><br /> Bu yöntemi yalnızca Kaynak Yöneticisi oluşturulmadan veya iki Kaynak Yöneticisi yaşam süresi arasında çağırmak için geçerlidir. Kaynak Yöneticisi, çağırma sırasında mevcut olmadığı sürece birden çok kez çağrılabilir. Benzeşim sınırı ayarlandıktan sonra, `set_task_execution_resources` yöntemine bir sonraki geçerli çağrıya kadar yürürlükte kalır.<br /><br /> Belirtilen benzeşim maskesi, işlem benzeşimi maskesinin bir alt kümesi olmamalıdır. İşlem benzeşimi gerekirse güncelleştirilir.|
|[Swap Işlevi](concurrency-namespace-functions.md#swap)|İki `concurrent_vector` nesnesinin öğelerini değiş tokuş eder.|
|[task_from_exception Işlevi (Eşzamanlılık Çalışma Zamanı)](concurrency-namespace-functions.md#task_from_exception)||
|[task_from_result Işlevi (Eşzamanlılık Çalışma Zamanı)](concurrency-namespace-functions.md#task_from_result)||
|[Trace_agents_register_name Işlevi](concurrency-namespace-functions.md#trace_agents_register_name)|Verilen adı ETW izlemesinde bulunan ileti bloğuna veya aracıya ilişkilendirir.|
|[try_receive Işlevi](concurrency-namespace-functions.md#try_receive)|Aşırı yüklendi. Bir bağlamın tam olarak bir kaynaktan verileri arayacağı ve kabul edilen değerleri filtrelemesine izin veren genel bir TRY-Receive uygulamasıdır. Veriler hazırsanız, yöntem false döndürür.|
|[wait Işlevi](concurrency-namespace-functions.md#wait)|Belirtilen süre boyunca geçerli bağlamı duraklatır.|
|[when_all Işlevi](concurrency-namespace-functions.md#when_all)|Bağımsız değişken olarak sağlanan tüm görevler başarıyla tamamlandığında başarıyla tamamlanacak bir görev oluşturur.|
|[when_any Işlevi](concurrency-namespace-functions.md#when_any)|Aşırı yüklendi. Bağımsız değişken olarak sağlanan görevlerden herhangi biri başarıyla tamamlandığında başarıyla tamamlanacak bir görev oluşturur.|

### <a name="operators"></a>İşleçler

|Name|Açıklama|
|----------|-----------------|
|[operator!=](concurrency-namespace-operators.md#operator_neq)|İşlecin sol tarafındaki `concurrent_vector` nesnesinin sağ taraftaki `concurrent_vector` nesnesine eşit olup olmadığını sınar.|
|[işleç & &](concurrency-namespace-operators.md#operator_amp_amp)|Aşırı yüklendi. Bağımsız değişken olarak sağlanan görevlerin her ikisi de başarıyla tamamlandığında başarıyla tamamlanacak bir görev oluşturur.|
|[operator&#124;&#124;](concurrency-namespace-operators.md#operator_lor)|Aşırı yüklendi. Bağımsız değişken olarak sağlanan görevlerden biri başarıyla tamamlandığında başarıyla tamamlanacak bir görev oluşturur.|
|[işleç <](concurrency-namespace-operators.md#operator_lt)|İşlecin sol tarafındaki `concurrent_vector` nesnesinin sağ taraftaki `concurrent_vector` nesnesinden küçük olup olmadığını sınar.|
|[işleç < =](concurrency-namespace-operators.md#operator_lt_eq)|İşlecin sol tarafındaki `concurrent_vector` nesnesinin sağ taraftaki `concurrent_vector` nesnesinden küçük veya ona eşit olup olmadığını sınar.|
|[operator==](concurrency-namespace-operators.md#operator_eq_eq)|İşlecin sol tarafındaki `concurrent_vector` nesnesinin sağ taraftaki `concurrent_vector` nesnesine eşit olup olmadığını sınar.|
|[işleç >](concurrency-namespace-operators.md#operator_gt)|İşlecin sol tarafındaki `concurrent_vector` nesnesinin sağ taraftaki `concurrent_vector` nesnesinden büyük olup olmadığını sınar.|
|[operator>=](concurrency-namespace-operators.md#operator_lt_eq)|İşlecin sol tarafındaki `concurrent_vector` nesnesinin sağ taraftaki `concurrent_vector` nesnesinden büyük veya ona eşit olup olmadığını sınar.|

### <a name="constants"></a>{1&gt;Sabitler&lt;1}

|Name|Açıklama|
|----------|-----------------|
|[AgentEventGuid](concurrency-namespace-constants1.md#agenteventguid)|Eşzamanlılık Çalışma Zamanı aracılar Kitaplığı tarafından tetiklenen ETW olaylarını açıklayan kategori GUID 'SI ({B9B5B78C-0713-4898-A21A-C67949DCED07}).|
|[ChoreEventGuid](concurrency-namespace-constants1.md#choreeventguid)|Doğrudan işlerini unutun veya görevlerle ilgili eşzamanlılık çalışma zamanı tarafından tetiklenen ETW olaylarını açıklayan kategori GUID 'si.|
|[ConcRT_ProviderGuid](concurrency-namespace-constants1.md#concrt_providerguid)|Eşzamanlılık Çalışma Zamanı için ETW sağlayıcısı GUID 'ı.|
|[CONCRT_RM_VERSION_1](concurrency-namespace-constants1.md#concrt_rm_version_1)|Visual Studio 2010 ' de tanımlanan Kaynak Yöneticisi arabiriminin desteğini gösterir.|
|[ConcRTEventGuid](concurrency-namespace-constants1.md#concrteventguid)|Başka bir kategori tarafından daha önce açıklanmayan Eşzamanlılık Çalışma Zamanı tarafından tetiklenen ETW olaylarını açıklayan kategori GUID 'SI.|
|[ContextEventGuid](concurrency-namespace-constants1.md#contexteventguid)|Bağlamlarla doğrudan ilgili olan Eşzamanlılık Çalışma Zamanı tarafından tetiklenen ETW olaylarını açıklayan kategori GUID 'SI.|
|[COOPERATIVE_TIMEOUT_INFINITE](concurrency-namespace-constants1.md#cooperative_timeout_infinite)|Bir bekleme süresinin asla zaman aşımına uğramayacağını gösteren değer.|
|[COOPERATIVE_WAIT_TIMEOUT](concurrency-namespace-constants1.md#cooperative_wait_timeout)|Bekleme süresinin zaman aşımına uğradığını belirten değer.|
|[INHERIT_THREAD_PRIORITY](concurrency-namespace-constants1.md#inherit_thread_priority)|İlke anahtarı için özel değer `ContextPriority` Scheduler 'daki tüm bağlamların iş parçacığı önceliğinin, Scheduler 'ı oluşturan iş parçacığıyla aynı olması gerektiğini belirtir.|
|[LockEventGuid](concurrency-namespace-constants1.md#lockeventguid)|Doğrudan kilitlerle ilgili Eşzamanlılık Çalışma Zamanı tarafından tetiklenen ETW olaylarını açıklayan kategori GUID 'SI.|
|[MaxExecutionResources](concurrency-namespace-constants1.md#maxexecutionresources)|`MinConcurrency` ve `MaxConcurrency`ilke anahtarları için özel değer. Diğer kısıtlamalar yokluğunda makinedeki donanım iş parçacığı sayısı varsayılan olarak belirlenmiştir.|
|[PPLParallelForeachEventGuid](concurrency-namespace-constants1.md#pplparallelforeacheventguid)|`parallel_for_each` işlevinin kullanımıyla doğrudan ilgili Eşzamanlılık Çalışma Zamanı tarafından tetiklenen ETW olaylarını açıklayan kategori GUID 'SI.|
|[PPLParallelForEventGuid](concurrency-namespace-constants1.md#pplparallelforeventguid)|`parallel_for` işlevinin kullanımıyla doğrudan ilgili Eşzamanlılık Çalışma Zamanı tarafından tetiklenen ETW olaylarını açıklayan kategori GUID 'SI.|
|[PPLParallelInvokeEventGuid](concurrency-namespace-constants1.md#pplparallelinvokeeventguid)|`parallel_invoke` işlevinin kullanımıyla doğrudan ilgili Eşzamanlılık Çalışma Zamanı tarafından tetiklenen ETW olaylarını açıklayan kategori GUID 'SI.|
|[ResourceManagerEventGuid](concurrency-namespace-constants1.md#resourcemanagereventguid)|Doğrudan Resource Manager ile ilgili olan Eşzamanlılık Çalışma Zamanı tarafından tetiklenen ETW olaylarını açıklayan kategori GUID 'SI.|
|[ScheduleGroupEventGuid](concurrency-namespace-constants1.md#schedulegroupeventguid)|Zamanlama gruplarıyla doğrudan ilgili Eşzamanlılık Çalışma Zamanı tarafından tetiklenen ETW olaylarını açıklayan kategori GUID 'SI.|
|[SchedulerEventGuid](concurrency-namespace-constants1.md#schedulereventguid)|Zamanlayıcı etkinliğiyle doğrudan ilgili Eşzamanlılık Çalışma Zamanı tarafından tetiklenen ETW olaylarını açıklayan kategori GUID 'SI.|
|[VirtualProcessorEventGuid](concurrency-namespace-constants1.md#virtualprocessoreventguid)|Sanal işlemcilerle doğrudan ilgili Eşzamanlılık Çalışma Zamanı tarafından tetiklenen ETW olaylarını açıklayan kategori GUID 'SI.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** Agents. h, concrt. h, concrtrm. h, concurrent_priority_queue. h, concurrent_queue. h, concurrent_unordered_map. h, concurrent_unordered_set. h, concurrent_vector. h, internal_concurrent_hash. h, internal_split_ordered_list. h, PPL. h, pplcancellation_token. h, pplconcrt. h, pplınterface. h, ppltasks. h

## <a name="see-also"></a>Ayrıca bkz.

[Başvuru](reference-concurrency-runtime.md)
