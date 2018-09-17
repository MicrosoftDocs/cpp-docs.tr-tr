---
title: unordered_multimap sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 52073a97e062d4ab96e50fed534edc24add0f8c5
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45715604"
---
# <a name="unorderedmultimap-class"></a>unordered_multimap Sınıfı

Şablon sınıfı bir türdeki öğelerin değişen uzunluktaki dizisini denetleyen bir nesneyi tanımlayan `std::pair<const Key, Ty>`. Dizi çağrılan demetlerin sıralı bir dizi kümesini bölümleyen bir karma işlev tarafından zayıf bir şekilde sıralanır. Her bir demette herhangi bir öğe çiftinin eşdeğer sıralamaya sahip olup olmadığını belirleyen bir karşılaştırma işlevi vardır. Her bir öğe iki nesne, bir sıralama anahtarı ve bir değer depolar. Dizi, en azından tüm demetleri kabaca eşit uzunlukta olduğunda, dizideki (sabit zaman) öğe sayısından bağımsız olabilen işlem sayısına sahip rastgele bir öğenin aranması, eklenmesi ve kaldırılmasına izin verecek şekilde temsil edilir. En kötü durumda, tüm öğeler tek bir demet içinde olduğunda işlem sayısı dizideki (doğrusal zaman) öğelerin sayısıyla orantılıdır. Ayrıca, bir öğe eklenmesi hiçbir yineleyiciyi geçersiz kılmaz; bir öğenin kaldırılması yalnızca bu kaldırılan öğeyi gösteren yineleyicileri geçersiz kılar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Key,
    class Ty,
    class Hash = std::hash<Key>,
    class Pred = std::equal_to<Key>,
    class Alloc = std::allocator<Key>>
class unordered_multimap;
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|-|-|
|*Key*|Anahtar türü.|
|*Ty*|Eşlenen tür.|
|*Karma*|Karma işlev nesne türü.|
|*Pred*|Eşitlik karşılaştırma işlevi nesne türü.|
|*Ayırma*|Ayırıcı sınıf.|

## <a name="members"></a>Üyeler

