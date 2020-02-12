---
title: Eşzamanlılık Çalışma Zamanı
ms.date: 07/20/2018
helpviewer_keywords:
- Concurrency Runtime, getting started
- ConcRT (see Concurrency Runtime)
- Concurrency Runtime
ms.assetid: 874bc58f-8dce-483e-a3a1-4dcc9e52ed2c
ms.openlocfilehash: a17b4439baaec9caacfeca08983d0255b5a145de
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77141614"
---
# <a name="concurrency-runtime"></a>Eşzamanlılık Çalışma Zamanı

İçin C++ eşzamanlılık çalışma zamanı sağlam, ölçeklenebilir ve hızlı yanıt veren paralel uygulamalar yazmanıza yardımcı olur. Eşzamanlılık düzeyini yükseltir, böylece eşzamanlılık ile ilgili altyapı ayrıntılarını yönetmek zorunda değilsiniz. Ayrıca, uygulamalarınızın hizmet taleplerinin kalitesini karşılayan zamanlama ilkelerini belirtmek için de kullanabilirsiniz. Eşzamanlılık Çalışma Zamanı ile çalışmaya başlamanıza yardımcı olması için bu kaynakları kullanın.

Başvuru belgeleri için bkz. [başvuru](../../parallel/concrt/reference/reference-concurrency-runtime.md).

> [!TIP]
> Eşzamanlılık Çalışma Zamanı, C++ 11 özelliklerine büyük ölçüde yararlanır ve daha modern C++ stili benimsemektedir. Daha fazla bilgi edinmek için uygulamasına [ C++geri hoş geldiniz ](../../cpp/welcome-back-to-cpp-modern-cpp.md)makalesini okuyun.

## <a name="choosing-concurrency-runtime-features"></a>Eşzamanlılık Çalışma Zamanı Özellikleri Seçme

