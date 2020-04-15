---
title: hash_set Sınıfı
ms.date: 11/04/2016
f1_keywords:
- hash_set/stdext::hash_set
- hash_set/stdext::hash_set::allocator_type
- hash_set/stdext::hash_set::const_iterator
- hash_set/stdext::hash_set::const_pointer
- hash_set/stdext::hash_set::const_reference
- hash_set/stdext::hash_set::const_reverse_iterator
- hash_set/stdext::hash_set::difference_type
- hash_set/stdext::hash_set::iterator
- hash_set/stdext::hash_set::key_compare
- hash_set/stdext::hash_set::key_type
- hash_set/stdext::hash_set::pointer
- hash_set/stdext::hash_set::reference
- hash_set/stdext::hash_set::reverse_iterator
- hash_set/stdext::hash_set::size_type
- hash_set/stdext::hash_set::value_compare
- hash_set/stdext::hash_set::value_type
- hash_set/stdext::hash_set::begin
- hash_set/stdext::hash_set::cbegin
- hash_set/stdext::hash_set::cend
- hash_set/stdext::hash_set::clear
- hash_set/stdext::hash_set::count
- hash_set/stdext::hash_set::crbegin
- hash_set/stdext::hash_set::crend
- hash_set/stdext::hash_set::emplace
- hash_set/stdext::hash_set::emplace_hint
- hash_set/stdext::hash_set::empty
- hash_set/stdext::hash_set::end
- hash_set/stdext::hash_set::equal_range
- hash_set/stdext::hash_set::erase
- hash_set/stdext::hash_set::find
- hash_set/stdext::hash_set::get_allocator
- hash_set/stdext::hash_set::insert
- hash_set/stdext::hash_set::key_comp
- hash_set/stdext::hash_set::lower_bound
- hash_set/stdext::hash_set::max_size
- hash_set/stdext::hash_set::rbegin
- hash_set/stdext::hash_set::rend
- hash_set/stdext::hash_set::size
- hash_set/stdext::hash_set::swap
- hash_set/stdext::hash_set::upper_bound
- hash_set/stdext::hash_set::value_comp
helpviewer_keywords:
- stdext::hash_set
- stdext::hash_set::allocator_type
- stdext::hash_set::const_iterator
- stdext::hash_set::const_pointer
- stdext::hash_set::const_reference
- stdext::hash_set::const_reverse_iterator
- stdext::hash_set::difference_type
- stdext::hash_set::iterator
- stdext::hash_set::key_compare
- stdext::hash_set::key_type
- stdext::hash_set::pointer
- stdext::hash_set::reference
- stdext::hash_set::reverse_iterator
- stdext::hash_set::size_type
- stdext::hash_set::value_compare
- stdext::hash_set::value_type
- stdext::hash_set::begin
- stdext::hash_set::cbegin
- stdext::hash_set::cend
- stdext::hash_set::clear
- stdext::hash_set::count
- stdext::hash_set::crbegin
- stdext::hash_set::crend
- stdext::hash_set::emplace
- stdext::hash_set::emplace_hint
- stdext::hash_set::empty
- stdext::hash_set::end
- stdext::hash_set::equal_range
- stdext::hash_set::erase
- stdext::hash_set::find
- stdext::hash_set::get_allocator
- stdext::hash_set::insert
- stdext::hash_set::key_comp
- stdext::hash_set::lower_bound
- stdext::hash_set::max_size
- stdext::hash_set::rbegin
- stdext::hash_set::rend
- stdext::hash_set::size
- stdext::hash_set::swap
- stdext::hash_set::upper_bound
- stdext::hash_set::value_comp
ms.assetid: c765c06e-cbb6-48c2-93ca-d15468eb28d7
ms.openlocfilehash: 3bf4065b4c409e1baad3183cc8ccbd8c97d43d5e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370598"
---
# <a name="hash_set-class"></a>hash_set Sınıfı

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set Sınıf](../standard-library/unordered-set-class.md).

Kapsayıcı sınıfı hash_set C++ Standart Kitaplığı'nın bir uzantısıdır ve içerdiği öğelerin değerlerinin benzersiz olduğu ve anahtar değerler olarak hizmet ettiği bir koleksiyondan veri depolama ve hızlı bir şekilde alınması için kullanılır.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Key,
    class Traits=hash_compare<Key, less<Key>>,
    class Allocator=allocator<Key>>
