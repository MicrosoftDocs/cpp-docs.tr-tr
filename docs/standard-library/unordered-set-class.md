---
title: unordered_set sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- unordered_set/std::unordered_set
- unordered_set/std::unordered_set::allocator_type
- unordered_set/std::unordered_set::const_iterator
- unordered_set/std::unordered_set::const_local_iterator
- unordered_set/std::unordered_set::const_pointer
- unordered_set/std::unordered_set::const_reference
- unordered_set/std::unordered_set::difference_type
- unordered_set/std::unordered_set::hasher
- unordered_set/std::unordered_set::iterator
- unordered_set/std::unordered_set::key_equal
- unordered_set/std::unordered_set::key_type
- unordered_set/std::unordered_set::local_iterator
- unordered_set/std::unordered_set::pointer
- unordered_set/std::unordered_set::reference
- unordered_set/std::unordered_set::size_type
- unordered_set/std::unordered_set::value_type
- unordered_set/std::unordered_set::begin
- unordered_set/std::unordered_set::bucket
- unordered_set/std::unordered_set::bucket_count
- unordered_set/std::unordered_set::bucket_size
- unordered_set/std::unordered_set::cbegin
- unordered_set/std::unordered_set::cend
- unordered_set/std::unordered_set::clear
- unordered_set/std::unordered_set::count
- unordered_set/std::unordered_set::emplace
- unordered_set/std::unordered_set::emplace_hint
- unordered_set/std::unordered_set::empty
- unordered_set/std::unordered_set::end
- unordered_set/std::unordered_set::equal_range
- unordered_set/std::unordered_set::erase
- unordered_set/std::unordered_set::find
- unordered_set/std::unordered_set::get_allocator
- unordered_set/std::unordered_set::hash
- unordered_set/std::unordered_set::insert
- unordered_set/std::unordered_set::key_eq
- unordered_set/std::unordered_set::load_factor
- unordered_set/std::unordered_set::max_bucket_count
- unordered_set/std::unordered_set::max_load_factor
- unordered_set/std::unordered_set::max_size
- unordered_set/std::unordered_set::rehash
- unordered_set/std::unordered_set::size
- unordered_set/std::unordered_set::swap
- unordered_set/std::unordered_set::unordered_set
- unordered_set/std::unordered_set::operator=
- unordered_set/std::unordered_set::hash_function
dev_langs:
- C++
helpviewer_keywords:
- std::unordered_set
- std::unordered_set::allocator_type
- std::unordered_set::const_iterator
- std::unordered_set::const_local_iterator
- std::unordered_set::const_pointer
- std::unordered_set::const_reference
- std::unordered_set::difference_type
- std::unordered_set::hasher
- std::unordered_set::iterator
- std::unordered_set::key_equal
- std::unordered_set::key_type
- std::unordered_set::local_iterator
- std::unordered_set::pointer
- std::unordered_set::reference
- std::unordered_set::size_type
- std::unordered_set::value_type
- std::unordered_set::begin
- std::unordered_set::bucket
- std::unordered_set::bucket_count
- std::unordered_set::bucket_size
- std::unordered_set::cbegin
- std::unordered_set::cend
- std::unordered_set::clear
- std::unordered_set::count
- std::unordered_set::emplace
- std::unordered_set::emplace_hint
- std::unordered_set::empty
- std::unordered_set::end
- std::unordered_set::equal_range
- std::unordered_set::erase
- std::unordered_set::find
- std::unordered_set::get_allocator
- std::unordered_set::hash
- std::unordered_set::insert
- std::unordered_set::key_eq
- std::unordered_set::load_factor
- std::unordered_set::max_bucket_count
- std::unordered_set::max_load_factor
- std::unordered_set::max_size
- std::unordered_set::rehash
- std::unordered_set::size
- std::unordered_set::swap
- std::unordered_set::unordered_set
- std::unordered_set::operator=
- std::unordered_set::allocator_type
- std::unordered_set::const_iterator
- std::unordered_set::const_local_iterator
- std::unordered_set::const_pointer
- std::unordered_set::const_reference
- std::unordered_set::difference_type
- std::unordered_set::hasher
- std::unordered_set::iterator
- std::unordered_set::key_equal
- std::unordered_set::key_type
- std::unordered_set::local_iterator
- std::unordered_set::pointer
- std::unordered_set::reference
- std::unordered_set::size_type
- std::unordered_set::value_type
- std::unordered_set::begin
- std::unordered_set::bucket
- std::unordered_set::bucket_count
- std::unordered_set::bucket_size
- std::unordered_set::cbegin
- std::unordered_set::cend
- std::unordered_set::clear
- std::unordered_set::count
- std::unordered_set::emplace
- std::unordered_set::emplace_hint
- std::unordered_set::empty
- std::unordered_set::end
- std::unordered_set::equal_range
- std::unordered_set::erase
- std::unordered_set::find
- std::unordered_set::get_allocator
- std::unordered_set::hash_function
- std::unordered_set::insert
- std::unordered_set::key_eq
- std::unordered_set::load_factor
- std::unordered_set::max_bucket_count
- std::unordered_set::max_load_factor
- std::unordered_set::max_size
- std::unordered_set::rehash
- std::unordered_set::size
- std::unordered_set::swap
ms.assetid: ac08084e-05a7-48c0-9ae4-d40c529922dd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dba290e01ae05021c55b824456384c5f6199991e
ms.sourcegitcommit: 1d9bd38cacbc783fccd3884b7b92062161c91c84
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/03/2018
ms.locfileid: "48236068"
---
# <a name="unorderedset-class"></a>unordered_set Sınıfı

