---
title: '&lt;ayırıcılar&gt;'
ms.date: 11/04/2016
f1_keywords:
- <allocators>
helpviewer_keywords:
- allocators header
ms.assetid: 4393a607-4df8-4278-bbb2-c8ec52e60b83
ms.openlocfilehash: 69c086515230fd5a9aaa039ef02b7995842fa260
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87204891"
---
# <a name="ltallocatorsgt"></a>&lt;ayırıcılar&gt;

Düğüm tabanlı kapsayıcılar için bellek blokları ayırmaya ve serbest bırakma konusunda yardımcı olan çeşitli şablonlar tanımlar.

## <a name="syntax"></a>Sözdizimi

```cpp
#include <allocators>
```

> [!NOTE]
> \<allocators>, Visual Studio 2019 sürüm 16,3 ' den itibaren kullanımdan kaldırılmıştır.

## <a name="remarks"></a>Açıklamalar

\<allocators>Üst bilgi, düğüm tabanlı kapsayıcılar için bellek yönetimi stratejilerini seçmek üzere kullanılabilecek altı ayırıcı şablonu sağlar. Bu şablonlarla birlikte kullanmak için, bellek yönetimi stratejisini farklı çoklu iş parçacığı oluşturma şemalarına (hiçbiri dahil) uyarlamak için birkaç farklı eşitleme filtresi de sağlar. Bir bellek yönetim stratejisini bellek kullanım desenleri ve eşitleme gereksinimleriyle eşleştirerek uygulamanızı hızlandırabilir veya bellek gereksinimlerini azaltabilirsiniz.

Ayırıcı şablonları, ek bellek yönetimi stratejileri sağlamak üzere özelleştirilebilen veya değiştirilmekte olan yeniden kullanılabilir bileşenler ile uygulanır.

C++ standart kitaplığı 'ndaki düğüm tabanlı kapsayıcılar (std:: List, std:: set, std:: multıset, std:: Map ve std:: multimap) öğelerini ayrı düğümlerde depolar. Belirli bir kapsayıcı türü için tüm düğümler aynı boyutta olduğundan, genel amaçlı bellek yöneticisinin esnekliği gerekli değildir. Her bir bellek bloğunun boyutu derleme zamanında bilindiğinden, bellek Yöneticisi çok daha basit ve daha hızlı olabilir.

Düğüm tabanlı olmayan kapsayıcılar ile kullanıldığında (std:: vector std::d eque ve std:: basic_string), ayırıcı şablonları doğru şekilde çalışır, ancak varsayılan ayırıcı üzerinde herhangi bir performans geliştirmesi sunamayacaktır.

Ayırıcı, belirlenen bir türdeki nesne ve diziler için depolama ayırmayı ve boşaltmayı yöneten bir nesneyi tanımlayan bir sınıf şablonudur. Ayırıcı nesneleri, C++ standart kitaplığındaki çeşitli kapsayıcı sınıfı şablonları tarafından kullanılır.

Ayrıcılar, bu türdeki tüm şablonlardır:

```cpp
template<class Type>
class allocator;
```

şablon bağımsız değişkeninin `Type` ayırıcı örneği tarafından yönetilen tür olduğu yerdir. C++ standart kitaplığı, ' de tanımlanan bir varsayılan ayırıcı, sınıf şablonu [ayırıcısı](allocator-class.md)sağlar [\<memory>](memory.md) . \<allocators>Üst bilgi aşağıdaki ayırıcıları sağlar:

- [allocator_newdel](allocator-newdel-class.md)

- [allocator_unbounded](allocator-unbounded-class.md)

- [allocator_fixed_size](allocator-fixed-size-class.md)

- [allocator_variable_size](allocator-variable-size-class.md)

- [allocator_suballoc](allocator-suballoc-class.md)

- [allocator_chunklist](allocator-chunklist-class.md)

Aşağıdaki kod örneği gibi bir kapsayıcı oluştururken ikinci tür bağımsız değişkeni olarak ayırıcı için uygun bir örnek oluşturma kullanın.

```cpp
#include <list>
#include <allocators>
std::list<int, stdext::allocators::allocator_chunklist<int> > _List0;
```

_List0, `allocator_chunklist` ve varsayılan Eşitleme filtresiyle düğümleri ayırır.