class hash_set
```

### <a name="parameters"></a>Parametreler

*Anahtar*\
hash_set depolanacak öğe veri türü.

*Özellik*\
İki işlev nesnesi içeren tür, bir sınıf karşılaştırması ikili yüklem iki öğe değeri göreli sıralarını belirlemek için sıra anahtarları ve tür imzasız tamsayılar `size_t`için öğelerin unary yüklem eşleme anahtar değerleri olan bir karma işlevi karşılaştırmak mümkün . Bu bağımsız değişken isteğe bağlıdır ve varsayılan `hash_compare<Key, less<Key> >` değerdir.

*Ayırıcı*\
hash_set ayırma ve bellek ayırma ile ilgili ayrıntıları kapsülleyen depolanan ayırıcı nesneyi temsil eden tür. Bu bağımsız değişken isteğe bağlıdır `allocator<Key>`ve varsayılan değer .

## <a name="remarks"></a>Açıklamalar

hash_set:

- İlişkili bir anahtar değerine dayalı öğe değerlerinin verimli alınmasını destekleyen bir değişken boyutu kapsayıcı olan ilişkilendirilebilir bir kapsayıcı. Dahası, basit bir ilişkilendirilebilir kapsayıcıdır, çünkü öğelerinin değerleri kendi anahtar değerleridir.

- Çift yönlüdür, çünkü öğelerine erişmek için çift yönlü bir yineleyici sağlar.

- Karma, çünkü elemanları, öğelerin temel değerlerine uygulanan karma işlevin değerine göre kovalar halinde gruplandırılır.

- Benzersizdir, çünkü öğelerinin her birinde benzersiz bir anahtar olması gerekir. hash_set aynı zamanda basit bir ilişkili kapsayıcı olduğundan, öğeleri de benzersizdir.

- Sağladığı işlevsellik genel olduğundan ve öğe veya anahtar olarak bulunan belirli veri türünden bağımsız olduğundan sınıf şablonu. Öğeler ve anahtarlar için kullanılacak veri türleri, karşılaştırma işlevi ve ayırıcı ile birlikte bir sınıf şablonunda parametreler olarak belirtilir.

Sıralama üzerinde karma temel avantajı daha fazla verimlilik; başarılı bir karma eklemeler, silmeler gerçekleştirir ve sıralama teknikleri için kapsayıcıdaki eleman sayısının logaritma ile orantılı bir süre ile karşılaştırıldığında sabit ortalama zaman bulur. Bir kümedeki bir öğenin değeri doğrudan değiştirilemez. Bunun yerine, eski değerleri silmeniz ve yeni değerlere sahip öğeler eklemeniz gerekir.

Kapsayıcı türünün seçimi genelde uygulamanın gerektirdiği arama ve ekleme türüne dayalı olmalıdır. Haşdi hashed musociative kaplar arama, ekleme ve kaldırma işlemleri için optimize edilmiştir. Bu işlemleri açıkça destekleyen üye işlevler, iyi tasarlanmış bir karma işlevle kullanıldığında verimlidir ve bunları ortalama sabit olan ve kapsayıcıdaki öğe sayısına bağlı olmayan bir zamanda gerçekleştirir. İyi tasarlanmış karma işlev karma değerlerin tek tip dağılımını üretir ve farklı anahtar değerleri aynı karma değere eşlendiğinde çakışacağı söylenen çarpışma sayısını en aza indirir. En kötü durumda, mümkün olan en kötü karma işlevi ile, işlem sayısı dizideki eleman sayısıyla (doğrusal zaman) orantılıdır.

Hash_set, değerleri anahtarlarıyla ilişkilendiren koşullar uygulama tarafından karşılandığında tercih edilen ilişkisel kapsayıcı olmalıdır. bir hash_set öğeleri benzersizdir ve kendi sıralama anahtarları olarak hizmet vermektedir. Bu tür bir yapı modeli, sözcüklerin yalnızca bir defa geçebildiği sıralı bir sözcükler listesindedir. Sözcüklerin birden çok oluşumuna izin verilirse, hash_multiset uygun kapsayıcı yapısı olacaktır. Değerlerin benzersiz anahtar sözcükler listesine eklenmesi gerekiyorsa, hash_map bu verileri içerecek uygun bir yapı olacaktır. Bunun yerine anahtarlar benzersiz değilse, hash_multimap tercih edilen kapsayıcı olacaktır.

hash_set, denetlediği sırayı, value_compare türündeki depolanmış karma `Traits` nesneyi çağırarak sıralar. [value_compare](#value_compare) Bu depolanan nesneye üye işlev [key_comp](#key_comp)çağırılarak erişilebilir. Böyle bir işlev nesnesi sınıf hash_compare *<Anahtarı,\<daha az Anahtar> >* bir nesne olarak aynı şekilde olmalıdır. Özellikle, tip `key` Anahtar'ın tüm değerleri için, Özellik (`key`) türü size_t değerlerinin dağılımını verir.

Genelde, bu sıralamayı oluşturmak için öğelerin yalnızca küçüktür biçiminde karşılaştırılabilir olması gerekir; böylece, herhangi iki öğe belirtildiğinde, eşit oldukları (yani birinin diğerinden daha küçük olmadığı anlamında) veya birinin diğerinden küçük olduğu belirlenebilir. Bu, eşdeğer olmayan öğeler arasında bir sıralama ile sonuçlanır. Daha teknik bir not üzerinde, karşılaştırma işlevi standart matematiksel anlamda katı bir zayıf sıralama sevk eden ikili bir koşuldur. İkili yüklem *f*( *x*, *y*) iki bağımsız değişken nesnesi x ve y ve doğru veya yanlışın dönüş değeri olan bir işlev nesnesidir. Bir hash_set uygulanan bir sıralama, ikili yüklem inreflexive, antisimetrik ve geçişli ve eşdeğerlik geçişli ise, iki nesne *x* ve *y* hem *f*( *x*, *y*) ve *f*( *y*, *x*) yanlış olduğunda eşdeğer olarak tanımlanır sıkı bir zayıf sıralamadır. Anahtarlar arasındaki eşitliğinin daha güçlü koşulu bu denkliğin yerini alırsa, sıralama (içindeki tüm öğelerin birbirine göre sıralanması anlamında) toplam haline gelir ve eşleşen anahtarlar birbirinden ayırt edilemez olacaktır.

Denetlenmiş dizideki öğelerin gerçek sırası karma işlevine, sıralama işlevine ve kapsayıcı nesnesinde depolanan karma tablonun geçerli boyutuna bağlıdır. Karma tablonun geçerli boyutunu belirleyemezsiniz, bu nedenle genel olarak denetitilen dizideki öğelerin sırasını tahmin edemezsiniz. Öğelerin eklenmesi hiçbir yineleyiciyi geçersiz kılmaz; öğelerin kaldırılması yalnızca özellikle kaldırılan öğeleri gösteren yineleyicileri geçersiz kılar.

hash_set sınıfı tarafından sağlanan yineleme çift yönlü bir yinelemedir, ancak sınıf üye işlevleri [şablon](#insert) parametreleri olarak alan sürümlere [sahip](#hash_set) hash_set, işlevsellik gereksinimleri çift yönlü yineleyiciler sınıfı tarafından garanti edilenden daha az olan daha zayıf bir giriş yineleyicisi alır. Farklı yineleyici kavramları, işlevselliklerindeki iyileştirmelere göre ilgili bir aile biçimlendirir. Her yineleyici kavramının kendi gereksinimler kümesi vardır ve bunlarla çalışan algoritmaların kendi varsayımlarını yineleyici türü tarafından sağlanan gereksinimlerle sınırlaması gerekir. Bir giriş yineleyicinin bazı nesnelere başvurusunun kaldırılacağı ve dizideki sonraki yineleyiciye artırılabileceği varsayılabilir. Bu en az işlevsellik kümesidir, ancak sınıf üye işlevleri bağlamında bir dizi `first`yineleyici [, `last`) hakkında anlamlı bir şekilde konuşabilmek yeterlidir.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[Hash_set](#hash_set)|Boş olan `hash_set` veya başka `hash_set`bir şeyin tamamının veya bir kısmının kopyası olan bir yapı.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[Allocator_type](#allocator_type)|Nesnenin sınıfını `allocator` `hash_set` temsil eden bir tür.|
|[const_iterator](#const_iterator)|Bir öğeyi okuyabilen çift yönlü bir yineleme `const` sağlayan `hash_set`bir tür.|
|[Const_pointer](#const_pointer)|Bir **const** öğesine işaretçi sağlayan `hash_set`bir tür .|
|[const_reference](#const_reference)|Const **işlemleri** okumak ve gerçekleştirmek için bir `hash_set` **const** öğesinde depolanan bir öğeye başvuru sağlayan bir tür.|
|[Const_reverse_iterator](#const_reverse_iterator)|Herhangi bir const öğeyi okuyabilen çift yönlü bir yineleme sağlayan bir tür. **const** `hash_set`|
|[difference_type](#difference_type)|Yineleyiciler tarafından işaret edilen öğeler arasındaki aralıktaki bir `hash_set` aralığın öğelerinin sayısını temsil etmek için kullanılabilecek imzalı bir tamsayı türü.|
|[Yineleyici](#iterator)|Bir 'deki herhangi bir öğeyi okuyabilen veya değiştirebilen `hash_set`çift yönlü bir yineleme sağlayan bir tür.|
|[Key_compare](#key_compare)|İki öğenin göreli sırasını belirlemek için iki sıralama anahtarını karşılaştırabilen bir işlev nesnesi `hash_set`sağlayan bir tür.|
|[Key_type](#key_type)|Sıralama anahtarı olarak kapasitesinde bir `hash_set` öğe olarak depolanan bir nesneyi açıklayan bir tür.|
|[pointer](#pointer)|Bir öğedeki bir öğeye işaretçi sağlayan bir `hash_set`tür|
|[Başvuru](#reference)|Bir 'de depolanan bir öğeye `hash_set`başvuru sağlayan bir tür|
|[Reverse_iterator](#reverse_iterator)|Ters bir öğedeki bir öğeyi okuyabilen veya değiştirebilen `hash_set`çift yönlü bir yineleme sağlayan bir tür.|
|[size_type](#size_type)|Bir 'deki öğe sayısını temsil eden imzasız `hash_set`bir tamsayı türü|
|[Value_compare](#value_compare)|İki işlev nesnesi sağlayan bir tür, bir sınıf karşılaştırması, göreli `hash_set` düzenlerini belirlemek için a'nın iki öğe değerini ve öğeleri işleyen bir unary yüklemi karşılaştırabilen bir tür.|
|[value_type](#value_type)|Değer olarak kapasitesinde bir `hash_set` öğe olarak depolanan bir nesneyi açıklayan bir tür.|

### <a name="member-functions"></a>Üye işlevler

|Üye fonksiyonu|Açıklama|
|-|-|
|[Başlamak](#begin)|`hash_set`'deki ilk öğeyi ele alan bir yineleyici döndürür.|
|[cbegin](#cbegin)|'deki ilk öğeyi ele alan bir const yineleyici döndürür. `hash_set`|
|[cend](#cend)|Bir `hash_set`'deki son öğeyi yerine getiren konumu gideren bir const yineleyici döndürür.|
|[Temizleyin](#clear)|Bir' `hash_set`nin tüm öğelerini siler.|
|[Sayısı](#count)|Anahtarı parametre yle `hash_set` belirtilen bir anahtarla eşleşen bir öğedeki öğe sayısını döndürür.|
|[crbegin](#crbegin)|Ters bir ilk öğeyi ele alan bir const yineleyici döndürür. `hash_set`|
|[crend](#crend)|Ters bir önceki son öğeyi yerine getiren konumu gideren bir `hash_set`const yineleyici döndürür.|
|[emplace](#emplace)|Yerinde inşa edilmiş bir öğeyi `hash_set`bir .|
|[emplace_hint](#emplace_hint)|Yerinde `hash_set`oluşturulmuş bir öğeyi yerleştirme ipucuyla ekler.|
|[empty](#empty)|A boşsa `hash_set` sınar.|
|[Son -unda](#end)|Bir 'deki son öğeyi yerine getiren konumu adresleyen `hash_set`bir yineleyici döndürür.|
|[equal_range](#equal_range)|Belirtilen bir anahtardan büyük bir `hash_set` anahtarla bir ilk öğeye ve anahtara eşit veya daha `hash_set` büyük bir anahtarla ilk öğeye sırasıyla bir çift yineleyici döndürür.|
|[Silmek](#erase)|Belirtilen konumlardaki `hash_set` bir öğeyi veya bir dizi öğeyi kaldırır veya belirtilen anahtarla eşleşen öğeleri kaldırır.|
|[find](#find)|Belirtilen bir anahtara eşdeğer anahtara sahip bir `hash_set` öğedeki öğenin konumunu ele alan bir yineleyici döndürür.|
|[Get_allocator](#get_allocator)|Oluşturmak için kullanılan `allocator` nesnenin bir `hash_set`kopyasını döndürür.|
|[Ekle](#insert)|Bir öğeye veya bir dizi öğeye `hash_set`bir öğe ekler.|
|[Key_comp](#key_comp)|Bir `hash_set`'deki anahtarları sipariş etmek için kullanılan karşılaştırma nesnesinin bir kopyasını alır.|
|[lower_bound](#lower_bound)|Bir yineleyiciyi, belirtilen bir anahtara eşit veya daha büyük bir `hash_set` anahtarla bir ilk öğeye döndürür.|
|[max_size](#max_size)|Maksimum uzunluğu `hash_set`verir.|
|[rbegin](#rbegin)|Ters bir ilk öğeyi ele alan bir `hash_set`yineleyici döndürür.|
|[Rend](#rend)|Ters çevrilmiş bir son öğedeki son öğeyi yerine `hash_set`getiren konumu adresleyen bir yineleyici döndürür.|
|[Boyutu](#size)|`hash_set`'deki öğe sayısını verir.|
|[Takas](#swap)|İki `hash_set`s'nin öğelerini değiştirir.|
|[upper_bound](#upper_bound)|Bir yineleyiciyi, belirtilen bir anahtara eşit veya daha büyük bir anahtarla bir ilk öğeye `hash_set` döndürür.|
|[value_comp](#value_comp)|Karma ve sipariş öğesi anahtar değerlerini bir `hash_set`' de karma ve sipariş etmek için kullanılan karma özellikleri nesnesinin bir kopyasını alır.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[hash_set::operator=](#op_eq)|Bir `hash_set` öğenin öğelerini başka `hash_set`bir kopyayla değiştirir.|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** \<hash_set>

**Ad alanı:** stdext

## <a name="hash_setallocator_type"></a><a name="allocator_type"></a>hash_set:allocator_type

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set Sınıf](../standard-library/unordered-set-class.md).

hash_set nesnesinin ayırıcı sınıfını temsil eden bir tür.

```cpp
typedef list<typename Traits::value_type, typename Traits::allocator_type>::allocator_type allocator_type;
```

### <a name="remarks"></a>Açıklamalar

`allocator_type`şablon parametre *Ayırıcısı*ile eş anlamlıdır.

*Allocator*hakkında daha fazla bilgi için [hash_set Sınıfı](../standard-library/hash-set-class.md) konusunun Açıklamalar bölümüne bakın.

### <a name="example"></a>Örnek

Kullanan `allocator_type`bir örnek için [get_allocator](#get_allocator) örneğine bakın.

## <a name="hash_setbegin"></a><a name="begin"></a>hash_set::başla

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set Sınıf](../standard-library/unordered-set-class.md).

hash_set ilk öğeyi ele alan bir yineleyici döndürür.

```cpp
const_iterator begin() const;

