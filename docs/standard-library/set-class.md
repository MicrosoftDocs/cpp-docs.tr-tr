---
title: set Sınıfı
ms.date: 11/04/2016
f1_keywords:
- set/std::set
- set/std::set::allocator_type
- set/std::set::const_iterator
- set/std::set::const_pointer
- set/std::set::const_reference
- set/std::set::const_reverse_iterator
- set/std::set::difference_type
- set/std::set::iterator
- set/std::set::key_compare
- set/std::set::key_type
- set/std::set::pointer
- set/std::set::reference
- set/std::set::reverse_iterator
- set/std::set::size_type
- set/std::set::value_compare
- set/std::set::value_type
- set/std::set::begin
- set/std::set::cbegin
- set/std::set::cend
- set/std::set::clear
- set/std::set::count
- set/std::set::crbegin
- set/std::set::crend
- set/std::set::emplace
- set/std::set::emplace_hint
- set/std::set::empty
- set/std::set::end
- set/std::set::equal_range
- set/std::set::erase
- set/std::set::find
- set/std::set::get_allocator
- set/std::set::insert
- set/std::set::key_comp
- set/std::set::lower_bound
- set/std::set::max_size
- set/std::set::rbegin
- set/std::set::rend
- set/std::set::size
- set/std::set::swap
- set/std::set::upper_bound
- set/std::set::value_comp
helpviewer_keywords:
- std::set [C++]
- std::set [C++], allocator_type
- std::set [C++], const_iterator
- std::set [C++], const_pointer
- std::set [C++], const_reference
- std::set [C++], const_reverse_iterator
- std::set [C++], difference_type
- std::set [C++], iterator
- std::set [C++], key_compare
- std::set [C++], key_type
- std::set [C++], pointer
- std::set [C++], reference
- std::set [C++], reverse_iterator
- std::set [C++], size_type
- std::set [C++], value_compare
- std::set [C++], value_type
- std::set [C++], begin
- std::set [C++], cbegin
- std::set [C++], cend
- std::set [C++], clear
- std::set [C++], count
- std::set [C++], crbegin
- std::set [C++], crend
- std::set [C++], emplace
- std::set [C++], emplace_hint
- std::set [C++], empty
- std::set [C++], end
- std::set [C++], equal_range
- std::set [C++], erase
- std::set [C++], find
- std::set [C++], get_allocator
- std::set [C++], insert
- std::set [C++], key_comp
- std::set [C++], lower_bound
- std::set [C++], max_size
- std::set [C++], rbegin
- std::set [C++], rend
- std::set [C++], size
- std::set [C++], swap
- std::set [C++], upper_bound
- std::set [C++], value_comp
ms.assetid: 8991f9aa-5509-4440-adc1-371512d32018
ms.openlocfilehash: e879e7ffd9f674769e32548195f5017e27e64576
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88846244"
---
# <a name="set-class"></a>set Sınıfı

C++ standart kitaplık kapsayıcı sınıfı kümesi, içerilen öğelerin değerlerinin benzersiz olduğu ve verilerin otomatik olarak sıralandığı anahtar değerler olarak kullanıldığı bir koleksiyondan verilerin depolanması ve alınması için kullanılır. Bir kümedeki bir öğenin değeri doğrudan değiştirilemez. Bunun yerine, eski değerleri silmeniz ve yeni değerlere sahip öğeler eklemeniz gerekir.

## <a name="syntax"></a>Söz dizimi

```cpp
template <class Key,
    class Traits=less<Key>,
    class Allocator=allocator<Key>>
class set
```

### <a name="parameters"></a>Parametreler

*Anahtar*\
Kümede depolanacak öğe veri türü.

*Lerdir*\
İki öğenin değerlerini kümede kendi göreli sıralarını belirlemek için sıralama anahtarları olarak karşılaştırabilen bir işlev nesnesi sağlayan tür. Bu bağımsız değişken isteğe bağlıdır ve ikili koşul **daha az** *\<Key>* varsayılan değerdir.

C++ 14 ' te, `std::less<>` hiçbir tür parametresi olmayan veya koşulunu belirterek heterojen aramayı etkinleştirebilirsiniz `std::greater<>` . Daha fazla bilgi için bkz. [Ilişkilendirilebilir kapsayıcılarda heterojen arama](../standard-library/stl-containers.md#sequence_containers)

*Öğe*\
Kümenin bellek ayırmayı ve ayırmayı kaldırma hakkındaki ayrıntıları içeren saklı ayırıcı nesnesini gösteren tür. Bu bağımsız değişken isteğe bağlıdır ve varsayılan değerdir `allocator<Key>` .

## <a name="remarks"></a>Açıklamalar

C++ standart kitaplığı kümesi:

- İlişkili bir anahtar değerine dayalı öğe değerlerinin verimli alınmasını destekleyen bir değişken boyutu kapsayıcı olan ilişkilendirilebilir bir kapsayıcı. Dahası, basit bir ilişkilendirilebilir kapsayıcıdır, çünkü öğelerinin değerleri kendi anahtar değerleridir.

- Çift yönlüdür, çünkü öğelerine erişmek için çift yönlü bir yineleyici sağlar.

- Sıralıdır, çünkü öğeleri belirtilen karşılaştırma işlevine uygun olarak kapsayıcı içindeki anahtar değerlere göre sıralanır.

- Benzersizdir, çünkü öğelerinin her birinde benzersiz bir anahtar olması gerekir. Ayrıca, küme basit ilişkilendirilebilir bir kapsayıcı olduğundan, onun da öğeleri benzersizdir.

Bir küme, bir sınıf şablonu olarak da tanımlanır, çünkü sağladığı işlevsellik geneldir ve öğe olarak bulunan belirli veri türünden bağımsızdır. Kullanılacak veri türü, karşılaştırma işlevi ve ayırıcı ile birlikte bir sınıf şablonunda bir parametre olarak belirtilir.

Kapsayıcı türünün seçimi genelde uygulamanın gerektirdiği arama ve ekleme türüne dayalı olmalıdır. İlişkilendirilebilir kapsayıcılar, arama, ekleme ve kaldırma işlemleri için en iyi duruma getirilir. Bu işlemleri açıkça destekleyen üye işlevleri, işlevlerini kapsayıcıdaki öğelerin sayısının logaritmasına ortalama orantılı bir sürede gerçekleştirir ve verimlidir. Öğelerin eklenmesi hiçbir yineleyiciyi geçersiz kılmaz; öğelerin kaldırılması yalnızca özellikle kaldırılan öğeleri gösteren yineleyicileri geçersiz kılar.

Küme, değerleri onların kendi anahtarlarıyla ilişkilendiren koşullar uygulama tarafından karşılandığında seçimin ilişkili kapsayıcısı olmalıdır. Kümenin öğeleri benzersizdir ve kendi sıralama anahtarı olarak hizmet eder. Bu tür bir yapı modeli, sözcüklerin yalnızca bir defa geçebildiği sıralı bir sözcükler listesindedir. Sözcüklerin birden çok defa geçmelerine izin verilirse, bir çoklu küme uygun bir kapsayıcı yapısı olacaktır. Değerlerin benzersiz anahtar sözcükler listesine eklenmesi gerekirse, bir eşlem verileri kapsayacak uygun bir yapı olacaktır. Bunun yerine, anahtarlar benzersiz değilse, seçilecek kapsayıcı bir çoklu eşlem olurdu.

