---
title: Zamanlayıcı ilkeleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- scheduler policies
ms.assetid: 58fb68bd-4a57-40a8-807b-6edb6f083cd9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: dbf9bb9fdbd930319147bfa2654915243fb8dd6a
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43219312"
---
# <a name="scheduler-policies"></a>Scheduler İlkeleri
Bu belge, Zamanlayıcı ilkeleri eşzamanlılık çalışma zamanındaki rolünü açıklar. A *Zamanlayıcı ilkesini* görevleri yönettiğinde, Zamanlayıcı kullanan stratejisi denetler. Örneğin, en yürütmek için bazı görevler gerektiren bir uygulamayı düşünün `THREAD_PRIORITY_NORMAL` ve diğer görevleri, yürütülecek `THREAD_PRIORITY_HIGHEST`.  İki Zamanlayıcı örnekleri oluşturabilirsiniz: belirten bir `ContextPriority` ilkenin `THREAD_PRIORITY_NORMAL` olmasını aynı ilkeyi belirten başka `THREAD_PRIORITY_HIGHEST`.  
  
 Zamanlayıcı ilkeleri kullanarak, geçerli işlem kaynakları ayırmak ve sabit bir kaynak kümesi için her bir zamanlayıcı atayın. Örneğin, dört işlemci ölçeklenmez bir paralel algoritma göz önünde bulundurun. Dörtten fazla işlemci eşzamanlı olarak kullanmak için kendi görevlerini sınırlandıran bir zamanlayıcı ilkesi oluşturabilirsiniz.  
  
