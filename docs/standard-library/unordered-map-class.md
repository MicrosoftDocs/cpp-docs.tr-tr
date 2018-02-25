---
title: "unordered_map sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
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
dev_langs:
- C++
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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: db73f5d2d064d96696d3d6e320855bb9d939af47
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="unorderedmap-class"></a>unordered_map Sınıfı
Şablon sınıfı türündeki öğeler değişen uzunluk dizisi denetleyen bir nesneyi tanımlayan `std::pair<const Key, Ty>`. Dizi çağrılan demetlerin sıralı bir dizi kümesini bölümleyen bir karma işlev tarafından zayıf bir şekilde sıralanır. Her bir demette herhangi bir öğe çiftinin eşdeğer sıralamaya sahip olup olmadığını belirleyen bir karşılaştırma işlevi vardır. Her bir öğe iki nesne, bir sıralama anahtarı ve bir değer depolar. Dizi, en azından tüm demetleri kabaca eşit uzunlukta olduğunda, dizideki (sabit zaman) öğe sayısından bağımsız olabilen işlem sayısına sahip rastgele bir öğenin aranması, eklenmesi ve kaldırılmasına izin verecek şekilde temsil edilir. En kötü durumda, tüm öğeler tek bir demet içinde olduğunda işlem sayısı dizideki (doğrusal zaman) öğelerin sayısıyla orantılıdır. Ayrıca, bir öğe eklenmesi hiçbir yineleyiciyi geçersiz kılmaz; bir öğenin kaldırılması yalnızca bu kaldırılan öğeyi gösteren yineleyicileri geçersiz kılar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template <class Key,  
    class Ty,  
    class Hash = std::hash<Key>,  
    class Pred = std::equal_to<Key>,  
    class Alloc = std::allocator<std::pair<const Key, Ty>>>  
