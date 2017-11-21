---
title: "Eşzamanlılık Çalışma zamanı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- Concurrency Runtime, getting started
- ConcRT (see Concurrency Runtime)
- Concurrency Runtime
ms.assetid: 874bc58f-8dce-483e-a3a1-4dcc9e52ed2c
caps.latest.revision: "40"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 87521d761a0355903408debe3ff27d26a006368b
ms.sourcegitcommit: ca2f94dfd015e0098a6eaf5c793ec532f1c97de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="concurrency-runtime"></a>Eşzamanlılık Çalışma Zamanı
Eşzamanlılık Çalışma zamanı c++ yazma güçlü, ölçeklenebilir ve esnek paralel uygulamalar yardımcı olur. Böylece eşzamanlılık için ilgili altyapı ayrıntıları yönetmek zorunda değilsiniz soyutlama düzeyinde başlatır. Hizmet taleplerini uygulamalarınızın kalitesini karşılayan zamanlama ilkeleri belirtmek için de kullanabilirsiniz. Eşzamanlılık Çalışma zamanı ile çalışmaya başlamanıza yardımcı olması için bu kaynakları kullanın.  
  
 Başvuru belgelerine bakın [başvuru](../../parallel/concrt/reference/reference-concurrency-runtime.md).  
  
> [!TIP]
>  Eşzamanlılık Çalışma zamanı yoğun C ++ 11 özellikleri güvenir ve daha modern C++ stili devralır. Daha fazla bilgi edinmek için okuma [Hoş Geldiniz geri c++](../../cpp/welcome-back-to-cpp-modern-cpp.md).  
  
## <a name="choosing-concurrency-runtime-features"></a>Eşzamanlılık Çalışma Zamanı Özellikleri Seçme  
  
