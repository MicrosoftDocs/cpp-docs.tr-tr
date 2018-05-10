---
title: '&lt;allocators&gt; | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- <allocators>
dev_langs:
- C++
helpviewer_keywords:
- allocators header
ms.assetid: 4393a607-4df8-4278-bbb2-c8ec52e60b83
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f578ab4ea06db68b23a03374bcd787dc03715ab5
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
---
# <a name="ltallocatorsgt"></a>&lt;allocators&gt;

Ayırın ve bellek blokları düğümünü tabanlı kapsayıcıları için boş Yardım çeşitli şablonlar tanımlar.

## <a name="syntax"></a>Sözdizimi

```cpp
#include <allocators>
```

## <a name="remarks"></a>Açıklamalar

\<Allocators > Üstbilgi düğümü tabanlı kapsayıcıları için bellek yönetimi stratejilerini seçmek için kullanılan altı ayırıcısı şablonları sağlar. Bu şablonlar ile kullanım için farklı çoklu iş parçacığı kullanımı düzenleri (hiçbiri dahil) çeşitli bellek yönetimi stratejisi uyarlamak için birkaç farklı eşitleme filtreleri de sağlar. Bellek yönetimi stratejisi bilinen bellek kullanım desenlerini ve eşitleme gereksinimleri, belirli bir uygulamanın eşleşen genellikle hızını artırmak veya bir uygulamanın genel bellek gereksinimlerini azaltın.

Ayırıcı şablonları özelleştirilmiş veya ek bellek yönetimi stratejilerini sağlamak için yerini yeniden kullanılabilir bileşenler ile uygulanır.

C++ Standart Kitaplığı (std::list, std::set, std::multiset, std::map ve std::multimap) düğüm tabanlı kapsayıcılarında öğeleri tek tek düğümler depolar. Belirli kapsayıcı türü için tüm düğümlerin aynı boyutta olduğundan, genel amaçlı bellek yöneticisi esnekliğini gerekli değildir. Her bellek bloğu boyutu derleme zamanında bilindiğinden bellek yöneticisi çok daha basit ve daha hızlı olabilir.

Düğüm tabanlı (C++ Standart Kitaplığı kapsayıcıları std::vector std::deque ve std::basic_string gibi) olmayan kapsayıcıları ile kullanıldığında, alllocator şablonları düzgün çalışmaz, ancak tüm performans geliştirmesi üzerinden sağlamak büyük olasılıkla değildir Varsayılan ayırıcısı.

Bir ayırıcı depolama ayırma ve nesneleri ve belirtilen türdeki nesneleri dizileri için boşaltma yöneten bir nesneyi tanımlayan bir şablon sınıftır. Ayırıcı nesneleri C++ Standart Kitaplığı'nda birkaç kapsayıcı şablon sınıfları tarafından kullanılır.

Allocators bu türdeki tüm şablonları şunlardır:

`template<class` `Type` `>`

`class allocator;`

Burada şablon bağımsız değişken `Type` ayırıcısı örneği tarafından yönetilen türü. C++ Standart Kitaplığı, varsayılan ayırıcısı, Şablon sınıfı sağlar [ayırıcısı](../standard-library/allocator-class.md), içinde tanımlanan [ \<bellek >](../standard-library/memory.md). \<Allocators > aşağıdaki allocators üstbilgisi sağlar:

- [allocator_newdel](../standard-library/allocator-newdel-class.md)

- [allocator_unbounded](../standard-library/allocator-unbounded-class.md)

- [allocator_fixed_size](../standard-library/allocator-fixed-size-class.md)

- [allocator_variable_size](../standard-library/allocator-variable-size-class.md)

- [allocator_suballoc](../standard-library/allocator-suballoc-class.md)

- [allocator_chunklist](../standard-library/allocator-chunklist-class.md)

Bir ayırıcı, uygun bir örnek oluşturma, aşağıdaki kod örneğinde gibi bir kapsayıcı oluştururken ikinci tür bağımsız değişkeni olarak kullanın.

`#include <list>`

`#include <allocators>`

`std::list<int, stdext::allocators::allocator_chunklist<int> > _List0;`

_List0 ayırır düğümleriyle `allocator_chunklist` ve varsayılan eşitleme filtresi.

