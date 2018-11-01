---
title: 'Nasıl yapılır: Bir Gecikmeden Sonra Tamamlanan bir Görev Oluşturma'
ms.date: 11/04/2016
helpviewer_keywords:
- task_completion_event class, example
- create a task that completes after a delay, example [C++]
ms.assetid: 3fc0a194-3fdb-4eba-8b8a-b890981a985d
ms.openlocfilehash: 89564a00dbfde078ef98cd53110853e30e33ad6b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50616379"
---
# <a name="how-to-create-a-task-that-completes-after-a-delay"></a>Nasıl yapılır: Bir Gecikmeden Sonra Tamamlanan bir Görev Oluşturma

Bu örnek nasıl kullanılacağını gösterir [concurrency::task](../../parallel/concrt/reference/task-class.md), [concurrency::cancellation_token_source](../../parallel/concrt/reference/cancellation-token-source-class.md), [concurrency::cancellation_token](../../parallel/concrt/reference/cancellation-token-class.md), [ CONCURRENCY::task_completion_event](../../parallel/concrt/reference/task-completion-event-class.md), [concurrency::timer](../../parallel/concrt/reference/timer-class.md), ve [concurrency::call](../../parallel/concrt/reference/call-class.md) bir gecikmeden sonra tamamlanan bir görev oluşturmak için sınıf. Bazen verileri yoklayan, zaman aşımlarını tanıtan, kullanıcı girişini işleme bir süre için erteleme ve benzeri döngüler oluşturmak için bu yöntemi kullanabilirsiniz.

## <a name="example"></a>Örnek

Aşağıdaki örnekte gösterildiği `complete_after` ve `cancel_after_timeout` işlevleri. `complete_after` İşlevi oluşturur bir `task` belirtilen gecikmeden sonra tamamlanan bir nesne. Kullandığı bir `timer` nesnesi ve bir `call` nesne ayarlayın bir `task_completion_event` belirtilen gecikmenin ardından nesne. Kullanarak `task_completion_event` sınıfı, bir iş parçacığı sonra tamamlanan bir görev tanımlayabilir veya başka bir görev bir değer kullanılabilir olduğunu bildirir. Olay ayarlandığında, dinleyici görevleri tamamlayacak ve bunların devamlılığını çalışmak üzere zamanlanır.

> [!TIP]
>  Hakkında daha fazla bilgi için `timer` ve `call` zaman uyumsuz aracılar Kitaplığı'nın parçası olan sınıfları için bkz [zaman uyumsuz ileti blokları](../../parallel/concrt/asynchronous-message-blocks.md).

`cancel_after_timeout` İşlevi yapılar `complete_after` bu görevi, belirli bir zaman aşımından önce tamamlanmazsa, bir görev iptal etmek için işlevi. `cancel_after_timeout` İşlev iki görevi oluşturur. İlk görev başarılı olduğunu gösterir ve sağlanan görevi tamamlandıktan sonra tamamlar; İkinci görev başarısız olduğunu gösterir ve tamamlandıktan sonra belirtilen zaman aşımı. `cancel_after_timeout` İşlevi, başarı veya başarısızlık görev tamamlandığında, çalışan bir devamlılık görevi oluşturur. İlk hata görev tamamlandığında devamlılık genel görev iptal etmek için belirteç kaynağı iptal eder.

[!code-cpp[concrt-task-delay#1](../../parallel/concrt/codesnippet/cpp/how-to-create-a-task-that-completes-after-a-delay_1.cpp)]

## <a name="example"></a>Örnek

Aşağıdaki örnek sayısı [0, 100000] aralığında asal sayıları hesaplar birden çok kez. Belirli bir süre sınırı içinde tamamlanmazsa işlemi başarısız olur. `count_primes` İşlevi nasıl kullanılacağını gösterir `cancel_after_timeout` işlevi. Verili aralıktaki primes sayar ve görev belirtilen süre içinde tamamlanmazsa başarısız olur. `wmain` İşlev çağrılarında `count_primes` birden çok kez işlev. Her zaman sınırı halves. İşlemi geçerli bir zaman sınırı içinde tamamlanmazsa sonra program tamamlanır.

[!code-cpp[concrt-task-delay#2](../../parallel/concrt/codesnippet/cpp/how-to-create-a-task-that-completes-after-a-delay_2.cpp)]

Bir gecikmeden sonra görevleri iptal etmek için bu yöntemi kullandığınızda, genel görev iptal edildikten sonra tüm başlamamış görevleri başlatılmaz. Ancak, herhangi bir uzun süre çalışan görevi iptal için zamanında yanıt vermek önemlidir. Görev iptali hakkında daha fazla bilgi için bkz: [ppl'de iptal](cancellation-in-the-ppl.md).

## <a name="example"></a>Örnek

Bu örnek için tam kod aşağıdaki gibidir:

[!code-cpp[concrt-task-delay#3](../../parallel/concrt/codesnippet/cpp/how-to-create-a-task-that-completes-after-a-delay_3.cpp)]

## <a name="compiling-the-code"></a>Kod Derleniyor

Kodu derlemek için kopyalayın ve bir Visual Studio projesine yapıştırın veya adlı bir dosyaya yapıştırın `task-delay.cpp` ve Visual Studio komut istemi penceresinde aşağıdaki komutu çalıştırın.

**cl.exe/ehsc görev delay.cpp**

## <a name="see-also"></a>Ayrıca Bkz.

[Görev Paralelliği](../../parallel/concrt/task-parallelism-concurrency-runtime.md)<br/>
[task Sınıfı (Eşzamanlılık Çalışma Zamanı)](../../parallel/concrt/reference/task-class.md)<br/>
[cancellation_token_source Sınıfı](../../parallel/concrt/reference/cancellation-token-source-class.md)<br/>
[cancellation_token Sınıfı](../../parallel/concrt/reference/cancellation-token-class.md)<br/>
[task_completion_event Sınıfı](../../parallel/concrt/reference/task-completion-event-class.md)<br/>
[timer Sınıfı](../../parallel/concrt/reference/timer-class.md)<br/>
[call Sınıfı](../../parallel/concrt/reference/call-class.md)<br/>
[Zaman Uyumsuz İleti Blokları](../../parallel/concrt/asynchronous-message-blocks.md)<br/>
[PPL'de İptal](cancellation-in-the-ppl.md)

