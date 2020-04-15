---
title: multiset Sınıfı
ms.date: 11/04/2016
f1_keywords:
- set/std::multiset
- set/std::multiset::allocator_type
- set/std::multiset::const_iterator
- set/std::multiset::const_pointer
- set/std::multiset::const_reference
- set/std::multiset::const_reverse_iterator
- set/std::multiset::difference_type
- set/std::multiset::iterator
- set/std::multiset::key_compare
- set/std::multiset::key_type
- set/std::multiset::pointer
- set/std::multiset::reference
- set/std::multiset::reverse_iterator
- set/std::multiset::size_type
- set/std::multiset::value_compare
- set/std::multiset::value_type
- set/std::multiset::begin
- set/std::multiset::cbegin
- set/std::multiset::cend
- set/std::multiset::clear
- set/std::multiset::count
- set/std::multiset::crbegin
- set/std::multiset::crend
- set/std::multiset::emplace
- set/std::multiset::emplace_hint
- set/std::multiset::empty
- set/std::multiset::end
- set/std::multiset::equal_range
- set/std::multiset::erase
- set/std::multiset::find
- set/std::multiset::get_allocator
- set/std::multiset::insert
- set/std::multiset::key_comp
- set/std::multiset::lower_bound
- set/std::multiset::max_size
- set/std::multiset::rbegin
- set/std::multiset::rend
- set/std::multiset::size
- set/std::multiset::swap
- set/std::multiset::upper_bound
- set/std::multiset::value_comp
helpviewer_keywords:
- std::multiset [C++]
- std::multiset [C++], allocator_type
- std::multiset [C++], const_iterator
- std::multiset [C++], const_pointer
- std::multiset [C++], const_reference
- std::multiset [C++], const_reverse_iterator
- std::multiset [C++], difference_type
- std::multiset [C++], iterator
- std::multiset [C++], key_compare
- std::multiset [C++], key_type
- std::multiset [C++], pointer
- std::multiset [C++], reference
- std::multiset [C++], reverse_iterator
- std::multiset [C++], size_type
- std::multiset [C++], value_compare
- std::multiset [C++], value_type
- std::multiset [C++], begin
- std::multiset [C++], cbegin
- std::multiset [C++], cend
- std::multiset [C++], clear
- std::multiset [C++], count
- std::multiset [C++], crbegin
- std::multiset [C++], crend
- std::multiset [C++], emplace
- std::multiset [C++], emplace_hint
- std::multiset [C++], empty
- std::multiset [C++], end
- std::multiset [C++], equal_range
- std::multiset [C++], erase
- std::multiset [C++], find
- std::multiset [C++], get_allocator
- std::multiset [C++], insert
- std::multiset [C++], key_comp
- std::multiset [C++], lower_bound
- std::multiset [C++], max_size
- std::multiset [C++], rbegin
- std::multiset [C++], rend
- std::multiset [C++], size
- std::multiset [C++], swap
- std::multiset [C++], upper_bound
- std::multiset [C++], value_comp
ms.assetid: 630e8c10-0ce9-4ad9-8d79-9e91a600713f
ms.openlocfilehash: 67cf79a935df71054dbc5c0ee2eb6ec98dd8b589
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367296"
---
# <a name="multiset-class"></a>multiset Sınıfı

