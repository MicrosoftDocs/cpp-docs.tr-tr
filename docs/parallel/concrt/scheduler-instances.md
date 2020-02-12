---
title: Zamanlayıcı Örnekleri
ms.date: 11/04/2016
helpviewer_keywords:
- scheduler instances
ms.assetid: 4819365f-ef99-49cc-963e-50a2a35a8d6b
ms.openlocfilehash: e9e9b8124254084ac30191d37d49f2ef72bd677e
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77142287"
---
# <a name="scheduler-instances"></a>Zamanlayıcı Örnekleri

Bu belge, Eşzamanlılık Çalışma Zamanı Zamanlayıcı örneklerinin rolünü ve Zamanlayıcı örnekleri oluşturmak ve yönetmek için [concurrency:: Scheduler](../../parallel/concrt/reference/scheduler-class.md) ve [concurrency:: CurrentScheduler](../../parallel/concrt/reference/currentscheduler-class.md) sınıflarının nasıl kullanılacağını açıklar. Zamanlayıcı örnekleri, açık zamanlama ilkelerini belirli iş yükleri türleriyle ilişkilendirmek istediğinizde faydalıdır. Örneğin, bazı görevleri yükseltilmiş bir iş parçacığı önceliğinde çalıştırmak için bir zamanlayıcı örneği oluşturabilir ve varsayılan Zamanlayıcı 'yı kullanarak normal iş parçacığı önceliğinde diğer görevleri çalıştırabilirsiniz.

