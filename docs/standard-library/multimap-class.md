---
title: multimap Sınıfı
description: '`multimap`Her bir öğenin hem veri değerine hem de sıralama anahtarına sahip olduğu bir çift olan bir koleksiyondaki verilerin depolanması ve alınması için kullanılan C++ Standart Şablon kitaplığı (STL) sınıfı IÇIN API başvurusu.'
ms.date: 9/9/2020
f1_keywords:
- map/std::multimap
- map/std::multimap::allocator_type
- map/std::multimap::const_iterator
- map/std::multimap::const_pointer
- map/std::multimap::const_reference
- map/std::multimap::const_reverse_iterator
- map/std::multimap::difference_type
- map/std::multimap::iterator
- map/std::multimap::key_compare
- map/std::multimap::key_type
- map/std::multimap::mapped_type
- map/std::multimap::pointer
- map/std::multimap::reference
- map/std::multimap::reverse_iterator
- map/std::multimap::size_type
- map/std::multimap::value_type
- map/std::multimap::begin
- map/std::multimap::cbegin
- map/std::multimap::cend
- map/std::multimap::clear
- map/std::multimap::contains
- map/std::multimap::count
- map/std::multimap::crbegin
- map/std::multimap::crend
- map/std::multimap::emplace
- map/std::multimap::emplace_hint
- map/std::multimap::empty
- map/std::multimap::end
- map/std::multimap::equal_range
- map/std::multimap::erase
- map/std::multimap::find
- map/std::multimap::get_allocator
- map/std::multimap::insert
- map/std::multimap::key_comp
- map/std::multimap::lower_bound
- map/std::multimap::max_size
- map/std::multimap::rbegin
- map/std::multimap::rend
- map/std::multimap::size
- map/std::multimap::swap
- map/std::multimap::upper_bound
- map/std::multimap::value_comp
helpviewer_keywords:
- std::multimap [C++]
- std::multimap [C++], allocator_type
- std::multimap [C++], const_iterator
- std::multimap [C++], const_pointer
- std::multimap [C++], const_reference
- std::multimap [C++], const_reverse_iterator
- std::multimap [C++], difference_type
- std::multimap [C++], iterator
- std::multimap [C++], key_compare
- std::multimap [C++], key_type
- std::multimap [C++], mapped_type
- std::multimap [C++], pointer
- std::multimap [C++], reference
- std::multimap [C++], reverse_iterator
- std::multimap [C++], size_type
- std::multimap [C++], value_type
- std::multimap [C++], begin
- std::multimap [C++], cbegin
- std::multimap [C++], cend
- std::multimap [C++], clear
- std::multimap [C++], contains
- std::multimap [C++], count
- std::multimap [C++], crbegin
- std::multimap [C++], crend
- std::multimap [C++], emplace
- std::multimap [C++], emplace_hint
- std::multimap [C++], empty
- std::multimap [C++], end
- std::multimap [C++], equal_range
- std::multimap [C++], erase
- std::multimap [C++], find
- std::multimap [C++], get_allocator
- std::multimap [C++], insert
- std::multimap [C++], key_comp
- std::multimap [C++], lower_bound
- std::multimap [C++], max_size
- std::multimap [C++], rbegin
- std::multimap [C++], rend
- std::multimap [C++], size
- std::multimap [C++], swap
- std::multimap [C++], upper_bound
- std::multimap [C++], value_comp
ms.assetid: 8796ae05-37c4-475a-9e61-75fde9d4a463
ms.openlocfilehash: e2d0236a0e643ac92bb771b90a1f021807f03fda
ms.sourcegitcommit: 6280a4c629de0f638ebc2edd446de2a9b11f0406
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2020
ms.locfileid: "90040684"
---
# <a name="multimap-class"></a>multimap Sınıfı

C++ standart kitaplığı multimap sınıfı, her bir öğenin hem veri değerine hem de sıralama anahtarına sahip olduğu bir çift olan bir koleksiyondaki verilerin depolanması ve alınması için kullanılır. Anahtarın değerinin benzersiz olması gerekmez ve verileri otomatik olarak sıralamak için kullanılır. Çoklu eşlemdeki bir öğenin değeri doğrudan değiştirilebilir, ancak ilişkili anahtar değeri doğrudan değiştirilemez. Bunun yerine, eski öğelerle ilişkili anahtar değerleri silinmeli ve eklenen yeni öğelerle ilişkili yeni anahtar değerleri eklenmelidir.

## <a name="syntax"></a>Söz dizimi

```cpp
template <class Key,
    class Type,
    class Traits=less <Key>,
    class Allocator=allocator <pair  <const Key, Type>>>
class multimap;
```

### <a name="parameters"></a>Parametreler

*Anahtar*\
Çoklu eşlemde depolanacak anahtar veri türü.

*Türüyle*\
Çoklu eşlemde depolanacak öğe veri türü.

*Lerdir*\
İki öğenin değerlerini çoklu eşlemde kendi göreli sıralarını belirlemek için sıralama anahtarları olarak karşılaştırabilen bir işlev nesnesi sağlayan tür. İkili koşul `less<Key>` varsayılan değerdir.

C++ 14 ' te, `std::less<>` hiçbir tür parametresi olmayan veya koşulunu belirterek heterojen aramayı etkinleştirebilirsiniz `std::greater<>` . Daha fazla bilgi için bkz. [Ilişkilendirilebilir kapsayıcılarda heterojen arama](../standard-library/stl-containers.md#heterogeneous-lookup-in-associative-containers-c14)

*Öğe*\
Eşlemin bellek ayırmayı ve ayırmayı kaldırma hakkındaki ayrıntıları içeren saklı ayırıcı nesnesini gösteren tür. Bu bağımsız değişken isteğe bağlıdır ve varsayılan değerdir `allocator<pair <const Key, Type> >` .

## <a name="remarks"></a>Açıklamalar

C++ standart kitaplığı multimap sınıfı

- İlişkili bir anahtar değerine dayalı öğe değerlerinin verimli alınmasını destekleyen bir değişken boyutu kapsayıcı olan ilişkilendirilebilir bir kapsayıcı.

- Çift yönlüdür, çünkü öğelerine erişmek için çift yönlü yineleyiciler sağlar.

- Sıralıdır, çünkü öğeleri belirtilen karşılaştırma işlevine uygun olarak kapsayıcı içindeki anahtar değerlere göre sıralanır.

- Birden çok, öğeleri benzersiz bir anahtara sahip olmadığından, bir anahtar değeri onunla ilişkili çok sayıda öğe veri değerine sahip olabilir.

- Bir çift ilişkilendirilebilir kapsayıcıdır, çünkü veri öğelerinin değerleri kendi anahtar değerlerinden farklıdır.

- Sınıf şablonu, sağladığı işlevsellik geneldir ve bu nedenle öğe veya anahtar olarak içerilen belirli veri türünden bağımsızdır. Öğeler ve anahtarlar için kullanılacak veri türleri, karşılaştırma işlevi ve ayırıcı ile birlikte bir sınıf şablonunda parametreler olarak belirtilir.

