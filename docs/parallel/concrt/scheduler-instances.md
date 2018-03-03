---
title: "Zamanlayıcı örnekleri | Microsoft Docs"
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
- scheduler instances
ms.assetid: 4819365f-ef99-49cc-963e-50a2a35a8d6b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1688a2b689b3fc3391e617f3d65d3c681f05a84f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="scheduler-instances"></a>Zamanlayıcı Örnekleri
Zamanlayıcı örnekleri eşzamanlılık çalışma zamanı ve nasıl kullanılacağını rolü bu belgeyi açıklanmaktadır [concurrency::Scheduler](../../parallel/concrt/reference/scheduler-class.md) ve [concurrency::CurrentScheduler](../../parallel/concrt/reference/currentscheduler-class.md) oluşturmak ve yönetmek için sınıflar Zamanlayıcı örnekleri. Zamanlayıcı örnekleri, belirli türde iş yükleri açık zamanlama ilkeleri ilişkilendirmek istediğinizde faydalıdır. Örneğin, yükseltilmiş iş parçacığı öncelikli olarak bazı görevleri çalıştırmak ve normal iş parçacığı öncelikli diğer görevleri çalıştırmak için varsayılan Zamanlayıcısı'nı kullanmak için bir zamanlayıcı örneğini oluşturabilirsiniz.  
  
> [!TIP]
>  Eşzamanlılık Çalışma zamanı varsayılan Zamanlayıcı sağlar ve bu nedenle, uygulamanızda oluşturmak için gerekli değildir. Görev Zamanlayıcısı'nı, uygulamalarınızın performansını ince ayar yardımcı olduğundan, ile başlamanızı öneririz [paralel Desen kitaplığı (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md) veya [zaman uyumsuz aracılar Kitaplığı](../../parallel/concrt/asynchronous-agents-library.md) kullanıyorsanız Eşzamanlılık Çalışma zamanı için yeni.  
  
##  <a name="top"></a>Bölümler  
  
