---
title: 'Nasıl yapılır: Zamanlayıcı Örneğini Yönetme'
ms.date: 11/04/2016
helpviewer_keywords:
- managing a scheduler instance [Concurrency Runtime]
- scheduler instances, managing [Concurrency Runtime]
ms.assetid: 2cc804f0-5ff3-498b-97f1-a9f67a005448
ms.openlocfilehash: 8c19eb801c7761b85580526e1ff8bed89112cc5e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50437823"
---
# <a name="how-to-manage-a-scheduler-instance"></a>Nasıl yapılır: Zamanlayıcı Örneğini Yönetme

Zamanlayıcı örnekleri çeşitli türlerdeki iş yüklerini özel zamanlama ilkeleri ilişkilendirmenizi sağlar. Bu konu, oluşturup bir zamanlayıcı örneğini yönetmek nasıl gösteren iki temel örnekler içerir.

Örnekler varsayılan Zamanlayıcı ilkelerini kullanan zamanlayıcılar oluşturur. Bir zamanlayıcı oluşturan bir örnek kullanan özel bir ilke için bkz: [nasıl yapılır: belirli Zamanlayıcı ilkeleri belirtme](../../parallel/concrt/how-to-specify-specific-scheduler-policies.md).

### <a name="to-manage-a-scheduler-instance-in-your-application"></a>Uygulamanızda bir zamanlayıcı örneğini yönetmek için

1. Oluşturma bir [concurrency::SchedulerPolicy](../../parallel/concrt/reference/schedulerpolicy-class.md) değerleri Zamanlayıcı kullanılacak ilkeyi içeren nesne.

1. Çağrı [concurrency::CurrentScheduler::Create](reference/currentscheduler-class.md#create) yöntemi veya [concurrency::Scheduler::Create](reference/scheduler-class.md#create) Zamanlayıcı örneğini oluşturmak için yöntemi.

   Kullanırsanız `Scheduler::Create` yöntemi, çağrı [concurrency::Scheduler::Attach](reference/scheduler-class.md#attach) Zamanlayıcı geçerli bağlam ile ilişkilendirmek gerektiğinde yöntemi.

1. Çağrı [CreateEvent](/windows/desktop/api/synchapi/nf-synchapi-createeventa) verilmemiş, otomatik sıfırlama olay nesnesi için bir tanıtıcı oluşturmak için işlevi.

1. İşleyici için oluşturduğunuz olay nesnesiyle geçirmek [concurrency::CurrentScheduler::RegisterShutdownEvent](reference/currentscheduler-class.md#registershutdownevent) yöntemi veya [concurrency::Scheduler::RegisterShutdownEvent](reference/scheduler-class.md#registershutdownevent) yöntemi. Bu zamanlayıcı kaldırıldığında ayarlamak için bir olay kaydeder.

1. Zamanlama geçerli Zamanlayıcı istediğiniz görevleri gerçekleştirin.

1. Çağrı [concurrency::CurrentScheduler::Detach](reference/currentscheduler-class.md#detach) geçerli Zamanlayıcı ayırma ve geçerli olarak önceki Zamanlayıcısı'nı geri yüklemek için yöntemi.

   Kullanırsanız `Scheduler::Create` yöntemi, çağrı [concurrency::Scheduler::Release](reference/scheduler-class.md#release) başvuru sayısını azaltmak için yöntemi `Scheduler` nesne.

1. Olay tanıtıcısı geçirmek [WaitForSingleObject](/windows/desktop/api/synchapi/nf-synchapi-waitforsingleobject) Zamanlayıcısı'nı kapatmak beklenecek işlevi.

1. Çağrı [CloseHandle](https://msdn.microsoft.com/library/windows/desktop/ms724211) olay nesne tanıtıcısını kapatmak için işlevi.

## <a name="example"></a>Örnek

Aşağıdaki kod, bir zamanlayıcı örneğini yönetmek için iki yolunu gösterir. Her örnek, benzersiz tanıtıcısı geçerli Zamanlayıcı yazdıran bir görevi gerçekleştirmek için önce varsayılan Zamanlayıcı kullanır. Her örnek daha sonra yeniden aynı görevi gerçekleştirmek için Zamanlayıcı örneğini kullanır. Son olarak, her örnek, geçerli bir varsayılan Zamanlayıcı'yı geri yükler ve bir kez daha görevi gerçekleştirir.

İlk örnekte [concurrency::CurrentScheduler](../../parallel/concrt/reference/currentscheduler-class.md) Zamanlayıcı örneğini oluşturun ve bunu geçerli bağlam ile ilişkilendirmek için sınıf. İkinci örnekte [concurrency::Scheduler](../../parallel/concrt/reference/scheduler-class.md) aynı görevi gerçekleştirmek için sınıf. Genellikle, `CurrentScheduler` sınıfı geçerli Zamanlayıcı ile çalışmak için kullanılır. İkinci örnek kullanan `Scheduler` sınıfı, Zamanlayıcı geçerli bağlam ile ilişkili olduğunda veya belirli zamanlayıcılar belirli görevler ile ilişkilendirmek istediğiniz zaman kontrol etmek istediğinizde yararlıdır.

[!code-cpp[concrt-scheduler-instance#1](../../parallel/concrt/codesnippet/cpp/how-to-manage-a-scheduler-instance_1.cpp)]

Bu örnek aşağıdaki çıktıyı üretir.

```Output
Using CurrentScheduler class...

Current scheduler id: 0
Creating and attaching scheduler...
Current scheduler id: 1
Detaching scheduler...
Current scheduler id: 0

Using Scheduler class...

Current scheduler id: 0
Creating scheduler...
Attaching scheduler...
Current scheduler id: 2
Detaching scheduler...
Current scheduler id: 0
```

## <a name="compiling-the-code"></a>Kod Derleniyor

Örnek kodu kopyalayın ve bir Visual Studio projesine yapıştırın veya adlı bir dosyaya yapıştırın `scheduler-instance.cpp` ve Visual Studio komut istemi penceresinde aşağıdaki komutu çalıştırın.

**cl.exe/ehsc Zamanlayıcı-instance.cpp**

## <a name="see-also"></a>Ayrıca Bkz.

[Zamanlayıcı Örnekleri](../../parallel/concrt/scheduler-instances.md)<br/>
[Nasıl yapılır: Belirli Zamanlayıcı İlkeleri Belirtme](../../parallel/concrt/how-to-specify-specific-scheduler-policies.md)

