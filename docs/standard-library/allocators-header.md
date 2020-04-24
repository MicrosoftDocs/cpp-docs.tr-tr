---
title: '&lt;Allocators&gt;'
ms.date: 11/04/2016
f1_keywords:
- <allocators>
helpviewer_keywords:
- allocators header
ms.assetid: 4393a607-4df8-4278-bbb2-c8ec52e60b83
ms.openlocfilehash: f6be154be68cd5e43fd6f934d88c04fb25be9dc5
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754448"
---
# <a name="ltallocatorsgt"></a>&lt;Allocators&gt;

Düğüm tabanlı kapsayıcılar için ayırmaya ve boşbellek blokları ayırmaya yardımcı olan birkaç şablon tanımlar.

## <a name="syntax"></a>Sözdizimi

```cpp
#include <allocators>
```

> [!NOTE]
> \<>, Visual Studio 2019 sürüm 16.3 ile başlayan amortismana hazırdır.

## <a name="remarks"></a>Açıklamalar

Üstbilgi \<> ayırıcılar, düğüm tabanlı kapsayıcılar için bellek yönetimi stratejilerini seçmek için kullanılabilecek altı ayırıcı şablonsağlar. Bu şablonlarla kullanım için, bellek yönetimi stratejisini çeşitli çok iş parçacığı düzenlerine (hiçbiri dahil) uyarlamak için birkaç farklı eşitleme filtresi de sağlar. Bir bellek yönetim stratejisini bellek kullanım kalıpları ve eşitleme gereksinimleriyle eşleştirerek uygulamanızı hızlandırabilir veya bellek gereksinimlerini azaltabilirsiniz.

Ayırıcı şablonlar, ek bellek yönetimi stratejileri sağlamak için özelleştirilebilen veya değiştirilebilen yeniden kullanılabilir bileşenlerle uygulanır.

C++ Standart Kitaplığı'ndaki düğüm tabanlı kapsayıcılar (std::list, std::set, std::multiset, std::map ve std::multimap) öğelerini tek tek düğümlerde saklar. Belirli bir kapsayıcı türü için tüm düğümler aynı boyuttadır, bu nedenle genel amaçlı bellek yöneticisinin esnekliğine gerek yoktur. Her bellek bloğunun boyutu derleme zamanında bilindiğinden, bellek yöneticisi çok daha basit ve daha hızlı olabilir.

Düğüm tabanlı olmayan kapsayıcılarla kullanıldığında (C++ Standart Kitaplık kapsayıcıları std::vektör std::deque ve std::basic_string gibi), ayırıcı şablonlar doğru çalışır, ancak varsayılan ayırıcı üzerinde herhangi bir performans geliştirmesi sağlama olasılığı düşüktür.

Ayırıcı, depolama ayırmayı yöneten ve belirli bir türdeki nesneler ve nesneler dizileri için serbest olan bir nesneyi açıklayan bir sınıf şablonudur. Allocator nesneleri, C++ Standart Kitaplığı'ndaki birkaç kapsayıcı sınıfı şablonu tarafından kullanılır.

Ayırıcılar bu türdeki tüm şablonlardır:

```cpp
template<class Type>
class allocator;
```

şablon bağımsız `Type` değişkeninin ayırıcı örnek tarafından yönetilen tür olduğu yer. C++ Standart Kitaplığı, [ \<bellek>](../standard-library/memory.md)tanımlanan varsayılan bir ayırıcı, sınıf [şablonu ayırıcısı](../standard-library/allocator-class.md)sağlar. Tahsisörler \<> üstbilgi aşağıdaki ayırıcıları sağlar:

- [allocator_newdel](../standard-library/allocator-newdel-class.md)

- [allocator_unbounded](../standard-library/allocator-unbounded-class.md)

- [allocator_fixed_size](../standard-library/allocator-fixed-size-class.md)

- [allocator_variable_size](../standard-library/allocator-variable-size-class.md)

- [allocator_suballoc](../standard-library/allocator-suballoc-class.md)

- [allocator_chunklist](../standard-library/allocator-chunklist-class.md)

Aşağıdaki kod örneği gibi bir kapsayıcı oluştururken ikinci tür bağımsız değişkenolarak bir ayırıcının uygun bir anlık oluşturmasını kullanın.

```cpp
#include <list>
#include <allocators>
std::list<int, stdext::allocators::allocator_chunklist<int> > _List0;
```

_List0 ile düğümleri `allocator_chunklist` ve varsayılan eşitleme filtresi ayırır.

