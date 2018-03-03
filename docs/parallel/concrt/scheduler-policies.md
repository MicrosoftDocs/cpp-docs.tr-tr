---
title: "Zamanlayıcı ilkeleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- scheduler policies
ms.assetid: 58fb68bd-4a57-40a8-807b-6edb6f083cd9
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6c2e669a429bebbfde19f54200610819d0849d8f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="scheduler-policies"></a>Scheduler İlkeleri
Bu belge eşzamanlılık çalışma zamanı Zamanlayıcı ilkeleri rolü açıklanmaktadır. A *Zamanlayıcı İlkesi* Zamanlayıcısı görevleri yönettiğinde kullanan stratejisi denetler. Örneğin, en yürütmek için bazı görevler gerektiren bir uygulama göz önünde bulundurun `THREAD_PRIORITY_NORMAL` ve diğer görevleri, yürütülecek `THREAD_PRIORITY_HIGHEST`.  İki Zamanlayıcı örnekleri oluşturabilirsiniz: belirten bir `ContextPriority` ilkenin `THREAD_PRIORITY_NORMAL` ve aynı ilkenin belirten başka `THREAD_PRIORITY_HIGHEST`.  
  
 Zamanlayıcı ilkeleri kullanarak, geçerli işlem kaynakları ayırın ve her Zamanlayıcı sabit bir kaynak kümesi atayın. Örneğin, dört işlemci ölçeklenmez paralel bir algoritma göz önünde bulundurun. Dörtten fazla işlemcileri aynı anda kullanmak için görevleri sınırlar bir zamanlayıcı ilkesi oluşturabilirsiniz.  
  