|Tür Tanımlaması|Açıklama|
|-|-|
|[allocator_type](#allocator_type)|Depolamayı yönetmek için bir ayırıcı türü.|
|[const_iterator](#const_iterator)|Denetlenen dizi için bir sabit yineleyici türü.|
|[const_local_iterator](#const_local_iterator)|Denetlenen dizi için bir sabit demet yineleyici türü.|
|[const_pointer](#const_pointer)|Bir öğe için sabit bir işaretçi türü.|
|[const_reference](#const_reference)|Bir öğe için sabit bir başvuru türü.|
|[difference_type](#difference_type)|İki öğe arasındaki işaretli mesafenin türü.|
|[karma değeri Oluşturucusu](#hasher)|Karma işlevin türü.|
|[Yineleyici](#iterator)|Denetlenen dizi için bir yineleyici türü.|
|[key_equal](#key_equal)|Karşılaştırma işlevinin türü.|
|[key_type](#key_type)|Bir sıralama anahtarının türü.|
|[local_iterator](#local_iterator)|Denetlenen dizi için bir demet yineleyici türü.|
|[mapped_type](#mapped_type)|Her bir anahtar ile ilişkili bir eşlenen değer türü.|
|[İşaretçi](#pointer)|Bir öğe için bir işaretçi türü.|
|[Başvuru](#reference)|Bir öğe için bir başvuru türü.|
|[size_type](#size_type)|İki öğe arasındaki işaretsiz bir mesafenin türü.|
|[value_type](#value_type)|Öğenin türü.|

|Üye İşlevi|Açıklama|
|-|-|
|[başlayın](#begin)|Denetlenen dizinin başlangıcını belirtir.|
|[Demet](#bucket)|Bir anahtar değeri için demet numarasını alır.|
|[bucket_count](#bucket_count)|Demet sayısını alır.|
|[bucket_size](#bucket_size)|Demet boyutunu alır.|
|[cbegin](#cbegin)|Denetlenen dizinin başlangıcını belirtir.|
|[cend](#cend)|Denetlenen dizinin bitişini belirtir.|
|[Temizle](#clear)|Tüm öğeleri kaldırır.|
|[Sayısı](#count)|Belirtilen bir anahtar ile eşleşen öğe sayısını bulur.|
|[emplace](#emplace)|Yerinde oluşturulmuş bir öğe ekler.|
|[emplace_hint](#emplace_hint)|Göstergeyle birlikte, yerinde oluşturulmuş bir öğe ekler.|
|[boş](#empty)|Bir öğe olup olmadığını sınar.|
|[Son](#end)|Denetlenen dizinin bitişini belirtir.|
|[equal_range](#equal_range)|Belirtilen bir anahtarla eşleşen aralığı bulur.|
|[silme](#erase)|Belirtilen konumlardaki öğeleri kaldırır.|
|[Bul](#find)|Belirtilen bir anahtarla eşleşen bir öğeyi bulur.|
|[get_allocator](#get_allocator)|Depolanan ayırıcı nesnesini alır.|
|[hash_function](#hash)|Depolanan karma işlevi nesnesini alır.|
|[Ekle](#insert)|Öğeleri ekler.|
|[key_eq](#key_eq)|Depolanan karşılaştırma işlevi nesnesini alır.|
|[load_factor](#load_factor)|Demet başına ortalama öğeyi sayar.|
|[max_bucket_count](#max_bucket_count)|En yüksek demet sayısını alır.|
|[max_load_factor](#max_load_factor)|Demet başına en yüksek öğe sayısını alır veya ayarlar.|
|[max_size](#max_size)|Denetlenen dizinin en büyük boyutunu alır.|
|[rehash](#rehash)|Karma tabloyu yeniden oluşturur.|
|[Boyutu](#size)|Öğe sayısını sayar.|
|[değiştirme](#swap)|İki kapsayıcının içeriğinin yerini değiştirir.|
|[unordered_multimap](#unordered_multimap)|Bir kapsayıcı nesnesi oluşturur.|

|İşleç|Açıklama|
|-|-|
|[unordered_multimap::operator =](#op_eq)|Bir karma tabloya kopyalar.|

## <a name="remarks"></a>Açıklamalar

Nesne depolanan iki nesneyi, türünde bir karşılaştırma işlev nesnesi çağırarak denetlediği diziyi sıralar [unordered_multimap::key_equal](#key_equal) ve karma işlev nesne türü [unordered_multimap::hasher](#hasher). Üye işlevini çağırarak depolanan birinci nesneye erişim [unordered_multimap::key_eq](#key_eq)`()`; ve üye işlevini çağırarak depolanan ikinci nesneye erişebilirsiniz [unordered_multimap::hash_ işlev](#hash)`()`. Tüm değerler için özellikle `X` ve `Y` türü `Key`, çağrı `key_eq()(X, Y)` yalnızca iki bağımsız değişken eşdeğer sıralamaya sahipse true değerini döndürür; çağrı `hash_function()(keyval)` türündebirdeğerlerdağıtımıverir`size_t`. Şablon sınıfının aksine [unordered_map sınıfı](../standard-library/unordered-map-class.md), şablon sınıfın bir nesnesi `unordered_multimap` emin olmaz `key_eq()(X, Y)` her zaman değerinin denetlenen dizideki herhangi iki öğe için yanlış. (Anahtarlarının benzersiz olması gerekmez.)

Nesne ayrıca, demet başına istenen ortalama öğe sayısını belirten en yüksek yük faktörünü depolar. Bir öğe eklenmesi neden olursa [unordered_multimap::load_factor](#load_factor) `()` en yüksek yük faktörünün aşılmasına, kapsayıcı demet sayısını artırır ve gerektiğinde karma tabloyu yeniden oluşturur.

Denetlenen dizideki öğelerin gerçek sırası karma işleve, karşılaştırma işlevine, ekleme sırasına, en yüksek yük faktörüne ve geçerli demet sayısına bağlıdır. Denetlenen dizideki öğelerin sırasını genelde tahmin edemezsiniz. Ancak, eşdeğer sıralamaya sahip öğelerin herhangi bir alt kümesinin her zaman denetlenen dizide bitişik olduğundan emin olabilirsiniz.

Nesneyi ayırır ve boşaltır türünde bir saklı ayırıcı nesnesi denetlediği dizi için depolama [unordered_multimap::allocator_type](#allocator_type). Böyle bir ayırıcı nesnenin şablon sınıfının bir nesnesiyle aynı dış arayüze sahip olması gerekir `allocator`. Depolanan ayırıcı nesnenin kapsayıcı nesne atandığında kopyalanmayacağını unutmayın.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<unordered_map >

**Namespace:** std

## <a name="allocator_type"></a>  unordered_multimap::allocator_type

Depolamayı yönetmek için bir ayırıcı türü.

```cpp
typedef Alloc allocator_type;
```

### <a name="remarks"></a>Açıklamalar

Şablon parametresi için bir eşanlamlı türüdür `Alloc`.

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

## <a name="begin"></a>  unordered_multimap::Begin

Denetlenen dizi veya bir demet başına belirler.

```cpp
iterator begin();

const_iterator begin() const;


local_iterator begin(size_type nbucket);

const_local_iterator begin(size_type nbucket) const;
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|-|-|
|*nbucket*|Demet sayısı.|

### <a name="remarks"></a>Açıklamalar

İlk iki üye işlev bu noktalarda ilk öğe dizisi (veya yalnızca boş bir dizi bitiminin ötesinde) ileriye doğru bir yineleyici döndürür. Son iki üye işlevleri bu noktalarda bir demet ilk öğesi ileriye doğru yineleyiciyi döndürür *nbucket* (veya yalnızca boş bir demet bitiminin ötesinde).

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

## <a name="bucket"></a>  unordered_multimap::Bucket

Bir anahtar değeri için demet numarasını alır.

```cpp
size_type bucket(const Key& keyval) const;
```

### <a name="parameters"></a>Parametreler

*keyval*<br/>
Eşlenecek anahtar değeri.

### <a name="remarks"></a>Açıklamalar

Üye işlevi şu anda anahtar değerine karşılık gelen demet numarasını döndürür *keyval*.

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

## <a name="bucket_count"></a>  unordered_multimap::bucket_count

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

## <a name="bucket_size"></a>  unordered_multimap::bucket_size

Demet boyutunu alır.

```cpp
size_type bucket_size(size_type nbucket) const;
```

### <a name="parameters"></a>Parametreler

*nbucket*<br/>
Demet sayısı.

### <a name="remarks"></a>Açıklamalar

Üye işlevleri, demet numarasını boyutunu döndürür *nbucket*.

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

## <a name="cbegin"></a>  unordered_multimap::cbegin

Döndürür bir **const** aralıktaki ilk öğeyi adresleyen bir yineleyici.

```cpp
const_iterator cbegin() const;
```

### <a name="return-value"></a>Dönüş Değeri

A **const** aralığı veya konuma boş bir aralığın ilk öğesine konumundaki ileriye doğru erişim yineleyicisi (boş bir aralık için `cbegin() == cend()`).

### <a name="remarks"></a>Açıklamalar

Dönüş değeri ile `cbegin`, aralıktaki öğeler değiştirilemez.

Bu üye işlevi yerine kullanabileceğiniz `begin()` üye işlev dönüş değeri olacağını garanti etmek için `const_iterator`. Genellikle birlikte kullanılır [otomatik](../cpp/auto-cpp.md) kesinti anahtar sözcüğü, aşağıdaki örnekte gösterildiği gibi yazın. Örnekte, göz önünde bulundurun `Container` değiştirilebilir (olmayan **const**) destekleyen herhangi bir türdeki kapsayıcı `begin()` ve `cbegin()`.

```cpp
auto i1 = Container.begin();
// i1 is Container<T>::iterator
auto i2 = Container.cbegin();

// i2 is Container<T>::const_iterator
```

## <a name="cend"></a>  unordered_multimap::cend

Döndürür bir **const** konuma bir aralıktaki son öğeyi ele alan bir yineleyici.

```cpp
const_iterator cend() const;
```

### <a name="return-value"></a>Dönüş Değeri

A **const** aralığın sonunu yalnızca ileri erişim yineleyicisi.

### <a name="remarks"></a>Açıklamalar

`cend` bir yineleyicinin kendi aralığının sonunu geçmediğini sınamak için kullanılır.

Bu üye işlevi yerine kullanabileceğiniz `end()` üye işlev dönüş değeri olacağını garanti etmek için `const_iterator`. Genellikle birlikte kullanılır [otomatik](../cpp/auto-cpp.md) kesinti anahtar sözcüğü, aşağıdaki örnekte gösterildiği gibi yazın. Örnekte, göz önünde bulundurun `Container` değiştirilebilir (olmayan **const**) destekleyen herhangi bir türdeki kapsayıcı `end()` ve `cend()`.

```cpp
auto i1 = Container.end();
// i1 is Container<T>::iterator
auto i2 = Container.cend();

// i2 is Container<T>::const_iterator
```

Tarafından döndürülen değer `cend` kaldırılmamalıdır.

## <a name="clear"></a>  unordered_multimap::Clear

Tüm öğeleri kaldırır.

```cpp
void clear();
```

### <a name="remarks"></a>Açıklamalar

Üye işlev çağrıları [unordered_multimap::erase](#erase) `(` [unordered_multimap::begin](#begin) `(),` [unordered_multimap::end](#end) `())`.

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

## <a name="const_iterator"></a>  unordered_multimap::const_iterator

Denetlenen dizi için bir sabit yineleyici türü.

```cpp
typedef T1 const_iterator;
```

### <a name="remarks"></a>Açıklamalar

Denetlenen dizi için sabit bir ileriye doğru yineleyici olarak hizmet verebilen bir nesneyi tanımlayan bir tür. Açıklanmıştır uygulama tanımlı türünün eşanlamlısı olarak burada `T1`.

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

## <a name="const_local_iterator"></a>  unordered_multimap::const_local_iterator

Denetlenen dizi için bir sabit demet yineleyici türü.

```cpp
typedef T5 const_local_iterator;
```

### <a name="remarks"></a>Açıklamalar

Bir demet için sabit bir ileriye doğru yineleyici olarak hizmet verebilen bir nesneyi tanımlayan bir tür. Açıklanmıştır uygulama tanımlı türünün eşanlamlısı olarak burada `T5`.

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

## <a name="const_pointer"></a>  unordered_multimap::const_pointer

Bir öğe için sabit bir işaretçi türü.

```cpp
typedef Alloc::const_pointer const_pointer;
```

### <a name="remarks"></a>Açıklamalar

Denetlenen dizinin bir öğe için sabit bir işaretçi olarak hizmet verebilen bir nesneyi tanımlayan bir tür.

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

## <a name="const_reference"></a>  unordered_multimap::const_reference

Bir öğe için sabit bir başvuru türü.

```cpp
typedef Alloc::const_reference const_reference;
```

### <a name="remarks"></a>Açıklamalar

Denetlenen dizinin bir öğe için sabit bir başvuru olarak hizmet verebilen bir nesneyi tanımlayan bir tür.

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

## <a name="count"></a>  unordered_multimap::Count

Belirtilen bir anahtar ile eşleşen öğe sayısını bulur.

```cpp
size_type count(const Key& keyval) const;
```

### <a name="parameters"></a>Parametreler

*keyval*<br/>
Aranacak anahtar değeri.

### <a name="remarks"></a>Açıklamalar

Üye işlevi tarafından ayrılmış aralıktaki öğelerin sayısını döndürür. [unordered_multimap::equal_range](#equal_range)`(keyval)`.

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

## <a name="difference_type"></a>  unordered_multimap::difference_type

İki öğe arasındaki işaretli mesafenin türü.

```cpp
typedef T3 difference_type;
```

### <a name="remarks"></a>Açıklamalar

İmzalı bir tamsayı türü adreslerini denetlenen dizideki herhangi iki öğe arasındaki farkı temsil edebilen bir nesneyi tanımlar. Açıklanmıştır uygulama tanımlı türünün eşanlamlısı olarak burada `T3`.

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

## <a name="emplace"></a>  unordered_multimap::emplace

(Hiçbir kopyalama veya taşıma işlemleri gerçekleştirilir) bir yerleşim ipucuyla birlikte yerinde oluşturulmuş bir öğe ekler.

```cpp
template <class... Args>
iterator emplace(Args&&... args);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|-|-|
|*bağımsız değişken*|Unordered_multimap eklenecek bir öğe oluşturmak için iletilen bağımsız değişkenler.|

### <a name="return-value"></a>Dönüş Değeri

Yeni eklenen öğeye bir yineleyici.

### <a name="remarks"></a>Açıklamalar

Bu işlev tarafından geçersiz kılınan kapsayıcı öğeleri için başvuru ancak kapsayıcıya tüm yineleyiciler geçersiz kılabilir.

[Value_type](../standard-library/map-class.md#value_type) böylece bir öğenin değerini sıralı bir çift anahtar değerine eşit olan ilk bileşen ve saniye bileşenini öğenin veri değerine eşit olan bir çift öğesidir.

Bir özel durum oluşturulur ancak kapsayıcının karma işlevi gerçekleşmez kapsayıcı ekleme sırasında değiştirilmez. Karma işlev özel durum, sonuç tanımsızdır.

Kod örneği için bkz: [multimap::emplace](../standard-library/multimap-class.md#emplace).

## <a name="emplace_hint"></a>  unordered_multimap::emplace_hint

(Hiçbir kopyalama veya taşıma işlemleri gerçekleştirilir) bir yerleşim ipucuyla birlikte yerinde oluşturulmuş bir öğe ekler.

```cpp
template <class... Args>
iterator emplace_hint(
    const_iterator where,
    Args&&... args);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|-|-|
|*bağımsız değişken*|Bağımsız değişkenler iletilen eklenecek bir öğe oluşturmak için sırasız içine.|
|*Burada*|Doğru ekleme noktasını için aramaya başlamak için yer ile ilgili bir ipucu.|

### <a name="return-value"></a>Dönüş Değeri

Yeni eklenen öğeye bir yineleyici.

### <a name="remarks"></a>Açıklamalar

Bu işlev tarafından geçersiz kılınan kapsayıcı öğeleri için başvuru ancak kapsayıcıya tüm yineleyiciler geçersiz kılabilir.

Bir özel durum oluşturulur ancak kapsayıcının karma işlevi gerçekleşmez kapsayıcı ekleme sırasında değiştirilmez. Karma işlev özel durum, sonuç tanımsızdır.

[Value_type](../standard-library/map-class.md#value_type) böylece bir öğenin değerini sıralı bir çift anahtar değerine eşit olan ilk bileşen ve saniye bileşenini öğenin veri değerine eşit olan bir çift öğesidir.

Kod örneği için bkz: [map::emplace_hint](../standard-library/map-class.md#emplace_hint).

## <a name="empty"></a>  unordered_multimap::empty

Bir öğe olup olmadığını sınar.

```cpp
bool empty() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi boş bir denetlenmiş dizi için true değerini döndürür.

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

## <a name="end"></a>  unordered_multimap::End

Denetlenen dizinin bitişini belirtir.

```cpp
iterator end();

const_iterator end() const;


local_iterator end(size_type nbucket);

const_local_iterator end(size_type nbucket) const;
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|-|-|
|*nbucket*|Demet sayısı.|

### <a name="remarks"></a>Açıklamalar

İlk iki üye işlevleri, son sırasının hemen ötesine işaret eden ileriye doğru bir yineleyici döndürür. Son iki üye işlevleri demetine sonuna hemen ötesine işaret eden ileriye doğru yineleyiciyi döndürür *nbucket*.

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

## <a name="equal_range"></a>  unordered_multimap::equal_range

Belirtilen bir anahtarla eşleşen aralığı bulur.

```cpp
std::pair<iterator, iterator>
    equal_range(const Key& keyval);

std::pair<const_iterator, const_iterator>
    equal_range(const Key& keyval) const;
```

### <a name="parameters"></a>Parametreler

*keyval*<br/>
Aranacak anahtar değeri.

### <a name="remarks"></a>Açıklamalar

Üye işlevi Yineleyicilerin bir çiftini döndürür `X` şekilde `[X.first, X.second)` yalnızca öğeleri ile eşdeğer sıralamaya sahip denetlenen dizinin sınırlandırır *keyval*. Böyle bir öğe varsa, her iki yineleyiciler olan `end()`.

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

## <a name="erase"></a>  unordered_multimap::ERASE

Bir öğenin veya öğelerin aralığını belirtilen konumlardan bir unordered_multimap kaldırır veya belirtilen bir anahtarla eşleşen öğeleri kaldırır.

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

*Burada*<br/>
Kaldırılacak öğenin konumu.

*ilk*<br/>
Kaldırılacak ilk öğenin konumu.

*Son*<br/>
Kaldırılacak yalnızca son öğenin ötesinde konumu.

*Key*<br/>
Kaldırılacak öğe anahtar değeri.

### <a name="return-value"></a>Dönüş Değeri

İlk iki üye işlevleri için çift yönlü bir yineleyici, kaldırılan herhangi bir öğe veya böyle bir öğe yoksa eşleme sonuna bir öğeyi ilk öğeyi belirtir.

Üye işlevi için üçüncü unordered_multimap kaldırılan öğelerin sayısını döndürür.

### <a name="remarks"></a>Açıklamalar

Kod örneği için bkz: [map::erase](../standard-library/map-class.md#erase).

## <a name="find"></a>  unordered_multimap::Find

Belirtilen bir anahtarla eşleşen bir öğeyi bulur.

```cpp
const_iterator find(const Key& keyval) const;
```

### <a name="parameters"></a>Parametreler

*keyval*<br/>
Aranacak anahtar değeri.

### <a name="remarks"></a>Açıklamalar

Üye işlevinin döndürdüğü [unordered_multimap::equal_range](#equal_range)`(keyval).first`.

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

## <a name="get_allocator"></a>  unordered_multimap::get_allocator

Depolanan ayırıcı nesnesini alır.

```cpp
Alloc get_allocator() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi saklı ayırıcı nesnesini döndürür.

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

## <a name="hash"></a>  unordered_multimap::hash_function

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

## <a name="hasher"></a>  unordered_multimap::hasher

Karma işlevin türü.

```cpp
typedef Hash hasher;
```

### <a name="remarks"></a>Açıklamalar

Şablon parametresi için bir eşanlamlı türüdür `Hash`.

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

## <a name="insert"></a>  unordered_multimap::insert

Bir öğenin veya öğelerin aralığını bir unordered_multimap ekler.

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

|Parametre|Açıklama|
|-|-|
|*VAL*|Unordered_multimap eklenecek bir öğenin değeri.|
|*Burada*|Doğru ekleme noktasını için aramaya başlamak için bir yerde.|
|*ValTy*|Unordered_multimap öğesi oluşturmak için kullanabileceğiniz bağımsız değişken türü belirten bir şablon parametresi [value_type](../standard-library/map-class.md#value_type)ve mükemmel ileten *Val* bağımsız değişken olarak.|
|*ilk*|Kopyalanacak ilk öğenin konumu.|
|*Son*|Kopyalanacak son öğenin ötesinde konumu.|
|*Inputıterator*|Gereksinimlerini karşılayan şablonu işlev bağımsız değişkeni bir [giriş yineleyici](../standard-library/input-iterator-tag-struct.md) oluşturmak için kullanılan bir tür öğelerine işaret eden [value_type](../standard-library/map-class.md#value_type) nesneleri.|
|*IList*|[İnitializer_list](../standard-library/initializer-list.md) öğeleri kopyalanacak.|

### <a name="return-value"></a>Dönüş Değeri

Tek öğe ekleme üye işlevleri (1) ve (2), burada yeni bir öğe unordered_multimap eklenmiş konumuna bir yineleyici döndürür.

İpucu ile tek öğe üye işlevleri, (3) ve (4), yeni bir öğe unordered_multimap eklenir burada konumu gösteren bir yineleyici döndürür.

### <a name="remarks"></a>Açıklamalar

Hiçbir işaretçileri veya başvuruları bu işlev tarafından geçersiz kılınan ancak kapsayıcıya tüm yineleyiciler geçersiz kılabilir.

Bir özel durum oluşturulur ancak kapsayıcının karma işlevi gerçekleşmez yalnızca bir öğe ekleme sırasında kapsayıcının durumu değiştirilmez. Karma işlev özel durum, sonuç tanımsızdır. Bir özel durum oluşturulursa, birden çok öğe ekleme sırasında kapsayıcı belirtilmeyen ancak geçerli bir durumda bırakılır.

[Value_type](../standard-library/map-class.md#value_type) eşlemesini yanı sıra, kapsayıcıya ait bir tür tanımı, kapsayıcısıdır `map<K, V>::value_type` olduğu `pair<const K, V>`. Bir öğenin ilk bileşen anahtar değerine eşittir ve ikinci bileşen öğenin veri değerine eşit olan sıralı bir çift değerdir.

Aralık üye işlevi (5) aralığında bir yineleyici tarafından ele alınan her öğe için karşılık gelen bir unordered_multimap öğe değerleri dizisi ekler `[First, Last)`; bu nedenle *son* takılı. Kapsayıcı üye işlevi `end()` kapsayıcıdaki son öğeden hemen sonra konuma başvuran — Örneğin, deyim `m.insert(v.begin(), v.end());` tüm öğeleri ekler `v` içine `m`.

Başlatıcı listesinde üye işlev (6) kullanan bir [initializer_list](../standard-library/initializer-list.md) öğeleri unordered_multimap kopyalanacak.

Yerinde oluşturulmuş bir öğe ekleme — diğer bir deyişle, hiçbir kopyalama veya taşıma işlemleri gerçekleştirilir — bkz [unordered_multimap::emplace](#emplace) ve [unordered_multimap::emplace_hint](#emplace_hint).

Kod örneği için bkz: [multimap::insert](../standard-library/multiset-class.md#insert).

## <a name="iterator"></a>  unordered_multimap::iterator

Denetlenen dizi için bir yineleyici türü.

```cpp
typedef T0 iterator;
```

### <a name="remarks"></a>Açıklamalar

Denetlenen dizi için ileriye doğru yineleyici olarak hizmet verebilen bir nesneyi tanımlayan bir tür. Açıklanmıştır uygulama tanımlı türünün eşanlamlısı olarak burada `T0`.

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

## <a name="key_eq"></a>  unordered_multimap::key_eq

Depolanan karşılaştırma işlevi nesnesini alır.

```cpp
Pred key_eq() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, depolanan karşılaştırma işlevi nesnesini döndürür.

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

## <a name="key_equal"></a>  unordered_multimap::key_equal

Karşılaştırma işlevinin türü.

```cpp
typedef Pred key_equal;
```

### <a name="remarks"></a>Açıklamalar

Şablon parametresi için bir eşanlamlı türüdür `Pred`.

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

## <a name="key_type"></a>  unordered_multimap::key_type

Bir sıralama anahtarının türü.

```cpp
typedef Key key_type;
```

### <a name="remarks"></a>Açıklamalar

Şablon parametresi için bir eşanlamlı türüdür `Key`.

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

## <a name="load_factor"></a>  unordered_multimap::load_factor

Demet başına ortalama öğeyi sayar.

```cpp
float load_factor() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevinin döndürdüğü `(float)` [unordered_multimap::size](#size)`() / (float)`[unordered_multimap::bucket_count](#bucket_count)`()`, öğe demet başına ortalama sayısı.

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

## <a name="local_iterator"></a>  unordered_multimap::local_iterator

Bir demet yineleyici türü.

```cpp
typedef T4 local_iterator;
```

### <a name="remarks"></a>Açıklamalar

Bir demet için ileriye doğru yineleyici olarak hizmet verebilen bir nesneyi tanımlayan bir tür. Açıklanmıştır uygulama tanımlı türünün eşanlamlısı olarak burada `T4`.

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

## <a name="mapped_type"></a>  unordered_multimap::mapped_type

Her bir anahtar ile ilişkili bir eşlenen değer türü.

```cpp
typedef Ty mapped_type;
```

### <a name="remarks"></a>Açıklamalar

Şablon parametresi için bir eşanlamlı türüdür `Ty`.

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

## <a name="max_bucket_count"></a>  unordered_multimap::max_bucket_count

En yüksek demet sayısını alır.

```cpp
size_type max_bucket_count() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, demet şu anda izin verilen en büyük sayısını döndürür.

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

## <a name="max_load_factor"></a>  unordered_multimap::max_load_factor

Demet başına en yüksek öğe sayısını alır veya ayarlar.

```cpp
float max_load_factor() const;


void max_load_factor(float factor);
```

### <a name="parameters"></a>Parametreler

*faktörü*<br/>
Yeni en yüksek yük faktörünün.

### <a name="remarks"></a>Açıklamalar

İlk üye işlevi, depolanan en yüksek yük faktörünün döndürür. İkinci üye işlevi ile depolanan en yüksek yük faktörünün değiştirir *faktörü*.

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

## <a name="max_size"></a>  unordered_multimap::max_size

Denetlenen dizinin en büyük boyutunu alır.

```cpp
size_type max_size() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, nesneyi de denetleyebilir kastetmek uzunluğunu döndürür.

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

## <a name="op_eq"></a>  unordered_multimap::operator =

Bir karma tabloya kopyalar.

```cpp
unordered_multimap& operator=(const unordered_multimap& right);

unordered_multimap& operator=(unordered_multimap&& right);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|-|-|
|*sağ*|Unordered_multimap kopyalanan unordered_multimap.|

### <a name="remarks"></a>Açıklamalar

Var olan herhangi bir unordered_multimap öğeleri silme sonra `operator=` kopyalar veya içeriğini hareket *doğru* unordered_multimap içine.

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

## <a name="pointer"></a>  unordered_multimap::pointer

Bir öğe için bir işaretçi türü.

```cpp
typedef Alloc::pointer pointer;
```

### <a name="remarks"></a>Açıklamalar

Denetlenen dizinin öğeye bir işaretçi olarak hizmet verebilen bir nesneyi tanımlayan bir tür.

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

## <a name="reference"></a>  unordered_multimap::Reference

Bir öğe için bir başvuru türü.

```cpp
typedef Alloc::reference reference;
```

### <a name="remarks"></a>Açıklamalar

Denetlenen dizinin bir öğesine bir başvuru olarak hizmet verebilen bir nesneyi tanımlayan bir tür.

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

## <a name="rehash"></a>  unordered_multimap::rehash

Karma tabloyu yeniden oluşturur.

```cpp
void rehash(size_type nbuckets);
```

### <a name="parameters"></a>Parametreler

*nbuckets*<br/>
İstenen demet sayısı.

### <a name="remarks"></a>Açıklamalar

Üye işlevi en az olacak şekilde demet sayısını değiştirir *nbuckets* ve gerektiğinde karma tabloyu yeniden oluşturur.

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

## <a name="size"></a>  unordered_multimap::size

Öğe sayısını sayar.

```cpp
size_type size() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, denetlenen dizinin uzunluğunu döndürür.

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

## <a name="size_type"></a>  unordered_multimap::size_type

İki öğe arasındaki işaretsiz bir mesafenin türü.

```cpp
typedef T2 size_type;
```

### <a name="remarks"></a>Açıklamalar

İşaretsiz tamsayı türü, denetlenen bir dizi uzunluğunu temsil edebilen bir nesneyi tanımlar. Açıklanmıştır uygulama tanımlı türünün eşanlamlısı olarak burada `T2`.

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

## <a name="swap"></a>  unordered_multimap::Swap

İki kapsayıcının içeriğinin yerini değiştirir.

```cpp
void swap(unordered_multimap& right);
```

### <a name="parameters"></a>Parametreler

*sağ*<br/>
İle takas için kapsayıcı.

### <a name="remarks"></a>Açıklamalar

Denetlenen diziyi üye işlevi değiştirir `*this` ve *doğru*. Varsa [unordered_multimap::get_allocator](#get_allocator)`() == right.get_allocator()`depolanan özellikleri nesnesinin türü kopyalama sonucunda yalnızca özel durum oluşturur, bunu sabit sürede yapar `Tr`, hiçbir başvurular, işaretçiler, gösteren geçersiz kılar veya Bu yineleyiciler iki denetlenen dizinin öğelerini belirleyin. Aksi takdirde, bir dizi öğesi atamalar ve oluşturucu çağrıları öğelerin sayısını orantılı iki denetimli sıralarında gerçekleştirir.

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

## <a name="unordered_multimap"></a>  unordered_multimap::unordered_multimap

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
InputIterator first, InputIterator last,
    size_type Bucket_count = N0,
    const Hash& Hash = Hash(),
    const Comp& Comp = Pred(),
    const Allocator& Al = Alloc());
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|-|-|
|*Inputıterator*|Yineleyici türü.|
|*Al*|Depolanacak ayırıcı nesne.|
|*Comp*|Depolanacak karşılaştırma işlevi nesnesi.|
|*Karma*|Depolanacak karma işlev nesnesi.|
|*Bucket_count*|En düşük demet sayısı.|
|*sağ*|Kopyalanacak kapsayıcı.|
|*IList*|Öğelerin kopyalanacağı initializer_list.|

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu tarafından denetlenen dizinin bir kopyasını belirtir *sağ*. İkinci oluşturucu boş bir denetlenmiş dizi belirtir. Üçüncü Oluşturucu. taşıyarak dizinin bir kopyasını belirtir *sağ*. Dördüncü, beşinci, altıncı, yedinci ve sekizinci oluşturucular üyeler için bir initializer_list kullanır. Dokuzuncu Oluşturucu öğe değerleri dizisi ekler `[First, Last)`.

Ayrıca, tüm oluşturucular çeşitli depolanmış değerleri başlatır. Kopya oluşturucusu için gelen değerler elde edilir *sağ*. Aksi durumda:.

Demetler en az sayıda bağımsız değişken olan *Bucket_count*, aksi takdirde mevcut açıklanan varsayılan bir değer olup olmadığını burada uygulama tanımlı değer olarak `N0`.

Karma işlev nesnesi bağımsız değişken olan *karma*, mevcut; Aksi durumda, `Hash()`.

Karşılaştırma işlevi nesnesini bağımsız değişken olan *kompozisyonu*, mevcut; Aksi durumda, `Pred()`.

Bağımsız değişken ayırıcısı nesnedir *Al*, mevcut; Aksi durumda, `Alloc()`.

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

## <a name="value_type"></a>  unordered_multimap::value_type

Öğenin türü.

```cpp
typedef std::pair<const Key, Ty> value_type;
```

### <a name="remarks"></a>Açıklamalar

Denetlenen dizinin bir öğe türü açıklar.

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

[<unordered_map>](../standard-library/unordered-map.md)<br/>
[Kapsayıcılar](../cpp/containers-modern-cpp.md)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)<br/>
