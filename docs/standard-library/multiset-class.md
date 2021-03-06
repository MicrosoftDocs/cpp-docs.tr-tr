---
title: multiset Sınıfı
description: '`multiset`İçerdiği öğelerin değerlerinin benzersiz olmaması ve verilerin otomatik olarak sıralanmasına göre anahtar değerler olarak kullandıkları bir koleksiyondan verilerin depolanması ve alınması için kullanılan C++ Standart Şablon kitaplığı (STL) sınıfı IÇIN API başvurusu.'
ms.date: 9/9/2020
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
- set/std::multiset::contains
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
- std::multiset [C++], contains
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
ms.openlocfilehash: e89c1ed44a7f467223d443b2ba24bb88227b1bab
ms.sourcegitcommit: 651f817a6c8e92211168d34f0542350559f436d5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/08/2021
ms.locfileid: "99823312"
---
# <a name="multiset-class"></a>`multiset` Sınıfı

C++ standart kitaplığı çoklu küme sınıfı, içerdiği öğelerin değerlerinin benzersiz olmaması ve verilerin otomatik olarak sıralandığı anahtar değerleri olarak kullandıkları bir koleksiyondan verilerin depolanması ve alınması için kullanılır. İçindeki bir öğenin anahtar değeri `multiset` doğrudan değiştirilemez. Bunun yerine, eski değerlerin silinmesi ve yeni değerlerle sahip öğelerin eklenmesi gerekir.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Key, class Compare =less <Key>, class Allocator =allocator <Key>>
class multiset
```

### <a name="parameters"></a>Parametreler

*`Key`*\
İçinde depolanacak öğe veri türü `multiset` .

*`Compare`*\
İki öğe değerini, içindeki göreli sıralarını belirleyebilmek için sıralama anahtarları olarak karşılaştırabilen bir işlev nesnesi sağlayan tür `multiset` . İkili koşul **daha az** \<Key> varsayılan değerdir.

C++ 14 ' te, `std::less<>` tür parametreleri olmayan veya koşulunu belirterek heterojen aramayı etkinleştirebilirsiniz `std::greater<>` . Daha fazla bilgi için bkz. [Ilişkilendirilebilir kapsayıcılarda heterojen arama](../standard-library/stl-containers.md#sequence_containers) .

*`Allocator`*\
Bellek ayırmayı ve ayırmayı kaldırma hakkındaki ayrıntıları kapsülleyen saklı ayırıcı nesnesini temsil eden tür `multiset` . `allocator<Key>` varsayılan değerdir.

## <a name="remarks"></a>Açıklamalar

C++ Standart Kitaplığı `multiset` Sınıfı:

- İlişkili bir anahtar değerine dayalı öğe değerlerinin verimli alınmasını destekleyen bir değişken boyutu kapsayıcı olan ilişkilendirilebilir bir kapsayıcı.

- Çift yönlüdür, çünkü öğelerine erişmek için çift yönlü yineleyiciler sağlar.

- Sıralıdır, çünkü öğeleri belirtilen karşılaştırma işlevine uygun olarak kapsayıcı içindeki anahtar değerlere göre sıralanır.

- Tek bir anahtar değeri, ilişkili birçok öğe değerine sahip olması için, öğelerinin benzersiz anahtarlara sahip olması gerekmez.

- Basit bir ilişkilendirilebilir kapsayıcıdır, çünkü öğelerinin değerleri kendi anahtar değerleridir.

- Bir sınıf şablonu, sağladığı işlevsellik geneldir ve bu nedenle öğe olarak içerilen belirli veri türünden bağımsızdır. Kullanılacak veri türü, karşılaştırma işlevi ve ayırıcı ile birlikte bir sınıf şablonunda bir parametre olarak belirtilir.

Sınıfı tarafından verilen yineleyici `multiset` çift yönlü bir yineleyicimdir, ancak sınıf üyesi işlevleri [`insert`](#insert) , [`multiset`](#multiset) işlev gereksinimleri çift yönlü yineleyicilerin sınıfının garantiinden daha düşük olan daha az bir giriş yineleyicisi olan, şablon parametresi olarak daha zayıf olan sürümlere sahiptir. Farklı yineleyici kavramları, işlevselliklerindeki iyileştirmelere göre ilgili bir aile biçimlendirir. Her yineleyici kavramının kendi gereksinimler kümesi vardır ve bunlarla çalışan algoritmaların kendi varsayımlarını yineleyici türü tarafından sağlanan gereksinimlerle sınırlaması gerekir. Bir giriş yineleyicinin bazı nesnelere başvurusunun kaldırılacağı ve dizideki sonraki yineleyiciye artırılabileceği varsayılabilir. Bu en düşük işlevsellik kümesidir, ancak `First` `Last` sınıfın üye işlevleri bağlamında yineleyicilerin bir aralığı hakkında anlamlı bir şekilde konuşabilmek için yeterlidir.

Kapsayıcı türünün seçimi genelde uygulamanın gerektirdiği arama ve ekleme türüne dayalı olmalıdır. İlişkilendirilebilir kapsayıcılar, arama, ekleme ve kaldırma işlemleri için en iyi duruma getirilir. Bu işlemleri açıkça destekleyen üye işlevleri etkilidir ve bu işlemler, kapsayıcıdaki öğelerin sayısının logaritmasına göre ortalama orantılı bir zamanda yapılır. Öğelerin eklenmesi yineleyiciler içermez ve öğeleri kaldırmak yalnızca kaldırılan öğeleri işaret eden yineleyiciler geçersiz kılar.

`multiset`Değerleri, anahtar ile ilişkilendirirken, uygulama tarafından yerine, seçeneğin ilişkilendirilebilir kapsayıcısı olmalıdır. Öğesinin öğeleri `multiset` birden çok olabilir ve kendi sıralama anahtarları olarak işlev gösterebilir. bu nedenle anahtarlar benzersiz değildir. Bu tür bir yapı modeli, sözcüklerin birden çok defa geçebildiği sıralı bir sözcükler listesindedir. Sözcüklerin birden çok defa geçmelerine izin verilmediğinde, bir küme uygun bir kapsayıcı yapısı olacaktır. Benzersiz tanımlar benzersiz anahtar sözcükler listesine değerler olarak eklendiyse, bir eşlem verileri kapsayacak uygun bir yapı olacaktır. Bunun yerine, tanımlar benzersiz değilse, bir, `multimap` tercih edilen kapsayıcı olur.

, `multiset` Türünde bir saklı işlev nesnesi çağırarak denetlediği diziyi sıralar *`Compare`* . Bu saklı nesne, üye işlevi çağırarak erişilebilen bir karşılaştırma işlevidir [`key_comp`](#key_comp) . Genel olarak, öğelerin bu sırayı oluşturmak için yalnızca karşılaştırılabilir olması gerekir: her iki öğe verildiğinde, eşdeğer oldukları (Yani bunlardan daha küçük olmadığı anlamda) ya da birinin diğerinin daha küçük olduğu belirlenebilir. Bu, denk olmayan öğeler arasında bir sıralamaya neden olur. Daha teknik bir not üzerinde, karşılaştırma işlevi standart matematiksel anlamda katı bir zayıf sıralama sevk eden ikili bir koşuldur. Bir ikili koşul *f*(*x*, *y*) iki bağımsız değişken nesnesi olan *x* ve *y* ve dönüş değeri olan bir işlev nesnesidir **`true`** **`false`** . İkili koşul geri dönüşsüz, antisimetrik ve geçişli ve denklik geçişli ise, küme üzerinde yer alan bir sıralama katı zayıf bir sıradır, burada iki nesne x ve y, her ikisi de *f*(*x, y*) ve *f*(*y, x*) false olduğunda denk olarak tanımlanır. Anahtarlar arasındaki eşitliğinin daha güçlü koşulu bu denkliğin yerini alırsa, sıralama (içindeki tüm öğelerin birbirine göre sıralanması anlamında) toplam haline gelir ve eşleşen anahtarlar birbirinden ayırt edilemez olacaktır.

C++ 14 ' te, `std::less<>` tür parametreleri olmayan veya koşulunu belirterek heterojen aramayı etkinleştirebilirsiniz `std::greater<>` . Daha fazla bilgi için bkz. [Ilişkilendirilebilir kapsayıcılarda heterojen arama](../standard-library/stl-containers.md#sequence_containers) .

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Description|
|-|-|
|[değerlerden](#multiset)|`multiset`Boş veya belirtilen bir kısmının kopyası olan bir oluşturur `multiset` .|

### <a name="typedefs"></a>Tür tanımları

| Tür adı | Description |
|--|--|
| [`allocator_type`](#allocator_type) | Nesnenin sınıfı için bir typedef `allocator` `multiset` . |
| [`const_iterator`](#const_iterator) | İçindeki bir öğeyi okuyabilen çift yönlü Yineleyici için bir typedef **`const`** `multiset` . |
| [`const_pointer`](#const_pointer) | İçindeki bir öğenin işaretçisi için bir typedef **`const`** `multiset` . |
| [`const_reference`](#const_reference) | **`const`** İşlem okumak ve gerçekleştirmek için içinde depolanan bir öğeye başvuru için bir typedef `multiset` **`const`** . |
| [`const_reverse_iterator`](#const_reverse_iterator) | İçindeki herhangi bir öğeyi okuyabilen çift yönlü Yineleyici için bir typedef **`const`** `multiset` . |
| [`difference_type`](#difference_type) | Yineleyiciler tarafından işaret edilen öğeler arasında bir aralıktaki öğe sayısı için işaretli bir tamsayı typedef `multiset` . |
| [`iterator`](#iterator) | Bir öğesinde herhangi bir öğeyi okuyabilen veya değiştirebilen çift yönlü Yineleyici için bir typedef `multiset` . |
| [`key_compare`](#key_compare) | İçindeki iki öğenin göreli sırasını belirleyebilmek için iki anahtarı karşılaştırabilen bir işlev nesnesi için bir typedef `multiset` . |
| [`key_type`](#key_type) | İki sıralama anahtarını karşılaştıran bir işlev nesnesi için bir typedef, içindeki iki öğenin göreli sırasını tespit edebilir `multiset` . |
| [`pointer`](#pointer) | İçindeki bir öğenin işaretçisi için bir typedef `multiset` . |
| [`reference`](#reference) | İçinde depolanan bir öğeye başvuru için bir typedef `multiset` . |
| [`reverse_iterator`](#reverse_iterator) | Ters çevrilen bir öğeyi okuyabilen veya değiştirebilen çift yönlü Yineleyici için bir typedef `multiset` . |
| [`size_type`](#size_type) | İçindeki öğe sayısını temsil eden işaretsiz bir tamsayı türü `multiset` . |
| [`value_compare`](#value_compare) | İki öğeyi, içindeki göreli sıralarını belirlemede sıralama anahtarları olarak karşılaştırabilen bir işlev nesnesi için typedef `multiset` . |
| [`value_type`](#value_type) | Bir nesne olarak `multiset` , bir değer olarak kapasitesinin bir öğesi olarak depolanan bir nesne tanımlayan typedef. |

### <a name="member-functions"></a>Üye işlevleri

| Üye işlevi | Description |
|--|--|
| [`begin`](#begin) | İçindeki ilk öğeyi gösteren bir yineleyici döndürür `multiset` . |
| [`cbegin`](#cbegin) | İçindeki ilk öğeyi ele alan bir sabit yineleyici döndürür `multiset` . |
| [`cend`](#cend) | İçindeki son öğeden sonraki konumu ele alan bir const yineleyici döndürür `multiset` . |
| [`clear`](#clear) | Tüm öğelerini siler `multiset` . |
| [`contains`](#contains)<sup>C++ 20</sup> | İçinde belirtilen anahtara sahip bir öğe olup olmadığını kontrol edin `multiset` . |
| [`count`](#count) | Bir anahtarı, bir `multiset` parametresi olarak belirtilen anahtarla eşleşen öğe sayısını döndürür. |
| [`crbegin`](#crbegin) | Ters çevrilen ilk öğeyi adresleyen bir const yineleyici döndürür `multiset` . |
| [`crend`](#crend) | Ters çevrilen son öğeden sonraki konumu ele alan bir const yineleyici döndürür `multiset` . |
| [`emplace`](#emplace) | İçinde oluşturulan bir öğesi ekler `multiset` . |
| [`emplace_hint`](#emplace_hint) | Bir yerleştirme ipucuyla birlikte, içine oluşturulmuş bir öğe ekler `multiset` . |
| [`empty`](#empty) | `multiset`Boşsa, sınar. |
| [`end`](#end) | İçindeki son öğeden sonraki konuma işaret eden bir yineleyici döndürür `multiset` . |
| [`equal_range`](#equal_range) | Yineleyicilerin bir çiftini döndürür. Çiftin ilk yineleyicisi, belirtilen anahtardan daha büyük olan bir anahtarla ilk öğesine işaret eder `multiset` . Çiftin ikinci yineleyicisi, `multiset` anahtarına eşit veya ondan daha büyük olan bir anahtarla ilk öğesine işaret eder. |
| [`erase`](#erase) | Belirtilen konumlardan bir öğeyi veya öğe aralığını kaldırır `multiset` veya belirtilen bir anahtarla eşleşen öğeleri kaldırır. |
| [`find`](#find) | İçindeki, `multiset` belirtilen anahtara eşit bir anahtara sahip bir öğenin ilk konumunu gösteren bir yineleyici döndürür. |
| [`get_allocator`](#get_allocator) | `allocator`Oluşturmak için kullanılan nesnesinin bir kopyasını döndürür `multiset` . |
| [`insert`](#insert) | İçine bir öğe veya öğe aralığı ekler `multiset` . |
| [`key_comp`](#key_comp) | İçindeki iki öğenin göreli sırasını belirleyebilmek için iki sıralama anahtarını karşılaştırabilen bir işlev nesnesi sağlar `multiset` . |
| [`lower_bound`](#lower_bound) | Bir yineleyiciyi, `multiset` belirtilen anahtardan daha büyük veya ona eşit olan bir anahtarla birlikte içindeki ilk öğeye döndürür. |
| [`max_size`](#max_size) | Maksimum uzunluğunu döndürür `multiset` . |
| [`rbegin`](#rbegin) | Ters çevrilen ilk öğeyi gösteren bir yineleyici döndürür `multiset` . |
| [`rend`](#rend) | Ters çevrilen son öğeden sonraki konuma işaret eden bir yineleyici döndürür `multiset` . |
| [`size`](#size) | İçindeki öğelerin sayısını döndürür `multiset` . |
| [`swap`](#swap) | İki öğenin öğelerini değiş tokuş eder `multiset` . |
| [`upper_bound`](#upper_bound) | Belirtilen anahtardan daha büyük bir anahtarla bir yineleyiciyi, içindeki ilk öğeye döndürür `multiset` . |
| [`value_comp`](#value_comp) | İçindeki öğe değerlerini sıralamak için kullanılan karşılaştırma nesnesinin bir kopyasını alır `multiset` . |

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[`operator=`](#op_eq)|Öğesinin öğelerini `multiset` başka bir kopyasıyla değiştirir `multiset` .|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**`<set>`

**Ad alanı:**`std`

## <a name="multisetallocator_type"></a><a name="allocator_type"></a> `multiset::allocator_type`

Nesnenin ayırıcı sınıfını temsil eden bir tür `multiset`

```cpp
typedef Allocator allocator_type;
```

### <a name="remarks"></a>Açıklamalar

`allocator_type` , şablon parametresinin eşanlamlısıdır `Allocator` .

Hakkında daha fazla bilgi için `Allocator` , [Çoklu küme sınıfı](../standard-library/multiset-class.md) konusunun açıklamalar bölümüne bakın.

### <a name="example"></a>Örnek

Şunu [`get_allocator`](#get_allocator) kullanarak bir örnek için örneğe bakın: `allocator_type`

## <a name="multisetbegin"></a><a name="begin"></a> `multiset::begin`

İçindeki ilk öğeyi adresleyen bir yineleyici döndürür `multiset` .

```cpp
const_iterator begin() const;

