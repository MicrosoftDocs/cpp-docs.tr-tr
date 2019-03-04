---
title: 'İzlenecek yol: COM özellikli bir uygulamada eşzamanlılık çalışma zamanı kullanma'
ms.date: 11/04/2016
helpviewer_keywords:
- Concurrency Runtime, use with COM
- COM, use with the Concurrency Runtime
ms.assetid: a7c798b8-0fc8-4bee-972f-22ef158f7f48
ms.openlocfilehash: 9d306377be4a000c54fb5556b15263a15b2d4618
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57278203"
---
# <a name="walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application"></a>İzlenecek yol: COM özellikli bir uygulamada eşzamanlılık çalışma zamanı kullanma

Bu belge Bileşen Nesne Modeli (COM) kullanan bir uygulamada eşzamanlılık çalışma zamanı nasıl yapılacağı açıklanır.

## <a name="prerequisites"></a>Önkoşullar

Bu kılavuza başlamadan önce aşağıdaki belgeleri okuyun:

- [Görev Paralelliği](../../parallel/concrt/task-parallelism-concurrency-runtime.md)

- [Paralel Algoritmalar](../../parallel/concrt/parallel-algorithms.md)

- [Zaman Uyumsuz Aracılar](../../parallel/concrt/asynchronous-agents.md)

- [Özel Durum İşleme](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)

COM hakkında daha fazla bilgi için bkz: [Bileşen Nesne Modeli (COM)](/windows/desktop/com/component-object-model--com--portal).

## <a name="managing-the-lifetime-of-the-com-library"></a>COM Kitaplığının Kullanım Süresini Yönetme

Diğer bir eşzamanlılık mekanizması olarak aynı ilkeler COM eşzamanlılık çalışma zamanı ile kullanımını izleyen olsa da, aşağıdaki yönergeleri Bu kitaplıklar birlikte etkili bir şekilde kullanmanıza yardımcı olabilir.

- Bir iş parçacığı çağırmalıdır [CoInitializeEx](/windows/desktop/api/combaseapi/nf-combaseapi-coinitializeex) COM kitaplığı kullanan önce.

- Bir iş parçacığı çağırabilirsiniz `CoInitializeEx` isteğe bağlı olarak birden çok kez aynı bağımsız değişkenleri her çağrı için sağladığı sürece.

- Her çağrı için `CoInitializeEx`, bir iş parçacığı da çağırmalıdır [CoUninitialize](/windows/desktop/api/combaseapi/nf-combaseapi-couninitialize). Diğer bir deyişle, çağrılar `CoInitializeEx` ve `CoUninitialize` dengelenmelidir.

- Çağırmadan önce bir iş parçacığı grubu diğerine geçmek için bir iş parçacığı tamamen COM kitaplığı boşaltmanız gerekir `CoInitializeEx` belirtimi yeni iş parçacığı oluşturma.

Eşzamanlılık Çalışma zamanı ile COM kullandığınızda diğer COM ilkeler geçerlidir. Örneğin, bir tek iş parçacıklı apartmanda (STA) bir nesne oluşturur ve bu nesneyi başka bir grup sürekliliğe devreder bir uygulama aynı zamanda gelen iletileri işlemek için bir ileti döngüsü sağlamanız gerekir. Ayrıca apartmanlar arasında nesneleri sıralama performansı düşürebilir unutmayın.

### <a name="using-com-with-the-parallel-patterns-library"></a>COM'u Paralel Desenler Kitaplığıyla Kullanma

COM bileşeni, paralel Desen kitaplığı (PPL), örneğin, bir görev grubu veya paralel algoritma kullandığınızda çağrı `CoInitializeEx` her görev veya yineleme ve çağrısı sırasında bir COM kitaplığı kullanmadan önce `CoUninitialize` her görev veya yineleme tamamlanmadan önce . Aşağıdaki örnek COM kitaplığı ile ömrünü yönetmek nasıl gösterir bir [concurrency::structured_task_group](../../parallel/concrt/reference/structured-task-group-class.md) nesne.