C++ Standart Kitaplığı çok ayarlı sınıfı, içerdiği öğelerin değerlerinin benzersiz olmaması ve verilerin otomatik olarak sipariş edildiği temel değerler olarak hizmet verdikleri bir koleksiyondan veri depolamave alma için kullanılır. Çoklu kümedeki bir öğenin anahtar değeri doğrudan değiştirilemez. Bunun yerine, eski değerlerin silinmesi ve yeni değerlerle sahip öğelerin eklenmesi gerekir.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Key, class Compare =less <Key>, class Allocator =allocator <Key>>
class multiset
```

### <a name="parameters"></a>Parametreler

*Anahtar*\
Çoklu kümede depolanacak öğe veri türü.

*Karşılaştırmak*\
İki öğenin değerlerini çoklu kümedeki kendi göreli sıralarını belirlemek için sıralama anahtarları olarak karşılaştırabilen bir işlev nesnesi sağlayan tür. İkili yüklem **daha az**\<Anahtar> varsayılan değerdir.

C++14'te, tür parametreleri olmayan yüklemi `std::less<>` `std::greater<>` veya yüklemi belirterek heterojen bir arama yı etkinleştirebilirsiniz. Daha fazla bilgi için [Bkz. Bağşanlı Kaplarda Heterojen Arama](../standard-library/stl-containers.md#sequence_containers)

*Ayırıcı*\
Çoklu küme için bellek ayırmayı ve ayırmayı kaldırma hakkındaki ayrıntıları içeren saklı ayırıcı nesnesini gösteren tür. Varsayılan değer: `allocator<Key>`.

## <a name="remarks"></a>Açıklamalar

C++ Standart Kitaplık çok setli sınıfı:

- İlişkili bir anahtar değerine dayalı öğe değerlerinin verimli alınmasını destekleyen bir değişken boyutu kapsayıcı olan ilişkilendirilebilir bir kapsayıcı.

- Çift yönlüdür, çünkü öğelerine erişmek için çift yönlü yineleyiciler sağlar.

- Sıralıdır, çünkü öğeleri belirtilen karşılaştırma işlevine uygun olarak kapsayıcı içindeki anahtar değerlere göre sıralanır.

- Öğelerinin benzersiz anahtarlara ihtiyacı olmaması bakımından çokludur, böylece bir anahtar değer onunla ilişkili çok sayıda öğe değerine sahip olabilir.

- Basit bir ilişkilendirilebilir kapsayıcıdır, çünkü öğelerinin değerleri kendi anahtar değerleridir.

- Sağladığı işlevsellik genel olduğundan ve öğe olarak bulunan belirli veri türünden bağımsız olduğundan, sınıf şablonu. Kullanılacak veri türü, karşılaştırma işlevi ve ayırıcı ile birlikte bir sınıf şablonunda bir parametre olarak belirtilir.

Çok ayarlı sınıf tarafından sağlanan yineleme çift yönlü bir yinelemedir, ancak sınıf üye işlevleri [ekleme](#insert) ve [çoklu küme,](#multiset) işlevsellik gereksinimleri çift yönlü yineleyiciler sınıfı tarafından garanti edilenden daha az olan şablon parametreleri olarak daha zayıf bir giriş yineleyicisi alan sürümleri vardır. Farklı yineleyici kavramları, işlevselliklerindeki iyileştirmelere göre ilgili bir aile biçimlendirir. Her yineleyici kavramının kendi gereksinimler kümesi vardır ve bunlarla çalışan algoritmaların kendi varsayımlarını yineleyici türü tarafından sağlanan gereksinimlerle sınırlaması gerekir. Bir giriş yineleyicinin bazı nesnelere başvurusunun kaldırılacağı ve dizideki sonraki yineleyiciye artırılabileceği varsayılabilir. Bu en az işlevsellik kümesidir, ancak sınıfın üye işlevleri bağlamında bir dizi `First`yineleyici [, `Last`) hakkında anlamlı bir şekilde konuşabilmek yeterlidir.

Kapsayıcı türünün seçimi genelde uygulamanın gerektirdiği arama ve ekleme türüne dayalı olmalıdır. İlişkilendirilebilir kapsayıcılar, arama, ekleme ve kaldırma işlemleri için en iyi duruma getirilir. Bu işlemleri açıkça destekleyen üye işlevleri, işlevlerini kapsayıcıdaki öğelerin sayısının logaritmasına ortalama orantılı bir sürede gerçekleştirir ve verimlidir. Öğelerin eklenmesi hiçbir yineleyiciyi geçersiz kılmaz; öğelerin kaldırılması yalnızca özellikle kaldırılan öğeleri gösteren yineleyicileri geçersiz kılar.

Çoklu küme, değerleri onların kendi anahtarlarıyla ilişkilendiren koşullar uygulama tarafından karşılandığında seçimin ilişkili kapsayıcısı olmalıdır. Bir çoklu kümenin öğeleri birden çok olabilir ve anahtarlar benzersiz olmadıklarından kendi sıralama anahtarları olarak hizmet verebilir. Bu tür bir yapı modeli, sözcüklerin birden çok defa geçebildiği sıralı bir sözcükler listesindedir. Sözcüklerin birden çok defa geçmelerine izin verilmediğinde, bir küme uygun bir kapsayıcı yapısı olacaktır. Benzersiz tanımlar benzersiz anahtar sözcükler listesine değerler olarak eklendiyse, bir eşlem verileri kapsayacak uygun bir yapı olacaktır. Bunun yerine tanımlar benzersiz değilse, seçilecek kapsayıcı bir çoklu eşlem olurdu.

Çoklu küme, denetlenen *sırayı,* depolanmış bir işlev nesnesi olarak adlandırarak denetler. Bu depolanan nesne, üye işlevi [key_comp](#key_comp)çağırarak erişilebilen bir karşılaştırma işlevidir. Genelde, bu sıralamayı oluşturmak için öğelerin yalnızca küçüktür biçiminde karşılaştırılabilir olması gerekir; böylece, herhangi iki öğe belirtildiğinde, eşit oldukları (yani birinin diğerinden daha küçük olmadığı anlamında) veya birinin diğerinden küçük olduğu belirlenebilir. Bu, denk olmayan öğeler arasında bir sıralamaya neden olur. Daha teknik bir not üzerinde, karşılaştırma işlevi standart matematiksel anlamda katı bir zayıf sıralama sevk eden ikili bir koşuldur. İkili yüklem *f*( *x*, *y*) iki bağımsız değişken nesnesi *x* ve *y* ve **doğru** veya **yanlışın**geri dönüş değeri olan bir işlev nesnesidir. Bir kümeye uygulanan bir sıralama, ikili yüklem inreflexive, antisimetrik ve geçişli ve eşdeğerlik geçişli ise, iki nesne x ve y hem *f*( *x,y*) ve *f*( *y,x*) yanlış olarak tanımlanır zaman, sıkı bir zayıf sıralamadır. Anahtarlar arasındaki eşitliğinin daha güçlü koşulu bu denkliğin yerini alırsa, sıralama (içindeki tüm öğelerin birbirine göre sıralanması anlamında) toplam haline gelir ve eşleşen anahtarlar birbirinden ayırt edilemez olacaktır.

C++14'te, tür parametreleri olmayan yüklemi `std::less<>` `std::greater<>` veya yüklemi belirterek heterojen bir arama yı etkinleştirebilirsiniz. Daha fazla bilgi için [Bkz. Bağşanlı Kaplarda Heterojen Arama](../standard-library/stl-containers.md#sequence_containers)

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[Multiset](#multiset)|Boş olan `multiset` veya belirtilen `multiset`bir bölümün veya bir kısmının kopyası olan bir yapı.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[Allocator_type](#allocator_type)|Nesne için sınıf `allocator` için bir typedef. `multiset`|
|[const_iterator](#const_iterator)|Bir **const** öğeyi `multiset`okuyabilen çift yönlü bir yineleme için typedef|
|[Const_pointer](#const_pointer)|Bir **const** öğesiiçin işaretçi için `multiset`bir typedef .|
|[const_reference](#const_reference)|Const **işlemleri** okumak ve gerçekleştirmek için bir `multiset` **const** öğesinde depolanan bir başvuru için bir typedef.|
|[Const_reverse_iterator](#const_reverse_iterator)|Herhangi bir **const** öğeyi `multiset`okuyabilen çift yönlü bir yineleme için typedef|
|[difference_type](#difference_type)|Yineleyiciler tarafından işaret edilen öğeler arasındaki `multiset` aralıktaki bir aralığın öğelerinin sayısı için imzalı bir tamsayı typedef.|
|[Yineleyici](#iterator)|Bir `multiset`öğedeki herhangi bir öğeyi okuyabilen veya değiştirebilen çift yönlü bir yineleme için typedef|
|[Key_compare](#key_compare)|`multiset`İki öğenin göreli sırasını belirlemek için iki anahtarı karşılaştırabilen bir işlev nesnesi için typedef|
|[Key_type](#key_type)|`multiset`İki öğenin göreli sırasını belirlemek için iki sıralama anahtarını karşılaştırabilen bir işlev nesnesi için typedef|
|[pointer](#pointer)|Bir öğedeki bir öğeiçin işaretçi için bir `multiset`typedef|
|[Başvuru](#reference)|Bir öğede depolanan bir öğeye `multiset`başvuru için bir typedef .|
|[Reverse_iterator](#reverse_iterator)|Ters bir öğedeki bir öğeyi okuyabilen veya değiştirebilen `multiset`çift yönlü bir yineleme için typedef.|
|[size_type](#size_type)|Bir 'deki öğe sayısını temsil eden imzasız `multiset`bir tamsayı türü|
|[Value_compare](#value_compare)|İki öğeyi sıraanahtarları olarak karşılaştırabilen bir işlev nesnesinin typedef'i, `multiset`göreli sıralarını .|
|[value_type](#value_type)|Öğe olarak depolanan bir nesneyi değer `multiset` olarak kapasitesinde açıklayan bir typedef.|

### <a name="member-functions"></a>Üye işlevler

|Üye fonksiyonu|Açıklama|
|-|-|
|[Başlamak](#begin)|'deki ilk öğeyi işaret eden bir `multiset`yineleyici döndürür.|
|[cbegin](#cbegin)|'deki ilk öğeyi ele alan bir const `multiset`yineleyici döndürür.|
|[cend](#cend)|Bir `multiset`'deki son öğeyi yerine getiren konumu gideren bir const yineleyici döndürür.|
|[Temizleyin](#clear)|Bir' `multiset`nin tüm öğelerini siler.|
|[Sayısı](#count)|Anahtar parametre olarak `multiset` belirtilen anahtarla eşleşen bir öğedeki öğe sayısını döndürür.|
|[crbegin](#crbegin)|Ters çevrilen kümedeki ilk öğeyi ele alan bir sabit yineleyici döndürür.|
|[crend](#crend)|Ters çevrilen kümedeki son öğeden sonra gelen konumu ele alan bir sabit yineleyici döndürür.|
|[emplace](#emplace)|Yerinde inşa edilmiş bir öğeyi `multiset`bir .|
|[emplace_hint](#emplace_hint)|Yerinde `multiset`oluşturulmuş bir öğeyi yerleştirme ipucuyla ekler.|
|[empty](#empty)|A boşsa `multiset` sınar.|
|[Son -unda](#end)|Bir 'deki son öğeden sonra konumu işaret eden `multiset`bir yineleyici döndürür.|
|[equal_range](#equal_range)|Yineleyicilerin bir çiftini döndürür. Çiftteki ilk yineleyici, belirtilen bir anahtardan `multiset` daha büyük bir anahtara sahip ilk öğeyi işaret eder. Çiftteki ikinci yineleyici, anahtara eşit veya `multiset` daha büyük bir anahtarla ilk öğeyi işaret eder.|
|[Silmek](#erase)|Belirtilen konumlardaki `multiset` bir öğeyi veya bir dizi öğeyi kaldırır veya belirtilen anahtarla eşleşen öğeleri kaldırır.|
|[find](#find)|Belirtilen anahtara eşit bir `multiset` anahtara sahip bir öğenin ilk konumuna işaret eden bir yineleyici döndürür.|
|[Get_allocator](#get_allocator)|' yi oluşturmak `allocator` için kullanılan nesnenin `multiset`bir kopyasını döndürür.|
|[Ekle](#insert)|Bir öğeye veya bir dizi öğeye `multiset`bir öğe ekler.|
|[Key_comp](#key_comp)|İki öğenin göreli sırasını belirlemek için iki sıralama anahtarını karşılaştırabilen bir işlev nesnesi `multiset`sağlar.|
|[lower_bound](#lower_bound)|Bir yineleyiciyi, belirtilen bir anahtara eşit veya daha büyük bir `multiset` anahtarla bir ilk öğeye döndürür.|
|[max_size](#max_size)|Maksimum uzunluğu `multiset`verir.|
|[rbegin](#rbegin)|Ters bir ilk öğeyi işaret eden bir `multiset`yineleyici döndürür.|
|[Rend](#rend)|Ters bir öğedeki son öğeyi başaran konuma işaret eden `multiset`bir yineleyici döndürür.|
|[Boyutu](#size)|Bir `multiset`'deki öğe sayısını döndürür.|
|[Takas](#swap)|İki `multiset`s'nin öğelerini değiştirir.|
|[upper_bound](#upper_bound)|Bir yineleyiciyi belirtilen anahtardan büyük `multiset` bir anahtarla bir ilk öğeye döndürür.|
|[value_comp](#value_comp)|Bir `multiset`' deki öğe değerlerini sıralamak için kullanılan karşılaştırma nesnesinin bir kopyasını alır.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[işleç=](#op_eq)|Bir `multiset` öğenin öğelerini başka `multiset`bir kopyayla değiştirir.|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** \<set>

**Ad alanı:** std

## <a name="multisetallocator_type"></a><a name="allocator_type"></a>çok ayarlı::allocator_type

Çok ayarlı nesneiçin ayırıcı sınıfını temsil eden bir tür

```cpp
typedef Allocator allocator_type;
```

### <a name="remarks"></a>Açıklamalar

`allocator_type`şablon parametresi `Allocator`ile eş anlamlıdır.

Daha fazla `Allocator`bilgi [için, çok ayarlı Sınıf](../standard-library/multiset-class.md) konusunun Açıklamalar bölümüne bakın.

### <a name="example"></a>Örnek

Bir örnek için [get_allocator](#get_allocator) örneğine bakın`allocator_type`

## <a name="multisetbegin"></a><a name="begin"></a>çok ayarlı::başla

Çok kümedeki ilk öğeyi ele alan bir yineleyici döndürür.

```cpp
const_iterator begin() const;

iterator begin();
```

### <a name="return-value"></a>Dönüş Değeri

Çoklu kümedeki ilk öğeyi veya boş bir çoklu kümeyi başaran konumu ele alan çift yönlü bir yineleyici.

### <a name="example"></a>Örnek

```cpp
// multiset_begin.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main( )
{
   using namespace std;
   multiset <int> ms1;
   multiset <int>::iterator ms1_Iter;
   multiset <int>::const_iterator ms1_cIter;

   ms1.insert( 1 );
   ms1.insert( 2 );
   ms1.insert( 3 );

   ms1_Iter = ms1.begin( );
   cout << "The first element of ms1 is " << *ms1_Iter << endl;

   ms1_Iter = ms1.begin( );
   ms1.erase( ms1_Iter );

   // The following 2 lines would err as the iterator is const
   // ms1_cIter = ms1.begin( );
   // ms1.erase( ms1_cIter );

   ms1_cIter = ms1.begin( );
   cout << "The first element of ms1 is now " << *ms1_cIter << endl;
}
```

```Output
The first element of ms1 is 1
The first element of ms1 is now 2
```

## <a name="multisetcbegin"></a><a name="cbegin"></a>çok ayarlı::cbegin

Aralıktaki ilk öğeyi ele alan bir **const** yineleyici döndürür.

```cpp
const_iterator cbegin() const;
```

### <a name="return-value"></a>Dönüş Değeri

Aralığın ilk öğesini veya boş aralığın sonundaki konumu işaret eden **bir çift** yönlü erişim yinelemesi (boş `cbegin() == cend()`bir aralık için).

### <a name="remarks"></a>Açıklamalar

İade değeri ile `cbegin`aralıktaki öğeler değiştirilemez.

Bu üye `begin()` işlevini, iade değerinin `const_iterator`. Genellikle, aşağıdaki örnekte gösterildiği gibi [otomatik](../cpp/auto-cpp.md) tür kesintisi anahtar sözcüğüyle birlikte kullanılır. Örnekte, herhangi `Container` bir tür değiştirilebilir (non-const) kapsayıcı ve `begin()` destekler `cbegin()`düşünün. **const**

```cpp
auto i1 = Container.begin();
// i1 is Container<T>::iterator
auto i2 = Container.cbegin();

// i2 is Container<T>::const_iterator
```

## <a name="multisetcend"></a><a name="cend"></a>çok ayar::cend

Bir aralıktaki son öğenin hemen ötesinde konuma hitap eden bir **const** yineleyici döndürür.

```cpp
const_iterator cend() const;
```

### <a name="return-value"></a>Dönüş Değeri

Aralığın sonuna işaret eden **bir konst** çift yönlü erişim yinelemesi.

### <a name="remarks"></a>Açıklamalar

`cend`bir yineleyicinin aralığının sonundan geçip geçmediğini test etmek için kullanılır.

Bu üye `end()` işlevini, iade değerinin `const_iterator`. Genellikle, aşağıdaki örnekte gösterildiği gibi [otomatik](../cpp/auto-cpp.md) tür kesintisi anahtar sözcüğüyle birlikte kullanılır. Örnekte, herhangi `Container` bir tür değiştirilebilir (non-const) kapsayıcı ve `end()` destekler `cend()`düşünün. **const**

```cpp
auto i1 = Container.end();
// i1 is Container<T>::iterator
auto i2 = Container.cend();

