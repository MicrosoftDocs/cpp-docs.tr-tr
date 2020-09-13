---
title: unordered_map Sınıfı
description: Farklı bir öğe dizisini denetleyen C++ standart kitaplık kapsayıcı sınıfı için API başvurusu `unordered_map` .
ms.date: 9/9/2020
f1_keywords:
- unordered_map/std::unordered_map
- unordered_map/std::unordered_map::allocator_type
- unordered_map/std::unordered_map::const_iterator
- unordered_map/std::unordered_map::const_local_iterator
- unordered_map/std::unordered_map::const_pointer
- unordered_map/std::unordered_map::const_reference
- unordered_map/std::unordered_map::difference_type
- unordered_map/std::unordered_map::hasher
- unordered_map/std::unordered_map::iterator
- unordered_map/std::unordered_map::key_equal
- unordered_map/std::unordered_map::key_type
- unordered_map/std::unordered_map::local_iterator
- unordered_map/std::unordered_map::mapped_type
- unordered_map/std::unordered_map::pointer
- unordered_map/std::unordered_map::reference
- unordered_map/std::unordered_map::size_type
- unordered_map/std::unordered_map::value_type
- unordered_map/std::unordered_map::at
- unordered_map/std::unordered_map::begin
- unordered_map/std::unordered_map::bucket
- unordered_map/std::unordered_map::bucket_count
- unordered_map/std::unordered_map::bucket_size
- unordered_map/std::unordered_map::cbegin
- unordered_map/std::unordered_map::cend
- unordered_map/std::unordered_map::clear
- unordered_map/std::unordered_map::contains
- unordered_map/std::unordered_map::count
- unordered_map/std::unordered_map::emplace
- unordered_map/std::unordered_map::emplace_hint
- unordered_map/std::unordered_map::empty
- unordered_map/std::unordered_map::end
- unordered_map/std::unordered_map::equal_range
- unordered_map/std::unordered_map::erase
- unordered_map/std::unordered_map::find
- unordered_map/std::unordered_map::get_allocator
- unordered_map/std::unordered_map::hash
- unordered_map/std::unordered_map::insert
- unordered_map/std::unordered_map::key_eq
- unordered_map/std::unordered_map::load_factor
- unordered_map/std::unordered_map::max_bucket_count
- unordered_map/std::unordered_map::max_load_factor
- unordered_map/std::unordered_map::max_size
- unordered_map/std::unordered_map::rehash
- unordered_map/std::unordered_map::size
- unordered_map/std::unordered_map::swap
- unordered_map/std::unordered_map::unordered_map
- unordered_map/std::unordered_map::hash_function
helpviewer_keywords:
- std::unordered_map
- std::unordered_map::allocator_type
- std::unordered_map::const_iterator
- std::unordered_map::const_local_iterator
- std::unordered_map::const_pointer
- std::unordered_map::const_reference
- std::unordered_map::difference_type
- std::unordered_map::hasher
- std::unordered_map::iterator
- std::unordered_map::key_equal
- std::unordered_map::key_type
- std::unordered_map::local_iterator
- std::unordered_map::mapped_type
- std::unordered_map::pointer
- std::unordered_map::reference
- std::unordered_map::size_type
- std::unordered_map::value_type
- std::unordered_map::at
- std::unordered_map::begin
- std::unordered_map::bucket
- std::unordered_map::bucket_count
- std::unordered_map::bucket_size
- std::unordered_map::cbegin
- std::unordered_map::cend
- std::unordered_map::clear
- std::unordered_map::contains
- std::unordered_map::count
- std::unordered_map::emplace
- std::unordered_map::emplace_hint
- std::unordered_map::empty
- std::unordered_map::end
- std::unordered_map::equal_range
- std::unordered_map::erase
- std::unordered_map::find
- std::unordered_map::get_allocator
- std::unordered_map::hash
- std::unordered_map::insert
- std::unordered_map::key_eq
- std::unordered_map::load_factor
- std::unordered_map::max_bucket_count
- std::unordered_map::max_load_factor
- std::unordered_map::max_size
- std::unordered_map::rehash
- std::unordered_map::size
- std::unordered_map::swap
- std::unordered_map::unordered_map
- std::unordered_map::allocator_type
- std::unordered_map::const_iterator
- std::unordered_map::const_local_iterator
- std::unordered_map::const_pointer
- std::unordered_map::const_reference
- std::unordered_map::difference_type
- std::unordered_map::hasher
- std::unordered_map::iterator
- std::unordered_map::key_equal
- std::unordered_map::key_type
- std::unordered_map::local_iterator
- std::unordered_map::mapped_type
- std::unordered_map::pointer
- std::unordered_map::reference
- std::unordered_map::size_type
- std::unordered_map::value_type
- std::unordered_map::at
- std::unordered_map::begin
- std::unordered_map::bucket
- std::unordered_map::bucket_count
- std::unordered_map::bucket_size
- std::unordered_map::cbegin
- std::unordered_map::cend
- std::unordered_map::clear
- std::unordered_map::count
- std::unordered_map::emplace
- std::unordered_map::emplace_hint
- std::unordered_map::empty
- std::unordered_map::end
- std::unordered_map::equal_range
- std::unordered_map::erase
- std::unordered_map::find
- std::unordered_map::get_allocator
- std::unordered_map::hash_function
- std::unordered_map::insert
- std::unordered_map::key_eq
- std::unordered_map::load_factor
- std::unordered_map::max_bucket_count
- std::unordered_map::max_load_factor
- std::unordered_map::max_size
- std::unordered_map::rehash
- std::unordered_map::size
- std::unordered_map::swap
ms.assetid: 7cf7cfa1-16e7-461c-a9b2-3b8d8ec24e0d
ms.openlocfilehash: 8fe2e153e3a7483d9c4698ef4a87e281ace653fc
ms.sourcegitcommit: 6280a4c629de0f638ebc2edd446de2a9b11f0406
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2020
ms.locfileid: "90042152"
---
# <a name="unordered_map-class"></a>unordered_map Sınıfı

