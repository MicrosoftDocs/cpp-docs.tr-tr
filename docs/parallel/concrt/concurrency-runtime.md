---
title: Eşzamanlılık Çalışma Zamanı
ms.date: 07/20/2018
helpviewer_keywords:
- Concurrency Runtime, getting started
- ConcRT (see Concurrency Runtime)
- Concurrency Runtime
ms.assetid: 874bc58f-8dce-483e-a3a1-4dcc9e52ed2c
ms.openlocfilehash: ce75d7a78fec69922c08479f6c130c6b6ccec566
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88845516"
---
# <a name="concurrency-runtime"></a>Eşzamanlılık Çalışma Zamanı

C++ için Eşzamanlılık Çalışma Zamanı sağlam, ölçeklenebilir ve hızlı yanıt veren paralel uygulamalar yazmanıza yardımcı olur. Eşzamanlılık düzeyini yükseltir, böylece eşzamanlılık ile ilgili altyapı ayrıntılarını yönetmek zorunda değilsiniz. Ayrıca, uygulamalarınızın hizmet taleplerinin kalitesini karşılayan zamanlama ilkelerini belirtmek için de kullanabilirsiniz. Eşzamanlılık Çalışma Zamanı ile çalışmaya başlamanıza yardımcı olması için bu kaynakları kullanın.

Başvuru belgeleri için bkz. [başvuru](../../parallel/concrt/reference/reference-concurrency-runtime.md).

> [!TIP]
> Eşzamanlılık Çalışma Zamanı, C++ 11 özelliklerine büyük ölçüde yararlanır ve daha modern C++ stilini benimsemektedir. Daha fazla bilgi edinmek için bkz. C++ ' a  [geri hoş geldiniz](../../cpp/welcome-back-to-cpp-modern-cpp.md).

## <a name="choosing-concurrency-runtime-features"></a>Eşzamanlılık Çalışma Zamanı Özellikleri Seçme