Map sınıfı tarafından verilen yineleyici çift yönlü bir yineleyicidir, ancak [Insert](#insert) ve [multimap](#multimap) sınıf üyesi işlevleri, şablon parametresi olarak daha zayıf bir giriş yineleyicisini alan, işlevsellik gereksinimleri çift yönlü yineleyicilerin sınıfının garantisiyle daha düşük olan sürümlere sahiptir. Farklı yineleyici kavramları, işlevselliklerindeki iyileştirmelere göre ilgili bir aile biçimlendirir. Her yineleyici kavramının kendi gereksinimler kümesi vardır ve bunlarla çalışan algoritmaların kendi varsayımlarını yineleyici türü tarafından sağlanan gereksinimlerle sınırlaması gerekir. Bir giriş yineleyicinin bazı nesnelere başvurusunun kaldırılacağı ve dizideki sonraki yineleyiciye artırılabileceği varsayılabilir. Bu en düşük işlevsellik kümesidir, ancak `[First, Last)` sınıfın üye işlevleri bağlamında yineleyicilerin bir aralığı hakkında anlamlı bir şekilde konuşabilmek yeterlidir.

Kapsayıcı türünün seçimi genelde uygulamanın gerektirdiği arama ve ekleme türüne dayalı olmalıdır. İlişkilendirilebilir kapsayıcılar, arama, ekleme ve kaldırma işlemleri için en iyi duruma getirilir. Bu işlemleri açıkça destekleyen üye işlevleri, işlevlerini kapsayıcıdaki öğelerin sayısının logaritmasına ortalama orantılı bir sürede gerçekleştirir ve verimlidir. Öğelerin eklenmesi yineleyiciler içermez ve öğeleri kaldırmak yalnızca kaldırılan öğeleri işaret eden yineleyiciler geçersiz kılar.

Çoklu eşlem, değerleri onların kendi anahtarlarıyla ilişkilendiren koşullar uygulama tarafından karşılandığında seçimin ilişkili kapsayıcısı olmalıdır. Bu tür bir yapı modeli, sözcüklerin her zaman benzersiz olarak tanımlanmadığı, deyin, tanımlar, ilişkili dize değerlerine sahip anahtar sözcüklerin sıralı bir listesidir. Bunun yerine anahtar sözcükler benzersiz olarak tanımlanırsa, seçilecek kapsayıcı bir eşlem olurdu. Diğer taraftan, yalnızca sözcüklerin listesi depolanmaktadır, ardından bir küme doğru kapsayıcı olacaktır. Sözcüklerin birden çok örneğine izin veriliyorsa, bir, `multiset` uygun kapsayıcı yapısı olur.

Multimap, [key_compare](#key_compare)türünde bir saklı işlev nesnesi çağırarak denetlediği diziyi sıralar. Bu saklı nesne, [key_comp](#key_comp)üye işlevi çağırarak erişilebilen bir karşılaştırma işlevidir. Genelde, bu sıralamayı oluşturmak için öğelerin yalnızca küçüktür biçiminde karşılaştırılabilir olması gerekir; böylece, herhangi iki öğe belirtildiğinde, eşit oldukları (yani birinin diğerinden daha küçük olmadığı anlamında) veya birinin diğerinden küçük olduğu belirlenebilir. Bu, denk olmayan öğeler arasında bir sıralamaya neden olur. Daha teknik bir not üzerinde, karşılaştırma işlevi standart matematiksel anlamda katı bir zayıf sıralama sevk eden ikili bir koşuldur. İkili koşul `f(x,y)` iki bağımsız değişken nesnesine `x` ve `y` true ya da false dönüş değerine sahip bir işlev nesnesidir. İkili koşul geri dönüşsüz, antisimetrik ve geçişli ve denklik geçişli ise, bir küme üzerinde uygulanan bir sıralama katı zayıf bir sıradır. Bu, iki nesne `x` ve `y` her ikisi de yanlış olduğunda eşdeğer olarak tanımlanır `f(x,y)` `f(y,x)` . Anahtarlar arasındaki eşitliğinin daha güçlü koşulu bu denkliğin yerini alırsa, sıralama (içindeki tüm öğelerin birbirine göre sıralanması anlamında) toplam haline gelir ve eşleşen anahtarlar birbirinden ayırt edilemez olacaktır.

C++ 14 ' te, `std::less<>` hiçbir tür parametresi olmayan veya koşulunu belirterek heterojen aramayı etkinleştirebilirsiniz `std::greater<>` . Daha fazla bilgi için bkz. [Ilişkilendirilebilir kapsayıcılarda heterojen arama](../standard-library/stl-containers.md#sequence_containers) .

## <a name="members"></a>Üyeler

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Description|
|-|-|
|[multimap](#multimap)|`multimap`Boş olan veya bir kısmının tümünün veya bir kısmının kopyası olan oluşturur `multimap` .|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Description|
|-|-|
|[allocator_type](#allocator_type)|Nesnenin sınıfını temsil eden bir tür `allocator` `multimap` .|
|[const_iterator](#const_iterator)|İçindeki bir öğeyi okuyabilen çift yönlü bir yineleyici sağlayan bir tür **`const`** `multimap` .|
|[const_pointer](#const_pointer)|İçindeki bir öğeye işaretçi sağlayan bir tür **`const`** `multimap` .|
|[const_reference](#const_reference)|**`const`** `multimap` İşlem okumak ve gerçekleştirmek için içinde depolanan bir öğeye başvuru sağlayan bir tür **`const`** .|
|[const_reverse_iterator](#const_reverse_iterator)|İçindeki herhangi bir öğeyi okuyabilen çift yönlü bir yineleyici sağlayan bir tür **`const`** `multimap` .|
|[difference_type](#difference_type)|Yineleyiciler tarafından gösterilen öğeler arasındaki bir aralıktaki öğelerinin sayısını temsil etmek için kullanılabilen işaretli bir tamsayı türü `multimap` .|
|[iden](#iterator)|Aynı içindeki öğelere başvuran iki yineleyiciler arasındaki farkı sağlayan bir tür `multimap` .|
|[key_compare](#key_compare)|İçindeki iki öğenin göreli sırasını belirleyebilmek için iki sıralama anahtarını karşılaştırabilen bir işlev nesnesi sağlayan bir tür `multimap` .|
|[key_type](#key_type)|Öğesinin her öğesini oluşturan sıralama anahtarı nesnesini açıklayan bir tür `multimap` .|
|[mapped_type](#mapped_type)|İçinde depolanan veri türünü temsil eden bir tür `multimap` .|
|[pointer](#pointer)|İçindeki bir öğeye işaretçi sağlayan bir tür **`const`** `multimap` .|
|[başvurunun](#reference)|İçinde depolanan bir öğeye başvuru sağlayan bir tür `multimap` .|
|[reverse_iterator](#reverse_iterator)|Ters çevrilen bir öğeyi okuyabilen veya değiştirebilen çift yönlü bir yineleyici sağlayan bir tür `multimap` .|
|[size_type](#size_type)|İçindeki bir öğeye işaretçi sağlayan işaretsiz tamsayı türü **`const`** `multimap` .|
|[value_type](#value_type)|İçinde göreli sıralarını belirlemede iki öğeyi sıralama anahtarları olarak karşılaştırabilen bir işlev nesnesi sağlayan bir tür `multimap` .|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Description|
|-|-|
|[başladı](#begin)|İçindeki ilk öğeyi adresleyen bir yineleyici döndürür `multimap` .|
|[cbegin](#cbegin)|İçindeki ilk öğeyi adresleyen bir const yineleyici döndürür `multimap` .|
|[cend](#cend)|İçindeki son öğeden sonraki konumu ele alan bir const yineleyici döndürür `multimap` .|
|[lediğiniz](#clear)|Tüm öğelerini siler `multimap` .|
|[contains](#contains)<sup>c++ 20</sup> içerir|İçinde belirtilen anahtara sahip bir öğe olup olmadığını denetler `multimap` .|
|[biriktirme](#count)|Bir `multimap` anahtarı parametre belirtilen anahtarla eşleşen bir öğe sayısını döndürür.|
|[crbegin](#crbegin)|Ters çevrilen ilk öğeyi adresleyen bir const yineleyici döndürür `multimap` .|
|[crend](#crend)|Ters çevrilen son öğeden sonraki konumu ele alan bir const yineleyici döndürür `multimap` .|
|[Emplace](#emplace)|İçinde oluşturulan bir öğesi ekler `multimap` .|
|[emplace_hint](#emplace_hint)|Bir yerleştirme ipucuyla birlikte öğesine yerinde oluşturulmuş bir öğe ekler `multimap`|
|[empty](#empty)|`multimap`Boşsa, sınar.|
|[erer](#end)|İçindeki son öğeden sonra gelen konumu ele alan bir yineleyici döndürür `multimap` .|
|[equal_range](#equal_range)|Öğenin anahtarının belirtilen değerle eşleştiği öğeler aralığını bulur.|
|[silme](#erase)|Belirtilen konumlardan bir öğeyi veya öğe aralığını kaldırır `multimap` veya belirtilen bir anahtarla eşleşen öğeleri kaldırır.|
|[find](#find)|İçindeki bir öğenin, `multimap` belirtilen anahtara eşdeğer bir anahtara sahip olan ilk konumunu ele alan bir yineleyici döndürür.|
|[get_allocator](#get_allocator)|`allocator`Oluşturmak için kullanılan nesnenin bir kopyasını döndürür `multimap` .|
|[ekleyin](#insert)|İçine bir öğe veya öğe aralığı ekler `multimap` .|
|[key_comp](#key_comp)|İçindeki anahtarları sıralamak için kullanılan karşılaştırma nesnesinin bir kopyasını alır `multimap` .|
|[lower_bound](#lower_bound)|Bir yineleyiciyi `multimap` belirtilen anahtardan daha büyük veya ona eşit olan bir anahtarla ilk öğesine döndürür.|
|[max_size](#max_size)|Maksimum uzunluğunu döndürür `multimap` .|
|[rbegin](#rbegin)|Ters çevrilen ilk öğeyi adresleyen bir yineleyici döndürür `multimap` .|
|[rend](#rend)|Ters çevrilen son öğeden sonraki konumu ele alan bir yineleyici döndürür `multimap` .|
|[boyutla](#size)|İçindeki öğelerin sayısını döndürür `multimap` .|
|[Kur](#swap)|İki öğenin öğelerini değiş tokuş eder `multimap` .|
|[upper_bound](#upper_bound)|Bir yineleyiciyi `multimap` belirtilen anahtardan daha büyük bir anahtara sahip olan ilk öğeye döndürür.|
|[value_comp](#value_comp)|Üye işlevi, anahtar değerlerini karşılaştırarak öğelerinin sırasını belirleyen bir işlev nesnesi döndürür `multimap` .|

|İşleç|Açıklama|
|-|-|
|[işleç =](#op_eq)|Öğesinin öğelerini `multimap` başka bir kopyasıyla değiştirir `multimap` .|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<map>

**Ad alanı:** std

( **Anahtar**, **değer**) çiftleri türündeki nesneler olarak multimap içinde depolanır `pair` . Çift sınıfı, \<utility> tarafından otomatik olarak eklenen üstbilgiyi gerektirir \<map> .

## <a name="multimapallocator_type"></a><a name="allocator_type"></a> multimap:: allocator_type

Multimap nesnesinin ayırıcı sınıfını temsil eden bir tür.

```cpp
typedef Allocator allocator_type;
```

### <a name="example"></a>Örnek

Kullanarak bir örnek için [get_allocator](#get_allocator) örneğe bakın `allocator_type` .

## <a name="multimapbegin"></a><a name="begin"></a> multimap:: Begin

Multimap içindeki ilk öğeyi adresleyen bir yineleyici döndürür.

```cpp
const_iterator begin() const;

iterator begin();
```

### <a name="return-value"></a>Dönüş Değeri

Çoklu haritadaki ilk öğeyi ele alarak çift yönlü bir yineleyici veya bir boş multimap ile başarılı bir yerde.

### <a name="example"></a>Örnek

```cpp
// multimap_begin.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;
   multimap <int, int> m1;

   multimap <int, int> :: iterator m1_Iter;
   multimap <int, int> :: const_iterator m1_cIter;
   typedef pair <int, int> Int_Pair;

   m1.insert ( Int_Pair ( 0, 0 ) );
   m1.insert ( Int_Pair ( 1, 1 ) );
   m1.insert ( Int_Pair ( 2, 4 ) );

   m1_cIter = m1.begin ( );
   cout << "The first element of m1 is " << m1_cIter -> first << endl;

   m1_Iter = m1.begin ( );
   m1.erase ( m1_Iter );

   // The following 2 lines would err as the iterator is const
   // m1_cIter = m1.begin ( );
   // m1.erase ( m1_cIter );

   m1_cIter = m1.begin( );
   cout << "First element of m1 is now " << m1_cIter -> first << endl;
}
```

```Output
The first element of m1 is 0
First element of m1 is now 1
```

## <a name="multimapcbegin"></a><a name="cbegin"></a> multimap:: cbegın

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

## <a name="multimapcend"></a><a name="cend"></a> multimap:: cend

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

## <a name="multimapclear"></a><a name="clear"></a> multimap:: Clear

Multimap 'in tüm öğelerini siler.

```cpp
void clear();
```

### <a name="example"></a>Örnek

Aşağıdaki örnek multimap:: Clear üye işlevinin kullanımını gösterir.

```cpp
// multimap_clear.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;
   multimap<int, int> m1;
   multimap<int, int>::size_type i;
   typedef pair<int, int> Int_Pair;

   m1.insert(Int_Pair(1, 1));
   m1.insert(Int_Pair(2, 4));

   i = m1.size();
   cout << "The size of the multimap is initially "
        << i << "." << endl;

   m1.clear();
   i = m1.size();
   cout << "The size of the multimap after clearing is "
        << i << "." << endl;
}
```

```Output
The size of the multimap is initially 2.
The size of the multimap after clearing is 0.
```

## <a name="multimapconst_iterator"></a><a name="const_iterator"></a> multimap:: const_iterator

Multimap içindeki bir öğeyi okuyabilen çift yönlü bir yineleyici sağlayan bir tür **`const`** .

```cpp
typedef implementation-defined const_iterator;
```

### <a name="remarks"></a>Açıklamalar

Bir tür `const_iterator` , bir öğenin değerini değiştirmek için kullanılamaz.

`const_iterator`Multimap tarafından tanımlanan [value_type](#value_type)nesnelerine işaret eder, bu tür `pair<const Key, Type>` . Anahtarın değeri, ilk üye çifti ile kullanılabilir ve eşlenmiş öğenin değeri, çiftin ikinci üyesi üzerinden kullanılabilir.

`const_iterator`Multimap içindeki bir öğeye işaret eden bir *citer* başvurusu yapmak için **->** işlecini kullanın.

Öğesinin anahtar değerine erişmek için, `cIter->first` ile eşdeğer olan öğesini kullanın `(*cIter).first` . Öğesi için eşlenen veri değerine erişmek için, `cIter->second` ile eşdeğer olan öğesini kullanın `(*cIter).second` .

### <a name="example"></a>Örnek

Kullanarak bir [örnek için bkz](#begin) `const_iterator` ..

## <a name="multimapconst_pointer"></a><a name="const_pointer"></a> multimap:: const_pointer

Multimap içindeki bir öğeye işaretçi sağlayan bir tür **`const`** .

```cpp
typedef typename allocator_type::const_pointer const_pointer;
```

### <a name="remarks"></a>Açıklamalar

Bir tür `const_pointer` , bir öğenin değerini değiştirmek için kullanılamaz.

Çoğu durumda, bir [Yineleyici](#iterator) multimap nesnesindeki öğelere erişmek için kullanılmalıdır.

## <a name="multimapconst_reference"></a><a name="const_reference"></a> multimap:: const_reference

**`const`** İşlem okumak ve gerçekleştirmek için multimap içinde depolanan bir öğeye başvuru sağlayan bir tür **`const`** .

```cpp
typedef typename allocator_type::const_reference const_reference;
```

### <a name="example"></a>Örnek

```cpp
// multimap_const_ref.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;
   multimap <int, int> m1;
   typedef pair <int, int> Int_Pair;

   m1.insert ( Int_Pair ( 1, 10 ) );
   m1.insert ( Int_Pair ( 2, 20 ) );

   // Declare and initialize a const_reference &Ref1
   // to the key of the first element
   const int &Ref1 = ( m1.begin( ) -> first );

   // The following line would cause an error because the
   // non-const_reference can't be used to access the key
   // int &Ref1 = ( m1.begin( ) -> first );

   cout << "The key of the first element in the multimap is "
        << Ref1 << "." << endl;

   // Declare and initialize a reference &Ref2
   // to the data value of the first element
   int &Ref2 = ( m1.begin( ) -> second );

   cout << "The data value of the first element in the multimap is "
        << Ref2 << "." << endl;
}
```

```Output
The key of the first element in the multimap is 1.
The data value of the first element in the multimap is 10.
```

## <a name="multimapconst_reverse_iterator"></a><a name="const_reverse_iterator"></a> multimap:: const_reverse_iterator

Multimap içinde herhangi bir öğeyi okuyabilen çift yönlü bir yineleyici sağlayan bir tür **`const`** .

```cpp
typedef std::reverse_iterator<const_iterator> const_reverse_iterator;
```

### <a name="remarks"></a>Açıklamalar

Bir tür `const_reverse_iterator` , bir öğenin değerini değiştiremez ve bu öğe, ters eşleme içinde daha sonra yinelemek için kullanılır.

`const_reverse_iterator`Multimap tarafından tanımlanan [value_type](#value_type)nesnelerine işaret eder, bu tür `pair<const Key, Type>` . Anahtarın değeri, ilk üye çifti ile kullanılabilir ve eşlenmiş öğenin değeri, çiftin ikinci üyesi üzerinden kullanılabilir.

`const_reverse_iterator`Multimap içindeki bir öğeye işaret eden *bir başvuruyu* başvuru için, **->** işlecini kullanın.

Öğesinin anahtar değerine erişmek için, `crIter->first` ile eşdeğer olan öğesini kullanın `(*crIter).first` . Öğesi için eşlenen veri değerine erişmek için, `crIter->second` ile eşdeğer olan öğesini kullanın `(*crIter).first` .

### <a name="example"></a>Örnek

Bildirme ve kullanma hakkında bir örnek için bkz. [rend](#rend) örneği `const_reverse_iterator` .

## <a name="multimapcontains"></a><a name="contains"></a> multimap:: Contains

İçinde belirtilen anahtara sahip bir öğe olup olmadığını kontrol edin `multimap` .

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

`template<class K> bool contains(const K& key) const` yalnızca, saydam ise aşırı yükleme çözümüne katılır `key_compare` . Daha fazla bilgi için bkz. [ilişkilendirilebilir kapsayıcılarda heterojen arama](https://docs.microsoft.com/cpp/standard-library/stl-containers#heterogeneous-lookup-in-associative-containers-c14) .

### <a name="example"></a>Örnek

```cpp
// Requires /std:c++latest
#include <map>
#include <string>
#include <iostream>
#include <functional>

int main()
{
    std::multimap<int, bool> m = {{0, false}, {1, true}};

    std::cout << std::boolalpha; // so booleans show as 'true' or 'false'
    std::cout << m.contains(1) << '\n';
    std::cout << m.contains(2) << '\n';

    // call template function
    std::multimap<std::string, int, std::less<>> m2 = {{"ten", 10}, {"twenty", 20}, {"thirty", 30}};
    std::cout << m2.contains("ten");
    
    return 0;
}
```

```Output
true
false
true
```

## <a name="multimapcount"></a><a name="count"></a> multimap:: Count

Anahtarları parametre belirtilen anahtarla eşleşen bir multimap içindeki öğe sayısını döndürür.

```cpp
size_type count(const Key& key) const;
```

### <a name="parameters"></a>Parametreler

*anahtar*\
Multimap 'ten eşleştirilecek öğelerin anahtarı.

### <a name="return-value"></a>Dönüş Değeri

Sıralama anahtarları parametre anahtarıyla eşleşen öğe sayısı; multimap eşleşen bir anahtara sahip bir öğe içermiyorsa 0.

### <a name="remarks"></a>Açıklamalar

Üye işlevi aralıktaki öğe sayısını döndürür

\[ lower_bound (*anahtar*), upper_bound (*anahtar*))

Bu, anahtar değer *anahtarına*sahiptir.

### <a name="example"></a>Örnek

Aşağıdaki örnek, multimap:: Count üye işlevinin kullanımını gösterir.

```cpp
// multimap_count.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
    using namespace std;
    multimap<int, int> m1;
    multimap<int, int>::size_type i;
    typedef pair<int, int> Int_Pair;

    m1.insert(Int_Pair(1, 1));
    m1.insert(Int_Pair(2, 1));
    m1.insert(Int_Pair(1, 4));
    m1.insert(Int_Pair(2, 1));

    // Elements don't need to have unique keys in multimap,
    // so duplicates are allowed and counted
    i = m1.count(1);
    cout << "The number of elements in m1 with a sort key of 1 is: "
         << i << "." << endl;

    i = m1.count(2);
    cout << "The number of elements in m1 with a sort key of 2 is: "
         << i << "." << endl;

    i = m1.count(3);
    cout << "The number of elements in m1 with a sort key of 3 is: "
         << i << "." << endl;
}
```

```Output
The number of elements in m1 with a sort key of 1 is: 2.
The number of elements in m1 with a sort key of 2 is: 2.
The number of elements in m1 with a sort key of 3 is: 0.
```

## <a name="multimapcrbegin"></a><a name="crbegin"></a> multimap:: crbegın

Ters çevrilen multimap içindeki ilk öğeyi adresleyen bir const yineleyici döndürür.

```cpp
const_reverse_iterator crbegin() const;
```

### <a name="return-value"></a>Dönüş Değeri

Ters çevrilen [multimap](../standard-library/multimap-class.md) içindeki ilk öğeyi ele almak veya geri çevrilmede son öğe olduğunu belirlemek için bir sabit ters çift yönlü Yineleyici `multimap` .

### <a name="remarks"></a>Açıklamalar

`crbegin` , `multimap` ile birlikte [Başlangıç](#begin) ile kullanılır `multimap` .

Dönüş değeri ile `crbegin` `multimap` nesne değiştirilemez.

`crbegin` , geriye doğru yinelemek için kullanılabilir `multimap` .

### <a name="example"></a>Örnek

```cpp
// multimap_crbegin.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;
   multimap <int, int> m1;

   multimap <int, int> :: const_reverse_iterator m1_crIter;
   typedef pair <int, int> Int_Pair;

   m1.insert ( Int_Pair ( 1, 10 ) );
   m1.insert ( Int_Pair ( 2, 20 ) );
   m1.insert ( Int_Pair ( 3, 30 ) );

   m1_crIter = m1.crbegin( );
   cout << "The first element of the reversed multimap m1 is "
        << m1_crIter -> first << "." << endl;
}
```

```Output
The first element of the reversed multimap m1 is 3.
```

## <a name="multimapcrend"></a><a name="crend"></a> multimap:: crend

Ters çevrilen multimap içindeki son öğeden sonra gelen konumu ele alan bir const yineleyici döndürür.

```cpp
const_reverse_iterator crend() const;
```

### <a name="return-value"></a>Dönüş Değeri

Ters çevrilen [multimap](../standard-library/multimap-class.md) içindeki son öğeden sonra gelen konumu ele alan bir sabit ters çift yönlü yineleyici (geri çevrilmede ilk öğeden önce gelen konum `multimap` ).

### <a name="remarks"></a>Açıklamalar

`crend` , `multimap` ile birlikte kullanılan [multimap:: End](#end) ile birlikte kullanılır `multimap` .

Dönüş değeri ile `crend` `multimap` nesne değiştirilemez.

`crend` , geriye doğru bir yineleyicinin sonuna ulaşılıp ulaşılmadığını test etmek için kullanılabilir `multimap` .

Tarafından döndürülen değer `crend` başvurulmamalıdır.

### <a name="example"></a>Örnek

```cpp
// multimap_crend.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;
   multimap <int, int> m1;

   multimap <int, int> :: const_reverse_iterator m1_crIter;
   typedef pair <int, int> Int_Pair;

   m1.insert ( Int_Pair ( 1, 10 ) );
   m1.insert ( Int_Pair ( 2, 20 ) );
   m1.insert ( Int_Pair ( 3, 30 ) );

   m1_crIter = m1.crend( );
   m1_crIter--;
   cout << "The last element of the reversed multimap m1 is "
        << m1_crIter -> first << "." << endl;
}
```

```Output
The last element of the reversed multimap m1 is 1.
```

## <a name="multimapdifference_type"></a><a name="difference_type"></a> multimap::d ifference_type

Yineleyiciler tarafından gösterilen öğeler arasındaki bir aralıktaki multimap 'in öğe sayısını temsil etmek için kullanılabilen işaretli bir tamsayı türü.

```cpp
typedef typename allocator_type::difference_type difference_type;
```

### <a name="remarks"></a>Açıklamalar

`difference_type`Kapsayıcının yineleyiciler aracılığıyla çıkartılacak veya artırılarak döndürülen türdür. `difference_type`Genellikle yineleyiciler arasındaki [*ilk*, *son*) aralıktaki öğelerin sayısını temsil etmek için kullanılır ve tarafından işaret edilen öğe `first` `last` `first` ve dahil olmak üzere öğe aralığı ile işaret eder `last` .

, `difference_type` Küme gibi tersine çevrilebilir kapsayıcılar tarafından desteklenen çift yönlü yineleyicilerin sınıfını içeren bir giriş yineleyicisinin gereksinimlerini karşılayan tüm yineleyiciler için kullanılabilir olsa da, yineleyiciler arasında çıkarma yalnızca vektör gibi bir rastgele erişim kapsayıcısı tarafından sağlanan rastgele erişim yineleyiciler tarafından desteklenir.

### <a name="example"></a>Örnek

```cpp
// multimap_diff_type.cpp
// compile with: /EHsc
#include <iostream>
#include <map>
#include <algorithm>

int main( )
{
   using namespace std;
   multimap <int, int> m1;
   typedef pair <int, int> Int_Pair;

   m1.insert ( Int_Pair ( 2, 20 ) );
   m1.insert ( Int_Pair ( 1, 10 ) );
   m1.insert ( Int_Pair ( 3, 20 ) );

   // The following will insert as multimap keys are not unique
   m1.insert ( Int_Pair ( 2, 30 ) );

   multimap <int, int>::iterator m1_Iter, m1_bIter, m1_eIter;
   m1_bIter = m1.begin( );
   m1_eIter = m1.end( );

   // Count the number of elements in a multimap
   multimap <int, int>::difference_type  df_count = 0;
   m1_Iter = m1.begin( );
   while ( m1_Iter != m1_eIter )
   {
      df_count++;
      m1_Iter++;
   }

   cout << "The number of elements in the multimap m1 is: "
        << df_count << "." << endl;
}
```

```Output
The number of elements in the multimap m1 is: 4.
```

## <a name="multimapemplace"></a><a name="emplace"></a> multimap:: emplace

Yerinde oluşturulmuş bir öğe ekler (kopyalama veya taşıma işlemleri yapılmaz).

```cpp
template <class... Args>
iterator emplace(Args&&... args);
```

### <a name="parameters"></a>Parametreler

*args*\
Multimap 'e eklenecek bir öğe oluşturmak için iletilen bağımsız değişkenler.

### <a name="return-value"></a>Dönüş Değeri

Yeni eklenmekte olan öğe için bir yineleyici.

### <a name="remarks"></a>Açıklamalar

Bu işlev tarafından kapsayıcı öğelerine yönelik başvuru geçersiz kılınmamıştır, ancak kapsayıcı için tüm yineleyiciler geçersiz kılınabilir.

Ekleme sırasında bir özel durum oluşturulursa, kapsayıcı değiştirilmemiş olarak kalır ve özel durum yeniden oluşturulur.

Bir öğe [value_type](../standard-library/map-class.md#value_type) bir çifdir, böylece bir öğe değeri, ilk bileşeni anahtar değerine eşit olan ve ikinci bileşen öğenin veri değerine eşit olan bir sıralı çift olacaktır.

### <a name="example"></a>Örnek

```cpp
// multimap_emplace.cpp
// compile with: /EHsc
#include <map>
#include <string>
#include <iostream>

using namespace std;

template <typename M> void print(const M& m) {
    cout << m.size() << " elements: " << endl;

    for (const auto& p : m) {
        cout << "(" << p.first <<  "," << p.second << ") ";
    }

    cout << endl;
}

int main()
{
    multimap<string, string> m1;

    m1.emplace("Anna", "Accounting");
    m1.emplace("Bob", "Accounting");
    m1.emplace("Carmine", "Engineering");

    cout << "multimap modified, now contains ";
    print(m1);
    cout << endl;

    m1.emplace("Bob", "Engineering");

    cout << "multimap modified, now contains ";
    print(m1);
    cout << endl;
}
```

## <a name="multimapemplace_hint"></a><a name="emplace_hint"></a> multimap:: emplace_hint

Yerinde oluşturulmuş bir öğe ekler (kopyalama veya taşıma işlemleri yapılmaz), yerleştirme ipucuyla birlikte.

```cpp
template <class... Args>
iterator emplace_hint(
    const_iterator where,
    Args&&... args);
```

### <a name="parameters"></a>Parametreler

*args*\
Multimap 'e eklenecek bir öğe oluşturmak için iletilen bağımsız değişkenler.

*olmadığı*\
Doğru ekleme noktasını aramaya başlamak için yer. (Bu nokta hemen bundan önce geliyorsa, ekleme, logaritmik bir süre yerine, sabit *zamanlı olarak gerçekleşebilir*.)

### <a name="return-value"></a>Dönüş Değeri

Yeni eklenmekte olan öğe için bir yineleyici.

### <a name="remarks"></a>Açıklamalar

Bu işlev tarafından kapsayıcı öğelerine yönelik başvuru geçersiz kılınmamıştır, ancak kapsayıcı için tüm yineleyiciler geçersiz kılınabilir.

Emplamak sırasında, bir özel durum oluşturulursa kapsayıcının durumu değiştirilmez.

Bir öğe [value_type](../standard-library/map-class.md#value_type) bir çifdir, böylece bir öğe değeri, ilk bileşeni anahtar değerine eşit olan ve ikinci bileşen öğenin veri değerine eşit olan bir sıralı çift olacaktır.

Kod örneği için bkz. [map:: emplace_hint](../standard-library/map-class.md#emplace_hint).

## <a name="multimapempty"></a><a name="empty"></a> multimap:: Empty

Çoklu eşleme boşsa sınar.

```cpp
bool empty() const;
```

### <a name="return-value"></a>Dönüş Değeri

**`true`** multimap boşsa; **`false`** multimap boş değilse.

### <a name="example"></a>Örnek

```cpp
// multimap_empty.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;
   multimap <int, int> m1, m2;

   typedef pair <int, int> Int_Pair;
   m1.insert ( Int_Pair ( 1, 1 ) );

   if ( m1.empty( ) )
      cout << "The multimap m1 is empty." << endl;
   else
      cout << "The multimap m1 is not empty." << endl;

   if ( m2.empty( ) )
      cout << "The multimap m2 is empty." << endl;
   else
      cout << "The multimap m2 is not empty." << endl;
}
```

```Output
The multimap m1 is not empty.
The multimap m2 is empty.
```

## <a name="multimapend"></a><a name="end"></a> multimap:: End

past-the-end yineleyici döndürür.

```cpp
const_iterator end() const;

iterator end();
```

### <a name="return-value"></a>Dönüş Değeri

Son uca Yineleyici. Multimap boşsa, `multimap::end() == multimap::begin()` .

### <a name="remarks"></a>Açıklamalar

**son** , bir yineleyicinin multimap 'in sonunu geçtiğini test etmek için kullanılır.

**End** tarafından döndürülen değer başvurulmamalıdır.

Kod örneği için bkz. [multimap:: Find](#find).

## <a name="multimapequal_range"></a><a name="equal_range"></a> multimap:: equal_range

Öğenin anahtarının belirtilen değerle eşleştiği öğeler aralığını bulur.

```cpp
pair <const_iterator, const_iterator> equal_range (const Key& key) const;

pair <iterator, iterator> equal_range (const Key& key);
```

### <a name="parameters"></a>Parametreler

*anahtar*\
Aranan multimap öğesinden bir öğenin sıralama anahtarıyla Karşılaştırılacak bağımsız değişken anahtarı.

### <a name="return-value"></a>Dönüş Değeri

Birincisi anahtarın [lower_bound](#lower_bound) , ikincisi ise anahtarın [upper_bound](#upper_bound) olan yinelemelerin bir çiftinden biridir.

Üye işlevi tarafından döndürülen bir çiftin ilk Yineleyici öğesine erişmek için `pr` kullanın `pr` . **ilk** olarak, alt sınır Yineleyici için başvuru yapmak üzere \* ( `pr` . **ilk**). Üye işlevi tarafından döndürülen bir çiftin ikinci Yineleyici öğesine erişmek için `pr` kullanın `pr` . **ikincisi** ve üst sınır yineleyicisini başvuru yapmak için \* ( `pr` . **ikinci**).

### <a name="example"></a>Örnek

```cpp
// multimap_equal_range.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;
   typedef multimap <int, int, less<int> > IntMMap;
   IntMMap m1;
   multimap <int, int> :: const_iterator m1_RcIter;
   typedef pair <int, int> Int_Pair;

   m1.insert ( Int_Pair ( 1, 10 ) );
   m1.insert ( Int_Pair ( 2, 20 ) );
   m1.insert ( Int_Pair ( 3, 30 ) );

   pair <IntMMap::const_iterator, IntMMap::const_iterator> p1, p2;
   p1 = m1.equal_range( 2 );

   cout << "The lower bound of the element with "
        << "a key of 2 in the multimap m1 is: "
        << p1.first -> second << "." << endl;

   cout << "The upper bound of the element with "
        << "a key of 2 in the multimap m1 is: "
        << p1.second -> second << "." << endl;

   // Compare the upper_bound called directly
   m1_RcIter = m1.upper_bound( 2 );

   cout << "A direct call of upper_bound( 2 ) gives "
        << m1_RcIter -> second << "," << endl
        << "matching the 2nd element of the pair "
        << "returned by equal_range( 2 )." << endl;

   p2 = m1.equal_range( 4 );

   // If no match is found for the key,
   // both elements of the pair return end( )
   if ( ( p2.first == m1.end( ) ) && ( p2.second == m1.end( ) ) )
      cout << "The multimap m1 doesn't have an element "
           << "with a key less than 4." << endl;
   else
      cout << "The element of multimap m1 with a key >= 40 is: "
           << p1.first -> first << "." << endl;
}
```

```Output
The lower bound of the element with a key of 2 in the multimap m1 is: 20.
The upper bound of the element with a key of 2 in the multimap m1 is: 30.
A direct call of upper_bound( 2 ) gives 30,
matching the 2nd element of the pair returned by equal_range( 2 ).
The multimap m1 doesn't have an element with a key less than 4.
```

## <a name="multimaperase"></a><a name="erase"></a> multimap:: Erase

Çoklu haritadaki bir öğeyi veya öğe aralığını belirtilen konumlardan kaldırır veya belirtilen bir anahtarla eşleşen öğeleri kaldırır.

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
Kaldırılacak öğelerin anahtarı.

### <a name="return-value"></a>Dönüş Değeri

İlk iki üye işlevi için, kaldırılan tüm öğelerin ötesinde kalan ilk öğeyi veya böyle bir öğe yoksa haritanın sonu olan bir öğeyi atayan çift yönlü bir yineleyici.

Üçüncü üye işlevi için multimap 'ten kaldırılmış olan öğe sayısını döndürür.

### <a name="remarks"></a>Açıklamalar

Kod örneği için bkz. [map:: Erase](../standard-library/map-class.md#erase).

## <a name="multimapfind"></a><a name="find"></a> multimap:: Find

Bir çok haritadaki, belirtilen anahtara eşdeğer bir anahtara sahip olan bir öğenin ilk konumuna başvuran bir yineleyici döndürür.

```cpp
iterator find(const Key& key);

const_iterator find(const Key& key) const;
```

### <a name="parameters"></a>Parametreler

*anahtar*\
Aranan multimap öğesinden bir öğenin sıralama anahtarıyla eşleştirilecek anahtar değeri.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen anahtara sahip bir öğenin konumuna başvuran bir yineleyici veya `multimap::end()` anahtar için eşleşme bulunmazsa, multimap () içindeki son öğeden geçen konumu.

### <a name="remarks"></a>Açıklamalar

Üye işlevi, sıralama anahtarı, karşılaştırıdan daha az bir ilişkiye göre sıralama yapan bir ikili koşul altındaki bağımsız değişken anahtarına denk gelen, multimap içindeki bir öğeye başvuran bir yineleyici döndürür.

Dönüş değeri `find` bir öğesine atanırsa `const_iterator` , multimap nesnesi değiştirilemez. Dönüş değeri `find` bir öğesine atanırsa `iterator` , multimap nesnesi değiştirilebilir.

### <a name="example"></a>Örnek

```cpp
// compile with: /EHsc /W4 /MTd
#include <map>
#include <iostream>
#include <vector>
#include <string>
#include <utility>  // make_pair()

using namespace std;

template <typename A, typename B> void print_elem(const pair<A, B>& p) {
    cout << "(" << p.first << ", " << p.second << ") ";
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
    multimap<int, string> m1({ { 40, "Zr" }, { 45, "Rh" } });
    cout << "The starting multimap m1 is (key, value):" << endl;
    print_collection(m1);

    vector<pair<int, string>> v;
    v.push_back(make_pair(43, "Tc"));
    v.push_back(make_pair(41, "Nb"));
    v.push_back(make_pair(46, "Pd"));
    v.push_back(make_pair(42, "Mo"));
    v.push_back(make_pair(44, "Ru"));
    v.push_back(make_pair(44, "Ru")); // attempt a duplicate

    cout << "Inserting the following vector data into m1:" << endl;
    print_collection(v);

    m1.insert(v.begin(), v.end());

    cout << "The modified multimap m1 is (key, value):" << endl;
    print_collection(m1);
    cout << endl;
    findit(m1, 45);
    findit(m1, 6);
}
```

## <a name="multimapget_allocator"></a><a name="get_allocator"></a> multimap:: get_allocator

Multimap oluşturmak için kullanılan ayırıcı nesnesinin bir kopyasını döndürür.

```cpp
allocator_type get_allocator() const;
```

### <a name="return-value"></a>Dönüş Değeri

Multimap tarafından kullanılan ayırıcı.

### <a name="remarks"></a>Açıklamalar

Multimap sınıfı için ayrıcılar, sınıfın depolamayı nasıl yönettiğini belirtir. C++ standart kitaplığı kapsayıcı sınıflarıyla birlikte sağlanan varsayılan ayrıcılar çoğu programlama ihtiyacı için yeterlidir. Kendi ayırıcı sınıfınızı yazmak ve kullanmak, gelişmiş bir C++ konudur.

### <a name="example"></a>Örnek

```cpp
// multimap_get_allocator.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;
   multimap <int, int>::allocator_type m1_Alloc;
   multimap <int, int>::allocator_type m2_Alloc;
   multimap <int, double>::allocator_type m3_Alloc;
   multimap <int, int>::allocator_type m4_Alloc;

   // The following lines declare objects
   // that use the default allocator.
   multimap <int, int> m1;
   multimap <int, int, allocator<int> > m2;
   multimap <int, double, allocator<double> > m3;

   m1_Alloc = m1.get_allocator( );
   m2_Alloc = m2.get_allocator( );
   m3_Alloc = m3.get_allocator( );

   cout << "The number of integers that can be allocated"
        << endl << "before free memory is exhausted: "
        << m2.max_size( ) << ".\n" << endl;

   cout << "The number of doubles that can be allocated"
        << endl << "before free memory is exhausted: "
        << m3.max_size( ) <<  ".\n" << endl;

   // The following line creates a multimap m4
   // with the allocator of multimap m1.
   map <int, int> m4( less<int>( ), m1_Alloc );

   m4_Alloc = m4.get_allocator( );

   // Two allocators are interchangeable if
   // storage allocated from each can be
   // deallocated via the other
   if( m1_Alloc == m4_Alloc )
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

## <a name="multimapinsert"></a><a name="insert"></a> multimap:: INSERT

Multimap içine bir öğe veya öğe aralığı ekler.

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
Multimap 'e eklenecek bir öğenin değeri.

*Olmadığı*\
Doğru ekleme noktasını aramaya başlamak için yer. (Bu nokta hemen bundan önce geliyorsa, ekleme, logaritmik bir süre yerine, sabit *zamanlı olarak gerçekleşebilir*.)

*ValTy*\
Eşlemenin [value_type](../standard-library/map-class.md#value_type)bir öğesi oluşturmak için kullanabileceği bağımsız değişken türünü belirten şablon parametresi ve bağımsız değişken olarak *kusursuz iletme değeri* .

*Adı*\
Kopyalanacak ilk öğenin konumu.

*Soyadına*\
Kopyalanacak son öğenin hemen ötesinde konum.

*InputIterator*\
[Value_type](../standard-library/map-class.md#value_type) nesneleri oluşturmak için kullanılabilecek bir türün öğelerine işaret eden bir [giriş yineleyicisinin](../standard-library/input-iterator-tag-struct.md) gereksinimlerini karşılayan şablon işlevi bağımsız değişkeni.

*IList*\
Öğelerin kopyalanacağı [initializer_list](../standard-library/initializer-list.md) .

### <a name="return-value"></a>Dönüş Değeri

Tek öğeli-ekleme üye işlevleri, (1) ve (2), yeni öğenin multimap 'e eklendiği konuma bir yineleyici döndürür.

Tek öğeli-ipucu üye işlevleri, (3) ve (4), yeni öğenin multimap 'e eklendiği konuma işaret eden bir yineleyici döndürür.

### <a name="remarks"></a>Açıklamalar

Bu işlev tarafından geçersiz kılınan işaretçiler veya başvurular yok, ancak kapsayıcı için tüm yineleyiciler geçersiz kılınabilir.

Yalnızca bir öğenin eklenmesi sırasında, bir özel durum oluşturulursa, kapsayıcının durumu değiştirilmez. Birden çok öğenin eklenmesi sırasında, bir özel durum oluşturulursa, kapsayıcı belirtilmemiş ancak geçerli bir durumda bırakılır.

Kapsayıcının [value_type](../standard-library/map-class.md#value_type) , kapsayıcısına ait olan ve Map için olan bir typedef 'dir `multimap<K, V>::value_type` `pair<const K, V>` . Bir öğenin değeri, ilk bileşenin anahtar değere eşit olduğu ve ikinci bileşenin öğenin veri değerine eşit olduğu sıralı bir çiftidir.

Aralık üye işlevi (5), öğe değerlerinin dizisini aralıktaki bir yineleyici tarafından bahsedilen her öğeye karşılık gelen multimap 'e ekler `[First, Last)` ; Bu nedenle, *son* eklenmez. Kapsayıcı üye işlevi, `end()` kapsayıcıdaki son öğeden hemen sonra gelen konumu ifade eder; örneğin, ifade öğesine `m.insert(v.begin(), v.end());` tüm öğelerini ekler `v` `m` .

Başlatıcı listesi üye işlevi (6), öğeleri haritaya kopyalamak için bir [initializer_list](../standard-library/initializer-list.md) kullanır.

Yerinde oluşturulmuş bir öğenin eklenmesi için (yani, kopyalama veya taşıma işlemleri yapılmaz), bkz. [multimap:: emplace](#emplace) ve [multimap:: emplace_hint](#emplace_hint).

### <a name="example"></a>Örnek

```cpp
// multimap_insert.cpp
// compile with: /EHsc
#include <map>
#include <iostream>
#include <string>
#include <vector>
#include <utility>  // make_pair()

using namespace std;

template <typename M> void print(const M& m) {
    cout << m.size() << " elements: ";

    for (const auto& p : m) {
        cout << "(" << p.first << ", " << p.second << ") ";
    }

    cout << endl;
}

int main()
{

    // insert single values
    multimap<int, int> m1;
    // call insert(const value_type&) version
    m1.insert({ 1, 10 });
    // call insert(ValTy&&) version
    m1.insert(make_pair(2, 20));

    cout << "The original key and mapped values of m1 are:" << endl;
    print(m1);

    // intentionally attempt a duplicate, single element
    m1.insert(make_pair(1, 111));

    cout << "The modified key and mapped values of m1 are:" << endl;
    print(m1);

    // single element, with hint
    m1.insert(m1.end(), make_pair(3, 30));
    cout << "The modified key and mapped values of m1 are:" << endl;
    print(m1);
    cout << endl;

    // The templatized version inserting a jumbled range
    multimap<int, int> m2;
    vector<pair<int, int>> v;
    v.push_back(make_pair(43, 294));
    v.push_back(make_pair(41, 262));
    v.push_back(make_pair(45, 330));
    v.push_back(make_pair(42, 277));
    v.push_back(make_pair(44, 311));

    cout << "Inserting the following vector data into m2:" << endl;
    print(v);

    m2.insert(v.begin(), v.end());

    cout << "The modified key and mapped values of m2 are:" << endl;
    print(m2);
    cout << endl;

    // The templatized versions move-constructing elements
    multimap<int, string>  m3;
    pair<int, string> ip1(475, "blue"), ip2(510, "green");

    // single element
    m3.insert(move(ip1));
    cout << "After the first move insertion, m3 contains:" << endl;
    print(m3);

    // single element with hint
    m3.insert(m3.end(), move(ip2));
    cout << "After the second move insertion, m3 contains:" << endl;
    print(m3);
    cout << endl;

    multimap<int, int> m4;
    // Insert the elements from an initializer_list
    m4.insert({ { 4, 44 }, { 2, 22 }, { 3, 33 }, { 1, 11 }, { 5, 55 } });
    cout << "After initializer_list insertion, m4 contains:" << endl;
    print(m4);
    cout << endl;
}
```

## <a name="multimapiterator"></a><a name="iterator"></a> multimap:: Yineleyici

Çoklu haritadaki herhangi bir öğeyi okuyabilen veya değiştirebilen çift yönlü bir yineleyici sağlayan bir tür.

```cpp
typedef implementation-defined iterator;
```

### <a name="remarks"></a>Açıklamalar

`iterator`Multimap tarafından tanımlanan [value_type](#value_type)nesnelerine işaret eder, bu tür `pair<const Key, Type>` . Anahtarın değeri, ilk üye çifti ile kullanılabilir ve eşlenmiş öğenin değeri, çiftin ikinci üyesi üzerinden kullanılabilir.

`iterator`Çoklu haritadaki bir öğeye işaret eden bir *Iter* başvurusu yapmak için **->** işlecini kullanın.

Öğesinin anahtar değerine erişmek için, `Iter->first` ile eşdeğer olan öğesini kullanın `(*Iter).first` . Öğesi için eşlenen veri değerine erişmek için, `Iter->second` ile eşdeğer olan öğesini kullanın `(*Iter).second` .

Bir türü `iterator` , bir öğenin değerini değiştirmek için kullanılabilir.

### <a name="example"></a>Örnek

Bildirme ve kullanma hakkında bir [örnek için bkz](#begin) . örnek `iterator` .

## <a name="multimapkey_comp"></a><a name="key_comp"></a> multimap:: key_comp

Birden çok haritadaki anahtarları sıralamak için kullanılan karşılaştırma nesnesinin bir kopyasını alır.

```cpp
key_compare key_comp() const;
```

### <a name="return-value"></a>Dönüş Değeri

Multimap 'in öğelerini sıralamak için kullandığı işlev nesnesini döndürür.

### <a name="remarks"></a>Açıklamalar

Saklı nesne, üye işlevini tanımlar

`bool operator( const Key& x, const Key& y);`

*x* sıralamayı sıralama düzeninde *tam olarak önce geliyorsa true* döndürür.

### <a name="example"></a>Örnek

```cpp
// multimap_key_comp.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;

   multimap <int, int, less<int> > m1;
   multimap <int, int, less<int> >::key_compare kc1 = m1.key_comp( ) ;
   bool result1 = kc1( 2, 3 ) ;
   if( result1 == true )
   {
      cout << "kc1( 2,3 ) returns value of true, "
           << "where kc1 is the function object of m1."
           << endl;
   }
   else
   {
      cout << "kc1( 2,3 ) returns value of false "
           << "where kc1 is the function object of m1."
           << endl;
   }

   multimap <int, int, greater<int> > m2;
   multimap <int, int, greater<int> >::key_compare kc2 = m2.key_comp( );
   bool result2 = kc2( 2, 3 ) ;
   if( result2 == true )
   {
      cout << "kc2( 2,3 ) returns value of true, "
           << "where kc2 is the function object of m2."
           << endl;
   }
   else
   {
      cout << "kc2( 2,3 ) returns value of false, "
           << "where kc2 is the function object of m2."
           << endl;
   }
}
```

```Output
kc1( 2,3 ) returns value of true, where kc1 is the function object of m1.
kc2( 2,3 ) returns value of false, where kc2 is the function object of m2.
```

## <a name="multimapkey_compare"></a><a name="key_compare"></a> multimap:: key_compare

Multimap içindeki iki öğenin göreli sırasını belirleyebilmek için iki sıralama anahtarını karşılaştırabilen bir işlev nesnesi sağlayan bir tür.

```cpp
typedef Traits key_compare;
```

### <a name="remarks"></a>Açıklamalar

`key_compare` , şablon parametresinin eşanlamlısıdır `Traits` .

Hakkında daha fazla bilgi için `Traits` bkz. [multimap sınıfı](../standard-library/multimap-class.md) konusu.

### <a name="example"></a>Örnek

Bildirme ve kullanma hakkında bir örnek için bkz. [key_comp](#key_comp) örneği `key_compare` .

## <a name="multimapkey_type"></a><a name="key_type"></a> multimap:: key_type

Multimap 'in her öğesini oluşturan sıralama anahtarı nesnesini açıklayan bir tür.

```cpp
typedef Key key_type;
```

### <a name="remarks"></a>Açıklamalar

`key_type` , şablon parametresinin eşanlamlısıdır `Key` .

Hakkında daha fazla bilgi için `Key` , [multimap sınıfı](../standard-library/multimap-class.md) konusunun açıklamalar bölümüne bakın.

### <a name="example"></a>Örnek

Bildirme ve kullanma hakkında bir örnek için bkz. [value_type](#value_type) örneği `key_type` .

## <a name="multimaplower_bound"></a><a name="lower_bound"></a> multimap:: lower_bound

Bir yineleyiciyi belirtilen anahtardan daha büyük veya ona eşit olan bir çok haritadaki ilk öğeye döndürür.

```cpp
iterator lower_bound(const Key& key);

const_iterator lower_bound(const Key& key) const;
```

### <a name="parameters"></a>Parametreler

*anahtar*\
Aranan multimap öğesinden bir öğenin sıralama anahtarıyla Karşılaştırılacak bağımsız değişken anahtarı.

### <a name="return-value"></a>Dönüş Değeri

Bir yineleyici veya `const_iterator` bağımsız değişken anahtarına eşit veya ondan daha büyük bir anahtara sahip olan çok haritadaki bir öğenin konumunu adresleyen ya da anahtar için eşleşme bulunmazsa, multimap içindeki son öğeden sonra gelen konumu ele alan bir yineleyici.

Dönüş değeri `lower_bound` bir öğesine atanırsa `const_iterator` , multimap nesnesi değiştirilemez. Dönüş değeri `lower_bound` bir **Yineleyici**öğesine atanırsa, multimap nesnesi değiştirilebilir.

### <a name="example"></a>Örnek

```cpp
// multimap_lower_bound.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;
   multimap <int, int> m1;
   multimap <int, int> :: const_iterator m1_AcIter, m1_RcIter;
   typedef pair <int, int> Int_Pair;

   m1.insert ( Int_Pair ( 1, 10 ) );
   m1.insert ( Int_Pair ( 2, 20 ) );
   m1.insert ( Int_Pair ( 3, 20 ) );
   m1.insert ( Int_Pair ( 3, 30 ) );

   m1_RcIter = m1.lower_bound( 2 );
   cout << "The element of multimap m1 with a key of 2 is: "
        << m1_RcIter -> second << "." << endl;

   m1_RcIter = m1.lower_bound( 3 );
   cout << "The first element of multimap m1 with a key of 3 is: "
        << m1_RcIter -> second << "." << endl;

   // If no match is found for the key, end( ) is returned
   m1_RcIter = m1.lower_bound( 4 );

   if ( m1_RcIter == m1.end( ) )
      cout << "The multimap m1 doesn't have an element "
              << "with a key of 4." << endl;
   else
      cout << "The element of multimap m1 with a key of 4 is: "
                << m1_RcIter -> second << "." << endl;

   // The element at a specific location in the multimap can be
   // found using a dereferenced iterator addressing the location
   m1_AcIter = m1.end( );
   m1_AcIter--;
   m1_RcIter = m1.lower_bound( m1_AcIter -> first );
   cout << "The first element of m1 with a key matching\n"
        << "that of the last element is: "
        << m1_RcIter -> second << "." << endl;

   // Note that the first element with a key equal to
   // the key of the last element is not the last element
   if ( m1_RcIter == --m1.end( ) )
      cout << "This is the last element of multimap m1."
           << endl;
   else
      cout << "This is not the last element of multimap m1."
           << endl;
}
```

```Output
The element of multimap m1 with a key of 2 is: 20.
The first element of multimap m1 with a key of 3 is: 20.
The multimap m1 doesn't have an element with a key of 4.
The first element of m1 with a key matching
that of the last element is: 20.
This is not the last element of multimap m1.
```

## <a name="multimapmapped_type"></a><a name="mapped_type"></a> multimap:: mapped_type

Multimap içinde depolanan veri türünü temsil eden bir tür.

```cpp
typedef Type mapped_type;
```

### <a name="remarks"></a>Açıklamalar

`mapped_type` , şablon parametresinin eşanlamlısıdır `Type` .

Hakkında daha fazla bilgi için `Type` bkz. [multimap sınıfı](../standard-library/multimap-class.md) konusu.

### <a name="example"></a>Örnek

Bildirme ve kullanma hakkında bir örnek için bkz. [value_type](#value_type) örneği `key_type` .

## <a name="multimapmax_size"></a><a name="max_size"></a> multimap:: max_size

Multimap 'in maksimum uzunluğunu döndürür.

```cpp
size_type max_size() const;
```

### <a name="return-value"></a>Dönüş Değeri

Multimap 'in olası en yüksek uzunluğu.

### <a name="example"></a>Örnek

```cpp
// multimap_max_size.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;
   multimap <int, int> m1;
   multimap <int, int> :: size_type i;

   i = m1.max_size( );
   cout << "The maximum possible length "
        << "of the multimap is " << i << "." << endl;
}
```

## <a name="multimapmultimap"></a><a name="multimap"></a> multimap:: multimap

Boş veya başka bir çok eşlemenin tümünün veya bir kısmının kopyası olan bir multimap oluşturur.

```cpp
multimap();

explicit multimap(
    const Traits& Comp);

multimap(
    const Traits& Comp,
    const Allocator& Al);

map(
    const multimap& Right);

multimap(
    multimap&& Right);

multimap(
    initializer_list<value_type> IList);

multimap(
    initializer_list<value_type> IList,
    const Compare& Comp);

multimap(
    initializer_list<value_type> IList,
    const Compare& Comp,
    const Allocator& Al);

template <class InputIterator>
multimap(
    InputIterator First,
    InputIterator Last);

template <class InputIterator>
multimap(
    InputIterator First,
    InputIterator Last,
    const Traits& Comp);

template <class InputIterator>
multimap(
    InputIterator First,
    InputIterator Last,
    const Traits& Comp,
    const Allocator& Al);
```

### <a name="parameters"></a>Parametreler

*Eşkenar*\
Varsayılan ayırıcı olan bu multimap nesnesi için kullanılacak depolama ayırıcı sınıfı.

*İnin*\
`constTraits`Haritadaki öğeleri sıralamak için kullanılan türün karşılaştırma işlevi, varsayılan olarak `Traits` .

*Right*\
Oluşturulan kümesinin bir kopya olması gereken harita.

*Adı*\
Kopyalanacak öğe aralığındaki ilk öğenin konumu.

*Soyadına*\
Kopyalanacak öğe aralığının ötesinde ilk öğenin konumu.

*IList*\
Öğelerin kopyalanacağı initializer_list.

### <a name="remarks"></a>Açıklamalar

Tüm oluşturucular, multimap için bellek depolamayı yöneten ve daha sonra [get_allocator](#get_allocator)çağırarak döndürülebilecek bir tür ayırıcı nesnesi depolar. Ayırıcı parametresi, genellikle sınıf bildirimlerinde atlanır ve alternatif ayırıcıları değiştirmek için kullanılan ön işleme makrolarıyla sonuçlanır.

Tüm oluşturucular multimap 'i başlatır.

Tüm oluşturucular `Traits` , multimap 'in anahtarları arasında bir sıra oluşturmak için kullanılan ve daha sonra [key_comp](#key_comp)çağırarak döndürülebilecek bir işlev nesnesini depolar.

İlk üç Oluşturucu boş bir ilk multimap, öğelerin sırasını oluşturmak için kullanılan karşılaştırma işlevi (*comp*) türünü ve üçüncü açıkça kullanılmak üzere ayırıcı türü (*Al*) belirten bir ad belirtir. Anahtar sözcük, **`explicit`** bazı otomatik tür dönüştürme türlerini bastırır.

Dördüncü Oluşturucu, multimap *sağ*bir kopyasını belirtir.

Beşinci Oluşturucu, *sağa*taşıyarak multimap 'in bir kopyasını belirtir.

6 TH, 7. ve 8. oluşturucular bir initializer_list üyelerini kopyalar.

Sonraki üç Oluşturucu, `[First, Last)` bir haritanın aralığını, sınıfın ve ayırıcının karşılaştırma işlevinin türünü belirtirken açıkça artarak kopyalar `Traits` .

### <a name="example"></a>Örnek

```cpp
// multimap_ctor.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main()
{
    using namespace std;
    typedef pair <int, int> Int_Pair;

    // Create an empty multimap m0 of key type integer
    multimap <int, int> m0;

    // Create an empty multimap m1 with the key comparison
    // function of less than, then insert 4 elements
    multimap <int, int, less<int> > m1;
    m1.insert(Int_Pair(1, 10));
    m1.insert(Int_Pair(2, 20));
    m1.insert(Int_Pair(3, 30));
    m1.insert(Int_Pair(4, 40));

    // Create an empty multimap m2 with the key comparison
    // function of greater than, then insert 2 elements
    multimap <int, int, less<int> > m2;
    m2.insert(Int_Pair(1, 10));
    m2.insert(Int_Pair(2, 20));

    // Create a multimap m3 with the
    // allocator of multimap m1
    multimap <int, int>::allocator_type m1_Alloc;
    m1_Alloc = m1.get_allocator();
    multimap <int, int> m3(less<int>(), m1_Alloc);
    m3.insert(Int_Pair(3, 30));

    // Create a copy, multimap m4, of multimap m1
    multimap <int, int> m4(m1);

    // Create a multimap m5 by copying the range m1[ first,  last)
    multimap <int, int>::const_iterator m1_bcIter, m1_ecIter;
    m1_bcIter = m1.begin();
    m1_ecIter = m1.begin();
    m1_ecIter++;
    m1_ecIter++;
    multimap <int, int> m5(m1_bcIter, m1_ecIter);

    // Create a multimap m6 by copying the range m4[ first,  last)
    // and with the allocator of multimap m2
    multimap <int, int>::allocator_type m2_Alloc;
    m2_Alloc = m2.get_allocator();
    multimap <int, int> m6(m4.begin(), ++m4.begin(), less<int>(), m2_Alloc);

    cout << "m1 =";
    for (auto i : m1)
        cout << i.first << " " << i.second << ", ";
    cout << endl;

    cout << "m2 =";
    for (auto i : m2)
        cout << i.first << " " << i.second << ", ";
    cout << endl;

    cout << "m3 =";
    for (auto i : m3)
        cout << i.first << " " << i.second << ", ";
    cout << endl;

    cout << "m4 =";
    for (auto i : m4)
        cout << i.first << " " << i.second << ", ";
    cout << endl;

    cout << "m5 =";
    for (auto i : m5)
        cout << i.first << " " << i.second << ", ";
    cout << endl;

    cout << "m6 =";
    for (auto i : m6)
        cout << i.first << " " << i.second << ", ";
    cout << endl;

    // Create a multimap m8 by copying in an initializer_list
    multimap<int, int> m8{ { { 1, 1 }, { 2, 2 }, { 3, 3 }, { 4, 4 } } };
    cout << "m8: = ";
    for (auto i : m8)
        cout << i.first << " " << i.second << ", ";
    cout << endl;

    // Create a multimap m9 with an initializer_list and a comparator
    multimap<int, int> m9({ { 5, 5 }, { 6, 6 }, { 7, 7 }, { 8, 8 } }, less<int>());
    cout << "m9: = ";
    for (auto i : m9)
        cout << i.first << " " << i.second << ", ";
    cout << endl;

    // Create a multimap m10 with an initializer_list, a comparator, and an allocator
    multimap<int, int> m10({ { 9, 9 }, { 10, 10 }, { 11, 11 }, { 12, 12 } }, less<int>(), m9.get_allocator());
    cout << "m10: = ";
    for (auto i : m10)
        cout << i.first << " " << i.second << ", ";
    cout << endl;

}
```

## <a name="multimapoperator"></a><a name="op_eq"></a> multimap:: operator =

Multimap 'in öğelerini başka bir multimap 'in kopyasıyla değiştirir.

```cpp
multimap& operator=(const multimap& right);

multimap& operator=(multimap&& right);
```

### <a name="parameters"></a>Parametreler

*Right*\
' A Kopyalanmakta olan [multimap](../standard-library/multimap-class.md) `multimap` .

### <a name="remarks"></a>Açıklamalar

İçindeki varolan öğeleri sildikten sonra `multimap` , ' `operator=` nin içeriğini kopyalar ya da içine *taşısa* `multimap` .

### <a name="example"></a>Örnek

```cpp
// multimap_operator_as.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
   {
   using namespace std;
   multimap<int, int> v1, v2, v3;
   multimap<int, int>::iterator iter;

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

## <a name="multimappointer"></a><a name="pointer"></a> multimap::p oınter

Multimap içindeki bir öğeye işaretçi sağlayan bir tür.

```cpp
typedef typename allocator_type::pointer pointer;
```

### <a name="remarks"></a>Açıklamalar

Bir türü `pointer` , bir öğenin değerini değiştirmek için kullanılabilir.

Çoğu durumda, bir [Yineleyici](#iterator) multimap nesnesindeki öğelere erişmek için kullanılmalıdır.

## <a name="multimaprbegin"></a><a name="rbegin"></a> multimap:: rbegin

Ters çevrilen multimap içindeki ilk öğeyi adresleyen bir yineleyici döndürür.

```cpp
const_reverse_iterator rbegin() const;

reverse_iterator rbegin();
```

### <a name="return-value"></a>Dönüş Değeri

Ters çevrilen multimap içindeki ilk öğeyi ele almak veya geri çevrilmeyen multimap içindeki son öğe olduğunu belirlemek için ters çift yönlü Yineleyici.

### <a name="remarks"></a>Açıklamalar

`rbegin` , [BEGIN](#begin) as multimap ile birlikte kullanıldığında, ters çevrilmiş multimap ile birlikte kullanılır.

Dönüş değeri `rbegin` bir öğesine atanırsa `const_reverse_iterator` , multimap nesnesi değiştirilemez. Dönüş değeri `rbegin` bir öğesine atanırsa `reverse_iterator` , multimap nesnesi değiştirilebilir.

`rbegin` , bir çoklu eşleme ile geriye doğru yinelemek için kullanılabilir.

### <a name="example"></a>Örnek

```cpp
// multimap_rbegin.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;
   multimap <int, int> m1;

   multimap <int, int> :: iterator m1_Iter;
   multimap <int, int> :: reverse_iterator m1_rIter;
   multimap <int, int> :: const_reverse_iterator m1_crIter;
   typedef pair <int, int> Int_Pair;

   m1.insert ( Int_Pair ( 1, 10 ) );
   m1.insert ( Int_Pair ( 2, 20 ) );
   m1.insert ( Int_Pair ( 3, 30 ) );

   m1_rIter = m1.rbegin( );
   cout << "The first element of the reversed multimap m1 is "
        << m1_rIter -> first << "." << endl;

   // begin can be used to start an iteration
   // through a multimap in a forward order
   cout << "The multimap is: ";
   for ( m1_Iter = m1.begin( ) ; m1_Iter != m1.end( ); m1_Iter++)
      cout << m1_Iter -> first << " ";
      cout << "." << endl;

   // rbegin can be used to start an iteration
   // through a multimap in a reverse order
   cout << "The reversed multimap is: ";
   for ( m1_rIter = m1.rbegin( ) ; m1_rIter != m1.rend( ); m1_rIter++)
      cout << m1_rIter -> first << " ";
      cout << "." << endl;

   // A multimap element can be erased by dereferencing its key
   m1_rIter = m1.rbegin( );
   m1.erase ( m1_rIter -> first );

   m1_rIter = m1.rbegin( );
   cout << "After the erasure, the first element "
        << "in the reversed multimap is "
        << m1_rIter -> first << "." << endl;
}
```

```Output
The first element of the reversed multimap m1 is 3.
The multimap is: 1 2 3 .
The reversed multimap is: 3 2 1 .
After the erasure, the first element in the reversed multimap is 2.
```

## <a name="multimapreference"></a><a name="reference"></a> multimap:: Reference

Multimap içinde depolanan bir öğeye başvuru sağlayan bir tür.

```cpp
typedef typename allocator_type::reference reference;
```

### <a name="example"></a>Örnek

```cpp
// multimap_ref.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;
   multimap <int, int> m1;
   typedef pair <int, int> Int_Pair;

   m1.insert ( Int_Pair ( 1, 10 ) );
   m1.insert ( Int_Pair ( 2, 20 ) );

   // Declare and initialize a const_reference &Ref1
   // to the key of the first element
   const int &Ref1 = ( m1.begin( ) -> first );

   // The following line would cause an error because the
   // non-const_reference can't be used to access the key
   // int &Ref1 = ( m1.begin( ) -> first );

   cout << "The key of first element in the multimap is "
        << Ref1 << "." << endl;

   // Declare and initialize a reference &Ref2
   // to the data value of the first element
   int &Ref2 = ( m1.begin( ) -> second );

   cout << "The data value of first element in the multimap is "
        << Ref2 << "." << endl;

   // The non-const_reference can be used to modify the
   // data value of the first element
   Ref2 = Ref2 + 5;
   cout << "The modified data value of first element is "
        << Ref2 << "." << endl;
}
```

```Output
The key of first element in the multimap is 1.
The data value of first element in the multimap is 10.
The modified data value of first element is 15.
```

## <a name="multimaprend"></a><a name="rend"></a> multimap:: rend

Ters çevrilen multimap içindeki son öğeden sonra gelen konumu ele alan bir yineleyici döndürür.

```cpp
const_reverse_iterator rend() const;

reverse_iterator rend();
```

### <a name="return-value"></a>Dönüş Değeri

Ters çevrilen multimap içindeki son öğeden sonra gelen konumu ele alan ters çift yönlü yineleyici (geri çevrilmeyen multimap içindeki ilk öğeden önce gelen konum).

### <a name="remarks"></a>Açıklamalar

`rend`[End](../standard-library/map-class.md#end) , multimap ile kullanıldığı gibi ters çevrilmiş multimap ile kullanılır.

Dönüş değeri `rend` bir öğesine atanırsa `const_reverse_iterator` , multimap nesnesi değiştirilemez. Dönüş değeri `rend` bir öğesine atanırsa `reverse_iterator` , multimap nesnesi değiştirilebilir.

`rend` , bir ters yineleyicinin multimap 'in sonuna ulaşıp ulaşılmadığını test etmek için kullanılabilir.

Tarafından döndürülen değer `rend` başvurulmamalıdır.

### <a name="example"></a>Örnek

```cpp
// multimap_rend.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;
   multimap <int, int> m1;

   multimap <int, int> :: iterator m1_Iter;
   multimap <int, int> :: reverse_iterator m1_rIter;
   multimap <int, int> :: const_reverse_iterator m1_crIter;
   typedef pair <int, int> Int_Pair;

   m1.insert ( Int_Pair ( 1, 10 ) );
   m1.insert ( Int_Pair ( 2, 20 ) );
   m1.insert ( Int_Pair ( 3, 30 ) );

   m1_rIter = m1.rend( );
   m1_rIter--;
   cout << "The last element of the reversed multimap m1 is "
        << m1_rIter -> first << "." << endl;

   // begin can be used to start an iteration
   // through a multimap in a forward order
   cout << "The multimap is: ";
   for ( m1_Iter = m1.begin( ) ; m1_Iter != m1.end( ); m1_Iter++)
      cout << m1_Iter -> first << " ";
      cout << "." << endl;

   // rbegin can be used to start an iteration
   // through a multimap in a reverse order
   cout << "The reversed multimap is: ";
   for ( m1_rIter = m1.rbegin( ) ; m1_rIter != m1.rend( ); m1_rIter++)
      cout << m1_rIter -> first << " ";
      cout << "." << endl;

   // A multimap element can be erased by dereferencing to its key
   m1_rIter = --m1.rend( );
   m1.erase ( m1_rIter -> first );

   m1_rIter = m1.rend( );
   m1_rIter--;
   cout << "After the erasure, the last element "
        << "in the reversed multimap is "
        << m1_rIter -> first << "." << endl;
}
```

```Output
The last element of the reversed multimap m1 is 1.
The multimap is: 1 2 3 .
The reversed multimap is: 3 2 1 .
After the erasure, the last element in the reversed multimap is 2.
```

## <a name="multimapreverse_iterator"></a><a name="reverse_iterator"></a> multimap:: reverse_iterator

Ters çevrilen multimap içindeki bir öğeyi okuyabilen veya değiştirebilen çift yönlü bir yineleyici sağlayan bir tür.

```cpp
typedef std::reverse_iterator<iterator> reverse_iterator;
```

### <a name="remarks"></a>Açıklamalar

Bir tür, `reverse_iterator` geriye doğru multimap üzerinden yinelemek için kullanılır.

`reverse_iterator`Multimap tarafından tanımlanan [value_type](#value_type)nesnelerine işaret eder, bu tür `pair<const Key, Type>` . Anahtarın değeri, ilk üye çifti ile kullanılabilir ve eşlenmiş öğenin değeri, çiftin ikinci üyesi üzerinden kullanılabilir.

`reverse_iterator`Birden çok haritadaki bir öğeye işaret eden bir *Grup* başvurusu için **->** işlecini kullanın.

Öğesinin anahtar değerine erişmek için, `rIter->first` ile eşdeğer olan öğesini kullanın `(*rIter).first` . Öğesi için eşlenen veri değerine erişmek için, `rIter->second` ile eşdeğer olan öğesini kullanın `(*rIter).second` .

### <a name="example"></a>Örnek

Bildirme ve kullanma hakkında bir örnek için bkz. [rbegin](#rbegin) örneği `reverse_iterator` .

## <a name="multimapsize"></a><a name="size"></a> multimap:: size

Multimap içindeki öğelerin sayısını döndürür.

```cpp
size_type size() const;
```

### <a name="return-value"></a>Dönüş Değeri

Multimap 'in geçerli uzunluğu.

### <a name="example"></a>Örnek

Aşağıdaki örnek, multimap:: size üye işlevinin kullanımını gösterir.

```cpp
// multimap_size.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main()
{
    using namespace std;
    multimap<int, int> m1, m2;
    multimap<int, int>::size_type i;
    typedef pair<int, int> Int_Pair;

    m1.insert(Int_Pair(1, 1));
    i = m1.size();
    cout << "The multimap length is " << i << "." << endl;

    m1.insert(Int_Pair(2, 4));
    i = m1.size();
    cout << "The multimap length is now " << i << "." << endl;
}
```

```Output
The multimap length is 1.
The multimap length is now 2.
```

## <a name="multimapsize_type"></a><a name="size_type"></a> multimap:: size_type

Çoklu haritadaki öğelerin sayısını sayan işaretsiz bir tamsayı türü.

```cpp
typedef typename allocator_type::size_type size_type;
```

### <a name="example"></a>Örnek

Nasıl bildirilemeyeceğini ve kullanılacağına ilişkin bir örnek için [Boyut](#size) örneğine bakın `size_type`

## <a name="multimapswap"></a><a name="swap"></a> multimap:: swap

İki multimaps öğesinin öğelerini değiş tokuş eder.

```cpp
void swap(
    multimap<Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*Right*\
Takas edilecek öğeleri sağlayan multimap veya öğeleri multimap ile değiş tokuş edilecek multimap `left` .

### <a name="remarks"></a>Açıklamalar

Üye işlevi, öğeleri takas edilmekte olan iki multimaps içindeki öğeleri belirten başvuruları, işaretçileri veya yineleyicileri geçersiz kılar.

### <a name="example"></a>Örnek

```cpp
// multimap_swap.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;
   multimap <int, int> m1, m2, m3;
   multimap <int, int>::iterator m1_Iter;
   typedef pair <int, int> Int_Pair;

   m1.insert ( Int_Pair ( 1, 10 ) );
   m1.insert ( Int_Pair ( 2, 20 ) );
   m1.insert ( Int_Pair ( 3, 30 ) );
   m2.insert ( Int_Pair ( 10, 100 ) );
   m2.insert ( Int_Pair ( 20, 200 ) );
   m3.insert ( Int_Pair ( 30, 300 ) );

   cout << "The original multimap m1 is:";
   for ( m1_Iter = m1.begin( ); m1_Iter != m1.end( ); m1_Iter++ )
      cout << " " << m1_Iter -> second;
   cout   << "." << endl;

   // This is the member function version of swap
   m1.swap( m2 );

   cout << "After swapping with m2, multimap m1 is:";
   for ( m1_Iter = m1.begin( ); m1_Iter != m1.end( ); m1_Iter++ )
      cout << " " << m1_Iter -> second;
   cout  << "." << endl;

   // This is the specialized template version of swap
   swap( m1, m3 );

   cout << "After swapping with m3, multimap m1 is:";
   for ( m1_Iter = m1.begin( ); m1_Iter != m1.end( ); m1_Iter++ )
      cout << " " << m1_Iter -> second;
   cout   << "." << endl;
}
```

```Output
The original multimap m1 is: 10 20 30.
After swapping with m2, multimap m1 is: 100 200.
After swapping with m3, multimap m1 is: 300.
```

## <a name="multimapupper_bound"></a><a name="upper_bound"></a> multimap:: upper_bound

Bir yineleyiciyi belirtilen anahtardan daha büyük bir anahtara sahip olan multimap içindeki ilk öğeye döndürür.

```cpp
iterator upper_bound(const Key& key);

const_iterator upper_bound(const Key& key) const;
```

### <a name="parameters"></a>Parametreler

*anahtar*\
Aranan multimap öğesinden bir öğenin sıralama anahtarıyla Karşılaştırılacak bağımsız değişken anahtarı.

### <a name="return-value"></a>Dönüş Değeri

Bir yineleyici veya `const_iterator` bağımsız değişken anahtarından büyük bir anahtara sahip olan multimap içindeki bir öğenin konumunu adresleyen ya da anahtar için eşleşme bulunmazsa, multimap içindeki son öğeden sonra gelen konumu ele alan bir yineleyici.

Dönüş değeri bir öğesine atanırsa `const_iterator` , multimap nesnesi değiştirilemez. Dönüş değeri bir öğesine atanırsa `iterator` , multimap nesnesi değiştirilebilir.

### <a name="example"></a>Örnek

```cpp
// multimap_upper_bound.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;
   multimap <int, int> m1;
   multimap <int, int> :: const_iterator m1_AcIter, m1_RcIter;
   typedef pair <int, int> Int_Pair;

   m1.insert ( Int_Pair ( 1, 10 ) );
   m1.insert ( Int_Pair ( 2, 20 ) );
   m1.insert ( Int_Pair ( 3, 30 ) );
   m1.insert ( Int_Pair ( 3, 40 ) );

   m1_RcIter = m1.upper_bound( 1 );
   cout << "The 1st element of multimap m1 with "
        << "a key greater than 1 is: "
        << m1_RcIter -> second << "." << endl;

   m1_RcIter = m1.upper_bound( 2 );
   cout << "The first element of multimap m1 with a key "
        << " greater than 2 is: "
        << m1_RcIter -> second << "." << endl;

   // If no match is found for the key, end( ) is returned
   m1_RcIter = m1.lower_bound( 4 );

   if ( m1_RcIter == m1.end( ) )
      cout << "The multimap m1 doesn't have an element "
           << "with a key of 4." << endl;
   else
      cout << "The element of multimap m1 with a key of 4 is: "
           << m1_RcIter -> second << "." << endl;

   // The element at a specific location in the multimap can be
   // found using a dereferenced iterator addressing the location
   m1_AcIter = m1.begin( );
   m1_RcIter = m1.upper_bound( m1_AcIter -> first );
   cout << "The first element of m1 with a key greater than\n"
        << "that of the initial element of m1 is: "
        << m1_RcIter -> second << "." << endl;
}
```

```Output
The 1st element of multimap m1 with a key greater than 1 is: 20.
The first element of multimap m1 with a key  greater than 2 is: 30.
The multimap m1 doesn't have an element with a key of 4.
The first element of m1 with a key greater than
that of the initial element of m1 is: 20.
```

## <a name="multimapvalue_comp"></a><a name="value_comp"></a> multimap:: value_comp

Üye işlevi, anahtar değerlerini karşılaştırarak multimap 'teki öğelerin sırasını belirleyen bir işlev nesnesi döndürür.

```cpp
value_compare value_comp() const;
```

### <a name="return-value"></a>Dönüş Değeri

Multimap 'in öğelerini sıralamak için kullandığı karşılaştırma işlevi nesnesini döndürür.

### <a name="remarks"></a>Açıklamalar

Multimap için, *m*iki öğe *E1*(*K1*, *D1*) ve *E2*(*K2*, *D2*) türündeki nesnelerdir `value_type` ; burada *K1* ve *K2* , türü `key_type` ve *D1* ve *D2* değerlerinin `mapped_type` `m.value_comp(e1, e2)` türü `m.key_comp(k1, k2)` ,

### <a name="example"></a>Örnek

```cpp
// multimap_value_comp.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;

   multimap <int, int, less<int> > m1;
   multimap <int, int, less<int> >::value_compare vc1 = m1.value_comp( );
   multimap<int,int>::iterator Iter1, Iter2;

   Iter1= m1.insert ( multimap <int, int> :: value_type ( 1, 10 ) );
   Iter2= m1.insert ( multimap <int, int> :: value_type ( 2, 5 ) );

   if( vc1( *Iter1, *Iter2 ) == true )
   {
      cout << "The element ( 1,10 ) precedes the element ( 2,5 )."
           << endl;
   }
   else
   {
      cout << "The element ( 1,10 ) does "
           << "not precede the element ( 2,5 )."
           << endl;
   }

   if( vc1( *Iter2, *Iter1 ) == true )
   {
      cout << "The element ( 2,5 ) precedes the element ( 1,10 )."
           << endl;
   }
   else
   {
      cout << "The element ( 2,5 ) does "
           << "not precede the element ( 1,10 )."
           << endl;
   }
}
```

```Output
The element ( 1,10 ) precedes the element ( 2,5 ).
The element ( 2,5 ) does not precede the element ( 1,10 ).
```

## <a name="multimapvalue_type"></a><a name="value_type"></a> multimap:: value_type

Haritada bir öğe olarak depolanan nesne türünü temsil eden bir tür.

```cpp
typedef pair<const Key, Type> value_type;
```

### <a name="example"></a>Örnek

```cpp
// multimap_value_type.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;
   typedef pair <const int, int> cInt2Int;
   multimap <int, int> m1;
   multimap <int, int> :: key_type key1;
   multimap <int, int> :: mapped_type mapped1;
   multimap <int, int> :: value_type value1;
   multimap <int, int> :: iterator pIter;

   // value_type can be used to pass the correct type
   // explicitly to avoid implicit type conversion
   m1.insert ( multimap <int, int> :: value_type ( 1, 10 ) );

   // Compare another way to insert objects into a hash_multimap
   m1.insert ( cInt2Int ( 2, 20 ) );

   // Initializing key1 and mapped1
   key1 = ( m1.begin( ) -> first );
   mapped1 = ( m1.begin( ) -> second );

   cout << "The key of first element in the multimap is "
        << key1 << "." << endl;

   cout << "The data value of first element in the multimap is "
        << mapped1 << "." << endl;

   // The following line would cause an error because
   // the value_type is not assignable
   // value1 = cInt2Int ( 4, 40 );

   cout  << "The keys of the mapped elements are:";
   for ( pIter = m1.begin( ) ; pIter != m1.end( ) ; pIter++ )
      cout << " " << pIter -> first;
   cout << "." << endl;

   cout  << "The values of the mapped elements are:";
   for ( pIter = m1.begin( ) ; pIter != m1.end( ) ; pIter++ )
      cout << " " << pIter -> second;
   cout << "." << endl;
}
```

```Output
The key of first element in the multimap is 1.
The data value of first element in the multimap is 10.
The keys of the mapped elements are: 1 2.
The values of the mapped elements are: 10 20.
```

## <a name="see-also"></a>Ayrıca bkz.

[Kapsayıcıları](../cpp/containers-modern-cpp.md)\
[C++ standart kitaplığı 'nda iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[C++ standart kitaplığı başvurusu](../standard-library/cpp-standard-library-reference.md)
