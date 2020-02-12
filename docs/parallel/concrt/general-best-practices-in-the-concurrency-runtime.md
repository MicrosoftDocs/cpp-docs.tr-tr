---
title: Eşzamanlılık Çalışma Zamanındaki Genel En İyi Yöntemler
ms.date: 11/04/2016
helpviewer_keywords:
- Concurrency Runtime, general best practices
ms.assetid: ce5c784c-051e-44a6-be84-8b3e1139c18b
ms.openlocfilehash: 15bae5ba25da4987b076cf3de67cd8484fe47df8
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77141769"
---
# <a name="general-best-practices-in-the-concurrency-runtime"></a>Eşzamanlılık Çalışma Zamanındaki Genel En İyi Yöntemler

Bu belgede Eşzamanlılık Çalışma Zamanı birden çok alanına uygulanan en iyi uygulamalar açıklanmaktadır.

## <a name="top"></a>Başlıklı

Bu belgede aşağıdaki bölümler yer alır:

- [Mümkün olduğunda birlikte bulunan eşitleme yapılarını kullanın](#synchronization)

- [Sonuç veren uzun görevlerden kaçının](#yield)

- [Yüksek gecikme süresini engelleyen veya olmayan Işlemler için fazla abonelik kullan](#oversubscription)

- [Mümkün olduğunda eşzamanlı bellek yönetimi Işlevlerini kullanma](#memory)

- [Eşzamanlılık nesnelerinin ömrünü yönetmek için, RAYıı kullanma](#raii)

- [Genel kapsamda eşzamanlılık nesneleri oluşturma](#global-scope)

- [Paylaşılan veri kesimlerinde eşzamanlılık nesneleri kullanma](#shared-data)

## <a name="synchronization"></a>Mümkün olduğunda birlikte bulunan eşitleme yapılarını kullanın

Eşzamanlılık Çalışma Zamanı, dış eşitleme nesnesi gerektirmeyen çok sayıda eşzamanlılık güvenli yapı sağlar. Örneğin, [concurrency:: concurrent_vector](../../parallel/concrt/reference/concurrent-vector-class.md) sınıfı eşzamanlılık açısından güvenli ekleme ve öğe erişim işlemleri sağlar. Burada eşzamanlılık açısından güvenli, işaretçiler veya yineleyiciler her zaman geçerlidir. Bu, öğe başlatma garantisi veya belirli bir geçiş düzeni değildir. Ancak, bir kaynağa özel erişim gerektiren durumlarda, çalışma zamanı [eşzamanlılık:: critical_section](../../parallel/concrt/reference/critical-section-class.md), [eşzamanlılık:: reader_writer_lock](../../parallel/concrt/reference/reader-writer-lock-class.md)ve [concurrency:: Event](../../parallel/concrt/reference/event-class.md) sınıflarını sağlar. Bu türler birlikte çalışır; Bu nedenle, Görev Zamanlayıcı, ilk görevin verileri beklediği şekilde işleme kaynaklarını başka bir bağlam ile yeniden tahsis edebilir. Mümkün olduğunda, bu eşitleme türlerini, Windows API 'si tarafından sağlananlar gibi, birlikte çalışmayan diğer eşitleme mekanizmaları yerine kullanın. Bu eşitleme türleri ve bir kod örneği hakkında daha fazla bilgi için bkz. [eşitleme veri yapıları](../../parallel/concrt/synchronization-data-structures.md) ve [eşitleme VERI yapılarını Windows API ile karşılaştırma](../../parallel/concrt/comparing-synchronization-data-structures-to-the-windows-api.md).

[[Üst](#top)]

## <a name="yield"></a>Sonuç veren uzun görevlerden kaçının

Görev Zamanlayıcı birlikte davrandığı için, görevler arasında eşitliği sağlamaz. Bu nedenle, bir görev diğer görevlerin başlamasını önleyebilir. Bazı durumlarda bu kabul edilebilir olsa da, diğer durumlarda bu, kilitlenme veya başlangıçları oluşmasına neden olabilir.

Aşağıdaki örnek, ayrılan işlem kaynakları sayısından daha fazla görev gerçekleştirir. İlk görev Görev Zamanlayıcısına gelmez ve bu nedenle ikinci görev ilk görev bitene kadar başlamaz.

[!code-cpp[concrt-cooperative-tasks#1](../../parallel/concrt/codesnippet/cpp/general-best-practices-in-the-concurrency-runtime_1.cpp)]

Bu örnek aşağıdaki çıktıyı üretir:

1: 250000000 1: 500000000 1: 750000000 1: 1000000000 2: 250000000 2: 500000000 2: 750000000 2: 1000000000

İki görev arasında birlikte işlem etkinleştirmenin birkaç yolu vardır. Tek yönlü, uzun süre çalışan bir görevde görev zamanlayıcısını zaman zaman elde etmenin bir yoludur. Aşağıdaki örnek, başka bir görevin çalıştırılabilmesi için Görev Zamanlayıcısına yürütülmesi için [concurrency:: Context:: yield](reference/context-class.md#yield) metodunu çağırmak üzere `task` işlevini değiştirir.

[!code-cpp[concrt-cooperative-tasks#2](../../parallel/concrt/codesnippet/cpp/general-best-practices-in-the-concurrency-runtime_2.cpp)]

Bu örnek aşağıdaki çıktıyı üretir:

```Output
1: 250000000
2: 250000000
1: 500000000
2: 500000000
1: 750000000
2: 750000000
1: 1000000000
2: 1000000000
```

`Context::Yield` yöntemi, geçerli iş parçacığının ait olduğu Zamanlayıcı üzerinde yalnızca başka bir etkin iş parçacığı, hafif bir görev veya başka bir işletim sistemi iş parçacığı oluşturur. Bu yöntem, [concurrency:: task_group](reference/task-group-class.md) veya [concurrency:: structured_task_group](../../parallel/concrt/reference/structured-task-group-class.md) nesnesinde çalışmak üzere zamanlanmış ancak henüz başlatılmamış bir işe vermez.

Uzun süre çalışan görevler arasında ortak işlemi etkinleştirmenin başka yolları vardır. Büyük bir görevi daha küçük alt görevlere kesebilirsiniz. Ayrıca, uzun bir görev sırasında fazla aboneliği etkinleştirebilirsiniz. Fazla abonelik, kullanılabilir donanım iş parçacığı sayısından daha fazla iş parçacığı oluşturmanızı sağlar. Aşırı abonelik özellikle uzun bir görev yüksek miktarda gecikme içerdiğinde (örneğin, diskten veya bir ağ bağlantısından veri okurken) yararlıdır. Hafif görevler ve fazla abonelik hakkında daha fazla bilgi için bkz. [Görev Zamanlayıcı](../../parallel/concrt/task-scheduler-concurrency-runtime.md).

[[Üst](#top)]

## <a name="oversubscription"></a>Yüksek gecikme süresini engelleyen veya olmayan Işlemler için fazla abonelik kullan

Eşzamanlılık Çalışma Zamanı, [eşzamanlılık:: critical_section](../../parallel/concrt/reference/critical-section-class.md)gibi görevlerin birbirlerine engel ve bir şekilde dönüşme olanağı sağlayan eşitleme temelleri sağlar. Bir görev birlikte çalışırken ya da olduğunda, Görev Zamanlayıcı, ilk görevin verileri beklediği şekilde işleme kaynaklarını başka bir bağlam ile yeniden tahsis edebilir.

Eşzamanlılık Çalışma Zamanı tarafından sunulan birlikte çalışmayan engelleme mekanizmasını kullanamadığı durumlar vardır. Örneğin, kullandığınız bir dış kitaplık farklı bir eşitleme mekanizması kullanabilir. Diğer bir örnek, örneğin, bir ağ bağlantısından verileri okumak için Windows API `ReadFile` işlevini kullandığınızda, yüksek gecikme süresine sahip olabilecek bir işlem gerçekleştirmeniz. Bu durumlarda, fazla abonelik başka bir görev boştayken diğer görevlerin çalışmasını sağlayabilir. Fazla abonelik, kullanılabilir donanım iş parçacığı sayısından daha fazla iş parçacığı oluşturmanızı sağlar.

Belirtilen URL 'de dosyayı indiren `download`aşağıdaki işlevi göz önünde bulundurun. Bu örnek, etkin iş parçacıklarının sayısını geçici olarak artırmak için [concurrency:: Context:: Oversubscribe](reference/context-class.md#oversubscribe) metodunu kullanır.

[!code-cpp[concrt-download-oversubscription#4](../../parallel/concrt/codesnippet/cpp/general-best-practices-in-the-concurrency-runtime_3.cpp)]

`GetHttpFile` işlevi potansiyel olarak görünmeyen bir işlem gerçekleştirdiğinden, çok sayıda abonelik geçerli görev için veri beklediği için diğer görevlerin çalışmasını sağlayabilir. Bu örneğin tüm sürümü için bkz. [nasıl yapılır: gecikme gecikmesini anlamak Için fazla abonelik kullanma](../../parallel/concrt/how-to-use-oversubscription-to-offset-latency.md).

[[Üst](#top)]

## <a name="memory"></a>Mümkün olduğunda eşzamanlı bellek yönetimi Işlevlerini kullanma

Görece kısa bir yaşam süresine sahip küçük nesneler genellikle ayıran ayrıntılı görevleriniz olduğunda, [concurrency::](reference/concurrency-namespace-functions.md#alloc) allocate ve [concurrency:: Free](reference/concurrency-namespace-functions.md#free)bellek yönetimi işlevlerini kullanın. Eşzamanlılık Çalışma Zamanı çalışan her iş parçacığı için ayrı bir bellek önbelleği barındırır. `Alloc` ve `Free` işlevleri, kilitler veya bellek engelleri kullanımı olmadan bu önbelleklerden bellek ayırır ve serbest bırakırsanız.

Bu bellek yönetimi işlevleri hakkında daha fazla bilgi için bkz. [Görev Zamanlayıcı](../../parallel/concrt/task-scheduler-concurrency-runtime.md). Bu işlevleri kullanan bir örnek için bkz. [nasıl yapılır: bellek performansını artırmak Için ayırma ve serbest kullanma](../../parallel/concrt/how-to-use-alloc-and-free-to-improve-memory-performance.md).

[[Üst](#top)]

## <a name="raii"></a>Eşzamanlılık nesnelerinin ömrünü yönetmek için, RAYıı kullanma

Eşzamanlılık Çalışma Zamanı, iptal gibi özellikleri uygulamak için özel durum işlemeyi kullanır. Bu nedenle, çalışma zamanına çağrı yaptığınızda veya çalışma zamanına çağıran başka bir kitaplığı çağırdığınızda özel durum güvenli kodu yazın.

*Kaynak alımı başlatma* (rampa) deseninin belirli bir kapsamdaki eşzamanlılık nesnesinin ömrünü güvenli bir şekilde yönetmenin bir yolu vardır. OYıı deseninin altında, yığın üzerinde bir veri yapısı ayrılır. Bu veri yapısı oluşturulduğunda bir kaynağı başlatır veya alır ve veri yapısı yok edildiğinde bu kaynağı yok eder veya serbest bırakır. RAMPALAMA kapsamı, yok edicinin kapsayan kapsam gelmeden önce çağrıldığından emin olur. Bu model, bir işlev birden çok `return` deyimi içerdiğinde yararlıdır. Bu model ayrıca özel durum güvenli kod yazmanıza yardımcı olur. `throw` bir ifade yığının geriye doğru neden olduğunda, bu nesne için yıkıcı çağrılır; Bu nedenle, kaynak her zaman doğru şekilde silinir veya serbest bırakılır.

Çalışma zamanı, KORII deseninin kullanıldığı birkaç sınıfı tanımlar, örneğin, [concurrency:: critical_section:: scoped_lock](../../parallel/concrt/reference/critical-section-class.md#critical_section__scoped_lock_class) ve [concurrency:: reader_writer_lock:: scoped_lock](reference/reader-writer-lock-class.md#scoped_lock_class). Bu yardımcı sınıflar, *kapsamlı kilitler*olarak bilinir. Bu sınıflar [eşzamanlılık:: critical_section](../../parallel/concrt/reference/critical-section-class.md) veya [eşzamanlılık:: reader_writer_lock](../../parallel/concrt/reference/reader-writer-lock-class.md) nesneleriyle çalışırken çeşitli avantajlar sağlar. Bu sınıfların Oluşturucusu, belirtilen `critical_section` veya `reader_writer_lock` nesnesine erişim sağlar; yıkıcı bu nesneye erişimi serbest bırakır. Kapsamlı bir kilit, yok edildiğinde otomatik olarak karşılıklı dışlama nesnesine erişim yayınlamadığından, temeldeki nesnenin kilidini el ile açamazsınız.

Bir dış kitaplık tarafından tanımlanan ve bu nedenle değiştirilemeyen `account`aşağıdaki sınıfı göz önünde bulundurun.

[!code-cpp[concrt-account-transactions#1](../../parallel/concrt/codesnippet/cpp/general-best-practices-in-the-concurrency-runtime_4.h)]

Aşağıdaki örnek, `account` nesnesi üzerinde paralel olarak birden çok işlem gerçekleştirir. Bu örnek, `account` sınıfı eşzamanlılık açısından güvenli olmadığından `account` nesnesine erişimi senkronize etmek için bir `critical_section` nesnesi kullanır. Her paralel işlem, işlem başarılı veya başarısız olduğunda `critical_section` nesnesinin kilidinin açık olmasını sağlamak için bir `critical_section::scoped_lock` nesnesi kullanır. Hesap bakiyesi negatifse `withdraw` işlem bir özel durum oluşturarak başarısız olur.

[!code-cpp[concrt-account-transactions#2](../../parallel/concrt/codesnippet/cpp/general-best-practices-in-the-concurrency-runtime_5.cpp)]

Bu örnek aşağıdaki örnek çıktıyı üretir:

```Output
Balance before deposit: 1924
Balance after deposit: 2924
Balance before withdrawal: 2924
Balance after withdrawal: -76
Balance before withdrawal: -76
Error details:
    negative balance: -76
```

Eşzamanlılık nesnelerinin ömrünü yönetmek için kıI modelini kullanan ek örnekler için, bkz [. Izlenecek yol: Kullanıcı arabirimi Iş parçacığından Işi kaldırma](../../parallel/concrt/walkthrough-removing-work-from-a-user-interface-thread.md), [nasıl yapılır: bağlam sınıfını kullanarak bir örnek semaforu uygulama](../../parallel/concrt/how-to-use-the-context-class-to-implement-a-cooperative-semaphore.md)ve [nasıl yapılır: gecikme süresini kaydırmak için aşırı abonelik kullanma](../../parallel/concrt/how-to-use-oversubscription-to-offset-latency.md).

[[Üst](#top)]

## <a name="global-scope"></a>Genel kapsamda eşzamanlılık nesneleri oluşturma

Genel kapsamda bir eşzamanlılık nesnesi oluşturduğunuzda, uygulamanızda kilitlenme veya bellek erişimi ihlalleri gibi sorunların oluşmasına neden olabilirsiniz.

Örneğin, bir Eşzamanlılık Çalışma Zamanı nesnesi oluşturduğunuzda, çalışma zamanı henüz oluşturulmadıysa sizin için varsayılan bir zamanlayıcı oluşturur. Genel nesne oluşturma sırasında oluşturulan bir çalışma zamanı nesnesi, çalışma zamanının bu varsayılan zamanlayıcıyı oluşturmasına neden olur. Ancak, bu işlem dahili bir kilit alır ve bu, Eşzamanlılık Çalışma Zamanı altyapısını destekleyen diğer nesnelerin başlatılmasına engel olabilir. Bu iç kilit, henüz başlatılmamış başka bir altyapı nesnesi tarafından gerekli olabilir ve bu nedenle uygulamanızda kilitlenmenin oluşmasına neden olabilir.

Aşağıdaki örnek, genel bir [eşzamanlılık:: Scheduler](../../parallel/concrt/reference/scheduler-class.md) nesnesinin oluşturulmasını gösterir. Bu model yalnızca `Scheduler` sınıfı için değil, Eşzamanlılık Çalışma Zamanı tarafından sağlanmış diğer tüm türler için de geçerlidir. Uygulamanızda beklenmeyen davranışlara neden olabileceğinden, bu kalıbı takip etmemenizi öneririz.

[!code-cpp[concrt-global-scheduler#1](../../parallel/concrt/codesnippet/cpp/general-best-practices-in-the-concurrency-runtime_6.cpp)]

`Scheduler` nesneleri oluşturmanın doğru yolu örnekleri için bkz. [Görev Zamanlayıcı](../../parallel/concrt/task-scheduler-concurrency-runtime.md).

[[Üst](#top)]

## <a name="shared-data"></a>Paylaşılan veri kesimlerinde eşzamanlılık nesneleri kullanma

Eşzamanlılık Çalışma Zamanı, paylaşılan bir veri bölümünde eşzamanlılık nesnelerinin kullanımını desteklemez, örneğin, [data_seg](../../preprocessor/data-seg.md)`#pragma` yönergesi tarafından oluşturulan bir veri bölümü. İşlem sınırları genelinde paylaşılan bir eşzamanlılık nesnesi, çalışma zamanını tutarsız veya geçersiz bir duruma geçirebilir.

[[Üst](#top)]

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Çalışma Zamanı En İyi Yöntemleri](../../parallel/concrt/concurrency-runtime-best-practices.md)<br/>
[Paralel Desen Kitaplığı (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md)<br/>
[Zaman Uyumsuz Aracılar Kitaplığı](../../parallel/concrt/asynchronous-agents-library.md)<br/>
[Görev Zamanlayıcı](../../parallel/concrt/task-scheduler-concurrency-runtime.md)<br/>
[Eşitleme Veri Yapıları](../../parallel/concrt/synchronization-data-structures.md)<br/>
[Eşitleme Veri Yapılarını Windows API ile Karşılaştırma](../../parallel/concrt/comparing-synchronization-data-structures-to-the-windows-api.md)<br/>
[Nasıl yapılır: Bellek Performansını Artırmak için Alloc ve Free Kullanma](../../parallel/concrt/how-to-use-alloc-and-free-to-improve-memory-performance.md)<br/>
[Nasıl yapılır: Gecikmeyi Dengelemek için Aşırı Aboneliği Kullanma](../../parallel/concrt/how-to-use-oversubscription-to-offset-latency.md)<br/>
[Nasıl yapılır: Bağlam Sınıfını İşbirlikçi Semafor Uygulamak için Kullanma](../../parallel/concrt/how-to-use-the-context-class-to-implement-a-cooperative-semaphore.md)<br/>
[İzlenecek Yol: Kullanıcı Arabirimi İş Parçacığından İşi Kaldırma](../../parallel/concrt/walkthrough-removing-work-from-a-user-interface-thread.md)<br/>
[Paralel Desen Kitaplığı'ndaki En İyi Yöntemler](../../parallel/concrt/best-practices-in-the-parallel-patterns-library.md)<br/>
[Zaman Uyumsuz Aracılar Kitaplığı'ndaki En İyi Yöntemler](../../parallel/concrt/best-practices-in-the-asynchronous-agents-library.md)