|Makale|Açıklama|
|-|-|
|[Genel Bakış](../../parallel/concrt/overview-of-the-concurrency-runtime.md)|Eşzamanlılık Çalışma Zamanı neden önemli olduğunu öğretir ve temel özelliklerini açıklar.|
|[Diğer eşzamanlılık modelleriyle karşılaştırma](../../parallel/concrt/comparing-the-concurrency-runtime-to-other-concurrency-models.md)|Uygulama gereksinimlerinize en uygun eşzamanlılık modelini kullanabilmeniz için, Eşzamanlılık Çalışma Zamanı Windows iş parçacığı havuzu ve OpenMP gibi diğer eşzamanlılık modelleriyle nasıl Karşılaştırıldığı gösterilmektedir.|
|[OpenMP döngüsünden Eşzamanlılık Çalışma Zamanına geçiş](../../parallel/concrt/migrating-from-openmp-to-the-concurrency-runtime.md)|OpenMP 'ı Eşzamanlılık Çalışma Zamanı karşılaştırır ve mevcut OpenMP kodunun Eşzamanlılık Çalışma Zamanı kullanmak için nasıl geçirileceğiyle ilgili örnekler sağlar.|
|[Paralel Desen Kitaplığı (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md)|, Paralel döngüler, görevler ve paralel kapsayıcılar sağlayan PPL 'yi tanıtır.|
|[Zaman Uyumsuz Aracılar Kitaplığı](../../parallel/concrt/asynchronous-agents-library.md)|, Uygulamalarınızda veri akışını ve ardışık düzen görevlerini kolayca birleştirmek için zaman uyumsuz aracıların ve ileti geçirmenin nasıl kullanılacağını tanıtır.|
|[Görev Zamanlayıcı](../../parallel/concrt/task-scheduler-concurrency-runtime.md)|Sizi, Eşzamanlılık Çalışma Zamanı kullanan masaüstü uygulamalarınızın performansını ince ayarlamanıza olanak tanıyan Görev Zamanlayıcı tanıtır.|

## <a name="task-parallelism-in-the-ppl"></a>PPL'de Görev Paralelliği

|Makale|Açıklama|
|-|-|
|[Görev Paralelliği](../../parallel/concrt/task-parallelism-concurrency-runtime.md)<br /><br /> [Nasıl yapılır: paralel sıralama yordamı yazmak için parallel_invoke kullanma](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md)<br /><br /> [Nasıl yapılır: paralel Işlemleri yürütmek için parallel_invoke kullanma](../../parallel/concrt/how-to-use-parallel-invoke-to-execute-parallel-operations.md)<br /><br /> [Nasıl yapılır: bir gecikmeden sonra tamamlanan bir görev oluşturma](../../parallel/concrt/how-to-create-a-task-that-completes-after-a-delay.md)|Zaman uyumsuz kod yazmanıza ve paralel çalışmayı daha küçük parçalara ayırmayı sağlamanıza yardımcı olan görevleri ve görev gruplarını açıklar.|
|[İzlenecek yol: Futures uygulama](../../parallel/concrt/walkthrough-implementing-futures.md)|Daha fazla şey yapmak için Eşzamanlılık Çalışma Zamanı özelliklerinin nasıl birleştirileceğini gösterir.|
|[İzlenecek yol: Kullanıcı arabirimi Iş parçacığından Iş kaldırma](../../parallel/concrt/walkthrough-removing-work-from-a-user-interface-thread.md)|Bir MFC uygulamasındaki UI iş parçacığı tarafından gerçekleştirilen çalışmanın bir çalışan iş parçacığına nasıl taşınacağını gösterir.|
|[Paralel Desenler kitaplığındaki en iyi uygulamalar](../../parallel/concrt/best-practices-in-the-parallel-patterns-library.md)<br /><br /> [Eşzamanlılık Çalışma Zamanı genel En Iyi Yöntemler](../../parallel/concrt/general-best-practices-in-the-concurrency-runtime.md)|PPL ile çalışmaya yönelik ipuçları ve en iyi uygulamalar sağlar.|

## <a name="data-parallelism-in-the-ppl"></a>PPL'de Veri Paralelliği

|Makale|Açıklama|
|-|-|
|[Paralel algoritmalar](../../parallel/concrt/parallel-algorithms.md)<br /><br /> [Nasıl yapılır: parallel_for döngüsü yazma](../../parallel/concrt/how-to-write-a-parallel-for-loop.md)<br /><br /> [Nasıl yapılır: parallel_for_each döngüsü yazma](../../parallel/concrt/how-to-write-a-parallel-for-each-loop.md)<br /><br /> [Nasıl yapılır: eşleme gerçekleştirme ve Işlemleri paralel olarak azaltma](../../parallel/concrt/how-to-perform-map-and-reduce-operations-in-parallel.md)|, `parallel_for` , `parallel_for_each` `parallel_invoke` Ve diğer paralel algoritmaları açıklar. Verilerin koleksiyonlarını içeren *paralel* sorunları çözümlemek için paralel algoritmaları kullanın.|
|[Paralel Kapsayıcılar ve nesneler](../../parallel/concrt/parallel-containers-and-objects.md)<br /><br /> [Nasıl yapılır: verimliliği artırmak için paralel kapsayıcılar kullanma](../../parallel/concrt/how-to-use-parallel-containers-to-increase-efficiency.md)<br /><br /> [Nasıl yapılır: performansı artırmak için combinable kullanma](../../parallel/concrt/how-to-use-combinable-to-improve-performance.md)<br /><br /> [Nasıl yapılır: kümeleri birleştirmek için combinable kullanma](../../parallel/concrt/how-to-use-combinable-to-combine-sets.md)|`combinable`Sınıfının yanı sıra,,, `concurrent_vector` `concurrent_queue` `concurrent_unordered_map` ve diğer paralel kapsayıcıları açıklar. Öğelerine iş parçacığı açısından güvenli erişim sağlayan kapsayıcılar gerektirdiğinde paralel kapsayıcıları ve nesneleri kullanın.|
|[Paralel Desenler kitaplığındaki en iyi uygulamalar](../../parallel/concrt/best-practices-in-the-parallel-patterns-library.md)<br /><br /> [Eşzamanlılık Çalışma Zamanı genel En Iyi Yöntemler](../../parallel/concrt/general-best-practices-in-the-concurrency-runtime.md)|PPL ile çalışmaya yönelik ipuçları ve en iyi uygulamalar sağlar.|

## <a name="canceling-tasks-and-parallel-algorithms"></a>Görevleri ve Paralel Algoritmaları İptal Etme

|Makale|Açıklama|
|-|-|
|[PPL'de İptal](cancellation-in-the-ppl.md)|İptal isteklerini başlatma ve yanıtlama dahil olmak üzere PPL 'de iptal etme rolünü açıklar.|
|[Nasıl yapılır: paralel bir döngüden ayırmak için Iptal kullanma](../../parallel/concrt/how-to-use-cancellation-to-break-from-a-parallel-loop.md)<br /><br /> [Nasıl yapılır: paralel bir döngüden ayırmak için özel durum Işlemeyi kullanma](../../parallel/concrt/how-to-use-exception-handling-to-break-from-a-parallel-loop.md)|Veri paralel çalışmayı iptal etmenin iki yolunu gösterir.|

## <a name="universal-windows-platform-apps"></a>Evrensel Windows Platformu uygulamalar

|Makale|Açıklama|
|-|-|
|[UWP uygulamaları için C++ ' da zaman uyumsuz Işlemler oluşturma](../../parallel/concrt/creating-asynchronous-operations-in-cpp-for-windows-store-apps.md)|UWP uygulamasında zaman uyumsuz işlemler üretmek için Eşzamanlılık Çalışma Zamanı kullandığınızda göz önünde bulundurmanız gereken bazı önemli noktaları açıklar.|
|[İzlenecek yol: görevleri ve XML HTTP Isteklerini kullanarak bağlanma](../../parallel/concrt/walkthrough-connecting-using-tasks-and-xml-http-requests.md)|`IXMLHTTPRequest2` `IXMLHTTPRequest2Callback` UWP uygulamasında bir Web HIZMETINE http get ve post istekleri göndermek için PPL görevlerinin ve arabirimleriyle nasıl birleştirileceğini gösterir.|
|[Windows Çalışma Zamanı uygulama örnekleri](/samples/browse/?languages=cpp&expanded=windows&products=windows-uwp)|Windows Çalışma Zamanı için indirilebilir kod örnekleri ve Tanıtım uygulamaları içerir.|

## <a name="dataflow-programming-in-the-asynchronous-agents-library"></a>Zaman Uyumsuz Aracılar Kitaplığı'nda Veri Akışı Programlama

|Makale|Açıklama|
|-|-|
|[Zaman uyumsuz aracılar](../../parallel/concrt/asynchronous-agents.md)<br /><br /> [Zaman uyumsuz Ileti blokları](../../parallel/concrt/asynchronous-message-blocks.md)<br /><br /> [İleti geçirme Işlevleri](../../parallel/concrt/message-passing-functions.md)<br /><br /> [Nasıl yapılır: çeşitli üretici tüketicisi desenleri uygulama](../../parallel/concrt/how-to-implement-various-producer-consumer-patterns.md)<br /><br /> [Nasıl yapılır: çağrıya ve transformatör sınıflarına çalışma Işlevleri sağlama](../../parallel/concrt/how-to-provide-work-functions-to-the-call-and-transformer-classes.md)<br /><br /> [Nasıl yapılır: bir veri ardışık düzeninde transformatör kullanma](../../parallel/concrt/how-to-use-transformer-in-a-data-pipeline.md)<br /><br /> [Nasıl yapılır: tamamlanan görevler arasında seçim yapma](../../parallel/concrt/how-to-select-among-completed-tasks.md)<br /><br /> [Nasıl yapılır: düzenli bir aralıkta Ileti gönderme](../../parallel/concrt/how-to-send-a-message-at-a-regular-interval.md)<br /><br /> [Nasıl yapılır: Ileti bloğu filtresini kullanma](../../parallel/concrt/how-to-use-a-message-block-filter.md)|Eşzamanlılık Çalışma Zamanı veri akışı işlemleri gerçekleştirmeye yönelik yapı taşları olan zaman uyumsuz aracılar, ileti blokları ve ileti geçirme işlevlerini açıklar.|
|[İzlenecek yol: aracı tabanlı uygulama oluşturma](../../parallel/concrt/walkthrough-creating-an-agent-based-application.md)<br /><br /> [İzlenecek yol: veri akışı Aracısı oluşturma](../../parallel/concrt/walkthrough-creating-a-dataflow-agent.md)|Temel aracı tabanlı uygulamaların nasıl oluşturulacağını gösterir.|
|[İzlenecek yol: görüntü Işleme ağı oluşturma](../../parallel/concrt/walkthrough-creating-an-image-processing-network.md)|Görüntü işleme gerçekleştiren zaman uyumsuz ileti blokları ağının nasıl oluşturulacağını gösterir.|
|[İzlenecek yol: kilitlenmeyi engellemek için birleştirmeyi kullanma](../../parallel/concrt/walkthrough-using-join-to-prevent-deadlock.md)|, Uygulamanızda kilitlenmeyi engellemek için Eşzamanlılık Çalışma Zamanı nasıl kullanacağınızı göstermek için dinleme filozoflar sorununu kullanır.|
|[İzlenecek yol: özel bir Ileti bloğu oluşturma](../../parallel/concrt/walkthrough-creating-a-custom-message-block.md)|Gelen iletileri önceliğe göre sipariş eden bir özel ileti bloğu türünün nasıl oluşturulacağını gösterir.|
|[Zaman uyumsuz aracılar kitaplığındaki en iyi uygulamalar](../../parallel/concrt/best-practices-in-the-asynchronous-agents-library.md)<br /><br /> [Eşzamanlılık Çalışma Zamanı genel En Iyi Yöntemler](../../parallel/concrt/general-best-practices-in-the-concurrency-runtime.md)|Aracılarla çalışmaya yönelik ipuçları ve en iyi uygulamalar sağlar.|

## <a name="exception-handling-and-debugging"></a>Özel Durum İşleme ve Hata Ayıklama

|Makale|Açıklama|
|-|-|
|[Özel Durum İşleme](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)|Eşzamanlılık Çalışma Zamanı özel durumlarla nasıl çalışabileceğinizi açıklar.|
|[Paralel Tanılama Araçları](../../parallel/concrt/parallel-diagnostic-tools-concurrency-runtime.md)|Uygulamalarınızı nasıl ince ayarlayacağını ve Eşzamanlılık Çalışma Zamanı en verimli şekilde kullanmasını öğretir.|

## <a name="tuning-performance"></a>Performans Ayarlama

|Makale|Açıklama|
|-|-|
|[Paralel Tanılama Araçları](../../parallel/concrt/parallel-diagnostic-tools-concurrency-runtime.md)|Uygulamalarınızı nasıl ince ayarlayacağını ve Eşzamanlılık Çalışma Zamanı en verimli şekilde kullanmasını öğretir.|
|[Zamanlayıcı örnekleri](../../parallel/concrt/scheduler-instances.md)<br /><br /> [Nasıl yapılır: zamanlayıcı örneğini yönetme](../../parallel/concrt/how-to-manage-a-scheduler-instance.md)<br /><br /> [Zamanlayıcı Ilkeleri](../../parallel/concrt/scheduler-policies.md)<br /><br /> [Nasıl yapılır: belirli Zamanlayıcı Ilkeleri belirtme](../../parallel/concrt/how-to-specify-specific-scheduler-policies.md)<br /><br /> [Nasıl yapılır: belirli Zamanlayıcı Ilkelerini kullanan aracılar oluşturma](../../parallel/concrt/how-to-create-agents-that-use-specific-scheduler-policies.md)|Zamanlayıcı örneklerini ve Zamanlayıcı ilkelerini yönetme ile çalışmayı gösterir. Masaüstü uygulamaları için Zamanlayıcı ilkeleri belirli kuralları belirli iş yükleri türleriyle ilişkilendirmenizi sağlar. Örneğin, bazı görevleri yükseltilmiş bir iş parçacığı önceliğinde çalıştırmak için bir zamanlayıcı örneği oluşturabilir ve varsayılan Zamanlayıcı 'yı kullanarak normal iş parçacığı önceliğinde diğer görevleri çalıştırabilirsiniz.|
|[Zamanlama grupları](../../parallel/concrt/schedule-groups.md)<br /><br /> [Nasıl yapılır: yürütme sırasını etkilemek için zamanlama grupları kullanma](../../parallel/concrt/how-to-use-schedule-groups-to-influence-order-of-execution.md)|Zamanlama gruplarının, ilgili görevleri bir araya getirme veya gruplama için nasıl kullanılacağını gösterir. Örneğin, bu görevler aynı işlemci düğümünde yürütmeyi avantajı olduğunda ilgili görevler arasında yüksek ölçüde yere sahip olmanız gerekebilir.|
|[Hafif görevler](../../parallel/concrt/lightweight-tasks.md)|Hafif görevlerin Yük Dengeleme veya iptal gerektirmeyen iş oluşturmak için nasıl yararlı olduğunu ve mevcut kodu Eşzamanlılık Çalışma Zamanı ile kullanmak üzere uyarlamak için de nasıl yararlı olduğunu açıklar.|
|[Bağlamlar](../../parallel/concrt/contexts.md)<br /><br /> [Nasıl yapılır: bir Cooperatıcı semaforu uygulamak için bağlam sınıfını kullanma](../../parallel/concrt/how-to-use-the-context-class-to-implement-a-cooperative-semaphore.md)<br /><br /> [Nasıl yapılır: gecikme gecikmesi için aşırı abonelik kullanma](../../parallel/concrt/how-to-use-oversubscription-to-offset-latency.md)|Eşzamanlılık Çalışma Zamanı tarafından yönetilen iş parçacıklarının davranışının nasıl kontrol edileceğini açıklar.|
|[Bellek yönetimi Işlevleri](../../parallel/concrt/memory-management-functions.md)<br /><br /> [Nasıl yapılır: bellek performansını artırmak için ayırma ve serbest kullanma](../../parallel/concrt/how-to-use-alloc-and-free-to-improve-memory-performance.md)|Eşzamanlılık Çalışma Zamanı için sağlanan bellek yönetimi işlevlerini, eşzamanlı bir biçimde ayırmayı ve serbest getirmenize yardımcı olmak için açıklar.|

## <a name="additional-resources"></a>Ek Kaynaklar

|Makale|Açıklama|
|-|-|
|[Windows Mağazası 'ndaki zaman uyumsuz programlama desenleri ve ipuçları (C++ ve XAML kullanan Windows Mağazası uygulamaları)](/previous-versions/windows/apps/jj160321(v=win.10))|C++ ve XAML kullanan bir Windows Çalışma Zamanı uygulaması olan Tepo 'da zaman uyumsuz işlemleri uygulamak için Eşzamanlılık Çalışma Zamanı nasıl kullandığımızda öğrenin.|
|[Yerel kod blogu 'nda paralel programlama](/archive/blogs/nativeconcurrency)|Eşzamanlılık Çalışma Zamanı paralel programlama hakkında ek kapsamlı blog makaleleri sağlar.|
|[C++ ve yerel kod forumundaki paralel bilgi Işlem](https://go.microsoft.com/fwlink/p/?linkid=183874)|Eşzamanlılık Çalışma Zamanı hakkındaki topluluk tartışmalarına katılımını sağlar.|
|[Paralel programlama](/dotnet/standard/parallel-programming/index)|.NET Framework bulunan paralel programlama modelini öğretir.|

## <a name="see-also"></a>Ayrıca bkz.

[Başvuru](../../parallel/concrt/reference/reference-concurrency-runtime.md)
