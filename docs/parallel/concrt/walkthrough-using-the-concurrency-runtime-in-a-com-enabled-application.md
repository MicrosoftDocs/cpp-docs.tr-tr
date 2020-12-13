---
description: 'Daha fazla bilgi edinin: Izlenecek yol: Eşzamanlılık Çalışma Zamanı COM-Enabled uygulamasında kullanma'
title: 'İzlenecek yol: COM Özellikli bir Uygulamada Eşzamanlılık Çalışma Zamanını Kullanma'
ms.date: 04/25/2019
helpviewer_keywords:
- Concurrency Runtime, use with COM
- COM, use with the Concurrency Runtime
ms.assetid: a7c798b8-0fc8-4bee-972f-22ef158f7f48
ms.openlocfilehash: 1844062531a9cc4e0b7bb8864fc8d8343063d75a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97150104"
---
# <a name="walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application"></a>İzlenecek yol: COM Özellikli bir Uygulamada Eşzamanlılık Çalışma Zamanını Kullanma

Bu belgede, bileşen nesne modeli (COM) kullanan bir uygulamada Eşzamanlılık Çalışma Zamanı nasıl kullanılacağı gösterilmiştir.

## <a name="prerequisites"></a>Önkoşullar

Bu yönergeyi başlamadan önce aşağıdaki belgeleri okuyun:

- [Görev Paralelliği](../../parallel/concrt/task-parallelism-concurrency-runtime.md)

- [Paralel algoritmalar](../../parallel/concrt/parallel-algorithms.md)

- [Zaman uyumsuz aracılar](../../parallel/concrt/asynchronous-agents.md)

- [Özel Durum İşleme](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)

COM hakkında daha fazla bilgi için bkz. [bileşen nesne modeli (com)](/windows/win32/com/component-object-model--com--portal).

## <a name="managing-the-lifetime-of-the-com-library"></a>COM Kitaplığının Kullanım Süresini Yönetme

Eşzamanlılık Çalışma Zamanı ile COM kullanılması diğer eşzamanlılık mekanizmasıyla aynı ilkeleri takip etse de, aşağıdaki kılavuzlar bu kitaplıkları etkin bir şekilde kullanmanıza yardımcı olabilir.

- COM kitaplığını kullanmadan önce bir iş parçacığının [CoInitializeEx](/windows/win32/api/combaseapi/nf-combaseapi-coinitializeex) çağrısı gerekir.

- `CoInitializeEx`Her çağrıda aynı bağımsız değişkenleri sağladığı sürece bir iş parçacığı birden çok kez çağrı yapabilir.

- Her çağrısı için `CoInitializeEx` bir iş parçacığının [CoUnInitialize](/windows/win32/api/combaseapi/nf-combaseapi-couninitialize)çağrısını de çağırması gerekir. Diğer bir deyişle, ve çağrıları `CoInitializeEx` `CoUninitialize` dengelenmesi gerekir.

- Bir iş parçacığı grubundan diğerine geçiş yapmak için, iş parçacığının yeni iş parçacığı belirtimine geçmeden önce COM kitaplığını tamamen boşaltmalıdır `CoInitializeEx` .

COM kullandığınızda Eşzamanlılık Çalışma Zamanı diğer COM ilkeleri geçerlidir. Örneğin, tek iş parçacıklı grupta (STA) bir nesne oluşturan ve bu nesnenin başka bir gruba göre sıraladığında, gelen iletileri işlemek için de bir ileti döngüsü sağlaması gerekir. Ayrıca, bu nesnelerin apartmanlar arasında sıralama performansını azaltamada unutmayın.

### <a name="using-com-with-the-parallel-patterns-library"></a>COM'u Paralel Desenler Kitaplığıyla Kullanma

Bir görev grubu veya paralel algoritma gibi bir bileşen ile COM kullandığınızda, `CoInitializeEx` her görev veya yineleme SıRASıNDA com kitaplığını kullanmadan önce çağırın ve `CoUninitialize` her bir görev veya yineleme bitmeden önce çağırın. Aşağıdaki örnek, COM kitaplığı yaşam süresinin [eşzamanlılık:: structured_task_group](../../parallel/concrt/reference/structured-task-group-class.md) nesnesiyle nasıl yönetileceğini gösterir.

