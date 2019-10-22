---
title: '&lt;allocators &gt;'
ms.date: 11/04/2016
f1_keywords:
- <allocators>
helpviewer_keywords:
- allocators header
ms.assetid: 4393a607-4df8-4278-bbb2-c8ec52e60b83
ms.openlocfilehash: 3619f3810f167fef291ad3def4a2b94f9a6b9b1a
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2019
ms.locfileid: "72688474"
---
# <a name="ltallocatorsgt"></a>&lt;allocators &gt;

Düğüm tabanlı kapsayıcılar için bellek blokları ayırmaya ve serbest bırakma konusunda yardımcı olan çeşitli şablonlar tanımlar.

## <a name="syntax"></a>Sözdizimi

```cpp
#include <allocators>
```

## <a name="remarks"></a>Açıklamalar

@No__t_0allocators > üst bilgisi, düğüm tabanlı kapsayıcılar için bellek yönetimi stratejilerini seçmek üzere kullanılabilecek altı ayırıcı şablonu sağlar. Bu şablonlarla birlikte kullanmak için, bellek yönetimi stratejisini farklı çoklu iş parçacığı oluşturma şemalarına (hiçbiri dahil) uyarlamak için birkaç farklı eşitleme filtresi de sağlar. Bir bellek yönetim stratejisini bilinen bellek kullanımı desenleriyle eşleştirme ve belirli bir uygulamanın eşitleme gereksinimleri, genellikle bir uygulamanın hızını artırabilir veya genel bellek gereksinimlerinin azalmasını sağlayabilir.

Ayırıcı şablonları, ek bellek yönetimi stratejileri sağlamak üzere özelleştirilebilen veya değiştirilmekte olan yeniden kullanılabilir bileşenler ile uygulanır.

C++ Standart kitaplıktaki düğüm tabanlı kapsayıcılar (std:: List, std:: set, std:: multıset, std:: Map ve std:: multimap) öğelerini ayrı düğümlerde depolar. Belirli bir kapsayıcı türü için tüm düğümler aynı boyutta olduğundan, genel amaçlı bellek yöneticisinin esnekliği gerekli değildir. Her bir bellek bloğunun boyutu derleme zamanında bilindiğinden, bellek Yöneticisi çok daha basit ve daha hızlı olabilir.

Düğüm tabanlı olmayan kapsayıcılar ( C++ standart kitaplık kapsayıcıları std:: vector std::d eque ve std:: basic_string) kullanıldığında, alllocator şablonları doğru şekilde çalışır, ancak herhangi bir performans geliştirmesi sağlamak olası değildir Varsayılan ayırıcı.

Ayırıcı, belirlenen bir türdeki nesne ve diziler için depolama ayırmayı ve boşaltmayı yöneten bir nesneyi tanımlayan bir sınıf şablonudur. Ayırıcı nesneleri C++ standart kitaplıktaki çeşitli kapsayıcı sınıfı şablonları tarafından kullanılır.

Ayrıcılar, bu türdeki tüm şablonlardır:

```cpp
template<class Type>
class allocator;
```

`Type` şablon bağımsız değişkeni ayırıcı örneği tarafından yönetilen türdür. C++ Standart kitaplık, [\<memory >](../standard-library/memory.md)tanımlanan bir varsayılan ayırıcı, sınıf şablonu [ayırıcısı](../standard-library/allocator-class.md)sağlar. @No__t_0allocators > üst bilgisi aşağıdaki ayırıcıları sağlar:

- [allocator_newdel](../standard-library/allocator-newdel-class.md)

- [allocator_unbounded](../standard-library/allocator-unbounded-class.md)

- [allocator_fixed_size](../standard-library/allocator-fixed-size-class.md)

- [allocator_variable_size](../standard-library/allocator-variable-size-class.md)

- [allocator_suballoc](../standard-library/allocator-suballoc-class.md)

- [allocator_chunklist](../standard-library/allocator-chunklist-class.md)

Aşağıdaki kod örneği gibi bir kapsayıcı oluştururken ikinci tür bağımsız değişkeni olarak ayırıcı için uygun bir örnek oluşturma kullanın.

```cpp
#include <list>
#include <allocators>
std::list<int, stdext::allocators::allocator_chunklist<int> > _List0;
```

_List0, `allocator_chunklist` ve varsayılan Eşitleme filtresiyle düğümleri ayırır.

