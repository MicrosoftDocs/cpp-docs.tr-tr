---
title: "unordered_multiset sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
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
dev_langs: C++
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
caps.latest.revision: "24"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a958bf441809da24b317b777fd2f79946f3dc727
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="unorderedmultiset-class"></a>unordered_multiset Sınıfı
Şablon sınıfı türündeki öğeler değişen uzunluk dizisi denetleyen bir nesneyi tanımlayan `const Key`. Dizi çağrılan demetlerin sıralı bir dizi kümesini bölümleyen bir karma işlev tarafından zayıf bir şekilde sıralanır. Her bir demette herhangi bir öğe çiftinin eşdeğer sıralamaya sahip olup olmadığını belirleyen bir karşılaştırma işlevi vardır. Her bir öğe hem bir sıralama anahtarı hem de bir değer depolar. Dizi, en azından tüm demetleri kabaca eşit uzunlukta olduğunda, dizideki (sabit zaman) öğe sayısından bağımsız olabilen işlem sayısına sahip rastgele bir öğenin aranması, eklenmesi ve kaldırılmasına izin verecek şekilde temsil edilir. En kötü durumda, tüm öğeler tek bir demet içinde olduğunda işlem sayısı dizideki (doğrusal zaman) öğelerin sayısıyla orantılıdır. Ayrıca, bir öğe eklenmesi hiçbir yineleyiciyi geçersiz kılmaz; bir öğenin kaldırılması yalnızca bu kaldırılan öğeyi gösteren yineleyicileri geçersiz kılar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template <class Key,  
    class Hash = std::hash<Key>,  
    class Pred = std::equal_to<Key>,  
    class Alloc = std::allocator<Key>>  
class unordered_multiset;  
```  
  
#### <a name="parameters"></a>Parametreler  
  
|||  
|-|-|  
|Parametre|Açıklama|  
|`Key`|Anahtar türü.|  
|`Hash`|Karma işlev nesne türü.|  
|`Pred`|Eşitlik karşılaştırma işlevi nesne türü.|  
|`Alloc`|Ayırıcı sınıf.|  
  
## <a name="members"></a>Üyeler  
  
|||  
|-|-|  
|Tür Tanımlaması|Açıklama|  
|[allocator_type](#allocator_type)|Depolamayı yönetmek için bir ayırıcı türü.|  
|[const_iterator](#const_iterator)|Denetlenen dizi için bir sabit yineleyici türü.|  
|[const_local_iterator](#const_local_iterator)|Denetlenen dizi için bir sabit demet yineleyici türü.|  
|[const_pointer](#const_pointer)|Bir öğe için sabit bir işaretçi türü.|  
|[const_reference](#const_reference)|Bir öğe için sabit bir başvuru türü.|  
|[difference_type](#difference_type)|İki öğe arasındaki işaretli mesafenin türü.|  
|[hasher](#hasher)|Karma işlevin türü.|  
|[Yineleyici](#iterator)|Denetlenen dizi için bir yineleyici türü.|  
|[key_equal](#key_equal)|Karşılaştırma işlevinin türü.|  
|[key_type](#key_type)|Bir sıralama anahtarının türü.|  
|[local_iterator](#local_iterator)|Denetlenen dizi için bir demet yineleyici türü.|  
|[İşaretçi](#pointer)|Bir öğe için bir işaretçi türü.|  
|[başvuru](#reference)|Bir öğe için bir başvuru türü.|  
|[size_type](#size_type)|İki öğe arasındaki işaretsiz bir mesafenin türü.|  
|[value_type](#value_type)|Öğenin türü.|  
  
|||  
|-|-|  
|Üye İşlevi|Açıklama|  
|[başlayın](#begin)|Denetlenen dizinin başlangıcını belirtir.|  
|[Demet](#bucket)|Bir anahtar değeri için demet numarasını alır.|  
|[bucket_count](#bucket_count)|Demet sayısını alır.|  
|[bucket_size](#bucket_size)|Demet boyutunu alır.|  
|[cbegin](#cbegin)|Denetlenen dizinin başlangıcını belirtir.|  
|[cend](#cend)|Denetlenen dizinin bitişini belirtir.|  
|[Temizle](#clear)|Tüm öğeleri kaldırır.|  
|[sayısı](#count)|Belirtilen bir anahtar ile eşleşen öğe sayısını bulur.|  
|[emplace](#emplace)|Yerinde oluşturulmuş bir öğe ekler.|  
|[emplace_hint](#emplace_hint)|Göstergeyle birlikte, yerinde oluşturulmuş bir öğe ekler.|  
|[boş](#empty)|Bir öğe olup olmadığını sınar.|  
|[Bitiş](#end)|Denetlenen dizinin bitişini belirtir.|  
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
|[boyutu](#size)|Öğe sayısını sayar.|  
|[değiştirme](#swap)|İki kapsayıcının içeriğinin yerini değiştirir.|  
|[unordered_multiset](#unordered_multiset)|Bir kapsayıcı nesnesi oluşturur.|  
  
|||  
|-|-|  
|İşleç|Açıklama|  
|[unordered_multiset::operator =](#op_eq)|Bir karma tabloya kopyalar.|  
  
## <a name="remarks"></a>Açıklamalar  
 Nesne denetlediği iki depolanan nesneler, bir karşılaştırma işlevi nesne türü çağırarak dizisi siparişleri [unordered_multiset::key_equal](#key_equal) ve karma işlevini nesne türü [unordered_multiset::hasher](#hasher). Üye işlevini çağırarak ilk saklı nesneye erişim [unordered_multiset::key_eq](#key_eq)`()`; ve üye işlevini çağırarak ikinci saklı nesneye erişim [unordered_multiset::hash_ işlev](#hash)`()`. Özellikle, tüm değerler için `X` ve `Y` türü `Key`, çağrı `key_eq()(X, Y)` yalnızca iki bağımsız değişken değerleri eşdeğer sıralama varsa true değerini döndürür; çağrı `hash_function()(keyval)` bir dağıtım türü değerlerinverir`size_t`. Şablon sınıfı aksine [unordered_set sınıfı](../standard-library/unordered-set-class.md), şablon sınıfın bir nesnesi `unordered_multiset` emin olun değil `key_eq()(X, Y)` her zaman denetimli dizisi için herhangi iki öğeleri false olur. (Anahtarlarının benzersiz olması gerekmez.)  
  
 Nesne ayrıca, demet başına istenen ortalama öğe sayısını belirten en yüksek yük faktörünü depolar. Bir öğe ekleme neden olursa [unordered_multiset::load_factor](#load_factor) `()` en fazla Yük faktörü aşmayı kapsayıcı sayısını artırır ve karma tablosu gerektiği gibi yeniden oluşturur.  
  
 Denetlenen dizideki öğelerin gerçek sırası karma işleve, karşılaştırma işlevine, ekleme sırasına, en yüksek yük faktörüne ve geçerli demet sayısına bağlıdır. Denetlenen dizideki öğelerin sırasını genelde tahmin edemezsiniz. Ancak, eşdeğer sıralamaya sahip öğelerin herhangi bir alt kümesinin her zaman denetlenen dizide bitişik olduğundan emin olabilirsiniz.  
  
 Nesne ayırır ve saklı ayırıcısı nesne türü denetlediği dizisi için depolama boşaltır [unordered_multiset::allocator_type](#allocator_type). Böyle bir ayırıcı nesne şablonu sınıfın bir nesnesi olarak aynı dış arabirimi olmalıdır `allocator`. Depolanan ayırıcı nesnenin kapsayıcı nesne atandığında kopyalanmayacağını unutmayın.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<unordered_set >  
  
 **Namespace:** std  
  
##  <a name="allocator_type"></a>unordered_multiset::allocator_type  
 Depolamayı yönetmek için bir ayırıcı türü.  
  
```  
typedef Alloc allocator_type;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Şablon parametresi için bir eş anlamlı türüdür `Alloc`.  
  
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
  
