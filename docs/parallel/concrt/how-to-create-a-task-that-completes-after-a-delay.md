---
title: 'Nasıl yapılır: Bir Gecikmeden Sonra Tamamlanan bir Görev Oluşturma'
ms.date: 11/04/2016
helpviewer_keywords:
- task_completion_event class, example
- create a task that completes after a delay, example [C++]
ms.assetid: 3fc0a194-3fdb-4eba-8b8a-b890981a985d
ms.openlocfilehash: 76189f45eb486e06b040155f6697bf003659b474
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77141753"
---
# <a name="how-to-create-a-task-that-completes-after-a-delay"></a>Nasıl yapılır: Bir Gecikmeden Sonra Tamamlanan bir Görev Oluşturma

Bu örnek, bir gecikmeden sonra tamamlanan bir görev oluşturmak için [concurrency:: Task](../../parallel/concrt/reference/task-class.md), [concurrency:: cancellation_token_source](../../parallel/concrt/reference/cancellation-token-source-class.md), concurrency:: [cancellation_token](../../parallel/concrt/reference/cancellation-token-class.md), [concurrency](../../parallel/concrt/reference/task-completion-event-class.md):: task_completion_event, [concurrency:: Timer](../../parallel/concrt/reference/timer-class.md)ve [concurrency:: Call](../../parallel/concrt/reference/call-class.md) sınıflarının nasıl kullanılacağını gösterir. Bu yöntemi, zaman zaman veri yoklamaya, zaman aşımlarını ortaya çıkaracak, önceden belirlenmiş bir süre için Kullanıcı girişinin geciktirilebilmesi ve bu şekilde devam eden döngüler oluşturmak için kullanabilirsiniz.

## <a name="example"></a>Örnek

Aşağıdaki örnekte `complete_after` ve `cancel_after_timeout` işlevleri gösterilmektedir. `complete_after` işlevi, belirtilen gecikmeden sonra tamamlanmış bir `task` nesnesi oluşturur. Belirtilen gecikmeden sonra bir `task_completion_event` nesnesi ayarlamak için bir `timer` nesnesi ve `call` nesnesi kullanır. `task_completion_event` sınıfını kullanarak, bir iş parçacığı veya başka bir görev bir değerin kullanılabilir olduğunu sinyalden sonra tamamlanmış bir görevi tanımlayabilirsiniz. Olay ayarlandığında, dinleyici görevleri tamamlanır ve devamlılıkları çalıştırılmak üzere zamanlanır.

> [!TIP]
> Zaman uyumsuz aracılar kitaplığının parçası olan `timer` ve `call` sınıfları hakkında daha fazla bilgi için bkz. [zaman uyumsuz Ileti blokları](../../parallel/concrt/asynchronous-message-blocks.md).

`cancel_after_timeout` işlevi, bu görev belirli bir zaman aşımından önce tamamlanmazsa bir görevi iptal etmek için `complete_after` işlevi üzerinde oluşturulur. `cancel_after_timeout` işlevi iki görevi oluşturur. İlk görev, belirtilen görev tamamlandıktan sonra başarıyı ve tamamlandığını gösterir; İkinci görev, belirtilen zaman aşımından sonra başarısız olduğunu ve tamamlandığını gösterir. `cancel_after_timeout` işlevi, başarı veya başarısızlık görevi tamamlandığında çalışan bir devamlılık görevi oluşturur. Önce hata görevi tamamlanırsa, devamlılık, genel görevi iptal etmek için belirteç kaynağını iptal eder.

[!code-cpp[concrt-task-delay#1](../../parallel/concrt/codesnippet/cpp/how-to-create-a-task-that-completes-after-a-delay_1.cpp)]

## <a name="example"></a>Örnek

Aşağıdaki örnek [0, 100000] aralığındaki asal sayıların sayısını birden çok kez hesaplar. İşlem belirli bir zaman sınırı içinde tamamlanmazsa başarısız olur. `count_primes` işlevi, `cancel_after_timeout` işlevinin nasıl kullanılacağını gösterir. Verilen aralıktaki primin sayısını sayar ve görev sağlanan sürede tamamlanmazsa başarısız olur. `wmain` işlevi `count_primes` işlevini birden çok kez çağırır. Her seferinde zaman sınırı yarıya iner. Program, işlem geçerli zaman sınırında tamamlanmadıktan sonra tamamlanır.

[!code-cpp[concrt-task-delay#2](../../parallel/concrt/codesnippet/cpp/how-to-create-a-task-that-completes-after-a-delay_2.cpp)]

Bir gecikmeden sonra görevleri iptal etmek için bu tekniği kullandığınızda, genel görev iptal edildikten sonra, herhangi bir başlamamış görev başlatılmaz. Ancak, uzun süre çalışan görevlerin iptal etmek için zamanında yanıt vermesi önemlidir. Görev iptali hakkında daha fazla bilgi için bkz. [PPL 'de iptal](cancellation-in-the-ppl.md).

## <a name="example"></a>Örnek

Bu örnek için kodun tamamı aşağıda verilmiştir:

[!code-cpp[concrt-task-delay#3](../../parallel/concrt/codesnippet/cpp/how-to-create-a-task-that-completes-after-a-delay_3.cpp)]

## <a name="compiling-the-code"></a>Kod Derleniyor

Kodu derlemek için, kopyalayın ve sonra bir Visual Studio projesine yapıştırın veya `task-delay.cpp` adlı bir dosyaya yapıştırın ve sonra bir Visual Studio komut Istemi penceresinde aşağıdaki komutu çalıştırın.

**CL. exe/EHsc Task-Delay. cpp**

## <a name="see-also"></a>Ayrıca bkz.

[Görev Paralelliği](../../parallel/concrt/task-parallelism-concurrency-runtime.md)<br/>
[task Sınıfı (Eşzamanlılık Çalışma Zamanı)](../../parallel/concrt/reference/task-class.md)<br/>
[cancellation_token_source Sınıfı](../../parallel/concrt/reference/cancellation-token-source-class.md)<br/>
[cancellation_token Sınıfı](../../parallel/concrt/reference/cancellation-token-class.md)<br/>
[task_completion_event Sınıfı](../../parallel/concrt/reference/task-completion-event-class.md)<br/>
[timer Sınıfı](../../parallel/concrt/reference/timer-class.md)<br/>
[call Sınıfı](../../parallel/concrt/reference/call-class.md)<br/>
[Zaman Uyumsuz İleti Blokları](../../parallel/concrt/asynchronous-message-blocks.md)<br/>
[PPL'de İptal](cancellation-in-the-ppl.md)
