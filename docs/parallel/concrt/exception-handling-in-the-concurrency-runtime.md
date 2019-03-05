---
title: Eşzamanlılık Çalışma Zamanında Özel Durum İşleme
ms.date: 11/04/2016
helpviewer_keywords:
- lightweight tasks, exception handling [Concurrency Runtime]
- exception handling [Concurrency Runtime]
- structured task groups, exception handling [Concurrency Runtime]
- agents, exception handling [Concurrency Runtime]
- task groups, exception handling [Concurrency Runtime]
ms.assetid: 4d1494fb-3089-4f4b-8cfb-712aa67d7a7a
ms.openlocfilehash: 8239913c369605503134a9ea4c99789528911868
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57272639"
---
# <a name="exception-handling-in-the-concurrency-runtime"></a>Eşzamanlılık Çalışma Zamanında Özel Durum İşleme

Eşzamanlılık Çalışma zamanı C++ özel durum işleme pek çok hata iletişim kurmak için kullanır. Bu hatalar, görevler ve görev grupları için sağladığınız iş işlevleri çalışma zamanı, çalışma zamanı hataları gibi bir kaynak alma hatası ve oluşan hataları geçersiz kullanımı dahil. Bir görevi veya görev grubu bir özel durum oluşturduğunda, çalışma zamanı bu özel durum tutar ve görev veya görev grubu tamamlanması için bekleyeceği bağlam sürekliliğe devreder. Basit görevler ve aracılar gibi bileşenler için çalışma zamanı özel durumları, yönetmez. Bu durumlarda, kendi özel durum işleme mekanizması uygulamanız gerekir. Bu konuda, çalışma zamanının görevler, görev grupları, Basit görevler ve zaman uyumsuz aracılar tarafından oluşturulan özel durumları nasıl işlediğini ve nasıl uygulamalarınızda özel durumları yanıt açıklanmaktadır.

## <a name="key-points"></a>Önemli Noktalar

- Bir görevi veya görev grubu bir özel durum oluşturduğunda, çalışma zamanı bu özel durum tutar ve görev veya görev grubu tamamlanması için bekleyeceği bağlam sürekliliğe devreder.

