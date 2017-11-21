---
title: "unordered_set sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
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
dev_langs: C++
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
caps.latest.revision: "23"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: dfc07d8cd923b945c04c8fb9a89e7f8ee8af1316
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="unorderedset-class"></a>unordered_set Sınıfı
Şablon sınıfı türündeki öğeler değişen uzunluk dizisi denetleyen bir nesneyi tanımlayan `const Key`. Dizi çağrılan demetlerin sıralı bir dizi kümesini bölümleyen bir karma işlev tarafından zayıf bir şekilde sıralanır. Her bir demette herhangi bir öğe çiftinin eşdeğer sıralamaya sahip olup olmadığını belirleyen bir karşılaştırma işlevi vardır. Her bir öğe hem bir sıralama anahtarı hem de bir değer depolar. Dizi, en azından tüm demetleri kabaca eşit uzunlukta olduğunda, dizideki (sabit zaman) öğe sayısından bağımsız olabilen işlem sayısına sahip rastgele bir öğenin aranması, eklenmesi ve kaldırılmasına izin verecek şekilde temsil edilir. En kötü durumda, tüm öğeler tek bir demet içinde olduğunda işlem sayısı dizideki (doğrusal zaman) öğelerin sayısıyla orantılıdır. Ayrıca, bir öğe eklenmesi hiçbir yineleyiciyi geçersiz kılmaz; bir öğenin kaldırılması yalnızca bu kaldırılan öğeyi gösteren yineleyicileri geçersiz kılar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template <
   class Key,  
   class Hash = std::hash<Key>,  
   class Pred = std::equal_to<Key>,  
   class Alloc = std::allocator<Key>>  