iterator begin();
```

### <a name="return-value"></a>Dönüş Değeri

İçindeki ilk öğeyi ele alarak çift yönlü bir yineleyici, bir `multiset` boş çoklu küme ile başarılı bir yerde.

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

## <a name="multisetcbegin"></a><a name="cbegin"></a> `multiset::cbegin`

**`const`** Aralıktaki ilk öğeyi ele alan bir yineleyici döndürür.

```cpp
const_iterator cbegin() const;
```

### <a name="return-value"></a>Dönüş Değeri

**`const`** Aralığın ilk öğesine veya boş bir aralığın sonundaki konuma (boş bir Aralık için) işaret eden çift yönlü erişim yineleyicisi `cbegin() == cend()` .

### <a name="remarks"></a>Açıklamalar

Dönüş değeri ile `cbegin` , aralıktaki öğeler değiştirilemez.

`begin()`Dönüş değerinin olduğunu garantilemek için üye işlevin yerine bu üye işlevi kullanabilirsiniz `const_iterator` . Genellikle, aşağıdaki örnekte gösterildiği gibi [Otomatik](../cpp/auto-cpp.md) tür kesintisi anahtar sözcüğüyle birlikte kullanılır. Örnekte, ve ' ı `Container` destekleyen herhangi bir türde değiştirilebilir (olmayan) bir kapsayıcı olarak göz önünde bulundurun **`const`** `begin()` `cbegin()` .

```cpp
auto i1 = Container.begin();
// i1 is Container<T>::iterator
auto i2 = Container.cbegin();

