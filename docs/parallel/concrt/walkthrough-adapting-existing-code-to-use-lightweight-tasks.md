---
title: 'İzlenecek yol: Mevcut Kodu Hafif Görevleri Kullanmaya Uyarlama'
ms.date: 04/25/2019
helpviewer_keywords:
- using lightweight tasks [Concurrency Runtime]
- lightweight tasks, using [Concurrency Runtime]
ms.assetid: 1edfe818-d274-46de-bdd3-e92967c9bbe0
ms.openlocfilehash: 7ce18b54835b2380d3baee77b00a670351e3279f
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87224922"
---
# <a name="walkthrough-adapting-existing-code-to-use-lightweight-tasks"></a>İzlenecek yol: Mevcut Kodu Hafif Görevleri Kullanmaya Uyarlama

Bu konu başlığı altında, hafif bir görevi kullanmak üzere iş parçacığı oluşturmak ve yürütmek için Windows API kullanan mevcut kodların nasıl uyarlanyapılacağı gösterilmektedir.

*Hafif görev* , doğrudan bir [eşzamanlılık:: Scheduler](../../parallel/concrt/reference/scheduler-class.md) veya [concurrency:: ScheduleGroup](../../parallel/concrt/reference/schedulegroup-class.md) nesnesinden zamanladığınız bir görevdir. Basit görevler, Eşzamanlılık Çalışma Zamanı zamanlama işlevini kullanmak üzere mevcut kodu uyarlıyorsanız faydalıdır.

## <a name="prerequisites"></a>Önkoşullar

Bu yönergeyi başlamadan önce [Görev Zamanlayıcı](../../parallel/concrt/task-scheduler-concurrency-runtime.md)konusunu okuyun.

## <a name="example"></a>Örnek

Aşağıdaki örnek, bir iş parçacığı oluşturmak ve yürütmek için Windows API 'sinin tipik kullanımını gösterir. Bu örnek, öğesini ayrı bir iş parçacığında çağırmak için [CreateThread](/windows/win32/api/processthreadsapi/nf-processthreadsapi-createthread) işlevini kullanır `MyThreadFunction` .

### <a name="initial-code"></a>İlk kod

[!code-cpp[concrt-windows-threads#1](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_1.cpp)]

Bu örnek aşağıdaki çıktıyı üretir.

```Output
Parameters = 50, 100
```

Aşağıdaki adımlarda, aynı görevi gerçekleştirmek üzere Eşzamanlılık Çalışma Zamanı kullanmak için kod örneğini nasıl uyarlayabileceğiniz gösterilmektedir.

### <a name="to-adapt-the-example-to-use-a-lightweight-task"></a>Örneği basit bir görev kullanacak şekilde uyarlamak için

1. `#include`Concrt. h üstbilgi dosyası için bir yönerge ekleyin.

[!code-cpp[concrt-migration-lwt#2](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_2.cpp)]

1. **`using`** Ad alanı için bir yönerge ekleyin `concurrency` .

[!code-cpp[concrt-migration-lwt#3](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_3.cpp)]

1. ' In bildirimini, `MyThreadFunction` **`__cdecl`** çağırma kuralını kullanacak ve döndürecek şekilde değiştirin **`void`** .

[!code-cpp[concrt-migration-lwt#4](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_4.cpp)]

1. Yapıyı, `MyData` görevin tamamlandığı ana uygulamaya işaret eden bir [eşzamanlılık:: Event](../../parallel/concrt/reference/event-class.md) nesnesi içerecek şekilde değiştirin.

[!code-cpp[concrt-migration-lwt#5](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_5.cpp)]

1. Çağrısını `CreateThread` [concurrency:: CurrentScheduler:: ScheduleTask](reference/currentscheduler-class.md#scheduletask) yöntemi çağrısıyla değiştirin.

[!code-cpp[concrt-migration-lwt#6](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_6.cpp)]

1. Çağrısını, `WaitForSingleObject` görevin bitmesini beklemek için [concurrency:: Event:: wait](reference/event-class.md#wait) yöntemine yönelik bir çağrı ile değiştirin.

[!code-cpp[concrt-migration-lwt#7](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_7.cpp)]

1. Çağrısını kaldırın `CloseHandle` .

1. Tanımın imzasını `MyThreadFunction` 3. adım ile eşleşecek şekilde değiştirin.

[!code-cpp[concrt-migration-lwt#8](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_8.cpp)]

1. `MyThreadFunction`İşlevin sonundaki [eşzamanlılık:: Event:: set](reference/event-class.md#set) metodunu, görevin bittiği ana uygulamaya işaret etmek için çağırın.

[!code-cpp[concrt-migration-lwt#9](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_9.cpp)]

1. **`return`** İfadesini öğesinden kaldırın `MyThreadFunction` .

### <a name="completed-code"></a>Tamamlanan kod

Aşağıdaki tamamlanan örnek, işlevini çağırmak için hafif bir görev kullanan kodu gösterir `MyThreadFunction` .

[!code-cpp[concrt-migration-lwt#1](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_10.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[Görev Zamanlayıcı](../../parallel/concrt/task-scheduler-concurrency-runtime.md)<br/>
[Zamanlayıcı sınıfı](../../parallel/concrt/reference/scheduler-class.md)