-   [Zamanlayıcı ve CurrentScheduler sınıfları](#classes)  
  
-   [Zamanlayıcı örneğini oluşturma](#creating)  
  
-   [Zamanlayıcı örneğini kullanım süresini yönetme](#managing)  
  
-   [Yöntemleri ve özellikleri](#features)  
  
-   [Örnek](#example)  
  
##  <a name="classes"></a>Zamanlayıcı ve CurrentScheduler sınıfları  
 Görev Zamanlayıcısı'nı uygulamaların bir veya daha fazla kullanmasını sağlar *Zamanlayıcı örnekleri* çalışması zamanlamak için. [Concurrency::Scheduler](../../parallel/concrt/reference/scheduler-class.md) sınıf Zamanlayıcı örneğini temsil eder ve görev zamanlama için ilgili işlevselliği kapsar.  
  
 Bir zamanlayıcı bağlı bir iş parçacığı olarak bilinen bir *yürütme bağlamı*, veya yalnızca *bağlamı*. Bir zamanlayıcı herhangi bir zamanda geçerli bağlama göre etkin olabilir. Etkin Zamanlayıcı da denir *geçerli Zamanlayıcı*. Eşzamanlılık Çalışma zamanı kullanan [concurrency::CurrentScheduler](../../parallel/concrt/reference/currentscheduler-class.md) geçerli Zamanlayıcı erişim sağlamak için sınıf. Tek bağlam için geçerli Zamanlayıcı başka bir bağlam için geçerli Zamanlayıcı farklı olabilir. Çalışma zamanı geçerli Zamanlayıcı işlem düzeyinde gösterimini sağlamaz.  
  
 Genellikle, `CurrentScheduler` sınıfı, geçerli Zamanlayıcı erişmek için kullanılır. `Scheduler` Sınıfı, geçerli olmayan bir zamanlayıcı yönetmeniz gereken durumlarda yararlıdır.  
  
 Aşağıdaki bölümlerde nasıl oluşturulacağı ve Zamanlayıcı örneğini yönetme açıklanmaktadır. Bu görevleri gösteren tam bir örnek için bkz: [nasıl yapılır: Zamanlayıcı örneğini yönetme](../../parallel/concrt/how-to-manage-a-scheduler-instance.md).  
  
 [[Üst](#top)]  
  
##  <a name="creating"></a>Zamanlayıcı örneğini oluşturma  
 Oluşturmak için bu üç yolu bir `Scheduler` nesnesi:  
  
-   Hiçbir Zamanlayıcı varsa, çalışma zamanı işlerini yapmak için çalışma zamanı işlevselliği, örneğin, bir paralel algoritması kullandığınızda varsayılan Zamanlayıcı sizin için oluşturur. Varsayılan Zamanlayıcı paralel iş başlatır bağlamı için geçerli Zamanlayıcı olur.  
  

-   [Concurrency::CurrentScheduler::Create](reference/currentscheduler-class.md#create) yöntemi oluşturur bir `Scheduler` belirli bir ilke kullanır ve bu Zamanlayıcı geçerli bağlamla ilişkilendirir nesnesi.  
  
-   [Concurrency::Scheduler::Create](reference/scheduler-class.md#create) yöntemi oluşturur bir `Scheduler` belirli bir ilke kullanır, ancak geçerli bağlamla ilişkilendirmez nesnesi.  

  
 Varsayılan Zamanlayıcı oluşturma çalışma zamanı aynı Zamanlayıcı paylaşmak tüm eş zamanlı görevleri sağlar. Genellikle, tarafından sağlanan işlevselliği [paralel Desen kitaplığı](../../parallel/concrt/parallel-patterns-library-ppl.md) (PPL) veya [zaman uyumsuz aracılar Kitaplığı](../../parallel/concrt/asynchronous-agents-library.md) paralel iş gerçekleştirmek için kullanılır. Bu nedenle, kendi ilke veya ömrünü denetlemek için doğrudan Zamanlayıcısı ile çalışması gerekmez. PPL'de veya Aracılar Kitaplığı kullandığınızda, çalışma zamanı yok ve her bağlam için geçerli Zamanlayıcı kolaylaştırır varsayılan Zamanlayıcı oluşturur. Bir zamanlayıcı oluşturma ve geçerli Zamanlayıcı ayarladığınızda, çalışma zamanı görevleri zamanlamak için bu Zamanlayıcı kullanır. Yalnızca belirli bir zamanlama ilkesi gerektirdiğinde ek Zamanlayıcı örnekleri oluşturun. Bir Zamanlayıcı ile ilişkili ilkeleri hakkında daha fazla bilgi için bkz: [Zamanlayıcı ilkeleri](../../parallel/concrt/scheduler-policies.md).  
  
 [[Üst](#top)]  
  
##  <a name="managing"></a>Zamanlayıcı örneğini kullanım süresini yönetme  
 Çalışma zamanı ömrü denetlemek için bir başvuru sayımı mekanizması kullanır `Scheduler` nesneleri.  
  

 Kullandığınızda `CurrentScheduler::Create` yöntemi veya `Scheduler::Create` yöntemi oluşturmak için bir `Scheduler` nesnesi, çalışma zamanı için bu Zamanlayıcı ilk başvuru sayısı ayarlar. Çağırdığınızda çalışma zamanı başvuru sayısını artırır [concurrency::Scheduler::Attach](reference/scheduler-class.md#attach) yöntemi. `Scheduler::Attach` Yöntemi ilişkilendirilmiş bir `Scheduler` birlikte geçerli bağlam nesnesi. Bu, geçerli Zamanlayıcı kolaylaştırır. Çağırdığınızda `CurrentScheduler::Create` yöntemi, her iki çalışma oluşturur bir `Scheduler` nesne geçerli Bağlamla ekler (ve ayarlar başvuru sayısı için). Aynı zamanda [concurrency::Scheduler::Reference](reference/scheduler-class.md#reference) başvuru sayısını artırmak için yöntemi bir `Scheduler` nesnesi.  
  
 Başvuru sayım çağırdığınızda çalışma zamanı azaltır [concurrency::CurrentScheduler::Detach](reference/currentscheduler-class.md#detach) geçerli Zamanlayıcı ayırmak için yöntemi veya arama [concurrency::Scheduler::Release](reference/scheduler-class.md#release) yöntemi. Başvuru sayısı sıfır ulaştığında, çalışma zamanı yok eder `Scheduler` tüm zamanlanmış görevlerin Son'a nesnesi. Çalışan bir görev geçerli Zamanlayıcı başvuru sayısı Artır izin verilmez. Bu nedenle, başvuru sayısı sıfır ulaşana ve bir görev başvurusu sayısını artırır, çalışma zamanı yok `Scheduler` başvuru sayısı sıfır yeniden ulaştığında ve tüm görevler son kadar nesnesi.  

  
 Bir iç yığınını çalışma zamanı tutar `Scheduler` nesneler her bağlam için. Çağırdığınızda `Scheduler::Attach` veya `CurrentScheduler::Create` yöntemi, çalışma zamanı iter `Scheduler` geçerli bağlam için yığına nesnesi. Bu, geçerli Zamanlayıcı kolaylaştırır. Çağırdığınızda `CurrentScheduler::Detach`, çalışma zamanı geçerli bağlam için yığından geçerli Zamanlayıcı açılır ve önceki bir geçerli Zamanlayıcı olarak ayarlar.  
  
 Çalışma zamanı Zamanlayıcı örneğini ömrünü yönetmek için çeşitli yöntemler sağlar. Aşağıdaki tabloda, serbest veya Zamanlayıcı oluşturan veya geçerli bağlamda bir zamanlayıcı iliştirir her bir yöntemin geçerli bağlamdan ayırır uygun yöntemi gösterilir.  
  
|Oluşturma veya attach yöntemi|Serbest bırakma veya detach yöntemi|  
|-----------------------------|------------------------------|  
|`CurrentScheduler::Create`|`CurrentScheduler::Detach`|  
|`Scheduler::Create`|`Scheduler::Release`|  
|`Scheduler::Attach`|`CurrentScheduler::Detach`|  
|`Scheduler::Reference`|`Scheduler::Release`|  
  
 Uygunsuz çağırma yayın veya yöntem üretir belirtilmeyen davranışını çalışma zamanında ayırma.  
  
 İşlevselliği, örneğin, sizin için varsayılan Zamanlayıcı oluşturmak çalışma zamanı neden olur, PPL, kullandığınızda değil bırakın veya bu Zamanlayıcı ayırma. Çalışma zamanı oluşturduğu Zamanlayıcı ömrü yönetir.  
  

 Çalışma zamanı yok çünkü bir `Scheduler` kullanabileceğiniz tüm görevler bitirmeden nesne [concurrency::Scheduler::RegisterShutdownEvent](reference/scheduler-class.md#registershutdownevent) yöntemi veya [concurrency::CurrentScheduler:: RegisterShutdownEvent](reference/currentscheduler-class.md#registershutdownevent) yöntemi bir bildirim almak için bir `Scheduler` nesne yok. Tarafından zamanlanan her görev için beklemeniz gerekir gerektiğinde bu faydalıdır bir `Scheduler` tamamlamak için nesne.  
  
 [[Üst](#top)]  
  
##  <a name="features"></a>Yöntemleri ve özellikleri  
 Bu bölümde önemli yöntemlerini özetler `CurrentScheduler` ve `Scheduler` sınıfları.  
  
 Düşünün `CurrentScheduler` olarak kullanmak için bir zamanlayıcı geçerli bağlama göre oluşturmak için bir yardımcı sınıfı. `Scheduler` Sınıfı, başka bir bağlamına ait bir zamanlayıcı denetlemenize olanak sağlar.  
  
 Aşağıdaki tabloda tarafından tanımlanan önemli yöntemleri gösterir `CurrentScheduler` sınıfı.  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[Oluşturma](reference/currentscheduler-class.md#create)|Oluşturur bir `Scheduler` belirtilen ilke kullanır ve geçerli bağlamla ilişkilendirir nesnesi.|  
|[Al](reference/currentscheduler-class.md#get)|Bir işaretçi alır `Scheduler` geçerli bağlamla ilişkili nesne. Bu yöntem, başvuru sayımı artırmaz `Scheduler` nesnesi.|  
|[Detach](reference/currentscheduler-class.md#detach)|Geçerli bağlamdan geçerli Zamanlayıcı ayırır ve öncekinin geçerli Zamanlayıcı olarak ayarlar.|  
|[RegisterShutdownEvent](reference/currentscheduler-class.md#registershutdownevent)|Çalışma zamanı geçerli Zamanlayıcı bozulduğunda ayarlayan bir olay kaydeder.|  
|[CreateScheduleGroup](reference/currentscheduler-class.md#createschedulegroup)|Oluşturur bir [concurrency::ScheduleGroup](../../parallel/concrt/reference/schedulegroup-class.md) geçerli Zamanlayıcı nesne.|  
|[ScheduleTask](reference/currentscheduler-class.md#scheduletask)|Basit bir görev geçerli Zamanlayıcı zamanlama kuyruğuna ekler.|  
|[GetPolicy](reference/currentscheduler-class.md#getpolicy)|Geçerli Zamanlayıcı ile ilişkili ilke kopyasını alır.|  
  
 Aşağıdaki tabloda tarafından tanımlanan önemli yöntemleri gösterir `Scheduler` sınıfı.  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[Oluşturma](reference/scheduler-class.md#create)|Oluşturur bir `Scheduler` belirtilen ilke kullanan bir nesne.|  
|[Attach](reference/scheduler-class.md#attach)|İlişkilendirir `Scheduler` birlikte geçerli bağlam nesnesi.|  
|[Başvuru](reference/scheduler-class.md#reference)|Başvuru sayaç artırılır `Scheduler` nesnesi.|  
|[Sürüm](reference/scheduler-class.md#release)|Azaltır, başvuru sayaç `Scheduler` nesnesi.|  
|[RegisterShutdownEvent](reference/scheduler-class.md#registershutdownevent)|Çalışma zamanı ayarlar bir olay kaydeder `Scheduler` nesne yok.|  
|[CreateScheduleGroup](reference/scheduler-class.md#createschedulegroup)|Oluşturur bir [concurrency::ScheduleGroup](../../parallel/concrt/reference/schedulegroup-class.md) nesnesinde `Scheduler` nesnesi.|  
|[ScheduleTask](reference/scheduler-class.md#scheduletask)|Basit bir görevden zamanlar `Scheduler` nesnesi.|  
|[GetPolicy](reference/scheduler-class.md#getpolicy)|İle ilişkili ilke kopyasını alır `Scheduler` nesnesi.|  
|[SetDefaultSchedulerPolicy](reference/scheduler-class.md#setdefaultschedulerpolicy)|Varsayılan Zamanlayıcı oluşturduğunda, çalışma zamanı için ilke ayarlar.|  
|[ResetDefaultSchedulerPolicy](reference/scheduler-class.md#resetdefaultschedulerpolicy)|Çağırmadan önce etkin olan bir varsayılan ilkeyi yükler `SetDefaultSchedulerPolicy`. Sonra bu çağrı varsayılan Zamanlayıcı oluşturduysanız, çalışma zamanı Zamanlayıcı oluşturmak için varsayılan ilke ayarlarını kullanır.|  

  
 [[Üst](#top)]  
  
##  <a name="example"></a>Örnek  
 Oluşturma ve Zamanlayıcı örneğini yönetme temel örnekleri için bkz: [nasıl yapılır: Zamanlayıcı örneğini yönetme](../../parallel/concrt/how-to-manage-a-scheduler-instance.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Görev Zamanlayıcısı](../../parallel/concrt/task-scheduler-concurrency-runtime.md)   
 [Nasıl yapılır: Zamanlayıcı örneğini yönetme](../../parallel/concrt/how-to-manage-a-scheduler-instance.md)   
 [Zamanlayıcı ilkeleri](../../parallel/concrt/scheduler-policies.md)   
 [Zamanlama Grupları](../../parallel/concrt/schedule-groups.md)

