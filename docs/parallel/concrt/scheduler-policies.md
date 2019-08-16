---
title: Zamanlayıcı İlkeleri
ms.date: 11/04/2016
helpviewer_keywords:
- scheduler policies
ms.assetid: 58fb68bd-4a57-40a8-807b-6edb6f083cd9
ms.openlocfilehash: 5569ed9fb6229373ba59d687f21627ac9415050f
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69510454"
---
# <a name="scheduler-policies"></a>Zamanlayıcı İlkeleri

Bu belge, Eşzamanlılık Çalışma Zamanı Zamanlayıcı ilkelerinin rolünü açıklamaktadır. *Zamanlayıcı İlkesi* , Scheduler 'ın görevleri yönettiğinde kullandığı stratejiyi denetler. Örneğin, ' de `THREAD_PRIORITY_NORMAL` `THREAD_PRIORITY_HIGHEST`yürütülecek bazı görevlerin ve diğer görevlerin yürütmesini gerektiren bir uygulamayı düşünün.  İki zamanlayıcı örneği oluşturabilirsiniz: bir `ContextPriority` ilkeyi `THREAD_PRIORITY_NORMAL` ve aynı ilkeyi `THREAD_PRIORITY_HIGHEST`belirten başka birini belirten bir ilke.

Zamanlayıcı ilkelerini kullanarak, kullanılabilir işleme kaynaklarını bölebilir ve her Scheduler 'a bir sabit kaynak kümesi atayabilirsiniz. Örneğin, dört işlemciyi aşmayan bir paralel algoritma düşünün. Görevlerini aynı anda dörtten fazla işlemciyi kullanacak şekilde sınırlayan bir Zamanlayıcı ilkesi oluşturabilirsiniz.

