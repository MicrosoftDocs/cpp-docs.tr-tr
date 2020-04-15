---
title: hash_multiset Sınıfı
ms.date: 11/04/2016
f1_keywords:
- hash_set/stdext::hash_multiset
- hash_set/stdext::hash_multiset::allocator_type
- hash_set/stdext::hash_multiset::const_iterator
- hash_set/stdext::hash_multiset::const_pointer
- hash_set/stdext::hash_multiset::const_reference
- hash_set/stdext::hash_multiset::const_reverse_iterator
- hash_set/stdext::hash_multiset::difference_type
- hash_set/stdext::hash_multiset::iterator
- hash_set/stdext::hash_multiset::key_compare
- hash_set/stdext::hash_multiset::key_type
- hash_set/stdext::hash_multiset::pointer
- hash_set/stdext::hash_multiset::reference
- hash_set/stdext::hash_multiset::reverse_iterator
- hash_set/stdext::hash_multiset::size_type
- hash_set/stdext::hash_multiset::value_compare
- hash_set/stdext::hash_multiset::value_type
- hash_set/stdext::hash_multiset::begin
- hash_set/stdext::hash_multiset::cbegin
- hash_set/stdext::hash_multiset::cend
- hash_set/stdext::hash_multiset::clear
- hash_set/stdext::hash_multiset::count
- hash_set/stdext::hash_multiset::crbegin
- hash_set/stdext::hash_multiset::crend
- hash_set/stdext::hash_multiset::emplace
- hash_set/stdext::hash_multiset::emplace_hint
- hash_set/stdext::hash_multiset::empty
- hash_set/stdext::hash_multiset::end
- hash_set/stdext::hash_multiset::equal_range
- hash_set/stdext::hash_multiset::erase
- hash_set/stdext::hash_multiset::find
- hash_set/stdext::hash_multiset::get_allocator
- hash_set/stdext::hash_multiset::insert
- hash_set/stdext::hash_multiset::key_comp
- hash_set/stdext::hash_multiset::lower_bound
- hash_set/stdext::hash_multiset::max_size
- hash_set/stdext::hash_multiset::rbegin
- hash_set/stdext::hash_multiset::rend
- hash_set/stdext::hash_multiset::size
- hash_set/stdext::hash_multiset::swap
- hash_set/stdext::hash_multiset::upper_bound
- hash_set/stdext::hash_multiset::value_comp
helpviewer_keywords:
- stdext::hash_multiset
- stdext::hash_multiset::allocator_type
- stdext::hash_multiset::const_iterator
- stdext::hash_multiset::const_pointer
- stdext::hash_multiset::const_reference
- stdext::hash_multiset::const_reverse_iterator
- stdext::hash_multiset::difference_type
- stdext::hash_multiset::iterator
- stdext::hash_multiset::key_compare
- stdext::hash_multiset::key_type
- stdext::hash_multiset::pointer
- stdext::hash_multiset::reference
- stdext::hash_multiset::reverse_iterator
- stdext::hash_multiset::size_type
- stdext::hash_multiset::value_compare
- stdext::hash_multiset::value_type
- stdext::hash_multiset::begin
- stdext::hash_multiset::cbegin
- stdext::hash_multiset::cend
- stdext::hash_multiset::clear
- stdext::hash_multiset::count
- stdext::hash_multiset::crbegin
- stdext::hash_multiset::crend
- stdext::hash_multiset::emplace
- stdext::hash_multiset::emplace_hint
- stdext::hash_multiset::empty
- stdext::hash_multiset::end
- stdext::hash_multiset::equal_range
- stdext::hash_multiset::erase
- stdext::hash_multiset::find
- stdext::hash_multiset::get_allocator
- stdext::hash_multiset::insert
- stdext::hash_multiset::key_comp
- stdext::hash_multiset::lower_bound
- stdext::hash_multiset::max_size
- stdext::hash_multiset::rbegin
- stdext::hash_multiset::rend
- stdext::hash_multiset::size
- stdext::hash_multiset::swap
- stdext::hash_multiset::upper_bound
- stdext::hash_multiset::value_comp
ms.assetid: 0580397a-a76e-40ad-aea2-5c6f3a9d0a21
ms.openlocfilehash: 8888f393e1058e3cd5ff968d9433b5306cac4949
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370654"
---
# <a name="hash_multiset-class"></a>hash_multiset Sınıfı

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multiset Sınıf](../standard-library/unordered-multiset-class.md).