iterator begin();
```

### <a name="return-value"></a>Dönüş Değeri

hash_set'daki ilk öğeyi veya boş bir hash_set yerine gelen konumu ele alan çift yönlü bir yineleyici.

### <a name="remarks"></a>Açıklamalar

`begin` Bir `const_iterator`, hash_set nesnesindeki öğelere atanırsa değiştirilemez. Bir `begin` `iterator`, hash_set nesnesindeki öğelere atanırsa değiştirilebilir.

### <a name="example"></a>Örnek

```cpp
// hash_set_begin.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_set <int> hs1;
   hash_set <int>::iterator hs1_Iter;
   hash_set <int>::const_iterator hs1_cIter;

   hs1.insert( 1 );
   hs1.insert( 2 );
   hs1.insert( 3 );

   hs1_Iter = hs1.begin( );
   cout << "The first element of hs1 is " << *hs1_Iter << endl;

   hs1_Iter = hs1.begin( );
   hs1.erase( hs1_Iter );

   // The following 2 lines would err because the iterator is const
   // hs1_cIter = hs1.begin( );
   // hs1.erase( hs1_cIter );

   hs1_cIter = hs1.begin( );
   cout << "The first element of hs1 is now " << *hs1_cIter << endl;
}
```

```Output
The first element of hs1 is 1
The first element of hs1 is now 2
```

## <a name="hash_setcbegin"></a><a name="cbegin"></a>hash_set::cbegin

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set Sınıf](../standard-library/unordered-set-class.md).

hash_set ilk öğeyi ele alan bir const yineleyici döndürür.

```cpp
const_iterator cbegin() const;
```

### <a name="return-value"></a>Dönüş Değeri

[hash_set'daki](../standard-library/hash-set-class.md) ilk öğeyi veya boş `hash_set`bir konumdan sonra gelen bir konst çift yönlü yineleme.

### <a name="remarks"></a>Açıklamalar

Geri dönüş değeri `cbegin`ile nesnedeki `hash_set` öğeler değiştirilemez.

### <a name="example"></a>Örnek

```cpp
// hash_set_cbegin.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_set <int> hs1;
   hash_set <int>::const_iterator hs1_cIter;

   hs1.insert( 1 );
   hs1.insert( 2 );
   hs1.insert( 3 );

   hs1_cIter = hs1.cbegin( );
   cout << "The first element of hs1 is " << *hs1_cIter << endl;
}
```

```Output
The first element of hs1 is 1
```

## <a name="hash_setcend"></a><a name="cend"></a>hash_set::cend

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set Sınıf](../standard-library/unordered-set-class.md).

Bir hash_set son öğesini yerine getiren konumu gideren bir const yineleyici döndürür.

```cpp
const_iterator cend() const;
```

### <a name="return-value"></a>Dönüş Değeri

[Bir hash_set](../standard-library/hash-set-class.md)son öğesini yerine getiren konumu gideren bir konst çift yönlü yineleme. Eğer `hash_set` boşsa, `hash_set::cend == hash_set::begin`o zaman.

### <a name="remarks"></a>Açıklamalar

`cend`bir yineleyicinin sonuna ulaşıp ulaşmadığını test `hash_set`etmek için kullanılır. Döndürülen `cend` değer dereferenced olmamalıdır.

### <a name="example"></a>Örnek

```cpp
// hash_set_cend.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_set <int> hs1;
   hash_set <int> :: const_iterator hs1_cIter;

   hs1.insert( 1 );
   hs1.insert( 2 );
   hs1.insert( 3 );

   hs1_cIter = hs1.cend( );
   hs1_cIter--;
   cout << "The last element of hs1 is " << *hs1_cIter << endl;
}
```

```Output
The last element of hs1 is 3
```

## <a name="hash_setclear"></a><a name="clear"></a>hash_set::açık

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set Sınıf](../standard-library/unordered-set-class.md).

Bir hash_set tüm öğelerini siler.

```cpp
void clear();
```

### <a name="remarks"></a>Açıklamalar

### <a name="example"></a>Örnek

```cpp
// hash_set_clear.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_set <int> hs1;

   hs1.insert( 1 );
   hs1.insert( 2 );

   cout << "The size of the hash_set is initially " << hs1.size( )
        << "." << endl;

   hs1.clear( );
   cout << "The size of the hash_set after clearing is "
        << hs1.size( ) << "." << endl;
}
```

```Output
The size of the hash_set is initially 2.
The size of the hash_set after clearing is 0.
```

## <a name="hash_setconst_iterator"></a><a name="const_iterator"></a>hash_set:const_iterator

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set Sınıf](../standard-library/unordered-set-class.md).

hash_set bir **const** öğeyi okuyabilen çift yönlü bir yineleme sağlayan bir tür.

```cpp
typedef list<typename Traits::value_type, typename Traits::allocator_type>::const_iterator const_iterator;
```

### <a name="remarks"></a>Açıklamalar

Bir `const_iterator` tür, bir öğenin değerini değiştirmek için kullanılamaz.

### <a name="example"></a>Örnek

Kullanan `const_iterator`bir örnek için [başlangıç](#begin) örneği bakın.

## <a name="hash_setconst_pointer"></a><a name="const_pointer"></a>hash_set:const_pointer

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set Sınıf](../standard-library/unordered-set-class.md).

hash_set bir **const** öğesine işaretçi sağlayan bir tür.

```cpp
typedef list<typename Traits::value_type, typename Traits::allocator_type>::const_pointer const_pointer;
```

### <a name="remarks"></a>Açıklamalar

Bir `const_pointer` tür, bir öğenin değerini değiştirmek için kullanılamaz.

Çoğu durumda, bir [const_iterator](#const_iterator) **bir const** hash_set nesnesindeki öğelere erişmek için kullanılmalıdır.

## <a name="hash_setconst_reference"></a><a name="const_reference"></a>hash_set:const_reference

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set Sınıf](../standard-library/unordered-set-class.md).

**Const** işlemleri okumak ve gerçekleştirmek için hash_set depolanan **bir const** öğesine başvuru sağlayan bir tür.

```cpp
typedef list<typename Traits::value_type, typename Traits::allocator_type>::const_reference const_reference;
```

### <a name="remarks"></a>Açıklamalar

### <a name="example"></a>Örnek

```cpp
// hash_set_const_ref.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_set <int> hs1;

   hs1.insert( 10 );
   hs1.insert( 20 );

   // Declare and initialize a const_reference &Ref1
   // to the 1st element
   const int &Ref1 = *hs1.begin( );

   cout << "The first element in the hash_set is "
        << Ref1 << "." << endl;

   // The following line would cause an error because the
   // const_reference cannot be used to modify the hash_set
   // Ref1 = Ref1 + 5;
}
```

```Output
The first element in the hash_set is 10.
```

## <a name="hash_setconst_reverse_iterator"></a><a name="const_reverse_iterator"></a>hash_set:const_reverse_iterator

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set Sınıf](../standard-library/unordered-set-class.md).

hash_set herhangi bir **const** öğeyi okuyabilen çift yönlü bir yineleme sağlayan bir tür.

```cpp
typedef list<typename Traits::value_type, typename Traits::allocator_type>::const_reverse_iterator const_reverse_iterator;
```

### <a name="remarks"></a>Açıklamalar

Bir `const_reverse_iterator` tür bir öğenin değerini değiştiremez ve hash_set ters olarak yinelemek için kullanılır.

### <a name="example"></a>Örnek

Nasıl beyan edilip kullanılacağına bir örnek için [rend](#rend) örneğine bakın`const_reverse_iterator`

## <a name="hash_setcount"></a><a name="count"></a>hash_set::say

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set Sınıf](../standard-library/unordered-set-class.md).

Anahtarı parametre yle belirtilen anahtarla eşleşen bir hash_set öğe sayısını verir.

```cpp
size_type count(const Key& key) const;
```

### <a name="parameters"></a>Parametreler

*Anahtar*\
hash_set eşleşecek öğelerin anahtarı.

### <a name="return-value"></a>Dönüş Değeri

1 hash_set, sıralama anahtarı parametre anahtarıyla eşleşen bir öğe içeriyorsa.

0 hash_set eşleşen bir anahtar ile bir öğe içermiyorsa.

### <a name="remarks"></a>Açıklamalar

Üye işlev aşağıdaki aralıktaki eleman sayısını döndürür:

\[lower_bound *(anahtar),* upper_bound *(anahtar)*).

### <a name="example"></a>Örnek

Aşağıdaki örnek, hash_set::count üye işlevinin kullanımını göstermektedir.

```cpp
// hash_set_count.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
    using namespace std;
    using namespace stdext;
    hash_set<int> hs1;
    hash_set<int>::size_type i;

    hs1.insert(1);
    hs1.insert(1);

    // Keys must be unique in hash_set, so duplicates are ignored.
    i = hs1.count(1);
    cout << "The number of elements in hs1 with a sort key of 1 is: "
         << i << "." << endl;

    i = hs1.count(2);
    cout << "The number of elements in hs1 with a sort key of 2 is: "
         << i << "." << endl;
}
```

```Output
The number of elements in hs1 with a sort key of 1 is: 1.
The number of elements in hs1 with a sort key of 2 is: 0.
```

## <a name="hash_setcrbegin"></a><a name="crbegin"></a>hash_set::crbegin

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set Sınıf](../standard-library/unordered-set-class.md).

Ters hash_set ilk öğeyi ele alan bir const yineleyici döndürür.

```cpp
const_reverse_iterator crbegin() const;
```

### <a name="return-value"></a>Dönüş Değeri

Ters [hash_set](../standard-library/hash-set-class.md) ilk öğeyi ele alan veya ters çevrilmemiş `hash_set`son öğeyi ele alan const ters çift yönlü bir yineleme.

### <a name="remarks"></a>Açıklamalar

`crbegin`hash_set gibi ters hash_set ile [kullanılır::begin](#begin) bir hash_set ile kullanılır.

İade değeri ile `crbegin` `hash_set` nesne değiştirilemez.

`crbegin``hash_set` geriye doğru doğrulamak için kullanılabilir.

### <a name="example"></a>Örnek

```cpp
// hash_set_crbegin.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_set <int> hs1;
   hash_set <int>::const_reverse_iterator hs1_crIter;

   hs1.insert( 10 );
   hs1.insert( 20 );
   hs1.insert( 30 );

   hs1_crIter = hs1.crbegin( );
   cout << "The first element in the reversed hash_set is "
        << *hs1_crIter << "." << endl;
}
```

```Output
The first element in the reversed hash_set is 30.
```

## <a name="hash_setcrend"></a><a name="crend"></a>hash_set::crend

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set Sınıf](../standard-library/unordered-set-class.md).

Ters hash_set son öğeyi yerine getiren konumu gideren bir const yineleyici döndürür.

```cpp
const_reverse_iterator crend() const;
```

### <a name="return-value"></a>Dönüş Değeri

Ters [hash_set](../standard-library/hash-set-class.md) 'deki son öğeyi başaran konumu (ters çevrilmemiş `hash_set`ilk öğeden önce gelen konum) gideren const ters çift yönlü bir yineleme.

### <a name="remarks"></a>Açıklamalar

`crend`hash_set gibi ters `hash_set` bir ile [kullanılır::end](#end) `hash_set`ile kullanılır .

İade değeri ile `crend` `hash_set` nesne değiştirilemez.

`crend`ters yineleyicinin sonuna ulaşıp ulaşmadığını test etmek için `hash_set`kullanılabilir.

### <a name="example"></a>Örnek

```cpp
// hash_set_crend.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_set <int> hs1;
   hash_set <int>::const_reverse_iterator hs1_crIter;

   hs1.insert( 10 );
   hs1.insert( 20 );
   hs1.insert( 30 );

   hs1_crIter = hs1.crend( );
   hs1_crIter--;
   cout << "The last element in the reversed hash_set is "
        << *hs1_crIter << "." << endl;
}
```

```Output
The last element in the reversed hash_set is 10.
```

## <a name="hash_setdifference_type"></a><a name="difference_type"></a>hash_set::difference_type

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set Sınıf](../standard-library/unordered-set-class.md).

Yineleyiciler tarafından işaret edilen öğeler arasındaki aralıkta bir hash_set öğelerinin sayısını temsil etmek için kullanılabilecek imzalı bir tamsayı türü.

```cpp
typedef list<typename Traits::value_type, typename Traits::allocator_type>::difference_type difference_type;
```

### <a name="remarks"></a>Açıklamalar

Kapsayıcının `difference_type` yineleyicileri arasından çıkarılırken veya artarken döndürülen türdür. Genellikle `difference_type` yinelemeciler `first` arasındaki aralıktaki öğe sayısını temsil `first` `last`etmek için kullanılır [ `last`, ) ve `first` , tarafından işaret edilen öğe ve elemanların aralığı kadar, ancak dahil değil, öğe tarafından `last`işaret .

Küme gibi `difference_type` geri döndürülebilir kapsayıcılar tarafından desteklenen çift yönlü yinelemeler sınıfını içeren bir giriş yineleyicisinin gereksinimlerini karşılayan tüm yineleyiciler için kullanılabilir olmasına rağmen, yineleyiciler arasındaki çıkarma yalnızca vektör veya deque gibi rasgele erişim li yinelemeler tarafından sağlanan rasgele erişim yinelemeleri tarafından desteklenir.

### <a name="example"></a>Örnek

```cpp
// hash_set_diff_type.cpp
// compile with: /EHsc
#include <iostream>
#include <hash_set>
#include <algorithm>

