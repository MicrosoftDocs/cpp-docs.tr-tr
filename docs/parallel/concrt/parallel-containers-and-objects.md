---
title: Paralel Kapsayıcılar ve Nesneler
ms.date: 03/27/2019
helpviewer_keywords:
- parallel objects
- parallel containers
- concurrent containers
ms.assetid: 90ab715c-29cd-48eb-8e76-528619aab466
ms.openlocfilehash: 7387173378e79a4707008a11846eab19d7ae4341
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88831794"
---
# <a name="parallel-containers-and-objects"></a>Paralel Kapsayıcılar ve Nesneler

Paralel Desenler kitaplığı (PPL), öğelerine iş parçacığı açısından güvenli erişim sağlayan çeşitli kapsayıcılar ve nesneler içerir.

*Eşzamanlı bir kapsayıcı* , en önemli işlemlere eşzamanlılık açısından güvenli erişim sağlar. Burada eşzamanlılık açısından güvenli, işaretçiler veya yineleyiciler her zaman geçerlidir. Bu, öğe başlatma garantisi veya belirli bir geçiş düzeni değildir. Bu kapsayıcıların işlevselliği, C++ standart kitaplığı tarafından sağlananlara benzer. Örneğin, [concurrency:: concurrent_vector](../../parallel/concrt/reference/concurrent-vector-class.md) sınıfı [std:: vector](../../standard-library/vector-class.md) sınıfına benzer, ancak `concurrent_vector` sınıf öğelerin paralel olarak eklenmesini sağlar. Aynı kapsayıcıya hem okuma hem de yazma erişimi gerektiren paralel kodunuz varsa, eş zamanlı kapsayıcıları kullanın.

*Eşzamanlı bir nesne* bileşenler arasında eşzamanlı olarak paylaşılır. Bir eşzamanlı nesnenin durumunu paralel olarak hesaplayan bir işlem, aynı durumu seri olarak hesaplayan başka bir işlemle aynı sonucu üretir. [Concurrency:: combinable](../../parallel/concrt/reference/combinable-class.md) sınıfı, eşzamanlı nesne türüne bir örnektir. `combinable`Sınıfı, hesaplamaları paralel olarak gerçekleştirmenize olanak tanır ve ardından bu hesaplamaları nihai bir sonuçla birleştirir. Paylaşılan bir değişkene veya kaynağa erişimi eşitlemek için başka bir eşitleme mekanizması (örneğin, bir mutex) kullandığınızda, eşzamanlı nesneleri kullanın.

## <a name="sections"></a><a name="top"></a> Başlıklı

Bu konuda, aşağıdaki paralel kapsayıcılar ve nesneler ayrıntılı olarak açıklanmaktadır.

Eşzamanlı kapsayıcılar:

- [concurrent_vector sınıfı](#vector)

  - [Concurrent_vector ve vektör arasındaki farklılıklar](#vector-differences)

  - [Eşzamanlılık güvenli Işlemler](#vector-safety)

  - [Özel durum güvenliği](#vector-exceptions)

- [concurrent_queue sınıfı](#queue)

  - [Concurrent_queue ve kuyruk arasındaki farklar](#queue-differences)

  - [Eşzamanlılık güvenli Işlemler](#queue-safety)

  - [Yineleyici desteği](#queue-iterators)

- [concurrent_unordered_map sınıfı](#unordered_map)

  - [Concurrent_unordered_map ve unordered_map arasındaki farklar](#map-differences)

  - [Eşzamanlılık güvenli Işlemler](#map-safety)

- [concurrent_unordered_multimap sınıfı](#unordered_multimap)

- [concurrent_unordered_set sınıfı](#unordered_set)

- [concurrent_unordered_multiset sınıfı](#unordered_multiset)

Eş zamanlı nesneler:

- [combinable Sınıfı](#combinable)

  - [Yöntemler ve Özellikler](#combinable-features)

  - [Örnekler](#combinable-examples)

## <a name="concurrent_vector-class"></a><a name="vector"></a> concurrent_vector sınıfı

[Concurrency:: concurrent_vector](../../parallel/concrt/reference/concurrent-vector-class.md) sınıfı, yalnızca [std:: vector](../../standard-library/vector-class.md) sınıfı gibi, öğelerine rastgele erişim sağlayan bir dizi kapsayıcı sınıfıdır. `concurrent_vector`Sınıfı eşzamanlılık açısından güvenli ekleme ve öğe erişim işlemleri sunar. Ekleme işlemleri varolan işaretçileri veya yineleyiciler geçersiz kılmaz. Yineleyici erişimi ve çapraz geçiş işlemleri de eşzamanlılık açısından güvenlidir. Burada eşzamanlılık açısından güvenli, işaretçiler veya yineleyiciler her zaman geçerlidir. Bu, öğe başlatma garantisi veya belirli bir geçiş düzeni değildir.

### <a name="differences-between-concurrent_vector-and-vector"></a><a name="vector-differences"></a> Concurrent_vector ve vektör arasındaki farklılıklar

`concurrent_vector`Sınıf, sınıfa yakından benzer `vector` . Bir nesne üzerinde Append, element Access ve yineleyici erişim işlemlerinin karmaşıklığı `concurrent_vector` bir nesne için aynıdır `vector` . Aşağıdaki noktalara göre nereden `concurrent_vector` farklı olduğu gösterilmektedir `vector` :

- Bir nesnedeki ekleme, öğe erişimi, yineleyici erişimi ve yineleyici çapraz geçiş işlemleri `concurrent_vector` eşzamanlılık açısından güvenlidir.

- Öğeleri yalnızca bir nesnenin sonuna ekleyebilirsiniz `concurrent_vector` . `concurrent_vector`Sınıfı `insert` yöntemini sağlamaz.

- Bir `concurrent_vector` nesne, sonuna eklediğinizde [taşıma semantiğini](../../cpp/rvalue-reference-declarator-amp-amp.md) kullanmaz.

- `concurrent_vector`Sınıfı `erase` veya `pop_back` yöntemlerini sağlamaz. İle olduğu gibi `vector` , bir nesneden tüm öğeleri kaldırmak için [clear](reference/concurrent-vector-class.md#clear) metodunu kullanın `concurrent_vector` .

- `concurrent_vector`Sınıfı, bitişik olarak öğelerini bellekte depolamaz. Bu nedenle, `concurrent_vector` bir diziyi kullanabileceğiniz tüm yollarla sınıfını kullanamazsınız. Örneğin, türünde adlı bir değişken için `v` `concurrent_vector` , ifade `&v[0]+2` tanımsız davranış üretir.

- `concurrent_vector`Sınıfı, [grow_by](reference/concurrent-vector-class.md#grow_by) ve [grow_to_at_least](reference/concurrent-vector-class.md#grow_to_at_least) yöntemlerini tanımlar. Bu yöntemler, eşzamanlılık açısından güvenli olmaları dışında [yeniden boyutlandırma](reference/concurrent-vector-class.md#resize) yöntemine benzer.

- Bir `concurrent_vector` nesne, eklediğinizde veya yeniden boyutlandırdığınızda kendi öğelerinin yerini almaz. Bu, mevcut işaretçiler ve yineleyicilerin eşzamanlı işlemler sırasında geçerli kalmasını sağlar.

- Çalışma zamanı, türü için özel bir sürümü tanımlamıyor `concurrent_vector` **`bool`** .

### <a name="concurrency-safe-operations"></a><a name="vector-safety"></a> Eşzamanlılık güvenli Işlemler

Bir nesnenin boyutunu ekleyen veya artıran `concurrent_vector` ya da bir nesne içindeki bir öğeye erişen tüm yöntemler `concurrent_vector` eşzamanlılık açısından güvenlidir. Burada eşzamanlılık açısından güvenli, işaretçiler veya yineleyiciler her zaman geçerlidir. Bu, öğe başlatma garantisi veya belirli bir geçiş düzeni değildir. Bu kuralın özel durumu `resize` yöntemi olur.

Aşağıdaki tabloda `concurrent_vector` eşzamanlılık açısından güvenli olan ortak Yöntemler ve işleçler gösterilmektedir.

:::row:::
   :::column span="":::
      [`at`](reference/concurrent-vector-class.md#at)\
      [`back`](reference/concurrent-vector-class.md#back)\
      [`begin`](reference/concurrent-vector-class.md#begin)\
      [`capacity`](reference/concurrent-vector-class.md#capacity)
   :::column-end:::
   :::column span="":::
      [`empty`](reference/concurrent-vector-class.md#empty)\
      [`end`](reference/concurrent-vector-class.md#end)\
      [`front`](reference/concurrent-vector-class.md#front)\
      [`grow_by`](reference/concurrent-vector-class.md#grow_by)
   :::column-end:::
   :::column span="":::
      [`grow_to_at_least`](reference/concurrent-vector-class.md#grow_to_at_least)\
      [`max_size`](reference/concurrent-vector-class.md#max_size)\
      [`operator[]`](reference/concurrent-vector-class.md#operator_at)\
      [`push_back`](reference/concurrent-vector-class.md#push_back)
   :::column-end:::
   :::column span="":::
      [`rbegin`](reference/concurrent-vector-class.md#rbegin)\
      [`rend`](reference/concurrent-vector-class.md#rend)\
      [`size`](reference/concurrent-vector-class.md#size)
   :::column-end:::
:::row-end:::

Çalışma zamanının C++ standart kitaplığıyla uyumluluk için sağladığı işlemler, örneğin, `reserve` eşzamanlılık açısından güvenli değildir. Aşağıdaki tabloda eşzamanlılık güvenli olmayan ortak Yöntemler ve işleçler gösterilmektedir.

:::row:::
   :::column span="":::
      [`assign`](reference/concurrent-vector-class.md#assign)\
      [`clear`](reference/concurrent-vector-class.md#clear)
   :::column-end:::
   :::column span="":::
      [`operator=`](reference/concurrent-vector-class.md#operator_eq)\
      [`reserve`](reference/concurrent-vector-class.md#reserve)
   :::column-end:::
   :::column span="":::
      [`resize`](reference/concurrent-vector-class.md#resize)
   :::column-end:::
   :::column span="":::
      [`shrink_to_fit`](reference/concurrent-vector-class.md#shrink_to_fit)
   :::column-end:::
:::row-end:::

Mevcut öğelerin değerini değiştiren işlemler eşzamanlılık açısından güvenli değildir. Aynı veri öğesiyle eşzamanlı okuma ve yazma işlemlerini eşitlemek için [reader_writer_lock](../../parallel/concrt/reference/reader-writer-lock-class.md) nesnesi gibi bir eşitleme nesnesi kullanın. Eşitleme nesneleri hakkında daha fazla bilgi için bkz. [eşitleme veri yapıları](../../parallel/concrt/synchronization-data-structures.md).

Kullanan mevcut kodu dönüştürdüğünüzde `vector` `concurrent_vector` , eşzamanlı işlemler uygulamanızın davranışının değişmesine neden olabilir. Örneğin, bir nesne üzerinde aynı anda iki görevi gerçekleştiren aşağıdaki programı göz önünde bulundurun `concurrent_vector` . İlk görev, bir nesneye ek öğeler ekler `concurrent_vector` . İkinci görev, aynı nesnedeki tüm öğelerin toplamını hesaplar.

[!code-cpp[concrt-vector-safety#1](../../parallel/concrt/codesnippet/cpp/parallel-containers-and-objects_1.cpp)]

`end`Yöntemi eşzamanlılık açısından güvenli olsa da, [push_back](reference/concurrent-vector-class.md#push_back) metoduna eşzamanlı bir çağrı tarafından döndürülen değerin değişmesine neden olur `end` . Yineleyicinin geçtiği öğe sayısı belirsiz. Bu nedenle, bu program her çalıştırdığınızda farklı bir sonuç oluşturabilir. Öğe türü önemsiz olmadığında, bir yarış koşulunun ve çağrıları arasında mevcut olması mümkündür `push_back` `end` . `end`Yöntemi ayrılan, ancak tam olarak başlatılmamış bir öğe döndürebilir.

### <a name="exception-safety"></a><a name="vector-exceptions"></a> Özel durum güvenliği

Bir büyüme veya atama işlemi bir özel durum oluşturursa, `concurrent_vector` nesnenin durumu geçersiz hale gelir. `concurrent_vector`Geçersiz durumda olan bir nesnenin davranışı, aksi belirtilmedikçe tanımsız olur. Ancak, yıkıcı her zaman nesnenin ayırdığı belleği serbest bırakır, nesne geçersiz bir durumda olsa bile.

Vektör öğelerinin veri türü, `T` aşağıdaki gereksinimleri karşılamalıdır. Aksi takdirde, `concurrent_vector` sınıfının davranışı tanımsızdır.

- Yok edicinin throw olmaması gerekir.

- Varsayılan veya kopya Oluşturucu oluşturursa, yıkıcının anahtar sözcüğü kullanılarak bildirilemediği **`virtual`** ve sıfır ile başlatılmış bellekle düzgün çalışması gerekir.

[[Üst](#top)]

## <a name="concurrent_queue-class"></a><a name="queue"></a> concurrent_queue sınıfı

Yalnızca [std:: Queue](../../standard-library/queue-class.md) sınıfı gibi [concurrency:: concurrent_queue](../../parallel/concrt/reference/concurrent-queue-class.md) sınıfı, ön ve arka öğelerine erişmenizi sağlar. `concurrent_queue`Sınıfı eşzamanlılık güvenli sıraya alma ve sıradan çıkarma işlemlerine izin vermez. Burada eşzamanlılık açısından güvenli, işaretçiler veya yineleyiciler her zaman geçerlidir. Bu, öğe başlatma garantisi veya belirli bir geçiş düzeni değildir. `concurrent_queue`Sınıfı ayrıca eşzamanlılık güvenli olmayan Yineleyici desteği sağlar.

### <a name="differences-between-concurrent_queue-and-queue"></a><a name="queue-differences"></a> Concurrent_queue ve kuyruk arasındaki farklar

`concurrent_queue`Sınıf, sınıfa yakından benzer `queue` . Aşağıdaki noktalara göre nereden `concurrent_queue` farklı olduğu gösterilmektedir `queue` :

- Bir nesne üzerindeki sıraya alma ve sıradan çıkarma işlemleri `concurrent_queue` eşzamanlılık açısından güvenlidir.

- `concurrent_queue`Sınıfı eşzamanlılık güvenli olmayan Yineleyici desteği sağlar.

- `concurrent_queue`Sınıfı `front` veya `pop` yöntemlerini sağlamaz. `concurrent_queue`Sınıfı, [try_pop](reference/concurrent-queue-class.md#try_pop) yöntemini tanımlayarak bu yöntemlerin yerini alır.

- `concurrent_queue`Sınıfı `back` yöntemini sağlamaz. Bu nedenle, sıranın sonuna başvurulamıyor.

- `concurrent_queue`Sınıfı yöntemi yerine [unsafe_size](reference/concurrent-queue-class.md#unsafe_size) yöntemi sağlar `size` . `unsafe_size`Yöntem eşzamanlılık açısından güvenli değildir.

### <a name="concurrency-safe-operations"></a><a name="queue-safety"></a> Eşzamanlılık güvenli Işlemler

Bir nesneden sıraya alınan veya sıradan oluşturulan tüm yöntemler `concurrent_queue` eşzamanlılık açısından güvenlidir. Burada eşzamanlılık açısından güvenli, işaretçiler veya yineleyiciler her zaman geçerlidir. Bu, öğe başlatma garantisi veya belirli bir geçiş düzeni değildir.

Aşağıdaki tabloda `concurrent_queue` eşzamanlılık açısından güvenli olan ortak Yöntemler ve işleçler gösterilmektedir.

:::row:::
   :::column span="":::
      [`empty`](reference/concurrent-queue-class.md#empty)
   :::column-end:::
   :::column span="":::
      [`get_allocator`](reference/concurrent-queue-class.md#get_allocator)
   :::column-end:::
   :::column span="":::
      [`push`](reference/concurrent-queue-class.md#push)
   :::column-end:::
   :::column span="":::
      [`try_pop`](reference/concurrent-queue-class.md#try_pop)
   :::column-end:::
:::row-end:::

`empty`Yöntemi eşzamanlılık açısından güvenli olsa da, eşzamanlı bir işlem, yöntemin dönüşmeden önce sıranın büyümesine veya küçültülmesine neden olabilir `empty` .

Aşağıdaki tabloda eşzamanlılık güvenli olmayan ortak Yöntemler ve işleçler gösterilmektedir.

:::row:::
   :::column span="":::
      [`clear`](reference/concurrent-queue-class.md#clear)
   :::column-end:::
   :::column span="":::
      [`unsafe_begin`](reference/concurrent-queue-class.md#unsafe_begin)
   :::column-end:::
   :::column span="":::
      [`unsafe_end`](reference/concurrent-queue-class.md#unsafe_end)
   :::column-end:::
   :::column span="":::
      [`unsafe_size`](reference/concurrent-queue-class.md#unsafe_size)
   :::column-end:::
:::row-end:::

### <a name="iterator-support"></a><a name="queue-iterators"></a> Yineleyici desteği

`concurrent_queue`Eşzamanlılık güvenli olmayan yineleyiciler sağlar. Bu yineleyiciler yalnızca hata ayıklama için kullanmanızı öneririz.

`concurrent_queue`Yineleyici, öğeleri yalnızca iletme yönünde geçer. Aşağıdaki tabloda her bir yineleyicinin desteklediği işleçler gösterilmektedir.

|İşleç|Açıklama|
|--------------|-----------------|
|`operator++`|Kuyruktaki bir sonraki öğeye ilerler. Bu işleç, hem ön artışı hem de artış sonrası semantiğini sağlamak için aşırı yüklenmiştir.|
|`operator*`|Geçerli öğeye bir başvuru alır.|
|`operator->`|Geçerli öğe için bir işaretçi alır.|

\[[Üst](#top)]

## <a name="concurrent_unordered_map-class"></a><a name="unordered_map"></a> concurrent_unordered_map sınıfı

[Concurrency:: concurrent_unordered_map](../../parallel/concrt/reference/concurrent-unordered-map-class.md) sınıfı, [std:: unordered_map](../../standard-library/unordered-map-class.md) sınıfında olduğu gibi, [std::p Air \<const Key, Ty> ](../../standard-library/pair-structure.md)türünde öğelerin değişen uzunluklu bir dizisini kontrol eden ilişkilendirilebilir bir kapsayıcı sınıfıdır. Sıralanmamış bir eşlemeyi, anahtar ve değer çifti ekleyebileceğiniz veya anahtara göre bir değer aramak için bir sözlük olarak düşünün. Bu sınıf, paylaşılan bir kapsayıcıya eşzamanlı olarak erişmesi gereken birden çok iş parçacığı veya göreviniz olduğunda, içine eklemek veya güncelleştirmek için yararlıdır.

Aşağıdaki örnek, kullanmak için temel yapıyı gösterir `concurrent_unordered_map` . Bu örnek [' a ', ' i '] aralığına karakter anahtarları ekler. İşlem sırası belirlenmediğinden, her anahtar için son değer de saptanmamış olur. Ancak, eklemeleri paralel yapmak güvenlidir.

[!code-cpp[concrt-unordered-map-structure#1](../../parallel/concrt/codesnippet/cpp/parallel-containers-and-objects_2.cpp)]

`concurrent_unordered_map`Bir eşleme gerçekleştirmek ve işlemi paralel olarak azaltmak için kullanan bir örnek için bkz. [nasıl yapılır: eşleme gerçekleştirme ve işlemleri paralel olarak azaltma](../../parallel/concrt/how-to-perform-map-and-reduce-operations-in-parallel.md).

### <a name="differences-between-concurrent_unordered_map-and-unordered_map"></a><a name="map-differences"></a> Concurrent_unordered_map ve unordered_map arasındaki farklar

`concurrent_unordered_map`Sınıf, sınıfa yakından benzer `unordered_map` . Aşağıdaki noktalara göre nereden `concurrent_unordered_map` farklı olduğu gösterilmektedir `unordered_map` :

- `erase`,, `bucket` Ve `bucket_count` `bucket_size` yöntemleri sırasıyla,,, `unsafe_erase` `unsafe_bucket` `unsafe_bucket_count` ve olarak adlandırılır `unsafe_bucket_size` . `unsafe_`Adlandırma kuralı, bu yöntemlerin eşzamanlılık açısından güvenli olmadığını gösterir. Eşzamanlılık güvenliği hakkında daha fazla bilgi için bkz. [eşzamanlılık güvenli işlemleri](#map-safety).

- Ekleme işlemleri mevcut işaretçileri veya yineleyicileri geçersiz kılmaz, ya da haritada zaten var olan öğelerin sırasını değiştirmezler. Ekleme ve çapraz geçiş işlemleri eşzamanlı olarak gerçekleşebilir.

- `concurrent_unordered_map` yalnızca ileri yinelemeyi destekler.

- Ekleme, tarafından döndürülen yineleyiciler geçersiz kılmaz veya güncelleştirmez `equal_range` . Ekleme, Aralık sonuna eşit olmayan öğeler ekleyebilir. Başlangıç yineleyicisi bir eşit öğeye işaret eder.

Kilitlenmeden kaçınmak için, `concurrent_unordered_map` bellek ayırıcı, karma işlevleri veya Kullanıcı tanımlı diğer kodları çağırdığında bir kilit tutma yöntemi yoktur. Ayrıca, karma işlevin her zaman aynı değere eşit anahtarları değerlendirdiğinden emin olmanız gerekir. En iyi karma işlevleri, anahtarları karma kod alanı genelinde bir yere dağıtır.

### <a name="concurrency-safe-operations"></a><a name="map-safety"></a> Eşzamanlılık güvenli Işlemler

`concurrent_unordered_map`Sınıfı eşzamanlılık güvenli ekleme ve öğe erişim işlemleri sunar. Ekleme işlemleri varolan işaretçileri veya yineleyiciler geçersiz kılmaz. Yineleyici erişimi ve çapraz geçiş işlemleri de eşzamanlılık açısından güvenlidir. Burada eşzamanlılık açısından güvenli, işaretçiler veya yineleyiciler her zaman geçerlidir. Bu, öğe başlatma garantisi veya belirli bir geçiş düzeni değildir. Aşağıdaki tabloda eşzamanlılık açısından güvenli olan yaygın olarak kullanılan `concurrent_unordered_map` Yöntemler ve işleçler gösterilmektedir.

:::row:::
   :::column span="":::
      [`at`](reference/concurrent-unordered-map-class.md#at)\
      [`begin`](reference/concurrent-unordered-map-class.md#begin)\
      [`cbegin`](reference/concurrent-unordered-map-class.md#cbegin)\
      [`cend`](reference/concurrent-unordered-map-class.md#cend)
   :::column-end:::
   :::column span="":::
      [`count`](reference/concurrent-unordered-map-class.md#count)\
      [`empty`](reference/concurrent-unordered-map-class.md#empty)\
      [`end`](reference/concurrent-unordered-map-class.md#cend)\
      [`equal_range`](reference/concurrent-unordered-map-class.md#equal_range)
   :::column-end:::
   :::column span="":::
      [`find`](reference/concurrent-unordered-map-class.md#find)\
      [`get_allocator`](reference/concurrent-unordered-map-class.md#get_allocator)\
      [`hash_function`](reference/concurrent-unordered-map-class.md#hash_function)\
      [`insert`](reference/concurrent-unordered-map-class.md#insert)
   :::column-end:::
   :::column span="":::
      [`key_eq`](reference/concurrent-unordered-map-class.md#key_eq)\
      [`max_size`](reference/concurrent-unordered-map-class.md#max_size)\
      [`operator[]`](./reference/concurrent-unordered-map-class.md#operator_at)\
      [`size`](reference/concurrent-unordered-map-class.md#size)
   :::column-end:::
:::row-end:::

`count`Yöntemi eşzamanlı çalışan iş parçacıklarından güvenle çağrılabilir olsa da, farklı iş parçacıkları kapsayıcıya aynı anda yeni bir değer eklenirse farklı sonuçlar alabilir.

Aşağıdaki tabloda eşzamanlılık güvenli olmayan yaygın olarak kullanılan yöntemler ve işleçler gösterilmektedir.

:::row:::
   :::column span="":::
      [`clear`](reference/concurrent-unordered-map-class.md#clear)\
      [`load_factor`](reference/concurrent-unordered-map-class.md#load_factor)
   :::column-end:::
   :::column span="":::
      [`max_load_factor`](reference/concurrent-unordered-map-class.md#max_load_factor)
   :::column-end:::
   :::column span="":::
      [`operator=`](reference/concurrent-unordered-map-class.md#operator_eq)
   :::column-end:::
   :::column span="":::
      [`rehash`](reference/concurrent-unordered-map-class.md#rehash)
   :::column-end:::
:::row-end:::

Bu yöntemlerin yanı sıra, ile başlayan tüm yöntemler `unsafe_` de eşzamanlılık açısından güvenli değildir.

[[Üst](#top)]

## <a name="concurrent_unordered_multimap-class"></a><a name="unordered_multimap"></a> concurrent_unordered_multimap sınıfı

[Concurrency:: concurrent_unordered_multimap](../../parallel/concrt/reference/concurrent-unordered-multimap-class.md) sınıfı, `concurrent_unordered_map` birden çok değerin aynı anahtarla eşleşmesini olanaklı hale, ancak sınıfa benzer. Ayrıca `concurrent_unordered_map` , aşağıdaki yollarla da farklılık gösterir:

- [Concurrent_unordered_multimap:: INSERT](reference/concurrent-unordered-multimap-class.md#insert) yöntemi yerine bir yineleyici döndürür `std::pair<iterator, bool>` .

- `concurrent_unordered_multimap`Sınıfı `operator[]` veya `at` yöntemi sağlamaz.

Aşağıdaki örnek, kullanmak için temel yapıyı gösterir `concurrent_unordered_multimap` . Bu örnek [' a ', ' i '] aralığına karakter anahtarları ekler. `concurrent_unordered_multimap` bir anahtarın birden çok değere sahip olmasını sağlar.

[!code-cpp[concrt-unordered-multimap-structure#1](../../parallel/concrt/codesnippet/cpp/parallel-containers-and-objects_3.cpp)]

[[Üst](#top)]

## <a name="concurrent_unordered_set-class"></a><a name="unordered_set"></a> concurrent_unordered_set sınıfı

[Concurrency:: concurrent_unordered_set](../../parallel/concrt/reference/concurrent-unordered-set-class.md) sınıfı, `concurrent_unordered_map` anahtar ve değer çiftleri yerine değerleri yönetmesi dışında sınıfına benzer. `concurrent_unordered_set`Sınıfı `operator[]` veya `at` yöntemi sağlamaz.

Aşağıdaki örnek, kullanmak için temel yapıyı gösterir `concurrent_unordered_set` . Bu örnek [' a ', ' i '] aralığındaki karakter değerlerini ekler. Eklemeleri paralel yapmak güvenlidir.

[!code-cpp[concrt-unordered-set#1](../../parallel/concrt/codesnippet/cpp/parallel-containers-and-objects_4.cpp)]

[[Üst](#top)]

## <a name="concurrent_unordered_multiset-class"></a><a name="unordered_multiset"></a> concurrent_unordered_multiset sınıfı

[Concurrency:: concurrent_unordered_multiset](../../parallel/concrt/reference/concurrent-unordered-multiset-class.md) sınıfı, `concurrent_unordered_set` yinelenen değerlere izin verdiğinden, sınıfa benzer. Ayrıca `concurrent_unordered_set` , aşağıdaki yollarla da farklılık gösterir:

- [Concurrent_unordered_multiset:: INSERT](reference/concurrent-unordered-multiset-class.md#insert) yöntemi yerine bir yineleyici döndürür `std::pair<iterator, bool>` .

- `concurrent_unordered_multiset`Sınıfı `operator[]` veya `at` yöntemi sağlamaz.

Aşağıdaki örnek, kullanmak için temel yapıyı gösterir `concurrent_unordered_multiset` . Bu örnek [' a ', ' i '] aralığındaki karakter değerlerini ekler. `concurrent_unordered_multiset` değerin birden çok kez gerçekleşmesini sağlar.

[!code-cpp[concrt-unordered-multiset#1](../../parallel/concrt/codesnippet/cpp/parallel-containers-and-objects_5.cpp)]

[[Üst](#top)]

## <a name="combinable-class"></a><a name="combinable"></a> combinable Sınıfı

[Concurrency:: combinable](../../parallel/concrt/reference/combinable-class.md) sınıfı, hassas hesaplamalar gerçekleştirmenizi ve ardından bu hesaplamaları nihai bir sonuçla birleştirmeye olanak tanıyan yeniden kullanılabilir, iş parçacığı yerel depolama alanı sağlar. Bir `combinable` nesneyi bir azaltma değişkeni olarak düşünebilirsiniz.

`combinable`Sınıfı, birkaç iş parçacığı veya görev arasında paylaşılan bir kaynağınız olduğunda faydalıdır. `combinable`Sınıfı, paylaşılan kaynaklara kilit boş bir şekilde erişim sağlayarak paylaşılan durumu ortadan kaldırmanıza yardımcı olur. Bu nedenle, bu sınıf, birden fazla iş parçacığından paylaşılan verilere erişimi eşitlemek için bir eşitleme mekanizması (örneğin, bir mutex) kullanılmasına alternatif sağlar.

### <a name="methods-and-features"></a><a name="combinable-features"></a> Yöntemler ve Özellikler

Aşağıdaki tabloda sınıfının bazı önemli yöntemleri gösterilmektedir `combinable` . Tüm sınıf yöntemleri hakkında daha fazla bilgi için `combinable` bkz. [combinable Class](../../parallel/concrt/reference/combinable-class.md).

|Yöntem|Açıklama|
|------------|-----------------|
|[Yerel](reference/combinable-class.md#local)|Geçerli iş parçacığı içeriğiyle ilişkili yerel değişkene bir başvuru alır.|
|[lediğiniz](reference/combinable-class.md#clear)|Nesnesinden tüm iş parçacığı yerel değişkenlerini kaldırır `combinable` .|
|[combine](reference/combinable-class.md#combine)<br /><br /> [combine_each](reference/combinable-class.md#combine_each)|, Tüm iş parçacığı yerel hesaplamaları kümesinden son bir değer oluşturmak için, belirtilen birleştirme işlevini kullanır.|

`combinable`Sınıfı, son birleştirilmiş sonuç üzerinde parametreli bir şablon sınıfıdır. Varsayılan oluşturucuyu çağırırsanız, `T` şablon parametre türünün varsayılan Oluşturucusu ve bir kopya Oluşturucusu olmalıdır. `T`Şablon parametre türünün varsayılan bir Oluşturucusu yoksa, bir başlatma işlevini parametresi olarak alan oluşturucunun aşırı yüklenmiş sürümünü çağırın.

`combinable` [Birleştirme](reference/combinable-class.md#combine) veya [combine_each](reference/combinable-class.md#combine_each) yöntemlerini çağırdıktan sonra, bir nesnede ek verileri saklayabilirsiniz. `combine`Ve `combine_each` yöntemlerini birden çok kez de çağırabilirsiniz. Bir nesnede yerel değer `combinable` değişmediğinde, `combine` ve `combine_each` yöntemleri her çağrılışında aynı sonucu üretir.

### <a name="examples"></a><a name="combinable-examples"></a> Örnekler

Sınıfının nasıl kullanılacağına ilişkin örnekler için `combinable` aşağıdaki konulara bakın:

- [Nasıl yapılır: performansı artırmak için combinable kullanma](../../parallel/concrt/how-to-use-combinable-to-improve-performance.md)

- [Nasıl yapılır: kümeleri birleştirmek için combinable kullanma](../../parallel/concrt/how-to-use-combinable-to-combine-sets.md)

[[Üst](#top)]

## <a name="related-topics"></a>İlgili Konular

[Nasıl yapılır: verimliliği artırmak için paralel kapsayıcılar kullanma](../../parallel/concrt/how-to-use-parallel-containers-to-increase-efficiency.md)<br/>
Paralel kapsayıcıları kullanarak paralel olarak verileri nasıl depolamak ve verilere erişmek için nasıl kullanılacağını gösterir.

[Nasıl yapılır: performansı artırmak için combinable kullanma](../../parallel/concrt/how-to-use-combinable-to-improve-performance.md)<br/>
, `combinable` Paylaşılan durumu ortadan kaldırmak için sınıfının nasıl kullanılacağını gösterir ve bu sayede performansı geliştirir.

[Nasıl yapılır: kümeleri birleştirmek için combinable kullanma](../../parallel/concrt/how-to-use-combinable-to-combine-sets.md)<br/>
Bir `combine` işlevin iş parçacığı yerel veri kümelerini birleştirmek için nasıl kullanılacağını gösterir.

[Paralel Desen Kitaplığı (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md)<br/>
Eşzamanlı uygulamalar geliştirmek için ölçeklenebilirliği ve kullanım kolaylığını kolaylaştıran bir zorunlu programlama modeli sağlayan PPL 'yi açıklar.

## <a name="reference"></a>Başvuru

[concurrent_vector sınıfı](../../parallel/concrt/reference/concurrent-vector-class.md)

[concurrent_queue sınıfı](../../parallel/concrt/reference/concurrent-queue-class.md)

[concurrent_unordered_map sınıfı](../../parallel/concrt/reference/concurrent-unordered-map-class.md)

[concurrent_unordered_multimap sınıfı](../../parallel/concrt/reference/concurrent-unordered-multimap-class.md)

[concurrent_unordered_set sınıfı](../../parallel/concrt/reference/concurrent-unordered-set-class.md)

[concurrent_unordered_multiset sınıfı](../../parallel/concrt/reference/concurrent-unordered-multiset-class.md)

[combinable Sınıfı](../../parallel/concrt/reference/combinable-class.md)
