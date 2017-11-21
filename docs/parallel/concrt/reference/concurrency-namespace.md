---
title: "Eşzamanlılık Namespace | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
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
dev_langs: C++
helpviewer_keywords: Concurrency namespace
ms.assetid: f1d33ca2-679b-4442-b140-22a9d9df61d1
caps.latest.revision: "37"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: ca728f3efa45c35306184e1aefa108c455470ab9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="concurrency-namespace"></a>concurrency Ad Alanı
`Concurrency` Ad alanı sınıflar sağlar ve size işlevleri erişim eşzamanlılık çalışma zamanı C++ için eşzamanlı bir programlama çerçevesi. Daha fazla bilgi için bkz: [eşzamanlılık çalışma zamanı](../../../parallel/concrt/concurrency-runtime.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
namespace concurrency;  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="namespaces"></a>Ad Alanları  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[Namespace CONCURRENCY::Extensibility](http://msdn.microsoft.com/en-us/16a86ff2-128e-4edf-89e4-38aac79c81f9)||  
  
### <a name="typedefs"></a>Tür tanımları  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`runtime_object_identity`|Her bir ileti örneği kopyalanabilen ve mesajlaşma bileşenler arasında geçen gibi kendisini izleyen bir kimliğe sahip. Bu ileti nesnesi adresini olamaz.|  
|`task_status`|Bir görevin terminal durumunu temsil eden tür. Geçerli değerler `completed` ve `canceled`.|  
|`TaskProc`|Bir başlangıç Özet olarak tanımlanmış bir görev için `void (__cdecl * TaskProc)(void *)`. A `TaskProc` bir görevin çağırmak için çağrılır.|  
|`TaskProc_t`|Bir başlangıç Özet olarak tanımlanmış bir görev için `void (__cdecl * TaskProc_t)(void *)`. A `TaskProc` bir görevin çağırmak için çağrılır.|  
  
### <a name="classes"></a>Sınıflar  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[affinity_partitioner sınıfı](affinity-partitioner-class.md)|`affinity_partitioner` Sınıfı benzer `static_partitioner` sınıfı, ancak çalışan iş parçacığı alt aralıklara eşleme dilediği tarafından önbellek benzeşim artırır. Döngü aynı veri kümesi üzerinde yeniden yürütülen olduğunda ve veri önbelleği'nde uygun, performansı önemli ölçüde artırabilir. Unutmayın aynı `affinity_partitioner` nesnesi belirli veri veri yerleşim yararlanmak için küme üzerinde yürütülen paralel bir döngüden sonraki yinelemelerini kullanılmalıdır.|  
|[Agent sınıfı](agent-class.md)|Tüm bağımsız aracılar için temel sınıf olarak kullanılmak üzere bir sınıf. Diğer aracıları durumundan gizleme ve ileti geçirme kullanarak etkileşim kurmak için kullanılır.|  
|[auto_partitioner sınıfı](auto-partitioner-class.md)|`auto_partitioner` Sınıfı temsil eder, varsayılan yöntemi `parallel_for`, `parallel_for_each` ve `parallel_transform` tekrarlanan üzerinden aralığı bölüm için kullanın. Employes bölümlendirme, bu yöntem Yük Dengeleme için çalarak aralığı yanı sıra başına-iptal yineleme.|  
|[bad_target sınıfı](bad-target-class.md)|Bu sınıf, bir ileti bloğu gerçekleştirilen işlem için geçersiz bir hedef için bir işaretçi verildiğinde oluşturulan bir özel açıklar.|  
|[Çağrı sınıfı](call-class.md)|A `call` ileti bloğu, birden çok kaynak sıralı `target_block` , çağırır belirtilen işlevi bir ileti alırken.|  
|[cancellation_token sınıfı](cancellation-token-class.md)|`cancellation_token` Sınıfı, başka bir işlem iptal istendi olup olmadığını belirleme özelliğini temsil eder. Verilen bir belirteç ile ilişkili bir `task_group`, `structured_task_group`, veya `task` örtük iptal sağlamak için. Bu ayrıca iptalleri sorgulanmak veya bir geri çağırma için varsa ve kayıtlı sahip ilişkili `cancellation_token_source` iptal edilir.|  
|[cancellation_token_registration sınıfı](cancellation-token-registration-class.md)|`cancellation_token_registration` Sınıfı temsil eden bir geri çağırma bildirimden bir `cancellation_token`. Zaman `register` yöntemi bir `cancellation_token` iptal oluştuğunda, bildirimi almak için kullanılan bir `cancellation_token_registration` nesne çağıran artık belirli bir geri çağırma istemesini geri dönüş için bir tanıtıcı kullanımlayapılmasıgibidöndürülür`deregister` yöntemi.|  
|[cancellation_token_source sınıfı](cancellation-token-source-class.md)|`cancellation_token_source` Sınıfı, bazı İptal işlemi iptal etme yeteneğini temsil eder.|  
|[seçenek sınıfı](choice-class.md)|A `choice` ileti bloğu olan bir kaynak kümesi akış denetimi etkileşim temsil eden birden çok kaynak, tek hedef blok. Seçim bloğu bir iletisi oluşturmak üzere birden çok kaynaktan herhangi biri için bekler ve ileti üretilen kaynak dizini yayılır.|  
|[combinable sınıfı](combinable-class.md)|`combinable<T>` Nesne kilidi serbest iş parçacığı yerel alt sırasında paralel algoritmalar hesaplamalar veri, iş parçacığı özel kopyasının sağlamak için tasarlanmıştır. Paralel işlemin sonunda, iş parçacığı özel alt hesaplamalar sonra nihai sonucu birleştirilebilir. Bu sınıf, paylaşılan bir değişken yerine kullanılabilir ve aksi durumda olurdu, çok sayıda paylaşılan değişken üzerinde Çekişme bir performans geliştirmesinden ortaya çıkabilir.|  
|[concurrent_priority_queue sınıfı](concurrent-priority-queue-class.md)|`concurrent_priority_queue` Sınıfı eş zamanlı gönderme ve pop öğeleri için birden çok iş parçacığı sağlayan bir kapsayıcıdır. Öğeleri, öncelik şablon bağımsız değişken sağlanan bir functor tarafından belirlendiği öncelik sırasına Sil'i.|  
|[concurrent_queue sınıfı](concurrent-queue-class.md)|`concurrent_queue` Sınıftır ilk sağlayan dizisi kapsayıcı sınıfı, öğeleri ilk erişim. Eşzamanlılık güvenli işlemler, sınırlı sayıda gibi etkinleştirir `push` ve `try_pop`.|  
|[concurrent_unordered_map sınıfı](concurrent-unordered-map-class.md)|`concurrent_unordered_map` Sınıftır türündeki öğeler değişen uzunluk dizisi denetleyen bir eşzamanlılık güvenli kapsayıcı `std::pair<const K, _Element_type>`. Sıra sağlayan eşzamanlılık güvenli bir şekilde temsil edilen ekleme, öğe erişim, yineleyici erişim ve yineleyici geçişi işlemleri.|  
|[concurrent_unordered_multimap sınıfı](concurrent-unordered-multimap-class.md)|`concurrent_unordered_multimap` Sınıftır türündeki öğeler değişen uzunluk dizisi denetleyen bir eşzamanlılık güvenli kapsayıcı `std::pair<const K, _Element_type>`. Sıra sağlayan eşzamanlılık güvenli bir şekilde temsil edilen ekleme, öğe erişim, yineleyici erişim ve yineleyici geçişi işlemleri.|  
|[concurrent_unordered_multiset sınıfı](concurrent-unordered-multiset-class.md)|`concurrent_unordered_multiset` Sınıfı K. türündeki öğeler değişen uzunluk dizisi denetleyen bir eşzamanlılık güvenli kapsayıcı. Sıra sağlayan eşzamanlılık güvenli bir şekilde temsil edilen ekleme, öğe erişim, yineleyici erişim ve yineleyici geçişi işlemleri.|  
|[concurrent_unordered_set sınıfı](concurrent-unordered-set-class.md)|`concurrent_unordered_set` Sınıfı K. türündeki öğeler değişen uzunluk dizisi denetleyen bir eşzamanlılık güvenli kapsayıcı. Sıra sağlayan eşzamanlılık güvenli bir şekilde temsil edilen ekleme, öğe erişim, yineleyici erişim ve yineleyici geçişi işlemleri.|  
|[concurrent_vector sınıfı](concurrent-vector-class.md)|`concurrent_vector` Sınıftır herhangi bir öğeye rasgele erişim sağlayan bir dizi kapsayıcı. Eşzamanlılık güvenli etkinleştirir ekleme, öğe erişim, yineleyici erişim ve yineleyici geçişi işlemleri.|  
|[Bağlam sınıfı](context-class.md)|Yürütme bağlamı için bir Özet temsil eder.|  
|[context_self_unblock sınıfı](context-self-unblock-class.md)|Bu sınıf ne zaman oluşturulan bir özel tanımlar `Unblock` yöntemi bir `Context` nesnesi aynı bağlamdan çağrılır. Bu girişiminde tarafından belirli bir bağlam kendisini engellemesini kaldırmak için gösterir.|  
|[context_unblock_unbalanced sınıfı](context-unblock-unbalanced-class.md)|Bu sınıf ne zaman oluşturulan bir özel tanımlar çağrılar `Block` ve `Unblock` yöntemlerinin bir `Context` nesne değil düzgün eşlenmemiş.|  
|[critical_section sınıfı](critical-section-class.md)|Eşzamanlılık Çalışma zamanı açıkça farkındadır yeniden girme olmayan mutex.|  
|[CurrentScheduler sınıfı](currentscheduler-class.md)|Bir Özet arama bağlamla ilişkili geçerli Zamanlayıcı temsil eder.|  
|[default_scheduler_exists sınıfı](default-scheduler-exists-class.md)|Bu sınıf ne zaman oluşturulan bir özel tanımlar `Scheduler::SetDefaultSchedulerPolicy` yöntemi, bir varsayılan Zamanlayıcı işlemi içinde zaten mevcut olduğunda çağrılır.|  
|[Event sınıfı](event-class.md)|Eşzamanlılık Çalışma zamanı açıkça farkındadır elle sıfırlama olayı.|  
|[improper_lock sınıfı](improper-lock-class.md)|Bu sınıf bir kilit yanlış alındığında bir özel durum açıklar.|  
|[improper_scheduler_attach sınıfı](improper-scheduler-attach-class.md)|Bu sınıf ne zaman oluşturulan bir özel tanımlar `Attach` yöntemi çağrıldığında bir `Scheduler` geçerli bağlama zaten eklenmiş bir nesne.|  
|[improper_scheduler_detach sınıfı](improper-scheduler-detach-class.md)|Bu sınıf ne zaman oluşturulan bir özel tanımlar `CurrentScheduler::Detach` yöntemi kullanarak tüm Zamanlayıcı bağlı olmayan bir bağlamda çağrılır `Attach` yöntemi bir `Scheduler` nesnesi.|  
|[improper_scheduler_reference sınıfı](improper-scheduler-reference-class.md)|Bu sınıf ne zaman oluşturulan bir özel tanımlar `Reference` yöntemi çağrıldığında bir `Scheduler` aşağı, bu Zamanlayıcı parçası olmayan bir bağlamından kapatılıyor nesne.|  
|[invalid_link_target sınıfı](invalid-link-target-class.md)|Bu sınıf ne zaman oluşturulan bir özel tanımlar `link_target` ileti bloğunun yöntemi çağrılır ve ileti bloğu hedef bağlanamıyor. Bu ileti bloğu izin verilen bağlantı sayısını aşan veya belirli bir hedefe iki kere aynı kaynağına bağlanma girişiminde sonucu olabilir.|  
|[invalid_multiple_scheduling sınıfı](invalid-multiple-scheduling-class.md)|Bu sınıf ne zaman oluşturulan bir özel tanımlar bir `task_handle` nesnesidir zamanlanmış birden çok kez kullanarak `run` yöntemi bir `task_group` veya `structured_task_group` nesne ya da müdahalede bulunan bir çağrı olmadan `wait` veya `run_and_wait` yöntemleri.|  
|[invalid_operation sınıfı](invalid-operation-class.md)|Bu sınıf daha doğru bir şekilde eşzamanlılık çalışma zamanı tarafından oluşturulan başka bir özel durum türü tarafından açıklanmayan geçersiz bir işlem gerçekleştirilirken oluşturulan bir özel açıklar.|  
|[invalid_oversubscribe_operation sınıfı](invalid-oversubscribe-operation-class.md)|Bu sınıf ne zaman oluşturulan bir özel tanımlar `Context::Oversubscribe` yöntemi ile çağrılır `_BeginOversubscription` parametre kümesine `false` önceki çağrı olmadan `Context::Oversubscribe` yöntemiyle `_BeginOversubscription` parametre kümesine `true`.|  
|[invalid_scheduler_policy_key sınıfı](invalid-scheduler-policy-key-class.md)|Bu sınıf geçersiz bir zaman oluşturulan bir özel tanımlar veya Bilinmeyen anahtar için geçirilen bir `SchedulerPolicy` Nesne oluşturucusu veya `SetPolicyValue` yöntemi bir `SchedulerPolicy` nesnesi gibi başka yöntemler kullanılarak değiştirilmelidir bir anahtar geçirildi `SetConcurrencyLimits` yöntemi.|  
|[invalid_scheduler_policy_thread_specification sınıfı](invalid-scheduler-policy-thread-specification-class.md)|Bu sınıf eşzamanlılık sınırlarını ayarlamak için bir girişimde zaman oluşturulan bir özel açıklar bir `SchedulerPolicy` nesne şekilde değerini `MinConcurrency` anahtar değerini azdır `MaxConcurrency` anahtarı.|  
|[invalid_scheduler_policy_value sınıfı](invalid-scheduler-policy-value-class.md)|Bu sınıf, bir ilke anahtar oluşturulan bir özel açıklar bir `SchedulerPolicy` nesnesi, bu anahtarı için geçersiz bir değere ayarlanır.|  
|[Isource sınıfı](isource-class.md)|`ISource` Sınıftır arabirimi tüm blokları kaynağı için. Kaynak blokları yayılması iletileri `ITarget` engeller.|  
|[Itarget sınıfı](itarget-class.md)|`ITarget` Sınıftır arabirimi tüm blokları hedef için. Hedef blokları kullanmak için onlara tarafından sunulan iletiler `ISource` engeller.|  
|[join sınıfı](join-class.md)|A `join` ileti bloğu bir tek-hedef, çok kaynaklı, sıralı `propagator_block` bir araya getiren birlikte türden iletileri `T` her kaynaklarının.|  
|[Location sınıfı](location-class.md)|Bir Özet donanımda fiziksel bir konum.|  
|[message sınıfı](message-class.md)|İleti blokları geçirilen veri yükü içeren temel ileti Zarf.|  
|[message_not_found sınıfı](message-not-found-class.md)|Bu sınıf, bir ileti bloğu istenen ileti bulamıyor olduğunda oluşturulan bir özel açıklar.|  
|[message_processor sınıfı](message-processor-class.md)|`message_processor` Sınıftır işlenmesi için Özet temel sınıf `message` nesneleri. İletilerin sıralama üzerinde garantisi yoktur.|  
|[missing_wait sınıfı](missing-wait-class.md)|Bu sınıf için hala zamanlanmış görevler olduğunda oluşturulan bir özel açıklayan bir `task_group` veya `structured_task_group` aynı anda bu nesnenin nesne yıkıcı yürütür. Yıkıcı bir özel durum sonucu olarak geriye doğru izleme yığını nedeniyle ulaşıldığında bu özel durumun hiçbir zaman oluşturulur.|  
|[multi_link_registry sınıfı](multi-link-registry-class.md)|`multi_link_registry` Nesne bir `network_link_registry` birden çok kaynak blokları veya birden çok hedef blokları yönetir.|  
|[multitype_join sınıfı](multitype-join-class.md)|A `multitype_join` ileti bloğu her kaynaklarının farklı türlerde iletiler birlikte birleştiren ve hedeflerine birleşik iletileri dizisi sunar çok kaynak, tek hedef ileti bloğu.|  
|[nested_scheduler_missing_detach sınıfı](nested-scheduler-missing-detach-class.md)|Bu sınıf eşzamanlılık çalışma zamanı çağırmak ihmal algıladığında oluşturulan bir özel tanımlar `CurrentScheduler::Detach` yöntemi kullanarak ikinci bir zamanlayıcı bağlı bir bağlamda `Attach` yöntemi `Scheduler` nesnesi.|  
|[network_link_registry sınıfı](network-link-registry-class.md)|`network_link_registry` Özet temel sınıf kaynak ve hedef blokları arasındaki bağlantıları yönetir.|  
|[operation_timed_out sınıfı](operation-timed-out-class.md)|Bu sınıf, bir işlem zaman aşımına uğradı zaman oluşturulan bir özel açıklar.|  
|[ordered_message_processor sınıfı](ordered-message-processor-class.md)|Bir `ordered_message_processor` olan bir `message_processor` sırada alınan iletileri işlemek ileti blokları sağlar.|  
|[overwrite_buffer sınıfı](overwrite-buffer-class.md)|Bir `overwrite_buffer` ileti bloğu birden çok hedef birden çok kaynak, sıralı `propagator_block` aynı anda tek bir ileti depolama yeteneği. Yeni iletiler önceden tutulan olanları üzerine yazın.|  
|[progress_reporter sınıfı](progress-reporter-class.md)|Belirli bir türdeki ilerleme bildirimleri raporlama ilerleme Raporlayıcı sınıf sağlar. Her progress_reporter nesne belirli bir zaman uyumsuz eylem veya işlem için bağlı.|  
|[propagator_block sınıfı](propagator-block-class.md)|`propagator_block` Sınıfı, hem kaynak hem de hedef ileti blokları için Özet temel sınıf. Her ikisi de işlevlerini birleştiren `source_block` ve `target_block` sınıfları.|  
|[reader_writer_lock sınıfı](reader-writer-lock-class.md)|Yalnızca dönmesini yerel yazıcı tercih Okuyucu-Yazıcı sırası tabanlı kilidi. Kilidi okuyucular yazıcılarının sürekli yükü altında starves ve daha önce yazıcılarının - ilk (FIFO) erişimi verir.|  
|[ScheduleGroup sınıfı](schedulegroup-class.md)|Bir zamanlama grubu için bir Özet temsil eder. Zamanlama grupları bir dizi ilgili iş geçici olarak, başka bir gruba geçmeden önce aynı gruptaki başka bir görev yürütme ya da dağınık şekilde, aynı aynı grubu içindeki birden çok öğe çalıştırarak birbirine yakın zamanlanma gelen o avantajları düzenleyin. NUMA düğümü veya fiziksel yuva.|  
|[Zamanlayıcı sınıfı](scheduler-class.md)|Bir Özet bir eşzamanlılık çalışma zamanı Zamanlayıcısı temsil eder.|  
|[scheduler_not_attached sınıfı](scheduler-not-attached-class.md)|Bu sınıf geçerli bağlamla eklenmesi için bir zamanlayıcı gerektiren bir işlem gerçekleştirdiğinizde ve bulunmaması oluşturulan bir özel açıklar.|  
|[scheduler_resource_allocation_error sınıfı](scheduler-resource-allocation-error-class.md)|Bu sınıf eşzamanlılık çalışma zamanı kritik kaynak edinmeye bir hatadan dolayı oluşturulan bir özel açıklar.|  
|[scheduler_worker_creation_error sınıfı](scheduler-worker-creation-error-class.md)|Bu sınıf eşzamanlılık çalışma zamanı'nda çalışan yürütme bağlamı oluşturmak için bir hatadan dolayı oluşturulan bir özel açıklar.|  
|[SchedulerPolicy sınıfı](schedulerpolicy-class.md)|`SchedulerPolicy` Sınıfı bir zamanlayıcı örneğini davranışını denetleyen anahtar/değer çifti kümesi, her ilke öğesi için bir tane içeriyor.|  
|[simple_partitioner sınıfı](simple-partitioner-class.md)|`simple_partitioner` Sınıfı temsil eden bir statik üzerinden tarafından yinelendiğinde aralığının bölümleme `parallel_for`. Her bir öbeğin öbek boyutu tarafından belirtilen yineleme sayısını en az sahip olacağı şekilde bölümleyici aralığı parçalara ayırır.|  
|[single_assignment sınıfı](single-assignment-class.md)|A `single_assignment` ileti bloğu birden çok hedef birden çok kaynak, sıralı `propagator_block` yeteneğine sahip tek bir depolama yazma-sonra `message`.|  
|[single_link_registry sınıfı](single-link-registry-class.md)|`single_link_registry` Nesne bir `network_link_registry` yalnızca tek bir kaynak veya hedef blok yönetir.|  
|[source_block sınıfı](source-block-class.md)|`source_block` Sınıfı, yalnızca kaynak blokları için Özet temel sınıf. Sınıf iyi olarak ortak hata denetimleri temel bağlantı yönetimi işlevselliği sağlar.|  
|[source_link_manager sınıfı](source-link-manager-class.md)|`source_link_manager` Nesnesi ileti bloğu ağ bağlantıları yönetir `ISource` engeller.|  
|[static_partitioner sınıfı](static-partitioner-class.md)|`static_partitioner` Sınıfı temsil eden bir statik üzerinden tarafından yinelendiğinde aralığının bölümleme `parallel_for`. Bölümleyici aralığı çalışanları underyling Zamanlayıcı kullanılabilir olduğu kadar parçalara ayırır.|  
|[structured_task_group sınıfı](structured-task-group-class.md)|`structured_task_group` Sınıfı paralel iş yüksek oranda yapılandırılmış koleksiyonunu temsil eder. Tek tek Paralel Görevler sıraya bir `structured_task_group` kullanarak `task_handle` nesnelerini ve tamamlanmalarını bekleyin veya yürütme başlamıştır olmayan herhangi bir görevi iptal edilecek yürütme tamamlandı önce görev grubu iptal.|  
|[target_block sınıfı](target-block-class.md)|`target_block` Sınıfı, temel bağlantı yönetim işlevleri sağlayan Özet temel sınıf ve hedef için hata denetimi yalnızca engeller.|  
|[task sınıfı (eşzamanlılık çalışma zamanı)](task-class.md)|Paralel Desen kitaplığı (PPL) `task` sınıfı. A `task` nesnesi paralel eşzamanlılık çalışma zamanı'nda paralel algoritmaları tarafından üretilen iş ve zaman uyumsuz olarak ve diğer görevleri ile aynı anda yürütülebilecek iş temsil eder. Bir sonuç türü üretir `_ResultType` başarıyla tamamlandığında. Tür görevleri `task<void>` hiçbir sonucu. Bir görev sırasında beklenen ve diğer görevler bağımsız olarak iptal. Ayrıca devamlılıklar kullanarak diğer görevleri ile birleştirilebilen (`then`) ve birleştirme (`when_all`) ve seçim (`when_any`) desenleri.|  
|[task_canceled sınıfı](task-canceled-class.md)|Bu sınıf, iptal etmek için geçerli görev zorlamak için PPL görevleri katmanı tarafından oluşturulan bir özel açıklar. Tarafından da oluşturulan `get()` yöntemi [görev](http://msdn.microsoft.com/en-us/5389e8a5-5038-40b6-844a-55e9b58ad35f), iptal edilen bir görev için.|  
|[task_completion_event sınıfı](task-completion-event-class.md)|`task_completion_event` Sınıfı, bir koşul sağlanırsa kadar bir görevi yürütme gecikme veya dış bir olaya yanıt olarak bir görevi başlatmak olanak sağlar.|  
|[task_continuation_context sınıfı](task-continuation-context-class.md)|`task_continuation_context` Sınıfı yürütülecek bir devamlılık oluşturulacağı yeri belirtmenize olanak verir. Yalnızca, bu sınıftan bir Windows mağazası uygulamasını kullanmak kullanışlıdır. Windows mağazası uygulamaları için görev devamlılığı 's yürütme bağlamı çalışma zamanı tarafından belirlenen ve yapılandırılamaz.|  
|[task_group sınıfı](task-group-class.md)|`task_group` Sınıfı beklenen veya iptal edilen paralel iş koleksiyonunu temsil eder.|  
|[task_handle sınıfı](task-handle-class.md)|`task_handle` Sınıfı, bir tek tek paralel iş öğesini temsil eder. Yönergeler ve bir parça işin yürütmek için gerekli verileri saklar.|  
|[task_options sınıfı (eşzamanlılık çalışma zamanı)](task-options-class-concurrency-runtime.md)|Bir görev oluşturmak için izin verilen seçeneklerini temsil eder|  
|[Timer sınıfı](timer-class.md)|A `timer` ileti bloğu tek hedef `source_block` hedefine belirtilen süre geçtikten sonra veya belirli aralıklarla ileti gönderme yapabilir.|  
|[Transformer sınıfı](transformer-class.md)|A `transformer` ileti bloğu bir tek-hedef, çok kaynaklı, sıralı `propagator_block` bir türden iletileri kabul edebilir ve farklı türde bir ileti sınırsız bir sayısı depolayabilen yeteneğine sahiptir.|  
|[unbounded_buffer sınıfı](unbounded-buffer-class.md)|Bir `unbounded_buffer` ileti bloğu birden çok hedef birden çok kaynak, sıralı `propagator_block` sınırsız bir ileti sayısı depolama yeteneği.|  
|[unsupported_os sınıfı](unsupported-os-class.md)|Bu sınıf, desteklenmeyen bir işletim sistemi kullanıldığında, bir özel durum açıklar.|  
  
### <a name="structures"></a>Yapılar  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[DispatchState yapısı](dispatchstate-structure.md)|`DispatchState` Yapısı durumuna aktarmak için kullanılır `IExecutionContext::Dispatch` yöntemi. Hangi koşullarda açıklar `Dispatch` yöntemi çağrıldığında bir `IExecutionContext` arabirimi.|  
|[Iexecutioncontext yapısı](iexecutioncontext-structure.md)|Belirli bir sanal işlemcinin çalıştırabilir ve işbirliği ile anahtarlı bağlamının olması bir yürütme bağlamı için bir arabirim.|  
|[Iexecutionresource yapısı](iexecutionresource-structure.md)|Bir donanım iş parçacığı için bir Özet.|  
|[Iresourcemanager yapısı](iresourcemanager-structure.md)|Eşzamanlılık Çalışma zamanı kaynak yöneticisi için bir arabirim. Bu, zamanlayıcılar Resource Manager ile iletişim kurmak arabirimidir.|  
|[Ischeduler yapısı](ischeduler-structure.md)|İş Zamanlayıcı bir soyutlamasını bir arabirim. Eşzamanlılık Çalışma zamanı Resource Manager, iş zamanlayıcılar ile iletişim kurmak için bu arabirimini kullanır.|  
|[Ischedulerproxy yapısı](ischedulerproxy-structure.md)|Tarafından zamanlayıcılar kaynak ayırma anlaşmak üzere eşzamanlılık çalışma zamanı Resource Manager ile iletişim kurmak arabirimi.|  
|[Ithreadproxy yapısı](ithreadproxy-structure.md)|Bir iş parçacığı için bir Özet yürütme. Bağlı olarak `SchedulerType` oluşturduğunuz Zamanlayıcı İlkesi anahtarı Resource Manager vermek, normal bir Win32 iş parçacığı veya kullanıcı modu zamanlanabilir (UMS) iş parçacığı tarafından yedeklenen bir iş parçacığı proxy. UMS iş parçacığı desteklenen 64-bit işletim sistemi sürümü Windows 7 ve üzeri.|  
|[Itopologyexecutionresource yapısı](itopologyexecutionresource-structure.md)|Kaynak Yöneticisi tarafından tanımlanan bir yürütme kaynak bir arabirim.|  
|[Itopologynode yapısı](itopologynode-structure.md)|Kaynak Yöneticisi tarafından tanımlanan bir topoloji düğüme bir arabirim. Bir düğüm bir veya daha fazla yürütme kaynakları içerir.|  
|[Iumscompletionlist yapısı](iumscompletionlist-structure.md)|UMS tamamlanma listesini temsil eder. Zamanlama scheduler'ın UMS iş parçacığı blokları belirlenmiş olduğunda içeriği ne özgün iş parçacığı engellendi karşın temel alınan sanal işlemci kök'zamanlamak bir karar vermek için gönderilir. Özgün iş parçacığı engelini kaldırır, işletim sistemi, bu arabirimi üzerinden erişilebilir olan tamamlanma listesini sıralar. Zamanlayıcı atanmış zamanlama bağlamı veya iş için arar başka bir yerde tamamlanma listesi sorgulayabilirsiniz.|  
|[Iumsscheduler yapısı](iumsscheduler-structure.md)|Kullanıcı modu zamanlanabilir (UMS) iş parçacıklarının el için Kaynak Yöneticisi'ni eşzamanlılık çalışma zamanı istediği bir iş Zamanlayıcı bir soyutlamasını bir arabirim. Kaynak Yöneticisi bu arabirimi UMS iş parçacığı zamanlayıcılar ile iletişim kurmak için kullanır. `IUMSScheduler` Arabirimi devraldığı `IScheduler` arabirimi.|  
|[Iumsthreadproxy yapısı](iumsthreadproxy-structure.md)|Bir iş parçacığı için bir Özet yürütme. Kullanıcı modu zamanlanabilir (UMS) iş parçacıklarının verilebilmesi için Zamanlayıcı istiyorsanız, Zamanlayıcı İlkesi öğesinin değeri ayarlayın `SchedulerKind` için `UmsThreadDefault`ve uygulamanıza `IUMSScheduler` arabirimi. UMS iş parçacıkları yalnızca desteklenen 64-bit işletim sistemi sürümü Windows 7 ve üzeri.|  
|[Iumsunblocknotification yapısı](iumsunblocknotification-structure.md)|Bildirim kaynağı engellenen ve zamanlama içeriği belirlenen Zamanlayıcının dönün tetiklenen bir iş parçacığı proxy engellemesini ve zamanlanması hazır Yöneticisi'nden temsil eder. İş parçacığı proxy'nin ilişkili yürütme bağlamı, döndürülen sonra bu arabirimi geçersiz `GetContext` yöntemi, yeniden.|  
|[Ivirtualprocessorroot yapısı](ivirtualprocessorroot-structure.md)|Bir iş parçacığı proxy yürütmek bir donanım iş parçacığı için bir Özet.|  
|[scheduler_interface yapısı](scheduler-interface-structure.md)|Zamanlayıcı arabirimi|  
|[scheduler_ptr yapısı (eşzamanlılık çalışma zamanı)](scheduler-ptr-structure-concurrency-runtime.md)|Bir işaretçi bir zamanlayıcı temsil eder. Bu sınıf izin vermek için mevcut ham işaretçi kullanarak shared_ptr veya yalnızca düz başvurusu kullanarak paylaşılan bir yaşam süresi'nin belirtimine.|  
  
### <a name="enumerations"></a>Numaralandırmalar  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[agent_status](concurrency-namespace-enums.md#agent_status)|Geçerli durumunu bir `agent`.|  
|[Agents_EventType](concurrency-namespace-enums.md#agents_eventtype)|Aracılar Kitaplığı tarafından sunulan izleme işlevselliği kullanılarak izlenebilir olay türleri|  
|[ConcRT_EventType](concurrency-namespace-enums.md#concrt_eventtype)|Eşzamanlılık Çalışma zamanı tarafından sunulan izleme işlevselliği kullanılarak izlenebilir olay türleri.|  
|[Concrt_TraceFlags](concurrency-namespace-enums.md#concrt_traceflags)|Olay türleri için izleme bayrakları|  
|[CriticalRegionType](concurrency-namespace-enums.md#criticalregiontype)|Kritik bölgesinin bir bağlam türünü içindedir.|  
|[DynamicProgressFeedbackType](concurrency-namespace-enums.md#dynamicprogressfeedbacktype)|Tarafından kullanılan `DynamicProgressFeedback` kaynakları Zamanlayıcı için istatistiksel bilgileri göre Zamanlayıcı'dan toplanan ya da yalnızca yeniden dengelenir olup olmadığını açıklamak için ilke temel alarak çağrılarıaracılığıylaboştadurumundakivegidensanalişlemciler`Activate` ve `Deactivate` yöntemlere `IVirtualProcessorRoot` arabirimi. Kullanılabilir Zamanlayıcı ilkeleri hakkında daha fazla bilgi için bkz: [PolicyElementKey](concurrency-namespace-enums.md#policyelementkey).|  
|[join_type](concurrency-namespace-enums.md#join_type)|Türü bir `join` ileti bloğu.|  
|[message_status](concurrency-namespace-enums.md#message_status)|Geçerli yanıtlar bir teklifi için bir `message` bloğu için nesne.|  
|[PolicyElementKey](concurrency-namespace-enums.md#policyelementkey)|İlke Zamanlayıcı davranışının açıklayan yönlerini anahtarları. Her ilke öğesi bir anahtar-değer çifti tarafından tanımlanır. Zamanlayıcılar Zamanlayıcı ilkeleri ve bunların etkisi hakkında daha fazla bilgi için bkz: [Görev Zamanlayıcı](../../../parallel/concrt/task-scheduler-concurrency-runtime.md).|  
|[SchedulerType](concurrency-namespace-enums.md#schedulertype)|Tarafından kullanılan `SchedulerKind` Zamanlayıcı için temel alınan yürütme bağlamı kullanmalıdır iş parçacığı türünü tanımlamak için ilke. Kullanılabilir Zamanlayıcı ilkeleri hakkında daha fazla bilgi için bkz: [PolicyElementKey](concurrency-namespace-enums.md#policyelementkey).|  
|[SchedulingProtocolType](concurrency-namespace-enums.md#schedulingprotocoltype)|Tarafından kullanılan `SchedulingProtocol` zamanlama algoritmayı Zamanlayıcı için yararlı olabilir açıklamak için ilke. Kullanılabilir Zamanlayıcı ilkeleri hakkında daha fazla bilgi için bkz: [PolicyElementKey](concurrency-namespace-enums.md#policyelementkey).|  
|[SwitchingProxyState](concurrency-namespace-enums.md#switchingproxystate)|Bir iş parçacığı proxy bulunduğu durumu belirtmek için kullanılan, ne zaman, farklı iş parçacığı proxy işbirlikçi içerik anahtarına yürütüyor.|  
|[task_group_status](concurrency-namespace-enums.md#task_group_status)|Yürütme durumu açıklayan bir `task_group` veya `structured_task_group` nesnesi. Görevin tamamlanması için bir görev grubuna zamanlanmış bekleme çeşitli yöntemlerle bu türde bir değer döndürdü.|  
|[Winrtınitializationtype](concurrency-namespace-enums.md#winrtinitializationtype)|Tarafından kullanılan `WinRTInitialization` olup olmadığını ve nasıl Windows çalışma zamanı sürümü Windows 8 işletim sistemlerinde çalışan bir uygulama için Zamanlayıcı iş parçacığı üzerinde başlatılmış veya daha yüksek olacak açıklamak için ilke. Kullanılabilir Zamanlayıcı ilkeleri hakkında daha fazla bilgi için bkz: [PolicyElementKey](concurrency-namespace-enums.md#policyelementkey).|  
  
### <a name="functions"></a>İşlevler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[Alloc işlevi](concurrency-namespace-functions.md#alloc)|Bir eşzamanlılık çalışma zamanı önbelleğe alma Suballocator ' belirtilen boyut, bellek bloğu ayırır.|  
|[asend işlevi](concurrency-namespace-functions.md#asend)|Fazla Yüklendi. Zaman uyumsuz bir hedef blok verileri yaymak için bir görev zamanlar işlemi gönderin.|  
|[cancel_current_task işlevi](concurrency-namespace-functions.md#cancel_current_task)|Şu anda yürütülen görev iptal eder. Bu işlev Görev Yürütme iptal etmek ve girmek neden görevi gövdesi içinde çağrılabilir `canceled` durumu.<br /><br /> Gövdesi içinde değilse bu işlevi çağırmak için desteklenen bir senaryo değildir bir `task`. Bunun yapılması bir kilitlenme veya yanıt vermemesine uygulamanızda gibi tanımsız davranış neden olur.|  
|[create_async işlevi](concurrency-namespace-functions.md#create_async)|Bir kullanıcı tarafından sağlanan lambda veya işlev nesnesine bağlı bir Windows çalışma zamanı zaman uyumsuz yapısı oluşturur. Dönüş türü `create_async` aşağıdakilerden biri `IAsyncAction^`, `IAsyncActionWithProgress<TProgress>^`, `IAsyncOperation<TResult>^`, veya `IAsyncOperationWithProgress<TResult, TProgress>^` yönteme geçirilen lambda imza göre.|  
|[create_task işlevi](concurrency-namespace-functions.md#create_task)|Fazla Yüklendi. Bir PPL oluşturur [görev](http://msdn.microsoft.com/en-us/5389e8a5-5038-40b6-844a-55e9b58ad35f) nesnesi. `create_task`kullanılabilir herhangi bir yere görev Oluşturucusu kullanıldığını. Kullanılmasına izin verdiği için çoğunlukla kolaylık sağlamak için sağlanmıştır `auto` görevleri oluşturulurken anahtar sözcüğü.|  
|[CreateResourceManager işlevi](concurrency-namespace-functions.md#createresourcemanager)|Eşzamanlılık Çalışma zamanı Kaynak Yöneticisi'nin singleton örneği temsil eden bir arabirim döndürür. Resource Manager kaynakları birbirleri ile işbirliği yapmak istediğiniz zamanlayıcılar atamak için sorumludur.|  
|[DisableTracing işlevi](concurrency-namespace-functions.md#disabletracing)|Eşzamanlılık Çalışma Zamanı'nda izleme devre dışı bırakır. ETW İzleme varsayılan olarak kaydı olmadığından bu işlev kullanım dışıdır.|  
|[EnableTracing işlevi](concurrency-namespace-functions.md#enabletracing)|Eşzamanlılık Çalışma Zamanı'nda izlemeyi etkinleştirir. ETW İzleme artık varsayılan olarak açık olduğundan bu işlev kullanım dışıdır.|  
|[Free işlevi](concurrency-namespace-functions.md#free)|Tarafından önceden ayrılmış bellek bloğu serbest `Alloc` eşzamanlılık çalışma zamanı Suballocator önbelleğe alma yöntemi.|  
|[get_ambient_scheduler işlevi (eşzamanlılık çalışma zamanı)](concurrency-namespace-functions.md#get_ambient_scheduler)||  
|[Getexecutioncontextıd işlevi](concurrency-namespace-functions.md#getexecutioncontextid)|Arabirimini uygulayan bir yürütme bağlamı atanmış benzersiz bir tanımlayıcı döndürür `IExecutionContext` arabirimi.|  
|[GetOSVersion işlevi](concurrency-namespace-functions.md#getosversion)|İşletim sistemi sürümünü döndürür.|  
|[GetProcessorCount işlevi](concurrency-namespace-functions.md#getprocessorcount)|Temel alınan sistemdeki donanım iş parçacığı sayısını döndürür.|  
|[GetProcessorNodeCount işlevi](concurrency-namespace-functions.md#getprocessornodecount)|Temel alınan sistemdeki NUMA düğümlerinin veya işlemci paketleri sayısını döndürür.|  
|[Getschedulerıd işlevi](concurrency-namespace-functions.md#getschedulerid)|Arabirimini uygulayan bir zamanlayıcı atanmış benzersiz bir tanımlayıcı döndürür `IScheduler` arabirimi.|  
|[interruption_point işlevi](concurrency-namespace-functions.md#interruption_point)|İptal için bir kesinti noktası oluşturur. Burada bu işlev çağrılır bağlamda iptal ediyor, bu şu anda yürütülen paralel iş yürütme durdurur dahili bir özel durum atar. İptal ediyor değilse işlev hiçbir şey yapmaz.|  
|[is_current_task_group_canceling işlevi](concurrency-namespace-functions.md#is_current_task_group_canceling)|Görev olup olmadığını grubu, şu anda geçerli bağlamda satır içi yürütüyor, ilişkin bir gösterge ortasında etkin bir iptal (ya da kısa süre içinde olacaktır) döndürür. Satır içi geçerli bağlama göre şu anda yürütülmekte olan hiçbir görev grubu ise unutmayın `false` döndürülür.|  
|[make_choice işlevi](concurrency-namespace-functions.md#make_choice)|Fazla Yüklendi. Oluşturan bir `choice` isteğe bağlı bir Mesajlaşma bloğundan `Scheduler` veya `ScheduleGroup` ve iki veya daha fazla giriş kaynağı.|  
|[make_greedy_join işlevi](concurrency-namespace-functions.md#make_greedy_join)|Fazla Yüklendi. Oluşturan bir `greedy multitype_join` isteğe bağlı bir Mesajlaşma bloğundan `Scheduler` veya `ScheduleGroup` ve iki veya daha fazla giriş kaynağı.|  
|[make_join işlevi](concurrency-namespace-functions.md#make_join)|Fazla Yüklendi. Oluşturan bir `non_greedy multitype_join` isteğe bağlı bir Mesajlaşma bloğundan `Scheduler` veya `ScheduleGroup` ve iki veya daha fazla giriş kaynağı.|  
|[make_task işlevi](concurrency-namespace-functions.md#make_task)|Oluşturmak için Üreteç yöntemi bir `task_handle` nesnesi.|  
|[parallel_buffered_sort işlevi](concurrency-namespace-functions.md#parallel_buffered_sort)|Fazla Yüklendi. Belirli bir aralık içinde öğeleri nondescending sırada ya da bir ikili karşılaştırma paralel tarafından belirtilen bir sıralama ölçütü göre düzenler. Bu işlev anlamsal olarak benzer `std::sort` gereksinim duyduğu dışında bir karşılaştırma tabanlı kararsız, yerinde sıralama aynıdır, `O(n)` ek alan ve varsayılan olarak başlatılması için sıralanan öğeleri gerektirir.|  
|[parallel_for işlevi](concurrency-namespace-functions.md#parallel_for)|Fazla Yüklendi. `parallel_for`dizinler aralığında tekrarlanan ve kullanıcı tarafından sağlanan bir işlev her yinelemesinde paralel olarak yürütür.|  
|[parallel_for_each işlevi](concurrency-namespace-functions.md#parallel_for_each)|Fazla Yüklendi. `parallel_for_each`Belirtilen işlev paralel bir aralıkta her öğesine uygular. Anlam olarak eşdeğerdir `for_each` işlevi `std` öğeleri üzerinden bu yineleme paralel olarak gerçekleştirilir ve yineleme sırasını belirtilmezse dışında ad. Bağımsız değişkeni `_Func` işlev çağırma işleci formun desteklemelidir `operator()(T)` burada parametresi `T` üzerinden yinelendiğinde kapsayıcı öğe türü değil.|  
|[parallel_invoke işlevi](concurrency-namespace-functions.md#parallel_invoke)|Fazla Yüklendi. Yürütme bitinceye kadar paralel ve blokları parametre olarak sağlanan işlev nesneleri yürütür. Her işlev nesnesi bir lambda ifadesi işlevi için bir işaretçi olabilir veya herhangi bir işlev çağırma işleci imzalı destekleyen nesne `void operator()()`.|  
|[parallel_radixsort işlevi](concurrency-namespace-functions.md#parallel_radixsort)|Fazla Yüklendi. Belirli bir aralık içinde öğeleri algoritması sıralama sayı tabanını kullanarak bir olmayan azalan düzenler. İmzasız tamsayı benzeri anahtarlara sıralanacak öğeleri yansıtabilirsiniz projeksiyon işlevi gerektiren bir tutarlı sıralama işlevi budur. Varsayılan olarak başlatılması için sıralanan öğeleri gereklidir.|  
|[parallel_reduce işlevi](concurrency-namespace-functions.md#parallel_reduce)|Fazla Yüklendi. Belirtilen aralıktaki tüm öğelerin toplamı, art arda kısmi toplamlarını bilgi işlem tarafından hesaplar veya benzer şekilde paralel olarak belirtilen bir ikili işlem toplam dışında kullanılarak elde edilen art arda kısmi sonuçlar sonucunu hesaplar. `parallel_reduce`anlam olarak benzer `std::accumulate`, ikili işlem ilişkilendirilebilir olmasını gerektirir ve bir başlangıç değeri yerine bir kimlik değeri gerektirir.|  
|[parallel_sort işlevi](concurrency-namespace-functions.md#parallel_sort)|Fazla Yüklendi. Belirli bir aralık içinde öğeleri nondescending sırada ya da bir ikili karşılaştırma paralel tarafından belirtilen bir sıralama ölçütü göre düzenler. Bu işlev anlamsal olarak benzer `std::sort` karşılaştırma tabanlı kararsız, yerinde bir sıralama olması.|  
|[parallel_transform işlevi](concurrency-namespace-functions.md#parallel_transform)|Fazla Yüklendi. Belirtilen işlev nesnesi kaynak aralığı her bir öğe veya çiftlerini iki kaynak aralıklarından geçerlidir ve paralel bir hedef aralığı içine işlev nesnesinin dönüş değerleri kopyalar. Bu işlev anlam olarak eşdeğerdir `std::transform`.|  
|[receive işlevi](concurrency-namespace-functions.md#receive)|Fazla Yüklendi. Bir genel uygulama, tam olarak bir kaynaktan veri bekleyin ve kabul edilen değerlerin filtrelemek bir bağlam izin vererek alırsınız.|  
|[run_with_cancellation_token işlevi](concurrency-namespace-functions.md#run_with_cancellation_token)|İşlev nesnesi, verilen iptal belirteci bağlamında hemen ve eşzamanlı olarak yürütür.|  
|[send işlevi](concurrency-namespace-functions.md#send)|Fazla Yüklendi. Zaman uyumlu bir hedef kabul eder ya da ileti reddettiğinde kadar bekler işlemi gönderin.|  
|[set_ambient_scheduler işlevi (eşzamanlılık çalışma zamanı)](concurrency-namespace-functions.md#set_ambient_scheduler)||  
|[set_task_execution_resources işlevi](concurrency-namespace-functions.md#set_task_execution_resources)|Fazla Yüklendi. Belirtilen benzeşim için eşzamanlılık çalışma zamanı iç çalışan iş parçacıkları tarafından kullanılan yürütme kaynakları kısıtlar.<br /><br /> Bu yöntemi yalnızca Resource Manager oluşturulmadan önce arasında veya iki Resource Manager yaşam süreleri çağırmak için geçerlidir. Kaynak Yöneticisi'ni çağırma aynı anda yok sürece birden çok kez çağrılabilir. Bir benzeşim sınırı ayarladıktan sonra onu sonraki geçerli çağrısı kadar sürdürür `set_task_execution_resources` yöntemi.<br /><br /> Sağlanan benzeşim maskesi bir alt işlem benzeşim maskesi olması gerekmez. İşlem benzeşimi gerekiyorsa güncelleştirilir.|  
|[swap işlevi](concurrency-namespace-functions.md#swap)|İki öğelerini alış verişleri `concurrent_vector` nesneleri.|  
|[task_from_exception işlevi (eşzamanlılık çalışma zamanı)](concurrency-namespace-functions.md#task_from_exception)||  
|[task_from_result işlevi (eşzamanlılık çalışma zamanı)](concurrency-namespace-functions.md#task_from_result)||  
|[Trace_agents_register_name işlevi](concurrency-namespace-functions.md#trace_agents_register_name)|Verilen ada ileti bloğu veya ETW İzleme Aracısı ilişkilendirir.|  
|[try_receive işlevi](concurrency-namespace-functions.md#try_receive)|Fazla Yüklendi. Genel try-alma uygulaması, tam olarak bir kaynaktan veriler arayabilir ve kabul edilen değerlerin filtrelemek bir bağlam sağlar. Veri hazır değilse yöntemi false döndürür.|  
|[wait işlevi](concurrency-namespace-functions.md#wait)|Belirtilen bir süre için geçerli bağlam duraklatır.|  
|[when_all işlevi](concurrency-namespace-functions.md#when_all)|Tüm bağımsız değişkenler olarak verilen görevleri başarıyla tamamlandığında, başarılı bir şekilde tamamlanır bir görev oluşturur.|  
|[when_any işlevi](concurrency-namespace-functions.md#when_any)|Fazla Yüklendi. Bağımsız değişkenler tamamladıkça başarıyla görevlerden herhangi birini ne zaman sağlanan başarıyla tamamlanır bir görev oluşturur.|  
  
### <a name="operators"></a>İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------| 
|[operator! =](concurrency-namespace-operators.md#operator_neq)|Varsa testleri `concurrent_vector` işlecinin sol tarafındaki nesnesi eşit değil `concurrent_vector` sağ tarafında nesne.|  
|[operator & &](concurrency-namespace-operators.md#operator_amp_amp)|Fazla Yüklendi. Bağımsız değişkenler olarak verilen görevleri her ikisi de başarıyla tamamlandığında, başarılı bir şekilde tamamlanır bir görev oluşturur.|  
|[operator &#124; &#124;](concurrency-namespace-operators.md#operator_lor)|Fazla Yüklendi. Bağımsız değişkenler tamamladıkça başarıyla görevlerin birini ne zaman sağlanan başarıyla tamamlanır bir görev oluşturur.|  
|[operator <](concurrency-namespace-operators.md#operator_lt)|Varsa testleri `concurrent_vector` nesne işlecinin sol tarafındaki küçük `concurrent_vector` sağ tarafında nesne.|  
|[operator < =](concurrency-namespace-operators.md#operator_lt_eq)|Varsa testleri `concurrent_vector` işlecinin sol tarafındaki nesnesidir küçük veya eşit `concurrent_vector` sağ tarafında nesne.|  
|[operator ==](concurrency-namespace-operators.md#operator_eq_eq)|Varsa testleri `concurrent_vector` nesne işlecinin sol tarafındaki eşittir `concurrent_vector` sağ tarafında nesne.|  
|[operator >](concurrency-namespace-operators.md#operator_gt)|Varsa testleri `concurrent_vector` işlecinin sol tarafındaki nesnesidir büyük `concurrent_vector` sağ tarafında nesne.|  
|[operator > =](concurrency-namespace-operators.md#operator_lt_eq)|Varsa testleri `concurrent_vector` işlecinin sol tarafındaki nesnesidir değerinden büyük veya eşit `concurrent_vector` sağ tarafında nesne.|  
  
### <a name="constants"></a>Sabitler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[AgentEventGuid](concurrency-namespace-constants1.md#agenteventguid)|Bir kategori açıklayan ETW olayları Aracılar Kitaplığı'nda eşzamanlılık çalışma zamanı tarafından tetiklenen GUID ({B9B5B78C-0713-4898-A21A-C67949DCED07}).|  
|[ChoreEventGuid](concurrency-namespace-constants1.md#choreeventguid)|Bir kategori ETW olayları tanımlayan GUID işlerinden veya görevler doğrudan ilgili eşzamanlılık çalışma zamanı tarafından tetiklenir.|  
|[ConcRT_ProviderGuid](concurrency-namespace-constants1.md#concrt_providerguid)|ETW sağlayıcı eşzamanlılık çalışma zamanı için GUID.|  
|[CONCRT_RM_VERSION_1](concurrency-namespace-constants1.md#concrt_rm_version_1)|Visual Studio 2010'da tanımlanan Resource Manager arabirimi desteği gösterir.|  
|[ConcRTEventGuid](concurrency-namespace-constants1.md#concrteventguid)|Bir kategori ETW olayları tanımlayan GUID başka bir kategoriye göre daha açık belirtmek gerekirse açıklanmayan eşzamanlılık çalışma zamanı tarafından tetiklenir.|  
|[ContextEventGuid](concurrency-namespace-constants1.md#contexteventguid)|Bir kategori ETW olayları tanımlayan GUID içerikleri doğrudan ilgili eşzamanlılık çalışma zamanı tarafından tetiklenir.|  
|[COOPERATIVE_TIMEOUT_INFINITE](concurrency-namespace-constants1.md#cooperative_timeout_infinite)|Bekleme zaman aşımı hiçbir zaman gerektiğini belirten değer.|  
|[COOPERATIVE_WAIT_TIMEOUT](concurrency-namespace-constants1.md#cooperative_wait_timeout)|Bekleme zaman aşımına uğradığını belirten değer.|  
|[INHERIT_THREAD_PRIORITY](concurrency-namespace-constants1.md#inherit_thread_priority)|Özel ilke anahtar değeri `ContextPriority` gösteren tüm bağlamlarda Zamanlayıcı iş parçacığı önceliği Zamanlayıcı oluşturulan iş parçacığının aynı olmalıdır.|  
|[LockEventGuid](concurrency-namespace-constants1.md#lockeventguid)|Bir kategori ETW olayları tanımlayan GUID kilitleri doğrudan ilgili eşzamanlılık çalışma zamanı tarafından tetiklenir.|  
|[MaxExecutionResources](concurrency-namespace-constants1.md#maxexecutionresources)|İlke anahtarları için özel değeri `MinConcurrency` ve `MaxConcurrency`. Varsayılan olarak diğer kısıtlamaları olmadığında makinede donanım iş parçacığı sayısı.|  
|[PPLParallelForeachEventGuid](concurrency-namespace-constants1.md#pplparallelforeacheventguid)|Bir kategori kullanımı için doğrudan ilgili eşzamanlılık çalışma zamanı tarafından ETW olayları tanımlayan GUID harekete `parallel_for_each` işlevi.|  
|[PPLParallelForEventGuid](concurrency-namespace-constants1.md#pplparallelforeventguid)|Bir kategori kullanımı için doğrudan ilgili eşzamanlılık çalışma zamanı tarafından ETW olayları tanımlayan GUID harekete `parallel_for` işlevi.|  
|[Pplparallelınvokeeventguid](concurrency-namespace-constants1.md#pplparallelinvokeeventguid)|Bir kategori kullanımı için doğrudan ilgili eşzamanlılık çalışma zamanı tarafından ETW olayları tanımlayan GUID harekete `parallel_invoke` işlevi.|  
|[ResourceManagerEventGuid](concurrency-namespace-constants1.md#resourcemanagereventguid)|Bir kategori GUID ETW olayları tanımlayan kaynak yöneticisi ile doğrudan ilişkilidir eşzamanlılık çalışma zamanı tarafından tetiklenir.|  
|[ScheduleGroupEventGuid](concurrency-namespace-constants1.md#schedulegroupeventguid)|Bir kategori ETW olayları tanımlayan GUID grupları zamanlamak için doğrudan ilgili eşzamanlılık çalışma tarafından tetiklenir.|  
|[SchedulerEventGuid](concurrency-namespace-constants1.md#schedulereventguid)|Bir kategori ETW olayları tanımlayan GUID Zamanlayıcı etkinliğe doğrudan ilgili eşzamanlılık çalışma zamanı tarafından tetiklenir.|  
|[VirtualProcessorEventGuid](concurrency-namespace-constants1.md#virtualprocessoreventguid)|Bir kategori ETW olayları tanımlayan GUID sanal işlemciye doğrudan ilgili eşzamanlılık çalışma zamanı tarafından tetiklenir.|  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** agents.h, concrt.h, concrtrm.h, concurrent_priority_queue.h, concurrent_queue.h, concurrent_unordered_map.h, concurrent_unordered_set.h, concurrent_vector.h, internal_concurrent_hash.h, internal_split_ordered_ List.h, ppl.h, pplcancellation_token.h, pplconcrt.h, pplinterface.h, ppltasks.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Başvuru](reference-concurrency-runtime.md)