int main( )
{
   using namespace std;
   using namespace stdext;

   hash_set <int> hs1;
   hash_set <int>::iterator hs1_Iter, hs1_bIter, hs1_eIter;

   hs1.insert( 20 );
   hs1.insert( 10 );
   hs1.insert( 20 );   // Won't insert as hash_set elements are unique

   hs1_bIter = hs1.begin( );
   hs1_eIter = hs1.end( );

   hash_set <int>::difference_type   df_typ5, df_typ10, df_typ20;

   df_typ5 = count( hs1_bIter, hs1_eIter, 5 );
   df_typ10 = count( hs1_bIter, hs1_eIter, 10 );
   df_typ20 = count( hs1_bIter, hs1_eIter, 20 );

   // The keys, and hence the elements, of a hash_set are unique,
   // so there is at most one of a given value
   cout << "The number '5' occurs " << df_typ5
        << " times in hash_set hs1.\n";
   cout << "The number '10' occurs " << df_typ10
        << " times in hash_set hs1.\n";
   cout << "The number '20' occurs " << df_typ20
        << " times in hash_set hs1.\n";

   // Count the number of elements in a hash_set
   hash_set <int>::difference_type  df_count = 0;
   hs1_Iter = hs1.begin( );
   while ( hs1_Iter != hs1_eIter)
   {
      df_count++;
      hs1_Iter++;
   }

   cout << "The number of elements in the hash_set hs1 is: "
        << df_count << "." << endl;
}
```

```Output
The number '5' occurs 0 times in hash_set hs1.
The number '10' occurs 1 times in hash_set hs1.
The number '20' occurs 1 times in hash_set hs1.
The number of elements in the hash_set hs1 is: 2.
```

## <a name="hash_setemplace"></a><a name="emplace"></a>hash_set::emplace

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set Sınıf](../standard-library/unordered-set-class.md).

Yerinde inşa edilmiş bir öğeyi hash_set ekler.

```cpp
template <class ValTy>
pair <iterator, bool>
emplace(
    ValTy&& val);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|-|-|
|*Val*|Zaten bu öğeyi veya daha genel [hash_set](../standard-library/hash-set-class.md) olarak, `hash_set` anahtarı eşdeğer sıralanmış bir öğeyi içermediği sürece hash_set eklenecek bir öğenin değeri.|

### <a name="return-value"></a>Dönüş Değeri

Üye `emplace` işlev, ekleme yapıldıysa **bool** bileşeni **doğru** döndürücü ve anahtar `hash_set` siparişte eşdeğer değere sahip bir öğe içeriyorsa ve yineleme bileşeni yeni bir öğenin eklendiği veya öğenin bulunduğu adresi döndürürse, **bir** çift döndürür.

### <a name="remarks"></a>Açıklamalar

### <a name="example"></a>Örnek

```cpp
// hash_set_emplace.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>
#include <string>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_set<string> hs3;
   string str1("a");

   hs3.emplace(move(str1));
   cout << "After the emplace insertion, hs3 contains "
      << *hs3.begin() << "." << endl;
}
```

```Output
After the emplace insertion, hs3 contains a.
```

## <a name="hash_setemplace_hint"></a><a name="emplace_hint"></a>hash_set:emplace_hint

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set Sınıf](../standard-library/unordered-set-class.md).

Yerinde inşa edilmiş bir öğeyi hash_set ekler.

```cpp
template <class ValTy>
iterator emplace(
    const_iterator _Where,
    ValTy&& val);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|-|-|
|*Val*|Zaten bu öğeyi veya daha genel [hash_set](../standard-library/hash-set-class.md) olarak, `hash_set` anahtarı eşdeğer sıralanmış bir öğeyi içermediği sürece hash_set eklenecek bir öğenin değeri.|
|*_Where*|Doğru ekleme noktasını aramaya başlamak için yer. (Ekleme noktası hemen *_Where*takip ederse, logaritmik zaman yerine, amortismana tabi sabit zaman oluşabilir .)|

### <a name="return-value"></a>Dönüş Değeri

[hash_set::emplace](#emplace) üye işlevi, yeni öğenin eklendiği `hash_set`veya eşdeğer sıralamaya sahip varolan öğenin bulunduğu konumu gösteren bir yineleyici döndürür.

### <a name="remarks"></a>Açıklamalar

Ekleme noktası hemen *_Where*takip ederse, logaritmik zaman yerine, amortismana tabi sabit zaman oluşabilir.

### <a name="example"></a>Örnek

```cpp
// hash_set_emplace_hint.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>
#include <string>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_set<string> hs3;
   string str1("a");

   hs3.insert(hs3.begin(), move(str1));
   cout << "After the emplace insertion, hs3 contains "
      << *hs3.begin() << "." << endl;
}
```

```Output
After the emplace insertion, hs3 contains a.
```

## <a name="hash_setempty"></a><a name="empty"></a>hash_set::boş

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set Sınıf](../standard-library/unordered-set-class.md).

bir hash_set boş olup olmadığını sınar.

```cpp
bool empty() const;
```

### <a name="return-value"></a>Dönüş Değeri

hash_set boşsa **doğrudur;** hash_set boş değilse **yanlış.**

### <a name="remarks"></a>Açıklamalar

### <a name="example"></a>Örnek

```cpp
// hash_set_empty.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_set <int> hs1, hs2;
   hs1.insert ( 1 );

   if ( hs1.empty( ) )
      cout << "The hash_set hs1 is empty." << endl;
   else
      cout << "The hash_set hs1 is not empty." << endl;

   if ( hs2.empty( ) )
      cout << "The hash_set hs2 is empty." << endl;
   else
      cout << "The hash_set hs2 is not empty." << endl;
}
```

```Output
The hash_set hs1 is not empty.
The hash_set hs2 is empty.
```

## <a name="hash_setend"></a><a name="end"></a>hash_set::sonu

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set Sınıf](../standard-library/unordered-set-class.md).

hash_set son öğesini yerine getiren konumu adresleyen bir yineleyici döndürür.

```cpp
const_iterator end() const;

iterator end();
```

### <a name="return-value"></a>Dönüş Değeri

Bir hash_set son öğesini yerine getiren konumu ele alan çift yönlü bir yineleyici. hash_set boşsa, hash_set::end == hash_set::begin.

### <a name="remarks"></a>Açıklamalar

`end`bir yineleyicinin hash_set sonuna ulaşıp ulaşmadığını test etmek için kullanılır. Döndürülen `end` değer dereferenced olmamalıdır.

### <a name="example"></a>Örnek

```cpp
// hash_set_end.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_set <int> hs1;
   hash_set <int> :: iterator hs1_Iter;
   hash_set <int> :: const_iterator hs1_cIter;

   hs1.insert( 1 );
   hs1.insert( 2 );
   hs1.insert( 3 );

   hs1_Iter = hs1.end( );
   hs1_Iter--;
   cout << "The last element of hs1 is " << *hs1_Iter << endl;

   hs1.erase( hs1_Iter );

   // The following 3 lines would err because the iterator is const:
   // hs1_cIter = hs1.end( );
   // hs1_cIter--;
   // hs1.erase( hs1_cIter );

   hs1_cIter = hs1.end( );
   hs1_cIter--;
   cout << "The last element of hs1 is now " << *hs1_cIter << endl;
}
```

```Output
The last element of hs1 is 3
The last element of hs1 is now 2
```

## <a name="hash_setequal_range"></a><a name="equal_range"></a>hash_set:equal_range

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set Sınıf](../standard-library/unordered-set-class.md).

Bir karma kümesindeki ilk öğeye sırasıyla bir çift yineleyici, belirtilen bir anahtara eşit bir anahtarla ve anahtardan büyük bir anahtarla karma kümesindeki ilk öğeye döndürür.

```cpp
pair <const_iterator, const_iterator> equal_range (const Key& key) const;

pair <iterator, iterator> equal_range (const Key& key);
```

### <a name="parameters"></a>Parametreler

*Anahtar*\
Aralanmakta olan hash_set öğenin tür anahtarıyla karşılaştırılacak bağımsız değişken anahtarı.

### <a name="return-value"></a>Dönüş Değeri

İlkanahtarın [lower_bound,](../standard-library/set-class.md#lower_bound) ikincisi anahtarın [upper_bound](../standard-library/set-class.md#upper_bound) olduğu bir çift yineleyici.

Üye işlev tarafından döndürülen bir çift pr'ın ilk `pr`yineleyicisine erişmek için. **ilk**, ve alt sınır yineleyici dereference \* `pr`için, kullanın ( . **ilk**). Üye işlev tarafından döndürülen bir `pr` çiftin ikinci yineleyicisine `pr`erişmek için. **ikinci**ve üst sınır yineleyicide dereference \*için, kullanın ( `pr`. **ikinci**).

### <a name="remarks"></a>Açıklamalar

### <a name="example"></a>Örnek

```cpp
// hash_set_equal_range.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   typedef hash_set<int> IntHSet;
   IntHSet hs1;
   hash_set <int> :: const_iterator hs1_RcIter;

   hs1.insert( 10 );
   hs1.insert( 20 );
   hs1.insert( 30 );

   pair <IntHSet::const_iterator, IntHSet::const_iterator> p1, p2;
   p1 = hs1.equal_range( 20 );

   cout << "The upper bound of the element with "
        << "a key of 20 in the hash_set hs1 is: "
        << *(p1.second) << "." << endl;

   cout << "The lower bound of the element with "
        << "a key of 20 in the hash_set hs1 is: "
        << *(p1.first) << "." << endl;

   // Compare the upper_bound called directly
   hs1_RcIter = hs1.upper_bound( 20 );
   cout << "A direct call of upper_bound( 20 ) gives "
        << *hs1_RcIter << "," << endl
        << "matching the 2nd element of the pair"
        << " returned by equal_range( 20 )." << endl;

   p2 = hs1.equal_range( 40 );

   // If no match is found for the key,
   // both elements of the pair return end( )
   if ( ( p2.first == hs1.end( ) ) && ( p2.second == hs1.end( ) ) )
      cout << "The hash_set hs1 doesn't have an element "
           << "with a key greater than or equal to 40." << endl;
   else
      cout << "The element of hash_set hs1 with a key >= 40 is: "
           << *(p1.first) << "." << endl;
}
```

```Output
The upper bound of the element with a key of 20 in the hash_set hs1 is: 30.
The lower bound of the element with a key of 20 in the hash_set hs1 is: 20.
A direct call of upper_bound( 20 ) gives 30,
matching the 2nd element of the pair returned by equal_range( 20 ).
The hash_set hs1 doesn't have an element with a key greater than or equal to 40.
```

## <a name="hash_seterase"></a><a name="erase"></a>hash_set::silme

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set Sınıf](../standard-library/unordered-set-class.md).

Bir öğeyi veya hash_set bir öğe aralığını belirtilen konumlardan kaldırır veya belirtilen anahtarla eşleşen öğeleri kaldırır.

```cpp
iterator erase(iterator _Where);

