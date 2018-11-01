---
title: 'İzlenecek yol: Mevcut Kodu Hafif Görevleri Kullanmaya Uyarlama'
ms.date: 11/04/2016
helpviewer_keywords:
- using lightweight tasks [Concurrency Runtime]
- lightweight tasks, using [Concurrency Runtime]
ms.assetid: 1edfe818-d274-46de-bdd3-e92967c9bbe0
ms.openlocfilehash: a0e724ff6f43dc0c888e787350f4841f14383f14
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50654512"
---
# <a name="walkthrough-adapting-existing-code-to-use-lightweight-tasks"></a>İzlenecek yol: Mevcut Kodu Hafif Görevleri Kullanmaya Uyarlama

Bu konuda, oluşturmak ve basit bir görev kullanmak için bir iş parçacığını yürütmek için Windows API kullanan mevcut kodu uyum gösterilmektedir.

A *basit görev* doğrudan zamanlama bir görev bir [concurrency::Scheduler](../../parallel/concrt/reference/scheduler-class.md) veya [concurrency::ScheduleGroup](../../parallel/concrt/reference/schedulegroup-class.md) nesne. Eşzamanlılık Çalışma zamanı zamanlama işlevselliğini kullanmak için mevcut kodu uyarlamak için basit görevler yararlıdır.

## <a name="prerequisites"></a>Önkoşullar

Bu kılavuza başlamadan önce bu konuyu okuyun [Görev Zamanlayıcı](../../parallel/concrt/task-scheduler-concurrency-runtime.md).

## <a name="example"></a>Örnek

### <a name="description"></a>Açıklama

Aşağıdaki örnek, oluşturup bir iş parçacığını yürütmek için Windows API'ın tipik kullanım gösterir. Bu örnekte [CreateThread](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-createthread) işlevi çağırmak için `MyThreadFunction` ayrı bir iş parçacığı üzerinde.

### <a name="code"></a>Kod

[!code-cpp[concrt-windows-threads#1](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_1.cpp)]

### <a name="comments"></a>Açıklamalar

Bu örnek aşağıdaki çıktıyı üretir.

```Output
Parameters = 50, 100
```

Aşağıdaki adımlarda, uyum aynı görevi gerçekleştirmek için eşzamanlılık çalışma zamanı kullanmak için kod örneği gösterilmektedir.

### <a name="to-adapt-the-example-to-use-a-lightweight-task"></a>Örneği basit bir görev kullanacak şekilde uyarlamak için

1. Ekleme bir `#include` üstbilgi dosyası concrt.h yönergesi.

[!code-cpp[concrt-migration-lwt#2](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_2.cpp)]

1. Ekleme bir `using` yönergesi `concurrency` ad alanı.

[!code-cpp[concrt-migration-lwt#3](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_3.cpp)]

1. Bildirimini değiştirmek `MyThreadFunction` kullanılacak `__cdecl` çağırma kuralı ve döndürülecek `void`.

[!code-cpp[concrt-migration-lwt#4](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_4.cpp)]

1. Değiştirme `MyData` içerecek şekilde yapısı bir [concurrency::event](../../parallel/concrt/reference/event-class.md) nesnesini ana uygulama görevin tamamlandığını bildirir.

[!code-cpp[concrt-migration-lwt#5](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_5.cpp)]

1. Çağrısını `CreateThread` çağrısıyla [concurrency::CurrentScheduler::ScheduleTask](reference/currentscheduler-class.md#scheduletask) yöntemi.

[!code-cpp[concrt-migration-lwt#6](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_6.cpp)]

1. Çağrısını `WaitForSingleObject` çağrısıyla [concurrency::event::wait](reference/event-class.md#wait) yöntemi görevin tamamlanmasını bekleyin.

[!code-cpp[concrt-migration-lwt#7](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_7.cpp)]

1. Çağrısını kaldırın `CloseHandle`.

1. Tanımı imzasını Değiştir `MyThreadFunction` 3. adım eşleştirilecek.

[!code-cpp[concrt-migration-lwt#8](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_8.cpp)]

9. Sonunda `MyThreadFunction` işlev, çağrı [concurrency::event::set](reference/event-class.md#set) ana uygulama görevin tamamlandığını göstermek için yöntemi.

[!code-cpp[concrt-migration-lwt#9](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_9.cpp)]

10. Kaldırma `return` deyimden `MyThreadFunction`.

## <a name="example"></a>Örnek

### <a name="description"></a>Açıklama

Aşağıdaki tamamlanan örnek çağırmak için basit bir görev kullanan kodu gösterir `MyThreadFunction` işlevi.

### <a name="code"></a>Kod

[!code-cpp[concrt-migration-lwt#1](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_10.cpp)]

### <a name="comments"></a>Açıklamalar

## <a name="see-also"></a>Ayrıca Bkz.

[Görev Zamanlayıcısı](../../parallel/concrt/task-scheduler-concurrency-runtime.md)<br/>
[Zamanlayıcı Sınıfı](../../parallel/concrt/reference/scheduler-class.md)
