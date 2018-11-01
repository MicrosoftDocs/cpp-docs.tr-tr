---
title: Eşzamanlılık Çalışma Zamanı
ms.date: 07/20/2018
helpviewer_keywords:
- Concurrency Runtime, getting started
- ConcRT (see Concurrency Runtime)
- Concurrency Runtime
ms.assetid: 874bc58f-8dce-483e-a3a1-4dcc9e52ed2c
ms.openlocfilehash: bed1d7680d9bc6615476c7d5d4b700d729026c66
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50495959"
---
# <a name="concurrency-runtime"></a>Eşzamanlılık Çalışma Zamanı

Eşzamanlılık Çalışma zamanı C++ için yazma sağlam, ölçeklenebilir ve hızlı yanıt veren paralel uygulamalar yardımcı olur. Böylece altyapı ayrıntılarını için eşzamanlılık ilgili yönetmek zorunda değilsiniz özet düzeyi başlatır. Servis taleplerini uygulamalarınızın kalitesini karşılayan zamanlama ilkeleri belirtmek için de kullanabilirsiniz. Eşzamanlılık Çalışma zamanı ile çalışmaya başlamanıza yardımcı olması için bu kaynakları kullanın.

Referans belgeleri için bkz. [başvuru](../../parallel/concrt/reference/reference-concurrency-runtime.md).

> [!TIP]
>  Eşzamanlılık Çalışma zamanı, yoğun C ++ 11 özelliklerini kullanır ve daha modern C++ stilinin devralır. Daha fazla bilgi edinmek için [Hoş Geldiniz geri c++](../../cpp/welcome-back-to-cpp-modern-cpp.md).

## <a name="choosing-concurrency-runtime-features"></a>Eşzamanlılık Çalışma Zamanı Özellikleri Seçme

