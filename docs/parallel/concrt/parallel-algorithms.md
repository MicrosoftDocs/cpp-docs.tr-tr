---
title: Paralel Algoritmalar
ms.date: 11/19/2018
helpviewer_keywords:
- parallel algorithms [Concurrency Runtime]
ms.assetid: 045dca7b-4d73-4558-a44c-383b88a28473
ms.openlocfilehash: b8a08919ce6792babb9b8b1b809e242465a200f9
ms.sourcegitcommit: 9e891eb17b73d98f9086d9d4bfe9ca50415d9a37
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/20/2018
ms.locfileid: "52176451"
---
# <a name="parallel-algorithms"></a>Paralel Algoritmalar

Paralel Desen kitaplığı (PPL) eşzamanlı olarak veri koleksiyonlarda iş gerçekleştiren algoritmalar sağlar. Bu algoritmalar C++ Standart Kitaplığı tarafından sağlanan benzer.

Paralel algoritmalar eşzamanlılık çalışma zamanındaki varolan işlevsellikte öğesinden oluşur. Örneğin, [concurrency::parallel_for](reference/concurrency-namespace-functions.md#parallel_for) algoritması kullanan bir [concurrency::structured_task_group](../../parallel/concrt/reference/structured-task-group-class.md) paralel döngü yinelemesi gerçekleştirmek için nesne. `parallel_for` Algoritması bölümler kullanılabilir bilgi işlem kaynaklarının sayısını belirtilen bir en iyi şekilde çalışır.

##  <a name="top"></a> Bölümleri

- [Parallel_for algoritması](#parallel_for)

- [Parallel_for_each algoritması](#parallel_for_each)

- [Parallel_invoke algoritması](#parallel_invoke)

- [Parallel_transform ve parallel_reduce algoritmaları](#parallel_transform_reduce)

    - [Parallel_transform algoritması](#parallel_transform)

    - [Parallel_reduce algoritması](#parallel_reduce)

    - [Örnek: Eşleme gerçekleştirme ve paralel olarak azaltma](#map_reduce_example)

- [Bölümlendirme çalışması](#partitions)

- [Paralel sıralama](#parallel_sorting)

    - [Sıralama algoritması seçme](#choose_sort)

##  <a name="parallel_for"></a> Parallel_for algoritması

[Concurrency::parallel_for](reference/concurrency-namespace-functions.md#parallel_for) algoritmasını paralel olarak tekrar tekrar aynı görevi gerçekleştirir. Bu görevlerin her biri, bir yineleme değere göre parametreli olup. Bu algoritma, kaynakları bu döngü yinelemesi arasında paylaşmaz bir döngü gövdesi olduğunda yararlıdır.

`parallel_for` Algoritması görevleri Paralel yürütme için iyi bir şekilde bölümler. Bir işi kaplayan algoritması ve iş yüklerini dengesiz olduğunda bu bölümler dengelemek için çalma aralığını kullanır. Bir döngü yinelemesi işbirliği içerisinde devamlılığı engellediğinde çalışma zamanı, diğer iş parçacıkları veya işlemcileri için geçerli iş parçacığının atandığı yineleme aralığı yeniden dağıtır. Benzer şekilde, bir iş parçacığı bir dizi yineleme tamamlandığında, çalışma zamanı iş parçacığı diğer iş parçacıklarından işi yeniden dağıtır. `parallel_for` Algoritması da destekler *paralellik iç içe geçmiş*. Paralel bir döngüden başka bir paralel bir döngüden içeriyorsa, çalışma zamanı işlem kaynakları arasında döngü gövdelerini Paralel yürütme için verimli bir şekilde düzenler.

`parallel_for` Algoritması, birden fazla aşırı yüklenmiş sürümleri vardır. İlk sürüm, başlangıç değeri, bir bitiş değeri ve bir iş işlevi (bir lambda ifadesi, işlev nesnesi veya işlev işaretçisi) alır. İkinci Sürüm başlangıç değeri, bir bitiş değeri, bir değer olarak adım ve iş işlevi alır. Bu işlevin ilk sürüm 1. adım değeri olarak kullanır. Kalan sürümleri belirtmenize olanak verir bölümleyici nesneleri, ele nasıl `parallel_for` aralıkları arasında iş parçacıklarını bölüm. Bölümleyiciler bölümünde daha ayrıntılı açıklanmıştır [bölümleme iş](#partitions) bu belgedeki.

Çoğu dönüştürebilirsiniz `for` kullanılacak döngüler `parallel_for`. Ancak, `parallel_for` algoritması farklıdır `for` aşağıdaki yollarla deyimi:

- `parallel_for` Algoritması `parallel_for` görevleri önceden belirlenmiş bir sırada yürütmez.

- `parallel_for` Algoritması rastgele sonlandırma koşulları desteklemez. `parallel_for` Algoritması durdurur geçerli yineleme değişkeni değeri olduğunda kısa `last`.

- `_Index_type` Tür parametresi, bir tamsayı türü olmalıdır. Bu integral türü imzalı veya imzasız.

- Döngü yinelemesi ileriye doğru olması gerekir. `parallel_for` Algoritması türünde bir özel durum oluşturur [std::invalid_argument](../../standard-library/invalid-argument-class.md) varsa `_Step` 1'den küçük bir parametredir.

- Özel durum işleme mekanizması `parallel_for` algoritması farklı bir `for` döngü. Birden çok özel durum, aynı anda paralel döngü gövdesinde meydana gelirse, çalışma zamanı çağıran iş parçacığına özel durumlardan yalnızca birini yayar `parallel_for`. Ayrıca, bir döngü yinelemesi bir özel durum oluşturduğunda, çalışma zamanının genel döngü hemen durdurmaz. Bunun yerine, döngü iptal edilmiş duruma yerleştirilir ve çalışma zamanı henüz başlamamış herhangi bir görevi atar. Özel durum işleme ve paralel algoritmalar hakkında daha fazla bilgi için bkz. [özel durum işleme](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md).

Ancak `parallel_for` algoritması rastgele sonlandırma koşulları desteklemez, tüm görevler durdurmak için İptal'i kullanabilirsiniz. İptal işlemleri hakkında daha fazla bilgi için bkz. [ppl'de iptal](cancellation-in-the-ppl.md).

> [!NOTE]
>  Yük Dengeleme ve iptal etme gibi özellikleri için destek sonuçlardan döngü gövdesi, paralel olarak yürütülen avantajları üstesinden değil, zamanlama maliyeti, özellikle döngü gövdesi nispeten küçük olduğunda. Paralel bir döngüde bir bölümleyici kullanarak bu ek yükü en aza indirebilirsiniz. Daha fazla bilgi için [bölümleme iş](#partitions) bu belgenin devamındaki.

### <a name="example"></a>Örnek

Aşağıdaki örnek, temel yapısını gösterir. `parallel_for` algoritması. Bu örnek, her bir değeri [1, 5] aralığında paralel konsola yazdırır.

[!code-cpp[concrt-parallel-for-structure#1](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_1.cpp)]

Bu örnek, örnek aşağıdaki çıktıyı üretir:

```Output
1 2 4 3 5
```

Çünkü `parallel_for` her öğesine paralel algoritma davranır, değerleri konsola yazdırılır sırasını farklılık gösterir.

Kullanan tam bir örnek `parallel_for` algoritmasını bkz [nasıl yapılır: parallel_for döngüsü yazma](../../parallel/concrt/how-to-write-a-parallel-for-loop.md).

[[Üst](#top)]

##  <a name="parallel_for_each"></a> Parallel_for_each algoritması

[Concurrency::parallel_for_each](reference/concurrency-namespace-functions.md#parallel_for_each) algoritmasını paralel C++ Standart Kitaplığı tarafından sağlananlar gibi yinelemeli bir kapsayıcısı üzerinde görevleri gerçekleştirir. Bölümleme aynı mantığı kullanır, `parallel_for` algoritması kullanır.

`parallel_for_each` Algoritması, C++ Standart Kitaplığı benzer [std::for_each](../../standard-library/algorithm-functions.md#for_each) hariç algoritmasını `parallel_for_each` algoritması görevleri aynı anda yürütür. Diğer paralel algoritmalar gibi `parallel_for_each` görevleri belirli bir sırayla yürütmez.

Ancak `parallel_for_each` algoritması, hem ileriye doğru Yineleyicilerin hem de rasgele erişim yineleyicileri çalışır, rasgele erişim yineleyicileri ile daha iyi gerçekleştirir.

### <a name="example"></a>Örnek

Aşağıdaki örnek, temel yapısını gösterir. `parallel_for_each` algoritması. Bu örnek, her bir değeri konsola yazdırır bir [std::array](../../standard-library/array-class-stl.md) paralel nesne.

[!code-cpp[concrt-parallel-for-each-structure#1](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_2.cpp)]

Bu örnek, örnek aşağıdaki çıktıyı üretir:

```Output
4 5 1 2 3
```

Çünkü `parallel_for_each` her öğesine paralel algoritma davranır, değerleri konsola yazdırılır sırasını farklılık gösterir.

Kullanan tam bir örnek `parallel_for_each` algoritmasını bkz [nasıl yapılır: parallel_for_each döngüsü yazma](../../parallel/concrt/how-to-write-a-parallel-for-each-loop.md).

[[Üst](#top)]

##  <a name="parallel_invoke"></a> Parallel_invoke algoritması

[Concurrency::parallel_invoke](reference/concurrency-namespace-functions.md#parallel_invoke) algoritması, bir dizi görevi paralel olarak yürütür. Her görev bitene kadar döndürmez. Bu algoritma, aynı anda yürütmek istediğiniz birkaç bağımsız görev olduğunda yararlıdır.

`parallel_invoke` Algoritması, bir dizi iş işlevleri (lambda işlevi, işlev nesneleri veya işlev işaretçileri), parametreler olarak alır. `parallel_invoke` Algoritması aşırı yüklü iki ile on parametreleri arasında gerçekleştirilecek. Geçirdiğiniz her işlev `parallel_invoke` sıfır parametreye gerçekleştirmeniz gerekir.

Diğer paralel algoritmalar gibi `parallel_invoke` görevleri belirli bir sırayla yürütmez. Konu [görev Paralelliği](../../parallel/concrt/task-parallelism-concurrency-runtime.md) açıklar nasıl `parallel_invoke` algoritması, görevler ve Görev gruplarına ilişkilendirir.

### <a name="example"></a>Örnek

Aşağıdaki örnek, temel yapısını gösterir. `parallel_invoke` algoritması. Bu örnek aynı anda çağırır `twice` işlevi üç yerel değişkenleri ve sonucu konsola yazdırır.

[!code-cpp[concrt-parallel-invoke-structure#1](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_3.cpp)]

Bu örnek aşağıdaki çıktıyı üretir:

```Output
108 11.2 HelloHello
```

Kullanan tam örnekler için `parallel_invoke` algoritmasını bkz [nasıl yapılır: paralel sıralama rutini yazmak için parallel_invoke kullanma](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md) ve [nasıl yapılır: paralel işlemleri yürütmek için parallel_invoke kullanma](../../parallel/concrt/how-to-use-parallel-invoke-to-execute-parallel-operations.md).

[[Üst](#top)]

##  <a name="parallel_transform_reduce"></a> Parallel_transform ve parallel_reduce algoritmaları

[Concurrency::parallel_transform](reference/concurrency-namespace-functions.md#parallel_transform) ve [concurrency::parallel_reduce](reference/concurrency-namespace-functions.md#parallel_reduce) algoritmalar standart C++ Kitaplığı algoritmaları paralel sürümleridir [std::transform](../../standard-library/algorithm-functions.md#transform)ve [std::accumulate](../../standard-library/numeric-functions.md#accumulate)sırasıyla. Eşzamanlılık Çalışma zamanı sürümleri, bunların paralel olarak yürütmek için işlem sırası belirlenmez dışında C++ Standart Kitaplığı sürümleri gibi davranır. Paralel olarak işlenir, performans ve ölçeklenebilirlik avantajlarını almak için büyük bir küme ile çalışırken, bu algoritmalar kullanın.

> [!IMPORTANT]
>  `parallel_transform` Ve `parallel_reduce` bu Yineleyicilerde kararlı bellek adresleri oluşturmadığından yalnızca rastgele erişim, iki yönlü ve İleri yineleyiciler algoritmaları desteklenir. Ayrıca, bu Yineleyicilerde olmayan üretmelidir`const` l-değeri.

###  <a name="parallel_transform"></a> Parallel_transform algoritması

Kullanabileceğiniz `parallel transform` birçok veri paralelleştirme işlemleri gerçekleştirmek için kullanılan algoritma. Örneğin, şunları yapabilirsiniz:

- Görüntü parlaklığını ve diğer görüntü işlemleri gerçekleştirin.

- Sum veya nokta çarpımını iki vektör arasındaki yararlanın ve diğer vektörler üzerinde sayısal hesaplamalar.

- 3B ışın izleme, burada her yineleme için oluşturulması gereken bir piksel başvuruyor gerçekleştirin.

Aşağıdaki örnek, çağırmak için kullanılan temel yapısını gösterir. `parallel_transform` algoritması. Bu örnekte her öğeyi bir std verilerek::[vektör](../../standard-library/vector-class.md) iki yolla nesne. İlk yol, bir lambda ifadesi kullanır. İkinci yol kullanan [std::negate](../../standard-library/negate-struct.md), öğesinden türetildiğini [std::unary_function](../../standard-library/unary-function-struct.md).

[!code-cpp[concrt-basic-parallel-transform#1](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_4.cpp)]

> [!WARNING]
>  Bu örnek, temel kullanımını gösterir. `parallel_transform`. İş işlevi, önemli miktarda iş gerçekleştirmez olduğundan, bu örnekte önemli bir performans artışı beklenmiyor.

`parallel_transform` Algoritması iki aşırı yüklemesi vardır. İlk aşırı yükleme, bir giriş aralığındaki ve birli işlevini alır. Birli işlevi bir bağımsız değişken, bir işlev nesnesi ve türeyen bir tür alan bir lambda ifadesi olabilir `unary_function`. İkinci aşırı yüklemesi, iki giriş aralıkları ve ikili fonksiyon alır. İkili işlevi iki bağımsız değişken, bir işlev nesnesi ve türeyen bir tür alan bir lambda ifadesi olabilir [std::binary_function](../../standard-library/binary-function-struct.md). Aşağıdaki örnek bu farklılıkları gösterir.

[!code-cpp[concrt-parallel-transform-vectors#2](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_5.cpp)]

> [!IMPORTANT]
>  Çıktısı için sağladığınız yineleyici `parallel_transform` tamamen giriş üst üste veya hiç çakışmaması gerekir. Giriş ve çıkış yineleyicileri kısmen çakışırsa bu algoritma belirtilmemiş davranışıdır.

###  <a name="parallel_reduce"></a> Parallel_reduce algoritması

`parallel_reduce` Algoritması, bir dizi ilişkilendirilebilir özelliği karşılayan bir işlem olduğunda yararlıdır. (Bu algoritmayı yer değiştirebilirlik özelliğini gerektirmez.) Bazı ile gerçekleştirebileceğiniz işlemlerin `parallel_reduce`:

- Matris üretmek için matrislerde dizileri çarpın.

- Bir vektör matrislerde bir vektör oluşturmak için bir dizi ile çarpın.

- Bir dize sırası uzunluğunu işlem.

- Dizeleri gibi öğelerin listesini tek bir öğede birleştirin.

Aşağıdaki temel örnek nasıl kullanılacağını gösterir `parallel_reduce` dize dizisine bir dizede birleştirmek için kullanılan algoritma. Örneklerde olduğu gibi `parallel_transform`, performans artışı bu temel örnekte beklenmiyordu.

[!code-cpp[concrt-basic-parallel-reduce#1](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_6.cpp)]

Çoğu durumda, kadar aklınıza gelebilecek `parallel_reduce` kullanımına yönelik toplu olarak `parallel_for_each` algoritması ile birlikte [concurrency::combinable](../../parallel/concrt/reference/combinable-class.md) sınıfı.

###  <a name="map_reduce_example"></a> Örnek: Eşleme gerçekleştirme ve paralel olarak azaltma

A *harita* işlemi, bir dizideki her bir değeri bir işlev uygular. A *azaltmak* işlemi bir dizisinin bir değer halinde birleştirir. C++ Standart Kitaplığı kullanabilirsiniz [std::transform](../../standard-library/algorithm-functions.md#transform) ve [std::accumulate](../../standard-library/numeric-functions.md#accumulate) eşleme gerçekleştirme ve işlemleri azaltmak için işlevleri. Ancak, karşılaşılan birçok sorun için kullanabilirsiniz `parallel_transform` paralel olarak harita işlemi gerçekleştirmek için algoritma ve `parallel_reduce` algoritmasını paralel olarak azaltma işlemi gerçekleştirin.

Aşağıdaki örnek, seri olarak ve paralel asal sayıları toplamını hesaplamak için geçen süreyi karşılaştırır. Harita aşaması asal olmayan değerleri 0'da azaltın aşaması SUM'ları değerleri dönüştürür.

[!code-cpp[concrt-parallel-map-reduce-sum-of-primes#1](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_7.cpp)]

Bir eşleme gerçekleştirir ve paralel işlem azaltmak başka bir örnek için bkz: [nasıl yapılır: eşleme gerçekleştirme ve işlemleri paralel azaltma](../../parallel/concrt/how-to-perform-map-and-reduce-operations-in-parallel.md).

[[Üst](#top)]

##  <a name="partitions"></a> Bölümlendirme çalışması

Bir işlem bir veri kaynağı üzerinde paralel hale getirmek için önemli bir adım olarak *bölüm* birden çok iş parçacığı tarafından erişilebilen eşzamanlı olarak birden çok bölümlere kaynak. Bir bölümleyici paralel algoritma aralıkları arasında iş parçacıklarını nasıl bölüm belirtir. PPL, bu belgede daha önce açıklandığı şekilde, bir başlangıç iş yükü oluşturur ve ardından bir işi kaplayan algoritması ve iş yüklerini dengesiz olduğunda bu bölümler dengelemek için çalma aralığı mekanizması bölümleme varsayılan kullanır. Örneğin, bir döngü yinelemesi yineleme aralığı tamamlandığında, çalışma zamanı iş parçacığı diğer iş parçacıklarından işi yeniden dağıtır. Ancak, bazı senaryolarda, daha iyi sorununuz için uygun olan farklı bir bölümleme mekanizması belirtmek isteyebilirsiniz.

`parallel_for`, `parallel_for_each`, Ve `parallel_transform` algoritmaları ek bir parametre alan aşırı yüklü sürümlerini sağlamanız `_Partitioner`. Bu parametre iş böler bölümleyici türü tanımlar. PPL tanımlayan bölümleyiciler türleri şunlardır:

[CONCURRENCY::affinity_partitioner](../../parallel/concrt/reference/affinity-partitioner-class.md)<br/>
Sabit sayıda aralık (genellikle döngü üzerinde çalışmak için uygun olan çalışan iş parçacığı sayısı) halinde böler çalışır. Böyle bir bölümleyici benzer `static_partitioner`, ancak önbellek benzeşim çalışan iş parçacıkları için bu eşlemeleri aralıkları yolu tarafından artırır. Bu bölümleyici türü, aynı veri kümesi birden çok kez (örneğin bir döngü bir döngü içinde) üzerinden bir döngü yürütüldükten ve veri önbellekte en uygun performansı artırabilir. Bu bölümleyici iptali tamamen yer almaz. İşbirlikçi engelleme semantiği de kullanmaz ve iletme bağımlılığı olan paralel döngüler ile kullanılamaz.

[CONCURRENCY::auto_partitioner](../../parallel/concrt/reference/auto-partitioner-class.md)<br/>
İlk bir aralığı (genellikle döngü üzerinde çalışmak için uygun olan çalışan iş parçacığı sayısı) sayısı ile böler çalışır. Çalışma zamanı alan aşırı yüklenmiş bir paralel algoritma çağırmayın, bu türü varsayılan olarak kullanır. bir `_Partitioner` parametresi. Her bir aralığı alt aralıkları ayrılabilir ve böylece gerçekleşmesi için yük dengelemeyi etkinleştirir. Bir dizi iş tamamlandığında, çalışma zamanı iş parçacığı diğer iş parçacıklarından işi alt aralığı yeniden dağıtır. İş yükünüz diğer kategorilerden birini altında düşmüyorsa ya da iptal veya birlikte engelleme için tam destek ihtiyacınız varsa bu bölümleyici kullanın.

[CONCURRENCY::simple_partitioner](../../parallel/concrt/reference/simple-partitioner-class.md)<br/>
Her bir aralığı en az belirtilen öbek boyutu tarafından belirtilen yineleme sayısını sahip olacak şekilde böler aralıkları içinde çalışır. Yük Dengeleme de bu bölümleyici türü katılır; Ancak, çalışma zamanı içinde alt aralıkları aralıkları bölünmez. Her alt çalışma zamanı iptalleri denetler ve sonra Yük Dengeleme gerçekleştirir `_Chunk_size` yinelemeler tamamlayın.

[CONCURRENCY::static_partitioner](../../parallel/concrt/reference/static-partitioner-class.md)<br/>
Sabit sayıda aralık (genellikle döngü üzerinde çalışmak için uygun olan çalışan iş parçacığı sayısı) halinde böler çalışır. İşi kaplayan kullanmaz ve bu nedenle daha az yüke sahiptir çünkü bu bölümleyici türü performansını geliştirebilirsiniz. Sabit ve Tekdüzen bir iş miktarı paralel bir döngüden her bir yinelemesini gerçekleştirir ve iptal için destek gerektirmez ya da birlikte engelleme iletmek bu bölümleyici türünü kullanın.

> [!WARNING]
>  `parallel_for_each` Ve `parallel_transform` algoritmalarını kullanan rasgele erişim yineleyicileri kapsayıcıları destekleyen (gibi std::[vektör](../../standard-library/vector-class.md)) statik, basit ve benzeşimi bölümleyiciler için. Çift yönlü ve ileriye doğru Yineleyicilerin kullanan kapsayıcıları kullanımı, bir derleme zamanı hatası oluşturur. Varsayılan bölümleyici `auto_partitioner`, yineleyici bunlardan üçünü destekler.

Genellikle, bu bölümleyiciler aynı şekilde dışında kullanılan `affinity_partitioner`. Bölümleyici türlerinin çoğu durum bilgisi bulundurmaz ve çalışma zamanı tarafından değiştirilmez. Bu nedenle aşağıdaki örnekte gösterildiği gibi çağıran sitede bu bölümleyici nesneleri oluşturabilirsiniz.

[!code-cpp[concrt-static-partitioner#1](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_8.cpp)]

Ancak, geçmesi gereken bir `affinity_partitioner` olarak olmayan bir nesne`const`, lvalue başvuru durumu yeniden kullanmak gelecekteki döngüler için algoritma depolayabilirsiniz. Aşağıdaki örnek, bir veri kümesi üzerinde aynı işlemi paralel olarak birden çok kez gerçekleştiren temel bir uygulama gösterir. Kullanımını `affinity_partitioner` dizisi önbelleğinde sığmayacak kadar büyük olasılıkla olduğu için performansı geliştirebilir.

[!code-cpp[concrt-affinity-partitioner#1](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_9.cpp)]

> [!CAUTION]
>  Kullanılacak işbirlikçi engelleme semantiği kullanan mevcut kodu değiştirirken dikkatli olun `static_partitioner` veya `affinity_partitioner`. Bu bölümleyici tür Yük Dengeleme veya aralığı çalarak kullanmayın ve bu nedenle uygulamanızın davranışını değiştirebilirsiniz.

Denemeler ve temsili yükler ve bilgisayar yapılandırmalarını altında tamamlamak için işlemleri ne kadar sürdüğünü ölçmek için bir bölümleyici herhangi belirli bir senaryoda kullanıp kullanmayacağınızı belirlemek için en iyi yolu var. Örneğin, statik bölümleme yalnızca birkaç çekirdeği olan bir çok çekirdekli bilgisayarda önemli hızlandırmayı sağlayabilir, ancak oldukça fazla çekirdeğe sahip bilgisayarlarda yavaşlamalara neden olabilir.

[[Üst](#top)]

##  <a name="parallel_sorting"></a> Paralel sıralama

PPL üç sıralama algoritmaları sağlar: [concurrency::parallel_sort](reference/concurrency-namespace-functions.md#parallel_sort), [concurrency::parallel_buffered_sort](reference/concurrency-namespace-functions.md#parallel_buffered_sort), ve [concurrency::parallel_radixsort](reference/concurrency-namespace-functions.md#parallel_radixsort). Paralel olarak sıralanmış avantaj elde edebileceği bir veri kümesine sahip olduğunuzda, bunlar algoritmaların sıralanması yararlıdır. Özellikle, paralel olarak sıralama büyük bir veri kümesine sahip olduğunuzda veya bir hesaplama açısından pahalı karşılaştırma işlemi, verileri sıralamak için kullandığınızda yararlıdır. Bu algoritmalar her yerde öğeleri sıralar.

`parallel_sort` Ve `parallel_buffered_sort` algoritmaları her iki karşılaştırma tabanlı algoritmalar şunlardır. Diğer bir deyişle, bunlar öğeleri değerle karşılaştırın. `parallel_sort` Algoritması ek bellek gereksinimi yoktur ve genel amaçlı sıralama için uygundur. `parallel_buffered_sort` Algoritması gerçekleştirebilir daha iyi `parallel_sort`, ancak O(N) alanı gereklidir.

`parallel_radixsort` Algoritmasıdır karma tabanlı. Diğer bir deyişle, öğeleri sıralamak için tamsayı anahtarları kullanır. Bu algoritma, anahtarlar kullanarak doğrudan karşılaştırmalarını kullanmak yerine, bir öğenin hedef hesaplayabilirsiniz. Gibi `parallel_buffered_sort`, bu algoritma O(N) alanı gereklidir.

Aşağıdaki tabloda, üç paralel sıralama algoritmaları önemli özelliklerini özetler.

|Algoritması|Açıklama|Sıralama mekanizması|Sıralama kararlılık|Bellek gereksinimleri|Zaman karmaşıklığı|Yineleyici erişimi|
|---------------|-----------------|-----------------------|--------------------|-------------------------|---------------------|---------------------|
|`parallel_sort`|Genel amaçlı karşılaştırma tabanlı Sırala.|(Artan karşılaştırma tabanlı)|Kararsız|Yok.|O((N/P)log(N/P) + 2N((P-1)/P))|rastgele|
|`parallel_buffered_sort`|O(N) alanı gerektiren daha hızlı genel amaçlı karşılaştırma tabanlı Sırala.|(Artan karşılaştırma tabanlı)|Kararsız|Ek O(N) alanı gereklidir|O((N/P)log(N))|rastgele|
|`parallel_radixsort`|O(N) alanı gerektiren tamsayı anahtar tabanlı Sırala.|Karma tabanlı|Kararlı|Ek O(N) alanı gereklidir|O(N/P)|rastgele|

Aşağıdaki resimde, üç paralel sıralama algoritmaları önemli özelliklerini daha grafik şeklinde gösterir.

![Sıralama algoritmaları karşılaştırması](../../parallel/concrt/media/concrt_parallel_sorting.png "sıralama algoritmaları karşılaştırması")

Bu paralel algoritmalar sıralama iptal ve özel durum işleme kurallarına izleyin. İptal ve özel durum işleme, eşzamanlılık çalışma zamanı hakkında daha fazla bilgi için bkz: [paralel algoritmaları iptal etme](../../parallel/concrt/cancellation-in-the-ppl.md#algorithms) ve [özel durum işleme](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md).

> [!TIP]
>  Bu paralel algoritmalar sıralama taşıma semantiklerini destekler. Daha verimli bir şekilde gerçekleşmesini değiştirme işlemlerini etkinleştirmek için bir taşıma atama işlecini tanımlayabilirsiniz. Taşıma semantiği ve taşıma atama işleci hakkında daha fazla bilgi için bkz: [Rvalue başvuru Bildirimcisi: & &](../../cpp/rvalue-reference-declarator-amp-amp.md), ve [taşıma oluşturucuları ve taşıma atama işleçleri (C++)](../../cpp/move-constructors-and-move-assignment-operators-cpp.md). Bir taşıma atama işleci veya takas işlevi sağlamazsanız sıralama algoritmaları kopya oluşturucusunu kullanın.

Aşağıdaki temel örnek nasıl kullanılacağını gösterir `parallel_sort` sıralamak için bir `vector` , `int` değerleri. Varsayılan olarak, `parallel_sort` kullanan [std::less](../../standard-library/less-struct.md) değerleri karşılaştırmak için.

[!code-cpp[concrt-basic-parallel-sort#1](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_10.cpp)]

Bu örnek bir özel karşılaştırma işlevi sağlamak nasıl gösterir. Kullandığı [std::complex::real](../../standard-library/complex-class.md#real) sıralanacak yöntemi [std::complex\<çift >](../../standard-library/complex-double.md) artan değerleri.

[!code-cpp[concrt-basic-parallel-sort#2](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_11.cpp)]

Bu örnek için bir karma işlevi sağlamak nasıl gösterir `parallel_radixsort` algoritması. Bu örnekte, 3B noktaları sıralar. Puanları başvuru noktası kendi mesafe göre sıralanır.

[!code-cpp[concrt-parallel-sort-points#1](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_12.cpp)]

Çizim için bu örnek, nispeten küçük bir veri kümesi kullanır. Performans geliştirmeleri ile büyük veri kümelerinde denemek için vektör başlangıç boyutunu artırabilirsiniz.

Bu örnekte bir lambda ifadesi karma işlevi olarak kullanılmaktadır. Std yerleşik uygulamaları birini de kullanabilirsiniz::[karma sınıfı](../../standard-library/hash-class.md) veya kendi özelleştirmesi tanımlayın. Bu örnekte gösterildiği gibi özel bir karma işlev nesnesi de kullanabilirsiniz:

[!code-cpp[concrt-parallel-sort-points#2](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_13.cpp)]

[!code-cpp[concrt-parallel-sort-points#3](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_14.cpp)]

Karma işlev bir tamsayı türü döndürmelidir ([std::is_integral::value](../../standard-library/is-integral-class.md) olmalıdır **true**). Böyle bir integral türüne dönüştürülebilir `size_t`.

###  <a name="choose_sort"></a> Sıralama algoritması seçme

Çoğu durumda, `parallel_sort` hız ve bellek performansı en iyi dengeyi sağlar. Veri kümeniz, kullanılabilir işlemci sayısı ve karmaşıklığı, karşılaştırma işlevi boyutu olarak artırmak ancak `parallel_buffered_sort` veya `parallel_radixsort` daha iyi gerçekleştirebilirsiniz. Belirli bir senaryoda kullanmak için hangi sıralama algoritması belirlemek için en iyi yolu, denemeler yapın ve temsili bilgisayar yapılandırmalarını altında tipik verileri sıralamak için ne kadar sürer ölçün sağlamaktır. Bir sıralama stratejisi seçtiğinizde aşağıdaki yönergeleri göz önünde bulundurun.

- Veri kümeniz boyutu. Bu belgede bir *küçük* veri kümesi, 1. 000'den az öğe içeren bir *orta* 10.000 ve 100.000 öğeleri arasında veri kümesini içeren ve *büyük* veri kümesini içeren 100. 000'den fazla öğe.

- Karşılaştırma işlevi veya karma işlevi gerçekleştiren iş miktarı.

- Kullanılabilir bilgi işlem kaynakları miktarı.

- Veri kümeniz özellikleri. Örneğin, bir algoritma da neredeyse zaten sıralanmış veriler için ancak değil de tamamen sıralanmamış olan veriler için gerçekleştirebilir.

- Öbek boyutu. İsteğe bağlı `_Chunk_size` bağımsız değişkeni belirtir, Genel sıralama daha küçük çalışma birimlerine kesen ve onun olarak ne zaman algoritmasını paralel seri sıralama uygulamasına geçer. Örneğin, 512 sağlarsanız, iş birimi 512 veya daha az öğe içerdiğinde algoritma seri uygulamasına geçer. Paralel verileri işlemek için gerekli olan ek yükü ortadan kaldırdığından seri uygulama genel performansını geliştirebilirsiniz.

Karşılaştırma işlevi veya karma işlevi görece büyük miktarda iş gerçekleştirir veya olsa bile çok sayıda kullanılabilir bilgi işlem kaynaklarına sahip küçük bir veri kümesinin paralel olarak sıralamak için faydalı olmayabilir. Kullanabileceğiniz [std::sort](../../standard-library/algorithm-functions.md#sort) küçük veri kümeleri sıralamak için işlevi. (`parallel_sort` ve `parallel_buffered_sort` çağrı `sort` veri kümesi; daha büyük öbek boyutunu belirttiğinizde ancak `parallel_buffered_sort` , kilit çekişmesini veya bellek ayırma nedeniyle ek zaman alacak O(N) alan ayırmak gerekir.)

Kilit çakışması tabidir, bellek ayırıcısı bellekten kazanacak gerekir veya kullanın `parallel_sort` orta ölçekli bir veri kümesi sıralanacak. `parallel_sort` ek boşluk gerektirir; diğer algoritmalar O(N) alan gerektirir.

Kullanım `parallel_buffered_sort` orta ölçekli veri kümeleri ve ne zaman uygulamanızı ek O(N) alanı gereksinimi karşılayan sıralanacak. `parallel_buffered_sort` çok sayıda bilgi işlem kaynakları veya pahalı bir karşılaştırma işlevi veya karma işlevi varsa, özellikle kullanışlı olabilir.

Kullanım `parallel_radixsort` büyük veri kümeleri ve ne zaman uygulamanızı ek O(N) alanı gereksinimi karşılayan sıralanacak. `parallel_radixsort` eşdeğer Karşılaştırma işleminin ne zaman daha pahalı olması veya her iki işlem pahalı olduğunda özellikle kullanışlı olabilir.

> [!CAUTION]
>  İyi bir karma işlevini uygulama, veri kümesi aralığı ve dataset içindeki her öğe için karşılık gelen işaretsiz bir değer nasıl dönüştürdüğünü bilmeniz gerekir. Karma işlemi imzasız değerler üzerinde çalıştığından, farklı bir sıralama strateji işaretsiz karma değerlerini oluşturduysa göz önünde bulundurun.

Aşağıdaki örnek performansını karşılaştırır `sort`, `parallel_sort`, `parallel_buffered_sort`, ve `parallel_radixsort` aynı büyük rastgele veri kümesine karşı.

[!code-cpp[concrt-choosing-parallel-sort#1](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_15.cpp)]

Bu örnekte, sıralama sırasında O(N) alan ayırmak için kabul edilebilir olduğunu varsayan `parallel_radixsort` bu bilgisayar yapılandırması üzerinde bu veri kümesi üzerinde en iyi gerçekleştirir.

[[Üst](#top)]

## <a name="related-topics"></a>İlgili Konular

|Başlık|Açıklama|
|-----------|-----------------|
|[Nasıl yapılır: parallel_for Döngüsü Yazma](../../parallel/concrt/how-to-write-a-parallel-for-loop.md)|Nasıl kullanılacağını gösterir `parallel_for` matris çarpım gerçekleştirmek için kullanılan algoritma.|
|[Nasıl yapılır: parallel_for_each Döngüsü Yazma](../../parallel/concrt/how-to-write-a-parallel-for-each-loop.md)|Nasıl kullanılacağını gösterir `parallel_for_each` sayısı içinde asal sayıları hesaplamak için algoritması bir [std::array](../../standard-library/array-class-stl.md) paralel nesne.|
|[Nasıl yapılır: Paralel Sıralama Rutini Yazmak için parallel_invoke Kullanma](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md)|Nasıl kullanılacağını gösterir `parallel_invoke` bitonic sıralama algoritmasının performansını artırmak için algoritma.|
|[Nasıl yapılır: Paralel İşlemleri Yürütmek için parallel_invoke Kullanma](../../parallel/concrt/how-to-use-parallel-invoke-to-execute-parallel-operations.md)|Nasıl kullanılacağını gösterir `parallel_invoke` bir paylaşılan veri kaynağı üzerinde birden çok işlem gerçekleştiren bir programın performansını artırmak için kullanılan algoritma.|
|[Nasıl yapılır: Eşleme Gerçekleştirme ve İşlemleri Paralel Olarak Azaltma](../../parallel/concrt/how-to-perform-map-and-reduce-operations-in-parallel.md)|Nasıl kullanılacağını gösterir `parallel_transform` ve `parallel_reduce` bir eşleme gerçekleştirme ve oluşumlarını dosyaları sözcükleri sayar işlemi azaltmak için algoritmalar.|
|[Paralel Desen Kitaplığı (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md)|PPL, ölçeklenebilirlik ve kolayca eş zamanlı uygulamalar geliştirmeye yönelik kullanım yükseltir kesinlik temelli bir programlama modeli sunar açıklar.|
|[PPL'de İptal](cancellation-in-the-ppl.md)|PPL, paralel işi iptal etmek nasıl ve ne zaman bir görev grubunu iptal belirleme iptal rolünü açıklar.|
|[Özel Durum İşleme](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)|Özel durum işleme eşzamanlılık çalışma zamanında rolünü açıklar.|

## <a name="reference"></a>Başvuru

[parallel_for işlevi](reference/concurrency-namespace-functions.md#parallel_for)

[parallel_for_each işlevi](reference/concurrency-namespace-functions.md#parallel_for_each)

[parallel_invoke işlevi](reference/concurrency-namespace-functions.md#parallel_invoke)

[affinity_partitioner Sınıfı](../../parallel/concrt/reference/affinity-partitioner-class.md)

[auto_partitioner Sınıfı](../../parallel/concrt/reference/auto-partitioner-class.md)

[simple_partitioner Sınıfı](../../parallel/concrt/reference/simple-partitioner-class.md)

[static_partitioner Sınıfı](../../parallel/concrt/reference/static-partitioner-class.md)

[parallel_sort işlevi](reference/concurrency-namespace-functions.md#parallel_sort)

[parallel_buffered_sort işlevi](reference/concurrency-namespace-functions.md#parallel_buffered_sort)

[parallel_radixsort işlevi](reference/concurrency-namespace-functions.md#parallel_radixsort)

