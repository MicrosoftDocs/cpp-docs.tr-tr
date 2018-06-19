---
title: Özel durum eşzamanlılık çalışma zamanı'nda işleme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- lightweight tasks, exception handling [Concurrency Runtime]
- exception handling [Concurrency Runtime]
- structured task groups, exception handling [Concurrency Runtime]
- agents, exception handling [Concurrency Runtime]
- task groups, exception handling [Concurrency Runtime]
ms.assetid: 4d1494fb-3089-4f4b-8cfb-712aa67d7a7a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5f30c98a8800c3aeaaf5ff1dab5bee9bdba971a6
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33695575"
---
# <a name="exception-handling-in-the-concurrency-runtime"></a>Eşzamanlılık Çalışma Zamanında Özel Durum İşleme
Eşzamanlılık Çalışma zamanı C++ özel durum işleme hataları birçok türde iletişim kurmak için kullanır. Bu hataların çalışma zamanı, çalışma zamanı hataları gibi bir kaynak edinmeye hatası ve oluşan hataları kullanımı geçersiz iş görevleri ve görev grupları sağlayan işlevler dahil edin. Bir görevi veya görev grubu bir özel durum oluşturduğunda, çalışma zamanı bu özel durum tutar ve görev veya sonlandırmak için görev grubu için bekler bağlamını sıralar. Basit görevler ve aracılar gibi bileşenleri için çalışma zamanı özel durumları, yönetmez. Bu durumda, kendi özel durum işleme mekanizması uygulamalıdır. Bu konuda, çalışma zamanı görevler, görev grupları, Basit görevler ve zaman uyumsuz aracılar tarafından oluşturulan özel durumları nasıl işler ve nasıl özel durumlar uygulamalarınızda yanıt açıklanmaktadır.  
  
## <a name="key-points"></a>Önemli Noktalar  
  
-   Bir görevi veya görev grubu bir özel durum oluşturduğunda, çalışma zamanı bu özel durum tutar ve görev veya sonlandırmak için görev grubu için bekler bağlamını sıralar.  
  