Hash_multiset kapsayıcı sınıfı, C++ Standart Kitaplığı'nın bir uzantısıdır ve içerdiği öğelerin değerlerinin anahtar değerler olarak hizmet ettiği ve benzersiz olması gerekmeyen bir koleksiyondan veri depolama ve hızlı bir şekilde alınması için kullanılır.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Key, class Traits =hash_compare<Key, less <Key>>, class Allocator =allocator <Key>>
class hash_multiset
```

### <a name="parameters"></a>Parametreler

*Anahtar*\
hash_multiset depolanacak öğe veri türü.

*Özellik*\
İki işlev nesnesi içeren tür, bir sınıf karşılaştırması ikili yüklem iki öğe değeri göreli sıralarını belirlemek için sıra anahtarları ve tür imzasız tamsayılar `size_t`için öğelerin unary yüklem eşleme anahtar değerleri olan bir karma işlevi karşılaştırmak mümkün . Bu bağımsız değişken isteğe bağlıdır ve varsayılan `hash_compare<Key, less<Key> >` değerdir.

*Ayırıcı*\
hash_multiset ayırma ve bellek ayırma ile ilgili ayrıntıları kapsülleyen depolanan ayırıcı nesneyi temsil eden tür. Bu bağımsız değişken isteğe bağlıdır `allocator<Key>`ve varsayılan değer .

## <a name="remarks"></a>Açıklamalar

hash_multiset:

- İlişkili bir anahtar değerine dayalı öğe değerlerinin verimli alınmasını destekleyen bir değişken boyutu kapsayıcı olan ilişkilendirilebilir bir kapsayıcı. Dahası, basit bir ilişkilendirilebilir kapsayıcıdır, çünkü öğelerinin değerleri kendi anahtar değerleridir.

- Çift yönlüdür, çünkü öğelerine erişmek için çift yönlü bir yineleyici sağlar.

- Karma, çünkü elemanları, öğelerin temel değerlerine uygulanan karma işlevin değerine göre kovalar halinde gruplandırılır.

- Benzersizdir, çünkü öğelerinin her birinde benzersiz bir anahtar olması gerekir. hash_multiset aynı zamanda basit bir ilişkili kapsayıcı olduğundan, elemanları da benzersizdir.

- Sağladığı işlevsellik genel olduğundan ve öğe veya anahtar olarak bulunan belirli veri türünden bağımsız olduğundan sınıf şablonu. Öğeler ve anahtarlar için kullanılacak veri türleri, karşılaştırma işlevi ve ayırıcı ile birlikte bir sınıf şablonunda parametreler olarak belirtilir.

Sıralama üzerinde karma nın en büyük avantajı daha fazla verimliliktir: başarılı bir karma eklemeler, silmeler yapar ve sıralama teknikleri için kaptaki eleman sayısının logaritması ile orantılı bir süre ile karşılaştırıldığında sabit ortalama süre içinde bulur. Bir kümedeki bir öğenin değeri doğrudan değiştirilemez. Bunun yerine, eski değerleri silmeniz ve yeni değerlere sahip öğeler eklemeniz gerekir.

Kapsayıcı türünün seçimi genelde uygulamanın gerektirdiği arama ve ekleme türüne dayalı olmalıdır. Haşdi hashed musociative kaplar arama, ekleme ve kaldırma işlemleri için optimize edilmiştir. Bu işlemleri açıkça destekleyen üye işlevler, iyi tasarlanmış bir karma işlevle kullanıldığında verimlidir ve bunları ortalama sabit olan ve kapsayıcıdaki öğe sayısına bağlı olmayan bir zamanda gerçekleştirir. İyi tasarlanmış karma işlev karma değerlerin tek tip dağılımını üretir ve farklı anahtar değerleri aynı karma değere eşlendiğinde çakışacağı söylenen çarpışma sayısını en aza indirir. En kötü durumda, mümkün olan en kötü karma işlevi ile, işlem sayısı dizideki eleman sayısıyla (doğrusal zaman) orantılıdır.

Hash_multiset, değerleri anahtarlarıile ilişkilendiren koşullar uygulama tarafından karşılandığında tercih edilen ilişkisel kapsayıcı olmalıdır. Bir hash_multiset öğeleri birden fazla olabilir ve kendi sıralama anahtarları olarak hizmet, bu nedenle anahtarları benzersiz değildir. Bu tür bir yapı modeli, sözcüklerin birden çok defa geçebildiği sıralı bir sözcükler listesindedir. Sözcüklerin birden fazla oluşumuna izin verilmeseydi, hash_set uygun kapsayıcı yapısı olurdu. Benzersiz tanımlar benzersiz anahtar kelimeler listesine değer olarak eklenmişse, hash_map bu verileri içerecek uygun bir yapı olacaktır. Bunun yerine tanımlar benzersiz değilse, o zaman bir hash_multimap tercih edilen kapsayıcı olacaktır.

hash_multiset, denetlediği sırayı, depolanmış karma özellikleri nesnesini [value_compare.](#value_compare) Bu depolanan nesneye üye işlev [key_comp](#key_comp)çağırılarak erişilebilir. Böyle bir işlev nesnesi sınıfın `hash_compare<Key, less<Key> >`nesnesi ile aynı şekilde kullanılmalıdır. Özellikle, tüm *Key* değerler için `Key`Anahtar `Trait(Key)` türü, çağrı türü `size_t`değerlerinin bir dağıtım verir.

Genelde, bu sıralamayı oluşturmak için öğelerin yalnızca küçüktür biçiminde karşılaştırılabilir olması gerekir; böylece, herhangi iki öğe belirtildiğinde, eşit oldukları (yani birinin diğerinden daha küçük olmadığı anlamında) veya birinin diğerinden küçük olduğu belirlenebilir. Bu, denk olmayan öğeler arasında bir sıralamaya neden olur. Daha teknik bir not üzerinde, karşılaştırma işlevi standart matematiksel anlamda katı bir zayıf sıralama sevk eden ikili bir koşuldur. İkili yüklem *f*( *x*, *y*) iki bağımsız değişken nesnesi x ve y ve doğru veya yanlışın dönüş değeri olan bir işlev nesnesidir. Bir hash_multiset uygulanan bir sıralama, ikili yüklem inreflexive, antisimetrik ve geçişli ve eşdeğerlik geçişli ise, iki nesne x ve y hem *f*( *x*, *y*) ve *f*( *y*, *x*) yanlış olduğunda eşdeğer olarak tanımlanır sıkı bir zayıf sıralamadır. Anahtarlar arasındaki eşitliğinin daha güçlü koşulu bu denkliğin yerini alırsa, sıralama (içindeki tüm öğelerin birbirine göre sıralanması anlamında) toplam haline gelir ve eşleşen anahtarlar birbirinden ayırt edilemez olacaktır.

Denetlenmiş dizideki öğelerin gerçek sırası karma işlevine, sıralama işlevine ve kapsayıcı nesnesinde depolanan karma tablonun geçerli boyutuna bağlıdır. Karma tablonun geçerli boyutunu belirleyemezsiniz, bu nedenle genel olarak denetitilen dizideki öğelerin sırasını tahmin edemezsiniz. Öğelerin eklenmesi hiçbir yineleyiciyi geçersiz kılmaz; öğelerin kaldırılması yalnızca özellikle kaldırılan öğeleri gösteren yineleyicileri geçersiz kılar.

hash_multiset sınıfı tarafından sağlanan yineleme iki yönlü bir yinelemedir, ancak sınıf üye işlevleri şablon parametreleri olarak alan sürümlere sahip hash_multiset işlevsellik gereksinimleri çift yönlü yineleyicisınıfı tarafından garanti edilenden daha az olan daha zayıf bir giriş yineleyicisi alır. Farklı yineleyici kavramları, işlevselliklerindeki iyileştirmelere göre ilgili bir aile biçimlendirir. Her yineleme kavramının kendi gereksinim hash_multiset vardır ve onlarla çalışan algoritmalar varsayımlarını bu tür bir yineleyici tarafından sağlanan gereksinimlerle sınırlandırmalıdır. Bir giriş yineleyicinin bazı nesnelere başvurusunun kaldırılacağı ve dizideki sonraki yineleyiciye artırılabileceği varsayılabilir. Bu, en az işlevsellik hash_multiset, ancak sınıf üye işlevleri bağlamında bir dizi `first`yineleyici [, `last`) hakkında anlamlı bir şekilde konuşabilmek yeterlidir.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[Hash_multiset](#hash_multiset)|Boş olan `hash_multiset` veya başka `hash_multiset`bir şeyin tamamının veya bir kısmının kopyası olan bir yapı.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[Allocator_type](#allocator_type)|Nesnenin sınıfını `allocator` `hash_multiset` temsil eden bir tür.|
|[const_iterator](#const_iterator)|`hash_multiset`Bir **const** öğesi okuyabilen çift yönlü bir yineleme sağlayan bir tür.|
|[Const_pointer](#const_pointer)|Bir **const** öğesine işaretçi sağlayan `hash_multiset`bir tür .|
|[const_reference](#const_reference)|Const **işlemleri** okumak ve gerçekleştirmek için bir `hash_multiset` **const** öğesinde depolanan bir öğeye başvuru sağlayan bir tür.|
|[Const_reverse_iterator](#const_reverse_iterator)|Herhangi bir const öğeyi okuyabilen çift yönlü bir yineleme sağlayan bir tür. **const** `hash_multiset`|
|[difference_type](#difference_type)|Aynı `hash_multiset`içindeki öğeleri ele alan iki yineleyici arasındaki farkı sağlayan imzalı bir tamsayı türü.|
|[Yineleyici](#iterator)|Bir 'deki herhangi bir öğeyi okuyabilen veya değiştirebilen `hash_multiset`çift yönlü bir yineleme sağlayan bir tür.|
|[Key_compare](#key_compare)|İki öğenin göreli sırasını belirlemek için iki sıralama anahtarını karşılaştırabilen bir işlev nesnesi `hash_multiset`sağlayan bir tür.|
|[Key_type](#key_type)|Sıralama anahtarı olarak kapasitesinde bir `hash_set` öğe olarak depolanan bir nesneyi açıklayan bir tür.|
|[pointer](#pointer)|Bir öğedeki bir öğeye işaretçi sağlayan bir `hash_multiset`tür|
|[Başvuru](#reference)|Bir 'de depolanan bir öğeye `hash_multiset`başvuru sağlayan bir tür|
|[Reverse_iterator](#reverse_iterator)|Ters bir öğedeki bir öğeyi okuyabilen veya değiştirebilen `hash_multiset`çift yönlü bir yineleme sağlayan bir tür.|
|[size_type](#size_type)|Bir 'deki öğe sayısını temsil eden imzasız `hash_multiset`bir tamsayı türü|
|[Value_compare](#value_compare)|İki işlev nesnesi sağlayan bir tür, bir sınıf karşılaştırması, göreli `hash_multiset` düzenlerini belirlemek için a'nın iki öğe değerini ve öğeleri işleyen bir unary yüklemi karşılaştırabilen bir tür.|
|[value_type](#value_type)|Değer olarak kapasitesinde bir `hash_multiset` öğe olarak depolanan bir nesneyi açıklayan bir tür.|

### <a name="member-functions"></a>Üye işlevler

|Üye fonksiyonu|Açıklama|
|-|-|
|[Başlamak](#begin)|`hash_multiset`'deki ilk öğeyi ele alan bir yineleyici döndürür.|
|[cbegin](#cbegin)|'deki ilk öğeyi ele alan bir const yineleyici döndürür. `hash_multiset`|
|[cend](#cend)|Bir `hash_multiset`'deki son öğeyi yerine getiren konumu gideren bir const yineleyici döndürür.|
|[Temizleyin](#clear)|Bir' `hash_multiset`nin tüm öğelerini siler.|
|[Sayısı](#count)|Anahtarı parametre yle `hash_multiset` belirtilen anahtarla eşleşen bir öğedeki eleman sayısını verir|
|[crbegin](#crbegin)|Ters bir ilk öğeyi ele alan bir const yineleyici döndürür. `hash_multiset`|
|[crend](#crend)|Ters bir önceki son öğeyi yerine getiren konumu gideren bir `hash_multiset`const yineleyici döndürür.|
|[emplace](#emplace)|Yerinde inşa edilmiş bir öğeyi `hash_multiset`bir .|
|[emplace_hint](#emplace_hint)|Yerinde `hash_multiset`oluşturulmuş bir öğeyi yerleştirme ipucuyla ekler.|
|[empty](#empty)|A boşsa `hash_multiset` sınar.|
|[Son -unda](#end)|Bir 'deki son öğeyi yerine getiren konumu adresleyen `hash_multiset`bir yineleyici döndürür.|
|[equal_range](#equal_range)|Belirtilen bir anahtardan büyük bir `hash_multiset` anahtarla bir ilk öğeye ve anahtara eşit veya daha `hash_multiset` büyük bir anahtarla ilk öğeye sırasıyla bir çift yineleyici döndürür.|
|[Silmek](#erase)|Belirtilen konumlardaki `hash_multiset` bir öğeyi veya bir dizi öğeyi kaldırır veya belirtilen anahtarla eşleşen öğeleri kaldırır.|
|[find](#find)|Belirtilen bir anahtara eşdeğer anahtara sahip bir `hash_multiset` öğedeki öğenin konumunu ele alan bir yineleyici döndürür.|
|[Get_allocator](#get_allocator)|Oluşturmak için kullanılan `allocator` nesnenin bir `hash_multiset`kopyasını döndürür.|
|[Ekle](#insert)|Bir öğeye veya bir dizi öğeye `hash_multiset`bir öğe ekler.|
|[Key_comp](#key_compare)|Bir `hash_multiset`'deki anahtarları sipariş etmek için kullanılan karşılaştırma nesnesinin bir kopyasını alır.|
|[lower_bound](#lower_bound)|Bir yineleyiciyi, belirtilen bir anahtara eşit veya daha büyük bir `hash_multiset` anahtarla bir ilk öğeye döndürür.|
|[max_size](#max_size)|Maksimum uzunluğu `hash_multiset`verir.|
|[rbegin](#rbegin)|Ters bir ilk öğeyi ele alan bir `hash_multiset`yineleyici döndürür.|
|[Rend](#rend)|Ters çevrilmiş bir son öğedeki son öğeyi yerine `hash_multiset`getiren konumu adresleyen bir yineleyici döndürür.|
|[Boyutu](#size)|`hash_multiset`'deki öğe sayısını verir.|
|[Takas](#swap)|İki `hash_multiset`s'nin öğelerini değiştirir.|
|[upper_bound](#upper_bound)|Bir yineleyiciyi, belirtilen bir anahtara eşit veya daha büyük bir anahtarla bir ilk öğeye `hash_multiset` döndürür.|
|[value_comp](#value_comp)|Karma ve sipariş öğesi anahtar değerlerini bir `hash_multiset`' de karma ve sipariş etmek için kullanılan karma özellikleri nesnesinin bir kopyasını alır.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[hash_multiset::operator=](#op_eq)|hash_multiset öğelerini başka bir hash_multiset kopyasıyla değiştirir.|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** \<hash_set>

**Ad alanı:** stdext

## <a name="hash_multisetallocator_type"></a><a name="allocator_type"></a>hash_multiset::allocator_type

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multiset Sınıf](../standard-library/unordered-multiset-class.md).

hash_multiset nesnesinin ayırıcı sınıfını temsil eden bir tür.

```cpp
typedef list<typename Traits::value_type, typename Traits::allocator_type>::allocator_type allocator_type;
```

### <a name="example"></a>Örnek

Get_allocator için [get_allocator](#get_allocator) örneğe bakın`allocator_type`

## <a name="hash_multisetbegin"></a><a name="begin"></a>hash_multiset::başla

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multiset Sınıf](../standard-library/unordered-multiset-class.md).

hash_multiset ilk öğeyi ele alan bir yineleyici döndürür.

```cpp
const_iterator begin() const;

iterator begin();
```

### <a name="return-value"></a>Dönüş Değeri

hash_multiset'daki ilk öğeyi veya boş bir hash_multiset yerine gelen konumu ele alan çift yönlü bir yineleyici.

### <a name="remarks"></a>Açıklamalar

`begin` Bir `const_iterator`, hash_multiset nesnesindeki öğelere atanırsa değiştirilemez. Bir `begin` `iterator`, hash_multiset nesnesindeki öğelere atanırsa değiştirilebilir.

### <a name="example"></a>Örnek

```cpp
// hash_multiset_begin.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_multiset <int> hms1;
   hash_multiset <int>::iterator hms1_Iter;
   hash_multiset <int>::const_iterator hms1_cIter;

   hms1.insert( 1 );
   hms1.insert( 2 );
   hms1.insert( 3 );

   hms1_Iter = hms1.begin( );
   cout << "The first element of hms1 is " << *hms1_Iter << endl;

   hms1_Iter = hms1.begin( );
   hms1.erase( hms1_Iter );

   // The following 2 lines would err because the iterator is const
   // hms1_cIter = hms1.begin( );
   // hms1.erase( hms1_cIter );

   hms1_cIter = hms1.begin( );
   cout << "The first element of hms1 is now " << *hms1_cIter << endl;
}
```

```Output
The first element of hms1 is 1
The first element of hms1 is now 2
```

## <a name="hash_multisetcbegin"></a><a name="cbegin"></a>hash_multiset::cbegin

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multiset Sınıf](../standard-library/unordered-multiset-class.md).

hash_multiset ilk öğeyi ele alan bir const yineleyici döndürür.

```cpp
const_iterator cbegin() const;
```

### <a name="return-value"></a>Dönüş Değeri

[hash_multiset'daki](../standard-library/hash-multiset-class.md) ilk öğeyi veya boş `hash_multiset`bir konumdan sonra gelen bir konst çift yönlü yineleme.

### <a name="remarks"></a>Açıklamalar

Geri dönüş değeri `cbegin`ile nesnedeki `hash_multiset` öğeler değiştirilemez.

### <a name="example"></a>Örnek

```cpp
// hash_multiset_cbegin.cpp
// compile with: /EHsc
#include <hash_multiset>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_multiset <int> hs1;
   hash_multiset <int>::const_iterator hs1_cIter;

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

