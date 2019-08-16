---
title: 'İzlenecek yol: COM özellikli bir uygulamada Eşzamanlılık Çalışma Zamanı kullanma'
ms.date: 04/25/2019
helpviewer_keywords:
- Concurrency Runtime, use with COM
- COM, use with the Concurrency Runtime
ms.assetid: a7c798b8-0fc8-4bee-972f-22ef158f7f48
ms.openlocfilehash: 23488522287ab5767c88cd3a3e90c09392634f46
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69512103"
---
# <a name="walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application"></a>İzlenecek yol: COM özellikli bir uygulamada Eşzamanlılık Çalışma Zamanı kullanma

Bu belgede, bileşen nesne modeli (COM) kullanan bir uygulamada Eşzamanlılık Çalışma Zamanı nasıl kullanılacağı gösterilmiştir.

## <a name="prerequisites"></a>Önkoşullar

Bu yönergeyi başlamadan önce aşağıdaki belgeleri okuyun:

- [Görev Paralelliği](../../parallel/concrt/task-parallelism-concurrency-runtime.md)

- [Paralel Algoritmalar](../../parallel/concrt/parallel-algorithms.md)

- [Zaman Uyumsuz Aracılar](../../parallel/concrt/asynchronous-agents.md)

- [Özel Durum İşleme](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)

COM hakkında daha fazla bilgi için bkz. [bileşen nesne modeli (com)](/windows/win32/com/component-object-model--com--portal).

## <a name="managing-the-lifetime-of-the-com-library"></a>COM Kitaplığının Kullanım Süresini Yönetme

Eşzamanlılık Çalışma Zamanı ile COM kullanılması diğer eşzamanlılık mekanizmasıyla aynı ilkeleri takip etse de, aşağıdaki kılavuzlar bu kitaplıkları etkin bir şekilde kullanmanıza yardımcı olabilir.

- COM kitaplığını kullanmadan önce bir iş parçacığının [CoInitializeEx](/windows/win32/api/combaseapi/nf-combaseapi-coinitializeex) çağrısı gerekir.

- Her çağrıda aynı bağımsız `CoInitializeEx` değişkenleri sağladığı sürece bir iş parçacığı birden çok kez çağrı yapabilir.

- Her çağrısı `CoInitializeEx`için bir iş parçacığının [CoUnInitialize](/windows/win32/api/combaseapi/nf-combaseapi-couninitialize)çağrısını de çağırması gerekir. Diğer bir deyişle, `CoInitializeEx` ve `CoUninitialize` çağrıları dengelenmesi gerekir.

- Bir iş parçacığı grubundan diğerine geçiş yapmak için, iş parçacığının yeni iş parçacığı belirtimine geçmeden önce `CoInitializeEx` com kitaplığını tamamen boşaltmalıdır.

COM kullandığınızda Eşzamanlılık Çalışma Zamanı diğer COM ilkeleri geçerlidir. Örneğin, tek iş parçacıklı grupta (STA) bir nesne oluşturan ve bu nesnenin başka bir gruba göre sıraladığında, gelen iletileri işlemek için de bir ileti döngüsü sağlaması gerekir. Ayrıca, bu nesnelerin apartmanlar arasında sıralama performansını azaltamada unutmayın.

### <a name="using-com-with-the-parallel-patterns-library"></a>COM'u Paralel Desenler Kitaplığıyla Kullanma

Bir görev grubu veya paralel algoritma gibi bir bileşen ile com kullandığınızda, her görev veya yineleme sırasında com kitaplığını kullanmadan önce çağırın `CoInitializeEx` ve her bir görev veya yineleme bitmeden önce çağırın `CoUninitialize` . Aşağıdaki örnek, COM kitaplığı yaşam süresinin [eşzamanlılık:: structured_task_group](../../parallel/concrt/reference/structured-task-group-class.md) nesnesi ile nasıl yönetileceğini gösterir.

