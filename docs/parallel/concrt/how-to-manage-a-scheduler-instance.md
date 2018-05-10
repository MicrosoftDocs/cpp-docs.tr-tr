---
title: 'Nasıl yapılır: Zamanlayıcı örneğini yönetme | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- managing a scheduler instance [Concurrency Runtime]
- scheduler instances, managing [Concurrency Runtime]
ms.assetid: 2cc804f0-5ff3-498b-97f1-a9f67a005448
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 699abcbc75dc4f0df40d07d26c0e6987d4711fe3
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
---
# <a name="how-to-manage-a-scheduler-instance"></a>Nasıl yapılır: Zamanlayıcı Örneğini Yönetme
Zamanlayıcı örnekleri özel zamanlama ilkeleri çeşitli iş yükleri ile ilişkilendirmenizi sağlar. Bu konu, oluşturma ve Zamanlayıcı örneğini yönetme gösteren iki temel örnekleri içerir.  
  
 Örnekler varsayılan Zamanlayıcı ilkelerini kullanan zamanlayıcılar oluşturun. Bir zamanlayıcı oluşturan bir örnek özel bir ilke kullandığı için bkz: [nasıl yapılır: belirli Zamanlayıcı ilkeleri belirtme](../../parallel/concrt/how-to-specify-specific-scheduler-policies.md).  
  
### <a name="to-manage-a-scheduler-instance-in-your-application"></a>Uygulamanızda bir zamanlayıcı örneğini yönetmek için  
  
1.  Oluşturma bir [concurrency::SchedulerPolicy](../../parallel/concrt/reference/schedulerpolicy-class.md) ilkeyi içeren nesne Zamanlayıcı kullanılacak değerler.  
  

2.  Çağrı [concurrency::CurrentScheduler::Create](reference/currentscheduler-class.md#create) yöntemi veya [concurrency::Scheduler::Create](reference/scheduler-class.md#create) Zamanlayıcı örneğini oluşturmak için yöntemi.  
  
     Kullanırsanız `Scheduler::Create` yöntemi, çağrı [concurrency::Scheduler::Attach](reference/scheduler-class.md#attach) yöntemi geçerli bağlamla Zamanlayıcı ilişkilendirmeniz gerekir.  
  
3.  Çağrı [CreateEvent](http://msdn.microsoft.com/library/windows/desktop/ms682396) işaret olmayan, otomatik sıfırlama olayı nesnesi için bir tanıtıcı oluşturmak için işlevi.  
  
4.  Tanıtıcı geçişi için oluşturduğunuz olay nesnesi için [concurrency::CurrentScheduler::RegisterShutdownEvent](reference/currentscheduler-class.md#registershutdownevent) yöntemi veya [concurrency::Scheduler::RegisterShutdownEvent](reference/scheduler-class.md#registershutdownevent) yöntemi. Bu zamanlayıcı bozulduğunda ayarlanacak olayı kaydeder.  
  
5.  Zamanlamak için geçerli Zamanlayıcı istediğiniz görevleri gerçekleştirin.  
  
6.  Çağrı [concurrency::CurrentScheduler::Detach](reference/currentscheduler-class.md#detach) geçerli Zamanlayıcı detach ve geçerli olarak önceki Zamanlayıcısı'nı geri yüklemek için yöntem.  
  
     Kullanırsanız `Scheduler::Create` yöntemi, çağrı [concurrency::Scheduler::Release](reference/scheduler-class.md#release) başvuru sayısını düşürmek için yöntemi `Scheduler` nesnesi.  
  
7.  İçin olay işleyicisini geçirmek [WaitForSingleObject](http://msdn.microsoft.com/library/windows/desktop/ms687032) Zamanlayıcısı'nı kapatmak beklenecek işlevi.  
  
8.  Çağrı [CloseHandle](http://msdn.microsoft.com/library/windows/desktop/ms724211) olay nesne tanıtıcısını kapatmaya işlevi.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod Zamanlayıcı örneğini yönetme için iki yol gösterir. Her örnek, geçerli Zamanlayıcı benzersiz tanımlayıcı yazdırır bir görevi gerçekleştirmek için ilk varsayılan Zamanlayıcısı'nı kullanır. Her örneğin Zamanlayıcı örneğini aynı görevi yeniden gerçekleştirmek için sonra kullanır. Son olarak, her örnek, geçerli bir varsayılan Zamanlayıcı'yı geri yükler ve bir kez daha görevi gerçekleştirir.  
  
 İlk örnek kullanan [concurrency::CurrentScheduler](../../parallel/concrt/reference/currentscheduler-class.md) Zamanlayıcı örneğini oluşturmak ve geçerli bağlamla ilişkilendirmek için sınıf. İkinci örnek kullanan [concurrency::Scheduler](../../parallel/concrt/reference/scheduler-class.md) aynı görevi gerçekleştirmenin sınıfı. Genellikle, `CurrentScheduler` sınıfı, geçerli Zamanlayıcısı ile çalışmak için kullanılır. Kullanır ikinci örnek `Scheduler` sınıfı, Zamanlayıcı geçerli bağlamla ilişkili olduğunda veya belirli zamanlayıcılar belirli görevleri ile ilişkilendirmek istediğiniz zaman denetlemek istediğinizde yararlı olur.  
  
 [!code-cpp[concrt-scheduler-instance#1](../../parallel/concrt/codesnippet/cpp/how-to-manage-a-scheduler-instance_1.cpp)]  
  
 Bu örnek şu çıkışı üretir.  
  
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
 Örnek kodu kopyalayın ve bir Visual Studio projesi yapıştırın veya adlı bir dosyaya yapıştırın `scheduler-instance.cpp` ve ardından Visual Studio komut istemi penceresinde aşağıdaki komutu çalıştırın.  
  
 **cl.exe /EHsc Zamanlayıcı-instance.cpp**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Zamanlayıcı örnekleri](../../parallel/concrt/scheduler-instances.md)   
 [Nasıl yapılır: Belirli Zamanlayıcı İlkeleri Belirtme](../../parallel/concrt/how-to-specify-specific-scheduler-policies.md)