## <a name="hash_multisetcend"></a><a name="cend"></a>hash_multiset::cend

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multiset Sınıf](../standard-library/unordered-multiset-class.md).

Bir hash_multiset son öğeyi yerine getiren konumu gideren bir const yineleyici döndürür.

```cpp
const_iterator cend() const;
```

### <a name="return-value"></a>Dönüş Değeri

[Bir hash_multiset](../standard-library/hash-multiset-class.md)son öğeyi yerine getiren konumu gideren bir konst çift yönlü yineleme. Eğer `hash_multiset` boşsa, `hash_multiset::cend == hash_multiset::begin`o zaman.

### <a name="remarks"></a>Açıklamalar

`cend`bir yineleyicinin sonuna ulaşıp ulaşmadığını test `hash_multiset`etmek için kullanılır. Döndürülen `cend` değer dereferenced olmamalıdır.

### <a name="example"></a>Örnek

```cpp
// hash_multiset_cend.cpp
// compile with: /EHsc
#include <hash_multiset>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_multiset <int> hs1;
   hash_multiset <int> :: const_iterator hs1_cIter;

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

## <a name="hash_multisetclear"></a><a name="clear"></a>hash_multiset::açık

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multiset Sınıf](../standard-library/unordered-multiset-class.md).

Bir hash_multiset tüm öğelerini siler.

```cpp
void clear();
```

### <a name="remarks"></a>Açıklamalar

### <a name="example"></a>Örnek

```cpp
// hash_multiset_clear.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_multiset <int> hms1;

   hms1.insert( 1 );
   hms1.insert( 2 );

   cout << "The size of the hash_multiset is initially " << hms1.size( )
        << "." << endl;

   hms1.clear( );
   cout << "The size of the hash_multiset after clearing is "
        << hms1.size( ) << "." << endl;
}
```

```Output
The size of the hash_multiset is initially 2.
The size of the hash_multiset after clearing is 0.
```

## <a name="hash_multisetconst_iterator"></a><a name="const_iterator"></a>hash_multiset:const_iterator

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multiset Sınıf](../standard-library/unordered-multiset-class.md).

hash_multiset bir **const** öğeyi okuyabilen çift yönlü bir yineleme sağlayan bir tür.

```cpp
typedef list<typename Traits::value_type, typename Traits::allocator_type>::const_iterator const_iterator;
```

### <a name="remarks"></a>Açıklamalar

Bir `const_iterator` tür, bir öğenin değerini değiştirmek için kullanılamaz.

### <a name="example"></a>Örnek

Bir `const_iterator`örnek kullanarak [başlamak](#begin) için örneğe bakın.

## <a name="hash_multisetconst_pointer"></a><a name="const_pointer"></a>hash_multiset:const_pointer

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multiset Sınıf](../standard-library/unordered-multiset-class.md).

bir hash_multiset bir **const** öğesi için işaretçi sağlayan bir tür.

```cpp
typedef list<typename _Traits::value_type, typename _Traits::allocator_type>::const_pointer const_pointer;
```

### <a name="remarks"></a>Açıklamalar

Bir `const_pointer` tür, bir öğenin değerini değiştirmek için kullanılamaz.

Çoğu durumda, bir **const** hash_multiset nesnesindeki öğelere erişmek için bir [const_iterator](#const_iterator) kullanılmalıdır.

## <a name="hash_multisetconst_reference"></a><a name="const_reference"></a>hash_multiset:const_reference

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multiset Sınıf](../standard-library/unordered-multiset-class.md).

**Const** işlemleri okumak ve gerçekleştirmek için hash_multiset depolanan **bir const** öğesine başvuru sağlayan bir tür.

```cpp
typedef list<typename _Traits::value_type, typename _Traits::allocator_type>::const_reference const_reference;
```

### <a name="remarks"></a>Açıklamalar

### <a name="example"></a>Örnek

```cpp
// hash_multiset_const_reference.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_multiset <int> hms1;

   hms1.insert( 10 );
   hms1.insert( 20 );

   // Declare and initialize a const_reference &Ref1
   // to the 1st element
   const int &Ref1 = *hms1.begin( );

   cout << "The first element in the hash_multiset is "
        << Ref1 << "." << endl;

   // The following line would cause an error because the
   // const_reference cannot be used to modify the hash_multiset
   // Ref1 = Ref1 + 5;
}
```

```Output
The first element in the hash_multiset is 10.
```

## <a name="hash_multisetconst_reverse_iterator"></a><a name="const_reverse_iterator"></a>hash_multiset:const_reverse_iterator

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multiset Sınıf](../standard-library/unordered-multiset-class.md).

hash_multiset herhangi bir **const** öğeyi okuyabilen çift yönlü bir yineleme sağlayan bir tür.

```cpp
typedef list<typename Traits::value_type, typename Traits::allocator_type>::const_reverse_iterator const_reverse_iterator;
```

### <a name="remarks"></a>Açıklamalar

Bir `const_reverse_iterator` tür bir öğenin değerini değiştiremez ve hash_multiset ters olarak yinelemek için kullanılır.

### <a name="example"></a>Örnek

Nasıl beyan edilip kullanılacağına bir örnek için `const_reverse_iterator` [rend](#rend) örneğine bakın.

## <a name="hash_multisetcount"></a><a name="count"></a>hash_multiset::say

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multiset Sınıf](../standard-library/unordered-multiset-class.md).

Anahtarı parametre yle belirtilen anahtarla eşleşen bir hash_multiset öğe sayısını verir.

```cpp
size_type count(const Key& key) const;
```

### <a name="parameters"></a>Parametreler

*Anahtar*\
hash_multiset eşleşecek öğelerin anahtarı.

### <a name="return-value"></a>Dönüş Değeri

Parametre belirtilen anahtar ile hash_multiset elemanların sayısı.

### <a name="remarks"></a>Açıklamalar

Üye işlev aşağıdaki aralıktaki eleman sayısını döndürür:

\[lower_bound *(anahtar),* upper_bound *(anahtar)*).

### <a name="example"></a>Örnek

Aşağıdaki örnek, hash_multiset::count üye işlevinin kullanımını göstermektedir.

```cpp
// hash_multiset_count.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
    using namespace std;
    using namespace stdext;
    hash_multiset<int> hms1;
    hash_multiset<int>::size_type i;

    hms1.insert(1);
    hms1.insert(1);

    // Keys do not need to be unique in hash_multiset,
    // so duplicates may exist.
    i = hms1.count(1);
    cout << "The number of elements in hms1 with a sort key of 1 is: "
         << i << "." << endl;

    i = hms1.count(2);
    cout << "The number of elements in hms1 with a sort key of 2 is: "
         << i << "." << endl;
}
```

```Output
The number of elements in hms1 with a sort key of 1 is: 2.
The number of elements in hms1 with a sort key of 2 is: 0.
```

## <a name="hash_multisetcrbegin"></a><a name="crbegin"></a>hash_multiset::crbegin

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multiset Sınıf](../standard-library/unordered-multiset-class.md).

Ters hash_multiset ilk öğeyi ele alan bir const yineleyici döndürür.

```cpp
const_reverse_iterator crbegin() const;
```

### <a name="return-value"></a>Dönüş Değeri

Ters [hash_multiset](../standard-library/hash-multiset-class.md) ilk öğeyi ele alan veya ters çevrilmemiş `hash_multiset`son öğeyi ele alan const ters yönlü bir yineleme.

### <a name="remarks"></a>Açıklamalar

`crbegin`hash_multiset gibi ters `hash_multiset` ile [kullanılır::begin](#begin) ile `hash_multiset`kullanılır .

İade değeri ile `crbegin` `hash_multiset` nesne değiştirilemez.

`crbegin``hash_multiset` geriye doğru doğrulamak için kullanılabilir.

### <a name="example"></a>Örnek

```cpp
// hash_multiset_crbegin.cpp
// compile with: /EHsc
#include <hash_multiset>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_multiset <int> hs1;
   hash_multiset <int>::const_reverse_iterator hs1_crIter;

   hs1.insert( 10 );
   hs1.insert( 20 );
   hs1.insert( 30 );

   hs1_crIter = hs1.crbegin( );
   cout << "The first element in the reversed hash_multiset is "
        << *hs1_crIter << "." << endl;
}
```

```Output
The first element in the reversed hash_multiset is 30.
```

## <a name="hash_multisetcrend"></a><a name="crend"></a>hash_multiset::crend

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multiset Sınıf](../standard-library/unordered-multiset-class.md).

Ters hash_multiset son öğeyi yerine getiren konumu gideren bir const yineleyici döndürür.

```cpp
const_reverse_iterator crend() const;
```

### <a name="return-value"></a>Dönüş Değeri

Ters [hash_multiset](../standard-library/hash-multiset-class.md) 'deki son öğeyi başaran konumu (ters çevrilmemiş `hash_multiset`ilk öğeden önce gelen konum) gideren const ters çift yönlü yineleme.

### <a name="remarks"></a>Açıklamalar

`crend`hash_multiset gibi ters `hash_multiset` bir ile [kullanılır::end](#end) `hash_multiset`ile kullanılır .

İade değeri ile `crend` `hash_multiset` nesne değiştirilemez.

`crend`ters yineleyicinin hash_multiset sonuna ulaşıp ulaşmadığını test etmek için kullanılabilir.

### <a name="example"></a>Örnek

```cpp
// hash_multiset_crend.cpp
// compile with: /EHsc
#include <hash_multiset>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_multiset <int> hs1;
   hash_multiset <int>::const_reverse_iterator hs1_crIter;

   hs1.insert( 10 );
   hs1.insert( 20 );
   hs1.insert( 30 );

   hs1_crIter = hs1.crend( );
   hs1_crIter--;
   cout << "The last element in the reversed hash_multiset is "
        << *hs1_crIter << "." << endl;
}
```

```Output
The last element in the reversed hash_multiset is 10.
```

## <a name="hash_multisetdifference_type"></a><a name="difference_type"></a>hash_multiset::difference_type

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multiset Sınıf](../standard-library/unordered-multiset-class.md).

Aynı hash_multiset içindeki öğeleri ele alan iki yineleyici arasındaki farkı sağlayan imzalı bir tamsayı türü.

```cpp
typedef list<typename _Traits::value_type, typename _Traits::allocator_type>::difference_type difference_type;
```

### <a name="remarks"></a>Açıklamalar

Kapsayıcının `difference_type` yineleyicileri arasından çıkarılırken veya artarken döndürülen türdür. Genellikle `difference_type` yinelemeciler `first` arasındaki aralıktaki öğe sayısını temsil `first` `last`etmek için kullanılır [ `last`, ) ve `first` , tarafından işaret edilen öğe ve elemanların aralığı kadar, ancak dahil değil, öğe tarafından `last`işaret .

Küme gibi `difference_type` geri dönüşümlü kapsayıcılar tarafından desteklenen çift yönlü yineleyiciler sınıfını içeren bir giriş yineleyicinin gereksinimlerini karşılayan tüm yineleyiciler için kullanılabilir olmasına rağmen. Yineleyiciler arasındaki çıkarma yalnızca vektör veya deque gibi rasgele erişim kapsayıcısı tarafından sağlanan rasgele erişim yineleyicileri tarafından desteklenir.

### <a name="example"></a>Örnek

```cpp
// hash_multiset_diff_type.cpp
// compile with: /EHsc
#include <iostream>
#include <hash_set>
#include <algorithm>