Küme, [key_compare](#key_compare)türünde bir saklı işlev nesnesi çağırarak denetlediği diziyi sıralar. Bu saklı nesne, [key_comp](#key_comp)üye işlevi çağırarak erişilebilen bir karşılaştırma işlevidir. Genelde, bu sıralamayı oluşturmak için öğelerin yalnızca küçüktür biçiminde karşılaştırılabilir olması gerekir; böylece, herhangi iki öğe belirtildiğinde, eşit oldukları (yani birinin diğerinden daha küçük olmadığı anlamında) veya birinin diğerinden küçük olduğu belirlenebilir. Bu, denk olmayan öğeler arasında bir sıralamaya neden olur. Daha teknik bir not üzerinde, karşılaştırma işlevi standart matematiksel anlamda katı bir zayıf sıralama sevk eden ikili bir koşuldur. Bir ikili koşul *f*( *x, y*) iki bağımsız değişken nesnesi olan *x* ve *y* ve dönüş değeri olan bir işlev nesnesidir **`true`** **`false`** . İkili koşul geri dönüşsüz, antisimetrik ve geçişli ve denklik geçişli ise, küme üzerinde yer alan bir sıralama katı zayıf bir sıradır, burada iki nesne *x* ve *y* , her ikisi de *f*( *x, y*) ve *f*( *y, x*) false olduğunda denk olarak tanımlanır. Anahtarlar arasındaki eşitliğinin daha güçlü koşulu bu denkliğin yerini alırsa, sıralama (içindeki tüm öğelerin birbirine göre sıralanması anlamında) toplam haline gelir ve eşleşen anahtarlar birbirinden ayırt edilemez olacaktır.

C++ 14 ' te, `std::less<>` hiçbir tür parametresi olmayan veya koşulunu belirterek heterojen aramayı etkinleştirebilirsiniz `std::greater<>` . Daha fazla bilgi için bkz. [Ilişkilendirilebilir kapsayıcılarda heterojen arama](../standard-library/stl-containers.md#sequence_containers)

Küme sınıfı tarafından verilen yineleyici çift yönlü bir yineleyicidir, ancak [Insert](#insert) ve [set](#set) sınıf üyesi işlevleri, şablon parametresi olarak daha zayıf bir giriş yineleyicisini alan, işlevsellik gereksinimleri çift yönlü yineleyicilerin sınıfının garantiden daha düşük olan sürümlere sahiptir. Farklı yineleyici kavramları, işlevselliklerindeki iyileştirmelere göre ilgili bir aile biçimlendirir. Her yineleyici kavramının kendi gereksinimler kümesi vardır ve bunlarla çalışan algoritmaların kendi varsayımlarını yineleyici türü tarafından sağlanan gereksinimlerle sınırlaması gerekir. Bir giriş yineleyicinin bazı nesnelere başvurusunun kaldırılacağı ve dizideki sonraki yineleyiciye artırılabileceği varsayılabilir. Bu en düşük işlevsellik kümesidir, ancak `First` `Last` sınıfın üye işlevleri bağlamında yineleyicilerin bir aralığı hakkında anlamlı bir şekilde konuşabilmek için yeterlidir.

### <a name="constructors"></a>Oluşturucular

|Ad|Açıklama|
|-|-|
|[kurmak](#set)|Boş veya küme öğesinin tümünün veya diğer bir kısmının kopyası olan bir küme oluşturur.|

### <a name="typedefs"></a>Tür tanımları

|Ad|Açıklama|
|-|-|
|[allocator_type](#allocator_type)|Küme nesnesinin sınıfını temsil eden bir tür `allocator` .|
|[const_iterator](#const_iterator)|Küme içindeki bir öğeyi okuyabilen çift yönlü bir yineleyici sağlayan bir tür **`const`** .|
|[const_pointer](#const_pointer)|Bir küme içindeki bir öğeye işaretçi sağlayan bir tür **`const`** .|
|[const_reference](#const_reference)|**`const`** İşlemleri okumak ve gerçekleştirmek için bir küme içinde depolanan öğeye başvuru sağlayan bir tür **`const`** .|
|[const_reverse_iterator](#const_reverse_iterator)|Küme içindeki herhangi bir öğeyi okuyabilen çift yönlü bir yineleyici sağlayan bir tür **`const`** .|
|[difference_type](#difference_type)|Yineleyiciler tarafından gösterilen öğeler arasındaki bir aralıktaki küme öğelerinin sayısını temsil etmek için kullanılabilen işaretli bir tamsayı türü.|
|[iden](#iterator)|Küme içindeki herhangi bir öğeyi okuyabilen veya değiştirebilen çift yönlü yineleyiciler sağlayan tür.|
|[key_compare](#key_compare)|Küme içindeki iki öğenin göreli sırasını belirlemek için iki sıralama anahtarını karşılaştıran bir işlev nesnesi sağlayan bir tür.|
|[key_type](#key_type)|Bir sıralama anahtarı olarak kapasitesi dahilinde bir küme öğesi olarak depolanan nesneyi tanımlayan bir tür.|
|[pointer](#pointer)|Bir küme içindeki öğeye işaretçi sağlayan bir tür.|
|[başvurunun](#reference)|Küme içinde depolanan öğeye başvuru sağlayan bir tür.|
|[reverse_iterator](#reverse_iterator)|Ters döndürülmüş küme içindeki bir öğeyi okuyabilen veya değiştirebilen çift yönlü yineleyiciler sağlayan tür.|
|[size_type](#size_type)|Küme içindeki öğelerin sayısını temsil edebilen bir işaretsiz tamsayı türü.|
|[value_compare](#value_compare)|Küme içindeki iki öğenin kendi göreli sıralarını belirlemek için iki öğeyi karşılaştıran bir işlev nesnesi sağlayan bir tür.|
|[value_type](#value_type)|Bir değer olarak kapasitesi dahilinde bir küme öğesi şeklinde depolanan nesneyi tanımlayan bir tür.|

### <a name="functions"></a>İşlevler

|Ad|Açıklama|
|-|-|
|[başladı](#begin)|Küme içindeki ilk öğeyi ele alan bir yineleyici döndürür.|
|[cbegin](#cbegin)|Küme içindeki ilk öğeyi ele alan sabit bir yineleyici döndürür.|
|[cend](#cend)|Küme içindeki son öğeyi takip eden konumu ele alan sabit bir yineleyici döndürür.|
|[lediğiniz](#clear)|Bir kümenin tüm öğelerini siler.|
|[count](#count)|Anahtarı parametre tarafından belirtilen anahtarla eşleşen küme içindeki öğelerin sayısını döndürür.|
|[crbegin](#rbegin)|Ters çevrilen kümedeki ilk öğeyi ele alan bir sabit yineleyici döndürür.|
|[crend](#rend)|Ters çevrilen kümedeki son öğeden sonra gelen konumu ele alan bir sabit yineleyici döndürür.|
|[Emplace](#emplace)|Bir küme içine yerinde oluşturulmuş bir öğe ekler.|
|[emplace_hint](#emplace_hint)|Bir küme içine, bir yerleşim ipucuyla birlikte yerinde oluşturulmuş bir öğe ekler.|
|[empty](#empty)|Kümenin boş olup olmadığını sınar.|
|[erer](#end)|Küme içindeki son öğeyi takip eden konumu ele alan bir yineleyici döndürür.|
|[equal_range](#equal_range)|Yineleyicilerin bir çiftini, sırasıyla belirtilen anahtardan daha büyük olan bir anahtar ile küme içindeki ilk öğeye ve anahtardan büyük veya ona eşit bir anahtar ile kümedeki ilk öğeye döndürür.|
|[silme](#erase)|Küme içindeki bir öğeyi veya öğelerin aralığını belirtilen konumlardan kaldırır veya belirtilen bir anahtarla eşleşen öğeleri kaldırır.|
|[find](#find)|Belirtilen anahtara denk bir anahtara sahip bir küme içindeki öğenin konumunu ele alan bir yineleyici döndürür.|
|[get_allocator](#get_allocator)|`allocator`Kümeyi oluşturmak için kullanılan nesnenin bir kopyasını döndürür.|
|[ekleyin](#insert)|Bir küme içine bir öğe veya öğe aralığı ekler.|
|[key_comp](#key_comp)|Bir küme içindeki anahtarları sıralamak için kullanılan karşılaştırma nesnesinin bir kopyasını alır.|
|[lower_bound](#lower_bound)|Bir yineleyiciyi belirtilen anahtardan daha büyük veya ona eşit bir anahtarla küme içindeki ilk öğeye döndürür.|
|[max_size](#max_size)|Küme öğesinin maksimum uzunluğunu döndürür.|
|[rbegin](#rbegin)|Ters çevrilen küme içindeki ilk öğeyi ele alan bir yineleyici döndürür.|
|[rend](#rend)|Ters çevrilen küme içindeki son öğeden sonra gelen konumu ele alan bir yineleyici döndürür.|
|[boyutla](#size)|Kümedeki öğelerin sayısını döndürür.|
|[Kur](#swap)|İki kümenin öğelerini birbiriyle değiştirir.|
|[upper_bound](#upper_bound)|Bir yineleyiciyi belirtilen anahtardan daha büyük bir anahtarla küme içindeki ilk öğeye döndürür.|
|[value_comp](#value_comp)|Küme içindeki öğe değerlerini sıralamak için kullanılan karşılaştırma nesnesinin bir kopyasını alır.|

### <a name="operators"></a>İşleçler

|Ad|Açıklama|
|-|-|
|[işleç =](#op_eq)|Bir kümenin öğelerini başka bir küme kopyasıyla değiştirir.|

## <a name="allocator_type"></a><a name="allocator_type"></a> allocator_type

Küme nesnesinin ayırıcı sınıfını temsil eden bir tür.

```cpp
typedef Allocator allocator_type;
```

### <a name="remarks"></a>Açıklamalar

`allocator_type` , şablon parametre [ayırıcısı](../standard-library/set-class.md)için bir eş anlamlı.

Bir çoklu küme tarafından, şablon parametresi olan öğelerini sıralamak için kullanılan işlev nesnesini döndürür `Allocator` .

Hakkında daha fazla bilgi için `Allocator` [set Class](../standard-library/set-class.md) konusunun açıklamalar bölümüne bakın.

### <a name="example"></a>Örnek

Tarafından kullanılan bir örnek için [get_allocator](#get_allocator) örneğe bakın `allocator_type` .

## <a name="begin"></a><a name="begin"></a> başladı

Küme içindeki ilk öğeyi ele alan bir yineleyici döndürür.

```cpp
const_iterator begin() const;

iterator begin();
```

### <a name="return-value"></a>Dönüş Değeri

Küme içindeki ilk öğeyi ele alarak çift yönlü bir yineleyici veya bir boş küme başarılı oluyor.

### <a name="remarks"></a>Açıklamalar

Dönüş değeri `begin` bir öğesine atanırsa `const_iterator` , set nesnesindeki öğeler değiştirilemez. Dönüş değeri `begin` bir öğesine atanırsa `iterator` , set nesnesindeki öğeler değiştirilebilir.

### <a name="example"></a>Örnek

```cpp
// set_begin.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main( )
{
   using namespace std;
   set <int> s1;
   set <int>::iterator s1_Iter;
   set <int>::const_iterator s1_cIter;

   s1.insert( 1 );
   s1.insert( 2 );
   s1.insert( 3 );

   s1_Iter = s1.begin( );
   cout << "The first element of s1 is " << *s1_Iter << endl;

   s1_Iter = s1.begin( );
   s1.erase( s1_Iter );

   // The following 2 lines would err because the iterator is const
   // s1_cIter = s1.begin( );
   // s1.erase( s1_cIter );

   s1_cIter = s1.begin( );
   cout << "The first element of s1 is now " << *s1_cIter << endl;
}
```

```Output
The first element of s1 is 1
The first element of s1 is now 2
```

## <a name="cbegin"></a><a name="cbegin"></a> cbegin

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

## <a name="cend"></a><a name="cend"></a> cend

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

## <a name="clear"></a><a name="clear"></a> lediğiniz

Bir kümenin tüm öğelerini siler.

```cpp
void clear();
```

### <a name="example"></a>Örnek

```cpp
// set_clear.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main( )
{
   using namespace std;
   set <int> s1;

   s1.insert( 1 );
   s1.insert( 2 );

   cout << "The size of the set is initially " << s1.size( )
        << "." << endl;

   s1.clear( );
   cout << "The size of the set after clearing is "
        << s1.size( ) << "." << endl;
}
```

```Output
The size of the set is initially 2.
The size of the set after clearing is 0.
```

## <a name="const_iterator"></a><a name="const_iterator"></a> const_iterator

Küme içindeki bir öğeyi okuyabilen çift yönlü bir yineleyici sağlayan bir tür **`const`** .

```cpp
typedef implementation-defined const_iterator;
```

### <a name="remarks"></a>Açıklamalar

Bir tür `const_iterator` , bir öğenin değerini değiştirmek için kullanılamaz.

### <a name="example"></a>Örnek

' In kullandığı örnek [için bkz](#begin) `const_iterator` ..

## <a name="const_pointer"></a><a name="const_pointer"></a> const_pointer

Bir küme içindeki bir öğeye işaretçi sağlayan bir tür **`const`** .

```cpp
typedef typename allocator_type::const_pointer const_pointer;
```

### <a name="remarks"></a>Açıklamalar

Bir tür `const_pointer` , bir öğenin değerini değiştirmek için kullanılamaz.

Çoğu durumda, bir const kümesi nesnesindeki öğelere erişmek için bir [const_iterator](#const_iterator) kullanılmalıdır.

## <a name="const_reference"></a><a name="const_reference"></a> const_reference

**`const`** İşlemleri okumak ve gerçekleştirmek için bir küme içinde depolanan öğeye başvuru sağlayan bir tür **`const`** .

```cpp
typedef typename allocator_type::const_reference const_reference;
```

### <a name="example"></a>Örnek

```cpp
// set_const_ref.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main( )
{
   using namespace std;
   set <int> s1;

   s1.insert( 10 );
   s1.insert( 20 );

   // Declare and initialize a const_reference &Ref1
   // to the 1st element
   const int &Ref1 = *s1.begin( );

   cout << "The first element in the set is "
        << Ref1 << "." << endl;

   // The following line would cause an error because the
   // const_reference cannot be used to modify the set
   // Ref1 = Ref1 + 5;
}
```

```Output
The first element in the set is 10.
```

## <a name="const_reverse_iterator"></a><a name="const_reverse_iterator"></a> const_reverse_iterator

Küme içindeki herhangi bir öğeyi okuyabilen çift yönlü bir yineleyici sağlayan bir tür **`const`** .

```cpp
typedef std::reverse_iterator<const_iterator> const_reverse_iterator;
```

### <a name="remarks"></a>Açıklamalar

Bir tür, `const_reverse_iterator` bir öğenin değerini değiştiremez ve ters ' de küme boyunca yinelemek için kullanılır.

### <a name="example"></a>Örnek

' In nasıl bildirilemeyeceğini ve kullanılacağına ilişkin bir örnek için bkz. [rend](#rend) için örneğe bakın `const_reverse_iterator` .

## <a name="count"></a><a name="count"></a> biriktirme

Anahtarı parametre tarafından belirtilen anahtarla eşleşen küme içindeki öğelerin sayısını döndürür.

```cpp
size_type count(const Key& key) const;
```

### <a name="parameters"></a>Parametreler

*anahtar*\
Kümeden eşleştirilecek öğelerin anahtarı.

### <a name="return-value"></a>Dönüş Değeri

küme, sıralama anahtarı parametre anahtarıyla eşleşen bir öğe içeriyorsa 1. küme eşleşen bir anahtara sahip bir öğe içermiyorsa 0.

### <a name="remarks"></a>Açıklamalar

Üye işlevi aşağıdaki aralıktaki öğelerin sayısını döndürür:

\[ lower_bound (*anahtar*), upper_bound (*anahtar*)).

### <a name="example"></a>Örnek

Aşağıdaki örnek set:: Count üye işlevinin kullanımını gösterir.

```cpp
// set_count.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main()
{
    using namespace std;
    set<int> s1;
    set<int>::size_type i;

    s1.insert(1);
    s1.insert(1);

    // Keys must be unique in set, so duplicates are ignored
    i = s1.count(1);
    cout << "The number of elements in s1 with a sort key of 1 is: "
         << i << "." << endl;

    i = s1.count(2);
    cout << "The number of elements in s1 with a sort key of 2 is: "
         << i << "." << endl;
}
```

```Output
The number of elements in s1 with a sort key of 1 is: 1.
The number of elements in s1 with a sort key of 2 is: 0.
```

## <a name="crbegin"></a><a name="crbegin"></a> crbegin

Ters çevrilen kümedeki ilk öğeyi ele alan bir sabit yineleyici döndürür.

```cpp
const_reverse_iterator crbegin() const;
```

### <a name="return-value"></a>Dönüş Değeri

Ters çevrilen küme içindeki ilk öğeyi ele almak veya geri alınamaz küme içindeki son öğe olduğunu belirlemek için bir sabit ters çift yönlü Yineleyici.

### <a name="remarks"></a>Açıklamalar

`crbegin` , [Başlangıç](#begin) olarak bir küme ile birlikte kullanıldığında, ters ayarlanmış bir küme ile kullanılır.

Dönüş değeri ile `crbegin` , küme nesnesi değiştirilemez.

### <a name="example"></a>Örnek

```cpp
// set_crbegin.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main( )
{
   using namespace std;
   set <int> s1;
   set <int>::const_reverse_iterator s1_crIter;

   s1.insert( 10 );
   s1.insert( 20 );
   s1.insert( 30 );

   s1_crIter = s1.crbegin( );
   cout << "The first element in the reversed set is "
        << *s1_crIter << "." << endl;
}
```

```Output
The first element in the reversed set is 30.
```

## <a name="crend"></a><a name="crend"></a> crend

Ters çevrilen kümedeki son öğeden sonra gelen konumu ele alan bir sabit yineleyici döndürür.

```cpp
const_reverse_iterator crend() const;
```

### <a name="return-value"></a>Dönüş Değeri

Ters çevrilen bir küme içindeki son öğeden sonra gelen konumu ele alan bir sabit ters çift yönlü yineleyici (geri alınamaz küme içindeki ilk öğeden önce gelen konum).

### <a name="remarks"></a>Açıklamalar

`crend`[End](#end) bir küme ile kullanıldığı gibi ters bir küme ile kullanılır.

Dönüş değeri ile `crend` , küme nesnesi değiştirilemez. Tarafından döndürülen değer `crend` başvurulmamalıdır.

`crend` , bir ters yineleyicinin kendi kümesinin sonuna ulaşmış olup olmadığını test etmek için kullanılabilir.

### <a name="example"></a>Örnek

```cpp
// set_crend.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main() {
   using namespace std;
   set <int> s1;
   set <int>::const_reverse_iterator s1_crIter;

   s1.insert( 10 );
   s1.insert( 20 );
   s1.insert( 30 );

   s1_crIter = s1.crend( );
   s1_crIter--;
   cout << "The last element in the reversed set is "
        << *s1_crIter << "." << endl;
}
```

## <a name="difference_type"></a><a name="difference_type"></a> difference_type

Yineleyiciler tarafından gösterilen öğeler arasındaki bir aralıktaki küme öğelerinin sayısını temsil etmek için kullanılabilen işaretli bir tamsayı türü.

```cpp
typedef typename allocator_type::difference_type difference_type;
```

### <a name="remarks"></a>Açıklamalar

`difference_type`Kapsayıcının yineleyiciler aracılığıyla çıkartılacak veya artırılarak döndürülen türdür. `difference_type`Genellikle yineleyiciler arasındaki *[ilk, son)* aralıktaki öğelerin sayısını temsil etmek için kullanılır ve tarafından işaret edilen öğe `first` `last` `first` ve dahil olmak üzere öğe aralığı ile işaret eder `last` .

`difference_type`Küme gibi tersine çevrilebilir kapsayıcılar tarafından desteklenen çift yönlü yineleyicilerin sınıfını içeren bir giriş yineleyicisinin gereksinimlerini karşılayan tüm yineleyiciler için kullanılabilir olsa da, yineleyiciler arasında çıkarma yalnızca vektör gibi bir rastgele erişim kapsayıcısı tarafından sağlanan rastgele erişim yineleyiciler tarafından desteklenir.

### <a name="example"></a>Örnek

```cpp
// set_diff_type.cpp
// compile with: /EHsc
#include <iostream>
#include <set>
#include <algorithm>

int main( )
{
   using namespace std;

   set <int> s1;
   set <int>::iterator s1_Iter, s1_bIter, s1_eIter;

   s1.insert( 20 );
   s1.insert( 10 );
   s1.insert( 20 );   // won't insert as set elements are unique

   s1_bIter = s1.begin( );
   s1_eIter = s1.end( );

   set <int>::difference_type   df_typ5, df_typ10, df_typ20;

   df_typ5 = count( s1_bIter, s1_eIter, 5 );
   df_typ10 = count( s1_bIter, s1_eIter, 10 );
   df_typ20 = count( s1_bIter, s1_eIter, 20 );

   // the keys, and hence the elements of a set are unique,
   // so there is at most one of a given value
   cout << "The number '5' occurs " << df_typ5
        << " times in set s1.\n";
   cout << "The number '10' occurs " << df_typ10
        << " times in set s1.\n";
   cout << "The number '20' occurs " << df_typ20
        << " times in set s1.\n";

   // count the number of elements in a set
   set <int>::difference_type  df_count = 0;
   s1_Iter = s1.begin( );
   while ( s1_Iter != s1_eIter)
   {
      df_count++;
      s1_Iter++;
   }

   cout << "The number of elements in the set s1 is: "
        << df_count << "." << endl;
}
```

```Output
The number '5' occurs 0 times in set s1.
The number '10' occurs 1 times in set s1.
The number '20' occurs 1 times in set s1.
The number of elements in the set s1 is: 2.
```

## <a name="emplace"></a><a name="emplace"></a> Emplace

Yerinde oluşturulmuş bir öğe ekler (kopyalama veya taşıma işlemleri yapılmaz).

```cpp
template <class... Args>
pair<iterator, bool>
emplace(
    Args&&... args);
```

### <a name="parameters"></a>Parametreler

*args*\
Değeri equivalently sıralı bir öğe içermiyorsa, bu değere eklenecek bir öğe oluşturmak için iletilen bağımsız değişkenler.

### <a name="return-value"></a>Dönüş Değeri

Bir ekleme yapıldıktan sonra bool bileşeni true döndüren bir [çift](../standard-library/pair-structure.md) ve eşleme zaten değeri sıralamada denk bir değere sahip olan bir öğe içeriyorsa false. Dönüş değeri çiftinin yineleyici bileşeni, yeni bir öğenin eklendiği (bool bileşen true ise) veya öğenin zaten bulunduğu yerlerde (bool bileşeni false ise) adresi döndürür.

### <a name="remarks"></a>Açıklamalar

Bu işlev tarafından hiçbir yineleyiciler veya başvuru geçersiz kılınmamıştır.

Emplamak sırasında, bir özel durum oluşturulursa kapsayıcının durumu değiştirilmez.

### <a name="example"></a>Örnek

```cpp
// set_emplace.cpp
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
    set<string> s1;

    auto ret = s1.emplace("ten");

    if (!ret.second){
        cout << "Emplace failed, element with value \"ten\" already exists."
            << endl << "  The existing element is (" << *ret.first << ")"
            << endl;
        cout << "set not modified" << endl;
    }
    else{
        cout << "set modified, now contains ";
        print(s1);
    }
    cout << endl;

    ret = s1.emplace("ten");

    if (!ret.second){
        cout << "Emplace failed, element with value \"ten\" already exists."
            << endl << "  The existing element is (" << *ret.first << ")"
            << endl;
    }
    else{
        cout << "set modified, now contains ";
        print(s1);
    }
    cout << endl;
}
```

## <a name="emplace_hint"></a><a name="emplace_hint"></a> emplace_hint

Yerinde oluşturulmuş bir öğe ekler (kopyalama veya taşıma işlemleri yapılmaz), yerleştirme ipucuyla birlikte.

```cpp
template <class... Args>
iterator emplace_hint(
    const_iterator where,
    Args&&... args);
```

### <a name="parameters"></a>Parametreler

*args*\
Zaten bir değeri equivalently sıralı bir öğe içermiyorsa, bu, küme içine eklenecek bir öğe oluşturmak için iletilen bağımsız değişkenler.

*olmadığı*\
Doğru ekleme noktasını aramaya başlamak için yer. (Bu nokta hemen bundan önce geliyorsa, ekleme, logaritmik bir süre yerine, sabit *zamanlı olarak gerçekleşebilir*.)

### <a name="return-value"></a>Dönüş Değeri

Yeni eklenmekte olan öğe için bir yineleyici.

Öğe zaten mevcut olduğundan ekleme başarısız olursa, varolan öğeye bir yineleyici döndürür.

### <a name="remarks"></a>Açıklamalar

Bu işlev tarafından hiçbir yineleyiciler veya başvuru geçersiz kılınmamıştır.

Emplamak sırasında, bir özel durum oluşturulursa kapsayıcının durumu değiştirilmez.

### <a name="example"></a>Örnek

```cpp
// set_emplace.cpp
// compile with: /EHsc
#include <set>
#include <string>
#include <iostream>

using namespace std;

template <typename S> void print(const S& s) {
    cout << s.size() << " elements: " << endl;

    for (const auto& p : s) {
        cout << "(" << p <<  ") ";
    }

    cout << endl;
}

int main()
{
    set<string> s1;

    // Emplace some test data
    s1.emplace("Anna");
    s1.emplace("Bob");
    s1.emplace("Carmine");

    cout << "set starting data: ";
    print(s1);
    cout << endl;

    // Emplace with hint
    // s1.end() should be the "next" element after this emplacement
    s1.emplace_hint(s1.end(), "Doug");

    cout << "set modified, now contains ";
    print(s1);
    cout << endl;
}
```

## <a name="empty"></a><a name="empty"></a> olmamalıdır

Kümenin boş olup olmadığını sınar.

```cpp
bool empty() const;
```

### <a name="return-value"></a>Dönüş Değeri

**`true`** küme boşsa; **`false`** küme boş değilse.

### <a name="example"></a>Örnek

```cpp
// set_empty.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main( )
{
   using namespace std;
   set <int> s1, s2;
   s1.insert ( 1 );

   if ( s1.empty( ) )
      cout << "The set s1 is empty." << endl;
   else
      cout << "The set s1 is not empty." << endl;

   if ( s2.empty( ) )
      cout << "The set s2 is empty." << endl;
   else
      cout << "The set s2 is not empty." << endl;
}
```

```Output
The set s1 is not empty.
The set s2 is empty.
```

## <a name="end"></a><a name="end"></a> erer

past-the-end yineleyici döndürür.

```cpp
const_iterator end() const;

iterator end();
```

### <a name="return-value"></a>Dönüş Değeri

Son uca Yineleyici. Küme boşsa, `set::end() == set::begin()` .

### <a name="remarks"></a>Açıklamalar

**End** , bir yineleyicinin kümesinin sonunu geçtiğini test etmek için kullanılır.

**End** tarafından döndürülen değer başvurulmamalıdır.

Kod örneği için bkz. [set:: Find](#find).

## <a name="equal_range"></a><a name="equal_range"></a> equal_range

Belirtilen bir anahtardan daha büyük veya ona eşit bir anahtarla ve anahtardan daha büyük bir anahtarla küme içindeki ilk öğeye eşit olan bir küme içindeki ilk öğeye sırasıyla yineleyiciler çiftini döndürür.

```cpp
pair <const_iterator, const_iterator> equal_range (const Key& key) const;

pair <iterator, iterator> equal_range (const Key& key);
```

### <a name="parameters"></a>Parametreler

*anahtar*\
Aranan kümeden bir öğenin sıralama anahtarıyla Karşılaştırılacak bağımsız değişken anahtarı.

### <a name="return-value"></a>Dönüş Değeri

İlk anahtarın [lower_bound](#lower_bound) ve ikincisi anahtarın [upper_bound](#upper_bound) olduğu yineleyiciler çifti.

Üye işlevi tarafından döndürülen bir çiftin ilk Yineleyici öğesine erişmek için `pr` kullanın `pr` . **ilk**olarak, alt sınır Yineleyici için başvuru yapmak üzere \* ( `pr` . **ilk**). Üye işlevi tarafından döndürülen bir çiftin ikinci Yineleyici öğesine erişmek için `pr` kullanın `pr` . **ikincisi**ve üst sınır yineleyicisini başvuru yapmak için \* ( `pr` . **ikinci**).

### <a name="example"></a>Örnek

```cpp
// set_equal_range.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main( )
{
   using namespace std;
   typedef set<int, less< int > > IntSet;
   IntSet s1;
   set <int, less< int > > :: const_iterator s1_RcIter;

   s1.insert( 10 );
   s1.insert( 20 );
   s1.insert( 30 );

   pair <IntSet::const_iterator, IntSet::const_iterator> p1, p2;
   p1 = s1.equal_range( 20 );

   cout << "The upper bound of the element with "
        << "a key of 20 in the set s1 is: "
        << *(p1.second) << "." << endl;

   cout << "The lower bound of the element with "
        << "a key of 20 in the set s1 is: "
        << *(p1.first) << "." << endl;

   // Compare the upper_bound called directly
   s1_RcIter = s1.upper_bound( 20 );
   cout << "A direct call of upper_bound( 20 ) gives "
        << *s1_RcIter << "," << endl
        << "matching the 2nd element of the pair"
        << " returned by equal_range( 20 )." << endl;

   p2 = s1.equal_range( 40 );

   // If no match is found for the key,
   // both elements of the pair return end( )
   if ( ( p2.first == s1.end( ) ) && ( p2.second == s1.end( ) ) )
      cout << "The set s1 doesn't have an element "
           << "with a key less than 40." << endl;
   else
      cout << "The element of set s1 with a key >= 40 is: "
           << *(p1.first) << "." << endl;
}
```

```Output
The upper bound of the element with a key of 20 in the set s1 is: 30.
The lower bound of the element with a key of 20 in the set s1 is: 20.
A direct call of upper_bound( 20 ) gives 30,
matching the 2nd element of the pair returned by equal_range( 20 ).
The set s1 doesn't have an element with a key less than 40.
```

## <a name="erase"></a><a name="erase"></a> silme

Küme içindeki bir öğeyi veya öğelerin aralığını belirtilen konumlardan kaldırır veya belirtilen bir anahtarla eşleşen öğeleri kaldırır.

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

İlk iki üye işlevi için, kaldırılan öğelerin dışında kalan ilk öğeyi veya böyle bir öğe yoksa, küme sonu olan bir öğeyi atayan çift yönlü bir yineleyici.

Üçüncü üye işlevi için, kümeden kaldırılmış olan öğe sayısını döndürür.

### <a name="example"></a>Örnek

```cpp
// set_erase.cpp
// compile with: /EHsc
#include <set>
#include <string>
#include <iostream>
#include <iterator> // next() and prev() helper functions

using namespace std;

using myset = set<string>;

void printset(const myset& s) {
    for (const auto& iter : s) {
        cout << " [" << iter << "]";
    }
    cout << endl << "size() == " << s.size() << endl << endl;
}

int main()
{
    myset s1;

    // Fill in some data to test with, one at a time
    s1.insert("Bob");
    s1.insert("Robert");
    s1.insert("Bert");
    s1.insert("Rob");
    s1.insert("Bobby");

    cout << "Starting data of set s1 is:" << endl;
    printset(s1);
    // The 1st member function removes an element at a given position
    s1.erase(next(s1.begin()));
    cout << "After the 2nd element is deleted, the set s1 is:" << endl;
    printset(s1);

    // Fill in some data to test with, one at a time, using an initializer list
    myset s2{ "meow", "hiss", "purr", "growl", "yowl" };

    cout << "Starting data of set s2 is:" << endl;
    printset(s2);
    // The 2nd member function removes elements
    // in the range [First, Last)
    s2.erase(next(s2.begin()), prev(s2.end()));
    cout << "After the middle elements are deleted, the set s2 is:" << endl;
    printset(s2);

    myset s3;

    // Fill in some data to test with, one at a time, using emplace
    s3.emplace("C");
    s3.emplace("C#");
    s3.emplace("D");
    s3.emplace("D#");
    s3.emplace("E");
    s3.emplace("E#");
    s3.emplace("F");
    s3.emplace("F#");
    s3.emplace("G");
    s3.emplace("G#");
    s3.emplace("A");
    s3.emplace("A#");
    s3.emplace("B");

    cout << "Starting data of set s3 is:" << endl;
    printset(s3);
    // The 3rd member function removes elements with a given Key
    myset::size_type count = s3.erase("E#");
    // The 3rd member function also returns the number of elements removed
    cout << "The number of elements removed from s3 is: " << count << "." << endl;
    cout << "After the element with a key of \"E#\" is deleted, the set s3 is:" << endl;
    printset(s3);
}
```

## <a name="find"></a><a name="find"></a> bilgi

Belirtilen anahtara denk eşdeğeri olan bir küme içindeki bir öğenin konumuna başvuran bir yineleyici döndürür.

```cpp
iterator find(const Key& key);

const_iterator find(const Key& key) const;
```

### <a name="parameters"></a>Parametreler

*anahtar*\
Aranmakta olan kümeden bir öğenin sıralama anahtarıyla eşleştirilecek anahtar değeri.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen anahtara sahip bir öğenin konumuna başvuran bir yineleyici veya `set::end()` anahtar için eşleşme bulunmazsa, küme içindeki son öğeyi () izleyen konum.

### <a name="remarks"></a>Açıklamalar

Üye işlevi, anahtarı karşılaştırıdan daha az bir ilişkiye göre bir sıralamayı karşılayan bir ikili koşul altındaki bağımsız değişken *anahtarına* denk gelen, küme içindeki bir öğeye başvuran bir yineleyici döndürür.

Dönüş değeri `find` bir öğesine atanırsa `const_iterator` , küme nesnesi değiştirilemez. Dönüş değeri `find` bir öğesine atanırsa `iterator` , küme nesnesi değiştirilebilir

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
    set<int> s1({ 40, 45 });
    cout << "The starting set s1 is: " << endl;
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

    cout << "The modified set s1 is: " << endl;
    print_collection(s1);
    cout << endl;
    findit(s1, 45);
    findit(s1, 6);
}
```

## <a name="get_allocator"></a><a name="get_allocator"></a> get_allocator

Kümeyi oluşturmak için kullanılan ayırıcı nesnesinin bir kopyasını döndürür.

```cpp
allocator_type get_allocator() const;
```

### <a name="return-value"></a>Dönüş Değeri

Küme tarafından, şablon parametresi olan belleği yönetmek için kullanılan ayırıcı `Allocator` .

Hakkında daha fazla bilgi için `Allocator` [set Class](../standard-library/set-class.md) konusunun açıklamalar bölümüne bakın.

### <a name="remarks"></a>Açıklamalar

Set sınıfı için ayrıcılar, sınıfın depolamayı nasıl yönettiğini belirtir. C++ standart kitaplık kapsayıcı sınıflarıyla birlikte sağlanan varsayılan ayrıcılar çoğu programlama ihtiyacı için yeterlidir. Kendi ayırıcı sınıfınızı yazmak ve kullanmak, gelişmiş bir C++ konudur.

### <a name="example"></a>Örnek

```cpp
// set_get_allocator.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main( )
{
   using namespace std;
   set <int>::allocator_type s1_Alloc;
   set <int>::allocator_type s2_Alloc;
   set <double>::allocator_type s3_Alloc;
   set <int>::allocator_type s4_Alloc;

   // The following lines declare objects
   // that use the default allocator.
   set <int> s1;
   set <int, allocator<int> > s2;
   set <double, allocator<double> > s3;

   s1_Alloc = s1.get_allocator( );
   s2_Alloc = s2.get_allocator( );
   s3_Alloc = s3.get_allocator( );

   cout << "The number of integers that can be allocated"
        << endl << "before free memory is exhausted: "
        << s2.max_size( ) << "." << endl;

   cout << "\nThe number of doubles that can be allocated"
        << endl << "before free memory is exhausted: "
        << s3.max_size( ) <<  "." << endl;

   // The following line creates a set s4
   // with the allocator of multiset s1.
   set <int> s4( less<int>( ), s1_Alloc );

   s4_Alloc = s4.get_allocator( );

   // Two allocators are interchangeable if
   // storage allocated from each can be
   // deallocated by the other
   if( s1_Alloc == s4_Alloc )
   {
      cout << "\nThe allocators are interchangeable."
           << endl;
   }
   else
   {
      cout << "\nThe allocators are not interchangeable."
           << endl;
   }
}
```

## <a name="insert"></a><a name="insert"></a> ekleyin

Bir küme içine bir öğe veya öğe aralığı ekler.

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
Değeri equivalently olarak sıralanmış bir öğe içermiyorsa, bu değere eklenecek öğenin değeri.

*Olmadığı*\
Doğru ekleme noktasını aramaya başlamak için yer. (Bu nokta hemen bundan önce geliyorsa, ekleme, logaritmik bir süre yerine, sabit *zamanlı olarak gerçekleşebilir*.)

*ValTy*\
Kümesinin bir [value_type](../standard-library/map-class.md#value_type)öğesi oluşturmak için kullanabileceği bağımsız değişken türünü belirten şablon parametresi ve bağımsız *değişken olarak kusursuz* iletme değeri.

*Adı*\
Kopyalanacak ilk öğenin konumu.

*Soyadına*\
Kopyalanacak son öğenin hemen ötesinde konum.

*InputIterator*\
[Value_type](../standard-library/map-class.md#value_type) nesneleri oluşturmak için kullanılabilecek bir türün öğelerine işaret eden bir [giriş yineleyicisinin](../standard-library/input-iterator-tag-struct.md) gereksinimlerini karşılayan şablon işlevi bağımsız değişkeni.

*IList*\
Öğelerin kopyalanacağı [initializer_list](../standard-library/initializer-list.md) .

### <a name="return-value"></a>Dönüş Değeri

Tek öğeli üye işlevleri, (1) ve (2), [pair](../standard-library/pair-structure.md) **`bool`** bir ekleme yapılırsa bileşeni doğru olan bir çift döndürür ve küme zaten sıralamada denk değer olan bir öğe içeriyorsa false 'tur. Return-Value çiftinin yineleyici bileşeni, bileşen true ise yeni ınsertedelement öğesine **`bool`** veya bileşen false ise var olan öğeye işaret eder **`bool`** .

Tek öğeli-ipucu üye işlevleri, (3) ve (4), yeni öğenin kümesine eklendiği konuma işaret eden bir yineleyici döndürür veya eşdeğer bir anahtara sahip bir öğe zaten varsa var olan öğeye.

### <a name="remarks"></a>Açıklamalar

Bu işlev tarafından hiçbir yineleyiciler, işaretçiler veya başvuru geçersiz kılınamaz.

Yalnızca bir öğenin eklenmesi sırasında, bir özel durum oluşturulursa, kapsayıcının durumu değiştirilmez. Birden çok öğenin eklenmesi sırasında, bir özel durum oluşturulursa, kapsayıcı belirtilmemiş ancak geçerli bir durumda bırakılır.

`pair` `pr` Tek öğeli üye işlevleri tarafından döndürülen bir ' ın Yineleyici bileşenine erişmek için, `pr.first` öğesini kullanın; döndürülen çiftin içindeki yineleyiciyi başvuru olarak kullanın `*pr.first` . Bileşene erişmek için **`bool`** kullanın `pr.second` . Örnek için, bu makalenin ilerleyen kısımlarında örnek koda bakın.

Kapsayıcının [value_type](../standard-library/map-class.md#value_type) , kapsayıcıya ait olan bir typedef ve set için `set<V>::value_type` tür `const V` .

Aralık üye işlevi (5), öğe değerlerinin dizisini aralıktaki bir yineleyici tarafından bahsedilen her öğeye karşılık gelen bir kümesine ekler `[First, Last)` ; Bu nedenle, `Last` eklenmez. Kapsayıcı üye işlevi, `end()` kapsayıcıdaki son öğeden hemen sonra gelen konuma başvurur — Örneğin, ifade öğesine `s.insert(v.begin(), v.end());` tüm öğelerini eklemeye çalışır `v` `s` . Yalnızca aralıktaki benzersiz değerlere sahip öğeler eklenir; yinelemeler yoksayıldı. Hangi öğelerin reddedildiğini gözlemlemek için, öğesinin tek öğeli sürümlerini kullanın `insert` .

Başlatıcı listesi üye işlevi (6), öğeleri kümesine kopyalamak için bir [initializer_list](../standard-library/initializer-list.md) kullanır.

Yerinde oluşturulmuş bir öğenin eklenmesi için — diğer bir deyişle, kopyalama veya taşıma işlemleri yapılmaz — bkz. [set:: emplace](#emplace) ve [set:: emplace_hint](#emplace_hint).

### <a name="example"></a>Örnek

```cpp
// set_insert.cpp
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
    set<int> s1;
    // call insert(const value_type&) version
    s1.insert({ 1, 10 });
    // call insert(ValTy&&) version
    s1.insert(20);

    cout << "The original set values of s1 are:" << endl;
    print(s1);

    // intentionally attempt a duplicate, single element
    auto ret = s1.insert(1);
    if (!ret.second){
        auto elem = *ret.first;
        cout << "Insert failed, element with value 1 already exists."
            << endl << "  The existing element is (" << elem << ")"
            << endl;
    }
    else{
        cout << "The modified set values of s1 are:" << endl;
        print(s1);
    }
    cout << endl;

    // single element, with hint
    s1.insert(s1.end(), 30);
    cout << "The modified set values of s1 are:" << endl;
    print(s1);
    cout << endl;

    // The templatized version inserting a jumbled range
    set<int> s2;
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

    cout << "The modified set values of s2 are:" << endl;
    print(s2);
    cout << endl;

    // The templatized versions move-constructing elements
    set<string>  s3;
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

    set<int> s4;
    // Insert the elements from an initializer_list
    s4.insert({ 4, 44, 2, 22, 3, 33, 1, 11, 5, 55 });
    cout << "After initializer_list insertion, s4 contains:" << endl;
    print(s4);
    cout << endl;
}
```

## <a name="iterator"></a><a name="iterator"></a> iden

Bir küme içindeki herhangi bir öğeyi okuyabilen sabit [çift yönlü yineleyiciyi](../standard-library/bidirectional-iterator-tag-struct.md) sağlayan bir tür.

```cpp
typedef implementation-defined iterator;
```

### <a name="example"></a>Örnek

' In nasıl bildirilemeyeceğini ve [kullanılacağına ilişkin bir örnek için bkz](#begin) `iterator` ..

## <a name="key_comp"></a><a name="key_comp"></a> key_comp

Bir küme içindeki anahtarları sıralamak için kullanılan karşılaştırma nesnesinin bir kopyasını alır.

```cpp
key_compare key_comp() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir küme tarafından, şablon parametresi olan öğelerini sıralamak için kullanılan işlev nesnesini döndürür `Traits` .

Hakkında daha fazla bilgi için `Traits` bkz. [set Class](../standard-library/set-class.md) topic.

### <a name="remarks"></a>Açıklamalar

Saklı nesne, üye işlevini tanımlar:

**bool işleci ()**(**const anahtar&** `_xVal` , **const anahtar&** `_yVal` );

Bu, **`true`** `_xVal` önceki ve sıralama düzeninde eşit değilse döndürür `_yVal` .

[Key_compare](#key_compare) ve [value_compare](#value_compare) şablon parametresi için eş anlamlı olduğunu unutmayın `Traits` . Her iki tür de, farklı oldukları, eşleme ve multimap sınıfları ile uyumluluk için, aynı oldukları küme ve çoklu küme sınıfları için sağlanır.

### <a name="example"></a>Örnek

```cpp
// set_key_comp.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main( )
{
   using namespace std;

   set <int, less<int> > s1;
   set<int, less<int> >::key_compare kc1 = s1.key_comp( ) ;
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
           << "where kc1 is the function object of s1."
           << endl;
   }

   set <int, greater<int> > s2;
   set<int, greater<int> >::key_compare kc2 = s2.key_comp( ) ;
   bool result2 = kc2( 2, 3 ) ;
   if(result2 == true)
   {
      cout << "kc2( 2,3 ) returns value of true, "
           << "where kc2 is the function object of s2."
           << endl;
   }
   else
   {
      cout << "kc2( 2,3 ) returns value of false, "
           << "where kc2 is the function object of s2."
           << endl;
   }
}
```

```Output
kc1( 2,3 ) returns value of true, where kc1 is the function object of s1.
kc2( 2,3 ) returns value of false, where kc2 is the function object of s2.
```

## <a name="key_compare"></a><a name="key_compare"></a> key_compare

Küme içindeki iki öğenin göreli sırasını belirlemek için iki sıralama anahtarını karşılaştıran bir işlev nesnesi sağlayan bir tür.

```cpp
typedef Traits key_compare;
```

### <a name="remarks"></a>Açıklamalar

`key_compare` , şablon parametresinin eşanlamlısıdır `Traits` .

Hakkında daha fazla bilgi için `Traits` bkz. [set Class](../standard-library/set-class.md) topic.

Hem hem de `key_compare` [value_compare](#value_compare) şablon parametresi için eş anlamlı olduğunu unutmayın `Traits` . Her iki tür de, farklı oldukları, eşleme ve multimap sınıfları ile uyumluluk için, aynı oldukları küme ve çoklu küme sınıfları için sağlanır.

### <a name="example"></a>Örnek

Bildirme ve kullanma hakkında bir örnek için bkz. [key_comp](#key_comp) örneği `key_compare` .

## <a name="key_type"></a><a name="key_type"></a> key_type

Kapasitesinin sıralama anahtarı olarak bir kümesinin bir öğesi olarak depolandığını tanımlayan bir tür.

```cpp
typedef Key key_type;
```

### <a name="remarks"></a>Açıklamalar

`key_type` , şablon parametresinin eşanlamlısıdır `Key` .

Hakkında daha fazla bilgi için `Key` [set Class](../standard-library/set-class.md) konusunun açıklamalar bölümüne bakın.

Hem hem de `key_type` [value_type](#value_type) şablon parametresi için eş anlamlı olduğunu unutmayın `Key` . Her iki tür de, farklı oldukları, eşleme ve multimap sınıfları ile uyumluluk için, aynı oldukları küme ve çoklu küme sınıfları için sağlanır.

### <a name="example"></a>Örnek

Bildirme ve kullanma hakkında bir örnek için bkz. [value_type](#value_type) örneği `key_type` .

## <a name="lower_bound"></a><a name="lower_bound"></a> lower_bound

Bir yineleyiciyi belirtilen anahtardan daha büyük veya ona eşit bir anahtarla küme içindeki ilk öğeye döndürür.

```cpp
const_iterator lower_bound(const Key& key) const;

iterator lower_bound(const Key& key);
```

### <a name="parameters"></a>Parametreler

*anahtar*\
Aranan kümeden bir öğenin sıralama anahtarıyla Karşılaştırılacak bağımsız değişken anahtarı.

### <a name="return-value"></a>Dönüş Değeri

Bir yineleyici veya `const_iterator` bağımsız değişken anahtarına eşit veya daha büyük bir anahtarla veya anahtar için eşleşme bulunmazsa, küme içindeki son öğeden sonra gelen konumu ele alan bir öğenin konumunu ele alan bir öğe.

### <a name="example"></a>Örnek

```cpp
// set_lower_bound.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main( )
{
   using namespace std;
   set <int> s1;
   set <int> :: const_iterator s1_AcIter, s1_RcIter;

   s1.insert( 10 );
   s1.insert( 20 );
   s1.insert( 30 );

   s1_RcIter = s1.lower_bound( 20 );
   cout << "The element of set s1 with a key of 20 is: "
        << *s1_RcIter << "." << endl;

   s1_RcIter = s1.lower_bound( 40 );

   // If no match is found for the key, end( ) is returned
   if ( s1_RcIter == s1.end( ) )
      cout << "The set s1 doesn't have an element "
           << "with a key of 40." << endl;
   else
      cout << "The element of set s1 with a key of 40 is: "
           << *s1_RcIter << "." << endl;

   // The element at a specific location in the set can be found
   // by using a dereferenced iterator that addresses the location
   s1_AcIter = s1.end( );
   s1_AcIter--;
   s1_RcIter = s1.lower_bound( *s1_AcIter );
   cout << "The element of s1 with a key matching "
        << "that of the last element is: "
        << *s1_RcIter << "." << endl;
}
```

```Output
The element of set s1 with a key of 20 is: 20.
The set s1 doesn't have an element with a key of 40.
The element of s1 with a key matching that of the last element is: 30.
```

## <a name="max_size"></a><a name="max_size"></a> max_size

Küme öğesinin maksimum uzunluğunu döndürür.

```cpp
size_type max_size() const;
```

### <a name="return-value"></a>Dönüş Değeri

Küme için olası en yüksek uzunluk.

### <a name="example"></a>Örnek

```cpp
// set_max_size.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main( )
{
   using namespace std;
   set <int> s1;
   set <int>::size_type i;

   i = s1.max_size( );
   cout << "The maximum possible length "
        << "of the set is " << i << "." << endl;
}
```

## <a name="operator"></a><a name="op_eq"></a> işleç =

Bu öğe öğelerini `set` başka bir öğeden kullanarak değiştirir `set` .

```cpp
set& operator=(const set& right);

set& operator=(set&& right);
```

### <a name="parameters"></a>Parametreler

*Right*\
`set`Buna atanacak yeni öğeler sağlanıyor `set` .

### <a name="remarks"></a>Açıklamalar

İlk sürümü sağ `operator=` için bir [lvalue başvurusu](../cpp/lvalue-reference-declarator-amp.md) kullanır ve *right*öğeleri *sağdan* buna kopyalamak için kullanılır `set` .

İkinci sürüm, sağ için bir [rvalue başvurusu](../cpp/rvalue-reference-declarator-amp-amp.md) kullanır. Öğeleri *sağdan* bu öğe olarak kaydırır `set` .

İşleç işlevi yürütmeden önce bu öğe içindeki tüm öğeler `set` atılır.

### <a name="example"></a>Örnek

```cpp
// set_operator_as.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main( )
   {
   using namespace std;
   set<int> v1, v2, v3;
   set<int>::iterator iter;

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

## <a name="pointer"></a><a name="pointer"></a> çağrısı

Bir küme içindeki öğeye işaretçi sağlayan bir tür.

```cpp
typedef typename allocator_type::pointer pointer;
```

### <a name="remarks"></a>Açıklamalar

Bir tür **işaretçisi** bir öğenin değerini değiştirmek için kullanılabilir.

Çoğu durumda, bir [Yineleyici](#iterator) küme nesnesindeki öğelere erişmek için kullanılmalıdır.

## <a name="rbegin"></a><a name="rbegin"></a> rbegin

Ters çevrilen küme içindeki ilk öğeyi ele alan bir yineleyici döndürür.

```cpp
const_reverse_iterator rbegin() const;

reverse_iterator rbegin();
```

### <a name="return-value"></a>Dönüş Değeri

Ters çevrilen bir küme içindeki ilk öğeyi ele almak veya geri çevrilmeyen küme içindeki son öğe ne olduğunu ele almak için ters yönlü bir yineleyici.

### <a name="remarks"></a>Açıklamalar

`rbegin` , [Başlangıç](#begin) olarak bir küme ile birlikte kullanıldığında, ters ayarlanmış bir küme ile kullanılır.

Öğesinin dönüş değeri `rbegin` öğesine atanmışsa `const_reverse_iterator` , küme nesnesi değiştirilemez. Öğesinin dönüş değeri `rbegin` öğesine atanmışsa `reverse_iterator` , küme nesnesi değiştirilebilir.

`rbegin` , bir küme üzerinde geriye doğru yinelemek için kullanılabilir.

### <a name="example"></a>Örnek

```cpp
// set_rbegin.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main( )
{
   using namespace std;
   set <int> s1;
   set <int>::iterator s1_Iter;
   set <int>::reverse_iterator s1_rIter;

   s1.insert( 10 );
   s1.insert( 20 );
   s1.insert( 30 );

   s1_rIter = s1.rbegin( );
   cout << "The first element in the reversed set is "
        << *s1_rIter << "." << endl;

   // begin can be used to start an iteration
   // through a set in a forward order
   cout << "The set is:";
   for ( s1_Iter = s1.begin( ) ; s1_Iter != s1.end( ); s1_Iter++ )
      cout << " " << *s1_Iter;
   cout << endl;

   // rbegin can be used to start an iteration
   // through a set in a reverse order
   cout << "The reversed set is:";
   for ( s1_rIter = s1.rbegin( ) ; s1_rIter != s1.rend( ); s1_rIter++ )
      cout << " " << *s1_rIter;
   cout << endl;

   // A set element can be erased by dereferencing to its key
   s1_rIter = s1.rbegin( );
   s1.erase ( *s1_rIter );

   s1_rIter = s1.rbegin( );
   cout << "After the erasure, the first element "
        << "in the reversed set is "<< *s1_rIter << "." << endl;
}
```

```Output
The first element in the reversed set is 30.
The set is: 10 20 30
The reversed set is: 30 20 10
After the erasure, the first element in the reversed set is 20.
```

## <a name="reference"></a><a name="reference"></a> başvurunun

Küme içinde depolanan öğeye başvuru sağlayan bir tür.

```cpp
typedef typename allocator_type::reference reference;
```

### <a name="example"></a>Örnek

```cpp
// set_reference.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main( )
{
   using namespace std;
   set <int> s1;

   s1.insert( 10 );
   s1.insert( 20 );

   // Declare and initialize a reference &Ref1 to the 1st element
   const int &Ref1 = *s1.begin( );

   cout << "The first element in the set is "
        << Ref1 << "." << endl;
}
```

```Output
The first element in the set is 10.
```

## <a name="rend"></a><a name="rend"></a> rend

Ters çevrilen küme içindeki son öğeden sonra gelen konumu ele alan bir yineleyici döndürür.

```cpp
const_reverse_iterator rend() const;

reverse_iterator rend();
```

### <a name="return-value"></a>Dönüş Değeri

Ters çevrilen bir küme içindeki son öğeden sonra gelen konumu ele alan ters çift yönlü yineleyici (geri alınamaz küme içindeki ilk öğeden önce gelen konum).

### <a name="remarks"></a>Açıklamalar

`rend`[End](#end) bir küme ile kullanıldığı gibi ters bir küme ile kullanılır.

Öğesinin dönüş değeri `rend` öğesine atanmışsa `const_reverse_iterator` , küme nesnesi değiştirilemez. Öğesinin dönüş değeri `rend` öğesine atanmışsa `reverse_iterator` , küme nesnesi değiştirilebilir. Tarafından döndürülen değer `rend` başvurulmamalıdır.

`rend` , bir ters yineleyicinin kendi kümesinin sonuna ulaşmış olup olmadığını test etmek için kullanılabilir.

### <a name="example"></a>Örnek

```cpp
// set_rend.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main() {
   using namespace std;
   set <int> s1;
   set <int>::iterator s1_Iter;
   set <int>::reverse_iterator s1_rIter;
   set <int>::const_reverse_iterator s1_crIter;

   s1.insert( 10 );
   s1.insert( 20 );
   s1.insert( 30 );

   s1_rIter = s1.rend( );
   s1_rIter--;
   cout << "The last element in the reversed set is "
        << *s1_rIter << "." << endl;

   // end can be used to terminate an iteration
   // through a set in a forward order
   cout << "The set is: ";
   for ( s1_Iter = s1.begin( ) ; s1_Iter != s1.end( ); s1_Iter++ )
      cout << *s1_Iter << " ";
   cout << "." << endl;

   // rend can be used to terminate an iteration
   // through a set in a reverse order
   cout << "The reversed set is: ";
   for ( s1_rIter = s1.rbegin( ) ; s1_rIter != s1.rend( ); s1_rIter++ )
      cout << *s1_rIter << " ";
   cout << "." << endl;

   s1_rIter = s1.rend( );
   s1_rIter--;
   s1.erase ( *s1_rIter );

   s1_rIter = s1.rend( );
   --s1_rIter;
   cout << "After the erasure, the last element in the "
        << "reversed set is " << *s1_rIter << "." << endl;
}
```

## <a name="reverse_iterator"></a><a name="reverse_iterator"></a> reverse_iterator

Ters döndürülmüş küme içindeki bir öğeyi okuyabilen veya değiştirebilen çift yönlü yineleyiciler sağlayan tür.

```cpp
typedef std::reverse_iterator<iterator> reverse_iterator;
```

### <a name="remarks"></a>Açıklamalar

Bir tür `reverse_iterator` , ters olarak küme içinde yinelemek için kullanılır.

### <a name="example"></a>Örnek

Bildirme ve kullanma hakkında bir örnek için bkz. [rbegin](#rbegin) örneği `reverse_iterator` .

## <a name="set"></a><a name="set"></a> kurmak

Boş veya küme öğesinin tümünün veya diğer bir kısmının kopyası olan bir küme oluşturur.

```cpp
set();

explicit set(
    const Traits& Comp);

set(
    const Traits& Comp,
    const Allocator& Al);

set(
    const set& Right);

set(
    set&& Right);

set(
    initializer_list<Type> IList);

set(
    initializer_list<Type> IList,
    const Compare& Comp);

set(
    initializer_list<Type> IList,
    const Compare& Comp,
    const Allocator& Al);

template <class InputIterator>
set(
    InputIterator First,
    InputIterator Last);

template <class InputIterator>
set(
    InputIterator First,
    InputIterator Last,
    const Traits& Comp);

template <class InputIterator>
set(
    InputIterator First,
    InputIterator Last,
    const Traits& Comp,
    const Allocator& Al);
```

### <a name="parameters"></a>Parametreler

*Eşkenar*\
Varsayılan olarak, bu set nesnesi için kullanılacak depolama ayırıcı sınıfı `Allocator` .

*İnin*\
`const Traits`Kümesindeki öğeleri sıralamak için kullanılan tür karşılaştırma işlevi, varsayılan olarak `Compare` .

*Rsağ*\
Oluşturulan küme, bir kopya olacak şekilde ayarlanır.

*Adı*\
Kopyalanacak öğe aralığındaki ilk öğenin konumu.

*Soyadına*\
Kopyalanacak öğe aralığının ötesinde ilk öğenin konumu.

*IList*\
Öğelerin kopyalanacağı initializer_list.

### <a name="remarks"></a>Açıklamalar

Tüm oluşturucular, küme için bellek depolamayı yöneten ve daha sonra [get_allocator](#get_allocator)çağırarak döndürülebilecek bir tür ayırıcı nesnesi depolar. Ayırıcı parametresi, genellikle sınıf bildirimlerinde atlanır ve alternatif ayırıcıları değiştirmek için kullanılan ön işleme makrolarıyla sonuçlanır.

Tüm oluşturucular kümelerini başlatır.

Tüm oluşturucular, `Traits` küme anahtarları arasında bir sıra oluşturmak için kullanılan ve daha sonra [key_comp](#key_comp)çağırarak döndürülebilecek bir işlev nesnesini depolar.

İlk üç Oluşturucu boş bir başlangıç kümesi belirtir. ikinci olarak, `comp` öğelerin sırasını oluşturmak için kullanılan karşılaştırma işlevinin türünü () ve kullanılacak ayırıcı türü () öğesini açıkça belirten üçüncü öğeyi belirtin `al` . Anahtar sözcüğü **`explicit`** bazı otomatik tür dönüştürme türlerini bastırır.

Dördüncü Oluşturucu, kümesinin bir kopyasını belirtir `right` .

Sonraki üç Oluşturucu öğeleri belirtmek için bir initializer_list kullanır.

Sonraki üç Oluşturucu, `first` `last` sınıfın `Traits` ve **ayırıcının**karşılaştırma işlevinin türünü belirtirken açıkça artan bir küme aralığını [,) kopyalar.

Sekizinci Oluşturucu, taşıyarak küme kopyasını belirtir `right` .

### <a name="example"></a>Örnek

```cpp
// set_set.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main()
{
    using namespace std;

    // Create an empty set s0 of key type integer
    set <int> s0;

    // Create an empty set s1 with the key comparison
    // function of less than, then insert 4 elements
    set <int, less<int> > s1;
    s1.insert(10);
    s1.insert(20);
    s1.insert(30);
    s1.insert(40);

    // Create an empty set s2 with the key comparison
    // function of less than, then insert 2 elements
    set <int, less<int> > s2;
    s2.insert(10);
    s2.insert(20);

    // Create a set s3 with the
    // allocator of set s1
    set <int>::allocator_type s1_Alloc;
    s1_Alloc = s1.get_allocator();
    set <int> s3(less<int>(), s1_Alloc);
    s3.insert(30);

    // Create a copy, set s4, of set s1
    set <int> s4(s1);

    // Create a set s5 by copying the range s1[ first,  last)
    set <int>::const_iterator s1_bcIter, s1_ecIter;
    s1_bcIter = s1.begin();
    s1_ecIter = s1.begin();
    s1_ecIter++;
    s1_ecIter++;
    set <int> s5(s1_bcIter, s1_ecIter);

    // Create a set s6 by copying the range s4[ first,  last)
    // and with the allocator of set s2
    set <int>::allocator_type s2_Alloc;
    s2_Alloc = s2.get_allocator();
    set <int> s6(s4.begin(), ++s4.begin(), less<int>(), s2_Alloc);

    cout << "s1 =";
    for (auto i : s1)
        cout << " " << i;
    cout << endl;

    cout << "s2 = " << *s2.begin() << " " << *++s2.begin() << endl;

    cout << "s3 =";
    for (auto i : s3)
        cout << " " << i;
    cout << endl;

    cout << "s4 =";
    for (auto i : s4)
        cout << " " << i;
    cout << endl;

    cout << "s5 =";
    for (auto i : s5)
        cout << " " << i;
    cout << endl;

    cout << "s6 =";
    for (auto i : s6)
        cout << " " << i;
    cout << endl;

    // Create a set by moving s5
    set<int> s7(move(s5));
    cout << "s7 =";
    for (auto i : s7)
        cout << " " << i;
    cout << endl;

    // Create a set with an initializer_list
    cout << "s8 =";
    set<int> s8{ { 1, 2, 3, 4 } };
    for (auto i : s8)
        cout << " " << i;
    cout << endl;

    cout << "s9 =";
    set<int> s9{ { 5, 6, 7, 8 }, less<int>() };
    for (auto i : s9)
        cout << " " << i;
    cout << endl;

    cout << "s10 =";
    set<int> s10{ { 10, 20, 30, 40 }, less<int>(), s9.get_allocator() };
    for (auto i : s10)
        cout << " " << i;
    cout << endl;
}
```

```Output
s1 = 10 20 30 40s2 = 10 20s3 = 30s4 = 10 20 30 40s5 = 10 20s6 = 10s7 = 10 20s8 = 1 2 3 4s9 = 5 6 7 8s10 = 10 20 30 40
```

## <a name="size"></a><a name="size"></a> boyutla

Kümedeki öğelerin sayısını döndürür.

```cpp
size_type size() const;
```

### <a name="return-value"></a>Dönüş Değeri

Küme geçerli uzunluğu.

### <a name="example"></a>Örnek

```cpp
// set_size.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main( )
{
   using namespace std;
   set <int> s1;
   set <int> :: size_type i;

   s1.insert( 1 );
   i = s1.size( );
   cout << "The set length is " << i << "." << endl;

   s1.insert( 2 );
   i = s1.size( );
   cout << "The set length is now " << i << "." << endl;
}
```

```Output
The set length is 1.
The set length is now 2.
```

## <a name="size_type"></a><a name="size_type"></a> size_type

Küme içindeki öğelerin sayısını temsil edebilen bir işaretsiz tamsayı türü.

```cpp
typedef typename allocator_type::size_type size_type;
```

### <a name="example"></a>Örnek

Nasıl bildirilemeyeceğini ve kullanılacağına ilişkin bir örnek için [Boyut](#size) örneğine bakın `size_type`

## <a name="swap"></a><a name="swap"></a> Kur

İki kümenin öğelerini birbiriyle değiştirir.

```cpp
void swap(
    set<Key, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*Right*\
Hedef kümesiyle takas edilecek öğeleri sağlayan bağımsız değişken.

### <a name="remarks"></a>Açıklamalar

Üye işlevi, öğeleri takas edilmekte olan iki küme içindeki öğeleri belirleyen başvuruları, işaretçileri veya yineleyicileri geçersiz kılar.

### <a name="example"></a>Örnek

```cpp
// set_swap.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main( )
{
   using namespace std;
   set <int> s1, s2, s3;
   set <int>::iterator s1_Iter;

   s1.insert( 10 );
   s1.insert( 20 );
   s1.insert( 30 );
   s2.insert( 100 );
   s2.insert( 200 );
   s3.insert( 300 );

   cout << "The original set s1 is:";
   for ( s1_Iter = s1.begin( ); s1_Iter != s1.end( ); s1_Iter++ )
      cout << " " << *s1_Iter;
   cout   << "." << endl;

   // This is the member function version of swap
   s1.swap( s2 );

   cout << "After swapping with s2, list s1 is:";
   for ( s1_Iter = s1.begin( ); s1_Iter != s1.end( ); s1_Iter++ )
      cout << " " << *s1_Iter;
   cout  << "." << endl;

   // This is the specialized template version of swap
   swap( s1, s3 );

   cout << "After swapping with s3, list s1 is:";
   for ( s1_Iter = s1.begin( ); s1_Iter != s1.end( ); s1_Iter++ )
      cout << " " << *s1_Iter;
   cout   << "." << endl;
}
```

```Output
The original set s1 is: 10 20 30.
After swapping with s2, list s1 is: 100 200.
After swapping with s3, list s1 is: 300.
```

## <a name="upper_bound"></a><a name="upper_bound"></a> upper_bound

Belirtilen anahtardan daha büyük bir anahtara sahip olan bir küme içindeki ilk öğeye bir yineleyici döndürür.

```cpp
const_iterator upper_bound(const Key& key) const;

iterator upper_bound(const Key& key);
```

### <a name="parameters"></a>Parametreler

*anahtar*\
Aranan kümeden bir öğenin sıralama anahtarıyla Karşılaştırılacak bağımsız değişken anahtarı.

### <a name="return-value"></a>Dönüş Değeri

Bir `iterator` veya `const_iterator` bağımsız değişken anahtarından daha büyük olan bir anahtarla bir öğenin konumunu ele alan veya anahtar için eşleşme bulunmazsa konumun, küme içindeki son öğeyi izleyen konuma adresleyen bir öğe.

### <a name="example"></a>Örnek

```cpp
// set_upper_bound.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main( )
{
   using namespace std;
   set <int> s1;
   set <int> :: const_iterator s1_AcIter, s1_RcIter;

   s1.insert( 10 );
   s1.insert( 20 );
   s1.insert( 30 );

   s1_RcIter = s1.upper_bound( 20 );
   cout << "The first element of set s1 with a key greater "
        << "than 20 is: " << *s1_RcIter << "." << endl;

   s1_RcIter = s1.upper_bound( 30 );

   // If no match is found for the key, end( ) is returned
   if ( s1_RcIter == s1.end( ) )
      cout << "The set s1 doesn't have an element "
           << "with a key greater than 30." << endl;
   else
      cout << "The element of set s1 with a key > 40 is: "
           << *s1_RcIter << "." << endl;

   // The element at a specific location in the set can be found
   // by using a dereferenced iterator addressing the location
   s1_AcIter = s1.begin( );
   s1_RcIter = s1.upper_bound( *s1_AcIter );
   cout << "The first element of s1 with a key greater than"
        << endl << "that of the initial element of s1 is: "
        << *s1_RcIter << "." << endl;
}
```

```Output
The first element of set s1 with a key greater than 20 is: 30.
The set s1 doesn't have an element with a key greater than 30.
The first element of s1 with a key greater than
that of the initial element of s1 is: 20.
```

## <a name="value_comp"></a><a name="value_comp"></a> value_comp

Küme içindeki öğe değerlerini sıralamak için kullanılan karşılaştırma nesnesinin bir kopyasını alır.

```cpp
value_compare value_comp() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir küme tarafından, şablon parametresi olan öğelerini sıralamak için kullanılan işlev nesnesini döndürür `Traits` .

Hakkında daha fazla bilgi için `Traits` bkz. [set Class](../standard-library/set-class.md) topic.

### <a name="remarks"></a>Açıklamalar

Saklı nesne, üye işlevini tanımlar:

**bool işleci**(**const Key&** `_xVal` , **const Key&** `_yVal` );

Bu, **`true`** `_xVal` önceki ve sıralama düzeninde eşit değilse döndürür `_yVal` .

[Value_compare](#value_compare) ve [key_compare](#key_compare) şablon parametresi için eş anlamlı olduğunu unutmayın `Traits` . Her iki tür de, farklı oldukları, eşleme ve multimap sınıfları ile uyumluluk için, aynı oldukları küme ve çoklu küme sınıfları için sağlanır.

### <a name="example"></a>Örnek

```cpp
// set_value_comp.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main( )
{
   using namespace std;

   set <int, less<int> > s1;
   set <int, less<int> >::value_compare vc1 = s1.value_comp( );
   bool result1 = vc1( 2, 3 );
   if( result1 == true )
   {
      cout << "vc1( 2,3 ) returns value of true, "
           << "where vc1 is the function object of s1."
           << endl;
   }
   else
   {
      cout << "vc1( 2,3 ) returns value of false, "
           << "where vc1 is the function object of s1."
           << endl;
   }

   set <int, greater<int> > s2;
   set<int, greater<int> >::value_compare vc2 = s2.value_comp( );
   bool result2 = vc2( 2, 3 );
   if( result2 == true )
   {
      cout << "vc2( 2,3 ) returns value of true, "
           << "where vc2 is the function object of s2."
           << endl;
   }
   else
   {
      cout << "vc2( 2,3 ) returns value of false, "
           << "where vc2 is the function object of s2."
           << endl;
   }
}
```

```Output
vc1( 2,3 ) returns value of true, where vc1 is the function object of s1.
vc2( 2,3 ) returns value of false, where vc2 is the function object of s2.
```

## <a name="value_compare"></a><a name="value_compare"></a> value_compare

Küme içindeki göreli sıralarını belirlemede iki öğe değerini karşılaştırabilen bir işlev nesnesi sağlayan bir tür.

```cpp
typedef key_compare value_compare;
```

### <a name="remarks"></a>Açıklamalar

`value_compare` , şablon parametresinin eşanlamlısıdır `Traits` .

Hakkında daha fazla bilgi için `Traits` bkz. [set Class](../standard-library/set-class.md) topic.

Hem [key_compare](#key_compare) hem de `value_compare` şablon parametresi için eş anlamlıların olduğunu unutmayın `Traits` . Her iki tür de, farklı oldukları, eşleme ve multimap sınıfları ile uyumluluk için, aynı oldukları küme ve çoklu küme sınıfları için sağlanır.

### <a name="example"></a>Örnek

Bildirme ve kullanma hakkında bir örnek için bkz. [value_comp](#value_comp) örneği `value_compare` .

## <a name="value_type"></a><a name="value_type"></a> value_type

Bir değer olarak kapasitesinin bir kümesi öğesi olarak depolanan bir nesneyi açıklayan bir tür.

```cpp
typedef Key value_type;
```

### <a name="remarks"></a>Açıklamalar

`value_type` , şablon parametresinin eşanlamlısıdır `Key` .

Hakkında daha fazla bilgi için `Key` [set Class](../standard-library/set-class.md) konusunun açıklamalar bölümüne bakın.

Hem [key_type](#key_type) hem de `value_type` şablon parametresi için eş anlamlıların olduğunu unutmayın `Key` . Her iki tür de, farklı oldukları, eşleme ve multimap sınıfları ile uyumluluk için, aynı oldukları küme ve çoklu küme sınıfları için sağlanır.

### <a name="example"></a>Örnek

```cpp
// set_value_type.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main( )
{
   using namespace std;
   set <int> s1;
   set <int>::iterator s1_Iter;

   set <int>::value_type svt_Int;   // Declare value_type
   svt_Int = 10;            // Initialize value_type

   set <int> :: key_type skt_Int;   // Declare key_type
   skt_Int = 20;             // Initialize key_type

   s1.insert( svt_Int );         // Insert value into s1
   s1.insert( skt_Int );         // Insert key into s1

   // A set accepts key_types or value_types as elements
   cout << "The set has elements:";
   for ( s1_Iter = s1.begin( ) ; s1_Iter != s1.end( ); s1_Iter++)
      cout << " " << *s1_Iter;
   cout << "." << endl;
}
```

```Output
The set has elements: 10 20.
```
