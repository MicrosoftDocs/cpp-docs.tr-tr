---
title: Paralel Algoritmalar
ms.date: 11/19/2018
helpviewer_keywords:
- parallel algorithms [Concurrency Runtime]
ms.assetid: 045dca7b-4d73-4558-a44c-383b88a28473
ms.openlocfilehash: 2c9fd5bd51bfeeaa17ac6f1118798f51b93938d6
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87194504"
---
# <a name="parallel-algorithms"></a>Paralel Algoritmalar

Paralel Desenler kitaplığı (PPL), veri koleksiyonlarında eşzamanlı olarak iş yapan algoritmalar sağlar. Bu algoritmalar, C++ standart kitaplığı tarafından sağlananlara benzer.

Paralel algoritmalar Eşzamanlılık Çalışma Zamanı var olan işlevlerden oluşur. Örneğin [eşzamanlılık::p arallel_for](reference/concurrency-namespace-functions.md#parallel_for) algoritması, paralel döngü yinelemelerini gerçekleştirmek için bir [concurrency:: structured_task_group](../../parallel/concrt/reference/structured-task-group-class.md) nesnesi kullanır. `parallel_for`Algoritma bölümleri, kullanılabilir bilgi işlem kaynağı sayısına göre en iyi şekilde çalışır.

## <a name="sections"></a><a name="top"></a>Başlıklı

- [Parallel_for algoritması](#parallel_for)

- [Parallel_for_each algoritması](#parallel_for_each)

- [Parallel_invoke algoritması](#parallel_invoke)

- [Parallel_transform ve parallel_reduce algoritmaları](#parallel_transform_reduce)

  - [Parallel_transform algoritması](#parallel_transform)

  - [Parallel_reduce algoritması](#parallel_reduce)

  - [Örnek: eşleme gerçekleştirme ve paralel olarak azaltma](#map_reduce_example)

- [Bölümlendirme Işi](#partitions)

- [Paralel sıralama](#parallel_sorting)

  - [Sıralama algoritması seçme](#choose_sort)

## <a name="the-parallel_for-algorithm"></a><a name="parallel_for"></a>Parallel_for algoritması

[Eşzamanlılık::p arallel_for](reference/concurrency-namespace-functions.md#parallel_for) algoritması sürekli olarak aynı görevi paralel olarak gerçekleştirir. Bu görevlerin her biri bir yineleme değeri tarafından parametrelenir. Bu algoritma, bu döngünün yinelemeleri arasında kaynakları paylaşmayan bir döngü gövdesi olduğunda faydalıdır.

`parallel_for`Algoritma, görevleri paralel yürütme için en uygun şekilde bölümler. İş yükleri dengesiz olduğunda bu bölümleri dengelemek için bir iş hırsızlığı algoritması ve Aralık hırsızlığı kullanır. Bir döngü yinelemesi birlikte çalışırken engellediğinde, çalışma zamanı geçerli iş parçacığına diğer iş parçacıklarına veya işlemcilere atanan yineleme aralığını yeniden dağıtır. Benzer şekilde, bir iş parçacığı bir dizi yinelemeyi tamamladığında, çalışma zamanı diğer iş parçacıklarından iş parçacığına yeniden dağıtır. `parallel_for`Algoritma, *iç içe paralel paralellik*de destekler. Bir paralel döngü başka bir paralel döngü içerdiğinde, çalışma zamanı, paralel yürütme için etkin bir şekilde döngü gövdelerinin arasındaki kaynakları işlemeyi düzenler.

`parallel_for`Algoritmanın birkaç aşırı yüklü sürümü vardır. İlk sürüm bir başlangıç değeri, bir bitiş değeri ve bir çalışma işlevi (bir lambda ifadesi, işlev nesnesi veya işlev işaretçisi) alır. İkinci sürüm, bir başlangıç değeri, bir bitiş değeri, adımla bir değer ve bir çalışma işlevi alır. Bu işlevin ilk sürümü adım değeri olarak 1 kullanır. Kalan sürümler bölümleyici nesneleri alır, bu da `parallel_for` iş parçacıkları arasında aralıkların nasıl bölümlenmesi gerektiğini belirtmenize olanak tanır. Bölümleyiciler, bu belgedeki [çalışmanın bölümlenmesi](#partitions) bölümünde daha ayrıntılı bir şekilde açıklanmıştır.

Kullanılabilecek birçok döngü dönüştürebilirsiniz **`for`** `parallel_for` . Ancak, `parallel_for` algoritma **`for`** deyimden aşağıdaki yollarla farklılık gösterir:

- `parallel_for`Algoritma, `parallel_for` görevleri önceden belirlenmiş bir sırada yürütmez.

- `parallel_for`Algoritma rastgele sonlandırma koşullarını desteklemez. `parallel_for`Algoritma, yineleme değişkeninin geçerli değeri bir küçüktür olduğunda duraklar `last` .

- `_Index_type`Tür parametresi bir integral türü olmalıdır. Bu integral türü imzalanabilir veya imzasız olabilir.

- Döngü yinelemesi ileri doğru olmalıdır. `parallel_for`Parametre 1 ' den küçükse, algoritma [std:: invalid_argument](../../standard-library/invalid-argument-class.md) türünde bir özel durum oluşturur `_Step` .

- Algoritma için özel durum işleme mekanizması `parallel_for` bir **`for`** döngüden farklıdır. Bir paralel döngü gövdesinde eşzamanlı olarak birden çok özel durum oluşursa, çalışma zamanı yalnızca bir özel durumu çağıran iş parçacığına yayar `parallel_for` . Ayrıca, bir döngü yinelemesi bir özel durum oluşturduğunda, çalışma zamanı genel döngüyü hemen durdurmaz. Bunun yerine, döngü iptal edildi durumuna konur ve çalışma zamanı henüz başlatılmamış tüm görevleri atar. Özel durum işleme ve paralel algoritmalar hakkında daha fazla bilgi için bkz. [özel durum işleme](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md).

`parallel_for`Algoritma rastgele sonlandırma koşullarını desteklemese de, tüm görevleri durdurmak için iptal 'i kullanabilirsiniz. İptal hakkında daha fazla bilgi için bkz. [PPL 'de iptal](cancellation-in-the-ppl.md).

> [!NOTE]
> Yük dengelemeden kaynaklanan zamanlama maliyeti ve iptal gibi özellikler için destek, özellikle döngü gövdesi görece küçük olduğunda döngü gövdesinin paralel olarak yürütülmesi avantajlarına neden olmayabilir. Paralel döngüsünde bir bölümleyici kullanarak bu ek yükü en aza indirmenize neden olabilirsiniz. Daha fazla bilgi için bu belgede daha sonra [bölümlendirme işi](#partitions) bölümüne bakın.

### <a name="example"></a>Örnek

Aşağıdaki örnek, algoritmanın temel yapısını gösterir `parallel_for` . Bu örnek, [1, 5] aralığındaki her bir değeri paralel olarak konsola yazdırır.

[!code-cpp[concrt-parallel-for-structure#1](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_1.cpp)]

Bu örnek aşağıdaki örnek çıktıyı üretir:

```Output
1 2 4 3 5
```

`parallel_for`Algoritma her öğe için paralel olarak davrandığı için, değerlerin konsola yazdırılma sırası farklılık gösterecektir.

Algoritmasını kullanan tüm bir örnek için `parallel_for` bkz. [nasıl yapılır: parallel_for döngüsü yazma](../../parallel/concrt/how-to-write-a-parallel-for-loop.md).

[[Üst](#top)]

## <a name="the-parallel_for_each-algorithm"></a><a name="parallel_for_each"></a>Parallel_for_each algoritması

[Eşzamanlılık::p arallel_for_each](reference/concurrency-namespace-functions.md#parallel_for_each) algoritması, C++ standart kitaplığı tarafından sağlananlar gibi, bir yinelemeli kapsayıcıda, paralel olarak görevler gerçekleştirir. Algoritmanın kullandığı bölümleme mantığını kullanır `parallel_for` .

Algoritma, `parallel_for_each` görevleri eşzamanlı olarak yürütdüğünden, algoritma C++ Standart Kitaplığı [std:: for_each](../../standard-library/algorithm-functions.md#for_each) algoritmasına benzer `parallel_for_each` . Diğer paralel algoritmalar gibi, `parallel_for_each` görevleri belirli bir sırada yürütmez.

`parallel_for_each`Algoritma hem ileri yineleyiciler hem de rastgele erişim yineleyiciler üzerinde çalışabilse de rastgele erişim yineleyiciler ile daha iyi çalışır.

### <a name="example"></a>Örnek

Aşağıdaki örnek, algoritmanın temel yapısını gösterir `parallel_for_each` . Bu örnek, her bir [std:: Array](../../standard-library/array-class-stl.md) nesnesindeki her bir değeri paralel olarak konsola yazdırır.

[!code-cpp[concrt-parallel-for-each-structure#1](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_2.cpp)]

Bu örnek aşağıdaki örnek çıktıyı üretir:

```Output
4 5 1 2 3
```

`parallel_for_each`Algoritma her öğe için paralel olarak davrandığı için, değerlerin konsola yazdırılma sırası farklılık gösterecektir.

Algoritmasını kullanan tüm bir örnek için `parallel_for_each` bkz. [nasıl yapılır: parallel_for_each döngüsü yazma](../../parallel/concrt/how-to-write-a-parallel-for-each-loop.md).

[[Üst](#top)]

## <a name="the-parallel_invoke-algorithm"></a><a name="parallel_invoke"></a>Parallel_invoke algoritması

[Eşzamanlılık::p arallel_invoke](reference/concurrency-namespace-functions.md#parallel_invoke) algoritması, bir dizi görevi paralel olarak yürütür. Her görev bitene kadar döndürmez. Aynı anda yürütmek istediğiniz birkaç bağımsız göreviniz varsa, bu algoritma yararlı olur.

`parallel_invoke`Algoritma, parametreleri dizi iş işlevleri (Lambda işlevleri, işlev nesneleri veya işlev işaretçileri) olarak alır. `parallel_invoke`İki ve on parametresi arasında işlem yapmak için algoritma aşırı yüklendi. ' Ye geçirdiğiniz her işlev `parallel_invoke` sıfır parametre almalıdır.

Diğer paralel algoritmalar gibi, `parallel_invoke` görevleri belirli bir sırada yürütmez. Bu konu [Görev Paralelliği](../../parallel/concrt/task-parallelism-concurrency-runtime.md) , `parallel_invoke` algoritmaların görevlerle ve görev gruplarıyla ilişkisini açıklar.

### <a name="example"></a>Örnek

Aşağıdaki örnek, algoritmanın temel yapısını gösterir `parallel_invoke` . Bu örnek, `twice` işlevini üç yerel değişkene eşzamanlı olarak çağırır ve sonucu konsola yazdırır.

[!code-cpp[concrt-parallel-invoke-structure#1](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_3.cpp)]

Bu örnek aşağıdaki çıktıyı üretir:

```Output
108 11.2 HelloHello
```

Algoritmayı kullanan tüm örnekler için `parallel_invoke` bkz. [nasıl yapılır: paralel sıralama yordamı yazmak Için parallel_invoke kullanma](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md) ve [nasıl yapılır: paralel Işlemleri yürütmek için parallel_invoke kullanma](../../parallel/concrt/how-to-use-parallel-invoke-to-execute-parallel-operations.md).

[[Üst](#top)]

## <a name="the-parallel_transform-and-parallel_reduce-algorithms"></a><a name="parallel_transform_reduce"></a>Parallel_transform ve parallel_reduce algoritmaları

[Eşzamanlılık::p arallel_transform](reference/concurrency-namespace-functions.md#parallel_transform) ve [eşzamanlılık::p arallel_reduce](reference/concurrency-namespace-functions.md#parallel_reduce) algoritmaları, sırasıyla [std:: Transform](../../standard-library/algorithm-functions.md#transform) ve [std:: biriktir](../../standard-library/numeric-functions.md#accumulate)C++ standart kitaplığı algoritmalarının paralel sürümleridir. Eşzamanlılık Çalışma Zamanı sürümleri, paralel olarak yürütülmediği için, işlem sırası belirlenmediğinden, C++ Standart Kitaplığı sürümleri gibi davranır. Performans ve ölçeklenebilirlik avantajlarından paralel olarak işlenmesini sağlamak için yeterince büyük olan bir küme ile çalışırken bu algoritmaları kullanın.

> [!IMPORTANT]
> `parallel_transform`Ve `parallel_reduce` algoritmaları yalnızca rastgele erişimi, çift yönlü ve ileriye doğru yineleyiciler destekler çünkü bu yineleyiciler kararlı bellek adresleri oluşturur. Ayrıca, bu yineleyiciler lvalue olmayan değerler üretmelidir **`const`** .

### <a name="the-parallel_transform-algorithm"></a><a name="parallel_transform"></a>Parallel_transform algoritması

`parallel transform`Birçok veri paralelleştirme işlemini gerçekleştirmek için algoritmayı kullanabilirsiniz. Örneğin, şunları yapabilirsiniz:

- Görüntünün parlaklığını ayarlayın ve diğer görüntü işleme işlemlerini gerçekleştirin.

- İki vektör arasında nokta çarpımını toplayın veya alın ve vektörde diğer sayısal hesaplamalar gerçekleştirin.

- Her yinelemenin oluşturulması gereken bir piksele başvurduğu 3-b Ray izlemeyi gerçekleştirin.

Aşağıdaki örnek, algoritmayı çağırmak için kullanılan temel yapıyı gösterir `parallel_transform` . Bu örnek, her bir std::[Vector](../../standard-library/vector-class.md) nesnesinin öğesini iki şekilde geçersiz kılar. İlk yöntem bir lambda ifadesi kullanır. İkinci yöntem std:: [unary_function](../../standard-library/unary-function-struct.md)' den türetilen [std:: Negate](../../standard-library/negate-struct.md)kullanır.

[!code-cpp[concrt-basic-parallel-transform#1](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_4.cpp)]

> [!WARNING]
> Bu örnek, öğesinin temel kullanımını gösterir `parallel_transform` . İş işlevi önemli miktarda iş gerçekleştirmediğinden, bu örnekte performansta önemli bir artış beklenmez.

`parallel_transform`Algoritmanın iki aşırı yüklemesi vardır. İlk aşırı yükleme bir giriş aralığını ve birli işlevi alır. Birli işlev bir bağımsız değişken, bir işlev nesnesi veya öğesinden türetilen bir tür alan bir lambda ifadesi olabilir `unary_function` . İkinci aşırı yükleme iki giriş aralığını ve bir ikili işlevi alır. İkili işlev iki bağımsız değişkeni, bir işlev nesnesini veya [std:: binary_function](../../standard-library/binary-function-struct.md)türetilen bir türü alan bir lambda ifadesi olabilir. Aşağıdaki örnekte bu farklılıklar gösterilmektedir.

[!code-cpp[concrt-parallel-transform-vectors#2](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_5.cpp)]

> [!IMPORTANT]
> Çıkışı için sağladığınız Yineleyici, `parallel_transform` giriş yineleyicisini tamamen örtüşmelidir veya hiç çakışmamalıdır. Giriş ve çıkış yineleyiciler kısmen çakışırsa bu algoritmanın davranışı belirtilmemiş olur.

### <a name="the-parallel_reduce-algorithm"></a><a name="parallel_reduce"></a>Parallel_reduce algoritması

, `parallel_reduce` İlişkilendirilebilir özelliğini karşılayan bir işlem dizisine sahipseniz, algoritma faydalıdır. (Bu algoritma, Commu, özelliği gerektirmez.) İle gerçekleştirebileceğiniz işlemlerden bazıları şunlardır `parallel_reduce` :

- Matris dizileri oluşturmak için Matrislerin dizilerini çarpın.

- Vektör oluşturmak için bir matrisi bir matrisle çarpın.

- Dizeler dizisinin uzunluğunu hesaplama.

- Dizeler gibi öğelerin bir listesini tek bir öğede birleştirin.

Aşağıdaki temel örnek, bir dizi `parallel_reduce` dizeyi tek bir dizede birleştirmek için algoritmasının nasıl kullanılacağını gösterir. Örneklerde olduğu gibi `parallel_transform` , bu temel örnekte performans kazançları beklenmez.

[!code-cpp[concrt-basic-parallel-reduce#1](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_6.cpp)]

Birçok durumda,, `parallel_reduce` `parallel_for_each` algoritmanın [eşzamanlılık:: combinable](../../parallel/concrt/reference/combinable-class.md) sınıfıyla birlikte kullanılması için toplu olarak düşünebilirsiniz.

### <a name="example-performing-map-and-reduce-in-parallel"></a><a name="map_reduce_example"></a>Örnek: eşleme gerçekleştirme ve paralel olarak azaltma

*Eşleme* işlemi, dizideki her değere bir işlev uygular. Bir *azaltma* işlemi bir dizinin öğelerini tek bir değer olarak birleştirir. C++ Standart Kitaplığı [std:: Transform](../../standard-library/algorithm-functions.md#transform) ve [std:: birikme](../../standard-library/numeric-functions.md#accumulate) işlevlerini kullanarak harita gerçekleştirir ve işlemleri azaltabilirsiniz. Ancak, birçok sorun için `parallel_transform` algoritmayı kullanarak eşleme işlemini paralel olarak gerçekleştirebilir ve `parallel_reduce` algoritma, azaltma işlemini paralel olarak gerçekleştirir.

Aşağıdaki örnek, genel olarak ve paralel sayıların toplamını hesaplamak için geçen süreyi karşılaştırır. Eşleme aşaması, ana olmayan değerleri 0 olarak dönüştürür ve azaltma aşaması değerleri toplar.

[!code-cpp[concrt-parallel-map-reduce-sum-of-primes#1](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_7.cpp)]

Bir eşleme gerçekleştiren ve işlemi paralel olarak azaltan başka bir örnek için bkz. [nasıl yapılır: eşleme gerçekleştirme ve Işlemleri paralel olarak azaltma](../../parallel/concrt/how-to-perform-map-and-reduce-operations-in-parallel.md).

[[Üst](#top)]

## <a name="partitioning-work"></a><a name="partitions"></a>Bölümlendirme Işi

Bir veri kaynağındaki bir işlemi paralel hale getirmek için, temel bir adım, kaynağı birden çok iş parçacığı tarafından aynı anda erişilebilen birden çok bölüme *bölümlemesidir* . Bir bölümleyici, bir paralel algoritmanın iş parçacıkları arasında aralıkları nasıl bölümlememelidir. Bu belgede daha önce açıklandığı gibi, PPL, ilk iş yükü oluşturan bir varsayılan bölümleme mekanizması kullanır ve sonra iş yükleri dengesiz olduğunda bu bölümleri dengelemek için bir iş hırsızlığı algoritması ve Aralık hırsızlığı kullanır. Örneğin, bir döngü yinelemesi bir dizi yinelemeyi tamamladığında, çalışma zamanı diğer iş parçacıklarından iş parçacığına yeniden dağıtır. Ancak bazı senaryolarda, sorununuza daha uygun olan farklı bir bölümleme mekanizması belirtmek isteyebilirsiniz.

`parallel_for`, `parallel_for_each` Ve `parallel_transform` algoritmaları ek bir parametre alan aşırı yüklenmiş sürümler sağlar `_Partitioner` . Bu parametre, işi bölen bölümleyici türünü tanımlar. PPL 'nin tanımladığı Bölümleyiciler türleri şunlardır:

[Eşzamanlılık:: affinity_partitioner](../../parallel/concrt/reference/affinity-partitioner-class.md)<br/>
Çalışmayı sabit sayıda aralığa böler (genellikle döngüde çalışan iş parçacığı sayısı). Bu bölümleyici türü benzerdir `static_partitioner` , ancak bir yandan çalışan iş parçacıklarıyla eşleme şeklini ile önbellek benzeşimini geliştirir. Bu bölümleyici türü, bir döngü aynı veri kümesinin birden çok kez yürütüldüğü zaman (örneğin, bir döngü içindeki bir döngü gibi) ve verilerin önbelleğe sığması durumunda performansı iyileştirebilir. Bu bölümleyici, İptalde tam olarak katılmaz. Ayrıca, birlikte çalışmayan engelleme semantiğini kullanmaz ve bu nedenle ileriye dönük bağımlılığı olan paralel döngülerle kullanılamaz.

[Eşzamanlılık:: auto_partitioner](../../parallel/concrt/reference/auto-partitioner-class.md)<br/>
İşi ilk Aralık sayısına böler (genellikle döngüdeki iş parçacığı sayısı için kullanılabilir). Bir parametre alan aşırı yüklenmiş bir paralel algoritmayı çağırdığınızda, çalışma zamanı varsayılan olarak bu türü kullanır `_Partitioner` . Her Aralık alt aralıklara ayrılabilir ve bu nedenle yük dengelemenin oluşmasına izin verebilir. Çalışma aralığı tamamlandığında, çalışma zamanı diğer iş parçacıklarından iş parçacıklarını o iş parçacığına yeniden dağıtır. İş yükünüz diğer kategorilerden birine düşmezse veya iptal ya da işbirliği engelleme için tam destek istiyorsanız bu bölümleyici 'yi kullanın.

[Eşzamanlılık:: simple_partitioner](../../parallel/concrt/reference/simple-partitioner-class.md)<br/>
Çalışmayı her aralığa en az verilen öbek boyutu tarafından belirtilen yineleme sayısına sahip olacak şekilde böler. Bu bölümleyici türü yük dengelemeye katılır; Ancak çalışma zamanı, aralıkları alt aralıklara bölemez. Her çalışan için, çalışma zamanı iptal olup olmadığını denetler ve yinelemeler tamamlandıktan sonra Yük Dengeleme gerçekleştirir `_Chunk_size` .

[Eşzamanlılık:: static_partitioner](../../parallel/concrt/reference/static-partitioner-class.md)<br/>
Çalışmayı sabit sayıda aralığa böler (genellikle döngüde çalışan iş parçacığı sayısı). Bu bölümleyici türü, iş hırsızlığı kullanmadığından ve bu nedenle daha az ek yük kullandığından performansı iyileştirebilir. Paralel bir döngünün her yinelemesi sabit ve tek bir iş miktarı gerçekleştirdiğinde ve iptal veya iletme için destek gerekli değilse, bu bölümleyici türünü kullanın.

> [!WARNING]
> `parallel_for_each`Ve `parallel_transform` algoritmaları yalnızca statik, basit ve benzeşim Bölümleyiciler için rastgele erişim yineleyiciler (std::[Vector](../../standard-library/vector-class.md)gibi) kullanan kapsayıcıları destekler. Çift yönlü ve ileri yineleyiciler kullanan kapsayıcıların kullanımı, derleme zamanı hatası oluşturur. Varsayılan partitioner, `auto_partitioner` Bu Yineleyici türlerin üçünü destekler.

Genellikle, bu Bölümleyiciler, hariç olmak üzere aynı şekilde kullanılır `affinity_partitioner` . Çoğu bölümleyici türü durumu korumaz ve çalışma zamanı tarafından değiştirilmez. Bu nedenle, aşağıdaki örnekte gösterildiği gibi, bu bölümleyici nesnelerini çağrı sitesinde oluşturabilirsiniz.

[!code-cpp[concrt-static-partitioner#1](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_8.cpp)]

Ancak, `affinity_partitioner` **`const`** algoritmanın daha sonra yeniden kullanmak üzere gelecekteki döngülerin durumunu depolayabilmesi için bir nesneyi, l-Value olmayan bir başvuru olarak geçirmeniz gerekir. Aşağıdaki örnek, bir veri kümesindeki aynı işlemi paralel olarak birden çok kez gerçekleştiren temel bir uygulamayı gösterir. Öğesinin kullanımı, `affinity_partitioner` dizinin önbellekte sığması olası olduğundan performansı artırabilir.

[!code-cpp[concrt-affinity-partitioner#1](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_9.cpp)]

> [!CAUTION]
> Veya kullanmak için birlikte çalışmayan engelleme semantiğinin kullanıldığı mevcut kodu değiştirirken dikkatli olun `static_partitioner` `affinity_partitioner` . Bu bölümleyici türleri yük dengelemeyi veya Aralık çalmasını kullanmaz ve bu nedenle uygulamanızın davranışını değiştirebilir.

Belirli bir senaryoda bir bölümleyici kullanılıp kullanılmayacağını belirlemenin en iyi yolu, temsilci yükleme ve bilgisayar yapılandırması altında işlemin ne kadar sürdüğünü tamamlamaya ve ölçmeye yönelik bir yöntemdir. Örneğin, statik bölümlendirme yalnızca birkaç çekirdeğe sahip olan çok çekirdekli bir bilgisayarda önemli bir hızlı yol sunabilir, ancak nispeten fazla çekirdeğe sahip bilgisayarlarda yavaşlamalara neden olabilir.

[[Üst](#top)]

## <a name="parallel-sorting"></a><a name="parallel_sorting"></a>Paralel sıralama

PPL, üç sıralama algoritması sağlar: [eşzamanlılık::p arallel_sort](reference/concurrency-namespace-functions.md#parallel_sort), [eşzamanlılık::p arallel_buffered_sort](reference/concurrency-namespace-functions.md#parallel_buffered_sort)ve [eşzamanlılık::p arallel_radixsort](reference/concurrency-namespace-functions.md#parallel_radixsort). Bu sıralama algoritmaları, paralel olarak sıralanabilecek bir veri kümesine sahip olduğunuzda yararlıdır. Özellikle, büyük bir veri kümeniz olduğunda veya verilerinizi sıralamak için hesaplama maliyetli bir karşılaştırma işlemi kullandığınızda paralel olarak sıralama faydalıdır. Bu algoritmaların her biri öğeleri yerinde sıralar.

`parallel_sort`Ve `parallel_buffered_sort` algoritmaları hem karşılaştırma tabanlı algoritmalardır. Diğer bir deyişle, öğeleri değere göre karşılaştırırlar. `parallel_sort`Algoritmanın ek bellek gereksinimleri yoktur ve genel amaçlı sıralama için uygundur. `parallel_buffered_sort`Algoritma şundan daha iyi çalışabilir `parallel_sort` , ancak o (N) alanı gerektirir.

`parallel_radixsort`Algoritma, karma tabanlıdır. Diğer bir deyişle, öğeleri sıralamak için tamsayı anahtarları kullanır. Anahtarlar kullanılarak bu algoritma, karşılaştırmaları kullanmak yerine bir öğenin hedefini doğrudan hesaplamanızı sağlayabilir. Benzer şekilde `parallel_buffered_sort` , bu algoritma O (N) alanını gerektirir.

Aşağıdaki tabloda, üç paralel sıralama algoritmalarının önemli özellikleri özetlenmektedir.

|Algoritma|Açıklama|Sıralama mekanizması|Kararlılığı Sırala|Bellek gereksinimleri|Zaman karmaşıklığı|Yineleyici erişimi|
|---------------|-----------------|-----------------------|--------------------|-------------------------|---------------------|---------------------|
|`parallel_sort`|Genel amaçlı karşılaştırma tabanlı sıralama.|Karşılaştırma tabanlı (artan)|Gelmesine|Hiçbiri|O ((N/P) günlüğü (N/P) + 2N ((P-1)/P))|Rastgele|
|`parallel_buffered_sort`|O (N) alanı gerektiren daha hızlı genel amaçlı karşılaştırma tabanlı sıralama.|Karşılaştırma tabanlı (artan)|Gelmesine|Ek O (N) alanı gerektirir|O ((N/P) günlük (N))|Rastgele|
|`parallel_radixsort`|O (N) alanı gerektiren tamsayı anahtar tabanlı sıralama.|Karma tabanlı|Dengeli|Ek O (N) alanı gerektirir|O (N/P)|Rastgele|

Aşağıdaki çizimde üç paralel sıralama algoritmalarının önemli özellikleri grafik olarak gösterilmektedir.

![Sıralama algoritmalarının karşılaştırması](../../parallel/concrt/media/concrt_parallel_sorting.png "Sıralama algoritmalarının karşılaştırması")

Bu paralel sıralama algoritmaları, iptal ve özel durum işleme kurallarını izler. Eşzamanlılık Çalışma Zamanı iptal ve özel durum işleme hakkında daha fazla bilgi için bkz. [paralel algoritmaları](../../parallel/concrt/cancellation-in-the-ppl.md#algorithms) ve [özel durum işlemeyi](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)iptal etme.

> [!TIP]
> Bu paralel sıralama algoritmaları, taşıma semantiğini destekler. Değiştirme işlemlerinin daha verimli gerçekleşmesini sağlamak için bir taşıma atama işleci tanımlayabilirsiniz. Taşıma semantiği ve taşıma atama işleci hakkında daha fazla bilgi için bkz. [rvalue başvuru bildirimci:  &&](../../cpp/rvalue-reference-declarator-amp-amp.md)ve [Taşıma Oluşturucuları ve taşıma atama işleçleri (C++)](../../cpp/move-constructors-and-move-assignment-operators-cpp.md). Bir Move atama işleci veya swap işlevi sağlamazsanız sıralama algoritmaları kopya oluşturucuyu kullanır.

Aşağıdaki temel örnek, `parallel_sort` bir değer sıralamak için nasıl kullanılacağını gösterir `vector` **`int`** . Varsayılan olarak, `parallel_sort` değerleri karşılaştırmak için [std:: less](../../standard-library/less-struct.md) kullanır.

[!code-cpp[concrt-basic-parallel-sort#1](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_10.cpp)]

Bu örnek, nasıl özel bir karşılaştırma işlevinin sağlanması gerektiğini gösterir. [Std:: Complex \<double> ](../../standard-library/complex-double.md) değerlerini artan düzende sıralamak için [std:: Complex:: Real](../../standard-library/complex-class.md#real) yöntemini kullanır.

[!code-cpp[concrt-basic-parallel-sort#2](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_11.cpp)]

Bu örnek, algoritmaya nasıl bir karma işlevi sağlayacağınızı gösterir `parallel_radixsort` . Bu örnek 3-b noktaları sıralar. Noktaları, bir başvuru noktasından uzaklığına göre sıralanır.

[!code-cpp[concrt-parallel-sort-points#1](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_12.cpp)]

Çizim için bu örnek görece küçük bir veri kümesi kullanır. Daha büyük veri kümeleri üzerinde performans iyileştirmeleri ile denemeler yapmak için vektör başlangıç boyutunu artırabilirsiniz.

Bu örnek, karma işlevi olarak bir lambda ifadesi kullanır. Std::[hash sınıfının](../../standard-library/hash-class.md) yerleşik uygulamalarından birini de kullanabilir veya kendi uzmanlarınızı tanımlayabilirsiniz. Ayrıca, aşağıdaki örnekte gösterildiği gibi özel bir karma işlev nesnesi de kullanabilirsiniz:

[!code-cpp[concrt-parallel-sort-points#2](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_13.cpp)]

[!code-cpp[concrt-parallel-sort-points#3](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_14.cpp)]

Karma işlevi bir integral türü döndürmelidir ([std:: is_integral:: değer](../../standard-library/is-integral-class.md) olmalıdır **`true`** ). Bu integral türü türüne dönüştürülebilir olmalıdır `size_t` .

### <a name="choosing-a-sorting-algorithm"></a><a name="choose_sort"></a>Sıralama algoritması seçme

Çoğu durumda, `parallel_sort` hız ve bellek performansının en iyi dengesini sağlar. Ancak, veri kümesi boyutunu, kullanılabilir işlemcilerin sayısını veya karşılaştırma işlevinizin karmaşıklığını artırdıkça `parallel_buffered_sort` veya `parallel_radixsort` daha iyi bir performans sağlayabilirsiniz. Belirli bir senaryoda kullanılacak sıralama algoritmasının belirlenmesi için en iyi yol, temsilci bilgisayar yapılandırmalarında tipik verileri sıralama süresinin ne kadar sürdüğünü belirlemektir ve ölçmektedir. Sıralama stratejisi seçerken aşağıdaki yönergeleri aklınızda bulundurun.

- Veri kümesi boyutu. Bu belgede, *küçük* bir veri kümesi 1.000 'den daha az öğe içeriyor, *Orta* bir veri kümesi 10.000 ve 100.000 öğelerini içerir ve *büyük* bir veri kümesi, 100.000 ' ten fazla öğe içerir.

- Karşılaştırma işleviniz veya karma işlevinizin gerçekleştirdiği iş miktarı.

- Kullanılabilir bilgi işlem kaynakları miktarı.

- Veri kümesi özellikleri. Örneğin, bir algoritma zaten neredeyse sıralanan veriler için iyi bir şekilde sıralanabilir, ancak tamamen sıralanmamış olan veriler için iyi bir işlem yapabilir.

- Öbek boyutu. İsteğe bağlı `_Chunk_size` bağımsız değişken, genel sıralamayı daha küçük iş birimlerine bölmek için algoritmanın ne zaman paralel bir seri sıralama uygulamasına geçiş yaptığı belirtir. Örneğin, 512 belirtirseniz, bir iş birimi 512 veya daha az öğe içerdiğinde algoritma seri uygulamaya geçer. Seri uygulama, verileri paralel olarak işlemek için gereken ek yükü ortadan kaldırdığı için genel performansı iyileştirebilir.

Çok sayıda kullanılabilir bilgi işlem kaynağınız olduğunda veya karşılaştırma işleviniz ya da karma işleviniz görece büyük bir iş gerçekleştirdiğinde bile küçük bir veri kümesinin paralel olarak sıralanması çok uzun olabilir. Küçük veri kümelerini sıralamak için [std:: Sort](../../standard-library/algorithm-functions.md#sort) işlevini kullanabilirsiniz. ( `parallel_sort` ve `parallel_buffered_sort` `sort` veri kümesinden daha büyük bir öbek boyutu belirttiğinizde çağırın; ancak, `parallel_buffered_sort` kilit çakışması veya bellek ayırma nedeniyle daha fazla zaman alan bir O (N) alanı ayırması gerekir.)

Bellek tasarrufu yapmanız gerekiyorsa veya bellek ayırıcı kilitleme çekişmesine tabidir, `parallel_sort` Orta ölçekli bir veri kümesini sıralamak için kullanın. `parallel_sort`ek boşluk gerekmez; diğer algoritmalar O (N) alanı gerektirir.

`parallel_buffered_sort`Orta ölçekli veri kümelerini ve uygulamanız ek O (N) alanı gereksinimini karşılıyorsa sıralamak için kullanın. `parallel_buffered_sort`özellikle çok sayıda bilgi işlem kaynağınız veya pahalı bir karşılaştırma işlevi ya da karma işleviniz olduğunda yararlı olabilir.

`parallel_radixsort`Büyük veri kümelerini sıralamak ve uygulamanız ek O (N) alanı gereksinimini karşılıyorsa kullanın. `parallel_radixsort`Özellikle eşdeğer karşılaştırma işlemi daha pahalı olduğunda veya her iki işlem de pahalı olduğunda yararlı olabilir.

> [!CAUTION]
> İyi bir karma işlevi uygulamak için veri kümesi aralığını ve veri kümesindeki her bir öğenin karşılık gelen bir işaretsiz değere nasıl dönüştürüleceğini bilmeniz gerekir. Karma işlemi imzasız değerler üzerinde çalıştığından, imzasız karma değerleri üretilemediğinden farklı bir sıralama stratejisi düşünün.

Aşağıdaki örnek,,, ve performansını `sort` `parallel_sort` `parallel_buffered_sort` `parallel_radixsort` aynı büyük rastgele veri kümesiyle karşılaştırır.

[!code-cpp[concrt-choosing-parallel-sort#1](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_15.cpp)]

Bu örnekte, sıralama sırasında O (N) alanı ayırmak için kabul edilebilir olduğunu varsayan bu, bu `parallel_radixsort` bilgisayar yapılandırmasında bu veri kümesinde en iyi şekilde çalışır.

[[Üst](#top)]

## <a name="related-topics"></a>İlgili Konular

|Başlık|Açıklama|
|-----------|-----------------|
|[Nasıl yapılır: parallel_for döngüsü yazma](../../parallel/concrt/how-to-write-a-parallel-for-loop.md)|`parallel_for`Algoritmanın matris çarpma işlemi gerçekleştirmek için nasıl kullanılacağını gösterir.|
|[Nasıl yapılır: parallel_for_each döngüsü yazma](../../parallel/concrt/how-to-write-a-parallel-for-each-loop.md)|`parallel_for_each`Bir [std:: Array](../../standard-library/array-class-stl.md) nesnesindeki asal sayıların sayısını paralel olarak hesaplamak için algoritmasının nasıl kullanılacağını gösterir.|
|[Nasıl yapılır: paralel sıralama yordamı yazmak için parallel_invoke kullanma](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md)|`parallel_invoke`Bitonic sıralama algoritmasının performansını artırmak için algoritmasının nasıl kullanılacağını gösterir.|
|[Nasıl yapılır: paralel Işlemleri yürütmek için parallel_invoke kullanma](../../parallel/concrt/how-to-use-parallel-invoke-to-execute-parallel-operations.md)|Bir `parallel_invoke` paylaşılan veri kaynağı üzerinde birden çok işlemi gerçekleştiren bir programın performansını artırmak için algoritmasının nasıl kullanılacağını gösterir.|
|[Nasıl yapılır: eşleme gerçekleştirme ve Işlemleri paralel olarak azaltma](../../parallel/concrt/how-to-perform-map-and-reduce-operations-in-parallel.md)|`parallel_transform` `parallel_reduce` Bir harita gerçekleştirmek ve dosyalardaki sözcüklerin tekrarlamalarını sayan işlemi azaltmak için ve algoritmaların nasıl kullanılacağını gösterir.|
|[Paralel Desen Kitaplığı (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md)|Eşzamanlı uygulamalar geliştirmek için ölçeklenebilirliği ve kullanım kolaylığını kolaylaştıran bir zorunlu programlama modeli sağlayan PPL 'yi açıklar.|
|[PPL'de İptal](cancellation-in-the-ppl.md)|PPL 'de iptal etme rolünü, paralel çalışmayı iptal etmeyi ve bir görev grubunun ne zaman iptal edildiğini belirleme işlemini açıklar.|
|[Özel Durum İşleme](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)|Eşzamanlılık Çalışma Zamanı özel durum işlemenin rolünü açıklar.|

## <a name="reference"></a>Başvuru

[parallel_for Işlevi](reference/concurrency-namespace-functions.md#parallel_for)

[parallel_for_each Işlevi](reference/concurrency-namespace-functions.md#parallel_for_each)

[parallel_invoke Işlevi](reference/concurrency-namespace-functions.md#parallel_invoke)

[affinity_partitioner sınıfı](../../parallel/concrt/reference/affinity-partitioner-class.md)

[auto_partitioner Sınıfı](../../parallel/concrt/reference/auto-partitioner-class.md)

[simple_partitioner sınıfı](../../parallel/concrt/reference/simple-partitioner-class.md)

[static_partitioner sınıfı](../../parallel/concrt/reference/static-partitioner-class.md)

[parallel_sort Işlevi](reference/concurrency-namespace-functions.md#parallel_sort)

[parallel_buffered_sort Işlevi](reference/concurrency-namespace-functions.md#parallel_buffered_sort)

[parallel_radixsort Işlevi](reference/concurrency-namespace-functions.md#parallel_radixsort)
