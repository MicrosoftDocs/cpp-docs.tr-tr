---
title: Basit Görevler
ms.date: 11/04/2016
helpviewer_keywords:
- lightweight tasks
ms.assetid: b6dcfc7a-9fa9-4144-96a6-2845ea272017
ms.openlocfilehash: 19918cf73c2b5b03db895c4751b22b1666ce01de
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57326692"
---
# <a name="lightweight-tasks"></a>Basit Görevler

Bu belge, eşzamanlılık çalışma zamanındaki Basit görevler rolünü açıklar. A *basit görev* doğrudan zamanlama bir görev bir `concurrency::Scheduler` veya `concurrency::ScheduleGroup` nesne. Windows API için sağladığınız işlevi bir basit görev benzer [CreateThread](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-createthread) işlevi. Bu nedenle, Basit görevler eşzamanlılık çalışma zamanı zamanlama işlevselliğini kullanmak için mevcut kodu uyum olduğunda yararlıdır. Eşzamanlılık çalışma zamanının kendisi Basit görevler zaman uyumsuz aracılar zamanlayın ve arasında zaman uyumsuz ileti blokları ileti göndermek için kullanır.

> [!TIP]
>  Eşzamanlılık Çalışma zamanı varsayılan Zamanlayıcı sağlar ve bu nedenle, bir uygulama oluşturmak için gerekli değildir. Görev Zamanlayıcısı'nı, uygulamalarınızın performansını ayarlamanıza yardımcı olduğundan, ile başlamanızı öneririz [paralel desenler kitaplığı (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md) veya [zaman uyumsuz aracılar Kitaplığı](../../parallel/concrt/asynchronous-agents-library.md) kullanıyorsanız Yeni eşzamanlılık çalışma zamanı.

Basit görevler zaman uyumsuz aracılar ve görev gruplarını'den daha az ek yük getirir. Örneğin, çalışma zamanı, basit bir görev tamamlandığında bildirmekten değil. Ayrıca, çalışma zamanı catch veya desteklemez basit bir görevden oluşturulan özel durumları işleyin. Özel durum işleme ve Basit görevler hakkında daha fazla bilgi için bkz. [özel durum işleme](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md).

Çoğu görevi için görev grupları gibi daha sağlam işlevselliği kullanmak ve bunlar daha kolay sağlar çünkü paralel algoritmalar karmaşık görevleri daha temel parçalara bölün. öneririz. Görev grupları hakkında daha fazla bilgi için bkz. [görev Paralelliği](../../parallel/concrt/task-parallelism-concurrency-runtime.md). Paralel algoritmalar hakkında daha fazla bilgi için bkz. [paralel algoritmalar](../../parallel/concrt/parallel-algorithms.md).

Basit bir görev oluşturmak için arama [concurrency::ScheduleGroup::ScheduleTask](reference/schedulegroup-class.md#scheduletask), [concurrency::CurrentScheduler::ScheduleTask](reference/currentscheduler-class.md#scheduletask), veya [concurrency::Scheduler::ScheduleTask ](reference/scheduler-class.md#scheduletask) yöntemi. Bir hafif bir görevi tamamlamak için beklenecek kapatın veya eşitleme mekanizması gibi üst Zamanlayıcı için bekleyin. bir [concurrency::event](../../parallel/concrt/reference/event-class.md) nesne.

## <a name="example"></a>Örnek

Basit bir görev kullanmak için mevcut kodu uyum yapmayı gösteren bir örnek için bkz: [izlenecek yol: Mevcut kodu hafif görevleri kullanmaya uyarlama](../../parallel/concrt/walkthrough-adapting-existing-code-to-use-lightweight-tasks.md).

## <a name="see-also"></a>Ayrıca bkz.

[Görev Zamanlayıcısı](../../parallel/concrt/task-scheduler-concurrency-runtime.md)<br/>
[İzlenecek yol: Mevcut Kodu Hafif Görevleri Kullanmaya Uyarlama](../../parallel/concrt/walkthrough-adapting-existing-code-to-use-lightweight-tasks.md)
