---
title: Paralel kapsayıcılar ve nesneler | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- parallel objects
- parallel containers
- concurrent containers
ms.assetid: 90ab715c-29cd-48eb-8e76-528619aab466
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cb06cf0c4e3e5868a0dadeefb30c2e75158d4e32
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46433393"
---
# <a name="parallel-containers-and-objects"></a>Paralel Kapsayıcılar ve Nesneler

Paralel Desen kitaplığı (PPL), çeşitli kapsayıcılar ve öğeleri için iş parçacığı açısından güvenli erişim sağlayan nesneleri içerir.

A *eşzamanlı kapsayıcı* en önemli işlemler eşzamanlı güvenli erişim sağlar. Bu kapsayıcıların işlevselliği, C++ Standart Kitaplığı tarafından sağlanan benzer. Örneğin, [concurrency::concurrent_vector](../../parallel/concrt/reference/concurrent-vector-class.md) sınıfına benzer [std::vector](../../standard-library/vector-class.md) ancak `concurrent_vector` sınıfı öğelerini paralel ekleme olanak tanır. Hem okuma hem de aynı kapsayıcıya yazma erişimi gerektiren paralel kod varsa eş zamanlı kapsayıcılar'ı kullanın.

A *eşzamanlı nesne* bileşenler arasında eşzamanlı olarak paylaşılır. Paralel eşzamanlı bir nesnenin durumu hesaplayan işlem aynı duruma seri olarak hesaplar. başka bir işlem olarak aynı sonucu üretir. [Concurrency::combinable](../../parallel/concrt/reference/combinable-class.md) sınıfı bir eş zamanlı nesne türünün bir örnek verilmiştir. `combinable` Sınıfı paralel hesaplamalar gerçekleştirin ve ardından bu hesaplamalar nihai sonucu halinde birleştirmek olanak tanır. Aksi takdirde bir eşitleme mekanizması, örneğin, bir mutex bir paylaşılan değişken ya da kaynağa erişimi eşitlemek için kullanacağınız eşzamanlı nesneleri kullanın.

##  <a name="top"></a> Bölümleri

Bu konuda aşağıdaki paralel kapsayıcılar ve nesneler ayrıntılı açıklanmaktadır.

Eş zamanlı kapsayıcılar:

- [concurrent_vector Sınıfı](#ctor)

   - [Concurrent_vector arasındaki farklar ve vektör](#ctor)

   - [Eşzamanlılık açısından güvenli işlemler](#ctor)

   - [Özel durum güvenliği](#ctor)

- [concurrent_queue Sınıfı](#queue)

   - [Concurrent_queue arasındaki farklar ve kuyruk](#queue-differences)

   - [Eşzamanlılık açısından güvenli işlemler](#queue-safety)

   - [Yineleyici desteği](#queue-iterators)

- [concurrent_unordered_map Sınıfı](#unordered_map)

   - [Concurrent_unordered_map arasındaki farklar ve unordered_map](#map-differences)

   - [Eşzamanlılık açısından güvenli işlemler](#map-safety)

- [concurrent_unordered_multimap Sınıfı](#unordered_multimap)

- [concurrent_unordered_set Sınıfı](#unordered_set)

- [concurrent_unordered_multiset Sınıfı](#unordered_multiset)

Eş zamanlı nesneler:

- [combinable Sınıfı](#combinable)

   - [Yöntemleri ve özellikleri](#combinable-features)

   - [Örnekler](#combinable-examples)

##  <a name="vector"></a> concurrent_vector sınıfı

[Concurrency::concurrent_vector](../../parallel/concrt/reference/concurrent-vector-class.md) olduğu gibi bir sıralı kapsayıcı sınıfı [std::vector](../../standard-library/vector-class.md) sınıfı, rastgele alt öğeleri erişmenizi sağlar. `concurrent_vector` Eşzamanlılık açısından güvenli sona Ekle sınıfını etkinleştirir ve öğe erişim işlemleri. Ekleme işlemleri mevcut işaretçiler veya yineleyiciler geçersiz değil. Yineleyici erişimi ve çapraz geçiş işlemlerine Ayrıca, eşzamanlılık açısından güvenli değildir.

###  <a name="vector-differences"></a> Concurrent_vector arasındaki farklar ve vektör

`concurrent_vector` Sınıfı çok benzeyen `vector` sınıfı. Ekleme, öğe erişimi ve yineleyici erişim işlemleri karmaşıklığı bir `concurrent_vector` nesnesi aynı olan bir `vector` nesne. Aşağıdaki noktaları nerede göstermek `concurrent_vector` farklıdır `vector`:

- Ekleme, öğe erişimi, yineleyici erişimi ve yineleyici çapraz geçiş işlemleri üzerinde bir `concurrent_vector` nesne, eşzamanlılık açısından güvenli.

- Yalnızca sonuna öğe ekleyebilirsiniz bir `concurrent_vector` nesne. `concurrent_vector` Sınıfı sağlamaz `insert` yöntemi.

- A `concurrent_vector` nesne kullanmaz [taşıma semantiği](../../cpp/rvalue-reference-declarator-amp-amp.md) zaman eklediğiniz şekilde.

- `concurrent_vector` Sınıfı sağlamaz `erase` veya `pop_back` yöntemleri. Olduğu gibi `vector`, kullanın [Temizle](reference/concurrent-vector-class.md#clear) tüm öğeleri kaldırmak için yöntemi bir `concurrent_vector` nesne.

- `concurrent_vector` Sınıfı depolamaz öğelerine bitişik bellek. Bu nedenle, kullanamazsınız `concurrent_vector` sınıfı bir dizi kullanabileceğiniz tüm yollar. Örneğin, adında bir değişken için `v` türü `concurrent_vector`, ifade `&v[0]+2` tanımlanmamış bir davranış üretir.

- `concurrent_vector` Sınıfı tanımlar [grow_by](reference/concurrent-vector-class.md#grow_by) ve [grow_to_at_least](reference/concurrent-vector-class.md#grow_to_at_least) yöntemleri. Bu yöntemlere benzer [yeniden boyutlandırma](reference/concurrent-vector-class.md#resize) yöntemi, eşzamanlılık açısından güvenli olmasını dışında.

- A `concurrent_vector` nesne değil dışında yeniden konumlandırmakta öğeleri eklenecek veya yeniden boyutlandırın. Bu, varolan işaretçilerin ve eş zamanlı işlemleri sırasında geçerli kalmasına yineleyiciler sağlar.

- Çalışma zamanı sürümünü tanımlamıyor `concurrent_vector` türünün `bool`.

###  <a name="vector-safety"></a> Eşzamanlılık açısından güvenli işlemler

Tüm yöntemleri eklemek veya boyutunu artırın bir `concurrent_vector` nesne ya da öğeye erişim bir `concurrent_vector` nesne, eşzamanlılık açısından güvenli olmalarını. Bu kuralın istisnası `resize` yöntemi.

Aşağıdaki tablo ortak gösterir `concurrent_vector` yöntemleri ve eşzamanlılık açısından güvenli olmalarını işleçleri.

||||
|-|-|-|

|[konumunda](reference/concurrent-vector-class.md#at)|[son](reference/concurrent-vector-class.md#end)|[işleci&#91;&#93;](reference/concurrent-vector-class.md#operator_at)||[ başlamak](reference/concurrent-vector-class.md#begin)|[ön](reference/concurrent-vector-class.md#front)|[push_back](reference/concurrent-vector-class.md#push_back)||[ Geri](reference/concurrent-vector-class.md#back)|[grow_by](reference/concurrent-vector-class.md#grow_by)|[rbegin](reference/concurrent-vector-class.md#rbegin)||[ Kapasite](reference/concurrent-vector-class.md#capacity)|[grow_to_at_least](reference/concurrent-vector-class.md#grow_to_at_least)|[rend](reference/concurrent-vector-class.md#rend)||[ boş](reference/concurrent-vector-class.md#empty)|[max_size](reference/concurrent-vector-class.md#max_size)|[boyutu](reference/concurrent-vector-class.md#size)|

Örneğin, çalışma zamanı C++ Standart kitaplığı ile uyumluluk sağlayan operations `reserve`, eşzamanlılık açısından güvenli değildir. Aşağıdaki tabloda, genel yöntemleri ve eşzamanlılık açısından güvenli değildir işleçlerini gösterir.

|||
|-|-|

|[Ata](reference/concurrent-vector-class.md#assign)|[rezerve](reference/concurrent-vector-class.md#reserve)||[ Temizle](reference/concurrent-vector-class.md#clear)|[yeniden boyutlandırma](reference/concurrent-vector-class.md#resize)||[ İşleç =](reference/concurrent-vector-class.md#operator_eq)|[shrink_to_fit](reference/concurrent-vector-class.md#shrink_to_fit)|

Var olan öğelerin değerini değiştiren işlemleri, eşzamanlılık açısından güvenli değildir. Bir eşitleme nesnesi gibi kullanan bir [reader_writer_lock](../../parallel/concrt/reference/reader-writer-lock-class.md) eşitleme eş zamanlı okuma ve yazma işlemleri için aynı veri öğesi için nesne. Eşitleme nesneleri hakkında daha fazla bilgi için bkz: [eşitleme veri yapıları](../../parallel/concrt/synchronization-data-structures.md).

Kullanan mevcut kodu dönüştürürken `vector` kullanılacak `concurrent_vector`, eşzamanlı işlemlerin davranışını değiştirmek için uygulamanızın neden olabilir. Örneğin, aşağıdaki program iki görevi aynı anda gerçekleştirir düşünün bir `concurrent_vector` nesne. Ek öğeler için ilk görev ekler bir `concurrent_vector` nesne. İkinci görev, aynı nesne içindeki tüm öğelerin toplamını hesaplar.

[!code-cpp[concrt-vector-safety#1](../../parallel/concrt/codesnippet/cpp/parallel-containers-and-objects_1.cpp)]

Ancak `end` yöntemidir, eşzamanlılık açısından güvenli, eş zamanlı çağrı [push_back](reference/concurrent-vector-class.md#push_back) yöntemi tarafından döndürülen değerin neden `end` değiştirmek için. Yineleyici trafiğiyle öğelerin sayısını belirsiz. Bu nedenle, bu program, onu çalıştıran her seferinde farklı bir sonuç üretebilir.

###  <a name="vector-exceptions"></a> Özel durum güvenliği

Bir büyüme veya atama işlemi, bir özel durumu oluşturursa, `concurrent_vector` Nesne geçersiz olur. Davranışını bir `concurrent_vector` geçersiz bir durumda nesne, aksi belirtilmediği sürece tanımlanmamış. Ancak, nesne geçersiz bir durumda bile yok edici her zaman nesneyi ayırır, bellek kazandırır.

Vector öğelerinin veri türü `T`, aşağıdaki gereksinimleri karşılaması gerekir. Aksi takdirde davranışını `concurrent_vector` sınıftır tanımlanmamış.

- Yok edici oluşturmamalıdır.

- Varsayılan veya kopya Oluşturucusu oluşturursa, yok edici kullanılarak bildirilmelidir değil `virtual` anahtar sözcüğü ve gerekir çalışma doğru bellek sıfır olarak başlatılır.

[[Üst](#top)]

##  <a name="queue"></a> concurrent_queue sınıfı

[Concurrency::concurrent_queue](../../parallel/concrt/reference/concurrent-queue-class.md) olduğu gibi sınıf [std::queue](../../standard-library/queue-class.md) sınıfı, kendi ön erişmek ve yedekleme öğeleri sağlar. `concurrent_queue` Eşzamanlı güvenli kuyruğa sağlar sınıfını ve sıradan çıkarma işlemleri. `concurrent_queue` Sınıf, eşzamanlılık açısından güvenli değildir yineleyici desteği de sağlar.

###  <a name="queue-differences"></a> Concurrent_queue arasındaki farklar ve kuyruk

`concurrent_queue` Sınıfı çok benzeyen `queue` sınıfı. Aşağıdaki noktaları nerede göstermek `concurrent_queue` farklıdır `queue`:

- Sıraya alma ve işlemleri üzerinde sıradan çıkarma bir `concurrent_queue` nesne, eşzamanlılık açısından güvenli.

- `concurrent_queue` Sınıf, eşzamanlılık açısından güvenli değildir yineleyici desteği sağlar.

- `concurrent_queue` Sınıfı sağlamaz `front` veya `pop` yöntemleri. `concurrent_queue` Sınıfı tanımlayarak bu yöntemleri değiştirir [try_pop](reference/concurrent-queue-class.md#try_pop) yöntemi.

- `concurrent_queue` Sınıfı sağlamaz `back` yöntemi. Bu nedenle, son sırasının başvuramaz.

- `concurrent_queue` Sağlar sınıfını [unsafe_size](reference/concurrent-queue-class.md#unsafe_size) yöntemi yerine `size` yöntemi. `unsafe_size` Yöntem eşzamanlı güvenli değil.

###  <a name="queue-safety"></a> Eşzamanlılık açısından güvenli işlemler

Tüm yöntemler, kuyruğa veya gelen sıradan bir `concurrent_queue` nesne, eşzamanlılık açısından güvenli.

Aşağıdaki tablo ortak gösterir `concurrent_queue` yöntemleri ve eşzamanlılık açısından güvenli olmalarını işleçleri.

|||
|-|-|
|[boş](reference/concurrent-queue-class.md#empty)|[push](reference/concurrent-queue-class.md#push)|
|[get_allocator](reference/concurrent-queue-class.md#get_allocator)|[try_pop](reference/concurrent-queue-class.md#try_pop)|

Ancak `empty` yöntem eşzamanlı güvenli, eş zamanlı işlemi büyütür veya küçültür önce kuyruk neden olabilir `empty` yöntemi döndürür.

Aşağıdaki tabloda, genel yöntemleri ve eşzamanlılık açısından güvenli değildir işleçlerini gösterir.

|||
|-|-|
|[Temizle](reference/concurrent-queue-class.md#clear)|[unsafe_end](reference/concurrent-queue-class.md#unsafe_end)|
|[unsafe_begin](reference/concurrent-queue-class.md#unsafe_begin)|[unsafe_size](reference/concurrent-queue-class.md#unsafe_size)|

###  <a name="queue-iterators"></a> Yineleyici desteği

`concurrent_queue` Eşzamanlılık açısından güvenli olmayan yineleyiciler sağlar. Hata ayıklama için yalnızca bu Yineleyicilerde kullanmanızı öneririz.

A `concurrent_queue` yineleyici yalnızca ileri yönde öğeleri erişir. Aşağıdaki tabloda, her yineleyici desteklediğini işleçler gösterilmektedir.

|İşleç|Açıklama|
|--------------|-----------------|
|`operator++`|Sıradaki sonraki öğeyi ilerler. Bu işleç, hem artırma öncesi ve artırma sonrası semantiği sağlamak için aşırı yüklendi.|
|`operator*`|Geçerli öğeye bir başvuru alır.|
|`operator->`|Geçerli öğeye bir işaretçi alır.|

[[Üst](#top)]

##  <a name="unordered_map"></a> concurrent_unordered_map sınıfı

[Concurrency::concurrent_unordered_map](../../parallel/concrt/reference/concurrent-unordered-map-class.md) olduğu gibi bir ilişkilendirilebilir kapsayıcıdır sınıfı [std::unordered_map](../../standard-library/unordered-map-class.md) sınıfı, bir türdekiöğelerindeğişenuzunluktakidizisinidenetleyen[std::pair\<const Key, Ty >](../../standard-library/pair-structure.md). Sırasız bir haritasını, bir anahtar ve değer çifti ekleyin veya anahtara göre bir değeri aramak bir sözlük olarak düşünün. Birden çok iş parçacığı veya eşzamanlı olarak paylaşılan kapsayıcısına erişmek, içine eklemek veya güncelleştirmek için olan görevler varsa, bu sınıf kullanışlıdır.

Aşağıdaki örnek kullanmak için temel yapısını gösterir `concurrent_unordered_map`. Bu örnekte karakter tuşları ['a', ' i'] aralığında ekler. İşlemlerin sırası saptanmamış olduğundan, her anahtar son değeri de belirlenmemiş. Ancak, paralel olarak eklemelerini gerçekleştirmek güvenlidir.

[!code-cpp[concrt-unordered-map-structure#1](../../parallel/concrt/codesnippet/cpp/parallel-containers-and-objects_2.cpp)]

Kullanan bir örnek için `concurrent_unordered_map` bir eşleme gerçekleştirme ve paralel işlem azaltmak için bkz: [nasıl yapılır: eşleme gerçekleştirme ve işlemleri paralel azaltma](../../parallel/concrt/how-to-perform-map-and-reduce-operations-in-parallel.md).

###  <a name="map-differences"></a> Concurrent_unordered_map arasındaki farklar ve unordered_map

`concurrent_unordered_map` Sınıfı çok benzeyen `unordered_map` sınıfı. Aşağıdaki noktaları nerede göstermek `concurrent_unordered_map` farklıdır `unordered_map`:

- `erase`, `bucket`, `bucket_count`, Ve `bucket_size` yöntemleri adlı `unsafe_erase`, `unsafe_bucket`, `unsafe_bucket_count`, ve `unsafe_bucket_size`sırasıyla. `unsafe_` Adlandırma kuralını gösteren bu yöntemler eşzamanlılık açısından güvenli değildir. Eşzamanlılık güvenliği hakkında daha fazla bilgi için bkz. [eşzamanlılık açısından güvenli işlemler](#map-safety).

- Varolan işaretçilerin veya yineleyiciler ekleme işlemleri geçersiz değil ya da bunlar haritada zaten öğelerin sırasını değiştirme. Ekleme ve geçiş işlemlerini eşzamanlı olarak gerçekleşebilir.

- `concurrent_unordered_map` destekler, yalnızca yineleme iletin.

- Ekleme etmez geçersiz kılmak veya tarafından döndürülen yineleyici güncelleştirme `equal_range`. Ekleme eşit olmayan öğeler aralığın sonuna ekleyebilirsiniz. Başlangıç yineleyici eşit bir öğeye işaret eder.

Kilitlenme, hiçbir yöntemi önlemeye yardımcı olmak için `concurrent_unordered_map` bellek ayırıcısı, karma işlevler veya başka bir kullanıcı tarafından tanımlanan kod çağırdığında bir kilit tutar. Ayrıca, karma işlev her zaman aynı değere eşit anahtarları değerlendirir emin olmanız gerekir. En iyi karma işlevlerini anahtarları arasında karma kodu alanı aynı şekilde dağıtın.

###  <a name="map-safety"></a> Eşzamanlılık açısından güvenli işlemler

`concurrent_unordered_map` Sınıfı, eşzamanlılık açısından güvenli INSERT ve öğe erişimi işlemleri sağlar. Ekleme işlemleri mevcut işaretçiler veya yineleyiciler geçersiz. Yineleyici erişimi ve çapraz geçiş işlemlerine Ayrıca, eşzamanlılık açısından güvenli değildir. Aşağıdaki tabloda yaygın olarak kullanılan gösterilmektedir `concurrent_unordered_map` yöntemleri ve eşzamanlılık açısından güvenli olmalarını işleçleri.

|||||
|-|-|-|-|
|[konumunda](reference/concurrent-unordered-map-class.md#at)|`count`|`find`|[key_eq](reference/concurrent-unordered-map-class.md#key_eq)|
|`begin`|`empty`|`get_allocator`|`max_size`|
|`cbegin`|`end`|`hash_function`|[işleci&#91;&#93;](reference/concurrent-unordered-map-class.md#operator_at)|
|`cend`|`equal_range`|[Ekle](reference/concurrent-unordered-map-class.md#insert)|`size`|

Ancak `count` yöntemi çağrıldığında güvenli iş parçacığı eşzamanlı olarak çalışan, yeni bir değer kapsayıcıya aynı anda eklenirse, farklı iş parçacıkları farklı sonuçlar alabilir.

Aşağıdaki tabloda, eşzamanlılık açısından güvenli değildir işleçlerini ve yaygın olarak kullanılan yöntemler gösterilmektedir.

||||
|-|-|-|
|`clear`|`max_load_factor`|`rehash`|
|`load_factor`|[operator=](reference/concurrent-unordered-map-class.md#operator_eq)

Bu yöntemlerin yanı sıra, herhangi bir yöntem ile başlayan `unsafe_` de eşzamanlılık açısından güvenli değildir.

[[Üst](#top)]

##  <a name="unordered_multimap"></a> concurrent_unordered_multimap sınıfı

[Concurrency::concurrent_unordered_multimap](../../parallel/concrt/reference/concurrent-unordered-multimap-class.md) sınıfı çok benzeyen `concurrent_unordered_map` dışında aynı anahtar için eşlemek birden çok değeri sağlar sınıfını. Bu da farklıdır `concurrent_unordered_map` aşağıdaki yollarla:

- [Concurrent_unordered_multimap::insert](reference/concurrent-unordered-multimap-class.md#insert) yöntemi yerine bir yineleyici döndüren `std::pair<iterator, bool>`.

- `concurrent_unordered_multimap` Sınıfı sağlamaz `operator[]` ya da `at` yöntemi.

Aşağıdaki örnek kullanmak için temel yapısını gösterir `concurrent_unordered_multimap`. Bu örnekte karakter tuşları ['a', ' i'] aralığında ekler. `concurrent_unordered_multimap` birden çok değer sağlamak bir anahtar sağlar.

[!code-cpp[concrt-unordered-multimap-structure#1](../../parallel/concrt/codesnippet/cpp/parallel-containers-and-objects_3.cpp)]

[[Üst](#top)]

##  <a name="unordered_set"></a> concurrent_unordered_set sınıfı

[Concurrency::concurrent_unordered_set](../../parallel/concrt/reference/concurrent-unordered-set-class.md) sınıfı çok benzeyen `concurrent_unordered_map` değerler yerine anahtar ve değer çiftlerini yönettiği dışında sınıf. `concurrent_unordered_set` Sınıfı sağlamaz `operator[]` ya da `at` yöntemi.

Aşağıdaki örnek kullanmak için temel yapısını gösterir `concurrent_unordered_set`. Bu örnekte karakter değerleri aralığı ['a', ' i'] ekler. Paralel olarak eklemelerini gerçekleştirmek güvenlidir.

[!code-cpp[concrt-unordered-set#1](../../parallel/concrt/codesnippet/cpp/parallel-containers-and-objects_4.cpp)]

[[Üst](#top)]

##  <a name="unordered_multiset"></a> concurrent_unordered_multiset sınıfı

[Concurrency::concurrent_unordered_multiset](../../parallel/concrt/reference/concurrent-unordered-multiset-class.md) sınıfı çok benzeyen `concurrent_unordered_set` için yinelenen değerler sağlayan dışında sınıf. Bu da farklıdır `concurrent_unordered_set` aşağıdaki yollarla:

- [Concurrent_unordered_multiset::insert](reference/concurrent-unordered-multiset-class.md#insert) yöntemi yerine bir yineleyici döndüren `std::pair<iterator, bool>`.

- `concurrent_unordered_multiset` Sınıfı sağlamaz `operator[]` ya da `at` yöntemi.

Aşağıdaki örnek kullanmak için temel yapısını gösterir `concurrent_unordered_multiset`. Bu örnekte karakter değerleri aralığı ['a', ' i'] ekler. `concurrent_unordered_multiset` birden çok kez gerçekleşmesi bir değer sağlar.

[!code-cpp[concrt-unordered-multiset#1](../../parallel/concrt/codesnippet/cpp/parallel-containers-and-objects_5.cpp)]

[[Üst](#top)]

##  <a name="combinable"></a> combinable sınıfı

[Concurrency::combinable](../../parallel/concrt/reference/combinable-class.md) sınıfı ayrıntılı hesaplamalar ve ardından bu hesaplamalar son sonucu bir birleştirme olanak tanıyan yeniden kullanılabilir, iş parçacığı yerel depolama sağlar. Kadar aklınıza gelebilecek bir `combinable` bir azaltma değişkeni olarak bir nesne.

`combinable` Sınıfı, birden çok iş parçacığı veya görevler arasında paylaşılan bir kaynak olduğunda yararlıdır. `combinable` Sınıfı, paylaşılan durum kilidi serbest bir şekilde paylaşılan kaynaklara erişim sağlayarak ortadan kaldırmanıza yardımcı olur. Bu nedenle, bu sınıf, birden fazla iş parçacığından Paylaşılan verilere erişimi eşitlemek için bir eşitleme mekanizması, örneğin, bir mutex kullanmaya alternatif sağlar.

###  <a name="combinable-features"></a> Yöntemleri ve özellikleri

Aşağıdaki tablo bazı önemli yöntemlerini gösterir `combinable` sınıfı. Tüm hakkında daha fazla bilgi için `combinable` sınıfı yöntemleri [combinable sınıfı](../../parallel/concrt/reference/combinable-class.md).

|Yöntem|Açıklama|
|------------|-----------------|
|[Yerel](reference/combinable-class.md#local)|Geçerli iş parçacığı bağlamı ile ilişkili olan bir yerel değişken bir başvuru alır.|
|[Temizle](reference/combinable-class.md#clear)|Tüm iş parçacığı yerel değişkenleri kaldırır `combinable` nesne.|
|[Birleştirme](reference/combinable-class.md#combine)<br /><br /> [combine_each](reference/combinable-class.md#combine_each)|Belirtilen birleştirme işlevi, tüm iş parçacığı-yerel hesaplamalar kümesinden son değer üretmek için kullanır.|

`combinable` Birleştirilmiş sonuç üzerinde parametreli bir şablon sınıfı. Varsayılan Oluşturucu çağırırsanız `T` şablon parametre türü varsayılan bir oluşturucu ve kopya oluşturucusu olmalıdır. Varsa `T` şablon parametre türü varsayılan bir oluşturucuya sahip değil, bir başlatma işlevi parametre olarak alan oluşturucu aşırı yüklenmiş sürümünü arayın.

Ek veri depolayabilir bir `combinable` çağırdıktan sonra nesne [birleştirmek](reference/combinable-class.md#combine) veya [combine_each](reference/combinable-class.md#combine_each) yöntemleri. Ayrıca, çağırabilirsiniz `combine` ve `combine_each` yöntemleri birden çok kez. Yerel hiçbir değer varsa bir `combinable` değişiklikleri, nesne `combine` ve `combine_each` yöntemleri çağrılır her zaman aynı sonucu üretir.

###  <a name="combinable-examples"></a> Örnekleri

Nasıl kullanılacağına dair örnekler `combinable` sınıfında, aşağıdaki konulara bakın:

- [Nasıl yapılır: Performansı arttırmak için combinable Kullanma](../../parallel/concrt/how-to-use-combinable-to-improve-performance.md)

- [Nasıl yapılır: Kümeleri Birleştirmek için combinable Kullanma](../../parallel/concrt/how-to-use-combinable-to-combine-sets.md)

[[Üst](#top)]

## <a name="related-topics"></a>İlgili Konular

[Nasıl yapılır: Etkinliği Arttırmak için Paralel Kapsayıcılar Kullanma](../../parallel/concrt/how-to-use-parallel-containers-to-increase-efficiency.md)<br/>
Verimli bir şekilde depolamak ve paralel verilere erişmek için paralel kapsayıcılar kullanma işlemi gösterilmektedir.

[Nasıl yapılır: Performansı arttırmak için combinable Kullanma](../../parallel/concrt/how-to-use-combinable-to-improve-performance.md)<br/>
Nasıl kullanılacağını gösterir `combinable` paylaşılan durumu ortadan kaldırmak için sınıf ve böylece performansı.

[Nasıl yapılır: Kümeleri Birleştirmek için combinable Kullanma](../../parallel/concrt/how-to-use-combinable-to-combine-sets.md)<br/>
Nasıl kullanılacağını gösteren bir `combine` iş parçacığı-yerel veri kümeleri birleştirmek için işlev.

[Paralel Desen Kitaplığı (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md)<br/>
PPL, ölçeklenebilirlik ve kolayca eş zamanlı uygulamalar geliştirmeye yönelik kullanım yükseltir kesinlik temelli bir programlama modeli sunar açıklar.

## <a name="reference"></a>Başvuru

[concurrent_vector Sınıfı](../../parallel/concrt/reference/concurrent-vector-class.md)

[concurrent_queue Sınıfı](../../parallel/concrt/reference/concurrent-queue-class.md)

[concurrent_unordered_map Sınıfı](../../parallel/concrt/reference/concurrent-unordered-map-class.md)

[concurrent_unordered_multimap Sınıfı](../../parallel/concrt/reference/concurrent-unordered-multimap-class.md)

[concurrent_unordered_set Sınıfı](../../parallel/concrt/reference/concurrent-unordered-set-class.md)

[concurrent_unordered_multiset Sınıfı](../../parallel/concrt/reference/concurrent-unordered-multiset-class.md)

[combinable Sınıfı](../../parallel/concrt/reference/combinable-class.md)