Sınıf şablonu, türünde öğelerin değişen uzunluklu dizisini denetleyen bir nesneyi tanımlar `std::pair<const Key, Ty>` . Dizi çağrılan demetlerin sıralı bir dizi kümesini bölümleyen bir karma işlev tarafından zayıf bir şekilde sıralanır. Her bir demette herhangi bir öğe çiftinin eşdeğer sıralamaya sahip olup olmadığını belirleyen bir karşılaştırma işlevi vardır. Her bir öğe iki nesne, bir sıralama anahtarı ve bir değer depolar. Dizi, en azından tüm demetleri kabaca eşit uzunlukta olduğunda, dizideki (sabit zaman) öğe sayısından bağımsız olabilen işlem sayısına sahip rastgele bir öğenin aranması, eklenmesi ve kaldırılmasına izin verecek şekilde temsil edilir. En kötü durumda, tüm öğeler tek bir demet içinde olduğunda işlem sayısı dizideki (doğrusal zaman) öğelerin sayısıyla orantılıdır. Ayrıca, bir öğe eklenmesi hiçbir yineleyiciyi geçersiz kılmaz; bir öğenin kaldırılması yalnızca bu kaldırılan öğeyi gösteren yineleyicileri geçersiz kılar.

## <a name="syntax"></a>Söz dizimi

```cpp
template <class Key,
    class Ty,
    class Hash = std::hash<Key>,
    class Pred = std::equal_to<Key>,
    class Alloc = std::allocator<std::pair<const Key, Ty>>>
class unordered_map;
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
|[hızı](#at)|Belirtilen anahtarı içeren bir öğe bulur.|
|[başladı](#begin)|Denetlenen dizinin başlangıcını belirtir.|
|[demet](#bucket)|Bir anahtar değeri için demet numarasını alır.|
|[bucket_count](#bucket_count)|Demet sayısını alır.|
|[bucket_size](#bucket_size)|Demet boyutunu alır.|
|[cbegin](#cbegin)|Denetlenen dizinin başlangıcını belirtir.|
|[cend](#cend)|Denetlenen dizinin bitişini belirtir.|
|[lediğiniz](#clear)|Tüm öğeleri kaldırır.|
|[biriktirme](#count)|Belirtilen bir anahtar ile eşleşen öğe sayısını bulur.|
|[contains](#contains)<sup>c++ 20</sup> içerir|İçinde belirtilen anahtara sahip bir öğe olup olmadığını kontrol edin `unordered_map` .|
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
|[unordered_map](#unordered_map)|Bir kapsayıcı nesnesi oluşturur.|

|İşleç|Açıklama|
|-|-|
|[unordered_map:: operator []](#op_at)|Belirtilen anahtarı içeren bir öğe bulur veya ekler.|
|[unordered_map:: operator =](#op_eq)|Bir karma tabloya kopyalar.|

## <a name="remarks"></a>Açıklamalar

Nesne, iki saklı nesneyi çağırarak denetlediği sırayı, [unordered_map:: key_equal](#key_equal) türünde bir karşılaştırma işlev nesnesi ve [unordered_map:: hasher](#hasher)türünde bir karma işlev nesnesi olarak sıralar. [Unordered_map:: key_eq](#key_eq); üye işlevini çağırarak `()` ve ikinci saklı nesneye eriştiğinizde, [unordered_map:: hash_function](#hash)üye işlevini çağırarak, ilk depolanan nesneye erişirsiniz `()` . Özellikle, tüm değerleri `X` ve `Y` türü için `Key` , çağrı `key_eq()(X, Y)` yalnızca iki bağımsız değişken değeri eşdeğer sıralama içeriyorsa true değerini döndürür; çağrı, `hash_function()(keyval)` türündeki değerlerin bir dağılımını verir `size_t` . Sınıf şablonu [unordered_multimap sınıfından](../standard-library/unordered-multimap-class.md)farklı olarak, türündeki bir nesne `unordered_map` `key_eq()(X, Y)` denetimli sıranın herhangi iki öğesi için her zaman false olur. (Anahtarlar benzersizdir.)

Nesne ayrıca, demet başına istenen ortalama öğe sayısını belirten en yüksek yük faktörünü depolar. Bir öğe eklemek [unordered_map:: load_factor](#load_factor) `()` en fazla yük faktörünü aşmasına neden olursa kapsayıcı, demetlerin sayısını artırır ve gerekirse karma tabloyu yeniden oluşturur.

Denetlenen dizideki öğelerin gerçek sırası karma işleve, karşılaştırma işlevine, ekleme sırasına, en yüksek yük faktörüne ve geçerli demet sayısına bağlıdır. Denetlenen dizideki öğelerin sırasını genelde tahmin edemezsiniz. Ancak, eşdeğer sıralamaya sahip öğelerin herhangi bir alt kümesinin her zaman denetlenen dizide bitişik olduğundan emin olabilirsiniz.

Nesnesi, [unordered_map:: allocator_type](#allocator_type)türünde depolanan bir ayırıcı nesne aracılığıyla denetlediği sıra için depolamayı ayırır ve boşaltır. Böyle bir ayırıcı nesne, türünde bir nesne ile aynı dış arabirime sahip olmalıdır `allocator` . Depolanan ayırıcı nesnenin kapsayıcı nesne atandığında kopyalanmayacağını unutmayın.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<unordered_map>

**Ad alanı:** std

## <a name="unordered_mapallocator_type"></a><a name="allocator_type"></a> unordered_map:: allocator_type

Depolamayı yönetmek için bir ayırıcı türü.

```cpp
typedef Alloc allocator_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, şablon parametresi için bir eş anlamlı `Alloc` .

### <a name="example"></a>Örnek

```cpp
// std__unordered_map__unordered_map_allocator_type.cpp
// compile with: /EHsc
#include <unordered_map>
#include <iostream>

typedef std::unordered_map<char, int> Mymap;
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

## <a name="unordered_mapat"></a><a name="at"></a> unordered_map:: at

Unordered_map, belirtilen anahtar değeri olan bir öğe bulur.

```cpp
Ty& at(const Key& key);
const Ty& at(const Key& key) const;
```

### <a name="parameters"></a>Parametreler

*anahtar*\
Bulunacak anahtar değeri.

### <a name="return-value"></a>Dönüş Değeri

Bulunan öğenin veri değerine başvuru.

### <a name="remarks"></a>Açıklamalar

Bağımsız değişken anahtar değeri bulunamazsa, işlev sınıfının bir nesnesini oluşturur `out_of_range` .

### <a name="example"></a>Örnek

```cpp
// unordered_map_at.cpp
// compile with: /EHsc
#include <unordered_map>
#include <iostream>