> [!TIP]
>  Eşzamanlılık Çalışma zamanı varsayılan Zamanlayıcı sağlar. Bu nedenle, bir uygulama oluşturmanız gerekmez. Görev Zamanlayıcısı'nı, uygulamalarınızın performansını ayarlamanıza yardımcı olduğundan, ile başlamanızı öneririz [paralel desenler kitaplığı (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md) veya [zaman uyumsuz aracılar Kitaplığı](../../parallel/concrt/asynchronous-agents-library.md) kullanıyorsanız Yeni eşzamanlılık çalışma zamanı.  
  
 Kullanırken [concurrency::CurrentScheduler::Create](reference/currentscheduler-class.md#create), [concurrency::Scheduler::Create](reference/scheduler-class.md#create), veya [concurrency::Scheduler::SetDefaultSchedulerPolicy](reference/scheduler-class.md#setdefaultschedulerpolicy) Sağladığınız bir zamanlayıcı örneğini oluşturmak için yöntemi bir [concurrency::SchedulerPolicy](../../parallel/concrt/reference/schedulerpolicy-class.md) Zamanlayıcı davranışını belirten bir anahtar-değer çiftleri koleksiyonu içeren nesne. `SchedulerPolicy` Oluşturucusu, değişken sayıda bağımsız değişken alır. İlk bağımsız değişken hakkında belirtmek için olan ilke öğeler sayısıdır. Kalan bağımsız değişkenleri, her ilke için anahtar-değer çiftleridir. Aşağıdaki örnek, oluşturur bir `SchedulerPolicy` üç ilke öğelerini belirten bir nesne. Çalışma zamanı belirtilmemiş ilke anahtarları için varsayılan değerleri kullanır.  

  
 [!code-cpp[concrt-scheduler-policy#2](../../parallel/concrt/codesnippet/cpp/scheduler-policies_1.cpp)]  
  

 [Concurrency::PolicyElementKey](reference/concurrency-namespace-enums.md#policyelementkey) Görev Zamanlayıcısı ile ilişkili ilke anahtarları sabit listesi tanımlar. Aşağıdaki tabloda, ilke anahtarları ve bunların her biri için çalışma zamanı kullanan varsayılan değer açıklar.  
  
|İlke anahtarı|Açıklama|Varsayılan Değer|  
|----------------|-----------------|-------------------|  
|`SchedulerKind`|A [concurrency::SchedulerType](reference/concurrency-namespace-enums.md#schedulertype) görevleri zamanlamak için kullanılacak iş parçacığı türünü belirten bir değer.|`ThreadScheduler` (normal iş parçacığı kullanın). Bu anahtar için geçerli olan tek değer budur.|  
|`MaxConcurrency`|Bir `unsigned int` Zamanlayıcı tarafından kullanılan kaynakları eşzamanlılık maksimum sayısını belirten bir değer.|[CONCURRENCY::MaxExecutionResources](reference/concurrency-namespace-constants1.md#maxexecutionresources)|  
|`MinConcurrency`|Bir `unsigned int` Zamanlayıcı tarafından kullanılan eşzamanlılık kaynakları en az sayısını belirten bir değer.|`1`|  
|`TargetOversubscriptionFactor`|Bir `unsigned int` için her işleme kaynağı ayırmak için kaç iş parçacıkları belirten bir değer.|`1`|  
|`LocalContextCacheSize`|Bir `unsigned int` her sanal işlemci yerel kuyrukta önbelleğe bağlamlarının en fazla sayısını belirten bir değer.|`8`|  
|`ContextStackSize`|Bir `unsigned int` her bağlam için ayrılacak kilobayt cinsinden yığın boyutunu belirten bir değer.|`0` (varsayılan yığın boyutu kullanın)|  
|`ContextPriority`|Bir `int` her bağlam iş parçacığının önceliğini belirten bir değer. Bu iletebileceğiniz herhangi bir değer olabilir [SetThreadPriority](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-setthreadpriority) veya `INHERIT_THREAD_PRIORITY`.|`THREAD_PRIORITY_NORMAL`|  

|`SchedulingProtocol`| A [concurrency::SchedulingProtocolType](reference/concurrency-namespace-enums.md#schedulingprotocoltype) kullanılacak zamanlama algoritmasını belirten bir değer. |`EnhanceScheduleGroupLocality`|  
|`DynamicProgressFeedback`| A [concurrency::DynamicProgressFeedbackType](reference/concurrency-namespace-enums.md#dynamicprogressfeedbacktype) istatistikleri tabanlı ilerleme bilgilerini göre kaynakları yeniden Dengeleme belirten değer.<br /><br /> **Not** Bu ilke ayarlanmamışsa `ProgressFeedbackDisabled` çalışma zamanı tarafından kullanılmak üzere ayrılmış olduğundan. |`ProgressFeedbackEnabled`|  

  
 Her bir zamanlayıcı görevleri zamanlar kendi İlkesi kullanır. Bir Zamanlayıcı ile ilişkili olan ilkeler, diğer bir zamanlayıcı davranışını etkilemez. Ayrıca, oluşturduktan sonra Zamanlayıcı ilkesini değiştiremezsiniz `Scheduler` nesne.  
  
> [!IMPORTANT]
>  Çalışma zamanını oluşturan iş parçacığı özniteliklerini kontrol etmek için yalnızca Zamanlayıcı ilkeleri kullanın. İş parçacığı benzeşimini veya tanımsız davranışa neden, çalışma zamanı tarafından oluşturulan iş parçacığı önceliği değiştirmeyin.  
  
 Siz açıkça bir oluşturmazsanız çalışma zamanı bir varsayılan Zamanlayıcı sizin için oluşturur. Varsayılan Zamanlayıcı uygulamanızda kullanmak istediğiniz ancak bir ilke kullanmak için arama, Zamanlayıcı için belirtmek istediğiniz [concurrency::Scheduler::SetDefaultSchedulerPolicy](reference/scheduler-class.md#setdefaultschedulerpolicy) paralel iş zamanlama önce yöntemi. Değil çağırırsanız `Scheduler::SetDefaultSchedulerPolicy` yöntemi, varsayılan ilke değerlerini tablodan çalışma zamanı kullanır.  
  
 Kullanım [concurrency::CurrentScheduler::GetPolicy](reference/currentscheduler-class.md#getpolicy) ve [concurrency::Scheduler::GetPolicy](reference/scheduler-class.md#getpolicy) Zamanlayıcı ilkesini bir kopyasını almak için yöntemler. Bu yöntemleri aldığınız ilke değerleri, scheduler'ı oluşturduğunuzda, belirttiğiniz ilke değerlerden farklı olabilir.  
  
## <a name="example"></a>Örnek  
 Zamanlayıcı davranışını denetlemek için belirli Zamanlayıcı ilkelerini kullanan örnekleri incelemek için bkz: [nasıl yapılır: belirli Zamanlayıcı ilkeleri belirtme](../../parallel/concrt/how-to-specify-specific-scheduler-policies.md) ve [nasıl yapılır: Bu kullanmak belirli Zamanlayıcı ilkeleriaracılarıoluşturma](../../parallel/concrt/how-to-create-agents-that-use-specific-scheduler-policies.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Görev Zamanlayıcısı](../../parallel/concrt/task-scheduler-concurrency-runtime.md)   
 [Nasıl yapılır: belirli Zamanlayıcı ilkeleri belirtme](../../parallel/concrt/how-to-specify-specific-scheduler-policies.md)   
 [Nasıl yapılır: Belirli Zamanlayıcı İlkelerini Kullanan Aracılar Oluşturma](../../parallel/concrt/how-to-create-agents-that-use-specific-scheduler-policies.md)