class unordered_set;  
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
|[unordered_set](#unordered_set)|Bir kapsayıcı nesnesi oluşturur.|  
  
|||  
|-|-|  
|İşleçler|Açıklama|  
|[unordered_set::operator =](#op_eq)|Bir karma tabloya kopyalar.|  
  
## <a name="remarks"></a>Açıklamalar  
 Nesne denetlediği iki depolanan nesneler, bir karşılaştırma işlevi nesne türü çağırarak dizisi siparişleri[unordered_set::key_equal](#key_equal) ve karma işlevini nesne türü[unordered_set::hasher](#hasher). Üye işlevini çağırarak ilk saklı nesneye erişim[unordered_set::key_eq](#key_eq)`()`; ve üye işlevini çağırarak ikinci saklı nesneye erişim[unordered_set::hash_function](#hash) `()`. Özellikle, tüm değerler için `X` ve `Y` türü `Key`, çağrı `key_eq()(X, Y)` yalnızca iki bağımsız değişken değerleri eşdeğer sıralama varsa true değerini döndürür; çağrı `hash_function()(keyval)` bir dağıtım türü değerlerinverir`size_t`. Şablon sınıfı aksine[unordered_multiset sınıfı](../standard-library/unordered-multiset-class.md), şablon sınıfın bir nesnesi `unordered_set` sağlar `key_eq()(X, Y)` her zaman denetimli dizisi için herhangi iki öğeleri false olur. (Anahtarlar benzersizdir.)  
  
 Nesne ayrıca, demet başına istenen ortalama öğe sayısını belirten en yüksek yük faktörünü depolar. Bir öğe ekleme neden olursa[unordered_set::load_factor](#load_factor) `()` en fazla Yük faktörü aşmayı kapsayıcı sayısını artırır ve karma tablosu gerektiği gibi yeniden oluşturur.  
  
 Denetlenen dizideki öğelerin gerçek sırası karma işleve, karşılaştırma işlevine, ekleme sırasına, en yüksek yük faktörüne ve geçerli demet sayısına bağlıdır. Denetlenen dizideki öğelerin sırasını genelde tahmin edemezsiniz. Ancak, eşdeğer sıralamaya sahip öğelerin herhangi bir alt kümesinin her zaman denetlenen dizide bitişik olduğundan emin olabilirsiniz.  
  
 Nesne ayırır ve saklı ayırıcısı nesne türü denetlediği dizisi için depolama boşaltır[unordered_set::allocator_type](#allocator_type). Böyle bir ayırıcı nesne şablonu sınıfın bir nesnesi olarak aynı dış arabirimi olmalıdır `allocator`. Depolanan ayırıcı nesnenin kapsayıcı nesne atandığında kopyalanmayacağını unutmayın.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<unordered_set >  
  
 **Namespace:** std  
  
##  <a name="allocator_type"></a>unordered_set::allocator_type  
 Depolamayı yönetmek için bir ayırıcı türü.  
  
```  
typedef Alloc allocator_type;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Şablon parametresi için bir eş anlamlı türüdür `Alloc`.  
  
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
  
##  <a name="begin"></a>unordered_set::Begin  
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
    cout << " [" << it << "]";  
    }  
      
    cout << endl;  
      
    // display contents using explicit for  
    for (MySet::const_iterator it = c1.begin(); it != c1.end(); ++it) {  
        cout << " [" << *it << "]";  
    }  
      
    cout << std::endl;  
      
    // display first two items  
    MySet::iterator it2 = c1.begin();  
    cout << " [" << *it2 << "]";  
    ++it2;  
    cout << " [" << *it2 << "]";  
    cout << endl;  
      
    // display bucket containing 'a'  
    MySet::const_local_iterator lit = c1.begin(c1.bucket('a'));  
    cout << " [" << *lit << "]";  
      
    return (0);  
}  
```  
  
```Output  
 [a] [b] [c]                                   
 [a] [b] [c]                                  
 [a] [b]                                   
 [a]  
```  
  
##  <a name="bucket"></a>unordered_set::Bucket  
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
      
    // display contents " [c] [b] [a]"  
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)  
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
  
##  <a name="bucket_count"></a>unordered_set::bucket_count  
 Demet sayısını alır.  
  
```  
size_type bucket_count() const;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevi geçerli sayısını döndürür.  
  
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
      
    // display contents " [c] [b] [a]"  
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)  
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
  
##  <a name="bucket_size"></a>unordered_set::bucket_size  
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
      
    // display contents " [c] [b] [a]"  
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)  
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
  
##  <a name="cbegin"></a>unordered_set::cbegin  
 Döndürür bir `const` aralığın ilk öğe adresleri yineleyici.  
  
```  
const_iterator cbegin() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 A `const` ilk öğede aralığı ya da yalnızca boş bir aralığın ötesinde konumunu işaret İleri erişim yineleyici (boş bir aralığın için `cbegin() == cend()`).  
  
### <a name="remarks"></a>Açıklamalar  
 Dönüş değeri ile `cbegin`, öğeleri aralığında değiştirilemez.  
  
 Bu üye işlevi yerine kullanabileceğiniz `begin()` üye işlevi dönüş değeri garanti `const_iterator`. Genellikle, ile birlikte kullanılır[otomatik](../cpp/auto-cpp.md) kesintisi anahtar sözcüğü, aşağıdaki örnekte gösterildiği gibi yazın. Örnekte, göz önünde bulundurun `Container` bir değiştirilebilir için (olmayan `const`) destekleyen herhangi bir türde kapsayıcı `begin()` ve `cbegin()`.  
  
```cpp  
auto i1 = Container.begin();
// i1 isContainer<T>::iterator  
auto i2 = Container.cbegin();

// i2 isContainer<T>::const_iterator  
```  
  
##  <a name="cend"></a>unordered_set::cend  
 Döndürür bir `const` konumun yalnızca bir aralıkta son öğenin ötesinde adresleri yineleyici.  
  
```  
const_iterator cend() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 A `const` yalnızca aralığın sonunu aşan işaret İleri erişim yineleyici.  
  
### <a name="remarks"></a>Açıklamalar  
 `cend`Yineleyici kendi aralığının sonunu geçti olup olmadığını test etmek için kullanılır.  
  
 Bu üye işlevi yerine kullanabileceğiniz `end()` üye işlevi dönüş değeri garanti `const_iterator`. Genellikle, ile birlikte kullanılır[otomatik](../cpp/auto-cpp.md) kesintisi anahtar sözcüğü, aşağıdaki örnekte gösterildiği gibi yazın. Örnekte, göz önünde bulundurun `Container` bir değiştirilebilir için (olmayan `const`) destekleyen herhangi bir türde kapsayıcı `end()` ve `cend()`.  
  
```cpp  
auto i1 = Container.end();
// i1 isContainer<T>::iterator  
auto i2 = Container.cend();

// i2 isContainer<T>::const_iterator  
```  
  
 Tarafından döndürülen değer `cend` değil başvuru yapıldı.  
  
##  <a name="clear"></a>unordered_set::Clear  
 Tüm öğeleri kaldırır.  
  
```  
void clear();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlev çağrılarını[unordered_set::erase](#erase) `(` [unordered_set::begin](#begin) `(),` [unordered_set::end](#end)`())`.  
  
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
      
    // display contents " [c] [b] [a]"  
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)  
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
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)  
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
  
##  <a name="const_iterator"></a>unordered_set::const_iterator  
 Denetlenen dizi için bir sabit yineleyici türü.  
  
```  
typedef T1 const_iterator;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Denetimli sırası için sabit bir iletme yineleyici olarak hizmet verebilir bir nesne türünü tanımlar. Bunu açıklanan burada uygulama tanımlı türü eşanlamlısı olarak `T1`.  
  
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
      
    // display contents " [c] [b] [a]"  
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)  
    std::cout << " [" << *it << "]";  
    std::cout << std::endl;  
      
    return (0);  
}  
```  
  
```Output  
 [c] [b] [a]  
```  
  
##  <a name="const_local_iterator"></a>unordered_set::const_local_iterator  
 Denetlenen dizi için bir sabit demet yineleyici türü.  
  
```  
typedef T5 const_local_iterator;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bir kabı için sabit bir iletme yineleyici olarak hizmet verebilir bir nesne türünü tanımlar. Bunu açıklanan burada uygulama tanımlı türü eşanlamlısı olarak `T5`.  
  
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
      
    // display contents " [c] [b] [a]"  
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)  
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
  
##  <a name="const_pointer"></a>unordered_set::const_pointer  
 Bir öğe için sabit bir işaretçi türü.  
  
```  
typedef Alloc::const_pointer const_pointer;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Denetimli dizi bir öğe için sabit bir işaretçi olarak hizmet verebilir bir nesne türünü tanımlar.  
  
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
      
    // display contents " [c] [b] [a]"  
    for (Myset::iterator it = c1.begin(); it != c1.end(); ++it)  
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
  
##  <a name="const_reference"></a>unordered_set::const_reference  
 Bir öğe için sabit bir başvuru türü.  
  
```  
typedef Alloc::const_reference const_reference;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Öğenin denetimli dizisi sabit bir başvuru olarak hizmet verebilir bir nesne türünü tanımlar.  
  
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
      
    // display contents " [c] [b] [a]"  
    for (Myset::iterator it = c1.begin(); it != c1.end(); ++it)  
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
  
##  <a name="count"></a>unordered_set::Count  
 Belirtilen bir anahtar ile eşleşen öğe sayısını bulur.  
  
```  
size_type count(const Key& keyval) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `keyval`  
 Aranacak anahtar değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 Üye fonksiyonu tarafından ayrılmış aralıktaki öğe sayısını döndürür[unordered_set::equal_range](#equal_range)`(keyval)`.  
  
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
      
    // display contents " [c] [b] [a]"  
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)  
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
  
##  <a name="difference_type"></a>unordered_set::difference_type  
 İki öğe arasındaki işaretli mesafenin türü.  
  
```  
typedef T3 difference_type;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 İmzalı tamsayı türünü herhangi iki öğe denetlenen sıradaki adreslerini arasındaki farkı temsil eden bir nesne tanımlar. Bunu açıklanan burada uygulama tanımlı türü eşanlamlısı olarak `T3`.  
  
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
      
    // display contents " [c] [b] [a]"  
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)  
        std::cout << " [" << *it << "]";  
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
  
##  <a name="emplace"></a>unordered_set::emplace  
 (Hiçbir kopyalama veya taşıma işlemler gerçekleştirilir) yerinde oluşturulan bir öğe ekler.  
  
```  
template <class... Args>  
pair<iterator, bool>  
emplace(
Args&&... args);
```  
  
### <a name="parameters"></a>Parametreler  
  
|||  
|-|-|  
|Parametre|Açıklama|  
|`args`|Öğenin değeri eşdeğer sıralı içermedikçe unordered_set eklenecek bir öğe oluşturmak için iletilen bağımsız değişkenler.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 A `pair` , `bool` ekleme yaptıysanız true, bulunmadıysa false değerini bileşenini döndürür `unordered_set` zaten anahtar sıralama içinde karşılık gelen bir değer var ve bu, yineleyici bileşenini döndürür adresi yeni bir yerde bir öğe içeriyor öğe eklendi veya öğe zaten bulunduğu.  
  
 Bir çift yineleyici bileşeninin erişmek için `pr` bu üye işlevi tarafından döndürülen, kullanın `pr.first`ve başvurabilir için `*(pr.first)`. Erişim için `bool` çiftinin bileşen `pr` bu üye işlevi tarafından döndürülen, kullanmak `pr.second`.  
  
### <a name="remarks"></a>Açıklamalar  
 Yineleyiciler veya başvuruları olmadığından bu işlev tarafından geçersiz kılınır.  
  
 Bir özel durum oluşturulur ancak kapsayıcının karma işlevi gerçekleşmez kapsayıcı ekleme sırasında değiştirilmez. Karma işlev özel durum, tanımlanmamış bir sonucudur.  
  
 Kod örneği için bkz:[set::emplace](../standard-library/set-class.md#emplace).  
  
##  <a name="emplace_hint"></a>unordered_set::emplace_hint  
 Yerinde (hiçbir kopyalama veya taşıma işlemler gerçekleştirilir), yerleştirme İpucu ile oluşturulan bir öğe ekler.  
  
```  
template <class... Args>  
iterator emplace_hint(
const_iteratorwhere,  
Args&&... args);
```  
  
### <a name="parameters"></a>Parametreler  
  
|||  
|-|-|  
|Parametre|Açıklama|  
|`args`|Unordered_set bu öğe zaten içeriyor veya zaten bir öğe olan anahtar içerdiği sürece daha genel olarak, eşdeğer sıralanır sürece unordered_set eklenecek bir öğe oluşturmak için iletilen bağımsız değişkenler.|  
|`where`|Ekleme için doğru noktası aramaya başlamak için yer ile ilgili bir ipucu.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yineleyici yeni eklenen öğesi.  
  
 Öğe zaten var olduğundan ekleme başarısız olursa, yineleyici varolan öğeyi döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Yineleyiciler veya başvuruları olmadığından bu işlev tarafından geçersiz kılınır.  
  
 Bir özel durum oluşturulur ancak kapsayıcının karma işlevi gerçekleşmez kapsayıcı ekleme sırasında değiştirilmez. Karma işlev özel durum, tanımlanmamış bir sonucudur.  
  
 Kod örneği için bkz:[set::emplace_hint](../standard-library/set-class.md#emplace_hint).  
  
##  <a name="empty"></a>unordered_set::empty  
 Bir öğe olup olmadığını sınar.  
  
```  
bool empty() const;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevi boş denetimli dizisi için true değerini döndürür.  
  
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
      
    // display contents " [c] [b] [a]"  
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)  
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
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)  
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
  
##  <a name="end"></a>unordered_set::End  
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
      
    // display contents " [c] [b] [a]"  
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)  
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
  