> [!TIP]
>  Eşzamanlılık Çalışma zamanı varsayılan Zamanlayıcı sağlar. Bu nedenle, uygulamanızda oluşturmak zorunda değilsiniz. Görev Zamanlayıcısı'nı, uygulamalarınızın performansını ince ayar yardımcı olduğundan, ile başlamanızı öneririz [paralel Desen kitaplığı (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md) veya [zaman uyumsuz aracılar Kitaplığı](../../parallel/concrt/asynchronous-agents-library.md) kullanıyorsanız Eşzamanlılık Çalışma zamanı için yeni.  
  
 Kullandığınızda [concurrency::CurrentScheduler::Create](reference/currentscheduler-class.md#create), [concurrency::Scheduler::Create](reference/scheduler-class.md#create), veya [concurrency::Scheduler::SetDefaultSchedulerPolicy](reference/scheduler-class.md#setdefaultschedulerpolicy) Sağladığınız bir zamanlayıcı örneğini oluşturmak için yöntemi bir [concurrency::SchedulerPolicy](../../parallel/concrt/reference/schedulerpolicy-class.md) Zamanlayıcı davranışını belirtmek anahtar-değer çiftleri koleksiyonu içeren nesne. `SchedulerPolicy` Oluşturucusu değişken sayıda bağımsız değişken alır. İlk bağımsız değişken hakkında bilgi belirtmek üzere olduğunuz ilke öğelerini sayısıdır. Her ilke öğesi için anahtar-değer çiftleri kalan bağımsız değişkenler. Aşağıdaki örnekte bir `SchedulerPolicy` üç ilke öğelerini belirtir nesnesi. Çalışma zamanı belirtilmedi İlkesi anahtarları için varsayılan değerleri kullanır.  

  
 [!code-cpp[concrt-scheduler-policy#2](../../parallel/concrt/codesnippet/cpp/scheduler-policies_1.cpp)]  
  

 [Concurrency::PolicyElementKey](reference/concurrency-namespace-enums.md#policyelementkey) numaralandırma Görev Zamanlayıcısı ile ilişkili olan ilke anahtarları tanımlar. Aşağıdaki tabloda, ilke anahtarları ve bunların her biri için çalışma zamanı kullanır varsayılan değer açıklanmaktadır.  
  
|İlke anahtarı|Açıklama|Varsayılan Değer|  
|----------------|-----------------|-------------------|  
|`SchedulerKind`|A [concurrency::SchedulerType](reference/concurrency-namespace-enums.md#schedulertype) görevleri zamanlamak için kullanılacak iş parçacıklarının türünü belirten değer.|`ThreadScheduler`(normal iş parçacığı kullanın). Bu anahtar için tek geçerli değer budur.|  
|`MaxConcurrency`|Bir `unsigned int` Zamanlayıcı kullandığı eşzamanlılık kaynaklarının sayısını belirten değer.|[CONCURRENCY::MaxExecutionResources](reference/concurrency-namespace-constants1.md#maxexecutionresources)|  
|`MinConcurrency`|Bir `unsigned int` Zamanlayıcı kullandığı eşzamanlılık kaynaklarının en az sayıda belirten değer.|`1`|  
|`TargetOversubscriptionFactor`|Bir `unsigned int` her işleme kaynak ayırmak için kaç tane iş parçacıkları belirten değer.|`1`|  
|`LocalContextCacheSize`|Bir `unsigned int` her sanal işlemci yerel sırada önbelleğe alınabilir bağlamları en fazla sayısını belirten değer.|`8`|  
|`ContextStackSize`|Bir `unsigned int` yığın boyutu kilobayt her bağlam için ayrılacak belirten değer.|`0`(varsayılan yığın boyutunu kullanın)|  
|`ContextPriority`|Bir `int` her bağlam iş parçacığı önceliğini belirten değer. Bu, geçirebilirsiniz herhangi bir değer olabilir [SetThreadPriority](http://msdn.microsoft.com/library/windows/desktop/ms686277) veya `INHERIT_THREAD_PRIORITY`.|`THREAD_PRIORITY_NORMAL`|  

|`SchedulingProtocol`| A [concurrency::SchedulingProtocolType](reference/concurrency-namespace-enums.md#schedulingprotocoltype) kullanılacak zamanlama algoritmayı belirten değer. |`EnhanceScheduleGroupLocality`|  
|`DynamicProgressFeedback`| A [concurrency::DynamicProgressFeedbackType](reference/concurrency-namespace-enums.md#dynamicprogressfeedbacktype) kaynakları istatistikleri tabanlı ilerleme durumu bilgileri göre yeniden dengelemeniz belirten değer.<br /><br /> **Not** Bu ilke ayarlanmamışsa `ProgressFeedbackDisabled` çalışma zamanı tarafından kullanılmak üzere ayrılmış olduğundan. |`ProgressFeedbackEnabled`|  

  
 Görevleri zamanlarken her Zamanlayıcı kendi İlkesi kullanır. Bir Zamanlayıcı ile ilişkili ilkeler, diğer bir zamanlayıcı davranışını etkilemez. Ayrıca, oluşturduktan sonra Zamanlayıcı İlkesi değiştirilemez `Scheduler` nesnesi.  
  
> [!IMPORTANT]
>  Çalışma zamanı oluşturur iş parçacığı özniteliklerini denetlemek için yalnızca Zamanlayıcı ilkeleri kullanın. İş parçacığı benzeşimini veya tanımsız davranış neden olabileceğinden çalışma zamanı tarafından oluşturulan iş parçacığı önceliği değiştirmeyin.  
  
 Çalışma zamanı, açıkça bir oluşturmazsanız varsayılan Zamanlayıcı sizin için oluşturur. Varsayılan Zamanlayıcı, uygulamanızda kullanmak istediğiniz ancak bir ilke kullanmak için arama bu Zamanlayıcı için belirtmek istediğiniz [concurrency::Scheduler::SetDefaultSchedulerPolicy](reference/scheduler-class.md#setdefaultschedulerpolicy) paralel iş zamanlama önce yöntemi. Değil çağırırsanız `Scheduler::SetDefaultSchedulerPolicy` yöntemi, varsayılan ilke değerleri tablosundan çalışma zamanı kullanır.  
  
 Kullanım [concurrency::CurrentScheduler::GetPolicy](reference/currentscheduler-class.md#getpolicy) ve [concurrency::Scheduler::GetPolicy](reference/scheduler-class.md#getpolicy) Zamanlayıcı İlkesi bir kopyasını almak için yöntemleri. Bu yöntemlerden aldığınız ilke değerleri Zamanlayıcı oluşturduğunuzda, belirttiğiniz ilke değerlerinden farklı olabilir.  
  
## <a name="example"></a>Örnek  
 Zamanlayıcı davranışını denetlemek için belirli Zamanlayıcı ilkelerini kullanan örnekler incelemek için bkz: [nasıl yapılır: belirli Zamanlayıcı ilkeleri belirtme](../../parallel/concrt/how-to-specify-specific-scheduler-policies.md) ve [nasıl yapılır: Bu kullanmak belirli Zamanlayıcı ilkeleriaracılarıoluşturma](../../parallel/concrt/how-to-create-agents-that-use-specific-scheduler-policies.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Görev Zamanlayıcısı](../../parallel/concrt/task-scheduler-concurrency-runtime.md)   
 [Nasıl yapılır: belirli Zamanlayıcı ilkeleri belirtme](../../parallel/concrt/how-to-specify-specific-scheduler-policies.md)   
 [Nasıl yapılır: Belirli Zamanlayıcı İlkelerini Kullanan Aracılar Oluşturma](../../parallel/concrt/how-to-create-agents-that-use-specific-scheduler-policies.md)