##  <a name="begin"></a>unordered_multiset::Begin  
 Denetimli dizisi veya bir demet başlangıcını belirtir.  
  
```  
iterator begin();

const_iterator begin() const;

 
local_iterator begin(size_type nbucket);

const_local_iterator begin(size_type nbucket) const;
```  
  
### <a name="parameters"></a>Parametreler  
  
|||  
|-|-|  
|Parametre|Açıklama|  
|`nbucket`|Demet sayısı.|  
  
### <a name="remarks"></a>Açıklamalar  
 İlk iki üye işlevleri iletme yineleyici bu noktalarda ilk öğe dizisi (veya yalnızca boş bir dizi ötesinde) döndürür. Son iki üye işlevleri iletme yineleyici demet ilk öğesi bu noktalarda dönmek `nbucket` (veya yalnızca boş bir demet ötesinde).  
  
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
  
// display contents " [c] [b] [a]"   
    for (Myset::const_iterator it = c1.begin();   
        it != c1.end(); ++it)   
        std::cout << " [" << *it << "]";   
    std::cout << std::endl;   
  
// inspect first two items " [c] [b]"   
    Myset::iterator it2 = c1.begin();   
    std::cout << " [" << *it2 << "]";   
    ++it2;   
    std::cout << " [" << *it2 << "]";   
    std::cout << std::endl;   
  
// inspect bucket containing 'a'   
    Myset::const_local_iterator lit = c1.begin(c1.bucket('a'));   
    std::cout << " [" << *lit << "]";   
  
    return (0);   
    }  
  
```  
  
```Output  
[c] [b] [a]  
[c] [b]  
[a]  
```  
  
##  <a name="bucket"></a>unordered_multiset::Bucket  
 Bir anahtar değeri için demet numarasını alır.  
  
```  
size_type bucket(const Key& keyval) const;
```  
  
### <a name="parameters"></a>Parametreler  
 keyval  
 Eşlemek için anahtar değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 Şu anda anahtar değerine karşılık gelen demet sayısı üye işlevinin döndürdüğü `keyval`.  
  
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
  
// display contents " [c] [b] [a]"   
    for (Myset::const_iterator it = c1.begin();   
        it != c1.end(); ++it)   
        std::cout << " [" << *it << "]";   
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
  
##  <a name="bucket_count"></a>unordered_multiset::bucket_count  
 Demet sayısını alır.  
  
```  
size_type bucket_count() const;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevi geçerli sayısını döndürür.  
  
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
  
// display contents " [c] [b] [a]"   
    for (Myset::const_iterator it = c1.begin();   
        it != c1.end(); ++it)   
        std::cout << " [" << *it << "]";   
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
  
##  <a name="bucket_size"></a>unordered_multiset::bucket_size  
 Bir demet boyutunu alır  
  
```  
size_type bucket_size(size_type nbucket) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `nbucket`  
 Demet sayısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevleri demet sayısı boyutu döndüren `nbucket`.  
  
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
  
// display contents " [c] [b] [a]"   
    for (Myset::const_iterator it = c1.begin();   
        it != c1.end(); ++it)   
        std::cout << " [" << *it << "]";   
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
  
##  <a name="cbegin"></a>unordered_multiset::cbegin  
 Döndürür bir `const` aralığın ilk öğe adresleri yineleyici.  
  
```  
const_iterator cbegin() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 A `const` ilk öğede aralığı ya da yalnızca boş bir aralığın ötesinde konumunu işaret İleri erişim yineleyici (boş bir aralığın için `cbegin() == cend()`).  
  