##  <a name="equal_range"></a>unordered_set::equal_range  
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
 Üye işlevini yineleyiciler çifti döndürür `X` şekilde`[X.first, X.second)` yalnızca bu öğeler ile eşdeğer sıralama sahip denetimli dizisi sınırlandırır `keyval`. Bu tür bir öğe varsa, her iki yineleyiciler olan `end()`.  
  
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
      
    // display contents " [c] [b] [a]"  
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)  
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
  
##  <a name="erase"></a>unordered_set::ERASE  
 Bir öğenin veya bir dizi öğeleri unordered_set belirtilen konumlardan kaldırır veya belirtilen anahtar eşleşen öğeleri kaldırır.  
  
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
 İlk iki üye işlevleri için çift yönlü Yineleyici, kaldırılan öğelerin ya da böyle bir öğe varsa unordered_set sonuna olan bir öğeyi dışında kalan ilk öğe belirler.  
  
 Üye işlevi için üçüncü unordered_set kaldırılmış olan öğe sayısını döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Kod örneği için bkz:[set::erase](../standard-library/set-class.md#erase).  
  
##  <a name="find"></a>unordered_set::Find  
 Belirtilen bir anahtarla eşleşen bir öğeyi bulur.  
  
```  
const_iterator find(const Key& keyval) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `keyval`  
 Aranacak anahtar değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevi döndürür[unordered_set::equal_range](#equal_range)`(keyval).first`.  
  
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
      
    // display contents " [c] [b] [a]"  
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)  
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
  
##  <a name="get_allocator"></a>unordered_set::get_allocator  
 Depolanan ayırıcı nesnesini alır.  
  
```  
Alloc get_allocator() const;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevini saklı ayırıcısı nesnesini döndürür.  
  
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
  
##  <a name="hash"></a>unordered_set::hash_function  
 Depolanan karma işlevi nesnesini alır.  
  
```  
Hash hash_function() const;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevini depolanan karma işlev nesnesi döndürür.  
  
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
  
##  <a name="hasher"></a>unordered_set::hasher  
 Karma işlevin türü.  
  
```  
typedef Hash hasher;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Şablon parametresi için bir eş anlamlı türüdür `Hash`.  
  
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
  
##  <a name="insert"></a>unordered_set::insert  
 Bir öğenin veya öğe aralığı bir unordered_set ekler.  
  
```  
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
  
|||  
|-|-|  
|Parametre|Açıklama|  
|`Val`|Anahtar eşdeğer sıralanmış bir öğe içermiyorsa unordered_set Eklenecek öğenin değeri.|  
|`Where`|Ekleme için doğru noktası aramaya başlamak için koyun.|  
|`ValTy`|Unordered_set öğesi oluşturmak için kullanabileceğiniz bağımsız değişken türünü belirten bir şablon parametresi[value_type](../standard-library/map-class.md#value_type)ve mükemmel ileten `Val` bağımsız değişken olarak.|  
|`First`|Kopyalanacak ilk öğe konumu.|  
|`Last`|Kopyalanacak yalnızca son öğenin ötesinde konumu.|  
|`InputIterator`|Gereksinimlerini karşılayan şablon işlevi bağımsız değişken bir[giriş yineleyici](../standard-library/input-iterator-tag-struct.md) oluşturmak için kullanılan bir türü öğelerine işaret[value_type](../standard-library/map-class.md#value_type) nesneleri.|  
|`IList`|[İnitializer_list](../standard-library/initializer-list.md) öğeleri kopyalanacak.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 Tek öğe üye işlevleri (1) ve (2), dönüş bir[çifti](../standard-library/pair-structure.md) , `bool` bileşenidir ekleme yaptıysanız true ve false unordered_set anahtar eşdeğer bir değere sahip bir öğe içeriyorsa, sıralama. Dönüş değeri çifti yineleyici bileşeninin varsa yeni eklenen öğesine işaret eden `bool` bileşenidir true veya varolan öğesine durumunda `bool` bileşen değer false.  
  
 İpucu ile tek öğe üye işlevleri (3) ve (4), yeni öğe unordered_set eklenen burada veya eşdeğer bir anahtarı olan bir öğe zaten var olan öğe varsa konumuna işaret eden bir yineleyici döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Hiçbir yineleyiciler, işaretçileri veya başvuruları bu işlev tarafından geçersiz kılınır.  
  
 Bir özel durum oluşturulur ancak kapsayıcının karma işlevi gerçekleşmez yalnızca bir öğe ekleme sırasında kapsayıcının durumu değiştirilemez. Karma işlev özel durum, tanımlanmamış bir sonucudur. Bir özel durum, birden çok öğe ekleme sırasında kapsayıcı belirtilmeyen ancak geçerli bir durumda bırakılır.  
  
 Yineleyici bileşeninin erişmek için bir `pair` `pr` tek öğe üye işlevleri tarafından döndürülen, kullanın `pr.first`; döndürülen çifti içinde yineleyici dereference kullanmak için`*pr.first`, bir öğenin vermiş. Erişim için `bool` bileşen, kullanım `pr.second`. Bu makaledeki örnek kod bir örnek için bkz.  
  
 [Value_type](../standard-library/map-class.md#value_type) , bir kapsayıcı ve, küme ait bir typedef kapsayıcısıdır `unordered_set<V>::value_type` türü `const V`.  
  
 Aralık üye işlevi (5) aralığında bir yineleyici tarafından ele her öğesine karşılık gelen bir unordered_set bir dizi öğesi değerlerini ekler `[First, Last)`; bu nedenle, `Last` takılı. Kapsayıcı üye fonksiyonu `end()` kapsayıcı son öğesi hemen sonra konuma başvuruyor — Örneğin, deyim `s.insert(v.begin(), v.end());` tüm öğeleri ekleme girişiminde `v` içine `s`. Yalnızca benzersiz değerler aralığında olan öğenin eklenir; Yinelenen değer yok sayılır. Hangi öğelerin reddedilir izlemek için tek öğe sürümlerini kullanan `insert`.  
  
 Başlatıcı listesi üye işlevi (6) kullanan bir[initializer_list](../standard-library/initializer-list.md) öğeleri unordered_set kopyalamak için.  
  
 Yerinde oluşturulan bir öğe eklemeye — diğer bir deyişle, kopyalama veya taşıma işlemi yok gerçekleştirilen — bkz[set::emplace](../standard-library/set-class.md#emplace) ve[set::emplace_hint](../standard-library/set-class.md#emplace_hint).  
  
 Kod örneği için bkz:[set::insert](../standard-library/set-class.md#insert).  
  
##  <a name="iterator"></a>unordered_set::iterator  
 Bir sabit sağlayan bir türü[iletme yineleyici](../standard-library/forward-iterator-tag-struct.md) bir unordered_set öğelerinde okuyabilir.  
  
```  
typedef implementation-defined iterator;  
```  
  
### <a name="example"></a>Örnek  
  Örneğin bkz[başlamak](../standard-library/set-class.md#begin) bildirme ve kullanma konusunda bir örnek için bir**yineleyici**.  
  
##  <a name="key_eq"></a>unordered_set::key_eq  
 Depolanan karşılaştırma işlevi nesnesini alır.  
  
```  
Pred key_eq() const;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevini saklı karşılaştırma işlev nesnesi döndürür.  
  
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
  
##  <a name="key_equal"></a>unordered_set::key_equal  
 Karşılaştırma işlevinin türü.  
  
```  
typedef Pred key_equal;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Şablon parametresi için bir eş anlamlı türüdür `Pred`.  
  
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
  
##  <a name="key_type"></a>unordered_set::key_type  
 Bir sıralama anahtarının türü.  
  
```  
typedef Key key_type;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Şablon parametresi için bir eş anlamlı türüdür `Key`.  
  
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
      
    // display contents " [c] [b] [a]"  
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)  
        std::cout << " [" << *it << "]";  
    std::cout << std::endl;  
      
    // add a value and reinspect  
    Myset::key_type key = 'd';  
    Myset::value_type val = key;  
    c1.insert(val);  
      
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)  
        std::cout << " [" << *it << "]";  
    std::cout << std::endl;  
      
    return (0);  
}  
```  
  
```Output  
 [c] [b] [a]  
 [d] [c] [b] [a]  