// i2 is Container<T>::const_iterator
```

## <a name="multisetcend"></a><a name="cend"></a> `multiset::cend`

**`const`** Bir aralıktaki son öğenin ötesinde konumu ele alan bir yineleyici döndürür.

```cpp
const_iterator cend() const;
```

### <a name="return-value"></a>Dönüş Değeri

**`const`** Yalnızca aralığın sonunu işaret eden çift yönlü erişim yineleyicisi.

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

## <a name="multisetclear"></a><a name="clear"></a> `multiset::clear`

Tüm öğelerini siler `multiset` .

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

## <a name="multisetconst_iterator"></a><a name="const_iterator"></a> `multiset::const_iterator`

İçindeki bir öğeyi okuyabilen çift yönlü bir yineleyici sağlayan bir tür **`const`** `multiset` .

```cpp
typedef implementation-defined const_iterator;
```

### <a name="remarks"></a>Açıklamalar

Bir tür `const_iterator` , bir öğenin değerini değiştirmek için kullanılamaz.

### <a name="example"></a>Örnek

[`begin`](#begin)Örneği için bkz `const_iterator` ..

## <a name="multisetconst_pointer"></a><a name="const_pointer"></a> `multiset::const_pointer`

İçindeki bir öğeye işaretçi sağlayan bir tür **`const`** `multiset` .

```cpp
typedef typename allocator_type::const_pointer const_pointer;
```

### <a name="remarks"></a>Açıklamalar

Bir tür `const_pointer` , bir öğenin değerini değiştirmek için kullanılamaz.

Çoğu durumda, bir [Yineleyici](#iterator) bir nesne içindeki öğelere erişmek için kullanılmalıdır `multiset` .

## <a name="multisetconst_reference"></a><a name="const_reference"></a> `multiset::const_reference`

**`const`** İşlem okumak ve gerçekleştirmek için içinde depolanan bir öğeye başvuru sağlayan bir tür `multiset` **`const`** .

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
   // const_reference can't be used to modify the multiset
   // Ref1 = Ref1 + 5;
}
```

```Output
The first element in the multiset is 10.
```

## <a name="multisetconst_reverse_iterator"></a><a name="const_reverse_iterator"></a> `multiset::const_reverse_iterator`

İçindeki herhangi bir öğeyi okuyabilen çift yönlü bir yineleyici sağlayan bir tür **`const`** `multiset` .

```cpp
typedef std::reverse_iterator<const_iterator> const_reverse_iterator;
```

### <a name="remarks"></a>Açıklamalar

Bir tür, bir `const_reverse_iterator` öğenin değerini değiştiremez ve `multiset` ' de ters yinelemek için kullanılır.

### <a name="example"></a>Örnek

