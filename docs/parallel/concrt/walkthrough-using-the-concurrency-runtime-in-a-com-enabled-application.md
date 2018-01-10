---
title: "İzlenecek yol: COM özellikli bir uygulamada eşzamanlılık çalışma zamanı kullanma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- Concurrency Runtime, use with COM
- COM, use with the Concurrency Runtime
ms.assetid: a7c798b8-0fc8-4bee-972f-22ef158f7f48
caps.latest.revision: "14"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 676601259e7f1a682a57430198d24bdbc744a360
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application"></a>İzlenecek yol: COM Özellikli bir Uygulamada Eşzamanlılık Çalışma Zamanını Kullanma
Bu belge, Bileşen Nesne Modeli (COM) kullanan bir uygulamada eşzamanlılık çalışma zamanı kullanmak gösterilmiştir.  
  
## <a name="prerequisites"></a>Önkoşullar  
 Bu kılavuza başlamadan önce aşağıdaki belgeleri okuyun:  
  
- [Görev Paralelliği](../../parallel/concrt/task-parallelism-concurrency-runtime.md)  
  
- [Paralel Algoritmalar](../../parallel/concrt/parallel-algorithms.md)  
  
- [Zaman Uyumsuz Aracılar](../../parallel/concrt/asynchronous-agents.md)  
  
