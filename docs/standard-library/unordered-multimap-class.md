---
title: unordered_multimap Sınıfı
description: C++ standart kitaplığı kapsayıcı sınıfı için API 'ye Genel Bakış `unordered_multimap` .
ms.date: 9/9/2020
f1_keywords:
- unordered_map/std::unordered_multimap
- unordered_map/std::unordered_multimap::allocator_type
- unordered_map/std::unordered_multimap::const_iterator
- unordered_map/std::unordered_multimap::const_local_iterator
- unordered_map/std::unordered_multimap::const_pointer
- unordered_map/std::unordered_multimap::const_reference
- unordered_map/std::unordered_multimap::difference_type
- unordered_map/std::unordered_multimap::hasher
- unordered_map/std::unordered_multimap::iterator
- unordered_map/std::unordered_multimap::key_equal
- unordered_map/std::unordered_multimap::key_type
- unordered_map/std::unordered_multimap::local_iterator
- unordered_map/std::unordered_multimap::mapped_type
- unordered_map/std::unordered_multimap::pointer
- unordered_map/std::unordered_multimap::reference
- unordered_map/std::unordered_multimap::size_type
- unordered_map/std::unordered_multimap::value_type
- unordered_map/std::unordered_multimap::begin
- unordered_map/std::unordered_multimap::bucket
- unordered_map/std::unordered_multimap::bucket_count
- unordered_map/std::unordered_multimap::bucket_size
- unordered_map/std::unordered_multimap::cbegin
- unordered_map/std::unordered_multimap::cend
- unordered_map/std::unordered_multimap::clear
- unordered_map/std::unordered_multimap::contains
- unordered_map/std::unordered_multimap::count
- unordered_map/std::unordered_multimap::emplace
- unordered_map/std::unordered_multimap::emplace_hint
- unordered_map/std::unordered_multimap::empty
- unordered_map/std::unordered_multimap::end
- unordered_map/std::unordered_multimap::equal_range
- unordered_map/std::unordered_multimap::erase
- unordered_map/std::unordered_multimap::find
- unordered_map/std::unordered_multimap::get_allocator
- unordered_map/std::unordered_multimap::hash
- unordered_map/std::unordered_multimap::insert
- unordered_map/std::unordered_multimap::key_eq
- unordered_map/std::unordered_multimap::load_factor
- unordered_map/std::unordered_multimap::max_bucket_count
- unordered_map/std::unordered_multimap::max_load_factor
- unordered_map/std::unordered_multimap::max_size
- unordered_map/std::unordered_multimap::rehash
- unordered_map/std::unordered_multimap::size
- unordered_map/std::unordered_multimap::swap
- unordered_map/std::unordered_multimap::unordered_multimap
- unordered_map/std::unordered_multimap::operator=
- unordered_map/std::unordered_multimap::hash_function
helpviewer_keywords:
- std::unordered_multimap
- std::unordered_multimap::allocator_type
- std::unordered_multimap::const_iterator
- std::unordered_multimap::const_local_iterator
- std::unordered_multimap::const_pointer
- std::unordered_multimap::const_reference
- std::unordered_multimap::difference_type
- std::unordered_multimap::hasher
- std::unordered_multimap::iterator
- std::unordered_multimap::key_equal
- std::unordered_multimap::key_type
- std::unordered_multimap::local_iterator
- std::unordered_multimap::mapped_type
- std::unordered_multimap::pointer
- std::unordered_multimap::reference
- std::unordered_multimap::size_type
- std::unordered_multimap::value_type
- std::unordered_multimap::begin
- std::unordered_multimap::bucket
- std::unordered_multimap::bucket_count
- std::unordered_multimap::bucket_size
- std::unordered_multimap::cbegin
- std::unordered_multimap::cend
- std::unordered_multimap::clear
- std::unordered_multimap::contains
- std::unordered_multimap::count
- std::unordered_multimap::emplace
- std::unordered_multimap::emplace_hint
- std::unordered_multimap::empty
- std::unordered_multimap::end
- std::unordered_multimap::equal_range
- std::unordered_multimap::erase
- std::unordered_multimap::find
- std::unordered_multimap::get_allocator
- std::unordered_multimap::hash
- std::unordered_multimap::insert
- std::unordered_multimap::key_eq
- std::unordered_multimap::load_factor
- std::unordered_multimap::max_bucket_count
- std::unordered_multimap::max_load_factor
- std::unordered_multimap::max_size
- std::unordered_multimap::rehash
- std::unordered_multimap::size
- std::unordered_multimap::swap
- std::unordered_multimap::unordered_multimap
- std::unordered_multimap::operator=
- std::unordered_multimap::allocator_type
- std::unordered_multimap::const_iterator
- std::unordered_multimap::const_local_iterator
- std::unordered_multimap::const_pointer
- std::unordered_multimap::const_reference
- std::unordered_multimap::difference_type
- std::unordered_multimap::hasher
- std::unordered_multimap::iterator
- std::unordered_multimap::key_equal
- std::unordered_multimap::key_type
- std::unordered_multimap::local_iterator
- std::unordered_multimap::mapped_type
- std::unordered_multimap::pointer
- std::unordered_multimap::reference
- std::unordered_multimap::size_type
- std::unordered_multimap::value_type
- std::unordered_multimap::begin
- std::unordered_multimap::bucket
- std::unordered_multimap::bucket_count
- std::unordered_multimap::bucket_size
- std::unordered_multimap::cbegin
- std::unordered_multimap::cend
- std::unordered_multimap::clear
- std::unordered_multimap::count
- std::unordered_multimap::emplace
- std::unordered_multimap::emplace_hint
- std::unordered_multimap::empty
- std::unordered_multimap::end
- std::unordered_multimap::equal_range
- std::unordered_multimap::erase
- std::unordered_multimap::find
- std::unordered_multimap::get_allocator
- std::unordered_multimap::hash_function
- std::unordered_multimap::insert
- std::unordered_multimap::key_eq
- std::unordered_multimap::load_factor
- std::unordered_multimap::max_bucket_count
- std::unordered_multimap::max_load_factor
- std::unordered_multimap::max_size
- std::unordered_multimap::rehash
- std::unordered_multimap::size
- std::unordered_multimap::swap
ms.assetid: 4baead6c-5870-4b85-940f-a47d6b891c27
ms.openlocfilehash: 5ca739e4c10fbca6cfd85b182e0052bcad19bf21
ms.sourcegitcommit: 6280a4c629de0f638ebc2edd446de2a9b11f0406
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2020
ms.locfileid: "90042075"
---
# <a name="unordered_multimap-class"></a>unordered_multimap Sınıfı

Sınıf şablonu, türünde öğelerin değişen uzunluklu dizisini denetleyen bir nesneyi tanımlar `std::pair<const Key, Ty>` . Dizi çağrılan demetlerin sıralı bir dizi kümesini bölümleyen bir karma işlev tarafından zayıf bir şekilde sıralanır. Her bir demette herhangi bir öğe çiftinin eşdeğer sıralamaya sahip olup olmadığını belirleyen bir karşılaştırma işlevi vardır. Her bir öğe iki nesne, bir sıralama anahtarı ve bir değer depolar. Dizi, en azından tüm demetleri kabaca eşit uzunlukta olduğunda, dizideki (sabit zaman) öğe sayısından bağımsız olabilen işlem sayısına sahip rastgele bir öğenin aranması, eklenmesi ve kaldırılmasına izin verecek şekilde temsil edilir. En kötü durumda, tüm öğeler tek bir demet içinde olduğunda işlem sayısı dizideki (doğrusal zaman) öğelerin sayısıyla orantılıdır. Ayrıca, bir öğe eklenmesi hiçbir yineleyiciyi geçersiz kılmaz; bir öğenin kaldırılması yalnızca bu kaldırılan öğeyi gösteren yineleyicileri geçersiz kılar.

## <a name="syntax"></a>Söz dizimi

```cpp
template <class Key,
    class Ty,
    class Hash = std::hash<Key>,
    class Pred = std::equal_to<Key>,
    class Alloc = std::allocator<Key>>
class unordered_multimap;
```

### <a name="parameters"></a>Parametreler

*Anahtar*\
Anahtar türü.

*Kalite*\
Eşlenen tür.

*Yla*\
Karma işlev nesne türü.

*Pred*\
Eşitlik karşılaştırma işlevi nesne türü.

*Tahsis*\
Ayırıcı sınıf.

## <a name="members"></a>Üyeler