// i2 is Container<T>::const_iterator
```

Döndürülen `cend` değer dereferenced olmamalıdır.

## <a name="multisetclear"></a><a name="clear"></a>çok ayarlı::açık

Çoklu kümenin tüm öğelerini siler.

```cpp
void clear();
```

### <a name="example"></a>Örnek

```cpp
// multiset_clear.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main( )
{
   using namespace std;
   multiset <int> ms1;

   ms1.insert( 1 );
   ms1.insert( 2 );

   cout << "The size of the multiset is initially "
        << ms1.size( ) << "." << endl;

   ms1.clear( );
   cout << "The size of the multiset after clearing is "
        << ms1.size( ) << "." << endl;
}
```

```Output
The size of the multiset is initially 2.
The size of the multiset after clearing is 0.
```

## <a name="multisetconst_iterator"></a><a name="const_iterator"></a>çok ayarlı::const_iterator

Çok kümedeki **bir const** öğeyi okuyabilen çift yönlü bir yineleme sağlayan bir tür.

```cpp
typedef implementation-defined const_iterator;
```

### <a name="remarks"></a>Açıklamalar

Bir `const_iterator` tür, bir öğenin değerini değiştirmek için kullanılamaz.

### <a name="example"></a>Örnek

Bir örneğin [ikullanarak](#begin) `const_iterator`başlatılamıörneğine bakın.

## <a name="multisetconst_pointer"></a><a name="const_pointer"></a>çok ayarlı::const_pointer

Çok kümedeki **const** öğesine işaretçi sağlayan bir tür.

```cpp
typedef typename allocator_type::const_pointer const_pointer;
```

### <a name="remarks"></a>Açıklamalar

Bir `const_pointer` tür, bir öğenin değerini değiştirmek için kullanılamaz.

Çoğu durumda, çok ayarlı bir nesnedeki öğelere erişmek için bir [yineleyici](#iterator) kullanılmalıdır.

## <a name="multisetconst_reference"></a><a name="const_reference"></a>çok ayarlı::const_reference

**Const** işlemleri okumak ve gerçekleştirmek için çok kümede depolanan **bir const** elemana başvuru sağlayan bir tür.

```cpp
typedef typename allocator_type::const_reference const_reference;
```

### <a name="example"></a>Örnek

```cpp
// multiset_const_ref.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main( )
{
   using namespace std;
   multiset <int> ms1;

   ms1.insert( 10 );
   ms1.insert( 20 );

   // Declare and initialize a const_reference &Ref1
   // to the 1st element
   const int &Ref1 = *ms1.begin( );

   cout << "The first element in the multiset is "
        << Ref1 << "." << endl;

   // The following line would cause an error because the
   // const_reference cannot be used to modify the multiset
   // Ref1 = Ref1 + 5;
}
```

```Output
The first element in the multiset is 10.
```

## <a name="multisetconst_reverse_iterator"></a><a name="const_reverse_iterator"></a>çok ayarlı::const_reverse_iterator

Çok kümedeki herhangi bir **const** öğeyi okuyabilen çift yönlü bir yineleme sağlayan bir tür.

```cpp
typedef std::reverse_iterator<const_iterator> const_reverse_iterator;
```

### <a name="remarks"></a>Açıklamalar

Bir `const_reverse_iterator` tür bir öğenin değerini değiştiremez ve ters çoklu küme ile yinelemek için kullanılır.

### <a name="example"></a>Örnek

Nasıl beyan edilip kullanılacağına bir örnek için `const_reverse_iterator` [rend](#rend) örneğine bakın.

## <a name="multisetcount"></a><a name="count"></a>çok ayarlı::say

Anahtarı parametre yle belirtilen anahtarla eşleşen bir çoklu kümedeki öğe sayısını verir.

```cpp
size_type count(const Key& key) const;
```

### <a name="parameters"></a>Parametreler

*Anahtar*\
Çoklu kümeden eşleşecek öğelerin anahtarı.

### <a name="return-value"></a>Dönüş Değeri

Sıralama anahtarı parametre anahtarıyla eşleşen çoklu kümedeki öğe sayısı.

### <a name="remarks"></a>Açıklamalar

Üye işlev aralıktaki *x* eleman sayısını döndürür

\[lower_bound (*anahtar*), upper_bound (*anahtar*)

### <a name="example"></a>Örnek

Aşağıdaki örnek, çoklu kümenin kullanımını gösterir::count üye işlevi.

```cpp
// multiset_count.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main()
{
    using namespace std;
    multiset<int> ms1;
    multiset<int>::size_type i;

    ms1.insert(1);
    ms1.insert(1);
    ms1.insert(2);

    // Elements do not need to be unique in multiset,
    // so duplicates are allowed and counted.
    i = ms1.count(1);
    cout << "The number of elements in ms1 with a sort key of 1 is: "
         << i << "." << endl;

    i = ms1.count(2);
    cout << "The number of elements in ms1 with a sort key of 2 is: "
         << i << "." << endl;

    i = ms1.count(3);
    cout << "The number of elements in ms1 with a sort key of 3 is: "
         << i << "." << endl;
}
```

```Output
The number of elements in ms1 with a sort key of 1 is: 2.
The number of elements in ms1 with a sort key of 2 is: 1.
The number of elements in ms1 with a sort key of 3 is: 0.
```

## <a name="multisetcrbegin"></a><a name="crbegin"></a>çok ayarlı::crbegin

Ters bir çoklu kümedeki ilk öğeyi ele alan bir const yineleyici döndürür.

```cpp
const_reverse_iterator crbegin() const;
```

### <a name="return-value"></a>Dönüş Değeri

Ters bir çoklu kümedeki ilk öğeyi ele alan veya ters çevrilmemiş çoklu kümedeki son öğeyi ele alan const ters yönlü bir yineleme.

### <a name="remarks"></a>Açıklamalar

`crbegin`bir çoklu set ile begin olarak ters bir çoklu set ile kullanılır.

İade değeri ile `crbegin`çok ayarlı nesne değiştirilemez.

`crbegin`geriye doğru bir çoklu küme üzerinden yinelemek için kullanılabilir.

### <a name="example"></a>Örnek

```cpp
// multiset_crbegin.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main( )
{
   using namespace std;
   multiset <int> ms1;
   multiset <int>::const_reverse_iterator ms1_crIter;

   ms1.insert( 10 );
   ms1.insert( 20 );
   ms1.insert( 30 );

   ms1_crIter = ms1.crbegin( );
   cout << "The first element in the reversed multiset is "
        << *ms1_crIter << "." << endl;
}
```

```Output
The first element in the reversed multiset is 30.
```

## <a name="multisetcrend"></a><a name="crend"></a>çok ayarlı::crend

Ters bir çoklu kümedeki son öğeyi yerine getiren konumu gideren bir const yineleyici döndürür.

```cpp
const_reverse_iterator crend() const;
```

### <a name="return-value"></a>Dönüş Değeri

Ters bir çoklu kümedeki son öğeyi (ters çevrilmemiş çoklu kümedeki ilk öğeden önce gelen konum) yerine hitap eden const ters çift yönlü yineleme.

### <a name="remarks"></a>Açıklamalar

`crend`[uç](#end) bir çoklu set ile kullanıldığı gibi ters bir çoklu set ile kullanılır.

İade değeri ile `crend`çok ayarlı nesne değiştirilemez.

`crend`ters yineleyicinin çoklu kümesinin sonuna ulaşıp ulaşmadığını test etmek için kullanılabilir.

Döndürülen `crend` değer dereferenced olmamalıdır.

### <a name="example"></a>Örnek

```cpp
// multiset_crend.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main() {
   using namespace std;
   multiset <int> ms1;
   multiset <int>::const_reverse_iterator ms1_crIter;

   ms1.insert( 10 );
   ms1.insert( 20 );
   ms1.insert( 30 );

   ms1_crIter = ms1.crend( ) ;
   ms1_crIter--;
   cout << "The last element in the reversed multiset is "
        << *ms1_crIter << "." << endl;
}
```

## <a name="multisetdifference_type"></a><a name="difference_type"></a>çok set::difference_type

Yineleyiciler tarafından işaret edilen öğeler arasındaki aralıkta bir çok kümenin öğelerinin sayısını temsil etmek için kullanılabilecek imzalı bir tamsayı türü.

```cpp
typedef typename allocator_type::difference_type difference_type;
```

### <a name="remarks"></a>Açıklamalar

Kapsayıcının `difference_type` yineleyicileri arasından çıkarılırken veya artarken döndürülen türdür. Genellikle `difference_type` yinelemeciler `first` arasındaki aralıktaki öğe sayısını temsil `first` `last`etmek için kullanılır [ `last`, ) ve `first` , tarafından işaret edilen öğe ve elemanların aralığı kadar, ancak dahil değil, öğe tarafından `last`işaret .

Küme gibi `difference_type` geri döndürülebilir kapsayıcılar tarafından desteklenen çift yönlü yineleyiciler sınıfını içeren bir giriş yineleyicisinin gereksinimlerini karşılayan tüm yineleyiciler için kullanılabilir olmasına rağmen, yineleyiciler arasındaki çıkarmanın yalnızca vektör gibi rasgele erişimli bir kapsayıcı tarafından sağlanan rasgele erişimli yinelemeciler tarafından desteklendiğine dikkat edin.

### <a name="example"></a>Örnek

```cpp
// multiset_diff_type.cpp
// compile with: /EHsc
#include <iostream>
#include <set>
#include <algorithm>

