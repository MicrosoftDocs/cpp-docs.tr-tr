---
title: Paralel algoritmalar | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- parallel algorithms [Concurrency Runtime]
ms.assetid: 045dca7b-4d73-4558-a44c-383b88a28473
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 365acd15c61b52631fc75018ab4c3a017d3eed8f
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
---
# <a name="parallel-algorithms"></a>Paralel Algoritmalar
Paralel Desen kitaplığı (PPL) eşzamanlı olarak veri koleksiyonlar üzerinde çalışmayı gerçekleştirmek algoritmaları sağlar. Bu algoritmalar C++ Standart Kitaplığı tarafından sağlanan benzer.  
  

 Paralel algoritmalar eşzamanlılık çalışma zamanı varolan işlevsellikte öğesinden oluşur. Örneğin, [concurrency::parallel_for](reference/concurrency-namespace-functions.md#parallel_for) algoritması kullanan bir [concurrency::structured_task_group](../../parallel/concrt/reference/structured-task-group-class.md) paralel döngüsü yinelemeleri gerçekleştirmek için nesne. `parallel_for` Algoritması bölümleri bilgi işlem kaynakları kullanılabilir sayısı verilen bir en iyi şekilde çalışır.  

  
##  <a name="top"></a> Bölümler  
  
- [Parallel_for algoritması](#parallel_for)  
  
- [Parallel_for_each algoritması](#parallel_for_each)  
  
- [Parallel_invoke algoritması](#parallel_invoke)  
  
- [Parallel_transform ve parallel_reduce algoritmaları](#parallel_transform_reduce)  
  
    - [Parallel_transform algoritması](#parallel_transform)  
  
    - [Parallel_reduce algoritması](#parallel_reduce)  
  
    - [Örnek: Eşleme gerçekleştirme ve paralel olarak azaltma](#map_reduce_example)  
  
- [Bölümleme çalışma](#partitions)  
  
- [Paralel sıralama](#parallel_sorting)  
  
    - [Sıralama algoritması seçme](#choose_sort)  
  
##  <a name="parallel_for"></a> Parallel_for algoritması  

 [Concurrency::parallel_for](reference/concurrency-namespace-functions.md#parallel_for) algoritmasını paralel olarak sürekli olarak aynı görevi gerçekleştirir. Bu görevlerin her birini bir yineleme değeriyle parametrelenmiş. Bu algoritma, kaynakları bu döngü yinelemelerini arasında paylaşmaz bir döngü gövdesine sahip yararlıdır.  
  
 `parallel_for` Algoritmasını Paralel yürütme için iyi bir şekilde görevleri bölümler. Bir iş çalarak algoritması ve iş yükleri dengesiz olduğunda bu bölümler dengelemek için çalarak aralığı kullanır. Bir döngü tekrarında işlevinizde engellediğinde çalışma zamanı, geçerli iş parçacığının başka iş parçacıkları veya işlemciler atandığı yineleme aralığı yeniden dağıtır. Benzer şekilde, bir iş parçacığı yineleme aralığı tamamlandığında, çalışma zamanının o iş parçacığı diğer iş parçacıklarından işi yeniden dağıtır. `parallel_for` Algoritma da destekler *paralellik iç içe geçmiş*. Paralel bir döngüden başka bir paralel döngü içeriyorsa, çalışma zamanı işlem kaynakları arasında döngü gövdelerini Paralel yürütme için verimli bir şekilde düzenler.  
  
 `parallel_for` Algoritmasına sahip birden fazla aşırı yüklenmiş sürümleri. İlk sürüm başlangıç değeri, bir bitiş değeri ve bir iş işlevi (bir lambda ifadesi, işlev nesnesi veya işlev işaretçisi) alır. İkinci Sürüm başlangıç değeri, bir bitiş değeri, bir değer olarak adım ve iş işlevi alır. Bu işlevin ilk sürüm 1. adım değeri olarak kullanır. Kalan sürümleri belirtmenizi sağlayan bölümleyici nesneleri ele nasıl `parallel_for` aralıkları iş parçacıkları arasında bölüm. Bölümleyiciler bölümünde daha ayrıntılı açıklanmıştır [bölümleme iş](#partitions) bu belgedeki.  
  
 Birçok dönüştürebilirsiniz `for` kullanılacak döngüler `parallel_for`. Ancak, `parallel_for` algoritması farklı olarak `for` deyimi aşağıdaki yollarla:  
  
-   `parallel_for` Algoritması `parallel_for` görevleri önceden belirlenmiş bir sırayla yürütmez.  
  
-   `parallel_for` Algoritması rasgele sonlandırma koşulları desteklemez. `parallel_for` Algoritması durdurur yineleme değişkeni geçerli değeri bir olduğunda değerinden `last`.  
  
-   `_Index_type` Tür parametresi bir tamsayı türünde olması gerekir. Bu tamsayı türü imzalanmış veya imzalanmamış.  
  
-   Döngü tekrarında ileriye doğru olması gerekir. `parallel_for` Algoritması türünde bir özel durum atar [std::invalid_argument](../../standard-library/invalid-argument-class.md) varsa `_Step` 1'den küçük bir parametredir.  
  
-   Özel durum işleme mekanizma `parallel_for` algoritması farklı bir `for` döngü. Paralel döngü gövdesine aynı anda birden çok özel durumlar meydana gelirse, çalışma zamanı özel durumlar çağıran iş parçacığının yalnızca biri yayar `parallel_for`. Ayrıca, bir döngü tekrarında bir özel durum oluşturduğunda, çalışma zamanı genel döngü hemen durdurmaz. Bunun yerine, döngü iptal edilmiş durumda yerleştirilir ve çalışma zamanı henüz başlatılmamış herhangi bir görevi atar. Özel durum işleme ve paralel algoritmalar hakkında daha fazla bilgi için bkz: [özel durum işleme](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md).  
  
 Ancak `parallel_for` algoritması rasgele sonlandırma koşulları desteklemiyor, tüm görevler durdurmak için İptal'i kullanabilirsiniz. İptal etme hakkında daha fazla bilgi için bkz: [PPL'de iptal](cancellation-in-the-ppl.md).  
  
> [!NOTE]
>  Yük Dengeleme ve iptal etme gibi özellikleri için destek sonuçlarından döngü gövdesine Paralel yürütme avantajlarını üstesinden değil, zamanlama maliyeti, özellikle döngü gövdesine nispeten küçük olduğunda. Paralel döngünüzde bir bölümleyici kullanarak bu yükünü en aza indirebilirsiniz. Daha fazla bilgi için bkz: [bölümleme iş](#partitions) belgesinde.  
  
### <a name="example"></a>Örnek  
 Aşağıdaki örnek, temel yapısını gösterir `parallel_for` algoritması. Bu örnek paralel aralığı [1, 5] içindeki her değerin konsola yazdırır.  
  
 [!code-cpp[concrt-parallel-for-structure#1](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_1.cpp)]  
  
 Bu örnekte aşağıdaki örnek çıkışı üretir:  
  
```Output  
1 2 4 3 5  
```  
  
 Çünkü `parallel_for` algoritması davranır her öğeye paralel, değerleri konsola yazdırılır sipariş farklılık gösterir.  
  
 Kullanan tam bir örnek için `parallel_for` algoritması bkz [nasıl yapılır: parallel_for döngüsü yazma](../../parallel/concrt/how-to-write-a-parallel-for-loop.md).  
  
 [[Üst](#top)]  
  
##  <a name="parallel_for_each"></a> Parallel_for_each algoritması  

 [Concurrency::parallel_for_each](reference/concurrency-namespace-functions.md#parallel_for_each) algoritmasını paralel C++ Standart Kitaplığı tarafından sağlananlar gibi bir yinelemeli kapsayıcısı üzerinde görevleri gerçekleştirir. Aynı bölümleme mantığını kullanır, `parallel_for` algoritması kullanır.  
  
 `parallel_for_each` Algoritması benzer C++ Standart Kitaplığı [std::for_each](../../standard-library/algorithm-functions.md#for_each) hariç algoritması `parallel_for_each` algoritması görevler eşzamanlı olarak yürütür. Gibi diğer paralel algoritmalar `parallel_for_each` görevleri belirli bir sırada yürütmez.  
  
 Ancak `parallel_for_each` algoritması çalışır iletme yineleyiciler hem rastgele erişim yineleyiciler, rastgele erişim yineleyiciler ile daha iyi gerçekleştirir.  
  
### <a name="example"></a>Örnek  
 Aşağıdaki örnek, temel yapısını gösterir `parallel_for_each` algoritması. Bu örnekte yer alan her değerin konsola yazdırır bir [std::array](../../standard-library/array-class-stl.md) paralel nesne.  
  
 [!code-cpp[concrt-parallel-for-each-structure#1](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_2.cpp)]  
  
 Bu örnekte aşağıdaki örnek çıkışı üretir:  
  
```Output  
4 5 1 2 3  
```  
  
 Çünkü `parallel_for_each` algoritması davranır her öğeye paralel, değerleri konsola yazdırılır sipariş farklılık gösterir.  
  
 Kullanan tam bir örnek için `parallel_for_each` algoritması bkz [nasıl yapılır: parallel_for_each döngüsü yazma](../../parallel/concrt/how-to-write-a-parallel-for-each-loop.md).  
  
 [[Üst](#top)]  
  
##  <a name="parallel_invoke"></a> Parallel_invoke algoritması  

 [Concurrency::parallel_invoke](reference/concurrency-namespace-functions.md#parallel_invoke) algoritmasını paralel olarak bir dizi görevi çalıştırır. Her görev bitene kadar döndürmez. Bu algoritma, aynı anda çalıştırmak istediğiniz birkaç bağımsız görevleri sahip yararlıdır.  
  
 `parallel_invoke` Algoritması iş işlevleri (lambda işlevleri, işlev nesneleri veya işlev işaretçileri) bir dizi alt parametreler olarak alır. `parallel_invoke` Algoritması aşırı yüklenmiş iki ve on parametreleri arasında gerçekleştirilecek. Geçirdiğiniz her işlev `parallel_invoke` sıfır parametresi almalıdır.  
  
 Gibi diğer paralel algoritmalar `parallel_invoke` görevleri belirli bir sırada yürütmez. Konu [görev Paralelliği](../../parallel/concrt/task-parallelism-concurrency-runtime.md) açıklar nasıl `parallel_invoke` algoritması ilişkili görevleri ve görev grupları.  
  
### <a name="example"></a>Örnek  
 Aşağıdaki örnek, temel yapısını gösterir `parallel_invoke` algoritması. Bu örnek aynı anda çağırır `twice` işlevi üç yerel değişkenleri ve sonucun konsola yazdırır.  
  
 [!code-cpp[concrt-parallel-invoke-structure#1](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_3.cpp)]  
  
 Bu örnek şu çıkışı üretir:  
  
```Output  
108 11.2 HelloHello  
```  
  
 Kullanan tüm örnekleri için `parallel_invoke` algoritması bkz [nasıl yapılır: paralel sıralama rutini yazmak için parallel_invoke kullanma](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md) ve [nasıl yapılır: paralel işlemleri yürütmek için parallel_invoke kullanma](../../parallel/concrt/how-to-use-parallel-invoke-to-execute-parallel-operations.md).  
  
 [[Üst](#top)]  
  
##  <a name="parallel_transform_reduce"></a> Parallel_transform ve parallel_reduce algoritmaları  

 [Concurrency::parallel_transform](reference/concurrency-namespace-functions.md#parallel_transform) ve [concurrency::parallel_reduce](reference/concurrency-namespace-functions.md#parallel_reduce) algoritmaları C++ Standart Kitaplığı algoritmaları paralel sürümleri şunlardır [std::transform](../../standard-library/algorithm-functions.md#transform)ve [std::accumulate](../../standard-library/numeric-functions.md#accumulate)sırasıyla. Paralel olarak yürüttüğünden işlem sırası belirlenmez dışında eşzamanlılık çalışma zamanı sürümlerini C++ standart kitaplık sürümleri gibi davranır. Paralel olarak işlenen performans ve ölçeklenebilirlik avantajlarını almak için büyük bir küme ile çalışırken bu algoritmalar kullanın.  
  
> [!IMPORTANT]
>  `parallel_transform` Ve `parallel_reduce` algoritmaları desteği yalnızca rasgele erişim, çift yönlü ve iletme yineleyiciler bu yineleyiciler kararlı bellek adresleri üretmek için. Ayrıca, bu yineleyiciler olmayan oluşturabilir gerekir`const` l değerleri.  
  
###  <a name="parallel_transform"></a> Parallel_transform algoritması  
 Kullanabileceğiniz `parallel transform` birçok veri paralelleştirme işlemleri gerçekleştirmeye algoritması. Örneğin, şunları yapabilirsiniz:  
  
-   Bir görüntü parlaklığını ve diğer görüntü işleme işlemleri gerçekleştirebilir.  
  
-   Sum veya iki vektör arasında nokta ürün ayırın ve diğer vektörlerinin üzerinde sayısal hesaplamalar.  
  
-   3-b ray izleme, burada her bir yineleme oluşturulması gereken bir piksel başvuruyor gerçekleştirin.  
  
 Aşağıdaki örnek, çağırmak için kullanılan temel yapı gösterir `parallel_transform` algoritması. Bu örnek bir std her öğeye üzerindeki geçersiz kılar::[vektör](../../standard-library/vector-class.md) iki yolla nesnesi. İlk yol lambda ifadesi kullanır. İkinci yol kullanan [std::negate](../../standard-library/negate-struct.md), den türetilen [std::unary_function](../../standard-library/unary-function-struct.md).  
  
 [!code-cpp[concrt-basic-parallel-transform#1](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_4.cpp)]  
  
> [!WARNING]
>  Bu örnek temel kullanımını gösteren `parallel_transform`. İş işlevi önemli miktarda iş gerçekleştirmez olduğundan, bu örnekte, performansı önemli bir artışa beklenmiyor.  
  
 `parallel_transform` İki aşırı algoritmaya sahiptir. İlk aşırı bir giriş aralığı ve birli işlevi alır. Birli işlevi bir bağımsız değişken, bir işlev nesnesi veya türeyen bir tür alan lambda ifadesi olabilir `unary_function`. İkinci aşırı iki giriş aralıkları ve ikili bir işlevi alır. İkili işlevi, iki bağımsız değişken, bir işlev nesnesi veya türeyen bir tür geçen lambda ifadesi olabilir [std::binary_function](../../standard-library/binary-function-struct.md). Aşağıdaki örnekte bu farklar gösterilmektedir.  
  
 [!code-cpp[concrt-parallel-transform-vectors#2](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_5.cpp)]  
  
> [!IMPORTANT]
>  Çıktısı için sağladığınız yineleyici `parallel_transform` tamamen giriş yineleyici üst üste veya hiç çakışmaması gerekir. Bu algoritma davranışını giriş ve çıkış yineleyiciler kısmen çakışırsa belirtilmedi.  
  
###  <a name="parallel_reduce"></a> Parallel_reduce algoritması  
 `parallel_reduce` Algoritması, bir dizi ilişkilendirilebilir özelliği karşılamak işlem olduğunda yararlıdır. (Bu algoritmayı yer değiştirebilme özelliğini gerektirmez.) Bazı ile gerçekleştirebileceğiniz işlemlerin `parallel_reduce`:  
  
-   Bir matris üretmek için matrisleri dizilerini çarpın.  
  
-   Vektör matrisleri vektör üretmek için bir dizi tarafından çarpın.  
  
-   Bir dizi dize uzunluğu işlem.  
  
-   Dizeler gibi öğelerin listesini tek bir öğede birleştirin.  
  
 Aşağıdaki temel örnek nasıl kullanılacağını gösterir `parallel_reduce` bir dizeler dizisi bir dize halinde birleştirmek için algoritması. Örneklerde olduğu gibi `parallel_transform`, performans artışı temel Bu örnekte beklendiği.  
  
 [!code-cpp[concrt-basic-parallel-reduce#1](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_6.cpp)]  
  
 Çoğu durumda, düşünebilirsiniz `parallel_reduce` kullanımı için toplu olarak `parallel_for_each` algoritması ile birlikte [concurrency::combinable](../../parallel/concrt/reference/combinable-class.md) sınıfı.  
  
###  <a name="map_reduce_example"></a> Örnek: Eşleme gerçekleştirme ve paralel olarak azaltma  

 A *harita* işlemi dizisindeki her bir değeri bir işlev uygular. A *azaltmak* işlemi sıradaki bir değer halinde birleştirir. C++ Standart Kitaplığı kullanabilirsiniz [std::transform](../../standard-library/algorithm-functions.md#transform) ve [std::accumulate](../../standard-library/numeric-functions.md#accumulate) eşleme gerçekleştirme ve işlemleri azaltmak için işlevleri. Bununla birlikte, birçok sorunları için kullanabileceğiniz `parallel_transform` paralel eşleme işlemi gerçekleştirmek için algoritma ve `parallel_reduce` algoritmasını paralel olarak azaltma işlemi gerçekleştirin.  

  
 Aşağıdaki örnek, asal sayıların toplamını seri olarak ve paralel işlem için geçen süreyi karşılaştırır. Harita aşaması asal olmayan değerler 0 ve küçültme aşaması SUM'ları değerleri dönüştürür.  
  
 [!code-cpp[concrt-parallel-map-reduce-sum-of-primes#1](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_7.cpp)]  
  
 Bir harita gerçekleştirir ve paralel işlem azaltmak başka bir örnek için bkz: [nasıl yapılır: eşleme gerçekleştirme ve işlemleri paralel azaltmak](../../parallel/concrt/how-to-perform-map-and-reduce-operations-in-parallel.md).  
  
 [[Üst](#top)]  
  
##  <a name="partitions"></a> Bölümleme çalışma  
 Bir veri kaynağı üzerinde bir işlemi paralel hale için için önemli bir adım olan *bölüm* birden çok iş parçacığı tarafından eşzamanlı olarak erişilebilir birden çok bölümlere kaynak. Bir bölümleyici paralel bir algoritma aralıkları iş parçacıkları arasında nasıl bölüm belirtir. Bu belgede daha önce açıklandığı gibi ilk iş yükü oluşturur ve ardından bir iş çalarak algoritması ve iş yükleri dengesiz olduğunda bu bölümler dengelemek için çalarak aralığı kullanan mekanizması bölümleme varsayılan PPL'de kullanır. Örneğin, bir döngü tekrarında yineleme aralığı tamamlandığında, çalışma zamanının o iş parçacığı diğer iş parçacıklarından işi yeniden dağıtır. Ancak, bazı senaryolar için daha iyi sorununuz için uygun olan farklı bir bölümleme mekanizması belirtmek isteyebilirsiniz.  
  
 `parallel_for`, `parallel_for_each`, Ve `parallel_transform` algoritmaları sağlamak ek bir parametre alan aşırı yüklü sürümlerini `_Partitioner`. Bu parametre iş böler bölümleyici türünü tanımlar. PPL'de tanımlar bölümleyiciler türleri şunlardır:  
  
 [CONCURRENCY::affinity_partitioner](../../parallel/concrt/reference/affinity-partitioner-class.md)  
 Aralıkları (genellikle döngü üzerinde çalışmak için uygun çalışan iş parçacığı sayısı) sabit sayıda içine böler çalışır. Bu bölümleyici türü benzer `static_partitioner`, ancak çalışan iş parçacığı, eşlemeleri aralıkları yolu tarafından önbellek benzeşim artırır. Bu bölümleyici türü, aynı veri kümesi birden çok kez (örneğin bir döngü döngü içinde) üzerinden bir döngü yürütülür ve veri önbelleği'nde uygun performansı artırabilir. Bu bölümleyici iptal tam olarak katılmıyor. Ayrıca işbirlikçi engelleme semantiği kullanmaz ve bu nedenle iletme bağımlılığı olan paralel döngüler ile kullanılamaz.  
  
 [CONCURRENCY::auto_partitioner](../../parallel/concrt/reference/auto-partitioner-class.md)  
 Aralık (genellikle döngü üzerinde çalışmak için uygun çalışan iş parçacığı sayısı) ilk bir sayısı içine böler çalışır. Alan aşırı yüklenmiş paralel algoritma çağırmayın, çalışma zamanı bu türü varsayılan olarak kullanır. bir `_Partitioner` parametresi. Her aralık alt aralıkları ayrılabilir ve böylece etkinleştirir gerçekleşmesi için Yük Dengeleme. Bir dizi iş tamamlandığında, çalışma zamanı başka bir iş parçacığı çalışmaya o iş parçacığı alt aralıkları yeniden dağıtır. İş yükünüzün diğer kategorilerden birini altında kapsamında değilse veya iptal veya işbirlikçi engellemek için tam destek gerektiren bu bölümleyici kullanın.  
  
 [CONCURRENCY::simple_partitioner](../../parallel/concrt/reference/simple-partitioner-class.md)  
 Her aralık en az belirtilen öbek boyutu tarafından belirtilen yineleme sayısını sahip olacağı şekilde böler aralıklar içinde çalışır. Bu bölümleyici tür Yük Dengeleme katılan; Ancak, çalışma zamanı alt aralıkları aralıkları bölünmez. Her worker çalışma zamanı iptalleri denetler ve sonra Yük Dengeleme gerçekleştirir `_Chunk_size` yineleme tamamlayın.  
  
 [CONCURRENCY::static_partitioner](../../parallel/concrt/reference/static-partitioner-class.md)  
 Aralıkları (genellikle döngü üzerinde çalışmak için uygun çalışan iş parçacığı sayısı) sabit sayıda içine böler çalışır. İş çalarak kullanmaz ve bu nedenle daha az yüke sahiptir çünkü bu bölümleyici türü performansı artırabilir. Sabit ve Tekdüzen tutar iş her paralel bir döngüden yinelemesi gerçekleştirir ve Destek iptalleri gerektirmez veya işbirlikçi engelleme iletmek bu bölümleyici türünü kullanın.  
  
> [!WARNING]
>  `parallel_for_each` Ve `parallel_transform` algoritmaları desteği rasgele erişim yineleyiciler kullanan kapsayıcıları (std gibi::[vektör](../../standard-library/vector-class.md)) statik, basit ve benzeşimi bölümleyiciler için. Çift yönlü ve iletme yineleyiciler kullanın kapsayıcıları kullanımını bir derleme zamanı hatası oluşturur. Varsayılan bölümleyici `auto_partitioner`, üçünü bu yineleyici türlerini destekler.  
  
 Genellikle, bu bölümleyiciler aynı şekilde dışında kullanılan `affinity_partitioner`. Çoğu bölümleyici türleri durumunu korumak değil ve çalışma zamanı tarafından değiştirilemez. Bu nedenle aşağıdaki örnekte gösterildiği gibi çağrı sitesinde bu bölümleyici nesneler oluşturabilirsiniz.  
  
 [!code-cpp[concrt-static-partitioner#1](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_8.cpp)]  
  
 Ancak, geçmesi gereken bir `affinity_partitioner` olarak olmayan bir nesne`const`, l-değeri başvuru algoritma yeniden gelecekteki döngüler durumu depolayabilirsiniz. Aşağıdaki örnek, bir veri kümesi üzerinde aynı işlemi paralel olarak birden çok kez gerçekleştirir temel bir uygulama gösterir. Kullanımını `affinity_partitioner` dizi önbelleğinde sığmayacak kadar büyük bir olasılıkla olduğundan, performansı artırabilir.  
  
 [!code-cpp[concrt-affinity-partitioner#1](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_9.cpp)]  
  
> [!CAUTION]
>  Kullanılacak işbirlikçi engelleme semantiği üzerinde dayanır var olan kodu değiştirirken dikkatli `static_partitioner` veya `affinity_partitioner`. Bu bölümleyici türleri Yük Dengeleme veya aralık çalarak kullanmayın ve bu nedenle uygulamanızın davranışını değiştirebilirsiniz.  
  
 Verilen herhangi bir senaryoda bir bölümleyici kullanılıp kullanılmayacağını belirlemek için en iyi deneme ve temsili yükler ve bilgisayar yapılandırmalarını altında tamamlanması için işlemleri süreyi ölçmek için yoludur. Örneğin, statik bölümleme önemli speedup yalnızca birkaç çekirdeğe sahip bir çok çekirdekli bilgisayarda sağlayabilir, ancak göreceli olarak pek çok çekirdek bilgisayarlara yavaşlamalara neden.  
  
 [[Üst](#top)]  
  
##  <a name="parallel_sorting"></a> Paralel sıralama  

 PPL'de üç sıralama algoritmaları sağlar: [concurrency::parallel_sort](reference/concurrency-namespace-functions.md#parallel_sort), [concurrency::parallel_buffered_sort](reference/concurrency-namespace-functions.md#parallel_buffered_sort), ve [concurrency::parallel_radixsort](reference/concurrency-namespace-functions.md#parallel_radixsort). Paralel olarak sıralanmış yararlanabilir bir veri kümesine sahip olduğunda, bu algoritmalar sıralama yararlıdır. Özellikle, paralel olarak sıralama büyük bir veri kümesi olduğunda veya bir pkı'ya pahalı karşılaştırma işlemi, verileri sıralamak için kullandığınızda yararlıdır. Bu algoritmalar her yerde öğelerini sıralar.  

  
 `parallel_sort` Ve `parallel_buffered_sort` algoritmaları hem karşılaştırma tabanlı algoritmalar şunlardır. Diğer bir deyişle, bunlar öğeleri değerle karşılaştırın. `parallel_sort` Algoritması ek bellek gereksinimi yoktur ve genel amaçlı sıralama için uygundur. `parallel_buffered_sort` Algoritması gerçekleştirebilir daha iyi `parallel_sort`, ancak O(N) alanı gerektirir.  
  
 `parallel_radixsort` Algoritmasıdır karma tabanlı. Diğer bir deyişle, öğeleri sıralamak için tamsayı anahtarları kullanır. Bu algoritma, tuşlarını kullanarak, doğrudan hedef karşılaştırmaları kullanmak yerine bir öğenin hesaplayabilirsiniz. Gibi `parallel_buffered_sort`, bu algoritma O(N) alanı gerektirir.  
  
 Aşağıdaki tabloda, üç paralel sıralama algoritmalar önemli özellikleri özetlenmektedir.  
  
|Algoritması|Açıklama|Sıralama mekanizması|Sıralama kararlılık|Bellek gereksinimleri|Zaman karmaşıklık|Yineleyici erişim|  
|---------------|-----------------|-----------------------|--------------------|-------------------------|---------------------|---------------------|  
|`parallel_sort`|Genel amaçlı karşılaştırma tabanlı sıralayın.|(Artan karşılaştırma tabanlı)|Kararsız|Yok.|O((N/P)log(N/P) + 2N((P-1)/P))|Rastgele|  
|`parallel_buffered_sort`|O(N) alanı gerektiren daha hızlı genel amaçlı karşılaştırma tabanlı sıralayın.|(Artan karşılaştırma tabanlı)|Kararsız|Ek O(N) alanı gerektirir|O((N/P)log(N))|Rastgele|  
|`parallel_radixsort`|O(N) alanı gerektiren tamsayı anahtar tabanlı sıralayın.|Karma tabanlı|Kararlı|Ek O(N) alanı gerektirir|O(N/P)|Rastgele|  
  
 Aşağıdaki çizim üç paralel sıralama algoritmalar önemli özelliklerini daha grafik şeklinde gösterir.  
  
 ![Sıralama algoritmaları karşılaştırması](../../parallel/concrt/media/concrt_parallel_sorting.png "concrt_parallel_sorting")  
  
 Bu paralel algoritmalar sıralama iptali ve özel durum işleme kurallarına izleyin. İptal etme ve Eşzamanlılık Çalışma zamanı özel durum işleme hakkında daha fazla bilgi için bkz: [paralel algoritmaları iptal etme](../../parallel/concrt/cancellation-in-the-ppl.md#algorithms) ve [özel durum işleme](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md).  
  
> [!TIP]
>  Bu paralel algoritmalar sıralama taşıma semantiği destekler. Daha verimli bir şekilde gerçekleşmesi değiştirme işlemlerini etkinleştirmek için bir taşıma atama işleci tanımlayabilirsiniz. Taşıma semantik ve taşıma atama işleci hakkında daha fazla bilgi için bkz: [Rvalue başvuru Bildirimcisi: & &](../../cpp/rvalue-reference-declarator-amp-amp.md), ve [taşıma oluşturucuları ve taşıma atama işleçleri (C++)](../../cpp/move-constructors-and-move-assignment-operators-cpp.md). Bir taşıma atama işleci veya takas işlevi sağlamazsanız sıralama algoritmaları kopya Oluşturucu kullanın.  
  
 Aşağıdaki temel örnek nasıl kullanılacağını gösterir `parallel_sort` sıralamak için bir `vector` , `int` değerleri. Varsayılan olarak, `parallel_sort` kullanan [std::less](../../standard-library/less-struct.md) değerleri karşılaştırmak için.  
  
 [!code-cpp[concrt-basic-parallel-sort#1](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_10.cpp)]  
  
 Bu örnek özel karşılaştırma işlevi sağlamak nasıl gösterir. Kullandığı [std::complex::real](../../standard-library/complex-class.md#real) sıralamak için yöntemi [std::complex\<çift >](../../standard-library/complex-double.md) artan düzende değerleri.  
  
 [!code-cpp[concrt-basic-parallel-sort#2](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_11.cpp)]  
  
 Bu örnek için karma işlevi sağlamak nasıl gösterir `parallel_radixsort` algoritması. Bu örnek, 3B noktaları sıralar. Puanları bir başvuru noktası kendi mesafe göre sıralanır.  
  
 [!code-cpp[concrt-parallel-sort-points#1](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_12.cpp)]  
  
 Çizim için bu örnek, nispeten küçük veri kümesi kullanır. Performans geliştirmeleri ile büyük veri kümeleri üzerinde denemeler yapmak için vektör ilk boyutunu artırabilirsiniz.  
  
 Bu örnek bir lambda ifadesi karma işlevi olarak kullanır. Std yerleşik uygulamaları birini de kullanabilirsiniz::[karma sınıfı](../../standard-library/hash-class.md) veya kendi uzmanlık tanımlayın. Bu örnekte gösterildiği gibi bir özel karma işlevi nesnesi de kullanabilirsiniz:  
  
 [!code-cpp[concrt-parallel-sort-points#2](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_13.cpp)]  
  
 [!code-cpp[concrt-parallel-sort-points#3](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_14.cpp)]  
  
 Karma işlevi bir tam sayı türü döndürmesi gerekir ([std::is_integral::value](../../standard-library/is-integral-class.md) olmalıdır `true`). Bu tamsayı türü türüne dönüştürülebilir olmalıdır `size_t`.  
  
###  <a name="choose_sort"></a> Sıralama algoritması seçme  
 Çoğu durumda, `parallel_sort` hızı ve bellek performansı en iyi dengeyi sağlar. Ancak, artırmanız Veri kümenizi, kullanılabilir işlemci sayısı veya karşılaştırma işlevinizi karmaşıklığını boyutunu `parallel_buffered_sort` veya `parallel_radixsort` daha iyi gerçekleştirebilirsiniz. Verilen herhangi bir senaryoda kullanmak için hangi sıralama algoritması belirlemek için en iyi deneme ve temsili bilgisayar yapılandırmalarını altında tipik verileri sıralamak için gereken süreyi ölçmek için yoludur. Sıralama stratejisi seçtiğinizde aşağıdaki yönergeleri göz önünde bulundurun.  
  
-   Veri kümenizi boyutu. Bu belgede, bir *küçük* dataset 1. 000'den az öğe içeren bir *orta* veri kümesi içerdiğinden 10.000 ve 100.000 öğeleri arasında ve bir *büyük* veri kümesi içerir 100. 000'den fazla öğe.  
  
-   Compare işlevi veya karma işlevi gerçekleştiren iş miktarı.  
  
-   Kullanılabilir bilgi işlem kaynaklarına miktarı.  
  
-   Veri kümesi özellikleri. Örneğin, bir algoritma da zaten neredeyse sıralanmış veri, ancak değil de tamamen sıralanmamış veri gerçekleştirebilir.  
  
-   Öbek boyutu. İsteğe bağlı `_Chunk_size` bağımsız değişkeni belirtir küçük çalışma birimlerine Genel sıralama subdivides olarak ne zaman algoritmasını paralel seri sıralama uygulamasına gelen geçer. Örneğin, 512 sağlarsanız, bir iş birimine 512 veya daha az öğe içerdiğinde algoritma seri uygulamasına geçer. Paralel verileri işlemek için gerekli olan ek yükü attığından seri uygulama genel performansı artırabilir.  
  
 Çok sayıda kullanılabilir bilgi işlem kaynaklarına sahip veya iş görece büyük miktarda karşılaştırma işlevi veya karma işlevi gerçekleştiren olsa bile paralel, küçük bir veri kümesini sıralamak için faydalı olabilir. Kullanabileceğiniz [std::sort](../../standard-library/algorithm-functions.md#sort) küçük veri kümelerini sıralama işlevi. (`parallel_sort` ve `parallel_buffered_sort` çağrısı `sort` dataset; büyük bir öbek boyutu belirttiğinizde ancak `parallel_buffered_sort` ek kilit çekişmesini veya bellek ayırma nedeniyle sürebilir O(N) alan ayırmak için sahip olması gerekir.)  
  
 Kilit çakışması tabi bellek ayırıcısı bellekten kazanacak veya kullanmak `parallel_sort` orta ölçekli bir veri kümesi sıralamak için. `parallel_sort` ek boşluk yok; gerektirir. diğer algoritmalar O(N) alan gerektirir.  
  
 Kullanım `parallel_buffered_sort` orta ölçekli veri kümelerini ve ne zaman uygulamanızı ek O(N) alan gereksinimini karşılayan sıralamak için. `parallel_buffered_sort` çok sayıda bilgi işlem kaynakları veya pahalı karşılaştırma işlevi veya karma işlevi varsa, özellikle yararlı olabilir.  
  
 Kullanım `parallel_radixsort` büyük veri kümelerini ve ne zaman uygulamanızı ek O(N) alan gereksinimini karşılayan sıralamak için. `parallel_radixsort` eşdeğer karşılaştırma işlemi daha pahalı olduğunda veya her iki işlem pahalı olduğunda özellikle yararlı olabilir.  
  
> [!CAUTION]
>  İyi bir karma işlevi uygulama dataset aralığı ve karşılık gelen bir imzasız değeri dönüştürülmüş kümesindeki her öğe nasıl bilmeniz gerekir. Karma işlemi imzasız değerler üzerinde çalıştığı için farklı bir sıralama strateji imzasız karma değerlerini oluşturduysa göz önünde bulundurun.  
  
 Aşağıdaki örnek performansını karşılaştırır `sort`, `parallel_sort`, `parallel_buffered_sort`, ve `parallel_radixsort` aynı büyük rastgele veri kümesine karşı.  
  
 [!code-cpp[concrt-choosing-parallel-sort#1](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_15.cpp)]  
  
 Bu örnekte, sıralama sırasında O(N) alan ayırmak için kabul edilebilir olduğunu varsayan `parallel_radixsort` bu bilgisayarı yapılandırma üzerinde bu veri kümesi üzerinde en iyi gerçekleştirir.  
  
 [[Üst](#top)]  
  
## <a name="related-topics"></a>İlgili Konular  
  
|Başlık|Açıklama|  
|-----------|-----------------|  
|[Nasıl yapılır: parallel_for Döngüsü Yazma](../../parallel/concrt/how-to-write-a-parallel-for-loop.md)|Nasıl kullanılacağını gösterir `parallel_for` matris çarpım gerçekleştirmek için algoritması.|  
|[Nasıl yapılır: parallel_for_each Döngüsü Yazma](../../parallel/concrt/how-to-write-a-parallel-for-each-loop.md)|Nasıl kullanılacağını gösterir `parallel_for_each` asal sayılar sayısı işlem için algoritma bir [std::array](../../standard-library/array-class-stl.md) paralel nesne.|  
|[Nasıl yapılır: Paralel Sıralama Rutini Yazmak için parallel_invoke Kullanma](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md)|Nasıl kullanılacağını gösterir `parallel_invoke` bitonic Sıralama algoritması performansını artırmak için algoritması.|  
|[Nasıl yapılır: Paralel İşlemleri Yürütmek için parallel_invoke Kullanma](../../parallel/concrt/how-to-use-parallel-invoke-to-execute-parallel-operations.md)|Nasıl kullanılacağını gösterir `parallel_invoke` bir paylaşılan veri kaynağı üzerinde birden çok işlemler gerçekleştiren bir program performansını artırmak için algoritması.|  
|[Nasıl yapılır: Eşleme Gerçekleştirme ve İşlemleri Paralel Olarak Azaltma](../../parallel/concrt/how-to-perform-map-and-reduce-operations-in-parallel.md)|Nasıl kullanılacağını gösterir `parallel_transform` ve `parallel_reduce` bir eşleme gerçekleştirme ve dosyaları sözcükleri oluşumlarını sayar işlemi azaltmak için algoritmaları.|  
|[Paralel Desen Kitaplığı (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md)|Ölçeklenebilirlik ve kolaylığı eşzamanlı uygulamaları geliştirmek için kullanım yükseltir kesinlik temelli bir programlama modelidir PPL açıklar.|  
|[PPL'de İptal](cancellation-in-the-ppl.md)|PPL'de, paralel iş iptal etme ve bir görev grubu ne zaman iptal belirleme iptal rolünü açıklar.|  
|[Özel Durum İşleme](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)|Özel durum eşzamanlılık çalışma zamanı'nda işleme rolünü açıklar.|  
  
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