int main( )
{
   using namespace std;
   using namespace stdext;

   hash_multiset <int> hms1;
   hash_multiset <int>::iterator hms1_Iter, hms1_bIter, hms1_eIter;

   hms1.insert( 20 );
   hms1.insert( 10 );

   // hash_multiset elements need not be unique
   hms1.insert( 20 );

   hms1_bIter = hms1.begin( );
   hms1_eIter = hms1.end( );

   hash_multiset <int>::difference_type   df_typ5, df_typ10,
        df_typ20;

   df_typ5 = count( hms1_bIter, hms1_eIter, 5 );
   df_typ10 = count( hms1_bIter, hms1_eIter, 10 );
   df_typ20 = count( hms1_bIter, hms1_eIter, 20 );

   // The keys & hence the elements of a hash_multiset
   // need not be unique and may occur multiple times
   cout << "The number '5' occurs " << df_typ5
        << " times in hash_multiset hms1.\n";
   cout << "The number '10' occurs " << df_typ10
        << " times in hash_multiset hms1.\n";
   cout << "The number '20' occurs " << df_typ20
        << " times in hash_multiset hms1.\n";

   // Count the number of elements in a hash_multiset
   hash_multiset <int>::difference_type  df_count = 0;
   hms1_Iter = hms1.begin( );
   while ( hms1_Iter != hms1_eIter)
   {
      df_count++;
      hms1_Iter++;
   }

   cout << "The number of elements in the hash_multiset hms1 is "
        << df_count << "." << endl;
}
```

```Output
The number '5' occurs 0 times in hash_multiset hms1.
The number '10' occurs 1 times in hash_multiset hms1.
The number '20' occurs 2 times in hash_multiset hms1.
The number of elements in the hash_multiset hms1 is 3.
```

## <a name="hash_multisetemplace"></a><a name="emplace"></a>hash_multiset::emplace

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multiset Sınıf](../standard-library/unordered-multiset-class.md).

Yerinde inşa edilmiş bir öğeyi hash_multiset içine ekler.

```cpp
template <class ValTy>
iterator insert(ValTy&& val);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|-|-|
|*Val*|Zaten bu öğeyi veya daha genel [hash_multiset](../standard-library/hash-multiset-class.md) olarak, `hash_multiset` anahtarı eşdeğer sıralanmış bir öğeyi içermediği sürece hash_multiset eklenecek bir öğenin değeri.|

### <a name="return-value"></a>Dönüş Değeri

Üye `emplace` işlev, yeni öğenin eklendiği konumu gösteren bir yineleyici döndürür.

### <a name="remarks"></a>Açıklamalar

### <a name="example"></a>Örnek

```cpp
// hash_multiset_emplace.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>
#include <string>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_multiset<string> hms3;
   string str1("a");

   hms3.emplace(move(str1));
   cout << "After the emplace insertion, hms3 contains "
      << *hms3.begin() << "." << endl;
}
```

```Output
After the emplace insertion, hms3 contains a.
```

## <a name="hash_multisetemplace_hint"></a><a name="emplace_hint"></a>hash_multiset:emplace_hint

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multiset Sınıf](../standard-library/unordered-multiset-class.md).

Yerinde oluşturulmuş bir öğeyi bir hash_multiset, bir yerleşim ipucuyla ekler.

```cpp
template <class ValTy>
iterator insert(
    const_iterator where,
    ValTy&& val);
```

### <a name="parameters"></a>Parametreler

*Val*\
Zaten bu öğeyi veya daha genel [hash_multiset](../standard-library/hash-multiset-class.md) olarak, `hash_multiset` anahtarı eşdeğer sıralanmış bir öğeyi içermediği sürece hash_multiset eklenecek bir öğenin değeri.

*Nerede*\
Doğru ekleme noktasını aramaya başlamak için yer. (Ekleme, giriş noktası hemen *nereye*giderse, logaritmik zaman yerine, amortismana tabi sabit bir süre içinde oluşabilir.)

### <a name="return-value"></a>Dönüş Değeri

[hash_multiset::emplace](#emplace) üye işlevi, yeni öğenin eklendiği konumu gösteren bir yineleyici `hash_multiset`döndürür.

### <a name="remarks"></a>Açıklamalar

Ekleme, giriş noktası hemen *nereye*giderse, logaritmik zaman yerine, amortismana tabi sabit bir süre içinde oluşabilir.

### <a name="example"></a>Örnek

```cpp
// hash_multiset_emplace_hint.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>
#include <string>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_multiset<string> hms1;
   string str1("a");

   hms1.insert(hms1.begin(), move(str1));
   cout << "After the emplace insertion, hms1 contains "
      << *hms1.begin() << "." << endl;
}
```

```Output
After the emplace insertion, hms1 contains a.
```

## <a name="hash_multisetempty"></a><a name="empty"></a>hash_multiset::boş

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multiset Sınıf](../standard-library/unordered-multiset-class.md).

hash_multiset boşolup hash_multiset.

```cpp
bool empty() const;
```

### <a name="return-value"></a>Dönüş Değeri

hash_multiset boşsa **doğrudur;** hash_multiset boş değilse **yanlış.**

### <a name="remarks"></a>Açıklamalar

### <a name="example"></a>Örnek

```cpp
// hash_multiset_empty.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_multiset <int> hms1, hms2;
   hms1.insert ( 1 );

   if ( hms1.empty( ) )
      cout << "The hash_multiset hms1 is empty." << endl;
   else
      cout << "The hash_multiset hms1 is not empty." << endl;

   if ( hms2.empty( ) )
      cout << "The hash_multiset hms2 is empty." << endl;
   else
      cout << "The hash_multiset hms2 is not empty." << endl;
}
```

```Output
The hash_multiset hms1 is not empty.
The hash_multiset hms2 is empty.
```

## <a name="hash_multisetend"></a><a name="end"></a>hash_multiset::sonu

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multiset Sınıf](../standard-library/unordered-multiset-class.md).

Hash_multiset son öğeyi yerine getiren konumu adresleyen bir yineleyici döndürür.

```cpp
const_iterator end() const;

iterator end();
```

### <a name="return-value"></a>Dönüş Değeri

Bir hash_multiset son öğesini yerine getiren konumu ele alan çift yönlü bir yineleyici. hash_multiset boşsa, hash_multiset::end == hash_multiset::begin.

### <a name="remarks"></a>Açıklamalar

`end`bir yineleyicinin hash_multiset sonuna ulaşıp ulaşmadığını test etmek için kullanılır. Döndürülen `end` değer dereferenced olmamalıdır.

### <a name="example"></a>Örnek

```cpp
// hash_multiset_end.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_multiset <int> hms1;
   hash_multiset <int> :: iterator hms1_Iter;
   hash_multiset <int> :: const_iterator hms1_cIter;

   hms1.insert( 1 );
   hms1.insert( 2 );
   hms1.insert( 3 );

   hms1_Iter = hms1.end( );
   hms1_Iter--;
   cout << "The last element of hms1 is " << *hms1_Iter << endl;

   hms1.erase( hms1_Iter );

   // The following 3 lines would err because the iterator is const
   // hms1_cIter = hms1.end( );
   // hms1_cIter--;
   // hms1.erase( hms1_cIter );

   hms1_cIter = hms1.end( );
   hms1_cIter--;
   cout << "The last element of hms1 is now " << *hms1_cIter << endl;
}
```

```Output
The last element of hms1 is 3
The last element of hms1 is now 2
```

## <a name="hash_multisetequal_range"></a><a name="equal_range"></a>hash_multiset:equal_range

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multiset Sınıf](../standard-library/unordered-multiset-class.md).

Belirtilen bir anahtardan büyük bir anahtarla hash_multiset ilk öğeye ve anahtara eşit veya daha büyük bir anahtarla hash_multiset ilk öğeye sırasıyla bir çift yineleyici döndürür.

```cpp
pair <const_iterator, const_iterator> equal_range (const Key& key) const;

pair <iterator, iterator> equal_range (const Key& key);
```

### <a name="parameters"></a>Parametreler

*Anahtar*\
Aralanan hash_multiset öğenin tür anahtarıyla karşılaştırılacak bağımsız değişken anahtarı.

### <a name="return-value"></a>Dönüş Değeri

İlkanahtarın [lower_bound,](#lower_bound) ikincisi anahtarın [upper_bound](#upper_bound) olduğu bir çift yineleyici.

Üye işlev tarafından döndürülen bir `pr` çiftin ilk yineleyicisine `pr`erişmek için. **ilk** ve alt sınır yineleyici dereference \*için, kullanın ( `pr`. **ilk**). Üye işlev tarafından döndürülen bir `pr` çiftin ikinci yineleyicisine `pr`erişmek için. **ikinci** ve üst sınır yineleyici dereference \*için, kullanın ( `pr`. **ikinci**).

### <a name="example"></a>Örnek

```cpp
// hash_multiset_equal_range.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   typedef hash_multiset<int> IntHSet;
   IntHSet hms1;
   hash_multiset <int> :: const_iterator hms1_RcIter;

   hms1.insert( 10 );
   hms1.insert( 20 );
   hms1.insert( 30 );

   pair <IntHSet::const_iterator, IntHSet::const_iterator> p1, p2;
   p1 = hms1.equal_range( 20 );

   cout << "The upper bound of the element with "
        << "a key of 20\nin the hash_multiset hms1 is: "
        << *(p1.second) << "." << endl;

   cout << "The lower bound of the element with "
        << "a key of 20\nin the hash_multiset hms1 is: "
        << *(p1.first) << "." << endl;

   // Compare the upper_bound called directly
   hms1_RcIter = hms1.upper_bound( 20 );
   cout << "A direct call of upper_bound( 20 ) gives "
        << *hms1_RcIter << "," << endl
        << "matching the 2nd element of the pair"
        << " returned by equal_range( 20 )." << endl;

   p2 = hms1.equal_range( 40 );

   // If no match is found for the key,
   // both elements of the pair return end( )
   if ( ( p2.first == hms1.end( ) )
      && ( p2.second == hms1.end( ) ) )
      cout << "The hash_multiset hms1 doesn't have an element "
           << "with a key less than 40." << endl;
   else
      cout << "The element of hash_multiset hms1"
           << "with a key >= 40 is: "
           << *(p1.first) << "." << endl;
}
```

```Output
The upper bound of the element with a key of 20
in the hash_multiset hms1 is: 30.
The lower bound of the element with a key of 20
in the hash_multiset hms1 is: 20.
A direct call of upper_bound( 20 ) gives 30,
matching the 2nd element of the pair returned by equal_range( 20 ).
The hash_multiset hms1 doesn't have an element with a key less than 40.
```

## <a name="hash_multiseterase"></a><a name="erase"></a>hash_multiset::silme

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multiset Sınıf](../standard-library/unordered-multiset-class.md).