iterator erase(iterator first, iterator last);

size_type erase(const key_type& key);
```

### <a name="parameters"></a>Parametreler

*_Where*\
Hash_set kaldırılacak öğenin konumu.

*Ilk*\
hash_set kaldırılan ilk öğenin konumu.

*Son*\
hash_set kaldırılan son öğenin hemen ötesine yerleştirin.

*Anahtar*\
hash_set kaldırılacak öğelerin anahtarı.

### <a name="return-value"></a>Dönüş Değeri

İlk iki üye işlev için, kaldırılan öğelerin ötesinde kalan ilk öğeyi belirleyen çift yönlü bir yineleyici veya böyle bir öğe yoksa hash_set sonuna işaretçi. Üçüncü üye işlev için, hash_set kaldırılan öğelerin sayısı.

### <a name="remarks"></a>Açıklamalar

Üye işlevler hiçbir zaman bir özel durum atmaz.

### <a name="example"></a>Örnek

Aşağıdaki örnek, hash_set::delete üye işlevinin kullanımını göstermektedir.

```cpp
// hash_set_erase.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main()
{
    using namespace std;
    using namespace stdext;
    hash_set<int> hs1, hs2, hs3;
    hash_set<int>::iterator pIter, Iter1, Iter2;
    int i;
    hash_set<int>::size_type n;

    for (i = 1; i < 5; i++)
    {
        hs1.insert (i);
        hs2.insert (i * i);
        hs3.insert (i - 1);
    }

    // The 1st member function removes an element at a given position
    Iter1 = ++hs1.begin();
    hs1.erase(Iter1);

    cout << "After the 2nd element is deleted, the hash_set hs1 is:";
    for (pIter = hs1.begin(); pIter != hs1.end(); pIter++)
        cout << " " << *pIter;
    cout << "." << endl;

    // The 2nd member function removes elements
    // in the range [ first,  last)
    Iter1 = ++hs2.begin();
    Iter2 = --hs2.end();
    hs2.erase(Iter1, Iter2);

    cout << "After the middle two elements are deleted, "
         << "the hash_set hs2 is:";
    for (pIter = hs2.begin(); pIter != hs2.end(); pIter++)
        cout << " " << *pIter;
    cout << "." << endl;

    // The 3rd member function removes elements with a given  key
    n = hs3.erase(2);

    cout << "After the element with a key of 2 is deleted, "
         << "the hash_set hs3 is:";
    for (pIter = hs3.begin(); pIter != hs3.end(); pIter++)
        cout << " " << *pIter;
    cout << "." << endl;

    // The 3rd member function returns the number of elements removed
    cout << "The number of elements removed from hs3 is: "
         << n << "." << endl;

    // The dereferenced iterator can also be used to specify a key
    Iter1 = ++hs3.begin();
    hs3.erase(Iter1);

    cout << "After another element (unique for hash_set) with a key "
         << endl;
    cout  << "equal to that of the 2nd element is deleted, "
          << "the hash_set hs3 is:";
    for (pIter = hs3.begin(); pIter != hs3.end(); pIter++)
        cout << " " << *pIter;
    cout << "." << endl;
}
```

```Output
After the 2nd element is deleted, the hash_set hs1 is: 1 3 4.
After the middle two elements are deleted, the hash_set hs2 is: 16 4.
After the element with a key of 2 is deleted, the hash_set hs3 is: 0 1 3.
The number of elements removed from hs3 is: 1.
After another element (unique for hash_set) with a key
equal to that of the 2nd element is deleted, the hash_set hs3 is: 0 3.
```

## <a name="hash_setfind"></a><a name="find"></a>hash_set::bul

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set Sınıf](../standard-library/unordered-set-class.md).

Belirli bir anahtara eşdeğer anahtara sahip bir hash_set öğenin konumunu ele alan bir yineleyici döndürür.

```cpp
iterator find(const Key& key);

const_iterator find(const Key& key) const;
```

### <a name="parameters"></a>Parametreler

*Anahtar*\
Aralanan hash_set öğenin tür anahtarıyla eşleşecek bağımsız değişken anahtarı.

### <a name="return-value"></a>Dönüş Değeri

Bir `iterator` `const_iterator` veya bu, belirtilen bir anahtara eşdeğer bir öğenin konumunu gideren veya anahtar için eşleşme bulunamazsa hash_set'daki son öğeyi yerine getiren konuma yöneliktir.

### <a name="remarks"></a>Açıklamalar

Üye işlev, hash_set bir öğeyi ele alan ve sıralama anahtarı `equivalent` ikili yüklem altında bağımsız değişken anahtarı olan ve karşılaştırılabilirlik ilişkisine dayalı bir sıralamayı başlatan bir öğeyi döndürür.

Bir `const_iterator`, hash_set `find` nesnesinin geri dönüş değeri ne olursa olsun değiştirilemez. Bir `iterator`, hash_set `find` nesnesinin geri dönüş değeri ne olursa olsun değiştirilebilir.

### <a name="example"></a>Örnek

```cpp
// hash_set_find.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_set <int> hs1;
   hash_set <int> :: const_iterator hs1_AcIter, hs1_RcIter;

   hs1.insert( 10 );
   hs1.insert( 20 );
   hs1.insert( 30 );

   hs1_RcIter = hs1.find( 20 );
   cout << "The element of hash_set hs1 with a key of 20 is: "
        << *hs1_RcIter << "." << endl;

   hs1_RcIter = hs1.find( 40 );

   // If no match is found for the key, end( ) is returned
   if ( hs1_RcIter == hs1.end( ) )
      cout << "The hash_set hs1 doesn't have an element "
           << "with a key of 40." << endl;
   else
      cout << "The element of hash_set hs1 with a key of 40 is: "
           << *hs1_RcIter << "." << endl;

   // The element at a specific location in the hash_set can be found
   // by using a dereferenced iterator addressing the location
   hs1_AcIter = hs1.end( );
   hs1_AcIter--;
   hs1_RcIter = hs1.find( *hs1_AcIter );
   cout << "The element of hs1 with a key matching "
        << "that of the last element is: "
        << *hs1_RcIter << "." << endl;
}
```

```Output
The element of hash_set hs1 with a key of 20 is: 20.
The hash_set hs1 doesn't have an element with a key of 40.
The element of hs1 with a key matching that of the last element is: 30.
```

## <a name="hash_setget_allocator"></a><a name="get_allocator"></a>hash_set:get_allocator

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set Sınıf](../standard-library/unordered-set-class.md).

hash_set oluşturmak için kullanılan ayırıcı nesnenin bir kopyasını döndürür.

```cpp
Allocator get_allocator() const;
```

### <a name="return-value"></a>Dönüş Değeri

Şablon parametre *Allocator*olan bellek yönetmek için hash_set tarafından kullanılan ayırıcı.

*Allocator*hakkında daha fazla bilgi için [hash_set Sınıfı](../standard-library/hash-set-class.md) konusunun Açıklamalar bölümüne bakın.

### <a name="remarks"></a>Açıklamalar

hash_set sınıfının ayırıcıları sınıfın depolamayı nasıl yönettiğini belirtir. C++ Standart Kitaplık kapsayıcı sınıfları ile birlikte verilen varsayılan ayırıcılar çoğu programlama gereksinimleri için yeterlidir. Kendi ayırıcı sınıfınızı yazmak ve kullanmak gelişmiş bir C++ konusudur.

### <a name="example"></a>Örnek

```cpp
// hash_set_get_allocator.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;

   // The following lines declare objects
   // that use the default allocator.
   hash_set <int, hash_compare <int, less<int> > > hs1;
   hash_set <int,  hash_compare <int, greater<int> > > hs2;
   hash_set <double, hash_compare <double,
      less<double> >, allocator<double> > hs3;

   hash_set <int, hash_compare <int,
      greater<int> > >::allocator_type hs2_Alloc;
   hash_set <double>::allocator_type hs3_Alloc;
   hs2_Alloc = hs2.get_allocator( );

   cout << "The number of integers that can be allocated"
        << endl << "before free memory is exhausted: "
        << hs1.max_size( ) << "." << endl;

   cout << "The number of doubles that can be allocated"
        << endl << "before free memory is exhausted: "
        << hs3.max_size( ) <<  "." << endl;

   // The following lines create a hash_set hs4
   // with the allocator of hash_set hs1.
   hash_set <int>::allocator_type hs4_Alloc;
   hash_set <int> hs4;
   hs4_Alloc = hs2.get_allocator( );

   // Two allocators are interchangeable if
   // storage allocated from each can be
   // deallocated by the other
   if( hs2_Alloc == hs4_Alloc )
   {
      cout << "The allocators are interchangeable."
           << endl;
   }
   else
   {
      cout << "The allocators are not interchangeable."
           << endl;
   }
}
```

## <a name="hash_sethash_set"></a><a name="hash_set"></a>hash_set:hash_set

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set Sınıf](../standard-library/unordered-set-class.md).

Boş olan `hash_set` veya başka `hash_set`bir şeyin tamamının veya bir kısmının kopyası olan bir yapı.

```cpp
hash_set();

explicit hash_set(
    const Traits& Comp);

hash_set(
    const Traits& Comp,
    const Allocator& Al);

hash_set(
    const hash_set<Key, Traits, Allocator>& Right);

hash_set(
    hash_set&& Right);

hash_set(
    initializer_list<Type> IList);

hash_set(
    initializer_list<Type> IList,
    const Compare& Comp);

hash_set(
    initializer_list<value_type> IList,
    const Compare& Comp,
    const Allocator& Al);

template <class InputIterator>
hash_set(
    InputIterator First,
    InputIterator Last);

template <class InputIterator>
hash_set(
    InputIterator First,
    InputIterator Last,
    const Traits& Comp);

template <class InputIterator>
hash_set(
    InputIterator First,
    InputIterator Last,
    const Traits& Comp,
    const Allocator& Al);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|-|-|
|*Al*|Varsayılan olarak bu `hash_set` nesne için kullanılacak depolama ayırıcı `Allocator`sınıfı.|
|*Comp*|'deki öğeleri `const Traits` sıralamak için kullanılan `hash_set`türün karşılaştırma `hash_compare`işlevi , hangi varsayılan .|
|*Doğru*|Hangi `hash_set` inşa `hash_set` bir kopyası olmaktır.|
|*Ilk*|Kopyalanacak öğeler aralığındaki ilk öğenin konumu.|
|*Son*|İlk öğenin kopyalanacak öğe aralığının ötesindeki konumu.|

