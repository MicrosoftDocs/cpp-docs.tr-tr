---
title: Zamanlayıcı İlkeleri
ms.date: 11/04/2016
helpviewer_keywords:
- scheduler policies
ms.assetid: 58fb68bd-4a57-40a8-807b-6edb6f083cd9
ms.openlocfilehash: 0f90b461ecba702501c2f6919572dc828c80907f
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77142275"
---
# <a name="scheduler-policies"></a>Zamanlayıcı İlkeleri

Bu belge, Eşzamanlılık Çalışma Zamanı Zamanlayıcı ilkelerinin rolünü açıklamaktadır. *Zamanlayıcı İlkesi* , Scheduler 'ın görevleri yönettiğinde kullandığı stratejiyi denetler. Örneğin, bazı görevlerin `THREAD_PRIORITY_HIGHEST`yürütmek üzere `THREAD_PRIORITY_NORMAL` ve diğer görevlerde yürütmesini gerektiren bir uygulamayı düşünün.  İki zamanlayıcı örneği oluşturabilirsiniz: bir tane, `THREAD_PRIORITY_NORMAL` olacak `ContextPriority` ilkeyi belirten diğeri ve `THREAD_PRIORITY_HIGHEST`aynı ilkeyi belirten başka bir ilke.

Zamanlayıcı ilkelerini kullanarak, kullanılabilir işleme kaynaklarını bölebilir ve her Scheduler 'a bir sabit kaynak kümesi atayabilirsiniz. Örneğin, dört işlemciyi aşmayan bir paralel algoritma düşünün. Görevlerini aynı anda dörtten fazla işlemciyi kullanacak şekilde sınırlayan bir Zamanlayıcı ilkesi oluşturabilirsiniz.