|Tür Tanımı|Description|
|-|-|
|[allocator_type](#allocator_type)|Depolamayı yönetmek için bir ayırıcı türü.|
|[const_iterator](#const_iterator)|Denetlenen dizi için bir sabit yineleyici türü.|
|[const_local_iterator](#const_local_iterator)|Denetlenen dizi için bir sabit demet yineleyici türü.|
|[const_pointer](#const_pointer)|Bir öğe için sabit bir işaretçi türü.|
|[const_reference](#const_reference)|Bir öğe için sabit bir başvuru türü.|
|[difference_type](#difference_type)|İki öğe arasındaki işaretli mesafenin türü.|
|[karma değeri Oluşturucusu](#hasher)|Karma işlevin türü.|
|[iden](#iterator)|Denetlenen dizi için bir yineleyici türü.|
|[key_equal](#key_equal)|Karşılaştırma işlevinin türü.|
|[key_type](#key_type)|Bir sıralama anahtarının türü.|
|[local_iterator](#local_iterator)|Denetlenen dizi için bir demet yineleyici türü.|
|[mapped_type](#mapped_type)|Her bir anahtar ile ilişkili bir eşlenen değer türü.|
|[pointer](#pointer)|Bir öğe için bir işaretçi türü.|
|[başvurunun](#reference)|Bir öğe için bir başvuru türü.|
|[size_type](#size_type)|İki öğe arasındaki işaretsiz bir mesafenin türü.|
|[value_type](#value_type)|Öğenin türü.|

|Üye İşlevi|Description|
|-|-|
|[başladı](#begin)|Denetlenen dizinin başlangıcını belirtir.|
|[demet](#bucket)|Bir anahtar değeri için demet numarasını alır.|
|[bucket_count](#bucket_count)|Demet sayısını alır.|
|[bucket_size](#bucket_size)|Demet boyutunu alır.|
|[cbegin](#cbegin)|Denetlenen dizinin başlangıcını belirtir.|
|[cend](#cend)|Denetlenen dizinin bitişini belirtir.|
|[lediğiniz](#clear)|Tüm öğeleri kaldırır.|
|[contains](#contains)<sup>c++ 20</sup> içerir|İçinde belirtilen anahtara sahip bir öğe olup olmadığını denetler `unordered_multimap` .|
|[biriktirme](#count)|Belirtilen bir anahtar ile eşleşen öğe sayısını bulur.|
|[Emplace](#emplace)|Yerinde oluşturulmuş bir öğe ekler.|
|[emplace_hint](#emplace_hint)|Göstergeyle birlikte, yerinde oluşturulmuş bir öğe ekler.|
|[empty](#empty)|Bir öğe olup olmadığını sınar.|
|[erer](#end)|Denetlenen dizinin bitişini belirtir.|
|[equal_range](#equal_range)|Belirtilen bir anahtarla eşleşen aralığı bulur.|
|[silme](#erase)|Belirtilen konumlardaki öğeleri kaldırır.|
|[find](#find)|Belirtilen bir anahtarla eşleşen bir öğeyi bulur.|
|[get_allocator](#get_allocator)|Depolanan ayırıcı nesnesini alır.|
|[hash_function](#hash)|Depolanan karma işlevi nesnesini alır.|
|[ekleyin](#insert)|Öğeleri ekler.|
|[key_eq](#key_eq)|Depolanan karşılaştırma işlevi nesnesini alır.|
|[load_factor](#load_factor)|Demet başına ortalama öğeyi sayar.|
|[max_bucket_count](#max_bucket_count)|En yüksek demet sayısını alır.|
|[max_load_factor](#max_load_factor)|Demet başına en yüksek öğe sayısını alır veya ayarlar.|
|[max_size](#max_size)|Denetlenen dizinin en büyük boyutunu alır.|
|[rehash](#rehash)|Karma tabloyu yeniden oluşturur.|
|[boyutla](#size)|Öğe sayısını sayar.|
|[Kur](#swap)|İki kapsayıcının içeriğinin yerini değiştirir.|
|[unordered_multimap](#unordered_multimap)|Bir kapsayıcı nesnesi oluşturur.|

|İşleç|Açıklama|
|-|-|
|[unordered_multimap:: operator =](#op_eq)|Bir karma tabloya kopyalar.|

## <a name="remarks"></a>Açıklamalar

Nesne, iki saklı nesneyi çağırarak denetlediği sırayı, [unordered_multimap:: key_equal](#key_equal) türünde bir karşılaştırma işlev nesnesi ve [unordered_multimap:: hasher](#hasher)türünde bir karma işlev nesnesi olarak sıralar. [Unordered_multimap:: key_eq](#key_eq); üye işlevini çağırarak `()` ve ikinci saklı nesneye eriştiğinizde, [unordered_multimap:: hash_function](#hash)üye işlevini çağırarak, ilk depolanan nesneye erişirsiniz `()` . Özellikle, tüm değerleri `X` ve `Y` türü için `Key` , çağrı `key_eq()(X, Y)` yalnızca iki bağımsız değişken değeri eşdeğer sıralama içeriyorsa true değerini döndürür; çağrı, `hash_function()(keyval)` türündeki değerlerin bir dağılımını verir `size_t` . Sınıf şablonu [unordered_map sınıfından](../standard-library/unordered-map-class.md)farklı olarak, türünde bir nesne, `unordered_multimap` `key_eq()(X, Y)` denetlenen sıranın herhangi iki öğesi için her zaman false olduğundan emin değildir. (Anahtarlarının benzersiz olması gerekmez.)

Nesne ayrıca, demet başına istenen ortalama öğe sayısını belirten en yüksek yük faktörünü depolar. Bir öğe eklemek [unordered_multimap:: load_factor](#load_factor) `()` en fazla yük faktörünü aşmasına neden olursa kapsayıcı, demetlerin sayısını artırır ve gerekirse karma tabloyu yeniden oluşturur.

Denetlenen dizideki öğelerin gerçek sırası karma işleve, karşılaştırma işlevine, ekleme sırasına, en yüksek yük faktörüne ve geçerli demet sayısına bağlıdır. Denetlenen dizideki öğelerin sırasını genelde tahmin edemezsiniz. Ancak, eşdeğer sıralamaya sahip öğelerin herhangi bir alt kümesinin her zaman denetlenen dizide bitişik olduğundan emin olabilirsiniz.

Nesnesi, [unordered_multimap:: allocator_type](#allocator_type)türünde depolanan bir ayırıcı nesne aracılığıyla denetlediği sıra için depolamayı ayırır ve boşaltır. Böyle bir ayırıcı nesne, türünde bir nesne ile aynı dış arabirime sahip olmalıdır `allocator` . Depolanan ayırıcı nesnenin kapsayıcı nesne atandığında kopyalanmayacağını unutmayın.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<unordered_map>

**Ad alanı:** std

## <a name="unordered_multimapallocator_type"></a><a name="allocator_type"></a> unordered_multimap:: allocator_type

Depolamayı yönetmek için bir ayırıcı türü.

```cpp
typedef Alloc allocator_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, şablon parametresi için bir eş anlamlı `Alloc` .

### <a name="example"></a>Örnek

```cpp
// std__unordered_map__unordered_multimap_allocator_type.cpp
// compile with: /EHsc
#include <unordered_map>
#include <iostream>

typedef std::unordered_multimap<char, int> Mymap;
typedef std::allocator<std::pair<const char, int> > Myalloc;
int main()
    {
    Mymap c1;

    Mymap::allocator_type al = c1.get_allocator();
    std::cout << "al == std::allocator() is "
        << std::boolalpha << (al == Myalloc()) << std::endl;

    return (0);
    }
```

```Output
al == std::allocator() is true
```

## <a name="unordered_multimapbegin"></a><a name="begin"></a> unordered_multimap:: Begin

Denetlenen sıranın veya bir demetini başlangıcını belirtir.

```cpp
iterator begin();

const_iterator begin() const;

local_iterator begin(size_type nbucket);

const_local_iterator begin(size_type nbucket) const;
```

### <a name="parameters"></a>Parametreler

*nbucket*\
Demet numarası.

### <a name="remarks"></a>Açıklamalar

İlk iki üye işlevi, dizinin ilk öğesine (veya boş bir sıranın sonuna kadar) işaret eden bir ileri yineleyici döndürür. Son iki üye işlevi, demet *nbucket* 'un ilk öğesini işaret eden bir ileri yineleyici döndürür (veya boş bir demet sonunun ötesinde).

### <a name="example"></a>Örnek

```cpp
// std__unordered_map__unordered_multimap_begin.cpp
// compile with: /EHsc
#include <unordered_map>
#include <iostream>

typedef std::unordered_multimap<char, int> Mymap;
int main()
    {
    Mymap c1;

    c1.insert(Mymap::value_type('a', 1));
    c1.insert(Mymap::value_type('b', 2));
    c1.insert(Mymap::value_type('c', 3));

// display contents " [c 3] [b 2] [a 1]"
    for (Mymap::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << " [" << it->first << ", " << it->second << "]";
    std::cout << std::endl;

// inspect first two items " [c 3] [b 2]"
    Mymap::iterator it2 = c1.begin();
    std::cout << " [" << it2->first << ", " << it2->second << "]";
    ++it2;
    std::cout << " [" << it2->first << ", " << it2->second << "]";
    std::cout << std::endl;

// inspect bucket containing 'a'
    Mymap::const_local_iterator lit = c1.begin(c1.bucket('a'));
    std::cout << " [" << lit->first << ", " << lit->second << "]";

    return (0);
    }
```

```Output
[c, 3] [b, 2] [a, 1]
[c, 3] [b, 2]
[a, 1]
```

## <a name="unordered_multimapbucket"></a><a name="bucket"></a> unordered_multimap:: Bucket

Bir anahtar değeri için demet numarasını alır.

```cpp
size_type bucket(const Key& keyval) const;
```

### <a name="parameters"></a>Parametreler

*keyval*\
Eşlenecek anahtar değer.

### <a name="remarks"></a>Açıklamalar

Üye işlevi, anahtar değeri *keyval*'e Şu anda karşılık gelen demet numarasını döndürür.

### <a name="example"></a>Örnek

```cpp
// std__unordered_map__unordered_multimap_bucket.cpp
// compile with: /EHsc
#include <unordered_map>
#include <iostream>

typedef std::unordered_multimap<char, int> Mymap;
int main()
    {
    Mymap c1;

    c1.insert(Mymap::value_type('a', 1));
    c1.insert(Mymap::value_type('b', 2));
    c1.insert(Mymap::value_type('c', 3));

// display contents " [c 3] [b 2] [a 1]"
    for (Mymap::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << " [" << it->first << ", " << it->second << "]";
    std::cout << std::endl;

// display buckets for keys
    Mymap::size_type bs = c1.bucket('a');
    std::cout << "bucket('a') == " << bs << std::endl;
    std::cout << "bucket_size(" << bs << ") == " << c1.bucket_size(bs)
        << std::endl;

    return (0);
    }
```

```Output
[c, 3] [b, 2] [a, 1]
bucket('a') == 7
bucket_size(7) == 1
```

## <a name="unordered_multimapbucket_count"></a><a name="bucket_count"></a> unordered_multimap:: bucket_count

Demet sayısını alır.

```cpp
size_type bucket_count() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, geçerli demet sayısını döndürür.

### <a name="example"></a>Örnek

```cpp
// std__unordered_map__unordered_multimap_bucket_count.cpp
// compile with: /EHsc
#include <unordered_map>
#include <iostream>

typedef std::unordered_multimap<char, int> Mymap;
int main()
    {
    Mymap c1;

    c1.insert(Mymap::value_type('a', 1));
    c1.insert(Mymap::value_type('b', 2));
    c1.insert(Mymap::value_type('c', 3));

// display contents " [c 3] [b 2] [a 1]"
    for (Mymap::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << " [" << it->first << ", " << it->second << "]";
    std::cout << std::endl;

// inspect current parameters
    std::cout << "bucket_count() == " << c1.bucket_count() << std::endl;
    std::cout << "load_factor() == " << c1.load_factor() << std::endl;
    std::cout << "max_bucket_count() == "
        << c1.max_bucket_count() << std::endl;
    std::cout << "max_load_factor() == "
        << c1.max_load_factor() << std::endl;
    std::cout << std::endl;

// change max_load_factor and redisplay
    c1.max_load_factor(0.10f);
    std::cout << "bucket_count() == " << c1.bucket_count() << std::endl;
    std::cout << "load_factor() == " << c1.load_factor() << std::endl;
    std::cout << "max_bucket_count() == "
        << c1.max_bucket_count() << std::endl;
    std::cout << "max_load_factor() == "
        << c1.max_load_factor() << std::endl;
    std::cout << std::endl;

// rehash and redisplay
    c1.rehash(100);
    std::cout << "bucket_count() == " << c1.bucket_count() << std::endl;
    std::cout << "load_factor() == " << c1.load_factor() << std::endl;
    std::cout << "max_bucket_count() == "
        << c1.max_bucket_count() << std::endl;
    std::cout << "max_load_factor() == "
        << c1.max_load_factor() << std::endl;
    std::cout << std::endl;

    return (0);
    }
```

```Output
[c, 3] [b, 2] [a, 1]
bucket_count() == 8
load_factor() == 0.375
max_bucket_count() == 8
max_load_factor() == 4

bucket_count() == 8
load_factor() == 0.375
max_bucket_count() == 8
max_load_factor() == 0.1

bucket_count() == 128
load_factor() == 0.0234375
max_bucket_count() == 128
max_load_factor() == 0.1
```

## <a name="unordered_multimapbucket_size"></a><a name="bucket_size"></a> unordered_multimap:: bucket_size

Bir demet boyutunu alır

```cpp
size_type bucket_size(size_type nbucket) const;
```

### <a name="parameters"></a>Parametreler

*nbucket*\
Demet numarası.

### <a name="remarks"></a>Açıklamalar

Üye işlevleri, *nbucket*demet sayısı boyutunu döndürür.

### <a name="example"></a>Örnek

```cpp
// std__unordered_map__unordered_multimap_bucket_size.cpp
// compile with: /EHsc
#include <unordered_map>
#include <iostream>

typedef std::unordered_multimap<char, int> Mymap;
int main()
    {
    Mymap c1;

    c1.insert(Mymap::value_type('a', 1));
    c1.insert(Mymap::value_type('b', 2));
    c1.insert(Mymap::value_type('c', 3));

// display contents " [c 3] [b 2] [a 1]"
    for (Mymap::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << " [" << it->first << ", " << it->second << "]";
    std::cout << std::endl;

// display buckets for keys
    Mymap::size_type bs = c1.bucket('a');
    std::cout << "bucket('a') == " << bs << std::endl;
    std::cout << "bucket_size(" << bs << ") == " << c1.bucket_size(bs)
        << std::endl;

    return (0);
    }
```

```Output
[c, 3] [b, 2] [a, 1]
bucket('a') == 7
bucket_size(7) == 1
```

## <a name="unordered_multimapcbegin"></a><a name="cbegin"></a> unordered_multimap:: cbegin

**`const`** Aralıktaki ilk öğeyi ele alan bir yineleyici döndürür.

```cpp
const_iterator cbegin() const;
```

### <a name="return-value"></a>Dönüş Değeri

**`const`** Aralığın ilk öğesine veya boş bir aralığın sonundaki konuma (boş bir Aralık için) işaret eden ileri erişimli bir yineleyici `cbegin() == cend()` .

### <a name="remarks"></a>Açıklamalar

Dönüş değeri ile `cbegin` , aralıktaki öğeler değiştirilemez.

`begin()`Dönüş değerinin olduğunu garantilemek için üye işlevin yerine bu üye işlevi kullanabilirsiniz `const_iterator` . Genellikle, aşağıdaki örnekte gösterildiği gibi [Otomatik](../cpp/auto-cpp.md) tür kesintisi anahtar sözcüğüyle birlikte kullanılır. Örnekte, ve ' ı `Container` destekleyen herhangi bir türde değiştirilebilir (olmayan) bir kapsayıcı olarak göz önünde bulundurun **`const`** `begin()` `cbegin()` .

```cpp
auto i1 = Container.begin();
// i1 is Container<T>::iterator
auto i2 = Container.cbegin();

// i2 is Container<T>::const_iterator
```

## <a name="unordered_multimapcend"></a><a name="cend"></a> unordered_multimap:: cend

**`const`** Bir aralıktaki son öğenin ötesinde konumu ele alan bir yineleyici döndürür.

```cpp
const_iterator cend() const;
```

### <a name="return-value"></a>Dönüş Değeri

**`const`** Yalnızca aralığın sonunu işaret eden ileri erişimli bir yineleyici.

### <a name="remarks"></a>Açıklamalar

`cend` , bir yineleyicinin aralığın sonunu geçtiğini test etmek için kullanılır.

`end()`Dönüş değerinin olduğunu garantilemek için üye işlevin yerine bu üye işlevi kullanabilirsiniz `const_iterator` . Genellikle, aşağıdaki örnekte gösterildiği gibi [Otomatik](../cpp/auto-cpp.md) tür kesintisi anahtar sözcüğüyle birlikte kullanılır. Örnekte, ve ' ı `Container` destekleyen herhangi bir türde değiştirilebilir (olmayan) bir kapsayıcı olarak göz önünde bulundurun **`const`** `end()` `cend()` .

```cpp
auto i1 = Container.end();
// i1 is Container<T>::iterator
auto i2 = Container.cend();

// i2 is Container<T>::const_iterator
```

Tarafından döndürülen değer `cend` başvurulmamalıdır.

## <a name="unordered_multimapclear"></a><a name="clear"></a> unordered_multimap:: Clear

Tüm öğeleri kaldırır.

```cpp
void clear();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi [unordered_multimap:: Erase](#erase) `(` [unordered_multimap:: BEGIN](#begin) `(),` [unordered_multimap:: End](#end)' i çağırır `())` .

### <a name="example"></a>Örnek

```cpp
// std__unordered_map__unordered_multimap_clear.cpp
// compile with: /EHsc
#include <unordered_map>
#include <iostream>

typedef std::unordered_multimap<char, int> Mymap;
int main()
    {
    Mymap c1;

    c1.insert(Mymap::value_type('a', 1));
    c1.insert(Mymap::value_type('b', 2));
    c1.insert(Mymap::value_type('c', 3));

// display contents " [c 3] [b 2] [a 1]"
    for (Mymap::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << " [" << it->first << ", " << it->second << "]";
    std::cout << std::endl;

// clear the container and reinspect
    c1.clear();
    std::cout << "size == " << c1.size() << std::endl;
    std::cout << "empty() == " << std::boolalpha << c1.empty() << std::endl;
    std::cout << std::endl;

    c1.insert(Mymap::value_type('d', 4));
    c1.insert(Mymap::value_type('e', 5));

// display contents " [e 5] [d 4]"
    for (Mymap::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << " [" << it->first << ", " << it->second << "]";
    std::cout << std::endl;

    std::cout << "size == " << c1.size() << std::endl;
    std::cout << "empty() == " << std::boolalpha << c1.empty() << std::endl;

    return (0);
    }
```

```Output
[c, 3] [b, 2] [a, 1]
size == 0
empty() == true

[e, 5] [d, 4]
size == 2
empty() == false
```

## <a name="unordered_multimapconst_iterator"></a><a name="const_iterator"></a> unordered_multimap:: const_iterator

Denetlenen dizi için bir sabit yineleyici türü.

```cpp
typedef T1 const_iterator;
```

### <a name="remarks"></a>Açıklamalar

Türü, denetimli sıra için sabit bir ileri Yineleyici işlevi görebilecek bir nesneyi tanımlar. Burada uygulama tanımlı tür için bir eş anlamlı olarak açıklanmaktadır `T1` .

### <a name="example"></a>Örnek

```cpp
// std__unordered_map__unordered_multimap_const_iterator.cpp
// compile with: /EHsc
#include <unordered_map>
#include <iostream>

typedef std::unordered_multimap<char, int> Mymap;
int main()
    {
    Mymap c1;

    c1.insert(Mymap::value_type('a', 1));
    c1.insert(Mymap::value_type('b', 2));
    c1.insert(Mymap::value_type('c', 3));

// display contents " [c 3] [b 2] [a 1]"
    for (Mymap::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << " [" << it->first << ", " << it->second << "]";
    std::cout << std::endl;

    return (0);
    }
```

```Output
[c, 3] [b, 2] [a, 1]
```

## <a name="unordered_multimapconst_local_iterator"></a><a name="const_local_iterator"></a> unordered_multimap:: const_local_iterator

Denetlenen dizi için bir sabit demet yineleyici türü.

```cpp
typedef T5 const_local_iterator;
```

### <a name="remarks"></a>Açıklamalar

Türü, bir demet için sabit bir ileri Yineleyici işlevi görebilecek bir nesneyi tanımlar. Burada uygulama tanımlı tür için bir eş anlamlı olarak açıklanmaktadır `T5` .

### <a name="example"></a>Örnek

```cpp
// std__unordered_map__unordered_multimap_const_local_iterator.cpp
// compile with: /EHsc
#include <unordered_map>
#include <iostream>

typedef std::unordered_multimap<char, int> Mymap;
int main()
    {
    Mymap c1;

    c1.insert(Mymap::value_type('a', 1));
    c1.insert(Mymap::value_type('b', 2));
    c1.insert(Mymap::value_type('c', 3));

// display contents " [c 3] [b 2] [a 1]"
    for (Mymap::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << " [" << it->first << ", " << it->second << "]";
    std::cout << std::endl;

// inspect bucket containing 'a'
    Mymap::const_local_iterator lit = c1.begin(c1.bucket('a'));
    std::cout << " [" << lit->first << ", " << lit->second << "]";

    return (0);
    }
```

```Output
[c, 3] [b, 2] [a, 1]
[a, 1]
```

## <a name="unordered_multimapconst_pointer"></a><a name="const_pointer"></a> unordered_multimap:: const_pointer

Bir öğe için sabit bir işaretçi türü.

```cpp
typedef Alloc::const_pointer const_pointer;
```

### <a name="remarks"></a>Açıklamalar

Türü, denetlenen dizinin bir öğesi için sabit bir işaretçi olarak kullanılabilecek bir nesneyi tanımlar.

### <a name="example"></a>Örnek

```cpp
// std__unordered_map__unordered_multimap_const_pointer.cpp
// compile with: /EHsc
#include <unordered_map>
#include <iostream>

typedef std::unordered_multimap<char, int> Mymap;
int main()
    {
    Mymap c1;

    c1.insert(Mymap::value_type('a', 1));
    c1.insert(Mymap::value_type('b', 2));
    c1.insert(Mymap::value_type('c', 3));

// display contents " [c 3] [b 2] [a 1]"
    for (Mymap::iterator it = c1.begin();
        it != c1.end(); ++it)
        {
        Mymap::const_pointer p = &*it;
        std::cout << " [" << p->first << ", " << p->second << "]";
        }
    std::cout << std::endl;

    return (0);
    }
```

```Output
[c, 3] [b, 2] [a, 1]
```

## <a name="unordered_multimapconst_reference"></a><a name="const_reference"></a> unordered_multimap:: const_reference

Bir öğe için sabit bir başvuru türü.

```cpp
typedef Alloc::const_reference const_reference;
```

### <a name="remarks"></a>Açıklamalar

Türü, denetlenen dizinin bir öğesine sabit başvuru olarak işlev yapabilecek bir nesneyi tanımlar.

### <a name="example"></a>Örnek

```cpp
// std__unordered_map__unordered_multimap_const_reference.cpp
// compile with: /EHsc
#include <unordered_map>
#include <iostream>

typedef std::unordered_multimap<char, int> Mymap;
int main()
    {
    Mymap c1;

    c1.insert(Mymap::value_type('a', 1));
    c1.insert(Mymap::value_type('b', 2));
    c1.insert(Mymap::value_type('c', 3));

// display contents " [c 3] [b 2] [a 1]"
    for (Mymap::iterator it = c1.begin();
        it != c1.end(); ++it)
        {
        Mymap::const_reference ref = *it;
        std::cout << " [" << ref.first << ", " << ref.second << "]";
        }
    std::cout << std::endl;

    return (0);
    }
```

```Output
[c, 3] [b, 2] [a, 1]
```

## <a name="unordered_multimapcontains"></a><a name="contains"></a> unordered_multimap:: Contains

İçinde belirtilen anahtara sahip bir öğe olup olmadığını denetler `unordered_multimap` .

```cpp
bool contains(const Key& key) const;
template<class K> bool contains(const K& key) const;
```

### <a name="parameters"></a>Parametreler

*Ek*\
Anahtarın türü.

*anahtar*\
Aranacak öğenin anahtar değeri.

### <a name="return-value"></a>Dönüş Değeri

`true` öğe kapsayıcıda bulunursa; `false` Aksi takdirde.

### <a name="remarks"></a>Açıklamalar

`contains()` C++ 20 ' de yenidir. Bunu kullanmak için [/std: c + + en son](../build/reference/std-specify-language-standard-version.md) derleyici seçeneğini belirtin.

`template<class K> bool contains(const K& key) const` yalnızca, saydam ise aşırı yükleme çözümüne katılır `key_compare` .

### <a name="example"></a>Örnek

```cpp
// Requires /std:c++latest
#include <unordered_map>
#include <iostream>

int main()
{
    std::unordered_multimap<int, bool> theUnorderedMultimap = {{0, false}, {1,true}};

    std::cout << std::boolalpha; // so booleans show as 'true' or 'false'
    std::cout << theUnorderedMultimap.contains(1) << '\n';
    std::cout << theUnorderedMultimap.contains(2) << '\n';

    return 0;
}
```

```Output
true
false
```

## <a name="unordered_multimapcount"></a><a name="count"></a> unordered_multimap:: Count

Belirtilen bir anahtar ile eşleşen öğe sayısını bulur.

```cpp
size_type count(const Key& keyval) const;
```

### <a name="parameters"></a>Parametreler

*keyval*\
Aranacak anahtar değer.

### <a name="remarks"></a>Açıklamalar

Üye işlevi [unordered_multimap:: equal_range](#equal_range)ile ayrılmış aralıktaki öğe sayısını döndürür `(keyval)` .

### <a name="example"></a>Örnek

```cpp
// std__unordered_map__unordered_multimap_count.cpp
// compile with: /EHsc
#include <unordered_map>
#include <iostream>

typedef std::unordered_multimap<char, int> Mymap;
int main()
    {
    Mymap c1;

    c1.insert(Mymap::value_type('a', 1));
    c1.insert(Mymap::value_type('b', 2));
    c1.insert(Mymap::value_type('c', 3));

// display contents " [c 3] [b 2] [a 1]"
    for (Mymap::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << " [" << it->first << ", " << it->second << "]";
    std::cout << std::endl;

    std::cout << "count('A') == " << c1.count('A') << std::endl;
    std::cout << "count('b') == " << c1.count('b') << std::endl;
    std::cout << "count('C') == " << c1.count('C') << std::endl;

    return (0);
    }
```

```Output
[c, 3] [b, 2] [a, 1]
count('A') == 0
count('b') == 1
count('C') == 0
```

## <a name="unordered_multimapdifference_type"></a><a name="difference_type"></a> unordered_multimap::d ifference_type

İki öğe arasındaki işaretli mesafenin türü.

```cpp
typedef T3 difference_type;
```

### <a name="remarks"></a>Açıklamalar

İmzalanan tamsayı türü, denetlenen dizideki herhangi iki öğenin adresleri arasındaki farkı temsil eden bir nesneyi tanımlar. Burada uygulama tanımlı tür için bir eş anlamlı olarak açıklanmaktadır `T3` .

### <a name="example"></a>Örnek

```cpp
// std__unordered_map__unordered_multimap_difference_type.cpp
// compile with: /EHsc
#include <unordered_map>
#include <iostream>

typedef std::unordered_multimap<char, int> Mymap;
int main()
    {
    Mymap c1;

    c1.insert(Mymap::value_type('a', 1));
    c1.insert(Mymap::value_type('b', 2));
    c1.insert(Mymap::value_type('c', 3));

// display contents " [c 3] [b 2] [a 1]"
    for (Mymap::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << " [" << it->first << ", " << it->second << "]";
    std::cout << std::endl;

// compute positive difference
    Mymap::difference_type diff = 0;
    for (Mymap::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        ++diff;
    std::cout << "end()-begin() == " << diff << std::endl;

// compute negative difference
    diff = 0;
    for (Mymap::const_iterator it = c1.end();
        it != c1.begin(); --it)
        --diff;
    std::cout << "begin()-end() == " << diff << std::endl;

    return (0);
    }
```

```Output
[c, 3] [b, 2] [a, 1]
end()-begin() == 3
begin()-end() == -3
```

## <a name="unordered_multimapemplace"></a><a name="emplace"></a> unordered_multimap:: emplace

Yerinde oluşturulmuş bir öğe ekler (kopyalama veya taşıma işlemleri yapılmaz), yerleştirme ipucuyla birlikte.

```cpp
template <class... Args>
iterator emplace(Args&&... args);
```

### <a name="parameters"></a>Parametreler

*args*\
İçine eklenecek bir öğe oluşturmak için iletilen bağımsız değişkenler `unordered_multimap` .

### <a name="return-value"></a>Dönüş Değeri

Yeni eklenmekte olan öğe için bir yineleyici.

### <a name="remarks"></a>Açıklamalar

Bu işlev tarafından kapsayıcı öğelerine yönelik başvuru geçersiz kılınmamıştır, ancak kapsayıcı için tüm yineleyiciler geçersiz kılınabilir.

Bir öğe [value_type](../standard-library/map-class.md#value_type) bir çifdir, böylece bir öğe değeri, ilk bileşeni anahtar değerine eşit olan ve ikinci bileşen öğenin veri değerine eşit olan bir sıralı çift olacaktır.

Ekleme sırasında, bir özel durum oluşturulursa, ancak kapsayıcının karma işlevinde gerçekleşmezse kapsayıcı değiştirilmez. Karma işlevde özel durum oluşturulursa, sonuç tanımsızdır.

Kod örneği için bkz. [multimap:: emplace](../standard-library/multimap-class.md#emplace).

## <a name="unordered_multimapemplace_hint"></a><a name="emplace_hint"></a> unordered_multimap:: emplace_hint

Yerinde oluşturulmuş bir öğe ekler (kopyalama veya taşıma işlemleri yapılmaz), yerleştirme ipucuyla birlikte.

```cpp
template <class... Args>
iterator emplace_hint(
    const_iterator where,
    Args&&... args);
```

### <a name="parameters"></a>Parametreler

*args*\
Sırasız olarak eklenecek bir öğe oluşturmak için iletilen bağımsız değişkenler.

*olmadığı*\
Doğru ekleme noktasını aramaya başlamak için yer hakkında bir ipucu.

### <a name="return-value"></a>Dönüş Değeri

Yeni eklenmekte olan öğe için bir yineleyici.

### <a name="remarks"></a>Açıklamalar

Bu işlev tarafından kapsayıcı öğelerine yönelik başvuru geçersiz kılınmamıştır, ancak kapsayıcı için tüm yineleyiciler geçersiz kılınabilir.

Ekleme sırasında, bir özel durum oluşturulursa, ancak kapsayıcının karma işlevinde gerçekleşmezse kapsayıcı değiştirilmez. Karma işlevde özel durum oluşturulursa, sonuç tanımsızdır.

Bir öğe [value_type](../standard-library/map-class.md#value_type) bir çifdir, böylece bir öğe değeri, ilk bileşeni anahtar değerine eşit olan ve ikinci bileşen öğenin veri değerine eşit olan bir sıralı çift olacaktır.

Kod örneği için bkz. [map:: emplace_hint](../standard-library/map-class.md#emplace_hint).

## <a name="unordered_multimapempty"></a><a name="empty"></a> unordered_multimap:: boş

Bir öğe olup olmadığını sınar.

```cpp
bool empty() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi boş bir denetlenen dizi için true döndürür.

### <a name="example"></a>Örnek

```cpp
// std__unordered_map__unordered_multimap_empty.cpp
// compile with: /EHsc
#include <unordered_map>
#include <iostream>

typedef std::unordered_multimap<char, int> Mymap;
int main()
    {
    Mymap c1;

    c1.insert(Mymap::value_type('a', 1));
    c1.insert(Mymap::value_type('b', 2));
    c1.insert(Mymap::value_type('c', 3));

// display contents " [c 3] [b 2] [a 1]"
    for (Mymap::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << " [" << it->first << ", " << it->second << "]";
    std::cout << std::endl;

// clear the container and reinspect
    c1.clear();
    std::cout << "size == " << c1.size() << std::endl;
    std::cout << "empty() == " << std::boolalpha << c1.empty() << std::endl;
    std::cout << std::endl;

    c1.insert(Mymap::value_type('d', 4));
    c1.insert(Mymap::value_type('e', 5));

// display contents " [e 5] [d 4]"
    for (Mymap::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << " [" << it->first << ", " << it->second << "]";
    std::cout << std::endl;

    std::cout << "size == " << c1.size() << std::endl;
    std::cout << "empty() == " << std::boolalpha << c1.empty() << std::endl;

    return (0);
    }
```

```Output
[c, 3] [b, 2] [a, 1]
size == 0
empty() == true

[e, 5] [d, 4]
size == 2
empty() == false
```

## <a name="unordered_multimapend"></a><a name="end"></a> unordered_multimap:: End

Denetlenen dizinin bitişini belirtir.

```cpp
iterator end();

const_iterator end() const;

local_iterator end(size_type nbucket);

const_local_iterator end(size_type nbucket) const;
```

### <a name="parameters"></a>Parametreler

*nbucket*\
Demet numarası.

### <a name="remarks"></a>Açıklamalar

İlk iki üye işlevi, dizinin sonunun hemen ötesinde işaret eden bir ileri yineleyici döndürür. Son iki üye işlevi, demet *nbucket*'un sonuna işaret eden bir ileri yineleyici döndürür.

### <a name="example"></a>Örnek

```cpp
// std__unordered_map__unordered_multimap_end.cpp
// compile with: /EHsc
#include <unordered_map>
#include <iostream>

typedef std::unordered_multimap<char, int> Mymap;
int main()
    {
    Mymap c1;

    c1.insert(Mymap::value_type('a', 1));
    c1.insert(Mymap::value_type('b', 2));
    c1.insert(Mymap::value_type('c', 3));

// display contents " [c 3] [b 2] [a 1]"
    for (Mymap::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << " [" << it->first << ", " << it->second << "]";
    std::cout << std::endl;

// inspect last two items " [a 1] [b 2]"
    Mymap::iterator it2 = c1.end();
    --it2;
    std::cout << " [" << it2->first << ", " << it2->second << "]";
    --it2;
    std::cout << " [" << it2->first << ", " << it2->second << "]";
    std::cout << std::endl;

// inspect bucket containing 'a'
    Mymap::const_local_iterator lit = c1.end(c1.bucket('a'));
    --lit;
    std::cout << " [" << lit->first << ", " << lit->second << "]";

    return (0);
    }
```

```Output
[c, 3] [b, 2] [a, 1]
[a, 1] [b, 2]
[a, 1]
```

## <a name="unordered_multimapequal_range"></a><a name="equal_range"></a> unordered_multimap:: equal_range

Belirtilen bir anahtarla eşleşen aralığı bulur.

```cpp
std::pair<iterator, iterator>
    equal_range(const Key& keyval);

std::pair<const_iterator, const_iterator>
    equal_range(const Key& keyval) const;
```

### <a name="parameters"></a>Parametreler

*keyval*\
Aranacak anahtar değer.

### <a name="remarks"></a>Açıklamalar

Üye işlevi, `X` `[X.first, X.second)` yalnızca *keyval*ile eşdeğer sıralamaya sahip olan denetimli dizinin öğelerini sınırlandıran bir çift yineleyiciyi döndürür. Böyle bir öğe yoksa, her iki yineleyiciler de vardır `end()` .

### <a name="example"></a>Örnek

```cpp
// std__unordered_map__unordered_multimap_equal_range.cpp
// compile with: /EHsc
#include <unordered_map>
#include <iostream>

typedef std::unordered_multimap<char, int> Mymap;
int main()
    {
    Mymap c1;

    c1.insert(Mymap::value_type('a', 1));
    c1.insert(Mymap::value_type('b', 2));
    c1.insert(Mymap::value_type('c', 3));

// display contents " [c 3] [b 2] [a 1]"
    for (Mymap::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << " [" << it->first << ", " << it->second << "]";
    std::cout << std::endl;

// display results of failed search
    std::pair<Mymap::iterator, Mymap::iterator> pair1 =
        c1.equal_range('x');
    std::cout << "equal_range('x'):";
    for (; pair1.first != pair1.second; ++pair1.first)
        std::cout << " [" << pair1.first->first
            << ", " << pair1.first->second << "]";
    std::cout << std::endl;

// display results of successful search
    pair1 = c1.equal_range('b');
    std::cout << "equal_range('b'):";
    for (; pair1.first != pair1.second; ++pair1.first)
        std::cout << " [" << pair1.first->first
            << ", " << pair1.first->second << "]";
    std::cout << std::endl;

    return (0);
    }
```

```Output
[c, 3] [b, 2] [a, 1]
equal_range('x'):
equal_range('b'): [b, 2]
```

## <a name="unordered_multimaperase"></a><a name="erase"></a> unordered_multimap:: Erase

Belirtilen konumlardan bir unordered_multimap öğeyi veya öğe aralığını kaldırır veya belirtilen bir anahtarla eşleşen öğeleri kaldırır.

```cpp
iterator erase(
    const_iterator Where);

iterator erase(
    const_iterator First,
    const_iterator Last);

size_type erase(
    const key_type& Key);
```

### <a name="parameters"></a>Parametreler

*Olmadığı*\
Kaldırılacak öğenin konumu.

*Adı*\
Kaldırılacak ilk öğenin konumu.

*Soyadına*\
Kaldırılacak son öğenin hemen ötesinde konumlandır.

*Anahtar*\
Kaldırılacak öğelerin anahtar değeri.

### <a name="return-value"></a>Dönüş Değeri

İlk iki üye işlevi için, kaldırılan tüm öğelerin ötesinde kalan ilk öğeyi veya böyle bir öğe yoksa haritanın sonu olan bir öğeyi atayan çift yönlü bir yineleyici.

Üçüncü üye işlevi için, unordered_multimap kaldırılan öğelerin sayısını döndürür.

### <a name="remarks"></a>Açıklamalar

Kod örneği için bkz. [map:: Erase](../standard-library/map-class.md#erase).

## <a name="unordered_multimapfind"></a><a name="find"></a> unordered_multimap:: Find

Belirtilen bir anahtarla eşleşen bir öğeyi bulur.

```cpp
const_iterator find(const Key& keyval) const;
```

### <a name="parameters"></a>Parametreler

*keyval*\
Aranacak anahtar değer.

### <a name="remarks"></a>Açıklamalar

Üye işlevi [unordered_multimap:: equal_range](#equal_range)döndürür `(keyval).first` .

### <a name="example"></a>Örnek

```cpp
// std__unordered_map__unordered_multimap_find.cpp
// compile with: /EHsc
#include <unordered_map>
#include <iostream>

typedef std::unordered_multimap<char, int> Mymap;
int main()
    {
    Mymap c1;

    c1.insert(Mymap::value_type('a', 1));
    c1.insert(Mymap::value_type('b', 2));
    c1.insert(Mymap::value_type('c', 3));

// display contents " [c 3] [b 2] [a 1]"
    for (Mymap::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << " [" << it->first << ", " << it->second << "]";
    std::cout << std::endl;

// try to find and fail
    std::cout << "find('A') == "
        << std::boolalpha << (c1.find('A') != c1.end()) << std::endl;

// try to find and succeed
    Mymap::iterator it = c1.find('b');
    std::cout << "find('b') == "
        << std::boolalpha << (it != c1.end())
        << ": [" << it->first << ", " << it->second << "]" << std::endl;

    return (0);
    }
```

```Output
[c, 3] [b, 2] [a, 1]
find('A') == false
find('b') == true: [b, 2]
```

## <a name="unordered_multimapget_allocator"></a><a name="get_allocator"></a> unordered_multimap:: get_allocator

Depolanan ayırıcı nesnesini alır.

```cpp
Alloc get_allocator() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, depolanan ayırıcı nesnesini döndürür.

### <a name="example"></a>Örnek

```cpp
// std__unordered_map__unordered_multimap_get_allocator.cpp
// compile with: /EHsc
#include <unordered_map>
#include <iostream>

typedef std::unordered_multimap<char, int> Mymap;
typedef std::allocator<std::pair<const char, int> > Myalloc;
int main()
    {
    Mymap c1;

    Mymap::allocator_type al = c1.get_allocator();
    std::cout << "al == std::allocator() is "
        << std::boolalpha << (al == Myalloc()) << std::endl;

    return (0);
    }
```

```Output
al == std::allocator() is true
```

## <a name="unordered_multimaphash_function"></a><a name="hash"></a> unordered_multimap:: hash_function

Depolanan karma işlevi nesnesini alır.

```cpp
Hash hash_function() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, depolanan karma işlevi nesnesini döndürür.

### <a name="example"></a>Örnek

```cpp
// std__unordered_map__unordered_multimap_hash_function.cpp
// compile with: /EHsc
#include <unordered_map>
#include <iostream>

typedef std::unordered_multimap<char, int> Mymap;
int main()
    {
    Mymap c1;

    Mymap::hasher hfn = c1.hash_function();
    std::cout << "hfn('a') == " << hfn('a') << std::endl;
    std::cout << "hfn('b') == " << hfn('b') << std::endl;

    return (0);
    }
```

```Output
hfn('a') == 1630279
hfn('b') == 1647086
```

## <a name="unordered_multimaphasher"></a><a name="hasher"></a> unordered_multimap:: hasher

Karma işlevin türü.

```cpp
typedef Hash hasher;
```

### <a name="remarks"></a>Açıklamalar

Tür, şablon parametresi için bir eş anlamlı `Hash` .

### <a name="example"></a>Örnek

```cpp
// std__unordered_map__unordered_multimap_hasher.cpp
// compile with: /EHsc
#include <unordered_map>
#include <iostream>

typedef std::unordered_multimap<char, int> Mymap;
int main()
    {
    Mymap c1;

    Mymap::hasher hfn = c1.hash_function();
    std::cout << "hfn('a') == " << hfn('a') << std::endl;
    std::cout << "hfn('b') == " << hfn('b') << std::endl;

    return (0);
    }
```

```Output
hfn('a') == 1630279
hfn('b') == 1647086
```

## <a name="unordered_multimapinsert"></a><a name="insert"></a> unordered_multimap:: INSERT

Bir unordered_multimap öğe veya öğe aralığı ekler.

```cpp
// (1) single element
pair<iterator, bool> insert(
    const value_type& Val);

// (2) single element, perfect forwarded
template <class ValTy>
pair<iterator, bool>
insert(
    ValTy&& Val);

// (3) single element with hint
iterator insert(
    const_iterator Where,
    const value_type& Val);

// (4) single element, perfect forwarded, with hint
template <class ValTy>
iterator insert(
    const_iterator Where,
    ValTy&& Val);

// (5) range
template <class InputIterator>
void insert(
    InputIterator First,
    InputIterator Last);

// (6) initializer list
void insert(
    initializer_list<value_type>
IList);
```

### <a name="parameters"></a>Parametreler

*Acil*\
Unordered_multimap eklenecek öğenin değeri.

*Olmadığı*\
Doğru ekleme noktasını aramaya başlamak için yer.

*ValTy*\
Unordered_multimap, [value_type](../standard-library/map-class.md#value_type)bir öğesi oluşturmak için kullanabileceği bağımsız değişken türünü belirten şablon parametresi ve bağımsız değişken olarak *kusursuz iletme değeri* .

*Adı*\
Kopyalanacak ilk öğenin konumu.

*Soyadına*\
Kopyalanacak son öğenin hemen ötesinde konum.

*InputIterator*\
[Value_type](../standard-library/map-class.md#value_type) nesneleri oluşturmak için kullanılabilecek bir türün öğelerine işaret eden bir [giriş yineleyicisinin](../standard-library/input-iterator-tag-struct.md) gereksinimlerini karşılayan şablon işlevi bağımsız değişkeni.

*IList*\
Öğelerin kopyalanacağı [initializer_list](../standard-library/initializer-list.md) .

### <a name="return-value"></a>Dönüş Değeri

Tek öğeli-ekleme üye işlevleri, (1) ve (2), yeni öğenin unordered_multimap eklendiği konuma bir yineleyici döndürür.

Tek öğeli-ipucu üye işlevleri, (3) ve (4), yeni öğenin unordered_multimap eklendiği konuma işaret eden bir yineleyici döndürür.

### <a name="remarks"></a>Açıklamalar

Bu işlev tarafından geçersiz kılınan işaretçiler veya başvurular yok, ancak kapsayıcı için tüm yineleyiciler geçersiz kılınabilir.

Yalnızca bir öğenin eklenmesi sırasında, bir özel durum oluşturulursa, ancak kapsayıcının karma işlevinde gerçekleşmemişse kapsayıcının durumu değiştirilmez. Karma işlevde özel durum oluşturulursa, sonuç tanımsızdır. Birden çok öğenin eklenmesi sırasında, bir özel durum oluşturulursa, kapsayıcı belirtilmemiş ancak geçerli bir durumda bırakılır.

Kapsayıcının [value_type](../standard-library/map-class.md#value_type) , kapsayıcısına ait olan ve Map için olan bir typedef 'dir `map<K, V>::value_type` `pair<const K, V>` . Bir öğenin değeri, ilk bileşenin anahtar değere eşit olduğu ve ikinci bileşenin öğenin veri değerine eşit olduğu sıralı bir çiftidir.

Aralık üye işlevi (5), öğe değerlerinin dizisini aralıktaki bir yineleyici tarafından bahsedilen her öğeye karşılık gelen bir unordered_multimap ekler `[First, Last)` ; Bu nedenle, *Last* eklenmez. Kapsayıcı üye işlevi, `end()` kapsayıcıdaki son öğeden hemen sonra gelen konumu ifade eder; örneğin, ifade öğesine `m.insert(v.begin(), v.end());` tüm öğelerini ekler `v` `m` .

Başlatıcı listesi üye işlevi (6), öğeleri unordered_multimap kopyalamak için bir [initializer_list](../standard-library/initializer-list.md) kullanır.

Yerinde oluşturulmuş bir öğenin eklenmesi için — diğer bir deyişle, kopyalama veya taşıma işlemleri yapılmaz — [unordered_multimap:: emplace](#emplace) ve [unordered_multimap:: emplace_hint](#emplace_hint).

Kod örneği için bkz. [multimap:: insert](../standard-library/multiset-class.md#insert).

## <a name="unordered_multimapiterator"></a><a name="iterator"></a> unordered_multimap:: Yineleyici

Denetlenen dizi için bir yineleyici türü.

```cpp
typedef T0 iterator;
```

### <a name="remarks"></a>Açıklamalar

Türü, denetimli sıra için ileri Yineleyici olarak işlev görebilecek bir nesne tanımlar. Burada uygulama tanımlı tür için bir eş anlamlı olarak açıklanmaktadır `T0` .

### <a name="example"></a>Örnek

```cpp
// std__unordered_map__unordered_multimap_iterator.cpp
// compile with: /EHsc
#include <unordered_map>
#include <iostream>

typedef std::unordered_multimap<char, int> Mymap;
int main()
    {
    Mymap c1;

    c1.insert(Mymap::value_type('a', 1));
    c1.insert(Mymap::value_type('b', 2));
    c1.insert(Mymap::value_type('c', 3));

// display contents " [c 3] [b 2] [a 1]"
    for (Mymap::iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << " [" << it->first << ", " << it->second << "]";
    std::cout << std::endl;

    return (0);
    }
```

```Output
[c, 3] [b, 2] [a, 1]
```

## <a name="unordered_multimapkey_eq"></a><a name="key_eq"></a> unordered_multimap:: key_eq

Depolanan karşılaştırma işlevi nesnesini alır.

```cpp
Pred key_eq() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, saklı karşılaştırma işlevi nesnesini döndürür.

### <a name="example"></a>Örnek

```cpp
// std__unordered_map__unordered_multimap_key_eq.cpp
// compile with: /EHsc
#include <unordered_map>
#include <iostream>

typedef std::unordered_multimap<char, int> Mymap;
int main()
    {
    Mymap c1;

    Mymap::key_equal cmpfn = c1.key_eq();
    std::cout << "cmpfn('a', 'a') == "
        << std::boolalpha << cmpfn('a', 'a') << std::endl;
    std::cout << "cmpfn('a', 'b') == "
        << std::boolalpha << cmpfn('a', 'b') << std::endl;

    return (0);
    }
```

```Output
cmpfn('a', 'a') == true
cmpfn('a', 'b') == false
```

## <a name="unordered_multimapkey_equal"></a><a name="key_equal"></a> unordered_multimap:: key_equal

Karşılaştırma işlevinin türü.

```cpp
typedef Pred key_equal;
```

### <a name="remarks"></a>Açıklamalar

Tür, şablon parametresi için bir eş anlamlı `Pred` .

### <a name="example"></a>Örnek

```cpp
// std__unordered_map__unordered_multimap_key_equal.cpp
// compile with: /EHsc
#include <unordered_map>
#include <iostream>

typedef std::unordered_multimap<char, int> Mymap;
int main()
    {
    Mymap c1;

    Mymap::key_equal cmpfn = c1.key_eq();
    std::cout << "cmpfn('a', 'a') == "
        << std::boolalpha << cmpfn('a', 'a') << std::endl;
    std::cout << "cmpfn('a', 'b') == "
        << std::boolalpha << cmpfn('a', 'b') << std::endl;

    return (0);
    }
```

```Output
cmpfn('a', 'a') == true
cmpfn('a', 'b') == false
```

## <a name="unordered_multimapkey_type"></a><a name="key_type"></a> unordered_multimap:: key_type

Bir sıralama anahtarının türü.

```cpp
typedef Key key_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, şablon parametresi için bir eş anlamlı `Key` .

### <a name="example"></a>Örnek

```cpp
// std__unordered_map__unordered_multimap_key_type.cpp
// compile with: /EHsc
#include <unordered_map>
#include <iostream>

typedef std::unordered_multimap<char, int> Mymap;
int main()
    {
    Mymap c1;

    c1.insert(Mymap::value_type('a', 1));
    c1.insert(Mymap::value_type('b', 2));
    c1.insert(Mymap::value_type('c', 3));

// display contents " [c 3] [b 2] [a 1]"
    for (Mymap::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << " [" << it->first << ", " << it->second << "]";
    std::cout << std::endl;

// add a value and reinspect
    Mymap::key_type key = 'd';
    Mymap::mapped_type mapped = 4;
    Mymap::value_type val = Mymap::value_type(key, mapped);
    c1.insert(val);

    for (Mymap::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << " [" << it->first << ", " << it->second << "]";
    std::cout << std::endl;

    return (0);
    }
```

```Output
[c, 3] [b, 2] [a, 1]
[d, 4] [c, 3] [b, 2] [a, 1]
```

## <a name="unordered_multimapload_factor"></a><a name="load_factor"></a> unordered_multimap:: load_factor

Demet başına ortalama öğeyi sayar.

```cpp
float load_factor() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi `(float)` [unordered_multimap:: size](#size) `() / (float)` [unordered_multimap:: bucket_count](#bucket_count) `()` , demet başına düşen ortalama öğe sayısını döndürür.

### <a name="example"></a>Örnek

```cpp
// std__unordered_map__unordered_multimap_load_factor.cpp
// compile with: /EHsc
#include <unordered_map>
#include <iostream>

typedef std::unordered_multimap<char, int> Mymap;
int main()
    {
    Mymap c1;

    c1.insert(Mymap::value_type('a', 1));
    c1.insert(Mymap::value_type('b', 2));
    c1.insert(Mymap::value_type('c', 3));

// display contents " [c 3] [b 2] [a 1]"
    for (Mymap::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << " [" << it->first << ", " << it->second << "]";
    std::cout << std::endl;

// inspect current parameters
    std::cout << "bucket_count() == " << c1.bucket_count() << std::endl;
    std::cout << "load_factor() == " << c1.load_factor() << std::endl;
    std::cout << "max_bucket_count() == "
        << c1.max_bucket_count() << std::endl;
    std::cout << "max_load_factor() == "
        << c1.max_load_factor() << std::endl;
    std::cout << std::endl;

// change max_load_factor and redisplay
    c1.max_load_factor(0.10f);
    std::cout << "bucket_count() == " << c1.bucket_count() << std::endl;
    std::cout << "load_factor() == " << c1.load_factor() << std::endl;
    std::cout << "max_bucket_count() == "
        << c1.max_bucket_count() << std::endl;
    std::cout << "max_load_factor() == "
        << c1.max_load_factor() << std::endl;
    std::cout << std::endl;

// rehash and redisplay
    c1.rehash(100);
    std::cout << "bucket_count() == " << c1.bucket_count() << std::endl;
    std::cout << "load_factor() == " << c1.load_factor() << std::endl;
    std::cout << "max_bucket_count() == "
        << c1.max_bucket_count() << std::endl;
    std::cout << "max_load_factor() == "
        << c1.max_load_factor() << std::endl;
    std::cout << std::endl;

    return (0);
    }
```

## <a name="unordered_multimaplocal_iterator"></a><a name="local_iterator"></a> unordered_multimap:: local_iterator

Demet yineleyicisinin türü.

```cpp
typedef T4 local_iterator;
```

### <a name="remarks"></a>Açıklamalar

Türü, bir demet için ileriye doğru Yineleyici işlevi görebilecek bir nesneyi tanımlar. Burada uygulama tanımlı tür için bir eş anlamlı olarak açıklanmaktadır `T4` .

### <a name="example"></a>Örnek

```cpp
// std__unordered_map__unordered_multimap_local_iterator.cpp
// compile with: /EHsc
#include <unordered_map>
#include <iostream>

typedef std::unordered_multimap<char, int> Mymap;
int main()
    {
    Mymap c1;

    c1.insert(Mymap::value_type('a', 1));
    c1.insert(Mymap::value_type('b', 2));
    c1.insert(Mymap::value_type('c', 3));

// display contents " [c 3] [b 2] [a 1]"
    for (Mymap::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << " [" << it->first << ", " << it->second << "]";
    std::cout << std::endl;

// inspect bucket containing 'a'
    Mymap::local_iterator lit = c1.begin(c1.bucket('a'));
    std::cout << " [" << lit->first << ", " << lit->second << "]";

    return (0);
    }
```

```Output
[c, 3] [b, 2] [a, 1]
[a, 1]
```

## <a name="unordered_multimapmapped_type"></a><a name="mapped_type"></a> unordered_multimap:: mapped_type

Her bir anahtar ile ilişkili bir eşlenen değer türü.

```cpp
typedef Ty mapped_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, şablon parametresi için bir eş anlamlı `Ty` .

### <a name="example"></a>Örnek

```cpp
// std__unordered_map__unordered_multimap_mapped_type.cpp
// compile with: /EHsc
#include <unordered_map>
#include <iostream>

typedef std::unordered_multimap<char, int> Mymap;
int main()
    {
    Mymap c1;

    c1.insert(Mymap::value_type('a', 1));
    c1.insert(Mymap::value_type('b', 2));
    c1.insert(Mymap::value_type('c', 3));

// display contents " [c 3] [b 2] [a 1]"
    for (Mymap::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << " [" << it->first << ", " << it->second << "]";
    std::cout << std::endl;

// add a value and reinspect
    Mymap::key_type key = 'd';
    Mymap::mapped_type mapped = 4;
    Mymap::value_type val = Mymap::value_type(key, mapped);
    c1.insert(val);

    for (Mymap::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << " [" << it->first << ", " << it->second << "]";
    std::cout << std::endl;

    return (0);
    }
```

```Output
[c, 3] [b, 2] [a, 1]
[d, 4] [c, 3] [b, 2] [a, 1]
```

## <a name="unordered_multimapmax_bucket_count"></a><a name="max_bucket_count"></a> unordered_multimap:: max_bucket_count

En yüksek demet sayısını alır.

```cpp
size_type max_bucket_count() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, şu anda izin verilen en fazla demet sayısını döndürür.

### <a name="example"></a>Örnek

```cpp
// std__unordered_map__unordered_multimap_max_bucket_count.cpp
// compile with: /EHsc
#include <unordered_map>
#include <iostream>

typedef std::unordered_multimap<char, int> Mymap;
int main()
    {
    Mymap c1;

    c1.insert(Mymap::value_type('a', 1));
    c1.insert(Mymap::value_type('b', 2));
    c1.insert(Mymap::value_type('c', 3));

// display contents " [c 3] [b 2] [a 1]"
    for (Mymap::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << " [" << it->first << ", " << it->second << "]";
    std::cout << std::endl;

// inspect current parameters
    std::cout << "bucket_count() == " << c1.bucket_count() << std::endl;
    std::cout << "load_factor() == " << c1.load_factor() << std::endl;
    std::cout << "max_bucket_count() == "
        << c1.max_bucket_count() << std::endl;
    std::cout << "max_load_factor() == "
        << c1.max_load_factor() << std::endl;
    std::cout << std::endl;

// change max_load_factor and redisplay
    c1.max_load_factor(0.10f);
    std::cout << "bucket_count() == " << c1.bucket_count() << std::endl;
    std::cout << "load_factor() == " << c1.load_factor() << std::endl;
    std::cout << "max_bucket_count() == "
        << c1.max_bucket_count() << std::endl;
    std::cout << "max_load_factor() == "
        << c1.max_load_factor() << std::endl;
    std::cout << std::endl;

// rehash and redisplay
    c1.rehash(100);
    std::cout << "bucket_count() == " << c1.bucket_count() << std::endl;
    std::cout << "load_factor() == " << c1.load_factor() << std::endl;
    std::cout << "max_bucket_count() == "
        << c1.max_bucket_count() << std::endl;
    std::cout << "max_load_factor() == "
        << c1.max_load_factor() << std::endl;
    std::cout << std::endl;

    return (0);
    }
```

```Output
[c, 3] [b, 2] [a, 1]
bucket_count() == 8
load_factor() == 0.375
max_bucket_count() == 8
max_load_factor() == 4

bucket_count() == 8
load_factor() == 0.375
max_bucket_count() == 8
max_load_factor() == 0.1

bucket_count() == 128
load_factor() == 0.0234375
max_bucket_count() == 128
max_load_factor() == 0.1
```

## <a name="unordered_multimapmax_load_factor"></a><a name="max_load_factor"></a> unordered_multimap:: max_load_factor

Demet başına en yüksek öğe sayısını alır veya ayarlar.

```cpp
float max_load_factor() const;

void max_load_factor(float factor);
```

### <a name="parameters"></a>Parametreler

*çarpan*\
Yeni en yüksek yük faktörü.

### <a name="remarks"></a>Açıklamalar

İlk üye işlevi, depolanan en fazla yük faktörünü döndürür. İkinci üye işlevi, saklı maksimum yük faktörünü *faktörle*değiştirir.

### <a name="example"></a>Örnek

```cpp
// std__unordered_map__unordered_multimap_max_load_factor.cpp
// compile with: /EHsc
#include <unordered_map>
#include <iostream>

typedef std::unordered_multimap<char, int> Mymap;
int main()
    {
    Mymap c1;

    c1.insert(Mymap::value_type('a', 1));
    c1.insert(Mymap::value_type('b', 2));
    c1.insert(Mymap::value_type('c', 3));

// display contents " [c 3] [b 2] [a 1]"
    for (Mymap::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << " [" << it->first << ", " << it->second << "]";
    std::cout << std::endl;

// inspect current parameters
    std::cout << "bucket_count() == " << c1.bucket_count() << std::endl;
    std::cout << "load_factor() == " << c1.load_factor() << std::endl;
    std::cout << "max_bucket_count() == "
        << c1.max_bucket_count() << std::endl;
    std::cout << "max_load_factor() == "
        << c1.max_load_factor() << std::endl;
    std::cout << std::endl;

// change max_load_factor and redisplay
    c1.max_load_factor(0.10f);
    std::cout << "bucket_count() == " << c1.bucket_count() << std::endl;
    std::cout << "load_factor() == " << c1.load_factor() << std::endl;
    std::cout << "max_bucket_count() == "
        << c1.max_bucket_count() << std::endl;
    std::cout << "max_load_factor() == "
        << c1.max_load_factor() << std::endl;
    std::cout << std::endl;

// rehash and redisplay
    c1.rehash(100);
    std::cout << "bucket_count() == " << c1.bucket_count() << std::endl;
    std::cout << "load_factor() == " << c1.load_factor() << std::endl;
    std::cout << "max_bucket_count() == "
        << c1.max_bucket_count() << std::endl;
    std::cout << "max_load_factor() == "
        << c1.max_load_factor() << std::endl;
    std::cout << std::endl;

    return (0);
    }
```

```Output
[c, 3] [b, 2] [a, 1]
bucket_count() == 8
load_factor() == 0.375
max_bucket_count() == 8
max_load_factor() == 4

bucket_count() == 8
load_factor() == 0.375
max_bucket_count() == 8
max_load_factor() == 0.1

bucket_count() == 128
load_factor() == 0.0234375
max_bucket_count() == 128
max_load_factor() == 0.1
```

## <a name="unordered_multimapmax_size"></a><a name="max_size"></a> unordered_multimap:: max_size

Denetlenen dizinin en büyük boyutunu alır.

```cpp
size_type max_size() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, nesnenin denetleyecan en uzun sırasının uzunluğunu döndürür.

### <a name="example"></a>Örnek

```cpp
// std__unordered_map__unordered_multimap_max_size.cpp
// compile with: /EHsc
#include <unordered_map>
#include <iostream>

typedef std::unordered_multimap<char, int> Mymap;
int main()
    {
    Mymap c1;

    std::cout << "max_size() == " << c1.max_size() << std::endl;

    return (0);
    }
```

```Output
max_size() == 536870911
```

## <a name="unordered_multimapoperator"></a><a name="op_eq"></a> unordered_multimap:: operator =

Bir karma tabloya kopyalar.

```cpp
unordered_multimap& operator=(const unordered_multimap& right);

unordered_multimap& operator=(unordered_multimap&& right);
```

### <a name="parameters"></a>Parametreler

*Right*\
`unordered_multimap`İçine kopyalandığı `unordered_multimap` .

### <a name="remarks"></a>Açıklamalar

Bir unordered_multimap var olan öğeleri sildikten sonra, `operator=` unordered_multimap içeriğini kopyalar ya da *sağa taşısa* .

### <a name="example"></a>Örnek

```cpp
// unordered_multimap_operator_as.cpp
// compile with: /EHsc
#include <unordered_multimap>
#include <iostream>

int main( )
   {
   using namespace std;
   unordered_multimap<int, int> v1, v2, v3;
   unordered_multimap<int, int>::iterator iter;

   v1.insert(pair<int, int>(1, 10));

   cout << "v1 = " ;
   for (iter = v1.begin(); iter != v1.end(); iter++)
      cout << iter->second << " ";
   cout << endl;

   v2 = v1;
   cout << "v2 = ";
   for (iter = v2.begin(); iter != v2.end(); iter++)
      cout << iter->second << " ";
   cout << endl;

// move v1 into v2
   v2.clear();
   v2 = move(v1);
   cout << "v2 = ";
   for (iter = v2.begin(); iter != v2.end(); iter++)
      cout << iter->second << " ";
   cout << endl;
   }
```

## <a name="unordered_multimappointer"></a><a name="pointer"></a> unordered_multimap::p oınter

Bir öğe için bir işaretçi türü.

```cpp
typedef Alloc::pointer pointer;
```

### <a name="remarks"></a>Açıklamalar

Türü, denetlenen sıranın bir öğesi için bir işaretçi olarak işlev görebilecek bir nesneyi tanımlar.

### <a name="example"></a>Örnek

```cpp
// std__unordered_map__unordered_multimap_pointer.cpp
// compile with: /EHsc
#include <unordered_map>
#include <iostream>

typedef std::unordered_multimap<char, int> Mymap;
int main()
    {
    Mymap c1;

    c1.insert(Mymap::value_type('a', 1));
    c1.insert(Mymap::value_type('b', 2));
    c1.insert(Mymap::value_type('c', 3));

// display contents " [c 3] [b 2] [a 1]"
    for (Mymap::iterator it = c1.begin();
        it != c1.end(); ++it)
        {
        Mymap::pointer p = &*it;
        std::cout << " [" << p->first << ", " << p->second << "]";
        }
    std::cout << std::endl;

    return (0);
    }
```

```Output
[c, 3] [b, 2] [a, 1]
```

## <a name="unordered_multimapreference"></a><a name="reference"></a> unordered_multimap:: Reference

Bir öğe için bir başvuru türü.

```cpp
typedef Alloc::reference reference;
```

### <a name="remarks"></a>Açıklamalar

Türü, denetlenen sıranın bir öğesine başvuru olarak işlev görebilecek bir nesne tanımlar.

### <a name="example"></a>Örnek

```cpp
// std__unordered_map__unordered_multimap_reference.cpp
// compile with: /EHsc
#include <unordered_map>
#include <iostream>

typedef std::unordered_multimap<char, int> Mymap;
int main()
    {
    Mymap c1;

    c1.insert(Mymap::value_type('a', 1));
    c1.insert(Mymap::value_type('b', 2));
    c1.insert(Mymap::value_type('c', 3));

// display contents " [c 3] [b 2] [a 1]"
    for (Mymap::iterator it = c1.begin();
        it != c1.end(); ++it)
        {
        Mymap::reference ref = *it;
        std::cout << " [" << ref.first << ", " << ref.second << "]";
        }
    std::cout << std::endl;

    return (0);
    }
```

```Output
[c, 3] [b, 2] [a, 1]
```

## <a name="unordered_multimaprehash"></a><a name="rehash"></a> unordered_multimap:: yeniden karma

Karma tabloyu yeniden oluşturur.

```cpp
void rehash(size_type nbuckets);
```

### <a name="parameters"></a>Parametreler

*ndemet 'ler*\
İstenen demet sayısı.

### <a name="remarks"></a>Açıklamalar

Üye işlevi, demetlerin sayısını en az *ndemetler* olacak şekilde değiştirir ve karma tabloyu gerektiği gibi yeniden oluşturur.

### <a name="example"></a>Örnek

```cpp
// std__unordered_map__unordered_multimap_rehash.cpp
// compile with: /EHsc
#include <unordered_map>
#include <iostream>

typedef std::unordered_multimap<char, int> Mymap;
int main()
    {
    Mymap c1;

    c1.insert(Mymap::value_type('a', 1));
    c1.insert(Mymap::value_type('b', 2));
    c1.insert(Mymap::value_type('c', 3));

// display contents " [c 3] [b 2] [a 1]"
    for (Mymap::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << " [" << it->first << ", " << it->second << "]";
    std::cout << std::endl;

// inspect current parameters
    std::cout << "bucket_count() == " << c1.bucket_count() << std::endl;
    std::cout << "load_factor() == " << c1.load_factor() << std::endl;
    std::cout << "max_load_factor() == " << c1.max_load_factor() << std::endl;
    std::cout << std::endl;

// change max_load_factor and redisplay
    c1.max_load_factor(0.10f);
    std::cout << "bucket_count() == " << c1.bucket_count() << std::endl;
    std::cout << "load_factor() == " << c1.load_factor() << std::endl;
    std::cout << "max_load_factor() == " << c1.max_load_factor() << std::endl;
    std::cout << std::endl;

// rehash and redisplay
    c1.rehash(100);
    std::cout << "bucket_count() == " << c1.bucket_count() << std::endl;
    std::cout << "load_factor() == " << c1.load_factor() << std::endl;
    std::cout << "max_load_factor() == " << c1.max_load_factor() << std::endl;

    return (0);
    }
```

```Output
[c, 3] [b, 2] [a, 1]
bucket_count() == 8
load_factor() == 0.375
max_load_factor() == 4

bucket_count() == 8
load_factor() == 0.375
max_load_factor() == 0.1

bucket_count() == 128
load_factor() == 0.0234375
max_load_factor() == 0.1
```

## <a name="unordered_multimapsize"></a><a name="size"></a> unordered_multimap:: size

Öğe sayısını sayar.

```cpp
size_type size() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi denetlenen sıranın uzunluğunu döndürür.

### <a name="example"></a>Örnek

```cpp
// std__unordered_map__unordered_multimap_size.cpp
// compile with: /EHsc
#include <unordered_map>
#include <iostream>

typedef std::unordered_multimap<char, int> Mymap;
int main()
    {
    Mymap c1;

    c1.insert(Mymap::value_type('a', 1));
    c1.insert(Mymap::value_type('b', 2));
    c1.insert(Mymap::value_type('c', 3));

// display contents " [c 3] [b 2] [a 1]"
    for (Mymap::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << " [" << it->first << ", " << it->second << "]";
    std::cout << std::endl;

// clear the container and reinspect
    c1.clear();
    std::cout << "size == " << c1.size() << std::endl;
    std::cout << "empty() == " << std::boolalpha << c1.empty() << std::endl;
    std::cout << std::endl;

    c1.insert(Mymap::value_type('d', 4));
    c1.insert(Mymap::value_type('e', 5));

// display contents " [e 5] [d 4]"
    for (Mymap::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << " [" << it->first << ", " << it->second << "]";
    std::cout << std::endl;

    std::cout << "size == " << c1.size() << std::endl;
    std::cout << "empty() == " << std::boolalpha << c1.empty() << std::endl;

    return (0);
    }
```

```Output
[c, 3] [b, 2] [a, 1]
size == 0
empty() == true

[e, 5] [d, 4]
size == 2
empty() == false
```

## <a name="unordered_multimapsize_type"></a><a name="size_type"></a> unordered_multimap:: size_type

İki öğe arasındaki işaretsiz bir mesafenin türü.

```cpp
typedef T2 size_type;
```

### <a name="remarks"></a>Açıklamalar

İşaretsiz tamsayı türü, denetlenen bir dizinin uzunluğunu temsil eden bir nesneyi tanımlar. Burada uygulama tanımlı tür için bir eş anlamlı olarak açıklanmaktadır `T2` .

### <a name="example"></a>Örnek

```cpp
// std__unordered_map__unordered_multimap_size_type.cpp
// compile with: /EHsc
#include <unordered_map>
#include <iostream>

typedef std::unordered_multimap<char, int> Mymap;
int main()
    {
    Mymap c1;
    Mymap::size_type sz = c1.size();

    std::cout << "size == " << sz << std::endl;

    return (0);
    }
```

```Output
size == 0
```

## <a name="unordered_multimapswap"></a><a name="swap"></a> unordered_multimap:: swap

İki kapsayıcının içeriğinin yerini değiştirir.

```cpp
void swap(unordered_multimap& right);
```

### <a name="parameters"></a>Parametreler

*Right*\
İle takas edilecek kapsayıcı.

### <a name="remarks"></a>Açıklamalar

Üye işlevi, ve sağ arasındaki denetlenen dizileri **`*this`** değiştirir *right*. [Unordered_multimap:: get_allocator](#get_allocator) `() == right.get_allocator()` , bu, sabit bir zamanda, yalnızca türünde depolanan nitelikler nesnesini kopyalamanın bir sonucu olarak bir özel durum oluşturur `Tr` ve iki denetimli sırada öğeleri belirten başvuruları, işaretçileri veya yineleyicileri geçersiz kılar. Aksi takdirde, bir dizi öğe ataması ve Oluşturucu çağrısı, iki denetimli dizi içindeki öğe sayısıyla orantılı olarak gerçekleştirilir.

### <a name="example"></a>Örnek

```cpp
// std__unordered_map__unordered_multimap_swap.cpp
// compile with: /EHsc
#include <unordered_map>
#include <iostream>

typedef std::unordered_multimap<char, int> Mymap;
int main()
    {
    Mymap c1;

    c1.insert(Mymap::value_type('a', 1));
    c1.insert(Mymap::value_type('b', 2));
    c1.insert(Mymap::value_type('c', 3));

// display contents " [c 3] [b 2] [a 1]"
    for (Mymap::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << " [" << it->first << ", " << it->second << "]";
    std::cout << std::endl;

    Mymap c2;

    c2.insert(Mymap::value_type('d', 4));
    c2.insert(Mymap::value_type('e', 5));
    c2.insert(Mymap::value_type('f', 6));

    c1.swap(c2);

// display contents " [f 6] [e 5] [d 4]"
    for (Mymap::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << " [" << it->first << ", " << it->second << "]";
    std::cout << std::endl;

    swap(c1, c2);

// display contents " [c 3] [b 2] [a 1]"
    for (Mymap::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << " [" << it->first << ", " << it->second << "]";
    std::cout << std::endl;

    return (0);
    }
```

```Output
[c, 3] [b, 2] [a, 1]
[f, 6] [e, 5] [d, 4]
[c, 3] [b, 2] [a, 1]
```

## <a name="unordered_multimapunordered_multimap"></a><a name="unordered_multimap"></a> unordered_multimap:: unordered_multimap

Bir kapsayıcı nesnesi oluşturur.

```cpp
unordered_multimap(
    const unordered_multimap& Right);

explicit unordered_multimap(
    size_type Bucket_count = N0,
    const Hash& Hash = Hash(),
    const Comp& Comp = Pred(),
    const Allocator& Al = Alloc());

unordered_multimap(
    unordered_multimap&& Right);

unordered_multimap(
    initializer_list<Type> IList);

unordered_multimap(
    initializer_list<Type> IList,
    size_type Bucket_count);

unordered_multimap(
    initializer_list<Type> IList,
    size_type Bucket_count,
    const Hash& Hash);

unordered_multimap(
    initializer_list<Type> IList,
    size_type Bucket_count,
    const Hash& Hash,
    const Key& Key);

unordered_multimap(
    initializer_list<Type> IList,
    size_type Bucket_count,
    const Hash& Hash,
    const Key& Key,
    const Allocator& Al);

template <class InputIterator>
unordered_multimap(
    InputIterator first,
    InputIterator last,
    size_type Bucket_count = N0,
    const Hash& Hash = Hash(),
    const Comp& Comp = Pred(),
    const Allocator& Al = Alloc());
```

### <a name="parameters"></a>Parametreler

*InputIterator*\
Yineleyici türü.

*Eşkenar*\
Depolanacak ayırıcı nesne.

*İnin*\
Depolanacak karşılaştırma işlevi nesnesi.

*Yla*\
Depolanacak karma işlev nesnesi.

*Bucket_count*\
En düşük demet sayısı.

*Right*\
Kopyalanacak kapsayıcı.

*IList*\
Öğelerin kopyalanacağı initializer_list.

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu, *sağdan*denetlenen sıranın bir kopyasını belirtir. İkinci oluşturucu boş bir denetlenmiş dizi belirtir. Üçüncü Oluşturucu. *sağa*taşıyarak sıranın bir kopyasını belirtir. Dördüncü, beşinci, altıncı, yedinci ve sekizinci oluşturucular üyeler için bir initializer_list kullanır. Dokuzuncu Oluşturucu öğe değerlerinin dizisini ekler `[First, Last)` .

Ayrıca, tüm oluşturucular çeşitli depolanmış değerleri başlatır. Kopya Oluşturucu için değerler *sağdan*alınır. Aksi durumda:.

Varsa, en düşük demet sayısı *Bucket_count*bağımsız değişkendir; Aksi takdirde, burada uygulama tanımlı değer olarak açıklanan varsayılan bir değerdir `N0` .

Karma işlev nesnesi varsa bağımsız değişken *karmasıdır*; Aksi takdirde, `Hash()` .

Karşılaştırma işlevi nesnesi, varsa, *comp*bağımsız değişkenidir; Aksi takdirde, `Pred()` .

Ayırıcı nesne varsa *Al*bağımsız değişkenidir; Aksi takdirde, `Alloc()` .

### <a name="example"></a>Örnek

```cpp
// std__unordered_map__unordered_multimap_construct.cpp
// compile with: /EHsc
#include <unordered_map>
#include <iostream>

using namespace std;

using  Mymap = unordered_multimap<char, int> ;
int main()
{
    Mymap c1;

    c1.insert(Mymap::value_type('a', 1));
    c1.insert(Mymap::value_type('b', 2));
    c1.insert(Mymap::value_type('c', 3));

    // display contents " [c 3] [b 2] [a 1]"
    for (const auto& c : c1) {
        cout << " [" << c.first << ", " << c.second << "]";
    }
    cout << endl;

    Mymap c2(8,
        hash<char>(),
        equal_to<char>(),
        allocator<pair<const char, int> >());

    c2.insert(Mymap::value_type('d', 4));
    c2.insert(Mymap::value_type('e', 5));
    c2.insert(Mymap::value_type('f', 6));

    // display contents " [f 6] [e 5] [d 4]"
    for (const auto& c : c2) {
        cout << " [" << c.first << ", " << c.second << "]";
    }
    cout << endl;

    Mymap c3(c1.begin(),
        c1.end(),
        8,
        hash<char>(),
        equal_to<char>(),
        allocator<pair<const char, int> >());

    // display contents " [c 3] [b 2] [a 1]"
    for (const auto& c : c3) {
        cout << " [" << c.first << ", " << c.second << "]";
    }
    cout << endl;

    Mymap c4(move(c3));

    // display contents " [c 3] [b 2] [a 1]"
    for (const auto& c : c4) {
        cout << " [" << c.first << ", " << c.second << "]";
    }
    cout << endl;

    // Construct with an initializer_list
    unordered_multimap<int, char> c5({ { 5, 'g' }, { 6, 'h' }, { 7, 'i' }, { 8, 'j' } });
    for (const auto& c : c5) {
        cout << " [" << c.first << ", " << c.second << "]";
    }
    cout << endl;

    // Initializer_list plus size
    unordered_multimap<int, char> c6({ { 5, 'g' }, { 6, 'h' }, { 7, 'i' }, { 8, 'j' } }, 4);
    for (const auto& c : c1) {
        cout << " [" << c.first << ", " << c.second << "]";
    }
    cout << endl;

    // Initializer_list plus size and hash
    unordered_multimap<int, char, hash<char>> c7(
        { { 5, 'g' }, { 6, 'h' }, { 7, 'i' }, { 8, 'j' } },
        4,
        hash<char>()
    );

    for (const auto& c : c1) {
        cout << " [" << c.first << ", " << c.second << "]";
    }
    cout << endl;

    // Initializer_list plus size, hash, and key_equal
    unordered_multimap<int, char, hash<char>, equal_to<char>> c8(
        { { 5, 'g' }, { 6, 'h' }, { 7, 'i' }, { 8, 'j' } },
        4,
        hash<char>(),
        equal_to<char>()
    );

    for (const auto& c : c1) {
        cout << " [" << c.first << ", " << c.second << "]";
    }
    cout << endl;

    // Initializer_list plus size, hash, key_equal, and allocator
    unordered_multimap<int, char, hash<char>, equal_to<char>> c9(
        { { 5, 'g' }, { 6, 'h' }, { 7, 'i' }, { 8, 'j' } },
        4,
        hash<char>(),
        equal_to<char>(),
        allocator<pair<const char, int> >()
    );

    for (const auto& c : c1) {
        cout << " [" << c.first << ", " << c.second << "]";
    }
    cout << endl;
}
```

```Output
[a, 1] [b, 2] [c, 3] [d, 4] [e, 5] [f, 6] [a, 1] [b, 2] [c, 3] [a, 1] [b, 2] [c, 3] [5, g] [6, h] [7, i] [8, j] [a, 1] [b, 2] [c, 3] [a, 1] [b, 2] [c, 3] [a, 1] [b, 2] [c, 3] [a, 1] [b, 2] [c, 3] [c, 3] [b, 2] [a, 1]
[f, 6] [e, 5] [d, 4]
[c, 3] [b, 2] [a, 1]
[c, 3] [b, 2] [a, 1]
```

## <a name="unordered_multimapvalue_type"></a><a name="value_type"></a> unordered_multimap:: value_type

Öğenin türü.

```cpp
typedef std::pair<const Key, Ty> value_type;
```

### <a name="remarks"></a>Açıklamalar

Tür denetimli sıranın bir öğesini açıklar.

### <a name="example"></a>Örnek

```cpp
// std__unordered_map__unordered_multimap_value_type.cpp
// compile with: /EHsc
#include <unordered_map>
#include <iostream>

typedef std::unordered_multimap<char, int> Mymap;
int main()
    {
    Mymap c1;

    c1.insert(Mymap::value_type('a', 1));
    c1.insert(Mymap::value_type('b', 2));
    c1.insert(Mymap::value_type('c', 3));

// display contents " [c 3] [b 2] [a 1]"
    for (Mymap::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << " [" << it->first << ", " << it->second << "]";
    std::cout << std::endl;

// add a value and reinspect
    Mymap::key_type key = 'd';
    Mymap::mapped_type mapped = 4;
    Mymap::value_type val = Mymap::value_type(key, mapped);
    c1.insert(val);

    for (Mymap::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << " [" << it->first << ", " << it->second << "]";
    std::cout << std::endl;

    return (0);
    }
```

```Output
[c, 3] [b, 2] [a, 1]
[d, 4] [c, 3] [b, 2] [a, 1]
```

## <a name="see-also"></a>Ayrıca bkz.

[<unordered_map>](../standard-library/unordered-map.md)\
[Kapsayıcıları](../cpp/containers-modern-cpp.md)\
[C++ standart kitaplığı 'nda iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[C++ standart kitaplığı başvurusu](../standard-library/cpp-standard-library-reference.md)