Makro kullanmak [ALLOCATOR_DECL](../standard-library/allocators-functions.md#allocator_decl) varsayılan dışındaki eşitleme filtrelerle ayırıcısı şablonları oluşturmak için:

`#include <list>`

`#include <allocators>`

`ALLOCATOR_DECL(CACHE_CHUNKLIST, stdext::allocators::sync_per_thread, Alloc);`

`std::list<int, alloc<int> > _List1;`

_Lst1 ayırır düğümleriyle `allocator_chunklist` ve [sync_per_thread](../standard-library/sync-per-thread-class.md) eşitleme filtresi.

Bir blok ayırıcısı bir önbellek veya bir filtre değil. Bir bağımsız değişken türü std::size_t, bir şablon sınıfı önbelleğidir. Ayırır ve bellek blokları tek bir boyutta kaldırır bloğu ayırıcısı tanımlar. İşlecini kullanarak bellek edinmelidir `new`, ancak işleci için ayrı bir çağrısı koymasına gerek yoktur `new` her bloğu. Daha büyük bir blok veya sonraki yeniden ayırma blokları serbest önbellek Örneğin, suballocate olabilir.

Şablon örneği çağrılırken std::size_t bağımsız değişkeninin değeri olmak zorunda değildir yeniden bağlamasını derlenemiyor derleyici önbelleği'nin üye işlevleri için geçirilen bağımsız değişken _Sz değerini ayırma ve serbest bırakma.

\<allocators > aşağıdaki önbellek şablonlar sağlar:

- [cache_freelist](../standard-library/cache-freelist-class.md)

- [cache_suballoc](../standard-library/cache-suballoc-class.md)

- [cache_chunklist](../standard-library/cache-chunklist-class.md)

Şablon bağımsız değişken geçirilen başka bir blok ayırıcıyı kullanarak kendi üye işlevleri uygulayan bir bloğu ayırıcısı filtredir. En yaygın filtre üye işlevleri başka bir bloğu ayırıcısı örneği erişimi denetlemek için bir eşitleme ilkesi uygulanır eşitleme filtresi biçimidir. \<allocators > aşağıdaki eşitleme filtreleri sağlar:

- [sync_none](../standard-library/sync-none-class.md)

- [sync_per_kapsayıcı](../standard-library/sync-per-container-class.md)

- [sync_per_thread](../standard-library/sync-per-thread-class.md)

- [sync_shared](../standard-library/sync-shared-class.md)

\<allocators > Ayrıca filtre sağlar [rts_alloc](../standard-library/rts-alloc-class.md), birden çok bloğu ayırıcısı tutan örnekleri ve ayırma veya derleme zamanında ayırmayı kaldırma yerine çalışma zamanında kullanılacak hangi örneği belirler. Yeniden bağlamasını derlenemiyor derleyicileri ile kullanılır.

Eşitleme ilkesi ayırıcısı örneği birden çok iş parçacığından eşzamanlı ayırma ve ayırmayı kaldırma isteklerini nasıl işleyeceğini belirler. En basit ilke aracılığıyla tüm istekleri doğrudan kullanıcıya eşitleme yönetim bırakarak önbellek nesnesini, geçirmektir. Daha karmaşık bir ilke bir mutex önbellek nesnesini erişimi serileştirmek için kullanılacak olabilir.

Derleyici tek iş parçacıklı hem çok iş parçacıklı uygulamalar derleme destekliyorsa, varsayılan eşitleme tek iş parçacıklı uygulamalar için filtredir `sync_none`; olduğu tüm diğer durumlarda `sync_shared`.

Önbellek şablonu `cache_freelist` boş listeden depolanması öğelerinin üst limiti belirleyen bir max sınıfı bağımsız değişkeni alır.

\<allocators > aşağıdaki max sınıflar sağlar:

- [max_none](../standard-library/max-none-class.md)

- [max_unbounded](../standard-library/max-unbounded-class.md)

- [max_fixed_size](../standard-library/max-fixed-size-class.md)

- [max_variable_size](../standard-library/max-variable-size-class.md)

### <a name="macros"></a>Makrolar

|Makrosu|Açıklama|
|-|-|
|[ALLOCATOR_DECL](../standard-library/allocators-functions.md#allocator_decl)|Bir ayırıcı Şablon sınıfı verir.|
|[CACHE_CHUNKLIST](../standard-library/allocators-functions.md#cache_chunklist)|Verir `stdext::allocators::cache_chunklist<sizeof(Type)>`.|
|[CACHE_FREELIST](../standard-library/allocators-functions.md#cache_freelist)|Verir `stdext::allocators::cache_freelist<sizeof(Type), max>`.|
|[CACHE_SUBALLOC](../standard-library/allocators-functions.md#cache_suballoc)|Verir `stdext::allocators::cache_suballoc<sizeof(Type)>`.|
|[SYNC_DEFAULT](../standard-library/allocators-functions.md#sync_default)|Eşitleme filtresi verir.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[operator! = (\<allocators >)](../standard-library/allocators-operators.md#op_neq)|Belirtilen sınıfın ayırıcı nesneleri arasındaki eşitsizliği sınar.|
|[operator == (\<allocators >)](../standard-library/allocators-operators.md#op_eq_eq)|Belirtilen sınıfın ayırıcı nesneleri arasındaki eşitliği sınar.|

### <a name="classes"></a>Sınıflar

|örneği|Açıklama|
|-|-|
|[allocator_base](../standard-library/allocator-base-class.md)|Kullanıcı tanımlı bir ayırıcı eşitleme filtresi oluşturmak için gereken genel işlevler ve temel sınıf tanımlar.|
|[allocator_chunklist](../standard-library/allocator-chunklist-class.md)|Depolama ayırma ve için bir önbellek türü kullanarak nesneleri serbest bırakma yöneten bir nesneyi tanımlayan [cache_chunklist](../standard-library/cache-chunklist-class.md).|
|[allocator_fixed_size](../standard-library/allocator-fixed-size-class.md)|Depolama ayırma ve serbest bırakma türündeki nesneler için yöneten bir nesneyi tanımlayan `Type` bir önbellek türü kullanarak [cache_freelist](../standard-library/cache-freelist-class.md) tarafından yönetilen bir uzunluğa sahip [max_fixed_size](../standard-library/max-fixed-size-class.md).|
|[allocator_newdel](../standard-library/allocator-newdel-class.md)|Kullanan bir ayırıcı uygulayan `operator delete` bellek ayırması için blok ve `operator new` bir bellek bloğu ayrılamadı.|
|[allocator_suballoc](../standard-library/allocator-suballoc-class.md)|Depolama ayırma ve serbest bırakma türündeki nesneler için yöneten bir nesneyi tanımlayan `Type` bir önbellek türü kullanarak [cache_suballoc](../standard-library/cache-suballoc-class.md).|
|[allocator_unbounded](../standard-library/allocator-unbounded-class.md)|Depolama ayırma ve serbest bırakma türündeki nesneler için yöneten bir nesneyi tanımlayan `Type` bir önbellek türü kullanarak [cache_freelist](../standard-library/cache-freelist-class.md) tarafından yönetilen bir uzunluğa sahip [max_unbounded](../standard-library/max-unbounded-class.md).|
|[allocator_variable_size](../standard-library/allocator-variable-size-class.md)|Depolama ayırma ve serbest bırakma türündeki nesneler için yöneten bir nesneyi tanımlayan `Type` bir önbellek türü kullanarak [cache_freelist](../standard-library/cache-freelist-class.md) tarafından yönetilen bir uzunluğa sahip [max_variable_size](../standard-library/max-variable-size-class.md).|
|[cache_chunklist](../standard-library/cache-chunklist-class.md)|Ayırır ve bellek blokları tek bir boyutta kaldırır bloğu ayırıcısı tanımlar.|
|[cache_freelist](../standard-library/cache-freelist-class.md)|Ayırır ve bellek blokları tek bir boyutta kaldırır bloğu ayırıcısı tanımlar.|
|[cache_suballoc](../standard-library/cache-suballoc-class.md)|Ayırır ve bellek blokları tek bir boyutta kaldırır bloğu ayırıcısı tanımlar.|
|[FreeList](../standard-library/freelist-class.md)|Bellek blokları bir listesini yönetir.|
|[max_fixed_size](../standard-library/max-fixed-size-class.md)|Sınırlar max sınıfı nesneyi tanımlayan bir [freelist](../standard-library/freelist-class.md) sabit uzunluk nesnesine.|
|[max_none](../standard-library/max-none-class.md)|Sınırlar max sınıfı nesneyi tanımlayan bir [freelist](../standard-library/freelist-class.md) sıfır en fazla nesne.|
|[max_unbounded](../standard-library/max-unbounded-class.md)|En büyük uzunluğu sınırlamaz max sınıfı nesneyi tanımlayan bir [freelist](../standard-library/freelist-class.md) nesnesi.|
|[max_variable_size](../standard-library/max-variable-size-class.md)|Sınırlar max sınıfı nesneyi tanımlayan bir [freelist](../standard-library/freelist-class.md) nesne sayısı için kabaca orantılıdır bir maksimum uzunluğu için ayrılan bellek blokları.|
|[rts_alloc](../standard-library/rts-alloc-class.md)|Rts_alloc Şablon sınıfı açıklayan bir [filtre](../standard-library/allocators-header.md) tutan bir dizi önbelleği örnekleri ve ayırma ve ayırmayı kaldırma yerine çalışma zamanında derleme zamanında kullanmak için hangi örneğinin belirler.|
|[sync_none](../standard-library/sync-none-class.md)|Hiçbir eşitleme sağlayan eşitleme filtresi açıklar.|
|[sync_per_kapsayıcı](../standard-library/sync-per-container-class.md)|Her bir ayırıcı nesne için ayrı önbellek nesnesini sağlayan eşitleme filtresi açıklar.|
|[sync_per_thread](../standard-library/sync-per-thread-class.md)|Her iş parçacığı için ayrı önbellek nesnesini sağlayan eşitleme filtresi açıklar.|
|[sync_shared](../standard-library/sync-shared-class.md)|Tüm allocators tarafından paylaşılan bir önbellek nesnesi erişimi denetlemek için bir mutex kullanan bir eşitleme filtresi açıklar.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<allocators >

**Namespace:** stdext

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)<br/>
