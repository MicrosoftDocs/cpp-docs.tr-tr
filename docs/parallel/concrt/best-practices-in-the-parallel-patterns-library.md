---
description: 'Daha fazla bilgi edinin: paralel Desenler kitaplığındaki En Iyi uygulamalar'
title: Paralel Desen Kitaplığı'ndaki En İyi Yöntemler
ms.date: 11/04/2016
helpviewer_keywords:
- Parallel Patterns Library, practices to avoid
- practices to avoid, Parallel Patterns Library
- best practices, Parallel Patterns Library
- Parallel Patterns Library, best practices
ms.assetid: e43e0304-4d54-4bd8-a3b3-b8673559a9d7
ms.openlocfilehash: 72b0ff36532decbc55ae792ee407b3b711bd54a5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97334696"
---
# <a name="best-practices-in-the-parallel-patterns-library"></a>Paralel Desen Kitaplığı'ndaki En İyi Yöntemler

Bu belgede, paralel Desenler kitaplığı 'nın (PPL) etkili bir şekilde kullanılması en iyi şekilde açıklanmıştır. PPL, hassas paralellik gerçekleştirmeye yönelik genel amaçlı kapsayıcılar, nesneler ve algoritmalar sağlar.

PPL hakkında daha fazla bilgi için bkz. [paralel Desenler kitaplığı (ppl)](../../parallel/concrt/parallel-patterns-library-ppl.md).

## <a name="sections"></a><a name="top"></a> Başlıklı

Bu belgede aşağıdaki bölümler yer alır:

