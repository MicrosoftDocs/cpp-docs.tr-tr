---
title: Zamanlayıcı Örnekleri
ms.date: 11/04/2016
helpviewer_keywords:
- scheduler instances
ms.assetid: 4819365f-ef99-49cc-963e-50a2a35a8d6b
ms.openlocfilehash: 370f8a3a8fdcc8e1daaee2d3424f939fb719a449
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50570176"
---
# <a name="scheduler-instances"></a>Zamanlayıcı Örnekleri

Bu belge Zamanlayıcı örneğini eşzamanlılık çalışma zamanı ve nasıl kullanılacağını açıklar [concurrency::Scheduler](../../parallel/concrt/reference/scheduler-class.md) ve [concurrency::CurrentScheduler](../../parallel/concrt/reference/currentscheduler-class.md) oluşturmak ve yönetmek için sınıflar Zamanlayıcı örnekleri. Zamanlayıcı örnekleri açık zamanlama ilkeleri belirli türlerdeki iş yükleri ile ilişkilendirmek istediğiniz durumlarda kullanışlıdır. Örneğin, bir yükseltilmiş iş parçacığı önceliği bazı görevleri çalıştırmak ve diğer görevleri sırasında normal iş parçacığı önceliği çalıştırmak için varsayılan Zamanlayıcı kullanmak için bir zamanlayıcı örneğini oluşturabilirsiniz.

> [!TIP]
>  Eşzamanlılık Çalışma zamanı varsayılan Zamanlayıcı sağlar ve bu nedenle, bir uygulama oluşturmak için gerekli değildir. Görev Zamanlayıcısı'nı, uygulamalarınızın performansını ayarlamanıza yardımcı olduğundan, ile başlamanızı öneririz [paralel desenler kitaplığı (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md) veya [zaman uyumsuz aracılar Kitaplığı](../../parallel/concrt/asynchronous-agents-library.md) kullanıyorsanız Yeni eşzamanlılık çalışma zamanı.

##  <a name="top"></a> Bölümleri

