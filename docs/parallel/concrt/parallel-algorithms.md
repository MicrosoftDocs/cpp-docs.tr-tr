---
title: Paralel Algoritmalar
ms.date: 11/19/2018
helpviewer_keywords:
- parallel algorithms [Concurrency Runtime]
ms.assetid: 045dca7b-4d73-4558-a44c-383b88a28473
ms.openlocfilehash: a31787172c89e23e5eb32aa203b9f541584c0f68
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81363203"
---
# <a name="parallel-algorithms"></a>Paralel Algoritmalar

Paralel Desenler Kitaplığı (PPL), veri koleksiyonları üzerinde aynı anda çalışma gerçekleştiren algoritmalar sağlar. Bu algoritmalar C++ Standart Kitaplığı tarafından sağlananlara benzer.

Paralel algoritmalar Eşzamanlılık Çalışma Süresi'ndeki varolan işlevsellikten oluşur. Örneğin, [eşzamanlılık::parallel_for](reference/concurrency-namespace-functions.md#parallel_for) algoritması [eşzamanlılık kullanır::structured_task_group](../../parallel/concrt/reference/structured-task-group-class.md) nesnesi paralel döngü yinelemeleri gerçekleştirmek için. Algoritma `parallel_for` bölümleri, kullanılabilir bilgi işlem kaynakları nın sayısı göz önüne alındığında en uygun şekilde çalışır.

## <a name="sections"></a><a name="top"></a>Bölüm