### <a name="remarks"></a>Açıklamalar

Tüm oluşturucular için bellek depolama yöneten `hash_set` ve daha sonra hash_set arayarak döndürülebilir ayırıcı nesne türü depolar::get_allocator . [hash_set::get_allocator](#get_allocator) Ayırıcı parametresi genellikle sınıf bildirimlerinde ve alternatif ayırıcıların yerine kullanılan ön işleme makrolarında atlanır.

Tüm yapıcılar hash_sets.

Tüm oluşturucular, anahtarları arasında `Traits` bir düzen oluşturmak için kullanılan `hash_set` ve daha sonra [hash_set::key_comp'](#key_comp)yi arayarak döndürülebilen bir işlev nesnesi depolarlar. [hash_set Sınıfı](../standard-library/hash-set-class.md) `Traits` konusu hakkında daha fazla bilgi için bkz.

İlk oluşturucu boş bir `hash_set` ilk oluşturur İkinci öğelerin sırasını `Comp`oluştururken kullanılacak karşılaştırma işlevinin türünü ( ) belirtir ve üçüncü açık `Al`bir şekilde kullanılacak ayırıcı türü ( ) belirtir. Anahtar sözcük, `explicit` belirli türde otomatik tür dönüştürmeyi bastırır.

Dördüncü ve beşinci yapıcılar bir kopyasını `hash_set` `Right`belirtir.

Son altıncı, yedinci ve sekizinci yapıcılar elementler için bir initializer_list kullanırlar.

Son oluşturucular, sınıf `First`Özellikleri `Last`ve `hash_set` ayırıcısının karşılaştırma işlevinin türünü belirtirken artan bir açıklıkla aralığı [, ) kopyalar.

Sekizinci yapıcı hareket `hash_set` `Right`eder.

Bir `hash_set` kapsayıcıdaki öğelerin gerçek sırası karma işlevine, sıralama işlevine ve karma tablonun geçerli boyutuna bağlıdır ve genel olarak, yalnızca sipariş işlevi tarafından belirlendiği küme kapsayıcıile olduğu gibi tahmin edilemez.

## <a name="hash_setinsert"></a><a name="insert"></a>hash_set::ekle

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set Sınıf](../standard-library/unordered-set-class.md).

Bir öğeye veya bir dizi öğeye `hash_set`bir öğe ekler.

```cpp
pair<iterator, bool> insert(
    const value_type& Val);

iterator insert(
    iterator Where,
    const value_type& Val);

void insert(
    initializer_list<value_type> IList)
template <class InputIterator>
void insert(
    InputIterator First,
    InputIterator Last);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|-|-|
|*Val*|Zaten bu öğeyi veya daha genel `hash_set` olarak, anahtarı eşdeğer sıralanmış bir öğeyi içermediği sürece, `hash_set` bir öğenin içine eklenecek öğenin değeri.|
|*Nerede*|Doğru ekleme noktasını aramaya başlamak için yer. (Ekleme noktası hemen takip `_Where`ederse, logaritmik zaman yerine, amortismana tabi sabit zaman oluşabilir .)|
|*Ilk*|Bir `hash_set`'den kopyalanacak ilk öğenin konumu|
|*Son*|Bir `hash_set`'den kopyalanacak son öğenin hemen ötesindeki konum.|
|*ılist*|Öğelerin kopyalanacağı initializer_list.|

### <a name="return-value"></a>Dönüş Değeri

İlk `insert` üye işlev, ekleme yapıldıysa **bool** bileşeni **doğru** döndüren **ve** `hash_set` anahtar siparişte eşdeğer değere sahip bir öğe yi içeren ve yineleyici bileşeni yeni bir öğenin eklendiği veya öğenin bulunduğu adresi döndüren bir öğe yi döndürür.

Bu üye işlev tarafından döndürülen `pr` bir çiftin yineleyici `pr.first` bileşenine erişmek için, `*(pr.first)`onu kullanmak ve dereference'ı kullanmak için. Bu üye işlev tarafından döndürülen bir çiftin `pr` **bool** bileşenine erişmek için, bunu kullanmak `pr.second`ve dereference için, kullanın `*(pr.second)`.

İkinci `insert` üye işlev, yeni öğenin `hash_set`'e eklendiği konumu gösteren bir yineleyici döndürür.

### <a name="remarks"></a>Açıklamalar

Üçüncü üye işlev, öğeleri bir initializer_list ekler.

Üçüncü üye işlev, öğe değerlerinin `hash_set` dizisini, belirtilen `First` `Last` `hash_set`bir aralıktaki [, ) bir yineleyici tarafından adreslenen her öğeye karşılık gelen bir öğeye ekler.

## <a name="hash_setiterator"></a><a name="iterator"></a>hash_set::iterator

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set Sınıf](../standard-library/unordered-set-class.md).

hash_set herhangi bir öğeyi okuyabilen veya değiştirebilen çift yönlü bir yineleme sağlayan bir tür.

```cpp
typedef list<typename Traits::value_type, typename Traits::allocator_type>::iterator iterator;
```

### <a name="remarks"></a>Açıklamalar

Bir `iterator` tür, bir öğenin değerini değiştirmek için kullanılabilir.

### <a name="example"></a>Örnek

Nasıl bildirilir [begin](#begin) ve kullanılacağına `iterator`bir örnek için başlangıç örneğine bakın.

## <a name="hash_setkey_comp"></a><a name="key_comp"></a>hash_set::key_comp

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set Sınıf](../standard-library/unordered-set-class.md).

Bir hash_set karma ve sipariş öğesi anahtar değerlerini için kullanılan karma özellikleri nesnesinin bir kopyasını alır.

```cpp
key_compare key_comp() const;
```

### <a name="return-value"></a>Dönüş Değeri

Şablon parametre *Özellikleri*olan öğelerini sıralamak için bir hash_set kullandığı işlev nesnesini döndürür.

*Özellikler* hakkında daha fazla bilgi için [hash_set Sınıfı](../standard-library/hash-set-class.md) konusuna bakın.

### <a name="remarks"></a>Açıklamalar

Depolanan nesne üye işlevi tanımlar:

`bool operator( const Key& _xVal, const Key& _yVal );`

önce yse ve sıralama `_yVal` sırasına eşit değilse doğru döndürür. **true** `_xVal`

Hem [key_compare](#key_compare) hem de [value_compare](#value_compare) şablon parametresi *Özellikleri*ile eş anlamlı olduğunu unutmayın. Her iki tür de, hash_map ve hash_multimap sınıflarıyla uyumluluğu için, farklı oldukları hash_set ve hash_multiset sınıfları için sağlanır.

### <a name="example"></a>Örnek

```cpp
// hash_set_key_comp.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;

   hash_set <int, hash_compare < int, less<int> > >hs1;
   hash_set<int, hash_compare < int, less<int> > >::key_compare kc1
          = hs1.key_comp( ) ;
   bool result1 = kc1( 2, 3 ) ;
   if( result1 == true )
   {
      cout << "kc1( 2,3 ) returns value of true, "
           << "where kc1 is the function object of hs1."
           << endl;
   }
   else
   {
      cout << "kc1( 2,3 ) returns value of false "
           << "where kc1 is the function object of hs1."
        << endl;
   }

   hash_set <int, hash_compare < int, greater<int> > > hs2;
   hash_set<int, hash_compare < int, greater<int> > >::key_compare
         kc2 = hs2.key_comp( ) ;
   bool result2 = kc2( 2, 3 ) ;
   if(result2 == true)
   {
      cout << "kc2( 2,3 ) returns value of true, "
           << "where kc2 is the function object of hs2."
           << endl;
   }
   else
   {
      cout << "kc2( 2,3 ) returns value of false, "
           << "where kc2 is the function object of hs2."
           << endl;
   }
}
```

## <a name="hash_setkey_compare"></a><a name="key_compare"></a>hash_set:key_compare

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set Sınıf](../standard-library/unordered-set-class.md).

hash_set iki öğenin göreli sırasını belirlemek için iki sıralama anahtarını karşılaştırabilen bir işlev nesnesi sağlayan bir tür.

```cpp
typedef Traits key_compare;
```

### <a name="remarks"></a>Açıklamalar

`key_compare`şablon parametresi *Özellikleri*ile eş anlamlıdır.

*Özellikler* hakkında daha fazla bilgi için [hash_set Sınıfı](../standard-library/hash-set-class.md) konusuna bakın.

Hem de `key_compare` [value_compare](#value_compare) şablon parametresi *Özellikleri*ile eş anlamlı olduğunu unutmayın. Her iki tür de, farklı oldukları harita ve çok eşli sınıflarla uyumluluk için, aynı oldukları küme ve çok ayarlı sınıflar için sağlanır.

### <a name="example"></a>Örnek

Nasıl bildirilir [key_comp](#key_comp) ve kullanılacağına `key_compare`ilgili bir örnek için key_comp örneğine bakın.

## <a name="hash_setkey_type"></a><a name="key_type"></a>hash_set:key_type

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set Sınıf](../standard-library/unordered-set-class.md).

Sıralama anahtarı olarak kapasitesinde hash_set öğesi olarak depolanan bir nesneyi açıklayan tür.

```cpp
typedef Key key_type;
```

### <a name="remarks"></a>Açıklamalar

`key_type`şablon parametre *Anahtarı*ile eş anlamlıdır.

*Anahtar*hakkında daha fazla bilgi için [hash_set Sınıfı](../standard-library/hash-set-class.md) konusunun Açıklamalar bölümüne bakın.

Hem de `key_type` [value_type](#value_type) şablon parametresi *Anahtarı*ile eş anlamlı olduğunu unutmayın. Her iki tür de, hash_map ve hash_multimap sınıflarıyla uyumluluğu için, farklı oldukları hash_set ve hash_multiset sınıfları için sağlanır.

### <a name="example"></a>Örnek

[Nasıl](#value_type) beyan value_type ve kullanılacağına `key_type`bir örnek için bkz.

## <a name="hash_setlower_bound"></a><a name="lower_bound"></a>hash_set:lower_bound

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set Sınıf](../standard-library/unordered-set-class.md).

Bir hash_set ilk öğeye, belirtilen anahtara eşit veya daha büyük bir anahtarla bir yineleyici döndürür.

```cpp
const_iterator lower_bound(const Key& key) const;

