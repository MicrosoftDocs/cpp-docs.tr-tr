---
title: 'Nasıl yapılır: Gecikmeden sonra tamamlanan bir görev oluşturma'
description: PPL ConcRT kitaplığını kullanarak bir gecikmeden sonra tamamlanan bir görev oluşturun.
ms.date: 10/19/2020
helpviewer_keywords:
- task_completion_event class, example
- create a task that completes after a delay, example [C++]
ms.assetid: 3fc0a194-3fdb-4eba-8b8a-b890981a985d
ms.openlocfilehash: 694b6190a7ec60043a5674e920dc54e6e7bf0eb6
ms.sourcegitcommit: 19016630f9d35f365e9ba249e0f3617515d7ca33
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/20/2020
ms.locfileid: "92274556"
---
# <a name="how-to-create-a-task-that-completes-after-a-delay"></a>Nasıl yapılır: Gecikmeden sonra tamamlanan bir görev oluşturma

Bu örnek [`concurrency::task`](../../parallel/concrt/reference/task-class.md) , [`concurrency::cancellation_token_source`](../../parallel/concrt/reference/cancellation-token-source-class.md) [`concurrency::cancellation_token`](../../parallel/concrt/reference/cancellation-token-class.md) [`concurrency::task_completion_event`](../../parallel/concrt/reference/task-completion-event-class.md) [`concurrency::timer`](../../parallel/concrt/reference/timer-class.md) [`concurrency::call`](../../parallel/concrt/reference/call-class.md) bir gecikmeden sonra tamamlanan bir görev oluşturmak için,,,, ve sınıflarının nasıl kullanılacağını gösterir. Bu yöntemi, zaman zaman veri yoklamaya yönelik döngüler oluşturmak için kullanabilirsiniz. Zaman aşımlarını, önceden belirlenmiş bir süre için Kullanıcı girişi işlemeyi erteleyebilir ve bu şekilde devam edebilirsiniz.

## <a name="example-complete_after-and-cancel_after_timeout-functions"></a>Örnek: complete_after ve cancel_after_timeout işlevleri

Aşağıdaki örnekte `complete_after` ve `cancel_after_timeout` işlevleri gösterilmektedir. `complete_after`İşlevi, `task` belirtilen gecikmeden sonra tamamlanan bir nesne oluşturur. `timer` `call` Belirtilen gecikmeden sonra bir nesne ayarlamak için bir nesne ve nesne kullanır `task_completion_event` . `task_completion_event`Sınıfını kullanarak, bir iş parçacığı veya başka bir görev bir değerin kullanılabilir olduğunu sinyalden sonra tamamlanmış bir görevi tanımlayabilirsiniz. Olay ayarlandığında, dinleyici görevleri tamamlanır ve devamlılıkları çalıştırılmak üzere zamanlanır.

> [!TIP]
> `timer`Zaman uyumsuz aracılar kitaplığının parçası olan ve sınıfları hakkında daha fazla bilgi için `call` bkz. [zaman uyumsuz ileti blokları](../../parallel/concrt/asynchronous-message-blocks.md).

`cancel_after_timeout`İşlevi, `complete_after` Bu görev belirli bir zaman aşımından önce tamamlanmazsa bir görevi iptal etmek için işlevini oluşturur. `cancel_after_timeout`İşlevi iki görevi oluşturur. İlk görev, belirtilen görev tamamlandıktan sonra başarılı ve tamamlanmış olduğunu gösterir. İkinci görev, belirtilen zaman aşımından sonra başarısız olduğunu ve tamamlandığını gösterir. `cancel_after_timeout`İşlevi, başarı veya başarısızlık görevi tamamlandığında çalışan bir devamlılık görevi oluşturur. Önce hata görevi tamamlanırsa, devamlılık, genel görevi iptal etmek için belirteç kaynağını iptal eder.

[!code-cpp[concrt-task-delay#1](../../parallel/concrt/codesnippet/cpp/how-to-create-a-task-that-completes-after-a-delay_1.cpp)]

## <a name="example-compute-count-of-prime-numbers"></a>Örnek: asal sayıların Işlem sayısı

Aşağıdaki örnek [0, 100000] aralığındaki asal sayıların sayısını birden çok kez hesaplar. İşlem belirli bir zaman sınırı içinde tamamlanmazsa başarısız olur. `count_primes`İşlevi, işlevinin nasıl kullanılacağını gösterir `cancel_after_timeout` . Verilen aralıktaki primin sayısını sayar ve görev sağlanan sürede tamamlanmazsa başarısız olur. `wmain`İşlevi `count_primes` işlevi birden çok kez çağırır. Her seferinde zaman sınırı yarıya iner. Program, işlem geçerli zaman sınırında tamamlanmazsa tamamlanır.

[!code-cpp[concrt-task-delay#2](../../parallel/concrt/codesnippet/cpp/how-to-create-a-task-that-completes-after-a-delay_2.cpp)]

Bir gecikmeden sonra görevleri iptal etmek için bu tekniği kullandığınızda, genel görev iptal edildikten sonra, başlamamış görevler başlatılmaz. Ancak, uzun süre çalışan görevlerin iptali hızlı bir şekilde yanıt vermesi önemlidir. Görev iptali hakkında daha fazla bilgi için bkz. [PPL 'de iptal](cancellation-in-the-ppl.md).

## <a name="complete-code-example"></a>Kod örneğini doldurun

Bu örnek için kodun tamamı aşağıda verilmiştir:

[!code-cpp[concrt-task-delay#3](../../parallel/concrt/codesnippet/cpp/how-to-create-a-task-that-completes-after-a-delay_3.cpp)]

## <a name="compiling-the-code"></a>Kod Derleniyor

Kodu derlemek için, kopyalayın ve sonra bir Visual Studio projesine yapıştırın veya adlandırılmış bir dosyaya yapıştırın `task-delay.cpp` ve sonra bir Visual Studio komut istemi penceresinde aşağıdaki komutu çalıştırın.

**cl.exe/EHsc Task-Delay. cpp**

## <a name="see-also"></a>Ayrıca bkz.

[Görev Paralelliği](../../parallel/concrt/task-parallelism-concurrency-runtime.md)<br/>
[Task sınıfı (Eşzamanlılık Çalışma Zamanı)](../../parallel/concrt/reference/task-class.md)<br/>
[cancellation_token_source sınıfı](../../parallel/concrt/reference/cancellation-token-source-class.md)<br/>
[cancellation_token sınıfı](../../parallel/concrt/reference/cancellation-token-class.md)<br/>
[task_completion_event sınıfı](../../parallel/concrt/reference/task-completion-event-class.md)<br/>
[Timer sınıfı](../../parallel/concrt/reference/timer-class.md)<br/>
[Call sınıfı](../../parallel/concrt/reference/call-class.md)<br/>
[Zaman uyumsuz Ileti blokları](../../parallel/concrt/asynchronous-message-blocks.md)<br/>
[PPL'de İptal](cancellation-in-the-ppl.md)