-   Mümkün olduğunda, her çağrı için çevreleyen [CONCURRENCY::Task](reference/task-class.md#get) ve [concurrency::task::wait](reference/task-class.md#wait) ile bir `try` / `catch` kurtarabileceğiniz hataları işlemek için bloğu Kaynak. Bir görev bir özel durum oluşturur ve görev tarafından bir kendi devamlılıklar ya da ana uygulama özel durum yakalandı, uygulama çalışma zamanı sonlandırır.  
  
-   Bir görev tabanlı devamlılık her zaman çalışır; Öncül görevi başarıyla tamamlandı, özel durum oluşturdu veya iptal edildi önemli değildir. Öncül görev oluşturur ya da iptal eder değeri tabanlı devamlılık çalışmaz.  
  
-   Görev tabanlı devamlılıklar her zaman çalıştığından, bir görev tabanlı devamlılık, devamlılık zincirinin sonunda eklenip eklenmeyeceğini göz önünde bulundurun. Bu, kodunuzu tüm özel durumları gözlemleyen garanti yardımcı olabilir.  
  
-   Çalışma zamanı oluşturur [concurrency::task_canceled](../../parallel/concrt/reference/task-canceled-class.md) çağırdığınızda [CONCURRENCY::Task](reference/task-class.md#get) ve bu görev iptal edildi.  

  
-   Çalışma zamanı özel durumları Basit görevler ve aracıları için yönetmez.  
  
##  <a name="top"></a> Bu belgede  
  
- [Görevler ve devamlılıklar](#tasks)  
  
- [Görev grupları ve paralel algoritmalar](#task_groups)  
  
- [Çalışma zamanı tarafından oluşturulan özel durumları](#runtime)  
  
- [Birden çok özel durumlar](#multiple)  
  
- [İptal](#cancellation)  
  
- [Basit Görevler](#lwts)  
  
- [Zaman Uyumsuz Aracılar](#agents)  
  
##  <a name="tasks"></a> Görevler ve devamlılıklar  
 Bu bölümde nasıl Çalışma Zamanı Modülü tarafından oluşturulan özel durumları işler açıklanmaktadır [concurrency::task](../../parallel/concrt/reference/task-class.md) nesneler ve onların devamlılıklar. Görev ve devamlılık modeli hakkında daha fazla bilgi için bkz: [görev Paralelliği](../../parallel/concrt/task-parallelism-concurrency-runtime.md).  
  
 Throw ne zaman bir özel durum geçişi için bir iş işlev gövdesine bir `task` nesne, çalışma zamanı bu özel durum depolar ve çağıran bağlamına sıralar [CONCURRENCY::Task](reference/task-class.md#get) veya [eşzamanlılık:: Task::wait](reference/task-class.md#wait). Belge [görev Paralelliği](../../parallel/concrt/task-parallelism-concurrency-runtime.md) açıklar görev tabanlı özetlemek üzere ancak değer tabanlı devamlılıklar karşı değeri tabanlı devamlılık türünde bir parametre alan `T` ve görev tabanlı bir devamlılık türünde bir parametre alır `task<T>`. Bir veya daha fazla değer tabanlı devamlılıklar oluşturur bir görev varsa, bu devamlılıklar çalışmak üzere zamanlanmış değil. Aşağıdaki örnekte, bu davranış gösterilmektedir:  

  
 [!code-cpp[concrt-eh-task#1](../../parallel/concrt/codesnippet/cpp/exception-handling-in-the-concurrency-runtime_1.cpp)]  
  
 Görev tabanlı bir devamlılık öncül görevi tarafından oluşturulan özel durumları işlemek etkinleştirir. Bir görev tabanlı devamlılık her zaman çalışır; başarıyla tamamlanan görev özel durum oluşturdu veya iptal edildi önemli değildir. Bir görev özel durum oluşturduğunda, görev tabanlı devamlılıklar çalışmak üzere zamanlanmış. Aşağıdaki örnekte, her zaman oluşturur bir görev gösterilmektedir. Görev iki devamlılıklar; yine de sahip istiyor musunuz? bir değer tabanlı ve diğer görev tabanlı. Görev tabanlı özel durumu her zaman çalışır ve bu nedenle öncül görevi tarafından oluşturulan özel durum yakalayabilir. Örnek hem devamlılıklar tamamlanmasını bekler, görev her zaman zaman özel durum çünkü yeniden özel durum `task::get` veya `task::wait` olarak adlandırılır.  
  
 [!code-cpp[concrt-eh-continuations#1](../../parallel/concrt/codesnippet/cpp/exception-handling-in-the-concurrency-runtime_2.cpp)]  
  
 İşleyebilen özel durumları yakalamak için görev tabanlı devamlılıklar kullanmanızı öneririz. Görev tabanlı devamlılıklar her zaman çalıştığından, bir görev tabanlı devamlılık, devamlılık zincirinin sonunda eklenip eklenmeyeceğini göz önünde bulundurun. Bu, kodunuzu tüm özel durumları gözlemleyen garanti yardımcı olabilir. Aşağıdaki örnek, bir temel değer tabanlı devamlılık zinciri gösterir. Üçüncü görev zincirindeki oluşturur ve bu nedenle izleyerek değeri tabanlı devamlılıklar çalıştırılamaz. Ancak, son devamlılık görevi dayalıdır ve bu nedenle her zaman çalışır. Bu son devamlılık üçüncü görevi tarafından oluşturulan özel durumu işler.  
  
 Yapabilecekleriniz en özel durumları yakalamak öneririz. Catch özel durum yoksa bu son görev tabanlı devamlılık atlayabilirsiniz. Herhangi bir özel durum işlenmemiş kalır ve uygulama sonlandırabilir.  
  
 [!code-cpp[concrt-eh-task-chain#1](../../parallel/concrt/codesnippet/cpp/exception-handling-in-the-concurrency-runtime_3.cpp)]  
  
> [!TIP]
>  Kullanabileceğiniz [concurrency::task_completion_event::set_exception](../../parallel/concrt/reference/task-completion-event-class.md) yöntemi bir özel durum ile bir görev tamamlama olayı ilişkilendirin. Belge [görev Paralelliği](../../parallel/concrt/task-parallelism-concurrency-runtime.md) açıklar [concurrency::task_completion_event](../../parallel/concrt/reference/task-completion-event-class.md) daha ayrıntılı sınıfı.  
  

 [CONCURRENCY::task_canceled](../../parallel/concrt/reference/task-canceled-class.md) ilişkili bir önemli çalışma zamanı özel durum türü `task`. Çalışma zamanı oluşturur `task_canceled` çağırdığınızda `task::get` ve bu görev iptal edildi. (Buna karşılık, `task::wait` döndürür [task_status::canceled](reference/concurrency-namespace-enums.md#task_group_status) ve throw değil.) Catch ve bu özel görev tabanlı bir devamlılık veya çağırdığınızda işlemek `task::get`. Görev iptali hakkında daha fazla bilgi için bkz: [PPL'de iptal](cancellation-in-the-ppl.md).  

  
> [!CAUTION]
>  Hiçbir zaman throw `task_canceled` kodunuzdan. Çağrı [concurrency::cancel_current_task](reference/concurrency-namespace-functions.md#cancel_current_task) yerine.  
  
 Bir görev bir özel durum oluşturur ve görev tarafından bir kendi devamlılıklar ya da ana uygulama özel durum yakalandı, uygulama çalışma zamanı sonlandırır. C++ özel durum oluştuğunda ayırmak için Visual Studio, uygulama çökerse yapılandırabilirsiniz. İşlenmeyen özel durum konumunu tanılamanızdan sonra görev tabanlı bir devamlılık işlenmesi için kullanın.  
  
 Bölüm [özel durumlar çalışma zamanı tarafından](#runtime) bu belgede daha ayrıntılı çalışma zamanı özel durumları ile nasıl çalışılacağını açıklar.  
  
 [[Üst](#top)]  
  
##  <a name="task_groups"></a> Görev grupları ve paralel algoritmalar  

 Bu bölümde, nasıl çalışma zamanı görev grupları tarafından oluşturulan özel durumları işler açıklanmaktadır. Bu bölüm ayrıca paralel algoritmalar gibi geçerlidir [concurrency::parallel_for](reference/concurrency-namespace-functions.md#parallel_for), bu algoritmalar görev grupları oluşturun.  
  
> [!CAUTION]
>  Bağımlı görevlerde özel durumlara sahip etkilerini anladığınızdan emin olun. Özel durum işleme görevlerini veya paralel algoritmalar kullanmaya ilişkin önerilen yöntemler için bkz: [anlayın nasıl iptali ve özel durum işleme etkileyen nesne yok etme](../../parallel/concrt/best-practices-in-the-parallel-patterns-library.md#object-destruction) paralel en iyi yöntemler bölümündeki Desenler kitaplığı konusu.  
  
 Görev grupları hakkında daha fazla bilgi için bkz: [görev Paralelliği](../../parallel/concrt/task-parallelism-concurrency-runtime.md). Paralel algoritmalar hakkında daha fazla bilgi için bkz: [paralel algoritmalar](../../parallel/concrt/parallel-algorithms.md).  

 Throw ne zaman bir özel durum geçişi için bir iş işlev gövdesine bir [concurrency::task_group](reference/task-group-class.md) veya [concurrency::structured_task_group](../../parallel/concrt/reference/structured-task-group-class.md) nesne, çalışma zamanı bu özel durum depolar ve onu sıralar çağıran bağlamını [concurrency::task_group::wait](reference/task-group-class.md#wait), [concurrency::structured_task_group::wait](reference/structured-task-group-class.md#wait), [concurrency::task_group::run_and_wait](reference/task-group-class.md#run_and_wait), veya [concurrency::structured_task_group::run_and_wait](reference/structured-task-group-class.md#run_and_wait). Çalışma zamanı da (alt görev grupları de dahil) görev grubunda yer alan tüm etkin görevleri durdurur ve henüz başlatılmamış herhangi bir görevi atar.  

  
 Aşağıdaki örnek aykırı bir iş işlevi temel yapısını gösterir. Örnek kullanan bir `task_group` iki değerlerini yazdırmak için nesne `point` paralel nesneler. `print_point` İş işlevi yazdırır değerlerini bir `point` konsoluna nesnesi. Giriş değeri ise çalışma işlevi bir özel durum oluşturur `NULL`. Çalışma zamanı bu özel durumun depolar ve çağıran bağlamına sıralar `task_group::wait`.  
  
 [!code-cpp[concrt-eh-task-group#1](../../parallel/concrt/codesnippet/cpp/exception-handling-in-the-concurrency-runtime_4.cpp)]  
  
 Bu örnek şu çıkışı üretir.  
  
```Output  
X = 15, Y = 30Caught exception: point is NULL.  
```  
  
 Özel durum işleme görev grubunda kullanan tam bir örnek için bkz: [nasıl yapılır: kullanım özel durum işleme sona paralel bir döngüden gelen](../../parallel/concrt/how-to-use-exception-handling-to-break-from-a-parallel-loop.md).  
  
 [[Üst](#top)]  
  
##  <a name="runtime"></a> Çalışma zamanı tarafından oluşturulan özel durumları  
 Bir özel durum çalışma zamanı çağrısından neden olabilir. Çoğu özel durum türleri dışında [concurrency::task_canceled](../../parallel/concrt/reference/task-canceled-class.md) ve [concurrency::operation_timed_out](../../parallel/concrt/reference/operation-timed-out-class.md), bir programlama hatası gösterir. Bu hatalar genellikle kurtarılamaz ve bu nedenle yakalanan veya gerekir uygulama kodu tarafından işlenir. Yalnızca catch veya programlama hataları tanılamak gerektiğinde kurtarılamayan hatalar uygulama kodunuzda işlemek öneririz. Ancak, çalışma zamanı tarafından tanımlanan özel durum türlerini anlama programlama hataları tanılamanıza yardımcı olabilir.  
  
 Özel durum mekanizması işleme iş işlevleri tarafından oluşturulan özel durumlar olarak çalışma zamanı tarafından oluşturulan özel durumlar için aynıdır. Örneğin, [concurrency::receive](reference/concurrency-namespace-functions.md#receive) işlev atar `operation_timed_out` zaman onu almaz bir ileti belirtilen süre içinde. Varsa `receive` iş işlevinde aykırı bir görev grubuna geçişi, çalışma zamanı bu özel durum depolar ve çağıran bağlamına sıralar `task_group::wait`, `structured_task_group::wait`, `task_group::run_and_wait`, veya `structured_task_group::run_and_wait`.  
  
 Aşağıdaki örnek kullanır [concurrency::parallel_invoke](reference/concurrency-namespace-functions.md#parallel_invoke) iki görevi paralel olarak çalıştırmak için algoritması. İlk görev beş saniye bekler ve ardından bir ileti arabelleği bir ileti gönderir. İkinci görev kullanan `receive` işlevi aynı ileti arabelleğinden bir ileti almak için üç saniye bekleyin. `receive` İşlev atar `operation_timed_out` bir zaman diliminde ileti almazsa.  
  
 [!code-cpp[concrt-eh-time-out#1](../../parallel/concrt/codesnippet/cpp/exception-handling-in-the-concurrency-runtime_5.cpp)]  
  
 Bu örnek şu çıkışı üretir.  
  
```Output  
The operation timed out.  
```  
  
 Uygulamanızın olağandışı sonlandırma önlemek için kodunuzu çalışma zamanına çağırdığında özel durumları işler emin olun. Örneğin, eşzamanlılık çalışma zamanı kullanan dış koda bir üçüncü taraf kitaplık çağırdığınızda ayrıca özel durumları işleme.  
  
 [[Üst](#top)]  
  
##  <a name="multiple"></a> Birden çok özel durumlar  
 Bir görev veya paralel algoritması birden fazla özel alırsa, çalışma zamanı bu özel durumlar çağıran bağlamını yalnızca biri sıralar. Çalışma zamanı bu sıralar hangi özel durum garanti etmez.  
  
 Aşağıdaki örnek kullanır `parallel_for` konsol sayılara yazdırmak için algoritması. Giriş değeri bazı en düşük değerden küçük veya bazı en büyük değerden daha büyük olması durumunda bir özel durum oluşturur. Bu örnekte, birden çok iş işlevleri bir özel durum.  
  
 [!code-cpp[concrt-eh-multiple#1](../../parallel/concrt/codesnippet/cpp/exception-handling-in-the-concurrency-runtime_6.cpp)]  
  
 Bu örnek için örnek çıktı aşağıda gösterilmiştir.  
  
```Output  
8293104567Caught exception: -5: the value is less than the minimum.  
```  
  
 [[Üst](#top)]  
  
##  <a name="cancellation"></a> İptal etme  
 Tüm özel durumlar bir hata gösterir. Örneğin, arama algoritması, özel durum işleme sonucu bulduğunda, ilişkili görevini durdurmak için kullanabilirsiniz. Kodunuzda iptal mekanizmaları kullanma hakkında daha fazla bilgi için bkz: [PPL'de iptal](../../parallel/concrt/cancellation-in-the-ppl.md).  
  
 [[Üst](#top)]  
  
##  <a name="lwts"></a> Basit görevler  
 Basit bir görev doğrudan zamanlama bir görevdir bir [concurrency::Scheduler](../../parallel/concrt/reference/scheduler-class.md) nesnesi. Basit görevler daha az yüke sıradan görevler gerçekleştirirsiniz. Ancak, çalışma zamanı Basit görevler tarafından oluşturulan özel durumları yakalamaz. Bunun yerine, özel durum, varsayılan işlemi sonlandırır işlenmeyen bir özel durum işleyici tarafından yakalanır. Bu nedenle, uygun bir hata işleme mekanizması uygulamanızda kullanın. Basit görevler hakkında daha fazla bilgi için bkz: [Görev Zamanlayıcı](../../parallel/concrt/task-scheduler-concurrency-runtime.md).  
  
 [[Üst](#top)]  
  
##  <a name="agents"></a> Zaman uyumsuz aracılar  
 Basit görevler gibi zaman uyumsuz aracılar tarafından oluşturulan özel durumları çalışma zamanı yönetmez.  
  
 Türetilen bir sınıfta özel durumları işleme yollarından biri aşağıdaki örnekte [concurrency::agent](../../parallel/concrt/reference/agent-class.md). Bu örnek tanımlar `points_agent` sınıfı. `points_agent::run` Yöntemi okuma `point` nesneleri ileti arabelleğinden ve bunları konsola yazdırır. `run` Yöntemi aykırı aldığı varsa bir `NULL` işaretçi.  
  
 `run` Yöntemi çevreleyen tüm iş bir `try` - `catch` bloğu. `catch` Blok özel durum iletisi arabellekte depolar. Uygulama, aracı bittikten sonra aracıyı bu arabellek okuma tarafından hatayla olup olmadığını denetler.  
  
 [!code-cpp[concrt-eh-agents#1](../../parallel/concrt/codesnippet/cpp/exception-handling-in-the-concurrency-runtime_7.cpp)]  
  
 Bu örnek şu çıkışı üretir.  
  
```Output  
X: 10 Y: 20  
X: 20 Y: 30  
error occurred in agent: point must not be NULL  
the status of the agent is: done  
```  
  
 Çünkü `try` - `catch` blok var. dışında `while` döngü, aracı bitip ilk hata ile karşılaştığında işleniyor. Varsa `try` - `catch` blok oluştu içinde `while` döngü, aracı devam hata oluştuktan sonra.  
  
 Bu örnek, özel durum iletisi arabellekte depolar çalışan başka bir bileşen aracı hataları için izleyebilirsiniz. Bu örnekte bir [concurrency::single_assignment](../../parallel/concrt/reference/single-assignment-class.md) hata depolamak için nesne. Burada bir aracı işler birden fazla özel durumda `single_assignment` sınıfı geçirilen yalnızca ilk iletiyi kendisine depolar. Yalnızca son istisnası depolamak için kullanmak [concurrency::overwrite_buffer](../../parallel/concrt/reference/overwrite-buffer-class.md) sınıfı. Tüm özel durumları depolamak için kullanmak [concurrency::unbounded_buffer](reference/unbounded-buffer-class.md) sınıfı. Bu ileti blokları hakkında daha fazla bilgi için bkz: [zaman uyumsuz ileti blokları](../../parallel/concrt/asynchronous-message-blocks.md).  
  
 Zaman uyumsuz aracılar hakkında daha fazla bilgi için bkz: [zaman uyumsuz aracılar](../../parallel/concrt/asynchronous-agents.md).  
  
 [[Üst](#top)]  
  
##  <a name="summary"></a> Özet  
 [[Üst](#top)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Çalışma zamanı](../../parallel/concrt/concurrency-runtime.md)   
 [Görev Paralelliği](../../parallel/concrt/task-parallelism-concurrency-runtime.md)   
 [Paralel algoritmalar](../../parallel/concrt/parallel-algorithms.md)   
 [PPL'de iptal](cancellation-in-the-ppl.md)   
 [Görev Zamanlayıcısı](../../parallel/concrt/task-scheduler-concurrency-runtime.md)   
 [Zaman Uyumsuz Aracılar](../../parallel/concrt/asynchronous-agents.md)

