---
title: unordered_multiset Sınıfı
description: '`unordered_multiset`İçinde bulunan öğelerin değerlerinin benzersiz olmaması ve anahtar değerleri olarak kullandıkları bir koleksiyondan verilerin depolanması ve alınması için kullanılan bir nesneyi tanımlayan C++ standart kitaplık kapsayıcı sınıfı IÇIN API başvurusu. Veriler otomatik olarak sıralı değildir.'
ms.date: 9/10/2020
f1_keywords:
- unordered_set/std::unordered_multiset
- unordered_set/std::unordered_multiset::allocator_type
- unordered_set/std::unordered_multiset::const_iterator
- unordered_set/std::unordered_multiset::const_local_iterator
- unordered_set/std::unordered_multiset::const_pointer
- unordered_set/std::unordered_multiset::const_reference
- unordered_set/std::unordered_multiset::difference_type
- unordered_set/std::unordered_multiset::hasher
- unordered_set/std::unordered_multiset::iterator
- unordered_set/std::unordered_multiset::key_equal
- unordered_set/std::unordered_multiset::key_type
- unordered_set/std::unordered_multiset::local_iterator
- unordered_set/std::unordered_multiset::pointer
- unordered_set/std::unordered_multiset::reference
- unordered_set/std::unordered_multiset::size_type
- unordered_set/std::unordered_multiset::value_type
- unordered_set/std::unordered_multiset::begin
- unordered_set/std::unordered_multiset::bucket
- unordered_set/std::unordered_multiset::bucket_count
- unordered_set/std::unordered_multiset::bucket_size
- unordered_set/std::unordered_multiset::cbegin
- unordered_set/std::unordered_multiset::cend
- unordered_set/std::unordered_multiset::clear
- unordered_set/std::unordered_multiset::contains
- unordered_set/std::unordered_multiset::count
- unordered_set/std::unordered_multiset::emplace
- unordered_set/std::unordered_multiset::emplace_hint
- unordered_set/std::unordered_multiset::empty
- unordered_set/std::unordered_multiset::end
- unordered_set/std::unordered_multiset::equal_range
- unordered_set/std::unordered_multiset::erase
- unordered_set/std::unordered_multiset::find
- unordered_set/std::unordered_multiset::get_allocator
- unordered_set/std::unordered_multiset::hash
- unordered_set/std::unordered_multiset::insert
- unordered_set/std::unordered_multiset::key_eq
- unordered_set/std::unordered_multiset::load_factor
- unordered_set/std::unordered_multiset::max_bucket_count
- unordered_set/std::unordered_multiset::max_load_factor
- unordered_set/std::unordered_multiset::max_size
- unordered_set/std::unordered_multiset::rehash
- unordered_set/std::unordered_multiset::size
- unordered_set/std::unordered_multiset::swap
- unordered_set/std::unordered_multiset::unordered_multiset
- unordered_set/std::unordered_multiset::operator=
- unordered_set/std::unordered_multiset::hash_function
helpviewer_keywords:
- std::unordered_multiset
- std::unordered_multiset::allocator_type
- std::unordered_multiset::const_iterator
- std::unordered_multiset::const_local_iterator
- std::unordered_multiset::const_pointer
- std::unordered_multiset::const_reference
- std::unordered_multiset::difference_type
- std::unordered_multiset::hasher
- std::unordered_multiset::iterator
- std::unordered_multiset::key_equal
- std::unordered_multiset::key_type
- std::unordered_multiset::local_iterator
- std::unordered_multiset::pointer
- std::unordered_multiset::reference
- std::unordered_multiset::size_type
- std::unordered_multiset::value_type
- std::unordered_multiset::begin
- std::unordered_multiset::bucket
- std::unordered_multiset::bucket_count
- std::unordered_multiset::bucket_size
- std::unordered_multiset::cbegin
- std::unordered_multiset::cend
- std::unordered_multiset::clear
- std::unordered_multiset::contains
- std::unordered_multiset::count
- std::unordered_multiset::emplace
- std::unordered_multiset::emplace_hint
- std::unordered_multiset::empty
- std::unordered_multiset::end
- std::unordered_multiset::equal_range
- std::unordered_multiset::erase
- std::unordered_multiset::find
- std::unordered_multiset::get_allocator
- std::unordered_multiset::hash
- std::unordered_multiset::insert
- std::unordered_multiset::key_eq
- std::unordered_multiset::load_factor
- std::unordered_multiset::max_bucket_count
- std::unordered_multiset::max_load_factor
- std::unordered_multiset::max_size
- std::unordered_multiset::rehash
- std::unordered_multiset::size
- std::unordered_multiset::swap
- std::unordered_multiset::unordered_multiset
- std::unordered_multiset::operator=
- std::unordered_multiset::allocator_type
- std::unordered_multiset::const_iterator
- std::unordered_multiset::const_local_iterator
- std::unordered_multiset::const_pointer
- std::unordered_multiset::const_reference
- std::unordered_multiset::difference_type
- std::unordered_multiset::hasher
- std::unordered_multiset::iterator
- std::unordered_multiset::key_equal
- std::unordered_multiset::key_type
- std::unordered_multiset::local_iterator
- std::unordered_multiset::pointer
- std::unordered_multiset::reference
- std::unordered_multiset::size_type
- std::unordered_multiset::value_type
- std::unordered_multiset::begin
- std::unordered_multiset::bucket
- std::unordered_multiset::bucket_count
- std::unordered_multiset::bucket_size
- std::unordered_multiset::cbegin
- std::unordered_multiset::cend
- std::unordered_multiset::clear
- std::unordered_multiset::count
- std::unordered_multiset::emplace
- std::unordered_multiset::emplace_hint
- std::unordered_multiset::empty
- std::unordered_multiset::end
- std::unordered_multiset::equal_range
- std::unordered_multiset::erase
- std::unordered_multiset::find
- std::unordered_multiset::get_allocator
- std::unordered_multiset::hash_function
- std::unordered_multiset::insert
- std::unordered_multiset::key_eq
- std::unordered_multiset::load_factor
- std::unordered_multiset::max_bucket_count
- std::unordered_multiset::max_load_factor
- std::unordered_multiset::max_size
- std::unordered_multiset::rehash
- std::unordered_multiset::size
- std::unordered_multiset::swap
ms.assetid: 70c8dfc5-492a-4af2-84f5-1aa9cb04b71c
ms.openlocfilehash: 0730f4eb6ba8e625c2c40cecddc4f689ec775d17
ms.sourcegitcommit: d9c94dcabd94537e304be0261b3263c2071b437b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/25/2020
ms.locfileid: "91352784"
---
# <a name="unordered_multiset-class"></a>unordered_multiset Sınıfı