Varsayılan dışında, eşitleme filtreleriyle ayırıcı şablonları oluşturmak için [ALLOCATOR_DECL](../standard-library/allocators-functions.md#allocator_decl) makrosunu kullanın:

```cpp
#include <list>
#include <allocators>
ALLOCATOR_DECL(CACHE_CHUNKLIST, stdext::allocators::sync_per_thread, Alloc);
std::list<int, alloc<int> > _List1;
```

_Lst1, `allocator_chunklist` ve [sync_per_thread](../standard-library/sync-per-thread-class.md) Eşitleme filtresiyle düğümleri ayırır.

Blok ayırıcısı bir önbellek veya filtredir. Önbellek, std:: size_t türünde bir bağımsız değişken alan bir sınıf şablonudur. Tek boyuttaki bellek bloklarını ayıran ve ayıran bir blok ayırıcısı tanımlar. **Yeni**işleç kullanarak bellek almalıdır, ancak her bir blok için **Yeni** operatör için ayrı bir çağrı yapmamalıdır. Örneğin, daha büyük bir bloktan veya ön yeniden tahsisatın ardından önbellek serbest bırakılmış bloklardan alt ayırma olabilir.

Derleyemeyen bir derleyici ile, şablon örneği oluşturulurken kullanılan std:: size_t bağımsız değişkeninin değeri, bir önbelleğin üye işlevlerine aktarılan ve serbest bırakma için _Sz bağımsız değişkeninin değeri olması gerekmez.

\<allocators > aşağıdaki önbellek şablonlarını sağlar:

- [cache_freelist](../standard-library/cache-freelist-class.md)

- [cache_suballoc](../standard-library/cache-suballoc-class.md)

- [cache_chunklist](../standard-library/cache-chunklist-class.md)

Filtre, bir şablon bağımsız değişkeni olarak kendisine geçirilen başka bir blok ayırıcısı kullanarak üye işlevlerini uygulayan bir blok ayırıcıdır. En yaygın filtre biçimi, başka bir blok ayırıcısı örneğinin üye işlevlerine erişimi denetlemek için bir eşitleme ilkesi uygulayan bir eşitleme filtresidir. \<allocators > Aşağıdaki eşitleme filtrelerini sağlar:

- [sync_none](../standard-library/sync-none-class.md)

- [sync_per_container](../standard-library/sync-per-container-class.md)

- [sync_per_thread](../standard-library/sync-per-thread-class.md)

- [sync_shared](../standard-library/sync-shared-class.md)

\<allocators >, birden fazla blok ayırıcı örneği tutan ve derleme süresi yerine çalışma zamanında ayırma veya ayırmayı kaldırma için hangi örneği kullanacağınızı belirleyen filtre [Rts_alloc](../standard-library/rts-alloc-class.md)de sağlar. Yeniden bağlama Derlenemeyen derleyiciler ile kullanılır.

Bir atama ilkesi, bir ayırıcı örneğinin birden çok iş parçacığından eşzamanlı ayırmayı ve kaldırma isteklerini nasıl işlediğini belirler. En basit ilke, tüm istekleri doğrudan temeldeki önbellek nesnesine geçirmektir ve eşitleme yönetimini kullanıcıya bırakır. Daha karmaşık bir ilke, temel alınan önbellek nesnesine erişimi seri hale getirmek için bir mutex kullanmak olabilir.

Bir derleyici hem tek iş parçacıklı hem çok iş parçacıklı uygulamalar derlemeyi destekliyorsa, tek iş parçacıklı uygulamalar için varsayılan eşitleme filtresi `sync_none`; Tüm diğer durumlar için `sync_shared`.

Önbellek şablonu `cache_freelist`, ücretsiz listede depolanacak en fazla öğe sayısını belirleyen bir Max Class bağımsız değişkeni alır.

\<allocators > aşağıdaki en büyük sınıfları sağlar:

- [max_none](../standard-library/max-none-class.md)

- [max_unbounded](../standard-library/max-unbounded-class.md)

- [max_fixed_size](../standard-library/max-fixed-size-class.md)

- [max_variable_size](../standard-library/max-variable-size-class.md)

### <a name="macros"></a>Makrolar

|Makroya|Açıklama|
|-|-|
|[ALLOCATOR_DECL](../standard-library/allocators-functions.md#allocator_decl)|Ayırıcı sınıf şablonu verir.|
|[CACHE_CHUNKLIST](../standard-library/allocators-functions.md#cache_chunklist)|@No__t_0 verir.|
|[CACHE_FREELIST](../standard-library/allocators-functions.md#cache_freelist)|@No__t_0 verir.|
|[CACHE_SUBALLOC](../standard-library/allocators-functions.md#cache_suballoc)|@No__t_0 verir.|
|[SYNC_DEFAULT](../standard-library/allocators-functions.md#sync_default)|Bir eşitleme filtresi verir.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[operator! = (\<allocators >)](../standard-library/allocators-operators.md#op_neq)|Belirtilen sınıfın ayırıcı nesneleri arasındaki eşitsizliği sınar.|
|[operator = = (\<allocators >)](../standard-library/allocators-operators.md#op_eq_eq)|Belirtilen sınıfın ayırıcı nesneleri arasındaki eşitliği sınar.|

### <a name="classes"></a>Sınıflar

|örneği|Açıklama|
|-|-|
|[allocator_base](../standard-library/allocator-base-class.md)|Bir eşitleme filtresinden Kullanıcı tanımlı bir ayırıcı oluşturmak için gereken temel sınıfı ve ortak işlevleri tanımlar.|
|[allocator_chunklist](../standard-library/allocator-chunklist-class.md)|[Cache_chunklist](../standard-library/cache-chunklist-class.md)türünde bir önbellek kullanarak nesneler için depolama ayırmayı ve boşaltmayı yöneten bir nesneyi tanımlar.|
|[allocator_fixed_size](../standard-library/allocator-fixed-size-class.md)|[Max_fixed_size](../standard-library/max-fixed-size-class.md)tarafından yönetilen bir uzunluğa sahip [cache_freelist](../standard-library/cache-freelist-class.md) türünde bir önbellek kullanarak `Type` türündeki nesneler için depolama ayırmayı ve boşaltmayı yöneten bir nesneyi tanımlar.|
|[allocator_newdel](../standard-library/allocator-newdel-class.md)|Bellek bloğunu serbest bırakmak için **operator delete** kullanan bir ayırıcı uygular ve **Yeni işleci** bir bellek bloğu ayırır.|
|[allocator_suballoc](../standard-library/allocator-suballoc-class.md)|[Cache_suballoc](../standard-library/cache-suballoc-class.md)türünde bir önbellek kullanarak `Type` türündeki nesneler için depolama ayırmayı ve boşaltmayı yöneten bir nesneyi tanımlar.|
|[allocator_unbounded](../standard-library/allocator-unbounded-class.md)|[Max_unbounded](../standard-library/max-unbounded-class.md)tarafından yönetilen bir uzunluğa sahip [cache_freelist](../standard-library/cache-freelist-class.md) türünde bir önbellek kullanarak `Type` türündeki nesneler için depolama ayırmayı ve boşaltmayı yöneten bir nesneyi tanımlar.|
|[allocator_variable_size](../standard-library/allocator-variable-size-class.md)|[Max_variable_size](../standard-library/max-variable-size-class.md)tarafından yönetilen bir uzunluğa sahip [cache_freelist](../standard-library/cache-freelist-class.md) türünde bir önbellek kullanarak `Type` türündeki nesneler için depolama ayırmayı ve boşaltmayı yöneten bir nesneyi tanımlar.|
|[cache_chunklist](../standard-library/cache-chunklist-class.md)|Tek boyuttaki bellek bloklarını ayıran ve ayıran blok ayırıcıyı tanımlar.|
|[cache_freelist](../standard-library/cache-freelist-class.md)|Tek boyuttaki bellek bloklarını ayıran ve ayıran blok ayırıcıyı tanımlar.|
|[cache_suballoc](../standard-library/cache-suballoc-class.md)|Tek boyuttaki bellek bloklarını ayıran ve ayıran blok ayırıcıyı tanımlar.|
|[freelist](../standard-library/freelist-class.md)|Bellek bloklarının listesini yönetir.|
|[max_fixed_size](../standard-library/max-fixed-size-class.md)|[Freelist](../standard-library/freelist-class.md) nesnesini sabit maksimum uzunlukla sınırlayan bir Max Class nesnesi tanımlar.|
|[max_none](../standard-library/max-none-class.md)|[Freelist](../standard-library/freelist-class.md) nesnesini en fazla sıfır uzunluğuna sınırlayan bir Max Class nesnesi tanımlar.|
|[max_unbounded](../standard-library/max-unbounded-class.md)|[Freelist](../standard-library/freelist-class.md) nesnesinin maksimum uzunluğunu sınırlayan bir Max Class nesnesi tanımlar.|
|[max_variable_size](../standard-library/max-variable-size-class.md)|[Freelist](../standard-library/freelist-class.md) nesnesini ayrılan bellek bloklarının sayısıyla kabaca orantılı olan en büyük uzunluğa sınırlayan bir Max Class nesnesi tanımlar.|
|[rts_alloc](../standard-library/rts-alloc-class.md)|Rts_alloc sınıf şablonu, bir dizi önbellek örneği tutan bir [filtre](../standard-library/allocators-header.md) tanımlar ve derleme zamanı yerine çalışma zamanında ayırma ve ayırmayı kaldırma için hangi örneği kullanacağınızı belirler.|
|[sync_none](../standard-library/sync-none-class.md)|Eşitleme sağlayan bir eşitleme filtresi tanımlar.|
|[sync_per_container](../standard-library/sync-per-container-class.md)|Her ayırıcı nesnesi için ayrı bir önbellek nesnesi sağlayan bir eşitleme filtresi tanımlar.|
|[sync_per_thread](../standard-library/sync-per-thread-class.md)|Her iş parçacığı için ayrı bir önbellek nesnesi sağlayan bir eşitleme filtresi tanımlar.|
|[sync_shared](../standard-library/sync-shared-class.md)|Tüm ayırıcılar tarafından paylaşılan bir önbellek nesnesine erişimi denetlemek için bir mutex kullanan bir eşitleme filtresi tanımlar.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<allocators >

**Ad alanı:** stdext

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)
