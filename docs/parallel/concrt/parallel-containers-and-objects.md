---
title: Paralel Kapsayıcılar ve Nesneler
ms.date: 03/27/2019
helpviewer_keywords:
- parallel objects
- parallel containers
- concurrent containers
ms.assetid: 90ab715c-29cd-48eb-8e76-528619aab466
ms.openlocfilehash: a2a44d267e16115f1b5a6ecb76308a66fc7abc8b
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/20/2019
ms.locfileid: "75302308"
---
# <a name="parallel-containers-and-objects"></a>Paralel Kapsayıcılar ve Nesneler

Paralel Desenler kitaplığı (PPL), öğelerine iş parçacığı açısından güvenli erişim sağlayan çeşitli kapsayıcılar ve nesneler içerir.

*Eşzamanlı bir kapsayıcı* , en önemli işlemlere eşzamanlılık açısından güvenli erişim sağlar. Burada eşzamanlılık açısından güvenli, işaretçiler veya yineleyiciler her zaman geçerlidir. Bu, öğe başlatma garantisi veya belirli bir geçiş düzeni değildir. Bu kapsayıcıların işlevselliği, C++ standart kitaplık tarafından sağlananlara benzer. Örneğin, [concurrency:: concurrent_vector](../../parallel/concrt/reference/concurrent-vector-class.md) sınıfı [std:: vector](../../standard-library/vector-class.md) sınıfına benzer, ancak `concurrent_vector` sınıfı öğeleri paralel olarak eklemenizi sağlar. Aynı kapsayıcıya hem okuma hem de yazma erişimi gerektiren paralel kodunuz varsa, eş zamanlı kapsayıcıları kullanın.

*Eşzamanlı bir nesne* bileşenler arasında eşzamanlı olarak paylaşılır. Bir eşzamanlı nesnenin durumunu paralel olarak hesaplayan bir işlem, aynı durumu seri olarak hesaplayan başka bir işlemle aynı sonucu üretir. [Concurrency:: combinable](../../parallel/concrt/reference/combinable-class.md) sınıfı, eşzamanlı nesne türüne bir örnektir. `combinable` sınıfı, hesaplamaları paralel olarak gerçekleştirmenize olanak tanır ve ardından bu hesaplamaları nihai bir sonuçla birleştirir. Paylaşılan bir değişkene veya kaynağa erişimi eşitlemek için başka bir eşitleme mekanizması (örneğin, bir mutex) kullandığınızda, eşzamanlı nesneleri kullanın.

##  <a name="top"></a>Başlıklı

Bu konuda, aşağıdaki paralel kapsayıcılar ve nesneler ayrıntılı olarak açıklanmaktadır.

Eşzamanlı kapsayıcılar:

- [concurrent_vector Sınıfı](#vector)

   - [Concurrent_vector ve vektör arasındaki farklılıklar](#vector-differences)

   - [Eşzamanlılık güvenli Işlemler](#vector-safety)

   - [Özel durum güvenliği](#vector-exceptions)

- [concurrent_queue Sınıfı](#queue)

   - [Concurrent_queue ve kuyruk arasındaki farklar](#queue-differences)

   - [Eşzamanlılık güvenli Işlemler](#queue-safety)

   - [Yineleyici desteği](#queue-iterators)

- [concurrent_unordered_map Sınıfı](#unordered_map)

   - [Concurrent_unordered_map ve unordered_map arasındaki farklar](#map-differences)

   - [Eşzamanlılık güvenli Işlemler](#map-safety)

- [concurrent_unordered_multimap Sınıfı](#unordered_multimap)

- [concurrent_unordered_set Sınıfı](#unordered_set)

- [concurrent_unordered_multiset Sınıfı](#unordered_multiset)

Eş zamanlı nesneler:

- [combinable Sınıfı](#combinable)

   - [Yöntemler ve Özellikler](#combinable-features)

   - [Örnekler](#combinable-examples)

##  <a name="vector"></a>concurrent_vector sınıfı

[Concurrency:: concurrent_vector](../../parallel/concrt/reference/concurrent-vector-class.md) sınıfı, yalnızca [std:: vector](../../standard-library/vector-class.md) sınıfı gibi, öğelerine rastgele erişim sağlayan bir dizi kapsayıcı sınıfıdır. `concurrent_vector` sınıfı eşzamanlılık açısından güvenli ekleme ve öğe erişim işlemlerine izin vermez. Ekleme işlemleri varolan işaretçileri veya yineleyiciler geçersiz kılmaz. Yineleyici erişimi ve çapraz geçiş işlemleri de eşzamanlılık açısından güvenlidir. Burada eşzamanlılık açısından güvenli, işaretçiler veya yineleyiciler her zaman geçerlidir. Bu, öğe başlatma garantisi veya belirli bir geçiş düzeni değildir.

###  <a name="vector-differences"></a>Concurrent_vector ve vektör arasındaki farklılıklar

`concurrent_vector` sınıfı, `vector` sınıfına benzer. `concurrent_vector` nesnesi üzerinde Append, element Access ve yineleyici erişim işlemlerinin karmaşıklığı, bir `vector` nesnesi ile aynıdır. Aşağıdaki noktalara `concurrent_vector` `vector`nereden farklı olduğu gösterilmektedir:

- `concurrent_vector` nesnesinde ekleme, öğe erişimi, yineleyici erişimi ve yineleyici çapraz geçişi işlemleri eşzamanlılık açısından güvenlidir.

- Öğeleri yalnızca bir `concurrent_vector` nesnesinin sonuna ekleyebilirsiniz. `concurrent_vector` sınıfı `insert` metodunu sağlamıyor.

- `concurrent_vector` nesne, sonuna ekleme yaparken [taşıma semantiğini](../../cpp/rvalue-reference-declarator-amp-amp.md) kullanmaz.

- `concurrent_vector` sınıfı `erase` veya `pop_back` yöntemleri sağlamıyor. `vector`gibi, bir `concurrent_vector` nesnesinden tüm öğeleri kaldırmak için [clear](reference/concurrent-vector-class.md#clear) metodunu kullanın.

- `concurrent_vector` sınıfı, bitişik olarak öğelerini bellekte depolamaz. Bu nedenle, bir diziyi kullanabileceğiniz tüm yollarla `concurrent_vector` sınıfını kullanamazsınız. Örneğin, `concurrent_vector`türü `v` adlı bir değişken için `&v[0]+2` ifadesi tanımlanmamış bir davranış üretir.

- `concurrent_vector` sınıfı [grow_by](reference/concurrent-vector-class.md#grow_by) ve [grow_to_at_least](reference/concurrent-vector-class.md#grow_to_at_least) yöntemlerini tanımlar. Bu yöntemler, eşzamanlılık açısından güvenli olmaları dışında [yeniden boyutlandırma](reference/concurrent-vector-class.md#resize) yöntemine benzer.

- `concurrent_vector` nesne, içine eklediğinizde veya yeniden boyutlandırdığınızda kendi öğelerini değiştirmez. Bu, mevcut işaretçiler ve yineleyicilerin eşzamanlı işlemler sırasında geçerli kalmasını sağlar.

- Çalışma zamanı, `bool`türü için `concurrent_vector` özelleştirilmiş bir sürümünü tanımlamaz.

###  <a name="vector-safety"></a>Eşzamanlılık güvenli Işlemler

`concurrent_vector` nesnenin boyutunu ekleyen veya artıran tüm yöntemler veya bir `concurrent_vector` nesnesindeki bir öğeye erişim eşzamanlılık açısından güvenlidir. Burada eşzamanlılık açısından güvenli, işaretçiler veya yineleyiciler her zaman geçerlidir. Bu, öğe başlatma garantisi veya belirli bir geçiş düzeni değildir. Bu kuralın özel durumu `resize` yöntemidir.

Aşağıdaki tabloda eşzamanlılık açısından güvenli olan ortak `concurrent_vector` yöntemleri ve işleçleri gösterilmektedir.

||||
|-|-|-|
|[hızı](reference/concurrent-vector-class.md#at)|[erer](reference/concurrent-vector-class.md#end)|[işlecinde&#91;&#93;](reference/concurrent-vector-class.md#operator_at)|
|[başladı](reference/concurrent-vector-class.md#begin)|[yapılan](reference/concurrent-vector-class.md#front)|[push_back](reference/concurrent-vector-class.md#push_back)|
|[Geri](reference/concurrent-vector-class.md#back)|[grow_by](reference/concurrent-vector-class.md#grow_by)|[rbegin](reference/concurrent-vector-class.md#rbegin)|
|[kü](reference/concurrent-vector-class.md#capacity)|[grow_to_at_least](reference/concurrent-vector-class.md#grow_to_at_least)|[rend](reference/concurrent-vector-class.md#rend)|
|[empty](reference/concurrent-vector-class.md#empty)|[max_size](reference/concurrent-vector-class.md#max_size)|[boyutla](reference/concurrent-vector-class.md#size)|

Çalışma zamanının C++ standart kitaplıkla uyumluluk için sağladığı işlemler (örneğin, `reserve`eşzamanlılık açısından güvenli değildir). Aşağıdaki tabloda eşzamanlılık güvenli olmayan ortak Yöntemler ve işleçler gösterilmektedir.

|||
|-|-|
|[ata](reference/concurrent-vector-class.md#assign)|[ayırmaya](reference/concurrent-vector-class.md#reserve)|
|[lediğiniz](reference/concurrent-vector-class.md#clear)|[yeniden boyutlandırma](reference/concurrent-vector-class.md#resize)|
|[operator=](reference/concurrent-vector-class.md#operator_eq)|[shrink_to_fit](reference/concurrent-vector-class.md#shrink_to_fit)|

Mevcut öğelerin değerini değiştiren işlemler eşzamanlılık açısından güvenli değildir. Aynı veri öğesiyle eşzamanlı okuma ve yazma işlemlerini eşitlemek için [reader_writer_lock](../../parallel/concrt/reference/reader-writer-lock-class.md) nesnesi gibi bir eşitleme nesnesi kullanın. Eşitleme nesneleri hakkında daha fazla bilgi için bkz. [eşitleme veri yapıları](../../parallel/concrt/synchronization-data-structures.md).

`concurrent_vector`kullanmak için `vector` kullanan mevcut kodu dönüştürdüğünüzde, eşzamanlı işlemler uygulamanızın davranışının değişmesine neden olabilir. Örneğin, `concurrent_vector` nesnesi üzerinde aynı anda iki görevi gerçekleştiren aşağıdaki programı göz önünde bulundurun. İlk görev bir `concurrent_vector` nesnesine ek öğeler ekler. İkinci görev, aynı nesnedeki tüm öğelerin toplamını hesaplar.

[!code-cpp[concrt-vector-safety#1](../../parallel/concrt/codesnippet/cpp/parallel-containers-and-objects_1.cpp)]

`end` yöntemi eşzamanlılık açısından güvenli olsa da, [push_back](reference/concurrent-vector-class.md#push_back) yöntemine eşzamanlı bir çağrı, `end` tarafından döndürülen değerin değişmesine neden olur. Yineleyicinin geçtiği öğe sayısı belirsiz. Bu nedenle, bu program her çalıştırdığınızda farklı bir sonuç oluşturabilir. Öğe türü önemsiz olmadığında, bir yarış koşulunun `push_back` ve `end` çağrıları arasında mevcut olması mümkündür. `end` yöntemi ayrılan, ancak tam olarak başlatılmamış bir öğe döndürebilir.

###  <a name="vector-exceptions"></a>Özel durum güvenliği

Bir büyüme veya atama işlemi bir özel durum oluşturursa, `concurrent_vector` nesnesinin durumu geçersiz hale gelir. Geçersiz durumda olan bir `concurrent_vector` nesnesinin davranışı, aksi belirtilmedikçe tanımsızdır. Ancak, yıkıcı her zaman nesnenin ayırdığı belleği serbest bırakır, nesne geçersiz bir durumda olsa bile.

`T`vektör öğelerinin veri türü aşağıdaki gereksinimlere uymalıdır. Aksi takdirde, `concurrent_vector` sınıfının davranışı tanımsızdır.

- Yok edicinin throw olmaması gerekir.

- Varsayılan veya kopya Oluşturucu oluşturursa, yıkıcının `virtual` anahtar sözcüğü kullanılarak bildirilemediği ve sıfır ile başlatılmış bellekle düzgün çalışması gerekir.

[[Üst](#top)]

##  <a name="queue"></a>concurrent_queue sınıfı

Yalnızca [std:: Queue](../../standard-library/queue-class.md) sınıfı gibi [concurrency:: concurrent_queue](../../parallel/concrt/reference/concurrent-queue-class.md) sınıfı, ön ve arka öğelerine erişmenizi sağlar. `concurrent_queue` sınıfı eşzamanlılık güvenli sıraya alma ve sıradan çıkarma işlemlerine izin vermez. Burada eşzamanlılık açısından güvenli, işaretçiler veya yineleyiciler her zaman geçerlidir. Bu, öğe başlatma garantisi veya belirli bir geçiş düzeni değildir. `concurrent_queue` sınıfı ayrıca eşzamanlılık açısından güvenli olmayan Yineleyici desteği de sağlar.

###  <a name="queue-differences"></a>Concurrent_queue ve kuyruk arasındaki farklar

`concurrent_queue` sınıfı, `queue` sınıfına benzer. Aşağıdaki noktalara `concurrent_queue` `queue`nereden farklı olduğu gösterilmektedir:

- `concurrent_queue` nesnesindeki sıraya alma ve sıradan çıkarma işlemleri eşzamanlılık açısından güvenlidir.

- `concurrent_queue` sınıfı eşzamanlılık açısından güvenli olmayan Yineleyici desteği sağlar.

- `concurrent_queue` sınıfı `front` veya `pop` yöntemleri sağlamıyor. `concurrent_queue` sınıfı, [try_pop](reference/concurrent-queue-class.md#try_pop) yöntemini tanımlayarak bu yöntemlerin yerini alır.

- `concurrent_queue` sınıfı `back` metodunu sağlamıyor. Bu nedenle, sıranın sonuna başvurulamıyor.

- `concurrent_queue` sınıfı `size` yöntemi yerine [unsafe_size](reference/concurrent-queue-class.md#unsafe_size) yöntemi sağlar. `unsafe_size` yöntemi eşzamanlılık açısından güvenli değildir.

###  <a name="queue-safety"></a>Eşzamanlılık güvenli Işlemler

`concurrent_queue` nesnesini sıraya alma veya sıradan çıkarma yöntemleri eşzamanlılık açısından güvenlidir. Burada eşzamanlılık açısından güvenli, işaretçiler veya yineleyiciler her zaman geçerlidir. Bu, öğe başlatma garantisi veya belirli bir geçiş düzeni değildir.

Aşağıdaki tabloda eşzamanlılık açısından güvenli olan ortak `concurrent_queue` yöntemleri ve işleçleri gösterilmektedir.

|||
|-|-|
|[empty](reference/concurrent-queue-class.md#empty)|[push](reference/concurrent-queue-class.md#push)|
|[get_allocator](reference/concurrent-queue-class.md#get_allocator)|[try_pop](reference/concurrent-queue-class.md#try_pop)|

`empty` yöntemi eşzamanlılık açısından güvenli olsa da, eşzamanlı bir işlem, `empty` yöntemi döndürülmeden önce sıranın büyümesine veya küçültülmesine neden olabilir.

Aşağıdaki tabloda eşzamanlılık güvenli olmayan ortak Yöntemler ve işleçler gösterilmektedir.

|||
|-|-|
|[lediğiniz](reference/concurrent-queue-class.md#clear)|[unsafe_end](reference/concurrent-queue-class.md#unsafe_end)|
|[unsafe_begin](reference/concurrent-queue-class.md#unsafe_begin)|[unsafe_size](reference/concurrent-queue-class.md#unsafe_size)|

###  <a name="queue-iterators"></a>Yineleyici desteği

`concurrent_queue` eşzamanlılık açısından güvenli olmayan yineleyiciler sağlar. Bu yineleyiciler yalnızca hata ayıklama için kullanmanızı öneririz.

`concurrent_queue` Yineleyici, öğeleri yalnızca iletme yönünde geçer. Aşağıdaki tabloda her bir yineleyicinin desteklediği işleçler gösterilmektedir.

|İşleç|Açıklama|
|--------------|-----------------|
|`operator++`|Kuyruktaki bir sonraki öğeye ilerler. Bu işleç, hem ön artışı hem de artış sonrası semantiğini sağlamak için aşırı yüklenmiştir.|
|`operator*`|Geçerli öğeye bir başvuru alır.|
|`operator->`|Geçerli öğe için bir işaretçi alır.|

[[Üst](#top)]

##  <a name="unordered_map"></a>concurrent_unordered_map sınıfı

[Concurrency:: concurrent_unordered_map](../../parallel/concrt/reference/concurrent-unordered-map-class.md) sınıfı, [std:: unordered_map](../../standard-library/unordered-map-class.md) sınıfında olduğu gibi, [std::p Air\<const anahtar, Ty >](../../standard-library/pair-structure.md)türünde öğelerin değişen uzunlukta bir dizisini kontrol eden ilişkilendirilebilir bir kapsayıcı sınıfıdır. Sıralanmamış bir eşlemeyi, anahtar ve değer çifti ekleyebileceğiniz veya anahtara göre bir değer aramak için bir sözlük olarak düşünün. Bu sınıf, paylaşılan bir kapsayıcıya eşzamanlı olarak erişmesi gereken birden çok iş parçacığı veya göreviniz olduğunda, içine eklemek veya güncelleştirmek için yararlıdır.

Aşağıdaki örnek, `concurrent_unordered_map`kullanmanın temel yapısını gösterir. Bu örnek [' a ', ' i '] aralığına karakter anahtarları ekler. İşlem sırası belirlenmediğinden, her anahtar için son değer de saptanmamış olur. Ancak, eklemeleri paralel yapmak güvenlidir.

[!code-cpp[concrt-unordered-map-structure#1](../../parallel/concrt/codesnippet/cpp/parallel-containers-and-objects_2.cpp)]

Bir eşlemeyi gerçekleştirmek için `concurrent_unordered_map` kullanan bir örnek için ve paralel olarak işlemi azaltmak için bkz. [nasıl yapılır: eşleme gerçekleştirme ve Işlemleri paralel olarak azaltma](../../parallel/concrt/how-to-perform-map-and-reduce-operations-in-parallel.md).

###  <a name="map-differences"></a>Concurrent_unordered_map ve unordered_map arasındaki farklar

`concurrent_unordered_map` sınıfı, `unordered_map` sınıfına benzer. Aşağıdaki noktalara `concurrent_unordered_map` `unordered_map`nereden farklı olduğu gösterilmektedir:

- `erase`, `bucket`, `bucket_count`ve `bucket_size` yöntemleri sırasıyla `unsafe_erase`, `unsafe_bucket`, `unsafe_bucket_count`ve `unsafe_bucket_size`olarak adlandırılır. `unsafe_` adlandırma kuralı, bu yöntemlerin eşzamanlılık açısından güvenli olmadığını gösterir. Eşzamanlılık güvenliği hakkında daha fazla bilgi için bkz. [eşzamanlılık güvenli işlemleri](#map-safety).

- Ekleme işlemleri mevcut işaretçileri veya yineleyicileri geçersiz kılmaz, ya da haritada zaten var olan öğelerin sırasını değiştirmezler. Ekleme ve çapraz geçiş işlemleri eşzamanlı olarak gerçekleşebilir.

- `concurrent_unordered_map` yalnızca ileri yinelemeyi destekler.

- Ekleme, `equal_range`tarafından döndürülen yineleyiciler geçersiz kılmaz veya güncelleştirmiyor. Ekleme, Aralık sonuna eşit olmayan öğeler ekleyebilir. Başlangıç yineleyicisi bir eşit öğeye işaret eder.

Kilitlenmeden kaçınmak için, bir `concurrent_unordered_map` yöntemi bellek ayırıcı, karma işlevleri veya Kullanıcı tanımlı diğer kod çağırdığında bir kilit bulundurmamalıdır. Ayrıca, karma işlevin her zaman aynı değere eşit anahtarları değerlendirdiğinden emin olmanız gerekir. En iyi karma işlevleri, anahtarları karma kod alanı genelinde bir yere dağıtır.

###  <a name="map-safety"></a>Eşzamanlılık güvenli Işlemler

`concurrent_unordered_map` sınıfı eşzamanlılık güvenli ekleme ve öğe erişimi işlemlerine izin vermez. Ekleme işlemleri varolan işaretçileri veya yineleyiciler geçersiz kılmaz. Yineleyici erişimi ve çapraz geçiş işlemleri de eşzamanlılık açısından güvenlidir. Burada eşzamanlılık açısından güvenli, işaretçiler veya yineleyiciler her zaman geçerlidir. Bu, öğe başlatma garantisi veya belirli bir geçiş düzeni değildir. Aşağıdaki tabloda, eşzamanlılık açısından güvenli olan, yaygın olarak kullanılan `concurrent_unordered_map` yöntemleri ve işleçleri gösterilmektedir.

|||||
|-|-|-|-|
|[hızı](reference/concurrent-unordered-map-class.md#at)|`count`|`find`|[key_eq](reference/concurrent-unordered-map-class.md#key_eq)|
|`begin`|`empty`|`get_allocator`|`max_size`|
|`cbegin`|`end`|`hash_function`|[işlecinde&#91;&#93;](reference/concurrent-unordered-map-class.md#operator_at)|
|`cend`|`equal_range`|[ekleyin](reference/concurrent-unordered-map-class.md#insert)|`size`|

`count` yöntemi eşzamanlı çalışan iş parçacıklarından güvenli şekilde çağrılabilir olsa da, farklı iş parçacıkları kapsayıcıya aynı anda yeni bir değer eklenirse farklı sonuçlar alabilir.

Aşağıdaki tabloda eşzamanlılık güvenli olmayan yaygın olarak kullanılan yöntemler ve işleçler gösterilmektedir.

||||
|-|-|-|
|`clear`|`max_load_factor`|`rehash`|
|`load_factor`|[operator=](reference/concurrent-unordered-map-class.md#operator_eq)

Bu yöntemlerin yanı sıra, `unsafe_` ile başlayan tüm yöntemler de eşzamanlılık açısından güvenli değildir.

[[Üst](#top)]

##  <a name="unordered_multimap"></a>concurrent_unordered_multimap sınıfı

[Concurrency:: concurrent_unordered_multimap](../../parallel/concrt/reference/concurrent-unordered-multimap-class.md) sınıfı, birden çok değerin aynı anahtarla eşlenme olanağı hariç, `concurrent_unordered_map` sınıfına benzer. Ayrıca, aşağıdaki yollarla `concurrent_unordered_map` farklıdır:

- [Concurrent_unordered_multimap:: INSERT](reference/concurrent-unordered-multimap-class.md#insert) yöntemi `std::pair<iterator, bool>`yerine bir yineleyici döndürür.

- `concurrent_unordered_multimap` sınıfı `operator[]` veya `at` metodunu sağlamıyor.

Aşağıdaki örnek, `concurrent_unordered_multimap`kullanmanın temel yapısını gösterir. Bu örnek [' a ', ' i '] aralığına karakter anahtarları ekler. `concurrent_unordered_multimap`, bir anahtarın birden çok değere sahip olmasını sağlar.

[!code-cpp[concrt-unordered-multimap-structure#1](../../parallel/concrt/codesnippet/cpp/parallel-containers-and-objects_3.cpp)]

[[Üst](#top)]

##  <a name="unordered_set"></a>concurrent_unordered_set sınıfı

[Concurrency:: concurrent_unordered_set](../../parallel/concrt/reference/concurrent-unordered-set-class.md) sınıfı, anahtar ve değer çiftleri yerine değerleri yönetmesi dışında `concurrent_unordered_map` sınıfına benzer. `concurrent_unordered_set` sınıfı `operator[]` veya `at` metodunu sağlamıyor.

Aşağıdaki örnek, `concurrent_unordered_set`kullanmanın temel yapısını gösterir. Bu örnek [' a ', ' i '] aralığındaki karakter değerlerini ekler. Eklemeleri paralel yapmak güvenlidir.

[!code-cpp[concrt-unordered-set#1](../../parallel/concrt/codesnippet/cpp/parallel-containers-and-objects_4.cpp)]

[[Üst](#top)]

##  <a name="unordered_multiset"></a>concurrent_unordered_multiset sınıfı

[Concurrency:: concurrent_unordered_multiset](../../parallel/concrt/reference/concurrent-unordered-multiset-class.md) sınıfı, yinelenen değerlere izin verdiğinden `concurrent_unordered_set` sınıfına benzer. Ayrıca, aşağıdaki yollarla `concurrent_unordered_set` farklıdır:

- [Concurrent_unordered_multiset:: INSERT](reference/concurrent-unordered-multiset-class.md#insert) yöntemi `std::pair<iterator, bool>`yerine bir yineleyici döndürür.

- `concurrent_unordered_multiset` sınıfı `operator[]` veya `at` metodunu sağlamıyor.

Aşağıdaki örnek, `concurrent_unordered_multiset`kullanmanın temel yapısını gösterir. Bu örnek [' a ', ' i '] aralığındaki karakter değerlerini ekler. `concurrent_unordered_multiset` bir değerin birden çok kez gerçekleşmesini sağlar.

[!code-cpp[concrt-unordered-multiset#1](../../parallel/concrt/codesnippet/cpp/parallel-containers-and-objects_5.cpp)]

[[Üst](#top)]

##  <a name="combinable"></a>combinable Sınıfı

[Concurrency:: combinable](../../parallel/concrt/reference/combinable-class.md) sınıfı, hassas hesaplamalar gerçekleştirmenizi ve ardından bu hesaplamaları nihai bir sonuçla birleştirmeye olanak tanıyan yeniden kullanılabilir, iş parçacığı yerel depolama alanı sağlar. Bir `combinable` nesnesini azaltma değişkeni olarak düşünebilirsiniz.

`combinable` sınıfı, birkaç iş parçacığı veya görev arasında paylaşılan bir kaynağınız olduğunda faydalıdır. `combinable` sınıfı, paylaşılan kaynaklara kilit boş bir şekilde erişim sağlayarak paylaşılan durumu ortadan kaldırmanıza yardımcı olur. Bu nedenle, bu sınıf, birden fazla iş parçacığından paylaşılan verilere erişimi eşitlemek için bir eşitleme mekanizması (örneğin, bir mutex) kullanılmasına alternatif sağlar.

###  <a name="combinable-features"></a>Yöntemler ve Özellikler

Aşağıdaki tabloda `combinable` sınıfının bazı önemli yöntemleri gösterilmektedir. Tüm `combinable` sınıfı yöntemleri hakkında daha fazla bilgi için bkz. [combinable Class](../../parallel/concrt/reference/combinable-class.md).

|Yöntem|Açıklama|
|------------|-----------------|
|[local](reference/combinable-class.md#local)|Geçerli iş parçacığı içeriğiyle ilişkili yerel değişkene bir başvuru alır.|
|[lediğiniz](reference/combinable-class.md#clear)|`combinable` nesnesinden tüm iş parçacığı yerel değişkenlerini kaldırır.|
|[bile](reference/combinable-class.md#combine)<br /><br /> [combine_each](reference/combinable-class.md#combine_each)|, Tüm iş parçacığı yerel hesaplamaları kümesinden son bir değer oluşturmak için, belirtilen birleştirme işlevini kullanır.|

`combinable` sınıfı, son birleştirilmiş sonuç üzerinde parametreli bir şablon sınıfıdır. Varsayılan oluşturucuyu çağırırsanız, `T` şablonu parametre türünün varsayılan Oluşturucusu ve bir kopya Oluşturucusu olmalıdır. `T` şablon parametre türünün varsayılan bir Oluşturucusu yoksa, kendi parametresi olarak bir başlatma işlevi alan oluşturucunun aşırı yüklenmiş sürümünü çağırın.

[Birleştirme](reference/combinable-class.md#combine) veya [combine_each](reference/combinable-class.md#combine_each) yöntemlerini çağırdıktan sonra `combinable` nesnesinde ek verileri saklayabilirsiniz. Ayrıca `combine` ve `combine_each` yöntemlerini birden çok kez çağırabilirsiniz. Bir `combinable` nesnesindeki yerel değer değişmediğinde, `combine` ve `combine_each` yöntemleri her çağrılışında aynı sonucu üretir.

###  <a name="combinable-examples"></a>Örnekler

`combinable` sınıfının kullanımıyla ilgili örnekler için aşağıdaki konulara bakın:

- [Nasıl yapılır: Performansı arttırmak için combinable Kullanma](../../parallel/concrt/how-to-use-combinable-to-improve-performance.md)

- [Nasıl yapılır: Kümeleri Birleştirmek için combinable Kullanma](../../parallel/concrt/how-to-use-combinable-to-combine-sets.md)

[[Üst](#top)]

## <a name="related-topics"></a>İlgili Konular

[Nasıl yapılır: Etkinliği Arttırmak için Paralel Kapsayıcılar Kullanma](../../parallel/concrt/how-to-use-parallel-containers-to-increase-efficiency.md)<br/>
Paralel kapsayıcıları kullanarak paralel olarak verileri nasıl depolamak ve verilere erişmek için nasıl kullanılacağını gösterir.

[Nasıl yapılır: Performansı arttırmak için combinable Kullanma](../../parallel/concrt/how-to-use-combinable-to-improve-performance.md)<br/>
Paylaşılan durumu ortadan kaldırmak için `combinable` sınıfının nasıl kullanılacağını gösterir ve bu sayede performansı geliştirir.

[Nasıl yapılır: Kümeleri Birleştirmek için combinable Kullanma](../../parallel/concrt/how-to-use-combinable-to-combine-sets.md)<br/>
İş parçacığı yerel veri kümelerini birleştirmek için `combine` işlevinin nasıl kullanılacağını gösterir.

[Paralel Desen Kitaplığı (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md)<br/>
Eşzamanlı uygulamalar geliştirmek için ölçeklenebilirliği ve kullanım kolaylığını kolaylaştıran bir zorunlu programlama modeli sağlayan PPL 'yi açıklar.

## <a name="reference"></a>Başvuru

[concurrent_vector Sınıfı](../../parallel/concrt/reference/concurrent-vector-class.md)

[concurrent_queue Sınıfı](../../parallel/concrt/reference/concurrent-queue-class.md)

[concurrent_unordered_map Sınıfı](../../parallel/concrt/reference/concurrent-unordered-map-class.md)

[concurrent_unordered_multimap Sınıfı](../../parallel/concrt/reference/concurrent-unordered-multimap-class.md)

[concurrent_unordered_set Sınıfı](../../parallel/concrt/reference/concurrent-unordered-set-class.md)

[concurrent_unordered_multiset Sınıfı](../../parallel/concrt/reference/concurrent-unordered-multiset-class.md)

[combinable Sınıfı](../../parallel/concrt/reference/combinable-class.md)