[!code-cpp[concrt-parallel-scripts#1](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_1.cpp)]

COM kitaplığından bir görev veya paralel algoritma iptal edildiğinde veya görev gövdesi bir özel durum oluşturduğunda doğru şekilde serbest emin emin olmanız gerekir. Görev güvence altına almak için çağrıları `CoUninitialize` çıkana önce kullanmak bir `try-finally` blok veya *olduğu kaynak alımı başlatma* (RAII) deseni. Aşağıdaki örnekte bir `try-finally` COM kitaplığı görev tamamlandığında veya iptal edilen olduğunda veya bir özel durum oluştuğunda boşaltmak için blok.

[!code-cpp[concrt-parallel-scripts#2](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_2.cpp)]

Aşağıdaki örnek, tanımlamak için RAII deseni kullanır. `CCoInitializer` sınıfı belirli bir kapsamda COM kitaplığının kullanım ömrü yönetir.

[!code-cpp[concrt-parallel-scripts#3](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_3.cpp)]

Kullanabileceğiniz `CCoInitializer` görev çıkar, şu şekilde otomatik olarak bir COM kitaplığı boşaltılacak sınıfı.

[!code-cpp[concrt-parallel-scripts#4](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_4.cpp)]

Eşzamanlılık Çalışma zamanı iptali hakkında daha fazla bilgi için bkz. [ppl'de iptal](cancellation-in-the-ppl.md).

### <a name="using-com-with-asynchronous-agents"></a>COM'u Zaman Uyumsuz Aracılarla Kullanma

COM ile zaman uyumsuz aracılar kullandığınızda, çağrı `CoInitializeEx` COM kitaplığı'nda kullanmadan önce [concurrency::agent::run](reference/agent-class.md#run) aracınız için yöntemi. Ardından çağırın `CoUninitialize` önce `run` yöntemi döndürür. Oluşturucuda veya yok edicide aracınızın COM yönetim yordamlarını kullanmayın ve geçersiz [concurrency::agent::start](reference/agent-class.md#start) veya [concurrency::agent:: Bitti](reference/agent-class.md#done) yöntemleri çünkü bu yöntemler farklı bir iş parçacığına göre çağrılır `run` yöntemi.

Aşağıdaki örnekte adlı bir temel aracı sınıf `CCoAgent`, COM kitaplığı'nda yönetir `run` yöntemi.

[!code-cpp[concrt-parallel-scripts#5](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_5.cpp)]

Bu izlenecek yolda tam bir örnek sağlanmaktadır.

### <a name="using-com-with-lightweight-tasks"></a>COM'u Basit Görevlerle Kullanma

Belge [Görev Zamanlayıcı](../../parallel/concrt/task-scheduler-concurrency-runtime.md) eşzamanlılık çalışma zamanındaki Basit görevler rolünü açıklar. Geçirdiğiniz tüm iş parçacığı yordamı ile olduğu gibi COM ile basit bir görev kullanabilirsiniz `CreateThread` Windows API işlevi. Bu, aşağıdaki örnekte gösterilir.

[!code-cpp[concrt-parallel-scripts#6](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_6.cpp)]

## <a name="an-example-of-a-com-enabled-application"></a>COM Özellikli Uygulama Örneği

Bu bölümde kullanan tüm COM özellikli uygulama gösterilir `IScriptControl` n hesaplayan bir betik yürütmek için arabirimi<sup>th</sup> Fibonacci sayı. Bu örnek, ilk ana iş parçacığından komut dosyasını çağırır ve ardından betiği eşzamanlı olarak çağırmak için PPL ve aracıları kullanır.

Aşağıdaki yardımcı işlevi, göz önünde bulundurun `RunScriptProcedure`, bir yordamı çağıran bir `IScriptControl` nesne.

[!code-cpp[concrt-parallel-scripts#7](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_7.cpp)]

`wmain` İşlevi oluşturur bir `IScriptControl` nesne, n hesaplar, bir kod ekler<sup>th</sup> Fibonacci numarası ve çağrıları `RunScriptProcedure` bu betiği çalıştırmak için işlev.

[!code-cpp[concrt-parallel-scripts#8](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_8.cpp)]

### <a name="calling-the-script-from-the-ppl"></a>PPL'den Betik çağırma

Aşağıdaki işlev `ParallelFibonacci`, kullanan [concurrency::parallel_for](reference/concurrency-namespace-functions.md#parallel_for) algoritmasını paralel olarak komut dosyasını çağırın. Bu işlev kullanır `CCoInitializer` her görevin yineleme sırasında bir COM kitaplığı ömrünü yönetmek için sınıf.

[!code-cpp[concrt-parallel-scripts#9](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_9.cpp)]

Kullanılacak `ParallelFibonacci` işlev örneği ile önce aşağıdaki kodu ekleyin `wmain` işlevi döndürür.

[!code-cpp[concrt-parallel-scripts#10](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_10.cpp)]

### <a name="calling-the-script-from-an-agent"></a>Bir Aracıdan Betik çağırma

Aşağıdaki örnekte gösterildiği `FibonacciScriptAgent` n hesaplamak için bir komut dosyası yordamı çağıran sınıfı<sup>th</sup> Fibonacci sayı. `FibonacciScriptAgent` Sınıfı, ileti geçirme, ana programından almak için giriş değerleri için betik işlevi kullanır. `run` Yöntemi ömrü boyunca görev COM kitaplığının yönetir.

[!code-cpp[concrt-parallel-scripts#11](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_11.cpp)]

Aşağıdaki işlev `AgentFibonacci`, birkaç oluşturur `FibonacciScriptAgent` nesneleri ve ileti geçirme birkaç göndermek için giriş değerleri bu nesnelere kullanır.

[!code-cpp[concrt-parallel-scripts#12](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_12.cpp)]

Kullanılacak `AgentFibonacci` işlev örneği ile önce aşağıdaki kodu ekleyin `wmain` işlevi döndürür.

[!code-cpp[concrt-parallel-scripts#13](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_13.cpp)]

### <a name="the-complete-example"></a>Tam Örnek

Aşağıdaki kod Fibonacci numaraları hesaplar bir komut dosyası yordamı çağırmak için paralel algoritmalar ve zaman uyumsuz aracılar kullanan tam bir örnek gösterir.

[!code-cpp[concrt-parallel-scripts#14](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_14.cpp)]

Örneğin, aşağıdaki örnek çıktısı üretir.

```Output
Main Thread:
fib(15) = 610

Parallel Fibonacci:
fib(15) = 610
fib(10) = 55
fib(16) = 987
fib(18) = 2584
fib(11) = 89
fib(17) = 1597
fib(19) = 4181
fib(12) = 144
fib(13) = 233
fib(14) = 377

Agent Fibonacci:
fib(30) = 832040
fib(22) = 17711
fib(10) = 55
fib(12) = 144
```

## <a name="compiling-the-code"></a>Kod Derleniyor

Örnek kodu kopyalayın ve bir Visual Studio projesine yapıştırın veya adlı bir dosyaya yapıştırın `parallel-scripts.cpp` ve Visual Studio komut istemi penceresinde aşağıdaki komutu çalıştırın.

**cl.exe/ehsc paralel scripts.cpp/Link ole32.lib**

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Çalışma Zamanı İzlenecek Yollar](../../parallel/concrt/concurrency-runtime-walkthroughs.md)<br/>
[Görev Paralelliği](../../parallel/concrt/task-parallelism-concurrency-runtime.md)<br/>
[Paralel Algoritmalar](../../parallel/concrt/parallel-algorithms.md)<br/>
[Zaman Uyumsuz Aracılar](../../parallel/concrt/asynchronous-agents.md)<br/>
[Özel Durum İşleme](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)<br/>
[PPL'de İptal](cancellation-in-the-ppl.md)<br/>
[Görev Zamanlayıcısı](../../parallel/concrt/task-scheduler-concurrency-runtime.md)
