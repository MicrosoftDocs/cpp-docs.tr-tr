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
ms.openlocfilehash: 4fa61772af96ba0d2602ff42a6a43b2b3a13a4e6
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46385905"
---
# <a name="schedule-groups"></a>Zamanlama Grupları

Bu belge, zamanlama grupları eşzamanlılık çalışma zamanındaki rolünü açıklar. A *zamanlama grubu* affinitizes veya gruplara, ilgili görevleri birlikte. Her bir Zamanlayıcı, bir veya daha fazla zamanlama grupları vardır. İlgili görevleri bir grup olduğunda yerleşim yeri görevler arasında yüksek derecede gibi gerek duyduğunuzda kullanın zamanlama grupları, aynı işlemci düğümde yürütülmesini yararlanır. Buna karşılık, bir dizi görevi için ayrılan işlem kaynaklarının miktarını sınırlandırmak istediğinizde, uygulamanızın belirli kalite gereksinimleri, örneğin, sahip olduğunda Zamanlayıcı örnekleri kullanın. Zamanlayıcı örnekleri hakkında daha fazla bilgi için bkz: [Zamanlayıcı örnekleri](../../parallel/concrt/scheduler-instances.md).

> [!TIP]
>  Eşzamanlılık Çalışma zamanı varsayılan Zamanlayıcı sağlar ve bu nedenle, bir uygulama oluşturmak için gerekli değildir. Görev Zamanlayıcısı'nı, uygulamalarınızın performansını ayarlamanıza yardımcı olduğundan, ile başlamanızı öneririz [paralel desenler kitaplığı (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md) veya [zaman uyumsuz aracılar Kitaplığı](../../parallel/concrt/asynchronous-agents-library.md) kullanıyorsanız Yeni eşzamanlılık çalışma zamanı.

Her `Scheduler` nesnenin bir zamanlama her düğümü için varsayılan zamanlama grubu vardır. A *zamanlamayı* temel sistem topolojiye eşler. Çalışma zamanı her işlemci paket için bir zamanlama düğümü veya Tekdüzen olmayan bellek mimarisi (NUMA) düğümü oluşturur, hangi daha büyük bir sayıdır. Bir görev bir zamanlama grubu ile açıkça ilişkilendirmezseniz, Zamanlayıcı görevin ekleneceği hangi Grup seçer.

`SchedulingProtocol` Zamanlayıcı ilkesini Zamanlayıcı her zamanlama grubu görevleri yürütür sırasını etkiler. Zaman `SchedulingProtocol` ayarlanır `EnhanceScheduleGroupLocality` (varsayılan değer olan), Görev Zamanlayıcı'yı sonraki görev geçerli görev tamamlandığında veya işbirliği içerisinde devamlılığı verir, üzerinde çalışmakta olduğu zamanlama grubu seçer. Sonraki kullanılabilir gruba taşınmadan önce Görev Zamanlayıcı iş için geçerli zamanlama grubu arar. Buna karşılık, `SchedulingProtocol` ayarlanır `EnhanceForwardProgress`, her görev tamamlandığında veya verir sonra sonraki zamanlama grubu için Zamanlayıcı taşır. Bu ilkeler karşılaştıran bir örnek için bkz [nasıl yapılır: yürütme sırasını etkisi için zamanlama grupları kullanın](../../parallel/concrt/how-to-use-schedule-groups-to-influence-order-of-execution.md).

Çalışma zamanı kullanan [concurrency::ScheduleGroup](../../parallel/concrt/reference/schedulegroup-class.md) zamanlama grupları temsil eden sınıf. Oluşturmak için bir `ScheduleGroup` nesne, çağrı [concurrency::CurrentScheduler::CreateScheduleGroup](reference/currentscheduler-class.md#createschedulegroup) veya [concurrency::Scheduler::CreateScheduleGroup](reference/scheduler-class.md#createschedulegroup) yöntemi. Çalışma zamanı ömrünü denetlemek için bir başvuru sayım mekanizması kullanır. `ScheduleGroup` nesneleri ile çalıştığı gibi `Scheduler` nesneleri. Oluştururken bir `ScheduleGroup` nesnesi, çalışma zamanı başvurusu bir sayaç ayarlar. [Concurrency::ScheduleGroup::Reference](reference/schedulegroup-class.md#reference) yöntemi bir başvuru sayacını artırır. [Concurrency::ScheduleGroup::Release](reference/schedulegroup-class.md#release) yöntemi azaltır birer birer başvuru sayacı.

Eşzamanlılık Çalışma zamanındaki birçok türü bir zamanlama grubu ile birlikte bir nesne ilişkilendirmenizi sağlar. Örneğin, [concurrency::agent](../../parallel/concrt/reference/agent-class.md) sınıfı ve ileti bloğu sınıflar gibi [concurrency::unbounded_buffer](reference/unbounded-buffer-class.md), [concurrency::join](../../parallel/concrt/reference/join-class.md)ve eşzamanlılık::[ Zamanlayıcı](reference/timer-class.md), ele oluşturucu aşırı yüklenmiş sürümleri sağlar bir `ScheduleGroup` nesne. Çalışma zamanı kullanan `Scheduler` bununla ilişkili nesne `ScheduleGroup` görevi zamanlamak için nesne.

Ayrıca [concurrency::ScheduleGroup::ScheduleTask](reference/schedulegroup-class.md#scheduletask) hafif bir görevi zamanlamak için yöntemi. Basit görevler hakkında daha fazla bilgi için bkz: [Basit görevler](../../parallel/concrt/lightweight-tasks.md).

## <a name="example"></a>Örnek

Kullanan görev yürütme sırasını denetlemek için Grup zamanlamak ve bir örnek için bkz [nasıl yapılır: yürütme sırasını etkisi için zamanlama grupları kullanın](../../parallel/concrt/how-to-use-schedule-groups-to-influence-order-of-execution.md).

## <a name="see-also"></a>Ayrıca Bkz.

[Görev Zamanlayıcısı](../../parallel/concrt/task-scheduler-concurrency-runtime.md)<br/>
[Zamanlayıcı Örnekleri](../../parallel/concrt/scheduler-instances.md)<br/>
[Nasıl yapılır: Yürütme Sırasını Etkilemek için Zamanlama Grupları Kullanma](../../parallel/concrt/how-to-use-schedule-groups-to-influence-order-of-execution.md)