typedef std::unordered_map<char, int> Mymap;
typedef std::unordered_map<char, int> Mymap;
int main()
{
    Mymap c1;

    c1.insert(Mymap::value_type('a', 1));
    c1.insert(Mymap::value_type('b', 2));
    c1.insert(Mymap::value_type('c', 3));

    // find and show elements
    std::cout << "c1.at('a') == " << c1.at('a') << std::endl;
    std::cout << "c1.at('b') == " << c1.at('b') << std::endl;
    std::cout << "c1.at('c') == " << c1.at('c') << std::endl;

    return (0);
}
```

## <a name="unordered_mapbegin"></a><a name="begin"></a> unordered_map:: Begin

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
// std__unordered_map__unordered_map_begin.cpp
// compile with: /EHsc
#include <unordered_map>
#include <iostream>

#typedef std::unordered_map<char, int> Mymap;
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

## <a name="unordered_mapbucket"></a><a name="bucket"></a> unordered_map:: Bucket

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
// std__unordered_map__unordered_map_bucket.cpp
// compile with: /EHsc
#include <unordered_map>
#include <iostream>

typedef std::unordered_map<char, int> Mymap;
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

## <a name="unordered_mapbucket_count"></a><a name="bucket_count"></a> unordered_map:: bucket_count

Demet sayısını alır.

```cpp
size_type bucket_count() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, geçerli demet sayısını döndürür.

### <a name="example"></a>Örnek

```cpp
// std__unordered_map__unordered_map_bucket_count.cpp
// compile with: /EHsc
#include <unordered_map>
#include <iostream>

typedef std::unordered_map<char, int> Mymap;
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
[c, 3][b, 2][a, 1]
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

## <a name="unordered_mapbucket_size"></a><a name="bucket_size"></a> unordered_map:: bucket_size

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
// std__unordered_map__unordered_map_bucket_size.cpp
// compile with: /EHsc
#include <unordered_map>
#include <iostream>

typedef std::unordered_map<char, int> Mymap;
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

## <a name="unordered_mapcbegin"></a><a name="cbegin"></a> unordered_map:: cbegin

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

## <a name="unordered_mapcend"></a><a name="cend"></a> unordered_map:: cend

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

## <a name="unordered_mapclear"></a><a name="clear"></a> unordered_map:: Clear

Tüm öğeleri kaldırır.

```cpp
void clear();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi [unordered_map:: Erase](#erase) `(` [unordered_map:: BEGIN](#begin) `(),` [unordered_map:: End](#end)' i çağırır `())` .

### <a name="example"></a>Örnek

```cpp
// std__unordered_map__unordered_map_clear.cpp
// compile with: /EHsc
#include <unordered_map>
#include <iostream>

typedef std::unordered_map<char, int> Mymap;
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

## <a name="unordered_mapconst_iterator"></a><a name="const_iterator"></a> unordered_map:: const_iterator

Denetlenen dizi için bir sabit yineleyici türü.

```cpp
typedef T1 const_iterator;
```

### <a name="remarks"></a>Açıklamalar

Türü, denetimli sıra için sabit bir ileri Yineleyici işlevi görebilecek bir nesneyi tanımlar. Burada uygulama tanımlı tür için bir eş anlamlı olarak açıklanmaktadır `T1` .

### <a name="example"></a>Örnek

```cpp
// std__unordered_map__unordered_map_const_iterator.cpp
// compile with: /EHsc
#include <unordered_map>
#include <iostream>

typedef std::unordered_map<char, int> Mymap;
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

## <a name="unordered_mapconst_local_iterator"></a><a name="const_local_iterator"></a> unordered_map:: const_local_iterator

Denetlenen dizi için bir sabit demet yineleyici türü.

```cpp
typedef T5 const_local_iterator;
```

### <a name="remarks"></a>Açıklamalar

Türü, bir demet için sabit bir ileri Yineleyici işlevi görebilecek bir nesneyi tanımlar. Burada uygulama tanımlı tür için bir eş anlamlı olarak açıklanmaktadır `T5` .

### <a name="example"></a>Örnek

```cpp
// std__unordered_map__unordered_map_const_local_iterator.cpp
// compile with: /EHsc
#include <unordered_map>
#include <iostream>

typedef std::unordered_map<char, int> Mymap;
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

## <a name="unordered_mapconst_pointer"></a><a name="const_pointer"></a> unordered_map:: const_pointer

Bir öğe için sabit bir işaretçi türü.

```cpp
typedef Alloc::const_pointer const_pointer;
```

### <a name="remarks"></a>Açıklamalar

Türü, denetlenen dizinin bir öğesi için sabit bir işaretçi olarak kullanılabilecek bir nesneyi tanımlar.

### <a name="example"></a>Örnek

```cpp
// std__unordered_map__unordered_map_const_pointer.cpp
// compile with: /EHsc
#include <unordered_map>
#include <iostream>

typedef std::unordered_map<char, int> Mymap;
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

## <a name="unordered_mapconst_reference"></a><a name="const_reference"></a> unordered_map:: const_reference

Bir öğe için sabit bir başvuru türü.

```cpp
typedef Alloc::const_reference const_reference;
```

### <a name="remarks"></a>Açıklamalar

Türü, denetlenen dizinin bir öğesine sabit başvuru olarak işlev yapabilecek bir nesneyi tanımlar.

### <a name="example"></a>Örnek

```cpp
// std__unordered_map__unordered_map_const_reference.cpp
// compile with: /EHsc
#include <unordered_map>
#include <iostream>

typedef std::unordered_map<char, int> Mymap;
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

## <a name="unordered_mapcontains"></a><a name="contains"></a> unordered_map:: Contains

Öğesinde belirtilen anahtarla bir öğe olup olmadığını denetler `unordered_map` .
C++ 20 ' de tanıtılmıştır.

```cpp
bool contains(const Key& key) const;
<class K> bool contains(const K& key) const;
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
    std::unordered_map<int, bool> theUnorderedMap = {{0, false}, {1,true}};

    std::cout << std::boolalpha; // so booleans show as 'true' or 'false'
    std::cout << theUnorderedMap.contains(1) << '\n';
    std::cout << theUnorderedMap.contains(2) << '\n';
    
    return 0;
}
```

```Output
true
false
```

## <a name="unordered_mapcount"></a><a name="count"></a> unordered_map:: Count

Belirtilen bir anahtar ile eşleşen öğe sayısını bulur.

```cpp
size_type count(const Key& keyval) const;
```

### <a name="parameters"></a>Parametreler

*keyval*\
Aranacak anahtar değer.

### <a name="remarks"></a>Açıklamalar

Üye işlevi [unordered_map:: equal_range](#equal_range)ile ayrılmış aralıktaki öğe sayısını döndürür `(keyval)` .

### <a name="example"></a>Örnek

```cpp
// std__unordered_map__unordered_map_count.cpp
// compile with: /EHsc
#include <unordered_map>
#include <iostream>