class unordered_map;  
```  
  
#### <a name="parameters"></a>Parametreler  
  
|||  
|-|-|  
|Parametre|Açıklama|  
|`Key`|Anahtar türü.|  
|`Ty`|Eşlenen tür.|  
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
|[iterator](#iterator)|Denetlenen dizi için bir yineleyici türü.|  
|[key_equal](#key_equal)|Karşılaştırma işlevinin türü.|  
|[key_type](#key_type)|Bir sıralama anahtarının türü.|  
|[local_iterator](#local_iterator)|Denetlenen dizi için bir demet yineleyici türü.|  
|[mapped_type](#mapped_type)|Her bir anahtar ile ilişkili bir eşlenen değer türü.|  
|[pointer](#pointer)|Bir öğe için bir işaretçi türü.|  
|[reference](#reference)|Bir öğe için bir başvuru türü.|  
|[size_type](#size_type)|İki öğe arasındaki işaretsiz bir mesafenin türü.|  
|[value_type](#value_type)|Öğenin türü.|  
  
|||  
|-|-|  
|Üye İşlevi|Açıklama|  
|[konumundaki](#at)|Belirtilen anahtarı içeren bir öğe bulur.|  
|[Başlangıç](#begin)|Denetlenen dizinin başlangıcını belirtir.|  
|[Demet](#bucket)|Bir anahtar değeri için demet numarasını alır.|  
|[bucket_count](#bucket_count)|Demet sayısını alır.|  
|[bucket_size](#bucket_size)|Demet boyutunu alır.|  
|[cbegin](#cbegin)|Denetlenen dizinin başlangıcını belirtir.|  
|[cend](#cend)|Denetlenen dizinin bitişini belirtir.|  
|[Temizle](#clear)|Tüm öğeleri kaldırır.|  
|[Sayısı](#count)|Belirtilen bir anahtar ile eşleşen öğe sayısını bulur.|  
|[emplace](#emplace)|Yerinde oluşturulmuş bir öğe ekler.|  
|[emplace_hint](#emplace_hint)|Göstergeyle birlikte, yerinde oluşturulmuş bir öğe ekler.|  
|[empty](#empty)|Bir öğe olup olmadığını sınar.|  
|[Bitiş](#end)|Denetlenen dizinin bitişini belirtir.|  
|[equal_range](#equal_range)|Belirtilen bir anahtarla eşleşen aralığı bulur.|  
|[silme](#erase)|Belirtilen konumlardaki öğeleri kaldırır.|  
|[find](#find)|Belirtilen bir anahtarla eşleşen bir öğeyi bulur.|  
|[get_allocator](#get_allocator)|Depolanan ayırıcı nesnesini alır.|  
|[hash_function](#hash)|Depolanan karma işlevi nesnesini alır.|  
|[insert](#insert)|Öğeleri ekler.|  
|[key_eq](#key_eq)|Depolanan karşılaştırma işlevi nesnesini alır.|  
|[load_factor](#load_factor)|Demet başına ortalama öğeyi sayar.|  
|[max_bucket_count](#max_bucket_count)|En yüksek demet sayısını alır.|  
|[max_load_factor](#max_load_factor)|Demet başına en yüksek öğe sayısını alır veya ayarlar.|  
|[max_size](#max_size)|Denetlenen dizinin en büyük boyutunu alır.|  
|[rehash](#rehash)|Karma tabloyu yeniden oluşturur.|  
|[Boyutu](#size)|Öğe sayısını sayar.|  
|[Değiştirme](#swap)|İki kapsayıcının içeriğinin yerini değiştirir.|  
|[unordered_map](#unordered_map)|Bir kapsayıcı nesnesi oluşturur.|  
  
|||  
|-|-|  
|İşleç|Açıklama|  
|[unordered_map::operator[]](#op_at)|Belirtilen anahtarı içeren bir öğe bulur veya ekler.|  
|[unordered_map::operator=](#op_eq)|Bir karma tabloya kopyalar.|  
  
## <a name="remarks"></a>Açıklamalar  
 Nesne denetlediği iki depolanan nesneler, bir karşılaştırma işlevi nesne türü çağırarak dizisi siparişleri [unordered_map::key_equal](#key_equal) ve karma işlevini nesne türü [unordered_map::hasher](#hasher). Üye işlevini çağırarak ilk saklı nesneye erişim [unordered_map::key_eq](#key_eq)`()`; ve üye işlevini çağırarak ikinci saklı nesneye erişim [unordered_map::hash_function](#hash) `()`. Özellikle, tüm değerler için `X` ve `Y` türü `Key`, çağrı `key_eq()(X, Y)` yalnızca iki bağımsız değişken değerleri eşdeğer sıralama varsa true değerini döndürür; çağrı `hash_function()(keyval)` bir dağıtım türü değerlerinverir`size_t`. Şablon sınıfı aksine [unordered_multimap sınıfı](../standard-library/unordered-multimap-class.md), şablon sınıfın bir nesnesi `unordered_map` sağlar `key_eq()(X, Y)` her zaman denetimli dizisi için herhangi iki öğeleri false olur. (Anahtarlar benzersizdir.)  
  
 Nesne ayrıca, demet başına istenen ortalama öğe sayısını belirten en yüksek yük faktörünü depolar. Bir öğe ekleme neden olursa [unordered_map::load_factor](#load_factor) `()` en fazla Yük faktörü aşmayı kapsayıcı sayısını artırır ve karma tablosu gerektiği gibi yeniden oluşturur.  
  
 Denetlenen dizideki öğelerin gerçek sırası karma işleve, karşılaştırma işlevine, ekleme sırasına, en yüksek yük faktörüne ve geçerli demet sayısına bağlıdır. Denetlenen dizideki öğelerin sırasını genelde tahmin edemezsiniz. Ancak, eşdeğer sıralamaya sahip öğelerin herhangi bir alt kümesinin her zaman denetlenen dizide bitişik olduğundan emin olabilirsiniz.  
  
 Nesne ayırır ve saklı ayırıcısı nesne türü denetlediği dizisi için depolama boşaltır [unordered_map::allocator_type](#allocator_type). Böyle bir ayırıcı nesne şablonu sınıfın bir nesnesi olarak aynı dış arabirimi olmalıdır `allocator`. Depolanan ayırıcı nesnenin kapsayıcı nesne atandığında kopyalanmayacağını unutmayın.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<unordered_map >  
  
 **Namespace:** std  
  
##  <a name="allocator_type"></a>  unordered_map::allocator_type  
 Depolamayı yönetmek için bir ayırıcı türü.  
  
```  
typedef Alloc allocator_type;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Şablon parametresi için bir eş anlamlı türüdür `Alloc`.  
  
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
  
##  <a name="at"></a>  unordered_map::AT  
 Unordered_map belirtilen anahtar değerine sahip bir öğe bulur.  
  
```  
Ty& at(const Key& key);
const Ty& at(const Key& key) const;
```  
  
### <a name="parameters"></a>Parametreler  
  
