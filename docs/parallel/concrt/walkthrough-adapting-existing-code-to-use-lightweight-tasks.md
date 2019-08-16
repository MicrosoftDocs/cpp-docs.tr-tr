---
title: 'İzlenecek yol: Mevcut kodu hafif görevleri kullanacak şekilde uyarlamak'
ms.date: 04/25/2019
helpviewer_keywords:
- using lightweight tasks [Concurrency Runtime]
- lightweight tasks, using [Concurrency Runtime]
ms.assetid: 1edfe818-d274-46de-bdd3-e92967c9bbe0
ms.openlocfilehash: 406d4d24d0042c7bded4f94dcef1e7731ab3947f
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69512157"
---
# <a name="walkthrough-adapting-existing-code-to-use-lightweight-tasks"></a>İzlenecek yol: Mevcut kodu hafif görevleri kullanacak şekilde uyarlamak

Bu konu başlığı altında, hafif bir görevi kullanmak üzere iş parçacığı oluşturmak ve yürütmek için Windows API kullanan mevcut kodların nasıl uyarlanyapılacağı gösterilmektedir.

*Hafif görev* , doğrudan bir [eşzamanlılık:: Scheduler](../../parallel/concrt/reference/scheduler-class.md) veya [concurrency:: ScheduleGroup](../../parallel/concrt/reference/schedulegroup-class.md) nesnesinden zamanladığınız bir görevdir. Basit görevler, Eşzamanlılık Çalışma Zamanı zamanlama işlevini kullanmak üzere mevcut kodu uyarlıyorsanız faydalıdır.

## <a name="prerequisites"></a>Önkoşullar

Bu yönergeyi başlamadan önce [Görev Zamanlayıcı](../../parallel/concrt/task-scheduler-concurrency-runtime.md)konusunu okuyun.

## <a name="example"></a>Örnek

### <a name="description"></a>Açıklama

Aşağıdaki örnek, bir iş parçacığı oluşturmak ve yürütmek için Windows API 'sinin tipik kullanımını gösterir. Bu örnek, `MyThreadFunction` öğesini ayrı bir iş parçacığında çağırmak için [CreateThread](/windows/win32/api/processthreadsapi/nf-processthreadsapi-createthread) işlevini kullanır.

### <a name="code"></a>Kod

[!code-cpp[concrt-windows-threads#1](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_1.cpp)]

### <a name="comments"></a>Açıklamalar

Bu örnek aşağıdaki çıktıyı üretir.

```Output
Parameters = 50, 100
```

Aşağıdaki adımlarda, aynı görevi gerçekleştirmek üzere Eşzamanlılık Çalışma Zamanı kullanmak için kod örneğini nasıl uyarlayabileceğiniz gösterilmektedir.

### <a name="to-adapt-the-example-to-use-a-lightweight-task"></a>Örneği basit bir görev kullanacak şekilde uyarlamak için

1. ConcRT `#include` . h üstbilgi dosyası için bir yönerge ekleyin.

[!code-cpp[concrt-migration-lwt#2](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_2.cpp)]

1. Ad`concurrency` alanı `using` için bir yönerge ekleyin.

[!code-cpp[concrt-migration-lwt#3](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_3.cpp)]

1. ' In `MyThreadFunction` bildirimini, `__cdecl` çağırma kuralını kullanacak ve döndürecek `void`şekilde değiştirin.

[!code-cpp[concrt-migration-lwt#4](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_4.cpp)]

1. Yapıyı, görevin tamamlandığı ana uygulamaya işaret eden bir [eşzamanlılık:: Event](../../parallel/concrt/reference/event-class.md) nesnesi içerecek şekilde değiştirin. `MyData`

[!code-cpp[concrt-migration-lwt#5](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_5.cpp)]

1. Çağrısını `CreateThread` [concurrency:: CurrentScheduler:: ScheduleTask](reference/currentscheduler-class.md#scheduletask) yöntemi çağrısıyla değiştirin.

[!code-cpp[concrt-migration-lwt#6](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_6.cpp)]

1. Çağrısını `WaitForSingleObject` , görevin bitmesini beklemek için [concurrency:: Event:: wait](reference/event-class.md#wait) yöntemine yönelik bir çağrı ile değiştirin.

[!code-cpp[concrt-migration-lwt#7](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_7.cpp)]

1. Çağrısını `CloseHandle`kaldırın.

1. Tanımın imzasını 3. adım ile eşleşecek `MyThreadFunction` şekilde değiştirin.

[!code-cpp[concrt-migration-lwt#8](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_8.cpp)]

9. `MyThreadFunction` İşlevin sonundaki [eşzamanlılık:: Event:: set](reference/event-class.md#set) metodunu, görevin bittiği ana uygulamaya işaret etmek için çağırın.

[!code-cpp[concrt-migration-lwt#9](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_9.cpp)]

10. `return` İfadesini öğesinden`MyThreadFunction`kaldırın.

## <a name="example"></a>Örnek

### <a name="description"></a>Açıklama

Aşağıdaki tamamlanan örnek, `MyThreadFunction` işlevini çağırmak için hafif bir görev kullanan kodu gösterir.

### <a name="code"></a>Kod

[!code-cpp[concrt-migration-lwt#1](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_10.cpp)]

### <a name="comments"></a>Açıklamalar

## <a name="see-also"></a>Ayrıca bkz.

[Görev Zamanlayıcı](../../parallel/concrt/task-scheduler-concurrency-runtime.md)<br/>
[Zamanlayıcı Sınıfı](../../parallel/concrt/reference/scheduler-class.md)