Şablon sınıfı bir türdeki öğelerin değişen uzunluktaki dizisini denetleyen bir nesneyi tanımlayan `const Key`. Dizi çağrılan demetlerin sıralı bir dizi kümesini bölümleyen bir karma işlev tarafından zayıf bir şekilde sıralanır. Her bir demette herhangi bir öğe çiftinin eşdeğer sıralamaya sahip olup olmadığını belirleyen bir karşılaştırma işlevi vardır. Her bir öğe hem bir sıralama anahtarı hem de bir değer depolar. Dizi, en azından tüm demetleri kabaca eşit uzunlukta olduğunda, dizideki (sabit zaman) öğe sayısından bağımsız olabilen işlem sayısına sahip rastgele bir öğenin aranması, eklenmesi ve kaldırılmasına izin verecek şekilde temsil edilir. En kötü durumda, tüm öğeler tek bir demet içinde olduğunda işlem sayısı dizideki (doğrusal zaman) öğelerin sayısıyla orantılıdır. Ayrıca, bir öğe eklenmesi hiçbir yineleyiciyi geçersiz kılmaz; bir öğenin kaldırılması yalnızca bu kaldırılan öğeyi gösteren yineleyicileri geçersiz kılar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <
   class Key,
   class Hash = std::hash<Key>,
   class Pred = std::equal_to<Key>,
   class Alloc = std::allocator<Key>>