- [Paralel hale getirmek küçük döngü gövdeleri oluşturun](#small-loops)

- [Hızlı paralellik mümkün olan en yüksek düzeyde](#highest)

- [Bölme ve Conquer sorunlarını gidermek için parallel_invoke kullanma](#divide-and-conquer)

- [Paralel bir döngüden ayırmak için Iptal veya özel durum Işlemeyi kullanma](#breaking-loops)

- [Iptal ve özel durum Işlemenin nesne yok etme işlemini nasıl etkilediğini anlayın](#object-destruction)

- [Paralel bir döngüde sürekli olarak Engellenmeyin](#repeated-blocking)

- [Paralel çalışmayı Iptal ettiğinizde engelleyici Işlemler gerçekleştirmeyin](#blocking)

- [Paralel bir döngüde paylaşılan verilere yazma](#shared-writes)

- [Mümkün olduğunda, yanlış paylaşıma karşı kaçının](#false-sharing)

- [Bir görevin ömrü boyunca değişkenlerin geçerli olduğundan emin olun](#lifetime)

## <a name="do-not-parallelize-small-loop-bodies"></a><a name="small-loops"></a> Paralel hale getirmek küçük döngü gövdeleri oluşturun

Görece küçük döngü gövdelerinin paralelleştirmesiyle, ilişkili zamanlama ek yükünün paralel işlemenin avantajlarından yararlanmasına neden olabilir. İki dizide her öğe çiftini ekleyen aşağıdaki örneği göz önünde bulundurun.

[!code-cpp[concrt-small-loops#1](../../parallel/concrt/codesnippet/cpp/best-practices-in-the-parallel-patterns-library_1.cpp)]

Her paralel döngü yinelemesinin iş yükü, paralel işleme yükünden faydalanmak için çok küçük. Döngü gövdesinde daha fazla iş gerçekleştirerek veya döngüyü genel olarak gerçekleştirerek, bu döngünün performansını artırabilirsiniz.

[[Üst](#top)]

## <a name="express-parallelism-at-the-highest-possible-level"></a><a name="highest"></a> Hızlı paralellik mümkün olan en yüksek düzeyde

Yalnızca düşük düzeyde kod paralel hale getirmek, işlemci sayısı arttıkça ölçeklendiremez bir çatal JOIN yapısı ortaya çıkarabilir. *Çatal-JOIN* yapısı, bir görevin çalışmasını daha küçük paralel alt görevlere böler ve bu alt görevlerin bitmesini bekler. Her alt görev yinelemeli olarak kendisini ek alt görevlere bölebilir.

Çatallı ekleme modeli çeşitli sorunları çözmek için yararlı olabilir, ancak eşitleme ek yükünün ölçeklenebilirliği azallabileceği durumlar vardır. Örneğin, görüntü verilerini işleyen aşağıdaki seri kodunu göz önünde bulundurun.

[!code-cpp[concrt-image-processing-filter#20](../../parallel/concrt/codesnippet/cpp/best-practices-in-the-parallel-patterns-library_2.cpp)]

Her döngü yinelemesi bağımsız olduğundan, aşağıdaki örnekte gösterildiği gibi çalışmanın çoğunu paralel hale getirmek yapabilirsiniz. Bu örnek, Outer döngüsünü paralel hale getirmek için [eşzamanlılık::p arallel_for](reference/concurrency-namespace-functions.md#parallel_for) algoritmasını kullanır.

[!code-cpp[concrt-image-processing-filter#3](../../parallel/concrt/codesnippet/cpp/best-practices-in-the-parallel-patterns-library_3.cpp)]

Aşağıdaki örnek, bir döngüdeki işlevi çağırarak bir çatal JOIN yapısını gösterir `ProcessImage` . Her bir çağrı `ProcessImage` , her bir alt görev bitene kadar döndürmez.

[!code-cpp[concrt-image-processing-filter#21](../../parallel/concrt/codesnippet/cpp/best-practices-in-the-parallel-patterns-library_4.cpp)]

Paralel döngünün her yinelemesi neredeyse hiç bir iş gerçekleştirdiyse veya paralel döngü tarafından gerçekleştirilen iş de imletilmiş ise, diğer bir deyişle, bazı döngü yinelemeleri diğerlerinden daha uzun sürer, iş için gereken zamanlama ek yükü paralel yürütme avantajını engelleyebilir. İşlemci sayısı arttıkça bu ek yük artar.

Bu örnekteki zamanlama ek yükünü azaltmak için, paralel hale getirmek iç döngüleri veya ardışık düzen oluşturma gibi başka bir paralel yapıyı kullanmadan önce dış döngüleri paralel hale getirmek yapabilirsiniz. Aşağıdaki örnek, `ProcessImages` dış döngüyü paralel hale getirmek için [eşzamanlılık::p arallel_for_each](reference/concurrency-namespace-functions.md#parallel_for_each) algoritmasını kullanmak üzere işlevi değiştirir.

[!code-cpp[concrt-image-processing-filter#22](../../parallel/concrt/codesnippet/cpp/best-practices-in-the-parallel-patterns-library_5.cpp)]

Paralel olarak görüntü işleme gerçekleştirmek için bir işlem hattı kullanan benzer bir örnek için bkz. [Izlenecek yol: Image-Processing ağı oluşturma](../../parallel/concrt/walkthrough-creating-an-image-processing-network.md).

[[Üst](#top)]

## <a name="use-parallel_invoke-to-solve-divide-and-conquer-problems"></a><a name="divide-and-conquer"></a> Bölme ve Conquer sorunlarını gidermek için parallel_invoke kullanma

Bir *bölme ve uyum* sorunu, bir görevi alt görevlere bölmek için özyineleme kullanan çatal-JOIN yapısının bir biçimidir. [Concurrency:: task_group](reference/task-group-class.md) ve [concurrency:: structured_task_group](../../parallel/concrt/reference/structured-task-group-class.md) sınıflarına ek olarak, Ayrıca, bölme ve Conquer sorunlarını gidermek için [eşzamanlılık::p arallel_invoke](reference/concurrency-namespace-functions.md#parallel_invoke) algoritmasını da kullanabilirsiniz. `parallel_invoke`Algoritma, görev grubu nesnelerinden daha kısa bir sözdizimine sahiptir ve sabit sayıda paralel göreviniz olduğunda faydalıdır.

Aşağıdaki örnek, `parallel_invoke` bitonic sıralama algoritmasını uygulamak için algoritmanın kullanımını gösterir.

[!code-cpp[concrt-parallel-bitonic-sort#12](../../parallel/concrt/codesnippet/cpp/best-practices-in-the-parallel-patterns-library_6.cpp)]

Ek yükü azaltmak için, `parallel_invoke` algoritma çağıran bağlam üzerinde görev dizisinin son kısmını gerçekleştirir.

Bu örneğin tüm sürümü için bkz. [nasıl yapılır: Parallel_invoke kullanımı paralel sıralama yordamı yazmak için](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md). Algoritma hakkında daha fazla bilgi için `parallel_invoke` bkz. [paralel algoritmalar](../../parallel/concrt/parallel-algorithms.md).

[[Üst](#top)]

## <a name="use-cancellation-or-exception-handling-to-break-from-a-parallel-loop"></a><a name="breaking-loops"></a> Paralel bir döngüden ayırmak için Iptal veya özel durum Işlemeyi kullanma

PPL, bir görev grubu veya paralel algoritma tarafından gerçekleştirilen paralel çalışmayı iptal etmenin iki yolunu sağlar. Tek yönlü [eşzamanlılık:: task_group](reference/task-group-class.md) ve [concurrency:: structured_task_group](../../parallel/concrt/reference/structured-task-group-class.md) sınıfları tarafından sağlanmış olan iptal mekanizmasını kullanmaktır. Diğer bir deyişle, bir görev çalışma işlevinin gövdesinde bir özel durum oluşturulur. İptal mekanizması, bir paralel iş ağacını iptal etmek için özel durum işleme göre daha etkilidir. *Paralel çalışma ağacı* , bazı görev gruplarının diğer görev gruplarını içerdiği ilgili görev gruplarının grubudur. İptal mekanizması, bir görev grubunu ve onun alt görev gruplarını yukarıdan aşağı doğru bir şekilde iptal eder. Buna karşılık, özel durum işleme bir alt şekilde çalışır ve özel durum yukarı doğru yayıldıklarından her bir alt görev grubunu bağımsız olarak iptal etmelidir.

Doğrudan bir görev grubu nesnesiyle çalıştığınızda, bu görev grubuna ait olan işleri iptal etmek için [concurrency:: task_group:: Cancel](reference/task-group-class.md#cancel) veya [concurrency:: structured_task_group:: Cancel](reference/structured-task-group-class.md#cancel) yöntemlerini kullanın. Örneğin, bir paralel algoritmayı iptal etmek için, `parallel_for` bir üst görev grubu oluşturun ve bu görev grubunu iptal edin. Örneğin, bir `parallel_find_any` dizideki bir değeri paralel olarak arayan aşağıdaki işlevi göz önünde bulundurun.

[!code-cpp[concrt-parallel-array-search#2](../../parallel/concrt/codesnippet/cpp/best-practices-in-the-parallel-patterns-library_7.cpp)]

Paralel algoritmalar görev grupları kullandığından, paralel yinelemeden biri üst görev grubunu iptal ettiğinde, genel görev iptal edilir. Bu örneğin tüm sürümü için bkz. [nasıl yapılır: paralel bir döngüden ayırmak Için Iptal kullanma](../../parallel/concrt/how-to-use-cancellation-to-break-from-a-parallel-loop.md).

Özel durum işleme, yük boşaltma mekanizmasından paralel çalışmayı iptal etmenin daha verimli bir yolu olsa da, özel durum işlemenin uygun olduğu durumlar vardır. Örneğin, aşağıdaki yöntem, `for_all` bir yapının her bir düğümünde yinelemeli olarak bir çalışma işlevi gerçekleştirir `tree` . Bu örnekte, `_children` veri üyesi nesneleri içeren bir [std:: List](../../standard-library/list-class.md) `tree` .

[!code-cpp[concrt-task-tree-search#6](../../parallel/concrt/codesnippet/cpp/best-practices-in-the-parallel-patterns-library_8.cpp)]

Yöntemi çağıran, `tree::for_all` bir çalışma işlevinin ağacın her öğesinde çağrılmasına gerek yoksa bir özel durum oluşturabilir. Aşağıdaki örnek, `search_for_value` belirtilen nesnede bir değer arayan işlevini gösterir `tree` . `search_for_value`İşlevi, ağacın geçerli öğesi belirtilen değerle eşleştiğinde bir özel durum oluşturan bir çalışma işlevi kullanır. `search_for_value`İşlevi `try-catch` özel durumu yakalamak ve sonucu konsola yazdırmak için bir blok kullanır.

[!code-cpp[concrt-task-tree-search#3](../../parallel/concrt/codesnippet/cpp/best-practices-in-the-parallel-patterns-library_9.cpp)]

Bu örneğin tüm sürümü için bkz. [nasıl yapılır: paralel bir döngüden ayırmak Için özel durum Işlemeyi kullanma](../../parallel/concrt/how-to-use-exception-handling-to-break-from-a-parallel-loop.md).

PPL tarafından sunulan iptal ve özel durum işleme mekanizmaları hakkında daha fazla genel bilgi için bkz. [PPL](cancellation-in-the-ppl.md) ve [özel durum işlemede](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)iptal.

[[Üst](#top)]

## <a name="understand-how-cancellation-and-exception-handling-affect-object-destruction"></a><a name="object-destruction"></a> Iptal ve özel durum Işlemenin nesne yok etme işlemini nasıl etkilediğini anlayın

Bir paralel çalışma ağacında, iptal edilen bir görev alt görevlerin çalışmasını engeller. Bu, alt görevlerden biri, uygulamanız için önemli bir işlem gerçekleştirdiğinde (örneğin, bir kaynağı boşaltma gibi) soruna neden olabilir. Ayrıca, Görev iptali bir özel durumun nesne yıkıcısı aracılığıyla yaymasına ve uygulamanızda tanımsız davranışlara neden olabilir.

Aşağıdaki örnekte, `Resource` sınıfı bir kaynağı açıklar ve `Container` sınıfı, kaynakları tutan bir kapsayıcıyı açıklar. ' In yıkıcısında, `Container` sınıfı `cleanup` kendi üyelerinin ikisi üzerinde yöntemi `Resource` paralel olarak çağırır ve sonra `cleanup` üçüncü üyesinde yöntemini çağırır `Resource` .

[!code-cpp[concrt-parallel-resource-destruction#1](../../parallel/concrt/codesnippet/cpp/best-practices-in-the-parallel-patterns-library_10.h)]

Bu düzende kendi kendine sorun olmasa da, paralel olarak iki görevi çalıştıran aşağıdaki kodu göz önünde bulundurun. İlk görev bir nesne oluşturur `Container` ve ikinci görev genel görevi iptal eder. Örnek olarak, örneğin, nesne oluşturulduktan [](../../parallel/concrt/reference/event-class.md) sonra iptal `Container` işleminin gerçekleşmesini ve `Container` iptal işlemi oluştuktan sonra nesnenin yok edilmesinden emin olmak için, örnek iki eşzamanlılık:: Event nesnesi kullanır.

[!code-cpp[concrt-parallel-resource-destruction#2](../../parallel/concrt/codesnippet/cpp/best-practices-in-the-parallel-patterns-library_11.cpp)]

Bu örnek aşağıdaki çıktıyı üretir:

```Output
Container 1: Freeing resources...Exiting program...
```

Bu kod örneği, beklediğinizden farklı davranmasına neden olabilecek aşağıdaki sorunları içerir:

- Üst görevin iptali alt göreve neden olur; [eşzamanlılık::p arallel_invoke](reference/concurrency-namespace-functions.md#parallel_invoke)çağrısı da iptal edilir. Bu nedenle, bu iki kaynak serbest bırakılmaz.

- Üst görevin iptali, alt görevin bir iç özel durum oluşturmasına neden olur. `Container`Yıkıcı bu özel durumu işlemediğinden, özel durum yukarı doğru yayılır ve üçüncü kaynak serbest bırakılmaz.

- Alt görev tarafından oluşturulan özel durum yıkıcı aracılığıyla yayar `Container` . Yıkıcıdan oluşturma, uygulamayı tanımsız bir duruma koyar.

Bu görevlerin iptal edilmeyeceği garantisi vermediğiniz sürece kaynakları boşaltma gibi kritik işlemler gerçekleştirmenizi öneririz. Ayrıca, türlerinizin yıkıcısında oluşturmayabilmeniz için çalışma zamanı işlevini kullanmanıza de tavsiye ederiz.

[[Üst](#top)]

## <a name="do-not-block-repeatedly-in-a-parallel-loop"></a><a name="repeated-blocking"></a> Paralel bir döngüde sürekli olarak Engellenmeyin

[Eşzamanlılık::p arallel_for](reference/concurrency-namespace-functions.md#parallel_for) veya [eşzamanlılık: arallel_for_each:p](reference/concurrency-namespace-functions.md#parallel_for_each) işlemleri gibi bir paralel döngü, çalışma zamanının kısa bir süre içinde çok sayıda iş parçacığı oluşturmasına neden olabilir.

Eşzamanlılık Çalışma Zamanı, bir görev tamamlandığında veya işbirliği yaptığında ya da olduğunda ek iş gerçekleştirir. Bir paralel döngü yinelemesi engellediğinde, çalışma zamanı başka bir yinelemeye başlayabilir. Kullanılabilir boşta iş parçacığı olmadığında, çalışma zamanı yeni bir iş parçacığı oluşturur.

Paralel bir döngünün gövdesi zaman zaman engellediğinde, bu mekanizma genel görev verimini en üst düzeye çıkarabilir. Ancak, çok sayıda yineleme bloğu olduğunda, çalışma zamanı ek çalışmayı çalıştırmak için birçok iş parçacığı oluşturabilir. Bu, düşük bellek koşullarına veya donanım kaynaklarının yetersiz kullanımına neden olabilir.

Bir döngünün her yinelemesinde [concurrency:: Send](reference/concurrency-namespace-functions.md#send) işlevini çağıran aşağıdaki örneği göz önünde bulundurun `parallel_for` . `send`Bloklar birlikte çalıştığından, çalışma zamanı her çağrıldığında ek iş çalıştırmak için yeni bir iş parçacığı oluşturur `send` .

[!code-cpp[concrt-repeated-blocking#1](../../parallel/concrt/codesnippet/cpp/best-practices-in-the-parallel-patterns-library_12.cpp)]

Bu düzenin önüne geçmek için kodunuzu yeniden düzenlemeniz önerilir. Bu örnekte, bir seri döngüsünde çağırarak ek iş parçacıkları oluşturmaktan kaçınabilirsiniz `send` **`for`** .

[[Üst](#top)]

## <a name="do-not-perform-blocking-operations-when-you-cancel-parallel-work"></a><a name="blocking"></a> Paralel çalışmayı Iptal ettiğinizde engelleyici Işlemler gerçekleştirmeyin

Mümkün olduğunda, paralel işi iptal etmek için [concurrency:: task_group:: Cancel](reference/task-group-class.md#cancel) veya [concurrency:: structured_task_group:: Cancel](reference/structured-task-group-class.md#cancel) metodunu çağırmadan önce engelleyici işlemler gerçekleştirmeyin.

Bir görev, bir ortak engelleme işlemi gerçekleştirdiğinde, çalışma zamanı, ilk görevin verileri beklediği sırada başka bir iş gerçekleştirebilir. Çalışma zamanı, blokları kaldırdığınızda bekleyen görevi müşteri sizinle randevusunu. Çalışma zamanı, genellikle daha önce engellenmemiş olan görevleri, son zamanlarda engellendikleri müşteri sizinle randevusunu görevlerden önce müşteri sizinle randevusunu. Bu nedenle, çalışma zamanı engelleyici işlem sırasında gereksiz çalışmayı zamanlayabilir ve bu da performansı düşürdü. Buna uygun olarak, paralel çalışmayı iptal etmeden önce engelleyici bir işlem gerçekleştirdiğinizde, engelleme işlemi çağrısı geciktirebilirler `cancel` . Bu, diğer görevlerin gereksiz işler gerçekleştirmesine neden olur.

Belirtilen `parallel_find_answer` koşul işlevini karşılayan, belirtilen dizinin bir öğesini arayan işlevini tanımlayan aşağıdaki örneği göz önünde bulundurun. Koşul işlevi döndüğünde **`true`** , paralel çalışma işlevi bir `Answer` nesne oluşturur ve genel görevi iptal eder.

[!code-cpp[concrt-blocking-cancel#1](../../parallel/concrt/codesnippet/cpp/best-practices-in-the-parallel-patterns-library_13.cpp)]

`new`İşleci, engelleyebilen bir yığın ayırması gerçekleştirir. Çalışma zamanı, yalnızca görev [eşzamanlılık:: critical_section:: Lock](reference/critical-section-class.md#lock)çağrısı gibi bir ortak engelleme çağrısı gerçekleştirdiğinde diğer işleri gerçekleştirir.

Aşağıdaki örnek, gereksiz çalışmanın nasıl önleneceği ve bu sayede performansı iyileştirmenin nasıl yapıldığını göstermektedir. Bu örnek, nesne için depolama alanını ayırmadan önce görev grubunu iptal eder `Answer` .

[!code-cpp[concrt-blocking-cancel#2](../../parallel/concrt/codesnippet/cpp/best-practices-in-the-parallel-patterns-library_14.cpp)]

[[Üst](#top)]

## <a name="do-not-write-to-shared-data-in-a-parallel-loop"></a><a name="shared-writes"></a> Paralel bir döngüde paylaşılan verilere yazma

Eşzamanlılık Çalışma Zamanı çeşitli veri yapıları sağlar, örneğin [critical_section](../../parallel/concrt/reference/critical-section-class.md), eş zamanlı erişimi paylaşılan verilere eşitler. Bu veri yapıları birçok durumda faydalıdır; Örneğin, birden çok görev nadiren bir kaynağa paylaşılan erişim gerektirirken.

[](reference/concurrency-namespace-functions.md#parallel_for_each) `critical_section` Bir [std:: Array](../../standard-library/array-class-stl.md) nesnesindeki asal sayıların sayısını hesaplamak için eşzamanlılık::p arallel_for_each algoritmasını ve nesnesini kullanan aşağıdaki örneği göz önünde bulundurun. Bu örnek ölçeklenmez çünkü her iş parçacığının paylaşılan değişkene erişmek için beklemesi gerekir `prime_sum` .

[!code-cpp[concrt-parallel-sum-of-primes#2](../../parallel/concrt/codesnippet/cpp/best-practices-in-the-parallel-patterns-library_15.cpp)]

Sık kilitleme işlemi döngüyü etkin bir şekilde seri hale getirtiğinden Bu örnek düşük performansa da yol açabilir. Ayrıca, bir Eşzamanlılık Çalışma Zamanı nesnesi engelleyici bir işlem gerçekleştirdiğinde, Zamanlayıcı ilk iş parçacığı veri beklerken diğer işleri gerçekleştirmek için ek bir iş parçacığı oluşturabilir. Çalışma zamanı çok sayıda iş parçacığı oluşturursa, çok sayıda görev paylaşılan verileri beklerken, uygulama düşük kaynak durumunda kötü bir şekilde çalışabilir veya bir durum girebilir.

PPL, paylaşılan kaynaklara kilit boş bir şekilde erişim sağlayarak paylaşılan durumu ortadan kaldırmanıza yardımcı olan [concurrency:: combinable](../../parallel/concrt/reference/combinable-class.md) sınıfını tanımlar. `combinable`Sınıfı, hassas hesaplamalar gerçekleştirmenizi ve ardından bu hesaplamaları nihai bir sonuçla birleştirmeye imkan tanıyan iş parçacığı yerel depolama alanı sağlar. Bir `combinable` nesneyi bir azaltma değişkeni olarak düşünebilirsiniz.

Aşağıdaki örnek, `combinable` `critical_section` toplamı hesaplamak için nesnesi yerine bir nesnesini kullanarak önceki bir nesneyi değiştirir. Bu örnek, her bir iş parçacığı toplamın kendi yerel kopyasını taşıdığı için ölçeklendirilir. Bu örnek, yerel hesaplamaları nihai sonuçla birleştirmek için [concurrency:: combinable::](reference/combinable-class.md#combine) Merge metodunu kullanır.

[!code-cpp[concrt-parallel-sum-of-primes#3](../../parallel/concrt/codesnippet/cpp/best-practices-in-the-parallel-patterns-library_16.cpp)]

Bu örneğin tüm sürümü için bkz. [nasıl yapılır: performansı artırmak için combinable kullanma](../../parallel/concrt/how-to-use-combinable-to-improve-performance.md). Sınıfı hakkında daha fazla bilgi için `combinable` bkz. [paralel kapsayıcılar ve nesneler](../../parallel/concrt/parallel-containers-and-objects.md).

[[Üst](#top)]

## <a name="when-possible-avoid-false-sharing"></a><a name="false-sharing"></a> Mümkün olduğunda, yanlış paylaşıma karşı kaçının

Ayrı işlemcilerde çalışan birden fazla eş zamanlı görev aynı önbellek satırında bulunan değişkenlere yazdığınızda *yanlış paylaşım* oluşur. Bir görev değişkenlerden birine yazdığında her iki değişken için de önbellek satırı geçersiz kılınır. Önbellek satırı her geçersiz kılınışında her işlemcinin önbellek satırını yeniden yüklemesi gerekir. Bu nedenle, yanlış paylaşım uygulamanızda performansın düşmesine neden olabilir.

Aşağıdaki temel örnek, her biri paylaşılan Sayaç değişkenini artıran iki eş zamanlı görevi gösterir.

[!code-cpp[concrt-false-sharing#1](../../parallel/concrt/codesnippet/cpp/best-practices-in-the-parallel-patterns-library_17.cpp)]

İki görev arasında veri paylaşımını ortadan kaldırmak için, örneği iki sayaç değişkeni kullanacak şekilde değiştirebilirsiniz. Bu örnek, son sayaç değerini görevler bittikten sonra hesaplar. Ancak, bu örnek, değişkenleri `count1` ve `count2` aynı önbellek satırında konumlandığı için yanlış paylaşımı gösterir.

[!code-cpp[concrt-false-sharing#2](../../parallel/concrt/codesnippet/cpp/best-practices-in-the-parallel-patterns-library_18.cpp)]

Yanlış paylaşımı ortadan kaldırmanın bir yolu, sayaç değişkenlerinin ayrı önbellek satırlarında olduğundan emin olmanızı sağlar. Aşağıdaki örnek, değişkenlerini `count1` ve `count2` 64 baytlık sınırları hizalar.

[!code-cpp[concrt-false-sharing#3](../../parallel/concrt/codesnippet/cpp/best-practices-in-the-parallel-patterns-library_19.cpp)]

Bu örnek, bellek önbelleğinin boyutunun 64 veya daha az bayt olduğunu varsayar.

Görevler arasında veri paylaşmak gerektiğinde [eşzamanlılık:: combinable](../../parallel/concrt/reference/combinable-class.md) sınıfını kullanmanızı öneririz. `combinable`Sınıfı, yanlış paylaşım olasılığını daha düşük olan bir şekilde iş parçacığı yerel değişkenleri oluşturur. Sınıfı hakkında daha fazla bilgi için `combinable` bkz. [paralel kapsayıcılar ve nesneler](../../parallel/concrt/parallel-containers-and-objects.md).

[[Üst](#top)]

## <a name="make-sure-that-variables-are-valid-throughout-the-lifetime-of-a-task"></a><a name="lifetime"></a> Bir görevin ömrü boyunca değişkenlerin geçerli olduğundan emin olun

Bir görev grubuna veya paralel algoritmaya bir lambda ifadesi sağladığınızda, yakalama yan tümcesi, lambda ifadesinin gövdesinin, kapsayan kapsamdaki değişkenlere değere göre veya başvuruya göre erişip erişemeyeceğini belirtir. Değişkenleri başvuruya göre lambda ifadesine geçirdiğinizde, bu değişkenin yaşam süresinin görev bitene kadar devam ettiğinden emin olmanız gerekir.

Sınıfını ve işlevini tanımlayan aşağıdaki örneği göz önünde bulundurun `object` `perform_action` . `perform_action`İşlev bir değişken oluşturur `object` ve bu değişken üzerinde zaman uyumsuz bir eylem gerçekleştirir. Görev, işlev döndürülmeden önce bitiş garantisi olmadığından `perform_action` , `object` görev çalışırken değişken yok edildiğinde program çöker veya belirtilmemiş bir davranış gösterir.

[!code-cpp[concrt-lambda-lifetime#1](../../parallel/concrt/codesnippet/cpp/best-practices-in-the-parallel-patterns-library_20.cpp)]

Uygulamanızın gereksinimlerine bağlı olarak, değişkenlerin her görevin yaşam süresi boyunca geçerli kalmasını güvence altına almak için aşağıdaki tekniklerden birini kullanabilirsiniz.

Aşağıdaki örnek, `object` değişkenine değere göre değişkenini geçirir. Bu nedenle, görev değişkeninin kendi kopyasında çalışır.

[!code-cpp[concrt-lambda-lifetime#2](../../parallel/concrt/codesnippet/cpp/best-practices-in-the-parallel-patterns-library_21.cpp)]

`object`Değişken değere göre geçirildiğinden, bu değişkende oluşan tüm durum değişiklikleri özgün kopyada görünmez.

Aşağıdaki örnek, işlevin dönüşden önce görevin tamamlandığından emin olmak için [concurrency:: task_group:: wait](reference/task-group-class.md#wait) yöntemini kullanır `perform_action` .

[!code-cpp[concrt-lambda-lifetime#3](../../parallel/concrt/codesnippet/cpp/best-practices-in-the-parallel-patterns-library_22.cpp)]

Görev artık işlev döndürülmesinden önce bittiği için, `perform_action` işlev zaman uyumsuz olarak davranmayacaktır.

Aşağıdaki örnek, `perform_action` değişkenine başvuru almak için işlevi değiştirir `object` . Çağıran, değişken ömrünün, `object` görev bitene kadar geçerli olduğundan emin olmalıdır.

[!code-cpp[concrt-lambda-lifetime#4](../../parallel/concrt/codesnippet/cpp/best-practices-in-the-parallel-patterns-library_23.cpp)]

Bir görev grubuna veya paralel algoritmaya geçirdiğiniz nesnenin ömrünü denetlemek için de bir işaretçi kullanabilirsiniz.

Lambda ifadeleri hakkında daha fazla bilgi için bkz. [lambda ifadeleri](../../cpp/lambda-expressions-in-cpp.md).

[[Üst](#top)]

## <a name="see-also"></a>Ayrıca bkz.

[En Iyi Eşzamanlılık Çalışma Zamanı uygulamalar](../../parallel/concrt/concurrency-runtime-best-practices.md)<br/>
[Paralel Desen Kitaplığı (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md)<br/>
[Paralel Kapsayıcılar ve nesneler](../../parallel/concrt/parallel-containers-and-objects.md)<br/>
[Paralel algoritmalar](../../parallel/concrt/parallel-algorithms.md)<br/>
[PPL'de İptal](cancellation-in-the-ppl.md)<br/>
[Özel Durum İşleme](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)<br/>
[İzlenecek yol: Image-Processing ağ oluşturma](../../parallel/concrt/walkthrough-creating-an-image-processing-network.md)<br/>
[Nasıl yapılır: paralel sıralama yordamı yazmak için parallel_invoke kullanma](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md)<br/>
[Nasıl yapılır: paralel bir döngüden ayırmak için Iptal kullanma](../../parallel/concrt/how-to-use-cancellation-to-break-from-a-parallel-loop.md)<br/>
[Nasıl yapılır: performansı artırmak için combinable kullanma](../../parallel/concrt/how-to-use-combinable-to-improve-performance.md)<br/>
[Zaman uyumsuz aracılar kitaplığındaki en iyi uygulamalar](../../parallel/concrt/best-practices-in-the-asynchronous-agents-library.md)<br/>
[Eşzamanlılık Çalışma Zamanı genel En Iyi Yöntemler](../../parallel/concrt/general-best-practices-in-the-concurrency-runtime.md)