```  
  
##  <a name="load_factor"></a>unordered_set::load_factor  
 Demet başına ortalama öğeyi sayar.  
  
```  
float load_factor() const;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevi döndürür`(float)`[unordered_set::size](#size)`() / (float)`[unordered_set::bucket_count](#bucket_count)`()`, sepet başına ortalama sayısı.  
  
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
      
    // display contents " [c] [b] [a]"  
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)  
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
  
##  <a name="local_iterator"></a>unordered_set::local_iterator  
 Bir demet yineleyici türü.  
  
```  
typedef T4 local_iterator;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Tür iletme yineleyici bir sepet olarak hizmet verebilir nesneyi açıklar. Bunu açıklanan burada uygulama tanımlı türü eşanlamlısı olarak `T4`.  
  
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
      
    // display contents " [c] [b] [a]"  
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)  
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
  
##  <a name="max_bucket_count"></a>unordered_set::max_bucket_count  
 En yüksek demet sayısını alır.  
  
```  
size_type max_bucket_count() const;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevini demet şu anda izin verilen maksimum sayısını döndürür.  
  
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
      
    // display contents " [c] [b] [a]"  
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)  
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
  
##  <a name="max_load_factor"></a>unordered_set::max_load_factor  
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
      
    // display contents " [c] [b] [a]"  
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)  
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
  
