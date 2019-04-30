---
title: Eşzamanlılık Çalışma Zamanındaki Genel En İyi Yöntemler
ms.date: 11/04/2016
helpviewer_keywords:
- Concurrency Runtime, general best practices
ms.assetid: ce5c784c-051e-44a6-be84-8b3e1139c18b
ms.openlocfilehash: e25011e2466d76c946cc55421ed228c8ea174161
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62413924"
---
# <a name="general-best-practices-in-the-concurrency-runtime"></a>Eşzamanlılık Çalışma Zamanındaki Genel En İyi Yöntemler

Bu belgede, birden fazla eşzamanlılık çalışma zamanı alanlarına uygulanan en iyi uygulamalar açıklanmaktadır.

##  <a name="top"></a> Bölümleri

Bu belgede aşağıdaki bölümler yer alır:

- [Mümkün olduğunda işbirliği halinde eşitleme yapılarını kullanma](#synchronization)

- [Yield değil verimsiz uzun görevlerden kaçınma](#yield)

- [Gecikmeyi engelleyen veya gecikmesi fazla olan işlemleri için aşırı aboneliği kullanma](#oversubscription)

- [Mümkün olduğunda eşzamanlı bellek yönetimi işlevlerini kullanma](#memory)

- [Eşzamanlılık nesnelerinin kullanım süresini yönetmek için RAII kullanma](#raii)

- [Genel kapsamda eşzamanlılık nesneleri oluşturma](#global-scope)

- [Paylaşılan veri kesimlerinde eşzamanlılık nesneleri kullanma](#shared-data)

##  <a name="synchronization"></a> Mümkün olduğunda işbirliği halinde eşitleme yapılarını kullanma

Eşzamanlılık Çalışma zamanı bir dış eşitleme nesnesi gerektirmeyen çok sayıda eşzamanlı güvenli yapıları sağlar. Örneğin, [concurrency::concurrent_vector](../../parallel/concrt/reference/concurrent-vector-class.md) sağlar sınıfını eşzamanlılık açısından güvenli sona Ekle ve işlem erişim öğesi. Ancak, bir kaynağa özel erişim gerektiren burada durumlarda, çalışma zamanı sağlar [concurrency::critical_section](../../parallel/concrt/reference/critical-section-class.md), [concurrency::reader_writer_lock](../../parallel/concrt/reference/reader-writer-lock-class.md), ve [eşzamanlılık :: olay](../../parallel/concrt/reference/event-class.md) sınıfları. Bu tür işbirliği içerisinde devamlılığı davranır; Bu nedenle, veriler için ilk görev bekler gibi Görev Zamanlayıcısı'nı işlem kaynakları için başka bir bağlamı yeniden tahsis edebilirsiniz. Mümkün olduğunda, bu eşitleme türleri, işbirliği içerisinde devamlılığı davranmayabilir diğer eşitleme mekanizmaları yerine, Windows API tarafından sağlanan gibi kullanın. Bu eşitleme türleri ve bir kod örneği hakkında daha fazla bilgi için bkz. [eşitleme veri yapıları](../../parallel/concrt/synchronization-data-structures.md) ve [eşitleme veri yapılarını Windows API ile karşılaştırma](../../parallel/concrt/comparing-synchronization-data-structures-to-the-windows-api.md).

[[Üst](#top)]

##  <a name="yield"></a> Yield değil verimsiz uzun görevlerden kaçınma

Görev Zamanlayıcısı'nı işbirliği içerisinde devamlılığı olarak davranır çünkü görevler eşitliği sağlamaz. Bu nedenle, bir görev, diğer görevler başlamasını engelleyebilir. Bazı durumlarda kabul edilebilir olsa da diğer durumlarda bu kilitlenme veya yetersizliğine neden olabilir.

Aşağıdaki örnek, ayrılmış işleme kaynakları sayısından daha fazla görevleri gerçekleştirir. İlk görev için Görev Zamanlayıcısı'nı vermez ve ilk görev bitene kadar ikinci görev bu nedenle başlamaz.

[!code-cpp[concrt-cooperative-tasks#1](../../parallel/concrt/codesnippet/cpp/general-best-practices-in-the-concurrency-runtime_1.cpp)]

Bu örnek aşağıdaki çıktıyı üretir:

1: 250000000 1: 500000000 1: 750000000 1: 1000000000 2: 250000000 2: 500000000 2: 750000000 2: 1000000000

İki görevler arasında işbirliği sağlamanın birkaç yolu vardır. Görev Zamanlayıcı'da uzun süre çalışan bir görev için bazen yield bir yoludur. Aşağıdaki örnek `task` işlevi çağırmak için [concurrency::Context::Yield](reference/context-class.md#yield) başka bir görev çalıştırabilmeniz için yürütme için Görev Zamanlayıcısı'nı elde etmek üzere yöntemi.

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

`Context::Yield` Yöntemi yalnızca başka bir etkin iş parçacığı üzerinde geçerli iş parçacığı ait olduğu, basit bir görev veya başka bir işletim sistemi iş parçacığı Zamanlayıcısı verir. Bu yöntem çalışmaya çalıştırmak için zamanlanan vermez bir [concurrency::task_group](reference/task-group-class.md) veya [concurrency::structured_task_group](../../parallel/concrt/reference/structured-task-group-class.md) nesnesi ancak henüz başlatılmadı.

Uzun süre çalışan görevler arasında işbirliği etkinleştirmek için farklı yöntemleri vardır. Büyük bir görevi daha küçük alt görevlere bölünebilir. Aşırı abonelik uzun bir görev sırasında da etkinleştirebilirsiniz. Aşırı abonelik, kullanılabilir donanım iş parçacığı sayısından daha fazla iş parçacığı oluşturmanızı sağlar. Verileri diskten veya bir ağ bağlantısı okuma gecikme süresi, örneğin, yüksek miktarda uzun bir görev içerdiğinde, gecikmeyi özellikle yararlıdır. Basit görevler ve gecikmeyi hakkında daha fazla bilgi için bkz. [Görev Zamanlayıcı](../../parallel/concrt/task-scheduler-concurrency-runtime.md).

[[Üst](#top)]

##  <a name="oversubscription"></a> Gecikmeyi engelleyen veya gecikmesi fazla olan işlemleri için aşırı aboneliği kullanma

Eşzamanlılık Çalışma Zamanı Eşitleme temellerine gibi sağlar [concurrency::critical_section](../../parallel/concrt/reference/critical-section-class.md), işbirliği içerisinde devamlılığı engelleyin ve birbirlerine yield görevleri etkinleştirin. Bir görev işbirliği içerisinde devamlılığı engeller veya verir, veriler için ilk görev bekleyeceği gibi Görev Zamanlayıcısı'nı işlem kaynakları için başka bir bağlamı yeniden tahsis edebilirsiniz.

Eşzamanlılık Çalışma zamanı tarafından sağlanan birlikte engelleme mekanizmasını kullanamazsınız durumlar vardır. Örneğin, kullandığınız dış kitaplık farklı eşitleme mekanizması kullanabilirsiniz. Windows API kullandığınızda, örneğin, gecikme süresi, yüksek miktarda sahip bir işlem gerçekleştirdiğinizde başka bir örnektir `ReadFile` işlevini bir ağ bağlantısından veriler okunamıyor. Bu gibi durumlarda, başka bir görev boşta olduğunda çalıştırılacak diğer görevler gecikmeyi etkinleştirebilirsiniz. Aşırı abonelik, kullanılabilir donanım iş parçacığı sayısından daha fazla iş parçacığı oluşturmanızı sağlar.

Aşağıdaki işlev göz önünde bulundurun `download`, verilen URL'den dosyasını indirir. Bu örnekte [concurrency::Context::Oversubscribe](reference/context-class.md#oversubscribe) geçici olarak etkin iş parçacığı sayısını artırmak için yöntemi.

[!code-cpp[concrt-download-oversubscription#4](../../parallel/concrt/codesnippet/cpp/general-best-practices-in-the-concurrency-runtime_3.cpp)]

Çünkü `GetHttpFile` işlevi potansiyel olarak görünmeyen bir işlemi gerçekleştirir, gecikmeyi geçerli görev için veri bekler çalışması diğer görevleri etkinleştirebilirsiniz. Bu örneğin tam sürümü için bkz: [nasıl yapılır: Gecikmeyi dengelemek için aşırı aboneliği kullanma](../../parallel/concrt/how-to-use-oversubscription-to-offset-latency.md).

[[Üst](#top)]

##  <a name="memory"></a> Mümkün olduğunda eşzamanlı bellek yönetimi işlevlerini kullanma

Bellek Yönetimi işlevleri kullanmak [concurrency::Alloc](reference/concurrency-namespace-functions.md#alloc) ve [concurrency::Free](reference/concurrency-namespace-functions.md#free), sık görece kısa ömürlü küçük nesneleri ayırmak hassas görevler vardır. Eşzamanlılık Çalışma zamanı, her bir çalışan iş parçacığı için ayrı bir önbellek tutar. `Alloc` Ve `Free` işlevleri bellek ayırıp bu önbellekler kilitler veya belleği engelleri kullanmadan öğesinden.

Bu bellek yönetimi işlevleri hakkında daha fazla bilgi için bkz: [Görev Zamanlayıcı](../../parallel/concrt/task-scheduler-concurrency-runtime.md). Bu işlevler kullanan bir örnek için bkz: [nasıl yapılır: Ayırma kullanın ve bellek performansını artırmak ücretsiz](../../parallel/concrt/how-to-use-alloc-and-free-to-improve-memory-performance.md).

[[Üst](#top)]

##  <a name="raii"></a> Eşzamanlılık nesnelerinin kullanım süresini yönetmek için RAII kullanma

Eşzamanlılık Çalışma zamanı özel durum işleme iptal gibi özellikleri uygulamak için kullanır. Çağırdığınızda, çalışma zamanına veya çalışma zamanına çağıran başka bir kitaplık çağırmak bu nedenle, özel durum-güvenli kod yazın.

*Olduğu kaynak alımı başlatma* (RAII) deseni, güvenli bir şekilde belirtilen kapsam altında bir eşzamanlılık nesnenin ömrünü yönetmek için bir yoludur. RAII deseni altında bir veri yapısı yığında ayrılır. Bu veri yapısını başlatır veya bir kaynak oluşturulur ve yok eder veya veri yapısı kaldırıldığında bu kaynağı yayınlar zaman alır. RAII deseni kapsayan kapsam çıkar önce yok Edicisi çağrılır garanti eder. Bir işlev birden çok içerdiğinde bu desen yararlıdır `return` deyimleri. Bu düzen ayrıca özel durum-güvenli kod yazmanıza yardımcı olur. Olduğunda bir `throw` deyimi için yığın geriye doğru izleme, yok edici RAII nesne çağrılır neden olur; bu nedenle, kaynağın her zaman doğru bir şekilde serbest veya silinmiş.

Çalışma zamanı gibi RAII deseni kullanan birden çok sınıf tanımlar [concurrency::critical_section::scoped_lock](../../parallel/concrt/reference/critical-section-class.md#critical_section__scoped_lock_class) ve [concurrency::reader_writer_lock::scoped_lock](reference/reader-writer-lock-class.md#scoped_lock_class). Bu yardımcı sınıfları olarak bilinen *kilit kapsamı*. İle çalışırken, bu sınıflar çeşitli avantajlar sunar [concurrency::critical_section](../../parallel/concrt/reference/critical-section-class.md) veya [concurrency::reader_writer_lock](../../parallel/concrt/reference/reader-writer-lock-class.md) nesneleri. Bu sınıfların Oluşturucusu erişim sağlanan edinme `critical_section` veya `reader_writer_lock` nesne; o nesnenin yok Edicisi yayınlar erişim. Bunu kaldırıldığında kapsamlı bir kilit, karşılıklı dışlama nesnesine erişim otomatik olarak yayımlar için el ile temel alınan nesnede kilidini değil.

Aşağıdaki sınıf göz önünde bulundurun `account`, harici bir kitaplığı tarafından tanımlanan ve bu nedenle değiştirilemez.

[!code-cpp[concrt-account-transactions#1](../../parallel/concrt/codesnippet/cpp/general-best-practices-in-the-concurrency-runtime_4.h)]

Aşağıdaki örnek birden çok işlem gerçekleştiren bir `account` paralel nesne. Örnekte bir `critical_section` nesnesi erişimi eşitlemek için `account` çünkü nesne `account` sınıf eşzamanlı güvenli değil. Her paralel işlemi kullanan bir `critical_section::scoped_lock` bunu garanti etmenin nesne `critical_section` işlemi başarılı veya başarısız olduğunda nesne kilidi. Hesap bakiyeniz negatif olduğunda `withdraw` işlemi, bir özel durum ile başarısız olur.

[!code-cpp[concrt-account-transactions#2](../../parallel/concrt/codesnippet/cpp/general-best-practices-in-the-concurrency-runtime_5.cpp)]

Bu örnek, örnek aşağıdaki çıktıyı üretir:

```Output
Balance before deposit: 1924
Balance after deposit: 2924
Balance before withdrawal: 2924
Balance after withdrawal: -76
Balance before withdrawal: -76
Error details:
    negative balance: -76
```

Eşzamanlılık nesnelerinin kullanım süresini yönetmek için RAII deseni kullanan diğer örnekler için [izlenecek yol: Bir kullanıcı arabirimi iş parçacığından işi kaldırma](../../parallel/concrt/walkthrough-removing-work-from-a-user-interface-thread.md), [nasıl yapılır: Bağlam sınıfını işbirlikçi semafor uygulamak için kullanma](../../parallel/concrt/how-to-use-the-context-class-to-implement-a-cooperative-semaphore.md), ve [nasıl yapılır: Gecikmeyi dengelemek için aşırı aboneliği kullanma](../../parallel/concrt/how-to-use-oversubscription-to-offset-latency.md).

[[Üst](#top)]

##  <a name="global-scope"></a> Genel kapsamda eşzamanlılık nesneleri oluşturma

Genel kapsamda eşzamanlılık nesne oluşturduğunuzda, uygulamanızda gerçekleşecek şekilde, erişim ihlallerine kilitlenme veya bellek gibi sorunlara neden olabilir.

Örneğin, bir eşzamanlılık çalışma zamanı nesnesi oluşturduğunuzda, bir henüz oluşturulmadı, çalışma zamanı bir varsayılan Zamanlayıcı sizin için oluşturur. Genel nesne oluşturma sırasında oluşturulan bir çalışma zamanı nesnesi buna uygun olarak bu varsayılan Zamanlayıcı oluşturmak çalışma zamanı neden olur. Ancak, bu işlem eşzamanlılık çalışma zamanı altyapısını destekleyen diğer nesnelerin ile başlatmayı engelleyebilir bir iç kilidi alır. Bu iç kilit henüz başlatılmadı ve bu nedenle, gerçekleşmesi kilitlenme uygulamanızda neden olabilir, başka bir altyapı nesnesi tarafından gerekli olabilir.

Aşağıdaki örnek, genel bir oluşturulmasını gösterir. [concurrency::Scheduler](../../parallel/concrt/reference/scheduler-class.md) nesne. Bu düzen için değil yalnızca geçerli `Scheduler` sınıf ancak eşzamanlılık çalışma zamanı tarafından sağlanan diğer tüm türleri. Uygulamada beklenmeyen davranışlara neden çünkü bu düzen izlemeyin öneririz.

[!code-cpp[concrt-global-scheduler#1](../../parallel/concrt/codesnippet/cpp/general-best-practices-in-the-concurrency-runtime_6.cpp)]

Doğru bir şekilde oluşturmak için örnekleri için `Scheduler` nesneleri görmek [Görev Zamanlayıcı](../../parallel/concrt/task-scheduler-concurrency-runtime.md).

[[Üst](#top)]

##  <a name="shared-data"></a> Paylaşılan veri kesimlerinde eşzamanlılık nesneleri kullanma

Eşzamanlılık Çalışma zamanı tarafından oluşturulan veri bölümü gibi bir paylaşılan veri bölümünde eşzamanlılık nesnelerinin kullanımını desteklemiyor [data_seg](../../preprocessor/data-seg.md) `#pragma` yönergesi. İşlem sınırları arasında paylaşılan bir eşzamanlılık nesnesi tutarsız ya da geçersiz bir durumda çalışma zamanının yerleştirebilirsiniz.

[[Üst](#top)]

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Çalışma Zamanı En İyi Yöntemleri](../../parallel/concrt/concurrency-runtime-best-practices.md)<br/>
[Paralel Desen Kitaplığı (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md)<br/>
[Zaman Uyumsuz Aracılar Kitaplığı](../../parallel/concrt/asynchronous-agents-library.md)<br/>
[Görev Zamanlayıcısı](../../parallel/concrt/task-scheduler-concurrency-runtime.md)<br/>
[Eşitleme Veri Yapıları](../../parallel/concrt/synchronization-data-structures.md)<br/>
[Eşitleme Veri Yapılarını Windows API ile Karşılaştırma](../../parallel/concrt/comparing-synchronization-data-structures-to-the-windows-api.md)<br/>
[Nasıl yapılır: Bellek Performansını Artırmak için Alloc ve Free Kullanma](../../parallel/concrt/how-to-use-alloc-and-free-to-improve-memory-performance.md)<br/>
[Nasıl yapılır: Gecikmeyi Dengelemek için Aşırı Aboneliği Kullanma](../../parallel/concrt/how-to-use-oversubscription-to-offset-latency.md)<br/>
[Nasıl yapılır: Bağlam Sınıfını İşbirliğine Dayalı Semafor Uygulamak için Kullanma](../../parallel/concrt/how-to-use-the-context-class-to-implement-a-cooperative-semaphore.md)<br/>
[İzlenecek yol: Kullanıcı Arabirimi İş Parçacığından İşi Kaldırma](../../parallel/concrt/walkthrough-removing-work-from-a-user-interface-thread.md)<br/>
[Paralel Desen Kitaplığı'ndaki En İyi Yöntemler](../../parallel/concrt/best-practices-in-the-parallel-patterns-library.md)<br/>
[Zaman Uyumsuz Aracılar Kitaplığı'ndaki En İyi Yöntemler](../../parallel/concrt/best-practices-in-the-asynchronous-agents-library.md)
