---
title: '&lt;Ayırıcılar&gt;'
ms.date: 11/04/2016
f1_keywords:
- <allocators>
helpviewer_keywords:
- allocators header
ms.assetid: 4393a607-4df8-4278-bbb2-c8ec52e60b83
ms.openlocfilehash: 064afd4467a2aedebe3a9892fc80b14597c8552f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62375411"
---
# <a name="ltallocatorsgt"></a>&lt;Ayırıcılar&gt;

Düğüm tabanlı kapsayıcılar için bellek bloğu ayırıp yardımcı çeşitli şablonları tanımlar.

## <a name="syntax"></a>Sözdizimi

```cpp
#include <allocators>
```

## <a name="remarks"></a>Açıklamalar

\<Ayırıcılar > Üstbilgi düğüm tabanlı kapsayıcılar için bellek yönetimi stratejileri seçmek için kullanılan altı ayırıcı şablonları sağlar. Bu şablonlar ile kullanım için bellek yönetimi stratejisi (hiçbiri dahil) farklı bir çoklu iş parçacığı kullanımı düzenlerini çeşitli uyarlamak için birkaç farklı eşitleme filtreleri de sağlar. Bellek yönetimi stratejisi bilinen bellek kullanım desenleri ve eşitleme gereksinimlerini, belirli bir uygulama için eşleşen genellikle hızını artırmak veya bir uygulamanın genel bellek gereksinimlerini azaltın.

Allocator şablonlar, özelleştirilmiş veya ek bellek yönetimi stratejileri sağlamak yerine yeniden kullanılabilir bileşenleri ile uygulanır.

C++ Standart Kitaplığı (std::list, std::set, std::multiset, std::map ve std::multimap) düğüm tabanlı kapsayıcılarda öğeleri tek tek düğümler depolayın. Belirli bir kapsayıcı türü için tüm düğümlerin aynı boyutta olduğundan, genel amaçlı bellek yöneticisi esnekliğini gerekli değildir. Her bellek bloğu boyutu, derleme zamanında bilinen çünkü çok daha kolay ve hızlı bellek yöneticisi olabilir.

Düğüm tabanlı olmayan kapsayıcılar ile kullanıldığında (gibi C++ standart kitaplığı kapsayıcıları std::vector std::deque ve std::basic_string), alllocator şablonları düzgün çalışır, ancak üzerinden herhangi bir performans geliştirmesi sağlayın olasılığı değildir Varsayılan ayırıcı.

Bir ayırıcıyı depolama ayırmayı ve nesneleri ve belirlenen türünde nesne dizileri için boşaltmayı yöneten bir nesneyi tanımlayan bir şablon sınıfıdır. Ayırıcı nesneleri, C++ Standart Kitaplığı'nda birkaç kapsayıcı Şablon sınıfı tarafından kullanılır.

Bu türün tüm şablonları ayırıcılar şunlardır:

```cpp
template<class Type>
class allocator;
```

Burada şablon bağımsız değişkeni `Type` ayırıcı örneği tarafından yönetilen bir tür. C++ Standart Kitaplığı sağlayan Şablon sınıfı, bir varsayılan ayırıcı [ayırıcı](../standard-library/allocator-class.md), tanımlanan [ \<bellek >](../standard-library/memory.md). \<Ayırıcılar > üst bilgi aşağıdaki ayırıcılar sağlar:

- [allocator_newdel](../standard-library/allocator-newdel-class.md)

- [allocator_unbounded](../standard-library/allocator-unbounded-class.md)

- [allocator_fixed_size](../standard-library/allocator-fixed-size-class.md)

- [allocator_variable_size](../standard-library/allocator-variable-size-class.md)

- [allocator_suballoc](../standard-library/allocator-suballoc-class.md)

- [allocator_chunklist](../standard-library/allocator-chunklist-class.md)

Aşağıdaki kod örneği gibi bir kapsayıcı oluştururken, uygun bir ayırıcı örneklemesi ikinci tür bağımsız değişkeni kullanın.

```cpp
#include <list>
#include <allocators>
std::list<int, stdext::allocators::allocator_chunklist<int> > _List0;
```

_List0 ayırır düğümleri `allocator_chunklist` ve varsayılan eşitleme filtresi.