int main( )
{
   using namespace std;

   multiset <int> ms1;
   multiset <int>::iterator ms1_Iter, ms1_bIter, ms1_eIter;

   ms1.insert( 20 );
   ms1.insert( 10 );
   ms1.insert( 20 );

   ms1_bIter = ms1.begin( );
   ms1_eIter = ms1.end( );

   multiset <int>::difference_type   df_typ5, df_typ10, df_typ20;

   df_typ5 = count( ms1_bIter, ms1_eIter, 5 );
   df_typ10 = count( ms1_bIter, ms1_eIter, 10 );
   df_typ20 = count( ms1_bIter, ms1_eIter, 20 );

   // The keys, and hence the elements, of a multiset are not unique
   cout << "The number '5' occurs " << df_typ5
        << " times in multiset ms1.\n";
   cout << "The number '10' occurs " << df_typ10
        << " times in multiset ms1.\n";
   cout << "The number '20' occurs " << df_typ20
        << " times in multiset ms1.\n";

   // Count the number of elements in a multiset
   multiset <int>::difference_type  df_count = 0;
   ms1_Iter = ms1.begin( );
   while ( ms1_Iter != ms1_eIter)
   {
      df_count++;
      ms1_Iter++;
   }

   cout << "The number of elements in the multiset ms1 is: "
        << df_count << "." << endl;
}
```

```Output
The number '5' occurs 0 times in multiset ms1.
The number '10' occurs 1 times in multiset ms1.
The number '20' occurs 2 times in multiset ms1.
The number of elements in the multiset ms1 is: 3.
```

## <a name="multisetemplace"></a><a name="emplace"></a>çok ayarlı::emplace

Yerine oluşturulmuş bir öğe ekler (kopya veya taşıma işlemleri yapılmaz), bir yerleşim ipucu ile.

```cpp
template <class... Args>
iterator emplace(Args&&... args);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|-|-|
|*Args*|Çok kümeye eklenecek bir öğe oluşturmak için iletilen bağımsız değişkenler.|

### <a name="return-value"></a>Dönüş Değeri

Yeni eklenen öğeiçin bir yineleyici.

### <a name="remarks"></a>Açıklamalar

Kapsayıcı öğelere yapılan başvurular bu işlev tarafından geçersiz kılınz, ancak kapsayıcıya tüm yineleyicileri geçersiz kılabilir.

Yerleşim sırasında, bir özel durum atılırsa, kapsayıcının durumu değiştirilmez.

### <a name="example"></a>Örnek

```cpp
// multiset_emplace.cpp
// compile with: /EHsc
#include <set>
#include <string>
#include <iostream>

using namespace std;

template <typename S> void print(const S& s) {
    cout << s.size() << " elements: ";

    for (const auto& p : s) {
        cout << "(" << p << ") ";
    }

    cout << endl;
}

int main()
{
    multiset<string> s1;

    s1.emplace("Anna");
    s1.emplace("Bob");
    s1.emplace("Carmine");

    cout << "multiset modified, now contains ";
    print(s1);
    cout << endl;

    s1.emplace("Bob");

    cout << "multiset modified, now contains ";
    print(s1);
    cout << endl;
}
```

## <a name="multisetemplace_hint"></a><a name="emplace_hint"></a>çok ayarlı::emplace_hint

Yerine oluşturulmuş bir öğe ekler (kopya veya taşıma işlemleri yapılmaz), bir yerleşim ipucu ile.

```cpp
template <class... Args>
iterator emplace_hint(
    const_iterator where,
    Args&&... args);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|-|-|
|*Args*|Çok kümeye eklenecek bir öğe oluşturmak için iletilen bağımsız değişkenler.|
|*Nerede*|Doğru ekleme noktasını aramaya başlamak için yer. (Bu nokta hemen *önce,* ekleme logaritmik zaman yerine amortismanlı sabit zaman oluşabilir.)|

### <a name="return-value"></a>Dönüş Değeri

Yeni eklenen öğeiçin bir yineleyici.

### <a name="remarks"></a>Açıklamalar

Kapsayıcı öğelere yapılan başvurular bu işlev tarafından geçersiz kılınz, ancak kapsayıcıya tüm yineleyicileri geçersiz kılabilir.

Yerleşim sırasında, bir özel durum atılırsa, kapsayıcının durumu değiştirilmez.

Kod örneği için [bkz: set:emplace_hint.](../standard-library/set-class.md#emplace_hint)

## <a name="multisetempty"></a><a name="empty"></a>çok ayarlı::boş

Çoklu küme boşsa sınar.

```cpp
bool empty() const;
```

### <a name="return-value"></a>Dönüş Değeri

çoklu küme boşsa **doğrudur;** çoklu küme boş değilse **false.**

### <a name="example"></a>Örnek

```cpp
// multiset_empty.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main( )
{
   using namespace std;
   multiset <int> ms1, ms2;
   ms1.insert ( 1 );

   if ( ms1.empty( ) )
      cout << "The multiset ms1 is empty." << endl;
   else
      cout << "The multiset ms1 is not empty." << endl;

   if ( ms2.empty( ) )
      cout << "The multiset ms2 is empty." << endl;
   else
      cout << "The multiset ms2 is not empty." << endl;
}
```

```Output
The multiset ms1 is not empty.
The multiset ms2 is empty.
```

## <a name="multisetend"></a><a name="end"></a>çok ayarlı::uç

past-the-end yineleyici döndürür.

```cpp
const_iterator end() const;

iterator end();
```

### <a name="return-value"></a>Dönüş Değeri

Son sınıf yineleme. Çoklu küme boşsa, `multiset::end() == multiset::begin()`o zaman.

### <a name="remarks"></a>Açıklamalar

**sonu,** bir yineleyicinin çoklu kümesinin sonundan geçip geçmediğini test etmek için kullanılır.

**Sonuna kadar** döndürülen değer dereferenced olmamalıdır.

Kod örneği [için, bkz.](#find)

## <a name="multisetequal_range"></a><a name="equal_range"></a>çok ayarlı::equal_range

Belirtilen bir anahtardan büyük bir anahtarla bir çok kümedeki ilk öğeye ve anahtara eşit veya daha büyük bir anahtarla çok kümedeki ilk öğeye sırasıyla bir çift yineleyici döndürür.

```cpp
pair <const_iterator, const_iterator> equal_range (const Key& key) const;

pair <iterator, iterator> equal_range (const Key& key);
```

### <a name="parameters"></a>Parametreler

*Anahtar*\
Aralanan çoklu kümedeki bir öğenin tür anahtarıyla karşılaştırılacak bağımsız değişken anahtarı.

### <a name="return-value"></a>Dönüş Değeri

İlki anahtarın [lower_bound,](#lower_bound) ikincisi anahtarın [upper_bound](#upper_bound) olacak şekilde bir çift yineleyici.

Üye işlev tarafından döndürülen bir `pr` çiftin ilk yineleyicisine `pr`erişmek için. **ilk**, ve alt sınır yineleyici dereference \* `pr`için, kullanın ( . **ilk**). Üye işlev tarafından döndürülen bir `pr` çiftin ikinci yineleyicisine `pr`erişmek için. **ikinci**ve üst sınır yineleyicide dereference \*için, kullanın ( `pr`. **ikinci**).

### <a name="example"></a>Örnek

```cpp
// multiset_equal_range.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main( )
{
   using namespace std;
   typedef multiset<int, less<int> > IntSet;
   IntSet ms1;
   multiset <int> :: const_iterator ms1_RcIter;

   ms1.insert( 10 );
   ms1.insert( 20 );
   ms1.insert( 30 );

   pair <IntSet::const_iterator, IntSet::const_iterator> p1, p2;
   p1 = ms1.equal_range( 20 );

   cout << "The upper bound of the element with "
        << "a key of 20 in the multiset ms1 is: "
        << *( p1.second ) << "." << endl;

   cout << "The lower bound of the element with "
        << "a key of 20 in the multiset ms1 is: "
        << *( p1.first ) << "." << endl;

   // Compare the upper_bound called directly
   ms1_RcIter = ms1.upper_bound( 20 );
   cout << "A direct call of upper_bound( 20 ) gives "
        << *ms1_RcIter << "," << endl
        << "matching the 2nd element of the pair"
        << " returned by equal_range( 20 )." << endl;

   p2 = ms1.equal_range( 40 );

   // If no match is found for the key,
   // both elements of the pair return end( )
   if ( ( p2.first == ms1.end( ) ) && ( p2.second == ms1.end( ) ) )
      cout << "The multiset ms1 doesn't have an element "
              << "with a key less than 40." << endl;
   else
      cout << "The element of multiset ms1 with a key >= 40 is: "
                << *( p1.first ) << "." << endl;
}
```

```Output
The upper bound of the element with a key of 20 in the multiset ms1 is: 30.
The lower bound of the element with a key of 20 in the multiset ms1 is: 20.
A direct call of upper_bound( 20 ) gives 30,
matching the 2nd element of the pair returned by equal_range( 20 ).
The multiset ms1 doesn't have an element with a key less than 40.
```

## <a name="multiseterase"></a><a name="erase"></a>çok ayarlı::silme

Çok ayardaki bir öğeyi veya bir dizi öğeyi belirtilen konumlardan kaldırır veya belirtilen anahtarla eşleşen öğeleri kaldırır.

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

*Nerede*\
Kaldırılacak öğenin konumu.

*Ilk*\
Kaldırılacak ilk öğenin konumu.

*Son*\
Kaldırılacak son öğenin hemen ötesine yerleştirin.

*Anahtar*\
Kaldırılacak öğelerin anahtar değeri.

### <a name="return-value"></a>Dönüş Değeri

İlk iki üye işlev için, kaldırılan öğelerin ötesinde kalan ilk öğeyi belirleyen çift yönlü bir yineleyici veya böyle bir öğe yoksa çoklu kümenin sonu olan bir öğe.

Üçüncü üye işlev için, çoklu kümeden kaldırılan öğe sayısını döndürür.

### <a name="remarks"></a>Açıklamalar

Kod örneği için [bkz: set::sil](../standard-library/set-class.md#erase).

## <a name="multisetfind"></a><a name="find"></a>çok ayarlı::bul

Belirli bir anahtara eşdeğer anahtara sahip bir çok kümedeki bir öğenin konumunu ifade eden bir yineleyici döndürür.

```cpp
iterator find(const Key& key);

const_iterator find(const Key& key) const;
```

### <a name="parameters"></a>Parametreler

*Anahtar*\
Aranmakta olan çok ayarlı bir öğenin tür anahtarıyla eşleşecek anahtar değeri.

### <a name="return-value"></a>Dönüş Değeri

Belirli bir anahtara sahip bir öğenin konumunu veya anahtar için eşleşme bulunamazsa çok kümedeki son öğeyi () `multiset::end()`başaran konumu ifade eden bir yineleyici.

### <a name="remarks"></a>Açıklamalar

Üye işlev, çoklu kümedeki anahtarı, karşılaştırılabilirlik ilişkisinden daha az bir ilişkiye dayalı bir sıralamayı neden eden ikili bir yüklem altında bağımsız değişken *anahtarına* eşdeğer olan bir öğeyi ifade eden bir yineleyici döndürür.

Bir `const_iterator`, çok `find` ayarlı nesnenin geri dönüş değeri ne olursa olsun değiştirilemez. Bir , çok `find` ayarlı `iterator`nesnenin geri dönüş değeri ne olursa olsun değiştirilebilir

### <a name="example"></a>Örnek

```cpp
// compile with: /EHsc /W4 /MTd
#include <set>
#include <iostream>
#include <vector>
#include <string>

