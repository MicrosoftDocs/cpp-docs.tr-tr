---
title: Eşzamanlılık Namespace | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- Concurrency namespace
ms.assetid: f1d33ca2-679b-4442-b140-22a9d9df61d1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 324acb33998246933b0c426357368247c6689c47
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43211323"
---
# <a name="concurrency-namespace"></a>concurrency Ad Alanı
`Concurrency` Size işlevleri erişmek için eşzamanlılık çalışma zamanı C++ için eşzamanlı programlama çerçevesi ve ad alanı sınıflar sağlar. Daha fazla bilgi için [eşzamanlılık çalışma zamanı](../../../parallel/concrt/concurrency-runtime.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
namespace concurrency;  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="namespaces"></a>Ad Alanları  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CONCURRENCY::Extensibility Namespace](https://msdn.microsoft.com/16a86ff2-128e-4edf-89e4-38aac79c81f9)||  
  
### <a name="typedefs"></a>Tür tanımları  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`runtime_object_identity`|Her bir ileti örneği kopyalanmış ve mesajlaşma bileşenleri arasında geçirilen, kendisini izleyen bir kimliğe sahiptir. Bu ileti nesnenin adresi olamaz.|  
|`task_status`|Bir görevin terminal durumunu temsil eden tür. Geçerli değerler `completed` ve `canceled`.|  
|`TaskProc`|Basit bir Özet olarak tanımlanmış bir görev için `void (__cdecl * TaskProc)(void *)`. A `TaskProc` gövdesi bir görev çağırmak için çağrılır.|  
|`TaskProc_t`|Basit bir Özet olarak tanımlanmış bir görev için `void (__cdecl * TaskProc_t)(void *)`. A `TaskProc` gövdesi bir görev çağırmak için çağrılır.|  
  
### <a name="classes"></a>Sınıflar  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[affinity_partitioner Sınıfı](affinity-partitioner-class.md)|`affinity_partitioner` Sınıfı benzer `static_partitioner` sınıfı, ancak alt aralıklara çalışan iş parçacıkları için eşleme dilediği tarafından önbellek benzeşim artırır. Bir döngü, aynı veri kümesi üzerinde yeniden çalıştırılır ve veri önbellekte en uygun, performansı önemli ölçüde artırabilir. Unutmayın aynı `affinity_partitioner` nesnesi, bir özel veri yerel veri konumu yararlanmak için küme üzerinde çalıştırılan paralel bir döngüden sonraki yinelemeleri ile kullanılmalıdır.|  
|[agent Sınıfı](agent-class.md)|Tüm bağımsız aracıları için temel sınıf olarak kullanılacak bir sınıf yöneliktir. Bu durum diğer aracılardan Gizle ve ileti geçirme kullanarak etkileşim kurmak için kullanılır.|  
|[auto_partitioner Sınıfı](auto-partitioner-class.md)|`auto_partitioner` Sınıfı temsil eder, varsayılan yöntemi `parallel_for`, `parallel_for_each` ve `parallel_transform` yinelenir üzerinden aralık bölümleme için kullanın. Employes bölümleme bu yöntemi Yük Dengeleme için çalma aralığı yanı sıra başına-iptal yineleyin.|  
|[bad_target Sınıfı](bad-target-class.md)|Bu sınıf, bir özel durum gerçekleştirilmekte olan işlem için geçersiz bir hedefe bir ileti bloğu bir işaretçi verildiğinde, durum açıklar.|  
|[call Sınıfı](call-class.md)|A `call` ileti bloğu, bir çok kaynak sıralı `target_block` , çağıran belirtilen işlev bir ileti alındığında.|  
|[cancellation_token Sınıfı](cancellation-token-class.md)|`cancellation_token` Sınıfı, bazı işlemlerin iptal istendi olup olmadığını belirleme yeteneğini temsil eder. Verilen bir belirteç ile ilişkilendirilmiş bir `task_group`, `structured_task_group`, veya `task` örtük iptal sağlamak için. Ayrıca iptal için yoklanabilir veya bir geri çağırma için kayıtlı olan ilişkili `cancellation_token_source` iptal edilir.|  
|[cancellation_token_registration Sınıfı](cancellation-token-registration-class.md)|`cancellation_token_registration` Sınıfı temsil eden bir geri çağırma bildiriminden bir `cancellation_token`. Zaman `register` metodunda bir `cancellation_token` gerçekleşen iptal bildirimi almak için kullanılan bir `cancellation_token_registration` çağıran özel bir geri çağırma artık isteyebilmesi için geri çağırma tanıtıcı kullanarakyapılmasıgibinesnedöndürülür`deregister` yöntemi.|  
|[cancellation_token_source Sınıfı](cancellation-token-source-class.md)|`cancellation_token_source` Sınıfı, iptal edilebilir bazı işlemleri iptal etme yeteneğini temsil eder.|  
|[choice Sınıfı](choice-class.md)|A `choice` ileti bloğu bir kaynak kümesi denetim akışı etkileşim temsil eden çok kaynak, hedef tek bir blok. Seçim bloğu bir iletisi oluşturmak üzere birden çok kaynaktan herhangi biri için bekleyeceği ve ileti üretilen kaynak dizinini yayılır.|  
|[combinable Sınıfı](combinable-class.md)|`combinable<T>` Nesne sırasında paralel algoritmalar kilidi serbest iş parçacığı-yerel alt hesaplamalar gerçekleştirmek için veri, iş parçacığı özel kopyalarını sağlamak için tasarlanmıştır. Paralel işlemin sonunda, iş parçacığı özel alt hesaplamalar sonra bir nihai sonucu birleştirilebilir. Bu sınıf, paylaşılan bir değişken yerine kullanılabilir ve aksi durumda olacaktır, paylaşılan bir değişken üzerinde Çekişme birçok performans geliştirmeyle neden olabilir.|  
|[concurrent_priority_queue Sınıfı](concurrent-priority-queue-class.md)|`concurrent_priority_queue` Sınıfı, birden çok iş parçacığı aynı anda anında iletme ve açılır öğelere izin veren bir kapsayıcıdır. Öğeleri, öncelik sırasına göre öncelik bir şablon bağımsız değişken olarak sağlanan bir functor tarafından belirlendiği POP.|  
|[concurrent_queue Sınıfı](concurrent-queue-class.md)|`concurrent_queue` Sınıfı, bir ilk sağlayan dizisi kapsayıcı sınıfı, ilk çıkar erişim öğeleri. Eşzamanlılık açısından güvenli işlemler, sınırlı sayıda gibi sağlayan `push` ve `try_pop`.|  
|[concurrent_unordered_map Sınıfı](concurrent-unordered-map-class.md)|`concurrent_unordered_map` Sınıfı, bir türdeki öğelerin değişen uzunluktaki dizisini denetleyen eşzamanlılığı güvenli bir kapsayıcıdır `std::pair<const K, _Element_type>`. Sıra, eşzamanlılık açısından güvenli sağlayan bir şekilde temsil edilir sona ekleme, öğe erişimi, yineleyici erişimi ve yineleyici çapraz geçiş işlemleri.|  
|[concurrent_unordered_multimap Sınıfı](concurrent-unordered-multimap-class.md)|`concurrent_unordered_multimap` Sınıfı, bir türdeki öğelerin değişen uzunluktaki dizisini denetleyen eşzamanlılığı güvenli bir kapsayıcıdır `std::pair<const K, _Element_type>`. Sıra, eşzamanlılık açısından güvenli sağlayan bir şekilde temsil edilir sona ekleme, öğe erişimi, yineleyici erişimi ve yineleyici çapraz geçiş işlemleri.|  
|[concurrent_unordered_multiset Sınıfı](concurrent-unordered-multiset-class.md)|`concurrent_unordered_multiset` Sınıfı, bir K. türdeki öğelerin değişen uzunluktaki dizisini denetleyen eşzamanlılığı güvenli bir kapsayıcıdır Sıra, eşzamanlılık açısından güvenli sağlayan bir şekilde temsil edilir sona ekleme, öğe erişimi, yineleyici erişimi ve yineleyici çapraz geçiş işlemleri.|  
|[concurrent_unordered_set Sınıfı](concurrent-unordered-set-class.md)|`concurrent_unordered_set` Sınıfı, bir K. türdeki öğelerin değişen uzunluktaki dizisini denetleyen eşzamanlılığı güvenli bir kapsayıcıdır Sıra, eşzamanlılık açısından güvenli sağlayan bir şekilde temsil edilir sona ekleme, öğe erişimi, yineleyici erişimi ve yineleyici çapraz geçiş işlemleri.|  
|[concurrent_vector Sınıfı](concurrent-vector-class.md)|`concurrent_vector` Herhangi bir öğeye rastgele erişim sağlayan bir sıralı kapsayıcı sınıfı. Bağlayabileceğinizi eşzamanlılık açısından güvenli sona ekleme, öğe erişimi, yineleyici erişimi ve yineleyici çapraz geçiş işlemleri.|  
|[Bağlam Sınıfı](context-class.md)|Bir yürütme bağlamı için bir soyutlamayı temsil eder.|  
|[context_self_unblock Sınıfı](context-self-unblock-class.md)|Bu sınıf oluşan bir özel durumu anlatmaktadır `Unblock` yöntemi bir `Context` nesnesi aynı bağlamdan çağrılır. Bu tarafından belirtilen bir bağlamda kendisini engelini kaldırmak için girişiminde bulunulduğunu.|  
|[context_unblock_unbalanced Sınıfı](context-unblock-unbalanced-class.md)|Bu sınıf oluşan bir özel durumu anlatmaktadır çağrılar `Block` ve `Unblock` yöntemlerinin bir `Context` nesne değil düzgün halindedir.|  
|[critical_section Sınıfı](critical-section-class.md)|Eşzamanlılık çalışma zamanının açıkça farkında olan reentrant olmayan mutex.|  
|[CurrentScheduler Sınıfı](currentscheduler-class.md)|Arama bağlamı ile ilişkili geçerli Zamanlayıcı için bir soyutlamayı temsil eder.|  
|[default_scheduler_exists Sınıfı](default-scheduler-exists-class.md)|Bu sınıf oluşan bir özel durumu anlatmaktadır `Scheduler::SetDefaultSchedulerPolicy` varsayılan Zamanlayıcı işlem içinde zaten mevcut olduğunda yöntemi çağrılır.|  
|[event Sınıfı](event-class.md)|Eşzamanlılık çalışma zamanının açıkça farkında olan el ile sıfırlama olayı.|  
|[improper_lock Sınıfı](improper-lock-class.md)|Bu sınıf, bir kilit alınmadığı yanlış olduğunda oluşturulan bir özel durum açıklar.|  
|[improper_scheduler_attach Sınıfı](improper-scheduler-attach-class.md)|Bu sınıf oluşan bir özel durumu anlatmaktadır `Attach` yöntemi çağrıldığında bir `Scheduler` geçerli bağlama zaten iliştirilmiş nesnesidir.|  
|[improper_scheduler_detach Sınıfı](improper-scheduler-detach-class.md)|Bu sınıf oluşan bir özel durumu anlatmaktadır `CurrentScheduler::Detach` yöntemi kullanarak herhangi bir zamanlayıcı için bağlı olmayan bir bağlamı çağrıldığında `Attach` yöntemi bir `Scheduler` nesne.|  
|[improper_scheduler_reference Sınıfı](improper-scheduler-reference-class.md)|Bu sınıf oluşan bir özel durumu anlatmaktadır `Reference` yöntemi çağrıldığında bir `Scheduler` aşağı, bu Zamanlayıcı bir parçası olmayan bir bağlamdan kapatılıyor nesne.|  
|[invalid_link_target Sınıfı](invalid-link-target-class.md)|Bu sınıf oluşan bir özel durumu anlatmaktadır `link_target` ileti bloğunun yöntemi çağrılır ve ileti bloğu Hedefe bağlanamıyor. Bu ileti bloğu izin verilen bağlantı sayısını aşan veya iki kez aynı kaynak için belirli bir hedef bağlantı girişimi sonucu olabilir.|  
|[invalid_multiple_scheduling Sınıfı](invalid-multiple-scheduling-class.md)|Bu sınıf oluşan bir özel durumu anlatmaktadır bir `task_handle` nesnedir kullanarak süreleri zamanlanmış birden çok `run` yöntemi bir `task_group` veya `structured_task_group` nesnesi olmadan bir çağrı göndermelisiniz `wait` veya `run_and_wait` yöntemleri.|  
|[invalid_operation Sınıfı](invalid-operation-class.md)|Bu sınıf, daha doğru bir şekilde eşzamanlılık çalışma zamanı tarafından oluşturulan başka bir özel durum türü tarafından açıklanmayan geçersiz bir işlem gerçekleştirildiğinde verilen bir özel durumu anlatmaktadır.|  
|[invalid_oversubscribe_operation Sınıfı](invalid-oversubscribe-operation-class.md)|Bu sınıf oluşan bir özel durumu anlatmaktadır `Context::Oversubscribe` yöntemi çağrıldığında `_BeginOversubscription` parametresini `false` çağrıda olmadan `Context::Oversubscribe` yöntemiyle `_BeginOversubscription` parametresini `true`.|  
|[invalid_scheduler_policy_key Sınıfı](invalid-scheduler-policy-key-class.md)|Bu sınıf geçersiz olduğunda oluşturulan bir özel durumu açıklayan veya bilinmeyen anahtarı geçirildiğinde bir `SchedulerPolicy` nesne Oluşturucu, veya `SetPolicyValue` yöntemi bir `SchedulerPolicy` nesnesi gibi diğer araçları kullanarak değiştirmesi gereken bir anahtarı geçirildi `SetConcurrencyLimits` yöntemi.|  
|[invalid_scheduler_policy_thread_specification Sınıfı](invalid-scheduler-policy-thread-specification-class.md)|Bu sınıf, eşzamanlılık sınırlarını ayarlamak için bir girişimde olduğunda oluşturulan bir özel durum açıklar bir `SchedulerPolicy` nesne gibi değerini `MinConcurrency` anahtar değerini azdır `MaxConcurrency` anahtarı.|  
|[invalid_scheduler_policy_value Sınıfı](invalid-scheduler-policy-value-class.md)|Bu sınıf bir ilke anahtarı olduğunda oluşturulan bir özel durumu anlatmaktadır bir `SchedulerPolicy` nesne bu anahtar için geçersiz bir değere ayarlanır.|  
|[ISource Sınıfı](isource-class.md)|`ISource` Tüm kaynak bloklar için sınıf, arabirim. Kaynak bloklar yayma iletileri `ITarget` engeller.|  
|[ITarget Sınıfı](itarget-class.md)|`ITarget` Tüm hedef blokları için sınıf, arabirim. Hedef blokları tarafından kendilerine sunulan iletileri kullanma `ISource` engeller.|  
|[join Sınıfı](join-class.md)|A `join` ileti bloğu tek-hedef birden çok kaynak, sıralı `propagator_block` bir araya getiren birlikte türden iletileri `T` her kaynakları.|  
|[location Sınıfı](location-class.md)|Fiziksel bir donanım konumunda bir soyutlamasıdır.|  
|[message Sınıfı](message-class.md)|İleti blokları arasında geçirilen veri yükü içeren temel ileti zarfı.|  
|[message_not_found Sınıfı](message-not-found-class.md)|Bu sınıf, bir ileti bloğu bulamıyor istenen bir ileti olduğunda oluşturulan bir özel açıklar.|  
|[message_processor Sınıfı](message-processor-class.md)|`message_processor` İşlenmesi için soyut temel sınıfı `message` nesneleri. İletilerin sıralama hakkında bir garanti yoktur.|  
|[missing_wait Sınıfı](missing-wait-class.md)|Bu sınıf için yine de zamanlanmış görevler olduğunda oluşturulan bir özel açıklayan bir `task_group` veya `structured_task_group` sırada bu nesnenin nesne yok Edicisi yürütür. Bu özel durumun hiçbir zaman yok edici bir özel durum sonucu olarak geriye doğru izleme yığın nedeniyle ulaşılırsa oluşturulur.|  
|[multi_link_registry Sınıfı](multi-link-registry-class.md)|`multi_link_registry` Nesnesi bir `network_link_registry` birden çok kaynak bloklar veya birden çok hedef bloğa yönetir.|  
|[multitype_join Sınıfı](multitype-join-class.md)|A `multitype_join` ileti bloğu her kaynaklarının farklı türdeki iletileri birleştirir ve hedeflerine birleşik iletileri tanımlama grubu sunar bir çok kaynak, hedef tek ileti bloğu.|  
|[nested_scheduler_missing_detach Sınıfı](nested-scheduler-missing-detach-class.md)|Bu sınıf, eşzamanlılık çalışma zamanı çağırmaya ihmal algıladığında oluşturulan bir özel tanımlar `CurrentScheduler::Detach` yöntemi kullanarak ikinci bir zamanlayıcı bağlı bir bağlam `Attach` yöntemi `Scheduler` nesne.|  
|[network_link_registry Sınıfı](network-link-registry-class.md)|`network_link_registry` Soyut temel sınıf kaynak ve hedef bloklar arasındaki bağlantıları yönetir.|  
|[operation_timed_out Sınıfı](operation-timed-out-class.md)|Bu sınıf, bir işlem zaman aşımına uğradığında oluşturulan bir özel açıklar.|  
|[ordered_message_processor Sınıfı](ordered-message-processor-class.md)|Bir `ordered_message_processor` olduğu bir `message_processor` sırada alınan iletileri işleyecek şekilde ileti blokları sağlar.|  
|[overwrite_buffer Sınıfı](overwrite-buffer-class.md)|Bir `overwrite_buffer` ileti bloğu birden çok hedef birden çok kaynak, sıralı `propagator_block` özellikli bir kerede tek bir ileti depolama. Yeni iletileri, daha önce tutulan olanları üzerine yazın.|  
|[progress_reporter Sınıfı](progress-reporter-class.md)|İlerleme Raporlayıcısı belirli bir türdeki ilerleme bildirimlerinin raporlama sağlar. Her progress_reporter nesnesi, bir belirli bir zaman uyumsuz eyleme veya işleme bağlıdır.|  
|[propagator_block Sınıfı](propagator-block-class.md)|`propagator_block` Sınıfı, hem kaynak hem de hedef ileti blokları için Özet temel sınıf. Her ikisi de işlevlerini birleştiren `source_block` ve `target_block` sınıfları.|  
|[reader_writer_lock Sınıfı](reader-writer-lock-class.md)|Dönen yalnızca yerel yazıcı tercih kuyruk tabanlı Okuyucu-Yazıcı kilidi. Kilit ilk yazıcılarının - ilk (FIFO) erişimi verir ve yazıcılar sürekli bir yük altında okuyucular starves.|  
|[ScheduleGroup Sınıfı](schedulegroup-class.md)|Bir zamanlama grubu için bir soyutlamayı temsil eder. Zamanlama grupları zamansal olarak, başka bir gruba geçmeden önce aynı grupta başka bir görev yürütülürken veya mekan, aynı birden çok öğe aynı grupta yürüterek birbirine yakın zamanlanmasını gelen faydalanan bir dizi ilgili iş düzenleme NUMA düğümünde veya fiziksel yuvadaki.|  
|[Zamanlayıcı Sınıfı](scheduler-class.md)|Bir Özet için eşzamanlılık çalışma zamanı Zamanlayıcı temsil eder.|  
|[scheduler_not_attached Sınıfı](scheduler-not-attached-class.md)|Bu sınıf, bir işlem için geçerli bağlam eklenmesi bir zamanlayıcı gerektiren gerçekleştirilir ve bulunmaması olduğunda oluşturulan bir özel durum açıklar.|  
|[scheduler_resource_allocation_error Sınıfı](scheduler-resource-allocation-error-class.md)|Bu sınıf, eşzamanlılık çalışma zamanı içinde kritik bir kaynak almak için bir hata nedeniyle verilen bir özel durumu anlatmaktadır.|  
|[scheduler_worker_creation_error Sınıfı](scheduler-worker-creation-error-class.md)|Bu sınıf, eşzamanlılık çalışma zamanı içinde çalışan yürütme bağlamı oluşturmak için bir hata nedeniyle verilen bir özel durumu anlatmaktadır.|  
|[SchedulerPolicy Sınıfı](schedulerpolicy-class.md)|`SchedulerPolicy` Sınıfı içeren bir zamanlayıcı örneğini davranışını denetleyen anahtar/değer çiftleri, her ilke öğesi için bir dizi.|  
|[simple_partitioner Sınıfı](simple-partitioner-class.md)|`simple_partitioner` Sınıfı temsil eder bir statik tarafından üzerinden yinelenir aralık bölümleme `parallel_for`. Her öbek öbek boyutu tarafından belirtilen yineleme sayısını en az sahip olacak şekilde bölümleyici aralığı öbeklere böler.|  
|[single_assignment Sınıfı](single-assignment-class.md)|A `single_assignment` ileti bloğu birden çok hedef birden çok kaynak, sıralı `propagator_block` özelliğine sahip tek bir depolama yazma-sonra `message`.|  
|[single_link_registry Sınıfı](single-link-registry-class.md)|`single_link_registry` Nesnesi bir `network_link_registry` , yalnızca tek bir kaynak veya hedef blok yönetir.|  
|[source_block Sınıfı](source-block-class.md)|`source_block` Sınıfı, yalnızca kaynak bloklar için Özet temel sınıf. Sınıfı, düzgün olarak sık karşılaşılan hata denetimleri temel bağlantı yönetimi işlevselliği sağlar.|  
|[source_link_manager Sınıfı](source-link-manager-class.md)|`source_link_manager` Nesnesi ileti bloğu ağ bağlantıları yönetir `ISource` engeller.|  
|[static_partitioner Sınıfı](static-partitioner-class.md)|`static_partitioner` Sınıfı temsil eder bir statik tarafından üzerinden yinelenir aralık bölümleme `parallel_for`. Bölümleyici aralığı çalışanları underyling Zamanlayıcı kullanılabilir olduğu kadar çok öbeklere böler.|  
|[structured_task_group Sınıfı](structured-task-group-class.md)|`structured_task_group` Sınıfı, yüksek düzeyde yapılandırılmış bir paralel iş koleksiyonunu temsil eder. Tek tek Paralel Görevler sıraya alabilirsiniz bir `structured_task_group` kullanarak `task_handle` yürütme başlamadığınız herhangi bir görevi iptal edilecek yürütme bitirmeden önce görev grubunu iptal nesneleri veya tamamlanmalarını bekleyin.|  
|[target_block Sınıfı](target-block-class.md)|`target_block` Temel bağlantı yönetim işlevleri sağlayan soyut bir temel sınıfı ve hedef için hata denetimini yalnızca engeller.|  
|[task Sınıfı (Eşzamanlılık Çalışma Zamanı)](task-class.md)|Paralel Desen kitaplığı (PPL) `task` sınıfı. A `task` nesnesi zaman uyumsuz olarak ve diğer görevleri aynı anda yürütülebilecek ve Eşzamanlılık Çalışma zamanında paralel algoritmalar tarafından üretilen iş paralel çalışmayı temsil eder. Türünün bir sonucu üretir `_ResultType` başarıyla tamamlandığında. Görev türü `task<void>` hiç sonuç vermez. Bir görev beklenebilir ve diğer görevlerden bağımsız olarak iptal edildi. Devamlılıkları kullanarak başka görevlerle de oluşabilir (`then`) ve birleştirme (`when_all`) ve seçim (`when_any`) desenleri.|  
|[task_canceled Sınıfı](task-canceled-class.md)|Bu sınıf, geçerli görevi iptal etmek için zorlamak için PPL görev katmanı tarafından verilen bir özel durumu anlatmaktadır. Ayrıca tarafından oluşturulur `get()` metodunda [görev](https://msdn.microsoft.com/5389e8a5-5038-40b6-844a-55e9b58ad35f), iptal edilen bir görev için.|  
|[task_completion_event Sınıfı](task-completion-event-class.md)|`task_completion_event` Sınıfı bir koşul sağlanana kadar bir görevin yürütülmesini geciktirmek veya dış bir olaya yanıt olarak bir görevi başlatma olanak tanır.|  
|[task_continuation_context Sınıfı](task-continuation-context-class.md)|`task_continuation_context` Sınıfı bir devamlılığın yürütülmesini istediğiniz belirtmenize olanak verir. Yalnızca, bu sınıftan bir UWP uygulaması kullanmak kullanışlıdır. Windows Runtime uygulamalar için görev devamlılığı yürütme içeriği, çalışma zamanı tarafından belirlenen ve yapılandırılabilir.|  
|[task_group sınıfı](task-group-class.md)|`task_group` Sınıf beklenen veya iptal edilen paralel iş koleksiyonunu temsil eder.|  
|[task_handle Sınıfı](task-handle-class.md)|`task_handle` Sınıfı, tek bir paralel iş öğesinin temsil eder. Bu yönergeler ve bir parça işin yürütme için gerekli verileri saklar.|  
|[task_options Sınıfı (Eşzamanlılık Çalışma Zamanı)](task-options-class-concurrency-runtime.md)|Bir görev oluşturmak için izin verilen seçenekleri temsil eder|  
|[timer Sınıfı](timer-class.md)|A `timer` ileti bloğu tek hedef `source_block` gönderebilen bir ileti hedefine belirtilen süre geçtikten sonra veya belirli aralıklarla.|  
|[transformer Sınıfı](transformer-class.md)|A `transformer` ileti bloğu tek-hedef birden çok kaynak, sıralı `propagator_block` bir türden iletileri kabul edebilir ve sınırsız sayıda farklı türden iletileri depolayabilen özelliğine sahiptir.|  
|[unbounded_buffer sınıfı](unbounded-buffer-class.md)|Bir `unbounded_buffer` ileti bloğu birden çok hedef birden çok kaynak, sıralı `propagator_block` iletilerin sınırsız sayıda depolama özelliğine sahip.|  
|[unsupported_os Sınıfı](unsupported-os-class.md)|Bu sınıf, desteklenmeyen bir işletim sistemi kullanıldığında oluşturulan bir özel durum açıklar.|  
  
### <a name="structures"></a>Yapılar  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[DispatchState Yapısı](dispatchstate-structure.md)|`DispatchState` Yapısı durumuna aktarmak için kullanılan `IExecutionContext::Dispatch` yöntemi. Hangi koşullarda açıklar `Dispatch` yöntemi çağrıldığında bir `IExecutionContext` arabirimi.|  
|[IExecutionContext Yapısı](iexecutioncontext-structure.md)|Belirli bir sanal işlemci üzerinde çalıştırabilir ve olması bir yürütme bağlamı için bir arabirim işbirliği içerisinde devamlılığı bağlam değiştirdi.|  
|[IExecutionResource Yapısı](iexecutionresource-structure.md)|Donanım iş parçacığı için bir Özet.|  
|[IResourceManager Yapısı](iresourcemanager-structure.md)|Eşzamanlılık Çalışma zamanı kaynak yöneticisi için arabirim. Bu, zamanlayıcılar Resource Manager ile iletişim kurmak arabirimidir.|  
|[IScheduler Yapısı](ischeduler-structure.md)|Bir arabirim için bir iş Zamanlayıcı bir soyutlamasıdır. Eşzamanlılık çalışma zamanının Resource Manager, bu arabirim iş zamanlayıcılar ile iletişim kurmak için kullanır.|  
|[ISchedulerProxy Yapısı](ischedulerproxy-structure.md)|Tarafından zamanlayıcılar kaynak ayırma anlaşmak için eşzamanlılık çalışma zamanının Resource Manager ile iletişim kurmak arabirim.|  
|[IThreadProxy Yapısı](ithreadproxy-structure.md)|Bir iş parçacığı için bir soyutlamayı yürütme. Yapılandırmanıza bağlı olarak `SchedulerType` oluşturduğunuz Zamanlayıcı ilke anahtarı, kaynak yöneticisi vermek, normal bir Win32 iş parçacığı veya bir kullanıcı modunda zamanlanabilen (UMS) iş parçacığı tarafından desteklenen bir iş parçacığı proxy'sini. UMS iş parçacıkları, sürümü Windows 7 64-bit işletim sistemlerinde desteklenen ve daha yüksek.|  
|[ITopologyExecutionResource Yapısı](itopologyexecutionresource-structure.md)|Kaynak Yöneticisi tarafından tanımlanan bir yürütme kaynağı arabirim.|  
|[ITopologyNode Yapısı](itopologynode-structure.md)|Kaynak Yöneticisi tarafından tanımlandığı gibi bir topoloji düğüm için bir arabirim. Bir düğüm, bir veya daha fazla yürütme kaynakları içerir.|  
|[IUMSCompletionList Yapısı](iumscompletionlist-structure.md)|UMS tamamlanma listesini temsil eder. UMS iş parçacığı blokları, scheduler'ın zamanlama atanan olduğunda bağlamı ne özgün iş parçacığı engellenir sırada temel alınan sanal işlemci kökünde zamanlamak bir karar vermek için gönderilir. Özgün iş parçacığı engellemesinin kaldırıldığı, işletim sistemi, bu arabirimle erişilebilen, tamamlanma listesini sıralar. Zamanlayıcı belirtilen zamanlama bağlamı veya iş için arar herhangi bir yerde tamamlanma listesi sorgulayabilirsiniz.|  
|[IUMSScheduler Yapısı](iumsscheduler-structure.md)|Eşzamanlılık çalışma zamanının Resource Manager'ı, kullanıcı modunda zamanlanabilen (UMS) iş parçacıklarını teslim etmek isteyen bir iş Zamanlayıcı bir Özet için arabirim. UMS iş parçacığı zamanlayıcılar ile iletişim kurmak için bu arabirimi Resource Manager'ı kullanır. `IUMSScheduler` Arabirimi devralır `IScheduler` arabirimi.|  
|[IUMSThreadProxy Yapısı](iumsthreadproxy-structure.md)|Bir iş parçacığı için bir soyutlamayı yürütme. Kullanıcı modunda zamanlanabilen (UMS) iş parçacıklarını verilebilmesi için scheduler istiyorsanız Zamanlayıcı ilkesini öğesinin değeri ayarlamak `SchedulerKind` için `UmsThreadDefault`ve uygulama `IUMSScheduler` arabirimi. UMS iş parçacıkları, yalnızca desteklenen 64 bit işletim sistemlerinde, sürümü Windows 7 ve üzeri.|  
|[IUMSUnblockNotification Yapısı](iumsunblocknotification-structure.md)|Bir bildirim kaynak engellenir ve zamanlama bağlam belirlenen Zamanlayıcının dön tetiklenen iş parçacığı proxy'sini engeli kaldırılmış ve zamanlanması hazır Yöneticisi'nden temsil eder. Sağlayıcıdan döndürülen iş parçacığı proxy'sinin ilişkili yürütme bağlamı, sonra bu arabirim geçersiz `GetContext` yöntemi, işlemi yeniden zamanlanacak.|  
|[IVirtualProcessorRoot Yapısı](ivirtualprocessorroot-structure.md)|Bir Özet donanım iş parçacığı üzerinde bir iş parçacığı proxy'sini yürütebilirsiniz.|  
|[scheduler_interface Yapısı](scheduler-interface-structure.md)|Zamanlayıcı arabirimi|  
|[scheduler_ptr Yapısı (Eşzamanlılık Çalışma Zamanı)](scheduler-ptr-structure-concurrency-runtime.md)|Bir işaretçi için bir Zamanlayıcı'yı temsil eder. Shared_ptr veya yalnızca bir düz başvuru ham işaretçiyi kullanarak paylaşılan bir kullanım ömrünün belirtilmesine izin vermek için bu sınıfı var.|  
  
### <a name="enumerations"></a>Numaralandırmalar  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[agent_status](concurrency-namespace-enums.md#agent_status)|Geçerli durumları bir `agent`.|  
|[Agents_EventType](concurrency-namespace-enums.md#agents_eventtype)|Aracılar Kitaplığı tarafından sunulan izleme işlevselliği kullanılarak izlenebilir olay türleri|  
|[ConcRT_EventType](concurrency-namespace-enums.md#concrt_eventtype)|Eşzamanlılık Çalışma zamanı tarafından sunulan izleme işlevselliği kullanılarak izlenebilir olay türleri.|  
|[Concrt_TraceFlags](concurrency-namespace-enums.md#concrt_traceflags)|Olay türleri için izleme bayrakları|  
|[CriticalRegionType](concurrency-namespace-enums.md#criticalregiontype)|Kritik bölgesinin bir bağlam içinde türüdür.|  
|[DynamicProgressFeedbackType](concurrency-namespace-enums.md#dynamicprogressfeedbacktype)|Tarafından kullanılan `DynamicProgressFeedback` yapılançağrılararacılığıylaboştadurumunaiçinevedışınagidereksanalişlemcitemelistatistikselbilgilerigöreZamanlayıcı'dantoplananyadayalnızcaZamanlayıcıiçinkaynaklarıDengelenecekolmadığınıtanımlamakiçinilke`Activate` ve `Deactivate` yöntemlerde `IVirtualProcessorRoot` arabirimi. Kullanılabilir Zamanlayıcı ilkeleri hakkında daha fazla bilgi için bkz. [PolicyElementKey](concurrency-namespace-enums.md#policyelementkey).|  
|[join_type](concurrency-namespace-enums.md#join_type)|Türü bir `join` ileti bloğu.|  
|[message_status](concurrency-namespace-enums.md#message_status)|Bir teklif için geçerli yanıtlar bir `message` bloğu için nesne.|  
|[PolicyElementKey](concurrency-namespace-enums.md#policyelementkey)|Zamanlayıcı davranış yönlerini açıklayan ilke anahtarları. Her ilke öğesi bir anahtar-değer çifti tarafından tanımlanır. Zamanlayıcılar hakkında Zamanlayıcı ilkeleri ve etkileri hakkında daha fazla bilgi için bkz. [Görev Zamanlayıcı](../../../parallel/concrt/task-scheduler-concurrency-runtime.md).|  
|[SchedulerType](concurrency-namespace-enums.md#schedulertype)|Tarafından kullanılan `SchedulerKind` Zamanlayıcı için temel yürütme bağlamları kullanmalıdır iş parçacıkları türünü tanımlamak için ilke. Kullanılabilir Zamanlayıcı ilkeleri hakkında daha fazla bilgi için bkz. [PolicyElementKey](concurrency-namespace-enums.md#policyelementkey).|  
|[SchedulingProtocolType](concurrency-namespace-enums.md#schedulingprotocoltype)|Tarafından kullanılan `SchedulingProtocol` Zamanlayıcı için zamanlama algoritmayı kullanılır tanımlamak için ilke. Kullanılabilir Zamanlayıcı ilkeleri hakkında daha fazla bilgi için bkz. [PolicyElementKey](concurrency-namespace-enums.md#policyelementkey).|  
|[SwitchingProxyState](concurrency-namespace-enums.md#switchingproxystate)|Bir iş parçacığı proxy'sini bulunduğu durumu belirtmek için kullanılan, ne zaman, bir ortak bağlam anahtara farklı iş parçacığı proxy yürütüyor.|  
|[task_group_status](concurrency-namespace-enums.md#task_group_status)|Yürütme durumunu açıklar bir `task_group` veya `structured_task_group` nesne. Bu türde bir değer tamamlamak için bir görev grubuna Zamanlanmış görevlerde bekleyen çok sayıda yöntem tarafından döndürülür.|  
|[Winrtınitializationtype](concurrency-namespace-enums.md#winrtinitializationtype)|Tarafından kullanılan `WinRTInitialization` görüntülenip görüntülenmeyeceğini ve nasıl Windows çalışma zamanı sürümü Windows 8 işletim sistemlerinde çalışan bir uygulama için Zamanlayıcı iş parçacıklarında başlatılmış veya üzeri başlatılacağını açıklamak için ilke. Kullanılabilir Zamanlayıcı ilkeleri hakkında daha fazla bilgi için bkz. [PolicyElementKey](concurrency-namespace-enums.md#policyelementkey).|  
  
### <a name="functions"></a>İşlevler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[Alloc işlevi](concurrency-namespace-functions.md#alloc)|Eşzamanlılık Çalışma zamanı önbelleğe alma ayırıcısını ' belirtilen boyut, bellek bloğu ayırır.|  
|[asend işlevi](concurrency-namespace-functions.md#asend)|Fazla Yüklendi. Hedef blok verileri yaymak için bir görevi zamanlar bir zaman uyumsuz gönderme işlemi.|  
|[cancel_current_task işlevi](concurrency-namespace-functions.md#cancel_current_task)|Şu anda yürütülmekte olan görevi iptal eder. Bu işlev görevin yürütülmesini durdurmak ve girmesine neden bir görevin gövdesinden çağrılabilir `canceled` durumu.<br /><br /> Gövdesinde değilseniz bu işlevin çağrılmasında desteklenen bir senaryo değil bir `task`. Bunun yapılması bir kilitlenme veya uygulamanızdaki bir takılma gibi tanımsız davranışa neden olur.|  
|[create_async işlevi](concurrency-namespace-functions.md#create_async)|Bir kullanıcı tarafından sağlanan lambda veya işlev nesnesine bağlı bir Windows çalışma zamanı zaman uyumsuz bir yapı oluşturur. Dönüş türünü `create_async` herhangi biri `IAsyncAction^`, `IAsyncActionWithProgress<TProgress>^`, `IAsyncOperation<TResult>^`, veya `IAsyncOperationWithProgress<TResult, TProgress>^` yönteme geçirilen lambda'nın imzası göre.|  
|[create_task işlevi](concurrency-namespace-functions.md#create_task)|Fazla Yüklendi. Oluşturur [görev](https://msdn.microsoft.com/5389e8a5-5038-40b6-844a-55e9b58ad35f) nesne. `create_task` kullanılabilir herhangi bir görev oluşturucuyu kullandığınız. Kullanılmasına izin verdiğinden çok uygunluk açısından sağlanır `auto` görevler oluşturulurken anahtar sözcüğü.|  
|[CreateResourceManager işlevi](concurrency-namespace-functions.md#createresourcemanager)|Eşzamanlılık Çalışma zamanı Kaynak Yöneticisi'nin tekil örneğini temsil eden bir arabirim döndürür. Kaynak Yöneticisi birbirleriyle işbirliği istediğiniz planlayıcılar için kaynakları atamak ile sorumludur.|  
|[DisableTracing işlevi](concurrency-namespace-functions.md#disabletracing)|Eşzamanlılık Çalışma zamanında izleme devre dışı bırakır. ETW İzleme, varsayılan olarak kaydı olduğundan, bu işlev kullanım dışı bırakılmıştır.|  
|[EnableTracing işlevi](concurrency-namespace-functions.md#enabletracing)|Eşzamanlılık Çalışma zamanında izleme sağlar. ETW İzleme şu anda varsayılan olarak etkin olduğundan, bu işlev kullanım dışı bırakılmıştır.|  
|[Free işlevi](concurrency-namespace-functions.md#free)|Tarafından önceden ayrılan bellek bloğunu serbest bırakır `Alloc` eşzamanlılık çalışma zamanı önbelleğe alma ayırıcısını için yöntemi.|  
|[get_ambient_scheduler işlevi (eşzamanlılık çalışma zamanı)](concurrency-namespace-functions.md#get_ambient_scheduler)||  
|[GetExecutionContextId Function](concurrency-namespace-functions.md#getexecutioncontextid)|Uygulayan bir yürütme bağlamına atanmış benzersiz bir tanımlayıcı döndürür `IExecutionContext` arabirimi.|  
|[GetOSVersion işlevi](concurrency-namespace-functions.md#getosversion)|İşletim sistemi sürümünü döndürür.|  
|[GetProcessorCount işlevi](concurrency-namespace-functions.md#getprocessorcount)|Temel sistemdeki donanım iş parçacıklarının sayısını döndürür.|  
|[GetProcessorNodeCount Function](concurrency-namespace-functions.md#getprocessornodecount)|Temel sistemdeki NUMA düğümlerinin veya işlemci paketlerinin sayısını döndürür.|  
|[GetSchedulerId Function](concurrency-namespace-functions.md#getschedulerid)|Uygulayan bir zamanlayıcı atanmış benzersiz bir tanımlayıcı döndürür `IScheduler` arabirimi.|  
|[interruption_point işlevi](concurrency-namespace-functions.md#interruption_point)|İptali için bir kesinti noktası oluşturur. Bu durum, iptal burada bu işlev çağrılır bağlamında devam ediyorsa, o anda yürütülen paralel iş yürütülmesini durdurur bir iç özel durum oluşturur. İptal ediyor değil ise, işlev hiçbir şey yapmaz.|  
|[is_current_task_group_canceling Function](concurrency-namespace-functions.md#is_current_task_group_canceling)|Bir gösterge olup görev grubu, şu anda geçerli bağlamda satır içi yürütüyor etkin bir iptalin ortasında (veya kısa süre içinde olacaktır) döndürür. Satır içi geçerli bağlam üzerinde şu anda yürütülen görev grubu ise unutmayın `false` döndürülür.|  
|[make_choice işlevi](concurrency-namespace-functions.md#make_choice)|Fazla Yüklendi. Oluşturur bir `choice` isteğe bağlı bir Mesajlaşma bloğundan `Scheduler` veya `ScheduleGroup` ve iki veya daha fazla giriş kaynağı.|  
|[make_greedy_join Function](concurrency-namespace-functions.md#make_greedy_join)|Fazla Yüklendi. Oluşturur bir `greedy multitype_join` isteğe bağlı bir Mesajlaşma bloğundan `Scheduler` veya `ScheduleGroup` ve iki veya daha fazla giriş kaynağı.|  
|[make_join işlevi](concurrency-namespace-functions.md#make_join)|Fazla Yüklendi. Oluşturur bir `non_greedy multitype_join` isteğe bağlı bir Mesajlaşma bloğundan `Scheduler` veya `ScheduleGroup` ve iki veya daha fazla giriş kaynağı.|  
|[make_task işlevi](concurrency-namespace-functions.md#make_task)|Oluşturmak için Üreteç yöntemi bir `task_handle` nesne.|  
|[parallel_buffered_sort işlevi](concurrency-namespace-functions.md#parallel_buffered_sort)|Fazla Yüklendi. Belirtilen bir aralıktaki öğeleri azalmayan veya paralel bir ikili koşula göre belirtilen bir sıralama ölçütüne göre düzenler. Bu işlev anlam olarak benzerdir, `std::sort` ihtiyacı, tek farkı, karşılaştırma tabanlı kararsız, yerinde bir sıralama, `O(n)` ek alan ve varsayılan olarak başlatılması için sıralanan öğeleri gerektirir.|  
|[parallel_for işlevi](concurrency-namespace-functions.md#parallel_for)|Fazla Yüklendi. `parallel_for` bir dizi dizinleri üzerinden yinelenir ve her yineleme sırasında bir kullanıcı tarafından sağlanan işlev paralel olarak yürütür.|  
|[parallel_for_each işlevi](concurrency-namespace-functions.md#parallel_for_each)|Fazla Yüklendi. `parallel_for_each` paralel bir aralıktaki her öğeye belirtilen işlevi uygular. Anlamsal olarak eşdeğer olan `for_each` işlevi `std` ad alanı, bu yineleme öğeleri üzerinde paralel olarak gerçekleştirilir ve yineleme sırası belirtilmezse dışında. Bağımsız değişken `_Func` biçiminde bir işlev çağrısı işleci desteklemelidir `operator()(T)` burada parametre `T` üzerinden yinelenir kapsayıcı öğe türü.|  
|[parallel_invoke işlevi](concurrency-namespace-functions.md#parallel_invoke)|Fazla Yüklendi. Paralel ve blokları parametreler olarak yürütülen bitinceye kadar sağlanan işlev nesneleri yürütür. Her işlev nesnesi bir lambda ifadesi bir işlev işaretçisine olabilir veya imzaya sahip işlev çağrısı işleci destekleyen herhangi nesne `void operator()()`.|  
|[parallel_radixsort işlevi](concurrency-namespace-functions.md#parallel_radixsort)|Fazla Yüklendi. Belirtilen bir aralıktaki öğeleri, bir taban Sıralama algoritması kullanarak bir olmayan azalan düzenler. Bu öğeleri işaretsiz tamsayı benzeri anahtarlara sıralanacak yansıtabilirsiniz bir projeksiyon işlevi gerektiren tutarlı bir sıralama işlevdir. Varsayılan olarak başlatılması için sıralanan öğeleri gereklidir.|  
|[parallel_reduce işlevi](concurrency-namespace-functions.md#parallel_reduce)|Fazla Yüklendi. Art arda gelen kısmi toplamları tarafından belirtilen bir aralıktaki tüm öğelerin toplamını hesaplar veya benzer şekilde paralel olarak belirtilen bir ikili işlem toplam, dışındaki kullanımından elde edilen art arda gelen kısmi sonuçların sonucunu hesaplar. `parallel_reduce` anlamsal olarak benzer `std::accumulate`, ikili işlem ilişkilendirilebilir olmasını gerektirir ve bir başlangıç değeri yerine bir kimlik değeri gerektirir.|  
|[parallel_sort işlevi](concurrency-namespace-functions.md#parallel_sort)|Fazla Yüklendi. Belirtilen bir aralıktaki öğeleri azalmayan veya paralel bir ikili koşula göre belirtilen bir sıralama ölçütüne göre düzenler. Bu işlev anlam olarak benzerdir, `std::sort` karşılaştırma tabanlı kararsız, yerinde bir sıralama olması.|  
|[parallel_transform işlevi](concurrency-namespace-functions.md#parallel_transform)|Fazla Yüklendi. Belirtilen işlev nesnesini bir kaynak aralıktaki her öğeye veya iki kaynak aralıktaki bir öğe çiftinin uygular ve işlev nesnenin dönüş değerlerini paralel bir hedef aralığına kopyalar. Bu işlev için anlamsal olarak eşdeğer `std::transform`.|  
|[receive işlevi](concurrency-namespace-functions.md#receive)|Fazla Yüklendi. Genel Uygulama, tam olarak bir kaynaktan gelen veriler için bekleyin ve kabul edilen değerler filtrelemek bir bağlam izin vererek alırsınız.|  
|[run_with_cancellation_token Function](concurrency-namespace-functions.md#run_with_cancellation_token)|Bir işlev nesnesi, belirli bir iptal belirteci bağlamında hemen ve eşzamanlı olarak yürütür.|  
|[send işlevi](concurrency-namespace-functions.md#send)|Fazla Yüklendi. Hedef kabul eder veya iletiyi reddettiğinde kadar bekler, bir eş zamanlı gönderme işlemi.|  
|[set_ambient_scheduler işlevi (eşzamanlılık çalışma zamanı)](concurrency-namespace-functions.md#set_ambient_scheduler)||  
|[set_task_execution_resources Function](concurrency-namespace-functions.md#set_task_execution_resources)|Fazla Yüklendi. Eşzamanlılık Çalışma zamanı iç çalışan iş parçacığı için belirtilen benzeşim tarafından kullanılan yürütme kaynakları kısıtlar.<br /><br /> Yalnızca Resource Manager oluşturulmadan önce arasında veya iki Resource Manager yaşam süreleri bu yöntemi çağırmak için geçerlidir. Kaynak Yöneticisi'ni çağırma sırasındaki yok sürece birden çok kez çağrılabilir. Benzeşim sınırı ayarladıktan sonra sonraki geçerli çağrı kadar devam eder `set_task_execution_resources` yöntemi.<br /><br /> Belirtilen benzeşim maskesi işlem benzeşim maskesi bir alt kümesi olması gerekmez. Gerekirse, process affınıty güncelleştirilecektir.|  
|[swap işlevi](concurrency-namespace-functions.md#swap)|İki öğeleri birbiriyle değiştirir `concurrent_vector` nesneleri.|  
|[task_from_exception işlevi (eşzamanlılık çalışma zamanı)](concurrency-namespace-functions.md#task_from_exception)||  
|[task_from_result işlevi (eşzamanlılık çalışma zamanı)](concurrency-namespace-functions.md#task_from_result)||  
|[Trace_agents_register_name işlevi](concurrency-namespace-functions.md#trace_agents_register_name)|Ad ileti bloğu veya ETW İzleme Aracısı ile ilişkilendirir.|  
|[try_receive işlevi](concurrency-namespace-functions.md#try_receive)|Fazla Yüklendi. Genel deneyin-alma uygulaması, tam olarak bir kaynaktan gelen veriler arayabilir ve kabul edilen değerler filtrelemek bir bağlam sağlar. Veriler hazır değilse, yöntem false döndürür.|  
|[wait işlevi](concurrency-namespace-functions.md#wait)|Belirtilen bir zaman miktarı için geçerli bağlam duraklatır.|  
|[when_all işlevi](concurrency-namespace-functions.md#when_all)|Tüm bağımsız değişken olarak sağlanan görevleri başarıyla tamamladığında başarıyla tamamlanacak bir görev oluşturur.|  
|[when_any işlevi](concurrency-namespace-functions.md#when_any)|Fazla Yüklendi. Ne zaman görevlerden herhangi birini sağlanan bağımsız değişkenler tamamladıkça başarıyla başarıyla tamamlanacak bir görev oluşturur.|  
  
### <a name="operators"></a>İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------| 
|[operator!=](concurrency-namespace-operators.md#operator_neq)|Olmadığını test eder `concurrent_vector` işlecinin sol tarafındaki nesnesi eşit değil `concurrent_vector` işlecin sağ tarafındaki nesne.|  
|[operator & &](concurrency-namespace-operators.md#operator_amp_amp)|Fazla Yüklendi. Her iki bağımsız değişken olarak sağlanan görevler başarıyla tamamladığında başarıyla tamamlanacak bir görev oluşturur.|  
|[operator&#124;&#124;](concurrency-namespace-operators.md#operator_lor)|Fazla Yüklendi. Ne zaman görevlerden birini sağlanan bağımsız değişkenler tamamladıkça başarıyla başarıyla tamamlanacak bir görev oluşturur.|  
|[işleç <](concurrency-namespace-operators.md#operator_lt)|Olmadığını test eder `concurrent_vector` nesne işlecinin sol tarafındaki küçüktür `concurrent_vector` işlecin sağ tarafındaki nesne.|  
|[operator < =](concurrency-namespace-operators.md#operator_lt_eq)|Olmadığını test eder `concurrent_vector` işlecin sol tarafındaki nesnesinin değerinden küçük veya buna eşit olup `concurrent_vector` işlecin sağ tarafındaki nesne.|  
|[operator==](concurrency-namespace-operators.md#operator_eq_eq)|Olmadığını test eder `concurrent_vector` işlecin sol tarafındaki nesnesinin eşit olup `concurrent_vector` işlecin sağ tarafındaki nesne.|  
|[operator >](concurrency-namespace-operators.md#operator_gt)|Olmadığını test eder `concurrent_vector` nesne işlecinin sol tarafındaki büyük `concurrent_vector` işlecin sağ tarafındaki nesne.|  
|[operator>=](concurrency-namespace-operators.md#operator_lt_eq)|Olmadığını test eder `concurrent_vector` işlecin sol tarafındaki nesnesinin değerinden büyük veya ona eşit olup `concurrent_vector` işlecin sağ tarafındaki nesne.|  
  
### <a name="constants"></a>Sabitler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[AgentEventGuid](concurrency-namespace-constants1.md#agenteventguid)|Bir kategori açıklayan ETW olayları eşzamanlılık çalışma zamanındaki Aracılar Kitaplığı tarafından tetiklenen GUID ({B9B5B78C-0713-4898-A21A-C67949DCED07}).|  
|[ChoreEventGuid](concurrency-namespace-constants1.md#choreeventguid)|Bir kategori ETW olayları tanımlayan GUID işlerini veya görevlerini doğrudan ilgili eşzamanlılık çalışma zamanı tarafından tetiklendi.|  
|[ConcRT_ProviderGuid](concurrency-namespace-constants1.md#concrt_providerguid)|ETW sağlayıcısı GUID için eşzamanlılık çalışma zamanı.|  
|[CONCRT_RM_VERSION_1](concurrency-namespace-constants1.md#concrt_rm_version_1)|Visual Studio 2010'da tanımlanan Resource Manager arabirimi desteği gösterir.|  
|[ConcRTEventGuid](concurrency-namespace-constants1.md#concrteventguid)|Bir kategori ETW olayları tanımlayan GUID daha açık belirtmek gerekirse, başka bir kategoriye göre bahsedilmeyen eşzamanlılık çalışma zamanı tarafından tetiklendi.|  
|[ContextEventGuid](concurrency-namespace-constants1.md#contexteventguid)|Bir kategori ETW olayları tanımlayan GUID içerikleri doğrudan ilgili eşzamanlılık çalışma zamanı tarafından tetiklendi.|  
|[COOPERATIVE_TIMEOUT_INFINITE](concurrency-namespace-constants1.md#cooperative_timeout_infinite)|Beklemenin asla zaman aşımına uğramayacağını belirten değer.|  
|[COOPERATIVE_WAIT_TIMEOUT](concurrency-namespace-constants1.md#cooperative_wait_timeout)|Bekleme zaman aşımına uğradığını belirten değer.|  
|[INHERIT_THREAD_PRIORITY](concurrency-namespace-constants1.md#inherit_thread_priority)|Özel ilke anahtarının değerini `ContextPriority` gösteren tüm bağlamlarda Bu zamanlayıcı iş parçacığı önceliği Zamanlayıcı oluşturulan iş parçacığının aynı olmalıdır.|  
|[LockEventGuid](concurrency-namespace-constants1.md#lockeventguid)|Bir kategori ETW olayları tanımlayan GUID kilitleri doğrudan ilgili eşzamanlılık çalışma zamanı tarafından tetiklendi.|  
|[MaxExecutionResources](concurrency-namespace-constants1.md#maxexecutionresources)|İlke anahtarları için özel değer `MinConcurrency` ve `MaxConcurrency`. Varsayılan olarak diğer kısıtlamaları olmadığında makinede donanım iş parçacığı sayısı.|  
|[PPLParallelForeachEventGuid](concurrency-namespace-constants1.md#pplparallelforeacheventguid)|Bir kategori ETW olayları tanımlayan GUID kullanımı için doğrudan ilgili eşzamanlılık çalışma zamanı tarafından harekete geçirilen `parallel_for_each` işlevi.|  
|[PPLParallelForEventGuid](concurrency-namespace-constants1.md#pplparallelforeventguid)|Bir kategori ETW olayları tanımlayan GUID kullanımı için doğrudan ilgili eşzamanlılık çalışma zamanı tarafından harekete geçirilen `parallel_for` işlevi.|  
|[PPLParallelInvokeEventGuid](concurrency-namespace-constants1.md#pplparallelinvokeeventguid)|Bir kategori ETW olayları tanımlayan GUID kullanımı için doğrudan ilgili eşzamanlılık çalışma zamanı tarafından harekete geçirilen `parallel_invoke` işlevi.|  
|[ResourceManagerEventGuid](concurrency-namespace-constants1.md#resourcemanagereventguid)|Bir kategori ETW olayları tanımlayan GUID resource Manager'a doğrudan ilgili eşzamanlılık çalışma zamanı tarafından tetiklendi.|  
|[ScheduleGroupEventGuid](concurrency-namespace-constants1.md#schedulegroupeventguid)|Bir kategori ETW olayları tanımlayan GUID eşzamanlılık grupları zamanlamak için doğrudan ilgili çalışma zamanı tarafından tetiklendi.|  
|[SchedulerEventGuid](concurrency-namespace-constants1.md#schedulereventguid)|Bir kategori ETW olayları tanımlayan GUID Zamanlayıcı etkinlik için doğrudan ilgili eşzamanlılık çalışma zamanı tarafından tetiklendi.|  
|[VirtualProcessorEventGuid](concurrency-namespace-constants1.md#virtualprocessoreventguid)|Bir kategori ETW olayları tanımlayan GUID sanal işlemci için doğrudan ilgili eşzamanlılık çalışma zamanı tarafından tetiklendi.|  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** agents.h, concrt.h, concrtrm.h, concurrent_priority_queue.h, concurrent_queue.h, concurrent_unordered_map.h, concurrent_unordered_set.h, concurrent_vector.h, internal_concurrent_hash.h, internal_split_ordered_ List.h, ppl.h, pplcancellation_token.h, pplconcrt.h, pplinterface.h, ppltasks.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Başvuru](reference-concurrency-runtime.md)