> [!TIP]
> Eşzamanlılık Çalışma Zamanı varsayılan bir Zamanlayıcı sağlar. Bu nedenle, uygulamanızda bir tane oluşturmanız gerekmez. Görev Zamanlayıcı uygulamalarınızın performansını hassas bir şekilde ayarlamanıza yardımcı olduğundan, Eşzamanlılık Çalışma Zamanı yeni başladıysanız [paralel Desenler kitaplığı (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md) veya [zaman uyumsuz aracılar Kitaplığı](../../parallel/concrt/asynchronous-agents-library.md) ile başlamanız önerilir.

Bir zamanlayıcı örneği oluşturmak için [concurrency:: CurrentScheduler:: Create](reference/currentscheduler-class.md#create), [concurrency:: Scheduler:: Create](reference/scheduler-class.md#create)veya [concurrency:: Scheduler:: SetDefaultSchedulerPolicy](reference/scheduler-class.md#setdefaultschedulerpolicy) metodunu kullandığınızda, Scheduler 'ın davranışını belirten anahtar-değer çiftleri koleksiyonunu içeren bir [concurrency:: SchedulerPolicy](../../parallel/concrt/reference/schedulerpolicy-class.md) nesnesi sağlarsınız. `SchedulerPolicy` Oluşturucusu değişken sayıda bağımsız değişken alır. İlk bağımsız değişken, belirtmek üzere olduğunuz ilke öğelerinin sayısıdır. Kalan bağımsız değişkenler, her ilke öğesi için anahtar-değer çiftleridir. Aşağıdaki örnek, üç ilke öğesini belirten bir `SchedulerPolicy` nesnesi oluşturur. Çalışma zamanı, belirtilen ilke anahtarları için varsayılan değerleri kullanır.

[!code-cpp[concrt-scheduler-policy#2](../../parallel/concrt/codesnippet/cpp/scheduler-policies_1.cpp)]

[Eşzamanlılık::P olicyElementKey](reference/concurrency-namespace-enums.md#policyelementkey) numaralandırması, Görev Zamanlayıcı ilişkili ilke anahtarlarını tanımlar. Aşağıdaki tabloda, ilke anahtarları ve çalışma zamanının her biri için kullandığı varsayılan değer açıklanmaktadır.

|İlke anahtarı|Açıklama|Varsayılan Değer|
|----------------|-----------------|-------------------|
|`SchedulerKind`|Görevleri zamanlamak için kullanılacak iş parçacıklarının türünü belirten bir [concurrency:: SchedulerType](reference/concurrency-namespace-enums.md#schedulertype) değeri.|`ThreadScheduler` (normal iş parçacıklarını kullanın). Bu anahtar için geçerli tek değer budur.|
|`MaxConcurrency`|Scheduler 'ın kullandığı en fazla eşzamanlılık kaynağı sayısını belirten bir `unsigned int` değeri.|[Eşzamanlılık:: MaxExecutionResources](reference/concurrency-namespace-constants1.md#maxexecutionresources)|
|`MinConcurrency`|Scheduler 'ın kullandığı en az eşzamanlılık kaynağı sayısını belirten bir `unsigned int` değeri.|`1`|
|`TargetOversubscriptionFactor`|Her bir işleme kaynağına ayrılacak iş parçacığı sayısını belirten bir `unsigned int` değeri.|`1`|
|`LocalContextCacheSize`|Her sanal işlemcinin yerel sırasında Önbelleğe alınabilecek en fazla bağlam sayısını belirten bir `unsigned int` değeri.|`8`|
|`ContextStackSize`|Her bağlam için ayrılacak yığın boyutunu kilobayt cinsinden belirten bir `unsigned int` değeri.|`0` (varsayılan yığın boyutunu kullanın)|
|`ContextPriority`|Her bağlamın iş parçacığı önceliğini belirten `int` değeri. Bu, [SetThreadPriority](/windows/win32/api/processthreadsapi/nf-processthreadsapi-setthreadpriority) veya `INHERIT_THREAD_PRIORITY`geçirebilmeniz için herhangi bir değer olabilir.|`THREAD_PRIORITY_NORMAL`|

|`SchedulingProtocol`| Kullanılacak zamanlama algoritmasını belirten bir [concurrency:: SchedulingProtocolType](reference/concurrency-namespace-enums.md#schedulingprotocoltype) değeri. |`EnhanceScheduleGroupLocality`| |`DynamicProgressFeedback`| [Tutarlılık::D ynamicprogressfeedbacktype](reference/concurrency-namespace-enums.md#dynamicprogressfeedbacktype) değeri, kaynakların istatistik tabanlı ilerleme bilgilerine göre yeniden dengelenmesi gerektiğini belirtir.<br /><br /> **Göz önünde** Çalışma zamanı tarafından kullanılmak üzere ayrıldığından, bu ilkeyi `ProgressFeedbackDisabled` olarak ayarlamayın. |`ProgressFeedbackEnabled`|

Her Zamanlayıcı, görevleri zamanlarken kendi ilkesini kullanır. Bir zamanlayıcı ile ilişkili ilkeler, başka bir Scheduler 'ın davranışını etkilemez. Ayrıca, `Scheduler` nesnesini oluşturduktan sonra zamanlayıcı ilkesini değiştiremezsiniz.

> [!IMPORTANT]
> Çalışma zamanının oluşturduğu iş parçacıklarının özniteliklerini denetlemek için yalnızca Zamanlayıcı ilkeleri kullanın. Çalışma zamanı tarafından oluşturulan iş parçacıklarının benzeşimini veya önceliğini değiştirmeyin, çünkü bu tanımsız davranışa neden olabilir.

Açıkça bir tane oluşturmadıysanız, çalışma zamanı sizin için varsayılan bir zamanlayıcı oluşturur. Uygulamanızda varsayılan zamanlayıcıyı kullanmak istiyorsanız, ancak bu Zamanlayıcı için kullanmak üzere bir ilke belirtmek istiyorsanız, paralel çalışmayı zamanlamadan önce [concurrency:: Scheduler:: SetDefaultSchedulerPolicy](reference/scheduler-class.md#setdefaultschedulerpolicy) yöntemini çağırın. `Scheduler::SetDefaultSchedulerPolicy` yöntemini çağırmayın, çalışma zamanı tablodaki varsayılan ilke değerlerini kullanır.

Zamanlayıcı ilkesinin bir kopyasını almak için [concurrency:: CurrentScheduler:: GetPolicy](reference/currentscheduler-class.md#getpolicy) ve [concurrency:: Scheduler:: GetPolicy](reference/scheduler-class.md#getpolicy) yöntemlerini kullanın. Bu yöntemlerden aldığınız ilke değerleri, Scheduler 'ı oluştururken belirttiğiniz ilke değerlerinden farklı olabilir.

## <a name="example"></a>Örnek

Scheduler 'ın davranışını denetlemek için belirli Zamanlayıcı ilkelerini kullanan örnekleri incelemek için bkz. [nasıl yapılır: belirli Zamanlayıcı Ilkeleri belirtme](../../parallel/concrt/how-to-specify-specific-scheduler-policies.md) ve [nasıl yapılır: belirli Zamanlayıcı Ilkelerini kullanan aracılar oluşturma](../../parallel/concrt/how-to-create-agents-that-use-specific-scheduler-policies.md).

## <a name="see-also"></a>Ayrıca bkz.

[Görev Zamanlayıcı](../../parallel/concrt/task-scheduler-concurrency-runtime.md)<br/>
[Nasıl yapılır: Belirli Zamanlayıcı İlkeleri Belirtme](../../parallel/concrt/how-to-specify-specific-scheduler-policies.md)<br/>
[Nasıl yapılır: Belirli Zamanlayıcı İlkelerini Kullanan Aracılar Oluşturma](../../parallel/concrt/how-to-create-agents-that-use-specific-scheduler-policies.md)
