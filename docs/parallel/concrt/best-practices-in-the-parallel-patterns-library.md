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
ms.openlocfilehash: 28bedc703a8fa965b5380cb8c7eba840d07f7772
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46396941"
---
# <a name="best-practices-in-the-parallel-patterns-library"></a>Paralel Desen Kitaplığı'ndaki En İyi Yöntemler

Bu belgede, paralel Desen kitaplığı (PPL) ın etkili kullanımı için en iyi şekilde nasıl açıklanmaktadır. PPL, hassas paralellik gerçekleştirmek için genel amaçlı kapsayıcıları ve nesneleri algoritmalar sağlar.

PPL hakkında daha fazla bilgi için bkz: [paralel desenler kitaplığı (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md).

##  <a name="top"></a> Bölümleri

Bu belgede aşağıdaki bölümler yer alır:

- [Küçük döngü gövdelerini Paralelleştirme](#small-loops)

- [Olası en yüksek düzeyde paralellik express](#highest)

- [Çözüm bölün-and-Conquer sorunlarını için parallel_invoke kullanma](#divide-and-conquer)

- [İptal veya özel durum paralel bir döngüden kurtulmak için işlemeyi kullanın](#breaking-loops)

- [Anlamak iptal ve özel durum işleme etkilemesi nesne yok etme](#object-destruction)

- [Sürekli olarak paralel bir döngüde engelleme](#repeated-blocking)

- [Paralel işi iptal ettiğinizde engelleme işlemleri yapma](#blocking)

- [Bir paralel döngüde Paylaşılan verilere yazma](#shared-writes)

- [Mümkün olduğunda, yanlış paylaşıma açmaktan Kaçın](#false-sharing)

- [Değişkenler bir görevin süresi geçerli olduğundan emin olun](#lifetime)

##  <a name="small-loops"></a> Küçük döngü gövdelerini Paralelleştirme

Nispeten küçük döngü gövdelerini paralelleştirme, ilişkili ek yükü ağır basıyor paralel işleme için zamanlama neden olabilir. İki dizide her bir öğe çiftinin ekler aşağıdaki örneği inceleyin.

[!code-cpp[concrt-small-loops#1](../../parallel/concrt/codesnippet/cpp/best-practices-in-the-parallel-patterns-library_1.cpp)]

Paralel işleme yükü yararlanmasını küçük her paralel döngü yinelemesi için yüküdür. Daha fazla iş döngü gövdesinde gerçekleştirerek veya seri olarak döngü gerçekleştirerek Bu döngü performansını artırabilir.

[[Üst](#top)]

##  <a name="highest"></a> Olası en yüksek düzeyde paralellik express

Yalnızca en düşük düzeyde kod paralel hale getirmek, sayısı arttıkça işlemci ölçeklenmez bir Çatal birleştirme yapısı ortaya çıkarabilir. A *çatal birleştirme* yapıdır bir yapısı bir görev burada işini daha küçük paralel alt görevlere böler ve bu görevleri tamamlamak bekler. Her bir alt yinelemeli olarak Böl kendisini ek görevleri halinde kullanabilirsiniz.

Çatal katılım modeli çeşitli sorunları çözmek için yararlı olabilir, ancak burada eşitleme ek yükü ölçeklenebilirliği düşürebilir durumlar vardır. Örneğin, görüntü verilerini işleyen aşağıdaki seri kodu göz önünde bulundurun.

[!code-cpp[concrt-image-processing-filter#20](../../parallel/concrt/codesnippet/cpp/best-practices-in-the-parallel-patterns-library_2.cpp)]

Her döngü yinelemesinin bağımsız olduğundan, aşağıdaki örnekte gösterildiği gibi işin çoğunu getirebilen. Bu örnekte [concurrency::parallel_for](reference/concurrency-namespace-functions.md#parallel_for) dış döngü paralel hale getirmek için kullanılan algoritma.

[!code-cpp[concrt-image-processing-filter#3](../../parallel/concrt/codesnippet/cpp/best-practices-in-the-parallel-patterns-library_3.cpp)]

Aşağıdaki örnekte, çağırarak bir Çatal birleştirme yapısı gösterilmektedir `ProcessImage` döngü içinde işlevi. Her çağrı `ProcessImage` her alt görevi bitene kadar döndürmez.

[!code-cpp[concrt-image-processing-filter#21](../../parallel/concrt/codesnippet/cpp/best-practices-in-the-parallel-patterns-library_4.cpp)]

Neredeyse hiçbir iş ya da paralel bir döngüden tarafından gerçekleştirilen iş ya da gerçekleştirir paralel döngünün her yinelemesinden imbalanced, ise, yani bazı döngü yinelemesi diğerlerine göre daha uzun sürer, yükü zamanlaması sık çatalını oluşturmanız için gerekli ve kullanılabilir birleştirme Paralel yürütme için avantajından daha fazla. Bu ek sayısı arttıkça işlemci artırır.

Bu örnekte yükü zamanlama miktarını azaltmak için iç döngü paralel hale getirmek veya ardışık düzen oluşturma gibi başka bir paralel yapı kullanmak için önce dış döngü paralel hale getirebilirsiniz. Aşağıdaki örnek `ProcessImages` kullanılacak işlevi [concurrency::parallel_for_each](reference/concurrency-namespace-functions.md#parallel_for_each) dış döngü paralel hale getirmek için kullanılan algoritma.

[!code-cpp[concrt-image-processing-filter#22](../../parallel/concrt/codesnippet/cpp/best-practices-in-the-parallel-patterns-library_5.cpp)]

Paralel olarak görüntü işleme gerçekleştirmek için bir işlem hattı kullanan benzer bir örnek için bkz. [izlenecek yol: görüntü işleme ağı oluşturma](../../parallel/concrt/walkthrough-creating-an-image-processing-network.md).

[[Üst](#top)]

##  <a name="divide-and-conquer"></a> Çözüm bölün-and-Conquer sorunlarını için parallel_invoke kullanma

A *bölün-and-conquer* bir forma bir görevi alt görevlere bölmek için özyineleme kullanır çatal birleştirme yapının bir sorundur. Ek olarak [concurrency::task_group](reference/task-group-class.md) ve [concurrency::structured_task_group](../../parallel/concrt/reference/structured-task-group-class.md) sınıfları, ayrıca kullanabileceğiniz [concurrency::parallel_invoke](reference/concurrency-namespace-functions.md#parallel_invoke) algoritmaya bölme-and-conquer sorunlarını çözün. `parallel_invoke` Algoritması daha kısa sözdizimleri görev grubu nesnelerden sahiptir ve sabit sayıda Paralel Görevler olduğunda yararlıdır.

Aşağıdaki örnek, kullanımını gösterir `parallel_invoke` bitonic sıralama algoritmasını uygulamak için kullanılan algoritma.

[!code-cpp[concrt-parallel-bitonic-sort#12](../../parallel/concrt/codesnippet/cpp/best-practices-in-the-parallel-patterns-library_6.cpp)]

Ek yükü, azaltmak için `parallel_invoke` algoritması, görev dizisini son arama bağlamda gerçekleştirir.

Bu örneğin tam sürümü için bkz: [nasıl yapılır: paralel sıralama rutini yazmak için parallel_invoke kullanma](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md). Hakkında daha fazla bilgi için `parallel_invoke` algoritmasını bkz [paralel algoritmalar](../../parallel/concrt/parallel-algorithms.md).

[[Üst](#top)]

##  <a name="breaking-loops"></a> İptal veya özel durum paralel bir döngüden kurtulmak için işlemeyi kullanın

PPL görev grubu veya paralel algoritma tarafından gerçekleştirilen paralel işi iptal etmek için iki yol sunar. Tek yönlü tarafından sağlanan iptal mekanizması kullanmaktır [concurrency::task_group](reference/task-group-class.md) ve [concurrency::structured_task_group](../../parallel/concrt/reference/structured-task-group-class.md) sınıfları. Bir görev iş işlevin gövdesinde bir özel durum oluşturmak için diğer yol ise. İptal mekanizması, özel durum işleme bir paralel iş ağacında iptal etme sırasında daha verimlidir. A *paralel iş ağacında* bazı görev grupları diğer görev gruplarını içeren ilgili görev gruplarını grubudur. İptal mekanizması görev grubu ve alt görev gruplarına yukarıdan aşağıya doğru bir şekilde iptal eder. Buna karşılık, özel durum işleme bir aşağıdan yukarıya şekilde çalışır ve özel durum yukarı yayar gibi her bir alt görev grubu bağımsız olarak iptal etmeniz gerekir.

Doğrudan bir görev grubu nesnesi ile çalışırken kullanmak [concurrency::task_group::cancel](reference/task-group-class.md#cancel) veya [CONCURRENCY::structured_task_group:: Cancel](reference/structured-task-group-class.md#cancel) bu görev grubuna ait işi iptal etmek için yöntemleri . Paralel algoritma, örneğin, iptal etmek için `parallel_for`, üst görev grubu oluşturun ve bu görev grubunu iptal edin. Örneğin, aşağıdaki işlev düşünün `parallel_find_any`, paralel bir dizi değeri arar.

[!code-cpp[concrt-parallel-array-search#2](../../parallel/concrt/codesnippet/cpp/best-practices-in-the-parallel-patterns-library_7.cpp)]

Paralel yineleme bir üst görev grubunu iptal ettiğinde, görev grupları, paralel algoritmalar kullanmak için genel görev iptal edildi. Bu örneğin tam sürümü için bkz: [nasıl yapılır: paralel bir döngüden sona kullanım İptalden](../../parallel/concrt/how-to-use-cancellation-to-break-from-a-parallel-loop.md).

Özel durum işleme iptal mekanizması daha paralel işi iptal etmek için daha az verimli bir şekilde olsa da, özel durum işleme uygun olduğu durumlar vardır. Örneğin, aşağıdaki yöntemi `for_all`, yinelemeli olarak gerçekleştiren iş işlevi her düğümde bir `tree` yapısı. Bu örnekte, `_children` veri üyesi olan bir [std::list](../../standard-library/list-class.md) içeren `tree` nesneleri.

[!code-cpp[concrt-task-tree-search#6](../../parallel/concrt/codesnippet/cpp/best-practices-in-the-parallel-patterns-library_8.cpp)]

Çağıran `tree::for_all` ağacında her bir öğede çağrılabilir iş işlevi gerektirmiyorsa, yöntemi bir özel durum throw. Aşağıdaki örnekte gösterildiği `search_for_value` belirtilen bir değeri arar işlevi `tree` nesne. `search_for_value` İşlevi, belirtilen değer geçerli öğe ağacı eşleştiğinde, bir özel durum oluşturan bir iş işlevini kullanır. `search_for_value` İşlevini kullanan bir `try-catch` bloğu özel durumu yakalayıp sonucu konsola yazdırır.

[!code-cpp[concrt-task-tree-search#3](../../parallel/concrt/codesnippet/cpp/best-practices-in-the-parallel-patterns-library_9.cpp)]

Bu örneğin tam sürümü için bkz: [nasıl yapılır: kullanım özel durum işleme sonu için paralel bir döngüden gelen](../../parallel/concrt/how-to-use-exception-handling-to-break-from-a-parallel-loop.md).

Ppl Yapıları tarafından sağlanan özel durum işleme mekanizmasını ve iptal etme hakkında daha fazla genel bilgi için bkz: [ppl'de iptal](cancellation-in-the-ppl.md) ve [özel durum işleme](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md).

[[Üst](#top)]

##  <a name="object-destruction"></a> Anlamak iptal ve özel durum işleme etkilemesi nesne yok etme

Paralel iş ağacında iptal edilen bir görev alt görevlerin çalışmasını önleyebilir. Alt görevlerden birini önemli bir kaynağı serbest bırakmak, uygulamanıza bir işlem yaparsa bu sorunlara neden olabilir. Ayrıca, görev iptali bir özel bir nesne yokedici yoluyla yayılabilir ve uygulamada tanımsız davranışlara neden neden olabilir.

Aşağıdaki örnekte, `Resource` açıklar bir kaynak sınıfı ve `Container` sınıfı, kaynakları barındıran bir kapsayıcı tanımlar. Yok edici içinde `Container` sınıf çağrıları `cleanup` iki yöntemi kendi `Resource` paralel ve çağrıları üyeleri `cleanup` yöntemi, üçüncü `Resource` üyesi.

[!code-cpp[concrt-parallel-resource-destruction#1](../../parallel/concrt/codesnippet/cpp/best-practices-in-the-parallel-patterns-library_10.h)]

Bu düzen herhangi bir sorun kendi kendine olsa da, iki görevi paralel olarak çalışan aşağıdaki kodu düşünün. İlk görev oluşturur. bir `Container` nesne ve ikinci görev genel görevi iptal eder. Çizim için iki örnekte [concurrency::event](../../parallel/concrt/reference/event-class.md) sonra gerçekleşen iptal emin olmak için nesneleri `Container` nesnesi oluşturulur ve `Container` nesnesi yok edildiğinde iptal işleminden sonra işlemi gerçekleşir.

[!code-cpp[concrt-parallel-resource-destruction#2](../../parallel/concrt/codesnippet/cpp/best-practices-in-the-parallel-patterns-library_11.cpp)]

Bu örnek aşağıdaki çıktıyı üretir:

```Output
Container 1: Freeing resources...Exiting program...
```

Bu kod örneği, beklediğinizden farklı şekilde davranmasına neden olabilecek aşağıdaki sorunları içerir:

- Çağrı alt görev üst görevin iptalini neden [concurrency::parallel_invoke](reference/concurrency-namespace-functions.md#parallel_invoke), iptal edilebilir. Bu nedenle, bu iki kaynakları serbest bırakılmaz.

- Üst görevin iptalini alt görev, bir iç özel durum oluşturmasına neden olur. Çünkü `Container` yok edici bu özel durumun işlemez, özel durum yukarı yayılır ve üçüncü kaynak değil serbest bırakılır.

- Aracılığıyla alt görev tarafından oluşturulan özel durum yayar `Container` yıkıcı. Bir yok ediciden atma uygulama tanımlanmamış bir duruma koyar.

Bu görevleri değil iptal edilmesini garanti sürece, görevler kaynakları serbest bırakma gibi kritik işlemler, gerçekleştirmeyin öneririz. Ayrıca, türleri yıkıcı oluşturabilecek çalışma zamanı işlevleri kullanmayın öneririz.

[[Üst](#top)]

##  <a name="repeated-blocking"></a> Sürekli olarak paralel bir döngüde engelleme

Gibi paralel bir döngüden [concurrency::parallel_for](reference/concurrency-namespace-functions.md#parallel_for) veya [concurrency::parallel_for_each](reference/concurrency-namespace-functions.md#parallel_for_each) , direncin hakim olduğu engelleyerek işlemleri kısa bir süre içinde birçok iş parçacığı oluşturmak çalışma zamanı neden olabilir.

Eşzamanlılık Çalışma zamanı, bir görev tamamlanır veya işbirliği içerisinde devamlılığı engeller veya verir ek çalışma gerçekleştirir. Bir paralel döngüsünün, yineleme blokları çalışma zamanı başka bir yineleme başlayabilir. Kullanılabilir hiçbir boşta iş parçacıkları olduğunda, çalışma zamanının yeni bir iş parçacığı oluşturur.

Döngü gövdesi, paralel bazen blokları, bu mekanizma genel görev performansını en üst düzeye yardımcı olur. Ancak, birçok yineleme engellerseniz, çalışma zamanı ek bir iş çalıştırmak için birçok iş parçacığı oluşturabilir. Bu, düşük bellek koşulları veya donanım kaynaklarının yetersiz kullanım için neden olabilir.

Çağıran aşağıdaki örneği inceleyin [concurrency::send](reference/concurrency-namespace-functions.md#send) her yinelemesinde işlevi bir `parallel_for` döngü. Çünkü `send` engeller işbirliği içerisinde devamlılığı, çalışma zamanı her zaman ek bir iş çalıştırmak için yeni bir iş parçacığı oluşturur `send` çağrılır.

[!code-cpp[concrt-repeated-blocking#1](../../parallel/concrt/codesnippet/cpp/best-practices-in-the-parallel-patterns-library_12.cpp)]

Bu düzen önlemek için kodunuzu yeniden düzenleyin öneririz. Bu örnekte, ek iş parçacığı oluşturma çağırarak kaçınabilirsiniz `send` bir seri içinde `for` döngü.

[[Üst](#top)]

##  <a name="blocking"></a> Paralel işi iptal ettiğinizde engelleme işlemleri yapma

Çağırmadan önce mümkün olduğunda, engelleme işlemleri gerçekleştirmez [concurrency::task_group::cancel](reference/task-group-class.md#cancel) veya [CONCURRENCY::structured_task_group:: Cancel](reference/structured-task-group-class.md#cancel) paralel işi iptal etmek için yöntemi.

Bir görev işlemi engelleyen bir Guyana gerçekleştirdiğinde, ilk görevi için veriler beklerken çalışma zamanı başka işleri gerçekleştirebilirsiniz. Çalışma zamanı, engellemesini kaldırır, bekleyen görev tarih değiştirdiğinde. Çalışma zamanı, daha az engeli görevleri tarih değiştirdiğinde önce daha kısa bir süre önce engeli görevler genellikle tarih değiştirdiğinde. Bu nedenle, çalışma zamanı, düşük performansa neden olur engelleme işlemi sırasında gereksiz iş zamanlayabilirsiniz. Paralel işi iptal etmeden önce engelleyici bir işlem gerçekleştirdiğinizde, buna göre engelleme işlemi çağrısı geciktirip `cancel`. Bu, gereksiz çalışmayı gerçekleştirmek diğer görevleri neden olur.

Tanımlar aşağıdaki örneği inceleyin `parallel_find_answer` işlevin sağlanan koşul işlevini karşılayan belirtilen dizi öğesi için arar. Koşul işlevi döndüğünde `true`, paralel çalışma oluşturur bir `Answer` nesne ve genel görev iptal eder.

[!code-cpp[concrt-blocking-cancel#1](../../parallel/concrt/codesnippet/cpp/best-practices-in-the-parallel-patterns-library_13.cpp)]

`new` İşleç engelleyebilecek bir yığın ayırmasını gerçekleştirir. Yalnızca görev engelleme çağrısının bir çağrı gibi bir Guyana gerçekleştirdiğinde diğer iş çalışma zamanı gerçekleştirir [concurrency::critical_section::lock](reference/critical-section-class.md#lock).

Aşağıdaki örnek, gereksiz iş önlemek ve böylece performansı gösterilmiştir. Depolama alanı için ayırır önce bu örnek görev grubunu iptal `Answer` nesne.

[!code-cpp[concrt-blocking-cancel#2](../../parallel/concrt/codesnippet/cpp/best-practices-in-the-parallel-patterns-library_14.cpp)]

[[Üst](#top)]

##  <a name="shared-writes"></a> Bir paralel döngüde Paylaşılan verilere yazma

Eşzamanlılık Çalışma zamanı çeşitli veri yapıları, örneğin sağlar [concurrency::critical_section](../../parallel/concrt/reference/critical-section-class.md), eş zamanlı Paylaşılan verilere erişimi eşitleme. Birden çok görev sık paylaşılan bir kaynağa erişim gerektirdiğinde bu veri yapılarının çoğu durumda, örneğin, kullanışlıdır.

Kullanan aşağıdaki örneği göz önünde bulundurun [concurrency::parallel_for_each](reference/concurrency-namespace-functions.md#parallel_for_each) algoritması ve `critical_section` sayısı içinde asal sayıları hesaplamak için nesne bir [std::array](../../standard-library/array-class-stl.md) nesne. Paylaşılan değişkene erişmek her iş parçacığı beklemeniz gerekir çünkü bu örnek ölçeklenmez `prime_sum`.

[!code-cpp[concrt-parallel-sum-of-primes#2](../../parallel/concrt/codesnippet/cpp/best-practices-in-the-parallel-patterns-library_15.cpp)]

Sık kilitleme işlemi etkili bir şekilde döngü serileştiren olduğundan bu örnek ayrıca düşük performansa neden olabilir. Ayrıca, bir eşzamanlılık çalışma zamanı nesnesi bir engelleme işlemi gerçekleştirdiğinde, Zamanlayıcı ilk iş parçacığı için veriler beklerken, diğer işlemleri gerçekleştirmesi için ek bir iş parçacığı oluşturabilir. Birçok görev için paylaşılan veri bekleyen olduğundan, çalışma zamanının birçok iş parçacığı oluşturur, uygulama sonlanmayacağından veya düşük kaynak durumu girin.

PPL tanımlar [concurrency::combinable](../../parallel/concrt/reference/combinable-class.md) sınıfını, paylaşılan durum kilidi serbest bir şekilde paylaşılan kaynaklara erişim sağlayarak ortadan kaldırmanıza yardımcı olur. `combinable` Ayrıntılı hesaplamalar ve ardından bu hesaplamalar son sonucu bir birleştirme sağlayan thread-local depolama sınıfı sağlar. Kadar aklınıza gelebilecek bir `combinable` bir azaltma değişkeni olarak bir nesne.

Aşağıdaki örnek Öncekine kullanarak değiştirir bir `combinable` yerine Nesne bir `critical_section` toplamı hesaplamak için nesne. Bu örnekte, her iş parçacığının kendi yerel kopya toplamı tutmadığından ölçeklendirir. Bu örnekte [concurrency::combinable::combine](reference/combinable-class.md#combine) nihai sonucu yerel hesaplamalar birleştirmek için yöntemi.

[!code-cpp[concrt-parallel-sum-of-primes#3](../../parallel/concrt/codesnippet/cpp/best-practices-in-the-parallel-patterns-library_16.cpp)]

Bu örneğin tam sürümü için bkz: [nasıl yapılır: performansı arttırmak için combinable kullanma](../../parallel/concrt/how-to-use-combinable-to-improve-performance.md). Hakkında daha fazla bilgi için `combinable` sınıfı [paralel kapsayıcılar ve nesneler](../../parallel/concrt/parallel-containers-and-objects.md).

[[Üst](#top)]

##  <a name="false-sharing"></a> Mümkün olduğunda, yanlış paylaşıma açmaktan Kaçın

*Yanlış paylaşıma* ayrı işlemciler üzerinde çalışan birden çok eşzamanlı görevler aynı önbellek satırda bulunan değişkenleri yazdığında gerçekleşir. Bir görev için değişkenlerden biri yazdığında önbellek satırı her iki değişken için geçersiz. Her işlemcinin önbellek satırı önbellek satırı geçersiz her seferinde yeniden yüklemeniz gerekir. Bu nedenle, yanlış paylaşıma performansın uygulamanızda neden olabilir.

Her paylaşılan sayaç değişkeni Artır aşağıdaki temel örnek iki eş zamanlı görevleri gösterir.

[!code-cpp[concrt-false-sharing#1](../../parallel/concrt/codesnippet/cpp/best-practices-in-the-parallel-patterns-library_17.cpp)]

İki görevler arasında veri paylaşımını kaldırmak için örneğin iki sayaç değişkenleri değiştirebilirsiniz. Bu örnek, görevler tamamlandıktan sonra son değerini hesaplar. Ancak, bu örnekte çünkü yanlış paylaşıma gösterilmektedir değişkenleri `count1` ve `count2` aynı önbellek satırda bulunması olasıdır.

[!code-cpp[concrt-false-sharing#2](../../parallel/concrt/codesnippet/cpp/best-practices-in-the-parallel-patterns-library_18.cpp)]

Yanlış paylaşıma ortadan kaldırmak için bir sayaç değişkenleri ayrı önbellek satırlarda emin olmak için yoludur. Aşağıdaki örnek, değişkenlerin hizalar `count1` ve `count2` 64 baytlık sınırlarda.

[!code-cpp[concrt-false-sharing#3](../../parallel/concrt/codesnippet/cpp/best-practices-in-the-parallel-patterns-library_19.cpp)]

Bu örnek, önbellek boyutu 64 veya daha az bayt olduğunu varsayar.

Kullanmanızı öneririz [concurrency::combinable](../../parallel/concrt/reference/combinable-class.md) sınıfı, görevler arasında verileri paylaşmanız gerekir. `combinable` Sınıfı, thread-local değişkenleri yanlış paylaşıma olasılığını olduğunu bir yol oluşturur. Hakkında daha fazla bilgi için `combinable` sınıfı [paralel kapsayıcılar ve nesneler](../../parallel/concrt/parallel-containers-and-objects.md).

[[Üst](#top)]

##  <a name="lifetime"></a> Değişkenler bir görevin süresi geçerli olduğundan emin olun

Bir lambda ifadesi için bir görev grubu veya paralel algoritma sağladığınızda, yakalama yan tümcesi lambda ifadesinin gövdesinin değere veya başvuruya göre kapsayan kapsamda değişkenlere erişmediğini belirtir. Değişkenleri, bir lambda ifadesi başvuruya göre geçiren, görev bitene kadar konusu değişkenin kullanım ömrünün ermeyeceğini güvence altına almalısınız.

Tanımlar aşağıdaki örneği inceleyin `object` sınıfı ve `perform_action` işlevi. `perform_action` İşlevi oluşturur bir `object` değişken ve bu değişkeni, zaman uyumsuz olarak bazı eylemleri gerçekleştirir. Görev önce tamamlanması kesin değildir çünkü `perform_action` işlevi döndürür, programın çökmesine veya belirtilmeyen varsa davranışlar `object` görev çalıştığında değişkeni yok.

[!code-cpp[concrt-lambda-lifetime#1](../../parallel/concrt/codesnippet/cpp/best-practices-in-the-parallel-patterns-library_20.cpp)]

Uygulama gereksinimlerine bağlı olarak, aşağıdaki tekniklerden birini değişkenleri her görevin ömrü geçerli kalmasını sağlamak için kullanabilirsiniz.

Aşağıdaki örnek geçen `object` değişkenini, görev için değer. Bu nedenle, görevin değişkeni kendisine ait kopyası üzerinde çalışır.

[!code-cpp[concrt-lambda-lifetime#2](../../parallel/concrt/codesnippet/cpp/best-practices-in-the-parallel-patterns-library_21.cpp)]

Çünkü `object` değişkeni değere göre geçirilir, bu değişken için gerçekleşen durumu değişiklikleri özgün kopyalama görünmez.

Aşağıdaki örnekte [CONCURRENCY::task_group:: wait](reference/task-group-class.md#wait) önce görev bitene emin olmak için yöntem `perform_action` işlevi döndürür.

[!code-cpp[concrt-lambda-lifetime#3](../../parallel/concrt/codesnippet/cpp/best-practices-in-the-parallel-patterns-library_22.cpp)]

İşlev döndürmeden önce artık görev bitene olduğundan, `perform_action` işlevi artık davranışını zaman uyumsuz olarak.

Aşağıdaki örnek `perform_action` bir başvuru almak için işlev `object` değişkeni. Çağıran, yaşam süresi garanti gerekir `object` değişken, görev bitene kadar geçerlidir.

[!code-cpp[concrt-lambda-lifetime#4](../../parallel/concrt/codesnippet/cpp/best-practices-in-the-parallel-patterns-library_23.cpp)]

Bir işaretçi, bir görev grubu veya paralel algoritma geçirdiğiniz bir nesnenin ömrünü denetlemek için de kullanabilirsiniz.

Lambda ifadeleri hakkında daha fazla bilgi için bkz. [Lambda ifadeleri](../../cpp/lambda-expressions-in-cpp.md).

[[Üst](#top)]

## <a name="see-also"></a>Ayrıca Bkz.

[Eşzamanlılık Çalışma Zamanı En İyi Yöntemleri](../../parallel/concrt/concurrency-runtime-best-practices.md)<br/>
[Paralel Desen Kitaplığı (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md)<br/>
[Paralel Kapsayıcılar ve Nesneler](../../parallel/concrt/parallel-containers-and-objects.md)<br/>
[Paralel Algoritmalar](../../parallel/concrt/parallel-algorithms.md)<br/>
[PPL'de İptal](cancellation-in-the-ppl.md)<br/>
[Özel Durum İşleme](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)<br/>
[İzlenecek yol: Görüntü İşleme Ağı Oluşturma](../../parallel/concrt/walkthrough-creating-an-image-processing-network.md)<br/>
[Nasıl yapılır: Paralel Sıralama Rutini Yazmak için parallel_invoke Kullanma](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md)<br/>
[Nasıl yapılır: Paralel Bir Döngüden Kurtulmak için İptal](../../parallel/concrt/how-to-use-cancellation-to-break-from-a-parallel-loop.md)<br/>
[Nasıl yapılır: Performansı arttırmak için combinable Kullanma](../../parallel/concrt/how-to-use-combinable-to-improve-performance.md)<br/>
[Zaman Uyumsuz Aracılar Kitaplığı'ndaki En İyi Yöntemler](../../parallel/concrt/best-practices-in-the-asynchronous-agents-library.md)<br/>
[Eşzamanlılık Çalışma Zamanındaki Genel En İyi Yöntemler](../../parallel/concrt/general-best-practices-in-the-concurrency-runtime.md)

