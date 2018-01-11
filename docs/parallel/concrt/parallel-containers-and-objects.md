---
title: "Paralel kapsayıcılar ve nesneler | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- parallel objects
- parallel containers
- concurrent containers
ms.assetid: 90ab715c-29cd-48eb-8e76-528619aab466
caps.latest.revision: "34"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9159b9c8170ee73afd8bee5305506a842368a231
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="parallel-containers-and-objects"></a>Paralel Kapsayıcılar ve Nesneler
Paralel Desen kitaplığı (PPL) birkaç kapsayıcıları ve bunların öğelerini iş parçacığı açısından güvenli erişim sağlayan nesneleri içerir.  
  
 A *eşzamanlı kapsayıcı* en önemli operations eşzamanlılık güvenli erişim sağlar. Bu kapsayıcıların işlevselliği, C++ Standart Kitaplığı tarafından sağlanan benzer. Örneğin, [concurrency::concurrent_vector](../../parallel/concrt/reference/concurrent-vector-class.md) sınıfı benzer [std::vector](../../standard-library/vector-class.md) ; tek fark sınıfı `concurrent_vector` sınıfı paralel öğeleri ekleme olanak sağlar. Eş zamanlı kapsayıcılar, hem okuma hem de aynı kapsayıcıya yazma erişimi gerektiren paralel kod sahip olduğunuzda kullanın.  
  
 A *eşzamanlı nesne* eşzamanlı olarak bileşenler arasında paylaşılır. Paralel eşzamanlı bir nesnenin durumu hesaplar bir işlem aynı duruma seri olarak hesaplar başka bir işlem olarak aynı sonucu verir. [Concurrency::combinable](../../parallel/concrt/reference/combinable-class.md) sınıfı eşzamanlı nesne türünün bir örnektir. `combinable` Sınıfı, paralel olarak hesaplamalar ve ardından bu hesaplamaların nihai sonucu içine birleştirme olanak sağlar. Aksi takdirde eşitleme mekanizması, örneğin, bir mutex paylaşılan değişken ya da kaynağa erişimi eşitlemek için kullanacağınız eşzamanlı nesneleri kullanın.  
  
##  <a name="top"></a>Bölümler  
 Bu konu aşağıdaki paralel kapsayıcılar ve nesneler ayrıntılı açıklar.  
  
 Eş zamanlı kapsayıcılar:  
  
