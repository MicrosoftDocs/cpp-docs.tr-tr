---
title: "Nasıl yapılır: bir gecikmeden sonra tamamlanan bir görev oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- task_completion_event class, example
- create a task that completes after a delay, example [C++]
ms.assetid: 3fc0a194-3fdb-4eba-8b8a-b890981a985d
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f9547bb5e586c20a22ce79d1227fa5f15b3ea305
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-create-a-task-that-completes-after-a-delay"></a>Nasıl yapılır: Bir Gecikmeden Sonra Tamamlanan bir Görev Oluşturma
Bu örnek nasıl kullanılacağını gösterir [concurrency::task](../../parallel/concrt/reference/task-class.md), [concurrency::cancellation_token_source](../../parallel/concrt/reference/cancellation-token-source-class.md), [concurrency::cancellation_token](../../parallel/concrt/reference/cancellation-token-class.md), [ CONCURRENCY::task_completion_event](../../parallel/concrt/reference/task-completion-event-class.md), [concurrency::timer](../../parallel/concrt/reference/timer-class.md), ve [concurrency::call](../../parallel/concrt/reference/call-class.md) bir gecikmeden sonra tamamlanan bir görev oluşturmak için sınıflar. Bazen verileri yoklamak, zaman aşımı getirir, kullanıcı girişini işleme önceden belirlenmiş bir süre için gecikme ve benzeri döngüler oluşturmak için bu yöntemi kullanabilirsiniz.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte gösterildiği `complete_after` ve `cancel_after_timeout` işlevleri. `complete_after` İşlev oluşturur bir `task` belirtilen gecikmeden sonra tamamlanan nesnesi. Kullandığı bir `timer` nesne ve `call` ayarlamak için nesne bir `task_completion_event` nesne belirtilen gecikmeden sonra. Kullanarak `task_completion_event` sınıfı, bir iş parçacığı sonra tamamlanan bir görev tanımlayabilirsiniz veya başka bir görev bir değer kullanılabilir olduğunu bildirir. Olay ayarladığınızda, dinleyicisi görevleri tamamlamak ve bunların devamlılıklar çalışacak şekilde zamanlanır.  
  
> [!TIP]
>  Hakkında daha fazla bilgi için `timer` ve `call` zaman uyumsuz aracılar kitaplığı parçası olan sınıfları için bkz [zaman uyumsuz ileti blokları](../../parallel/concrt/asynchronous-message-blocks.md).  
  
 `cancel_after_timeout` İşlevi derlemeler `complete_after` işlevi bu görevin belirli bir zaman aşımından önce tamamlanmazsa bir görevi iptal etme. `cancel_after_timeout` İşlevi iki görevi oluşturur. İlk görev başarılı olduğunu gösterir ve sağlanan görevi tamamlandıktan sonra tamamlar; İkinci görev başarısız olduğunu gösterir ve belirtilen zaman aşımından sonra tamamlar. `cancel_after_timeout` İşlevi başarı veya başarısızlık görev tamamlandığında çalışan bir devamlılık görev oluşturur. Hata görevi ilk tamamlarsa, devamlılık genel görev iptal belirteci kaynağı iptal eder.  
  
 [!code-cpp[concrt-task-delay#1](../../parallel/concrt/codesnippet/cpp/how-to-create-a-task-that-completes-after-a-delay_1.cpp)]  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek asal sayılar [0, 100000] aralığında sayısı hesaplar birden çok kez. Belirli bir süre sınırı içinde tamamlanmazsa işlemi başarısız olur. `count_primes` İşlevi nasıl kullanılacağını gösteren `cancel_after_timeout` işlevi. Verilen aralıktaki primes sayar ve görev belirtilen süre içinde tamamlanmazsa başarısız olur. `wmain` İşlev çağrıları `count_primes` birden çok kez işlev. Her zaman zaman sınırı halves. İşlemi geçerli süre sınırı içinde tamamlanmazsa sonra programın tamamlanır.  
  
 [!code-cpp[concrt-task-delay#2](../../parallel/concrt/codesnippet/cpp/how-to-create-a-task-that-completes-after-a-delay_2.cpp)]  
  
 Bir gecikmeden sonra görevleri iptal etmek için bu yöntemi kullandığınızda, genel görev iptal edildikten sonra Başlamamış görevler başlatılmaz. Bununla birlikte, tüm uzun süre çalışan görevler iptali için zamanında yanıt önemlidir. Görev iptali hakkında daha fazla bilgi için bkz: [PPL'de iptal](cancellation-in-the-ppl.md).  
  
## <a name="example"></a>Örnek  
 Bu örneğin tam kod aşağıdaki gibidir:  
  
 [!code-cpp[concrt-task-delay#3](../../parallel/concrt/codesnippet/cpp/how-to-create-a-task-that-completes-after-a-delay_3.cpp)]  
  
## <a name="compiling-the-code"></a>Kod Derleniyor  
 Kodu derlemek için kopyalayın ve ardından bir Visual Studio projesi yapıştırın veya adlı bir dosyaya yapıştırın `task-delay.cpp` ve ardından Visual Studio komut istemi penceresinde aşağıdaki komutu çalıştırın.  
  
 **cl.exe /EHsc görev-delay.cpp**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Görev Paralelliği](../../parallel/concrt/task-parallelism-concurrency-runtime.md)   
 [task sınıfı (eşzamanlılık çalışma zamanı)](../../parallel/concrt/reference/task-class.md)   
 [cancellation_token_source sınıfı](../../parallel/concrt/reference/cancellation-token-source-class.md)   
 [cancellation_token sınıfı](../../parallel/concrt/reference/cancellation-token-class.md)   
 [task_completion_event sınıfı](../../parallel/concrt/reference/task-completion-event-class.md)   
 [Timer sınıfı](../../parallel/concrt/reference/timer-class.md)   
 [Çağrı sınıfı](../../parallel/concrt/reference/call-class.md)   
 [Zaman uyumsuz ileti blokları](../../parallel/concrt/asynchronous-message-blocks.md)   
 [PPL'de İptal](cancellation-in-the-ppl.md)