- [Özel Durum İşleme](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)  
  
 COM hakkında daha fazla bilgi için bkz: [Bileşen Nesne Modeli (COM)](http://msdn.microsoft.com/library/windows/desktop/ms680573).  
  
## <a name="managing-the-lifetime-of-the-com-library"></a>COM Kitaplığının Kullanım Süresini Yönetme  
 Başka bir eşzamanlılık mekanizma aynı ilkeleri COM eşzamanlılık çalışma zamanı ile kullanımını izleyen rağmen aşağıdaki yönergeleri Bu kitaplıklar birlikte etkili bir şekilde kullanmanıza yardımcı olabilir.  
  
-   Bir iş parçacığı çağırmalısınız [CoInitializeEx](http://msdn.microsoft.com/library/windows/desktop/ms695279) önce COM kitaplığını kullanır.  
  
-   Bir iş parçacığı çağırabilir `CoInitializeEx` isteğe bağlı olarak birden çok kez aynı bağımsız değişkenlere yapılan her çağrı için sağladığı sürece.  
  
-   Her çağrı için `CoInitializeEx`, bir iş parçacığı de çağırmanız gerekir [CoUninitialize](http://msdn.microsoft.com/library/windows/desktop/ms688715). Diğer bir deyişle, çağrılar `CoInitializeEx` ve `CoUninitialize` dengelenmelidir.  
  
-   Çağırmadan önce bir iş parçacığı grubu diğerine geçmek için bir iş parçacığı tamamen COM kitaplığı serbest gerekir `CoInitializeEx` belirtimi yeni iş parçacığı oluşturma.  
  
 Eşzamanlılık Çalışma zamanı ile COM kullandığınızda diğer COM ilkeleri uygulanır. Örneğin, bir tek iş parçacıklı grupta (STA) bir nesne oluşturur ve bu nesneyi başka bir grup sıralar bir uygulama gelen iletileri işlemek için bir ileti döngüsü de belirtmeniz gerekir. Ayrıca grupların arasında nesneleri sıralama performansı düşürebilir unutmayın.  
  
### <a name="using-com-with-the-parallel-patterns-library"></a>COM'u Paralel Desenler Kitaplığıyla Kullanma  
 COM bileşeni içinde paralel Desen kitaplığı (PPL), örneğin, bir görev grubu veya paralel algoritması ile kullandığınızda çağrısı `CoInitializeEx` her görev veya yineleme ve çağrısı sırasında COM kitaplığı kullanmadan önce `CoUninitialize` her bir görev veya yineleme tamamlanmadan önce . Aşağıdaki örnek COM kitaplığı ile ömrünü yönetmek nasıl gösterir bir [concurrency::structured_task_group](../../parallel/concrt/reference/structured-task-group-class.md) nesnesi.  
  
 [!code-cpp[concrt-parallel-scripts#1](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_1.cpp)]  
  
 COM kitaplığı bir görev veya paralel algoritması iptal ettiğinizde veya görev gövdesi bir özel durum oluşturduğunda doğru serbest olduğundan emin olmanız gerekir. Görev garanti çağrılar `CoUninitialize` sonlandırılır önce kullanmak bir `try-finally` blok veya *kaynak edinme olan başlatma* (RAII) deseni. Aşağıdaki örnek kullanan bir `try-finally` blok COM kitaplığı görevi tamamlanana veya iptal edilene veya bir özel durum boş.  
  
 [!code-cpp[concrt-parallel-scripts#2](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_2.cpp)]  
  
 Aşağıdaki örnek RAII düzeni tanımlamak için kullanır. `CCoInitializer` belirli bir kapsamda COM kitaplığı ömrü yöneten sınıf.  
  
 [!code-cpp[concrt-parallel-scripts#3](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_3.cpp)]  
  
 Kullanabileceğiniz `CCoInitializer` görev, aşağıdaki gibi çıktığında COM kitaplığı otomatik olarak boşaltılacak sınıfı.  
  
 [!code-cpp[concrt-parallel-scripts#4](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_4.cpp)]  
  
 Eşzamanlılık Çalışma zamanı iptal hakkında daha fazla bilgi için bkz: [PPL'de iptal](cancellation-in-the-ppl.md).  
  
### <a name="using-com-with-asynchronous-agents"></a>COM'u Zaman Uyumsuz Aracılarla Kullanma  

 Zaman uyumsuz aracılar ile COM kullandığınızda, çağrı `CoInitializeEx` COM kitaplığı'nda kullanmadan önce [concurrency::agent::run](reference/agent-class.md#run) aracınızı yöntemi. ' I çağırın `CoUninitialize` önce `run` yöntemi döndürür. COM yönetimi yordamları Oluşturucusu veya aracınızı yıkıcısı kullanmayın ve geçersiz [concurrency::agent::start](reference/agent-class.md#start) veya [concurrency::agent:: Bitti](reference/agent-class.md#done) yöntemleri bu yöntemleri olduğundan farklı bir iş parçacığı çağrılır `run` yöntemi.  

  
 Aşağıdaki örnek, adında bir temel Aracısı sınıfı gösterir `CCoAgent`, COM kitaplığı'nda yönetir `run` yöntemi.  
  
 [!code-cpp[concrt-parallel-scripts#5](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_5.cpp)]  
  
 Bu kılavuzda daha sonra tam bir örnek sağlanmaktadır.  
  
### <a name="using-com-with-lightweight-tasks"></a>COM'u Basit Görevlerle Kullanma  
 Belge [Görev Zamanlayıcı](../../parallel/concrt/task-scheduler-concurrency-runtime.md) eşzamanlılık çalışma zamanındaki Basit görevler rolü açıklanmaktadır. Geçişi için herhangi bir iş parçacığı yordamı ile yaptığınız gibi basit görev COM kullanabilirsiniz `CreateThread` Windows API işlev. Bu, aşağıdaki örnekte gösterilir.  
  
 [!code-cpp[concrt-parallel-scripts#6](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_6.cpp)]  
  
## <a name="an-example-of-a-com-enabled-application"></a>COM Özellikli Uygulama Örneği  
 Bu bölümde kullanan tam COM özellikli bir uygulama gösterir `IScriptControl` n hesaplar bir betik yürütmek için arabirim<sup>th</sup> Fibonacci numarası. Bu örnek ilk komut dosyası ana iş parçacığından çağırır ve ardından komut dosyasını aynı anda çağırmak için PPL ve aracıları kullanır.  
  
 Aşağıdaki yardımcı işlevini göz önünde bulundurun `RunScriptProcedure`, bir yordamı çağıran bir `IScriptControl` nesnesi.  
  
 [!code-cpp[concrt-parallel-scripts#7](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_7.cpp)]  
  
 `wmain` İşlev oluşturur bir `IScriptControl` nesne, bir kod n hesaplayan ekler<sup>th</sup> Fibonacci numarası ve çağrıları `RunScriptProcedure` işlevi bu komut dosyasını çalıştırın.  
  
 [!code-cpp[concrt-parallel-scripts#8](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_8.cpp)]  
  
### <a name="calling-the-script-from-the-ppl"></a>PPL'den Betik çağırma  

 Aşağıdaki işlevi `ParallelFibonacci`, kullanan [concurrency::parallel_for](reference/concurrency-namespace-functions.md#parallel_for) algoritmasını paralel olarak komut dosyasını çağırın. Bu işlev kullanır `CCoInitializer` görevinin her yinelemede COM kitaplığı ömrünü yönetmek için sınıf.  

  
 [!code-cpp[concrt-parallel-scripts#9](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_9.cpp)]  
  
 Kullanılacak `ParallelFibonacci` işlev örnekle, önce aşağıdaki kodu ekleyin `wmain` işlev döndürür.  
  
 [!code-cpp[concrt-parallel-scripts#10](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_10.cpp)]  
  
### <a name="calling-the-script-from-an-agent"></a>Bir Aracıdan Betik çağırma  
 Aşağıdaki örnekte gösterildiği `FibonacciScriptAgent` n işlem için bir komut dosyası yordamı çağıran sınıfı<sup>th</sup> Fibonacci numarası. `FibonacciScriptAgent` Sınıfı, ileti geçirme, ana programdan almak için giriş değerleri betik işlevi kullanır. `run` Yöntemi COM kitaplığı görev boyunca ömrü yönetir.  
  
 [!code-cpp[concrt-parallel-scripts#11](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_11.cpp)]  
  
 Aşağıdaki işlevi `AgentFibonacci`, birkaç oluşturur `FibonacciScriptAgent` nesneleri ve ileti geçirme birkaç göndermek için giriş değerleri bu nesnelere kullanır.  
  
 [!code-cpp[concrt-parallel-scripts#12](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_12.cpp)]  
  
 Kullanılacak `AgentFibonacci` işlev örnekle, önce aşağıdaki kodu ekleyin `wmain` işlev döndürür.  
  
 [!code-cpp[concrt-parallel-scripts#13](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_13.cpp)]  
  
### <a name="the-complete-example"></a>Tam Örnek  
 Aşağıdaki kod paralel algoritmalar ve zaman uyumsuz aracılar Fibonacci numaraları hesaplar bir komut dosyası yordamı çağırma için kullandığı tam bir örnek gösterilir.  
  
 [!code-cpp[concrt-parallel-scripts#14](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_14.cpp)]  
  
 Örneğin şu örnek çıkışı üretir.  
  
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
 Örnek kodu kopyalayın ve bir Visual Studio projesi yapıştırın veya adlı bir dosyaya yapıştırın `parallel-scripts.cpp` ve ardından Visual Studio komut istemi penceresinde aşağıdaki komutu çalıştırın.  
  
 **cl.exe /EHsc paralel scripts.cpp/Link ole32.lib**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Çalışma zamanı izlenecek yollar](../../parallel/concrt/concurrency-runtime-walkthroughs.md)   
 [Görev Paralelliği](../../parallel/concrt/task-parallelism-concurrency-runtime.md)   
 [Paralel algoritmalar](../../parallel/concrt/parallel-algorithms.md)   
 [Zaman uyumsuz aracılar](../../parallel/concrt/asynchronous-agents.md)   
 [Özel durum işleme](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)   
 [PPL'de iptal](cancellation-in-the-ppl.md)   
 [Görev Zamanlayıcısı](../../parallel/concrt/task-scheduler-concurrency-runtime.md)