Makroyu kullanın [ALLOCATOR_DECL](../standard-library/allocators-functions.md#allocator_decl) eşitleme filtreleri varsayılan dışındaki ayırıcı şablonları oluşturmak için:

```cpp
#include <list>
#include <allocators>
ALLOCATOR_DECL(CACHE_CHUNKLIST, stdext::allocators::sync_per_thread, Alloc);
std::list<int, alloc<int> > _List1;
```

_Lst1 ayırır düğümleri `allocator_chunklist` ve [sync_per_thread](../standard-library/sync-per-thread-class.md) eşitleme filtresi.

Bir blok ayırıcı bir önbellek ya da bir filtre ' dir. Bir önbellek türü std::size_t bir bağımsız değişken alan bir şablon sınıfıdır. Ayırır ve bellek blokları tek bir boyutta ayırmayı iptal eder bloğu ayırıcısı tanımlar. İşlecini kullanarak bellek almalısınız **yeni**, ancak işleci ayrı çağrı yapmak olmayan **yeni** her blok için. Daha büyük bir blok veya sonraki yeniden ayırma için blokları serbest önbellek gibi suballocate olabilir.

Şablon oluşturulduğunda kullanılan std::size_t bağımsız değişkenin değeri olmak zorunda değildir yeniden bağlamasını derlenemez bir derleyici ile bir önbelleğin üye işleve geçirilen bağımsız değişken _Sz değerini ayırma ve serbest bırakın.

\<Ayırıcılar > aşağıdaki önbellek şablonlarını sunar:

- [cache_freelist](../standard-library/cache-freelist-class.md)

- [cache_suballoc](../standard-library/cache-suballoc-class.md)

- [cache_chunklist](../standard-library/cache-chunklist-class.md)

Üye işlevleri bir şablon bağımsız değişken olarak geçirilen başka bir blok ayırıcı kullanılarak uygulayan bir blok ayırıcı bir filtredir. En yaygın filtresi geçerli bir eşitleme ilkesi, başka bir blok ayırıcı örneği üye işlevleri erişimi denetlemek için bir eşitleme filtre biçimidir. \<Ayırıcılar > aşağıdaki eşitleme filtreleri sağlar:

- [sync_none](../standard-library/sync-none-class.md)

- [sync_per_container](../standard-library/sync-per-container-class.md)

- [sync_per_thread](../standard-library/sync-per-thread-class.md)

- [sync_shared](../standard-library/sync-shared-class.md)

\<Ayırıcılar > de filtre sağlar [rts_alloc](../standard-library/rts-alloc-class.md), birden fazla blok ayırıcı tutan, örnekler ve ayırma ya da ayırmayı kaldırma yerine çalışma zamanında derleme zamanında kullanılmak üzere hangi örneğinin belirler. Yeniden bağlamasını derlenemez derleyicilerle birlikte kullanılır.

Eşitleme ilkesi, bir ayırıcı örneği birden çok iş parçacığından eşzamanlı ayırmayı ve ayırmayı kaldırma isteklerini nasıl işleyeceğini belirler. Basit ilke üzerinden tüm istekleri doğrudan kullanıcıya eşitleme yönetim bırakarak temel alınan önbellek nesnesini geçirmektir. Daha karmaşık bir ilke bir mutex önbellek nesnesini erişimi serileştirmek için kullanılacak olabilir.

Derleyici, hem tek iş parçacıklı ve çok iş parçacıklı uygulamalar derleme destekliyorsa, tek iş parçacıklı uygulamalar için varsayılan eşitleme filtresi olduğundan `sync_none`; bu diğer tüm durumlarda `sync_shared`.

Önbellek şablonu `cache_freelist` en fazla boş listeden depolanacak öğe sayısını belirleyen bir max sınıfı bağımsız değişken alır.

\<Ayırıcılar > aşağıdaki max sınıfları sağlar:

- [max_none](../standard-library/max-none-class.md)

- [max_unbounded](../standard-library/max-unbounded-class.md)

- [max_fixed_size](../standard-library/max-fixed-size-class.md)

- [max_variable_size](../standard-library/max-variable-size-class.md)

### <a name="macros"></a>Makrolar

|Makrosu|Açıklama|
|-|-|
|[ALLOCATOR_DECL](../standard-library/allocators-functions.md#allocator_decl)|Şablon sınıfı bir ayırıcı verir.|
|[CACHE_CHUNKLIST](../standard-library/allocators-functions.md#cache_chunklist)|Verir `stdext::allocators::cache_chunklist<sizeof(Type)>`.|
|[CACHE_FREELIST](../standard-library/allocators-functions.md#cache_freelist)|Verir `stdext::allocators::cache_freelist<sizeof(Type), max>`.|
|[CACHE_SUBALLOC](../standard-library/allocators-functions.md#cache_suballoc)|Verir `stdext::allocators::cache_suballoc<sizeof(Type)>`.|
|[SYNC_DEFAULT](../standard-library/allocators-functions.md#sync_default)|Eşitleme filtresi verir.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[işleç! = (\<ayırıcılar >)](../standard-library/allocators-operators.md#op_neq)|Belirtilen sınıfın ayırıcı nesneleri arasındaki eşitsizliği sınar.|
|[işleç == (\<ayırıcılar >)](../standard-library/allocators-operators.md#op_eq_eq)|Belirtilen sınıfın ayırıcı nesneleri arasındaki eşitliği sınar.|

### <a name="classes"></a>Sınıflar

|örneği|Açıklama|
|-|-|
|[allocator_base](../standard-library/allocator-base-class.md)|Eşitleme filtresi kullanıcı tarafından tanımlanan bir ayırıcı oluşturmak için gereken genel işlevler ve temel sınıf tanımlar.|
|[allocator_chunklist](../standard-library/allocator-chunklist-class.md)|Depolama ayırmayı ve boşaltmayı kullanarak bir önbellek türü nesneler için yöneten bir nesneyi tanımlayan [cache_chunklist](../standard-library/cache-chunklist-class.md).|
|[allocator_fixed_size](../standard-library/allocator-fixed-size-class.md)|Depolama ayırmayı ve boşaltmayı türü nesneler için yöneten bir nesneyi tanımlayan `Type` kullanarak bir önbellek türü [cache_freelist](../standard-library/cache-freelist-class.md) tarafından yönetilen bir uzunlukta [max_fixed_size](../standard-library/max-fixed-size-class.md).|
|[allocator_newdel](../standard-library/allocator-newdel-class.md)|Kullanan bir ayırıcı uygulayan **delete işleci** ayırması bir bellek bloğu ve **new işleci** bir bellek bloğu ayrılamadı.|
|[allocator_suballoc](../standard-library/allocator-suballoc-class.md)|Depolama ayırmayı ve boşaltmayı türü nesneler için yöneten bir nesneyi tanımlayan `Type` kullanarak bir önbellek türü [cache_suballoc](../standard-library/cache-suballoc-class.md).|
|[allocator_unbounded](../standard-library/allocator-unbounded-class.md)|Depolama ayırmayı ve boşaltmayı türü nesneler için yöneten bir nesneyi tanımlayan `Type` kullanarak bir önbellek türü [cache_freelist](../standard-library/cache-freelist-class.md) tarafından yönetilen bir uzunlukta [max_unbounded](../standard-library/max-unbounded-class.md).|
|[allocator_variable_size](../standard-library/allocator-variable-size-class.md)|Depolama ayırmayı ve boşaltmayı türü nesneler için yöneten bir nesneyi tanımlayan `Type` kullanarak bir önbellek türü [cache_freelist](../standard-library/cache-freelist-class.md) tarafından yönetilen bir uzunlukta [max_variable_size](../standard-library/max-variable-size-class.md).|
|[cache_chunklist](../standard-library/cache-chunklist-class.md)|Ayırır ve bellek blokları tek bir boyutta ayırmayı iptal eder bloğu ayırıcısı tanımlar.|
|[cache_freelist](../standard-library/cache-freelist-class.md)|Ayırır ve bellek blokları tek bir boyutta ayırmayı iptal eder bloğu ayırıcısı tanımlar.|
|[cache_suballoc](../standard-library/cache-suballoc-class.md)|Ayırır ve bellek blokları tek bir boyutta ayırmayı iptal eder bloğu ayırıcısı tanımlar.|
|[FreeList](../standard-library/freelist-class.md)|Bellek bloklarını listesini yönetir.|
|[max_fixed_size](../standard-library/max-fixed-size-class.md)|Sınırlayan max sınıfı bir nesneyi tanımlayan bir [freelist](../standard-library/freelist-class.md) nesne sabit en büyük uzunluğu.|
|[max_none](../standard-library/max-none-class.md)|Sınırlayan max sınıfı bir nesneyi tanımlayan bir [freelist](../standard-library/freelist-class.md) nesne en fazla uzunluğu sıfır.|
|[max_unbounded](../standard-library/max-unbounded-class.md)|En büyük uzunluğunu sınırlamaz bir max sınıfı nesneyi tanımlayan bir [freelist](../standard-library/freelist-class.md) nesne.|
|[max_variable_size](../standard-library/max-variable-size-class.md)|Sınırlayan max sınıfı bir nesneyi tanımlayan bir [freelist](../standard-library/freelist-class.md) ayrılan bellek blokları nesne sayısı için kabaca orantılı en büyük uzunluğu.|
|[rts_alloc](../standard-library/rts-alloc-class.md)|Rts_alloc Şablon sınıfı tanımlar bir [filtre](../standard-library/allocators-header.md) tutan bir dizi önbellek örnekleri ve ayırmayı ve ayırmayı kaldırma yerine çalışma zamanında derleme zamanında kullanılmak üzere hangi örneğinin belirler.|
|[sync_none](../standard-library/sync-none-class.md)|Eşitleme sağlayan eşitleme filtresi açıklar.|
|[sync_per_container](../standard-library/sync-per-container-class.md)|Her bir ayırıcı nesne için ayrı önbellek nesnesi sağlayan bir eşitleme filtresi açıklar.|
|[sync_per_thread](../standard-library/sync-per-thread-class.md)|Her iş parçacığı için ayrı önbellek nesnesi sağlayan bir eşitleme filtresi açıklar.|
|[sync_shared](../standard-library/sync-shared-class.md)|Tüm ayırıcılar tarafından paylaşılan bir önbellek nesnesi erişimi bir mutex kullanan eşitleme filtresi açıklar.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<ayırıcılar >

**Namespace:** stdext

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)<br/>