- [parallel_for Algoritması](#parallel_for)

- [parallel_for_each Algoritması](#parallel_for_each)

- [parallel_invoke Algoritması](#parallel_invoke)

- [parallel_transform ve parallel_reduce Algoritmaları](#parallel_transform_reduce)

  - [parallel_transform Algoritması](#parallel_transform)

  - [parallel_reduce Algoritması](#parallel_reduce)

  - [Örnek: Eşme Gerçekleştirme ve Paralel Olarak Azaltma](#map_reduce_example)

- [Bölümleme Çalışmaları](#partitions)

- [Paralel Sıralama](#parallel_sorting)

  - [Sıralama Algoritması Seçme](#choose_sort)

## <a name="the-parallel_for-algorithm"></a><a name="parallel_for"></a>parallel_for Algoritması

[Eşzamanlılık::parallel_for](reference/concurrency-namespace-functions.md#parallel_for) algoritması aynı görevi tekrar tekrar paralel olarak gerçekleştirir. Bu görevlerin her biri bir yineleme değeri tarafından parametreye ayrılır. Bu algoritma, bu döngü yinelemeleri arasında kaynakları paylaşmayan bir döngü gövdesine sahip olduğunuzda yararlıdır.

Algoritma, `parallel_for` görevleri paralel yürütme için en uygun şekilde bölümlere ayırır. İş yükleri dengesiz olduğunda bu bölümleri dengelemek için bir iş çalma algoritması ve aralık çalma kullanır. Bir döngü yinelemesi birlikte bloklar, çalışma zamanı, geçerli iş parçacığına atanan yineleme aralığını diğer iş parçacıklarına veya işlemcilere yeniden dağıtır. Benzer şekilde, bir iş parçacığı bir dizi yinelemeyi tamamladığında, çalışma zamanı çalışmayı diğer iş parçacıklarından bu iş parçacığına yeniden dağıtır. Algoritma `parallel_for` iç *içe paralelliği*de destekler. Bir paralel döngü başka bir paralel döngü içeriyorsa, çalışma zamanı, döngü gövdeleri arasındaki işleme kaynaklarını paralel yürütme için etkili bir şekilde koordine eder.

Algoritmanın `parallel_for` birkaç aşırı yüklenmiş sürümü vardır. İlk sürüm bir başlangıç değeri, bir bitiş değeri ve bir iş işlevi (lambda ifadesi, işlev nesnesi veya işlev işaretçisi) alır. İkinci sürüm bir başlangıç değeri, bir bitiş değeri, adım atılabilen bir değer ve bir çalışma işlevi alır. Bu işlevin ilk sürümü adım değeri olarak 1 kullanır. Kalan sürümler, iş parçacıkları arasında bölüm aralıklarının nasıl `parallel_for` olması gerektiğini belirtmenize olanak tanıyan bölümleyici nesneleri alır. Bölümleyiciler, bu belgedeki [Bölümleme Çalışması](#partitions) bölümünde daha ayrıntılı olarak açıklanır.

Kullanmak için `for` birçok döngüyü `parallel_for`dönüştürebilirsiniz. Ancak, `parallel_for` algoritma aşağıdaki şekillerde `for` ifade farklıdır:

- Algoritma `parallel_for` `parallel_for` görevleri önceden belirlenmiş bir sırada yürütmez.

- Algoritma `parallel_for` rasgele sonlandırma koşullarını desteklemez. Yineleme `parallel_for` değişkeninin geçerli değeri `last`.

- Tür `_Index_type` parametresi integral bir tür olmalıdır. Bu integral türü imzalanabilir veya imzasız olabilir.

- Döngü yinelemesi ileri olmalıdır. Algoritma, `parallel_for` `_Step` parametre 1'den küçükse, invalid_argument [türünde](../../standard-library/invalid-argument-class.md) bir özel durum oluşturur.

- Algoritma için `parallel_for` özel durum işleme mekanizması bir `for` döngü farklıdır. Paralel döngü gövdesinde aynı anda birden çok özel durum oluşursa, çalışma zamanı `parallel_for`, . Buna ek olarak, bir döngü yineleme sayılsa, çalışma süresi genel döngüyü hemen durdurmaz. Bunun yerine, döngü iptal durumuna yerleştirilir ve çalışma zamanı henüz başlatılmış olan tüm görevleri atar. Özel durum işleme ve paralel algoritmalar hakkında daha fazla bilgi için [bkz.](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)

Algoritma `parallel_for` rasgele sonlandırma koşullarını desteklemese de, tüm görevleri durdurmak için iptali kullanabilirsiniz. İptal hakkında daha fazla bilgi için [PPL'deki İptal'e](cancellation-in-the-ppl.md)bakın.

> [!NOTE]
> Yükleme dengeleme ve iptal gibi özellikler için destekten kaynaklanan zamanlama maliyeti, özellikle döngü gövdesi nispeten küçükse, döngü gövdesini paralel olarak yürütmenin yararlarının üstesinden gelemeyebilir. Paralel döngünüzde bir bölümleyici kullanarak bu yükü en aza indirebilirsiniz. Daha fazla bilgi için, bu belgede daha sonra [Bölümleme Çalışması'na](#partitions) bakın.

### <a name="example"></a>Örnek

Aşağıdaki örnek, `parallel_for` algoritmanın temel yapısını gösterir. Bu örnek, konsola [1, 5] aralığındaki her değeri paralel olarak yazdırır.

[!code-cpp[concrt-parallel-for-structure#1](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_1.cpp)]

Bu örnek, aşağıdaki örnek çıktıyı üretir:

```Output
1 2 4 3 5
```

`parallel_for` Algoritma her öğe üzerinde paralel olarak hareket ettiği için, değerlerin konsola yazdırılma sırası değişir.

Algoritmayı `parallel_for` kullanan tam bir örnek için bkz [parallel_for.](../../parallel/concrt/how-to-write-a-parallel-for-loop.md)

[[Üst](#top)]

## <a name="the-parallel_for_each-algorithm"></a><a name="parallel_for_each"></a>parallel_for_each Algoritması

[Eşzamanlılık::parallel_for_each](reference/concurrency-namespace-functions.md#parallel_for_each) algoritması, C++ Standart Kitaplığı tarafından sağlananlar gibi yinelemeli bir kapsayıcıda görevleri paralel olarak gerçekleştirir. `parallel_for` Algoritmanın kullandığı bölümleme mantığını kullanır.

Algoritma, `parallel_for_each` algoritmanın görevleri aynı anda yürütmesi dışında `parallel_for_each` C++ Standart Kitaplığı [std::for_each](../../standard-library/algorithm-functions.md#for_each) algoritmasına benzer. Diğer paralel algoritmalar `parallel_for_each` gibi, görevleri belirli bir sırada yürütmez.

Algoritma `parallel_for_each` hem ileri yinelemeler hem de rasgele erişim yineleyicileri üzerinde çalışsa da, rasgele erişim yineleyicileri ile daha iyi performans gösterir.

### <a name="example"></a>Örnek

Aşağıdaki örnek, `parallel_for_each` algoritmanın temel yapısını gösterir. Bu örnek, konsola her değeri [bir std::dizi](../../standard-library/array-class-stl.md) nesnesi paralel olarak yazdırır.

[!code-cpp[concrt-parallel-for-each-structure#1](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_2.cpp)]

Bu örnek, aşağıdaki örnek çıktıyı üretir:

```Output
4 5 1 2 3
```

`parallel_for_each` Algoritma her öğe üzerinde paralel olarak hareket ettiği için, değerlerin konsola yazdırılma sırası değişir.

Algoritmayı `parallel_for_each` kullanan tam bir örnek için bkz [parallel_for_each.](../../parallel/concrt/how-to-write-a-parallel-for-each-loop.md)

[[Üst](#top)]

## <a name="the-parallel_invoke-algorithm"></a><a name="parallel_invoke"></a>parallel_invoke Algoritması

[Eşzamanlılık::parallel_invoke](reference/concurrency-namespace-functions.md#parallel_invoke) algoritması paralel bir dizi görev yürütür. Her görev bitene kadar dönmez. Bu algoritma, aynı anda yürütmek istediğiniz birkaç bağımsız göreviniz olduğunda yararlıdır.

Algoritma `parallel_invoke` parametreleri olarak bir dizi iş fonksiyonu (lambda işlevleri, işlev nesneleri veya işlev işaretçileri) alır. Algoritma `parallel_invoke` iki ve on parametre arasında almak için aşırı yüklenir. Geçtiğiniz her işlev `parallel_invoke` sıfır parametre almalıdır.

Diğer paralel algoritmalar `parallel_invoke` gibi, görevleri belirli bir sırada yürütmez. Görev [Paralelliği](../../parallel/concrt/task-parallelism-concurrency-runtime.md) konusu, `parallel_invoke` algoritmanın görevler ve görev gruplarıyla nasıl ilişkili olduğunu açıklar.

### <a name="example"></a>Örnek

Aşağıdaki örnek, `parallel_invoke` algoritmanın temel yapısını gösterir. Bu örnek aynı `twice` anda üç yerel değişkendeki işlevi çağırır ve sonucu konsola yazdırır.

[!code-cpp[concrt-parallel-invoke-structure#1](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_3.cpp)]

Bu örnek, aşağıdaki çıktıyı üretir:

```Output
108 11.2 HelloHello
```

Algoritmayı `parallel_invoke` kullanan tam örnekler için [bkz: Paralel Sıralama Yordamı Yazmak için parallel_invoke ve](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md) Paralel İşlemleri Yürütmek için parallel_invoke [kullanma.](../../parallel/concrt/how-to-use-parallel-invoke-to-execute-parallel-operations.md)

[[Üst](#top)]

## <a name="the-parallel_transform-and-parallel_reduce-algorithms"></a><a name="parallel_transform_reduce"></a>parallel_transform ve parallel_reduce Algoritmaları

[Eşzamanlılık::parallel_transform](reference/concurrency-namespace-functions.md#parallel_transform) ve [eşzamanlılık::parallel_reduce](reference/concurrency-namespace-functions.md#parallel_reduce) algoritmaları C++ Standart Kitaplık algoritmaları [std paralel sürümleri::transform](../../standard-library/algorithm-functions.md#transform) ve [std::accumulate](../../standard-library/numeric-functions.md#accumulate), sırasıyla. Eşzamanlılık Runtime sürümleri, paralel olarak yürütüldikleri için işlem sırasının belirlenmemesi dışında C++ Standart Kitaplığı sürümleri gibi çalışır. Performans ve ölçeklenebilirlik avantajlarından elde etmek için yeterince büyük bir kümeyle çalışırken bu algoritmaları kullanın.

> [!IMPORTANT]
> Bu `parallel_transform` `parallel_reduce` yineleyiciler kararlı bellek adresleri üretmek, çünkü ve algoritmalar yalnızca rasgele erişim, çift yönlü ve ileri yineleyicileri destekler. Ayrıca, bu yineleyiciler olmayan`const` l-değerleri üretmek gerekir.

### <a name="the-parallel_transform-algorithm"></a><a name="parallel_transform"></a>parallel_transform Algoritması

Algoritmayı `parallel transform` birçok veri paralelleştirme işlemi gerçekleştirmek için kullanabilirsiniz. Örneğin, şunları yapabilirsiniz:

- Görüntünün parlaklığını ayarlayın ve diğer görüntü işleme işlemlerini gerçekleştirin.

- İki vektör arasındaki nokta ürünlerini toplamı veya al ve vektörler üzerinde diğer sayısal hesaplamaları gerçekleştirin.

- Her yinelemenin işlenmesi gereken bir pikseli ifade ettiği 3-B ışın izleme gerçekleştirin.

Aşağıdaki örnek, algoritmayı çağırmak için kullanılan `parallel_transform` temel yapıyı gösterir. Bu örnek, bir std'nin her öğesini iki şekilde geçersiz kAkıyor:[vektör](../../standard-library/vector-class.md) nesnesi. İlk yol bir lambda ifade kullanır. İkinci yol [std kullanır::negate](../../standard-library/negate-struct.md), [std türetilmiştir::unary_function](../../standard-library/unary-function-struct.md).

[!code-cpp[concrt-basic-parallel-transform#1](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_4.cpp)]

> [!WARNING]
> Bu örnek, `parallel_transform`'nin temel kullanımını göstermektedir. İş işlevi önemli miktarda iş yapmadığından, bu örnekte performansta önemli bir artış beklenmez.

Algoritmada `parallel_transform` iki aşırı yük var. İlk aşırı yükleme bir giriş aralığı ve unary işlevi alır. Unary işlevi bir bağımsız değişken, bir işlev nesnesi veya türetilmiştir bir `unary_function`tür alan bir lambda ifadesi olabilir. İkinci aşırı yük iki giriş aralığı ve bir ikili işlev alır. İkili işlev iki bağımsız değişken, bir işlev nesnesi veya std türeyen bir tür alan bir lambda ifade [olabilir::binary_function](../../standard-library/binary-function-struct.md). Aşağıdaki örnekte bu farklılıklar gösterisin.

[!code-cpp[concrt-parallel-transform-vectors#2](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_5.cpp)]

> [!IMPORTANT]
> Çıktı `parallel_transform` için sağladığınız yineleyici, giriş yineleyicisi ile tamamen örtüşmeli veya hiç örtüşmemelidir. Giriş ve çıktı yineleyicileri kısmen çakışıyorsa, bu algoritmanın davranışı belirtilmemiştir.

### <a name="the-parallel_reduce-algorithm"></a><a name="parallel_reduce"></a>parallel_reduce Algoritması

Algoritma, `parallel_reduce` bağşör özelliğini karşılayan bir dizi işlem olduğunda yararlıdır. (Bu algoritma commutative özelliği gerektirmez.) Şunları `parallel_reduce`yapabilirsiniz:

- Matris üretmek için matris dizilerini çarpın.

- Bir vektör üretmek için matrisbir dizi ile bir vektör çarpın.

- Bir dizi dize dizisinin uzunluğunu hesapla.

- Dizeleri gibi öğelerin listesini tek bir öğede birleştirin.

Aşağıdaki temel örnek, bir `parallel_reduce` dize dizisini tek bir dize halinde birleştirmek için algoritmanın nasıl kullanılacağını gösterir. Bu temel örnekte olduğu gibi, `parallel_transform`performans kazançları bekgörememaktadır.

[!code-cpp[concrt-basic-parallel-reduce#1](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_6.cpp)]

Çoğu durumda, `parallel_reduce` `parallel_for_each` eşzamanlılık ile birlikte algoritmakullanımı için steno olarak düşünebilirsiniz::birleştirilebilir sınıf. [concurrency::combinable](../../parallel/concrt/reference/combinable-class.md)

### <a name="example-performing-map-and-reduce-in-parallel"></a><a name="map_reduce_example"></a>Örnek: Eşme Gerçekleştirme ve Paralel Olarak Azaltma

Bir *harita* işlemi, bir dizideki her değere bir işlev uygular. *Azaltma* işlemi, bir dizinin öğelerini tek bir değerde birleştirir. C++ Standart Kitaplığı [std::transform](../../standard-library/algorithm-functions.md#transform) and [std::birikerek](../../standard-library/numeric-functions.md#accumulate) haritayı gerçekleştirebilir ve işlemleri azaltabilirsiniz. Ancak, birçok sorun için, `parallel_transform` harita işlemini paralel olarak gerçekleştirmek `parallel_reduce` için algoritmayı kullanabilirsiniz ve algoritma azaltma işlemini paralel olarak gerçekleştirebilirsiniz.

Aşağıdaki örnek, asal sayıların toplamını seri ve paralel olarak hesaplamak için gereken süreyi karşılaştırır. Eşlemi aşaması asal olmayan değerleri 0'a dönüştürür ve azaltma aşaması değerleri toplamlar.

[!code-cpp[concrt-parallel-map-reduce-sum-of-primes#1](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_7.cpp)]

Bir harita gerçekleştiren ve işlemi paralel olarak azaltan başka bir örnek için [bkz.](../../parallel/concrt/how-to-perform-map-and-reduce-operations-in-parallel.md)

[[Üst](#top)]

## <a name="partitioning-work"></a><a name="partitions"></a>Bölümleme Çalışmaları

Bir işlemi veri kaynağındaki bir işlemi paralelleştirmek için, önemli bir adım, kaynağı aynı anda birden çok iş parçacığı tarafından erişilebilen birden çok bölüme *bölmektir.* Bir bölümleyici, paralel bir algoritmanın iş parçacıkları arasında bölüm aralıklarını nasıl yapması gerektiğini belirtir. Bu belgede daha önce açıklandığı gibi, PPL ilk iş yükünü oluşturan varsayılan bir bölümleme mekanizması kullanır ve daha sonra iş yükleri dengesiz olduğunda bu bölümleri dengelemek için bir iş çalma algoritması ve aralık çalma kullanır. Örneğin, bir döngü yinelemesi bir dizi yinelemeyi tamamladığında, çalışma zamanı işi diğer iş parçacıklarından bu iş parçacığına yeniden dağıtır. Ancak, bazı senaryolar için, sorununuza daha uygun olan farklı bir bölümleme mekanizması belirtmek isteyebilirsiniz.

, `parallel_for` `parallel_for_each`, `parallel_transform` ve algoritmalar ek bir parametre almak `_Partitioner`aşırı yüklü sürümleri sağlar. Bu parametre, çalışmayı bölen bölümleyici türünü tanımlar. PPL'nin tanımladığı bölümleyici türleri şunlardır:

[eşzamanlılık::affinity_partitioner](../../parallel/concrt/reference/affinity-partitioner-class.md)<br/>
Çalışmayı sabit sayıda aralıklara böler (genellikle döngü üzerinde çalışabilen alt iş parçacığı sayısı). Bu bölümleyici türü `static_partitioner`benzer, ancak alt iş parçacıkları aralıkları eşler şekilde önbellek affinity artırır. Bu bölümleyici türü, bir döngü aynı veri kümesi üzerinde birden çok kez (döngü içindeki döngü gibi) yürütüldüğünde ve veriler önbelleğe sığdığında performansı artırabilir. Bu bölümleyici iptale tam olarak katılmaz. Ayrıca kooperatif engelleme semantik kullanmaz ve bu nedenle ileri bağımlılığı olan paralel döngüler ile kullanılamaz.

[eşzamanlılık::auto_partitioner](../../parallel/concrt/reference/auto-partitioner-class.md)<br/>
Çalışmayı başlangıç aralık sayısına böler (genellikle döngü üzerinde çalışabilen alt iş parçacığı sayısı). Parametre alan `_Partitioner` aşırı yüklü paralel algoritmayı çağırmadığınızda çalışma süresi varsayılan olarak bu türü kullanır. Her aralık alt aralıklara ayrılabilir ve böylece yük dengelemenin oluşmasını sağlar. Çalışma aralığı tamamlandığında, çalışma zamanı diğer iş parçacıklarından bu iş parçacığına alt çalışma aralıklarını yeniden dağıtır. İş yükünüz diğer kategorilerden birine girmiyorsa veya iptal veya işbirliği engelleme için tam destek gerektiriyorsanız bu bölümleyiciyi kullanın.

[eşzamanlılık::simple_partitioner](../../parallel/concrt/reference/simple-partitioner-class.md)<br/>
İşi, her aralık, verilen öbek boyututarafından belirtilen yineleme sayısına sahip olacak şekilde ayırır. Bu bölümleyici türü yük dengeleme katılır; ancak, çalışma süresi aralıkları alt aralıklara bölmez. Her çalışan için çalışma zamanı iptali denetler ve `_Chunk_size` yinelemeler tamamlandıktan sonra yük dengeleme gerçekleştirir.

[eşzamanlılık::static_partitioner](../../parallel/concrt/reference/static-partitioner-class.md)<br/>
Çalışmayı sabit sayıda aralıklara böler (genellikle döngü üzerinde çalışabilen alt iş parçacığı sayısı). Bu bölümleyici türü, iş çalma yı kullanmadığından ve bu nedenle daha az yükü olduğundan performansı artırabilir. Paralel döngünün her yinelemesi sabit ve tek düze bir çalışma miktarı gerçekleştirdiğinde ve iptal veya ileri kooperatif engelleme için destek gerektirmediğinde bu bölümleyici türünü kullanın.

> [!WARNING]
> Ve algoritmalar yalnızca statik, basit ve yakınlık bölümleyicileri için rasgele erişim yineleyicileri (std:: vektör gibi) kullanan kapsayıcıları destekler.[vector](../../standard-library/vector-class.md) `parallel_for_each` `parallel_transform` Çift yönlü ve ileri yinelemekullanan kapsayıcıların kullanımı derleme zamanı hatası üretir. Varsayılan bölümleyici, `auto_partitioner`bu üç yineleyici türlerini destekler.

Genellikle, bu bölümleyiciler dışında, aynı şekilde `affinity_partitioner`kullanılır. Çoğu bölümleyici türü durumu korumaz ve çalışma süresine göre değiştirilmez. Bu nedenle, aşağıdaki örnekte gösterildiği gibi, çağrı sitesinde bu bölümleyici nesneleri oluşturabilirsiniz.

[!code-cpp[concrt-static-partitioner#1](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_8.cpp)]

Ancak, algoritmanın `affinity_partitioner` gelecekteki döngüleri`const`yeniden kullanmak için durum depolayabilmesi için bir nesneyi non- , l-değer başvurusu olarak geçirmeniz gerekir. Aşağıdaki örnek, aynı işlemi bir veri kümesi üzerinde aynı işlemi birden çok kez paralel olarak gerçekleştiren temel bir uygulamayı gösterir. Dizi önbelleğe sığacak gibi görünüyor, çünkü kullanımı `affinity_partitioner` performansı artırabilir.

[!code-cpp[concrt-affinity-partitioner#1](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_9.cpp)]

> [!CAUTION]
> Kullanılacak anlambilimi birlikte engellemeye dayanan varolan kodu değiştirirken `static_partitioner` dikkatli `affinity_partitioner`olun veya . Bu bölümleyici türleri yük dengeleme veya aralık çalma kullanmaz ve bu nedenle uygulamanızın davranışını değiştirebilir.

Belirli bir senaryoda bir bölümleyici kullanılıp kullanılmayacağını belirlemenin en iyi yolu, temsili yükler ve bilgisayar yapılandırmaları altında işlemlerin tamamlanmasının ne kadar sürdüğünü denemek ve ölçmektir. Örneğin, statik bölümleme yalnızca birkaç çekirdekli çok çekirdekli bir bilgisayarda önemli bir hız sağlayabilir, ancak nispeten çok sayıda çekirdek olan bilgisayarlarda yavaşlamalara neden olabilir.

[[Üst](#top)]

## <a name="parallel-sorting"></a><a name="parallel_sorting"></a>Paralel Sıralama

PPL üç sıralama algoritması sağlar: [eşzamanlılık::parallel_sort,](reference/concurrency-namespace-functions.md#parallel_sort) [eşzamanlılık::parallel_buffered_sort,](reference/concurrency-namespace-functions.md#parallel_buffered_sort)ve [eşzamanlılık::parallel_radixsort](reference/concurrency-namespace-functions.md#parallel_radixsort). Bu sıralama algoritmaları, paralel olarak sıralanmanın avantajını sağabilecek bir veri kümeniz olduğunda yararlıdır. Özellikle, büyük bir veri setine sahip olduğunuzda veya verilerinizi sıralamak için hesaplama açısından pahalı bir karşılaştırma işlemi kullandığınızda paralel sıralama yararlıdır. Bu algoritmaların her biri öğeleri yerinde sıralar.

`parallel_sort` Algoritmalar `parallel_buffered_sort` ve algoritmalar karşılaştırma tabanlı algoritmalardır. Diğer bir se, öğeleri değere göre karşılaştırırlar. Algoritma `parallel_sort` ek bellek gereksinimleri vardır ve genel amaçlı sıralama için uygundur. Algoritma `parallel_buffered_sort` daha `parallel_sort`iyi performans gösterebilirsiniz, ancak O(N) alanı gerektirir.

Algoritma `parallel_radixsort` karma tabanlıdır. Diğer bir deyişle, öğeleri sıralamak için tümsedo anahtarlarını kullanır. Bu algoritma, anahtarları kullanarak karşılaştırmalar kullanmak yerine bir öğenin hedefini doğrudan hesaplayabilir. Gibi `parallel_buffered_sort`, Bu algoritma O(N) alanı gerektirir.

Aşağıdaki tabloda üç paralel sıralama algoritmasının önemli özellikleri özetlenmiştir.

|Algoritma|Açıklama|Sıralama mekanizması|Sıralama Kararlılığı|Bellek gereksinimleri|Zaman Karmaşıklığı|Yineleyici erişimi|
|---------------|-----------------|-----------------------|--------------------|-------------------------|---------------------|---------------------|
|`parallel_sort`|Genel amaçlı karşılaştırma tabanlı sıralama.|Karşılaştırma tabanlı (artan)|Kararsız|None|O((N/P)log(N/P) + 2N((P-1)/P))|Rasgele|
|`parallel_buffered_sort`|O(N) alanı gerektiren daha hızlı genel amaçlı karşılaştırma tabanlı sıralama.|Karşılaştırma tabanlı (artan)|Kararsız|Ek O(N) alanı gerektirir|O((N/P)log(N))|Rasgele|
|`parallel_radixsort`|O(N) alanı gerektiren tamsayı anahtar tabanlı sıralama.|Karma tabanlı|Dengeli|Ek O(N) alanı gerektirir|O(N/P)|Rasgele|

Aşağıdaki resimde, üç paralel sıralama algoritmasının önemli özellikleri daha grafikolarak gösterilmektedir.

![Sıralama algoritmalarının karşılaştırılması](../../parallel/concrt/media/concrt_parallel_sorting.png "Sıralama algoritmalarının karşılaştırılması")

Bu paralel sıralama algoritmaları iptal ve özel durum işleme kurallarını izler. Eşzamanlılık Çalışma Zamanında iptal ve özel durum işleme hakkında daha fazla [Exception Handling](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)bilgi için [bkz.](../../parallel/concrt/cancellation-in-the-ppl.md#algorithms)

> [!TIP]
> Bu paralel sıralama algoritmaları taşıma semantiklerini destekler. Takas işlemlerinin daha verimli bir şekilde gerçekleşmesini sağlamak için bir taşıma atama işleci tanımlayabilirsiniz. Taşıma semantikleri ve taşıma atama işleci hakkında daha fazla bilgi için [Rvalue Başvuru Bildirimcisi: &&](../../cpp/rvalue-reference-declarator-amp-amp.md)ve [Taşı Oluşturucuları ve Taşıma Atama Operatörleri (C++)](../../cpp/move-constructors-and-move-assignment-operators-cpp.md)'ye bakın. Bir taşıma atama işleci veya değiştirme işlevi sağlamazsanız, sıralama algoritmaları kopya oluşturucuyu kullanır.

Aşağıdaki temel örnek, bir `parallel_sort` `vector` değeri sıralamak için nasıl kullanılacağını `int` gösterir. Varsayılan olarak, `parallel_sort` değerleri karşılaştırmak için [std::daha az](../../standard-library/less-struct.md) kullanır.

[!code-cpp[concrt-basic-parallel-sort#1](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_10.cpp)]

Bu örnek, özel bir karşılaştırma işlevinin nasıl sağlayabileceğini gösterir. [Std::complex::std](../../standard-library/complex-class.md#real) sıralamak için gerçek yöntem [kullanır::artan\<](../../standard-library/complex-double.md) sırada karmaşık çift>değerleri.

[!code-cpp[concrt-basic-parallel-sort#2](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_11.cpp)]

Bu örnek, `parallel_radixsort` algoritmaya karma işlevin nasıl sağverilebildiğini gösterir. Bu örnek, 3-B noktaları sıralar. Puanlar, referans noktasından uzaklıklarına göre sıralanır.

[!code-cpp[concrt-parallel-sort-points#1](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_12.cpp)]

Çizim için, bu örnek nispeten küçük bir veri kümesi kullanır. Daha büyük veri kümeleri üzerinde performans iyileştirmelerini denemek için vektörün ilk boyutunu artırabilirsiniz.

Bu örnekkarma işlevi olarak lambda ifadesini kullanır. Ayrıca std yerleşik uygulamalarından birini kullanabilirsiniz: karma[sınıf](../../standard-library/hash-class.md) veya kendi uzmanlık tanımlayın. Bu örnekte gösterildiği gibi özel karma işlev nesnesi de kullanabilirsiniz:

[!code-cpp[concrt-parallel-sort-points#2](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_13.cpp)]

[!code-cpp[concrt-parallel-sort-points#3](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_14.cpp)]

Karma işlevi integral türü döndürmelidir ([std::is_integral::değer](../../standard-library/is-integral-class.md) **doğru**olmalıdır). Bu integral türü türüne `size_t`dönüştürülebilir olmalıdır.

### <a name="choosing-a-sorting-algorithm"></a><a name="choose_sort"></a>Sıralama Algoritması Seçme

Çoğu durumda, `parallel_sort` hız ve bellek performansı en iyi dengeyi sağlar. Ancak, veri kümenizin boyutunu, kullanılabilir işlemci sayısını veya karşılaştırma işlevinizin karmaşıklığını `parallel_buffered_sort` `parallel_radixsort` artırdıkça veya daha iyi performans gösterebilirsiniz. Belirli bir senaryoda hangi sıralama algoritmasının kullanılacağını belirlemenin en iyi yolu, temsili bilgisayar yapılandırmaları altında tipik verileri sıralamanın ne kadar sürdüğünü denemek ve ölçmektir. Bir sıralama stratejisi seçerken aşağıdaki yönergeleri aklınızda bulundurun.

- Veri setinizin boyutu. Bu belgede, *küçük* bir veri kümesi 1.000'den az öğe, *orta* veri kümesi 10.000 ile 100.000 arasında öğe ve *büyük* bir veri kümesi 100.000'den fazla öğe içerir.

- Karşılaştırma işlevinizin veya karma işlevinizin gerçekleştirdiği çalışma miktarı.

- Kullanılabilir bilgi işlem kaynaklarının miktarı.

- Veri setinizin özellikleri. Örneğin, bir algoritma zaten neredeyse sıralanmış veriler için iyi performans gösterebilir, ancak tamamen sıralanmamış veriler için iyi performans gösteremeyebilir.

- Parça boyutu. İsteğe `_Chunk_size` bağlı bağımsız değişken, algoritmanın bir paralelden seri sıralama uygulamasına geçtiğinde genel sıralamayı daha küçük çalışma birimlerine böldüğünü belirtir. Örneğin, 512'yi sağlarsanız, bir çalışma birimi 512 veya daha az öğe içerdiğinde algoritma seri uygulamaya geçer. Seri uygulama, verileri paralel olarak işlemek için gereken ek yükü ortadan kaldırdığından genel performansı artırabilir.

Çok sayıda kullanılabilir bilgi işlem kaynağınız olsa veya karşılaştırma işleviniz veya karma işleviniz nispeten büyük miktarda iş gerçekleştirse bile, küçük bir veri kümesini paralel olarak sıralamaya değmeyebilir. Küçük veri kümelerini sıralamak için [std::sort](../../standard-library/algorithm-functions.md#sort) işlevini kullanabilirsiniz. (`parallel_sort` `parallel_buffered_sort` ve `sort` veri kümesinden daha büyük bir yığın boyutu `parallel_buffered_sort` belirttiğiniz zaman arayın; ancak, kilit çekişmesi veya bellek ayırma nedeniyle ek zaman alabilir O(N) alanı ayırmak zorunda kalacak.)

Bellek tasarrufu yapmanız gerekiyorsa veya bellek ayırıcınız kilit `parallel_sort` çekişmesine tabiyse, orta ölçekli bir veri kümesini sıralamak için kullanın. `parallel_sort`ek alan gerektirmez; diğer algoritmalar O(N) alanı gerektirir.

Orta `parallel_buffered_sort` ölçekli veri kümelerini sıralamak için ve uygulamanız ek O(N) alanı gereksinimini karşıladığında kullanın. `parallel_buffered_sort`çok sayıda bilgi işlem kaynağınız veya pahalı bir karşılaştırma işlevi veya karma işleviniz varsa, özellikle yararlı olabilir.

Büyük `parallel_radixsort` veri kümelerini sıralamak için ve uygulamanız ek O(N) alanı gereksinimini karşıladığında kullanın. `parallel_radixsort`eşdeğer karşılaştırma işlemi daha pahalı olduğunda veya her iki işlem de pahalı olduğunda özellikle yararlı olabilir.

> [!CAUTION]
> İyi bir karma işlevin uygulanması, veri kümesi aralığını ve veri kümesindeki her öğenin karşılık gelen imzalanmamış değere nasıl dönüştürüldüğünü bilmenizi gerektirir. Karma işlemi imzalanmamış değerler üzerinde çalıştığından, imzasız karma değerler üretilemiyorsa farklı bir sıralama stratejisi düşünün.

Aşağıdaki `sort`örnek, aynı `parallel_sort` `parallel_buffered_sort`büyük rasgele veri `parallel_radixsort` kümesinin performansını karşılaştırır.

[!code-cpp[concrt-choosing-parallel-sort#1](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_15.cpp)]

Sıralama sırasında O(N) alanını ayırmanın kabul edilebilir olduğunu varsayan `parallel_radixsort` bu örnekte, bu bilgisayar yapılandırmasında bu veri kümesinde en iyi performansı gösterir.

[[Üst](#top)]

## <a name="related-topics"></a>İlgili Konular

|Başlık|Açıklama|
|-----------|-----------------|
|[Nasıl yapılır: parallel_for Döngüsü Yazma](../../parallel/concrt/how-to-write-a-parallel-for-loop.md)|Matris çarpma işlemini gerçekleştirmek için algoritmanın nasıl kullanılacağını `parallel_for` gösterir.|
|[Nasıl yapılır: parallel_for_each Döngüsü Yazma](../../parallel/concrt/how-to-write-a-parallel-for-each-loop.md)|Bir std `parallel_for_each` asal sayıların sayısını hesaplamak için algoritmanın nasıl kullanılacağını [gösterir::dizi](../../standard-library/array-class-stl.md) nesnesi paralel olarak.|
|[Nasıl yapılır: Paralel Sıralama Rutini Yazmak için parallel_invoke Kullanma](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md)|Bitonik sıralama `parallel_invoke` algoritmasının performansını artırmak için algoritmanın nasıl kullanılacağını gösterir.|
|[Nasıl Kullanılır: Paralel İşlemleri Yürütmek için parallel_invoke Kullanın](../../parallel/concrt/how-to-use-parallel-invoke-to-execute-parallel-operations.md)|Paylaşılan bir veri `parallel_invoke` kaynağında birden çok işlem gerçekleştiren bir programın performansını artırmak için algoritmanın nasıl kullanılacağını gösterir.|
|[Nasıl yapılır: Eşleme Gerçekleştirme ve İşlemleri Paralel Olarak Azaltma](../../parallel/concrt/how-to-perform-map-and-reduce-operations-in-parallel.md)|Bir harita gerçekleştirmek `parallel_transform` `parallel_reduce` ve dosyalardaki sözcüklerin oluşumlarını sayan işlemi azaltmak için algoritmaların ve algoritmaların nasıl kullanılacağını gösterir.|
|[Paralel Desen Kitaplığı (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md)|Eşzamanlı uygulamalar geliştirmek için ölçeklenebilirliği ve kullanım kolaylığını destekleyen zorunlu bir programlama modeli sağlayan PPL'yi açıklar.|
|[PPL'de İptal](cancellation-in-the-ppl.md)|PPL'de iptal rolünü, paralel çalışmayı nasıl iptal edineceklerini ve görev grubunun ne zaman iptal edildiğini nasıl belirleyeceklerini açıklar.|
|[Özel Durum İşleme](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)|Eşzamanlılık Çalışma Zamanında özel durum işlemenin rolünü açıklar.|

## <a name="reference"></a>Başvuru

[parallel_for Fonksiyonu](reference/concurrency-namespace-functions.md#parallel_for)

[parallel_for_each Fonksiyonu](reference/concurrency-namespace-functions.md#parallel_for_each)

[parallel_invoke Fonksiyonu](reference/concurrency-namespace-functions.md#parallel_invoke)

[affinity_partitioner Sınıfı](../../parallel/concrt/reference/affinity-partitioner-class.md)

[auto_partitioner Sınıfı](../../parallel/concrt/reference/auto-partitioner-class.md)

[simple_partitioner Sınıfı](../../parallel/concrt/reference/simple-partitioner-class.md)

[static_partitioner Sınıfı](../../parallel/concrt/reference/static-partitioner-class.md)

[parallel_sort Fonksiyonu](reference/concurrency-namespace-functions.md#parallel_sort)

[parallel_buffered_sort Fonksiyonu](reference/concurrency-namespace-functions.md#parallel_buffered_sort)

[parallel_radixsort Fonksiyonu](reference/concurrency-namespace-functions.md#parallel_radixsort)
