---
title: "Eşzamanlılık Çalışma zamanındaki genel en iyi yöntemler | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- Concurrency Runtime, general best practices
ms.assetid: ce5c784c-051e-44a6-be84-8b3e1139c18b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d5c2c626ceb0243e91e56d70f0d8ae71208b157f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="general-best-practices-in-the-concurrency-runtime"></a>Eşzamanlılık Çalışma Zamanındaki Genel En İyi Yöntemler
Bu belge eşzamanlılık çalışma zamanı birden çok alanlarına uygulanan en iyi uygulamaları açıklar.  
  
##  <a name="top"></a>Bölümler  
 Bu belgede aşağıdaki bölümler yer alır:  
  
- [İşbirlikçi eşitleme yapıları mümkün olduğunda kullanın](#synchronization)  
  
- [Değil verim uzun görevlerden kaçının](#yield)  
  
- [Aşırı abonelik engelleyen veya yüksek gecikme süresine sahiptir uzaklık işlemleri için kullanın](#oversubscription)  
  
- [Eşzamanlı bellek yönetimi işlevleri mümkün olduğunda kullanın](#memory)  
  
- [RAII eşzamanlılık nesnelerin ömrü yönetmek için kullanın](#raii)  
  
- [Genel kapsamda eşzamanlılık nesneleri oluşturma](#global-scope)  
  
- [Eşzamanlılık nesneleri paylaşılan veri Segmentlerinde kullanmayın](#shared-data)  
  
##  <a name="synchronization"></a>İşbirlikçi eşitleme yapıları mümkün olduğunda kullanın  
 Eşzamanlılık Çalışma zamanı dış eşitleme nesneyi gerektirmeyen birçok eşzamanlılık güvenli yapıları sağlar. Örneğin, [concurrency::concurrent_vector](../../parallel/concrt/reference/concurrent-vector-class.md) SAX eşzamanlılık güvenli ekleme ve işlemleri erişim öğesi. Ancak, bir kaynağa özel erişim gerektiren olduğu durumlarda, çalışma zamanı sağlar [concurrency::critical_section](../../parallel/concrt/reference/critical-section-class.md), [concurrency::reader_writer_lock](../../parallel/concrt/reference/reader-writer-lock-class.md), ve [eşzamanlılık :: olay](../../parallel/concrt/reference/event-class.md) sınıfları. Bu tür işlevinizde davranır; Bu nedenle, veriler için ilk görev bekler gibi Görev Zamanlayıcısı'nı başka bir bağlam için işlem kaynakları yeniden tahsis edebilirsiniz. Mümkün olduğunda, bu eşitleme türleri hangi işlevinizde davranır olmayan diğer eşitleme mekanizmaları yerine, Windows API'si tarafından sağlanan gibi kullanın. Bu eşitleme türleri ve bir kod örneği hakkında daha fazla bilgi için bkz: [eşitleme veri yapıları](../../parallel/concrt/synchronization-data-structures.md) ve [eşitleme veri yapılarını Windows API karşılaştırma](../../parallel/concrt/comparing-synchronization-data-structures-to-the-windows-api.md).  
  
 [[Üst](#top)]  
  
##  <a name="yield"></a>Değil verim uzun görevlerden kaçının  
 Görev Zamanlayıcısı'nı işlevinizde davrandığı için görevler arasında eşitliği sağlamaz. Bu nedenle, bir görev, diğer görevleri başlamasını engelleyebilir. Bu bazı durumlarda kabul edilebilir olmasına karşın, diğer durumlarda bu kilitlenme ya da yetersizliğini neden olabilir.  
  
 Aşağıdaki örnek, ayrılmış işleme kaynakları sayısından daha fazla görevleri gerçekleştirir. İlk görev için Görev Zamanlayıcısı'nı vermez ve ilk görevi tamamlanana kadar ikinci görevi bu nedenle başlatmaz.  
  
 [!code-cpp[concrt-cooperative-tasks#1](../../parallel/concrt/codesnippet/cpp/general-best-practices-in-the-concurrency-runtime_1.cpp)]  
  
 Bu örnek şu çıkışı üretir:  
  
 1: 250000000 1: 500000000 1: 750000000 1: 1000000000 2: 250000000 2: 500000000 2: 750000000 2: 1000000000  
  

 İki görev arasındaki iş Birliği sağlamanın birkaç yolu vardır. Görev Zamanlayıcı'uzun süre çalışan bir görev için bazen verim bir yoludur. Aşağıdaki örnek değiştirir `task` çağrılacak işlevi [concurrency::Context::Yield](reference/context-class.md#yield) başka bir görev çalıştırabilmeniz için yürütme için Görev Zamanlayıcısı'nı elde etmek üzere yöntemi.  

  
 [!code-cpp[concrt-cooperative-tasks#2](../../parallel/concrt/codesnippet/cpp/general-best-practices-in-the-concurrency-runtime_2.cpp)]  
  
 Bu örnek şu çıkışı üretir:  
  
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
  
 `Context::Yield` Yöntemi yalnızca başka bir etkin iş parçacığında geçerli iş parçacığının ait olduğu, basit bir görev veya başka bir işletim sistemi iş parçacığı Zamanlayıcı verir. Bu yöntem çalışmaya çalıştırmak için zamanlanan vermez bir [concurrency::task_group](reference/task-group-class.md) veya [concurrency::structured_task_group](../../parallel/concrt/reference/structured-task-group-class.md) nesne ancak henüz başlatılmadı.  
  
 Uzun süre çalışan görevler arasında işbirliği etkinleştirmek için diğer yolları vardır. Büyük bir görevi daha küçük alt görevlere bozulabilir. Aşırı abonelik uzun bir görev sırasında etkinleştirebilirsiniz. Aşırı abonelik donanım iş parçacıkları kullanılabilir sayısından daha fazla iş parçacığı oluşturmanıza olanak sağlar. Uzun bir iş gecikme, örneğin, disk veya bir ağ bağlantısından veri okuma yüksek miktarda içerdiğinde aşırı abonelik özellikle yararlı olur. Basit görevler ve aşırı abonelik hakkında daha fazla bilgi için bkz: [Görev Zamanlayıcı](../../parallel/concrt/task-scheduler-concurrency-runtime.md).  
  
 [[Üst](#top)]  
  
##  <a name="oversubscription"></a>Aşırı abonelik engelleyen veya yüksek gecikme süresine sahiptir uzaklık işlemleri için kullanın  
 Eşzamanlılık Çalışma Zamanı Eşitleme temelleri gibi sağlar [concurrency::critical_section](../../parallel/concrt/reference/critical-section-class.md), işbirliği ile engellemek ve birbirlerine elde etmek için görevleri etkinleştirin. Bir görev işlevinizde engeller veya verir, Görev Zamanlayıcı'yı bir veri için ilk görev bekler gibi başka bir bağlam için işlem kaynakları yeniden tahsis edebilirsiniz.  
  
 Eşzamanlılık Çalışma zamanı tarafından sağlanan işbirlikçi engelleme mekanizması kullanamazsınız durumlar vardır. Örneğin, kullandığınız harici bir kitaplığı farklı eşitleme mekanizması kullanıyor olabilir. Windows API kullandığınızda, örneğin, gecikme, yüksek miktarda olabilir bir işlem gerçekleştirdiğinizde başka bir örnektir `ReadFile` bir ağ bağlantısından veri okumak için işlev. Bu durumlarda, aşırı abonelik diğer görevlerini başka bir görev boştayken çalışacak şekilde etkinleştirebilirsiniz. Aşırı abonelik donanım iş parçacıkları kullanılabilir sayısından daha fazla iş parçacığı oluşturmanıza olanak sağlar.  
  
 Aşağıdaki işlevi göz önünde bulundurun `download`, dosyanın belirtilen URL'de indirir. Bu örnekte [concurrency::Context::Oversubscribe](reference/context-class.md#oversubscribe) geçici olarak etkin iş parçacığı sayısını artırmak için yöntem.  

 [!code-cpp[concrt-download-oversubscription#4](../../parallel/concrt/codesnippet/cpp/general-best-practices-in-the-concurrency-runtime_3.cpp)]  
  
 Çünkü `GetHttpFile` işlevi olası görünmeyen bir işlemi gerçekleştirir, aşırı abonelik diğer görevlerini geçerli görev için verileri bekler olarak çalışacak şekilde etkinleştirebilirsiniz. Bu örneğin tam sürümü için bkz: [nasıl yapılır: kullanım aşırı abonelik uzaklığı gecikme](../../parallel/concrt/how-to-use-oversubscription-to-offset-latency.md).  
  
 [[Üst](#top)]  
  
##  <a name="memory"></a>Eşzamanlı bellek yönetimi işlevleri mümkün olduğunda kullanın  

 Bellek Yönetimi işlevleri kullanmak [concurrency::Alloc](reference/concurrency-namespace-functions.md#alloc) ve [concurrency::Free](reference/concurrency-namespace-functions.md#free)sık görece kısa ömürlü küçük nesneler tahsis hassas görevler varsa,. Eşzamanlılık Çalışma zamanı her çalışan iş parçacığı için ayrı bir önbellek tutar. `Alloc` Ve `Free` işlevleri ayırma ve serbest kilitleri ya da bellek engelleri kullanmanıza gerek kalmadan bu önbellekler bellekten.  
  
 Bu bellek yönetimi işlevleri hakkında daha fazla bilgi için bkz: [Görev Zamanlayıcı](../../parallel/concrt/task-scheduler-concurrency-runtime.md). Bu işlevlerini kullanan bir örnek için bkz: [nasıl yapılır: kullanım ayırma ve serbest bellek performansını artırmak için](../../parallel/concrt/how-to-use-alloc-and-free-to-improve-memory-performance.md).  
  
 [[Üst](#top)]  
  
##  <a name="raii"></a>RAII eşzamanlılık nesnelerin ömrü yönetmek için kullanın  
 Eşzamanlılık Çalışma zamanı özel durum işleme iptal gibi özellikleri uygulamak için kullanır. Bu nedenle, çalışma zamanına çağırmak ya da çalışma zamanına çağıran başka bir kitaplıkla çağrı özel durum güvenli kod yazın.  
  
 *Kaynak edinme olan başlatma* (RAII) düzeni verilen kapsam altında bir eşzamanlılık nesnesinin ömrü güvenli bir şekilde yönetmek için bir yol olduğu. RAII deseni altında bir veri yapısı yığında ayrılmış. Bu veri yapısını başlatır veya bir kaynak oluşturulur ve bozar veya veri yapısı kaldırıldığı zaman, kaynak serbest zaman alır. RAII deseni çevreleyen kapsamdaki çıkar önce yıkıcı adlandırılır güvence altına alır. Bir işlev birden çok içerdiğinde bu deseni yararlıdır `return` deyimleri. Bu deseni Ayrıca, özel durum güvenli kod yazmanıza yardımcı olur. Zaman bir `throw` deyimi neden bırakma için yıkıcı RAII nesnesi adında için yığın; bu nedenle, kaynağın her zaman doğru yayımlanan veya silinmiş.  
  
 Örneğin, RAII desen kullanan birden fazla sınıf çalışma zamanı tanımlar [concurrency::critical_section::scoped_lock](../../parallel/concrt/reference/critical-section-class.md#critical_section__scoped_lock_class) ve [concurrency::reader_writer_lock::scoped_lock](reference/reader-writer-lock-class.md#scoped_lock_class). Bu yardımcı sınıfları olarak da bilinir *kilitleri kapsamlı*. İle çalışırken bu sınıflar birkaç avantaj sunar [concurrency::critical_section](../../parallel/concrt/reference/critical-section-class.md) veya [concurrency::reader_writer_lock](../../parallel/concrt/reference/reader-writer-lock-class.md) nesneleri. Bu sınıfların Oluşturucusu sağlanan erişim edinir `critical_section` veya `reader_writer_lock` nesne; söz konusu nesne yıkıcı sürümleri erişimi. Da kaldırıldığı zaman kapsamlı bir kilit karşılıklı dışlama nesnesine erişim otomatik olarak yayımlar için el ile temel alınan nesnenin kilidini açma değil.  
  
 Aşağıdaki sınıf göz önünde bulundurun `account`, harici bir kitaplığı tarafından tanımlanır ve bu nedenle değiştirilemez.  
  
 [!code-cpp[concrt-account-transactions#1](../../parallel/concrt/codesnippet/cpp/general-best-practices-in-the-concurrency-runtime_4.h)]  
  
 Aşağıdaki örnek birden çok işlem gerçekleştirir. bir `account` paralel nesne. Örnek kullanan bir `critical_section` erişimi eşitlemek için nesne `account` çünkü nesne `account` sınıf eşzamanlılık uyumlu değil. Her paralel işlem kullanan bir `critical_section::scoped_lock` , garanti nesnesine `critical_section` işlemi başarılı veya başarısız olduğunda nesne kilidi. Hesap bakiyesini negatifse `withdraw` işlemi başarısız bir özel durum atma tarafından.  
  
 [!code-cpp[concrt-account-transactions#2](../../parallel/concrt/codesnippet/cpp/general-best-practices-in-the-concurrency-runtime_5.cpp)]  
  
 Bu örnekte aşağıdaki örnek çıkışı üretir:  
  
```Output  
Balance before deposit: 1924  
Balance after deposit: 2924  
Balance before withdrawal: 2924  
Balance after withdrawal: -76  
Balance before withdrawal: -76  
Error details:  
    negative balance: -76  
```  
  
 Eşzamanlılık nesneleri ömrünü yönetmek için RAII desenini kullanan ek örnekler için bkz [izlenecek yol: bir kullanıcı arabirimi iş parçacığı kaldırma çalışma](../../parallel/concrt/walkthrough-removing-work-from-a-user-interface-thread.md), [nasıl yapılır: bir Cooperative uygulamak için bağlam sınıfını kullanın Semafor](../../parallel/concrt/how-to-use-the-context-class-to-implement-a-cooperative-semaphore.md), ve [nasıl yapılır: gecikmeyi dengelemek için aşırı abonelik kullanma](../../parallel/concrt/how-to-use-oversubscription-to-offset-latency.md).  
  
 [[Üst](#top)]  
  
##  <a name="global-scope"></a>Genel kapsamda eşzamanlılık nesneleri oluşturma  
 Genel kapsamda bir eşzamanlılık nesne oluşturduğunuzda, uygulamanızda gerçekleşmesi erişim ihlalleri kilitlenme veya bellek gibi sorunlara neden olabilir.  
  
 Örneğin, bir eşzamanlılık çalışma zamanı nesne oluşturduğunuzda, bir henüz oluşturulmadı, çalışma zamanı varsayılan Zamanlayıcı sizin için oluşturur. Genel nesne oluşturma sırasında oluşturulan bir çalışma zamanı nesne buna göre bu varsayılan Zamanlayıcı oluşturmak çalışma zamanı neden olur. Ancak, bu işlem eşzamanlılık çalışma zamanı altyapısını destekleyen diğer nesnelerin başlatılması ile etkileyebilir bir iç kilit alır. Bu dahili kilit henüz başlatılmamış ve böylece gerçekleşmesi kilitlenme uygulamanızda neden olabilir, başka bir altyapı nesne tarafından gerekli olabilir.  
  
 Aşağıdaki örnek, bir genel oluşturulmasını gösterir [concurrency::Scheduler](../../parallel/concrt/reference/scheduler-class.md) nesnesi. Bu model için değil yalnızca geçerli `Scheduler` sınıfı ancak eşzamanlılık çalışma zamanı tarafından sağlanan diğer tüm türleri. Uygulamanızda beklenmeyen davranışlara neden olabileceği için bu deseni izlemeyin öneririz.  
  
 [!code-cpp[concrt-global-scheduler#1](../../parallel/concrt/codesnippet/cpp/general-best-practices-in-the-concurrency-runtime_6.cpp)]  
  
 Doğru bir şekilde oluşturmak için örnekleri için `Scheduler` nesneleri bkz [Görev Zamanlayıcı](../../parallel/concrt/task-scheduler-concurrency-runtime.md).  
  
 [[Üst](#top)]  
  
##  <a name="shared-data"></a>Eşzamanlılık nesneleri paylaşılan veri Segmentlerinde kullanmayın  
 Eşzamanlılık Çalışma zamanı, paylaşılan veri bölümünde, örneğin, tarafından oluşturulan bir veri bölümü eşzamanlılık nesnelerinin kullanımını desteklemez [data_seg](../../preprocessor/data-seg.md) `#pragma` yönergesi. İşlem sınırları genelinde paylaşılan bir eşzamanlılık nesnesi tutarsız veya geçersiz bir durumda çalışma zamanı koyabilirsiniz.  
  
 [[Üst](#top)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Çalışma zamanı en iyi uygulamalar](../../parallel/concrt/concurrency-runtime-best-practices.md)   
 [Paralel Desen kitaplığı (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md)   
 [Zaman uyumsuz aracılar kitaplığı](../../parallel/concrt/asynchronous-agents-library.md)   
 [Görev Zamanlayıcısı](../../parallel/concrt/task-scheduler-concurrency-runtime.md)   
 [Eşitleme veri yapıları](../../parallel/concrt/synchronization-data-structures.md)   
 [Eşitleme veri yapılarını Windows API ile karşılaştırma](../../parallel/concrt/comparing-synchronization-data-structures-to-the-windows-api.md)   
 [Nasıl yapılır: ayırma kullanın ve boş bellek performansını artırmak](../../parallel/concrt/how-to-use-alloc-and-free-to-improve-memory-performance.md)   
 [Nasıl yapılır: gecikmeyi dengelemek için aşırı abonelik kullanma](../../parallel/concrt/how-to-use-oversubscription-to-offset-latency.md)   
 [Nasıl yapılır: bağlam sınıfını işbirlikçi semafor uygulamak için kullanın](../../parallel/concrt/how-to-use-the-context-class-to-implement-a-cooperative-semaphore.md)   
 [İzlenecek yol: Bir kullanıcı arabirimi iş parçacığından işi kaldırma](../../parallel/concrt/walkthrough-removing-work-from-a-user-interface-thread.md)   
 [Paralel desen Kitaplığı'ndaki en iyi yöntemler](../../parallel/concrt/best-practices-in-the-parallel-patterns-library.md)   
 [Zaman Uyumsuz Aracılar Kitaplığı'ndaki En İyi Yöntemler](../../parallel/concrt/best-practices-in-the-asynchronous-agents-library.md)
