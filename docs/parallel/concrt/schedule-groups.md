---
title: Zamanlama grupları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- schedule groups
ms.assetid: 03523572-5891-4d17-89ce-fa795605f28b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c1395fbc58d8a4d1d06cd93eea21c0f3d2dec8c6
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33688797"
---
# <a name="schedule-groups"></a>Zamanlama Grupları
Bu belge eşzamanlılık çalışma zamanı, zamanlama grupları rolü açıklanmaktadır. A *zamanlama grup* affinitizes ya da grupları, ilgili görevleri birlikte. Her Zamanlayıcı, bir veya daha fazla zamanlama grupları vardır. İlgili görevleri grubunu zaman yere göre görevleri arasında yüksek derecede Örneğin, gerekirse, kullanım zamanlama grupları aynı işlemci düğümde yürütülen yararlanır. Buna karşılık, bir dizi görevi için ayrılan işlem kaynaklarının miktarını sınırlamak istediğinizde, uygulamanızın belirli kalitesi gereksinimleri, örneğin, sahip olduğunda Zamanlayıcı örnekleri kullanın. Zamanlayıcı örnekleri hakkında daha fazla bilgi için bkz: [Zamanlayıcı örnekleri](../../parallel/concrt/scheduler-instances.md).  
  
> [!TIP]
>  Eşzamanlılık Çalışma zamanı varsayılan Zamanlayıcı sağlar ve bu nedenle, uygulamanızda oluşturmak için gerekli değildir. Görev Zamanlayıcısı'nı, uygulamalarınızın performansını ince ayar yardımcı olduğundan, ile başlamanızı öneririz [paralel Desen kitaplığı (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md) veya [zaman uyumsuz aracılar Kitaplığı](../../parallel/concrt/asynchronous-agents-library.md) kullanıyorsanız Eşzamanlılık Çalışma zamanı için yeni.  
  
 Her `Scheduler` nesnesi zamanlama her düğüm için varsayılan bir zamanlama grubu sahiptir. A *düğümü zamanlama* temel sistem topolojiye eşler. Çalışma zamanı her işlemci paket için bir zamanlama düğümü veya Tekdüzen olmayan bellek mimarisi (NUMA) düğümü oluşturur, hangisi daha büyük bir sayıdır. Açıkça bir görev zamanlama grubu ile ilişkilendirmek, Zamanlayıcı görevi eklemek için hangi Grup seçer.  
  
 `SchedulingProtocol` Zamanlayıcı İlkesi Zamanlayıcı her zamanlama grubu görevleri yürütür sipariş etkiler. Zaman `SchedulingProtocol` ayarlanır `EnhanceScheduleGroupLocality` (varsayılan değer olan), geçerli görev tamamlandıktan veya işlevinizde verir, üzerinde çalıştığı zamanlama grubundan sonraki görev Görev Zamanlayıcısı'nı seçer. Sonraki kullanılabilir grubuna gitmeden önce Görev Zamanlayıcı iş için geçerli zamanlama grubu arar. Buna karşılık, ne zaman `SchedulingProtocol` ayarlanır `EnhanceForwardProgress`, her görevin sonlandığında veya verir Zamanlayıcı sonraki zamanlama grubuna taşınır. Bu ilkeler karşılaştıran bir örnek için bkz: [nasıl yapılır: kullanım zamanlama grupları, etkisi sipariş yürütme için](../../parallel/concrt/how-to-use-schedule-groups-to-influence-order-of-execution.md).  
  

 Çalışma zamanı kullanır [concurrency::ScheduleGroup](../../parallel/concrt/reference/schedulegroup-class.md) zamanlama grupları temsil eden sınıf. Oluşturmak için bir `ScheduleGroup` nesne, çağrı [concurrency::CurrentScheduler::CreateScheduleGroup](reference/currentscheduler-class.md#createschedulegroup) veya [concurrency::Scheduler::CreateScheduleGroup](reference/scheduler-class.md#createschedulegroup) yöntemi. Çalışma zamanı ömrü denetlemek için bir başvuru sayımı mekanizması kullanır `ScheduleGroup` , birlikte çalıştığı gibi nesneleri `Scheduler` nesneleri. Oluştururken bir `ScheduleGroup` nesnesi, çalışma zamanı başvuru bir sayaç ayarlar. [Concurrency::ScheduleGroup::Reference](reference/schedulegroup-class.md#reference) yöntemi tarafından başvuru sayacı artırır. [Concurrency::ScheduleGroup::Release](reference/schedulegroup-class.md#release) yöntemi azaltır başvuru sayaç.  
  
 Eşzamanlılık Çalışma zamanı birçok türlerinde bir zamanlama grubu ile birlikte bir nesne ilişkilendirmenizi sağlar. Örneğin, [concurrency::agent](../../parallel/concrt/reference/agent-class.md) sınıfı ve ileti bloğu sınıfları gibi [concurrency::unbounded_buffer](reference/unbounded-buffer-class.md), [concurrency::join](../../parallel/concrt/reference/join-class.md)ve eşzamanlılık::[ Zamanlayıcı](reference/timer-class.md), ele aşırı yüklü Oluşturucu sürümü sağlayan bir `ScheduleGroup` nesnesi. Çalışma zamanı kullanır `Scheduler` bu ile ilişkili olan nesne `ScheduleGroup` görevi zamanlamak için nesne.  
  
 Aynı zamanda [concurrency::ScheduleGroup::ScheduleTask](reference/schedulegroup-class.md#scheduletask) basit bir görev zamanlama yöntemi. Basit görevler hakkında daha fazla bilgi için bkz: [Basit görevler](../../parallel/concrt/lightweight-tasks.md).  

  
## <a name="example"></a>Örnek  
 Kullandığı görev yürütme sırasını denetlemek için Grup zamanlama bir örnek için bkz: [nasıl yapılır: kullanım zamanlama grupları, etkisi sipariş yürütme için](../../parallel/concrt/how-to-use-schedule-groups-to-influence-order-of-execution.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Görev Zamanlayıcısı](../../parallel/concrt/task-scheduler-concurrency-runtime.md)   
 [Zamanlayıcı örnekleri](../../parallel/concrt/scheduler-instances.md)   
 [Nasıl yapılır: Yürütme Sırasını Etkilemek için Zamanlama Grupları Kullanma](../../parallel/concrt/how-to-use-schedule-groups-to-influence-order-of-execution.md)