using namespace std;

template <typename T> void print_elem(const T& t) {
    cout << "(" << t << ") ";
}

template <typename T> void print_collection(const T& t) {
    cout << t.size() << " elements: ";

    for (const auto& p : t) {
        print_elem(p);
    }
    cout << endl;
}

template <typename C, class T> void findit(const C& c, T val) {
    cout << "Trying find() on value " << val << endl;
    auto result = c.find(val);
    if (result != c.end()) {
        cout << "Element found: "; print_elem(*result); cout << endl;
    } else {
        cout << "Element not found." << endl;
    }
}

int main()
{
    multiset<int> s1({ 40, 45 });
    cout << "The starting multiset s1 is: " << endl;
    print_collection(s1);

    vector<int> v;
    v.push_back(43);
    v.push_back(41);
    v.push_back(46);
    v.push_back(42);
    v.push_back(44);
    v.push_back(44); // attempt a duplicate

    cout << "Inserting the following vector data into s1: " << endl;
    print_collection(v);

    s1.insert(v.begin(), v.end());

    cout << "The modified multiset s1 is: " << endl;
    print_collection(s1);
    cout << endl;
    findit(s1, 45);
    findit(s1, 6);
}
```

## <a name="multisetget_allocator"></a><a name="get_allocator"></a>çok ayarlı::get_allocator

Çok kümeoluşturmak için kullanılan ayırıcı nesnenin bir kopyasını döndürür.

```cpp
allocator_type get_allocator() const;
```

### <a name="return-value"></a>Dönüş Değeri

Çok ayarlı tarafından kullanılan ayırıcı.

### <a name="remarks"></a>Açıklamalar

Çok ayarlı sınıfın ayırıcıları sınıfın depolamayı nasıl yönettiğini belirtir. C++ Standart Kitaplık kapsayıcı sınıfları ile birlikte verilen varsayılan ayırıcılar çoğu programlama gereksinimleri için yeterlidir. Kendi ayırıcı sınıfınızı yazmak ve kullanmak gelişmiş bir C++ konusudur.

### <a name="example"></a>Örnek

```cpp
// multiset_get_allocator.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main( )
{
   using namespace std;
   multiset <int>::allocator_type ms1_Alloc;
   multiset <int>::allocator_type ms2_Alloc;
   multiset <double>::allocator_type ms3_Alloc;
   multiset <int>::allocator_type ms4_Alloc;

   // The following lines declare objects
   // that use the default allocator.
   multiset <int> ms1;
   multiset <int, allocator<int> > ms2;
   multiset <double, allocator<double> > ms3;

   cout << "The number of integers that can be allocated"
        << endl << "before free memory is exhausted: "
        << ms2.max_size( ) << "." << endl;

   cout << "The number of doubles that can be allocated"
        << endl << "before free memory is exhausted: "
        << ms3.max_size( ) <<  "." << endl;

   // The following lines create a multiset ms4
   // with the allocator of multiset ms1
   ms1_Alloc = ms1.get_allocator( );
   multiset <int> ms4( less<int>( ), ms1_Alloc );
   ms4_Alloc = ms4.get_allocator( );

   // Two allocators are interchangeable if
   // storage allocated from each can be
   // deallocated with the other
   if( ms1_Alloc == ms4_Alloc )
   {
      cout << "Allocators are interchangeable."
           << endl;
   }
   else
   {
      cout << "Allocators are not interchangeable."
           << endl;
   }
}
```

## <a name="multisetinsert"></a><a name="insert"></a>çok ayarlı::insert

Bir öğeyi veya bir dizi öğeyi çoklu kümeye ekler.

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
|*Val*|Çoklu kümeye eklenecek bir öğenin değeri.|
|*Nerede*|Doğru ekleme noktasını aramaya başlamak için yer. (Bu nokta hemen *nerede,* ekleme logaritmik zaman yerine amortismanlı sabit zaman oluşabilir önce gelir.)|
|*Valty*|Çoklu kümenin [value_type](../standard-library/map-class.md#value_type)bir öğe oluşturmak için kullanabileceği bağımsız değişken türünü belirten şablon parametresi ve *val'i* bağımsız değişken olarak mükemmel iletme.|
|*Ilk*|Kopyalanacak ilk öğenin konumu.|
|*Son*|Kopyalanacak son öğenin hemen ötesindeki konum.|
|*GirişIterator*|Value_type [nesneleri](../standard-library/map-class.md#value_type) oluşturmak için kullanılabilecek bir tür öğeleri işaret eden bir [giriş yineleyici](../standard-library/input-iterator-tag-struct.md) gereksinimlerini karşılayan şablon işlev bağımsız değişkeni.|
|*ılist*|Öğeleri kopyalamak için [initializer_list.](../standard-library/initializer-list.md)|

### <a name="return-value"></a>Dönüş Değeri

Tek öğeli ekleme üye işlevleri (1) ve (2), bir yineleyiciyi yeni öğenin çoklu kümeye eklendiği konuma döndürür.

İpucu ile tek elemanlı üye işlevler( 3) ve (4), yeni öğenin çoklu kümeye eklendiği konuma işaret eden bir yineleyici döndürür.

### <a name="remarks"></a>Açıklamalar

Bu işlev tarafından hiçbir işaretçi veya başvuru geçersiz kılındı, ancak kapsayıcıya tüm yineleyicileri geçersiz kılabilir.

Tek bir öğenin eklenmesi sırasında, bir özel durum atılırsa, kapsayıcının durumu değiştirilmez. Birden çok öğe nin eklenmesi sırasında, bir özel durum atılırsa, kapsayıcı belirtilmemiş ancak geçerli bir durumda bırakılır.

Bir kapsayıcının [value_type](../standard-library/map-class.md#value_type) kapsayıcıya ait bir typedef ve küme `multiset<V>::value_type` için `const V`türü.

Aralık üye işlevi (5), aralıktaki bir yineleyici tarafından ele verilen her elemana karşılık gelen bir `[First, Last)`çoklu kümeye öğe değerlerinin sırasını ekler; bu `Last` nedenle, takılı almaz. Kapsayıcı üye `end()` işlevi, kapsayıcıdaki son öğeden hemen sonra konumu ifade `s.insert(v.begin(), v.end());` eder—örneğin, `v` deyim `s`tüm öğeleri .

Initializer list üye işlevi (6) öğeleri çoklu kümeye kopyalamak için [bir initializer_list](../standard-library/initializer-list.md) kullanır.

Yerinde inşa edilmiş bir öğenin eklenmesi için-yani, hiçbir kopyalama veya taşıma işlemleri [gerçekleştirilir-bkz. multiset::emplace](#emplace) ve [multiset::emplace_hint](#emplace_hint).

### <a name="example"></a>Örnek

```cpp
// multiset_insert.cpp
// compile with: /EHsc
#include <set>
#include <iostream>
#include <string>
#include <vector>

using namespace std;

template <typename S> void print(const S& s) {
    cout << s.size() << " elements: ";

    for (const auto& p : s) {
        cout << "(" << p << ") ";
    }

    cout << endl;
}