|||  
|-|-|  
|Parametre|Açıklama|  
|`key`|Bulunacak anahtar değeri.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 Öğe bulundu veri değerinin bir başvuru.  
  
### <a name="remarks"></a>Açıklamalar  
 Bağımsız değişken anahtar değeri bulunamadı sonra işlevi sınıfın bir nesnesi oluşturur `out_of_range`.  
  
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
  
##  <a name="begin"></a>  unordered_map::Begin  
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
  
##  <a name="bucket"></a>  unordered_map::Bucket  
 Bir anahtar değeri için demet numarasını alır.  
  
```  
size_type bucket(const Key& keyval) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `keyval`  
 Eşlemek için anahtar değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 Şu anda anahtar değerine karşılık gelen demet sayısı üye işlevinin döndürdüğü `keyval`.  
  
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
  
##  <a name="bucket_count"></a>  unordered_map::bucket_count  
 Demet sayısını alır.  
  
```  
size_type bucket_count() const;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevi geçerli sayısını döndürür.  
  
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
  
##  <a name="bucket_size"></a>  unordered_map::bucket_size  
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
  
##  <a name="cbegin"></a>  unordered_map::cbegin  
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
  
##  <a name="cend"></a>  unordered_map::cend  
 Döndürür bir `const` konumun yalnızca bir aralıkta son öğenin ötesinde adresleri yineleyici.  
  