Sınıf şablonu, türünde öğelerin değişen uzunluklu dizisini denetleyen bir nesneyi tanımlar `const Key` . Dizi çağrılan demetlerin sıralı bir dizi kümesini bölümleyen bir karma işlev tarafından zayıf bir şekilde sıralanır. Her bir demette herhangi bir öğe çiftinin eşdeğer sıralamaya sahip olup olmadığını belirleyen bir karşılaştırma işlevi vardır. Her bir öğe hem bir sıralama anahtarı hem de bir değer depolar. Dizi, en azından tüm demetleri kabaca eşit uzunlukta olduğunda, dizideki (sabit zaman) öğe sayısından bağımsız olabilen işlem sayısına sahip rastgele bir öğenin aranması, eklenmesi ve kaldırılmasına izin verecek şekilde temsil edilir. En kötü durumda, tüm öğeler tek bir demet içinde olduğunda işlem sayısı dizideki (doğrusal zaman) öğelerin sayısıyla orantılıdır. Ayrıca, bir öğe eklenmesi hiçbir yineleyiciyi geçersiz kılmaz; bir öğenin kaldırılması yalnızca bu kaldırılan öğeyi gösteren yineleyicileri geçersiz kılar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Key,
    class Hash = std::hash<Key>,
    class Pred = std::equal_to<Key>,
    class Alloc = std::allocator<Key>>
class unordered_multiset;
```

### <a name="parameters"></a>Parametreler

*Anahtar*\
Anahtar türü.

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
|[contains](#contains)<sup>c++ 20</sup> içerir|Belirtilen anahtara sahip bir öğe olup olmadığını denetler.|
|[biriktirme](#count)|Belirtilen bir anahtar ile eşleşen öğe sayısını bulur.|
|[Emplace](#emplace)|Yerinde oluşturulmuş bir öğe ekler.|
|[emplace_hint](#emplace_hint)|Göstergeyle birlikte, yerinde oluşturulmuş bir öğe ekler.|
|[empty](#empty)|Bir öğe olup olmadığını sınar.|
|[erer](#end)|Denetlenen dizinin bitişini belirtir.|
|[equal_range](#equal_range)|Belirtilen bir anahtarla eşleşen aralığı bulur.|
|[silme](#erase)|Belirtilen konumlardaki öğeleri kaldırır.|
|[bilgi](#find)|Belirtilen bir anahtarla eşleşen bir öğeyi bulur.|
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
|[unordered_multiset](#unordered_multiset)|Bir kapsayıcı nesnesi oluşturur.|

|İşleç|Açıklama|
|-|-|
|[unordered_multiset:: operator =](#op_eq)|Bir karma tabloya kopyalar.|

## <a name="remarks"></a>Açıklamalar

Nesne, iki saklı nesneyi çağırarak denetlediği sırayı, [unordered_multiset:: key_equal](#key_equal) türünde bir karşılaştırma işlev nesnesi ve [unordered_multiset:: hasher](#hasher)türünde bir karma işlev nesnesi olarak sıralar. [Unordered_multiset:: key_eq](#key_eq); üye işlevini çağırarak `()` ve ikinci saklı nesneye eriştiğinizde, [unordered_multiset:: hash_function](#hash)üye işlevini çağırarak, ilk depolanan nesneye erişirsiniz `()` . Özellikle, tüm değerleri `X` ve `Y` türü için `Key` , çağrı `key_eq()(X, Y)` yalnızca iki bağımsız değişken değeri eşdeğer sıralama içeriyorsa true değerini döndürür; çağrı, `hash_function()(keyval)` türündeki değerlerin bir dağılımını verir `size_t` . Sınıf şablonu [unordered_set sınıfından](../standard-library/unordered-set-class.md)farklı olarak, türünde bir nesne, `unordered_multiset` `key_eq()(X, Y)` denetlenen sıranın herhangi iki öğesi için her zaman false olduğundan emin değildir. (Anahtarlarının benzersiz olması gerekmez.)

Nesne ayrıca, demet başına istenen ortalama öğe sayısını belirten en yüksek yük faktörünü depolar. Bir öğe eklemek [unordered_multiset:: load_factor](#load_factor) `()` en fazla yük faktörünü aşmasına neden olursa kapsayıcı, demetlerin sayısını artırır ve gerekirse karma tabloyu yeniden oluşturur.

Denetlenen dizideki öğelerin gerçek sırası karma işleve, karşılaştırma işlevine, ekleme sırasına, en yüksek yük faktörüne ve geçerli demet sayısına bağlıdır. Denetlenen dizideki öğelerin sırasını genelde tahmin edemezsiniz. Ancak, eşdeğer sıralamaya sahip öğelerin herhangi bir alt kümesinin her zaman denetlenen dizide bitişik olduğundan emin olabilirsiniz.

Nesnesi, [unordered_multiset:: allocator_type](#allocator_type)türünde depolanan bir ayırıcı nesne aracılığıyla denetlediği sıra için depolamayı ayırır ve boşaltır. Böyle bir ayırıcı nesne, türünde bir nesne ile aynı dış arabirime sahip olmalıdır `allocator` . Depolanan ayırıcı nesnenin kapsayıcı nesne atandığında kopyalanmayacağını unutmayın.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<unordered_set>

**Ad alanı:** std

## <a name="unordered_multisetallocator_type"></a><a name="allocator_type"></a> unordered_multiset:: allocator_type

Depolamayı yönetmek için bir ayırıcı türü.

```cpp
typedef Alloc allocator_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, şablon parametresi için bir eş anlamlı `Alloc` .

### <a name="example"></a>Örnek

```cpp
// std__unordered_set__unordered_multiset_allocator_type.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_multiset<char> Myset;
typedef std::allocator<std::pair<const char, int> > Myalloc;
int main()
{
    Myset c1;

    Myset::allocator_type al = c1.get_allocator();
    std::cout << "al == std::allocator() is "
        << std::boolalpha << (al == Myalloc()) << std::endl;

    return (0);
}
```

```Output
al == std::allocator() is true
```