int main()
{

    // insert single values
    multiset<int> s1;
    // call insert(const value_type&) version
    s1.insert({ 1, 10 });
    // call insert(ValTy&&) version
    s1.insert(20);

    cout << "The original multiset values of s1 are:" << endl;
    print(s1);

    // intentionally attempt a duplicate, single element
    s1.insert(1);
    cout << "The modified multiset values of s1 are:" << endl;
    print(s1);
    cout << endl;

    // single element, with hint
    s1.insert(s1.end(), 30);
    cout << "The modified multiset values of s1 are:" << endl;
    print(s1);
    cout << endl;

    // The templatized version inserting a jumbled range
    multiset<int> s2;
    vector<int> v;
    v.push_back(43);
    v.push_back(294);
    v.push_back(41);
    v.push_back(330);
    v.push_back(42);
    v.push_back(45);

    cout << "Inserting the following vector data into s2:" << endl;
    print(v);

    s2.insert(v.begin(), v.end());

    cout << "The modified multiset values of s2 are:" << endl;
    print(s2);
    cout << endl;

    // The templatized versions move-constructing elements
    multiset<string>  s3;
    string str1("blue"), str2("green");

    // single element
    s3.insert(move(str1));
    cout << "After the first move insertion, s3 contains:" << endl;
    print(s3);

    // single element with hint
    s3.insert(s3.end(), move(str2));
    cout << "After the second move insertion, s3 contains:" << endl;
    print(s3);
    cout << endl;

    multiset<int> s4;
    // Insert the elements from an initializer_list
    s4.insert({ 4, 44, 2, 22, 3, 33, 1, 11, 5, 55 });
    cout << "After initializer_list insertion, s4 contains:" << endl;
    print(s4);
    cout << endl;
}
```

## <a name="multisetiterator"></a><a name="iterator"></a>çok ayarlı::iterator

Bir çok kümedeki herhangi bir [öğeyi](../standard-library/bidirectional-iterator-tag-struct.md) okuyabilen sabit bir çift yönlü yineleme sağlayan bir tür.

```cpp
typedef implementation-defined iterator;
```

### <a name="example"></a>Örnek

Nasıl bildirilir [begin](#begin) ve kullanılacağına bir örnek için `iterator`başlangıç örneğine bakın.

## <a name="multisetkey_comp"></a><a name="key_comp"></a>çok ayarlı:key_comp

Çoklu kümedeki anahtarları sipariş etmek için kullanılan karşılaştırma nesnesinin bir kopyasını alır.

```cpp
key_compare key_comp() const;
```

### <a name="return-value"></a>Dönüş Değeri

Şablon parametresi `Compare`olan öğelerini sıralamak için çok ayarlının kullandığı işlev nesnesini döndürür.

Daha fazla `Compare`bilgi [için, çok ayarlı Sınıf](../standard-library/multiset-class.md) konusunun Açıklamalar bölümüne bakın.

### <a name="remarks"></a>Açıklamalar

Depolanan nesne üye işlevi tanımlar:

**bool operatoru**( **const Key&** *x*, **const Key&** *y*);

*x* kesinlikle sıralama sırasına göre *y'den* önce yse doğru döner.

Hem [key_compare](#key_compare) hem de [value_compare](#value_compare) şablon parametresi `Compare`ile eş anlamlı olduğunu unutmayın. Her iki tür de sınıflar haritası ve çoklu harita ile uyumluluk için, farklı oldukları sınıflar kümesi ve çoklu küme, için sağlanır.

### <a name="example"></a>Örnek

```cpp
// multiset_key_comp.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main( )
{
   using namespace std;

   multiset <int, less<int> > ms1;
   multiset <int, less<int> >::key_compare kc1 = ms1.key_comp( ) ;
   bool result1 = kc1( 2, 3 ) ;
   if( result1 == true )
   {
      cout << "kc1( 2,3 ) returns value of true, "
           << "where kc1 is the function object of s1."
           << endl;
   }
   else
   {
      cout << "kc1( 2,3 ) returns value of false "
           << "where kc1 is the function object of ms1."
           << endl;
   }

   multiset <int, greater<int> > ms2;
   multiset <int, greater<int> >::key_compare kc2 = ms2.key_comp( ) ;
   bool result2 = kc2( 2, 3 ) ;
   if( result2 == true )
   {
      cout << "kc2( 2,3 ) returns value of true, "
           << "where kc2 is the function object of ms2."
           << endl;
   }
   else
   {
      cout << "kc2( 2,3 ) returns value of false, "
           << "where kc2 is the function object of ms2."
           << endl;
   }
}
```

```Output
kc1( 2,3 ) returns value of true, where kc1 is the function object of s1.
kc2( 2,3 ) returns value of false, where kc2 is the function object of ms2.
```

## <a name="multisetkey_compare"></a><a name="key_compare"></a>çok ayarlı::key_compare

Çoklu kümedeki iki öğenin göreli sırasını belirlemek için iki sıralama anahtarını karşılaştırabilen bir işlev nesnesi sağlayan bir tür.

```cpp
typedef Compare key_compare;
```

### <a name="remarks"></a>Açıklamalar

`key_compare`şablon parametresi `Compare`ile eş anlamlıdır.

Daha fazla `Compare`bilgi [için, çok ayarlı Sınıf](../standard-library/multiset-class.md) konusunun Açıklamalar bölümüne bakın.

### <a name="example"></a>Örnek

Nasıl bildirilir [key_comp](#key_comp) ve kullanılacağına `key_compare`ilgili bir örnek için key_comp örneğine bakın.

## <a name="multisetkey_type"></a><a name="key_type"></a>çok ayarlı::key_type

Çoklu kümedeki iki öğenin göreli sırasını belirlemek için sıralama anahtarlarını karşılaştırabilen bir işlev nesnesi sağlayan bir tür.

```cpp
typedef Key key_type;
```

### <a name="remarks"></a>Açıklamalar

`key_type`şablon parametresi `Key`ile eş anlamlıdır.

Daha fazla `Key`bilgi [için, çok ayarlı Sınıf](../standard-library/multiset-class.md) konusunun Açıklamalar bölümüne bakın.

### <a name="example"></a>Örnek

[Nasıl](#value_type) beyan value_type ve kullanılacağına `key_type`bir örnek için bkz.

## <a name="multisetlower_bound"></a><a name="lower_bound"></a>çok ayarlı::lower_bound

Bir çok kümedeki ilk öğeye, belirtilen anahtara eşit veya daha büyük bir anahtarla bir yineleyici döndürür.

```cpp
const_iterator lower_bound(const Key& key) const;

iterator lower_bound(const Key& key);
```

### <a name="parameters"></a>Parametreler

*Anahtar*\
Aralanan çoklu kümedeki bir öğenin tür anahtarıyla karşılaştırılacak bağımsız değişken anahtarı.

### <a name="return-value"></a>Dönüş Değeri

Bir `iterator` `const_iterator` veya bağımsız değişken anahtarına eşit veya daha büyük bir anahtarla bir çok kümedeki öğenin konumunu gideren veya anahtar için eşleşme yoksa çoklu kümedeki son öğeden sonra gelen konumu gideren bir öğe.

### <a name="example"></a>Örnek

```cpp
// multiset_lower_bound.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main( )
{
   using namespace std;
   multiset <int> ms1;
   multiset <int> :: const_iterator ms1_AcIter, ms1_RcIter;

   ms1.insert( 10 );
   ms1.insert( 20 );
   ms1.insert( 30 );

   ms1_RcIter = ms1.lower_bound( 20 );
   cout << "The element of multiset ms1 with a key of 20 is: "
        << *ms1_RcIter << "." << endl;

   ms1_RcIter = ms1.lower_bound( 40 );

   // If no match is found for the key, end( ) is returned
   if ( ms1_RcIter == ms1.end( ) )
      cout << "The multiset ms1 doesn't have an element "
           << "with a key of 40." << endl;
   else
      cout << "The element of multiset ms1 with a key of 40 is: "
           << *ms1_RcIter << "." << endl;

   // The element at a specific location in the multiset can be
   // found using a dereferenced iterator addressing the location
   ms1_AcIter = ms1.end( );
   ms1_AcIter--;
   ms1_RcIter = ms1.lower_bound( *ms1_AcIter );
   cout << "The element of ms1 with a key matching "
        << "that of the last element is: "
        << *ms1_RcIter << "." << endl;
}
```

```Output
The element of multiset ms1 with a key of 20 is: 20.
The multiset ms1 doesn't have an element with a key of 40.
The element of ms1 with a key matching that of the last element is: 30.
```

## <a name="multisetmax_size"></a><a name="max_size"></a>çok ayarlı::max_size

Çoklu kümenin maksimum uzunluğunu verir.

```cpp
size_type max_size() const;
```

### <a name="return-value"></a>Dönüş Değeri

Çoklu setin mümkün olan en fazla uzunluğu.

### <a name="example"></a>Örnek

```cpp
// multiset_max_size.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main( )
{
   using namespace std;
   multiset <int> ms1;
   multiset <int>::size_type i;

   i = ms1.max_size( );
   cout << "The maximum possible length "
        << "of the multiset is " << i << "." << endl;
}
```

## <a name="multisetmultiset"></a><a name="multiset"></a>çok ayarlı::çok setli

Boş veya başka bir çok kümenin tamamının veya bir kısmının kopyası olan bir çoklu küme oluşturuyor.

```cpp
multiset();

explicit multiset (
    const Compare& Comp);

multiset (
    const Compare& Comp,
    const Allocator& Al);

multiset(
    const multiset& Right);

multiset(
    multiset&& Right);

multiset(
    initializer_list<Type> IList);

multiset(
    initializer_list<Type> IList,
    const Compare& Comp);

multiset(
    initializer_list<Type> IList,
    const Compare& Comp,
    const Allocator& Al);

template <class InputIterator>
multiset (
    InputIterator First,
    InputIterator Last);

template <class InputIterator>
multiset (
    InputIterator First,
    InputIterator Last,
    const Compare& Comp);

template <class InputIterator>
multiset (
    InputIterator First,
    InputIterator Last,
    const Compare& Comp,
    const Allocator& Al);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|-|-|
|*Al*|Bu çok ayarlı nesne için kullanılacak depolama ayırıcı `Allocator`sınıfı, varsayılan olarak .|
|*Comp*|Çoklu kümedeki `const Compare` öğeleri sıralamak için kullanılan tür karşılaştırma işlevi, varsayılan `Compare`olarak .|
|*Doğru*|Hangi inşa multiset bir kopyası olmaktır multiset.|
|*Ilk*|Kopyalanacak öğeler aralığındaki ilk öğenin konumu.|
|*Son*|İlk öğenin kopyalanacak öğe aralığının ötesindeki konumu.|
|*ılist*|Öğelerin kopyalanacağı initializer_list.|

### <a name="remarks"></a>Açıklamalar