> [!TIP]
> Eşzamanlılık Çalışma Zamanı varsayılan bir Zamanlayıcı sağlar ve bu nedenle uygulamanızda bir tane oluşturmanız gerekmez. Görev Zamanlayıcı uygulamalarınızın performansını hassas bir şekilde ayarlamanıza yardımcı olduğundan, Eşzamanlılık Çalışma Zamanı yeni başladıysanız [paralel Desenler kitaplığı (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md) veya [zaman uyumsuz aracılar Kitaplığı](../../parallel/concrt/asynchronous-agents-library.md) ile başlamanız önerilir.

## <a name="top"></a>Başlıklı

- [Zamanlayıcı ve CurrentScheduler sınıfları](#classes)

- [Zamanlayıcı örneği oluşturma](#creating)

- [Zamanlayıcı örneğinin ömrünü yönetme](#managing)

- [Yöntemler ve Özellikler](#features)

- [Örnek](#example)

## <a name="classes"></a>Zamanlayıcı ve CurrentScheduler sınıfları

Görev Zamanlayıcı, uygulamaların işi zamanlamak için bir veya daha fazla *zamanlayıcı örneği* kullanmasına olanak sağlar. [Concurrency:: Scheduler](../../parallel/concrt/reference/scheduler-class.md) sınıfı bir zamanlayıcı örneğini temsil eder ve Zamanlama görevleriyle ilgili işlevselliği kapsüller.

Bir Scheduler 'a bağlı olan iş parçacığı, *yürütme bağlamı*veya yalnızca *bağlam*olarak bilinir. Bir zamanlayıcı, geçerli bağlamda dilediğiniz zaman etkin olabilir. Etkin Zamanlayıcı, *geçerli Zamanlayıcı*olarak da bilinir. Eşzamanlılık Çalışma Zamanı, geçerli Scheduler 'a erişim sağlamak için [concurrency:: CurrentScheduler](../../parallel/concrt/reference/currentscheduler-class.md) sınıfını kullanır. Bir bağlam için geçerli Zamanlayıcı, başka bir bağlam için geçerli Scheduler 'dan farklı olabilir. Çalışma zamanı, geçerli Scheduler 'ın işlem düzeyi gösterimini sağlamıyor.

Genellikle, `CurrentScheduler` sınıfı geçerli Scheduler 'a erişmek için kullanılır. `Scheduler` sınıfı, geçerli olmayan bir zamanlayıcıyı yönetmeniz gerektiğinde faydalıdır.

Aşağıdaki bölümlerde bir Zamanlayıcı örneğinin nasıl oluşturulacağı ve yönetileceği anlatılmaktadır. Bu görevleri gösteren bir örnek için bkz. [nasıl yapılır: zamanlayıcı örneğini yönetme](../../parallel/concrt/how-to-manage-a-scheduler-instance.md).

[[Üst](#top)]

## <a name="creating"></a>Zamanlayıcı örneği oluşturma

`Scheduler` nesne oluşturmanın üç yolu vardır:

- Zamanlayıcı yoksa çalışma zamanı, iş için bir paralel algoritma gibi çalışma zamanı işlevselliği kullandığınızda sizin için varsayılan bir zamanlayıcı oluşturur. Varsayılan Zamanlayıcı, paralel çalışmayı başlatan bağlam için geçerli Zamanlayıcı olur.

- [Concurrency:: CurrentScheduler:: Create](reference/currentscheduler-class.md#create) yöntemi, belirli bir ilkeyi kullanan ve bu Scheduler 'ı geçerli bağlamla ilişkilendiren bir `Scheduler` nesnesi oluşturur.

- [Concurrency:: Scheduler:: Create](reference/scheduler-class.md#create) yöntemi, belirli bir ilkeyi kullanan bir `Scheduler` nesnesi oluşturur, ancak onu geçerli içerikle ilişkilendirmez.

Çalışma zamanının varsayılan Zamanlayıcı oluşturmasına izin verilmesi, tüm eşzamanlı görevlerin aynı Zamanlayıcı 'yı paylaşmasını sağlar. Genellikle, paralel [desenler kitaplığı](../../parallel/concrt/parallel-patterns-library-ppl.md) (ppl) veya [zaman uyumsuz aracılar Kitaplığı](../../parallel/concrt/asynchronous-agents-library.md) tarafından belirtilen işlevsellik paralel çalışma gerçekleştirmek için kullanılır. Bu nedenle, ilke veya yaşam süresini denetlemek için Zamanlayıcı ile doğrudan çalışmanız gerekmez. PPL veya Agents kitaplığını kullandığınızda, çalışma zamanı yoksa varsayılan zamanlayıcıyı oluşturur ve her bağlam için geçerli Zamanlayıcı yapar. Bir Zamanlayıcı oluşturup geçerli Zamanlayıcı olarak ayarlarsanız, çalışma zamanı, görevleri zamanlamak için bu zamanlayıcıyı kullanır. Yalnızca belirli bir zamanlama ilkesine ihtiyacınız olduğunda ek Zamanlayıcı örnekleri oluşturun. Zamanlayıcı ile ilişkili ilkeler hakkında daha fazla bilgi için bkz. [Zamanlayıcı ilkeleri](../../parallel/concrt/scheduler-policies.md).

[[Üst](#top)]

## <a name="managing"></a>Zamanlayıcı örneğinin ömrünü yönetme

Çalışma zamanı `Scheduler` nesnelerinin ömrünü denetlemek için bir başvuru sayma mekanizması kullanır.

Bir `Scheduler` nesnesi oluşturmak için `CurrentScheduler::Create` yöntemini veya `Scheduler::Create` yöntemini kullandığınızda, çalışma zamanı bu zamanlayıcının ilk başvuru sayısını bir olarak ayarlar. [Concurrency:: Scheduler:: Attach](reference/scheduler-class.md#attach) metodunu çağırdığınızda çalışma zamanı başvuru sayısını artırır. `Scheduler::Attach` yöntemi, `Scheduler` nesnesini geçerli bağlamla birlikte ilişkilendirir. Bu, geçerli Zamanlayıcı yapar. `CurrentScheduler::Create` yöntemini çağırdığınızda, çalışma zamanının her ikisi de bir `Scheduler` nesnesi oluşturur ve geçerli içeriğe iliştirir (ve başvuru sayısını bir olarak ayarlar). Ayrıca, bir `Scheduler` nesnesinin başvuru sayısını artırmak için [concurrency:: Scheduler:: Reference](reference/scheduler-class.md#reference) yöntemini de kullanabilirsiniz.

Geçerli zamanlayıcıyı ayırmak için [concurrency:: CurrentScheduler::D etach](reference/currentscheduler-class.md#detach) metodunu çağırdığınızda çalışma zamanı, başvuru sayısını azaltır veya [concurrency:: Scheduler:: Release](reference/scheduler-class.md#release) yöntemini çağırır. Başvuru sayısı sıfıra ulaştığında, çalışma zamanı tüm zamanlanmış görevler bittikten sonra `Scheduler` nesnesini yok eder. Çalışan bir görevin, geçerli Scheduler 'ın başvuru sayısını arttırmasına izin verilir. Bu nedenle, başvuru sayısı sıfıra ulaşırsa ve bir görev başvuru sayısını artırıyorsa, çalışma zamanı, başvuru sayısı tekrar sıfır olana ve tüm görevler tamamlanıncaya kadar `Scheduler` nesnesini yok etmez.

Çalışma zamanı her bağlam için `Scheduler` nesnelerinin iç yığınını tutar. `Scheduler::Attach` veya `CurrentScheduler::Create` yöntemini çağırdığınızda, çalışma zamanı ilgili `Scheduler` nesnesini geçerli bağlam için yığına iter. Bu, geçerli Zamanlayıcı yapar. `CurrentScheduler::Detach`çağırdığınızda, çalışma zamanı geçerli bağlam için yığından geçerli zamanlayıcıyı ve önceki bir zamanlayıcıyı geçerli Zamanlayıcı olarak ayarlar.

Çalışma zamanı, bir Zamanlayıcı örneğinin ömrünü yönetmek için çeşitli yollar sağlar. Aşağıdaki tabloda, geçerli bağlamı bir Zamanlayıcı oluşturan veya bağlayan her yöntemin geçerli bağlamından Zamanlayıcı 'yı serbest bırakır veya ayırır.

|Oluşturma veya iliştirme yöntemi|Serbest bırakma veya ayırma yöntemi|
|-----------------------------|------------------------------|
|`CurrentScheduler::Create`|`CurrentScheduler::Detach`|
|`Scheduler::Create`|`Scheduler::Release`|
|`Scheduler::Attach`|`CurrentScheduler::Detach`|
|`Scheduler::Reference`|`Scheduler::Release`|

Uygunsuz yayın veya ayırma yönteminin çağrılması, çalışma zamanında belirtilmeyen bir davranış üretir.

Çalışma zamanının sizin için varsayılan zamanlayıcıyı oluşturmasına neden olan PPL gibi işlevleri kullandığınızda, bu zamanlayıcıyı serbest bırakma veya ayırma. Çalışma zamanı, oluşturduğu tüm zamanlayıcının ömrünü yönetir.

Çalışma zamanı tüm görevler tamamlanmadan önce bir `Scheduler` nesnesini yok etmez, bir `Scheduler` nesnesi yok edildiğinde bildirim almak için [concurrency:: Scheduler:: RegisterShutdownEvent](reference/scheduler-class.md#registershutdownevent) metodunu veya [concurrency:: CurrentScheduler:: RegisterShutdownEvent](reference/currentscheduler-class.md#registershutdownevent) metodunu kullanabilirsiniz. Bu, `Scheduler` nesnesi tarafından zamanlanan her görevin bitmesini beklemeniz gerektiğinde faydalıdır.

[[Üst](#top)]

## <a name="features"></a>Yöntemler ve Özellikler

Bu bölüm `CurrentScheduler` ve `Scheduler` sınıflarının önemli yöntemlerini özetler.

`CurrentScheduler` sınıfını, geçerli bağlamda kullanılmak üzere bir zamanlayıcı oluşturmak için yardımcı olarak düşünün. `Scheduler` sınıfı, başka bir bağlama ait olan bir zamanlayıcıyı denetlemenize olanak tanır.

Aşağıdaki tabloda `CurrentScheduler` sınıfı tarafından tanımlanan önemli Yöntemler gösterilmektedir.

|Yöntem|Açıklama|
|------------|-----------------|
|[Oluşturma](reference/currentscheduler-class.md#create)|Belirtilen ilkeyi kullanan bir `Scheduler` nesnesi oluşturur ve onu geçerli içerikle ilişkilendirir.|
|[Get](reference/currentscheduler-class.md#get)|Geçerli bağlamla ilişkili `Scheduler` nesnesine bir işaretçi alır. Bu yöntem `Scheduler` nesnesinin başvuru sayısını artırmaz.|
|[Detach](reference/currentscheduler-class.md#detach)|Geçerli bir zamanlayıcıyı geçerli bağlamdan ayırır ve önceki bir zamanlayıcıyı geçerli Zamanlayıcı olarak ayarlar.|
|[RegisterShutdownEvent](reference/currentscheduler-class.md#registershutdownevent)|Geçerli Zamanlayıcı yok edildiğinde çalışma zamanı kümelerinin bir olayını kaydeder.|
|[CreateScheduleGroup](reference/currentscheduler-class.md#createschedulegroup)|Geçerli zamanlayıcıda bir [concurrency:: ScheduleGroup](../../parallel/concrt/reference/schedulegroup-class.md) nesnesi oluşturur.|
|[ScheduleTask](reference/currentscheduler-class.md#scheduletask)|Geçerli Scheduler 'ın zamanlama kuyruğuna hafif bir görev ekler.|
|[GetPolicy](reference/currentscheduler-class.md#getpolicy)|Geçerli Scheduler ile ilişkili ilkenin bir kopyasını alır.|

Aşağıdaki tabloda `Scheduler` sınıfı tarafından tanımlanan önemli Yöntemler gösterilmektedir.

|Yöntem|Açıklama|
|------------|-----------------|
|[Oluşturma](reference/scheduler-class.md#create)|Belirtilen ilkeyi kullanan bir `Scheduler` nesnesi oluşturur.|
|[Attach](reference/scheduler-class.md#attach)|`Scheduler` nesnesini geçerli bağlamla birlikte ilişkilendirir.|
|[Başvuru](reference/scheduler-class.md#reference)|`Scheduler` nesnesinin başvuru sayacını artırır.|
|[Sürüm](reference/scheduler-class.md#release)|`Scheduler` nesnesinin başvuru sayacını azaltır.|
|[RegisterShutdownEvent](reference/scheduler-class.md#registershutdownevent)|`Scheduler` nesnesi yok edildiğinde çalışma zamanı kümelerinin bir olayını kaydeder.|
|[CreateScheduleGroup](reference/scheduler-class.md#createschedulegroup)|`Scheduler` nesnesinde bir [concurrency:: ScheduleGroup](../../parallel/concrt/reference/schedulegroup-class.md) nesnesi oluşturur.|
|[ScheduleTask](reference/scheduler-class.md#scheduletask)|`Scheduler` nesnesinden hafif bir görev zamanlar.|
|[GetPolicy](reference/scheduler-class.md#getpolicy)|`Scheduler` nesnesiyle ilişkili ilkenin bir kopyasını alır.|
|[SetDefaultSchedulerPolicy](reference/scheduler-class.md#setdefaultschedulerpolicy)|Çalışma zamanının varsayılan zamanlayıcıyı oluşturduğunda kullanacağı ilkeyi ayarlar.|
|[ResetDefaultSchedulerPolicy](reference/scheduler-class.md#resetdefaultschedulerpolicy)|`SetDefaultSchedulerPolicy`çağrısından önce varsayılan ilkeyi etkin olan birine geri yükler. Bu çağrıdan sonra varsayılan Zamanlayıcı oluşturulduysa, çalışma zamanı Scheduler 'ı oluşturmak için varsayılan ilke ayarlarını kullanır.|

[[Üst](#top)]

## <a name="example"></a>Örneğinde

Zamanlayıcı örneği oluşturma ve yönetme hakkında temel örnekler için bkz. [nasıl yapılır: zamanlayıcı örneğini yönetme](../../parallel/concrt/how-to-manage-a-scheduler-instance.md).

## <a name="see-also"></a>Ayrıca bkz.

[Görev Zamanlayıcı](../../parallel/concrt/task-scheduler-concurrency-runtime.md)<br/>
[Nasıl yapılır: Zamanlayıcı Örneğini Yönetme](../../parallel/concrt/how-to-manage-a-scheduler-instance.md)<br/>
[Scheduler İlkeleri](../../parallel/concrt/scheduler-policies.md)<br/>
[Zamanlama Grupları](../../parallel/concrt/schedule-groups.md)