##  <a name="max_size"></a>unordered_set::max_size  
 Denetlenen dizinin en büyük boyutunu alır.  
  
```  
size_type max_size() const;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevini nesne denetleyebilirsiniz uzun sırası uzunluğunu döndürür.  
  
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
  
##  <a name="op_eq"></a>unordered_set::operator =  
 Bir karma tabloya kopyalar.  
  
```  
unordered_set& operator=(const unordered_set& right);

unordered_set& operator=(unordered_set&& right);
```  
  
### <a name="parameters"></a>Parametreler  
  
|||  
|-|-|  
|Parametre|Açıklama|  
|`right`|[Unordered_set](../standard-library/unordered-set-class.md) içine kopyalanmasını `unordered_set`.|  
  
### <a name="remarks"></a>Açıklamalar  
 Var olan öğeleri silindikten sonra bir `unordered_set`, `operator=` kopyalar ya da içeriğini taşır `right` içine `unordered_set`.  
  
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
  
##  <a name="pointer"></a>unordered_set::pointer  
 Bir öğe için bir işaretçi türü.  
  
```  
typedef Alloc::pointer pointer;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Denetimli dizi bir öğe için bir işaretçi olarak hizmet verebilir bir nesne türünü tanımlar.  
  
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
      
    // display contents " [c] [b] [a]"  
    for (Myset::iterator it = c1.begin(); it != c1.end(); ++it)  
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
  