- [CurrentScheduler sınıfları ve Zamanlayıcı](#classes)

- [Zamanlayıcı örneğini oluşturma](#creating)

- [Yaşam süresi Zamanlayıcı örneğini yönetme](#managing)

- [Yöntemleri ve özellikleri](#features)

- [Örnek](#example)

##  <a name="classes"></a> CurrentScheduler sınıfları ve Zamanlayıcı

Görev Zamanlayıcısı'nı bir veya daha fazla kullanmak uygulamaları etkinleştiren *Zamanlayıcı örnekleri* iş zamanlamak için. [Concurrency::Scheduler](../../parallel/concrt/reference/scheduler-class.md) sınıfı bir zamanlayıcı örneğini temsil eder ve görevleri zamanlamayla ilgili işlevselliğini kapsüller.

Bir zamanlayıcı için bağlı bir iş parçacığı olarak da bilinen bir *yürütme bağlamı*, veya yalnızca *bağlam*. Bir zamanlayıcı herhangi bir zamanda geçerli bağlam üzerinde etkin olabilir. Etkin olarak da bilinen zamanlayıcısının *geçerli Zamanlayıcı*. Eşzamanlılık Çalışma zamanı kullanan [concurrency::CurrentScheduler](../../parallel/concrt/reference/currentscheduler-class.md) sınıfı için geçerli Zamanlayıcı erişim sağlamak için. Tek bağlam için geçerli Zamanlayıcı başka bir bağlamı için geçerli Zamanlayıcı farklı olabilir. Çalışma zamanı, geçerli Zamanlayıcı işlem düzeyinde gösterimini sağlamaz.

Genellikle, `CurrentScheduler` sınıfı, geçerli Zamanlayıcı erişmek için kullanılır. `Scheduler` Sınıfı, geçerli olmayan bir Zamanlayıcı'yı yönetmek ihtiyacınız olduğunda yararlıdır.

Aşağıdaki bölümlerde, oluşturma ve Zamanlayıcı örneğini yönetme işlemleri açıklanmaktadır. Bu görevleri gösteren tam bir örnek için bkz. [nasıl yapılır: Zamanlayıcı örneğini yönetme](../../parallel/concrt/how-to-manage-a-scheduler-instance.md).

[[Üst](#top)]

##  <a name="creating"></a> Zamanlayıcı örneğini oluşturma

Oluşturmak için bu üç yolla bir `Scheduler` nesnesi:

- Hiçbir Zamanlayıcı varsa, çalışma zamanı işlerini yapmak için çalışma zamanı işlevselliği, örneğin, bir paralel algoritma kullandığınızda bir varsayılan Zamanlayıcı sizin için oluşturur. Paralel işi başlatan bağlamı için geçerli Zamanlayıcı varsayılan Zamanlayıcı olur.

- [Concurrency::CurrentScheduler::Create](reference/currentscheduler-class.md#create) yöntemi oluşturur bir `Scheduler` nesnesini belirli bir ilke kullanır ve bu Zamanlayıcı geçerli bağlam ile ilişkilendirir.

- [Concurrency::Scheduler::Create](reference/scheduler-class.md#create) yöntemi oluşturur bir `Scheduler` nesnesini belirli bir ilke kullanır, ancak geçerli bağlam ile ilişkilendirmez.

Aynı Zamanlayıcı paylaşmak tüm eş zamanlı görevleri bir varsayılan Zamanlayıcı oluşturmak çalışma zamanı sağlayabiliyor. Genellikle, tarafından sağlanan işlevselliği [paralel desenler Kitaplığı](../../parallel/concrt/parallel-patterns-library-ppl.md) (PPL) veya [zaman uyumsuz aracılar Kitaplığı](../../parallel/concrt/asynchronous-agents-library.md) paralel işi gerçekleştirmek için kullanılır. Bu nedenle, ilke veya ömrünü denetlemek için doğrudan Zamanlayıcı ile çalışmak zorunda değildir. PPL veya Aracılar Kitaplığı kullandığınızda, çalışma zamanı mevcut değil ve her bağlam için geçerli Zamanlayıcı kolaylaştırır varsayılan Zamanlayıcı oluşturur. Zamanlayıcı oluşturma ve geçerli bir zamanlayıcı ayarlayın, çalışma zamanı görevleri zamanlamak için bu Zamanlayıcı kullanır. Yalnızca belirli bir zamanlama ilkesi gerektirdiğinde ek Zamanlayıcı örnekleri oluşturun. Zamanlayıcı ile ilişkili olan ilkeleri hakkında daha fazla bilgi için bkz. [Zamanlayıcı ilkeleri](../../parallel/concrt/scheduler-policies.md).

[[Üst](#top)]

##  <a name="managing"></a> Yaşam süresi Zamanlayıcı örneğini yönetme

Çalışma zamanı ömrünü denetlemek için bir başvuru sayım mekanizması kullanır. `Scheduler` nesneleri.

Kullanırken `CurrentScheduler::Create` yöntemi veya `Scheduler::Create` yöntemi oluşturmak için bir `Scheduler` nesnesi, çalışma zamanı için bu Zamanlayıcı ilk başvuru sayısını ayarlar. Çağırdığınızda çalışma zamanı başvuru sayısını artırır [concurrency::Scheduler::Attach](reference/scheduler-class.md#attach) yöntemi. `Scheduler::Attach` Yöntemi ilişkilendirir `Scheduler` nesnesiyle birlikte geçerli bağlam. Bu, geçerli Zamanlayıcı kolaylaştırır. Çağırdığınızda `CurrentScheduler::Create` çalışma zamanı her iki yöntem, oluşturur bir `Scheduler` nesne ve bunu geçerli bağlam için ekler (ve ayarlar başvuru sayısı için). Ayrıca [concurrency::Scheduler::Reference](reference/scheduler-class.md#reference) başvuru sayısını artırmak için yöntemi bir `Scheduler` nesne.

Başvuru sayma çağırdığınızda çalışma zamanı azaltır [concurrency::CurrentScheduler::Detach](reference/currentscheduler-class.md#detach) geçerli Zamanlayıcı ayırmak için yöntemi veya çağrı [concurrency::Scheduler::Release](reference/scheduler-class.md#release) yöntemi. Başvuru sayısı sıfır ulaştığında, çalışma zamanı yok eder `Scheduler` tüm zamanlanmış görevleri son nesne. Çalışan bir görev geçerli Zamanlayıcı başvuru sayısını artırmak için kullanılabilir. Bu nedenle, bir görev başvuru sayısını artırır ve başvuru sayısı sıfır oluncaya, çalışma zamanı yok `Scheduler` tüm görevleri tamamlamak ve başvuru sayısı sıfır yeniden oluncaya kadar nesne.

Çalışma zamanı iç bir yığını korur `Scheduler` her bağlam için nesneleri. Çağırdığınızda `Scheduler::Attach` veya `CurrentScheduler::Create` metodu, çalışma zamanı gönderim `Scheduler` geçerli bağlam için yığına nesne. Bu, geçerli Zamanlayıcı kolaylaştırır. Çağırdığınızda `CurrentScheduler::Detach`, çalışma zamanı yığını geçerli bağlam için geçerli Zamanlayıcıdan POP ve öncekinin geçerli Zamanlayıcı olarak ayarlar.

Çalışma zamanı bir zamanlayıcı örneği ömrünü yönetmek için birçok yol sağlar. Aşağıdaki tablo sürümleri ya da Zamanlayıcı oluşturan veya geçerli bağlam için bir zamanlayıcı bağlayan her bir yöntemin geçerli bağlamdan çıkarır uygun yöntemi gösterir.

|Oluşturma veya attach yöntemi|Sürüm veya detach yöntemi|
|-----------------------------|------------------------------|
|`CurrentScheduler::Create`|`CurrentScheduler::Detach`|
|`Scheduler::Create`|`Scheduler::Release`|
|`Scheduler::Attach`|`CurrentScheduler::Detach`|
|`Scheduler::Reference`|`Scheduler::Release`|

Uygunsuz çağırma bırakın veya yöntem üretir belirtilmeyen davranışını çalışma zamanında ayırma.

Örneğin, sizin için varsayılan Zamanlayıcı oluşturmak çalışma zamanı neden PPL, işlevselliği kullandığınızda değil sürüm veya bu Zamanlayıcı ayırma. Çalışma zamanının oluşturduğu herhangi bir zamanlayıcı ömrünü yönetir.

Çalışma zamanı yok çünkü bir `Scheduler` kullanabileceğiniz tüm görevleri tamamladıktan önce nesne [concurrency::Scheduler::RegisterShutdownEvent](reference/scheduler-class.md#registershutdownevent) yöntemi veya [concurrency::CurrentScheduler:: RegisterShutdownEvent](reference/currentscheduler-class.md#registershutdownevent) yöntemi bir bildirim almak için bir `Scheduler` nesnesi yok edildiğinde. Tarafından zamanlanan her görev için beklemelisiniz gerektiğinde bu faydalıdır bir `Scheduler` tamamlamak için nesne.

[[Üst](#top)]

##  <a name="features"></a> Yöntemleri ve özellikleri

Bu bölümde önemli yöntemlerini özetler `CurrentScheduler` ve `Scheduler` sınıfları.

Düşünün `CurrentScheduler` olarak kullanmak için bir zamanlayıcı geçerli bağlamda oluşturmaya yönelik bir yardımcı sınıfı. `Scheduler` Sınıfı için başka bir bağlamın ait bir zamanlayıcı denetlemenize olanak tanır.

Aşağıdaki tabloda tanımlanır önemli yöntemler gösterilmektedir `CurrentScheduler` sınıfı.

|Yöntem|Açıklama|
|------------|-----------------|
|[Oluşturma](reference/currentscheduler-class.md#create)|Oluşturur bir `Scheduler` nesnesini belirtilen ilke kullanır ve bunu geçerli bağlam ile ilişkilendirir.|
|[Al](reference/currentscheduler-class.md#get)|Bir işaretçi alır `Scheduler` geçerli bağlam ile ilişkili olan nesne. Bu yöntem, başvuru sayısını artırmaz `Scheduler` nesne.|
|[Detach](reference/currentscheduler-class.md#detach)|Geçerli Zamanlayıcı geçerli bağlamdan çıkarır ve öncekinin geçerli Zamanlayıcı olarak ayarlar.|
|[RegisterShutdownEvent](reference/currentscheduler-class.md#registershutdownevent)|Geçerli Zamanlayıcı kaldırıldığında çalışma zamanı ayarlar bir olay kaydeder.|
|[CreateScheduleGroup](reference/currentscheduler-class.md#createschedulegroup)|Oluşturur bir [concurrency::ScheduleGroup](../../parallel/concrt/reference/schedulegroup-class.md) geçerli Zamanlayıcı nesnesi.|
|[ScheduleTask](reference/currentscheduler-class.md#scheduletask)|Basit bir görev geçerli Zamanlayıcı zamanlama kuyruğa ekler.|
|[GetPolicy](reference/currentscheduler-class.md#getpolicy)|Geçerli Zamanlayıcı ile ilişkili ilkeyi bir kopyasını alır.|

Aşağıdaki tabloda tanımlanır önemli yöntemler gösterilmektedir `Scheduler` sınıfı.

|Yöntem|Açıklama|
|------------|-----------------|
|[Oluşturma](reference/scheduler-class.md#create)|Oluşturur bir `Scheduler` belirtilen ilke kullanan bir nesne.|
|[Attach](reference/scheduler-class.md#attach)|İlişkilendirir `Scheduler` nesnesiyle birlikte geçerli bağlam.|
|[Başvuru](reference/scheduler-class.md#reference)|Başvuru sayaç artırılır `Scheduler` nesne.|
|[Sürüm](reference/scheduler-class.md#release)|Azaltır, başvuru sayaç `Scheduler` nesne.|
|[RegisterShutdownEvent](reference/scheduler-class.md#registershutdownevent)|Çalışma zamanı zaman ayarlayan bir olay kaydeder `Scheduler` nesnesi yok edildiğinde.|
|[CreateScheduleGroup](reference/scheduler-class.md#createschedulegroup)|Oluşturur bir [concurrency::ScheduleGroup](../../parallel/concrt/reference/schedulegroup-class.md) nesnesine `Scheduler` nesne.|
|[ScheduleTask](reference/scheduler-class.md#scheduletask)|Hafif bir görevi zamanlar `Scheduler` nesne.|
|[GetPolicy](reference/scheduler-class.md#getpolicy)|İlke ile ilişkili bir kopyasını alır `Scheduler` nesne.|
|[SetDefaultSchedulerPolicy](reference/scheduler-class.md#setdefaultschedulerpolicy)|Varsayılan Zamanlayıcı oluşturduğunda, kullanılacak çalışma zamanı ilkesini ayarlar.|
|[ResetDefaultSchedulerPolicy](reference/scheduler-class.md#resetdefaultschedulerpolicy)|Çağırmadan önce etkin olduğu bir varsayılan ilkeyi yükler `SetDefaultSchedulerPolicy`. Varsayılan Zamanlayıcı Bu çağrıdan sonra oluşturduysanız, çalışma zamanı Zamanlayıcı oluşturmak için varsayılan ilke ayarlarını kullanır.|

[[Üst](#top)]

##  <a name="example"></a> Örnek

Oluşturma ve Zamanlayıcı örneğini yönetme temel örnekler için bkz [nasıl yapılır: Zamanlayıcı örneğini yönetme](../../parallel/concrt/how-to-manage-a-scheduler-instance.md).

## <a name="see-also"></a>Ayrıca Bkz.

[Görev Zamanlayıcısı](../../parallel/concrt/task-scheduler-concurrency-runtime.md)<br/>
[Nasıl yapılır: Zamanlayıcı Örneğini Yönetme](../../parallel/concrt/how-to-manage-a-scheduler-instance.md)<br/>
[Scheduler İlkeleri](../../parallel/concrt/scheduler-policies.md)<br/>
[Zamanlama Grupları](../../parallel/concrt/schedule-groups.md)