```  
const_iterator cend() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 A `const` yalnızca aralığın sonunu aşan işaret İleri erişim yineleyici.  
  
### <a name="remarks"></a>Açıklamalar  
 `cend` Yineleyici kendi aralığının sonunu geçti olup olmadığını test etmek için kullanılır.  
  
 Bu üye işlevi yerine kullanabileceğiniz `end()` üye işlevi dönüş değeri garanti `const_iterator`. Genellikle, ile birlikte kullanılır [otomatik](../cpp/auto-cpp.md) kesintisi anahtar sözcüğü, aşağıdaki örnekte gösterildiği gibi yazın. Örnekte, göz önünde bulundurun `Container` bir değiştirilebilir için (olmayan `const`) destekleyen herhangi bir türde kapsayıcı `end()` ve `cend()`.  
  
```cpp  
auto i1 = Container.end();
// i1 is Container<T>::iterator   
auto i2 = Container.cend();
// i2 is Container<T>::const_iterator  
```  
  
 Tarafından döndürülen değer `cend` değil başvuru yapıldı.  
  
##  <a name="clear"></a>  unordered_map::Clear  
 Tüm öğeleri kaldırır.  
  
```  
void clear();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlev çağrılarını [unordered_map::erase](#erase) `(` [unordered_map::begin](#begin) `(),` [unordered_map::end](#end)`())`.  
  
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
  
##  <a name="const_iterator"></a>  unordered_map::const_iterator  
 Denetlenen dizi için bir sabit yineleyici türü.  
  
```  
typedef T1 const_iterator;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Denetimli sırası için sabit bir iletme yineleyici olarak hizmet verebilir bir nesne türünü tanımlar. Bunu açıklanan burada uygulama tanımlı türü eşanlamlısı olarak `T1`.  
  
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
  
##  <a name="const_local_iterator"></a>  unordered_map::const_local_iterator  
 Denetlenen dizi için bir sabit demet yineleyici türü.  
  
```  
typedef T5 const_local_iterator;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bir kabı için sabit bir iletme yineleyici olarak hizmet verebilir bir nesne türünü tanımlar. Bunu açıklanan burada uygulama tanımlı türü eşanlamlısı olarak `T5`.  
  
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
  
##  <a name="const_pointer"></a>  unordered_map::const_pointer  
 Bir öğe için sabit bir işaretçi türü.  
  
```  
typedef Alloc::const_pointer const_pointer;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Denetimli dizi bir öğe için sabit bir işaretçi olarak hizmet verebilir bir nesne türünü tanımlar.  
  
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
  
##  <a name="const_reference"></a>  unordered_map::const_reference  
 Bir öğe için sabit bir başvuru türü.  
  
```  
typedef Alloc::const_reference const_reference;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Öğenin denetimli dizisi sabit bir başvuru olarak hizmet verebilir bir nesne türünü tanımlar.  
  
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
  
##  <a name="count"></a>  unordered_map::Count  
 Belirtilen bir anahtar ile eşleşen öğe sayısını bulur.  
  
```  
size_type count(const Key& keyval) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `keyval`  
 Aranacak anahtar değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 Üye fonksiyonu tarafından ayrılmış aralıktaki öğe sayısını döndürür [unordered_map::equal_range](#equal_range)`(keyval)`.  
  
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
  
##  <a name="difference_type"></a>  unordered_map::difference_type  
 İki öğe arasındaki işaretli mesafenin türü.  
  
```  
typedef T3 difference_type;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 İmzalı tamsayı türünü herhangi iki öğe denetlenen sıradaki adreslerini arasındaki farkı temsil eden bir nesne tanımlar. Bunu açıklanan burada uygulama tanımlı türü eşanlamlısı olarak `T3`.  
  
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
  
##  <a name="emplace"></a>  unordered_map::emplace  
 (Hiçbir kopyalama veya taşıma işlemler gerçekleştirilir) yerinde bir unordered_map oluşturulan bir öğe ekler.  
  
```  
template <class... Args>  
pair<iterator, bool>  emplace( Args&&... args);
```  
  
### <a name="parameters"></a>Parametreler  
  
|||  
|-|-|  
|Parametre|Açıklama|  
|`args`|Öğenin değeri eşdeğer sıralı içermedikçe unordered_map eklenecek bir öğe oluşturmak için iletilen bağımsız değişkenler.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 A `pair` , `bool` ekleme yaptıysanız true, bulunmadıysa false değerini bileşenini döndürür `unordered_map` zaten anahtar sıralama içinde karşılık gelen bir değer var ve bu, yineleyici bileşenini döndürür adresi yeni bir yerde bir öğe içeriyor öğe eklendi veya öğe zaten bulunduğu.  
  
 Bir çift yineleyici bileşeninin erişmek için `pr` bu üye işlevi tarafından döndürülen, kullanın `pr.first`ve başvurabilir için `*(pr.first)`. Erişim için `bool` çiftinin bileşen `pr` bu üye işlevi tarafından döndürülen, kullanmak `pr.second`.  
  
### <a name="remarks"></a>Açıklamalar  
 Yineleyiciler veya başvuruları olmadığından bu işlev tarafından geçersiz kılınır.  
  
 Bir özel durum oluşturulur ancak kapsayıcının karma işlevi gerçekleşmez kapsayıcı ekleme sırasında değiştirilmez. Karma işlev özel durum, tanımlanmamış bir sonucudur.  
  
 Kod örneği için bkz: [map::emplace](../standard-library/map-class.md#emplace).  
  
##  <a name="emplace_hint"></a>  unordered_map::emplace_hint  
 Yerinde (hiçbir kopyalama veya taşıma işlemler gerçekleştirilir), yerleştirme İpucu ile oluşturulan bir öğe ekler.  
  
```  
template <class... Args>  
iterator emplace_hint(const_iterator where, Args&&... args);
```  
  
### <a name="parameters"></a>Parametreler  
  
|||  
|-|-|  
|Parametre|Açıklama|  
|`args`|Unordered_map bu öğe zaten içeriyor veya zaten bir öğe olan anahtar içerdiği sürece daha genel olarak, eşdeğer sıralanır sürece unordered_map eklenecek bir öğe oluşturmak için iletilen bağımsız değişkenler.|  
|`where`|Ekleme için doğru noktası aramaya başlamak için yer ile ilgili bir ipucu.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yineleyici yeni eklenen öğesi.  
  
 Öğe zaten var olduğundan ekleme başarısız olursa, yineleyici varolan öğeyi döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Başvuru bu işlev tarafından geçersiz kılınır.  
  
 Bir özel durum oluşturulur ancak kapsayıcının karma işlevi gerçekleşmez kapsayıcı ekleme sırasında değiştirilmez. Karma işlev özel durum, tanımlanmamış bir sonucudur.  
  
 [Value_type](../standard-library/map-class.md#value_type) böylece bir öğe değerini bir sıralı çifti anahtar değerine eşit ilk bileşeni ve öğenin veri değerine eşit ikinci bileşeni ile bir çift öğesidir.  
  
 Kod örneği için bkz: [map::emplace_hint](../standard-library/map-class.md#emplace_hint).  
  
##  <a name="empty"></a>  unordered_map::empty  
 Bir öğe olup olmadığını sınar.  
  
```  
bool empty() const;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevi boş denetimli dizisi için true değerini döndürür.  
  
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
  
##  <a name="end"></a>  unordered_map::End  
 Denetlenen dizinin bitişini belirtir.  
  
```  
iterator end();
const_iterator end() const; 
local_iterator end(size_type nbucket);
const_local_iterator end(size_type nbucket) const;
```  
  
### <a name="parameters"></a>Parametreler  
  
|||  
|-|-|  
|Parametre|Açıklama|  
|`nbucket`|Demet sayısı.|  
  
### <a name="remarks"></a>Açıklamalar  
 İlk iki üye işlevleri iletme yineleyici dizisi yalnızca ötesinde işaret döndür. Son iki üye işlevleri yalnızca demet ötesinde işaret iletme yineleyici dönmek `nbucket`.  
  
##  <a name="equal_range"></a>  unordered_map::equal_range  
 Belirtilen bir anahtarla eşleşen aralığı bulur.  
  
```  
std::pair<iterator, iterator>  equal_range(const Key& keyval);
std::pair<const_iterator, const_iterator>  equal_range(const Key& keyval) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `keyval`  
 Aranacak anahtar değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevini yineleyiciler çifti döndürür `X` şekilde `[X.first, X.second)` yalnızca bu öğeler ile eşdeğer sıralama sahip denetimli dizisi sınırlandırır `keyval`. Bu tür bir öğe varsa, her iki yineleyiciler olan `end()`.  
  
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
  
##  <a name="erase"></a>  unordered_map::ERASE  
 Bir öğenin veya bir dizi öğeleri unordered_map belirtilen konumlardan kaldırır veya belirtilen anahtar eşleşen öğeleri kaldırır.  
  
```  
iterator erase(const_iterator Where);
iterator erase(const_iterator First, const_iterator Last);
size_type erase(const key_type& Key);
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
 İlk iki üye işlevleri için çift yönlü Yineleyici, kaldırılan öğelerin ya da böyle bir öğe varsa harita sonuna olan bir öğeyi dışında kalan ilk öğe belirler.  
  
 Üye işlevi için üçüncü unordered_map kaldırılmış olan öğe sayısını döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Kod örneği için bkz: [map::erase](../standard-library/map-class.md#erase).  
  
##  <a name="find"></a>  unordered_map::Find  
 Belirtilen bir anahtarla eşleşen bir öğeyi bulur.  
  
```  
const_iterator find(const Key& keyval) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `keyval`  
 Aranacak anahtar değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevi döndürür [unordered_map::equal_range](#equal_range)`(keyval).first`.  
  
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
  
##  <a name="get_allocator"></a>  unordered_map::get_allocator  
 Depolanan ayırıcı nesnesini alır.  
  
```  
Alloc get_allocator() const;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevini saklı ayırıcısı nesnesini döndürür.  
  
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
  
##  <a name="hash"></a>  unordered_map::hash_function  
 Depolanan karma işlevi nesnesini alır.  
  
```  
Hash hash_function() const;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevini depolanan karma işlev nesnesi döndürür.  
  
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
  
##  <a name="hasher"></a>  unordered_map::hasher  
 Karma işlevin türü.  
  
```  
typedef Hash hasher;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Şablon parametresi için bir eş anlamlı türüdür `Hash`.  
  
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
  
##  <a name="insert"></a>  unordered_map::insert  
 Bir öğenin veya öğe aralığı bir unordered_map ekler.  
  
```  
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
  
|||  
|-|-|  
|Parametre|Açıklama|  
|`Val`|Anahtar eşdeğer sıralanmış bir öğe içermiyorsa unordered_map Eklenecek öğenin değeri.|  
|`Where`|Ekleme için doğru noktası aramaya başlamak için koyun.|  
|`ValTy`|Unordered_map öğesi oluşturmak için kullanabileceğiniz bağımsız değişken türünü belirten bir şablon parametresi [value_type](../standard-library/map-class.md#value_type)ve mükemmel ileten `Val` bağımsız değişken olarak.|  
|`First`|Kopyalanacak ilk öğe konumu.|  
|`Last`|Kopyalanacak yalnızca son öğenin ötesinde konumu.|  
|`InputIterator`|Gereksinimlerini karşılayan şablon işlevi bağımsız değişken bir [giriş yineleyici](../standard-library/input-iterator-tag-struct.md) oluşturmak için kullanılan bir türü öğelerine işaret [value_type](../standard-library/map-class.md#value_type) nesneleri.|  
|`IList`|[İnitializer_list](../standard-library/initializer-list.md) öğeleri kopyalanacak.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 Tek öğe üye işlevleri (1) ve (2), dönüş bir [çifti](../standard-library/pair-structure.md) , `bool` bileşenidir ekleme yaptıysanız true ve false unordered_map anahtar eşdeğer bir değere sahip bir öğe içeriyorsa, sıralama. Dönüş değeri çifti yineleyici bileşeninin varsa yeni eklenen öğesine işaret eden `bool` bileşenidir true veya varolan öğesine durumunda `bool` bileşen değer false.  
  
 İpucu ile tek öğe üye işlevleri (3) ve (4), yeni öğe unordered_map eklenen burada veya eşdeğer bir anahtarı olan bir öğe zaten var olan öğe varsa konumuna işaret eden bir yineleyici döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Hiçbir yineleyiciler, işaretçileri veya başvuruları bu işlev tarafından geçersiz kılınır.  
  
 Bir özel durum oluşturulur ancak kapsayıcının karma işlevi gerçekleşmez yalnızca bir öğe ekleme sırasında kapsayıcının durumu değiştirilemez. Karma işlev özel durum, tanımlanmamış bir sonucudur. Bir özel durum, birden çok öğe ekleme sırasında kapsayıcı belirtilmeyen ancak geçerli bir durumda bırakılır.  
  
 Yineleyici bileşeninin erişmek için bir `pair` `pr` tek öğe üye işlevleri tarafından döndürülen, kullanın `pr.first`; döndürülen çifti içinde yineleyici dereference kullanmak için `*pr.first`, bir öğenin vermiş. Erişim için `bool` bileşen, kullanım `pr.second`. Bu makaledeki örnek kod bir örnek için bkz.  
  
 [Value_type](../standard-library/map-class.md#value_type) kapsayıcısı ve harita Yakınlaştırmasını ait bir typedef, kapsayıcısıdır `map<K, V>::value_type` olan `pair<const K, V>`. Bir öğenin ilk bileşen anahtar değerine eşit olan ve ikinci bileşen öğesi veri değerine eşit olan bir sıralı çifti değerdir.  
  
 Aralık üye işlevi (5) aralığında bir yineleyici tarafından ele her öğesine karşılık gelen bir unordered_map bir dizi öğesi değerlerini ekler `[First, Last)`; bu nedenle, `Last` takılı. Kapsayıcı üye fonksiyonu `end()` kapsayıcı son öğesi hemen sonra konuma başvuruyor — Örneğin, deyim `m.insert(v.begin(), v.end());` tüm öğeleri ekleme girişiminde `v` içine `m`. Yalnızca benzersiz değerler aralığında olan öğenin eklenir; Yinelenen değer yok sayılır. Hangi öğelerin reddedilir izlemek için tek öğe sürümlerini kullanan `insert`.  
  
 Başlatıcı listesi üye işlevi (6) kullanan bir [initializer_list](../standard-library/initializer-list.md) öğeleri unordered_map kopyalamak için.  
  
 Yerinde oluşturulan bir öğe eklemeye — diğer bir deyişle, kopyalama veya taşıma işlemi yok gerçekleştirilen — bkz [unordered_map::emplace](#emplace) ve [unordered_map::emplace_hint](#emplace_hint).  
  
 Kod örneği için bkz: [map::insert](../standard-library/map-class.md#insert).  
  
##  <a name="iterator"></a>  unordered_map::iterator  
 Denetlenen dizi için bir yineleyici türü.  
  
```  
typedef T0 iterator;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Tür iletme yineleyici denetlenen dizisi olarak hizmet verebilir nesneyi açıklar. Bunu açıklanan burada uygulama tanımlı türü eşanlamlısı olarak `T0`.  
  
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
  
##  <a name="key_eq"></a>  unordered_map::key_eq  
 Depolanan karşılaştırma işlevi nesnesini alır.  
  
```  
Pred key_eq() const;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevini saklı karşılaştırma işlev nesnesi döndürür.  
  
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
  
##  <a name="key_equal"></a>  unordered_map::key_equal  
 Karşılaştırma işlevinin türü.  
  
```  
typedef Pred key_equal;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Şablon parametresi için bir eş anlamlı türüdür `Pred`.  
  
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
  
##  <a name="key_type"></a>  unordered_map::key_type  
 Bir sıralama anahtarının türü.  
  
```  
typedef Key key_type;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Şablon parametresi için bir eş anlamlı türüdür `Key`.  
  
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
  
##  <a name="load_factor"></a>  unordered_map::load_factor  
 Demet başına ortalama öğeyi sayar.  
  
```  
float load_factor() const;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevi döndürür `(float)` [unordered_map::size](#size)`() / (float)`[unordered_map::bucket_count](#bucket_count)`()`, sepet başına ortalama sayısı.  
  
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
  
##  <a name="local_iterator"></a>  unordered_map::local_iterator  
 Bir demet yineleyici türü.  
  
```  
typedef T4 local_iterator;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Tür iletme yineleyici bir sepet olarak hizmet verebilir nesneyi açıklar. Bunu açıklanan burada uygulama tanımlı türü eşanlamlısı olarak `T4`.  
  
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
  
##  <a name="mapped_type"></a>  unordered_map::mapped_type  
 Her bir anahtar ile ilişkili bir eşlenen değer türü.  
  
```  
typedef Ty mapped_type;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Şablon parametresi için bir eş anlamlı türüdür `Ty`.  
  
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
  
##  <a name="max_bucket_count"></a>  unordered_map::max_bucket_count  
 En yüksek demet sayısını alır.  
  
```  
size_type max_bucket_count() const;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevini demet şu anda izin verilen maksimum sayısını döndürür.  
  
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
  
##  <a name="max_load_factor"></a>  unordered_map::max_load_factor  
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
  
##  <a name="max_size"></a>  unordered_map::max_size  
 Denetlenen dizinin en büyük boyutunu alır.  
  
```  
size_type max_size() const;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevini nesne denetleyebilirsiniz uzun sırası uzunluğunu döndürür.  
  
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
  
##  <a name="op_at"></a>  unordered_map::operator]  
 Belirtilen anahtarı içeren bir öğe bulur veya ekler.  
  
```  
Ty& operator[](const Key& keyval);

Ty& operator[](Key&& keyval);
```  
  
### <a name="parameters"></a>Parametreler  
  
|||  
|-|-|  
|Parametre|Açıklama|  
|`Keyval`|Bulmak veya eklemek için anahtar değeri.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 Eklenen öğenin veri değerine başvuru.  
  
### <a name="remarks"></a>Açıklamalar  
 Bağımsız değişken anahtar değeri bulunamazsa, değer veri türünün varsayılan değeriyle birlikte eklenir.  
  
 `operator[]` bir eşlemeye öğe eklemek için kullanılabilir *m* kullanarak *m*[_ *anahtar*] = `DataValue`; burada `DataValue` değeri `mapped_type` öğesi ile bir anahtar değerini \_ *anahtar*.  
  
 Kullanırken `operator[]` öğe eklemek için döndürülen başvuru ekleme önceden var olan bir öğe değiştirme veya yeni bir tane oluşturmak anlamına gelmez. Üye işlevleri [Bul](../standard-library/map-class.md#find) ve [Ekle](../standard-library/map-class.md#insert) belirtilen anahtara sahip bir öğe zaten bir ekleme önce mevcut olup olmadığını belirlemek için kullanılabilir.  
  
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
 Yineleyici üye fonksiyonu belirler `where` dönüş değeri olarak [unordered_map::insert](#insert) `(` [unordered_map::value_type](#value_type)`(keyval, Ty())`. (Böyle bir öğe yoksa, belirtilen anahtara sahip öğe ekler.) Daha sonra bir başvuru döndürür `(*where).second`.  
  
##  <a name="op_eq"></a>  unordered_map::operator=  
 Başka bir unordered_map öğeleri kullanarak bu unordered_map öğeleri değiştirir.  
  
```  
unordered_map& operator=(const unordered_map& right);

unordered_map& operator=(unordered_map&& right);
```  
  
### <a name="parameters"></a>Parametreler  
  
|||  
|-|-|  
|Parametre|Açıklama|  
|`right`|İşleç işlevi içerikten atar unordered_map.|  
  
### <a name="remarks"></a>Açıklamalar  
 Tüm öğeleri ilk sürüm kopyalar `right` bu unordered_map için.  
  
 İkinci Sürüm tüm öğeleri taşır `right` bu unordered_map için.  
  
 Önce bu unordered_map bulunan herhangi bir öğe `operator`= yürütür atılır.  
  
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
  
##  <a name="pointer"></a>  unordered_map::pointer  
 Bir öğe için bir işaretçi türü.  
  
```  
typedef Alloc::pointer pointer;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Denetimli dizi bir öğe için bir işaretçi olarak hizmet verebilir bir nesne türünü tanımlar.  
  
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
  
##  <a name="reference"></a>  unordered_map::Reference  
 Bir öğe için bir başvuru türü.  
  
```  
typedef Alloc::reference reference;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Öğenin denetimli sırasının bir başvuru olarak hizmet verebilir bir nesne türünü tanımlar.  
  
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
  
##  <a name="rehash"></a>  unordered_map::rehash  
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
  
##  <a name="size"></a>  unordered_map::size  
 Öğe sayısını sayar.  
  
```  
size_type size() const;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevini denetimli sırası uzunluğunu döndürür.  
  
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
  
##  <a name="size_type"></a>  unordered_map::size_type  
 İki öğe arasındaki işaretsiz bir mesafenin türü.  
  
```  
typedef T2 size_type;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 İşaretsiz tamsayı türünü herhangi denetimli sırası uzunluğu temsil eden bir nesne tanımlar. Bunu açıklanan burada uygulama tanımlı türü eşanlamlısı olarak `T2`.  
  
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
  
##  <a name="swap"></a>  unordered_map::Swap  
 İki kapsayıcının içeriğinin yerini değiştirir.  
  
```  
void swap(unordered_map& right);
```  
  
### <a name="parameters"></a>Parametreler  
 `right`  
 İle değiştirme kapsayıcı.  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevini denetimli sıraları arasında değiştirir `*this` ve `right`. Varsa [unordered_map::get_allocator](#get_allocator)`() == right.get_allocator()`, bunu sabit sürede yapar, depolanan nitelikler nesne türünün kopyalama sonucunda yalnızca bir özel durum oluşturur `Tr`, ve işaretçileri, hiçbir başvuru geçersiz kılar veya iki denetimli sıraları öğelerinde atamak yineleyiciler. Aksi durumda, iki denetimli sıralarında öğesi atamaları ve oluşturucu çağrıları öğe sayısını orantılı çeşitli gerçekleştirir.  
  
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
  
##  <a name="unordered_map"></a>  unordered_map::unordered_map  
 Bir kapsayıcı nesnesi oluşturur.  
  
```  
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
  
|||  
|-|-|  
|Parametre|Açıklama|  
|`Al`|Depolanacak ayırıcı nesne.|  
|`Comp`|Depolanacak karşılaştırma işlevi nesnesi.|  
|`Hash`|Depolanacak karma işlev nesnesi.|  
|`Bucket_count`|En düşük demet sayısı.|  
|`Right`|Kopyalanacak kapsayıcı.|  
|`First`||  
|`Last`||  
|`IList`|Kopyalanacak öğeleri içeren initializer_list.|  
  
### <a name="remarks"></a>Açıklamalar  
 İlk oluşturucusu tarafından denetlenen sırasının bir kopyasını belirtir `right`. İkinci oluşturucu boş bir denetlenmiş dizi belirtir. Bir dizi öğesi değerlerini üçüncü Oluşturucusu ekler `[first, last)`. Dördüncü Oluşturucusu taşıyarak sırasının bir kopyasını belirtir `right`.  
  
 Ayrıca, tüm oluşturucular çeşitli depolanmış değerleri başlatır. Kopya Oluşturucu için değerleri alanından elde edilen `Right`. Aksi durumda:.  
  
 Bağımsız değişken demet sayısı alt sınırı: `Bucket_count`, yoksa açıklanan varsayılan bir değer olup olmadığını burada uygulama tanımlı bir değer olarak `N0`.  
  
 Bağımsız değişken karma işlev nesnesidir `Hash`, yoksa bu olup olmadığını `Hash()`.  
  
 Karşılaştırma işlevi bağımsız değişken nesnesidir `Comp`, yoksa bu olup olmadığını `Pred()`.  
  
 Bağımsız değişken ayırıcısı nesnesidir `Al`, mevcut; Aksi takdirde bu olup olmadığını `Alloc()`.  
  
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
  
##  <a name="value_type"></a>  unordered_map::value_type  
 Öğenin türü.  
  
```  
typedef std::pair<const Key, Ty> value_type;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Öğenin denetimli dizisinin türünü tanımlar.  
  
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
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [<unordered_map>](../standard-library/unordered-map.md)   
 [Kapsayıcıları](../cpp/containers-modern-cpp.md)   
 [C++ Standart kitaplığında iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)