##  <a name="reference"></a>unordered_set::Reference  
 Bir öğe için bir başvuru türü.  
  
```  
typedef Alloc::reference reference;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Öğenin denetimli sırasının bir başvuru olarak hizmet verebilir bir nesne türünü tanımlar.  
  
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
      
    // display contents " [c] [b] [a]"  
    for (Myset::iterator it = c1.begin(); it != c1.end(); ++it)  
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
  
##  <a name="rehash"></a>unordered_set::rehash  
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
      
    // display contents " [c] [b] [a]"  
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)  
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
  
##  <a name="size"></a>unordered_set::size  
 Öğe sayısını sayar.  
  
```  
size_type size() const;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevini denetimli sırası uzunluğunu döndürür.  
  
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
      
    // display contents " [c] [b] [a]"  
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)  
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
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)  
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
  
##  <a name="size_type"></a>unordered_set::size_type  
 İki öğe arasındaki işaretsiz bir mesafenin türü.  
  
```  
typedef T2 size_type;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 İşaretsiz tamsayı türünü herhangi denetimli sırası uzunluğu temsil eden bir nesne tanımlar. Bunu açıklanan burada uygulama tanımlı türü eşanlamlısı olarak `T2`.  
  
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
  
##  <a name="swap"></a>unordered_set::Swap  
 İki kapsayıcının içeriğinin yerini değiştirir.  
  
```  
void swap(unordered_set& right);
```  
  
### <a name="parameters"></a>Parametreler  
 `right`  
 İle değiştirme kapsayıcı.  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevini denetimli sıraları arasında değiştirir `*this` ve `right`. Varsa [unordered_set::get_allocator](#get_allocator)`() == right.get_allocator()`, bunu sabit sürede yapar, depolanan nitelikler nesne türünün kopyalama sonucunda yalnızca bir özel durum oluşturur `Tr`, ve işaretçileri, hiçbir başvuru geçersiz kılar veya iki denetimli sıraları öğelerinde atamak yineleyiciler. Aksi durumda, iki denetimli sıralarında öğesi atamaları ve oluşturucu çağrıları öğe sayısını orantılı çeşitli gerçekleştirir.  
  
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
      
    // display contents " [c] [b] [a]"  
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)  
        std::cout << " [" << *it << "]";  
    std::cout << std::endl;  
      
    Myset c2;  
      
    c2.insert('d');  
    c2.insert('e');  
    c2.insert('f');  
      
    c1.swap(c2);  
      
    // display contents " [f] [e] [d]"  
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)  
        std::cout << " [" << *it << "]";  
    std::cout << std::endl;  
      
    swap(c1, c2);  
      
    // display contents " [c] [b] [a]"  
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)  
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
  
##  <a name="unordered_set"></a>unordered_set::unordered_set  
 Bir kapsayıcı nesnesi oluşturur.  
  
```  
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
  