### <a name="remarks"></a>Açıklamalar  
 Dönüş değeri ile `cbegin`, öğeleri aralığında değiştirilemez.  
  
 Bu üye işlevi yerine kullanabileceğiniz `begin()` üye işlevi dönüş değeri garanti `const_iterator`. Genellikle, ile birlikte kullanılır [otomatik](../cpp/auto-cpp.md) kesintisi anahtar sözcüğü, aşağıdaki örnekte gösterildiği gibi yazın. Örnekte, göz önünde bulundurun `Container` bir değiştirilebilir için (olmayan `const`) destekleyen herhangi bir türde kapsayıcı `begin()` ve `cbegin()`.  
  
```cpp  
auto i1 = Container.begin();
// i1 is Container<T>::iterator   
auto i2 = Container.cbegin();

// i2 is Container<T>::const_iterator  
```  
  
##  <a name="cend"></a>unordered_multiset::cend  
 Döndürür bir `const` konumun yalnızca bir aralıkta son öğenin ötesinde adresleri yineleyici.  
  
```  
const_iterator cend() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 A `const` yalnızca aralığın sonunu aşan işaret İleri erişim yineleyici.  
  
### <a name="remarks"></a>Açıklamalar  
 `cend`Yineleyici kendi aralığının sonunu geçti olup olmadığını test etmek için kullanılır.  
  
 Bu üye işlevi yerine kullanabileceğiniz `end()` üye işlevi dönüş değeri garanti `const_iterator`. Genellikle, ile birlikte kullanılır [otomatik](../cpp/auto-cpp.md) kesintisi anahtar sözcüğü, aşağıdaki örnekte gösterildiği gibi yazın. Örnekte, göz önünde bulundurun `Container` bir değiştirilebilir için (olmayan `const`) destekleyen herhangi bir türde kapsayıcı `end()` ve `cend()`.  
  
```cpp  
auto i1 = Container.end();
// i1 is Container<T>::iterator   
auto i2 = Container.cend();