class unordered_set;
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|-|-|
|*Key*|Anahtar türü.|
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
|[unordered_set](#unordered_set)|Bir kapsayıcı nesnesi oluşturur.|

|İşleçler|Açıklama|
|-|-|
|[unordered_set::operator=](#op_eq)|Bir karma tabloya kopyalar.|

## <a name="remarks"></a>Açıklamalar

Nesne depolanan iki nesneyi, türünde bir karşılaştırma işlev nesnesi çağırarak denetlediği diziyi sıralar[unordered_set::key_equal](#key_equal) ve karma işlev nesne türü[unordered_set::hasher](#hasher). Üye işlevini çağırarak depolanan birinci nesneye erişim[unordered_set::key_eq](#key_eq)`()`; ve üye işlevini çağırarak depolanan ikinci nesneye erişebilirsiniz[unordered_set::hash_function](#hash) `()`. Tüm değerler için özellikle `X` ve `Y` türü `Key`, çağrı `key_eq()(X, Y)` yalnızca iki bağımsız değişken eşdeğer sıralamaya sahipse true değerini döndürür; çağrı `hash_function()(keyval)` türündebirdeğerlerdağıtımıverir`size_t`. Şablon sınıfının aksine[unordered_multiset sınıfı](../standard-library/unordered-multiset-class.md), şablon sınıfın bir nesnesi `unordered_set` sağlar `key_eq()(X, Y)` her zaman değerinin denetlenen dizideki herhangi iki öğe için yanlış. (Anahtarlar benzersizdir.)

Nesne ayrıca, demet başına istenen ortalama öğe sayısını belirten en yüksek yük faktörünü depolar. Bir öğe eklenmesi neden olursa[unordered_set::load_factor](#load_factor) `()` en yüksek yük faktörünün aşılmasına, kapsayıcı demet sayısını artırır ve gerektiğinde karma tabloyu yeniden oluşturur.

Denetlenen dizideki öğelerin gerçek sırası karma işleve, karşılaştırma işlevine, ekleme sırasına, en yüksek yük faktörüne ve geçerli demet sayısına bağlıdır. Denetlenen dizideki öğelerin sırasını genelde tahmin edemezsiniz. Ancak, eşdeğer sıralamaya sahip öğelerin herhangi bir alt kümesinin her zaman denetlenen dizide bitişik olduğundan emin olabilirsiniz.

Nesneyi ayırır ve boşaltır türünde bir saklı ayırıcı nesnesi denetlediği dizi için depolama[unordered_set::allocator_type](#allocator_type). Böyle bir ayırıcı nesnenin şablon sınıfının bir nesnesiyle aynı dış arayüze sahip olması gerekir `allocator`. Depolanan ayırıcı nesnenin kapsayıcı nesne atandığında kopyalanmayacağını unutmayın.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<unordered_set >

**Namespace:** std

## <a name="allocator_type"></a>  unordered_set::allocator_type

Depolamayı yönetmek için bir ayırıcı türü.

```cpp
typedef Alloc allocator_type;
```

### <a name="remarks"></a>Açıklamalar

Şablon parametresi için bir eşanlamlı türüdür `Alloc`.

### <a name="example"></a>Örnek

```cpp
// std__unordered_set__unordered_set_allocator_type.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_set<char> Myset;
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

## <a name="begin"></a>  unordered_set::Begin

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
// unordered_set_begin.cpp
// compile using: cl.exe /EHsc /nologo /W4 /MTd
#include <unordered_set>
#include <iostream>

using namespace std;

typedef unordered_set<char> MySet;

int main()
{
    MySet c1;

    c1.insert('a');
    c1.insert('b');
    c1.insert('c');

    // display contents using range-based for
    for (auto it : c1) {
    cout << "[" << it << "] ";
    }

    cout << endl;

    // display contents using explicit for
    for (MySet::const_iterator it = c1.begin(); it != c1.end(); ++it) {
        cout << "[" << *it << "] ";
    }

    cout << std::endl;

    // display first two items
    MySet::iterator it2 = c1.begin();
    cout << "[" << *it2 << "] ";
    ++it2;
    cout << "[" << *it2 << "] ";
    cout << endl;

    // display bucket containing 'a'
    MySet::const_local_iterator lit = c1.begin(c1.bucket('a'));
    cout << "[" << *lit << "] ";

    return (0);
}
```

```Output
[a] [b] [c]
[a] [b] [c]
[a] [b]
[a]
```

## <a name="bucket"></a>  unordered_set::Bucket

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
// std__unordered_set__unordered_set_bucket.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_set<char> Myset;
int main()
{
    Myset c1;

    c1.insert('a');
    c1.insert('b');
    c1.insert('c');

    // display contents "[c] [b] [a] "
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)
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

## <a name="bucket_count"></a>  unordered_set::bucket_count

Demet sayısını alır.

```cpp
size_type bucket_count() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, geçerli demet sayısını döndürür.

### <a name="example"></a>Örnek

```cpp
// std__unordered_set__unordered_set_bucket_count.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_set<char> Myset;
int main()
{
    Myset c1;

    c1.insert('a');
    c1.insert('b');
    c1.insert('c');

    // display contents "[c] [b] [a] "
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)
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

## <a name="bucket_size"></a>  unordered_set::bucket_size

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
// std__unordered_set__unordered_set_bucket_size.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_set<char> Myset;
int main()
{
    Myset c1;

    c1.insert('a');
    c1.insert('b');
    c1.insert('c');

    // display contents "[c] [b] [a] "
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)
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

## <a name="cbegin"></a>  unordered_set::cbegin

Döndürür bir **const** aralıktaki ilk öğeyi adresleyen bir yineleyici.

```cpp
const_iterator cbegin() const;
```

### <a name="return-value"></a>Dönüş Değeri

A **const** aralığı veya konuma boş bir aralığın ilk öğesine konumundaki ileriye doğru erişim yineleyicisi (boş bir aralık için `cbegin() == cend()`).

### <a name="remarks"></a>Açıklamalar

Dönüş değeri ile `cbegin`, aralıktaki öğeler değiştirilemez.

Bu üye işlevi yerine kullanabileceğiniz `begin()` üye işlev dönüş değeri olacağını garanti etmek için `const_iterator`. Genellikle birlikte kullanılır[otomatik](../cpp/auto-cpp.md) kesinti anahtar sözcüğü, aşağıdaki örnekte gösterildiği gibi yazın. Örnekte, göz önünde bulundurun `Container` değiştirilebilir (olmayan **const**) destekleyen herhangi bir türdeki kapsayıcı `begin()` ve `cbegin()`.

```cpp
auto i1 = Container.begin();
// i1 isContainer<T>::iterator
auto i2 = Container.cbegin();

// i2 isContainer<T>::const_iterator
```

## <a name="cend"></a>  unordered_set::cend

Döndürür bir **const** konuma bir aralıktaki son öğeyi ele alan bir yineleyici.

```cpp
const_iterator cend() const;
```

### <a name="return-value"></a>Dönüş Değeri

A **const** aralığın sonunu yalnızca ileri erişim yineleyicisi.

### <a name="remarks"></a>Açıklamalar

`cend` bir yineleyicinin kendi aralığının sonunu geçmediğini sınamak için kullanılır.

Bu üye işlevi yerine kullanabileceğiniz `end()` üye işlev dönüş değeri olacağını garanti etmek için `const_iterator`. Genellikle birlikte kullanılır[otomatik](../cpp/auto-cpp.md) kesinti anahtar sözcüğü, aşağıdaki örnekte gösterildiği gibi yazın. Örnekte, göz önünde bulundurun `Container` değiştirilebilir (olmayan **const**) destekleyen herhangi bir türdeki kapsayıcı `end()` ve `cend()`.

```cpp
auto i1 = Container.end();
// i1 isContainer<T>::iterator
auto i2 = Container.cend();

// i2 isContainer<T>::const_iterator
```

Tarafından döndürülen değer `cend` kaldırılmamalıdır.

## <a name="clear"></a>  unordered_set::Clear

Tüm öğeleri kaldırır.

```cpp
void clear();
```

### <a name="remarks"></a>Açıklamalar

Üye işlev çağrıları[unordered_set::erase](#erase) `(` [unordered_set::begin](#begin) `(),` [unordered_set::end](#end)`())`.

### <a name="example"></a>Örnek

```cpp
// std__unordered_set__unordered_set_clear.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_set<char> Myset;
int main()
{
    Myset c1;

    c1.insert('a');
    c1.insert('b');
    c1.insert('c');

    // display contents "[c] [b] [a] "
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)
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
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)
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

## <a name="const_iterator"></a>  unordered_set::const_iterator

Denetlenen dizi için bir sabit yineleyici türü.

```cpp
typedef T1 const_iterator;
```

### <a name="remarks"></a>Açıklamalar

Denetlenen dizi için sabit bir ileriye doğru yineleyici olarak hizmet verebilen bir nesneyi tanımlayan bir tür. Açıklanmıştır uygulama tanımlı türünün eşanlamlısı olarak burada `T1`.

### <a name="example"></a>Örnek

```cpp
// std__unordered_set__unordered_set_const_iterator.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_set<char> Myset;
int main()
{
    Myset c1;

    c1.insert('a');
    c1.insert('b');
    c1.insert('c');

    // display contents "[c] [b] [a] "
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)
    std::cout << "[" << *it << "] ";
    std::cout << std::endl;

    return (0);
}
```

```Output
[c] [b] [a]
```

## <a name="const_local_iterator"></a>  unordered_set::const_local_iterator

Denetlenen dizi için bir sabit demet yineleyici türü.

```cpp
typedef T5 const_local_iterator;
```

### <a name="remarks"></a>Açıklamalar

Bir demet için sabit bir ileriye doğru yineleyici olarak hizmet verebilen bir nesneyi tanımlayan bir tür. Açıklanmıştır uygulama tanımlı türünün eşanlamlısı olarak burada `T5`.

### <a name="example"></a>Örnek

```cpp
// std__unordered_set__unordered_set_const_local_iterator.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_set<char> Myset;
int main()
{
    Myset c1;

    c1.insert('a');
    c1.insert('b');
    c1.insert('c');

    // display contents "[c] [b] [a] "
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)
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

## <a name="const_pointer"></a>  unordered_set::const_pointer

Bir öğe için sabit bir işaretçi türü.

```cpp
typedef Alloc::const_pointer const_pointer;
```

### <a name="remarks"></a>Açıklamalar

Denetlenen dizinin bir öğe için sabit bir işaretçi olarak hizmet verebilen bir nesneyi tanımlayan bir tür.

### <a name="example"></a>Örnek

```cpp
// std__unordered_set__unordered_set_const_pointer.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_set<char> Myset;
int main()
{
    Myset c1;

    c1.insert('a');
    c1.insert('b');
    c1.insert('c');

    // display contents "[c] [b] [a] "
    for (Myset::iterator it = c1.begin(); it != c1.end(); ++it)
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

## <a name="const_reference"></a>  unordered_set::const_reference

Bir öğe için sabit bir başvuru türü.

```cpp
typedef Alloc::const_reference const_reference;
```

### <a name="remarks"></a>Açıklamalar

Denetlenen dizinin bir öğe için sabit bir başvuru olarak hizmet verebilen bir nesneyi tanımlayan bir tür.

### <a name="example"></a>Örnek

```cpp
// std__unordered_set__unordered_set_const_reference.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_set<char> Myset;
int main()
{
    Myset c1;

    c1.insert('a');
    c1.insert('b');
    c1.insert('c');

    // display contents "[c] [b] [a] "
    for (Myset::iterator it = c1.begin(); it != c1.end(); ++it)
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

## <a name="count"></a>  unordered_set::Count

Belirtilen bir anahtar ile eşleşen öğe sayısını bulur.

```cpp
size_type count(const Key& keyval) const;
```

### <a name="parameters"></a>Parametreler

*keyval*<br/>
Aranacak anahtar değeri.

### <a name="remarks"></a>Açıklamalar

Üye işlevi tarafından ayrılmış aralıktaki öğelerin sayısını döndürür.[unordered_set::equal_range](#equal_range)`(keyval)`.

### <a name="example"></a>Örnek

```cpp
// std__unordered_set__unordered_set_count.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_set<char> Myset;
int main()
{
    Myset c1;

    c1.insert('a');
    c1.insert('b');
    c1.insert('c');

    // display contents "[c] [b] [a] "
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)
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

## <a name="difference_type"></a>  unordered_set::difference_type

İki öğe arasındaki işaretli mesafenin türü.

```cpp
typedef T3 difference_type;
```

### <a name="remarks"></a>Açıklamalar

İmzalı bir tamsayı türü adreslerini denetlenen dizideki herhangi iki öğe arasındaki farkı temsil edebilen bir nesneyi tanımlar. Açıklanmıştır uygulama tanımlı türünün eşanlamlısı olarak burada `T3`.

### <a name="example"></a>Örnek

```cpp
// std__unordered_set__unordered_set_difference_type.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_set<char> Myset;
int main()
{
    Myset c1;

    c1.insert('a');
    c1.insert('b');
    c1.insert('c');

    // display contents "[c] [b] [a] "
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)
        std::cout << "[" << *it << "] ";
    std::cout << std::endl;

    // compute positive difference
    Myset::difference_type diff = 0;
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)
        ++diff;
    std::cout << "end()-begin() == " << diff << std::endl;

    // compute negative difference
    diff = 0;
    for (Myset::const_iterator it = c1.end(); it != c1.begin(); --it)
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

## <a name="emplace"></a>  unordered_set::emplace

(Hiçbir kopyalama veya taşıma işlemleri gerçekleştirilir) yerinde oluşturulmuş bir öğe ekler.

```cpp
template <class... Args>
pair<iterator, bool>
emplace(
Args&&... args);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|-|-|
|*bağımsız değişken*|Bir öğenin değerini eşdeğer sıralı bir öğe içermiyorsa unordered_set eklenecek oluşturmak için iletilen bağımsız değişkenler.|

### <a name="return-value"></a>Dönüş Değeri

A `pair` olan **bool** bileşeni ekleme yaptıysanız true ve false değerini döndürür `unordered_set` anahtarı sıralama, eşdeğer bir değer vardı ve yineleyici bileşeni döndürür bir öğe zaten içeriyordu Burada yeni bir öğe eklendi veya öğenin zaten bulunduğu adres.

Yineleyici bileşen çifti erişmeye `pr` bu üye işlevi tarafından döndürülen, kullanın `pr.first`ve bu başvuru için `*(pr.first)`. Erişim için **bool** bileşen çifti `pr` bu üye işlevi tarafından döndürülen, kullanın `pr.second`.

### <a name="remarks"></a>Açıklamalar

Yineleyiciler ya da başvuruları, bu işlev tarafından geçersiz kılınır.

Bir özel durum oluşturulur ancak kapsayıcının karma işlevi gerçekleşmez kapsayıcı ekleme sırasında değiştirilmez. Karma işlev özel durum, sonuç tanımsızdır.

Kod örneği için bkz:[set::emplace](../standard-library/set-class.md#emplace).

## <a name="emplace_hint"></a>  unordered_set::emplace_hint

(Hiçbir kopyalama veya taşıma işlemleri gerçekleştirilir) bir yerleşim ipucuyla birlikte yerinde oluşturulmuş bir öğe ekler.

```cpp
template <class... Args>
iterator emplace_hint(
const_iteratorwhere,
Args&&... args);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|-|-|
|*bağımsız değişken*|Unordered_set bu öğeyi zaten içeriyor veya zaten anahtarı bir öğe içeriyorsa sürece daha genel olarak, eşdeğer sıralanır sürece unordered_set eklenecek bir öğe oluşturmak için iletilen bağımsız değişkenler.|
|*Burada*|Doğru ekleme noktasını için aramaya başlamak için yer ile ilgili bir ipucu.|

### <a name="return-value"></a>Dönüş Değeri

Yeni eklenen öğeye bir yineleyici.

Öğe zaten var olduğundan ekleme başarısız olursa var olan öğeye bir yineleyici döndürür.

### <a name="remarks"></a>Açıklamalar

Yineleyiciler ya da başvuruları, bu işlev tarafından geçersiz kılınır.

Bir özel durum oluşturulur ancak kapsayıcının karma işlevi gerçekleşmez kapsayıcı ekleme sırasında değiştirilmez. Karma işlev özel durum, sonuç tanımsızdır.

Kod örneği için bkz:[set::emplace_hint](../standard-library/set-class.md#emplace_hint).

## <a name="empty"></a>  unordered_set::empty

Bir öğe olup olmadığını sınar.

```cpp
bool empty() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi boş bir denetlenmiş dizi için true değerini döndürür.

### <a name="example"></a>Örnek

```cpp
// std__unordered_set__unordered_set_empty.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_set<char> Myset;
int main()
{
    Myset c1;

    c1.insert('a');
    c1.insert('b');
    c1.insert('c');

    // display contents "[c] [b] [a] "
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)
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
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)
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

## <a name="end"></a>  unordered_set::End

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
// std__unordered_set__unordered_set_end.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_set<char> Myset;
int main()
{
    Myset c1;

    c1.insert('a');
    c1.insert('b');
    c1.insert('c');

    // display contents "[c] [b] [a] "
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)
        std::cout << "[" << *it << "] ";
    std::cout << std::endl;

    // inspect last two items "[a] [b] "
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

## <a name="equal_range"></a>  unordered_set::equal_range

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

Üye işlevi Yineleyicilerin bir çiftini döndürür `X` şekilde`[X.first, X.second)` yalnızca öğeleri ile eşdeğer sıralamaya sahip denetlenen dizinin sınırlandırır *keyval*. Böyle bir öğe varsa, her iki yineleyiciler olan `end()`.

### <a name="example"></a>Örnek

```cpp
// std__unordered_set__unordered_set_equal_range.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_set<char> Myset;
int main()
{
    Myset c1;

    c1.insert('a');
    c1.insert('b');
    c1.insert('c');

    // display contents "[c] [b] [a] "
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)
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

## <a name="erase"></a>  unordered_set::ERASE

Bir öğenin veya öğelerin aralığını belirtilen konumlardan bir unordered_set kaldırır veya belirtilen bir anahtarla eşleşen öğeleri kaldırır.

```cpp
iterator erase(const_iterator Where);

iterator erase(const_iterator First, const_iterator Last);

size_type erase(const key_type& Key);
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

İlk iki üye işlevleri için çift yönlü bir yineleyici, kaldırılan tüm öğelerin veya böyle bir öğe varsa, unordered_set sonuna bir öğe dışında kalan ilk öğeyi belirtir.

Üye işlevi için üçüncü unordered_set kaldırılan öğelerin sayısını döndürür.

### <a name="remarks"></a>Açıklamalar

Kod örneği için bkz:[set::erase](../standard-library/set-class.md#erase).

## <a name="find"></a>  unordered_set::Find

Belirtilen bir anahtarla eşleşen bir öğeyi bulur.

```cpp
const_iterator find(const Key& keyval) const;
```

### <a name="parameters"></a>Parametreler

*keyval*<br/>
Aranacak anahtar değeri.

### <a name="remarks"></a>Açıklamalar

Üye işlevinin döndürdüğü[unordered_set::equal_range](#equal_range)`(keyval).first`.

### <a name="example"></a>Örnek

```cpp
// std__unordered_set__unordered_set_find.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_set<char> Myset;
int main()
{
    Myset c1;

    c1.insert('a');
    c1.insert('b');
    c1.insert('c');

    // display contents "[c] [b] [a] "
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)
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

## <a name="get_allocator"></a>  unordered_set::get_allocator

Depolanan ayırıcı nesnesini alır.

```cpp
Alloc get_allocator() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi saklı ayırıcı nesnesini döndürür.

### <a name="example"></a>Örnek

```cpp
// std__unordered_set__unordered_set_get_allocator.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_set<char> Myset;
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

## <a name="hash"></a>  unordered_set::hash_function

Depolanan karma işlevi nesnesini alır.

```cpp
Hash hash_function() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, depolanan karma işlevi nesnesini döndürür.

### <a name="example"></a>Örnek

```cpp
// std__unordered_set__unordered_set_hash_function.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_set<char> Myset;
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

## <a name="hasher"></a>  unordered_set::hasher

Karma işlevin türü.

```cpp
typedef Hash hasher;
```

### <a name="remarks"></a>Açıklamalar

Şablon parametresi için bir eşanlamlı türüdür `Hash`.

### <a name="example"></a>Örnek

```cpp
// std__unordered_set__unordered_set_hasher.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_set<char> Myset;
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

## <a name="insert"></a>  unordered_set::insert

Bir öğenin veya öğelerin aralığını bir unordered_set ekler.

```cpp
// (1) single element
pair<iterator, bool> insert(const value_type& Val);

// (2) single element, perfect forwarded
template <class ValTy>
pair<iterator, bool> insert(ValTy&& Val);

// (3) single element with hint
iterator insert(const_iterator Where, const value_type& Val);

// (4) single element, perfect forwarded, with hint
template <class ValTy>
iterator insert(const_iterator Where, ValTy&& Val);

// (5) range
template <class InputIterator>
void insert(InputIterator First, InputIterator Last);

// (6) initializer list
void insert(initializer_list<value_type> IList);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|-|-|
|*VAL*|Anahtarı eşdeğer sıralı bir öğe içermiyorsa unordered_set eklenecek bir öğenin değeri.|
|*Burada*|Doğru ekleme noktasını için aramaya başlamak için bir yerde.|
|*ValTy*|Unordered_set öğesi oluşturmak için kullanabileceğiniz bağımsız değişken türü belirten bir şablon parametresi[value_type](../standard-library/map-class.md#value_type)ve mükemmel ileten *Val* bağımsız değişken olarak.|
|*ilk*|Kopyalanacak ilk öğenin konumu.|
|*Son*|Kopyalanacak son öğenin ötesinde konumu.|
|*Inputıterator*|Gereksinimlerini karşılayan şablonu işlev bağımsız değişkeni bir[giriş yineleyici](../standard-library/input-iterator-tag-struct.md) oluşturmak için kullanılan bir tür öğelerine işaret eden[value_type](../standard-library/map-class.md#value_type) nesneleri.|
|*IList*|[İnitializer_list](../standard-library/initializer-list.md) öğeleri kopyalanacak.|

### <a name="return-value"></a>Dönüş Değeri

Tek öğeli üye işlevleri (1) ve (2) iade bir[çifti](../standard-library/pair-structure.md) olan **bool** bileşendir ekleme yaptıysanız true ve false unordered_set anahtarı olan bir öğe içeriyorsa bir sıralama, eşdeğer bir değer. Yineleyici bileşeni dönüş değeri çiftinin yeni eklenen öğeye işaret ederse **bool** bileşendir true veya var olan öğeye varsa **bool** bileşen değer false.

İpucu ile tek öğe üye işlevleri, (3) ve (4), yeni bir öğe unordered_set eklenen burada veya eşdeğer bir anahtara sahip bir öğe zaten var olan öğeye varsa konuma gösteren bir yineleyici döndürür.

### <a name="remarks"></a>Açıklamalar

Hiçbir yineleyiciler, işaretçiler veya başvurular, bu işlev tarafından geçersiz kılınır.

Bir özel durum oluşturulur ancak kapsayıcının karma işlevi gerçekleşmez yalnızca bir öğe ekleme sırasında kapsayıcının durumu değiştirilmez. Karma işlev özel durum, sonuç tanımsızdır. Bir özel durum oluşturulursa, birden çok öğe ekleme sırasında kapsayıcı belirtilmeyen ancak geçerli bir durumda bırakılır.

Yineleyici bileşeni erişmek için bir `pair` `pr` kullanın, tek öğeli üye işlevleri tarafından döndürülen `pr.first`; döndürülen çiftin içinde yineleyicinin başvuru kaldırma, kullanın`*pr.first`, size bir öğe sağlar. Erişim için **bool** bileşeni, kullanım `pr.second`. Bu makaledeki örnek kod örneği için bkz.

[Value_type](../standard-library/map-class.md#value_type) küme ve, kapsayıcıya ait bir tür tanımı, kapsayıcısıdır `unordered_set<V>::value_type` türü `const V`.

Aralık üye işlevi (5) aralığında bir yineleyici tarafından ele alınan her öğe için karşılık gelen bir unordered_set öğe değerleri dizisi ekler `[First, Last)`; bu nedenle *son* takılı. Kapsayıcı üye işlevi `end()` kapsayıcıdaki son öğeden hemen sonra konuma başvuran — Örneğin, deyim `s.insert(v.begin(), v.end());` tüm öğeleri ekleme girişiminde `v` içine `s`. Yalnızca benzersiz değerler aralığında olan öğeler eklenir; Yinelenen göz ardı edilir. Hangi öğelerin reddedilir gözlemlemek için tek öğeli sürümleri kullanın `insert`.

Başlatıcı listesinde üye işlev (6) kullanan bir[initializer_list](../standard-library/initializer-list.md) öğeleri unordered_set kopyalanacak.

Yerinde oluşturulmuş bir öğe ekleme — diğer bir deyişle, hiçbir kopyalama veya taşıma işlemleri gerçekleştirilir — bkz[set::emplace](../standard-library/set-class.md#emplace) ve[set::emplace_hint](../standard-library/set-class.md#emplace_hint).

Kod örneği için bkz:[set::insert](../standard-library/set-class.md#insert).

## <a name="iterator"></a>  unordered_set::iterator

Bir sabit sağlayan bir tür[ileriye doğru yineleyici](../standard-library/forward-iterator-tag-struct.md) bir unordered_set öğelerini okuyabilir.

```cpp
typedef implementation-defined iterator;
```

### <a name="example"></a>Örnek

Örneğin bakın[başlamak](../standard-library/set-class.md#begin) bildirme ve kullanma konusunda bir örnek için bir**yineleyici**.

## <a name="key_eq"></a>  unordered_set::key_eq

Depolanan karşılaştırma işlevi nesnesini alır.

```cpp
Pred key_eq() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, depolanan karşılaştırma işlevi nesnesini döndürür.

### <a name="example"></a>Örnek

```cpp
// std__unordered_set__unordered_set_key_eq.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_set<char> Myset;
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

## <a name="key_equal"></a>  unordered_set::key_equal

Karşılaştırma işlevinin türü.

```cpp
typedef Pred key_equal;
```

### <a name="remarks"></a>Açıklamalar

Şablon parametresi için bir eşanlamlı türüdür `Pred`.

### <a name="example"></a>Örnek

```cpp
// std__unordered_set__unordered_set_key_equal.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_set<char> Myset;
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

## <a name="key_type"></a>  unordered_set::key_type

Bir sıralama anahtarının türü.

```cpp
typedef Key key_type;
```

### <a name="remarks"></a>Açıklamalar

Şablon parametresi için bir eşanlamlı türüdür `Key`.

### <a name="example"></a>Örnek

```cpp
// std__unordered_set__unordered_set_key_type.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_set<char> Myset;
int main()
{
    Myset c1;

    c1.insert('a');
    c1.insert('b');
    c1.insert('c');

    // display contents "[c] [b] [a] "
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)
        std::cout << "[" << *it << "] ";
    std::cout << std::endl;

    // add a value and reinspect
    Myset::key_type key = 'd';
    Myset::value_type val = key;
    c1.insert(val);

    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)
        std::cout << "[" << *it << "] ";
    std::cout << std::endl;

    return (0);
}
```

```Output
[c] [b] [a]
[d] [c] [b] [a]
```

## <a name="load_factor"></a>  unordered_set::load_factor

Demet başına ortalama öğeyi sayar.

```cpp
float load_factor() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevinin döndürdüğü`(float)`[unordered_set::size](#size)`() / (float)`[unordered_set::bucket_count](#bucket_count)`()`, öğe demet başına ortalama sayısı.

### <a name="example"></a>Örnek

```cpp
// std__unordered_set__unordered_set_load_factor.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_set<char> Myset;
int main()
{
    Myset c1;

    c1.insert('a');
    c1.insert('b');
    c1.insert('c');

    // display contents "[c] [b] [a] "
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)
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

## <a name="local_iterator"></a>  unordered_set::local_iterator

Bir demet yineleyici türü.

```cpp
typedef T4 local_iterator;
```

### <a name="remarks"></a>Açıklamalar

Bir demet için ileriye doğru yineleyici olarak hizmet verebilen bir nesneyi tanımlayan bir tür. Açıklanmıştır uygulama tanımlı türünün eşanlamlısı olarak burada `T4`.

### <a name="example"></a>Örnek

```cpp
// std__unordered_set__unordered_set_local_iterator.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_set<char> Myset;
int main()
{
    Myset c1;

    c1.insert('a');
    c1.insert('b');
    c1.insert('c');

    // display contents "[c] [b] [a] "
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)
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

## <a name="max_bucket_count"></a>  unordered_set::max_bucket_count

En yüksek demet sayısını alır.

```cpp
size_type max_bucket_count() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, demet şu anda izin verilen en büyük sayısını döndürür.

### <a name="example"></a>Örnek

```cpp
// std__unordered_set__unordered_set_max_bucket_count.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_set<char> Myset;
int main()
{
    Myset c1;

    c1.insert('a');
    c1.insert('b');
    c1.insert('c');

    // display contents "[c] [b] [a] "
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)
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

## <a name="max_load_factor"></a>  unordered_set::max_load_factor

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
// std__unordered_set__unordered_set_max_load_factor.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_set<char> Myset;
int main()
{
    Myset c1;

    c1.insert('a');
    c1.insert('b');
    c1.insert('c');

    // display contents "[c] [b] [a] "
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)
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

## <a name="max_size"></a>  unordered_set::max_size

Denetlenen dizinin en büyük boyutunu alır.

```cpp
size_type max_size() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, nesneyi de denetleyebilir kastetmek uzunluğunu döndürür.

### <a name="example"></a>Örnek

```cpp
// std__unordered_set__unordered_set_max_size.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_set<char> Myset;
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

## <a name="op_eq"></a>  unordered_set::operator=

Bir karma tabloya kopyalar.

```cpp
unordered_set& operator=(const unordered_set& right);

unordered_set& operator=(unordered_set&& right);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|-|-|
|*sağ*|[Unordered_set](../standard-library/unordered-set-class.md) içine kopyalanan `unordered_set`.|

### <a name="remarks"></a>Açıklamalar

Var olan tüm öğeleri silme sonra bir `unordered_set`, `operator=` kopyalar veya içeriğini hareket *doğru* içine `unordered_set`.

### <a name="example"></a>Örnek

```cpp
// unordered_set_operator_as.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

int main( )
{
    using namespace std;
    unordered_set<int> v1, v2, v3;
    unordered_set<int>::iterator iter;

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

## <a name="pointer"></a>  unordered_set::pointer

Bir öğe için bir işaretçi türü.

```cpp
typedef Alloc::pointer pointer;
```

### <a name="remarks"></a>Açıklamalar

Denetlenen dizinin öğeye bir işaretçi olarak hizmet verebilen bir nesneyi tanımlayan bir tür.

### <a name="example"></a>Örnek

```cpp
// std__unordered_set__unordered_set_pointer.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_set<char> Myset;
int main()
{
    Myset c1;

    c1.insert('a');
    c1.insert('b');
    c1.insert('c');

    // display contents "[c] [b] [a] "
    for (Myset::iterator it = c1.begin(); it != c1.end(); ++it)
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

## <a name="reference"></a>  unordered_set::reference

Bir öğe için bir başvuru türü.

```cpp
typedef Alloc::reference reference;
```

### <a name="remarks"></a>Açıklamalar

Denetlenen dizinin bir öğesine bir başvuru olarak hizmet verebilen bir nesneyi tanımlayan bir tür.

### <a name="example"></a>Örnek

```cpp
// std__unordered_set__unordered_set_reference.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_set<char> Myset;
int main()
{
    Myset c1;

    c1.insert('a');
    c1.insert('b');
    c1.insert('c');

    // display contents "[c] [b] [a] "
    for (Myset::iterator it = c1.begin(); it != c1.end(); ++it)
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

## <a name="rehash"></a>  unordered_set::rehash

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
// std__unordered_set__unordered_set_rehash.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_set<char> Myset;
int main()
{
    Myset c1;

    c1.insert('a');
    c1.insert('b');
    c1.insert('c');

    // display contents "[c] [b] [a] "
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)
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

## <a name="size"></a>  unordered_set::size

Öğe sayısını sayar.

```cpp
size_type size() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, denetlenen dizinin uzunluğunu döndürür.

### <a name="example"></a>Örnek

```cpp
// std__unordered_set__unordered_set_size.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_set<char> Myset;
int main()
{
    Myset c1;

    c1.insert('a');
    c1.insert('b');
    c1.insert('c');

    // display contents "[c] [b] [a] "
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)
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
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)
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

## <a name="size_type"></a>  unordered_set::size_type

İki öğe arasındaki işaretsiz bir mesafenin türü.

```cpp
typedef T2 size_type;
```

### <a name="remarks"></a>Açıklamalar

İşaretsiz tamsayı türü, denetlenen bir dizi uzunluğunu temsil edebilen bir nesneyi tanımlar. Açıklanmıştır uygulama tanımlı türünün eşanlamlısı olarak burada `T2`.

### <a name="example"></a>Örnek

```cpp
// std__unordered_set__unordered_set_size_type.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_set<char> Myset;
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

## <a name="swap"></a>  unordered_set::Swap

İki kapsayıcının içeriğinin yerini değiştirir.

```cpp
void swap(unordered_set& right);
```

### <a name="parameters"></a>Parametreler

*sağ*<br/>
İle takas için kapsayıcı.

### <a name="remarks"></a>Açıklamalar

Denetlenen diziyi üye işlevi değiştirir `*this` ve *doğru*. Varsa [unordered_set::get_allocator](#get_allocator)`() == right.get_allocator()`depolanan özellikleri nesnesinin türü kopyalama sonucunda yalnızca özel durum oluşturur, bunu sabit sürede yapar `Tr`, hiçbir başvurular, işaretçiler, gösteren geçersiz kılar veya Bu yineleyiciler iki denetlenen dizinin öğelerini belirleyin. Aksi takdirde, bir dizi öğesi atamalar ve oluşturucu çağrıları öğelerin sayısını orantılı iki denetimli sıralarında gerçekleştirir.

### <a name="example"></a>Örnek

```cpp
// std__unordered_set__unordered_set_swap.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_set<char> Myset;
int main()
{
    Myset c1;

    c1.insert('a');
    c1.insert('b');
    c1.insert('c');

    // display contents "[c] [b] [a] "
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)
        std::cout << "[" << *it << "] ";
    std::cout << std::endl;

    Myset c2;

    c2.insert('d');
    c2.insert('e');
    c2.insert('f');

    c1.swap(c2);

    // display contents "[f] [e] [d] "
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)
        std::cout << "[" << *it << "] ";
    std::cout << std::endl;

    swap(c1, c2);

    // display contents "[c] [b] [a] "
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)
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

## <a name="unordered_set"></a>  unordered_set::unordered_set

Bir kapsayıcı nesnesi oluşturur.

```cpp
unordered_set(const unordered_set& Right);

explicit unordered_set(
    size_typebucket_count = N0,
    const Hash& Hash = Hash(),
    const Comp& Comp = Comp(),
    const Allocator& Al = Alloc());

unordered_set(unordered_set&& Right);

unordered_set(initializer_list<Type> IList);

unordered_set(initializer_list<Type> IList, size_typebucket_count);

unordered_set(
    initializer_list<Type> IList,
    size_typebucket_count,
    const Hash& Hash);

unordered_set(
    initializer_list<Type> IList,
    size_typebucket_count,
    const Hash& Hash,
    const Comp& Comp);

unordered_set(
    initializer_list<Type> IList,
    size_typebucket_count,
    const Hash& Hash,
    const Comp& Comp,
    const Allocator& Al);

template <class InputIterator>
unordered_set(
    InputIteratorfirst,
    InputIteratorlast,
    size_typebucket_count = N0,
    const Hash& Hash = Hash(),
    const Comp& Comp = Comp(),
    const Allocator& Al = Alloc());
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|-|-|
|*Inputıterator*|Yineleyici türü.|
|*Al*|Depolanacak ayırıcı nesne.|
|*Comp*|Depolanacak karşılaştırma işlevi nesnesi.|
|*Karma*|Depolanacak karma işlev nesnesi.|
|*bucket_count*|En düşük demet sayısı.|
|*sağ*|Kopyalanacak kapsayıcı.|
|*IList*|Kopyalanacak öğe içeren initializer_list.|

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu tarafından denetlenen dizinin bir kopyasını belirtir *sağ*. İkinci oluşturucu boş bir denetlenmiş dizi belirtir. Üçüncü Oluşturucu taşıyarak dizinin bir kopyasını belirtir. *sağ* sekizinci oluşturucular aracılığıyla dördüncü kopyalanacak öğe belirtmek için bir initializer_list kullanır. Dokuzuncu Oluşturucu öğe değerleri dizisi ekler`[first, last)`.

Ayrıca, tüm oluşturucular çeşitli depolanmış değerleri başlatır. Kopya oluşturucusu için gelen değerler elde edilir *sağ*. Aksi durumda:.

Demetler en az sayıda bağımsız değişken olan *bucket_count*, aksi takdirde mevcut açıklanan varsayılan bir değer olup olmadığını burada uygulama tanımlı değer olarak `N0`.

Karma işlev nesnesi bağımsız değişken olan *karma*, mevcut; Aksi durumda, `Hash()`.

Karşılaştırma işlevi nesnesini bağımsız değişken olan *kompozisyonu*, mevcut; Aksi durumda, `Comp()`.

Bağımsız değişken ayırıcısı nesnedir *Al*, mevcut; Aksi durumda, `Alloc()`.

## <a name="value_type"></a>  unordered_set::value_type

Öğenin türü.

```cpp
typedef Key value_type;
```

### <a name="remarks"></a>Açıklamalar

Denetlenen dizinin bir öğe türü açıklar.

### <a name="example"></a>Örnek

```cpp
// std__unordered_set__unordered_set_value_type.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_set<char> Myset;
int main()
{
    Myset c1;

    c1.insert('a');
    c1.insert('b');
    c1.insert('c');

    // display contents "[c] [b] [a] "
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)
        std::cout << "[" << *it << "] ";
    std::cout << std::endl;

    // add a value and reinspect
    Myset::key_type key = 'd';
    Myset::value_type val = key;
    c1.insert(val);

    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)
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

[<unordered_set>](../standard-library/unordered-set.md)<br/>
[Kapsayıcılar](../cpp/containers-modern-cpp.md)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)<br/>