|||  
|-|-|  
|Parametre|Açıklama|  
|`InputIterator`|Yineleyici türü.|  
|`Al`|Depolanacak ayırıcı nesne.|  
|`Comp`|Depolanacak karşılaştırma işlevi nesnesi.|  
|`Hash`|Depolanacak karma işlev nesnesi.|  
|`bucket_count`|En düşük demet sayısı.|  
|`Right`|Kopyalanacak kapsayıcı.|  
|`IList`|Kopyalanacak öğe içeren initializer_list.|  
  
### <a name="remarks"></a>Açıklamalar  
 İlk oluşturucusu tarafından denetlenen sırasının bir kopyasını belirtir `Right`. İkinci oluşturucu boş bir denetlenmiş dizi belirtir. Üçüncü Oluşturucusu taşıyarak sırasının bir kopyasını belirtir `Right` sekizinci oluşturucular aracılığıyla dördüncü bir initializer_list kopyalanacak öğe belirtmek için kullanın. Dokuzuncu Oluşturucusu bir dizi öğesi değerlerini ekler`[first, last)`.  
  
 Ayrıca, tüm oluşturucular çeşitli depolanmış değerleri başlatır. Kopya Oluşturucu için değerleri alanından elde edilen `Right`. Aksi durumda:.  
  
 Bağımsız değişken demet sayısı alt sınırı: `bucket_count`, yoksa açıklanan varsayılan bir değer olup olmadığını burada uygulama tanımlı bir değer olarak `N0`.  
  
 Bağımsız değişken karma işlev nesnesidir `Hash`, yoksa bu olup olmadığını `Hash()`.  
  
 Karşılaştırma işlevi bağımsız değişken nesnesidir `Comp`, yoksa bu olup olmadığını `Comp()`.  
  
 Bağımsız değişken ayırıcısı nesnesidir `Al`, mevcut; Aksi takdirde bu olup olmadığını `Alloc()`.  
  
##  <a name="value_type"></a>unordered_set::value_type  
 Öğenin türü.  
  
```  
typedef Key value_type;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Öğenin denetimli dizisinin türünü tanımlar.  
  
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
      
    // display contents " [c] [b] [a]"  
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)  
        std::cout << " [" << *it << "]";  
    std::cout << std::endl;  
      
    // add a value and reinspect  
    Myset::key_type key = 'd';  
    Myset::value_type val = key;  
    c1.insert(val);  
      
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)  
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