-   [concurrent_vector Sınıfı](#ctor)  
  
    -   [Concurrent_vector arasındaki farklar ve vektör](#ctor)  
  
    -   [Eşzamanlılık uyumlu işlemler](#ctor)  
  
    -   [Özel durum güvenliği](#ctor)  
  
-   [concurrent_queue Sınıfı](#queue)  
  
    -   [Concurrent_queue arasındaki farklar ve sıra](#queue-differences)  
  
    -   [Eşzamanlılık uyumlu işlemler](#queue-safety)  
  
    -   [Yineleyici desteği](#queue-iterators)  
  
-   [concurrent_unordered_map Sınıfı](#unordered_map)  
  
    -   [Concurrent_unordered_map arasındaki farklar ve unordered_map](#map-differences)  
  
    -   [Eşzamanlılık uyumlu işlemler](#map-safety)  
  
-   [concurrent_unordered_multimap Sınıfı](#unordered_multimap)  
  
-   [concurrent_unordered_set Sınıfı](#unordered_set)  
  
-   [concurrent_unordered_multiset Sınıfı](#unordered_multiset)  
  
 Eşzamanlı nesneler:  
  
-   [combinable Sınıfı](#combinable)  
  
    -   [Yöntemleri ve özellikleri](#combinable-features)  
  
    -   [Örnekler](#combinable-examples)  
  
##  <a name="vector"></a>concurrent_vector sınıfı  
 [Concurrency::concurrent_vector](../../parallel/concrt/reference/concurrent-vector-class.md) sınıftır olduğu gibi bir dizi kapsayıcı [std::vector](../../standard-library/vector-class.md) sınıfı, rastgele öğeleri erişmenize olanak tanır. `concurrent_vector` Eşzamanlılık güvenli Ekle sınıfını etkinleştirir ve öğesi erişim işlemleri. Ekleme işlemleri mevcut işaretçileri veya yineleyiciler geçersiz değil. Yineleyici erişim ve çapraz geçiş işlemlerini de eşzamanlılık güvenlidir.  
  
###  <a name="vector-differences"></a>Concurrent_vector arasındaki farklar ve vektör  
 `concurrent_vector` Sınıfı çok benzeyen `vector` sınıfı. Ekle, öğe erişim ve yineleyici erişim işlemlerine karmaşıklığını bir `concurrent_vector` nesnesi aynı olan bir `vector` nesnesi. Aşağıdaki noktaları nerede göstermeye `concurrent_vector` farklıdır `vector`:  
  
-   Ekleme, öğesi erişim, yineleyici erişim ve yineleyici geçişi işlemler üzerinde bir `concurrent_vector` nesne eşzamanlılık güvenli.  
  
-   Öğeleri yalnızca sonuna ekleyebilirsiniz bir `concurrent_vector` nesnesi. `concurrent_vector` Sınıfı sağlamaz `insert` yöntemi.  
  
-   A `concurrent_vector` nesne kullanmaz [semantiği taşıma](../../cpp/rvalue-reference-declarator-amp-amp.md) zaman, eklemek için.  
  

-   `concurrent_vector` Sınıfı sağlamaz `erase` veya `pop_back` yöntemleri. İle `vector`, kullanın [temizleyin](reference/concurrent-vector-class.md#clear) tüm öğeleri kaldırmak için yöntemi bir `concurrent_vector` nesnesi.  
  
-   `concurrent_vector` Sınıfı saklamadığı öğeleri bitişik bellek. Bu nedenle, kullanamazsınız `concurrent_vector` bir dizi kullanabileceğiniz tüm yollar sınıfta. Örneğin, adlandırılmış bir değişken için `v` türü `concurrent_vector`, ifade `&v[0]+2` tanımsız davranış üretir.  
  
-   `concurrent_vector` Sınıfı tanımlayan [grow_by](reference/concurrent-vector-class.md#grow_by) ve [grow_to_at_least](reference/concurrent-vector-class.md#grow_to_at_least) yöntemleri. Bu yöntemlere benzer [yeniden boyutlandırma](reference/concurrent-vector-class.md#resize) yöntemi, eşzamanlılık güvenli olmasını dışında.  
  
-   A `concurrent_vector` nesnesi değil taşımanızı öğeleri eklenecek veya yeniden boyutlandırın. Bu, varolan işaretçiler ve eşzamanlı işlemleri sırasında geçerli kalmasına yineleyiciler sağlar.  
  
-   Çalışma zamanı özelleştirilmiş bir sürümünü tanımlamaz `concurrent_vector` türü için `bool`.  
  
###  <a name="vector-safety"></a>Eşzamanlılık uyumlu işlemler  
 Eklemek veya boyutunu artırın tüm yöntemleri bir `concurrent_vector` nesnesi veya bir öğedeki erişim bir `concurrent_vector` nesne, eşzamanlılık güvenlidir. Bu kural için özel durum `resize` yöntemi.  
  
 Aşağıdaki tabloda ortak gösterilmektedir `concurrent_vector` yöntemleri ve eşzamanlılık güvenli işleçler.  
  
||||  
|-|-|-|  

|[konumundaki](reference/concurrent-vector-class.md#at)|[son](reference/concurrent-vector-class.md#end)|[işleci &#91; &#93;](reference/concurrent-vector-class.md#operator_at)|  
|[Begin](reference/concurrent-vector-class.md#begin)|[ön](reference/concurrent-vector-class.md#front)|[push_back](reference/concurrent-vector-class.md#push_back)|  
|[Geri](reference/concurrent-vector-class.md#back)|[grow_by](reference/concurrent-vector-class.md#grow_by)|[rbegin](reference/concurrent-vector-class.md#rbegin)|  
|[Kapasite](reference/concurrent-vector-class.md#capacity)|[grow_to_at_least](reference/concurrent-vector-class.md#grow_to_at_least)|[rend](reference/concurrent-vector-class.md#rend)|  
|[boş](reference/concurrent-vector-class.md#empty)|[max_size](reference/concurrent-vector-class.md#max_size)|[boyutu](reference/concurrent-vector-class.md#size)|  

  
 Örneğin, çalışma zamanı C++ Standart kitaplığı ile uyumluluk için sağladığı işlemleri `reserve`, eşzamanlılık güvenli değildir. Aşağıdaki tabloda ortak yöntemleri ve eşzamanlılık güvenli olmayan işleçleri gösterir.  
  
|||  
|-|-|  

|[Ata](reference/concurrent-vector-class.md#assign)|[yedek](reference/concurrent-vector-class.md#reserve)|  
|[Clear](reference/concurrent-vector-class.md#clear)|[yeniden boyutlandırma](reference/concurrent-vector-class.md#resize)|  
|[operator =](reference/concurrent-vector-class.md#operator_eq)|[shrink_to_fit](reference/concurrent-vector-class.md#shrink_to_fit)|  
  
 Varolan öğeleri değerini değiştirme işlemleri eşzamanlılık güvenli değildir. Eşitleme nesnesi gibi kullandığınız bir [reader_writer_lock](../../parallel/concrt/reference/reader-writer-lock-class.md) eşitlemek eşzamanlı okuma ve yazma işlemleri için aynı veri öğesi için nesne. Eşitleme nesneleri hakkında daha fazla bilgi için bkz: [eşitleme veri yapıları](../../parallel/concrt/synchronization-data-structures.md).  
  
 Kullanan var olan kodu dönüştürürken `vector` kullanmak için `concurrent_vector`, eşzamanlı işlem davranışını değiştirmek için uygulamanızın neden olabilir. Örneğin, aynı anda iki görevi gerçekleştirir. aşağıdaki programı göz önünde bulundurun bir `concurrent_vector` nesnesi. Ek öğeler için ilk görev ekler bir `concurrent_vector` nesnesi. İkinci görev aynı nesnede tüm öğelerin toplamı, hesaplar.  
  
 [!code-cpp[concrt-vector-safety#1](../../parallel/concrt/codesnippet/cpp/parallel-containers-and-objects_1.cpp)]  
  

 Ancak `end` yöntemdir eşzamanlılık uyumlu eşzamanlı çağrı [push_back](reference/concurrent-vector-class.md#push_back) yöntemi tarafından döndürülen değer neden `end` değiştirmek için. Yineleyici geçeceğini öğeler belirsiz sayısıdır. Bu nedenle, bu program, onu çalıştıran her zaman farklı bir sonuç üretebilir.  
  
###  <a name="vector-exceptions"></a>Özel durum güvenliği  
 Büyüme veya atama işlemi, durumu aykırı varsa `concurrent_vector` nesnesi geçersiz olur. Davranışını bir `concurrent_vector` geçersiz bir durumda olan nesne, aksi belirtilmediği sürece tanımlanmadı. Ancak, nesne geçersiz bir durumda olsa bile yıkıcı her zaman nesne ayırır, bellek boşaltır.  
  
 Vektör öğelerin veri türü `T`, aşağıdaki gereksinimleri karşılaması gerekir. Aksi takdirde davranışını `concurrent_vector` sınıfı tanımlanmadı.  
  
-   Yok Edicisi throw gerekir değil.  
  
-   Varsayılan veya kopya Oluşturucu oluşturursa yıkıcı kullanılarak bildirilmelidir değil `virtual` anahtar sözcüğü ve onu gerekir iş doğru sıfır başlatılmış belleğe sahip.  
  
 [[Üst](#top)]  
  
##  <a name="queue"></a>concurrent_queue sınıfı  
 [Concurrency::concurrent_queue](../../parallel/concrt/reference/concurrent-queue-class.md) sınıfı, tıpkı [std::queue](../../standard-library/queue-class.md) sınıfı, kendi ön erişim ve yedekleme öğeleri sağlar. `concurrent_queue` Sınıfını etkinleştirir eşzamanlılık güvenli enqueue ve işlemleri dequeue. `concurrent_queue` Sınıfı eşzamanlılık güvenli değil yineleyici desteği sağlar.  
  
###  <a name="queue-differences"></a>Concurrent_queue arasındaki farklar ve sıra  
 `concurrent_queue` Sınıfı çok benzeyen `queue` sınıfı. Aşağıdaki noktaları nerede göstermeye `concurrent_queue` farklıdır `queue`:  
  
-   Sıraya alma ve üzerinde işlem dequeue bir `concurrent_queue` nesne eşzamanlılık güvenli.  
  
-   `concurrent_queue` Sınıfı eşzamanlılık güvenli değil yineleyici desteği sağlar.  
  

-   `concurrent_queue` Sınıfı sağlamaz `front` veya `pop` yöntemleri. `concurrent_queue` Sınıfı tanımlayarak bu yöntemleri değiştirir [try_pop](reference/concurrent-queue-class.md#try_pop) yöntemi.  
  
-   `concurrent_queue` Sınıfı sağlamaz `back` yöntemi. Bu nedenle, sıranın sonuna başvuramaz.  
  
-   `concurrent_queue` SAX [unsafe_size](reference/concurrent-queue-class.md#unsafe_size) yöntemi yerine `size` yöntemi. `unsafe_size` Yöntemi eşzamanlılık uyumlu değil.  

  
###  <a name="queue-safety"></a>Eşzamanlılık uyumlu işlemler  
 Tüm yöntemleri için bu kuyruğa veya gelen dequeue bir `concurrent_queue` nesne eşzamanlılık güvenli.  
  
 Aşağıdaki tabloda ortak gösterilmektedir `concurrent_queue` yöntemleri ve eşzamanlılık güvenli işleçler.  
  
|||  
|-|-|  
|[boş](reference/concurrent-queue-class.md#empty)|[push](reference/concurrent-queue-class.md#push)|  
|[get_allocator](reference/concurrent-queue-class.md#get_allocator)|[try_pop](reference/concurrent-queue-class.md#try_pop)|  


  
 Ancak `empty` eşzamanlılık güvenli yöntemdir, eş zamanlı bir işlemi büyütür veya küçültür önce kuyruk neden olabilirsiniz `empty` yöntemi döndürür.  
  
 Aşağıdaki tabloda ortak yöntemleri ve eşzamanlılık güvenli olmayan işleçleri gösterir.  
  
|||  
|-|-|  
|[Temizle](reference/concurrent-queue-class.md#clear)|[unsafe_end](reference/concurrent-queue-class.md#unsafe_end)|  
|[unsafe_begin](reference/concurrent-queue-class.md#unsafe_begin)|[unsafe_size](reference/concurrent-queue-class.md#unsafe_size)|  


  
###  <a name="queue-iterators"></a>Yineleyici desteği  
 `concurrent_queue` Eşzamanlılık güvenli olmayan yineleyiciler sağlar. Yalnızca hata ayıklama için bu yineleyiciler kullanmanızı öneririz.  
  
 A `concurrent_queue` yineleyici yalnızca ileri yönde öğeleri erişir. Aşağıdaki tabloda, her yineleyici desteklediğini işleçleri gösterir.  
  
|İşleç|Açıklama|  
|--------------|-----------------|  
|[operator ++](http://msdn.microsoft.com/en-us/4cfdd07e-927a-42f8-aaa0-d6881687f413)|Sırasındaki sonraki öğeye ilerler. Bu işleç öncesi artırma ve sonrası artışı semantiği sağlamak için aşırı yüklendi.|  
|[işleç *](http://msdn.microsoft.com/en-us/a0e671fc-76e6-4fb4-b95c-ced4dd2b2017)|Geçerli öğeye başvuru alır.|  
|[-> işleci](http://msdn.microsoft.com/en-us/41fa393d-ae1e-4a38-bb4b-19e8df709ca9)|Geçerli öğe için bir işaretçi alır.|  
  
 [[Üst](#top)]  
  
##  <a name="unordered_map"></a>concurrent_unordered_map sınıfı  
 [HYPERLINK "file:///C:\\\Users\\\thompet\\\AppData\\\Local\\\Temp\\\DxEditor\\\DduePreview\\\Default \\\798d7037-df37-4310-858b-6f590bbf6ebf\\\HTM\\\html\\\a217b4ac-af2b-4d41-94eb-09a75ee28622 "concurrency::concurrent_unordered_map](../../parallel/concrt/reference/concurrent-unordered-map-class.md) sınıfı bir olduğu gibi ilişkilendirilebilir kapsayıcı sınıfı [std::unordered_map](../../standard-library/unordered-map-class.md) sınıfı, öğe türü değişen uzunluk dizisi denetimleri [std::pair\<const anahtar, Ty >](../../standard-library/pair-structure.md). Bir anahtar ve değer çifti eklemek veya bir değeri anahtarının aramak bir sözlük olarak sırasız bir haritasını düşünün. Bu sınıf, birden çok iş parçacığı veya aynı anda paylaşılan bir kapsayıcı erişim, içine eklemek veya güncelleştirmek için olan görevler varsa yararlıdır.  
  
 Aşağıdaki örnek kullanmak için temel yapı gösterir `concurrent_unordered_map`. Bu örnek karakter tuşları ['bir', ' i'] aralığında ekler. İşlem sırası saptanmamış olduğundan her anahtar için son değer de belirlenmemiş. Ancak, paralel olarak eklemeleri gerçekleştirmek güvenli değildir.  
  
 [!code-cpp[concrt-unordered-map-structure#1](../../parallel/concrt/codesnippet/cpp/parallel-containers-and-objects_2.cpp)]  
  
 Kullanan bir örnek `concurrent_unordered_map` bir eşleme gerçekleştirme ve paralel işlem azaltmak için bkz: [nasıl yapılır: eşleme gerçekleştirme ve işlemleri paralel azaltmak](../../parallel/concrt/how-to-perform-map-and-reduce-operations-in-parallel.md).  
  
###  <a name="map-differences"></a>Concurrent_unordered_map arasındaki farklar ve unordered_map  
 `concurrent_unordered_map` Sınıfı çok benzeyen `unordered_map` sınıfı. Aşağıdaki noktaları nerede göstermeye `concurrent_unordered_map` farklıdır `unordered_map`:  
  
-   `erase`, `bucket`, `bucket_count`, Ve `bucket_size` yöntemleri adlı `unsafe_erase`, `unsafe_bucket`, `unsafe_bucket_count`, ve `unsafe_bucket_size`sırasıyla. `unsafe_` Adlandırma kuralını gösterir bu yöntemleri eşzamanlılık güvenli değildir. Eşzamanlılık güvenliği hakkında daha fazla bilgi için bkz: [eşzamanlılık güvenli işlemler](#map-safety).  
  
-   INSERT işlemlerine varolan işaretçileri veya yineleyiciler geçersiz değil veya zaten eşlemesinde mevcut öğelerin sırasını değiştirmez. INSERT ve çapraz geçiş işlemleri aynı anda oluşabilir.  
  
-   `concurrent_unordered_map`destekler yalnızca yineleme iletin.  
  
-   Ekleme geçersiz ya da tarafından döndürülen yineleyiciler güncelleştirme `equal_range`. Ekleme eşit olmayan öğeler aralığın sonuna ekleyebilirsiniz. Begin yineleyici eşit bir öğeye işaret eder.  
  
 Kilitlenme, hiçbir yöntemi önlemeye yardımcı olmak için `concurrent_unordered_map` bellek ayırıcısı, karma işlevler veya başka bir kullanıcı tarafından tanımlanan kod çağırdığında bir kilit tutar. Ayrıca, karma işlevi her zaman aynı değere eşit anahtarları değerlendirir emin olmalısınız. En iyi karma işlevlerini anahtarları hep karma kodu alanında dağıtın.  
  
###  <a name="map-safety"></a>Eşzamanlılık uyumlu işlemler  
 `concurrent_unordered_map` Sınıfı eşzamanlılık güvenli Ekle ve öğesi erişim işlemleri sağlar. Ekleme işlemleri, var olan işaretçileri veya yineleyiciler geçersiz. Yineleyici erişim ve çapraz geçiş işlemlerini de eşzamanlılık güvenlidir. Aşağıdaki tabloda, yaygın olarak kullanılan gösterilmektedir `concurrent_unordered_map` yöntemleri ve eşzamanlılık güvenli işleçler.  
  
|||||  
|-|-|-|-|  
|[konumundaki](reference/concurrent-unordered-map-class.md#at)|`count`|`find`|[key_eq](reference/concurrent-unordered-map-class.md#key_eq)|  
|`begin`|`empty`|`get_allocator`|`max_size`|  
|`cbegin`|`end`|`hash_function`|[operator &#91; &#93;](reference/concurrent-unordered-map-class.md#operator_at)|  
|`cend`|`equal_range`|[Ekle](reference/concurrent-unordered-map-class.md#insert)|`size`|  
  
 Rağmen `count` yöntemi çağrılabilir güvenli iş parçacığı eşzamanlı olarak çalışan, farklı iş parçacıkları, farklı sonuçlar alabilir, yeni değer aynı anda kapsayıcıya eklediyseniz.  
  
 Aşağıdaki tabloda yaygın olarak kullanılan yöntemleri ve eşzamanlılık güvenli olmayan işleçleri gösterir.  
  
||||  
|-|-|-|  
|`clear`|`max_load_factor`|`rehash`|  
|`load_factor`|[işleç =](reference/concurrent-unordered-map-class.md#operator_eq) 


  
 Bu yöntemleri ek olarak, herhangi bir yöntemini başlayan ile `unsafe_` de eşzamanlılık uyumlu değil.  
  
 [[Üst](#top)]  
  
##  <a name="unordered_multimap"></a>concurrent_unordered_multimap sınıfı  
 [Concurrency::concurrent_unordered_multimap](../../parallel/concrt/reference/concurrent-unordered-multimap-class.md) sınıfı çok benzeyen `concurrent_unordered_map` aynı anahtara eşlemek birden çok değeri sağlar ancak bu sınıf. Bu aynı zamanda farklı `concurrent_unordered_map` aşağıdaki yollarla:  
  
-   [Concurrent_unordered_multimap::insert](reference/concurrent-unordered-multimap-class.md#insert) yöntemi döndürür yineleyici yerine `std::pair<iterator, bool>`.  

  
-   `concurrent_unordered_multimap` Sınıfı sağlamaz `operator[]` veya `at` yöntemi.  
  
 Aşağıdaki örnek kullanmak için temel yapı gösterir `concurrent_unordered_multimap`. Bu örnek karakter tuşları ['bir', ' i'] aralığında ekler. `concurrent_unordered_multimap`birden çok değer bir anahtar sağlar.  
  
 [!code-cpp[concrt-unordered-multimap-structure#1](../../parallel/concrt/codesnippet/cpp/parallel-containers-and-objects_3.cpp)]  
  
 [[Üst](#top)]  
  
##  <a name="unordered_set"></a>concurrent_unordered_set sınıfı  
 [Concurrency::concurrent_unordered_set](../../parallel/concrt/reference/concurrent-unordered-set-class.md) sınıfı çok benzeyen `concurrent_unordered_map` anahtar ve değer çiftleri yerine değerlerini yönetir ancak bu sınıf. `concurrent_unordered_set` Sınıfı sağlamaz `operator[]` veya `at` yöntemi.  
  
 Aşağıdaki örnek kullanmak için temel yapı gösterir `concurrent_unordered_set`. Bu örnek karakter değerleri aralığı ['bir', ' i'] ekler. Paralel olarak eklemeleri gerçekleştirmek güvenlidir.  
  
 [!code-cpp[concrt-unordered-set#1](../../parallel/concrt/codesnippet/cpp/parallel-containers-and-objects_4.cpp)]  
  
 [[Üst](#top)]  
  
##  <a name="unordered_multiset"></a>concurrent_unordered_multiset sınıfı  
 [Concurrency::concurrent_unordered_multiset](../../parallel/concrt/reference/concurrent-unordered-multiset-class.md) sınıfı çok benzeyen `concurrent_unordered_set` için yinelenen değerler sağlar ancak bu sınıf. Bu aynı zamanda farklı `concurrent_unordered_set` aşağıdaki yollarla:  
  

-   [Concurrent_unordered_multiset::insert](reference/concurrent-unordered-multiset-class.md#insert) yöntemi döndürür yineleyici yerine `std::pair<iterator, bool>`.  

  
-   `concurrent_unordered_multiset` Sınıfı sağlamaz `operator[]` veya `at` yöntemi.  
  
 Aşağıdaki örnek kullanmak için temel yapı gösterir `concurrent_unordered_multiset`. Bu örnek karakter değerleri aralığı ['bir', ' i'] ekler. `concurrent_unordered_multiset`birden çok kez gerçekleşmesi bir değer sağlar.  
  
 [!code-cpp[concrt-unordered-multiset#1](../../parallel/concrt/codesnippet/cpp/parallel-containers-and-objects_5.cpp)]  
  
 [[Üst](#top)]  
  
##  <a name="combinable"></a>combinable sınıfı  
 [Concurrency::combinable](../../parallel/concrt/reference/combinable-class.md) sınıfı hassas hesaplamalar ve ardından bu hesaplamaların nihai sonucu birleştirme sağlayan yeniden kullanılabilir, iş parçacığı yerel depolama sağlar. Düşünebilirsiniz bir `combinable` nesnesi azaltma değişkeni olarak.  
  
 `combinable` Sınıfı, çeşitli iş parçacığı veya görevler arasında paylaşılan bir kaynak olduğunda yararlıdır. `combinable` Sınıfı, bir kilidi serbest şekilde paylaşılan kaynaklara erişim sağlayarak paylaşılan durum ortadan kaldırmanıza yardımcı olur. Bu nedenle, bu sınıfın birden çok iş parçacığı tarafından paylaşılan verilere erişimi eşitlemek için eşitleme mekanizması, örneğin, bir mutex kullanmaya alternatif sağlar.  
  
###  <a name="combinable-features"></a>Yöntemleri ve özellikleri  
 Aşağıdaki tabloda bazı önemli yöntemlerinden birini gösterilmektedir `combinable` sınıfı. Tüm hakkında daha fazla bilgi için `combinable` sınıfı yöntemlerinin, bkz: [combinable sınıfı](../../parallel/concrt/reference/combinable-class.md).  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[Yerel](reference/combinable-class.md#local)|Geçerli iş parçacığı içerikle ilişkili yerel değişken için bir başvuru alır.|  
|[Temizle](reference/combinable-class.md#clear)|Tüm iş parçacığı yerel değişkenler arasından kaldırır `combinable` nesnesi.|  
|[Birleştirme](reference/combinable-class.md#combine)<br /><br /> [combine_each](reference/combinable-class.md#combine_each)|Tüm iş parçacığı yerel hesaplamalar kümesinden son bir değer üretmek için sağlanan birleştirme işlevi kullanır.|  
  
 `combinable` Son birleştirilen sonucuna parametreli bir şablon sınıfı bir sınıftır. Varsayılan Oluşturucu çağırırsanız `T` varsayılan bir oluşturucu ve kopya Oluşturucu şablon parametresi türü olması gerekir. Varsa `T` şablon parametresi türü varsayılan bir oluşturucu yok, bir başlatma işlevi, parametre olarak alan oluşturucu aşırı yüklü sürümünü arayın.  
  
 Ek veri deposundaki bir `combinable` , çağrısından sonra nesne [birleştirmek](reference/combinable-class.md#combine) veya [combine_each](reference/combinable-class.md#combine_each) yöntemleri. Ayrıca, çağırabilirsiniz `combine` ve `combine_each` yöntemleri birden çok kez. Yerel hiçbir değer varsa bir `combinable` nesnesi değişiklikleri `combine` ve `combine_each` yöntemleri adı verilir her zaman aynı sonucu üretir.  
  
###  <a name="combinable-examples"></a>Örnekler  
 Kullanımıyla ilgili örnekler için `combinable` sınıfında, aşağıdaki konulara bakın:  
  
-   [Nasıl yapılır: Performansı arttırmak için combinable Kullanma](../../parallel/concrt/how-to-use-combinable-to-improve-performance.md)  
  
-   [Nasıl yapılır: Kümeleri Birleştirmek için combinable Kullanma](../../parallel/concrt/how-to-use-combinable-to-combine-sets.md)  
  
 [[Üst](#top)]  
  
## <a name="related-topics"></a>İlgili Konular  
 [Nasıl yapılır: Etkinliği Arttırmak için Paralel Kapsayıcılar Kullanma](../../parallel/concrt/how-to-use-parallel-containers-to-increase-efficiency.md)  
 Paralel kapsayıcılar verimli bir şekilde depolamak ve paralel verilere erişmek için nasıl kullanılacağını gösterir.  
  
 [Nasıl yapılır: Performansı arttırmak için combinable Kullanma](../../parallel/concrt/how-to-use-combinable-to-improve-performance.md)  
 Nasıl kullanılacağını gösterir `combinable` paylaşılan durum ortadan kaldırmak için sınıf ve böylece performansı.  
  
 [Nasıl yapılır: Kümeleri Birleştirmek için combinable Kullanma](../../parallel/concrt/how-to-use-combinable-to-combine-sets.md)  
 Nasıl kullanılacağını gösteren bir `combine` iş parçacığı yerel veri kümelerinin birleştirmek için işlevi.  
  
 [Paralel Desen Kitaplığı (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md)  
 Ölçeklenebilirlik ve kolaylığı eşzamanlı uygulamaları geliştirmek için kullanım yükseltir kesinlik temelli bir programlama modelidir PPL açıklar.  
  
## <a name="reference"></a>Başvuru  
 [concurrent_vector Sınıfı](../../parallel/concrt/reference/concurrent-vector-class.md)  
  
 [concurrent_queue Sınıfı](../../parallel/concrt/reference/concurrent-queue-class.md)  
  
 [concurrent_unordered_map Sınıfı](../../parallel/concrt/reference/concurrent-unordered-map-class.md)  
  
 [concurrent_unordered_multimap Sınıfı](../../parallel/concrt/reference/concurrent-unordered-multimap-class.md)  
  
 [concurrent_unordered_set Sınıfı](../../parallel/concrt/reference/concurrent-unordered-set-class.md)  
  
 [concurrent_unordered_multiset Sınıfı](../../parallel/concrt/reference/concurrent-unordered-multiset-class.md)  
  
 [combinable Sınıfı](../../parallel/concrt/reference/combinable-class.md)