|||
|-|-|
|[Genel bakış](../../parallel/concrt/overview-of-the-concurrency-runtime.md)|Eşzamanlılık Çalışma zamanı neden önemlidir ve anahtar özelliklerini açıklar öğretir.|
|[Diğer eşzamanlılık modelleriyle karşılaştırma](../../parallel/concrt/comparing-the-concurrency-runtime-to-other-concurrency-models.md)|Eşzamanlılık çalışma zamanını diğer eşzamanlılık modelleriyle nasıl karşılaştırır ve böylece uygulama gereksinimlerinize en uygun eşzamanlılık modeli kullandığınız Windows havuzu ve OpenMP, iş parçacığı gibi gösterir.|
|[OpenMP döngüsünden Eşzamanlılık Çalışma Zamanına geçiş](../../parallel/concrt/migrating-from-openmp-to-the-concurrency-runtime.md)|Eşzamanlılık Çalışma zamanı OpenMP karşılaştırır ve Eşzamanlılık Çalışma zamanı kullanmak için mevcut OpenMP kod geçirme hakkında örnekler sağlar.|
|[Paralel Desen Kitaplığı (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md)|Size, paralel döngüler, görevler ve paralel kapsayıcılar sağlar PPL tanıtır.|
|[Zaman Uyumsuz Aracılar Kitaplığı](../../parallel/concrt/asynchronous-agents-library.md)|Zaman uyumsuz aracılar ve ileti veri akışı ve ardışık düzen oluşturma görevleri uygulamalarınıza kolayca eklemesine geçirme nasıl kullanılacağını size tanıtır.|
|[Görev Zamanlayıcısı](../../parallel/concrt/task-scheduler-concurrency-runtime.md)|Size eşzamanlılık çalışma zamanı kullanan masaüstü uygulamalarınızın performansını ince ayar sayesinde Görev Zamanlayıcı'tanıtır.|

## <a name="task-parallelism-in-the-ppl"></a>PPL'de Görev Paralelliği

|||
|-|-|
|[Görev Paralelliği](../../parallel/concrt/task-parallelism-concurrency-runtime.md)<br /><br /> [Nasıl yapılır: Paralel Sıralama Rutini Yazmak için parallel_invoke Kullanma](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md)<br /><br /> [Nasıl yapılır: Paralel İşlemleri Yürütmek için parallel_invoke Kullanma](../../parallel/concrt/how-to-use-parallel-invoke-to-execute-parallel-operations.md)<br /><br /> [Nasıl yapılır: Bir Gecikmeden Sonra Tamamlanan bir Görev Oluşturma](../../parallel/concrt/how-to-create-a-task-that-completes-after-a-delay.md)|Görevler ve görev grupları, zaman uyumsuz kod yazmanıza ve paralel işleri küçük parçalara ayırmak yardımcı olabilecek açıklar.|
|[İzlenecek Yol: Vadeli İşlemleri Uygulama](../../parallel/concrt/walkthrough-implementing-futures.md)|Daha fazla şey için eşzamanlılık çalışma zamanı Özellikleri birleştirmek nasıl gösterir.|
|[İzlenecek Yol: Kullanıcı Arabirimi İş Parçacığından İşi Kaldırma](../../parallel/concrt/walkthrough-removing-work-from-a-user-interface-thread.md)|Bir MFC uygulaması için bir iş parçacığı UI iş parçacığı tarafından gerçekleştirilen iş taşıma işlemi gösterilmektedir.|
|[Paralel Desen Kitaplığı'ndaki En İyi Yöntemler](../../parallel/concrt/best-practices-in-the-parallel-patterns-library.md)<br /><br /> [Eşzamanlılık Çalışma Zamanındaki Genel En İyi Yöntemler](../../parallel/concrt/general-best-practices-in-the-concurrency-runtime.md)|PPL ile çalışmak için ipuçları ve en iyi yöntemler sağlar.|

## <a name="data-parallelism-in-the-ppl"></a>PPL'de Veri Paralelliği

|||
|-|-|
|[Paralel Algoritmalar](../../parallel/concrt/parallel-algorithms.md)<br /><br /> [Nasıl yapılır: parallel_for Döngüsü Yazma](../../parallel/concrt/how-to-write-a-parallel-for-loop.md)<br /><br /> [Nasıl yapılır: parallel_for_each Döngüsü Yazma](../../parallel/concrt/how-to-write-a-parallel-for-each-loop.md)<br /><br /> [Nasıl yapılır: Eşleme Gerçekleştirme ve İşlemleri Paralel Olarak Azaltma](../../parallel/concrt/how-to-perform-map-and-reduce-operations-in-parallel.md)|Açıklar `parallel_for`, `parallel_for_each`, `parallel_invoke`ve diğer paralel algoritmalar. Çözmek için paralel algoritmalar kullanın *paralel veri* veri içeren sorunlar.|
|[Paralel Kapsayıcılar ve Nesneler](../../parallel/concrt/parallel-containers-and-objects.md)<br /><br /> [Nasıl yapılır: Etkinliği Arttırmak için Paralel Kapsayıcılar Kullanma](../../parallel/concrt/how-to-use-parallel-containers-to-increase-efficiency.md)<br /><br /> [Nasıl yapılır: Performansı arttırmak için combinable Kullanma](../../parallel/concrt/how-to-use-combinable-to-improve-performance.md)<br /><br /> [Nasıl yapılır: Kümeleri Birleştirmek için combinable Kullanma](../../parallel/concrt/how-to-use-combinable-to-combine-sets.md)|Açıklar `combinable` sınıfı olarak `concurrent_vector`, `concurrent_queue`, `concurrent_unordered_map`ve diğer paralel kapsayıcılar. Paralel kapsayıcılar ve nesneler, öğeleri iş parçacığı açısından güvenli erişim sağlayan kapsayıcılar gerektiğinde kullanın.|
|[Paralel Desen Kitaplığı'ndaki En İyi Yöntemler](../../parallel/concrt/best-practices-in-the-parallel-patterns-library.md)<br /><br /> [Eşzamanlılık Çalışma Zamanındaki Genel En İyi Yöntemler](../../parallel/concrt/general-best-practices-in-the-concurrency-runtime.md)|PPL ile çalışmak için ipuçları ve en iyi yöntemler sağlar.|

## <a name="canceling-tasks-and-parallel-algorithms"></a>Görevleri ve Paralel Algoritmaları İptal Etme

|||
|-|-|
|[PPL'de İptal](cancellation-in-the-ppl.md)|Başlatma ve iptal isteklerini yanıtlamasını dahil olmak üzere ppl'de iptal rolünü açıklar.|
|[Nasıl yapılır: Paralel Bir Döngüden Kurtulmak için İptal](../../parallel/concrt/how-to-use-cancellation-to-break-from-a-parallel-loop.md)<br /><br /> [Nasıl yapılır: Paralel Bir Döngüden Kurtulmak için Özel Durum İşlemeyi Kullanma](../../parallel/concrt/how-to-use-exception-handling-to-break-from-a-parallel-loop.md)|Veri-paralel işi iptal etmek için iki yolunu gösterir.|

## <a name="universal-windows-platform-apps"></a>Evrensel Windows platformu uygulamaları

|||
|-|-|
|[UWP Uygulamaları için C++ Uygulamasında Zaman Uyumsuz İşlemler Oluşturma](../../parallel/concrt/creating-asynchronous-operations-in-cpp-for-windows-store-apps.md)|Eşzamanlılık Çalışma zamanı bir UWP uygulamasında zaman uyumsuz işlemler oluşturmak için kullandığınız zaman akılda tutulması gereken önemli noktaları bazılarını açıklar.|
|[İzlenecek Yol: Görevleri ve XML HTTP İsteklerini Kullanarak Bağlanma](../../parallel/concrt/walkthrough-connecting-using-tasks-and-xml-http-requests.md)|PPL görevleri ile birleştirilecek gösterilmektedir `IXMLHTTPRequest2` ve `IXMLHTTPRequest2Callback` bir UWP uygulamasında bir web hizmetine HTTP GET ve POST istekleri göndermek için gereken arabirimler.|
|[Windows çalışma zamanı uygulama örnekleri](http://code.msdn.microsoft.com/windowsapps)|İndirilebilir kod örneklerini ve demo içeren uygulamalar için Windows 8.x. C++ örnekleri UX duyarlı korumak için arka planda gibi verileri işlemek için PPL görevlerinin eşzamanlılık çalışma zamanı özellikleri kullanın.|

## <a name="dataflow-programming-in-the-asynchronous-agents-library"></a>Zaman Uyumsuz Aracılar Kitaplığı'nda Veri Akışı Programlama

|||
|-|-|
|[Zaman Uyumsuz Aracılar](../../parallel/concrt/asynchronous-agents.md)<br /><br /> [Zaman Uyumsuz İleti Blokları](../../parallel/concrt/asynchronous-message-blocks.md)<br /><br /> [İleti Geçirme İşlevleri](../../parallel/concrt/message-passing-functions.md)<br /><br /> [Nasıl yapılır: Çeşitli Üretici-Tüketici Desenlerini Uygulama](../../parallel/concrt/how-to-implement-various-producer-consumer-patterns.md)<br /><br /> [Nasıl yapılır: call ve transformer Sınıflarına İş İşlevleri Sağlama](../../parallel/concrt/how-to-provide-work-functions-to-the-call-and-transformer-classes.md)<br /><br /> [Nasıl yapılır: Veri İşlem Hattında transformer Kullanma](../../parallel/concrt/how-to-use-transformer-in-a-data-pipeline.md)<br /><br /> [Nasıl yapılır: Tamamlanan Görevler Arasında Seçim Yapma](../../parallel/concrt/how-to-select-among-completed-tasks.md)<br /><br /> [Nasıl yapılır: Düzenli Aralıkla İleti Gönderme](../../parallel/concrt/how-to-send-a-message-at-a-regular-interval.md)<br /><br /> [Nasıl yapılır: İleti Bloğu Filtresini Kullanma](../../parallel/concrt/how-to-use-a-message-block-filter.md)|Zaman uyumsuz aracılar, ileti blokları ve Eşzamanlılık Çalışma Zamanı'nda veri akışı işlemleri gerçekleştirmek için yapı taşları olan ileti geçirme işlevleri açıklanmaktadır.|
|[İzlenecek Yol: Aracı Temelli Uygulama Oluşturma](../../parallel/concrt/walkthrough-creating-an-agent-based-application.md)<br /><br /> [İzlenecek Yol: Veri Akışı Aracısı Oluşturma](../../parallel/concrt/walkthrough-creating-a-dataflow-agent.md)|Temel aracı tabanlı uygulamalar oluşturma işlemi gösterilmektedir.|
|[İzlenecek yol: Görüntü İşleme Ağı Oluşturma](../../parallel/concrt/walkthrough-creating-an-image-processing-network.md)|Görüntü işleme gerçekleştiren zaman uyumsuz ileti blokları, ağ oluşturma işlemi gösterilmektedir.|
|[İzlenecek Yol: Kilitlenmeyi Önlemek için birleştirme kullanma](../../parallel/concrt/walkthrough-using-join-to-prevent-deadlock.md)|Yemek Yiyen Filozoflar sorunu eşzamanlılık çalışma zamanı, uygulamanızda kilitlenmeyi önlemek için nasıl kullanılacağını göstermek için kullanır.|
|[İzlenecek Yol: Özel bir İleti Bloğu Oluşturma](../../parallel/concrt/walkthrough-creating-a-custom-message-block.md)|Gelen iletileri öncelik sırasına göre sıralayan bir özel ileti bloğu türünün nasıl oluşturulacağını gösterir.|
|[Zaman Uyumsuz Aracılar Kitaplığı'ndaki En İyi Yöntemler](../../parallel/concrt/best-practices-in-the-asynchronous-agents-library.md)<br /><br /> [Eşzamanlılık Çalışma Zamanındaki Genel En İyi Yöntemler](../../parallel/concrt/general-best-practices-in-the-concurrency-runtime.md)|Aracıları ile çalışmak için ipuçları ve en iyi yöntemler sağlar.|

## <a name="exception-handling-and-debugging"></a>Özel Durum İşleme ve Hata Ayıklama

|||
|-|-|
|[Özel Durum İşleme](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)|Eşzamanlılık Çalışma zamanı özel durumları ile nasıl çalışılacağını açıklar.|
|[Paralel Tanılama Araçları](../../parallel/concrt/parallel-diagnostic-tools-concurrency-runtime.md)|Uygulamalarınızı ince ayar yapma ve Eşzamanlılık Çalışma zamanı en etkili kullanımını sağlamak öğretir.|

## <a name="tuning-performance"></a>Performans Ayarlama

|||
|-|-|
|[Paralel Tanılama Araçları](../../parallel/concrt/parallel-diagnostic-tools-concurrency-runtime.md)|Uygulamalarınızı ince ayar yapma ve Eşzamanlılık Çalışma zamanı en etkili kullanımını sağlamak öğretir.|
|[Zamanlayıcı Örnekleri](../../parallel/concrt/scheduler-instances.md)<br /><br /> [Nasıl yapılır: Zamanlayıcı Örneğini Yönetme](../../parallel/concrt/how-to-manage-a-scheduler-instance.md)<br /><br /> [Scheduler İlkeleri](../../parallel/concrt/scheduler-policies.md)<br /><br /> [Nasıl yapılır: Belirli Zamanlayıcı İlkeleri Belirtme](../../parallel/concrt/how-to-specify-specific-scheduler-policies.md)<br /><br /> [Nasıl yapılır: Belirli Zamanlayıcı İlkelerini Kullanan Aracılar Oluşturma](../../parallel/concrt/how-to-create-agents-that-use-specific-scheduler-policies.md)|Nasıl çalışacağınızı göstermektedir Zamanlayıcı örnekleri ve Zamanlayıcı ilkeleri yönetin. Masaüstü uygulamaları için Zamanlayıcı ilkeleri belirli kuralları belirli türlerdeki iş yükleri ile ilişkilendirmek etkinleştirin. Örneğin, bir yükseltilmiş iş parçacığı önceliği bazı görevleri çalıştırmak ve diğer görevleri sırasında normal iş parçacığı önceliği çalıştırmak için varsayılan Zamanlayıcı kullanmak için bir zamanlayıcı örneğini oluşturabilirsiniz.|
|[Zamanlama Grupları](../../parallel/concrt/schedule-groups.md)<br /><br /> [Nasıl yapılır: Yürütme Sırasını Etkilemek için Zamanlama Grupları Kullanma](../../parallel/concrt/how-to-use-schedule-groups-to-influence-order-of-execution.md)|Affinitize veya grup, ilgili görevleri birlikte için zamanlama grupları kullanma işlemi gösterilmektedir. Örneğin, bu görevleri aynı işlemci düğümde yürütülmesini avantajı, Yerleşim Yeri İlgili Görevler arasında yüksek derecede gerektirebilir.|
|[Basit Görevler](../../parallel/concrt/lightweight-tasks.md)|Nasıl basit görevleri açıklanır Yük Dengeleme veya iptal, ve bunlar da eşzamanlılık çalışma zamanı ile kullanmak için mevcut kodu uyarlama için yarar gerektirmeyen iş oluşturmak için kullanışlıdır.|
|[Bağlamlar](../../parallel/concrt/contexts.md)<br /><br /> [Nasıl yapılır: Bağlam Sınıfını İşbirlikçi Semafor Uygulamak için Kullanma](../../parallel/concrt/how-to-use-the-context-class-to-implement-a-cooperative-semaphore.md)<br /><br /> [Nasıl yapılır: Gecikmeyi Dengelemek için Aşırı Aboneliği Kullanma](../../parallel/concrt/how-to-use-oversubscription-to-offset-latency.md)|Eşzamanlılık Çalışma zamanı tarafından yönetilen iş parçacıkları davranışını denetlemek nasıl açıklar.|
|[Bellek Yönetimi İşlevleri](../../parallel/concrt/memory-management-functions.md)<br /><br /> [Nasıl yapılır: Bellek Performansını Artırmak için Alloc ve Free Kullanma](../../parallel/concrt/how-to-use-alloc-and-free-to-improve-memory-performance.md)|Eşzamanlılık Çalışma zamanı ayırın ve eş zamanlı bir şekilde belleği boşaltmak yardımcı sağlayan bellek yönetimi işlevleri açıklanmaktadır.|

## <a name="additional-resources"></a>Ek Kaynaklar

|||
|-|-|
|[Zaman uyumsuz programlama desenleri ve Hilo (C++ ve XAML kullanan Windows Store apps) içinde ipuçları](https://msdn.microsoft.com/library/windows/apps/jj160321.aspx)|Nasıl eşzamanlılık çalışma zamanı zaman uyumsuz işlemler Hilo, C++ ve XAML kullanarak bir Windows çalışma zamanı uygulaması uygulamak için kullandığımız öğrenin.|
|[Eşzamanlılık Çalışma zamanı ve paralel desen Kitaplığı'nda Visual Studio 2010 için kod örnekleri](http://go.microsoft.com/fwlink/p/?linkid=183875)|Örnek uygulamalar ve Eşzamanlılık Çalışma zamanı gösteren yardımcı programları sağlar.|
|[Yerel kod blog içinde paralel programlama](http://go.microsoft.com/fwlink/p/?linkid=183873)|Eşzamanlılık Çalışma zamanı içinde paralel programlama hakkında ek ayrıntılı blog makaleler sağlar.|
|[C++ ve yerel kod forumdaki paralel bilgi işlem](http://go.microsoft.com/fwlink/p/?linkid=183874)|Eşzamanlılık Çalışma zamanı hakkında topluluk tartışmaları katılmasını sağlar.|
|[Paralel Programlama](/dotnet/standard/parallel-programming/index)|.NET Framework'teki kullanılabilir paralel programlama modeli hakkında size öğretir.|

## <a name="see-also"></a>Ayrıca Bkz.

[Başvuru](../../parallel/concrt/reference/reference-concurrency-runtime.md)