// i2 is Container<T>::const_iterator  
```  
  
 Tarafından döndürülen değer `cend` değil başvuru yapıldı.  
  
##  <a name="clear"></a>unordered_multiset::Clear  
 Tüm öğeleri kaldırır.  
  
```  
void clear();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlev çağrılarını [unordered_multiset::erase](#erase) `(` [unordered_multiset::begin](#begin) `(),` [unordered_multiset::end](#end) `())`.  
  
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
  
// display contents " [c] [b] [a]"   
    for (Myset::const_iterator it = c1.begin();   
        it != c1.end(); ++it)   
        std::cout << " [" << *it << "]";   
    std::cout << std::endl;   
  
// clear the container and reinspect   
    c1.clear();   
    std::cout << "size == " << c1.size() << std::endl;   
    std::cout << "empty() == " << std::boolalpha << c1.empty() << std::endl;   
    std::cout << std::endl;   
  
    c1.insert('d');   
    c1.insert('e');   
  
// display contents " [e] [d]"   
    for (Myset::const_iterator it = c1.begin();   
        it != c1.end(); ++it)   
        std::cout << " [" << *it << "]";   
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
  
##  <a name="const_iterator"></a>unordered_multiset::const_iterator  
 Denetlenen dizi için bir sabit yineleyici türü.  
  
```  
typedef T1 const_iterator;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Denetimli sırası için sabit bir iletme yineleyici olarak hizmet verebilir bir nesne türünü tanımlar. Bunu açıklanan burada uygulama tanımlı türü eşanlamlısı olarak `T1`.  
  
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
  
// display contents " [c] [b] [a]"   
    for (Myset::const_iterator it = c1.begin();   
        it != c1.end(); ++it)   
        std::cout << " [" << *it << "]";   
    std::cout << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
[c] [b] [a]  
```  
  
##  <a name="const_local_iterator"></a>unordered_multiset::const_local_iterator  
 Denetlenen dizi için bir sabit demet yineleyici türü.  
  
```  
typedef T5 const_local_iterator;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bir kabı için sabit bir iletme yineleyici olarak hizmet verebilir bir nesne türünü tanımlar. Bunu açıklanan burada uygulama tanımlı türü eşanlamlısı olarak `T5`.  
  
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
  
// display contents " [c] [b] [a]"   
    for (Myset::const_iterator it = c1.begin();   
        it != c1.end(); ++it)   
        std::cout << " [" << *it << "]";   
    std::cout << std::endl;   
  
// inspect bucket containing 'a'   
    Myset::const_local_iterator lit = c1.begin(c1.bucket('a'));   
    std::cout << " [" << *lit << "]";   
  
    return (0);   
    }  
  
```  
  
```Output  
[c] [b] [a]  
[a]  
```  
  
##  <a name="const_pointer"></a>unordered_multiset::const_pointer  
 Bir öğe için sabit bir işaretçi türü.  
  
```  
typedef Alloc::const_pointer const_pointer;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Denetimli dizi bir öğe için sabit bir işaretçi olarak hizmet verebilir bir nesne türünü tanımlar.  
  
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
  
// display contents " [c] [b] [a]"   
    for (Myset::iterator it = c1.begin();   
        it != c1.end(); ++it)   
        {   
        Myset::const_pointer p = &*it;   
        std::cout << " [" << *p << "]";   
        }   
    std::cout << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
[c] [b] [a]  
```  
  
##  <a name="const_reference"></a>unordered_multiset::const_reference  
 Bir öğe için sabit bir başvuru türü.  
  
```  
typedef Alloc::const_reference const_reference;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Öğenin denetimli dizisi sabit bir başvuru olarak hizmet verebilir bir nesne türünü tanımlar.  
  
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
  
// display contents " [c] [b] [a]"   
    for (Myset::iterator it = c1.begin();   
        it != c1.end(); ++it)   
        {   
        Myset::const_reference ref = *it;   
        std::cout << " [" << ref << "]";   
        }   
    std::cout << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
[c] [b] [a]  
```  
  
##  <a name="count"></a>unordered_multiset::Count  
 Belirtilen bir anahtar ile eşleşen öğe sayısını bulur.  
  
```  
size_type count(const Key& keyval) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `keyval`  
 Aranacak anahtar değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 Üye fonksiyonu tarafından ayrılmış aralıktaki öğe sayısını döndürür [unordered_multiset::equal_range](#equal_range)`(keyval)`.  
  
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
  
// display contents " [c] [b] [a]"   
    for (Myset::const_iterator it = c1.begin();   
        it != c1.end(); ++it)   
        std::cout << " [" << *it << "]";   
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
  
##  <a name="difference_type"></a>unordered_multiset::difference_type  
 İki öğe arasındaki işaretli mesafenin türü.  
  
```  
typedef T3 difference_type;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 İmzalı tamsayı türünü herhangi iki öğe denetlenen sıradaki adreslerini arasındaki farkı temsil eden bir nesne tanımlar. Bunu açıklanan burada uygulama tanımlı türü eşanlamlısı olarak `T3`.  
  
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
  
// display contents " [c] [b] [a]"   
    for (Myset::const_iterator it = c1.begin();   
        it != c1.end(); ++it)   
        std::cout << " [" << *it << "]";   
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
  
##  <a name="emplace"></a>unordered_multiset::emplace  
 (Hiçbir kopyalama veya taşıma işlemler gerçekleştirilir) yerinde oluşturulan bir öğe ekler.  
  
```  
template <class... Args>  
iterator emplace(Args&&... args);
```  
  
### <a name="parameters"></a>Parametreler  
  
|||  
|-|-|  
|Parametre|Açıklama|  
|`args`|Unordered_multiset eklenecek bir öğe oluşturmak için iletilen bağımsız değişkenler.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yineleyici yeni eklenen öğesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Kapsayıcı öğeleri için başvuru bu işlev tarafından geçersiz kılınır, ancak tüm yineleyiciler kapsayıcısı için geçersiz kılabilir.  
  
 Bir özel durum oluşturulur ancak kapsayıcının karma işlevi gerçekleşmez kapsayıcı ekleme sırasında değiştirilmez. Karma işlev özel durum, tanımlanmamış bir sonucudur.  
  
 Kod örneği için bkz: [multiset::emplace](../standard-library/multiset-class.md#emplace).  
  
##  <a name="emplace_hint"></a>unordered_multiset::emplace_hint  
 Yerinde (hiçbir kopyalama veya taşıma işlemler gerçekleştirilir), yerleştirme İpucu ile oluşturulan bir öğe ekler.  
  
```  
template <class... Args>  
iterator emplace_hint(
    const_iterator where,  
    Args&&... args);
```  
  
### <a name="parameters"></a>Parametreler  
  
|||  
|-|-|  
|Parametre|Açıklama|  
|`args`|Unordered_multiset eklenecek bir öğe oluşturmak için iletilen bağımsız değişkenler.|  
|`where`|Ekleme için doğru noktası aramaya başlamak için yer ile ilgili bir ipucu.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yineleyici yeni eklenen öğesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Kapsayıcı öğeleri için başvuru bu işlev tarafından geçersiz kılınır, ancak tüm yineleyiciler kapsayıcısı için geçersiz kılabilir.  
  
 Bir özel durum oluşturulur ancak kapsayıcının karma işlevi gerçekleşmez kapsayıcı ekleme sırasında değiştirilmez. Karma işlev özel durum, tanımlanmamış bir sonucudur.  
  
 Kod örneği için bkz: [set::emplace_hint](../standard-library/set-class.md#emplace_hint).  
  
##  <a name="empty"></a>unordered_multiset::empty  
 Bir öğe olup olmadığını sınar.  
  
```  
bool empty() const;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevi boş denetimli dizisi için true değerini döndürür.  
  
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
  
// display contents " [c] [b] [a]"   
    for (Myset::const_iterator it = c1.begin();   
        it != c1.end(); ++it)   
        std::cout << " [" << *it << "]";   
    std::cout << std::endl;   
  
// clear the container and reinspect   
    c1.clear();   
    std::cout << "size == " << c1.size() << std::endl;   
    std::cout << "empty() == " << std::boolalpha << c1.empty() << std::endl;   
    std::cout << std::endl;   
  
    c1.insert('d');   
    c1.insert('e');   
  
// display contents " [e] [d]"   
    for (Myset::const_iterator it = c1.begin();   
        it != c1.end(); ++it)   
        std::cout << " [" << *it << "]";   
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
  
##  <a name="end"></a>unordered_multiset::End  
 Denetlenen dizinin bitişini belirtir.  
  
```  
iterator end();
const_iterator end() const;

 
    local_iterator end(size_type nbucket);
const_local_iterator end(size_type nbucket) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `nbucket`  
 Demet sayısı.  
  
### <a name="remarks"></a>Açıklamalar  
 İlk iki üye işlevleri iletme yineleyici dizisi yalnızca ötesinde işaret döndür. Son iki üye işlevleri yalnızca demet ötesinde işaret iletme yineleyici dönmek `nbucket`.  
  
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
  
// display contents " [c] [b] [a]"   
    for (Myset::const_iterator it = c1.begin();   
        it != c1.end(); ++it)   
        std::cout << " [" << *it << "]";   
    std::cout << std::endl;   
  
// inspect last two items " [a] [b]"   
    Myset::iterator it2 = c1.end();   
    --it2;   
    std::cout << " [" << *it2 << "]";   
    --it2;   
    std::cout << " [" << *it2 << "]";   
    std::cout << std::endl;   
  
// inspect bucket containing 'a'   
    Myset::const_local_iterator lit = c1.end(c1.bucket('a'));   
    --lit;   
    std::cout << " [" << *lit << "]";   
  
    return (0);   
    }  
  
```  
  
```Output  
[c] [b] [a]  
[a] [b]  
[a]  
```  
  
##  <a name="equal_range"></a>unordered_multiset::equal_range  
 Belirtilen bir anahtarla eşleşen aralığı bulur.  
  
```  
std::pair<iterator, iterator>  
    equal_range(const Key& keyval);

std::pair<const_iterator, const_iterator>  
    equal_range(const Key& keyval) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `keyval`  
 Aranacak anahtar değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevini yineleyiciler çifti döndürür `X` şekilde `[X.first, X.second)` yalnızca bu öğeler ile eşdeğer sıralama sahip denetimli dizisi sınırlandırır `keyval`. Bu tür bir öğe varsa, her iki yineleyiciler olan `end()`.  
  
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
  
// display contents " [c] [b] [a]"   
    for (Myset::const_iterator it = c1.begin();   
        it != c1.end(); ++it)   
        std::cout << " [" << *it << "]";   
    std::cout << std::endl;   
  
// display results of failed search   
    std::pair<Myset::iterator, Myset::iterator> pair1 =   
        c1.equal_range('x');   
    std::cout << "equal_range('x'):";   
    for (; pair1.first != pair1.second; ++pair1.first)   
        std::cout << " [" << *pair1.first << "]";   
    std::cout << std::endl;   
  
// display results of successful search   
    pair1 = c1.equal_range('b');   
    std::cout << "equal_range('b'):";   
    for (; pair1.first != pair1.second; ++pair1.first)   
        std::cout << " [" << *pair1.first << "]";   
    std::cout << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
 [c] [b] [a]  
equal_range('x'):  
equal_range('b'): [b]  
```  
  
##  <a name="erase"></a>unordered_multiset::ERASE  
 Bir öğenin veya bir dizi öğeleri unordered_multiset belirtilen konumlardan kaldırır veya belirtilen anahtar eşleşen öğeleri kaldırır.  
  
```  
iterator erase(
    const_iterator Where);

iterator erase(
    const_iterator First,  
    const_iterator Last);

size_type erase(
    const key_type& Key);
```  
  
### <a name="parameters"></a>Parametreler  
 `Where`  
 Kaldırılacak öğe konumu.  
  
 `First`  
 Kaldırılacak ilk öğe konumu.  
  
 `Last`  
 Kaldırılacak yalnızca son öğenin ötesinde konumu.  
  
 `Key`  
 Kaldırılacak öğe anahtar değeri.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İlk iki üye işlevleri için çift yönlü Yineleyici, kaldırılan öğelerin ya da böyle bir öğe varsa unordered_multiset sonuna olan bir öğeyi dışında kalan ilk öğe belirler.  
  
 Üye işlevi için üçüncü unordered_multiset kaldırılmış olan öğe sayısını döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Kod örneği için bkz: [set::erase](../standard-library/set-class.md#erase).  
  
##  <a name="find"></a>unordered_multiset::Find  
 Belirtilen bir anahtarla eşleşen bir öğeyi bulur.  
  
```  
const_iterator find(const Key& keyval) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `keyval`  
 Aranacak anahtar değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevi döndürür [unordered_multiset::equal_range](#equal_range)`(keyval).first`.  
  
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
  
// display contents " [c] [b] [a]"   
    for (Myset::const_iterator it = c1.begin();   
        it != c1.end(); ++it)   
        std::cout << " [" << *it << "]";   
    std::cout << std::endl;   
  
// try to find and fail   
    std::cout << "find('A') == "   
        << std::boolalpha << (c1.find('A') != c1.end()) << std::endl;   
  
// try to find and succeed   
    Myset::iterator it = c1.find('b');   
    std::cout << "find('b') == "   
        << std::boolalpha << (it != c1.end())   
        << ": [" << *it << "]" << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
 [c] [b] [a]  
find('A') == false  
find('b') == true: [b]  
```  
  
##  <a name="get_allocator"></a>unordered_multiset::get_allocator  
 Depolanan ayırıcı nesnesini alır.  
  
```  
Alloc get_allocator() const;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevini saklı ayırıcısı nesnesini döndürür.  
  
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
  
##  <a name="hash"></a>unordered_multiset::hash_function  
 Depolanan karma işlevi nesnesini alır.  
  
```  
Hash hash_function() const;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevini depolanan karma işlev nesnesi döndürür.  
  
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
  
##  <a name="hasher"></a>unordered_multiset::hasher  
 Karma işlevin türü.  
  
```  
typedef Hash hasher;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Şablon parametresi için bir eş anlamlı türüdür `Hash`.  
  
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
  
##  <a name="insert"></a>unordered_multiset::insert  
 Bir öğenin veya öğe aralığı bir unordered_multiset ekler.  
  
```  
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
  
|||  
|-|-|  
|Parametre|Açıklama|  
|`Val`|Unordered_multiset Eklenecek öğenin değeri.|  
|`Where`|Ekleme için doğru noktası aramaya başlamak için koyun.|  
|`ValTy`|Unordered_multiset öğesi oluşturmak için kullanabileceğiniz bağımsız değişken türünü belirten bir şablon parametresi [value_type](../standard-library/map-class.md#value_type)ve mükemmel ileten `Val` bağımsız değişken olarak.|  
|`First`|Kopyalanacak ilk öğe konumu.|  
|`Last`|Kopyalanacak yalnızca son öğenin ötesinde konumu.|  
|`InputIterator`|Gereksinimlerini karşılayan şablon işlevi bağımsız değişken bir [giriş yineleyici](../standard-library/input-iterator-tag-struct.md) oluşturmak için kullanılan bir türü öğelerine işaret [value_type](../standard-library/map-class.md#value_type) nesneleri.|  
|`IList`|[İnitializer_list](../standard-library/initializer-list.md) öğeleri kopyalanacak.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 Tek öğe Ekle üye işlevleri (1) ve (2), yineleyici yeni öğe unordered_multiset burada eklenmiş konumuna döndürür.  
  
 İpucu ile tek öğe üye işlevleri (3) ve (4), yeni öğe unordered_multiset eklenir burada konumuna işaret eden bir yineleyici döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 İşaretçileri veya başvuruları olmadığından bu işlev tarafından geçersiz kılınır, ancak tüm yineleyiciler kapsayıcısı için geçersiz kılabilir.  
  
 Bir özel durum oluşturulur ancak kapsayıcının karma işlevi gerçekleşmez yalnızca bir öğe ekleme sırasında kapsayıcının durumu değiştirilemez. Karma işlev özel durum, tanımlanmamış bir sonucudur. Bir özel durum, birden çok öğe ekleme sırasında kapsayıcı belirtilmeyen ancak geçerli bir durumda bırakılır.  
  
 [Value_type](../standard-library/map-class.md#value_type) , bir kapsayıcı ve, küme ait bir typedef kapsayıcısıdır `unordered_multiset<V>::value_type` türü `const V`.  
  
 Aralık üye işlevi (5) aralığında bir yineleyici tarafından ele her öğesine karşılık gelen bir unordered_multiset bir dizi öğesi değerlerini ekler `[First, Last)`; bu nedenle, `Last` takılı. Kapsayıcı üye fonksiyonu `end()` kapsayıcı son öğesi hemen sonra konuma başvuruyor — Örneğin, deyim `m.insert(v.begin(), v.end());` tüm öğeleri ekler `v` içine `m`.  
  
 Başlatıcı listesi üye işlevi (6) kullanan bir [initializer_list](../standard-library/initializer-list.md) öğeleri unordered_multiset kopyalamak için.  
  
 Yerinde oluşturulan bir öğe eklemeye — diğer bir deyişle, kopyalama veya taşıma işlemi yok gerçekleştirilen — bkz [unordered_multiset::emplace](#emplace) ve [unordered_multiset::emplace_hint](#emplace_hint).  
  
 Kod örneği için bkz: [multiset::insert](../standard-library/multiset-class.md#insert).  
  
##  <a name="iterator"></a>unordered_multiset::iterator  
 Bir sabit sağlayan bir türü [iletme yineleyici](../standard-library/forward-iterator-tag-struct.md) bir unordered_multiset öğelerinde okuyabilir.  
  
```  
typedef implementation-defined iterator;  
```  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [başlamak](../standard-library/multiset-class.md#begin) bildirme ve kullanma konusunda bir örnek için bir **yineleyici**.  
  
##  <a name="key_eq"></a>unordered_multiset::key_eq  
 Depolanan karşılaştırma işlevi nesnesini alır.  
  
```  
Pred key_eq() const;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevini saklı karşılaştırma işlev nesnesi döndürür.  
  
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
  
##  <a name="key_equal"></a>unordered_multiset::key_equal  
 Karşılaştırma işlevinin türü.  
  
```  
typedef Pred key_equal;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Şablon parametresi için bir eş anlamlı türüdür `Pred`.  
  
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
  
##  <a name="key_type"></a>unordered_multiset::key_type  
 Bir sıralama anahtarının türü.  
  
```  
typedef Key key_type;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Şablon parametresi için bir eş anlamlı türüdür `Key`.  
  
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
  
// display contents " [c] [b] [a]"   
    for (Myset::const_iterator it = c1.begin();   
        it != c1.end(); ++it)   
        std::cout << " [" << *it << "]";   
    std::cout << std::endl;   
  
// add a value and reinspect   
    Myset::key_type key = 'd';   
    Myset::value_type val = key;   
    c1.insert(val);   
  
    for (Myset::const_iterator it = c1.begin();   
        it != c1.end(); ++it)   
        std::cout << " [" << *it << "]";   
    std::cout << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
[c] [b] [a]  
[d] [c] [b] [a]  
```  
  
##  <a name="load_factor"></a>unordered_multiset::load_factor  
 Demet başına ortalama öğeyi sayar.  
  
```  
float load_factor() const;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevi döndürür `(float)` [unordered_multiset::size](#size)`() / (float)`[unordered_multiset::bucket_count](#bucket_count)`()`, sepet başına ortalama sayısı.  
  
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
  
// display contents " [c] [b] [a]"   
    for (Myset::const_iterator it = c1.begin();   
        it != c1.end(); ++it)   
        std::cout << " [" << *it << "]";   
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
  
##  <a name="local_iterator"></a>unordered_multiset::local_iterator  
 Bir demet yineleyici türü.  
  
```  
typedef T4 local_iterator;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Tür iletme yineleyici bir sepet olarak hizmet verebilir nesneyi açıklar. Bunu açıklanan burada uygulama tanımlı türü eşanlamlısı olarak `T4`.  
  
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
  
// display contents " [c] [b] [a]"   
    for (Myset::const_iterator it = c1.begin();   
        it != c1.end(); ++it)   
        std::cout << " [" << *it << "]";   
    std::cout << std::endl;   
  
// inspect bucket containing 'a'   
    Myset::local_iterator lit = c1.begin(c1.bucket('a'));   
    std::cout << " [" << *lit << "]";   
  
    return (0);   
    }  
  
```  
  
```Output  
[c] [b] [a]  
[a]  
```  
  
##  <a name="max_bucket_count"></a>unordered_multiset::max_bucket_count  
 En yüksek demet sayısını alır.  
  
```  
size_type max_bucket_count() const;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevini demet şu anda izin verilen maksimum sayısını döndürür.  
  
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
  
// display contents " [c] [b] [a]"   
    for (Myset::const_iterator it = c1.begin();   
        it != c1.end(); ++it)   
        std::cout << " [" << *it << "]";   
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
  
##  <a name="max_load_factor"></a>unordered_multiset::max_load_factor  
 Demet başına en yüksek öğe sayısını alır veya ayarlar.  
  
```  
float max_load_factor() const;

 
void max_load_factor(float factor);
```  
  
### <a name="parameters"></a>Parametreler  
 `factor`  
 Yeni en fazla Yük faktörü.  
  
### <a name="remarks"></a>Açıklamalar  
 İlk üye işlevi depolanan en fazla Yük faktörü döndürür. İkinci üye işlevi depolanan en fazla yük faktörüyle değiştirir `factor`.  
  
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
  
// display contents " [c] [b] [a]"   
    for (Myset::const_iterator it = c1.begin();   
        it != c1.end(); ++it)   
        std::cout << " [" << *it << "]";   
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
  
##  <a name="max_size"></a>unordered_multiset::max_size  
 Denetlenen dizinin en büyük boyutunu alır.  
  
```  
size_type max_size() const;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevini nesne denetleyebilirsiniz uzun sırası uzunluğunu döndürür.  
  
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
  
##  <a name="op_eq"></a>unordered_multiset::operator =  
 Bir karma tabloya kopyalar.  
  
```  
unordered_multiset& operator=(const unordered_multiset& right);

unordered_multiset& operator=(unordered_multiset&& right);
```  
  
### <a name="parameters"></a>Parametreler  
  
|||  
|-|-|  
|Parametre|Açıklama|  
|`right`|[Unordered_multiset](../standard-library/unordered-multiset-class.md) içine kopyalanmasını `unordered_multiset`.|  
  
### <a name="remarks"></a>Açıklamalar  
 Var olan öğeleri silindikten sonra bir `unordered_multiset`, `operator=` kopyalar ya da içeriğini taşır `right` içine `unordered_multiset`.  
  
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
  
##  <a name="pointer"></a>unordered_multiset::pointer  
 Bir öğe için bir işaretçi türü.  
  
```  
typedef Alloc::pointer pointer;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Denetimli dizi bir öğe için bir işaretçi olarak hizmet verebilir bir nesne türünü tanımlar.  
  
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
  
// display contents " [c] [b] [a]"   
    for (Myset::iterator it = c1.begin();   
        it != c1.end(); ++it)   
        {   
        Myset::key_type key = *it;   
        Myset::pointer p = &key;   
        std::cout << " [" << *p << "]";   
        }   
    std::cout << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
[c] [b] [a]  
```  
  
##  <a name="reference"></a>unordered_multiset::Reference  
 Bir öğe için bir başvuru türü.  
  
```  
typedef Alloc::reference reference;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Öğenin denetimli sırasının bir başvuru olarak hizmet verebilir bir nesne türünü tanımlar.  
  
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
  
// display contents " [c] [b] [a]"   
    for (Myset::iterator it = c1.begin();   
        it != c1.end(); ++it)   
        {   
        Myset::key_type key = *it;   
        Myset::reference ref = key;   
        std::cout << " [" << ref << "]";   
        }   
    std::cout << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
[c] [b] [a]  
```  
  
##  <a name="rehash"></a>unordered_multiset::rehash  
 Karma tabloyu yeniden oluşturur.  
  
```  
void rehash(size_type nbuckets);
```  
  
### <a name="parameters"></a>Parametreler  
 `nbuckets`  
 İstenen sayıda demete.  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevini sayısı en az olacak şekilde değiştirir `nbuckets` ve karma tablosu gerektiği gibi yeniden oluşturur.  
  
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
  
// display contents " [c] [b] [a]"   
    for (Myset::const_iterator it = c1.begin();   
        it != c1.end(); ++it)   
        std::cout << " [" << *it << "]";   
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
  
##  <a name="size"></a>unordered_multiset::size  
 Öğe sayısını sayar.  
  
```  
size_type size() const;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevini denetimli sırası uzunluğunu döndürür.  
  
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
  
// display contents " [c] [b] [a]"   
    for (Myset::const_iterator it = c1.begin();   
        it != c1.end(); ++it)   
        std::cout << " [" << *it << "]";   
    std::cout << std::endl;   
  
// clear the container and reinspect   
    c1.clear();   
    std::cout << "size == " << c1.size() << std::endl;   
    std::cout << "empty() == " << std::boolalpha << c1.empty() << std::endl;   
    std::cout << std::endl;   
  
    c1.insert('d');   
    c1.insert('e');   
  
// display contents " [e] [d]"   
    for (Myset::const_iterator it = c1.begin();   
        it != c1.end(); ++it)   
        std::cout << " [" << *it << "]";   
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
  
##  <a name="size_type"></a>unordered_multiset::size_type  
 İki öğe arasındaki işaretsiz bir mesafenin türü.  
  
```  
typedef T2 size_type;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 İşaretsiz tamsayı türünü herhangi denetimli sırası uzunluğu temsil eden bir nesne tanımlar. Bunu açıklanan burada uygulama tanımlı türü eşanlamlısı olarak `T2`.  
  
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
  
##  <a name="swap"></a>unordered_multiset::Swap  
 İki kapsayıcının içeriğinin yerini değiştirir.  
  
```  
void swap(unordered_multiset& right);
```  
  
### <a name="parameters"></a>Parametreler  
 `right`  
 İle değiştirme kapsayıcı.  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevini denetimli sıraları arasında değiştirir `*this` ve `right`. Varsa [unordered_multiset::get_allocator](#get_allocator)`() == right.get_allocator()`, bunu sabit sürede yapar, depolanan nitelikler nesne türünün kopyalama sonucunda yalnızca bir özel durum oluşturur `Tr`, ve işaretçileri, hiçbir başvuru geçersiz kılar veya iki denetimli sıraları öğelerinde atamak yineleyiciler. Aksi durumda, iki denetimli sıralarında öğesi atamaları ve oluşturucu çağrıları öğe sayısını orantılı çeşitli gerçekleştirir.  
  
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
  
// display contents " [c] [b] [a]"   
    for (Myset::const_iterator it = c1.begin();   
        it != c1.end(); ++it)   
        std::cout << " [" << *it << "]";   
    std::cout << std::endl;   
  
    Myset c2;   
  
    c2.insert('d');   
    c2.insert('e');   
    c2.insert('f');   
  
    c1.swap(c2);   
  
// display contents " [f] [e] [d]"   
    for (Myset::const_iterator it = c1.begin();   
        it != c1.end(); ++it)   
        std::cout << " [" << *it << "]";   
    std::cout << std::endl;   
  
    swap(c1, c2);   
  
// display contents " [c] [b] [a]"   
    for (Myset::const_iterator it = c1.begin();   
        it != c1.end(); ++it)   
        std::cout << " [" << *it << "]";   
    std::cout << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
[c] [b] [a]  
[f] [e] [d]  
[c] [b] [a]  
```  
  
##  <a name="unordered_multiset"></a>unordered_multiset::unordered_multiset  
 Bir kapsayıcı nesnesi oluşturur.  
  
```  
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
  
|||  
|-|-|  
|Parametre|Açıklama|  
|`InputIterator`|Yineleyici türü.|  
|`Al`|Depolanacak ayırıcı nesne.|  
|`Comp`|Depolanacak karşılaştırma işlevi nesnesi.|  
|`Hash`|Depolanacak karma işlev nesnesi.|  
|`Bucket_count`|En düşük demet sayısı.|  
|`Right`|Kopyalanacak kapsayıcı.|  
|`IList`|İnitializer_list kopyalanacak.|  
  
### <a name="remarks"></a>Açıklamalar  
 İlk oluşturucusu tarafından denetlenen sırasının bir kopyasını belirtir `Right`. İkinci oluşturucu boş bir denetlenmiş dizi belirtir. Bir dizi öğesi değerlerini üçüncü Oluşturucusu ekler `[First, Last)`. Dördüncü Oluşturucusu taşıyarak sırasının bir kopyasını belirtir `Right`.  
  
 Ayrıca, tüm oluşturucular çeşitli depolanmış değerleri başlatır. Kopya Oluşturucu için değerleri alanından elde edilen `Right`. Aksi durumda:.  
  
 Bağımsız değişken demet sayısı alt sınırı: `Bucket_count`, yoksa açıklanan varsayılan bir değer olup olmadığını burada uygulama tanımlı bir değer olarak `N0`.  
  
 Bağımsız değişken karma işlev nesnesidir `Hash`, yoksa bu olup olmadığını `Hash()`.  
  
 Karşılaştırma işlevi bağımsız değişken nesnesidir `Comp`, yoksa bu olup olmadığını `Comp()`.  
  
 Bağımsız değişken ayırıcısı nesnesidir `Al`, mevcut; Aksi takdirde bu olup olmadığını `Alloc()`.  
  
##  <a name="value_type"></a>unordered_multiset::value_type  
 Öğenin türü.  
  
```  
typedef Key value_type;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Öğenin denetimli dizisinin türünü tanımlar.  
  
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
  
// display contents " [c] [b] [a]"   
    for (Myset::const_iterator it = c1.begin();   
        it != c1.end(); ++it)   
        std::cout << " [" << *it << "]";   
    std::cout << std::endl;   
  
// add a value and reinspect   
    Myset::key_type key = 'd';   
    Myset::value_type val = key;   
    c1.insert(val);   
  
    for (Myset::const_iterator it = c1.begin();   
        it != c1.end(); ++it)   
        std::cout << " [" << *it << "]";   
    std::cout << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
[c] [b] [a]  
[d] [c] [b] [a]  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [< unordered_set >](../standard-library/unordered-set.md)   
 [Kapsayıcıları](../cpp/containers-modern-cpp.md)   
 [C++ Standart kitaplığında iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)