typedef std::unordered_map<char, int> Mymap;
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

## <a name="unordered_mapdifference_type"></a><a name="difference_type"></a> unordered_map::d ifference_type

İki öğe arasındaki işaretli mesafenin türü.

```cpp
typedef T3 difference_type;
```

### <a name="remarks"></a>Açıklamalar

İmzalanan tamsayı türü, denetlenen dizideki herhangi iki öğenin adresleri arasındaki farkı temsil eden bir nesneyi tanımlar. Burada uygulama tanımlı tür için bir eş anlamlı olarak açıklanmaktadır `T3` .

### <a name="example"></a>Örnek

```cpp
// std__unordered_map__unordered_map_difference_type.cpp
// compile with: /EHsc
#include <unordered_map>
#include <iostream>

typedef std::unordered_map<char, int> Mymap;
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

## <a name="unordered_mapemplace"></a><a name="emplace"></a> unordered_map:: emplace

Yerinde oluşturulmuş bir öğe ekler (kopyalama veya taşıma işlemleri yapılmaz) unordered_map.

```cpp
template <class... Args>
pair<iterator, bool>  emplace( Args&&... args);
```

### <a name="parameters"></a>Parametreler

*args*\
Değeri equivalently sıralı bir öğe içermiyorsa, içine eklenecek bir öğe oluşturmak için iletilen bağımsız değişkenler `unordered_map` .

### <a name="return-value"></a>Dönüş Değeri

Bir `pair` **`bool`** ekleme yapılırsa ve `unordered_map` anahtarı sıralamada denk bir değere sahip olan bir öğe içeriyorsa ve yineleyici bileşeni yeni bir öğenin eklendiği veya öğenin zaten bulunduğu adresi döndüren bir öğe içeriyorsa, bu bileşen bir ekleme işlemi yapıldıktan sonra true değerini döndürür.

Bu üye işlevi tarafından döndürülen bir çiftin Yineleyici bileşenine erişmek için, `pr` kullanın ve öğesini kullanın `pr.first` `*(pr.first)` . **`bool`** `pr` Bu üye işlevi tarafından döndürülen bir çiftin bileşenine erişmek için kullanın `pr.second` .

### <a name="remarks"></a>Açıklamalar

Bu işlev tarafından hiçbir yineleyiciler veya başvuru geçersiz kılınmamıştır.

Ekleme sırasında, bir özel durum oluşturulursa, ancak kapsayıcının karma işlevinde gerçekleşmezse kapsayıcı değiştirilmez. Karma işlevde özel durum oluşturulursa, sonuç tanımsızdır.

Kod örneği için bkz. [map:: emplace](../standard-library/map-class.md#emplace).

## <a name="unordered_mapemplace_hint"></a><a name="emplace_hint"></a> unordered_map:: emplace_hint

Yerinde oluşturulmuş bir öğe ekler (kopyalama veya taşıma işlemleri yapılmaz), yerleştirme ipucuyla birlikte.

```cpp
template <class... Args>
iterator emplace_hint(const_iterator where, Args&&... args);
```

### <a name="parameters"></a>Parametreler

*args*\
Unordered_map zaten bu öğeyi içermediği veya daha önce anahtarı equivalently sıralı bir öğe içermediğinden, unordered_map içine eklenecek bir öğe oluşturmak için iletilen bağımsız değişkenler.

*olmadığı*\
Doğru ekleme noktasını aramaya başlamak için yer hakkında bir ipucu.

### <a name="return-value"></a>Dönüş Değeri

Yeni eklenmekte olan öğe için bir yineleyici.

Öğe zaten mevcut olduğundan ekleme başarısız olursa, varolan öğeye bir yineleyici döndürür.

### <a name="remarks"></a>Açıklamalar

Bu işlev tarafından hiçbir başvuru geçersiz kılınmamıştır.

Ekleme sırasında, bir özel durum oluşturulursa, ancak kapsayıcının karma işlevinde gerçekleşmezse kapsayıcı değiştirilmez. Karma işlevde özel durum oluşturulursa, sonuç tanımsızdır.

Bir öğe [value_type](../standard-library/map-class.md#value_type) bir çifdir, böylece bir öğe değeri, ilk bileşeni anahtar değerine eşit olan ve ikinci bileşen öğenin veri değerine eşit olan bir sıralı çift olacaktır.

Kod örneği için bkz. [map:: emplace_hint](../standard-library/map-class.md#emplace_hint).

## <a name="unordered_mapempty"></a><a name="empty"></a> unordered_map:: boş

Bir öğe olup olmadığını sınar.

```cpp
bool empty() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi boş bir denetlenen dizi için true döndürür.

### <a name="example"></a>Örnek

```cpp
// std__unordered_map__unordered_map_empty.cpp
// compile with: /EHsc
#include <unordered_map>
#include <iostream>

typedef std::unordered_map<char, int> Mymap;
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

## <a name="unordered_mapend"></a><a name="end"></a> unordered_map:: End

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

## <a name="unordered_mapequal_range"></a><a name="equal_range"></a> unordered_map:: equal_range

Belirtilen bir anahtarla eşleşen aralığı bulur.

```cpp
std::pair<iterator, iterator>  equal_range(const Key& keyval);
std::pair<const_iterator, const_iterator>  equal_range(const Key& keyval) const;
```

### <a name="parameters"></a>Parametreler

*keyval*\
Aranacak anahtar değer.

### <a name="remarks"></a>Açıklamalar

Üye işlevi, `X` `[X.first, X.second)` yalnızca *keyval*ile eşdeğer sıralamaya sahip olan denetimli dizinin öğelerini sınırlandıran bir çift yineleyiciyi döndürür. Böyle bir öğe yoksa, her iki yineleyiciler de vardır `end()` .

### <a name="example"></a>Örnek

```cpp
// std__unordered_map__unordered_map_equal_range.cpp
// compile with: /EHsc
#include <unordered_map>
#include <iostream>

typedef std::unordered_map<char, int> Mymap;
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

## <a name="unordered_maperase"></a><a name="erase"></a> unordered_map:: Erase

Belirtilen konumlardan bir unordered_map öğeyi veya öğe aralığını kaldırır veya belirtilen bir anahtarla eşleşen öğeleri kaldırır.