Varsayılan değer dışında eşitleme filtreleriyle ayırıcı şablonlar oluşturmak için makro [ALLOCATOR_DECL](../standard-library/allocators-functions.md#allocator_decl) kullanın:

```cpp
#include <list>
#include <allocators>
ALLOCATOR_DECL(CACHE_CHUNKLIST, stdext::allocators::sync_per_thread, Alloc);
std::list<int, alloc<int> > _List1;
```

_Lst1 ve `allocator_chunklist` [sync_per_thread](../standard-library/sync-per-thread-class.md) eşitleme filtresi ile düğümleri ayırır.

Blok ayırıcı, önbellek veya filtredir. Önbellek, std türünden bir bağımsız değişken alan bir sınıf şablonudur::size_t. Tek bir boyuttaki bellek bloklarını ayıran ve ayıran bir blok ayırıcı tanımlar. Bu işleç **yeni**kullanarak bellek elde etmek gerekir, ancak her blok için **yeni** operatör için ayrı bir arama yapmak gerekmez. Örneğin, daha büyük bir bloktan veya önbellekten sonraki yeniden ayırma için ayrılan blokları alt tahsis edebilir.

Std değerini yeniden bindiremeyen bir derleyici ile::şablon anında kullanıldığında kullanılan size_t bağımsız değişken, bir önbelleğin üye işlevlerine aktarılan _Sz bağımsız değişkenin değeri olmak zorunda değildir.

\<ayırıcılar> aşağıdaki önbellek şablonlarını sağlar:

- [Cache_freelist](../standard-library/cache-freelist-class.md)

- [cache_suballoc](../standard-library/cache-suballoc-class.md)

- [cache_chunklist](../standard-library/cache-chunklist-class.md)

Filtre, üye işlevlerini şablon bağımsız değişkeni olarak geçirilen başka bir blok ayırıcısını kullanarak uygulayan bir blok ayırıcıdır. Filtrenin en yaygın biçimi, başka bir blok ayırıcının üye işlevlerine erişimi denetlemek için bir eşitleme ilkesi uygulayan bir eşitleme filtresidir. \<ayırıcılar> aşağıdaki eşitleme filtrelerini sağlar:

- [sync_none](../standard-library/sync-none-class.md)

- [sync_per_container](../standard-library/sync-per-container-class.md)

- [sync_per_thread](../standard-library/sync-per-thread-class.md)

- [sync_shared](../standard-library/sync-shared-class.md)

\<ayırıcılar>, birden çok blok ayırma örneğini tutan ve derleme zamanında yerine çalışma zamanında ayırma veya ayırma için hangi örneğin kullanılacağını belirleyen filtre [rts_alloc](../standard-library/rts-alloc-class.md)de sağlar. Rebind'i derleyemeyen derleyicilerle kullanılır.

Eşitleme ilkesi, ayırıcı örneğinin birden çok iş parçacığından eşzamanlı ayırma ve ayırma isteklerini nasıl işleyeceğini belirler. En basit ilke, tüm istekleri doğrudan temel önbellek nesnesine geçirerek eşitleme yönetimini kullanıcıya bırakmaktır. Daha karmaşık bir ilke, temel önbellek nesnesine erişimi seri hale getirmek için bir mutex kullanmak olabilir.

Derleyici hem tek iş parçacığı hem de çok iş parçacığı uygulamaları derlemeyi destekliyorsa, tek iş `sync_none`parçacığı uygulamaları için varsayılan eşitleme filtresi; diğer tüm durumlar `sync_shared`için öyle.

Önbellek şablonu, `cache_freelist` serbest listede depolanacak en fazla öğe sayısını belirleyen bir maksimum sınıf bağımsız değişkeni alır.

\<ayırıcılar> aşağıdaki max sınıfları sağlar:

- [max_none](../standard-library/max-none-class.md)

- [max_unbounded](../standard-library/max-unbounded-class.md)

- [max_fixed_size](../standard-library/max-fixed-size-class.md)

- [max_variable_size](../standard-library/max-variable-size-class.md)

### <a name="macros"></a>Makrolar

|Makro|Açıklama|
|-|-|
|[ALLOCATOR_DECL](../standard-library/allocators-functions.md#allocator_decl)|Ayırıcı sınıf şablonu verir.|
|[CACHE_CHUNKLIST](../standard-library/allocators-functions.md#cache_chunklist)|Verim. `stdext::allocators::cache_chunklist<sizeof(Type)>`|
|[Cache_freelist](../standard-library/allocators-functions.md#cache_freelist)|Verim. `stdext::allocators::cache_freelist<sizeof(Type), max>`|
|[CACHE_SUBALLOC](../standard-library/allocators-functions.md#cache_suballoc)|Verim. `stdext::allocators::cache_suballoc<sizeof(Type)>`|
|[SYNC_DEFAULT](../standard-library/allocators-functions.md#sync_default)|Eşitleme filtresi verir.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[işleç!=\<( tahsisat>)](../standard-library/allocators-operators.md#op_neq)|Belirtilen sınıfın ayırıcı nesneleri arasındaki eşitsizliği sınar.|
|[operator==\<( tahsisörler>)](../standard-library/allocators-operators.md#op_eq_eq)|Belirtilen sınıfın ayırıcı nesneleri arasındaki eşitliği sınar.|

### <a name="classes"></a>Sınıflar

|Sınıf|Açıklama|
|-|-|
|[allocator_base](../standard-library/allocator-base-class.md)|Eşitleme filtresinden kullanıcı tanımlı bir ayırıcı oluşturmak için gereken taban sınıf ve ortak işlevleri tanımlar.|
|[allocator_chunklist](../standard-library/allocator-chunklist-class.md)|Depolama ayırmayı yöneten ve [cache_chunklist](../standard-library/cache-chunklist-class.md)bir tür önbelleği kullanarak nesneler için serbest olan bir nesneyi açıklar.|
|[allocator_fixed_size](../standard-library/allocator-fixed-size-class.md)|max_fixed_size tarafından yönetilen bir uzunlukla [cache_freelist](../standard-library/cache-freelist-class.md) bir tür `Type` önbelleği kullanarak depolama ayırma ve tür nesneleri için serbest yöneten bir [nesneyi](../standard-library/max-fixed-size-class.md)açıklar.|
|[allocator_newdel](../standard-library/allocator-newdel-class.md)|Bir bellek bloğunu bulmak için **işleç delete'i** kullanan bir ayırıcı ve bellek bloğunu ayırmak için **yeni işleç** uygular.|
|[allocator_suballoc](../standard-library/allocator-suballoc-class.md)|Cache_suballoc türü önbelleği kullanarak depolama ayırma ve `Type` tür nesneleri için [cache_suballoc](../standard-library/cache-suballoc-class.md)serbest yöneten bir nesneyi açıklar.|
|[allocator_unbounded](../standard-library/allocator-unbounded-class.md)|Depolama ayırmayı yöneten ve cache_freelist bir önbellek `Type` kullanarak [tür](../standard-library/cache-freelist-class.md) nesneleri için serbest [max_unbounded](../standard-library/max-unbounded-class.md)tarafından yönetilen bir uzunluk ile bir nesne açıklar.|
|[allocator_variable_size](../standard-library/allocator-variable-size-class.md)|[Depolama](../standard-library/max-variable-size-class.md)ayırmayı yöneten ve max_variable_size tarafından yönetilen bir uzunluğa sahip [bir](../standard-library/cache-freelist-class.md) tür cache_freelist önbelleği kullanarak tür `Type` nesneleri için serbest bir nesneyi açıklar.|
|[cache_chunklist](../standard-library/cache-chunklist-class.md)|Tek bir boyuttaki bellek bloklarını ayıran ve ayıran bir blok ayırıcı tanımlar.|
|[Cache_freelist](../standard-library/cache-freelist-class.md)|Tek bir boyuttaki bellek bloklarını ayıran ve ayıran bir blok ayırıcı tanımlar.|
|[cache_suballoc](../standard-library/cache-suballoc-class.md)|Tek bir boyuttaki bellek bloklarını ayıran ve ayıran bir blok ayırıcı tanımlar.|
|[Freelist](../standard-library/freelist-class.md)|Bellek bloklarının listesini yönetir.|
|[max_fixed_size](../standard-library/max-fixed-size-class.md)|[Freelist](../standard-library/freelist-class.md) nesnesini sabit bir maksimum uzunluğa sınırlayan bir max sınıf nesnesini açıklar.|
|[max_none](../standard-library/max-none-class.md)|[Freelist](../standard-library/freelist-class.md) nesnesini en fazla sıfır uzunluğuyla sınırlayan bir max sınıf nesnesini açıklar.|
|[max_unbounded](../standard-library/max-unbounded-class.md)|[Freelist](../standard-library/freelist-class.md) nesnesinin maksimum uzunluğunu sınırlamayan bir max sınıf nesnesini açıklar.|
|[max_variable_size](../standard-library/max-variable-size-class.md)|[Freelist](../standard-library/freelist-class.md) nesnesini ayrılan bellek bloklarının sayısıyla kabaca orantılı olan en büyük uzunluğa sınırlayan bir max sınıf nesnesini açıklar.|
|[rts_alloc](../standard-library/rts-alloc-class.md)|rts_alloc sınıf şablonu, bir dizi önbellek örneği tutan ve derleme zamanında yerine çalışma zamanında ayırma ve ayırma için hangi örneğin kullanılacağını belirleyen bir [filtreyi](../standard-library/allocators-header.md) açıklar.|
|[sync_none](../standard-library/sync-none-class.md)|Eşitleme olmayan bir eşitleme filtresiaçıklar.|
|[sync_per_container](../standard-library/sync-per-container-class.md)|Her ayırıcı nesne için ayrı bir önbellek nesnesi sağlayan bir eşitleme filtresi açıklar.|
|[sync_per_thread](../standard-library/sync-per-thread-class.md)|Her iş parçacığı için ayrı bir önbellek nesnesi sağlayan bir eşitleme filtresi açıklar.|
|[sync_shared](../standard-library/sync-shared-class.md)|Tüm ayırıcılar tarafından paylaşılan bir önbellek nesnesine erişimi denetlemek için mutex kullanan bir eşitleme filtresi açıklar.|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** \<tahsisörler>

**Ad alanı:** stdext

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi Dosyaları Başvurusu](../standard-library/cpp-standard-library-header-files.md)