> [!TIP]
>  Eşzamanlılık Çalışma Zamanı varsayılan bir Zamanlayıcı sağlar. Bu nedenle, uygulamanızda bir tane oluşturmanız gerekmez. Görev Zamanlayıcı uygulamalarınızın performansını hassas bir şekilde ayarlamanıza yardımcı olduğundan, Eşzamanlılık Çalışma Zamanı yeni başladıysanız [paralel Desenler kitaplığı (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md) veya [zaman uyumsuz aracılar Kitaplığı](../../parallel/concrt/asynchronous-agents-library.md) ile başlamanız önerilir.

Bir zamanlayıcı örneği oluşturmak için [concurrency:: CurrentScheduler:: Create](reference/currentscheduler-class.md#create), [concurrency:: Scheduler:: Create](reference/scheduler-class.md#create)veya [concurrency:: Scheduler:: SetDefaultSchedulerPolicy](reference/scheduler-class.md#setdefaultschedulerpolicy) metodunu kullandığınızda bir [eşzamanlılık sağlarsınız:: ](../../parallel/concrt/reference/schedulerpolicy-class.md)Scheduler 'ın davranışını belirten anahtar-değer çiftleri koleksiyonunu Içeren SchedulerPolicy nesnesi. `SchedulerPolicy` Oluşturucu değişken sayıda bağımsız değişken alır. İlk bağımsız değişken, belirtmek üzere olduğunuz ilke öğelerinin sayısıdır. Kalan bağımsız değişkenler, her ilke öğesi için anahtar-değer çiftleridir. Aşağıdaki örnek, üç ilke `SchedulerPolicy` öğesini belirten bir nesnesi oluşturur. Çalışma zamanı, belirtilen ilke anahtarları için varsayılan değerleri kullanır.

[!code-cpp[concrt-scheduler-policy#2](../../parallel/concrt/codesnippet/cpp/scheduler-policies_1.cpp)]

[Eşzamanlılık::P olicyElementKey](reference/concurrency-namespace-enums.md#policyelementkey) numaralandırması, Görev Zamanlayıcı ilişkili ilke anahtarlarını tanımlar. Aşağıdaki tabloda, ilke anahtarları ve çalışma zamanının her biri için kullandığı varsayılan değer açıklanmaktadır.

|İlke anahtarı|Açıklama|Varsayılan Değer|
|----------------|-----------------|-------------------|
|`SchedulerKind`|Görevleri zamanlamak için kullanılacak iş parçacıklarının türünü belirten bir [concurrency:: SchedulerType](reference/concurrency-namespace-enums.md#schedulertype) değeri.|`ThreadScheduler`(normal iş parçacıklarını kullanın). Bu anahtar için geçerli tek değer budur.|
|`MaxConcurrency`|Scheduler `unsigned int` 'ın kullandığı en fazla eşzamanlılık kaynağı sayısını belirten bir değer.|[Eşzamanlılık:: MaxExecutionResources](reference/concurrency-namespace-constants1.md#maxexecutionresources)|
|`MinConcurrency`|Scheduler `unsigned int` 'ın kullandığı en az eşzamanlılık kaynağı sayısını belirten bir değer.|`1`|
|`TargetOversubscriptionFactor`|Her `unsigned int` bir işleme kaynağına ayrılacak iş parçacığı sayısını belirten bir değer.|`1`|
|`LocalContextCacheSize`|Her `unsigned int` Sanal işlemcinin yerel sırasında Önbelleğe alınabilecek en fazla bağlam sayısını belirten bir değer.|`8`|
|`ContextStackSize`|Her `unsigned int` bağlam için ayrılacak yığın boyutunu kilobayt cinsinden belirten bir değer.|`0`(varsayılan yığın boyutunu kullanın)|
|`ContextPriority`|Her `int` bağlamın iş parçacığı önceliğini belirten bir değer. Bu, [SetThreadPriority](/windows/win32/api/processthreadsapi/nf-processthreadsapi-setthreadpriority) veya `INHERIT_THREAD_PRIORITY`' a geçirebilmeniz gereken herhangi bir değer olabilir.|`THREAD_PRIORITY_NORMAL`|

|`SchedulingProtocol`| Kullanılacak zamanlama algoritmasını belirten bir [concurrency:: SchedulingProtocolType](reference/concurrency-namespace-enums.md#schedulingprotocoltype) değeri. | `EnhanceScheduleGroupLocality`| | `DynamicProgressFeedback`| [Tutarlılık::D ynamicprogressfeedbacktype](reference/concurrency-namespace-enums.md#dynamicprogressfeedbacktype) değeri, kaynakların istatistik tabanlı ilerleme bilgilerine göre yeniden dengelenmesi gerektiğini belirtir.<br /><br /> **Göz önünde** Çalışma zamanı tarafından kullanılmak üzere ayrıldığından `ProgressFeedbackDisabled` , bu ilkeyi öğesine ayarlamayın. |`ProgressFeedbackEnabled`|

Her Zamanlayıcı, görevleri zamanlarken kendi ilkesini kullanır. Bir zamanlayıcı ile ilişkili ilkeler, başka bir Scheduler 'ın davranışını etkilemez. Ayrıca, `Scheduler` nesnesini oluşturduktan sonra zamanlayıcı ilkesini değiştiremezsiniz.

> [!IMPORTANT]
>  Çalışma zamanının oluşturduğu iş parçacıklarının özniteliklerini denetlemek için yalnızca Zamanlayıcı ilkeleri kullanın. Çalışma zamanı tarafından oluşturulan iş parçacıklarının benzeşimini veya önceliğini değiştirmeyin, çünkü bu tanımsız davranışa neden olabilir.

Açıkça bir tane oluşturmadıysanız, çalışma zamanı sizin için varsayılan bir zamanlayıcı oluşturur. Uygulamanızda varsayılan zamanlayıcıyı kullanmak istiyorsanız, ancak bu Zamanlayıcı için kullanmak üzere bir ilke belirtmek istiyorsanız, paralel çalışmayı zamanlamadan önce [concurrency:: Scheduler:: SetDefaultSchedulerPolicy](reference/scheduler-class.md#setdefaultschedulerpolicy) yöntemini çağırın. `Scheduler::SetDefaultSchedulerPolicy` Yöntemini çağırmayın, çalışma zamanı tablodaki varsayılan ilke değerlerini kullanır.

Zamanlayıcı ilkesinin bir kopyasını almak için [concurrency:: CurrentScheduler:: GetPolicy](reference/currentscheduler-class.md#getpolicy) ve [concurrency:: Scheduler:: GetPolicy](reference/scheduler-class.md#getpolicy) yöntemlerini kullanın. Bu yöntemlerden aldığınız ilke değerleri, Scheduler 'ı oluştururken belirttiğiniz ilke değerlerinden farklı olabilir.

## <a name="example"></a>Örnek

Scheduler 'ın davranışını denetlemek için belirli Zamanlayıcı ilkelerini kullanan örnekleri incelemek için bkz [. nasıl yapılır: Belirli Zamanlayıcı ilkelerini](../../parallel/concrt/how-to-specify-specific-scheduler-policies.md) belirtin ve [şunları yapın: Belirli Zamanlayıcı Ilkelerini](../../parallel/concrt/how-to-create-agents-that-use-specific-scheduler-policies.md)kullanan aracılar oluşturun.

## <a name="see-also"></a>Ayrıca bkz.

[Görev Zamanlayıcı](../../parallel/concrt/task-scheduler-concurrency-runtime.md)<br/>
[Nasıl yapılır: Belirli Zamanlayıcı İlkeleri Belirtme](../../parallel/concrt/how-to-specify-specific-scheduler-policies.md)<br/>
[Nasıl yapılır: Belirli Zamanlayıcı İlkelerini Kullanan Aracılar Oluşturma](../../parallel/concrt/how-to-create-agents-that-use-specific-scheduler-policies.md)
