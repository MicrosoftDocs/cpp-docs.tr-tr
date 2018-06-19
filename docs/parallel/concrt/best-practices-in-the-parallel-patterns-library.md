---
title: En iyi uygulamalar paralel desen Kitaplığı'ndaki | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Parallel Patterns Library, practices to avoid
- practices to avoid, Parallel Patterns Library
- best practices, Parallel Patterns Library
- Parallel Patterns Library, best practices
ms.assetid: e43e0304-4d54-4bd8-a3b3-b8673559a9d7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6ce3a4745b52c518484d14eafd483625eed2a0da
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33694569"
---
# <a name="best-practices-in-the-parallel-patterns-library"></a>Paralel Desen Kitaplığı'ndaki En İyi Yöntemler
Bu belgede etkili kullanımı paralel Desen kitaplığı (PPL) biri için en iyi şekilde nasıl açıklanmaktadır. PPL'de hassas paralellik gerçekleştirmek için genel amaçlı kapsayıcıları ve nesneleri algoritmaları sağlar.  
  
 PPL'de hakkında daha fazla bilgi için bkz: [paralel Desen kitaplığı (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md).  
  
##  <a name="top"></a> Bölümler  
 Bu belgede aşağıdaki bölümler yer alır:  
  
- [Küçük döngü gövdelerini paralel hale değil](#small-loops)  
  
- [Olası en yüksek düzeyde paralellik express](#highest)  
  
- [Bölme-ve-Yönet sorunları çözme için parallel_invoke kullanma](#divide-and-conquer)  
  
- [İptal ya da özel durum paralel bir döngüden kurtulmak için işleme kullanın](#breaking-loops)  
  
- [Anlamak iptali ve özel durum işleme etkilemesi nesne yok etme](#object-destruction)  
  
- [Art arda paralel bir döngüden engellemez](#repeated-blocking)  
  
- [Paralel iş iptal ettiğinizde işlemleri engelleyen gerçekleştirme](#blocking)  
  
- [Paralel bir döngüden paylaşılan veri yazma](#shared-writes)  
  
- [Mümkün olduğunda, yanlış paylaşımı kaçının](#false-sharing)  
  
- [Değişkenleri görev ömrü geçerli olduğundan emin olun](#lifetime)  
  
##  <a name="small-loops"></a> Küçük döngü gövdelerini paralel hale değil  
 Görece küçük döngü gövdelerini paralelleştirme ilişkili ek yükü paralel işleme ağır basıyor planlama neden olabilir. İki dizide öğelerinin her çifti ekler aşağıdaki örnekte, göz önünde bulundurun.  
  
 [!code-cpp[concrt-small-loops#1](../../parallel/concrt/codesnippet/cpp/best-practices-in-the-parallel-patterns-library_1.cpp)]  
  
 İş yükü her paralel döngü tekrarında için paralel işleme yükünü yararlı için çok küçük. Daha fazla iş döngü gövdesine gerçekleştirerek veya seri olarak döngü gerçekleştirerek Bu döngü performansını artırabilir.  
  
 [[Üst](#top)]  
  
##  <a name="highest"></a> Olası en yüksek düzeyde paralellik express  
 Yalnızca en düşük düzeyde kod paralel hale, işlemciler artar sayı olarak ölçeklenmez çatalı Birleştirme yapı ortaya çıkarabilir. A *çatalı birleştirme* yapıdır bir yapı burada bir görevi daha küçük paralel alt görevleri çalışmasını böler ve bu görevleri tamamlamak bekler. Her alt yinelemeli olarak bölme kendisini ek görevleri halinde kullanabilirsiniz.  
  
 Çatalı birleştirme modeli çeşitli sorunlarını çözmek için yararlı olsa da, eşitleme yükünü ölçeklenebilirlik burada düşürebilir durumlar vardır. Örneğin, görüntü verilerini işler aşağıdaki seri kodu göz önünde bulundurun.  
  
 [!code-cpp[concrt-image-processing-filter#20](../../parallel/concrt/codesnippet/cpp/best-practices-in-the-parallel-patterns-library_2.cpp)]  
  
 Her döngü tekrarında bağımsız olduğundan, büyük bir iş, aşağıdaki örnekte gösterildiği gibi paralel hale. Bu örnekte [concurrency::parallel_for](reference/concurrency-namespace-functions.md#parallel_for) dış döngü paralel hale algoritması.  

  
 [!code-cpp[concrt-image-processing-filter#3](../../parallel/concrt/codesnippet/cpp/best-practices-in-the-parallel-patterns-library_3.cpp)]  
  
 Aşağıdaki örnekte, çağırarak çatalı Birleştirme yapı gösterilmektedir `ProcessImage` döngü işlevi. Her çağrı `ProcessImage` her alt tamamlanana kadar döndürmüyor.  
  
 [!code-cpp[concrt-image-processing-filter#21](../../parallel/concrt/codesnippet/cpp/best-practices-in-the-parallel-patterns-library_4.cpp)]  
  
 Her döngü ya da gerçekleştirir neredeyse hiçbir iş ya da paralel döngü tarafından gerçekleştirilen iş paralel yani imbalanced, ise, bazı döngüsü yinelemeleri diğerlerinden daha uzun sürer, sık çatallaştırma için ek yükü zamanlaması gereklidir ve birleştirme iş olabilir Paralel yürütme için avantajı daha ağır basar. Bu yükünü işlemciler artar sayısı artar.  
  
 Bu örnekte yükünü zamanlama miktarını azaltmak için iç döngüler paralel hale veya ardışık düzen oluşturma gibi başka bir paralel yapı kullanmadan önce dış döngüler paralel hale. Aşağıdaki örnek değiştirir `ProcessImages` kullanmak için işlevi [concurrency::parallel_for_each](reference/concurrency-namespace-functions.md#parallel_for_each) dış döngü paralel hale algoritması.  

  
 [!code-cpp[concrt-image-processing-filter#22](../../parallel/concrt/codesnippet/cpp/best-practices-in-the-parallel-patterns-library_5.cpp)]  
  
 Görüntü işleme paralel olarak gerçekleştirmek için bir işlem hattı kullanan benzer bir örnek için bkz: [izlenecek yol: görüntü işleme ağı oluşturma](../../parallel/concrt/walkthrough-creating-an-image-processing-network.md).  
  
 [[Üst](#top)]  
  
##  <a name="divide-and-conquer"></a> Bölme-ve-Yönet sorunları çözme için parallel_invoke kullanma  

 A *bölme-ve-Yönet* form özyineleme bir görevi alt görevlere ayırmak için kullanır çatalı birleştirme yapının bir sorundur. Ek olarak [concurrency::task_group](reference/task-group-class.md) ve [concurrency::structured_task_group](../../parallel/concrt/reference/structured-task-group-class.md) sınıfları ayrıca kullanabileceğiniz [concurrency::parallel_invoke](reference/concurrency-namespace-functions.md#parallel_invoke) algoritmasına bölme-ve-Yönet sorunları çözün. `parallel_invoke` Algoritması görev Grup nesneleri değerinden daha kısa sözdizimine sahip ve Paralel Görevler sabit sayıda olduğunda faydalıdır.  
  
 Aşağıdaki örnek kullanımını göstermektedir `parallel_invoke` algoritması sıralama bitonic uygulamak için algoritması.  
  
 [!code-cpp[concrt-parallel-bitonic-sort#12](../../parallel/concrt/codesnippet/cpp/best-practices-in-the-parallel-patterns-library_6.cpp)]  
  
 Yükü, azaltmak için `parallel_invoke` algoritması arama bağlamda görev dizisini son gerçekleştirir.  
  
 Bu örneğin tam sürümü için bkz: [nasıl yapılır: paralel sıralama rutini yazmak için parallel_invoke kullanma](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md). Hakkında daha fazla bilgi için `parallel_invoke` algoritması bkz [paralel algoritmalar](../../parallel/concrt/parallel-algorithms.md).  
  
 [[Üst](#top)]  
  
##  <a name="breaking-loops"></a> İptal ya da özel durum paralel bir döngüden kurtulmak için işleme kullanın  
 PPL'de bir görev grubu veya paralel algoritması tarafından gerçekleştirilen paralel iş iptal etmek için iki yöntem sağlar. Tek yönlü tarafından sağlanan iptal mekanizması kullanmaktır [concurrency::task_group](reference/task-group-class.md) ve [concurrency::structured_task_group](../../parallel/concrt/reference/structured-task-group-class.md) sınıfları. Başka bir görev iş işlev gövdesine bir özel durum yoludur. Özel durum işleme paralel iş ağacının iptal etme sırasında daha etkili iptal mekanizmadır. A *paralel iş ağaç* bazı görev grupları diğer görev grupları içeren ilgili görev grupları oluşan bir gruptur. İptal mekanizması görev grubunu ve onun alt görev grupları yukarıdan aşağıya doğru bir biçimde iptal eder. Buna karşılık, özel durum işleme aşağıdan yukarıya biçimde çalışır ve özel durum yukarı yayar gibi her alt görev grubu bağımsız olarak iptal etmeniz gerekir.  
  

 Doğrudan bir görev grup nesnesi ile çalışırken kullanmaya [concurrency::task_group::cancel](reference/task-group-class.md#cancel) veya [concurrency::structured_task_group::cancel](reference/structured-task-group-class.md#cancel) o görev grubuna ait iş iptal etmek için yöntemleri . Bir paralel algoritması, örneğin, iptal etmek için `parallel_for`, üst görev grubu oluşturun ve o görev grubu iptal edin. Örneğin, aşağıdaki işlev göz önünde bulundurun `parallel_find_any`, paralel bir dizi değeri arar.  


  
 [!code-cpp[concrt-parallel-array-search#2](../../parallel/concrt/codesnippet/cpp/best-practices-in-the-parallel-patterns-library_7.cpp)]  
  
 Paralel yineleme birini üst görev grubu iptal ettiğinde paralel algoritmalar görev grupları kullandığından, genel görev iptal edildi. Bu örneğin tam sürümü için bkz: [nasıl yapılır: paralel bir döngüden gelen sonu için kullanım iptal](../../parallel/concrt/how-to-use-cancellation-to-break-from-a-parallel-loop.md).  
  
 Özel durum işleme iptal mekanizması daha paralel iş iptal etmek için daha az verimli bir şekilde olsa da, özel durum işleme uygun olduğu durumlar vardır. Örneğin, aşağıdaki yöntemi `for_all`, yinelemeli olarak her düğümde bir iş işlevi gerçekleştiren bir `tree` yapısı. Bu örnekte, `_children` veri üyesi olan bir [std::list](../../standard-library/list-class.md) içeren `tree` nesneleri.  
  
 [!code-cpp[concrt-task-tree-search#6](../../parallel/concrt/codesnippet/cpp/best-practices-in-the-parallel-patterns-library_8.cpp)]  
  
 Çağıranın `tree::for_all` ağaç her öğesinin çağrılmasına iş işlevi gerektirmiyorsa, yöntemi bir özel durum throw. Aşağıdaki örnekte gösterildiği `search_for_value` sağlanan değer arar işlevi `tree` nesnesi. `search_for_value` İşlevi geçerli öğe ağacının sağlanan değer eşleştiğinde aykırı bir iş işlevi kullanır. `search_for_value` İşlev kullanan bir `try-catch` blok özel durum yakalama ve sonucu konsola yazdırır.  
  
 [!code-cpp[concrt-task-tree-search#3](../../parallel/concrt/codesnippet/cpp/best-practices-in-the-parallel-patterns-library_9.cpp)]  
  
 Bu örneğin tam sürümü için bkz: [nasıl yapılır: kullanım özel durum işleme sona paralel bir döngüden gelen](../../parallel/concrt/how-to-use-exception-handling-to-break-from-a-parallel-loop.md).  
  
 İptal etme ve PPL tarafından sağlanan özel durum işleme mekanizmaları hakkında daha fazla genel bilgi için bkz: [PPL'de iptal](cancellation-in-the-ppl.md) ve [özel durum işleme](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md).  
  
 [[Üst](#top)]  
  
##  <a name="object-destruction"></a> Anlamak iptali ve özel durum işleme etkilemesi nesne yok etme  
 Paralel iş ağacında iptal bir görev alt görevler çalışmasını engeller. Alt görevler birini uygulamanıza bir kaynak boşaltma gibi önemli bir işlem gerçekleştirdiğinde bu sorunlara neden olabilir. Buna ek olarak, görev iptali bir nesne yıkıcı yaymak ve uygulamanızda tanımsız davranışlara neden için bir özel duruma neden olabilir.  
  
 Aşağıdaki örnekte, `Resource` sınıfı bir kaynak açıklar ve `Container` sınıf kaynakları tutan bir kapsayıcı tanımlar. Kendi yıkıcı içinde `Container` sınıfı çağrıları `cleanup` üzerinde ikisinden yöntemi kendi `Resource` üyeleri paralel ve çağrıları `cleanup` yöntemi, üçüncü `Resource` üyesi.  
  
 [!code-cpp[concrt-parallel-resource-destruction#1](../../parallel/concrt/codesnippet/cpp/best-practices-in-the-parallel-patterns-library_10.h)]  
  
 Bu desen herhangi bir sorun kendi kendine olsa da, iki görevi paralel olarak çalışan aşağıdaki kod göz önünde bulundurun. İlk görev oluşturur bir `Container` nesne ve ikinci görev genel görev iptal eder. Çizim için bu örnek iki kullanır [concurrency::event](../../parallel/concrt/reference/event-class.md) iptal sonra gerçekleşir emin olmak için nesneleri `Container` nesnesi oluşturulur ve `Container` nesne iptal işleminden sonra yok işlemi gerçekleşir.  
  
 [!code-cpp[concrt-parallel-resource-destruction#2](../../parallel/concrt/codesnippet/cpp/best-practices-in-the-parallel-patterns-library_11.cpp)]  
  
 Bu örnek şu çıkışı üretir:  
  
```Output  
Container 1: Freeing resources...Exiting program...  
```  
  
 Bu kod örneği, beklenenden farklı davranır neden aşağıdaki sorunları içerir:  
  
-   Çağrısı alt görevin üst görev iptali neden [concurrency::parallel_invoke](reference/concurrency-namespace-functions.md#parallel_invoke), aynı zamanda iptal edilecek. Bu nedenle, bu iki kaynakları serbest bırakılmaz.  

  
-   Üst görev iptali bir iç özel durum alt görev neden olur. Çünkü `Container` yıkıcı bu özel durumun işlemiyor, özel durum yukarı yayılır ve üçüncü kaynak serbest.  
  
-   Alt görevi tarafından oluşturulan özel durum aracılığıyla yayar `Container` yıkıcı. Bir yıkıcı atma uygulama tanımlanmamış bir durumda koyar.  
  
 Bu görevleri iptal garanti edemediği sürece görevler kaynakları serbest bırakma gibi kritik işlemler gerçekleştirmeyin öneririz. Ayrıca türlerinizi yıkıcı atabilirsiniz çalışma zamanı işlevselliği kullanmamanızı öneririz.  
  
 [[Üst](#top)]  
  
##  <a name="repeated-blocking"></a> Art arda paralel bir döngüden engellemez  

 Gibi paralel bir döngüden [concurrency::parallel_for](reference/concurrency-namespace-functions.md#parallel_for) veya [concurrency::parallel_for_each](reference/concurrency-namespace-functions.md#parallel_for_each) engelleyerek hâkim işlemleri çalışma zamanının kısa bir süre içinde birçok iş parçacığı oluşturma neden olabilir.  

  
 Bir görev tamamlandıktan işlevinizde engeller veya verir eşzamanlılık çalışma zamanı ek çalışma gerçekleştirir. Bir paralel döngü, yineleme blokları çalışma zamanı başka bir yineleme başlayabilir. Kullanılabilir boş iş parçacığı olduğunda, çalışma zamanı yeni bir iş parçacığı oluşturur.  
  
 Paralel gövdesi döngü, bazen blokları bu düzenek genel görev üretilen işi en üst düzeye çıkarmanıza yardımcı olur. Ancak, çok sayıda yineleme engellerseniz, çalışma zamanı ek bir iş çalıştırmak için çok sayıda iş parçacığı oluşturabilir. Bu, düşük bellek koşulları veya donanım kaynakları zayıf kullanımı için neden olabilir.  
  
 Çağıran aşağıdaki örneği göz önünde bulundurun [concurrency::send](reference/concurrency-namespace-functions.md#send) her yinelemesinden işlevinde bir `parallel_for` döngü. Çünkü `send` işlevinizde, engeller çalışma zamanı ek iş her zaman çalıştırmak için yeni bir iş parçacığı oluşturur `send` olarak adlandırılır.  
  
 [!code-cpp[concrt-repeated-blocking#1](../../parallel/concrt/codesnippet/cpp/best-practices-in-the-parallel-patterns-library_12.cpp)]  
  
 Bu desen önlemek için kodunuzu yeniden düzenlemeniz öneririz. Bu örnekte, çağırarak ek iş parçacığı oluşturma önleyebilirsiniz `send` bir seri içinde `for` döngü.  
  
 [[Üst](#top)]  
  
##  <a name="blocking"></a> Paralel iş iptal ettiğinizde işlemleri engelleyen gerçekleştirme  

 Çağırmadan önce mümkün olduğunda engelleme işlemleri gerçekleştirmeyin [concurrency::task_group::cancel](reference/task-group-class.md#cancel) veya [concurrency::structured_task_group::cancel](reference/structured-task-group-class.md#cancel) paralel iş iptal etmek için yöntem.  


  
 Bir görev işlemi engelleyen bir işbirlikçi gerçekleştirdiğinde, ilk görevi için verileri beklerken çalışma zamanı diğer iş gerçekleştirebilirsiniz. Bunu engelini kaldırır, çalışma zamanı bekleme görev reschedules. Çalışma zamanı genellikle daha az engeli görevleri reschedules önce daha yakın zamanda engeli görevler reschedules. Bu nedenle, çalışma zamanı performansın için müşteri adayları engelleme işlemi sırasında gereksiz iş zamanlaması yapılamıyor. Buna göre paralel iş iptal etmeden önce engelleyici bir işlem gerçekleştirdiğinizde, engelleme işlemi çağrısı geciktirebilir `cancel`. Bu, gereksiz işlemleri gerçekleştirmesi diğer görevleri neden olur.  
  
 Tanımlar aşağıdaki örneği göz önünde bulundurun `parallel_find_answer` sağlanan koşul işlevini karşılayan sağlanan dizi bir öğe için arama işlevi. Koşul işlevi döndüğünde `true`, paralel iş işlev oluşturur bir `Answer` nesne ve genel görev iptal eder.  
  
 [!code-cpp[concrt-blocking-cancel#1](../../parallel/concrt/codesnippet/cpp/best-practices-in-the-parallel-patterns-library_13.cpp)]  
  


 `new` İşleci engelleyebilecek bir yığın ayırma gerçekleştirir. Görev çağrısı gibi çağrısı engelleme bir işbirlikçi gerçekleştirdiğinde çalışma zamanı diğer çalışma gerçekleştirir [concurrency::critical_section::lock](reference/critical-section-class.md#lock).  


  
 Aşağıdaki örnek, gereksiz iş önlemek ve böylece performansı gösterilmektedir. Bu örnek için depolama ayırır önce görev grubu iptal `Answer` nesnesi.  
  
 [!code-cpp[concrt-blocking-cancel#2](../../parallel/concrt/codesnippet/cpp/best-practices-in-the-parallel-patterns-library_14.cpp)]  
  
 [[Üst](#top)]  
  
##  <a name="shared-writes"></a> Paralel bir döngüden paylaşılan veri yazma  
 Eşzamanlılık Çalışma zamanı birkaç veri yapılarını, örneğin sağlar [concurrency::critical_section](../../parallel/concrt/reference/critical-section-class.md), paylaşılan veri eş zamanlı erişim eşitleyin. Birden çok görev seyrek paylaşılan bir kaynağa erişim gerektirdiğinde çoğu durumda, örneğin, bu veri yapıları faydalıdır.  
  
 Kullanan aşağıdaki örneği göz önünde bulundurun [concurrency::parallel_for_each](reference/concurrency-namespace-functions.md#parallel_for_each) algoritması ve `critical_section` asal sayılar sayısı işlem için nesne bir [std::array](../../standard-library/array-class-stl.md) nesnesi. Her iş parçacığı paylaşılan değişken erişmek için beklemeniz gerekir çünkü bu örnek ölçeklenmez `prime_sum`.  

  
 [!code-cpp[concrt-parallel-sum-of-primes#2](../../parallel/concrt/codesnippet/cpp/best-practices-in-the-parallel-patterns-library_15.cpp)]  
  
 Sık kilitleme işlemi etkili bir şekilde döngü serileştiren olduğundan bu örnek ayrıca düşük performans yol açabilir. Ayrıca, bir eşzamanlılık çalışma zamanı nesne engelleme işlemi gerçekleştirdiğinde, Zamanlayıcı ilk iş parçacığı için verileri beklerken diğer işlemleri gerçekleştirmesi için ek bir iş parçacığı oluşturabilir. Pek çok görev için paylaşılan veri bekleyen çünkü çalışma zamanı birçok iş parçacığı oluşturursa, uygulama kötü gerçekleştirmek veya düşük kaynak durumu girin.  
  
 PPL'de tanımlar [concurrency::combinable](../../parallel/concrt/reference/combinable-class.md) , paylaşılan durum bir kilidi serbest şekilde paylaşılan kaynaklara erişim sağlayarak ortadan kaldırmanıza yardımcı sınıfı. `combinable` Sınıfı hassas hesaplamalar ve ardından bu hesaplamaların nihai sonucu birleştirme sağlayan iş parçacığı yerel depolama sağlar. Düşünebilirsiniz bir `combinable` nesnesi azaltma değişkeni olarak.  
  
 Aşağıdaki örnek kullanarak öncekinin değiştirir bir `combinable` yerine Nesne bir `critical_section` toplam işlem nesnesi. Her iş parçacığı toplamı kendi yerel kopyasını tutar olduğundan bu örnek ölçeklendirir. Bu örnekte [concurrency::combinable::combine](reference/combinable-class.md#combine) yerel hesaplamalar nihai sonucu birleştirmek için yöntem.  

  
 [!code-cpp[concrt-parallel-sum-of-primes#3](../../parallel/concrt/codesnippet/cpp/best-practices-in-the-parallel-patterns-library_16.cpp)]  
  
 Bu örneğin tam sürümü için bkz: [nasıl yapılır: performansı arttırmak için combinable kullanma](../../parallel/concrt/how-to-use-combinable-to-improve-performance.md). Hakkında daha fazla bilgi için `combinable` sınıfı için bkz: [paralel kapsayıcılar ve nesneler](../../parallel/concrt/parallel-containers-and-objects.md).  
  
 [[Üst](#top)]  
  
##  <a name="false-sharing"></a> Mümkün olduğunda, yanlış paylaşımı kaçının  
 *False paylaşımı* ayrı işlemcilerde çalıştıran birden çok eş zamanlı görevleri bulunan değişkenlere aynı önbellek satırında yazma oluşur. Bir görev değişkenlerinden biri yazdığında, her iki değişken için önbellek satırı geçersiz kılınır. Her işlemci önbellek satırı önbellek satırı geçersiz kılınan her zaman yeniden yüklemeniz gerekir. Bu nedenle, yanlış paylaşımı performansın uygulamanızda neden olabilir.  
  
 Her bir paylaşılan sayaç değişkeni Artır aşağıdaki temel örnek iki eş zamanlı görevleri gösterir.  
  
 [!code-cpp[concrt-false-sharing#1](../../parallel/concrt/codesnippet/cpp/best-practices-in-the-parallel-patterns-library_17.cpp)]  
  
 İki görev arasında veri paylaşımı ortadan kaldırmak için iki sayaç değişkenleri kullanma örneği değiştirebilirsiniz. Görevleri tamamladıktan sonra bu örnek son sayaç değeri hesaplar. Ancak, bu örnek için false paylaşımı gösterir değişkenleri `count1` ve `count2` aynı önbellek satırında bulunması olasıdır.  
  
 [!code-cpp[concrt-false-sharing#2](../../parallel/concrt/codesnippet/cpp/best-practices-in-the-parallel-patterns-library_18.cpp)]  
  
 False paylaşımı ortadan kaldırmak için bir sayaç değişkenlerin ayrı önbelleği satırlarında olduğundan emin olmak için yoludur. Aşağıdaki örnek değişkenleri hizalar `count1` ve `count2` 64 baytlık sınırlarda.  
  
 [!code-cpp[concrt-false-sharing#3](../../parallel/concrt/codesnippet/cpp/best-practices-in-the-parallel-patterns-library_19.cpp)]  
  
 Bu örnek, önbellek boyutu 64 veya daha az bayt olduğunu varsayar.  
  
 Kullanmanızı öneririz [concurrency::combinable](../../parallel/concrt/reference/combinable-class.md) sınıf görevler arasında veri paylaştığınızda gerekir. `combinable` Sınıfı iş parçacığı yerel değişkenleri false paylaşımı olasılığını olduğunu yolu oluşturur. Hakkında daha fazla bilgi için `combinable` sınıfı için bkz: [paralel kapsayıcılar ve nesneler](../../parallel/concrt/parallel-containers-and-objects.md).  
  
 [[Üst](#top)]  
  
##  <a name="lifetime"></a> Değişkenleri görev ömrü geçerli olduğundan emin olun  
 Lambda ifadesi bir görev grubu veya paralel algoritması sağladığınızda, yakalama yan tümcesi lambda ifadesi gövdesi çevreleyen kapsamdaki değişkenler değere veya başvuruya göre erişen olup olmadığını belirler. Başvuruya göre bir lambda ifadesi değişkenleri geçirdiğinizde, görevi tamamlanana kadar bu değişken ömrü devam güvence altına almalıdır.  
  
 Tanımlar aşağıdaki örneği göz önünde bulundurun `object` sınıfı ve `perform_action` işlevi. `perform_action` İşlev oluşturur bir `object` değişken ve bu değişken üzerindeki zaman uyumsuz olarak bazı eylemleri gerçekleştirir. Görev önce tamamlamak için kesin değildir çünkü `perform_action` işlevi döndürür, program kilitleniyor veya belirtilmeyen varsa davranışlar `object` görev çalıştığında değişkeni yok.  
  
 [!code-cpp[concrt-lambda-lifetime#1](../../parallel/concrt/codesnippet/cpp/best-practices-in-the-parallel-patterns-library_20.cpp)]  
  
 Uygulamanızın gereksinimlerine bağlı olarak, aşağıdaki yöntemlerden birini değişkenleri her görev ömrü geçerli kalmasını sağlamak için kullanabilirsiniz.  
  
 Aşağıdaki örnek geçirir `object` görev değerine göre değişken. Bu nedenle, görevin değişkeni kendi kopyası üzerinde çalışır.  
  
 [!code-cpp[concrt-lambda-lifetime#2](../../parallel/concrt/codesnippet/cpp/best-practices-in-the-parallel-patterns-library_21.cpp)]  
  
 Çünkü `object` değişken değeri tarafından geçirilen, bu değişkenin gerçekleşen durumu değişiklikleri özgün kopya görünmez.  
  
 Aşağıdaki örnek kullanır [concurrency::task_group::wait](reference/task-group-class.md#wait) görev önce tamamladığından emin olmak için yöntem `perform_action` işlev döndürür.  


  
 [!code-cpp[concrt-lambda-lifetime#3](../../parallel/concrt/codesnippet/cpp/best-practices-in-the-parallel-patterns-library_22.cpp)]  
  
 İşlev döndürmeden önce görev şimdi tamamlandığında olduğundan, `perform_action` işlevi artık davranır zaman uyumsuz olarak.  
  
 Aşağıdaki örnek değiştirir `perform_action` başvuru yapılacak işlevi `object` değişkeni. Çağıran, yaşam süresi güvence altına almalıdır `object` değişken, görev bitene kadar geçerlidir.  
  
 [!code-cpp[concrt-lambda-lifetime#4](../../parallel/concrt/codesnippet/cpp/best-practices-in-the-parallel-patterns-library_23.cpp)]  
  
 Bir görev grubu veya paralel algoritması geçirdiğiniz bir nesne ömrü denetlemek için bir işaretçi de kullanabilirsiniz.  
  
 Lambda ifadeleri hakkında daha fazla bilgi için bkz: [Lambda ifadeleri](../../cpp/lambda-expressions-in-cpp.md).  
  
 [[Üst](#top)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Çalışma zamanı en iyi uygulamalar](../../parallel/concrt/concurrency-runtime-best-practices.md)   
 [Paralel Desen kitaplığı (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md)   
 [Paralel kapsayıcılar ve nesneler](../../parallel/concrt/parallel-containers-and-objects.md)   
 [Paralel algoritmalar](../../parallel/concrt/parallel-algorithms.md)   
 [PPL'de iptal](cancellation-in-the-ppl.md)   
 [Özel durum işleme](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)   
 [İzlenecek yol: bir görüntü işleme ağı oluşturma](../../parallel/concrt/walkthrough-creating-an-image-processing-network.md)   
 [Nasıl yapılır: paralel sıralama rutini yazmak için parallel_invoke kullanma](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md)   
 [Nasıl yapılır: paralel bir döngüden kurtulmak için İptal kullanın](../../parallel/concrt/how-to-use-cancellation-to-break-from-a-parallel-loop.md)   
 [Nasıl yapılır: performansı arttırmak için combinable kullanma](../../parallel/concrt/how-to-use-combinable-to-improve-performance.md)   
 [Zaman uyumsuz aracılar Kitaplığı'ndaki en iyi yöntemler](../../parallel/concrt/best-practices-in-the-asynchronous-agents-library.md)   
 [Eşzamanlılık Çalışma Zamanındaki Genel En İyi Yöntemler](../../parallel/concrt/general-best-practices-in-the-concurrency-runtime.md)