Hash_multiset bir öğeyi veya bir öğe aralığını belirtilen konumlardan kaldırır veya belirtilen anahtarla eşleşen öğeleri kaldırır.

```cpp
iterator erase(iterator where);

iterator erase(iterator first, iterator last);

size_type erase(const key_type& key);
```

### <a name="parameters"></a>Parametreler

*Nerede*\
Hash_multiset kaldırılacak öğenin konumu.

*Ilk*\
hash_multiset kaldırılan ilk öğenin konumu.

*Son*\
hash_multiset kaldırılan son öğenin hemen ötesine yerleştirin.

*Anahtar*\
hash_multiset kaldırılacak öğelerin anahtarı.

### <a name="return-value"></a>Dönüş Değeri

İlk iki üye işlev için, kaldırılan öğelerin ötesinde kalan ilk öğeyi belirleyen çift yönlü bir yineleyici veya böyle bir öğe yoksa hash_multiset sonuna işaretçi. Üçüncü üye işlev için, hash_multiset kaldırılan öğelerin sayısı.

### <a name="remarks"></a>Açıklamalar

Üye işlevler hiçbir zaman bir özel durum atmaz.

### <a name="example"></a>Örnek

Aşağıdaki örnek, hash_multiset::delete üye işlevinin kullanımını göstermektedir.

```cpp
// hash_multiset_erase.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main()
{
    using namespace std;
    using namespace stdext;
    hash_multiset<int> hms1, hms2, hms3;
    hash_multiset<int> :: iterator pIter, Iter1, Iter2;
    int i;
    hash_multiset<int>::size_type n;

    for (i = 1; i < 5; i++)
    {
        hms1.insert(i);
        hms2.insert(i * i);
        hms3.insert(i - 1);
    }

    // The 1st member function removes an element at a given position
    Iter1 = ++hms1.begin();
    hms1.erase(Iter1);

    cout << "After the 2nd element is deleted,\n"
         << "the hash_multiset hms1 is:" ;
    for (pIter = hms1.begin(); pIter != hms1.end(); pIter++)
        cout << " " << *pIter;
    cout << "." << endl;

    // The 2nd member function removes elements
    // in the range [ first,  last)
    Iter1 = ++hms2.begin();
    Iter2 = --hms2.end();
    hms2.erase(Iter1, Iter2);

    cout << "After the middle two elements are deleted,\n"
         << "the hash_multiset hms2 is:" ;
    for (pIter = hms2.begin(); pIter != hms2.end(); pIter++)
        cout << " " << *pIter;
    cout << "." << endl;

    // The 3rd member function removes elements with a given  key
    n = hms3.erase(2);

    cout << "After the element with a key of 2 is deleted,\n"
         << "the hash_multiset hms3 is:" ;
    for (pIter = hms3.begin(); pIter != hms3.end(); pIter++)
        cout << " " << *pIter;
    cout << "." << endl;

    // The 3rd member function returns the number of elements removed
    cout << "The number of elements removed from hms3 is: "
         << n << "." << endl;

    // The dereferenced iterator can also be used to specify a key
    Iter1 = ++hms3.begin();
    hms3.erase(Iter1);

    cout << "After another element with a key "
         << "equal to that of the 2nd element\n"
         << "is deleted, the hash_multiset hms3 is:" ;
    for (pIter = hms3.begin(); pIter != hms3.end(); pIter++)
        cout << " " << *pIter;
    cout << "." << endl;
}
```

```Output
After the 2nd element is deleted,
the hash_multiset hms1 is: 1 3 4.
After the middle two elements are deleted,
the hash_multiset hms2 is: 16 4.
After the element with a key of 2 is deleted,
the hash_multiset hms3 is: 0 1 3.
The number of elements removed from hms3 is: 1.
After another element with a key equal to that of the 2nd element
is deleted, the hash_multiset hms3 is: 0 3.
```

## <a name="hash_multisetfind"></a><a name="find"></a>hash_multiset::bul

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multiset Sınıf](../standard-library/unordered-multiset-class.md).

Belirli bir anahtara eşdeğer anahtara sahip bir hash_multiset öğenin konumunu ele alan bir yineleyici döndürür.

```cpp
iterator find(const Key& key);

const_iterator find(const Key& key) const;
```

### <a name="parameters"></a>Parametreler

*Anahtar*\
Aralanan hash_multiset öğenin tür anahtarıyla eşleşecek bağımsız değişken anahtarı.

### <a name="return-value"></a>Dönüş Değeri

Belirli bir anahtara eşdeğer bir öğenin konumunu ele alan veya anahtar için eşleşme bulunamazsa hash_multiset son öğeyi yerine getiren konumu ele alan bir [yineleyici](#iterator) veya [const_iterator.](#const_iterator)

### <a name="remarks"></a>Açıklamalar

Üye işlev, hash_multiset bir öğeyi ele alan ve sıra anahtarı `equivalent` bağımsız değişken anahtarıolan ve karşılaştırılabilirlik ilişkisine dayalı bir sıralamayı başlatan ikili bir yüklem altında olan bir öğeyi döndürür.

Bir `const_iterator`, hash_multiset `find` nesnesinin geri dönüş değeri ne olursa olsun değiştirilemez. Bir `iterator`, hash_multiset `find` nesnesinin geri dönüş değeri ne olursa olsun değiştirilebilir.

### <a name="example"></a>Örnek

```cpp
// hash_multiset_find.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_multiset <int> hms1;
   hash_multiset <int> :: const_iterator hms1_AcIter, hms1_RcIter;

   hms1.insert( 10 );
   hms1.insert( 20 );
   hms1.insert( 30 );

   hms1_RcIter = hms1.find( 20 );
   cout << "The element of hash_multiset hms1 with a key of 20 is: "
        << *hms1_RcIter << "." << endl;

   hms1_RcIter = hms1.find( 40 );

   // If no match is found for the key, end( ) is returned
   if ( hms1_RcIter == hms1.end( ) )
      cout << "The hash_multiset hms1 doesn't have an element "
           << "with a key of 40." << endl;
   else
      cout << "The element of hash_multiset hms1 with a key of 40 is: "
           << *hms1_RcIter << "." << endl;

   // The element at a specific location in the hash_multiset can be found
   // by using a dereferenced iterator addressing the location
   hms1_AcIter = hms1.end( );
   hms1_AcIter--;
   hms1_RcIter = hms1.find( *hms1_AcIter );
   cout << "The element of hms1 with a key matching "
        << "that of the last element is: "
        << *hms1_RcIter << "." << endl;
}
```

```Output
The element of hash_multiset hms1 with a key of 20 is: 20.
The hash_multiset hms1 doesn't have an element with a key of 40.
The element of hms1 with a key matching that of the last element is: 30.
```

## <a name="hash_multisetget_allocator"></a><a name="get_allocator"></a>hash_multiset::get_allocator

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multiset Sınıf](../standard-library/unordered-multiset-class.md).

hash_multiset oluşturmak için kullanılan ayırıcı nesnenin bir kopyasını döndürür.

```cpp
Allocator get_allocator() const;
```

### <a name="return-value"></a>Dönüş Değeri

Sınıfın şablon parametresi olan belleği `Allocator`yönetmek için hash_multiset tarafından kullanılan ayırıcı.

Daha fazla `Allocator`bilgi için [hash_multiset Sınıfı](../standard-library/hash-multiset-class.md) konusunun Açıklamalar bölümüne bakın.

### <a name="remarks"></a>Açıklamalar

hash_multiset sınıfının ayırıcıları sınıfın depolamayı nasıl yönettiğini belirtir. C++ Standart Kitaplık kapsayıcı sınıfları ile birlikte verilen varsayılan ayırıcılar çoğu programlama gereksinimleri için yeterlidir. Kendi ayırıcı sınıfınızı yazmak ve kullanmak gelişmiş bir C++ konusudur.

### <a name="example"></a>Örnek

```cpp
// hash_multiset_get_allocator.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;

   // The following lines declare objects
   // that use the default allocator.
   hash_multiset <int, hash_compare <int, less<int> > > hms1;
   hash_multiset <int, hash_compare <int, greater<int> > > hms2;
   hash_multiset <double, hash_compare <double,
      less<double> >, allocator<double> > hms3;

   hash_multiset <int, hash_compare <int,
      greater<int> > >::allocator_type hms2_Alloc;
   hash_multiset <double>::allocator_type hms3_Alloc;
   hms2_Alloc = hms2.get_allocator( );

   cout << "The number of integers that can be allocated"
        << endl << "before free memory is exhausted: "
        << hms1.max_size( ) << "." << endl;

   cout << "The number of doubles that can be allocated"
        << endl << "before free memory is exhausted: "
        << hms3.max_size( ) <<  "." << endl;

   // The following lines create a hash_multiset hms4
   // with the allocator of hash_multiset hms1.
   hash_multiset <int>::allocator_type hms4_Alloc;
   hash_multiset <int> hms4;
   hms4_Alloc = hms2.get_allocator( );

   // Two allocators are interchangeable if
   // storage allocated from each can be
   // deallocated by the other
   if( hms2_Alloc == hms4_Alloc )
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

## <a name="hash_multisethash_multiset"></a><a name="hash_multiset"></a>hash_multiset:hash_multiset

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multiset Sınıf](../standard-library/unordered-multiset-class.md).

Boş olan `hash_multiset` veya başka `hash_multiset`bir şeyin tamamının veya bir kısmının kopyası olan bir yapı.

```cpp
hash_multiset();

explicit hash_multiset(
    const Traits& Comp);

hash_multiset(
    const Traits& Comp,
    const Allocator& Al);

hash_multiset(
    const hash_multiset<Key, Traits, Allocator>& Right);

hash_multiset(
    hash_multiset&& Right
};
hash_multiset (initializer_list<Type> IList);