```cpp
iterator erase(const_iterator Where);
iterator erase(const_iterator First, const_iterator Last);
size_type erase(const key_type& Key);
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

Üçüncü üye işlevi için, unordered_map kaldırılan öğelerin sayısını döndürür.

### <a name="remarks"></a>Açıklamalar

Kod örneği için bkz. [map:: Erase](../standard-library/map-class.md#erase).

## <a name="unordered_mapfind"></a><a name="find"></a> unordered_map:: Find

Belirtilen bir anahtarla eşleşen bir öğeyi bulur.

```cpp
const_iterator find(const Key& keyval) const;
```

### <a name="parameters"></a>Parametreler

*keyval*\
Aranacak anahtar değer.

### <a name="remarks"></a>Açıklamalar

Üye işlevi [unordered_map:: equal_range](#equal_range)döndürür `(keyval).first` .

### <a name="example"></a>Örnek

```cpp
// std__unordered_map__unordered_map_find.cpp
// compile with: /EHsc
#include <unordered_map>
#include <iostream>

typedef std::unordered_map<char, int> Mymap;
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

## <a name="unordered_mapget_allocator"></a><a name="get_allocator"></a> unordered_map:: get_allocator

Depolanan ayırıcı nesnesini alır.

```cpp
Alloc get_allocator() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, depolanan ayırıcı nesnesini döndürür.

### <a name="example"></a>Örnek

```cpp
// std__unordered_map__unordered_map_get_allocator.cpp
// compile with: /EHsc
#include <unordered_map>
#include <iostream>

typedef std::unordered_map<char, int> Mymap;
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

## <a name="unordered_maphash_function"></a><a name="hash"></a> unordered_map:: hash_function

Depolanan karma işlevi nesnesini alır.

```cpp
Hash hash_function() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, depolanan karma işlevi nesnesini döndürür.

### <a name="example"></a>Örnek

```cpp
// std__unordered_map__unordered_map_hash_function.cpp
// compile with: /EHsc
#include <unordered_map>
#include <iostream>

typedef std::unordered_map<char, int> Mymap;
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

## <a name="unordered_maphasher"></a><a name="hasher"></a> unordered_map:: hasher

Karma işlevin türü.

```cpp
typedef Hash hasher;
```

### <a name="remarks"></a>Açıklamalar

Tür, şablon parametresi için bir eş anlamlı `Hash` .

### <a name="example"></a>Örnek

```cpp
// std__unordered_map__unordered_map_hasher.cpp
// compile with: /EHsc
#include <unordered_map>
#include <iostream>

typedef std::unordered_map<char, int> Mymap;
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

## <a name="unordered_mapinsert"></a><a name="insert"></a> unordered_map:: INSERT

Bir unordered_map öğe veya öğe aralığı ekler.

```cpp
// (1) single element
pair<iterator, bool> insert(    const value_type& Val);

// (2) single element, perfect forwarded
template <class ValTy>
pair<iterator, bool>
insert(    ValTy&& Val);

// (3) single element with hint
iterator insert(    const_iterator Where,
    const value_type& Val);

// (4) single element, perfect forwarded, with hint
template <class ValTy>
iterator insert(    const_iterator Where,
    ValTy&& Val);

// (5) range
template <class InputIterator>
void insert(InputIterator First,
    InputIterator Last);

// (6) initializer list
void insert(initializer_list<value_type>
IList);
```

### <a name="parameters"></a>Parametreler

*Acil*\
Anahtarı equivalently olarak sıralanmış bir öğe içermiyorsa, unordered_map eklenecek öğenin değeri.

*Olmadığı*\
Doğru ekleme noktasını aramaya başlamak için yer.

*ValTy*\
Unordered_map, [value_type](../standard-library/map-class.md#value_type)bir öğesi oluşturmak için kullanabileceği bağımsız değişken türünü belirten şablon parametresi ve bağımsız değişken olarak *kusursuz iletme değeri* .

*Adı*\
Kopyalanacak ilk öğenin konumu.

*Soyadına*\
Kopyalanacak son öğenin hemen ötesinde konum.

*InputIterator*\
[Value_type](../standard-library/map-class.md#value_type) nesneleri oluşturmak için kullanılabilecek bir türün öğelerine işaret eden bir [giriş yineleyicisinin](../standard-library/input-iterator-tag-struct.md) gereksinimlerini karşılayan şablon işlevi bağımsız değişkeni.

*IList*\
Öğelerin kopyalanacağı [initializer_list](../standard-library/initializer-list.md) .

### <a name="return-value"></a>Dönüş Değeri

Tek öğeli üye işlevleri, (1) ve (2), [pair](../standard-library/pair-structure.md) **`bool`** bir ekleme yapılırsa bileşeni doğru olan bir çift döndürür ve unordered_map zaten anahtarı sıralamada denk bir değere sahip olan bir öğe içeriyorsa false. Return-Value çiftinin yineleyici bileşeni, bileşen true ise yeni ınsertedelement öğesine **`bool`** veya bileşen false ise var olan öğeye işaret eder **`bool`** .

Tek öğeli-ipucu üye işlevleri, (3) ve (4), yeni öğenin unordered_map eklendiği konuma ya da eşdeğer anahtara sahip bir öğe zaten varsa var olan öğeye işaret eden bir yineleyici döndürür.

### <a name="remarks"></a>Açıklamalar

Bu işlev tarafından hiçbir yineleyiciler, işaretçiler veya başvuru geçersiz kılınamaz.

Yalnızca bir öğenin eklenmesi sırasında, bir özel durum oluşturulursa, ancak kapsayıcının karma işlevinde gerçekleşmemişse kapsayıcının durumu değiştirilmez. Karma işlevde özel durum oluşturulursa, sonuç tanımsızdır. Birden çok öğenin eklenmesi sırasında, bir özel durum oluşturulursa, kapsayıcı belirtilmemiş ancak geçerli bir durumda bırakılır.

`pair` `pr` Tek öğeli üye işlevleri tarafından döndürülen bir ' ın Yineleyici bileşenine erişmek için, `pr.first` öğesini kullanın; döndürülen çiftin içindeki yineleyiciyi başvuru olarak kullanın `*pr.first` . Bileşene erişmek için **`bool`** kullanın `pr.second` . Örnek için, bu makalenin ilerleyen kısımlarında örnek koda bakın.

Kapsayıcının [value_type](../standard-library/map-class.md#value_type) , kapsayıcısına ait olan ve Map için olan bir typedef 'dir `map<K, V>::value_type` `pair<const K, V>` . Bir öğenin değeri, ilk bileşenin anahtar değere eşit olduğu ve ikinci bileşenin öğenin veri değerine eşit olduğu sıralı bir çiftidir.

Aralık üye işlevi (5), öğe değerlerinin dizisini aralıktaki bir yineleyici tarafından bahsedilen her öğeye karşılık gelen bir unordered_map ekler `[First, Last)` ; Bu nedenle, `Last` eklenmez. Kapsayıcı üye işlevi, `end()` kapsayıcıdaki son öğeden hemen sonra gelen konuma başvurur — Örneğin, ifade öğesine `m.insert(v.begin(), v.end());` tüm öğelerini eklemeye çalışır `v` `m` . Yalnızca aralıktaki benzersiz değerlere sahip öğeler eklenir; yinelemeler yoksayıldı. Hangi öğelerin reddedildiğini gözlemlemek için, öğesinin tek öğeli sürümlerini kullanın `insert` .

Başlatıcı listesi üye işlevi (6), öğeleri unordered_map kopyalamak için bir [initializer_list](../standard-library/initializer-list.md) kullanır.

Yerinde oluşturulmuş bir öğenin eklenmesi için — diğer bir deyişle, kopyalama veya taşıma işlemleri yapılmaz — [unordered_map:: emplace](#emplace) ve [unordered_map:: emplace_hint](#emplace_hint).

Kod örneği için bkz. [map:: insert](../standard-library/map-class.md#insert).

## <a name="unordered_mapiterator"></a><a name="iterator"></a> unordered_map:: Yineleyici

Denetlenen dizi için bir yineleyici türü.

```cpp
typedef T0 iterator;
```

### <a name="remarks"></a>Açıklamalar

Türü, denetimli sıra için ileri Yineleyici olarak işlev görebilecek bir nesne tanımlar. Burada uygulama tanımlı tür için bir eş anlamlı olarak açıklanmaktadır `T0` .

### <a name="example"></a>Örnek

```cpp
// std__unordered_map__unordered_map_iterator.cpp
// compile with: /EHsc
#include <unordered_map>
#include <iostream>

