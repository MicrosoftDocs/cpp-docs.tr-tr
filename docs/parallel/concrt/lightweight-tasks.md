---
title: Basit Görevler
ms.date: 11/04/2016
helpviewer_keywords:
- lightweight tasks
ms.assetid: b6dcfc7a-9fa9-4144-96a6-2845ea272017
ms.openlocfilehash: be417052ffab19c1bc2d2ba6f35094f98e315812
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77141845"
---
# <a name="lightweight-tasks"></a>Basit Görevler

Bu belgede Eşzamanlılık Çalışma Zamanı basit görevlerinin rolü açıklanmaktadır. *Hafif görev* , doğrudan bir `concurrency::Scheduler` veya `concurrency::ScheduleGroup` nesnesinden zamanladığınız bir görevdir. Hafif bir görev, Windows API [CreateThread](/windows/win32/api/processthreadsapi/nf-processthreadsapi-createthread) işlevine sağladığınız işleve benzer. Bu nedenle, mevcut kodu Eşzamanlılık Çalışma Zamanı zamanlama işlevini kullanacak şekilde uyarlıyorsanız, hafif görevler faydalıdır. Eşzamanlılık Çalışma Zamanı, zaman uyumsuz aracıları zamanlamak ve zaman uyumsuz ileti blokları arasında ileti göndermek için basit görevleri kullanır.

> [!TIP]
> Eşzamanlılık Çalışma Zamanı varsayılan bir Zamanlayıcı sağlar ve bu nedenle uygulamanızda bir tane oluşturmanız gerekmez. Görev Zamanlayıcı uygulamalarınızın performansını hassas bir şekilde ayarlamanıza yardımcı olduğundan, Eşzamanlılık Çalışma Zamanı yeni başladıysanız [paralel Desenler kitaplığı (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md) veya [zaman uyumsuz aracılar Kitaplığı](../../parallel/concrt/asynchronous-agents-library.md) ile başlamanız önerilir.

Hafif görevler, zaman uyumsuz aracılardan ve görev gruplarından daha az ek yük taşır. Örneğin, bir hafif görev tamamlandığında çalışma zamanı sizi bilgilendirmez. Ayrıca, çalışma zamanı, hafif bir görevden oluşturulan özel durumları yakalayamaz veya işlemez. Özel durum işleme ve hafif görevler hakkında daha fazla bilgi için bkz. [özel durum işleme](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md).

Birçok görev için görev grupları ve paralel algoritmalar gibi daha güçlü işlevler kullanmanızı öneririz, çünkü karmaşık görevleri daha basit bir hale yenilerini daha kolay bir şekilde bozabilmenizi sağlar. Görev grupları hakkında daha fazla bilgi için bkz. [Görev Paralelliği](../../parallel/concrt/task-parallelism-concurrency-runtime.md). Paralel algoritmalar hakkında daha fazla bilgi için bkz. [paralel algoritmalar](../../parallel/concrt/parallel-algorithms.md).

Hafif bir görev oluşturmak için [concurrency:: ScheduleGroup:: ScheduleTask](reference/schedulegroup-class.md#scheduletask), [concurrency:: CurrentScheduler::](reference/currentscheduler-class.md#scheduletask)ScheduleTask veya [concurrency:: Scheduler:: ScheduleTask](reference/scheduler-class.md#scheduletask) metodunu çağırın. Hafif bir görevin bitmesini beklemek için, üst Scheduler 'ın kapatılmasını bekleyin veya [eşzamanlılık:: olay](../../parallel/concrt/reference/event-class.md) nesnesi gibi bir eşitleme mekanizması kullanın.

## <a name="example"></a>Örnek

Var olan kodun hafif bir görevi kullanmak üzere nasıl uyarlanacağını gösteren bir örnek için, bkz. [Izlenecek yol: mevcut kodu hafif görevleri kullanacak şekilde uyarlayın](../../parallel/concrt/walkthrough-adapting-existing-code-to-use-lightweight-tasks.md).

## <a name="see-also"></a>Ayrıca bkz.

[Görev Zamanlayıcı](../../parallel/concrt/task-scheduler-concurrency-runtime.md)<br/>
[İzlenecek Yol: Mevcut Kodu Hafif Görevleri Kullanmaya Uyarlama](../../parallel/concrt/walkthrough-adapting-existing-code-to-use-lightweight-tasks.md)