hash_multiset(
    initializer_list<Tu[e> IList, const Compare& Comp):
hash_multiset(
    initializer_list<Type> IList, const Compare& Comp, const Allocator& Al);

template <class InputIterator>
hash_multiset(
    InputIterator first,
    InputIterator last);

template <class InputIterator>
hash_multiset(
    InputIterator first,
    InputIterator last,
    const Traits& Comp);

template <class InputIterator>
hash_multiset(
    InputIterator first,
    InputIterator last,
    const Traits& Comp,
    const Allocator& Al);
```

### <a name="parameters"></a>Parametreler

*Al*\
Varsayılan olarak bu `hash_multiset` nesne için kullanılacak depolama ayırıcı `Allocator`sınıfı.

*Comp*\
'deki öğeleri `const Traits` sıralamak için kullanılan `hash_multiset`türün karşılaştırma `hash_compare`işlevi , hangi varsayılan .

*Doğru*\
Hangi `hash_multiset` inşa `hash_multiset` bir kopyası olmaktır.

*Ilk*\
Kopyalanacak öğeler aralığındaki ilk öğenin konumu.

*Son*\
İlk öğenin kopyalanacak öğe aralığının ötesindeki konumu.

*ılist*\
Kopyalanacak öğeleri içeren initializer_list.

### <a name="remarks"></a>Açıklamalar

Tüm oluşturucular için bellek depolama yöneten `hash_multiset` ve daha sonra hash_multiset arayarak döndürülebilir ayırıcı nesne türü depolar::get_allocator. [hash_multiset::get_allocator](#get_allocator) Ayırıcı parametresi genellikle sınıf bildirimlerinde ve alternatif ayırıcıların yerine kullanılan ön işleme makrolarında atlanır.

Tüm yapıcılar hash_multisets.

Tüm oluşturucular, anahtarları arasında `Traits` bir düzen oluşturmak için kullanılan `hash_multiset` ve daha sonra hash_multiset arayarak döndürülebilecek bir işlev nesnesi depolar:key_comp. [hash_multiset::key_comp](#key_comp) [hash_multiset Sınıfı](../standard-library/hash-multiset-class.md) `Traits` konusu hakkında daha fazla bilgi için bkz.

İlk üç oluşturucu boş bir `hash_multiset`baş harf belirtir , ikinci karşılaştırma fonksiyonunun türünü belirten *(Comp*) elemanların sırasını oluştururken kullanılacak ve üçüncü açıkça kullanılacak ayırıcı türü *(Al)* belirterek. Anahtar kelime **açık** otomatik tür dönüştürme belirli türleri bastırır.

Dördüncü yapıcı hareket `hash_multiset` `Right`eder.

Beşinci, altıncı ve yedinci yapıcılar initializer_list kullanırlar.

Son üç oluşturucu, karşılaştır `first`ve `last`ayırıcı `hash_multiset` sınıfın karşılaştırma işlevinin türünü belirtirken artan açıklıkla bir aralığı [, ) kopyalar.

Karma küme kapsayıcısındaki öğelerin gerçek sırası karma işlevine, sıralama işlevine ve karma tablonun geçerli boyutuna bağlıdır ve genel olarak, yalnızca sipariş işlevi tarafından belirlendiği küme kapsayıcısıyla olduğu gibi tahmin edilemez.

## <a name="hash_multisetinsert"></a><a name="insert"></a>hash_multiset::ekle

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multiset Sınıf](../standard-library/unordered-multiset-class.md).

Bir öğeyi veya bir öğe aralığını hash_multiset ekler.

```cpp
iterator insert(
    const Type& value);

iterator insert(
    iterator where,
    const Type& Al);

void insert(
    initializer_list<Type> IList);

iterator insert(
    const Type& value);

iterator insert(
    Iterator where,
    const Type& value);

template <class InputIterator>
void insert(
    InputIterator first,
    InputIterator last);

template <class ValTy>
iterator insert(
    ValTy&& value);

template <class ValTy>
iterator insert(
    const_iterator where,
    ValTy&& value);
```

### <a name="parameters"></a>Parametreler

*Değer*\
hash_multiset zaten bu öğeyi veya daha genel olarak, anahtarı eşdeğer sıralanmış bir öğeyi içermediği sürece, hash_multiset eklenecek bir öğenin değeri.

*Nerede*\
Doğru ekleme noktasını aramaya başlamak için yer. (Ekleme, giriş noktası hemen *nereye*giderse, logaritmik zaman yerine, amortismana tabi sabit bir süre içinde oluşabilir.)

*Ilk*\
Bir hash_multiset kopyalanacak ilk öğenin konumu.

*Son*\
Bir hash_multiset kopyalanacak son öğenin hemen ötesindeki konum.

*ılist*\
Kopyalanması gereken öğeleri içeren initializer_list.

### <a name="return-value"></a>Dönüş Değeri

İlk iki ekle üye işlevi, yeni öğenin eklendiği konumu gösteren bir yineleyici döndürür.

Sonraki üç üye işlev bir initializer_list kullanır.

Üçüncü üye işlev, öğe değerlerinin dizisini, belirli bir hash_multiset aralığındaki bir yineleme `first`[, `last`) tarafından adreslenen her öğeye karşılık gelen bir hash_multiset ekler.

### <a name="remarks"></a>Açıklamalar

Ekleme ekleme noktası hemen *nereye*aşağıdaki ise, logaritmik zaman yerine, eklemek ipucu sürümü için amortismana tabi sabit zaman oluşabilir.

## <a name="hash_multisetiterator"></a><a name="iterator"></a>hash_multiset::iterator

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multiset Sınıf](../standard-library/unordered-multiset-class.md).

bir hash_multiset herhangi bir öğeyi okuyabilen veya değiştirebilen çift yönlü bir yineleme sağlayan bir tür.

```cpp
typedef list<typename Traits::value_type, typename Traits::allocator_type>::iterator iterator;
```

### <a name="remarks"></a>Açıklamalar

Bir `iterator` tür, bir öğenin değerini değiştirmek için kullanılabilir.

### <a name="example"></a>Örnek

Nasıl bildirilir ve kullanılacağına `iterator`bir örnek için [bkz.](#begin)

## <a name="hash_multisetkey_comp"></a><a name="key_comp"></a>hash_multiset:key_comp

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multiset Sınıf](../standard-library/unordered-multiset-class.md).

Hash_multiset anahtarları sipariş etmek için kullanılan karşılaştırma nesnesinin bir kopyasını alır.

```cpp
key_compare key_comp() const;
```

### <a name="return-value"></a>Dönüş Değeri

Karma ve kapsayıcının öğelerini sıralamak için kullanılan işlev nesnelerini içeren hash_multiset şablon parametre *Özellikleri'ni*döndürür.

*Özellikler* hakkında daha fazla bilgi için [hash_multiset Sınıfı](../standard-library/hash-multiset-class.md) konusuna bakın.

### <a name="remarks"></a>Açıklamalar

Depolanan nesne bir üye işlev tanımlar:

`bool operator<(const Key& _xVal, const Key& _yVal);`

önce yse ve sıralama `_yVal` sırasına eşit değilse doğru döndürür. **true** `_xVal`

Hem [key_compare](#key_compare) hem de [value_compare](#value_compare) şablon parametresi *Özellikleri*ile eş anlamlı olduğunu unutmayın. Her iki tür de, farklı oldukları hash_map ve hash_multimap sınıflarıyla uyumluluk için, aynı oldukları hash_multiset ve hash_multiset sınıfları için sağlanır.

### <a name="example"></a>Örnek

```cpp
// hash_multiset_key_comp.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;

   hash_multiset <int, hash_compare < int, less<int> > >hms1;
   hash_multiset<int, hash_compare < int, less<int> > >::key_compare kc1
          = hms1.key_comp( ) ;
   bool result1 = kc1( 2, 3 ) ;
   if( result1 == true )
   {
      cout << "kc1( 2,3 ) returns value of true, "
           << "where kc1 is the function object of hms1."
           << endl;
   }
   else
   {
      cout << "kc1( 2,3 ) returns value of false "
           << "where kc1 is the function object of hms1."
        << endl;
   }

   hash_multiset <int, hash_compare < int, greater<int> > > hms2;
   hash_multiset<int, hash_compare < int, greater<int> > >::key_compare
         kc2 = hms2.key_comp( ) ;
   bool result2 = kc2( 2, 3 ) ;
   if( result2 == true )
   {
      cout << "kc2( 2,3 ) returns value of true, "
           << "where kc2 is the function object of hms2."
           << endl;
   }
   else
   {
      cout << "kc2( 2,3 ) returns value of false, "
           << "where kc2 is the function object of hms2."
           << endl;
   }
}
```

## <a name="hash_multisetkey_compare"></a><a name="key_compare"></a>hash_multiset:key_compare

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multiset Sınıf](../standard-library/unordered-multiset-class.md).

İki işlev nesnesi sağlayan bir tür, bir hash_multiset iki öğe değerlerini karşılaştırabilen bir sınıf karşılaştırması ve öğeleri işleyen bir unary yüklemi.

```cpp
typedef Traits key_compare;
```

### <a name="remarks"></a>Açıklamalar

`key_compare`şablon parametresi *Özellikleri*ile eş anlamlıdır.

*Özellikler* hakkında daha fazla bilgi için [hash_multiset Sınıfı](../standard-library/hash-multiset-class.md) konusuna bakın.

Hem value_compare `key_compare` hem de şablon parametresi *Özellikleri*ile eş anlamlı olduğunu unutmayın. Her iki tür de, hash_map ve hash_multimap sınıflarıyla uyumluluğu için, farklı oldukları hash_set ve hash_multiset sınıfları için sağlanır.

### <a name="example"></a>Örnek

Nasıl bildirilir ve kullanılır? `key_compare` [key_comp](#key_comp)

## <a name="hash_multisetkey_type"></a><a name="key_type"></a>hash_multiset:key_type

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multiset Sınıf](../standard-library/unordered-multiset-class.md).

hash_multiset iki öğenin göreli sırasını belirlemek için sıralama anahtarlarını karşılaştırabilen bir işlev nesnesi sağlayan bir tür.

```cpp
typedef Key key_type;
```

### <a name="remarks"></a>Açıklamalar

`key_type`şablon parametre *Anahtarı*ile eş anlamlıdır.

Hem de `key_type` [value_type](../standard-library/hash-set-class.md#value_type) şablon parametresi *Anahtarı*ile eş anlamlı olduğunu unutmayın. Her iki tür de, farklı oldukları harita ve çok eşli sınıflarla uyumluluk için, aynı oldukları küme ve çok ayarlı sınıflar için sağlanır.

*Anahtar*hakkında daha fazla bilgi için [hash_multiset Sınıfı](../standard-library/hash-multiset-class.md) konusunun Açıklamalar bölümüne bakın.

### <a name="example"></a>Örnek

Nasıl bildirilir ve kullanılacağına `key_type`bir örnek için [value_type](#value_type) örneğe bakın.

## <a name="hash_multisetlower_bound"></a><a name="lower_bound"></a>hash_multiset:lower_bound

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multiset Sınıf](../standard-library/unordered-multiset-class.md).

Bir hash_multiset ilk öğeye, belirli bir anahtara eşit veya daha büyük bir anahtarla bir yineleyici döndürür.

```cpp
const_iterator lower_bound(const Key& key) const;