typedef std::unordered_map<char, int> Mymap;
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

## <a name="unordered_mapkey_eq"></a><a name="key_eq"></a> unordered_map:: key_eq

Depolanan karşılaştırma işlevi nesnesini alır.

```cpp
Pred key_eq() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, saklı karşılaştırma işlevi nesnesini döndürür.

### <a name="example"></a>Örnek

```cpp
// std__unordered_map__unordered_map_key_eq.cpp
// compile with: /EHsc
#include <unordered_map>
#include <iostream>

typedef std::unordered_map<char, int> Mymap;
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

## <a name="unordered_mapkey_equal"></a><a name="key_equal"></a> unordered_map:: key_equal

Karşılaştırma işlevinin türü.

```cpp
typedef Pred key_equal;
```

### <a name="remarks"></a>Açıklamalar

Tür, şablon parametresi için bir eş anlamlı `Pred` .

### <a name="example"></a>Örnek

```cpp
// std__unordered_map__unordered_map_key_equal.cpp
// compile with: /EHsc
#include <unordered_map>
#include <iostream>

typedef std::unordered_map<char, int> Mymap;
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

## <a name="unordered_mapkey_type"></a><a name="key_type"></a> unordered_map:: key_type

Bir sıralama anahtarının türü.

```cpp
typedef Key key_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, şablon parametresi için bir eş anlamlı `Key` .

### <a name="example"></a>Örnek