Tüm oluşturucular, çok ayarlı bellek depolamayı yöneten ve daha sonra [get_allocator](#get_allocator)çağırarak döndürülebilen bir allocator nesnesi türünü depolar. Ayırıcı parametresi genellikle sınıf bildirimlerinde ve alternatif ayırıcıların yerine kullanılan ön işleme makrolarında atlanır.

Tüm yapıcılar çoklu kümelerini ortaya koymak.

Tüm oluşturucular, çoklu kümenin anahtarları arasında bir sipariş oluşturmak için kullanılan ve daha sonra [key_comp](#key_comp)çağırarak döndürülebilen bir işlev nesnesini karşılaştır yazın türünde bir işlev nesnesi depolar.

İlk üç oluşturucu boş bir ilk çoklu küme belirtir, ikinci karşılaştırma fonksiyonu nun türünü belirten *(Comp*) elemanların sırasını oluştururken kullanılacak ve üçüncü açıkça tahsis türünü belirten *(Al)* kullanılacak. Anahtar kelime **açık** otomatik tür dönüştürme belirli türleri bastırır.

Dördüncü oluşturucu, çok ayarlı *Sağ'ın*bir kopyasını belirtir.

Beşinci oluşturucu *sağ*hareket ettirerek multiset bir kopyasını belirtir.

Altıncı, yedinci ve sekizinci kurucular, öğeleri kopyalamak için bir initializer_list belirtir.

Sonraki üç oluşturucu, karşılaştırma `[First, Last)` işlevi ve ayırıcıtürünü belirtirken artan açıklıkla bir çok kümenin aralığını kopyalar.

### <a name="example"></a>Örnek

```cpp
// multiset_ctor.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main()
{
    using namespace std;
    //multiset <int>::iterator ms1_Iter, ms2_Iter, ms3_Iter;
    multiset <int>::iterator ms4_Iter, ms5_Iter, ms6_Iter, ms7_Iter;

    // Create an empty multiset ms0 of key type integer
    multiset <int> ms0;

    // Create an empty multiset ms1 with the key comparison
    // function of less than, then insert 4 elements
    multiset <int, less<int> > ms1;
    ms1.insert(10);
    ms1.insert(20);
    ms1.insert(20);
    ms1.insert(40);

    // Create an empty multiset ms2 with the key comparison
    // function of greater than, then insert 2 elements
    multiset <int, less<int> > ms2;
    ms2.insert(10);
    ms2.insert(20);

    // Create a multiset ms3 with the
    // allocator of multiset ms1
    multiset <int>::allocator_type ms1_Alloc;
    ms1_Alloc = ms1.get_allocator();
    multiset <int> ms3(less<int>(), ms1_Alloc);
    ms3.insert(30);

    // Create a copy, multiset ms4, of multiset ms1
    multiset <int> ms4(ms1);

    // Create a multiset ms5 by copying the range ms1[ first,  last)
    multiset <int>::const_iterator ms1_bcIter, ms1_ecIter;
    ms1_bcIter = ms1.begin();
    ms1_ecIter = ms1.begin();
    ms1_ecIter++;
    ms1_ecIter++;
    multiset <int> ms5(ms1_bcIter, ms1_ecIter);

    // Create a multiset ms6 by copying the range ms4[ first,  last)
    // and with the allocator of multiset ms2
    multiset <int>::allocator_type ms2_Alloc;
    ms2_Alloc = ms2.get_allocator();
    multiset <int> ms6(ms4.begin(), ++ms4.begin(), less<int>(), ms2_Alloc);

    cout << "ms1 =";
    for (auto i : ms1)
        cout << " " << i;
    cout << endl;

    cout << "ms2 =";
    for (auto i : ms2)
        cout << " " << i;
   cout << endl;

   cout << "ms3 =";
   for (auto i : ms3)
       cout << " " << i;
    cout << endl;

    cout << "ms4 =";
    for (auto i : ms4)
        cout << " " << i;
    cout << endl;

    cout << "ms5 =";
    for (auto i : ms5)
        cout << " " << i;
    cout << endl;

    cout << "ms6 =";
    for (auto i : ms6)
        cout << " " << i;
    cout << endl;

    // Create a multiset by moving ms5
    multiset<int> ms7(move(ms5));
    cout << "ms7 =";
    for (auto i : ms7)
        cout << " " << i;
    cout << endl;

    // Create a multiset with an initializer_list
    multiset<int> ms8({1, 2, 3, 4});
    cout << "ms8=";
    for (auto i : ms8)
        cout << " " << i;
    cout << endl;
}
```

## <a name="multisetoperator"></a><a name="op_eq"></a>çok set::operator=

Başka bir öğeden `multiset` öğeleri kullanarak `multiset`bu öğeleri değiştirir.

```cpp
multiset& operator=(const multiset& right);

multiset& operator=(multiset&& right);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|-|-|
|*Doğru*|Öğelerin `multiset` kopyalandığı veya taşındığı.|

### <a name="remarks"></a>Açıklamalar

`operator=`kullanılan referans türüne (lvalue `multiset`veya rvalue) bağlı olarak, *bu sağdaki* öğeleri kopyalar veya taşır. Yürütülmelerden `multiset` önce `operator=` bu öğeler atılır.

### <a name="example"></a>Örnek

```cpp
// multiset_operator_as.cpp
// compile with: /EHsc
#include <multiset>
#include <iostream>

int main( )
   {
   using namespace std;
   multiset<int> v1, v2, v3;
   multiset<int>::iterator iter;

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

## <a name="multisetpointer"></a><a name="pointer"></a>çok set::pointer

Çok kümedeki bir öğeye işaretçi sağlayan bir tür.

```cpp
typedef typename allocator_type::pointer pointer;
```

### <a name="remarks"></a>Açıklamalar

Bir tür **işaretçisi** bir öğenin değerini değiştirmek için kullanılabilir.

Çoğu durumda, çok ayarlı bir nesnedeki öğelere erişmek için bir [yineleyici](#iterator) kullanılmalıdır.

## <a name="multisetrbegin"></a><a name="rbegin"></a>çok ayarlı::rbegin

Ters bir çoklu kümedeki ilk öğeyi ele alan bir yineleyici döndürür.

```cpp
const_reverse_iterator rbegin() const;

reverse_iterator rbegin();
```

### <a name="return-value"></a>Dönüş Değeri

Ters bir çoklu kümedeki ilk öğeyi ele alan veya ters çevrilmemiş çoklu kümedeki son öğeyi ele alan ters çift yönlü bir yineleme.

### <a name="remarks"></a>Açıklamalar

`rbegin`rbegin bir çoklu set ile kullanıldığı gibi ters bir multiset ile kullanılır.

Bir `const_reverse_iterator`, çok `rbegin` ayarlı nesnenin geri dönüş değeri ne olursa olsun değiştirilemez. Bir `reverse_iterator`, çok `rbegin` ayarlı nesnenin geri dönüş değeri atanırsa değiştirilebilir.

`rbegin`geriye doğru bir çoklu küme üzerinden yinelemek için kullanılabilir.

### <a name="example"></a>Örnek

```cpp
// multiset_rbegin.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main( )
{
   using namespace std;
   multiset <int> ms1;
   multiset <int>::iterator ms1_Iter;
   multiset <int>::reverse_iterator ms1_rIter;

   ms1.insert( 10 );
   ms1.insert( 20 );
   ms1.insert( 30 );

   ms1_rIter = ms1.rbegin( );
   cout << "The first element in the reversed multiset is "
        << *ms1_rIter << "." << endl;

   // begin can be used to start an iteration
   // through a multiset in a forward order
   cout << "The multiset is:";
   for ( ms1_Iter = ms1.begin( ) ; ms1_Iter != ms1.end( ); ms1_Iter++ )
      cout << " " << *ms1_Iter;
   cout << endl;

   // rbegin can be used to start an iteration
   // through a multiset in a reverse order
   cout << "The reversed multiset is:";
   for ( ms1_rIter = ms1.rbegin( ) ; ms1_rIter != ms1.rend( ); ms1_rIter++ )
      cout << " " << *ms1_rIter;
   cout << endl;

   // A multiset element can be erased by dereferencing to its key
   ms1_rIter = ms1.rbegin( );
   ms1.erase ( *ms1_rIter );

   ms1_rIter = ms1.rbegin( );
   cout << "After the erasure, the first element "
        << "in the reversed multiset is "<< *ms1_rIter << "."
        << endl;
}
```

```Output
The first element in the reversed multiset is 30.
The multiset is: 10 20 30
The reversed multiset is: 30 20 10
After the erasure, the first element in the reversed multiset is 20.
```

## <a name="multisetreference"></a><a name="reference"></a>çok ayarlı::başvuru

Çok kümede depolanan bir öğeye başvuru sağlayan bir tür.

```cpp
typedef typename allocator_type::reference reference;
```

### <a name="example"></a>Örnek

```cpp
// multiset_ref.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main( )
{
   using namespace std;
   multiset <int> ms1;

   ms1.insert( 10 );
   ms1.insert( 20 );

   // Declare and initialize a reference &Ref1 to the 1st element
   const int &Ref1 = *ms1.begin( );

   cout << "The first element in the multiset is "
        << Ref1 << "." << endl;
}
```

```Output
The first element in the multiset is 10.
```

## <a name="multisetrend"></a><a name="rend"></a>çok ayarlı::rend

Ters bir çoklu kümedeki son öğeyi yerine getiren konumu gideren bir yineleyici döndürür.

```cpp
const_reverse_iterator rend() const;

reverse_iterator rend();
```

### <a name="return-value"></a>Dönüş Değeri

Ters bir çoklu kümedeki son öğeyi (ters çevrilmemiş çoklu kümedeki ilk öğeden önce gelen konum) yerine hitap eden ters çift yönlü bir yineleme.

### <a name="remarks"></a>Açıklamalar

`rend`[uç](#end) bir çoklu set ile kullanıldığı gibi ters bir çoklu set ile kullanılır.

Bir `const_reverse_iterator`, çok `rend` ayarlı nesnenin geri dönüş değeri ne olursa olsun değiştirilemez. Bir `reverse_iterator`, çok `rend` ayarlı nesnenin geri dönüş değeri atanırsa değiştirilebilir.

`rend`ters yineleyicinin çoklu kümesinin sonuna ulaşıp ulaşmadığını test etmek için kullanılabilir.

Döndürülen `rend` değer dereferenced olmamalıdır.

### <a name="example"></a>Örnek

```cpp
// multiset_rend.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main() {
   using namespace std;
   multiset <int> ms1;
   multiset <int>::iterator ms1_Iter;
   multiset <int>::reverse_iterator ms1_rIter;
   multiset <int>::const_reverse_iterator ms1_crIter;

   ms1.insert( 10 );
   ms1.insert( 20 );
   ms1.insert( 30 );

   ms1_rIter = ms1.rend( ) ;
   ms1_rIter--;
   cout << "The last element in the reversed multiset is "
        << *ms1_rIter << "." << endl;

   // end can be used to terminate an iteration
   // through a multiset in a forward order
   cout << "The multiset is: ";
   for ( ms1_Iter = ms1.begin( ) ; ms1_Iter != ms1.end( ); ms1_Iter++ )
      cout << *ms1_Iter << " ";
   cout << "." << endl;

   // rend can be used to terminate an iteration
   // through a multiset in a reverse order
   cout << "The reversed multiset is: ";
   for ( ms1_rIter = ms1.rbegin( ) ; ms1_rIter != ms1.rend( ); ms1_rIter++ )
      cout << *ms1_rIter << " ";
   cout << "." << endl;

   ms1_rIter = ms1.rend( );
   ms1_rIter--;
   ms1.erase ( *ms1_rIter );

   ms1_rIter = ms1.rend( );
   --ms1_rIter;
   cout << "After the erasure, the last element in the "
        << "reversed multiset is " << *ms1_rIter << "." << endl;
}
```

## <a name="multisetreverse_iterator"></a><a name="reverse_iterator"></a>çok ayarlı::reverse_iterator

Ters bir çoklu kümedeki bir öğeyi okuyabilen veya değiştirebilen çift yönlü bir yineleme sağlayan bir tür.

```cpp
typedef std::reverse_iterator<iterator> reverse_iterator;
```

### <a name="remarks"></a>Açıklamalar

Bir `reverse_iterator` tür ters multiset üzerinden yinelemek için kullanılır.

### <a name="example"></a>Örnek

Nasıl bildirilir ve kullanılır. [rbegin](#rbegin) `reverse_iterator`

## <a name="multisetsize"></a><a name="size"></a>çok ayarlı::boyut

Çoklu kümedeki öğe sayısını verir.

```cpp
size_type size() const;
```

### <a name="return-value"></a>Dönüş Değeri

Çoklu kümenin geçerli uzunluğu.

### <a name="example"></a>Örnek

```cpp
// multiset_size.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main( )
{
   using namespace std;
   multiset <int> ms1;
   multiset <int> :: size_type i;

   ms1.insert( 1 );
   i = ms1.size( );
   cout << "The multiset length is " << i << "." << endl;

   ms1.insert( 2 );
   i = ms1.size( );
   cout << "The multiset length is now " << i << "." << endl;
}
```

```Output
The multiset length is 1.
The multiset length is now 2.
```

## <a name="multisetsize_type"></a><a name="size_type"></a>çok ayarlı::size_type

Çok kümedeki öğe sayısını temsil eden imzasız bir tamsayı türü.

```cpp
typedef typename allocator_type::size_type size_type;
```

### <a name="example"></a>Örnek

Nasıl beyan edilip kullanılacağına bir örnek için [boyut](#size) örneğine bakın`size_type`

## <a name="multisetswap"></a><a name="swap"></a>çok ayarlı::takas

İki çok kümenin öğelerini değiştirir.

```cpp
void swap(
    multiset<Key, Compare, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*Doğru*\
Hedef çok kümeyle değiştirilecek öğeleri sağlayan bağımsız değişken çok kümesi.

### <a name="remarks"></a>Açıklamalar

Üye işlev, öğeleri değiştirilen iki çok kümedeki öğeleri belirleyen hiçbir başvuruyu, işaretçiyi veya yineleyiciyi geçersiz kılmaz.

### <a name="example"></a>Örnek

```cpp
// multiset_swap.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main( )
{
   using namespace std;
   multiset <int> ms1, ms2, ms3;
   multiset <int>::iterator ms1_Iter;

   ms1.insert( 10 );
   ms1.insert( 20 );
   ms1.insert( 30 );
   ms2.insert( 100 );
   ms2.insert( 200 );
   ms3.insert( 300 );

   cout << "The original multiset ms1 is:";
   for ( ms1_Iter = ms1.begin( ); ms1_Iter != ms1.end( ); ms1_Iter++ )
      cout << " " << *ms1_Iter;
   cout << "." << endl;

   // This is the member function version of swap
   ms1.swap( ms2 );

   cout << "After swapping with ms2, list ms1 is:";
   for ( ms1_Iter = ms1.begin( ); ms1_Iter != ms1.end( ); ms1_Iter++ )
      cout << " " << *ms1_Iter;
   cout << "." << endl;

   // This is the specialized template version of swap
   swap( ms1, ms3 );

   cout << "After swapping with ms3, list ms1 is:";
   for ( ms1_Iter = ms1.begin( ); ms1_Iter != ms1.end( ); ms1_Iter++ )
      cout << " " << *ms1_Iter;
   cout   << "." << endl;
}
```

```Output
The original multiset ms1 is: 10 20 30.
After swapping with ms2, list ms1 is: 100 200.
After swapping with ms3, list ms1 is: 300.
```

## <a name="multisetupper_bound"></a><a name="upper_bound"></a>çok ayarlı::upper_bound

Bir çok kümedeki ilk öğeye, belirli bir anahtardan büyük bir anahtarla bir yineleyici döndürür.

```cpp
const_iterator upper_bound(const Key& key) const;

iterator upper_bound(const Key& key);
```

### <a name="parameters"></a>Parametreler

*Anahtar*\
Aralanan çoklu kümedeki bir öğenin tür anahtarıyla karşılaştırılacak bağımsız değişken anahtarı.

### <a name="return-value"></a>Dönüş Değeri

Bir **yineleyici** veya `const_iterator` bağımsız değişken anahtarından daha büyük bir anahtarla çok ayarlı bir öğenin konumunu gideren veya anahtar için eşleşme yoksa çoklu kümedeki son öğeden sonra gelen konumu gideren.

### <a name="example"></a>Örnek

```cpp
// multiset_upper_bound.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main( )
{
   using namespace std;
   multiset <int> ms1;
   multiset <int> :: const_iterator ms1_AcIter, ms1_RcIter;

   ms1.insert( 10 );
   ms1.insert( 20 );
   ms1.insert( 30 );

   ms1_RcIter = ms1.upper_bound( 20 );
   cout << "The first element of multiset ms1 with a key greater "
           << "than 20 is: " << *ms1_RcIter << "." << endl;

   ms1_RcIter = ms1.upper_bound( 30 );

   // If no match is found for the key, end( ) is returned
   if ( ms1_RcIter == ms1.end( ) )
      cout << "The multiset ms1 doesn't have an element "
              << "with a key greater than 30." << endl;
   else
      cout << "The element of multiset ms1 with a key > 40 is: "
           << *ms1_RcIter << "." << endl;

   // The element at a specific location in the multiset can be
   // found using a dereferenced iterator addressing the location
   ms1_AcIter = ms1.begin( );
   ms1_RcIter = ms1.upper_bound( *ms1_AcIter );
   cout << "The first element of ms1 with a key greater than"
        << endl << "that of the initial element of ms1 is: "
        << *ms1_RcIter << "." << endl;
}
```

```Output
The first element of multiset ms1 with a key greater than 20 is: 30.
The multiset ms1 doesn't have an element with a key greater than 30.
The first element of ms1 with a key greater than
that of the initial element of ms1 is: 20.
```

## <a name="multisetvalue_comp"></a><a name="value_comp"></a>çok ayarlı:value_comp

Bir çoklu kümedeki öğe değerlerini sıralamak için kullanılan karşılaştırma nesnesinin bir kopyasını alır.

```cpp
value_compare value_comp() const;
```

### <a name="return-value"></a>Dönüş Değeri

Şablon parametresi `Compare`olan öğelerini sıralamak için çok ayarlının kullandığı işlev nesnesini döndürür.

Daha fazla `Compare`bilgi [için, çok ayarlı Sınıf](../standard-library/multiset-class.md) konusunun Açıklamalar bölümüne bakın.

### <a name="remarks"></a>Açıklamalar

Depolanan nesne üye işlevi tanımlar:

**bool operatoru**( **const Key&** `_xVal`, **const Key&** `_yVal`);

`_xVal` önce yse ve sıralama `_yVal` sırasına eşit değilse doğru döndürür.

Hem [key_compare](#key_compare) hem de [value_compare](#value_compare) şablon parametresi `Compare`ile eş anlamlı olduğunu unutmayın. Her iki tür de sınıflar haritası ve çoklu harita ile uyumluluk için, farklı oldukları sınıflar kümesi ve çoklu küme, için sağlanır.

### <a name="example"></a>Örnek

```cpp
// multiset_value_comp.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main( )
{
   using namespace std;

   multiset <int, less<int> > ms1;
   multiset <int, less<int> >::value_compare vc1 = ms1.value_comp( );
   bool result1 = vc1( 2, 3 );
   if( result1 == true )
   {
      cout << "vc1( 2,3 ) returns value of true, "
           << "where vc1 is the function object of ms1."
           << endl;
   }
   else
   {
      cout << "vc1( 2,3 ) returns value of false, "
           << "where vc1 is the function object of ms1."
           << endl;
   }

   set <int, greater<int> > ms2;
   set<int, greater<int> >::value_compare vc2 = ms2.value_comp( );
   bool result2 = vc2( 2, 3 );
   if( result2 == true )
   {
      cout << "vc2( 2,3 ) returns value of true, "
           << "where vc2 is the function object of ms2."
           << endl;
   }
   else
   {
      cout << "vc2( 2,3 ) returns value of false, "
           << "where vc2 is the function object of ms2."
           << endl;
   }
}
```

```Output
vc1( 2,3 ) returns value of true, where vc1 is the function object of ms1.
vc2( 2,3 ) returns value of false, where vc2 is the function object of ms2.
```

## <a name="multisetvalue_compare"></a><a name="value_compare"></a>çok ayarlı::value_compare

Çoklu kümedeki göreli sıralarını belirlemek için iki sıralama anahtarını karşılaştırabilen bir işlev nesnesi sağlayan tür.

```cpp
typedef key_compare value_compare;
```

### <a name="remarks"></a>Açıklamalar

`value_compare`şablon parametresi `Compare`ile eş anlamlıdır.

[Hem key_compare](#key_compare) hem `value_compare` de şablon parametresi `Compare`ile eş anlamlı dır. Her iki tür de sınıflar haritası ve çoklu harita ile uyumluluk için, farklı oldukları sınıflar kümesi ve çoklu küme, için sağlanır.

Daha fazla `Compare`bilgi [için, çok ayarlı Sınıf](../standard-library/multiset-class.md) konusunun Açıklamalar bölümüne bakın.

### <a name="example"></a>Örnek

Nasıl beyan value_comp ve nasıl kullanılacağına `value_compare`bir örnek için örneğe bakın. [value_comp](#value_comp)

## <a name="multisetvalue_type"></a><a name="value_type"></a>çok ayarlı::value_type

Öğe olarak depolanan bir nesneyi, değer olarak kapasitesinde çok küme olarak açıklayan bir tür.

```cpp
typedef Key value_type;
```

### <a name="remarks"></a>Açıklamalar

`value_type`şablon parametresi `Key`ile eş anlamlıdır.

Hem [key_type](#key_type) hem `value_type` de şablon parametresi `Key`ile eş anlamlı dır. Her iki tür de sınıflar haritası ve çoklu harita ile uyumluluk için, farklı oldukları sınıflar kümesi ve çoklu küme, için sağlanır.

Daha fazla `Key`bilgi için konunun Açıklamalar bölümüne bakın.

### <a name="example"></a>Örnek

```cpp
// multiset_value_type.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main( )
{
   using namespace std;
   multiset <int> ms1;
   multiset <int>::iterator ms1_Iter;

   multiset <int> :: value_type svt_Int;   // Declare value_type
   svt_Int = 10;             // Initialize value_type

   multiset <int> :: key_type skt_Int;   // Declare key_type
   skt_Int = 20;             // Initialize key_type

   ms1.insert( svt_Int );         // Insert value into s1
   ms1.insert( skt_Int );         // Insert key into s1

   // A multiset accepts key_types or value_types as elements
   cout << "The multiset has elements:";
   for ( ms1_Iter = ms1.begin( ) ; ms1_Iter != ms1.end( ); ms1_Iter++ )
      cout << " " << *ms1_Iter;
   cout << "." << endl;
}
```

```Output
The multiset has elements: 10 20.
```

## <a name="see-also"></a>Ayrıca bkz.

[Konteyner](../cpp/containers-modern-cpp.md)\
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[C++ Standart Kütüphane Başvurusu](../standard-library/cpp-standard-library-reference.md)