iterator lower_bound(const Key& key);
```

### <a name="parameters"></a>Parametreler

*Anahtar*\
Aralanan hash_multiset öğenin tür anahtarıyla karşılaştırılacak bağımsız değişken anahtarı.

### <a name="return-value"></a>Dönüş Değeri

Bir hash_multiset ilk öğenin konumunu bağımsız değişken anahtarına eşit veya daha büyük bir anahtarla ele alan veya anahtar için eşleşme yoksa hash_multiset'daki son öğeyi başaran konumu gideren bir [yineleyici](#iterator) veya [const_iterator.](#const_iterator)

### <a name="remarks"></a>Açıklamalar

### <a name="example"></a>Örnek

```cpp
// hash_multiset_lower_bound.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main() {
   using namespace std;
   using namespace stdext;
   hash_multiset <int> hms1;
   hash_multiset <int> :: const_iterator hms1_AcIter, hms1_RcIter;

   hms1.insert( 10 );
   hms1.insert( 20 );
   hms1.insert( 30 );

   hms1_RcIter = hms1.lower_bound( 20 );
   cout << "The element of hash_multiset hms1 with a key of 20 is: "
        << *hms1_RcIter << "." << endl;

   hms1_RcIter = hms1.lower_bound( 40 );

   // If no match is found for the key, end( ) is returned
   if ( hms1_RcIter == hms1.end( ) )
      cout << "The hash_multiset hms1 doesn't have an element "
           << "with a key of 40." << endl;
   else
      cout << "The element of hash_multiset hms1 with a key of 40 is: "
           << *hms1_RcIter << "." << endl;

   // An element at a specific location in the hash_multiset can be found
   // by using a dereferenced iterator that addresses the location
   hms1_AcIter = hms1.end( );
   hms1_AcIter--;
   hms1_RcIter = hms1.lower_bound( *hms1_AcIter );
   cout << "The element of hms1 with a key matching "
        << "that of the last element is: "
        << *hms1_RcIter << "." << endl;
}
```

## <a name="hash_multisetmax_size"></a><a name="max_size"></a>hash_multiset:max_size

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multiset Sınıf](../standard-library/unordered-multiset-class.md).

hash_multiset maksimum uzunluğu verir.

```cpp
size_type max_size() const;
```

### <a name="return-value"></a>Dönüş Değeri

Mümkün olan en fazla hash_multiset uzunluğu.

### <a name="remarks"></a>Açıklamalar

### <a name="example"></a>Örnek

```cpp
// hash_multiset_max_size.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_multiset <int> hms1;
   hash_multiset <int>::size_type i;

   i = hms1.max_size( );
   cout << "The maximum possible length "
        << "of the hash_multiset is " << i << "." << endl;
}
```

## <a name="hash_multisetoperator"></a><a name="op_eq"></a>hash_multiset::operator=

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multiset Sınıf](../standard-library/unordered-multiset-class.md).

hash_multiset öğelerini başka bir hash_multiset kopyasıyla değiştirir.

```cpp
hash_multiset& operator=(const hash_multiset& right);

hash_multiset& operator=(hash_multiset&& right);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|-|-|
|*Doğru*|[hash_multiset](../standard-library/hash-multiset-class.md) `hash_multiset`kopyalanıyor.|

### <a name="remarks"></a>Açıklamalar

Bir'deki varolan öğeleri `hash_multiset`silersonra , `operator=` *''nin* içeriğini `hash_multiset`kopyalar veya 'ye taşır.

### <a name="example"></a>Örnek

```cpp
// hash_multiset_operator_as.cpp
// compile with: /EHsc
#include <hash_multiset>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_multiset<int> v1, v2, v3;
   hash_multiset<int>::iterator iter;

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

## <a name="hash_multisetpointer"></a><a name="pointer"></a>hash_multiset::pointer

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multiset Sınıf](../standard-library/unordered-multiset-class.md).

hash_multiset bir öğeiçin işaretçi sağlayan bir tür.

```cpp
typedef list<typename _Traits::value_type, typename _Traits::allocator_type>::pointer pointer;
```

### <a name="remarks"></a>Açıklamalar

Bir `pointer` tür, bir öğenin değerini değiştirmek için kullanılabilir.

Çoğu durumda, çok ayarlı bir nesnedeki öğelere erişmek için bir [yineleyici](#iterator) kullanılmalıdır.

## <a name="hash_multisetrbegin"></a><a name="rbegin"></a>hash_multiset::rbegin

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multiset Sınıf](../standard-library/unordered-multiset-class.md).

Ters hash_multiset ilk öğeyi ele alan bir yineleyici döndürür.

```cpp
const_reverse_iterator rbegin() const;

reverse_iterator rbegin();
```

### <a name="return-value"></a>Dönüş Değeri

Ters hash_multiset ilk öğeyi ele alan veya tersine çevrilmemiş hash_multiset son öğesini ele alan ters çift yönlü bir yineleyici.

### <a name="remarks"></a>Açıklamalar

`rbegin`bir hash_multiset ile kullanılan [gibi](#begin) ters hash_multiset ile kullanılır.

Bir `const_reverse_iterator`,'ye `rbegin` atanırsa, hash_multiset nesnesi değiştirilemez. Bir `reverse_iterator`, hash_multiset `rbegin` nesnesinin geri dönüş değerine atanmışsa değiştirilebilir.

`rbegin`geriye doğru bir hash_multiset ile yinelemek için kullanılabilir.

### <a name="example"></a>Örnek

```cpp
// hash_multiset_rbegin.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_multiset <int> hms1;
   hash_multiset <int>::iterator hms1_Iter;
   hash_multiset <int>::reverse_iterator hms1_rIter;

   hms1.insert( 10 );
   hms1.insert( 20 );
   hms1.insert( 30 );

   hms1_rIter = hms1.rbegin( );
   cout << "The first element in the reversed hash_multiset is "
        << *hms1_rIter << "." << endl;

   // begin can be used to start an iteration
   // through a hash_multiset in a forward order
   cout << "The hash_multiset is: ";
   for ( hms1_Iter = hms1.begin( ) ; hms1_Iter != hms1.end( );
         hms1_Iter++ )
      cout << *hms1_Iter << " ";
   cout << endl;

   // rbegin can be used to start an iteration
   // through a hash_multiset in a reverse order
   cout << "The reversed hash_multiset is: ";
   for ( hms1_rIter = hms1.rbegin( ) ; hms1_rIter != hms1.rend( );
         hms1_rIter++ )
      cout << *hms1_rIter << " ";
   cout << endl;

   // A hash_multiset element can be erased by dereferencing to its key
   hms1_rIter = hms1.rbegin( );
   hms1.erase ( *hms1_rIter );

   hms1_rIter = hms1.rbegin( );
   cout << "After the erasure, the first element "
        << "in the reversed hash_multiset is "<< *hms1_rIter << "."
        << endl;
}
```

```Output
The first element in the reversed hash_multiset is 30.
The hash_multiset is: 10 20 30
The reversed hash_multiset is: 30 20 10
After the erasure, the first element in the reversed hash_multiset is 20.
```

## <a name="hash_multisetreference"></a><a name="reference"></a>hash_multiset::başvuru

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multiset Sınıf](../standard-library/unordered-multiset-class.md).

hash_multiset depolanan bir öğeye başvuru sağlayan bir tür.

```cpp
typedef list<typename _Traits::value_type, typename _Traits::allocator_type>::reference reference;
```

### <a name="remarks"></a>Açıklamalar

### <a name="example"></a>Örnek

```cpp
// hash_multiset_reference.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_multiset <int> hms1;

   hms1.insert( 10 );
   hms1.insert( 20 );

   // Declare and initialize a reference &Ref1 to the 1st element
   int &Ref1 = *hms1.begin( );

   cout << "The first element in the hash_multiset is "
        << Ref1 << "." << endl;

   // The value of the 1st element of the hash_multiset can be
   // changed by operating on its (non const) reference
   Ref1 = Ref1 + 5;

   cout << "The first element in the hash_multiset is now "
        << *hms1.begin() << "." << endl;
}
```

```Output
The first element in the hash_multiset is 10.
The first element in the hash_multiset is now 15.
```

## <a name="hash_multisetrend"></a><a name="rend"></a>hash_multiset::rend

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multiset Sınıf](../standard-library/unordered-multiset-class.md).

Ters hash_multiset son öğeyi yerine getiren konumu adresleyen bir yineleyici döndürür.

```cpp
const_reverse_iterator rend() const;