- Mümkün olduğunda, yapılan her çağrı çevreleyen [CONCURRENCY::Task:: get](reference/task-class.md#get) ve [CONCURRENCY::Task:: wait](reference/task-class.md#wait) ile bir `try` / `catch` kurtarabileceğiniz hataları işlemek için Kaynak. Bir görev bir özel durum oluşturur ve görev kendi devamlılıklarının veya ana uygulama özel durum yakalandı, uygulama çalışma zamanı sonlandırır.

- Bir görev tabanlı devamlılık her zaman çalışır; Öncül görev başarıyla tamamlandı, özel durum oluşturdu veya iptal edildi önemli değildir. Değer tabanlı devamlılık, öncül görevin oluşturur ya da iptal eder çalıştırmaz.

- Görev tabanlı devamlılık her zaman çalıştığından, bir görev tabanlı devamlılık, devamlılık zincirini sonunda eklenip eklenmeyeceğini göz önünde bulundurun. Bu, kodunuzun tüm özel durumları gözlemlemesini garanti yardımcı olabilir.

- Çalışma zamanı [concurrency::task_canceled](../../parallel/concrt/reference/task-canceled-class.md) çağırdığınızda [CONCURRENCY::Task:: get](reference/task-class.md#get) ve görev iptal edildi.

- Çalışma zamanı özel durumlarını Basit görevler ve aracılar için yönetmez.

##  <a name="top"></a> Bu belgede

- [Görevler ve devamlılıklar](#tasks)

- [Görev grupları ve paralel algoritmalar](#task_groups)

- [Çalışma zamanı tarafından oluşturulan özel durumları](#runtime)

- [Birden çok özel durum](#multiple)

- [İptal](#cancellation)

- [Basit Görevler](#lwts)

- [Zaman Uyumsuz Aracılar](#agents)

##  <a name="tasks"></a> Görevler ve devamlılıklar

Bu bölümde, çalışma zamanı tarafından oluşturulan özel durumları nasıl işlediğini açıklar [concurrency::task](../../parallel/concrt/reference/task-class.md) nesneleri ve bunların devamlılığını. Görev ve devamı modeli hakkında daha fazla bilgi için bkz. [görev Paralelliği](../../parallel/concrt/task-parallelism-concurrency-runtime.md).

Geçirdiğiniz iş işlevin gövdesinde bir özel durum throw ne zaman bir `task` nesnesi, çalışma zamanı bu özel durum depolar ve çağıran bağlamına sıralar [CONCURRENCY::Task:: get](reference/task-class.md#get) veya [eşzamanlılık:: Task::wait](reference/task-class.md#wait). Belge [görev Paralelliği](../../parallel/concrt/task-parallelism-concurrency-runtime.md) açıklar özetlemek şekilde ancak değer tabanlı devamlılık karşı görev tabanlı bir değer tabanlı devamlılık türünde bir parametre alan `T` ve görev tabanlı devamlılık türünde bir parametre alır `task<T>`. Bir veya daha fazla değer tabanlı devamlılık oluşturan bir görev varsa bu devamlılıklar olarak çalıştırılması zamanlanan değil. Aşağıdaki örnekte, bu davranışı gösterilmektedir:

[!code-cpp[concrt-eh-task#1](../../parallel/concrt/codesnippet/cpp/exception-handling-in-the-concurrency-runtime_1.cpp)]

Bir görev tabanlı devamlılık, öncül görev tarafından oluşturulan herhangi bir özel durumu işlemek sağlar. Bir görev tabanlı devamlılık her zaman çalışır; görev başarıyla tamamlandı, özel durum oluşturdu veya iptal edildi önemli değildir. Bir görev bir özel durum oluşturduğunda, görev tabanlı devamlılık çalışmak üzere zamanlanır. Aşağıdaki örnek, her zaman oluşturur bir görevi gösterir. Görev devamlılıkları iki; yine de sahip istiyor musunuz? değer tabanlı biridir ve diğer görev-tabanlı. Görev tabanlı özel durumu her zaman çalışır ve bu nedenle, öncül görev tarafından oluşturulan özel durum yakalamak mümkündür. Her iki devamlar için örnek bekler, görev her zaman zaman özel durum nedeniyle yeniden özel durum `task::get` veya `task::wait` çağrılır.

[!code-cpp[concrt-eh-continuations#1](../../parallel/concrt/codesnippet/cpp/exception-handling-in-the-concurrency-runtime_2.cpp)]

İşleyebilen özel durumları yakalamak için görev tabanlı devamlılık kullanmanızı öneririz. Görev tabanlı devamlılık her zaman çalıştığından, bir görev tabanlı devamlılık, devamlılık zincirini sonunda eklenip eklenmeyeceğini göz önünde bulundurun. Bu, kodunuzun tüm özel durumları gözlemlemesini garanti yardımcı olabilir. Aşağıdaki örnek, bir temel değer tabanlı devamlılık zincirini göstermektedir. Üçüncü görev zinciri oluşturur ve bu nedenle onu izleyen değer tabanlı devamlılık çalıştırılamaz. Ancak, son devam görevi dayalıdır ve bu nedenle her zaman çalışır. Bu son devam üçüncü görev tarafından oluşturulan özel durum işleme.

Yapabilecekleriniz en belirli özel durumları yakalamak öneririz. Belirli özel durumları yakalamak için yoksa, bu son görev tabanlı devamlılık atlayabilirsiniz. Herhangi bir özel durum işlenmemiş olarak kalır ve uygulamayı sonlandırabilirsiniz.

[!code-cpp[concrt-eh-task-chain#1](../../parallel/concrt/codesnippet/cpp/exception-handling-in-the-concurrency-runtime_3.cpp)]

> [!TIP]
>  Kullanabileceğiniz [concurrency::task_completion_event::set_exception](../../parallel/concrt/reference/task-completion-event-class.md) yöntemi bir özel görev tamamlama olayı ile ilişkilendirilecek. Belge [görev Paralelliği](../../parallel/concrt/task-parallelism-concurrency-runtime.md) açıklar [concurrency::task_completion_event](../../parallel/concrt/reference/task-completion-event-class.md) daha ayrıntılı sınıfı.

[CONCURRENCY::task_canceled](../../parallel/concrt/reference/task-canceled-class.md) ilişkili bir önemli bir çalışma zamanı özel durum türü `task`. Çalışma zamanı `task_canceled` çağırdığınızda `task::get` ve görev iptal edildi. (Buna karşılık, `task::wait` döndürür [task_status::canceled](reference/concurrency-namespace-enums.md#task_group_status) ve oluşturmaz.) Catch ve görev tabanlı devamlılık veya çağırdığınızda bu özel durumu işle `task::get`. Görev iptali hakkında daha fazla bilgi için bkz: [ppl'de iptal](cancellation-in-the-ppl.md).

> [!CAUTION]
>  Hiçbir zaman throw `task_canceled` kodunuzdan. Çağrı [concurrency::cancel_current_task](reference/concurrency-namespace-functions.md#cancel_current_task) yerine.

Bir görev bir özel durum oluşturur ve görev kendi devamlılıklarının veya ana uygulama özel durum yakalandı, uygulama çalışma zamanı sonlandırır. Uygulamanızı bir çökme gerçekleşirse, Visual Studio C++ özel durumlarını oluşturulduğunda Kes yapılandırabilirsiniz. İşlenmeyen özel durumun konumu tanılamanızdan sonra görev tabanlı devamlılık işlenmesi için kullanın.

Bölüm [özel durumlar çalışma zamanı tarafından](#runtime) bu belgede daha ayrıntılı çalışma zamanı özel durumları ile nasıl çalışılacağını açıklar.

[[Üst](#top)]

##  <a name="task_groups"></a> Görev grupları ve paralel algoritmalar

Bu bölümde, çalışma zamanının görev grupları tarafından oluşturulan özel durumları nasıl işlediğini açıklar. Bu bölüm ayrıca için paralel algoritmalar gibi geçerlidir [concurrency::parallel_for](reference/concurrency-namespace-functions.md#parallel_for), bu algoritmalar Görev gruplarına oluşturun.

> [!CAUTION]
>  Özel durumlar bağımlı görevlere sahip etkilerini anladığınızdan emin olun. Özel durum işleme görevleri veya paralel algoritmalar ile kullanmaya ilişkin önerilen yöntemler için bkz: [anlayın nasıl iptal ve özel durum işleme etkileyen nesne yok etme](../../parallel/concrt/best-practices-in-the-parallel-patterns-library.md#object-destruction) bölümünde paralel en iyi uygulamalar Desenler kitaplığı konusu.

Görev grupları hakkında daha fazla bilgi için bkz. [görev Paralelliği](../../parallel/concrt/task-parallelism-concurrency-runtime.md). Paralel algoritmalar hakkında daha fazla bilgi için bkz. [paralel algoritmalar](../../parallel/concrt/parallel-algorithms.md).

Geçirdiğiniz iş işlevin gövdesinde bir özel durum throw ne zaman bir [concurrency::task_group](reference/task-group-class.md) veya [concurrency::structured_task_group](../../parallel/concrt/reference/structured-task-group-class.md) nesnesi, çalışma zamanı bu özel durum depolar ve onu sürekliliğe devreder çağıran bağlamını [CONCURRENCY::task_group:: wait](reference/task-group-class.md#wait), [CONCURRENCY::structured_task_group](reference/structured-task-group-class.md#wait), [run_and_wait](reference/task-group-class.md#run_and_wait), veya [CONCURRENCY::structured_task_group:: run_and_wait](reference/structured-task-group-class.md#run_and_wait). Ayrıca çalışma zamanı (alt görev grupları de dahil) görev grubu olan tüm etkin görevleri durdurur ve henüz başlamamış herhangi bir görevi atar.

Aşağıdaki örnek bir özel durum oluşturan iş işlevi temel yapısını gösterir. Örnekte bir `task_group` iki değerini yazdırmak için nesne `point` paralel nesneler. `print_point` İş işlevi değerlerini yazdırır bir `point` konsola nesne. Giriş değeri ise iş işlevi bir özel durum oluşturur. `NULL`. Çalışma zamanı bu özel durumun depolar ve çağıran bağlamına sıralar `task_group::wait`.

[!code-cpp[concrt-eh-task-group#1](../../parallel/concrt/codesnippet/cpp/exception-handling-in-the-concurrency-runtime_4.cpp)]

Bu örnek aşağıdaki çıktıyı üretir.

```Output
X = 15, Y = 30Caught exception: point is NULL.
```

Özel durum işleme bir görev grubunda kullanan tam bir örnek için bkz. [nasıl yapılır: Özel durum paralel bir döngüden kurtulmak için işlemeyi kullanma](../../parallel/concrt/how-to-use-exception-handling-to-break-from-a-parallel-loop.md).

[[Üst](#top)]

##  <a name="runtime"></a> Çalışma zamanı tarafından oluşturulan özel durumları

Bir özel durum, çalışma zamanı çağrısından neden olabilir. Çoğu özel durum türlerini hariç [concurrency::task_canceled](../../parallel/concrt/reference/task-canceled-class.md) ve [concurrency::operation_timed_out](../../parallel/concrt/reference/operation-timed-out-class.md), bir programlama hatasından kaynaklanıyor olabilir. Bu hatalar genellikle kurtarılamaz olarak kabul edilir ve bu nedenle yakalandı veya uygulama kodu tarafından işlenir. Yalnızca catch veya programlama hatalarını tanılamak gerektiğinde kurtarılamaz hatalar, uygulama kodunda işlemeye öneririz. Ancak, çalışma zamanı tarafından tanımlanan özel durum türleri, programlama hatalarını tanılamanıza yardımcı olabileceğini anlama.

Özel durum işleme mekanizmasını iş işlevleri tarafından oluşturulan özel durumlar olarak çalışma zamanı tarafından oluşturulan özel durumlar için aynıdır. Örneğin, [concurrency::receive](reference/concurrency-namespace-functions.md#receive) işlevi atar `operation_timed_out` zaman bunu almaz bir ileti belirtilen süre içinde. Varsa `receive` iş işlevinde bir özel durum oluşturur, bir görev grubuna geçirirsiniz, çalışma zamanı bu özel durum depolar ve çağıran bağlamına sıralar `task_group::wait`, `structured_task_group::wait`, `task_group::run_and_wait`, veya `structured_task_group::run_and_wait`.

Aşağıdaki örnekte [concurrency::parallel_invoke](reference/concurrency-namespace-functions.md#parallel_invoke) iki görevi paralel olarak çalıştırmak için kullanılan algoritma. İlk görev beş saniye bekler ve ardından bir ileti arabelleği için bir ileti gönderir. İkinci görev kullanan `receive` işlevini aynı ileti arabellekteki ileti almak için üç saniye bekleyin. `receive` İşlevi atar `operation_timed_out` süre içinde bir ileti almazsa.

[!code-cpp[concrt-eh-time-out#1](../../parallel/concrt/codesnippet/cpp/exception-handling-in-the-concurrency-runtime_5.cpp)]

Bu örnek aşağıdaki çıktıyı üretir.

```Output
The operation timed out.
```

Olağan dışı sonlandırma uygulamanızın önlemek için kodunuzun çalışma zamanına çağırdığında, özel durumları işler emin olun. Örneğin, eşzamanlılık çalışma zamanı kullanan dış koda bir üçüncü taraf kitaplığı çağırdığınızda ayrıca özel durumları işleme.

[[Üst](#top)]

##  <a name="multiple"></a> Birden çok özel durum

Bir görev veya paralel algoritma birden çok özel durum alırsa, çalışma zamanı bu özel durumlar çağıran bağlamını yalnızca biri sürekliliğe devreder. Çalışma zamanı, sürekliliğe devreder hangi özel durumun garanti etmez.

Aşağıdaki örnekte `parallel_for` numaraları konsola yazdırmak için algoritma. Giriş değeri bazı en düşük değerden küçük veya bazı maksimum değerden daha büyük ise bir özel durum oluşturur. Bu örnekte, birden çok iş işlevlerini bir durum oluşturabilir.

[!code-cpp[concrt-eh-multiple#1](../../parallel/concrt/codesnippet/cpp/exception-handling-in-the-concurrency-runtime_6.cpp)]

Bu örnek için örnek çıktı aşağıda gösterilmiştir.

```Output
8293104567Caught exception: -5: the value is less than the minimum.
```

[[Üst](#top)]

##  <a name="cancellation"></a> İptal etme

Tüm özel durumlar, bir hata gösterir. Örneğin, bir arama algoritması, özel durum işleme, ilişkili görev sonucu bulduğunda durdurmak için kullanabilirsiniz. Kodunuzda iptal mekanizmaları kullanma hakkında daha fazla bilgi için bkz. [ppl'de iptal](../../parallel/concrt/cancellation-in-the-ppl.md).

[[Üst](#top)]

##  <a name="lwts"></a> Basit görevler

Basit bir görev doğrudan zamanlama görevdir bir [concurrency::Scheduler](../../parallel/concrt/reference/scheduler-class.md) nesne. Basit görevler daha az yüke sıradan görevleri gerçekleştirirsiniz. Ancak, çalışma zamanı, hafif görevler tarafından oluşturulan özel durumları yakalamaz. Bunun yerine, özel durum işlemi sonlandırır ve varsayılan işlenmeyen özel durum işleyicisi tarafından yakalanır. Bu nedenle, uygun bir hata işleme mekanizması, uygulamanızı kullanın. Basit görevler hakkında daha fazla bilgi için bkz: [Görev Zamanlayıcı](../../parallel/concrt/task-scheduler-concurrency-runtime.md).

[[Üst](#top)]

##  <a name="agents"></a> Zaman uyumsuz aracılar

Basit görevler gibi çalışma zamanı zaman uyumsuz aracılar tarafından oluşturulan özel durumları yönetmez.

Aşağıdaki örnek, türetilen sınıftaki özel durumları işlemek için bir yol gösterir [concurrency::agent](../../parallel/concrt/reference/agent-class.md). Bu örnek tanımlar `points_agent` sınıfı. `points_agent::run` Yöntemi okuma `point` ileti arabellek nesneleri ve bunları konsola yazdırır. `run` Yöntemi bir özel durum oluşturursa, alırsa bir `NULL` işaretçi.

`run` Yöntemi çevreleyen tüm iş bir `try` - `catch` blok. `catch` Blok özel durum iletisi arabelleğinde depolar. Uygulama, aracı bittikten sonra aracıyı bu buffer'dan alınan okuyarak hatayla olup olmadığını denetler.

[!code-cpp[concrt-eh-agents#1](../../parallel/concrt/codesnippet/cpp/exception-handling-in-the-concurrency-runtime_7.cpp)]

Bu örnek aşağıdaki çıktıyı üretir.

```Output
X: 10 Y: 20
X: 20 Y: 30
error occurred in agent: point must not be NULL
the status of the agent is: done
```

Çünkü `try` - `catch` blok var. dışında `while` aracı döngü sona ilk hata ile karşılaştığında işleme. Varsa `try` - `catch` blok olan içinde `while` döngü, aracıyı devam bir hata gerçekleştikten sonra.

Çalışırken hataları için aracı başka bir bileşen takip edebilmeniz Bu örnek özel durumları ileti arabelleğinde depolar. Bu örnekte bir [concurrency::single_assignment](../../parallel/concrt/reference/single-assignment-class.md) hata depolamak için nesne. Burada bir aracı birden çok özel durum işleme durumda `single_assignment` sınıfı geçirilen yalnızca ilk iletiyi kendisine depolar. Yalnızca son özel durum depolamak için kullanmak [concurrency::overwrite_buffer](../../parallel/concrt/reference/overwrite-buffer-class.md) sınıfı. Tüm özel durumları depolamak için kullanmak [concurrency::unbounded_buffer](reference/unbounded-buffer-class.md) sınıfı. Bu ileti blokları hakkında daha fazla bilgi için bkz: [zaman uyumsuz ileti blokları](../../parallel/concrt/asynchronous-message-blocks.md).

Zaman uyumsuz aracılar hakkında daha fazla bilgi için bkz: [zaman uyumsuz aracılar](../../parallel/concrt/asynchronous-agents.md).

[[Üst](#top)]

##  <a name="summary"></a> Özeti

[[Üst](#top)]

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Çalışma Zamanı](../../parallel/concrt/concurrency-runtime.md)<br/>
[Görev Paralelliği](../../parallel/concrt/task-parallelism-concurrency-runtime.md)<br/>
[Paralel Algoritmalar](../../parallel/concrt/parallel-algorithms.md)<br/>
[PPL'de İptal](cancellation-in-the-ppl.md)<br/>
[Görev Zamanlayıcısı](../../parallel/concrt/task-scheduler-concurrency-runtime.md)<br/>
[Zaman Uyumsuz Aracılar](../../parallel/concrt/asynchronous-agents.md)