[`rend`](#rend)Bildirme ve kullanma hakkında bir örnek için bkz `const_reverse_iterator` ..

## <a name="multisetcontains"></a><a name="contains"></a> `multiset::contains`

İçinde belirtilen anahtara sahip bir öğe olup olmadığını kontrol edin `multiset` .

```cpp
bool contains(const Key& key) const;
template<class K> bool contains(const K& key) const;
```

### <a name="parameters"></a>Parametreler

*`K`*\
Anahtarın türü.

*`key`*\
Aranacak öğenin anahtar değeri.

### <a name="return-value"></a>Dönüş Değeri

`true` öğe kapsayıcıda bulunursa; `false` Aksi takdirde.

### <a name="remarks"></a>Açıklamalar

`contains()` C++ 20 ' de yenidir. Bunu kullanmak için [/std: c + + en son](../build/reference/std-specify-language-standard-version.md) derleyici seçeneğini belirtin.

`template<class K> bool contains(const K& key) const` yalnızca, saydam ise aşırı yükleme çözümüne katılır `key_compare` . Daha fazla bilgi için bkz. [ilişkilendirilebilir kapsayıcılarda heterojen arama](./stl-containers.md#heterogeneous-lookup-in-associative-containers-c14) .

### <a name="example"></a>Örnek

```cpp
// Requires /std:c++latest
#include <set>
#include <iostream>

int main()
{
    std::multiset<int> theMultiSet = {1, 2};

    std::cout << std::boolalpha; // so booleans show as 'true' or 'false'
    std::cout << theMultiSet.contains(2) << '\n';
    std::cout << theMultiSet.contains(3) << '\n';

    return 0;
}
```

```Output
true
false
```

## <a name="multisetcount"></a><a name="count"></a> `multiset::count`

Bir `multiset` anahtarı parametre belirtilen anahtarla eşleşen bir öğe sayısını döndürür.

```cpp
size_type count(const Key& key) const;
```

### <a name="parameters"></a>Parametreler

*`key`*\
İle eşleştirilecek öğelerin anahtarı `multiset` .

### <a name="return-value"></a>Dönüş Değeri

`multiset`Sıralama anahtarı parametre anahtarıyla eşleşen öğe sayısı.

### <a name="remarks"></a>Açıklamalar

Üye işlevi aralıktaki *x* öğelerinin sayısını döndürür

\[ lower_bound ( *`key`* ), upper_bound ( *`key`* ))

### <a name="example"></a>Örnek

Aşağıdaki örnek `multiset` :: Count üye işlevinin kullanımını gösterir.

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

    // Elements don't need to be unique in multiset,
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

## <a name="multisetcrbegin"></a><a name="crbegin"></a> `multiset::crbegin`

Ters çevrilen bir çoklu küme içindeki ilk öğeyi adresleyen bir const yineleyici döndürür.

```cpp
const_reverse_iterator crbegin() const;
```

### <a name="return-value"></a>Dönüş Değeri

Ters çevrilen bir çoklu küme içindeki ilk öğeyi ele alarak veya geri çevrilmeyen çoklu kümeli en son öğe olduğunu adresleyen bir const ters çift yönlü Yineleyici.

### <a name="remarks"></a>Açıklamalar

`crbegin` , BEGIN ile birlikte kullanıldığı gibi, ters bir çoklu kümeli birlikte kullanılır `multiset` .

Dönüş değeri ile `crbegin` `multiset` nesne değiştirilemez.

`crbegin` , geriye doğru yinelemek için kullanılabilir `multiset` .

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

## <a name="multisetcrend"></a><a name="crend"></a> `multiset::crend`

Ters çevrilen bir çoklu küme içindeki son öğeden sonra gelen konumu ele alan bir const yineleyici döndürür.

```cpp
const_reverse_iterator crend() const;
```

### <a name="return-value"></a>Dönüş Değeri

Ters çevrilen bir çoklu küme içindeki son öğeden sonra gelen konumu ele alan bir sabit ters çift yönlü yineleyici (geri çevrilmeyen çok kümeli ilk öğeden önce gelen konum).

### <a name="remarks"></a>Açıklamalar

`crend` , ile birlikte kullanıldığı gibi, ters bir çoklu küme ile kullanılır [`end`](#end) `multiset` .

Dönüş değeri ile `crend` `multiset` nesne değiştirilemez.

`crend` , geriye doğru bir yineleyicinin sonuna ulaşılıp ulaşılmadığını test etmek için kullanılabilir `multiset` .

Tarafından döndürülen değer `crend` başvurulmamalıdır.

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

## <a name="multisetdifference_type"></a><a name="difference_type"></a> `multiset::difference_type`

Yineleyiciler tarafından gösterilen öğeler arasındaki bir aralıktaki öğelerinin sayısını temsil etmek için kullanılabilen işaretli bir tamsayı türü `multiset` .

```cpp
typedef typename allocator_type::difference_type difference_type;
```

### <a name="remarks"></a>Açıklamalar

`difference_type`Kapsayıcının yineleyiciler aracılığıyla çıkartılacak veya artırılarak döndürülen türdür. , `difference_type` Genellikle yineleyiciler arasındaki [,) aralıktaki öğelerin sayısını temsil etmek için kullanılır ve öğesi tarafından işaret edilen öğe `first` `last` `first` `last` `first` ve dahil `last` olmak üzere öğe aralığı ile işaret eder.

, `difference_type` Küme gibi ters çevrilebilir kapsayıcılar tarafından desteklenen çift yönlü yineleyicilerin sınıfını içeren bir giriş yineleyicisinin gereksinimlerini karşılayan tüm yineleyiciler için kullanılabilir olsa da, yineleyiciler arasında çıkarma yalnızca vektör gibi bir rastgele erişim kapsayıcısı tarafından sağlanan rastgele erişim yineleyiciler tarafından desteklenir.

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

   // The keys, and hence the elements, of a multiset aren't unique
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

## <a name="multisetemplace"></a><a name="emplace"></a> `multiset::emplace`

Yerinde oluşturulmuş bir öğe ekler (kopyalama veya taşıma işlemleri yapılmaz), yerleştirme ipucuyla birlikte.

```cpp
template <class... Args>
iterator emplace(Args&&... args);
```

### <a name="parameters"></a>Parametreler

*`args`*\
İçine eklenecek bir öğe oluşturmak için iletilen bağımsız değişkenler `multiset` .

### <a name="return-value"></a>Dönüş Değeri

Yeni eklenmekte olan öğe için bir yineleyici.

### <a name="remarks"></a>Açıklamalar

Bu işlev tarafından kapsayıcı öğelerine yönelik başvuru geçersiz kılınmamıştır, ancak kapsayıcı için tüm yineleyiciler geçersiz kılınabilir.

Emplaka sırasında, bir özel durum oluşturulursa, kapsayıcının durumu değiştirilmez.

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

## <a name="multisetemplace_hint"></a><a name="emplace_hint"></a> `multiset::emplace_hint`

Yerinde oluşturulmuş bir öğe ekler (kopyalama veya taşıma işlemleri yapılmaz), yerleştirme ipucuyla birlikte.

```cpp
template <class... Args>
iterator emplace_hint(
    const_iterator where,
    Args&&... args);
```

### <a name="parameters"></a>Parametreler

*`args`*\
İçine eklenecek bir öğe oluşturmak için iletilen bağımsız değişkenler `multiset` .

*`where`*\
Doğru ekleme noktasını aramaya başlamak için yer. (Bu nokta hemen önceyse *`where`* , ekleme, logaritmik bir süre yerine itfası sabit zamanlı olarak gerçekleşebilir.)

### <a name="return-value"></a>Dönüş Değeri

Yeni eklenmekte olan öğe için bir yineleyici.

### <a name="remarks"></a>Açıklamalar

Bu işlev tarafından kapsayıcı öğelerine yönelik başvuru geçersiz kılınmamıştır, ancak kapsayıcı için tüm yineleyiciler geçersiz kılınabilir.

Emplaka sırasında, bir özel durum oluşturulursa, kapsayıcının durumu değiştirilmez.

Kod örneği için bkz [`set::emplace_hint`](../standard-library/set-class.md#emplace_hint) ..

## <a name="multisetempty"></a><a name="empty"></a> `multiset::empty`

`multiset`Boşsa, sınar.

```cpp
bool empty() const;
```

### <a name="return-value"></a>Dönüş Değeri

**`true`** boşsa, boşsa `multiset` **`false`** `multiset` .

### <a name="example"></a>Örnek

```cpp
// multiset_empty.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main()
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

## <a name="multisetend"></a><a name="end"></a> `multiset::end`

past-the-end yineleyici döndürür.

```cpp
const_iterator end() const;

iterator end();
```

### <a name="return-value"></a>Dönüş Değeri

Son uca Yineleyici. `multiset`Boşsa, `multiset::end() == multiset::begin()` .

### <a name="remarks"></a>Açıklamalar

**`end`** bir yineleyicinin kendi çoklu küme sonunu geçtiğini test etmek için kullanılır.

Tarafından döndürülen değer **`end`** başvurulmamalıdır.

Kod örneği için bkz [`multiset::find`](#find) ..

## <a name="multisetequal_range"></a><a name="equal_range"></a> `multiset::equal_range`

`multiset`Belirtilen anahtardan daha büyük bir anahtarla ve anahtarından bir anahtarla `multiset` eşit veya ondan daha büyük olan bir anahtarla ilk öğesine kadar yineleyicilerin bir çiftini döndürür.

```cpp
pair <const_iterator, const_iterator> equal_range (const Key& key) const;

pair <iterator, iterator> equal_range (const Key& key);
```

### <a name="parameters"></a>Parametreler

*`key`*\
Aranmakta olan bir öğenin sıralama anahtarıyla Karşılaştırılacak bağımsız değişken anahtarı `multiset` .

### <a name="return-value"></a>Dönüş Değeri

Birincisi [`lower_bound`](#lower_bound) anahtarın ilk ve ikincisinin olduğu bir çift yineleyiciler [`upper_bound`](#upper_bound) .

Üye işlevi tarafından döndürülen bir çiftin ilk Yineleyici öğesine erişmek için `pr` kullanın `pr` . **`first`** ve alt sınır Yineleyici için başvuru yapmak üzere \* ( `pr` . **`first`**). Üye işlevi tarafından döndürülen bir çiftin ikinci Yineleyici öğesine erişmek için `pr` kullanın `pr` . **`second`** ve üst sınır yineleyici başvurusu için \* ( `pr` . **`second`**).

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

## <a name="multiseterase"></a><a name="erase"></a> `multiset::erase`

Belirtilen konumlardan bir öğeyi veya öğe aralığını kaldırır `multiset` veya belirtilen bir anahtarla eşleşen öğeleri kaldırır.

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

*`Where`*\
Kaldırılacak öğenin konumu.

*`First`*\
Kaldırılacak ilk öğenin konumu.

*`Last`*\
Kaldırılacak son öğenin hemen ötesinde konumlandır.

*`key`*\
Kaldırılacak öğelerin anahtar değeri.

### <a name="return-value"></a>Dönüş Değeri

İlk iki üye işlevi için, kaldırılan öğelerin dışında kalan ilk öğeyi veya böyle bir öğe yoksa öğesinin sonu olan bir öğeyi belirten çift yönlü bir yineleyici `multiset` .

Üçüncü üye işlevi için, öğesinden kaldırılmış olan öğe sayısını döndürür `multiset` .

### <a name="remarks"></a>Açıklamalar

Kod örneği için bkz [`set::erase`](../standard-library/set-class.md#erase) ..

## <a name="multisetfind"></a><a name="find"></a> `multiset::find`

İçindeki bir öğenin, `multiset` belirtilen anahtara denk bir anahtara sahip olan konumuna başvuran bir yineleyici döndürür.

```cpp
iterator find(const Key& key);

const_iterator find(const Key& key) const;
```

### <a name="parameters"></a>Parametreler

*`key`*\
Aranmakta olan bir öğenin sıralama anahtarıyla eşleştirilecek anahtar değeri `multiset` .

### <a name="return-value"></a>Dönüş Değeri

`multiset` `multiset::end()` Anahtar için hiçbir eşleşme bulunmazsa, belirtilen anahtara sahip bir öğenin konumunu veya () içindeki son öğeden geçen konumu ifade eden bir yineleyici.

### <a name="remarks"></a>Açıklamalar

Üye işlevi, `multiset` anahtarı *`key`* karşılaştırıdan daha az bir ilişkiye göre bir sıralamayı karşılayan bir ikili koşul altındaki bağımsız değişkene eşdeğer olan bir öğeyi ifade eden bir yineleyici döndürür.

Dönüş değeri `find` bir öğesine atanırsa `const_iterator` , `multiset` nesne değiştirilemez. Dönüş değeri `find` bir öğesine atanırsa `iterator` , `multiset` nesne değiştirilebilir

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

## <a name="multisetget_allocator"></a><a name="get_allocator"></a> `multiset::get_allocator`

Oluşturmak için kullanılan ayırıcı nesnesinin bir kopyasını döndürür `multiset` .

```cpp
allocator_type get_allocator() const;
```

### <a name="return-value"></a>Dönüş Değeri

Tarafından kullanılan ayırıcı `multiset` .

### <a name="remarks"></a>Açıklamalar

Sınıfı için ayrıcılar `multiset` , sınıfın depolamayı nasıl yönettiğini belirtir. C++ standart kitaplığı kapsayıcı sınıflarıyla birlikte sağlanan varsayılan ayrıcılar çoğu programlama ihtiyacı için yeterlidir. Kendi ayırıcı sınıfınızı yazmak ve kullanmak, gelişmiş bir C++ konudur.

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

## <a name="multisetinsert"></a><a name="insert"></a> `multiset::insert`

İçine bir öğe veya öğe aralığı ekler `multiset` .

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

*`Val`*\
İçine eklenecek öğenin değeri `multiset` .

*`Where`*\
Doğru ekleme noktasını aramaya başlamak için yer. (Bu nokta hemen önceyse *`Where`* , ekleme, logaritmik bir süre yerine itfası sabit zamanlı olarak gerçekleşebilir.)

*`ValTy`*\
`multiset`Öğesinin bir öğesi oluşturmak için kullanabileceği bağımsız değişken türünü belirten şablon parametresi [`value_type`](../standard-library/map-class.md#value_type) ve *`Val`* bağımsız değişken olarak kusursuz iletme.

*`First`*\
Kopyalanacak ilk öğenin konumu.

*`Last`*\
Kopyalanacak son öğenin hemen ötesinde konum.

*1*\
[`input_iterator_tag`](../standard-library/input-iterator-tag-struct.md) [1](../standard-library/map-class.md#value_type) nesne oluşturmak için kullanılabilecek bir türün öğelerine işaret eden bir öğesinin gereksinimlerini karşılayan şablon işlevi bağımsız değişkeni.

*`IList`*\
[`initializer_list`](../standard-library/initializer-list.md)Öğelerin kopyalanacağı yer.

### <a name="return-value"></a>Dönüş Değeri

Tek öğeli-ekleme üye işlevleri, (1) ve (2), yeni öğenin içine eklendiği konuma bir yineleyici döndürür `multiset` .

Tek öğeli-ipucu üye işlevleri, (3) ve (4), yeni öğenin içine eklendiği konuma işaret eden bir yineleyici döndürür `multiset` .

### <a name="remarks"></a>Açıklamalar

Bu işlev tarafından geçersiz kılınan işaretçiler veya başvurular yok, ancak kapsayıcı için tüm yineleyiciler geçersiz kılınabilir.

Yalnızca bir öğenin eklenmesi sırasında, bir özel durum oluşturulursa, kapsayıcının durumu değiştirilmez. Birden çok öğenin eklenmesi sırasında, bir özel durum oluşturulursa, kapsayıcı belirtilmemiş ancak geçerli bir durumda bırakılır.

[`value_type`](../standard-library/map-class.md#value_type)Kapsayıcı, kapsayıcıya ait olan bir typedef ve set için `multiset<V>::value_type` tür `const V` .

Aralık üye işlevi (5), öğe değerlerinin dizisini `multiset` aralıktaki bir yineleyici tarafından bahsedilen her öğeye karşılık gelen öğesine ekler `[First, Last)` ; Bu nedenle, `Last` eklenmez. Kapsayıcı üye işlevi, `end()` kapsayıcıdaki son öğeden hemen sonra gelen konumu ifade eder; örneğin, ifade öğesine `s.insert(v.begin(), v.end());` tüm öğelerini ekler `v` `s` .

Başlatıcı listesi üye işlevi (6) [`initializer_list`](../standard-library/initializer-list.md) öğesini öğesine kopyalamak için bir kullanır `multiset` .

Yerinde oluşturulmuş bir öğenin eklenmesi için — yani, kopyalama veya taşıma işlemleri yapılmaz — bkz [`multiset::emplace`](#emplace) [`multiset::emplace_hint`](#emplace_hint) . ve.

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

## <a name="multisetiterator"></a><a name="iterator"></a> `multiset::iterator`

İçindeki herhangi bir öğeyi okuyabilen sabit [çift yönlü yineleyiciyi](../standard-library/bidirectional-iterator-tag-struct.md) sağlayan bir tür `multiset` .

```cpp
typedef implementation-defined iterator;
```

### <a name="example"></a>Örnek

' In nasıl bildirilemeyeceğini ve [kullanılacağına ilişkin bir örnek için bkz](#begin) `iterator` ..

## <a name="multisetkey_comp"></a><a name="key_comp"></a> `multiset::key_comp`

İçindeki anahtarları sıralamak için kullanılan karşılaştırma nesnesinin bir kopyasını alır `multiset` .

```cpp
key_compare key_comp() const;
```

### <a name="return-value"></a>Dönüş Değeri

`multiset`Şablon parametresi olan öğelerini sıralamak için kullanılan işlev nesnesini döndürür `Compare` .

Hakkında daha fazla bilgi için `Compare` , [Çoklu küme sınıfı](../standard-library/multiset-class.md) konusunun açıklamalar bölümüne bakın.

### <a name="remarks"></a>Açıklamalar

Saklı nesne, üye işlevini tanımlar:

**bool işleci**( **const Key&** *x*, **const Key&** *y*);

*x* sıralamayı sıralama düzeninde *tam olarak önce geliyorsa true* döndürür.

Hem hem de [`key_compare`](#key_compare) [`value_compare`](#value_compare) şablon parametresi için eş anlamlılardır ``Compare`` . Her iki tür de, sınıfları ve çoklu küme için, özdeş oldukları, sınıflar haritalarının ve multimap ile uyumluluk açısından, farklı oldukları durumlar için sağlanır.

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

## <a name="multisetkey_compare"></a><a name="key_compare"></a> `multiset::key_compare`

İçindeki iki öğenin göreli sırasını belirleyebilmek için iki sıralama anahtarını karşılaştırabilen bir işlev nesnesi sağlayan bir tür `multiset` .

```cpp
typedef Compare key_compare;
```

### <a name="remarks"></a>Açıklamalar

`key_compare` , şablon parametresinin eşanlamlısıdır `Compare` .

Hakkında daha fazla bilgi için `Compare` , [ `multiset` sınıf](../standard-library/multiset-class.md) konusunun açıklamalar bölümüne bakın.

### <a name="example"></a>Örnek

[`key_comp`](#key_comp)Bildirme ve kullanma hakkında bir örnek için örneğe bakın `key_compare` .

## <a name="multisetkey_type"></a><a name="key_type"></a> `multiset::key_type`

İçindeki iki öğenin göreli sırasını belirlemede sıralama anahtarlarını karşılaştırabilen bir işlev nesnesi sağlayan bir tür `multiset` .

```cpp
typedef Key key_type;
```

### <a name="remarks"></a>Açıklamalar

`key_type` , şablon parametresinin eşanlamlısıdır `Key` .

Hakkında daha fazla bilgi için `Key` , [ `multiset` sınıf](../standard-library/multiset-class.md) konusunun açıklamalar bölümüne bakın.

### <a name="example"></a>Örnek

[`value_type`](#value_type)Bildirme ve kullanma hakkında bir örnek için örneğe bakın ``key_type`` .

## <a name="multisetlower_bound"></a><a name="lower_bound"></a> `multiset::lower_bound`

Bir yineleyiciyi, `multiset` belirtilen anahtardan daha büyük veya ona eşit olan bir anahtarla birlikte içindeki ilk öğeye döndürür.

```cpp
const_iterator lower_bound(const Key& key) const;

iterator lower_bound(const Key& key);
```

### <a name="parameters"></a>Parametreler

*`key`*\
Aranmakta olan bir öğenin sıralama anahtarıyla Karşılaştırılacak bağımsız değişken anahtarı `multiset` .

### <a name="return-value"></a>Dönüş Değeri

Bir `iterator` veya `const_iterator` `multiset` bağımsız değişken anahtarına eşit veya daha büyük bir anahtarla bir öğenin konumunu adresleyen ya da `multiset` anahtar için hiçbir eşleşme bulunmazsa içindeki son öğeden sonra gelen konumu ele alan bir öğesi.

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

## <a name="multisetmax_size"></a><a name="max_size"></a> `multiset::max_size`

Maksimum uzunluğunu döndürür `multiset` .

```cpp
size_type max_size() const;
```

### <a name="return-value"></a>Dönüş Değeri

Mümkün olan en yüksek uzunluk `multiset` .

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

## <a name="multisetmultiset"></a><a name="multiset"></a> `multiset::multiset`

`multiset`Boş olan veya bir kısmının tümünün veya bir kısmının kopyası olan oluşturur `multiset` .

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

*`Al`*\
Bu çok kümeli nesne için kullanılacak depolama ayırıcısı sınıfı, varsayılan olarak `Allocator` .

*`Comp`*\
`const Compare`' Deki öğeleri sıralamak için kullanılan tür karşılaştırma işlevi, `multiset` Varsayılan olarak `Compare` .

*`Right`*\
`multiset`oluşturulan çok kümeli bir kopya olacak.

*`First`*\
Kopyalanacak öğe aralığındaki ilk öğenin konumu.

*`Last`*\
Kopyalanacak öğe aralığının ötesinde ilk öğenin konumu.

*`IList`*\
`initializer_list`Öğelerin kopyalanacağı yer.

### <a name="remarks"></a>Açıklamalar

Tüm oluşturucular, `multiset` daha sonra çağırarak geri döndürülebilecek ve için bellek depolamayı yöneten bir tür ayırıcı nesnesi depolar [`get_allocator`](#get_allocator) . Ayırıcı parametresi, genellikle sınıf bildirimlerinde atlanır ve alternatif ayırıcıları değiştirmek için kullanılan ön işleme makrolarıyla sonuçlanır.

Tüm oluşturucular çoklu kümeli bir başlangıç yapın.

Tüm oluşturucular, `multiset` ve daha sonra çağırarak geri döndürülebilecek anahtarlar arasında bir sıra oluşturmak için kullanılan Compare türünde bir işlev nesnesi depolar [`key_comp`](#key_comp) .

İlk üç Oluşturucu boş bir ilk çoklu küme, *`Comp`* öğelerin sırasını oluşturmak için kullanılan karşılaştırma işlevinin türünü () ve kullanılacak ayırıcı türü () öğesini açıkça belirten, ikincisini belirtir *`Al`* . Anahtar sözcüğü **`explicit`** bazı otomatik tür dönüştürme türlerini bastırır.

Dördüncü Oluşturucu öğesinin bir kopyasını belirtir `multiset` *`Right`* .

Beşinci Oluşturucu taşıyarak öğesinin bir kopyasını belirtir `multiset` *`Right`* .

6 TH, 7. ve 8. oluşturucular, öğelerin kopyalanacağı bir initializer_list belirtir.

Sonraki üç Oluşturucu, `[First, Last)` bir öğesinin aralığını, `multiset` karşılaştırma işlevi ve ayırıcı türünü belirtirken açıkça bir artırılarak kopyalar.

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

## <a name="multisetoperator"></a><a name="op_eq"></a> `multiset::operator=`

Bu öğe öğelerini `multiset` başka bir öğeden kullanarak değiştirir `multiset` .

```cpp
multiset& operator=(const multiset& right);

multiset& operator=(multiset&& right);
```

### <a name="parameters"></a>Parametreler

*`Right`*\
`multiset`Hangi öğelerin kopyalandığı veya taşındığı.

### <a name="remarks"></a>Açıklamalar

`operator=`*`Right`* `multiset` kullanılan başvuru türüne (lvalue veya rvalue) bağlı olarak, içindeki öğeleri kopyalar veya buna kaydırır. Yürütmeden önce içinde olan `multiset` öğeler `operator=` atılır.

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

## <a name="multisetpointer"></a><a name="pointer"></a> `multiset::pointer`

İçindeki bir öğeye işaretçi sağlayan bir tür `multiset` .

```cpp
typedef typename allocator_type::pointer pointer;
```

### <a name="remarks"></a>Açıklamalar

Bir türü **`pointer`** , bir öğenin değerini değiştirmek için kullanılabilir.

Çoğu durumda, bir [Yineleyici](#iterator) bir nesne içindeki öğelere erişmek için kullanılmalıdır `multiset` .

## <a name="multisetrbegin"></a><a name="rbegin"></a> `multiset::rbegin`

Ters çevrilen bir çoklu küme içindeki ilk öğeyi adresleyen bir yineleyici döndürür.

```cpp
const_reverse_iterator rbegin() const;

reverse_iterator rbegin();
```

### <a name="return-value"></a>Dönüş Değeri

Ters çevrilen bir çift yönlü yineleyiciden, geri çevrilmede `multiset` son öğe ne olduğunu veya adreslemeyi geri alınamaz `multiset` .

### <a name="remarks"></a>Açıklamalar

`rbegin` , `multiset` bir ile birlikte kullanıldığında, yalnızca rbegın ile birlikte kullanılır `multiset` .

Öğesinin dönüş değeri `rbegin` öğesine atanmışsa `const_reverse_iterator` , `multiset` nesne değiştirilemez. Öğesinin dönüş değeri `rbegin` öğesine atanmışsa `reverse_iterator` , `multiset` nesne değiştirilebilir.

`rbegin` , geriye doğru yinelemek için kullanılabilir `multiset` .

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

   // a multiset element can be erased by dereferencing to its key
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

## <a name="multisetreference"></a><a name="reference"></a> `multiset::reference`

İçinde depolanan bir öğeye başvuru sağlayan bir tür `multiset` .

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

## <a name="multisetrend"></a><a name="rend"></a> `multiset::rend`

Ters çevrilen son öğeden sonraki konumu ele alan bir yineleyici döndürür `multiset` .

```cpp
const_reverse_iterator rend() const;

reverse_iterator rend();
```

### <a name="return-value"></a>Dönüş Değeri

Ters çevrilen bir çift yönlü yineleyici (geri alınamaz olan `multiset` ilk öğeden önce gelen konum `multiset` ).

### <a name="remarks"></a>Açıklamalar

`rend` , ile birlikte kullanıldığı gibi, ters bir çoklu küme ile kullanılır [`end`](#end) `multiset` .

Öğesinin dönüş değeri `rend` öğesine atanmışsa `const_reverse_iterator` , `multiset` nesne değiştirilemez. Öğesinin dönüş değeri `rend` öğesine atanmışsa `reverse_iterator` , `multiset` nesne değiştirilebilir.

`rend` , bir ters yineleyicinin kendi çoklu küme sonuna ulaşıp ulaşılmadığını test etmek için kullanılabilir.

Tarafından döndürülen değer `rend` başvurulmamalıdır.

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

## <a name="multisetreverse_iterator"></a><a name="reverse_iterator"></a> `multiset::reverse_iterator`

Ters çevrilen bir çoklu küme içindeki bir öğeyi okuyabilen veya değiştirebilen çift yönlü bir yineleyici sağlayan bir tür.

```cpp
typedef std::reverse_iterator<iterator> reverse_iterator;
```

### <a name="remarks"></a>Açıklamalar

Bir tür `reverse_iterator` , geriye doğru yinelemek için kullanılır `multiset` .

### <a name="example"></a>Örnek

[`rbegin`](#rbegin)Bildirme ve kullanma hakkında bir örnek için bkz `reverse_iterator` . örneği.

## <a name="multisetsize"></a><a name="size"></a> `multiset::size`

İçindeki öğelerin sayısını döndürür `multiset` .

```cpp
size_type size() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli uzunluğu `multiset` .

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

## <a name="multisetsize_type"></a><a name="size_type"></a> `multiset::size_type`

İçindeki öğe sayısını temsil eden işaretsiz bir tamsayı türü `multiset` .

```cpp
typedef typename allocator_type::size_type size_type;
```

### <a name="example"></a>Örnek

[`size`](#size)Bildirme ve kullanma hakkında bir örnek için bkz. örnek`size_type`

## <a name="multisetswap"></a><a name="swap"></a> `multiset::swap`

İki multiset 'in öğelerini değiş tokuş eder.

```cpp
void swap(
    multiset<Key, Compare, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*`Right`*\
Bağımsız değişken, hedef çoklu küme ile takas edilecek öğeleri sağlayan çoklu küme.

### <a name="remarks"></a>Açıklamalar

Üye işlevi, öğeleri takas edilmekte olan iki multiset içindeki öğeleri belirleyen başvuruları, işaretçileri veya yineleyicileri geçersiz kılar.

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

## <a name="multisetupper_bound"></a><a name="upper_bound"></a> `multiset::upper_bound`

Belirtilen anahtardan daha büyük bir anahtarla bir yineleyiciyi, içindeki ilk öğeye döndürür `multiset` .

```cpp
const_iterator upper_bound(const Key& key) const;

iterator upper_bound(const Key& key);
```

### <a name="parameters"></a>Parametreler

*`key`*\
Aranmakta olan bir öğenin sıralama anahtarıyla Karşılaştırılacak bağımsız değişken anahtarı `multiset` .

### <a name="return-value"></a>Dönüş Değeri

Bir **Yineleyici** veya `const_iterator` bağımsız değişken anahtarından büyük bir anahtarla içindeki bir öğenin konumunu adresleyen `multiset` veya `multiset` anahtar için hiçbir eşleşme bulunmazsa içindeki son öğeden sonra gelen konumu ele alan bir yineleyici.

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

## <a name="multisetvalue_comp"></a><a name="value_comp"></a> `multiset::value_comp`

İçindeki öğe değerlerini sıralamak için kullanılan karşılaştırma nesnesinin bir kopyasını alır `multiset` .

```cpp
value_compare value_comp() const;
```

### <a name="return-value"></a>Dönüş Değeri

`multiset`Şablon parametresi olan öğelerini sıralamak için kullanılan işlev nesnesini döndürür `Compare` .

Hakkında daha fazla bilgi için `Compare` , [ `multiset` sınıf](../standard-library/multiset-class.md) konusunun açıklamalar bölümüne bakın.

### <a name="remarks"></a>Açıklamalar

Saklı nesne, üye işlevini tanımlar:

**bool işleci**( **const Key&** `_xVal` , **const Key&** `_yVal` );

Bu, önce varsa true, `_xVal` sıralama düzeninde eşit değildir döndürür `_yVal` .

Hem hem de [`key_compare`](#key_compare) [`value_compare`](#value_compare) şablon parametresi için eş anlamlılardır `Compare` . Her iki tür de sınıflar kümesi için ve `multiset` özdeş oldukları yerde, sınıflar haritalarının ve farklı oldukları yerlerde uyumluluk için sağlanır `multimap` .

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

## <a name="multisetvalue_compare"></a><a name="value_compare"></a> `multiset::value_compare`

İki sıralama anahtarını karşılaştıran bir işlev nesnesi sağlayan tür, içindeki göreli sıralarını tespit edebilir `multiset` .

```cpp
typedef key_compare value_compare;
```

### <a name="remarks"></a>Açıklamalar

`value_compare` , şablon parametresinin eşanlamlısıdır `Compare` .

Hem hem de [`key_compare`](#key_compare) `value_compare` şablon parametresi için eş anlamlılardır `Compare` . Her iki tür de sınıflar kümesi için ve `multiset` özdeş oldukları yerde, sınıflar haritalarının ve farklı oldukları yerlerde uyumluluk için sağlanır `multimap` .

Hakkında daha fazla bilgi için `Compare` , [Çoklu küme sınıfı](../standard-library/multiset-class.md) konusunun açıklamalar bölümüne bakın.

### <a name="example"></a>Örnek

[`value_comp`](#value_comp)Bildirme ve kullanma hakkında bir örnek için örneğe bakın `value_compare` .

## <a name="multisetvalue_type"></a><a name="value_type"></a> `multiset::value_type`

Bir nesne olarak `multiset` , bir değer olarak kapasitesinin bir öğesi olarak depolanan bir tür.

```cpp
typedef Key value_type;
```

### <a name="remarks"></a>Açıklamalar

`value_type` , şablon parametresinin eşanlamlısıdır `Key` .

Hem hem de [`key_type`](#key_type) `value_type` şablon parametresi için eş anlamlılardır `Key` . Her iki tür de, sınıfları ve çoklu küme için, özdeş oldukları, sınıflar haritalarının ve multimap ile uyumluluk açısından, farklı oldukları durumlar için sağlanır.

Hakkında daha fazla bilgi için `Key` konusunun açıklamalar bölümüne bakın.

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

   // a multiset accepts key_types or value_types as elements
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

[Kapsayıcıları](./stl-containers.md)\
[C++ standart kitaplığı 'nda iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[C++ standart kitaplığı başvurusu](../standard-library/cpp-standard-library-reference.md)