## <a name="unordered_multisetbegin"></a><a name="begin"></a> unordered_multiset:: Begin

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
// std__unordered_set__unordered_multiset_begin.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_multiset<char> Myset;
int main()
{
    Myset c1;

    c1.insert('a');
    c1.insert('b');
    c1.insert('c');

    // display contents "[c] [b] [a]"
    for (Myset::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << "[" << *it << "] ";
    std::cout << std::endl;

    // inspect first two items "[c] [b]"
    Myset::iterator it2 = c1.begin();
    std::cout << "[" << *it2 << "] ";
    ++it2;
    std::cout << "[" << *it2 << "] ";
    std::cout << std::endl;

    // inspect bucket containing 'a'
    Myset::const_local_iterator lit = c1.begin(c1.bucket('a'));
    std::cout << "[" << *lit << "] ";

    return (0);
}
```

```Output
[c] [b] [a]
[c] [b]
[a]
```

## <a name="unordered_multisetbucket"></a><a name="bucket"></a> unordered_multiset:: Bucket

Bir anahtar değeri için demet numarasını alır.

```cpp
size_type bucket(const Key& keyval) const;
```

### <a name="parameters"></a>Parametreler

*keyval*\
Eşlenecek anahtar değer.

### <a name="remarks"></a>Açıklamalar

Üye işlevi, şu anda anahtar değerine karşılık gelen demet numarasını döndürür `keyval` .

### <a name="example"></a>Örnek

```cpp
// std__unordered_set__unordered_multiset_bucket.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_multiset<char> Myset;
int main()
{
    Myset c1;

    c1.insert('a');
    c1.insert('b');
    c1.insert('c');

    // display contents "[c] [b] [a] "
    for (Myset::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << "[" << *it << "] ";
    std::cout << std::endl;

    // display buckets for keys
    Myset::size_type bs = c1.bucket('a');
    std::cout << "bucket('a') == " << bs << std::endl;
    std::cout << "bucket_size(" << bs << ") == " << c1.bucket_size(bs)
        << std::endl;

    return (0);
}
```

```Output
[c] [b] [a]
bucket('a') == 7
bucket_size(7) == 1
```

## <a name="unordered_multisetbucket_count"></a><a name="bucket_count"></a> unordered_multiset:: bucket_count

Demet sayısını alır.

```cpp
size_type bucket_count() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, geçerli demet sayısını döndürür.

### <a name="example"></a>Örnek

```cpp
// std__unordered_set__unordered_multiset_bucket_count.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_multiset<char> Myset;
int main()
{
    Myset c1;

    c1.insert('a');
    c1.insert('b');
    c1.insert('c');

    // display contents "[c] [b] [a] "
    for (Myset::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << "[" << *it << "] ";
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

    return (0);
}
```

```Output
[c] [b] [a]
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

## <a name="unordered_multisetbucket_size"></a><a name="bucket_size"></a> unordered_multiset:: bucket_size

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
// std__unordered_set__unordered_multiset_bucket_size.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_multiset<char> Myset;
int main()
{
    Myset c1;

    c1.insert('a');
    c1.insert('b');
    c1.insert('c');

    // display contents "[c] [b] [a] "
    for (Myset::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << "[" << *it << "] ";
    std::cout << std::endl;

    // display buckets for keys
    Myset::size_type bs = c1.bucket('a');
    std::cout << "bucket('a') == " << bs << std::endl;
    std::cout << "bucket_size(" << bs << ") == " << c1.bucket_size(bs)
        << std::endl;

    return (0);
}
```

```Output
[c] [b] [a]
bucket('a') == 7
bucket_size(7) == 1
```

## <a name="unordered_multisetcbegin"></a><a name="cbegin"></a> unordered_multiset:: cbegin

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

## <a name="unordered_multisetcend"></a><a name="cend"></a> unordered_multiset:: cend

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

## <a name="unordered_multisetclear"></a><a name="clear"></a> unordered_multiset:: Clear

Tüm öğeleri kaldırır.

```cpp
void clear();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi [unordered_multiset:: Erase](#erase) `(` [unordered_multiset:: BEGIN](#begin) `(),` [unordered_multiset:: End](#end)' i çağırır `())` .

### <a name="example"></a>Örnek

```cpp
// std__unordered_set__unordered_multiset_clear.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_multiset<char> Myset;
int main()
{
    Myset c1;

    c1.insert('a');
    c1.insert('b');
    c1.insert('c');

    // display contents "[c] [b] [a] "
    for (Myset::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << "[" << *it << "] ";
    std::cout << std::endl;

    // clear the container and reinspect
    c1.clear();
    std::cout << "size == " << c1.size() << std::endl;
    std::cout << "empty() == " << std::boolalpha << c1.empty() << std::endl;
    std::cout << std::endl;

    c1.insert('d');
    c1.insert('e');

    // display contents "[e] [d] "
    for (Myset::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << "[" << *it << "] ";
    std::cout << std::endl;

    std::cout << "size == " << c1.size() << std::endl;
    std::cout << "empty() == " << std::boolalpha << c1.empty() << std::endl;

    return (0);
}
```

```Output
[c] [b] [a]
size == 0
empty() == true

[e] [d]
size == 2
empty() == false
```

## <a name="unordered_multisetconst_iterator"></a><a name="const_iterator"></a> unordered_multiset:: const_iterator

Denetlenen dizi için bir sabit yineleyici türü.

```cpp
typedef T1 const_iterator;
```

### <a name="remarks"></a>Açıklamalar

Türü, denetimli sıra için sabit bir ileri Yineleyici işlevi görebilecek bir nesneyi tanımlar. Burada uygulama tanımlı tür için bir eş anlamlı olarak açıklanmaktadır `T1` .

### <a name="example"></a>Örnek

```cpp
// std__unordered_set__unordered_multiset_const_iterator.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_multiset<char> Myset;
int main()
{
    Myset c1;

    c1.insert('a');
    c1.insert('b');
    c1.insert('c');

    // display contents "[c] [b] [a]"
    for (Myset::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << "[" << *it << "] ";
    std::cout << std::endl;

    return (0);
}
```

```Output
[c] [b] [a]
```

## <a name="unordered_multisetconst_local_iterator"></a><a name="const_local_iterator"></a> unordered_multiset:: const_local_iterator

Denetlenen dizi için bir sabit demet yineleyici türü.

```cpp
typedef T5 const_local_iterator;
```

### <a name="remarks"></a>Açıklamalar

Türü, bir demet için sabit bir ileri Yineleyici işlevi görebilecek bir nesneyi tanımlar. Burada uygulama tanımlı tür için bir eş anlamlı olarak açıklanmaktadır `T5` .

### <a name="example"></a>Örnek

```cpp
// std__unordered_set__unordered_multiset_const_local_iterator.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_multiset<char> Myset;
int main()
{
    Myset c1;

    c1.insert('a');
    c1.insert('b');
    c1.insert('c');

    // display contents "[c] [b] [a]"
    for (Myset::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << "[" << *it << "] ";
    std::cout << std::endl;

    // inspect bucket containing 'a'
    Myset::const_local_iterator lit = c1.begin(c1.bucket('a'));
    std::cout << "[" << *lit << "] ";

    return (0);
}
```

```Output
[c] [b] [a]
[a]
```

## <a name="unordered_multisetconst_pointer"></a><a name="const_pointer"></a> unordered_multiset:: const_pointer

Bir öğe için sabit bir işaretçi türü.

```cpp
typedef Alloc::const_pointer const_pointer;
```

### <a name="remarks"></a>Açıklamalar

Türü, denetlenen dizinin bir öğesi için sabit bir işaretçi olarak kullanılabilecek bir nesneyi tanımlar.

### <a name="example"></a>Örnek

```cpp
// std__unordered_set__unordered_multiset_const_pointer.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_multiset<char> Myset;
int main()
{
    Myset c1;

    c1.insert('a');
    c1.insert('b');
    c1.insert('c');

    // display contents "[c] [b] [a]"
    for (Myset::iterator it = c1.begin();
        it != c1.end(); ++it)
        {
        Myset::const_pointer p = &*it;
        std::cout << "[" << *p << "] ";
        }
    std::cout << std::endl;

    return (0);
}
```

```Output
[c] [b] [a]
```

## <a name="unordered_multisetconst_reference"></a><a name="const_reference"></a> unordered_multiset:: const_reference

Bir öğe için sabit bir başvuru türü.

```cpp
typedef Alloc::const_reference const_reference;
```

### <a name="remarks"></a>Açıklamalar

Türü, denetlenen dizinin bir öğesine sabit başvuru olarak işlev yapabilecek bir nesneyi tanımlar.

### <a name="example"></a>Örnek

```cpp
// std__unordered_set__unordered_multiset_const_reference.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_multiset<char> Myset;
int main()
{
    Myset c1;

    c1.insert('a');
    c1.insert('b');
    c1.insert('c');

    // display contents "[c] [b] [a]"
    for (Myset::iterator it = c1.begin();
        it != c1.end(); ++it)
        {
        Myset::const_reference ref = *it;
        std::cout << "[" << ref << "] ";
        }
    std::cout << std::endl;

    return (0);
}
```

```Output
[c] [b] [a]
```

## <a name="unordered_multisetcontains"></a><a name="contains"></a> unordered_multiset:: Contains

İçinde belirtilen anahtara sahip bir öğe olup olmadığını denetler `unordered_multiset` .

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
#include <unordered_set>
#include <iostream>

int main()
{
    std::unordered_multiset<int> theUnorderedMultiset = { 1, 2, 3 };

    std::cout << std::boolalpha; // so booleans show as 'true' or 'false'
    std::cout << theUnorderedMultiset.contains(1) << '\n';
    std::cout << theUnorderedMultiset.contains(4) << '\n';

    return 0;
}
```

```Output
true
false
```

## <a name="unordered_multisetcount"></a><a name="count"></a> unordered_multiset:: Count

Belirtilen bir anahtar ile eşleşen öğe sayısını bulur.

```cpp
size_type count(const Key& keyval) const;
```

### <a name="parameters"></a>Parametreler

*keyval*\
Aranacak anahtar değer.

### <a name="remarks"></a>Açıklamalar

Üye işlevi [unordered_multiset:: equal_range](#equal_range)ile ayrılmış aralıktaki öğe sayısını döndürür `(keyval)` .

### <a name="example"></a>Örnek

```cpp
// std__unordered_set__unordered_multiset_count.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_multiset<char> Myset;
int main()
{
    Myset c1;

    c1.insert('a');
    c1.insert('b');
    c1.insert('c');

    // display contents "[c] [b] [a]"
    for (Myset::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << "[" << *it << "] ";
    std::cout << std::endl;

    std::cout << "count('A') == " << c1.count('A') << std::endl;
    std::cout << "count('b') == " << c1.count('b') << std::endl;
    std::cout << "count('C') == " << c1.count('C') << std::endl;

    return (0);
}
```

```Output
[c] [b] [a]
count('A') == 0
count('b') == 1
count('C') == 0
```

## <a name="unordered_multisetdifference_type"></a><a name="difference_type"></a> unordered_multiset::d ifference_type

İki öğe arasındaki işaretli mesafenin türü.

```cpp
typedef T3 difference_type;
```

### <a name="remarks"></a>Açıklamalar

İmzalanan tamsayı türü, denetlenen dizideki herhangi iki öğenin adresleri arasındaki farkı temsil eden bir nesneyi tanımlar. Burada uygulama tanımlı tür için bir eş anlamlı olarak açıklanmaktadır `T3` .

### <a name="example"></a>Örnek

```cpp
// std__unordered_set__unordered_multiset_difference_type.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_multiset<char> Myset;
int main()
{
    Myset c1;

    c1.insert('a');
    c1.insert('b');
    c1.insert('c');

    // display contents "[c] [b] [a]"
    for (Myset::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << "[" << *it << "] ";
    std::cout << std::endl;

    // compute positive difference
    Myset::difference_type diff = 0;
    for (Myset::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        ++diff;
    std::cout << "end()-begin() == " << diff << std::endl;

    // compute negative difference
    diff = 0;
    for (Myset::const_iterator it = c1.end();
        it != c1.begin(); --it)
        --diff;
    std::cout << "begin()-end() == " << diff << std::endl;

    return (0);
}
```

```Output
[c] [b] [a]
end()-begin() == 3
begin()-end() == -3
```

## <a name="unordered_multisetemplace"></a><a name="emplace"></a> unordered_multiset:: emplace

Yerinde oluşturulmuş bir öğe ekler (kopyalama veya taşıma işlemleri yapılmaz).

```cpp
template <class... Args>
iterator emplace(Args&&... args);
```

### <a name="parameters"></a>Parametreler

*args*\
Unordered_multiset eklenecek bir öğe oluşturmak için iletilen bağımsız değişkenler.

### <a name="return-value"></a>Dönüş Değeri

Yeni eklenmekte olan öğe için bir yineleyici.

### <a name="remarks"></a>Açıklamalar

Bu işlev tarafından kapsayıcı öğelerine yönelik başvuru geçersiz kılınmamıştır, ancak kapsayıcı için tüm yineleyiciler geçersiz kılınabilir.

Ekleme sırasında, bir özel durum oluşturulursa, ancak kapsayıcının karma işlevinde gerçekleşmezse kapsayıcı değiştirilmez. Karma işlevde özel durum oluşturulursa, sonuç tanımsızdır.

Kod örneği için bkz. [Çoklu küme:: emplace](../standard-library/multiset-class.md#emplace).

## <a name="unordered_multisetemplace_hint"></a><a name="emplace_hint"></a> unordered_multiset:: emplace_hint

Yerinde oluşturulmuş bir öğe ekler (kopyalama veya taşıma işlemleri yapılmaz), yerleştirme ipucuyla birlikte.

```cpp
template <class... Args>
iterator emplace_hint(
    const_iterator where,
    Args&&... args);
```

### <a name="parameters"></a>Parametreler

*args*\
Unordered_multiset eklenecek bir öğe oluşturmak için iletilen bağımsız değişkenler.

*olmadığı*\
Doğru ekleme noktasını aramaya başlamak için yer hakkında bir ipucu.

### <a name="return-value"></a>Dönüş Değeri

Yeni eklenmekte olan öğe için bir yineleyici.

### <a name="remarks"></a>Açıklamalar

Bu işlev tarafından kapsayıcı öğelerine yönelik başvuru geçersiz kılınmamıştır, ancak kapsayıcı için tüm yineleyiciler geçersiz kılınabilir.

Ekleme sırasında, bir özel durum oluşturulursa, ancak kapsayıcının karma işlevinde gerçekleşmezse kapsayıcı değiştirilmez. Karma işlevde özel durum oluşturulursa, sonuç tanımsızdır.

Kod örneği için bkz. [set:: emplace_hint](../standard-library/set-class.md#emplace_hint).

## <a name="unordered_multisetempty"></a><a name="empty"></a> unordered_multiset:: boş

Bir öğe olup olmadığını sınar.

```cpp
bool empty() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi boş bir denetlenen dizi için true döndürür.

### <a name="example"></a>Örnek

```cpp
// std__unordered_set__unordered_multiset_empty.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_multiset<char> Myset;
int main()
{
    Myset c1;

    c1.insert('a');
    c1.insert('b');
    c1.insert('c');

    // display contents "[c] [b] [a]"
    for (Myset::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << "[" << *it << "] ";
    std::cout << std::endl;

    // clear the container and reinspect
    c1.clear();
    std::cout << "size == " << c1.size() << std::endl;
    std::cout << "empty() == " << std::boolalpha << c1.empty() << std::endl;
    std::cout << std::endl;

    c1.insert('d');
    c1.insert('e');

    // display contents "[e] [d]"
    for (Myset::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << "[" << *it << "] ";
    std::cout << std::endl;

    std::cout << "size == " << c1.size() << std::endl;
    std::cout << "empty() == " << std::boolalpha << c1.empty() << std::endl;

    return (0);
}
```

```Output
[c] [b] [a]
size == 0
empty() == true

[e] [d]
size == 2
empty() == false
```

## <a name="unordered_multisetend"></a><a name="end"></a> unordered_multiset:: End

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
// std__unordered_set__unordered_multiset_end.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_multiset<char> Myset;
int main()
{
    Myset c1;

    c1.insert('a');
    c1.insert('b');
    c1.insert('c');

    // display contents "[c] [b] [a]"
    for (Myset::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << "[" << *it << "] ";
    std::cout << std::endl;

    // inspect last two items "[a] [b]"
    Myset::iterator it2 = c1.end();
    --it2;
    std::cout << "[" << *it2 << "] ";
    --it2;
    std::cout << "[" << *it2 << "] ";
    std::cout << std::endl;

    // inspect bucket containing 'a'
    Myset::const_local_iterator lit = c1.end(c1.bucket('a'));
    --lit;
    std::cout << "[" << *lit << "] ";

    return (0);
}
```

```Output
[c] [b] [a]
[a] [b]
[a]
```

## <a name="unordered_multisetequal_range"></a><a name="equal_range"></a> unordered_multiset:: equal_range

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
// std__unordered_set__unordered_multiset_equal_range.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_multiset<char> Myset;
int main()
{
    Myset c1;

    c1.insert('a');
    c1.insert('b');
    c1.insert('c');

    // display contents "[c] [b] [a]"
    for (Myset::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << "[" << *it << "] ";
    std::cout << std::endl;

    // display results of failed search
    std::pair<Myset::iterator, Myset::iterator> pair1 =
        c1.equal_range('x');
    std::cout << "equal_range('x'):";
    for (; pair1.first != pair1.second; ++pair1.first)
        std::cout << "[" << *pair1.first << "] ";
    std::cout << std::endl;

    // display results of successful search
    pair1 = c1.equal_range('b');
    std::cout << "equal_range('b'):";
    for (; pair1.first != pair1.second; ++pair1.first)
        std::cout << "[" << *pair1.first << "] ";
    std::cout << std::endl;

    return (0);
}
```

```Output
[c] [b] [a]
equal_range('x'):
equal_range('b'): [b]
```

## <a name="unordered_multiseterase"></a><a name="erase"></a> unordered_multiset:: Erase

Belirtilen konumlardan bir unordered_multiset öğeyi veya öğe aralığını kaldırır veya belirtilen bir anahtarla eşleşen öğeleri kaldırır.

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

İlk iki üye işlevi için, kaldırılan öğelerin dışında kalan ilk öğeyi veya böyle bir öğe yoksa unordered_multiset sonu olan bir öğeyi atayan çift yönlü bir yineleyici.

Üçüncü üye işlevi için, unordered_multiset kaldırılan öğelerin sayısını döndürür.

### <a name="remarks"></a>Açıklamalar

Kod örneği için bkz. [set:: Erase](../standard-library/set-class.md#erase).

## <a name="unordered_multisetfind"></a><a name="find"></a> unordered_multiset:: Find

Belirtilen bir anahtarla eşleşen bir öğeyi bulur.

```cpp
const_iterator find(const Key& keyval) const;
```

### <a name="parameters"></a>Parametreler

*keyval*\
Aranacak anahtar değer.

### <a name="remarks"></a>Açıklamalar

Üye işlevi [unordered_multiset:: equal_range](#equal_range)döndürür `(keyval).first` .

### <a name="example"></a>Örnek

```cpp
// std__unordered_set__unordered_multiset_find.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_multiset<char> Myset;
int main()
{
    Myset c1;

    c1.insert('a');
    c1.insert('b');
    c1.insert('c');

    // display contents "[c] [b] [a]"
    for (Myset::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << "[" << *it << "] ";
    std::cout << std::endl;

    // try to find and fail
    std::cout << "find('A') == "
        << std::boolalpha << (c1.find('A') != c1.end()) << std::endl;

    // try to find and succeed
    Myset::iterator it = c1.find('b');
    std::cout << "find('b') == "
        << std::boolalpha << (it != c1.end())
        << ": [" << *it << "] " << std::endl;

    return (0);
}
```

```Output
[c] [b] [a]
find('A') == false
find('b') == true: [b]
```

## <a name="unordered_multisetget_allocator"></a><a name="get_allocator"></a> unordered_multiset:: get_allocator

Depolanan ayırıcı nesnesini alır.

```cpp
Alloc get_allocator() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, depolanan ayırıcı nesnesini döndürür.

### <a name="example"></a>Örnek

```cpp
// std__unordered_set__unordered_multiset_get_allocator.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_multiset<char> Myset;
typedef std::allocator<std::pair<const char, int> > Myalloc;
int main()
{
    Myset c1;

    Myset::allocator_type al = c1.get_allocator();
    std::cout << "al == std::allocator() is "
        << std::boolalpha << (al == Myalloc()) << std::endl;

    return (0);
}
```

```Output
al == std::allocator() is true
```

## <a name="unordered_multisethash_function"></a><a name="hash"></a> unordered_multiset:: hash_function

Depolanan karma işlevi nesnesini alır.

```cpp
Hash hash_function() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, depolanan karma işlevi nesnesini döndürür.

### <a name="example"></a>Örnek

```cpp
// std__unordered_set__unordered_multiset_hash_function.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_multiset<char> Myset;
int main()
{
    Myset c1;

    Myset::hasher hfn = c1.hash_function();
    std::cout << "hfn('a') == " << hfn('a') << std::endl;
    std::cout << "hfn('b') == " << hfn('b') << std::endl;

    return (0);
}
```

```Output
hfn('a') == 1630279
hfn('b') == 1647086
```

## <a name="unordered_multisethasher"></a><a name="hasher"></a> unordered_multiset:: hasher

Karma işlevin türü.

```cpp
typedef Hash hasher;
```

### <a name="remarks"></a>Açıklamalar

Tür, şablon parametresi için bir eş anlamlı `Hash` .

### <a name="example"></a>Örnek

```cpp
// std__unordered_set__unordered_multiset_hasher.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_multiset<char> Myset;
int main()
{
    Myset c1;

    Myset::hasher hfn = c1.hash_function();
    std::cout << "hfn('a') == " << hfn('a') << std::endl;
    std::cout << "hfn('b') == " << hfn('b') << std::endl;

    return (0);
}
```

```Output
hfn('a') == 1630279
hfn('b') == 1647086
```

## <a name="unordered_multisetinsert"></a><a name="insert"></a> unordered_multiset:: INSERT

Bir unordered_multiset öğe veya öğe aralığı ekler.

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
Unordered_multiset eklenecek öğenin değeri.

*Olmadığı*\
Doğru ekleme noktasını aramaya başlamak için yer.

*ValTy*\
Unordered_multiset, [value_type](../standard-library/map-class.md#value_type)bir öğesi oluşturmak için kullanabileceği bağımsız değişken türünü belirten şablon parametresi ve bağımsız değişken olarak *kusursuz iletme değeri* .

*Adı*\
Kopyalanacak ilk öğenin konumu.

*Soyadına*\
Kopyalanacak son öğenin hemen ötesinde konum.

*InputIterator*\
[Value_type](../standard-library/map-class.md#value_type) nesneleri oluşturmak için kullanılabilecek bir türün öğelerine işaret eden bir [giriş yineleyicisinin](../standard-library/input-iterator-tag-struct.md) gereksinimlerini karşılayan şablon işlevi bağımsız değişkeni.

*IList*\
Öğelerin kopyalanacağı [initializer_list](../standard-library/initializer-list.md) .

### <a name="return-value"></a>Dönüş Değeri

Tek öğeli-ekleme üye işlevleri, (1) ve (2), yeni öğenin unordered_multiset eklendiği konuma bir yineleyici döndürür.

Tek öğeli-ipucu üye işlevleri, (3) ve (4), yeni öğenin unordered_multiset eklendiği konuma işaret eden bir yineleyici döndürür.

### <a name="remarks"></a>Açıklamalar

Bu işlev tarafından geçersiz kılınan işaretçiler veya başvurular yok, ancak kapsayıcı için tüm yineleyiciler geçersiz kılınabilir.

Yalnızca bir öğenin eklenmesi sırasında, bir özel durum oluşturulursa, ancak kapsayıcının karma işlevinde gerçekleşmemişse kapsayıcının durumu değiştirilmez. Karma işlevde özel durum oluşturulursa, sonuç tanımsızdır. Birden çok öğenin eklenmesi sırasında, bir özel durum oluşturulursa, kapsayıcı belirtilmemiş ancak geçerli bir durumda bırakılır.

Kapsayıcının [value_type](../standard-library/map-class.md#value_type) , kapsayıcıya ait olan bir typedef ve set için `unordered_multiset<V>::value_type` tür `const V` .

Aralık üye işlevi (5), öğe değerlerinin dizisini aralıktaki bir yineleyici tarafından bahsedilen her öğeye karşılık gelen bir unordered_multiset ekler `[First, Last)` ; Bu nedenle, *Last* eklenmez. Kapsayıcı üye işlevi, `end()` kapsayıcıdaki son öğeden hemen sonra gelen konumu ifade eder; örneğin, ifade öğesine `m.insert(v.begin(), v.end());` tüm öğelerini ekler `v` `m` .

Başlatıcı listesi üye işlevi (6), öğeleri unordered_multiset kopyalamak için bir [initializer_list](../standard-library/initializer-list.md) kullanır.

Yerinde oluşturulmuş bir öğenin eklenmesi için — diğer bir deyişle, kopyalama veya taşıma işlemleri yapılmaz — [unordered_multiset:: emplace](#emplace) ve [unordered_multiset:: emplace_hint](#emplace_hint).

Kod örneği için bkz. [Çoklu küme:: INSERT](../standard-library/multiset-class.md#insert).

## <a name="unordered_multisetiterator"></a><a name="iterator"></a> unordered_multiset:: Yineleyici

Bir unordered_multiset öğeleri okuyabilen sabit bir [İleri Yineleyici](../standard-library/forward-iterator-tag-struct.md) sağlayan bir tür.

```cpp
typedef implementation-defined iterator;
```

### <a name="example"></a>Örnek

**Yineleyici**bildirme ve kullanma [begin](../standard-library/multiset-class.md#begin) örneğine örnek olarak bkz..

## <a name="unordered_multisetkey_eq"></a><a name="key_eq"></a> unordered_multiset:: key_eq

Depolanan karşılaştırma işlevi nesnesini alır.

```cpp
Pred key_eq() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, saklı karşılaştırma işlevi nesnesini döndürür.

### <a name="example"></a>Örnek

```cpp
// std__unordered_set__unordered_multiset_key_eq.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_multiset<char> Myset;
int main()
{
    Myset c1;

    Myset::key_equal cmpfn = c1.key_eq();
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

## <a name="unordered_multisetkey_equal"></a><a name="key_equal"></a> unordered_multiset:: key_equal

Karşılaştırma işlevinin türü.

```cpp
typedef Pred key_equal;
```

### <a name="remarks"></a>Açıklamalar

Tür, şablon parametresi için bir eş anlamlı `Pred` .

### <a name="example"></a>Örnek

```cpp
// std__unordered_set__unordered_multiset_key_equal.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_multiset<char> Myset;
int main()
{
    Myset c1;

    Myset::key_equal cmpfn = c1.key_eq();
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

## <a name="unordered_multisetkey_type"></a><a name="key_type"></a> unordered_multiset:: key_type

Bir sıralama anahtarının türü.

```cpp
typedef Key key_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, şablon parametresi için bir eş anlamlı `Key` .

### <a name="example"></a>Örnek

```cpp
// std__unordered_set__unordered_multiset_key_type.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_multiset<char> Myset;
int main()
{
    Myset c1;

    c1.insert('a');
    c1.insert('b');
    c1.insert('c');

    // display contents "[c] [b] [a]"
    for (Myset::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << "[" << *it << "] ";
    std::cout << std::endl;

    // add a value and reinspect
    Myset::key_type key = 'd';
    Myset::value_type val = key;
    c1.insert(val);

    for (Myset::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << "[" << *it << "] ";
    std::cout << std::endl;

    return (0);
}
```

```Output
[c] [b] [a]
[d] [c] [b] [a]
```

## <a name="unordered_multisetload_factor"></a><a name="load_factor"></a> unordered_multiset:: load_factor

Demet başına ortalama öğeyi sayar.

```cpp
float load_factor() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi `(float)` [unordered_multiset:: size](#size) `() / (float)` [unordered_multiset:: bucket_count](#bucket_count) `()` , demet başına düşen ortalama öğe sayısını döndürür.

### <a name="example"></a>Örnek

```cpp
// std__unordered_set__unordered_multiset_load_factor.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_multiset<char> Myset;
int main()
{
    Myset c1;

    c1.insert('a');
    c1.insert('b');
    c1.insert('c');

    // display contents "[c] [b] [a]"
    for (Myset::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << "[" << *it << "] ";
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

## <a name="unordered_multisetlocal_iterator"></a><a name="local_iterator"></a> unordered_multiset:: local_iterator

Demet yineleyicisinin türü.

```cpp
typedef T4 local_iterator;
```

### <a name="remarks"></a>Açıklamalar

Türü, bir demet için ileriye doğru Yineleyici işlevi görebilecek bir nesneyi tanımlar. Burada uygulama tanımlı tür için bir eş anlamlı olarak açıklanmaktadır `T4` .

### <a name="example"></a>Örnek

```cpp
// std__unordered_set__unordered_multiset_local_iterator.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_multiset<char> Myset;
int main()
{
    Myset c1;

    c1.insert('a');
    c1.insert('b');
    c1.insert('c');

    // display contents "[c] [b] [a]"
    for (Myset::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << "[" << *it << "] ";
    std::cout << std::endl;

    // inspect bucket containing 'a'
    Myset::local_iterator lit = c1.begin(c1.bucket('a'));
    std::cout << "[" << *lit << "] ";

    return (0);
}
```

```Output
[c] [b] [a]
[a]
```

## <a name="unordered_multisetmax_bucket_count"></a><a name="max_bucket_count"></a> unordered_multiset:: max_bucket_count

En yüksek demet sayısını alır.

```cpp
size_type max_bucket_count() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, şu anda izin verilen en fazla demet sayısını döndürür.

### <a name="example"></a>Örnek

```cpp
// std__unordered_set__unordered_multiset_max_bucket_count.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_multiset<char> Myset;
int main()
{
    Myset c1;

    c1.insert('a');
    c1.insert('b');
    c1.insert('c');

    // display contents "[c] [b] [a]"
    for (Myset::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << "[" << *it << "] ";
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
[c] [b] [a]
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

## <a name="unordered_multisetmax_load_factor"></a><a name="max_load_factor"></a> unordered_multiset:: max_load_factor

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
// std__unordered_set__unordered_multiset_max_load_factor.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_multiset<char> Myset;
int main()
{
    Myset c1;

    c1.insert('a');
    c1.insert('b');
    c1.insert('c');

    // display contents "[c] [b] [a]"
    for (Myset::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << "[" << *it << "] ";
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
[c] [b] [a]
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

## <a name="unordered_multisetmax_size"></a><a name="max_size"></a> unordered_multiset:: max_size

Denetlenen dizinin en büyük boyutunu alır.

```cpp
size_type max_size() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, nesnenin denetleyecan en uzun sırasının uzunluğunu döndürür.

### <a name="example"></a>Örnek

```cpp
// std__unordered_set__unordered_multiset_max_size.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_multiset<char> Myset;
int main()
{
    Myset c1;

    std::cout << "max_size() == " << c1.max_size() << std::endl;

    return (0);
}
```

```Output
max_size() == 4294967295
```

## <a name="unordered_multisetoperator"></a><a name="op_eq"></a> unordered_multiset:: operator =

Bir karma tabloya kopyalar.

```cpp
unordered_multiset& operator=(const unordered_multiset& right);

unordered_multiset& operator=(unordered_multiset&& right);
```

### <a name="parameters"></a>Parametreler

*Right*\
İçine kopyalandığı [unordered_multiset](../standard-library/unordered-multiset-class.md) `unordered_multiset` .

### <a name="remarks"></a>Açıklamalar

İçindeki varolan öğeleri sildikten sonra `unordered_multiset` , ' `operator=` nin içeriğini kopyalar ya da içine *taşısa* `unordered_multiset` .

### <a name="example"></a>Örnek

```cpp
// unordered_multiset_operator_as.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

int main( )
{
    using namespace std;
    unordered_multiset<int> v1, v2, v3;
    unordered_multiset<int>::iterator iter;

    v1.insert(10);

    cout << "v1 = " ;
    for (iter = v1.begin(); iter != v1.end(); iter++)
        cout << *iter << " ";
    cout << endl;

    v2 = v1;
    cout << "v2 = ";
    for (iter = v2.begin(); iter != v2.end(); iter++)
        cout << *iter << " ";
    cout << endl;

    // move v1 into v2
    v2.clear();
    v2 = move(v1);
    cout << "v2 = ";
    for (iter = v2.begin(); iter != v2.end(); iter++)
        cout << *iter << " ";
    cout << endl;
}
```

## <a name="unordered_multisetpointer"></a><a name="pointer"></a> unordered_multiset::p oınter

Bir öğe için bir işaretçi türü.

```cpp
typedef Alloc::pointer pointer;
```

### <a name="remarks"></a>Açıklamalar

Türü, denetlenen sıranın bir öğesi için bir işaretçi olarak işlev görebilecek bir nesneyi tanımlar.

### <a name="example"></a>Örnek

```cpp
// std__unordered_set__unordered_multiset_pointer.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_multiset<char> Myset;
int main()
{
    Myset c1;

    c1.insert('a');
    c1.insert('b');
    c1.insert('c');

    // display contents "[c] [b] [a]"
    for (Myset::iterator it = c1.begin();
        it != c1.end(); ++it)
        {
        Myset::key_type key = *it;
        Myset::pointer p = &key;
        std::cout << "[" << *p << "] ";
        }
    std::cout << std::endl;

    return (0);
}
```

```Output
[c] [b] [a]
```

## <a name="unordered_multisetreference"></a><a name="reference"></a> unordered_multiset:: Reference

Bir öğe için bir başvuru türü.

```cpp
typedef Alloc::reference reference;
```

### <a name="remarks"></a>Açıklamalar

Türü, denetlenen sıranın bir öğesine başvuru olarak işlev görebilecek bir nesne tanımlar.

### <a name="example"></a>Örnek

```cpp
// std__unordered_set__unordered_multiset_reference.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_multiset<char> Myset;
int main()
{
    Myset c1;

    c1.insert('a');
    c1.insert('b');
    c1.insert('c');

    // display contents "[c] [b] [a]"
    for (Myset::iterator it = c1.begin();
        it != c1.end(); ++it)
        {
        Myset::key_type key = *it;
        Myset::reference ref = key;
        std::cout << "[" << ref << "] ";
        }
    std::cout << std::endl;

    return (0);
}
```

```Output
[c] [b] [a]
```

## <a name="unordered_multisetrehash"></a><a name="rehash"></a> unordered_multiset:: yeniden karma

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
// std__unordered_set__unordered_multiset_rehash.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_multiset<char> Myset;
int main()
{
    Myset c1;

    c1.insert('a');
    c1.insert('b');
    c1.insert('c');

    // display contents "[c] [b] [a]"
    for (Myset::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << "[" << *it << "] ";
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
[c] [b] [a]
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

## <a name="unordered_multisetsize"></a><a name="size"></a> unordered_multiset:: size

Öğe sayısını sayar.

```cpp
size_type size() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi denetlenen sıranın uzunluğunu döndürür.

### <a name="example"></a>Örnek

```cpp
// std__unordered_set__unordered_multiset_size.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_multiset<char> Myset;
int main()
{
    Myset c1;

    c1.insert('a');
    c1.insert('b');
    c1.insert('c');

    // display contents "[c] [b] [a]"
    for (Myset::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << "[" << *it << "] ";
    std::cout << std::endl;

    // clear the container and reinspect
    c1.clear();
    std::cout << "size == " << c1.size() << std::endl;
    std::cout << "empty() == " << std::boolalpha << c1.empty() << std::endl;
    std::cout << std::endl;

    c1.insert('d');
    c1.insert('e');

    // display contents "[e] [d]"
    for (Myset::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << "[" << *it << "] ";
    std::cout << std::endl;

    std::cout << "size == " << c1.size() << std::endl;
    std::cout << "empty() == " << std::boolalpha << c1.empty() << std::endl;

    return (0);
}
```

```Output
[c] [b] [a]
size == 0
empty() == true

[e] [d]
size == 2
empty() == false
```

## <a name="unordered_multisetsize_type"></a><a name="size_type"></a> unordered_multiset:: size_type

İki öğe arasındaki işaretsiz bir mesafenin türü.

```cpp
typedef T2 size_type;
```

### <a name="remarks"></a>Açıklamalar

İşaretsiz tamsayı türü, denetlenen bir dizinin uzunluğunu temsil eden bir nesneyi tanımlar. Burada uygulama tanımlı tür için bir eş anlamlı olarak açıklanmaktadır `T2` .

### <a name="example"></a>Örnek

```cpp
// std__unordered_set__unordered_multiset_size_type.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_multiset<char> Myset;
int main()
{
    Myset c1;
    Myset::size_type sz = c1.size();

    std::cout << "size == " << sz << std::endl;

    return (0);
}
```

```Output
size == 0
```

## <a name="unordered_multisetswap"></a><a name="swap"></a> unordered_multiset:: swap

İki kapsayıcının içeriğinin yerini değiştirir.

```cpp
void swap(unordered_multiset& right);
```

### <a name="parameters"></a>Parametreler

*Right*\
İle takas edilecek kapsayıcı.

### <a name="remarks"></a>Açıklamalar

Üye işlevi, ve sağ arasındaki denetlenen dizileri **`*this`** değiştirir *right*. [Unordered_multiset:: get_allocator](#get_allocator) `() == right.get_allocator()` , bu, sabit bir zamanda, yalnızca türünde depolanan nitelikler nesnesini kopyalamanın bir sonucu olarak bir özel durum oluşturur `Tr` ve iki denetimli sırada öğeleri belirten başvuruları, işaretçileri veya yineleyicileri geçersiz kılar. Aksi takdirde, bir dizi öğe ataması ve Oluşturucu çağrısı, iki denetimli dizi içindeki öğe sayısıyla orantılı olarak gerçekleştirilir.

### <a name="example"></a>Örnek

```cpp
// std__unordered_set__unordered_multiset_swap.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_multiset<char> Myset;
int main()
{
    Myset c1;

    c1.insert('a');
    c1.insert('b');
    c1.insert('c');

    // display contents "[c] [b] [a]"
    for (Myset::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << "[" << *it << "] ";
    std::cout << std::endl;

    Myset c2;

    c2.insert('d');
    c2.insert('e');
    c2.insert('f');

    c1.swap(c2);

    // display contents "[f] [e] [d]"
    for (Myset::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << "[" << *it << "] ";
    std::cout << std::endl;

    swap(c1, c2);

    // display contents "[c] [b] [a]"
    for (Myset::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << "[" << *it << "] ";
    std::cout << std::endl;

    return (0);
}
```

```Output
[c] [b] [a]
[f] [e] [d]
[c] [b] [a]
```

## <a name="unordered_multisetunordered_multiset"></a><a name="unordered_multiset"></a> unordered_multiset:: unordered_multiset

Bir kapsayıcı nesnesi oluşturur.

```cpp
unordered_multiset(
    const unordered_multiset& Right);

explicit unordered_multiset(
    size_type Bucket_count = N0,
    const Hash& Hash = Hash(),
    const Comp& Comp = Comp(),
    const Allocator& Al = Alloc());

unordered_multiset(
    unordered_multiset&& Right);

unordered_set(
    initializer_list<Type> IList);

unordered_set(
    initializer_list<Typ> IList,
    size_type Bucket_count);

unordered_set(
    initializer_list<Type> IList,
    size_type Bucket_count,
    const Hash& Hash);

unordered_set(
    initializer_list<Type> IList,
    size_type Bucket_count,
    const Hash& Hash,
    const Key& Key);

unordered_set(
    initializer_list<Type> IList,
    size_type Bucket_count,
    const Hash& Hash,
    const Key& Key,
    const Allocator& Al);

template <class InputIterator>
unordered_multiset(
    InputIterator First,
    InputIterator Last,
    size_type Bucket_count = N0,
    const Hash& Hash = Hash(),
    const Comp& Comp = Comp(),
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
Kopyalamanın initializer_list.

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu, *sağdan*denetlenen sıranın bir kopyasını belirtir. İkinci oluşturucu boş bir denetlenmiş dizi belirtir. Üçüncü Oluşturucu öğe değerlerinin dizisini ekler `[First, Last)` . Dördüncü Oluşturucu *sağ*taşıyarak sıranın bir kopyasını belirtir.

Ayrıca, tüm oluşturucular çeşitli depolanmış değerleri başlatır. Kopya Oluşturucu için değerler *sağdan*alınır. Aksi durumda:.

Varsa, en düşük demet sayısı *Bucket_count*bağımsız değişkendir; Aksi takdirde, burada uygulama tanımlı değer olarak açıklanan varsayılan bir değerdir `N0` .

Karma işlev nesnesi varsa bağımsız değişken *karmasıdır*; Aksi takdirde, `Hash()` .

Karşılaştırma işlevi nesnesi, varsa, *comp*bağımsız değişkenidir; Aksi takdirde, `Comp()` .

Ayırıcı nesne varsa *Al*bağımsız değişkenidir; Aksi takdirde, `Alloc()` .

## <a name="unordered_multisetvalue_type"></a><a name="value_type"></a> unordered_multiset:: value_type

Öğenin türü.

```cpp
typedef Key value_type;
```

### <a name="remarks"></a>Açıklamalar

Tür denetimli sıranın bir öğesini açıklar.

### <a name="example"></a>Örnek

```cpp
// std__unordered_set__unordered_multiset_value_type.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_multiset<char> Myset;
int main()
{
    Myset c1;

    c1.insert('a');
    c1.insert('b');
    c1.insert('c');

    // display contents "[c] [b] [a]"
    for (Myset::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << "[" << *it << "] ";
    std::cout << std::endl;

    // add a value and reinspect
    Myset::key_type key = 'd';
    Myset::value_type val = key;
    c1.insert(val);

    for (Myset::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << "[" << *it << "] ";
    std::cout << std::endl;

    return (0);
}
```

```Output
[c] [b] [a]
[d] [c] [b] [a]
```

## <a name="see-also"></a>Ayrıca bkz.

[<unordered_set>](../standard-library/unordered-set.md)\
[Kapsayıcıları](./stl-containers.md)\
[C++ standart kitaplığı 'nda iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[C++ standart kitaplığı başvurusu](../standard-library/cpp-standard-library-reference.md)