reverse_iterator rend();
```

### <a name="return-value"></a>Dönüş Değeri

Ters hash_multiset 'daki son öğeyi başaran konumu (tersine çevrilmemiş hash_multiset ilk öğeden önce gelen konum) gideren ters çift yönlü bir yineleme.

### <a name="remarks"></a>Açıklamalar

`rend`[uç](#end) bir hash_multiset ile kullanıldığı gibi ters hash_multiset ile kullanılır.

Bir `const_reverse_iterator`,'ye `rend` atanırsa, hash_multiset nesnesi değiştirilemez. Bir `reverse_iterator`, hash_multiset `rend` nesnesinin geri dönüş değerine atanmışsa değiştirilebilir. Döndürülen `rend` değer dereferenced olmamalıdır.

`rend`ters yineleyicinin hash_multiset sonuna ulaşıp ulaşmadığını test etmek için kullanılabilir.

### <a name="example"></a>Örnek

```cpp
// hash_multiset_rend.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_multiset <int> hms1;
   hash_multiset <int>::iterator hms1_Iter;
   hash_multiset <int>::reverse_iterator hms1_rIter;
   hash_multiset <int>::const_reverse_iterator hms1_crIter;

   hms1.insert( 10 );
   hms1.insert( 20 );
   hms1.insert( 30 );

   hms1_rIter = hms1.rend( );
   hms1_rIter--;
   cout << "The last element in the reversed hash_multiset is "
        << *hms1_rIter << "." << endl;

   // end can be used to terminate an iteration
   // through a hash_multiset in a forward order
   cout << "The hash_multiset is: ";
   for ( hms1_Iter = hms1.begin( ) ; hms1_Iter != hms1.end( );
         hms1_Iter++ )
      cout << *hms1_Iter << " ";
   cout << "." << endl;

   // rend can be used to terminate an iteration
   // through a hash_multiset in a reverse order
   cout << "The reversed hash_multiset is: ";
   for ( hms1_rIter = hms1.rbegin( ) ; hms1_rIter != hms1.rend( );
         hms1_rIter++ )
      cout << *hms1_rIter << " ";
   cout << "." << endl;

   hms1_rIter = hms1.rend( );
   hms1_rIter--;
   hms1.erase ( *hms1_rIter );

   hms1_rIter = hms1.rend( );
   hms1_rIter--;
   cout << "After the erasure, the last element in the "
        << "reversed hash_multiset is " << *hms1_rIter << "."
        << endl;
}
```

```Output
The last element in the reversed hash_multiset is 10.
The hash_multiset is: 10 20 30 .
The reversed hash_multiset is: 30 20 10 .
After the erasure, the last element in the reversed hash_multiset is 20.
```

## <a name="hash_multisetreverse_iterator"></a><a name="reverse_iterator"></a>hash_multiset:reverse_iterator

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multiset Sınıf](../standard-library/unordered-multiset-class.md).

Ters hash_multiset bir öğeyi okuyabilen veya değiştirebilen çift yönlü bir yineleme sağlayan bir tür.

```cpp
typedef list<typename Traits::value_type, typename Traits::allocator_type>::reverse_iterator reverse_iterator;
```

### <a name="remarks"></a>Açıklamalar

Bir `reverse_iterator` tür ters hash_multiset ile yinelemek için kullanılır.

### <a name="example"></a>Örnek

Nasıl bildirilir ve kullanılır. [rbegin](#rbegin) `reverse_iterator`

## <a name="hash_multisetsize"></a><a name="size"></a>hash_multiset::boyut

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multiset Sınıf](../standard-library/unordered-multiset-class.md).

hash_multiset'daki öğe sayısını verir.

```cpp
size_type size() const;
```

### <a name="return-value"></a>Dönüş Değeri

hash_multiset geçerli uzunluğu.

### <a name="remarks"></a>Açıklamalar

### <a name="example"></a>Örnek

```cpp
// hash_multiset_size.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_multiset <int> hms1;
   hash_multiset <int> :: size_type i;

   hms1.insert( 1 );
   i = hms1.size( );
   cout << "The hash_multiset length is " << i << "." << endl;

   hms1.insert( 2 );
   i = hms1.size( );
   cout << "The hash_multiset length is now " << i << "." << endl;
}
```

```Output
The hash_multiset length is 1.
The hash_multiset length is now 2.
```

## <a name="hash_multisetsize_type"></a><a name="size_type"></a>hash_multiset:size_type

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multiset Sınıf](../standard-library/unordered-multiset-class.md).

hash_multiset öğelerinin sayısını temsil eden imzasız bir tamsayı türü.

```cpp
typedef list<typename _Traits::value_type, typename _Traits::allocator_type>::size_type size_type;
```

### <a name="remarks"></a>Açıklamalar

### <a name="example"></a>Örnek

Nasıl beyan edilip kullanılacağına bir örnek için [boyut](#size) örneğine bakın`size_type`

## <a name="hash_multisetswap"></a><a name="swap"></a>hash_multiset::takas

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multiset Sınıf](../standard-library/unordered-multiset-class.md).

İki hash_multisets öğelerini değiştirir.

```cpp
void swap(hash_multiset& right);
```

### <a name="parameters"></a>Parametreler

*Doğru*\
Bağımsız değişken, hedef hash_multiset değiştirilecek öğeleri sağlayan hash_multiset.

### <a name="remarks"></a>Açıklamalar

Üye işlev, öğeleri değiştirilen iki hash_multisets öğeleri belirleyen hiçbir başvuru, işaretçi veya yineleyicigeçersiz olur.

### <a name="example"></a>Örnek

```cpp
// hash_multiset_swap.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_multiset <int> hms1, hms2, hms3;
   hash_multiset <int>::iterator hms1_Iter;

   hms1.insert( 10 );
   hms1.insert( 20 );
   hms1.insert( 30 );
   hms2.insert( 100 );
   hms2.insert( 200 );
   hms3.insert( 300 );

   cout << "The original hash_multiset hms1 is:";
   for ( hms1_Iter = hms1.begin( ); hms1_Iter != hms1.end( );
         hms1_Iter++ )
         cout << " " << *hms1_Iter;
   cout   << "." << endl;

   // This is the member function version of swap
   hms1.swap( hms2 );

   cout << "After swapping with hms2, list hms1 is:";
   for ( hms1_Iter = hms1.begin( ); hms1_Iter != hms1.end( );
         hms1_Iter++ )
         cout << " " << *hms1_Iter;
   cout  << "." << endl;

   // This is the specialized template version of swap
   swap( hms1, hms3 );

   cout << "After swapping with hms3, list hms1 is:";
   for ( hms1_Iter = hms1.begin( ); hms1_Iter != hms1.end( );
         hms1_Iter++ )
         cout << " " << *hms1_Iter;
   cout   << "." << endl;
}
```

```Output
The original hash_multiset hms1 is: 10 20 30.
After swapping with hms2, list hms1 is: 200 100.
After swapping with hms3, list hms1 is: 300.
```

## <a name="hash_multisetupper_bound"></a><a name="upper_bound"></a>hash_multiset::upper_bound

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multiset Sınıf](../standard-library/unordered-multiset-class.md).

Bir hash_multiset ilk öğeye belirtilen anahtardan daha büyük bir anahtarla bir yineleyici döndürür.

```cpp
const_iterator upper_bound(const Key& key) const;

iterator upper_bound(const Key& key);
```

### <a name="parameters"></a>Parametreler

*Anahtar*\
Aralanan hash_multiset öğenin tür anahtarıyla karşılaştırılacak bağımsız değişken anahtarı.

### <a name="return-value"></a>Dönüş Değeri

Bir hash_multiset ilk öğenin konumunu bağımsız değişken anahtarından daha büyük bir anahtarla ele alan veya anahtar için eşleşme bulunamazsa hash_multiset'daki son öğeyi başaran konumu gideren bir [yineleyici](#iterator) veya [const_iterator.](#const_iterator)

### <a name="remarks"></a>Açıklamalar

### <a name="example"></a>Örnek

```cpp
// hash_multiset_upper_bound.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_multiset <int> hms1;
   hash_multiset <int> :: const_iterator hms1_AcIter, hms1_RcIter;

   hms1.insert( 10 );
   hms1.insert( 20 );
   hms1.insert( 30 );

   hms1_RcIter = hms1.upper_bound( 20 );
   cout << "The first element of hash_multiset hms1" << endl
        << "with a key greater than 20 is: "
        << *hms1_RcIter << "." << endl;

   hms1_RcIter = hms1.upper_bound( 30 );

   // If no match is found for the key, end( ) is returned
   if ( hms1_RcIter == hms1.end( ) )
      cout << "The hash_multiset hms1 doesn't have an element\n"
           << "with a key greater than 30." << endl;
   else
      cout << "The element of hash_multiset hms1"
           << "with a key > 40 is: "
           << *hms1_RcIter << "." << endl;

   // An element at a specific location in the hash_multiset can be
   // found by using a dereferenced iterator addressing the location
   hms1_AcIter = hms1.begin( );
   hms1_RcIter = hms1.upper_bound( *hms1_AcIter );
   cout << "The first element of hms1 with a key greater than "
        << endl << "that of the initial element of hms1 is: "
        << *hms1_RcIter << "." << endl;
}
```

```Output
The first element of hash_multiset hms1
with a key greater than 20 is: 30.
The hash_multiset hms1 doesn't have an element
with a key greater than 30.
The first element of hms1 with a key greater than
that of the initial element of hms1 is: 20.
```

## <a name="hash_multisetvalue_comp"></a><a name="value_comp"></a>hash_multiset:value_comp

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multiset Sınıf](../standard-library/unordered-multiset-class.md).

Bir hash_multiset öğe değerlerini sıralamak için kullanılan karşılaştırma nesnesinin bir kopyasını alır.

```cpp
value_compare value_comp() const;
```

### <a name="return-value"></a>Dönüş Değeri

Karma ve kapsayıcının öğelerini sıralamak için kullanılan işlev nesnelerini içeren hash_multiset şablon *parametre*Özellikleri'ni döndürür.

*Özellikler* hakkında daha fazla bilgi için [hash_multiset Sınıfı](../standard-library/hash-multiset-class.md) konusuna bakın.

### <a name="remarks"></a>Açıklamalar

Depolanan nesne bir üye işlev tanımlar:

**bool operatörü**( **constKey&** `_xVal`, **const Key&** *_yVal*);

önce yse ve sıralama `_yVal` sırasına eşit değilse doğru döndürür. **true** `_xVal`

Hem [key_compare](#key_compare) hem de [value_compare](#value_compare) şablon parametresi *Özellikleri*ile eş anlamlı olduğunu unutmayın. Her iki tür de, farklı oldukları hash_map ve hash_multimap sınıflarıyla uyumluluk için, aynı oldukları hash_multiset ve hash_multiset sınıfları için sağlanır.

### <a name="example"></a>Örnek

```cpp
// hash_multiset_value_comp.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;

   hash_multiset <int, hash_compare < int, less<int> > > hms1;
   hash_multiset <int, hash_compare < int, less<int> > >::value_compare
      vc1 = hms1.value_comp( );
   bool result1 = vc1( 2, 3 );
   if( result1 == true )
   {
      cout << "vc1( 2,3 ) returns value of true, "
           << "where vc1 is the function object of hms1."
           << endl;
   }
   else
   {
      cout << "vc1( 2,3 ) returns value of false, "
           << "where vc1 is the function object of hms1."
           << endl;
   }

   hash_multiset <int, hash_compare < int, greater<int> > > hms2;
   hash_multiset<int, hash_compare < int, greater<int> > >::
           value_compare vc2 = hms2.value_comp( );
   bool result2 = vc2( 2, 3 );
   if( result2 == true )
   {
      cout << "vc2( 2,3 ) returns value of true, "
           << "where vc2 is the function object of hms2."
           << endl;
   }
   else
   {
      cout << "vc2( 2,3 ) returns value of false, "
           << "where vc2 is the function object of hms2."
           << endl;
   }
}
```

```Output
vc1( 2,3 ) returns value of true, where vc1 is the function object of hms1.
vc2( 2,3 ) returns value of false, where vc2 is the function object of hms2.
```

## <a name="hash_multisetvalue_compare"></a><a name="value_compare"></a>hash_multiset::value_compare

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multiset Sınıf](../standard-library/unordered-multiset-class.md).

İki işlev nesnesi sağlayan bir tür, bir hash_multiset iki öğe değerlerini karşılaştırabilen bir sınıf karşılaştırması ve öğeleri işleyen bir unary yüklemi.

```cpp
typedef key_compare value_compare;
```

### <a name="remarks"></a>Açıklamalar

`value_compare`şablon parametresi *Özellikleri*ile eş anlamlıdır.

*Özellikler* hakkında daha fazla bilgi için [hash_multiset Sınıfı](../standard-library/hash-multiset-class.md) konusuna bakın.

Hem [key_compare](#key_compare) hem `value_compare` de şablon parametresi *Özellikleri*ile eş anlamlıdır. Her iki tür de sınıflar haritası ve çoklu harita ile uyumluluk için, farklı oldukları sınıflar kümesi ve çoklu küme, için sağlanır.

### <a name="example"></a>Örnek

[Nasıl](#value_comp) beyan edilip kullanılacağına `value_compare`value_comp örneğe bakın.

## <a name="hash_multisetvalue_type"></a><a name="value_type"></a>hash_multiset:value_type

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multiset Sınıf](../standard-library/unordered-multiset-class.md).

Değer olarak kapasitesinde hash_multiset olarak öğe olarak depolanan bir nesneyi açıklayan bir tür.

```cpp
typedef Key value_type;
```

### <a name="example"></a>Örnek

```cpp
// hash_multiset_value_type.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_multiset <int> hms1;
   hash_multiset <int>::iterator hms1_Iter;

   // Declare value_type
   hash_multiset <int> :: value_type hmsvt_Int;

   hmsvt_Int = 10;   // Initialize value_type

   // Declare key_type
   hash_multiset <int> :: key_type hmskt_Int;
   hmskt_Int = 20;             // Initialize key_type

   hms1.insert( hmsvt_Int );         // Insert value into s1
   hms1.insert( hmskt_Int );         // Insert key into s1

   // A hash_multiset accepts key_types or value_types as elements
   cout << "The hash_multiset has elements:";
   for ( hms1_Iter = hms1.begin() ; hms1_Iter != hms1.end( );
         hms1_Iter++)
      cout << " " << *hms1_Iter;
      cout << "." << endl;
}
```

```Output
The hash_multiset has elements: 10 20.
```

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[C++ Standart Kütüphane Başvurusu](../standard-library/cpp-standard-library-reference.md)