|||
|-|-|
|[Genel bakış](../../parallel/concrt/overview-of-the-concurrency-runtime.md)|Eşzamanlılık Çalışma Zamanı neden önemli olduğunu öğretir ve temel özelliklerini açıklar.|
|[Diğer eşzamanlılık modelleriyle karşılaştırma](../../parallel/concrt/comparing-the-concurrency-runtime-to-other-concurrency-models.md)|Uygulama gereksinimlerinize en uygun eşzamanlılık modelini kullanabilmeniz için, Eşzamanlılık Çalışma Zamanı Windows iş parçacığı havuzu ve OpenMP gibi diğer eşzamanlılık modelleriyle nasıl Karşılaştırıldığı gösterilmektedir.|
|[OpenMP döngüsünden Eşzamanlılık Çalışma Zamanına geçiş](../../parallel/concrt/migrating-from-openmp-to-the-concurrency-runtime.md)|OpenMP 'ı Eşzamanlılık Çalışma Zamanı karşılaştırır ve mevcut OpenMP kodunun Eşzamanlılık Çalışma Zamanı kullanmak için nasıl geçirileceğiyle ilgili örnekler sağlar.|
|[Paralel Desen Kitaplığı (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md)|, Paralel döngüler, görevler ve paralel kapsayıcılar sağlayan PPL 'yi tanıtır.|
|[Zaman Uyumsuz Aracılar Kitaplığı](../../parallel/concrt/asynchronous-agents-library.md)|, Uygulamalarınızda veri akışını ve ardışık düzen görevlerini kolayca birleştirmek için zaman uyumsuz aracıların ve ileti geçirmenin nasıl kullanılacağını tanıtır.|
|[Görev Zamanlayıcı](../../parallel/concrt/task-scheduler-concurrency-runtime.md)|Sizi, Eşzamanlılık Çalışma Zamanı kullanan masaüstü uygulamalarınızın performansını ince ayarlamanıza olanak tanıyan Görev Zamanlayıcı tanıtır.|

## <a name="task-parallelism-in-the-ppl"></a>PPL'de Görev Paralelliği

|||
|-|-|
|[Görev Paralelliği](../../parallel/concrt/task-parallelism-concurrency-runtime.md)<br /><br /> [Nasıl yapılır: Paralel Sıralama Rutini Yazmak için parallel_invoke Kullanma](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md)<br /><br /> [Nasıl yapılır: Paralel İşlemleri Yürütmek için parallel_invoke Kullanma](../../parallel/concrt/how-to-use-parallel-invoke-to-execute-parallel-operations.md)<br /><br /> [Nasıl yapılır: Bir Gecikmeden Sonra Tamamlanan bir Görev Oluşturma](../../parallel/concrt/how-to-create-a-task-that-completes-after-a-delay.md)|Zaman uyumsuz kod yazmanıza ve paralel çalışmayı daha küçük parçalara ayırmayı sağlamanıza yardımcı olan görevleri ve görev gruplarını açıklar.|
|[İzlenecek Yol: Vadeli İşlemleri Uygulama](../../parallel/concrt/walkthrough-implementing-futures.md)|Daha fazla şey yapmak için Eşzamanlılık Çalışma Zamanı özelliklerinin nasıl birleştirileceğini gösterir.|
|[İzlenecek Yol: Kullanıcı Arabirimi İş Parçacığından İşi Kaldırma](../../parallel/concrt/walkthrough-removing-work-from-a-user-interface-thread.md)|Bir MFC uygulamasındaki UI iş parçacığı tarafından gerçekleştirilen çalışmanın bir çalışan iş parçacığına nasıl taşınacağını gösterir.|
|[Paralel Desen Kitaplığı'ndaki En İyi Yöntemler](../../parallel/concrt/best-practices-in-the-parallel-patterns-library.md)<br /><br /> [Eşzamanlılık Çalışma Zamanındaki Genel En İyi Yöntemler](../../parallel/concrt/general-best-practices-in-the-concurrency-runtime.md)|PPL ile çalışmaya yönelik ipuçları ve en iyi uygulamalar sağlar.|

## <a name="data-parallelism-in-the-ppl"></a>PPL'de Veri Paralelliği

|||
|-|-|
|[Paralel Algoritmalar](../../parallel/concrt/parallel-algorithms.md)<br /><br /> [Nasıl yapılır: parallel_for Döngüsü Yazma](../../parallel/concrt/how-to-write-a-parallel-for-loop.md)<br /><br /> [Nasıl yapılır: parallel_for_each Döngüsü Yazma](../../parallel/concrt/how-to-write-a-parallel-for-each-loop.md)<br /><br /> [Nasıl yapılır: Eşleme Gerçekleştirme ve İşlemleri Paralel Olarak Azaltma](../../parallel/concrt/how-to-perform-map-and-reduce-operations-in-parallel.md)|`parallel_for`, `parallel_for_each`, `parallel_invoke`ve diğer paralel algoritmaları açıklar. Verilerin koleksiyonlarını içeren *paralel* sorunları çözümlemek için paralel algoritmaları kullanın.|
|[Paralel Kapsayıcılar ve Nesneler](../../parallel/concrt/parallel-containers-and-objects.md)<br /><br /> [Nasıl yapılır: Etkinliği Arttırmak için Paralel Kapsayıcılar Kullanma](../../parallel/concrt/how-to-use-parallel-containers-to-increase-efficiency.md)<br /><br /> [Nasıl yapılır: Performansı arttırmak için combinable Kullanma](../../parallel/concrt/how-to-use-combinable-to-improve-performance.md)<br /><br /> [Nasıl yapılır: Kümeleri Birleştirmek için combinable Kullanma](../../parallel/concrt/how-to-use-combinable-to-combine-sets.md)|`combinable` sınıfının yanı sıra `concurrent_vector`, `concurrent_queue`, `concurrent_unordered_map`ve diğer paralel kapsayıcıları açıklar. Öğelerine iş parçacığı açısından güvenli erişim sağlayan kapsayıcılar gerektirdiğinde paralel kapsayıcıları ve nesneleri kullanın.|
|[Paralel Desen Kitaplığı'ndaki En İyi Yöntemler](../../parallel/concrt/best-practices-in-the-parallel-patterns-library.md)<br /><br /> [Eşzamanlılık Çalışma Zamanındaki Genel En İyi Yöntemler](../../parallel/concrt/general-best-practices-in-the-concurrency-runtime.md)|PPL ile çalışmaya yönelik ipuçları ve en iyi uygulamalar sağlar.|

## <a name="canceling-tasks-and-parallel-algorithms"></a>Görevleri ve Paralel Algoritmaları İptal Etme

|||
|-|-|
|[PPL'de İptal](cancellation-in-the-ppl.md)|İptal isteklerini başlatma ve yanıtlama dahil olmak üzere PPL 'de iptal etme rolünü açıklar.|
|[Nasıl yapılır: Paralel Bir Döngüden Kurtulmak için İptal](../../parallel/concrt/how-to-use-cancellation-to-break-from-a-parallel-loop.md)<br /><br /> [Nasıl yapılır: Paralel Bir Döngüden Kurtulmak için Özel Durum İşlemeyi Kullanma](../../parallel/concrt/how-to-use-exception-handling-to-break-from-a-parallel-loop.md)|Veri paralel çalışmayı iptal etmenin iki yolunu gösterir.|

## <a name="universal-windows-platform-apps"></a>Evrensel Windows platformu uygulamaları

|||
|-|-|
|[UWP Uygulamaları için C++ Uygulamasında Zaman Uyumsuz İşlemler Oluşturma](../../parallel/concrt/creating-asynchronous-operations-in-cpp-for-windows-store-apps.md)|UWP uygulamasında zaman uyumsuz işlemler üretmek için Eşzamanlılık Çalışma Zamanı kullandığınızda göz önünde bulundurmanız gereken bazı önemli noktaları açıklar.|
|[İzlenecek Yol: Görevleri ve XML HTTP İsteklerini Kullanarak Bağlanma](../../parallel/concrt/walkthrough-connecting-using-tasks-and-xml-http-requests.md)|UWP uygulamasındaki bir Web hizmetine HTTP GET ve POST istekleri göndermek için `IXMLHTTPRequest2` ve `IXMLHTTPRequest2Callback` arabirimleriyle PPL görevlerinin nasıl birleştirileceğini gösterir.|
|[Windows Çalışma Zamanı uygulama örnekleri](https://code.msdn.microsoft.com/windowsapps)|Windows 8. x için indirilebilir kod örnekleri ve Tanıtım uygulamaları içerir. C++ Örnekler, UX 'in yanıt vermesini sağlamak için arka plandaki verileri işlemek üzere PPL görevleri gibi eşzamanlılık çalışma zamanı özellikleri kullanır.|

## <a name="dataflow-programming-in-the-asynchronous-agents-library"></a>Zaman Uyumsuz Aracılar Kitaplığı'nda Veri Akışı Programlama

|||
|-|-|
|[Zaman Uyumsuz Aracılar](../../parallel/concrt/asynchronous-agents.md)<br /><br /> [Zaman Uyumsuz İleti Blokları](../../parallel/concrt/asynchronous-message-blocks.md)<br /><br /> [İleti Geçirme İşlevleri](../../parallel/concrt/message-passing-functions.md)<br /><br /> [Nasıl yapılır: Çeşitli Üretici-Tüketici Desenlerini Uygulama](../../parallel/concrt/how-to-implement-various-producer-consumer-patterns.md)<br /><br /> [Nasıl yapılır: call ve transformer Sınıflarına İş İşlevleri Sağlama](../../parallel/concrt/how-to-provide-work-functions-to-the-call-and-transformer-classes.md)<br /><br /> [Nasıl yapılır: Veri İşlem Hattında transformer Kullanma](../../parallel/concrt/how-to-use-transformer-in-a-data-pipeline.md)<br /><br /> [Nasıl yapılır: Tamamlanan Görevler Arasında Seçim Yapma](../../parallel/concrt/how-to-select-among-completed-tasks.md)<br /><br /> [Nasıl yapılır: Düzenli Aralıkla İleti Gönderme](../../parallel/concrt/how-to-send-a-message-at-a-regular-interval.md)<br /><br /> [Nasıl yapılır: İleti Bloğu Filtresini Kullanma](../../parallel/concrt/how-to-use-a-message-block-filter.md)|Eşzamanlılık Çalışma Zamanı veri akışı işlemleri gerçekleştirmeye yönelik yapı taşları olan zaman uyumsuz aracılar, ileti blokları ve ileti geçirme işlevlerini açıklar.|
|[İzlenecek Yol: Aracı Temelli Uygulama Oluşturma](../../parallel/concrt/walkthrough-creating-an-agent-based-application.md)<br /><br /> [İzlenecek Yol: Veri Akışı Aracısı Oluşturma](../../parallel/concrt/walkthrough-creating-a-dataflow-agent.md)|Temel aracı tabanlı uygulamaların nasıl oluşturulacağını gösterir.|
|[İzlenecek yol: Görüntü İşleme Ağı Oluşturma](../../parallel/concrt/walkthrough-creating-an-image-processing-network.md)|Görüntü işleme gerçekleştiren zaman uyumsuz ileti blokları ağının nasıl oluşturulacağını gösterir.|
|[İzlenecek Yol: Kilitlenmeyi Önlemek için birleştirme kullanma](../../parallel/concrt/walkthrough-using-join-to-prevent-deadlock.md)|, Uygulamanızda kilitlenmeyi engellemek için Eşzamanlılık Çalışma Zamanı nasıl kullanacağınızı göstermek için dinleme filozoflar sorununu kullanır.|
|[İzlenecek Yol: Özel bir İleti Bloğu Oluşturma](../../parallel/concrt/walkthrough-creating-a-custom-message-block.md)|Gelen iletileri önceliğe göre sipariş eden bir özel ileti bloğu türünün nasıl oluşturulacağını gösterir.|
|[Zaman Uyumsuz Aracılar Kitaplığı'ndaki En İyi Yöntemler](../../parallel/concrt/best-practices-in-the-asynchronous-agents-library.md)<br /><br /> [Eşzamanlılık Çalışma Zamanındaki Genel En İyi Yöntemler](../../parallel/concrt/general-best-practices-in-the-concurrency-runtime.md)|Aracılarla çalışmaya yönelik ipuçları ve en iyi uygulamalar sağlar.|

## <a name="exception-handling-and-debugging"></a>Özel Durum İşleme ve Hata Ayıklama

|||
|-|-|
|[Özel Durum İşleme](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)|Eşzamanlılık Çalışma Zamanı özel durumlarla nasıl çalışabileceğinizi açıklar.|
|[Paralel Tanılama Araçları](../../parallel/concrt/parallel-diagnostic-tools-concurrency-runtime.md)|Uygulamalarınızı nasıl ince ayarlayacağını ve Eşzamanlılık Çalışma Zamanı en verimli şekilde kullanmasını öğretir.|

## <a name="tuning-performance"></a>Performans Ayarlama

|||
|-|-|
|[Paralel Tanılama Araçları](../../parallel/concrt/parallel-diagnostic-tools-concurrency-runtime.md)|Uygulamalarınızı nasıl ince ayarlayacağını ve Eşzamanlılık Çalışma Zamanı en verimli şekilde kullanmasını öğretir.|
|[Zamanlayıcı Örnekleri](../../parallel/concrt/scheduler-instances.md)<br /><br /> [Nasıl yapılır: Zamanlayıcı Örneğini Yönetme](../../parallel/concrt/how-to-manage-a-scheduler-instance.md)<br /><br /> [Scheduler İlkeleri](../../parallel/concrt/scheduler-policies.md)<br /><br /> [Nasıl yapılır: Belirli Zamanlayıcı İlkeleri Belirtme](../../parallel/concrt/how-to-specify-specific-scheduler-policies.md)<br /><br /> [Nasıl yapılır: Belirli Zamanlayıcı İlkelerini Kullanan Aracılar Oluşturma](../../parallel/concrt/how-to-create-agents-that-use-specific-scheduler-policies.md)|Zamanlayıcı örneklerini ve Zamanlayıcı ilkelerini yönetme ile çalışmayı gösterir. Masaüstü uygulamaları için Zamanlayıcı ilkeleri belirli kuralları belirli iş yükleri türleriyle ilişkilendirmenizi sağlar. Örneğin, bazı görevleri yükseltilmiş bir iş parçacığı önceliğinde çalıştırmak için bir zamanlayıcı örneği oluşturabilir ve varsayılan Zamanlayıcı 'yı kullanarak normal iş parçacığı önceliğinde diğer görevleri çalıştırabilirsiniz.|
|[Zamanlama Grupları](../../parallel/concrt/schedule-groups.md)<br /><br /> [Nasıl yapılır: Yürütme Sırasını Etkilemek için Zamanlama Grupları Kullanma](../../parallel/concrt/how-to-use-schedule-groups-to-influence-order-of-execution.md)|Zamanlama gruplarının, ilgili görevleri bir araya getirme veya gruplama için nasıl kullanılacağını gösterir. Örneğin, bu görevler aynı işlemci düğümünde yürütmeyi avantajı olduğunda ilgili görevler arasında yüksek ölçüde yere sahip olmanız gerekebilir.|
|[Basit Görevler](../../parallel/concrt/lightweight-tasks.md)|Hafif görevlerin Yük Dengeleme veya iptal gerektirmeyen iş oluşturmak için nasıl yararlı olduğunu ve mevcut kodu Eşzamanlılık Çalışma Zamanı ile kullanmak üzere uyarlamak için de nasıl yararlı olduğunu açıklar.|
|[Bağlamlar](../../parallel/concrt/contexts.md)<br /><br /> [Nasıl yapılır: Bağlam Sınıfını İşbirlikçi Semafor Uygulamak için Kullanma](../../parallel/concrt/how-to-use-the-context-class-to-implement-a-cooperative-semaphore.md)<br /><br /> [Nasıl yapılır: Gecikmeyi Dengelemek için Aşırı Aboneliği Kullanma](../../parallel/concrt/how-to-use-oversubscription-to-offset-latency.md)|Eşzamanlılık Çalışma Zamanı tarafından yönetilen iş parçacıklarının davranışının nasıl kontrol edileceğini açıklar.|
|[Bellek Yönetimi İşlevleri](../../parallel/concrt/memory-management-functions.md)<br /><br /> [Nasıl yapılır: Bellek Performansını Artırmak için Alloc ve Free Kullanma](../../parallel/concrt/how-to-use-alloc-and-free-to-improve-memory-performance.md)|Eşzamanlılık Çalışma Zamanı için sağlanan bellek yönetimi işlevlerini, eşzamanlı bir biçimde ayırmayı ve serbest getirmenize yardımcı olmak için açıklar.|

## <a name="additional-resources"></a>Ek Kaynaklar

|||
|-|-|
|[Zaman uyumsuz programlama desenleri ve Tepklerdeki ipuçları (Windows Mağazası uygulamaları C++ ve XAML kullanarak)](/previous-versions/windows/apps/jj160321(v=win.10))|Ve XAML kullanan C++ bir Windows çalışma zamanı uygulama olan Tepo 'da zaman uyumsuz işlemleri uygulamak için eşzamanlılık çalışma zamanı nasıl kullandığımızda öğrenin.|
|[Yerel kod blogu 'nda paralel programlama](https://go.microsoft.com/fwlink/p/?linkid=183873)|Eşzamanlılık Çalışma Zamanı paralel programlama hakkında ek kapsamlı blog makaleleri sağlar.|
|[C++ Ve yerel kod forumuna paralel bilgi işlem](https://go.microsoft.com/fwlink/p/?linkid=183874)|Eşzamanlılık Çalışma Zamanı hakkındaki topluluk tartışmalarına katılımını sağlar.|
|[Paralel Programlama](/dotnet/standard/parallel-programming/index)|.NET Framework bulunan paralel programlama modelini öğretir.|

## <a name="see-also"></a>Ayrıca bkz.

[Başvuru](../../parallel/concrt/reference/reference-concurrency-runtime.md)
