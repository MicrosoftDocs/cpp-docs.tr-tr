---
title: Paralel Kapsayıcılar ve Nesneler
ms.date: 03/27/2019
helpviewer_keywords:
- parallel objects
- parallel containers
- concurrent containers
ms.assetid: 90ab715c-29cd-48eb-8e76-528619aab466
ms.openlocfilehash: f3fb2bb57c8bcf65de0a7f74f2992050d8257429
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81363053"
---
# <a name="parallel-containers-and-objects"></a>Paralel Kapsayıcılar ve Nesneler

Paralel Desenler Kitaplığı (PPL), öğelerine iş parçacığı için güvenli erişim sağlayan birkaç kapsayıcı ve nesne içerir.

*Eşzamanlı bir kapsayıcı,* en önemli işlemlere eşzamanlı güvenli erişim sağlar. Burada, eşzamanlılık güvenli işaretçiler veya yineleyiciler her zaman geçerli anlamına gelir. Bu, öğe başlatmanın veya belirli bir geçiş sırasının garantisi değildir. Bu kapsayıcıların işlevselliği, C++ Standart Kitaplığı tarafından sağlananlara benzer. Örneğin, [eşzamanlılık::concurrent_vector](../../parallel/concrt/reference/concurrent-vector-class.md) sınıfı [std benzer::vektör](../../standard-library/vector-class.md) sınıfı, `concurrent_vector` sınıf paralel öğeleri ek sağlar dışında. Aynı kapsayıcıya hem okuma hem de yazma erişimi gerektiren paralel kodunuz varsa eşzamanlı kapsayıcılar kullanın.

Eşzamanlı bir *nesne* bileşenler arasında aynı anda paylaşılır. Eşzamanlı bir nesnenin durumunu paralel olarak hesaplayan bir işlem, aynı durumu seri olarak hesaplayan başka bir işlemle aynı sonucu üretir. [Eşzamanlılık::birleştirilebilir](../../parallel/concrt/reference/combinable-class.md) sınıf eşzamanlı nesne türüne bir örnektir. Sınıf, `combinable` hesaplamaları paralel olarak gerçekleştirmenize ve bu hesaplamaları nihai sonuca birleştirmenize olanak tanır. Paylaşılan bir değişkene veya kaynağa erişimi eşitlemek için bir eşitleme mekanizması (örneğin, bir mutex) kullandığınızda eşzamanlı nesneleri kullanın.

## <a name="sections"></a><a name="top"></a>Bölüm

Bu konu, aşağıdaki paralel kapsayıcıları ve nesneleri ayrıntılı olarak açıklar.

Eşzamanlı kapsayıcılar:

- [concurrent_vector Sınıfı](#vector)

  - [concurrent_vector ve vektör arasındaki farklar](#vector-differences)

  - [Eşzamanlılık Güvenli İşlemler](#vector-safety)

  - [Özel Durum Güvenliği](#vector-exceptions)

- [concurrent_queue Sınıfı](#queue)

  - [concurrent_queue ve sıra arasındaki farklar](#queue-differences)

  - [Eşzamanlılık Güvenli İşlemler](#queue-safety)

  - [Yineleyici Desteği](#queue-iterators)

- [concurrent_unordered_map Sınıfı](#unordered_map)

  - [concurrent_unordered_map ve unordered_map Arasındaki Farklar](#map-differences)

  - [Eşzamanlılık Güvenli İşlemler](#map-safety)

- [concurrent_unordered_multimap Sınıfı](#unordered_multimap)

- [concurrent_unordered_set Sınıfı](#unordered_set)

- [concurrent_unordered_multiset Sınıfı](#unordered_multiset)

Eşzamanlı nesneler:

- [birleştirilebilir Sınıf](#combinable)

  - [Yöntemler ve Özellikler](#combinable-features)

  - [Örnekler](#combinable-examples)

## <a name="concurrent_vector-class"></a><a name="vector"></a>concurrent_vector Sınıfı

[Eşzamanlılık::concurrent_vector](../../parallel/concrt/reference/concurrent-vector-class.md) sınıfı, [std::vektör](../../standard-library/vector-class.md) sınıfı gibi, öğelerine rasgele erişmenizi sağlayan bir sıra kapsayıcı sınıfıdır. Sınıf `concurrent_vector` eşzamanlılık güvenli ek ve öğe erişim işlemleri sağlar. Ek işlemleri varolan işaretçileri veya yineleyicileri geçersiz kılmaz. Yineleyici erişimi ve geçiş işlemleri de eşzamanlılık için güvenlidir. Burada, eşzamanlılık güvenli işaretçiler veya yineleyiciler her zaman geçerli anlamına gelir. Bu, öğe başlatmanın veya belirli bir geçiş sırasının garantisi değildir.

### <a name="differences-between-concurrent_vector-and-vector"></a><a name="vector-differences"></a>concurrent_vector ve vektör arasındaki farklar

Sınıf `concurrent_vector` `vector` sınıfa çok benzer. Bir `concurrent_vector` nesnedeki ek, öğe erişimi ve yineleyici erişim işlemlerinin karmaşıklığı, nesne `vector` yle aynıdır. Aşağıdaki noktalar, `concurrent_vector` aşağıdakilerden `vector`farklı olduğunu göstermektedir:

- Bir `concurrent_vector` nesneüzerindeki ek, öğe erişimi, yineleyici erişimi ve yineleyici geçiş işlemleri eşzamanlılık için güvenlidir.

- Öğeleri yalnızca nesnenin `concurrent_vector` sonuna ekleyebilirsiniz. Sınıf `concurrent_vector` `insert` yöntemi sağlamaz.

- Bir `concurrent_vector` nesne, ona eklediğinizde [taşı semantikkullanmaz.](../../cpp/rvalue-reference-declarator-amp-amp.md)

- Sınıf `concurrent_vector` `erase` veya `pop_back` yöntemleri sağlamaz. Olduğu `vector`gibi, [clear](reference/concurrent-vector-class.md#clear) bir `concurrent_vector` nesneden tüm öğeleri kaldırmak için açık yöntemi kullanın.

- Sınıf, `concurrent_vector` öğelerini bitişik olarak bellekte depolamaz. Bu nedenle, `concurrent_vector` sınıfı bir diziyi kullanabileceğiniz tüm şekillerde kullanamazsınız. Örneğin, tür `v` `concurrent_vector`adlı bir değişken için, ifade `&v[0]+2` tanımlanmamış davranış üretir.

- `concurrent_vector` Sınıf, [grow_by](reference/concurrent-vector-class.md#grow_by) ve [grow_to_at_least](reference/concurrent-vector-class.md#grow_to_at_least) yöntemlerini tanımlar. Bu yöntemler, eşzamanlılık güvenli olmaları dışında [yeniden boyutlandırma](reference/concurrent-vector-class.md#resize) yöntemine benzer.

- Bir `concurrent_vector` nesne, öğeyi eklediğinizde veya yeniden boyutlandırdığınızda öğelerini değiştirmez. Bu, varolan işaretçilerin ve yineleyicilerin eşzamanlı işlemler sırasında geçerli kalmasını sağlar.

- Çalışma zamanı türü `concurrent_vector` `bool`için özel bir sürümünü tanımlamaz.

### <a name="concurrency-safe-operations"></a><a name="vector-safety"></a>Eşzamanlılık Güvenli İşlemler

Bir `concurrent_vector` nesnenin boyutunu ekleyen veya artıran veya bir `concurrent_vector` nesnedeki bir öğeye erişen tüm yöntemler eşzamanlılık açısından güvenlidir. Burada, eşzamanlılık güvenli işaretçiler veya yineleyiciler her zaman geçerli anlamına gelir. Bu, öğe başlatmanın veya belirli bir geçiş sırasının garantisi değildir. Bu kuralın istisnası `resize` yöntemdir.

Aşağıdaki tabloda eşzamanlılık güvenli ortak `concurrent_vector` yöntemleri ve işleçleri gösterir.

||||
|-|-|-|
|[at](reference/concurrent-vector-class.md#at)|[Son -unda](reference/concurrent-vector-class.md#end)|[operatör&#91;&#93;](reference/concurrent-vector-class.md#operator_at)|
|[Başlamak](reference/concurrent-vector-class.md#begin)|[Ön](reference/concurrent-vector-class.md#front)|[push_back](reference/concurrent-vector-class.md#push_back)|
|[Geri](reference/concurrent-vector-class.md#back)|[grow_by](reference/concurrent-vector-class.md#grow_by)|[rbegin](reference/concurrent-vector-class.md#rbegin)|
|[Kapasite](reference/concurrent-vector-class.md#capacity)|[grow_to_at_least](reference/concurrent-vector-class.md#grow_to_at_least)|[Rend](reference/concurrent-vector-class.md#rend)|
|[empty](reference/concurrent-vector-class.md#empty)|[max_size](reference/concurrent-vector-class.md#max_size)|[Boyutu](reference/concurrent-vector-class.md#size)|

Çalışma zamanının C++ Standart Kitaplığı ile uyumluluk sağladığı `reserve`işlemler, örneğin, eşzamanlılık için güvenli değildir. Aşağıdaki tablo, eşzamanlılık güvenli olmayan ortak yöntemleri ve işleçleri gösterir.

|||
|-|-|
|[Atamak](reference/concurrent-vector-class.md#assign)|[Rezerve et](reference/concurrent-vector-class.md#reserve)|
|[Temizleyin](reference/concurrent-vector-class.md#clear)|[Yeni -den boyutlandırmak](reference/concurrent-vector-class.md#resize)|
|[işleç=](reference/concurrent-vector-class.md#operator_eq)|[shrink_to_fit](reference/concurrent-vector-class.md#shrink_to_fit)|

Varolan öğelerin değerini değiştiren işlemler eşzamanlılık açısından güvenli değildir. Eşzamanlı okuma ve yazma işlemlerini aynı veri öğesiyle eşitlemek için [reader_writer_lock](../../parallel/concrt/reference/reader-writer-lock-class.md) nesnesi gibi bir eşitleme nesnesi kullanın. Eşitleme nesneleri hakkında daha fazla bilgi için [bkz.](../../parallel/concrt/synchronization-data-structures.md)

Kullanmak `vector` `concurrent_vector`için kullanılan varolan kodu dönüştürdüğünüzde, eşzamanlı işlemler uygulamanızın davranışının değişmesine neden olabilir. Örneğin, bir `concurrent_vector` nesne üzerinde aynı anda iki görev gerçekleştiren aşağıdaki programı düşünün. İlk görev bir `concurrent_vector` nesneye ek öğeler ekler. İkinci görev, aynı nesnedeki tüm öğelerin toplamını hesaplar.

[!code-cpp[concrt-vector-safety#1](../../parallel/concrt/codesnippet/cpp/parallel-containers-and-objects_1.cpp)]

Yöntem eşzamanlılık güvenli olmasına rağmen, push_back yöntemine eşzamanlı bir çağrı değiştirmek `end` için döndürülen değere neden olur. [push_back](reference/concurrent-vector-class.md#push_back) `end` Yineleyicinin geçtiği öğelerin sayısı belirsizdir. Bu nedenle, bu program çalıştırmak her zaman farklı bir sonuç üretebilir. Öğe türü önemsiz olmadığında, bir yarış koşulunun `push_back` `end` ve aramalar arasında var olması mümkündür. Yöntem, `end` ayrılan ancak tam olarak başharfe atılmayan bir öğe döndürebilir.

### <a name="exception-safety"></a><a name="vector-exceptions"></a>Özel Durum Güvenliği

Bir büyüme veya atama işlemi bir özel durum `concurrent_vector` atarsa, nesnenin durumu geçersiz olur. Geçersiz durumda `concurrent_vector` olan bir nesnenin davranışı, aksi belirtilmedikçe tanımsızdır. Ancak, yıkıcı nesne geçersiz bir durumda olsa bile, nesnenin ayırdığı belleği her zaman boşaltır.

Vektör elemanlarının veri türü, `T`aşağıdaki gereksinimleri karşılamalıdır. Aksi takdirde, `concurrent_vector` sınıfın davranışı tanımsız.

- Yıkıcı atmemeli.

- Varsayılan veya kopya oluşturucu atarsa, yıkıcı `virtual` anahtar sözcüğü kullanılarak bildirilmemeli ve sıfır-başlatma bellekle doğru şekilde çalışması gerekir.

[[Üst](#top)]

## <a name="concurrent_queue-class"></a><a name="queue"></a>concurrent_queue Sınıfı

[Eşzamanlılık::concurrent_queue](../../parallel/concrt/reference/concurrent-queue-class.md) sınıfı, tıpkı [std::queue](../../standard-library/queue-class.md) sınıfı gibi, ön ve arka öğelerine erişmenizi sağlar. Sınıf `concurrent_queue` eşzamanlılık güvenli enqueue ve dequeue işlemleri sağlar. Burada, eşzamanlılık güvenli işaretçiler veya yineleyiciler her zaman geçerli anlamına gelir. Bu, öğe başlatmanın veya belirli bir geçiş sırasının garantisi değildir. Sınıf, `concurrent_queue` eşzamanlılık için güvenli olmayan yineleyici desteği de sağlar.

### <a name="differences-between-concurrent_queue-and-queue"></a><a name="queue-differences"></a>concurrent_queue ve sıra arasındaki farklar

Sınıf `concurrent_queue` `queue` sınıfa çok benzer. Aşağıdaki noktalar, `concurrent_queue` aşağıdakilerden `queue`farklı olduğunu göstermektedir:

- Bir `concurrent_queue` nesne üzerindeki enqueue ve dequeue işlemleri eşzamanlılık güvenlidir.

- Sınıf `concurrent_queue` eşzamanlılık güvenli olmayan yineleyici desteği sağlar.

- Sınıf `concurrent_queue` `front` veya `pop` yöntemleri sağlamaz. `concurrent_queue` Sınıf, [try_pop](reference/concurrent-queue-class.md#try_pop) yöntemini tanımlayarak bu yöntemlerin yerini alır.

- Sınıf `concurrent_queue` `back` yöntemi sağlamaz. Bu nedenle, sıranın sonuna başvuru yapamazsınız.

- Sınıf `concurrent_queue` yöntem yerine [unsafe_size](reference/concurrent-queue-class.md#unsafe_size) yöntemisağlar. `size` Yöntem `unsafe_size` eşzamanlılık güvenli değildir.

### <a name="concurrency-safe-operations"></a><a name="queue-safety"></a>Eşzamanlılık Güvenli İşlemler

Bir `concurrent_queue` nesneye sıralayan veya bir nesneyi dequeue'yi bozan tüm yöntemler eşzamanlılık için güvenlidir. Burada, eşzamanlılık güvenli işaretçiler veya yineleyiciler her zaman geçerli anlamına gelir. Bu, öğe başlatmanın veya belirli bir geçiş sırasının garantisi değildir.

Aşağıdaki tabloda eşzamanlılık güvenli ortak `concurrent_queue` yöntemleri ve işleçleri gösterir.

|||
|-|-|
|[empty](reference/concurrent-queue-class.md#empty)|[Itme](reference/concurrent-queue-class.md#push)|
|[Get_allocator](reference/concurrent-queue-class.md#get_allocator)|[try_pop](reference/concurrent-queue-class.md#try_pop)|

`empty` Yöntem eşzamanlılık güvenli olsa da, eşzamanlı bir işlem `empty` yöntem dönmeden önce sıranın büyümesine veya küçülmesine neden olabilir.

Aşağıdaki tablo, eşzamanlılık güvenli olmayan ortak yöntemleri ve işleçleri gösterir.

|||
|-|-|
|[Temizleyin](reference/concurrent-queue-class.md#clear)|[unsafe_end](reference/concurrent-queue-class.md#unsafe_end)|
|[unsafe_begin](reference/concurrent-queue-class.md#unsafe_begin)|[unsafe_size](reference/concurrent-queue-class.md#unsafe_size)|

### <a name="iterator-support"></a><a name="queue-iterators"></a>Yineleyici Desteği

Eşzamanlılık `concurrent_queue` güvenli olmayan yinelemeler sağlar. Bu yineleyicileri yalnızca hata ayıklama için kullanmanızı öneririz.

Bir `concurrent_queue` yineleyici öğeleri yalnızca ileri yönde iletilir. Aşağıdaki tablo, her yineleyicinin desteklediği işleçleri gösterir.

|İşleç|Açıklama|
|--------------|-----------------|
|`operator++`|Sıradaki sonraki öğeye ilerler. Bu işleç hem ön artış hem de artma sonrası semantik sağlamak için aşırı yüklenir.|
|`operator*`|Geçerli öğeye bir başvuru alır.|
|`operator->`|Geçerli öğeiçin bir işaretçi alır.|

[[Üst](#top)]

## <a name="concurrent_unordered_map-class"></a><a name="unordered_map"></a>concurrent_unordered_map Sınıfı

[Eşzamanlılık::concurrent_unordered_map](../../parallel/concrt/reference/concurrent-unordered-map-class.md) sınıfı, tıpkı std gibi bir bağdaştırıcı kapsayıcı [sınıfıdır::unordered_map](../../standard-library/unordered-map-class.md) sınıfı, std türündeki öğelerin değişen uzunluktaki sırasını kontrol [eder::pair\<const Key, Ty>](../../standard-library/pair-structure.md). Sıralanmamış bir haritayı, anahtar ve değer çiftine ekleyebileceğiniz veya anahtarla değer arayaabileceğiniz bir sözlük olarak düşünün. Bu sınıf, paylaşılan bir kapsayıcıya aynı anda erişmeniz, içine eklemeniz veya güncelleştirmeniz gereken birden çok iş parçacığı nız veya göreviniz olduğunda yararlıdır.

Aşağıdaki örnekte kullanmak `concurrent_unordered_map`için temel yapı yı gösterir. Bu örnek, ['a', 'i']aralığına karakter anahtarları ekler. İşlem sırası belirlenmedığından, her anahtar için son değer de belirlenmemiştir. Ancak, eklemeleri paralel olarak gerçekleştirmek güvenlidir.

[!code-cpp[concrt-unordered-map-structure#1](../../parallel/concrt/codesnippet/cpp/parallel-containers-and-objects_2.cpp)]

Bir harita gerçekleştirmek `concurrent_unordered_map` ve işlemi paralel olarak azaltmak için kullanan bir örnek için [bkz.](../../parallel/concrt/how-to-perform-map-and-reduce-operations-in-parallel.md)

### <a name="differences-between-concurrent_unordered_map-and-unordered_map"></a><a name="map-differences"></a>concurrent_unordered_map ve unordered_map Arasındaki Farklar

Sınıf `concurrent_unordered_map` `unordered_map` sınıfa çok benzer. Aşağıdaki noktalar, `concurrent_unordered_map` aşağıdakilerden `unordered_map`farklı olduğunu göstermektedir:

- , `erase` `bucket`, `bucket_count`, `bucket_size` ve `unsafe_erase`yöntemleri `unsafe_bucket` `unsafe_bucket_count`sırasıyla `unsafe_bucket_size`, , , ve , olarak adlandırılır. Adlandırma `unsafe_` kuralı, bu yöntemlerin eşzamanlılık için güvenli olmadığını gösterir. Eşzamanlılık güvenliği hakkında daha fazla bilgi için [Eşzamanlılık Güvenli Operasyonlar'a](#map-safety)bakın.

- Ekleme işlemleri varolan işaretçileri veya yineleyicileri geçersiz kılmaz veya haritada zaten var olan öğelerin sırasını değiştirmez. Ekleme ve geçiş işlemleri aynı anda oluşabilir.

- `concurrent_unordered_map`yalnızca ileri yinelemeyi destekler.

- Ekleme, `equal_range`'' tarafından döndürülen yineleyicileri geçersiz kılmaz veya güncelleştirmez. Ekleme, eşit olmayan öğeleri aralığın sonuna ekleyebilir. Başlangıç yineleyicisi eşit bir öğeyi işaret edin.

Kilitlenmeyi önlemek için, `concurrent_unordered_map` bellek ayırıcısını, karma işlevleri veya kullanıcı tanımlı diğer kodu aradığında kilit tutamaz. Ayrıca, karma işlevinin her zaman aynı değere eşit tuşları değerlendirdiğinden emin olmalısınız. En iyi karma işlevler anahtarları karma kod alanına eşit olarak dağıtır.

### <a name="concurrency-safe-operations"></a><a name="map-safety"></a>Eşzamanlılık Güvenli İşlemler

Sınıf `concurrent_unordered_map` eşzamanlılık güvenli ekleme ve öğe erişim işlemleri sağlar. Ekleme işlemleri varolan işaretçileri veya yineleyicileri geçersiz kılmaz. Yineleyici erişimi ve geçiş işlemleri de eşzamanlılık için güvenlidir. Burada, eşzamanlılık güvenli işaretçiler veya yineleyiciler her zaman geçerli anlamına gelir. Bu, öğe başlatmanın veya belirli bir geçiş sırasının garantisi değildir. Aşağıdaki tablo, eşzamanlılık `concurrent_unordered_map` güvenli sık kullanılan yöntemleri ve işleçleri gösterir.

|||||
|-|-|-|-|
|[at](reference/concurrent-unordered-map-class.md#at)|`count`|`find`|[key_eq](reference/concurrent-unordered-map-class.md#key_eq)|
|`begin`|`empty`|`get_allocator`|`max_size`|
|`cbegin`|`end`|`hash_function`|[operatör&#91;&#93;](reference/concurrent-unordered-map-class.md#operator_at)|
|`cend`|`equal_range`|[Ekle](reference/concurrent-unordered-map-class.md#insert)|`size`|

Yöntem `count` aynı anda çalışan iş parçacığı güvenli bir şekilde çağrılabilir olsa da, yeni bir değer aynı anda kapsayıcıya eklenirse farklı iş parçacıkları farklı sonuçlar alabilir.

Aşağıdaki tablo, eşzamanlılık güvenli olmayan yaygın olarak kullanılan yöntemleri ve işleçleri gösterir.

||||
|-|-|-|
|`clear`|`max_load_factor`|`rehash`|
|`load_factor`|[işleç=](reference/concurrent-unordered-map-class.md#operator_eq)

Bu yöntemlere ek olarak, ile `unsafe_` başlayan herhangi bir yöntem de eşzamanlılık güvenli değildir.

[[Üst](#top)]

## <a name="concurrent_unordered_multimap-class"></a><a name="unordered_multimap"></a>concurrent_unordered_multimap Sınıfı

[Eşzamanlılık::concurrent_unordered_multimap](../../parallel/concrt/reference/concurrent-unordered-multimap-class.md) sınıfı, birden çok `concurrent_unordered_map` değerin aynı anahtarla eşlemesine izin vermek dışında sınıfa yakından benzer. Ayrıca aşağıdaki şekillerde `concurrent_unordered_map` farklıdır:

- [concurrent_unordered_multimap::insert](reference/concurrent-unordered-multimap-class.md#insert) yöntemi yerine bir yineleyici `std::pair<iterator, bool>`döndürür.

- Sınıf `concurrent_unordered_multimap` ne `at` yöntem `operator[]` ne de sağlamaz.

Aşağıdaki örnekte kullanmak `concurrent_unordered_multimap`için temel yapı yı gösterir. Bu örnek, ['a', 'i']aralığına karakter anahtarları ekler. `concurrent_unordered_multimap`bir anahtarın birden çok değere sahip olmasını sağlar.

[!code-cpp[concrt-unordered-multimap-structure#1](../../parallel/concrt/codesnippet/cpp/parallel-containers-and-objects_3.cpp)]

[[Üst](#top)]

## <a name="concurrent_unordered_set-class"></a><a name="unordered_set"></a>concurrent_unordered_set Sınıfı

[Eşzamanlılık::concurrent_unordered_set](../../parallel/concrt/reference/concurrent-unordered-set-class.md) sınıfı, anahtar ve `concurrent_unordered_map` değer çiftleri yerine değerleri yönetmesi dışında sınıfa yakından benzer. Sınıf `concurrent_unordered_set` ne `at` yöntem `operator[]` ne de sağlamaz.

Aşağıdaki örnekte kullanmak `concurrent_unordered_set`için temel yapı yı gösterir. Bu örnek, ['a', 'i']aralığındaki karakter değerlerini ekler. Eklemeleri paralel olarak gerçekleştirmek güvenlidir.

[!code-cpp[concrt-unordered-set#1](../../parallel/concrt/codesnippet/cpp/parallel-containers-and-objects_4.cpp)]

[[Üst](#top)]

## <a name="concurrent_unordered_multiset-class"></a><a name="unordered_multiset"></a>concurrent_unordered_multiset Sınıfı

[Eşzamanlılık::concurrent_unordered_multiset](../../parallel/concrt/reference/concurrent-unordered-multiset-class.md) sınıfı, yinelenen değerlere izin verdiği dışında `concurrent_unordered_set` sınıfa yakından benzer. Ayrıca aşağıdaki şekillerde `concurrent_unordered_set` farklıdır:

- [concurrent_unordered_multiset::insert](reference/concurrent-unordered-multiset-class.md#insert) yöntemi yerine bir yineleyici `std::pair<iterator, bool>`döndürür.

- Sınıf `concurrent_unordered_multiset` ne `at` yöntem `operator[]` ne de sağlamaz.

Aşağıdaki örnekte kullanmak `concurrent_unordered_multiset`için temel yapı yı gösterir. Bu örnek, ['a', 'i']aralığındaki karakter değerlerini ekler. `concurrent_unordered_multiset`bir değerin birden çok kez oluşmasını sağlar.

[!code-cpp[concrt-unordered-multiset#1](../../parallel/concrt/codesnippet/cpp/parallel-containers-and-objects_5.cpp)]

[[Üst](#top)]

## <a name="combinable-class"></a><a name="combinable"></a>birleştirilebilir Sınıf

[Eşzamanlılık::birleştirilebilir](../../parallel/concrt/reference/combinable-class.md) sınıf, ince taneli hesaplamalar gerçekleştirmenize ve bu hesaplamaları nihai sonuca birleştirmenize olanak tanıyan yeniden kullanılabilir, iş parçacığı yerel depolama sağlar. Bir `combinable` nesneyi azaltma değişkeni olarak düşünebilirsiniz.

Sınıf, `combinable` çeşitli iş parçacıkları veya görevler arasında paylaşılan bir kaynağınız olduğunda yararlıdır. Sınıf, `combinable` paylaşılan kaynaklara kilitsiz bir şekilde erişim sağlayarak paylaşılan durumu ortadan kaldırmanıza yardımcı olur. Bu nedenle, bu sınıf, birden çok iş parçacığı paylaşılan verilere erişimi eşitlemek için bir eşitleme mekanizması, örneğin, bir mutex kullanarak bir alternatif sağlar.

### <a name="methods-and-features"></a><a name="combinable-features"></a>Yöntemler ve Özellikler

Aşağıdaki tabloda `combinable` sınıfın bazı önemli yöntemleri gösterilmektedir. Tüm `combinable` sınıf yöntemleri hakkında daha fazla bilgi [için, birleştirilebilir Sınıf'a](../../parallel/concrt/reference/combinable-class.md)bakın.

|Yöntem|Açıklama|
|------------|-----------------|
|[Yerel](reference/combinable-class.md#local)|Geçerli iş parçacığı bağlamıyla ilişkili yerel değişkene bir başvuru alır.|
|[Temizleyin](reference/combinable-class.md#clear)|Tüm iş parçacığı yerel değişkenlerini `combinable` nesneden kaldırır.|
|[combine](reference/combinable-class.md#combine)<br /><br /> [combine_each](reference/combinable-class.md#combine_each)|Tüm iş parçacığı yerel hesaplamaları kümesinden son bir değer oluşturmak için sağlanan birleştirme işlevini kullanır.|

Sınıf, `combinable` son birleştirilmiş sonuç üzerinde parametreli bir şablon sınıfıdır. Varsayılan oluşturucuyu çağırırsanız, `T` şablon parametre türünde varsayılan bir oluşturucu ve kopya oluşturucu olmalıdır. Şablon `T` parametre türünde varsayılan bir oluşturucu yoksa, parametresi olarak bir başlatma işlevi alan oluşturucunun aşırı yüklü sürümünü arayın.

`combinable` [Birleştirme](reference/combinable-class.md#combine) veya [combine_each](reference/combinable-class.md#combine_each) yöntemlerini aradıktan sonra ek verileri nesnede depolayabilirsiniz. Ayrıca `combine` ve `combine_each` yöntemleri birden çok kez arayabilirsiniz. Bir `combinable` nesnedeki yerel değer değişmezse, ve `combine` `combine_each` yöntemler çağrıldıkları her zaman aynı sonucu üretir.

### <a name="examples"></a><a name="combinable-examples"></a>Örnekler

`combinable` Sınıfın nasıl kullanılacağı yla ilgili örnekler için aşağıdaki konulara bakın:

- [Nasıl yapılır: Performansı arttırmak için combinable Kullanma](../../parallel/concrt/how-to-use-combinable-to-improve-performance.md)

- [Nasıl yapılır: Kümeleri Birleştirmek için combinable Kullanma](../../parallel/concrt/how-to-use-combinable-to-combine-sets.md)

[[Üst](#top)]

## <a name="related-topics"></a>İlgili Konular

[Nasıl yapılır: Etkinliği Arttırmak için Paralel Kapsayıcılar Kullanma](../../parallel/concrt/how-to-use-parallel-containers-to-increase-efficiency.md)<br/>
Verileri paralel olarak verimli bir şekilde depolamak ve erişmek için paralel kapsayıcıların nasıl kullanılacağını gösterir.

[Nasıl yapılır: Performansı arttırmak için combinable Kullanma](../../parallel/concrt/how-to-use-combinable-to-improve-performance.md)<br/>
Paylaşılan durumu ortadan `combinable` kaldırmak ve performansı artırmak için sınıfın nasıl kullanılacağını gösterir.

[Nasıl yapılır: Kümeleri Birleştirmek için combinable Kullanma](../../parallel/concrt/how-to-use-combinable-to-combine-sets.md)<br/>
İş parçacığı yerel `combine` veri kümelerini birleştirmek için bir işlevin nasıl kullanılacağını gösterir.

[Paralel Desen Kitaplığı (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md)<br/>
Eşzamanlı uygulamalar geliştirmek için ölçeklenebilirliği ve kullanım kolaylığını destekleyen zorunlu bir programlama modeli sağlayan PPL'yi açıklar.

## <a name="reference"></a>Başvuru

[concurrent_vector Sınıfı](../../parallel/concrt/reference/concurrent-vector-class.md)

[concurrent_queue Sınıfı](../../parallel/concrt/reference/concurrent-queue-class.md)

[concurrent_unordered_map Sınıfı](../../parallel/concrt/reference/concurrent-unordered-map-class.md)

[concurrent_unordered_multimap Sınıfı](../../parallel/concrt/reference/concurrent-unordered-multimap-class.md)

[concurrent_unordered_set Sınıfı](../../parallel/concrt/reference/concurrent-unordered-set-class.md)

[concurrent_unordered_multiset Sınıfı](../../parallel/concrt/reference/concurrent-unordered-multiset-class.md)

[birleştirilebilir Sınıf](../../parallel/concrt/reference/combinable-class.md)