iterator lower_bound(const Key& key);
```

### <a name="parameters"></a>Parametreler

*Anahtar*\
Aralanmakta olan hash_set öğenin tür anahtarıyla karşılaştırılacak bağımsız değişken anahtarı.

### <a name="return-value"></a>Dönüş Değeri

Bir `iterator` `const_iterator` veya hash_set bir öğenin konumunu ele alan, bağımsız değişken anahtarına eşit veya daha büyük bir anahtarla veya anahtar için eşleşme bulunamazsa hash_set'daki son öğeyi başaran konumu ele alan bir öğe.

### <a name="remarks"></a>Açıklamalar

### <a name="example"></a>Örnek

```cpp
// hash_set_lower_bound.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_set <int> hs1;
   hash_set <int> :: const_iterator hs1_AcIter, hs1_RcIter;

   hs1.insert( 10 );
   hs1.insert( 20 );
   hs1.insert( 30 );

   hs1_RcIter = hs1.lower_bound( 20 );
   cout << "The element of hash_set hs1 with a key of 20 is: "
        << *hs1_RcIter << "." << endl;

   hs1_RcIter = hs1.lower_bound( 40 );

   // If no match is found for the key, end( ) is returned
   if ( hs1_RcIter == hs1.end( ) )
      cout << "The hash_set hs1 doesn't have an element "
           << "with a key of 40." << endl;
   else
      cout << "The element of hash_set hs1 with a key of 40 is: "
           << *hs1_RcIter << "." << endl;

   // An element at a specific location in the hash_set can be found
   // by using a dereferenced iterator that addresses the location
   hs1_AcIter = hs1.end( );
   hs1_AcIter--;
   hs1_RcIter = hs1.lower_bound( *hs1_AcIter );
   cout << "The element of hs1 with a key matching "
        << "that of the last element is: "
        << *hs1_RcIter << "." << endl;
}
```

```Output
The element of hash_set hs1 with a key of 20 is: 20.
The hash_set hs1 doesn't have an element with a key of 40.
The element of hs1 with a key matching that of the last element is: 30.
```

## <a name="hash_setmax_size"></a><a name="max_size"></a>hash_set:max_size

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set Sınıf](../standard-library/unordered-set-class.md).

hash_set maksimum uzunluğunu verir.

```cpp
size_type max_size() const;
```

### <a name="return-value"></a>Dönüş Değeri

Mümkün olan en fazla hash_set uzunluğu.

### <a name="remarks"></a>Açıklamalar

### <a name="example"></a>Örnek

```cpp
// hash_set_max_size.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_set <int> hs1;
   hash_set <int>::size_type i;

   i = hs1.max_size( );
   cout << "The maximum possible length "
        << "of the hash_set is " << i << "." << endl;
}
```

## <a name="hash_setoperator"></a><a name="op_eq"></a>hash_set::operator=

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set Sınıf](../standard-library/unordered-set-class.md).

hash_set öğelerini başka bir hash_set kopyasıyla değiştirir.

```cpp
hash_set& operator=(const hash_set& right);

hash_set& operator=(hash_set&& right);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|-|-|
|*Doğru*|[hash_set](../standard-library/hash-set-class.md) `hash_set`kopyalanıyor.|

### <a name="remarks"></a>Açıklamalar

Bir'deki varolan öğeleri `hash_set`silersonra , `operator=` *''nin* içeriğini `hash_set`kopyalar veya 'ye taşır.

### <a name="example"></a>Örnek

```cpp
// hash_set_operator_as.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_set<int> v1, v2, v3;
   hash_set<int>::iterator iter;

   v1.insert(10);

   cout << "v1 = " ;
   for (iter = v1.begin(); iter != v1.end(); iter++)
      cout << iter << " ";
   cout << endl;

   v2 = v1;
   cout << "v2 = ";
   for (iter = v2.begin(); iter != v2.end(); iter++)
      cout << iter << " ";
   cout << endl;

// move v1 into v2
   v2.clear();
   v2 = move(v1);
   cout << "v2 = ";
   for (iter = v2.begin(); iter != v2.end(); iter++)
      cout << iter << " ";
   cout << endl;
}
```

## <a name="hash_setpointer"></a><a name="pointer"></a>hash_set::pointer

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set Sınıf](../standard-library/unordered-set-class.md).

hash_set bir öğeiçin işaretçi sağlayan bir tür.

```cpp
typedef list<typename Traits::value_type, typename Traits::allocator_type>::pointer pointer;
```

### <a name="remarks"></a>Açıklamalar

Bir `pointer` tür, bir öğenin değerini değiştirmek için kullanılabilir.

Çoğu durumda, bir hash_set nesnesindeki öğelere erişmek için bir [yineleyici](#iterator) kullanılmalıdır.

## <a name="hash_setrbegin"></a><a name="rbegin"></a>hash_set::rbegin

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set Sınıf](../standard-library/unordered-set-class.md).

Ters hash_set ilk öğeyi ele alan bir yineleyici döndürür.

```cpp
const_reverse_iterator rbegin() const;

reverse_iterator rbegin();
```

### <a name="return-value"></a>Dönüş Değeri

Ters hash_set ilk öğeyi ele alan veya tersine çevrilmemiş hash_set son öğesini ele alan ters çift yönlü bir yineleyici.

### <a name="remarks"></a>Açıklamalar

`rbegin`bir hash_set ile [begin](#begin) olarak ters hash_set ile kullanılır.

Bir `const_reverse_iterator`, hash_set `rbegin` nesnesinin geri dönüş değeri ne olursa olsun değiştirilemez. Bir `reverse_iterator`, hash_set `rbegin` nesnesinin geri dönüş değerine atanmışsa değiştirilebilir.

`rbegin`geriye doğru bir hash_set ile yinelemek için kullanılabilir.

### <a name="example"></a>Örnek

```cpp
// hash_set_rbegin.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_set <int> hs1;
   hash_set <int>::iterator hs1_Iter;
   hash_set <int>::reverse_iterator hs1_rIter;

   hs1.insert( 10 );
   hs1.insert( 20 );
   hs1.insert( 30 );

   hs1_rIter = hs1.rbegin( );
   cout << "The first element in the reversed hash_set is "
        << *hs1_rIter << "." << endl;

   // begin can be used to start an iteration
   // through a hash_set in a forward order
   cout << "The hash_set is: ";
   for ( hs1_Iter = hs1.begin( ) ; hs1_Iter != hs1.end( );
         hs1_Iter++ )
      cout << *hs1_Iter << " ";
   cout << endl;

   // rbegin can be used to start an iteration
   // through a hash_set in a reverse order
   cout << "The reversed hash_set is: ";
   for ( hs1_rIter = hs1.rbegin( ) ; hs1_rIter != hs1.rend( );
         hs1_rIter++ )
      cout << *hs1_rIter << " ";
   cout << endl;

   // A hash_set element can be erased by dereferencing to its key
   hs1_rIter = hs1.rbegin( );
   hs1.erase ( *hs1_rIter );

   hs1_rIter = hs1.rbegin( );
   cout << "After the erasure, the first element "
        << "in the reversed hash_set is "<< *hs1_rIter << "."
        << endl;
}
```

```Output
The first element in the reversed hash_set is 30.
The hash_set is: 10 20 30
The reversed hash_set is: 30 20 10
After the erasure, the first element in the reversed hash_set is 20.
```

## <a name="hash_setreference"></a><a name="reference"></a>hash_set::referans

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set Sınıf](../standard-library/unordered-set-class.md).

hash_set depolanan bir öğeye başvuru sağlayan bir tür.

```cpp
typedef list<typename Traits::value_type, typename Traits::allocator_type>::reference reference;
```

### <a name="remarks"></a>Açıklamalar

### <a name="example"></a>Örnek

```cpp
// hash_set_reference.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_set <int> hs1;

   hs1.insert( 10 );
   hs1.insert( 20 );

   // Declare and initialize a reference &Ref1 to the 1st element
   int &Ref1 = *hs1.begin( );

   cout << "The first element in the hash_set is "
        << Ref1 << "." << endl;

   // The value of the 1st element of the hash_set can be changed
   // by operating on its (non-const) reference
   Ref1 = Ref1 + 5;

   cout << "The first element in the hash_set is now "
        << *hs1.begin() << "." << endl;
}
```

```Output
The first element in the hash_set is 10.
The first element in the hash_set is now 15.
```

## <a name="hash_setrend"></a><a name="rend"></a>hash_set::rend

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set Sınıf](../standard-library/unordered-set-class.md).

Ters hash_set son öğeyi yerine getiren konumu adresleyen bir yineleyici döndürür.

```cpp
const_reverse_iterator rend() const;

reverse_iterator rend();
```

### <a name="return-value"></a>Dönüş Değeri

Ters hash_set 'deki son öğeyi başaran konumu (ters çevrilmemiş hash_set ilk öğeden önce gelen konum) gideren ters çift yönlü bir yineleme.

### <a name="remarks"></a>Açıklamalar

`rend`[uç](#end) bir hash_set ile kullanıldığı gibi ters hash_set ile kullanılır.

Bir `const_reverse_iterator`, hash_set `rend` nesnesinin geri dönüş değeri ne olursa olsun değiştirilemez. Bir `reverse_iterator`, hash_set `rend` nesnesinin geri dönüş değerine atanmışsa değiştirilebilir. Döndürülen `rend` değer dereferenced olmamalıdır.

`rend`ters yineleyicinin hash_set sonuna ulaşıp ulaşmadığını test etmek için kullanılabilir.

### <a name="example"></a>Örnek

```cpp
// hash_set_rend.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_set <int> hs1;
   hash_set <int>::iterator hs1_Iter;
   hash_set <int>::reverse_iterator hs1_rIter;
   hash_set <int>::const_reverse_iterator hs1_crIter;

   hs1.insert( 10 );
   hs1.insert( 20 );
   hs1.insert( 30 );

   hs1_rIter = hs1.rend( );
   hs1_rIter--;
   cout << "The last element in the reversed hash_set is "
        << *hs1_rIter << "." << endl;

   // end can be used to terminate an iteration
   // through a hash_set in a forward order
   cout << "The hash_set is: ";
   for ( hs1_Iter = hs1.begin( ) ; hs1_Iter != hs1.end( );
         hs1_Iter++ )
      cout << *hs1_Iter << " ";
   cout << "." << endl;

   // rend can be used to terminate an iteration
   // through a hash_set in a reverse order
   cout << "The reversed hash_set is: ";
   for ( hs1_rIter = hs1.rbegin( ) ; hs1_rIter != hs1.rend( );
         hs1_rIter++ )
      cout << *hs1_rIter << " ";
   cout << "." << endl;

   hs1_rIter = hs1.rend( );
   hs1_rIter--;
   hs1.erase ( *hs1_rIter );

   hs1_rIter = hs1.rend( );
   hs1_rIter--;
   cout << "After the erasure, the last element in the "
        << "reversed hash_set is " << *hs1_rIter << "."
        << endl;
}
```

```Output
The last element in the reversed hash_set is 10.
The hash_set is: 10 20 30 .
The reversed hash_set is: 30 20 10 .
After the erasure, the last element in the reversed hash_set is 20.
```

## <a name="hash_setreverse_iterator"></a><a name="reverse_iterator"></a>hash_set:reverse_iterator

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set Sınıf](../standard-library/unordered-set-class.md).

Ters hash_set bir öğeyi okuyabilen veya değiştirebilen çift yönlü bir yineleme sağlayan bir tür.

```cpp
typedef list<typename Traits::value_type, typename Traits::allocator_type>::reverse_iterator reverse_iterator;
```