[!code-cpp[concrt-parallel-scripts#1](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_1.cpp)]

Bir görev veya paralel algoritma iptal edildiğinde veya görev gövdesi bir özel durum oluşturduğunda COM kitaplığının düzgün şekilde serbest olduğundan emin olmanız gerekir. Görevin uygulamadan önce çağırdığından `CoUninitialize` emin olmak için bir `try-finally` blok veya *kaynak alımı başlatma* (rampaı) kalıbı kullanın. Aşağıdaki örnek, görev tamamlandığında `try-finally` veya iptal edildiğinde ya da bir özel durum oluştuğunda com kitaplığını serbest bırakmak için bir blok kullanır.

[!code-cpp[concrt-parallel-scripts#2](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_2.cpp)]

Aşağıdaki örnek, belirli bir kapsamdaki com kitaplığı ömrünü yöneten `CCoInitializer` sınıfını tanımlamak için bir esii modelini kullanır.

[!code-cpp[concrt-parallel-scripts#3](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_3.cpp)]

Aşağıdaki gibi, görev `CCoInitializer` çıkış sırasında com kitaplığını otomatik olarak serbest bırakmak için sınıfını kullanabilirsiniz.

[!code-cpp[concrt-parallel-scripts#4](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_4.cpp)]

Eşzamanlılık Çalışma Zamanı iptal hakkında daha fazla bilgi için bkz. [PPL 'de iptal](cancellation-in-the-ppl.md).

### <a name="using-com-with-asynchronous-agents"></a>COM'u Zaman Uyumsuz Aracılarla Kullanma

Com 'u zaman uyumsuz aracılar ile kullandığınızda, aracılarınız için `CoInitializeEx` [concurrency:: Agent:: Run](reference/agent-class.md#run) yönteminde com kitaplığını kullanmadan önce çağırın. Sonra, `CoUninitialize` `run` yöntemi döndürmadan önce çağırın. Aracıınızın oluşturucusunda veya yıkıcısında COM yönetim yordamlarını kullanmayın ve bu yöntemler farklı bir iş parçacığından çağrıldığında, [concurrency:: Agent:: Start](reference/agent-class.md#start) veya [concurrency:: Agent::d One](reference/agent-class.md#done) yönteminigeçersizkılmaz.`run` yöntemi.

Aşağıdaki örnek, `CCoAgent` `run` yönteminde com kitaplığını yöneten adlı temel bir aracı sınıfını gösterir.

[!code-cpp[concrt-parallel-scripts#5](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_5.cpp)]

Bu izlenecek yolda daha sonra bir örnek verilmiştir.

### <a name="using-com-with-lightweight-tasks"></a>COM'u Basit Görevlerle Kullanma

Belge [Görev Zamanlayıcı](../../parallel/concrt/task-scheduler-concurrency-runtime.md) , eşzamanlılık çalışma zamanı basit görevlerin rolünü açıklar. Windows API 'sindeki `CreateThread` işleve geçirdiğiniz iş parçacığı yordamında olduğu gibi, com öğesini hafif bir görevle birlikte kullanabilirsiniz. Bu, aşağıdaki örnekte gösterilir.

[!code-cpp[concrt-parallel-scripts#6](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_6.cpp)]

## <a name="an-example-of-a-com-enabled-application"></a>COM Özellikli Uygulama Örneği

Bu bölümde, n. `IScriptControl` fibonaccı numarasını hesaplayan bir betiği yürütmek için arabirimini kullanan tam bir com özellikli<sup></sup> uygulama gösterilmektedir. Bu örnek ilk olarak ana iş parçacığından betiği çağırır ve ardından betiği aynı anda çağırmak için PPL ve aracılarını kullanır.

`RunScriptProcedure` Bir`IScriptControl` nesne içindeki bir yordamı çağıran aşağıdaki yardımcı işlevi göz önünde bulundurun.

[!code-cpp[concrt-parallel-scripts#7](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_7.cpp)]

İşlevi bir `IScriptControl` nesnesi oluşturur, ona n.<sup></sup> `RunScriptProcedure` fibonaccı numarasını hesaplayan betik kodu ekler ve sonra bu betiği çalıştırmak için işlevini çağırır. `wmain`

[!code-cpp[concrt-parallel-scripts#8](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_8.cpp)]

### <a name="calling-the-script-from-the-ppl"></a>PPL'den Betik çağırma

Aşağıdaki işlev `ParallelFibonacci`, komut dosyasını paralel olarak çağırmak için [eşzamanlılık::p arallel_for](reference/concurrency-namespace-functions.md#parallel_for) algoritmasını kullanır. Bu işlev, görevi `CCoInitializer` her tekrarında com kitaplığı ömrünü yönetmek için sınıfını kullanır.

[!code-cpp[concrt-parallel-scripts#9](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_9.cpp)]

`ParallelFibonacci` İşlevini örnekle birlikte kullanmak için, `wmain` işlevin döndürüldüğünden önce aşağıdaki kodu ekleyin.

[!code-cpp[concrt-parallel-scripts#10](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_10.cpp)]

### <a name="calling-the-script-from-an-agent"></a>Bir Aracıdan Betik çağırma

Aşağıdaki örnek, n. `FibonacciScriptAgent` fibonaccı numarasını hesaplamak için bir betik yordamı çağıran<sup></sup> sınıfını gösterir. `FibonacciScriptAgent` Sınıfı, ana programdan, giriş değerlerini komut dosyası işlevine almak için ileti geçişini kullanır. `run` Yöntemi, görev boyunca com kitaplığı ömrünü yönetir.

[!code-cpp[concrt-parallel-scripts#11](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_11.cpp)]

Aşağıdaki işlev `AgentFibonacci`, birkaç `FibonacciScriptAgent` nesne oluşturur ve bu nesnelere birkaç giriş değeri göndermek için ileti geçişini kullanır.

[!code-cpp[concrt-parallel-scripts#12](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_12.cpp)]

`AgentFibonacci` İşlevini örnekle birlikte kullanmak için, `wmain` işlevin döndürüldüğünden önce aşağıdaki kodu ekleyin.

[!code-cpp[concrt-parallel-scripts#13](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_13.cpp)]

### <a name="the-complete-example"></a>Tam Örnek

Aşağıdaki kod, Fipriaccı numaralarını hesaplayan bir betik yordamını çağırmak için paralel algoritmaları ve zaman uyumsuz aracıları kullanan tüm örneği gösterir.

[!code-cpp[concrt-parallel-scripts#14](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_14.cpp)]

Örnek, aşağıdaki örnek çıktıyı üretir.

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

Örnek kodu kopyalayın ve bir Visual Studio projesine yapıştırın veya adlandırılmış `parallel-scripts.cpp` bir dosyaya yapıştırın ve sonra bir Visual Studio komut istemi penceresinde aşağıdaki komutu çalıştırın.

**CL. exe/EHsc Parallel-Scripts. cpp/link Ole32. lib**

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Çalışma Zamanı İzlenecek Yollar](../../parallel/concrt/concurrency-runtime-walkthroughs.md)<br/>
[Görev Paralelliği](../../parallel/concrt/task-parallelism-concurrency-runtime.md)<br/>
[Paralel Algoritmalar](../../parallel/concrt/parallel-algorithms.md)<br/>
[Zaman Uyumsuz Aracılar](../../parallel/concrt/asynchronous-agents.md)<br/>
[Özel Durum İşleme](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)<br/>
[PPL'de İptal](cancellation-in-the-ppl.md)<br/>
[Görev Zamanlayıcı](../../parallel/concrt/task-scheduler-concurrency-runtime.md)