Varsayılan dışında, eşitleme filtreleriyle ayırıcı şablonları oluşturmak için [ALLOCATOR_DECL](allocators-functions.md#allocator_decl) makro kullanın:

```cpp
#include <list>
#include <allocators>
ALLOCATOR_DECL(CACHE_CHUNKLIST, stdext::allocators::sync_per_thread, Alloc);
std::list<int, alloc<int> > _List1;
```

_Lst1, `allocator_chunklist` ve [sync_per_thread](sync-per-thread-class.md) Eşitleme filtresiyle düğümleri ayırır.

Blok ayırıcısı bir önbellek veya filtredir. Önbellek, std:: size_t türünde bir bağımsız değişken alan bir sınıf şablonudur. Tek boyuttaki bellek bloklarını ayıran ve ayıran bir blok ayırıcısı tanımlar. Bu, işleç kullanarak bellek almalıdır **`new`** , ancak her blok için ayrı bir işleç çağrısı yapmamalıdır **`new`** . Örneğin, daha büyük bir bloktan veya ön yeniden tahsisatın ardından önbellek serbest bırakılmış bloklardan alt ayırma olabilir.

Şablon örneği oluşturulurken kullanılan std:: size_t bağımsız değişkeninin değerini yeniden ayıramayan bir derleyici ile, bir önbelleğin üye işlevlerine aktarılan ve serbest bırakma _Sz bağımsız değişkenin değeri olması gerekmez.

\<allocators>aşağıdaki önbellek şablonlarını sağlar:

- [cache_freelist](cache-freelist-class.md)

- [cache_suballoc](cache-suballoc-class.md)

- [cache_chunklist](cache-chunklist-class.md)

Filtre, bir şablon bağımsız değişkeni olarak kendisine geçirilen başka bir blok ayırıcısı kullanarak üye işlevlerini uygulayan bir blok ayırıcıdır. En yaygın filtre biçimi, başka bir blok ayırıcısı örneğinin üye işlevlerine erişimi denetlemek için bir eşitleme ilkesi uygulayan bir eşitleme filtresidir. \<allocators>Aşağıdaki eşitleme filtrelerini sağlar:

- [sync_none](sync-none-class.md)

- [sync_per_container](sync-per-container-class.md)

- [sync_per_thread](sync-per-thread-class.md)

- [sync_shared](sync-shared-class.md)

\<allocators>Ayrıca, birden çok blok ayırıcı örneği tutan filtre [Rts_alloc](rts-alloc-class.md)sağlar ve derleme süresi yerine çalışma zamanında ayırma veya ayırmayı kaldırma için hangi örneği kullanacağınızı belirler. Yeniden bağlama Derlenemeyen derleyiciler ile kullanılır.

Bir atama ilkesi, bir ayırıcı örneğinin birden çok iş parçacığından eşzamanlı ayırmayı ve kaldırma isteklerini nasıl işlediğini belirler. En basit ilke, tüm istekleri doğrudan temeldeki önbellek nesnesine geçirmektir ve eşitleme yönetimini kullanıcıya bırakır. Daha karmaşık bir ilke, temel alınan önbellek nesnesine erişimi seri hale getirmek için bir mutex kullanmak olabilir.

Bir derleyici hem tek iş parçacıklı hem çok iş parçacıklı uygulamalar derlemeyi destekliyorsa, tek iş parçacıklı uygulamalar için varsayılan eşitleme filtresi olur `sync_none` ; diğer tüm durumlar için `sync_shared` .

Önbellek şablonu, `cache_freelist` ücretsiz listede depolanacak en fazla öğe sayısını belirleyen bir Max Class bağımsız değişkeni alır.

\<allocators>Aşağıdaki en büyük sınıfları sağlar:

- [max_none](max-none-class.md)

- [max_unbounded](max-unbounded-class.md)

- [max_fixed_size](max-fixed-size-class.md)

- [max_variable_size](max-variable-size-class.md)

### <a name="macros"></a>Makrolar

|Makroya|Açıklama|
|-|-|
|[ALLOCATOR_DECL](allocators-functions.md#allocator_decl)|Ayırıcı sınıf şablonu verir.|
|[CACHE_CHUNKLIST](allocators-functions.md#cache_chunklist)|Verir `stdext::allocators::cache_chunklist<sizeof(Type)>` .|
|[CACHE_FREELIST](allocators-functions.md#cache_freelist)|Verir `stdext::allocators::cache_freelist<sizeof(Type), max>` .|
|[CACHE_SUBALLOC](allocators-functions.md#cache_suballoc)|Verir `stdext::allocators::cache_suballoc<sizeof(Type)>` .|
|[SYNC_DEFAULT](allocators-functions.md#sync_default)|Bir eşitleme filtresi verir.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[operator! = ( \<allocators> )](allocators-operators.md#op_neq)|Belirtilen sınıfın ayırıcı nesneleri arasındaki eşitsizliği sınar.|
|[operator = = ( \<allocators> )](allocators-operators.md#op_eq_eq)|Belirtilen sınıfın ayırıcı nesneleri arasındaki eşitliği sınar.|

### <a name="classes"></a>Sınıflar

|Sınıf|Açıklama|
|-|-|
|[allocator_base](allocator-base-class.md)|Bir eşitleme filtresinden Kullanıcı tanımlı bir ayırıcı oluşturmak için gereken temel sınıfı ve ortak işlevleri tanımlar.|
|[allocator_chunklist](allocator-chunklist-class.md)|[Cache_chunklist](cache-chunklist-class.md)türünde bir önbellek kullanarak nesneler için depolama ayırmayı ve boşaltmayı yöneten bir nesneyi tanımlar.|
|[allocator_fixed_size](allocator-fixed-size-class.md)|`Type` [Max_fixed_size](max-fixed-size-class.md)tarafından yönetilen uzunluğa sahip [cache_freelist](cache-freelist-class.md) türünde bir önbellek kullanarak türündeki nesneler için depolama ayırmayı ve boşaltmayı yöneten bir nesneyi tanımlar.|
|[allocator_newdel](allocator-newdel-class.md)|Bellek bloğunu serbest bırakmak için **operator delete** kullanan bir ayırıcı uygular ve **Yeni işleci** bir bellek bloğu ayırır.|
|[allocator_suballoc](allocator-suballoc-class.md)|`Type` [Cache_suballoc](cache-suballoc-class.md)türünde bir önbellek kullanarak türündeki nesneler için depolama ayırmayı ve boşaltmayı yöneten bir nesneyi tanımlar.|
|[allocator_unbounded](allocator-unbounded-class.md)|`Type` [Max_unbounded](max-unbounded-class.md)tarafından yönetilen uzunluğa sahip [cache_freelist](cache-freelist-class.md) türünde bir önbellek kullanarak türündeki nesneler için depolama ayırmayı ve boşaltmayı yöneten bir nesneyi tanımlar.|
|[allocator_variable_size](allocator-variable-size-class.md)|`Type` [Max_variable_size](max-variable-size-class.md)tarafından yönetilen uzunluğa sahip [cache_freelist](cache-freelist-class.md) türünde bir önbellek kullanarak türündeki nesneler için depolama ayırmayı ve boşaltmayı yöneten bir nesneyi tanımlar.|
|[cache_chunklist](cache-chunklist-class.md)|Tek boyuttaki bellek bloklarını ayıran ve ayıran blok ayırıcıyı tanımlar.|
|[cache_freelist](cache-freelist-class.md)|Tek boyuttaki bellek bloklarını ayıran ve ayıran blok ayırıcıyı tanımlar.|
|[cache_suballoc](cache-suballoc-class.md)|Tek boyuttaki bellek bloklarını ayıran ve ayıran blok ayırıcıyı tanımlar.|
|[freelist](freelist-class.md)|Bellek bloklarının listesini yönetir.|
|[max_fixed_size](max-fixed-size-class.md)|[Freelist](freelist-class.md) nesnesini sabit maksimum uzunlukla sınırlayan bir Max Class nesnesi tanımlar.|
|[max_none](max-none-class.md)|[Freelist](freelist-class.md) nesnesini en fazla sıfır uzunluğuna sınırlayan bir Max Class nesnesi tanımlar.|
|[max_unbounded](max-unbounded-class.md)|[Freelist](freelist-class.md) nesnesinin maksimum uzunluğunu sınırlayan bir Max Class nesnesi tanımlar.|
|[max_variable_size](max-variable-size-class.md)|[Freelist](freelist-class.md) nesnesini ayrılan bellek bloklarının sayısıyla kabaca orantılı olan en büyük uzunluğa sınırlayan bir Max Class nesnesi tanımlar.|
|[rts_alloc](rts-alloc-class.md)|Rts_alloc sınıf şablonu, bir dizi önbellek örneği tutan ve derleme süresi yerine çalışma zamanında ayırma ve ayırmayı kaldırma için hangi örneği kullanacağınızı belirleyen bir [filtre](allocators-header.md) tanımlar.|
|[sync_none](sync-none-class.md)|Eşitleme sağlayan bir eşitleme filtresi tanımlar.|
|[sync_per_container](sync-per-container-class.md)|Her ayırıcı nesnesi için ayrı bir önbellek nesnesi sağlayan bir eşitleme filtresi tanımlar.|
|[sync_per_thread](sync-per-thread-class.md)|Her iş parçacığı için ayrı bir önbellek nesnesi sağlayan bir eşitleme filtresi tanımlar.|
|[sync_shared](sync-shared-class.md)|Tüm ayırıcılar tarafından paylaşılan bir önbellek nesnesine erişimi denetlemek için bir mutex kullanan bir eşitleme filtresi tanımlar.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<allocators>

**Ad alanı:** stdext

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](cpp-standard-library-header-files.md)