### <a name="remarks"></a>Açıklamalar

Bir `reverse_iterator` tür ters hash_set ile yinelemek için kullanılır.

### <a name="example"></a>Örnek

Nasıl bildirilir ve kullanılacağına `reverse_iterator`bir örnek için [rbegin](#rbegin) örneğine bakın.

## <a name="hash_setsize"></a><a name="size"></a>hash_set::boyut

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set Sınıf](../standard-library/unordered-set-class.md).

hash_set'daki öğe sayısını verir.

```cpp
size_type size() const;
```

### <a name="return-value"></a>Dönüş Değeri

hash_set geçerli uzunluğu.

### <a name="remarks"></a>Açıklamalar

### <a name="example"></a>Örnek

```cpp
// hash_set_size.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_set <int> hs1;
   hash_set <int> :: size_type i;

   hs1.insert( 1 );
   i = hs1.size( );
   cout << "The hash_set length is " << i << "." << endl;

   hs1.insert( 2 );
   i = hs1.size( );
   cout << "The hash_set length is now " << i << "." << endl;
}
```

```Output
The hash_set length is 1.
The hash_set length is now 2.
```

## <a name="hash_setsize_type"></a><a name="size_type"></a>hash_set:size_type

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set Sınıf](../standard-library/unordered-set-class.md).

hash_set öğelerinin sayısını temsil eden imzasız bir tamsayı türü.

```cpp
typedef list<typename Traits::value_type, typename Traits::allocator_type>::size_type size_type;
```

### <a name="remarks"></a>Açıklamalar

### <a name="example"></a>Örnek

Nasıl beyan edilip kullanılacağına ilgili bir örnek için [boyut](#size) örneğine bakın`size_type`

## <a name="hash_setswap"></a><a name="swap"></a>hash_set::takas

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set Sınıf](../standard-library/unordered-set-class.md).

İki hash_sets öğelerini değiştirir.

```cpp
void swap(hash_set& right);
```

### <a name="parameters"></a>Parametreler

*Doğru*\
Argüman, hedef hash_set değiştirilecek öğeleri sağlayan hash_set.

### <a name="remarks"></a>Açıklamalar

Üye işlev, öğeleri değiştirilen iki hash_sets öğeleri belirleyen hiçbir başvuru, işaretçi veya yineleyicigeçersiz olur.

### <a name="example"></a>Örnek

```cpp
// hash_set_swap.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_set <int> hs1, hs2, hs3;
   hash_set <int>::iterator hs1_Iter;

   hs1.insert( 10 );
   hs1.insert( 20 );
   hs1.insert( 30 );
   hs2.insert( 100 );
   hs2.insert( 200 );
   hs3.insert( 300 );

   cout << "The original hash_set hs1 is:";
   for ( hs1_Iter = hs1.begin( ); hs1_Iter != hs1.end( );
         hs1_Iter++ )
         cout << " " << *hs1_Iter;
   cout   << "." << endl;

   // This is the member function version of swap
   hs1.swap( hs2 );

   cout << "After swapping with hs2, list hs1 is:";
   for ( hs1_Iter = hs1.begin( ); hs1_Iter != hs1.end( );
         hs1_Iter++ )
         cout << " " << *hs1_Iter;
   cout  << "." << endl;

   // This is the specialized template version of swap
   swap( hs1, hs3 );

   cout << "After swapping with hs3, list hs1 is:";
   for ( hs1_Iter = hs1.begin( ); hs1_Iter != hs1.end( );
         hs1_Iter++ )
         cout << " " << *hs1_Iter;
   cout   << "." << endl;
}
```

```Output
The original hash_set hs1 is: 10 20 30.
After swapping with hs2, list hs1 is: 200 100.
After swapping with hs3, list hs1 is: 300.
```

## <a name="hash_setupper_bound"></a><a name="upper_bound"></a>hash_set:upper_bound

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set Sınıf](../standard-library/unordered-set-class.md).

Bir hash_set ilk öğeye belirtilen anahtardan daha büyük bir anahtarla bir yineleyici döndürür.

```cpp
const_iterator upper_bound(const Key& key) const;

iterator upper_bound(const Key& key);
```

### <a name="parameters"></a>Parametreler

*Anahtar*\
Aralanmakta olan hash_set öğenin tür anahtarıyla karşılaştırılacak bağımsız değişken anahtarı.

### <a name="return-value"></a>Dönüş Değeri

Bir `iterator` `const_iterator` veya bu, bağımsız değişken anahtarına eşit veya daha büyük bir anahtarla veya anahtar için eşleşme bulunamazsa hash_set'daki son öğeyi başaran konumu gideren bir hash_set öğenin konumunu ele alan bir öğedir.

### <a name="remarks"></a>Açıklamalar

### <a name="example"></a>Örnek

```cpp
// hash_set_upper_bound.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_set <int> hs1;
   hash_set <int> :: const_iterator hs1_AcIter, hs1_RcIter;

   hs1.insert( 10 );
   hs1.insert( 20 );
   hs1.insert( 30 );

   hs1_RcIter = hs1.upper_bound( 20 );
   cout << "The first element of hash_set hs1 with a key greater "
        << "than 20 is: " << *hs1_RcIter << "." << endl;

   hs1_RcIter = hs1.upper_bound( 30 );

   // If no match is found for the key, end( ) is returned
   if ( hs1_RcIter == hs1.end( ) )
      cout << "The hash_set hs1 doesn't have an element "
           << "with a key greater than 30." << endl;
   else
      cout << "The element of hash_set hs1 with a key > 40 is: "
           << *hs1_RcIter << "." << endl;

   // An element at a specific location in the hash_set can be found
   // by using a dereferenced iterator addressing the location
   hs1_AcIter = hs1.begin( );
   hs1_RcIter = hs1.upper_bound( *hs1_AcIter );
   cout << "The first element of hs1 with a key greater than "
        << endl << "that of the initial element of hs1 is: "
        << *hs1_RcIter << "." << endl;
}
```

```Output
The first element of hash_set hs1 with a key greater than 20 is: 30.
The hash_set hs1 doesn't have an element with a key greater than 30.
The first element of hs1 with a key greater than
that of the initial element of hs1 is: 20.
```

## <a name="hash_setvalue_comp"></a><a name="value_comp"></a>hash_set:value_comp

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set Sınıf](../standard-library/unordered-set-class.md).

Hash_set öğe değerlerini sıralamak için kullanılan karşılaştırma nesnesinin bir kopyasını alır.

```cpp
value_compare value_comp() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir hash_set öğelerini sıralamak için kullandığı işlev nesnesini döndürür, şablon parametresi *Karşılaştır.*

*Karşılaştır*hakkında daha fazla bilgi için [hash_set Sınıfı](../standard-library/hash-set-class.md) konusunun Açıklamalar bölümüne bakın.

### <a name="remarks"></a>Açıklamalar

Depolanan nesne üye işlevi tanımlar:

`bool operator( const Key& _xVal, const Key& _yVal );`

önce yse ve sıralama `_yVal` sırasına eşit değilse doğru döndürür. **true** `_xVal`

Hem [value_compare](../standard-library/set-class.md#value_compare) hem de [key_compare](../standard-library/set-class.md#key_compare) şablon parametresi *Karşılaştır*ile eşanlamlı olduğunu unutmayın. Her iki tür de, hash_map ve hash_multimap sınıflarıyla uyumluluğu için, farklı oldukları hash_set ve hash_multiset sınıfları için sağlanır.

### <a name="example"></a>Örnek

```cpp
// hash_set_value_comp.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;

   hash_set <int, hash_compare < int, less<int> > > hs1;
   hash_set <int, hash_compare < int, less<int> >  >::value_compare
      vc1 = hs1.value_comp( );
   bool result1 = vc1( 2, 3 );
   if( result1 == true )
   {
      cout << "vc1( 2,3 ) returns value of true, "
           << "where vc1 is the function object of hs1."
           << endl;
   }
   else
   {
      cout << "vc1( 2,3 ) returns value of false, "
           << "where vc1 is the function object of hs1."
           << endl;
   }

   hash_set <int, hash_compare < int, greater<int> > > hs2;
   hash_set<int, hash_compare < int, greater<int> > >::value_compare
      vc2 = hs2.value_comp( );
   bool result2 = vc2( 2, 3 );
   if( result2 == true )
   {
      cout << "vc2( 2,3 ) returns value of true, "
           << "where vc2 is the function object of hs2."
           << endl;
   }
   else
   {
      cout << "vc2( 2,3 ) returns value of false, "
           << "where vc2 is the function object of hs2."
           << endl;
   }
}
```

## <a name="hash_setvalue_compare"></a><a name="value_compare"></a>hash_set:value_compare

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set Sınıf](../standard-library/unordered-set-class.md).

İki işlev nesnesi sağlayan bir tür, bir hash_set iki öğe değerlerini karşılaştırabilen bir sınıf karşılaştırması ve öğeleri işleyen bir unary yüklemi.

```cpp
typedef key_compare value_compare;
```

### <a name="remarks"></a>Açıklamalar

`value_compare`şablon parametresi *Özellikleri*ile eş anlamlıdır.

*Özellikler* hakkında daha fazla bilgi için [hash_set Sınıfı](../standard-library/hash-set-class.md) konusuna bakın.

Hem [key_compare](#key_compare) hem `value_compare` de şablon parametresi *Özellikleri*ile eş anlamlıdır. Her iki tür de, hash_map ve hash_multimap sınıflarıyla uyumluluğu için, farklı oldukları hash_set ve hash_multiset sınıfları için sağlanır.

### <a name="example"></a>Örnek

Nasıl beyan value_comp ve nasıl kullanılacağına `value_compare`bir örnek için örneğe bakın. [value_comp](#value_comp)

## <a name="hash_setvalue_type"></a><a name="value_type"></a>hash_set:value_type

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set Sınıf](../standard-library/unordered-set-class.md).

Değer olarak kapasitesinde hash_set bir öğesi olarak depolanan bir nesneyi açıklayan tür.

```cpp
typedef Key value_type;
```

### <a name="example"></a>Örnek

```cpp
// hash_set_value_type.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_set <int> hs1;
   hash_set <int>::iterator hs1_Iter;

   hash_set <int> :: value_type hsvt_Int;   // Declare value_type
   hsvt_Int = 10;             // Initialize value_type

   hash_set <int> :: key_type hskt_Int;   // Declare key_type
   hskt_Int = 20;             // Initialize key_type

   hs1.insert( hsvt_Int );         // Insert value into hs1
   hs1.insert( hskt_Int );         // Insert key into hs1

   // A hash_set accepts key_types or value_types as elements
   cout << "The hash_set has elements:";
   for ( hs1_Iter = hs1.begin( ) ; hs1_Iter != hs1.end( ); hs1_Iter++)
      cout << " " << *hs1_Iter;
   cout << "." << endl;
}
```

```Output
The hash_set has elements: 10 20.
```

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[C++ Standart Kütüphane Başvurusu](../standard-library/cpp-standard-library-reference.md)