[!code-cpp[concrt-parallel-scripts#1](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_1.cpp)]

Bir görev veya paralel algoritma iptal edildiğinde veya görev gövdesi bir özel durum oluşturduğunda COM kitaplığının düzgün şekilde serbest olduğundan emin olmanız gerekir. Görevin uygulamadan `CoUninitialize` önce çağırdığından emin olmak için bir `try-finally` blok veya *kaynak alımı başlatma* (rampaı) kalıbı kullanın. Aşağıdaki örnek, `try-finally` görev tamamlandığında veya iptal edildiğinde ya da bir özel durum OLUŞTUĞUNDA com kitaplığını serbest bırakmak için bir blok kullanır.

[!code-cpp[concrt-parallel-scripts#2](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_2.cpp)]

Aşağıdaki örnek, `CCoInitializer` belirli bir KAPSAMDAKI com kitaplığı ömrünü yöneten sınıfını tanımlamak için bir ESII modelini kullanır.

[!code-cpp[concrt-parallel-scripts#3](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_3.cpp)]

`CCoInitializer`Aşağıdaki gibi, Görev çıkış SıRASıNDA com kitaplığını otomatik olarak serbest bırakmak için sınıfını kullanabilirsiniz.

[!code-cpp[concrt-parallel-scripts#4](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_4.cpp)]

Eşzamanlılık Çalışma Zamanı iptal hakkında daha fazla bilgi için bkz. [PPL 'de iptal](cancellation-in-the-ppl.md).

### <a name="using-com-with-asynchronous-agents"></a>COM'u Zaman Uyumsuz Aracılarla Kullanma

COM 'u zaman uyumsuz aracılar ile kullandığınızda, `CoInitializeEx` aracılarınız için [concurrency:: Agent:: Run](reference/agent-class.md#run) yönteminde com kitaplığını kullanmadan önce çağırın. Sonra `CoUninitialize` , `run` yöntemi döndürmadan önce çağırın. Aracılarınızın oluşturucusunda veya yıkıcısında COM yönetim yordamlarını kullanmayın ve bu yöntemler yöntemden farklı bir iş parçacığından çağrıldığı için [concurrency:: Agent:: Start](reference/agent-class.md#start) veya [concurrency:: Agent::d One](reference/agent-class.md#done) metodunu geçersiz kılmaz `run` .

Aşağıdaki örnek, `CCoAgent` YÖNTEMINDE com kitaplığını yöneten adlı temel bir aracı sınıfını gösterir `run` .

[!code-cpp[concrt-parallel-scripts#5](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_5.cpp)]

Bu izlenecek yolda daha sonra bir örnek verilmiştir.

### <a name="using-com-with-lightweight-tasks"></a>COM'u Basit Görevlerle Kullanma

Belge [Görev Zamanlayıcı](../../parallel/concrt/task-scheduler-concurrency-runtime.md) , eşzamanlılık çalışma zamanı basit görevlerin rolünü açıklar. Windows API 'sindeki işleve geçirdiğiniz iş parçacığı yordamında olduğu gibi, COM öğesini hafif bir görevle birlikte kullanabilirsiniz `CreateThread` . Bu, aşağıdaki örnekte gösterilir.

[!code-cpp[concrt-parallel-scripts#6](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_6.cpp)]

## <a name="an-example-of-a-com-enabled-application"></a>COM Özellikli Uygulama Örneği

Bu bölümde `IScriptControl` , n. fibonaccı numarasını hesaplayan bir betiği yürütmek için arabirimini kullanan tam bır com özellikli<sup></sup> uygulama gösterilmektedir. Bu örnek ilk olarak ana iş parçacığından betiği çağırır ve ardından betiği aynı anda çağırmak için PPL ve aracılarını kullanır.

`RunScriptProcedure`Bir nesne içindeki bir yordamı çağıran aşağıdaki yardımcı işlevi göz önünde bulundurun `IScriptControl` .

[!code-cpp[concrt-parallel-scripts#7](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_7.cpp)]

`wmain`İşlevi bir nesnesi oluşturur `IScriptControl` , ona n. fibonaccı numarasını hesaplayan betik<sup></sup> kodu ekler ve sonra `RunScriptProcedure` bu betiği çalıştırmak için işlevini çağırır.

[!code-cpp[concrt-parallel-scripts#8](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_8.cpp)]

### <a name="calling-the-script-from-the-ppl"></a>PPL'den Betik çağırma

Aşağıdaki işlev, `ParallelFibonacci` komut dosyasını paralel olarak çağırmak için [eşzamanlılık::p arallel_for](reference/concurrency-namespace-functions.md#parallel_for) algoritmasını kullanır. Bu işlev, `CCoInitializer` görevi her tekrarında com kitaplığı ömrünü yönetmek için sınıfını kullanır.

[!code-cpp[concrt-parallel-scripts#9](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_9.cpp)]

`ParallelFibonacci`İşlevini örnekle birlikte kullanmak için, işlevin döndürüldüğünden önce aşağıdaki kodu ekleyin `wmain` .

[!code-cpp[concrt-parallel-scripts#10](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_10.cpp)]

### <a name="calling-the-script-from-an-agent"></a>Bir Aracıdan Betik çağırma

Aşağıdaki örnek, n. `FibonacciScriptAgent` fibonaccı numarasını hesaplamak için bir betik yordamı çağıran<sup></sup> sınıfını gösterir. `FibonacciScriptAgent`Sınıfı, ana programdan, giriş değerlerini komut dosyası işlevine almak için ileti geçişini kullanır. `run`Yöntemi, görev boyunca com kitaplığı ömrünü yönetir.

[!code-cpp[concrt-parallel-scripts#11](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_11.cpp)]

Aşağıdaki işlev, `AgentFibonacci` birkaç `FibonacciScriptAgent` nesne oluşturur ve bu nesnelere birkaç giriş değeri göndermek için ileti geçişini kullanır.

[!code-cpp[concrt-parallel-scripts#12](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_12.cpp)]

`AgentFibonacci`İşlevini örnekle birlikte kullanmak için, işlevin döndürüldüğünden önce aşağıdaki kodu ekleyin `wmain` .

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

Örnek kodu kopyalayın ve bir Visual Studio projesine yapıştırın veya adlandırılmış bir dosyaya yapıştırın `parallel-scripts.cpp` ve sonra bir Visual Studio komut istemi penceresinde aşağıdaki komutu çalıştırın.

> **cl.exe/EHsc Parallel-Scripts. cpp/link Ole32. lib**

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Çalışma Zamanı Izlenecek yollar](../../parallel/concrt/concurrency-runtime-walkthroughs.md)<br/>
[Görev Paralelliği](../../parallel/concrt/task-parallelism-concurrency-runtime.md)<br/>
[Paralel algoritmalar](../../parallel/concrt/parallel-algorithms.md)<br/>
[Zaman uyumsuz aracılar](../../parallel/concrt/asynchronous-agents.md)<br/>
[Özel Durum İşleme](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)<br/>
[PPL'de İptal](cancellation-in-the-ppl.md)<br/>
[Görev Zamanlayıcı](../../parallel/concrt/task-scheduler-concurrency-runtime.md)