|||  
|-|-|  
|[Genel bakış](../../parallel/concrt/overview-of-the-concurrency-runtime.md)|Eşzamanlılık Çalışma zamanı neden önemlidir ve anahtar özelliklerini açıklayan öğretir.|  
|[Diğer eşzamanlılık modelleriyle karşılaştırma](../../parallel/concrt/comparing-the-concurrency-runtime-to-other-concurrency-models.md)|Uygulama gereksinimlerine en uygun eşzamanlılık modeli kullanabilmesi için Windows havuzu ve OpenMP, iş parçacığı gibi diğer eşzamanlılık modelleriyle nasıl eşzamanlılık çalışma zamanı karşılaştırır gösterir.|  
|[OpenMP öğesinden eşzamanlılık çalışma zamanına geçiş](../../parallel/concrt/migrating-from-openmp-to-the-concurrency-runtime.md)|Eşzamanlılık Çalışma zamanı için OpenMP karşılaştırır ve Eşzamanlılık Çalışma zamanı kullanmak için mevcut OpenMP kod geçirme hakkında örnekler verilmektedir.|  
|[Paralel Desen kitaplığı (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md)|Paralel döngüler, görevler ve paralel kapsayıcılar sağlar PPL tanıtır.|  
|[Zaman uyumsuz aracılar kitaplığı](../../parallel/concrt/asynchronous-agents-library.md)|Zaman uyumsuz aracılar ve ileti veri akışı ve ardışık düzen görevleri uygulamalarınızda kolayca eklemenizi geçirme nasıl kullanılacağı için tanıtır.|  
|[Görev Zamanlayıcısı](../../parallel/concrt/task-scheduler-concurrency-runtime.md)|Eşzamanlılık Çalışma zamanı kullanan masaüstü uygulamalarınızın performansını ince ayar sağlar Görev Zamanlayıcı'tanıtır.|  
  
## <a name="task-parallelism-in-the-ppl"></a>PPL'de Görev Paralelliği  
  
|||  
|-|-|  
|[Görev Paralelliği](../../parallel/concrt/task-parallelism-concurrency-runtime.md)<br /><br /> [Nasıl yapılır: paralel sıralama rutini yazmak için parallel_invoke kullanma](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md)<br /><br /> [Nasıl yapılır: paralel işlemleri yürütmek için parallel_invoke kullanma](../../parallel/concrt/how-to-use-parallel-invoke-to-execute-parallel-operations.md)<br /><br /> [Nasıl yapılır: bir gecikmeden sonra tamamlanan bir görev oluşturma](../../parallel/concrt/how-to-create-a-task-that-completes-after-a-delay.md)|Görevler ve zaman uyumsuz kod yazın ve daha küçük parçalara paralel iş parçalayın size yardımcı olabilecek görev grupları açıklar.|  
|[İzlenecek yol: Vadeli işlemleri uygulama](../../parallel/concrt/walkthrough-implementing-futures.md)|Eşzamanlılık Çalışma zamanı özellikleri daha şeyler birleştirmek gösterilmiştir.|  
|[İzlenecek yol: Bir kullanıcı arabirimi iş parçacığından işi kaldırma](../../parallel/concrt/walkthrough-removing-work-from-a-user-interface-thread.md)|Bir MFC uygulamasında çalışan iş parçacığı için kullanıcı Arabirimi iş parçacığı tarafından gerçekleştirilen iş taşımak gösterilmiştir.|  
|[Paralel desen Kitaplığı'ndaki en iyi yöntemler](../../parallel/concrt/best-practices-in-the-parallel-patterns-library.md)<br /><br /> [Eşzamanlılık Çalışma zamanındaki genel en iyi yöntemler](../../parallel/concrt/general-best-practices-in-the-concurrency-runtime.md)|PPL'de ile çalışmak için ipuçları ve en iyi yöntemler sağlar.|  
  
## <a name="data-parallelism-in-the-ppl"></a>PPL'de Veri Paralelliği  
  
|||  
|-|-|  
|[Paralel algoritmalar](../../parallel/concrt/parallel-algorithms.md)<br /><br /> [Nasıl yapılır: parallel_for döngüsü yazma](../../parallel/concrt/how-to-write-a-parallel-for-loop.md)<br /><br /> [Nasıl yapılır: parallel_for_each döngüsü yazma](../../parallel/concrt/how-to-write-a-parallel-for-each-loop.md)<br /><br /> [Nasıl yapılır: eşleme gerçekleştirme ve işlemleri paralel azaltın](../../parallel/concrt/how-to-perform-map-and-reduce-operations-in-parallel.md)|Açıklar `parallel_for`, `parallel_for_each`, `parallel_invoke`ve diğer paralel algoritmalar. Çözmek için paralel algoritmalar kullanın *verileri paralel* veri toplulukları ile ilgili sorunları.|  
|[Paralel kapsayıcılar ve nesneler](../../parallel/concrt/parallel-containers-and-objects.md)<br /><br /> [Nasıl yapılır: etkinliği arttırmak için paralel kapsayıcılar kullanma](../../parallel/concrt/how-to-use-parallel-containers-to-increase-efficiency.md)<br /><br /> [Nasıl yapılır: performansı arttırmak için combinable kullanma](../../parallel/concrt/how-to-use-combinable-to-improve-performance.md)<br /><br /> [Nasıl yapılır: kümeleri birleştirmek için combinable kullanma](../../parallel/concrt/how-to-use-combinable-to-combine-sets.md)|Açıklar `combinable` sınıfı, yanı `concurrent_vector`, `concurrent_queue`, `concurrent_unordered_map`ve diğer paralel kapsayıcılar. Öğeleri iş parçacığı açısından güvenli erişim sağlayan kapsayıcıları gerektirdiğinde paralel kapsayıcılar ve nesneler kullanın.|  
|[Paralel desen Kitaplığı'ndaki en iyi yöntemler](../../parallel/concrt/best-practices-in-the-parallel-patterns-library.md)<br /><br /> [Eşzamanlılık Çalışma zamanındaki genel en iyi yöntemler](../../parallel/concrt/general-best-practices-in-the-concurrency-runtime.md)|PPL'de ile çalışmak için ipuçları ve en iyi yöntemler sağlar.|  
  
## <a name="canceling-tasks-and-parallel-algorithms"></a>Görevleri ve Paralel Algoritmaları İptal Etme  
  
|||  
|-|-|  
|[PPL'de iptal](cancellation-in-the-ppl.md)|Başlatmak ve iptal isteklerini yanıtlamak nasıl dahil olmak üzere PPL'de iptal rolü açıklanmaktadır.|  
|[Nasıl yapılır: paralel bir döngüden kurtulmak için İptal kullanın](../../parallel/concrt/how-to-use-cancellation-to-break-from-a-parallel-loop.md)<br /><br /> [Nasıl yapılır: özel durum paralel bir döngüden kurtulmak için işleme kullanın](../../parallel/concrt/how-to-use-exception-handling-to-break-from-a-parallel-loop.md)|Veri paralel iş iptal etmek için iki yol gösterir.|  
  
## <a name="windows-store-apps"></a>Windows Mağazası Uygulamaları  
  
|||  
|-|-|  
|[Windows mağazası uygulamaları için C++ içinde zaman uyumsuz işlemler oluşturma](../../parallel/concrt/creating-asynchronous-operations-in-cpp-for-windows-store-apps.md)|Zaman uyumsuz işlemleri üretmek için eşzamanlılık çalışma zamanı kullanırken dikkate alınması gereken önemli noktaları bazıları açıklanmaktadır bir [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] uygulama.|  
|[İzlenecek yol: Görevleri ve XML HTTP isteklerini kullanarak bağlanma](../../parallel/concrt/walkthrough-connecting-using-tasks-and-xml-http-requests.md)|PPL görevlerle birleştirmek gösterilmiştir `IXMLHTTPRequest2` ve `IXMLHTTPRequest2Callback` bir web hizmeti için HTTP GET ve POST istekleri göndermek için arabirimleri bir [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] uygulama.|  
|[Windows mağazası uygulama örnekleri](http://code.msdn.microsoft.com/windowsapps)|İndirilebilir kod örnekleri ve tanıtım içeren uygulamalar için [!INCLUDE[win8](../../build/reference/includes/win8_md.md)]. C++ örnekleri verileri işlemek için PPL görevler gibi eşzamanlılık çalışma zamanı özellikleri arka planda UX yanıt verebilir durumda tutmak için kullanın.|  
  
## <a name="dataflow-programming-in-the-asynchronous-agents-library"></a>Zaman Uyumsuz Aracılar Kitaplığı'nda Veri Akışı Programlama  
  
|||  
|-|-|  
|[Zaman uyumsuz aracılar](../../parallel/concrt/asynchronous-agents.md)<br /><br /> [Zaman uyumsuz ileti blokları](../../parallel/concrt/asynchronous-message-blocks.md)<br /><br /> [İleti geçirme işlevleri](../../parallel/concrt/message-passing-functions.md)<br /><br /> [Nasıl yapılır: çeşitli üretici-tüketici desenlerini uygulama](../../parallel/concrt/how-to-implement-various-producer-consumer-patterns.md)<br /><br /> [Nasıl yapılır: call ve transformer sınıflarına iş işlevleri sağlama](../../parallel/concrt/how-to-provide-work-functions-to-the-call-and-transformer-classes.md)<br /><br /> [Nasıl yapılır: veri ardışık düzeninde transformer kullanma](../../parallel/concrt/how-to-use-transformer-in-a-data-pipeline.md)<br /><br /> [Nasıl yapılır: Tamamlanan görevler arasında seçim](../../parallel/concrt/how-to-select-among-completed-tasks.md)<br /><br /> [Nasıl yapılır: düzenli aralıkla ileti gönderme](../../parallel/concrt/how-to-send-a-message-at-a-regular-interval.md)<br /><br /> [Nasıl yapılır: ileti bloğu filtresini kullanma](../../parallel/concrt/how-to-use-a-message-block-filter.md)|Zaman uyumsuz aracılar, ileti blokları ve Eşzamanlılık Çalışma Zamanı'nda veri akışı işlemleri gerçekleştirmek için yapı taşları ileti geçirme işlevleri açıklanmaktadır.|  
|[İzlenecek yol: aracı temelli uygulama oluşturma](../../parallel/concrt/walkthrough-creating-an-agent-based-application.md)<br /><br /> [İzlenecek yol: bir veri akışı Aracısı oluşturma](../../parallel/concrt/walkthrough-creating-a-dataflow-agent.md)|Temel tabanlı aracı uygulamalarının nasıl oluşturulacağını gösterir.|  
|[İzlenecek yol: bir görüntü işleme ağı oluşturma](../../parallel/concrt/walkthrough-creating-an-image-processing-network.md)|Görüntü işleme gerçekleştirmek zaman uyumsuz ileti blokları bir ağ oluşturulacağını gösterir.|  
|[İzlenecek yol: kilitlenmeyi önlemek için birleştirme birleştirme kullanma](../../parallel/concrt/walkthrough-using-join-to-prevent-deadlock.md)|Eşzamanlılık Çalışma zamanı, uygulamanızda kilitlenmeyi önlemek için nasıl kullanılacağını göstermek için yemek Yiyen Filozoflar sorunu kullanır.|  
|[İzlenecek yol: özel bir ileti bloğu oluşturma](../../parallel/concrt/walkthrough-creating-a-custom-message-block.md)|Önceliğe göre gelen iletileri sıralar özel ileti blok türünün nasıl oluşturulacağı gösterilmektedir.|  
|[Zaman uyumsuz aracılar Kitaplığı'ndaki en iyi yöntemler](../../parallel/concrt/best-practices-in-the-asynchronous-agents-library.md)<br /><br /> [Eşzamanlılık Çalışma zamanındaki genel en iyi yöntemler](../../parallel/concrt/general-best-practices-in-the-concurrency-runtime.md)|Aracıları ile çalışmak için ipuçları ve en iyi yöntemler sağlar.|  
  
## <a name="exception-handling-and-debugging"></a>Özel Durum İşleme ve Hata Ayıklama  
  
|||  
|-|-|  
|[Özel durum işleme](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)|Eşzamanlılık Çalışma zamanı özel durumları ile nasıl çalışılacağını açıklar.|  
|[Paralel tanılama araçları](../../parallel/concrt/parallel-diagnostic-tools-concurrency-runtime.md)|Uygulamalarınızın ince ayar ve Eşzamanlılık Çalışma zamanı en etkili kullanımını sağlamak öğretir.|  
  
## <a name="tuning-performance"></a>Performans Ayarlama  
  
|||  
|-|-|  
|[Paralel tanılama araçları](../../parallel/concrt/parallel-diagnostic-tools-concurrency-runtime.md)|Uygulamalarınızın ince ayar ve Eşzamanlılık Çalışma zamanı en etkili kullanımını sağlamak öğretir.|  
|[Zamanlayıcı örnekleri](../../parallel/concrt/scheduler-instances.md)<br /><br /> [Nasıl yapılır: Zamanlayıcı örneğini yönetme](../../parallel/concrt/how-to-manage-a-scheduler-instance.md)<br /><br /> [Zamanlayıcı ilkeleri](../../parallel/concrt/scheduler-policies.md)<br /><br /> [Nasıl yapılır: belirli Zamanlayıcı ilkeleri belirtme](../../parallel/concrt/how-to-specify-specific-scheduler-policies.md)<br /><br /> [Nasıl yapılır: belirli Zamanlayıcı ilkelerini kullanan aracılar oluşturma](../../parallel/concrt/how-to-create-agents-that-use-specific-scheduler-policies.md)|Nasıl çalışacağınız gösterilmektedir ile Zamanlayıcı örnekleri ve Zamanlayıcı ilkelerini yönetin. Masaüstü uygulamaları için Zamanlayıcı ilkeleri belirli kurallar belirli iş yükleri türleri ile ilişkilendirmek etkinleştirin. Örneğin, yükseltilmiş iş parçacığı öncelikli olarak bazı görevleri çalıştırmak ve normal iş parçacığı öncelikli diğer görevleri çalıştırmak için varsayılan Zamanlayıcısı'nı kullanmak için bir zamanlayıcı örneğini oluşturabilirsiniz.|  
|[Zamanlama grupları](../../parallel/concrt/schedule-groups.md)<br /><br /> [Nasıl yapılır: yürütme sırasını etkilemek için zamanlama grupları kullanma](../../parallel/concrt/how-to-use-schedule-groups-to-influence-order-of-execution.md)|Zamanlama grupları affinitize ya da grup, ilgili görevleri birlikte nasıl kullanılacağını gösterir. Örneğin, aynı işlemci düğümde yürütülen görevleri fayda zaman yere göre ilgili görevler arasında yüksek derecede gerektirebilir.|  
|[Basit görevler](../../parallel/concrt/lightweight-tasks.md)|Nasıl basit görevler açıklanmaktadır Yük Dengeleme veya iptal ve nasıl ayrıca eşzamanlılık çalışma zamanı ile kullanılmak üzere var olan kodu uyarlamak için yararlı oldukları gerektirmez iş oluşturmak için kullanışlıdır.|  
|[Bağlamları](../../parallel/concrt/contexts.md)<br /><br /> [Nasıl yapılır: bağlam sınıfını işbirlikçi semafor uygulamak için kullanın](../../parallel/concrt/how-to-use-the-context-class-to-implement-a-cooperative-semaphore.md)<br /><br /> [Nasıl yapılır: gecikmeyi dengelemek için aşırı abonelik kullanma](../../parallel/concrt/how-to-use-oversubscription-to-offset-latency.md)|Eşzamanlılık Çalışma zamanı tarafından yönetilen iş parçacığı davranışını denetlemek açıklar.|  
|[Bellek Yönetimi işlevleri](../../parallel/concrt/memory-management-functions.md)<br /><br /> [Nasıl yapılır: ayırma kullanın ve boş bellek performansını artırmak](../../parallel/concrt/how-to-use-alloc-and-free-to-improve-memory-performance.md)|Eşzamanlılık Çalışma zamanı ayırın ve eş zamanlı bir biçimde belleği serbest yardımcı olmak için sağladığı bellek yönetimi işlevleri açıklanmaktadır.|  
  
## <a name="additional-resources"></a>Ek Kaynaklar  
  
|||  
|-|-|  
|[Zaman uyumsuz programlama desenleri ve Hilo (C++ ve XAML kullanarak Windows mağazası uygulamaları) ipuçları](http://msdn.microsoft.com/library/windows/apps/jj160321.aspx)|Biz eşzamanlılık çalışma zamanı Hilo içinde zaman uyumsuz işlemleri uygulamak için nasıl kullanılacağını öğrenin bir [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] C++ ve XAML kullanarak uygulama.|  
|[Eşzamanlılık Çalışma zamanı ve paralel Desen kitaplığı Visual Studio 2010 için kod örnekleri](http://go.microsoft.com/fwlink/linkid=183875)|Örnek uygulamalar ve Eşzamanlılık Çalışma zamanı göstermek yardımcı programlarını sağlar.|  
|[Yerel kod günlüğündeki paralel programlama](http://go.microsoft.com/fwlink/linkid=183873)|Eşzamanlılık Çalışma zamanı içinde paralel programlama hakkında ek ayrıntılı blog makaleleri sağlar.|  
|[C++ ve yerel kodu Forumunda paralel Computing](http://go.microsoft.com/fwlink/linkid=183874)|Eşzamanlılık Çalışma zamanı hakkında topluluk tartışmalar katılma olanak tanır.|  
|[Paralel Programlama](/dotnet/standard/parallel-programming/index)|Kullanılabilir paralel programlama modeli hakkında öğretilmektedir [!INCLUDE[dnprdnshort](../../error-messages/tool-errors/includes/dnprdnshort_md.md)].|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Başvuru](../../parallel/concrt/reference/reference-concurrency-runtime.md)