```cpp
// std__unordered_map__unordered_map_key_type.cpp
// compile with: /EHsc
#include <unordered_map>
#include <iostream>

typedef std::unordered_map<char, int> Mymap;
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

## <a name="unordered_mapload_factor"></a><a name="load_factor"></a> unordered_map:: load_factor

Demet başına ortalama öğeyi sayar.

```cpp
float load_factor() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi `(float)` [unordered_map:: size](#size) `() / (float)` [unordered_map:: bucket_count](#bucket_count) `()` , demet başına düşen ortalama öğe sayısını döndürür.

### <a name="example"></a>Örnek

```cpp
// std__unordered_map__unordered_map_load_factor.cpp
// compile with: /EHsc
#include <unordered_map>
#include <iostream>

typedef std::unordered_map<char, int> Mymap;
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

## <a name="unordered_maplocal_iterator"></a><a name="local_iterator"></a> unordered_map:: local_iterator

Demet yineleyicisinin türü.

```cpp
typedef T4 local_iterator;
```

### <a name="remarks"></a>Açıklamalar

Türü, bir demet için ileriye doğru Yineleyici işlevi görebilecek bir nesneyi tanımlar. Burada uygulama tanımlı tür için bir eş anlamlı olarak açıklanmaktadır `T4` .

### <a name="example"></a>Örnek

```cpp
// std__unordered_map__unordered_map_local_iterator.cpp
// compile with: /EHsc
#include <unordered_map>
#include <iostream>

typedef std::unordered_map<char, int> Mymap;
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

## <a name="unordered_mapmapped_type"></a><a name="mapped_type"></a> unordered_map:: mapped_type

Her bir anahtar ile ilişkili bir eşlenen değer türü.

```cpp
typedef Ty mapped_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, şablon parametresi için bir eş anlamlı `Ty` .

### <a name="example"></a>Örnek

```cpp
// std__unordered_map__unordered_map_mapped_type.cpp
// compile with: /EHsc
#include <unordered_map>
#include <iostream>

typedef std::unordered_map<char, int> Mymap;
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

## <a name="unordered_mapmax_bucket_count"></a><a name="max_bucket_count"></a> unordered_map:: max_bucket_count

En yüksek demet sayısını alır.

```cpp
size_type max_bucket_count() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, şu anda izin verilen en fazla demet sayısını döndürür.

### <a name="example"></a>Örnek

```cpp
// std__unordered_map__unordered_map_max_bucket_count.cpp
// compile with: /EHsc
#include <unordered_map>
#include <iostream>

typedef std::unordered_map<char, int> Mymap;
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

## <a name="unordered_mapmax_load_factor"></a><a name="max_load_factor"></a> unordered_map:: max_load_factor

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
// std__unordered_map__unordered_map_max_load_factor.cpp
// compile with: /EHsc
#include <unordered_map>
#include <iostream>

typedef std::unordered_map<char, int> Mymap;
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

## <a name="unordered_mapmax_size"></a><a name="max_size"></a> unordered_map:: max_size

Denetlenen dizinin en büyük boyutunu alır.

```cpp
size_type max_size() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, nesnenin denetleyecan en uzun sırasının uzunluğunu döndürür.

### <a name="example"></a>Örnek

```cpp
// std__unordered_map__unordered_map_max_size.cpp
// compile with: /EHsc
#include <unordered_map>
#include <iostream>

typedef std::unordered_map<char, int> Mymap;
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

## <a name="unordered_mapoperator"></a><a name="op_at"></a> unordered_map:: operator []

Belirtilen anahtarı içeren bir öğe bulur veya ekler.

```cpp
Ty& operator[](const Key& keyval);

Ty& operator[](Key&& keyval);
```

### <a name="parameters"></a>Parametreler

*Keyval*\
Bulmak veya eklemek için anahtar değeri.

### <a name="return-value"></a>Dönüş Değeri

Eklenen öğenin veri değerine başvuru.

### <a name="remarks"></a>Açıklamalar

Bağımsız değişken anahtar değeri bulunamazsa, değer veri türünün varsayılan değeriyle birlikte eklenir.

`operator[]` , *bir Map 'e* , *k*[*Key*] =; kullanarak öğe eklemek Için kullanılabilir `DataValue` ; burada anahtar `DataValue` `mapped_type` değeri *anahtar*olan öğenin değeridir.

`operator[]`Öğeleri eklemek için kullanırken, döndürülen başvuru, bir eklentinin önceden varolan bir öğeyi değiştirip değiştirmediğini veya yeni bir tane oluşturmadığını göstermez. [Bul](../standard-library/map-class.md#find) ve [Ekle](../standard-library/map-class.md#insert) üye işlevleri, bir ekleme işleminden önce belirtilen anahtara sahip bir öğenin zaten mevcut olup olmadığını anlamak için kullanılabilir.

### <a name="example"></a>Örnek

```cpp
// std__unordered_map__unordered_map_operator_sub.cpp
// compile with: /EHsc
#include <unordered_map>
#include <iostream>
#include <string>

typedef std::unordered_map<char, int> Mymap;
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
    std::cout << "c1['A'] == " << c1['A'] << std::endl;

// try to find and succeed
    std::cout << "c1['a'] == " << c1['a'] << std::endl;

// redisplay contents
    for (Mymap::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << " [" << it->first << ", " << it->second << "]";
    std::cout << std::endl;

// insert by moving key
    std::unordered_map<string, int> c2;
    std::string str("abc");
    std::cout << "c2[std::move(str)] == " << c2[std::move(str)] << std::endl;
    std::cout << "c2["abc"] == " << c2["abc"] << std::endl;

    return (0);
    }
```

```Output
[c, 3] [b, 2] [a, 1]
c1['A'] == 0
c1['a'] == 1
[c, 3] [b, 2] [A, 0] [a, 1]
c2[move(str)] == 0
c2["abc"] == 1
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi yineleyiciyi `where` [unordered_map:: INSERT](#insert) `(` [unordered_map:: value_type](#value_type)dönüş değeri olarak belirler `(keyval, Ty())` . (Böyle bir öğe yoksa, belirtilen anahtara sahip bir öğe ekler.) Daha sonra öğesine bir başvuru döndürür `(*where).second` .

## <a name="unordered_mapoperator"></a><a name="op_eq"></a> unordered_map:: operator =

Bu unordered_map öğelerini başka bir unordered_map öğeleri kullanarak değiştirir.

```cpp
unordered_map& operator=(const unordered_map& right);

unordered_map& operator=(unordered_map&& right);
```

### <a name="parameters"></a>Parametreler

*Right*\
İşleç işlevinin içeriği atadığı unordered_map.

### <a name="remarks"></a>Açıklamalar

İlk sürüm tüm öğeleri *sağdan* Bu unordered_map kopyalar.

İkinci sürüm tüm öğeleri *sağdan* Bu unordered_map kaydırır.

Yürütmeden önce Bu unordered_map olan tüm öğeler `operator=` atılır.

### <a name="example"></a>Örnek

```cpp
// unordered_map_operator_as.cpp
// compile with: /EHsc
#include <unordered_map>
#include <iostream>

int main( )
   {
   using namespace std;
   unordered_map<int, int> v1, v2, v3;
   unordered_map<int, int>::iterator iter;

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

## <a name="unordered_mappointer"></a><a name="pointer"></a> unordered_map::p oınter

Bir öğe için bir işaretçi türü.

```cpp
typedef Alloc::pointer pointer;
```

### <a name="remarks"></a>Açıklamalar

Türü, denetlenen sıranın bir öğesi için bir işaretçi olarak işlev görebilecek bir nesneyi tanımlar.

### <a name="example"></a>Örnek

```cpp
// std__unordered_map__unordered_map_pointer.cpp
// compile with: /EHsc
#include <unordered_map>
#include <iostream>

typedef std::unordered_map<char, int> Mymap;
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

## <a name="unordered_mapreference"></a><a name="reference"></a> unordered_map:: Reference

Bir öğe için bir başvuru türü.

```cpp
typedef Alloc::reference reference;
```

### <a name="remarks"></a>Açıklamalar

Türü, denetlenen sıranın bir öğesine başvuru olarak işlev görebilecek bir nesne tanımlar.

### <a name="example"></a>Örnek

```cpp
// std__unordered_map__unordered_map_reference.cpp
// compile with: /EHsc
#include <unordered_map>
#include <iostream>

typedef std::unordered_map<char, int> Mymap;
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

## <a name="unordered_maprehash"></a><a name="rehash"></a> unordered_map:: yeniden karma

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
// std__unordered_map__unordered_map_rehash.cpp
// compile with: /EHsc
#include <unordered_map>
#include <iostream>

typedef std::unordered_map<char, int> Mymap;
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

## <a name="unordered_mapsize"></a><a name="size"></a> unordered_map:: size

Öğe sayısını sayar.

```cpp
size_type size() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi denetlenen sıranın uzunluğunu döndürür.

### <a name="example"></a>Örnek

```cpp
// std__unordered_map__unordered_map_size.cpp
// compile with: /EHsc
#include <unordered_map>
#include <iostream>

typedef std::unordered_map<char, int> Mymap;
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

## <a name="unordered_mapsize_type"></a><a name="size_type"></a> unordered_map:: size_type

İki öğe arasındaki işaretsiz bir mesafenin türü.

```cpp
typedef T2 size_type;
```

### <a name="remarks"></a>Açıklamalar

İşaretsiz tamsayı türü, denetlenen bir dizinin uzunluğunu temsil eden bir nesneyi tanımlar. Burada uygulama tanımlı tür için bir eş anlamlı olarak açıklanmaktadır `T2` .

### <a name="example"></a>Örnek

```cpp
// std__unordered_map__unordered_map_size_type.cpp
// compile with: /EHsc
#include <unordered_map>
#include <iostream>

typedef std::unordered_map<char, int> Mymap;
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

## <a name="unordered_mapswap"></a><a name="swap"></a> unordered_map:: swap

İki kapsayıcının içeriğinin yerini değiştirir.

```cpp
void swap(unordered_map& right);
```

### <a name="parameters"></a>Parametreler

*Right*\
İle takas edilecek kapsayıcı.

### <a name="remarks"></a>Açıklamalar

Üye işlevi, ve sağ arasındaki denetlenen dizileri **`*this`** değiştirir *right*. [Unordered_map:: get_allocator](#get_allocator) `() == right.get_allocator()` , bu, sabit bir zamanda, yalnızca türünde depolanan nitelikler nesnesini kopyalamanın bir sonucu olarak bir özel durum oluşturur `Tr` ve iki denetimli sırada öğeleri belirten başvuruları, işaretçileri veya yineleyicileri geçersiz kılar. Aksi takdirde, bir dizi öğe ataması ve Oluşturucu çağrısı, iki denetimli dizi içindeki öğe sayısıyla orantılı olarak gerçekleştirilir.

### <a name="example"></a>Örnek

```cpp
// std__unordered_map__unordered_map_swap.cpp
// compile with: /EHsc
#include <unordered_map>
#include <iostream>

typedef std::unordered_map<char, int> Mymap;
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

## <a name="unordered_mapunordered_map"></a><a name="unordered_map"></a> unordered_map:: unordered_map

Bir kapsayıcı nesnesi oluşturur.

```cpp
unordered_map(const unordered_map& Right);

explicit unordered_map(
    size_type Bucket_count = N0,
    const Hash& Hash = Hash(),
    const Comp& Comp = Comp(),
    const Allocator& Al = Allocator());

unordered_map(unordered_map&& Right);
unordered_map(initializer_list<Type> IList);
unordered_map(initializer_list<Type> IList, size_type Bucket_count);

unordered_map(
    initializer_list<Type> IList,
    size_type Bucket_count,
    const Hash& Hash);

unordered_map(
    initializer_list<Type> IList,
    size_type Bucket_count,
    const Hash& Hash,
    KeyEqual& equal);

unordered_map(
    initializer_list<Type> IList,
    size_type Bucket_count,
    const Hash& Hash,
    KeyEqual& Equal
    const Allocator& Al);

template <class InIt>
unordered_map(
    InputIterator First,
    InputIterator Last,
    size_type Bucket_count = N0,
    const Hash& Hash = Hash(),
    const Comp& Comp = Comp(),
    const Allocator& Al = Alloc());
```

### <a name="parameters"></a>Parametreler

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

*Adı*\
Kopyalanacak ilk öğenin konumu.

*Soyadına*\
Kopyalanacak son öğenin hemen ötesinde konum.

*IList*\
Kopyalanacak öğeleri içeren initializer_list.

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu tarafından denetlenen sıranın bir kopyasını belirtir `right` . İkinci oluşturucu boş bir denetlenmiş dizi belirtir. Üçüncü Oluşturucu öğe değerlerinin dizisini ekler `[first, last)` . Dördüncü Oluşturucu taşıyarak sıranın bir kopyasını belirtir `right` .

Ayrıca, tüm oluşturucular çeşitli depolanmış değerleri başlatır. Kopya Oluşturucu için değerler *sağdan*alınır. Aksi durumda:.

varsa, en düşük demet sayısı *Bucket_count*bağımsız değişkendir; Aksi takdirde, burada uygulama tanımlı değer olarak açıklanan varsayılan bir değerdir `N0` .

karma işlev nesnesi varsa bağımsız değişken *karmasıdır*; Aksi takdirde, `Hash()` .

Karşılaştırma işlevi nesnesi, varsa, *comp*bağımsız değişkenidir; Aksi takdirde, `Pred()` .

Ayırıcı nesne varsa *Al*bağımsız değişkenidir; Aksi takdirde, `Alloc()` .

### <a name="example"></a>Örnek

```cpp
// std__unordered_map__unordered_map_construct.cpp
// compile with: /EHsc
#include <unordered_map>
#include <iostream>
#include <initializer_list>

using namespace std;

using Mymap = unordered_map<char, int>;

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
    cout << endl;

    // Construct with an initializer_list
    unordered_map<int, char> c5({ { 5, 'g' }, { 6, 'h' }, { 7, 'i' }, { 8, 'j' } });
    for (const auto& c : c5) {
        cout << " [" << c.first << ", " << c.second << "]";
    }
    cout << endl;

    // Initializer_list plus size
    unordered_map<int, char> c6({ { 5, 'g' }, { 6, 'h' }, { 7, 'i' }, { 8, 'j' } }, 4);
    for (const auto& c : c1) {
        cout << " [" << c.first << ", " << c.second << "]";
    }
    cout << endl;
    cout << endl;

    // Initializer_list plus size and hash
    unordered_map<int, char, hash<char>> c7(
        { { 5, 'g' }, { 6, 'h' }, { 7, 'i' }, { 8, 'j' } },
        4,
        hash<char>()
    );

    for (const auto& c : c1) {
        cout << " [" << c.first << ", " << c.second << "]";
    }
    cout << endl;

    // Initializer_list plus size, hash, and key_equal
    unordered_map<int, char, hash<char>, equal_to<char>> c8(
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
    unordered_map<int, char, hash<char>, equal_to<char>> c9(
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
[a, 1] [b, 2] [c, 3]
[d, 4] [e, 5] [f, 6]
[a, 1] [b, 2] [c, 3]
[a, 1] [b, 2] [c, 3]

[5, g] [6, h] [7, i] [8, j]
[a, 1] [b, 2] [c, 3]

[a, 1] [b, 2] [c, 3]
[a, 1] [b, 2] [c, 3]
[a, 1] [b, 2] [c, 3]
```

## <a name="unordered_mapvalue_type"></a><a name="value_type"></a> unordered_map:: value_type

Öğenin türü.

```cpp
typedef std::pair<const Key, Ty> value_type;
```

### <a name="remarks"></a>Açıklamalar

Tür denetimli sıranın bir öğesini açıklar.

### <a name="example"></a>Örnek

```cpp
// std__unordered_map__unordered_map_value_type.cpp
// compile with: /EHsc
#include <unordered_map>
#include <iostream>

typedef std::unordered_map<char, int> Mymap;
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
