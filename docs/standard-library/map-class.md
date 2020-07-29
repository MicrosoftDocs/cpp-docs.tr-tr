---
title: map Sınıfı
ms.date: 10/18/2018
f1_keywords:
- map/std::map
- map/std::map::allocator_type
- map/std::map::const_iterator
- map/std::map::const_pointer
- map/std::map::const_reference
- map/std::map::const_reverse_iterator
- map/std::map::difference_type
- map/std::map::iterator
- map/std::map::key_compare
- map/std::map::key_type
- map/std::map::mapped_type
- map/std::map::pointer
- map/std::map::reference
- map/std::map::reverse_iterator
- map/std::map::size_type
- map/std::map::value_type
- map/std::map::at
- map/std::map::begin
- map/std::map::cbegin
- map/std::map::cend
- map/std::map::clear
- map/std::map::count
- map/std::map::crbegin
- map/std::map::crend
- map/std::map::emplace
- map/std::map::emplace_hint
- map/std::map::empty
- map/std::map::end
- map/std::map::equal_range
- map/std::map::erase
- map/std::map::find
- map/std::map::get_allocator
- map/std::map::insert
- map/std::map::key_comp
- map/std::map::lower_bound
- map/std::map::max_size
- map/std::map::rbegin
- map/std::map::rend
- map/std::map::size
- map/std::map::swap
- map/std::map::upper_bound
- map/std::map::value_comp
helpviewer_keywords:
- std::map [C++]
- std::map [C++], allocator_type
- std::map [C++], const_iterator
- std::map [C++], const_pointer
- std::map [C++], const_reference
- std::map [C++], const_reverse_iterator
- std::map [C++], difference_type
- std::map [C++], iterator
- std::map [C++], key_compare
- std::map [C++], key_type
- std::map [C++], mapped_type
- std::map [C++], pointer
- std::map [C++], reference
- std::map [C++], reverse_iterator
- std::map [C++], size_type
- std::map [C++], value_type
- std::map [C++], at
- std::map [C++], begin
- std::map [C++], cbegin
- std::map [C++], cend
- std::map [C++], clear
- std::map [C++], count
- std::map [C++], crbegin
- std::map [C++], crend
- std::map [C++], emplace
- std::map [C++], emplace_hint
- std::map [C++], empty
- std::map [C++], end
- std::map [C++], equal_range
- std::map [C++], erase
- std::map [C++], find
- std::map [C++], get_allocator
- std::map [C++], insert
- std::map [C++], key_comp
- std::map [C++], lower_bound
- std::map [C++], max_size
- std::map [C++], rbegin
- std::map [C++], rend
- std::map [C++], size
- std::map [C++], swap
- std::map [C++], upper_bound
- std::map [C++], value_comp
ms.assetid: 7876f4c9-ebb4-4878-af1e-09364c43af0a
ms.openlocfilehash: 6166c5f1d90ab795cce39eaa1ce22f025f700d81
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87224779"
---
# <a name="map-class"></a>map Sınıfı

Her bir öğenin hem veri değerine hem de sıralama anahtarına sahip olduğu bir çift olan bir koleksiyondaki verileri alma ve depolama için kullanılır. Anahtarın değeri benzersizdir ve verileri otomatik olarak sıralamak için kullanılır.

Bir eşlemdeki bir öğenin değeri doğrudan değiştirilemez. Anahtar değeri sabittir ve değiştirilemez. Bunun yerine, eski öğelerle ilişkili anahtar değerleri silinmeli ve yeni öğeler için yeni anahtar değerleri eklenmelidir.

## <a name="syntax"></a>Söz dizimi

```cpp
template <class Key,
    class Type,
    class Traits = less<Key>,
    class Allocator=allocator<pair <const Key, Type>>>
class map;
```

### <a name="parameters"></a>Parametreler

*Anahtar*\
Eşlemde depolanacak anahtar veri türü.

*Türüyle*\
Eşlemde depolanacak öğe veri türü.

*Lerdir*\
İki öğenin değerlerini eşlemde kendi göreli sıralarını belirlemek için sıralama anahtarları olarak karşılaştırabilen bir işlev nesnesi sağlayan tür. Bu bağımsız değişken isteğe bağlıdır ve ikili koşul `less<Key>` varsayılan değerdir.

C++ 14 ' te, tür parametreleri olmayan std:: less<> koşulunu belirterek heterojen aramayı etkinleştirebilirsiniz. Daha fazla bilgi için bkz. [Ilişkilendirilebilir kapsayıcılarda heterojen arama](../standard-library/stl-containers.md#sequence_containers)

*Öğe*\
Eşlemin bellek ayırmayı ve ayırmayı kaldırma hakkındaki ayrıntıları içeren saklı ayırıcı nesnesini gösteren tür. Bu bağımsız değişken isteğe bağlıdır ve varsayılan değerdir `allocator<pair<const Key, Type> >` .

## <a name="remarks"></a>Açıklamalar

C++ standart kitaplık eşleme sınıfı:

- Öğe değerlerini etkin olarak alan değişken boyutunun bir kapsayıcısı ilişkili anahtar değerlerine dayalıdır.

- Çift yönlüdür, çünkü öğelerine erişmek için çift yönlü yineleyiciler sağlar.

- Sıralıdır, çünkü öğeleri belirtilen karşılaştırma işlevine uygun olarak anahtar değerlere göre sıralanır.

- Eşi. Her bir öğesi benzersiz bir anahtara sahip olmalıdır.

- Bir çift ilişkilendirilebilir kapsayıcıdır, çünkü veri öğelerinin değerleri kendi anahtar değerlerinden farklıdır.

- Bir sınıf şablonu, sağladığı işlev genel ve öğe veya anahtar türünden bağımsızdır. Öğeler ve anahtarlar için kullanılan veri türleri, karşılaştırma işlevi ve ayırıcı ile birlikte bir sınıf şablonunda parametreler olarak belirtilir.

Map sınıfı tarafından verilen yineleyici çift yönlü bir yineleyicidir, ancak [Insert](#insert) ve [map](#map) sınıf üyesi işlevleri, şablon parametresi olarak daha zayıf bir giriş yineleyicisini alan, işlevsellik gereksinimleri çift yönlü yineleyicilerin sınıfının garantiden daha az olan sürümlere sahiptir. Farklı yineleyici kavramları, işlevselliklerindeki iyileştirmelerle ilgilidir. Her yineleyici kavramı kendi gereksinimler kümesine sahiptir ve onunla çalışan algoritmalar bu gereksinimler ile sınırlı olmalıdır. Bir giriş yineleyicinin bazı nesnelere başvurusu kaldırılabilir ve dizideki sonraki yineleyiciye artırılabilir.

Kapsayıcı türünün seçimini uygulamanın gerektirdiği arama ve ekleme türüne dayalı yapmanız önerilir. İlişkilendirilebilir kapsayıcılar, arama, ekleme ve kaldırma işlemleri için en iyi duruma getirilir. Bu işlemleri açıkça destekleyen üye işlevleri, işlevlerini kapsayıcıdaki öğelerin sayısının logaritmasına ortalama orantılı en kötü sürede gerçekleştirir. Öğelerin eklenmesi hiçbir yineleyiciyi geçersiz kılmaz; öğelerin kaldırılması yalnızca özellikle kaldırılan öğeleri gösteren yineleyicileri geçersiz kılar.

Eşlemi, değerleri anahtarlarıyla ilişkilendiren koşullar uygulama tarafından karşılandığında seçimin ilişkili kapsayıcısı yapmanız önerilir. Bu tür bir yapı modeli, tanımlar sağlayan ilişkilendirmiş dize değerlerine sahip benzersiz oluşan anahtar sözcüklerin sıralı bir listesidir. Bir sözcüğün birden fazla doğru tanımı varsa, anahtar benzersiz olmadığından, çoklu eşlem kapsayıcı seçimi olacaktır. Yalnızca sözcüklerin listesi depolanmaktaysa, uygun kapsayıcı bir küme olacaktır. Sözcüklerin birden çok defa geçmelerine izin verilirse, bir çoklu küme uygun olacaktır.

Map, [key_compare](#key_compare)türünde bir saklı işlev nesnesi çağırarak denetlediği öğeleri sıralar. Bu saklı nesne, [key_comp](#key_comp) metodu çağırarak erişilen bir karşılaştırma işlevidir. Genelde, verilen herhangi iki öğe, birinin diğerinden daha küçük olup olmadığının veya denk olup olmadıklarının belirlenmesi için karşılaştırılır. Tüm öğeler karşılaştırıldığında, denk olmayan öğelerin sıralı bir dizisi oluşturulur.

> [!NOTE]
> Karşılaştırma işlevi standart matematiksel anlamda katı bir zayıf sıralama sevk eden ikili bir koşuldur. Bir ikili koşul f (x, y) iki bağımsız değişken nesnesi olan x ve y ve dönüş değeri olan bir işlev nesnesidir **`true`** **`false`** . İkili koşul geri dönüşsüz, antisimetrik ve geçişli ise ve denklik geçişli ise, küme üzerinde yer alan bir sıralama katı zayıf bir sıradır. burada iki nesne x ve y, her ikisi de f (x, y) ve f (y, x) olduğunda eşdeğer olarak tanımlanmıştır **`false`** . Anahtarlar arasındaki eşitliğinin daha güçlü koşulu bu denkliğin yerini alırsa, sıralama (içindeki tüm öğelerin birbirine göre sıralanması anlamında) toplam haline gelir ve eşleşen anahtarlar birbirinden ayırt edilemez olacaktır.
>
> C++ 14 ' te, `std::less<>` hiçbir tür parametresi olmayan veya koşulunu belirterek heterojen aramayı etkinleştirebilirsiniz `std::greater<>` . Daha fazla bilgi için bkz. [Ilişkilendirilebilir kapsayıcılarda heterojen arama](../standard-library/stl-containers.md#sequence_containers)

## <a name="members"></a>Üyeler

### <a name="constructors"></a>Oluşturucular

|||
|-|-|
|[harita](#map)|Belirli bir boyutun veya belirli bir değerin veya belirli bir eşlemenin kopyası olan öğelerin bir listesini oluşturur `allocator` .|

### <a name="typedefs"></a>Tür tanımları

|||
|-|-|
|[allocator_type](#allocator_type)|`allocator`Map nesnesinin sınıfı için bir typedef.|
|[const_iterator](#const_iterator)|Eşlemedeki bir öğeyi okuyabilen çift yönlü Yineleyici için bir typedef **`const`** .|
|[const_pointer](#const_pointer)|Haritada bir öğe işaretçisi için bir typedef **`const`** .|
|[const_reference](#const_reference)|**`const`** İşlemleri okumak ve gerçekleştirmek için bir haritada depolanan öğeye başvuru için bir typedef **`const`** .|
|[const_reverse_iterator](#const_reverse_iterator)|Haritadaki herhangi bir öğeyi okuyabilen çift yönlü bir yineleyici sağlayan bir tür **`const`** .|
|[difference_type](#difference_type)|Yineleyiciler tarafından gösterilen öğeler arasındaki bir aralıktaki eşlemin öğelerinin işaretli bir tamsayı typedef'i.|
|[iden](#iterator)|Eşlem içindeki herhangi bir öğeyi okuyabilen veya değiştirebilen çift yönlü yineleyiciler için typedef.|
|[key_compare](#key_compare)|Eşlem içindeki iki öğenin göreli sırasını belirlemek için iki sıralama anahtarını karşılaştıran işlev nesnesi için bir typedef.|
|[key_type](#key_type)|Eşlemin her öğesinde depolanan sıralama anahtarı için bir typedef.|
|[mapped_type](#mapped_type)|Bir eşlemin her öğesinde depolanan veriler için bir typedef.|
|[pointer](#pointer)|Haritada bir öğe işaretçisi için bir typedef **`const`** .|
|[başvurunun](#reference)|Bir eşlem içinde depolan bir öğeye başvuru için bir typedef.|
|[reverse_iterator](#reverse_iterator)|Ters döndürülmüş eşlem içindeki bir öğeyi okuyabilen veya değiştirebilen çift yönlü yineleyiciler için typedef.|
|[size_type](#size_type)|Bir eşlemdeki öğe sayısı için işaretsiz tamsayı typedef'i.|
|[value_type](#value_type)|Bir eşlem içinde bir öğe olarak depolanan nesne türü için bir typedef.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[hızı](#at)|Belirtilen anahtar değere sahip bir öğe bulur.|
|[başladı](#begin)|Eşlem içindeki ilk öğeyi gösteren bir yineleyici döndürür.|
|[cbegin](#cbegin)|Eşlem içindeki ilk öğeyi gösteren sabit bir yineleyici döndürür.|
|[cend](#cend)|Bir sabit past-the-end yineleyici döndürür.|
|[lediğiniz](#clear)|Eşlemin tüm öğelerini siler.|
|[biriktirme](#count)|Anahtarı bir parametre içinde belirtilen anahtarla eşleşen eşlem içindeki öğelerin sayısını döndürür.|
|[crbegin](#crbegin)|Ters döndürülmüş bir eşlem içindeki ilk öğeyi gösteren sabit bir yineleyici döndürür.|
|[crend](#crend)|Ters döndürülmüş bir eşlem içindeki son öğenin ardındaki konumu gösteren sabit bir yineleyici döndürür.|
|[Emplace](#emplace)|Eşlem içine yerinde oluşturulmuş bir öğe ekler.|
|[emplace_hint](#emplace_hint)|Eşlem içine, bir yerleşim ipucuyla birlikte yerinde oluşturulmuş bir öğe ekler.|
|[empty](#empty)|**`true`** Bir haritanın boş olup olmadığını döndürür.|
|[erer](#end)|past-the-end yineleyici döndürür.|
|[equal_range](#equal_range)|Yineleyicilerin bir çiftini döndürür. Çiftin ilk yineleyicisi, belirtilen anahtardan daha büyük olan bir anahtarla ilk öğesine işaret eder `map` . Çiftin ikinci yineleyicisi, `map` anahtarına eşit veya ondan daha büyük olan bir anahtarla ilk öğesine işaret eder.|
|[silme](#erase)|Bir eşlemdeki bir öğe veya öğe aralığını belirtilen konumdan kaldırır.|
|[find](#find)|Belirtilen anahtara eşit bir anahtara sahip bir eşlem içindeki bir öğenin konumunu gösteren bir yineleyici döndürür.|
|[get_allocator](#get_allocator)|`allocator`Haritayı oluşturmak için kullanılan nesnenin bir kopyasını döndürür.|
|[ekleyin](#insert)|Bir eşlemdeki bir öğeyi veya öğe aralığını belirtilen konumda ekler.|
|[key_comp](#key_comp)|Bir eşlem içindeki anahtarları sıralamak için kullanılan karşılaştırma nesnesinin bir kopyasını döndürür.|
|[lower_bound](#lower_bound)|Bir yineleyiciyi belirtilen anahtardan daha büyük veya ona eşit bir anahtar değere sahip bir eşlem içindeki ilk öğeye döndürür.|
|[max_size](#max_size)|Eşlem öğesinin maksimum uzunluğunu döndürür.|
|[rbegin](#rbegin)|Ters döndürülmüş eşlem içindeki ilk öğeyi gösteren bir yineleyici döndürür.|
|[rend](#rend)|Ters döndürülmüş bir eşlem içindeki son öğenin ardındaki konumu gösteren bir yineleyici döndürür.|
|[boyutla](#size)|Eşlem içindeki öğelerin sayısını döndürür.|
|[Kur](#swap)|İki eşlemin öğelerini birbiriyle değiştirir.|
|[upper_bound](#upper_bound)|Bir yineleyiciyi belirtilen anahtardan daha büyükse bir anahtar değere sahip bir eşlem içindeki ilk öğeye döndürür.|
|[value_comp](#value_comp)|Bir eşlem içindeki öğe değerlerini sıralamak için kullanılan karşılaştırma nesnesinin bir kopyasını alır.|

### <a name="operators"></a>İşleçler

|||
|-|-|
|[işleç&#91;&#93;](#op_at)|Belirtilen bir anahtar değere sahip bir eşleme bir öğe ekler.|
|[işleç =](#op_eq)|Bir eşlemin öğelerini başka bir eşlem kopyasıyla değiştirir.|

## <a name="allocator_type"></a><a name="allocator_type"></a>allocator_type

Map nesnesinin ayırıcı sınıfını temsil eden bir tür.

```cpp
typedef Allocator allocator_type;
```

### <a name="example"></a>Örnek

Tarafından kullanılan bir örnek için bkz. [get_allocator](#get_allocator) örneği `allocator_type` .

## <a name="at"></a><a name="at"></a>hızı

Belirtilen anahtar değere sahip bir öğe bulur.

```cpp
Type& at(const Key& key);

const Type& at(const Key& key) const;
```

### <a name="parameters"></a>Parametreler

anahtar * \
Bulunacak anahtar değeri.

### <a name="return-value"></a>Dönüş Değeri

Bulunan öğenin veri değerine başvuru.

### <a name="remarks"></a>Açıklamalar

Bağımsız değişken anahtar değeri bulunamazsa, işlev sınıf [Out_of_range sınıfından](../standard-library/out-of-range-class.md)bir nesne oluşturur.

### <a name="example"></a>Örnek

```cpp
// map_at.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

typedef std::map<char, int> Mymap;
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

## <a name="begin"></a><a name="begin"></a>başladı

Eşlemedeki ilk öğeyi adresleyen bir yineleyici döndürür.

```cpp
const_iterator begin() const;

iterator begin();
```

### <a name="return-value"></a>Dönüş Değeri

Haritadaki ilk öğeyi ele alarak çift yönlü bir yineleyici veya boş bir eşlemeyi izleyen konum.

### <a name="example"></a>Örnek

```cpp
// map_begin.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;
   map <int, int> m1;

   map <int, int> :: iterator m1_Iter;
   map <int, int> :: const_iterator m1_cIter;
   typedef pair <int, int> Int_Pair;

   m1.insert ( Int_Pair ( 0, 0 ) );
   m1.insert ( Int_Pair ( 1, 1 ) );
   m1.insert ( Int_Pair ( 2, 4 ) );

   m1_cIter = m1.begin ( );
   cout << "The first element of m1 is " << m1_cIter -> first << endl;

   m1_Iter = m1.begin ( );
   m1.erase ( m1_Iter );

   // The following 2 lines would err because the iterator is const
   // m1_cIter = m1.begin ( );
   // m1.erase ( m1_cIter );

   m1_cIter = m1.begin( );
   cout << "The first element of m1 is now " << m1_cIter -> first << endl;
}
```

```Output
The first element of m1 is 0
The first element of m1 is now 1
```

## <a name="cbegin"></a><a name="cbegin"></a>cbegin

**`const`** Bir aralıktaki son öğenin ötesinde konumu ele alan bir yineleyici döndürür.

```cpp
const_iterator cbegin() const;
```

### <a name="return-value"></a>Dönüş Değeri

**`const`** Aralıktaki ilk öğeyi veya boş aralığın sonundaki konumu (boş bir Aralık için) geçen çift yönlü bir yineleyici `cbegin() == cend()` .

### <a name="remarks"></a>Açıklamalar

Dönüş değeri ile `cbegin` , aralıktaki öğeler değiştirilemez.

`begin()`Dönüş değerinin olduğunu garantilemek için üye işlevin yerine bu üye işlevi kullanabilirsiniz `const_iterator` . Genellikle, aşağıdaki örnekte gösterildiği gibi [Otomatik](../cpp/auto-cpp.md) tür kesintisi anahtar sözcüğüyle birlikte kullanılır. Örnekte, ve ' ı `Container` destekleyen herhangi bir türde değiştirilebilir (olmayan) bir kapsayıcı olarak göz önünde bulundurun **`const`** `begin()` `cbegin()` .

```cpp
auto i1 = Container.begin();
// i1 is Container<T>::iterator
auto i2 = Container.cbegin();

// i2 is Container<T>::const_iterator
```

## <a name="cend"></a><a name="cend"></a>cend

**`const`** Bir aralıktaki son öğenin ötesinde konumu ele alan bir yineleyici döndürür.

```cpp
const_iterator cend() const;
```

### <a name="return-value"></a>Dönüş Değeri

**`const`** Yalnızca aralığın sonunu işaret eden çift yönlü erişim yineleyicisi.

### <a name="remarks"></a>Açıklamalar

`cend`, bir yineleyicinin aralığın sonunu geçtiğini test etmek için kullanılır.

`end()`Dönüş değerinin olduğunu garantilemek için üye işlevin yerine bu üye işlevi kullanabilirsiniz `const_iterator` . Genellikle, aşağıdaki örnekte gösterildiği gibi [Otomatik](../cpp/auto-cpp.md) tür kesintisi anahtar sözcüğüyle birlikte kullanılır. Örnekte, ve ' ı `Container` destekleyen herhangi bir türde değiştirilebilir (olmayan) bir kapsayıcı olarak göz önünde bulundurun **`const`** `end()` `cend()` .

```cpp
auto i1 = Container.end();
// i1 is Container<T>::iterator
auto i2 = Container.cend();

// i2 is Container<T>::const_iterator
```

Tarafından döndürülen değer `cend` başvurulmamalıdır.

## <a name="clear"></a><a name="clear"></a>lediğiniz

Eşlemin tüm öğelerini siler.

```cpp
void clear();
```

### <a name="example"></a>Örnek

Aşağıdaki örnek, map:: Clear üye işlevinin kullanımını gösterir.

```cpp
// map_clear.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main()
{
    using namespace std;
    map<int, int> m1;
    map<int, int>::size_type i;
    typedef pair<int, int> Int_Pair;

    m1.insert(Int_Pair(1, 1));
    m1.insert(Int_Pair(2, 4));

    i = m1.size();
    cout << "The size of the map is initially "
         << i << "." << endl;

    m1.clear();
    i = m1.size();
    cout << "The size of the map after clearing is "
         << i << "." << endl;
}
```

```Output
The size of the map is initially 2.
The size of the map after clearing is 0.
```

## <a name="const_iterator"></a><a name="const_iterator"></a>const_iterator

Haritadaki bir öğeyi okuyabilen çift yönlü bir yineleyici sağlayan bir tür **`const`** .

```cpp
typedef implementation-defined const_iterator;
```

### <a name="remarks"></a>Açıklamalar

Bir tür `const_iterator` , bir öğenin değerini değiştirmek için kullanılamaz.

`const_iterator`Tarafından tanımlanan eşleme, [value_type](#value_type) `pair` \< **constKey**, **Type**> ilk üyesi öğe için anahtar olan ve ikinci üye öğesi tarafından tutulan eşlenmiş veri olan, türü value_type nesneler olan öğeleri gösterir.

Bir `const_iterator` `cIter` haritadaki bir öğeye işaret başvurusu yapmak için `->` işlecini kullanın.

Öğesinin anahtar değerine erişmek için, `cIter`  ->  () ile eşdeğer olan **ilk**öğesini kullanın \* `cIter` . **ilk**olarak.

Öğesi için eşlenen veri değerine erişmek için, `cIter`  ->  () eşdeğeri olan **ikincisini**kullanın \* `cIter` . **ikinci**.

### <a name="example"></a>Örnek

Tarafından kullanılan bir [örnek için bkz](#begin) `const_iterator` . örnek.

## <a name="const_pointer"></a><a name="const_pointer"></a>const_pointer

Haritada bir öğeye işaretçi sağlayan bir tür **`const`** .

```cpp
typedef typename allocator_type::const_pointer const_pointer;
```

### <a name="remarks"></a>Açıklamalar

Bir tür `const_pointer` , bir öğenin değerini değiştirmek için kullanılamaz.

Çoğu durumda, bir [Yineleyici](#iterator) bir eşleme nesnesindeki öğelere erişmek için kullanılmalıdır.

## <a name="const_reference"></a><a name="const_reference"></a>const_reference

**`const`** İşlemleri okumak ve gerçekleştirmek için bir haritada depolanan öğeye başvuru sağlayan bir tür **`const`** .

```cpp
typedef typename allocator_type::const_reference const_reference;
```

### <a name="example"></a>Örnek

```cpp
// map_const_ref.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;
   map <int, int> m1;
   typedef pair <int, int> Int_Pair;

   m1.insert ( Int_Pair ( 1, 10 ) );
   m1.insert ( Int_Pair ( 2, 20 ) );

   // Declare and initialize a const_reference &Ref1
   // to the key of the first element
   const int &Ref1 = ( m1.begin( ) -> first );

   // The following line would cause an error as the
   // non-const_reference cannot be used to access the key
   // int &Ref1 = ( m1.begin( ) -> first );

   cout << "The key of first element in the map is "
        << Ref1 << "." << endl;

   // Declare and initialize a reference &Ref2
   // to the data value of the first element
   int &Ref2 = ( m1.begin( ) -> second );

   cout << "The data value of first element in the map is "
        << Ref2 << "." << endl;
}
```

```Output
The key of first element in the map is 1.
The data value of first element in the map is 10.
```

## <a name="const_reverse_iterator"></a><a name="const_reverse_iterator"></a>const_reverse_iterator

Haritadaki herhangi bir öğeyi okuyabilen çift yönlü bir yineleyici sağlayan bir tür **`const`** .

```cpp
typedef std::reverse_iterator<const_iterator> const_reverse_iterator;
```

### <a name="remarks"></a>Açıklamalar

Bir tür `const_reverse_iterator` , bir öğenin değerini değiştiremez ve eşleme boyunca ters yönde yinelemek için kullanılır.

`const_reverse_iterator`Tarafından tanımlanan eşleme, [value_type](#value_type) `pair<const Key, Type>` ilk üyesi öğe için anahtar olan ve ikinci üye öğesi tarafından tutulan eşlenmiş veri olan, türü value_type nesneler olan öğeleri gösterir.

Bir `const_reverse_iterator crIter` haritadaki bir öğeye işaret başvurusu yapmak için `->` işlecini kullanın.

Öğesinin anahtar değerine erişmek için, `crIter`  ->  () ile eşdeğer olan **ilk**öğesini kullanın \* `crIter` .** ilk**olarak.

Öğesi için eşlenen veri değerine erişmek için, `crIter`  ->  () eşdeğeri olan **ikincisini**kullanın \* `crIter` .** ilk**olarak.

### <a name="example"></a>Örnek

Bildirme ve kullanma hakkında bir örnek için bkz. [rend](#rend) örneği `const_reverse_iterator` .

## <a name="count"></a><a name="count"></a>biriktirme

Anahtarı parametre tarafından belirtilen anahtarla eşleşen bir haritadaki öğe sayısını döndürür.

```cpp
size_type count(const Key& key) const;
```

### <a name="parameters"></a>Parametreler

*anahtar*\
Eşlemden eşleştirilecek öğelerin anahtar değeri.

### <a name="return-value"></a>Dönüş Değeri

eşleme sıralama anahtarı parametre anahtarıyla eşleşen bir öğe içeriyorsa 1; Haritada eşleşen bir anahtara sahip bir öğe yoksa 0.

### <a name="remarks"></a>Açıklamalar

Üye işlevi aralıktaki *x* öğelerinin sayısını döndürür

\[lower_bound (*anahtar*), upper_bound (*anahtar*))

Bu, benzersiz bir ilişkilendirilebilir kapsayıcı olan eşleme durumunda 0 veya 1 ' dir.

### <a name="example"></a>Örnek

Aşağıdaki örnek, map:: Count üye işlevinin kullanımını gösterir.

```cpp
// map_count.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main()
{
    using namespace std;
    map<int, int> m1;
    map<int, int>::size_type i;
    typedef pair<int, int> Int_Pair;

    m1.insert(Int_Pair(1, 1));
    m1.insert(Int_Pair(2, 1));
    m1.insert(Int_Pair(1, 4));
    m1.insert(Int_Pair(2, 1));

    // Keys must be unique in map, so duplicates are ignored
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
The number of elements in m1 with a sort key of 1 is: 1.
The number of elements in m1 with a sort key of 2 is: 1.
The number of elements in m1 with a sort key of 3 is: 0.
```

## <a name="crbegin"></a><a name="crbegin"></a>crbegin

Ters çevrilen eşlemedeki ilk öğeyi adresleyen bir const yineleyici döndürür.

```cpp
const_reverse_iterator crbegin() const;
```

### <a name="return-value"></a>Dönüş Değeri

Ters çevrilen bir [haritadaki](../standard-library/map-class.md) ilk öğeyi ele almak veya geri çevrilmede son öğe olduğunu ele almak için bir sabit ters çift yönlü Yineleyici `map` .

### <a name="remarks"></a>Açıklamalar

`crbegin`, `map` ile birlikte [Başlangıç](#begin) ile kullanılır `map` .

Dönüş değeri ile `crbegin` `map` nesne değiştirilemez

`crbegin`, geriye doğru yinelemek için kullanılabilir `map` .

### <a name="example"></a>Örnek

```cpp
// map_crbegin.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;
   map <int, int> m1;

   map <int, int> :: const_reverse_iterator m1_crIter;
   typedef pair <int, int> Int_Pair;

   m1.insert ( Int_Pair ( 1, 10 ) );
   m1.insert ( Int_Pair ( 2, 20 ) );
   m1.insert ( Int_Pair ( 3, 30 ) );

   m1_crIter = m1.crbegin( );
   cout << "The first element of the reversed map m1 is "
        << m1_crIter -> first << "." << endl;
}
```

```Output
The first element of the reversed map m1 is 3.
```

## <a name="crend"></a><a name="crend"></a>crend

Tersine çevrilmiş eşlemedeki son öğeden sonraki konumu adresleyen bir const yineleyici döndürür.

```cpp
const_reverse_iterator crend() const;
```

### <a name="return-value"></a>Dönüş Değeri

Ters çevrilen bir [haritadaki](../standard-library/map-class.md) son öğeden sonra gelen konumu ele alan bir sabit ters çift yönlü yineleyici (geri çevrilmede ilk öğeden önce gelen konum `map` ).

### <a name="remarks"></a>Açıklamalar

`crend`, [End](#end) ile birlikte kullanıldığı gibi tersine çevrilmiş bir eşleme ile kullanılır `map` .

Dönüş değeri ile `crend` `map` nesne değiştirilemez.

`crend`, geriye doğru bir yineleyicinin sonuna ulaşılıp ulaşılmadığını test etmek için kullanılabilir `map` .

Tarafından döndürülen değer `crend` başvurulmamalıdır.

### <a name="example"></a>Örnek

```cpp
// map_crend.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;
   map <int, int> m1;

   map <int, int> :: const_reverse_iterator m1_crIter;
   typedef pair <int, int> Int_Pair;

   m1.insert ( Int_Pair ( 1, 10 ) );
   m1.insert ( Int_Pair ( 2, 20 ) );
   m1.insert ( Int_Pair ( 3, 30 ) );

   m1_crIter = m1.crend( );
   m1_crIter--;
   cout << "The last element of the reversed map m1 is "
        << m1_crIter -> first << "." << endl;
}
```

```Output
The last element of the reversed map m1 is 1.
```

## <a name="difference_type"></a><a name="difference_type"></a>difference_type

Yineleyiciler tarafından gösterilen öğeler arasındaki bir aralıktaki bir haritanın öğelerinin sayısını temsil etmek için kullanılabilen işaretli bir tamsayı türü.

```cpp
typedef allocator_type::difference_type difference_type;
```

### <a name="remarks"></a>Açıklamalar

`difference_type`Kapsayıcının yineleyiciler aracılığıyla çıkartılacak veya artırılarak döndürülen türdür. `difference_type`Genellikle yineleyiciler arasındaki *[ilk, son)* aralıktaki öğelerin sayısını temsil etmek için kullanılır ve tarafından işaret edilen öğe `first` `last` `first` ve dahil olmak üzere öğe aralığı ile işaret eder `last` .

`difference_type`Küme gibi ters çevrilebilir kapsayıcılar tarafından desteklenen çift yönlü yineleyicilerin sınıfını içeren bir giriş yineleyicisinin gereksinimlerini karşılayan tüm yineleyiciler için kullanılabilir olsa da, yineleyiciler arasında çıkarma yalnızca vektör gibi bir rastgele erişim kapsayıcısı tarafından sağlanan rastgele erişim yineleyiciler tarafından desteklenir.

### <a name="example"></a>Örnek

```cpp
// map_diff_type.cpp
// compile with: /EHsc
#include <iostream>
#include <map>
#include <algorithm>

int main( )
{
   using namespace std;
   map <int, int> m1;
   typedef pair <int, int> Int_Pair;

   m1.insert ( Int_Pair ( 2, 20 ) );
   m1.insert ( Int_Pair ( 1, 10 ) );
   m1.insert ( Int_Pair ( 3, 20 ) );
   m1.insert ( Int_Pair ( 2, 30 ) );

   map <int, int>::iterator m1_Iter, m1_bIter, m1_eIter;
   m1_bIter = m1.begin( );
   m1_eIter = m1.end( );

   // Count the number of elements in a map
   map <int, int>::difference_type  df_count = 1;
   m1_Iter = m1.begin( );
   while ( m1_Iter != m1_eIter)
   {
      df_count++;
      m1_Iter++;
   }

   cout << "The number of elements in the map m1 is: "
        << df_count << "." << endl;
}
```

```Output
The number of elements in the map m1 is: 4.
```

## <a name="emplace"></a><a name="emplace"></a>Emplace

Bir haritaya oluşturulmuş bir öğe ekler (kopyalama veya taşıma işlemleri yapılmaz).

```cpp
template <class... Args>
pair<iterator, bool>
emplace(
    Args&&... args);
```

### <a name="parameters"></a>Parametreler

*args*\
Değeri equivalently sıralı olan bir öğe içermiyorsa, haritaya eklenecek bir öğe oluşturmak için iletilen bağımsız değişkenler.

### <a name="return-value"></a>Dönüş Değeri

[pair](../standard-library/pair-structure.md) **`bool`** Bir ekleme yapılırsa bileşeni doğru olan bir çift ve eşleme, sıralamada zaten denk değer olan bir öğe içeriyorsa false. Return-Value çiftinin yineleyici bileşeni, bileşen true ise yeni ınsertedelement öğesine **`bool`** veya bileşen false ise var olan öğeye işaret eder **`bool`** .

' A ait Yineleyici bileşenine erişmek için `pair` `pr` , öğesini kullanın `pr.first` ; başvuru yapmak için kullanın `*pr.first` . Bileşene erişmek için **`bool`** kullanın `pr.second` . Örnek için, bu makalenin ilerleyen kısımlarında örnek koda bakın.

### <a name="remarks"></a>Açıklamalar

Bu işlev tarafından hiçbir yineleyiciler veya başvuru geçersiz kılınmamıştır.

Emplamak sırasında, bir özel durum oluşturulursa kapsayıcının durumu değiştirilmez.

Bir öğe [value_type](#value_type) bir çifdir, böylece bir öğe değeri, ilk bileşeni anahtar değerine eşit olan ve ikinci bileşen öğenin veri değerine eşit olan bir sıralı çift olacaktır.

### <a name="example"></a>Örnek

```cpp
// map_emplace.cpp
// compile with: /EHsc
#include <map>
#include <string>
#include <iostream>

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
    map<int, string> m1;

    auto ret = m1.emplace(10, "ten");

    if (!ret.second){
        auto pr = *ret.first;
        cout << "Emplace failed, element with key 10 already exists."
            << endl << "  The existing element is (" << pr.first << ", " << pr.second << ")"
            << endl;
        cout << "map not modified" << endl;
    }
    else{
        cout << "map modified, now contains ";
        print(m1);
    }
    cout << endl;

    ret = m1.emplace(10, "one zero");

    if (!ret.second){
        auto pr = *ret.first;
        cout << "Emplace failed, element with key 10 already exists."
            << endl << "  The existing element is (" << pr.first << ", " << pr.second << ")"
            << endl;
    }
    else{
        cout << "map modified, now contains ";
        print(m1);
    }
    cout << endl;
}
```

## <a name="emplace_hint"></a><a name="emplace_hint"></a>emplace_hint

Yerinde oluşturulmuş bir öğe ekler (kopyalama veya taşıma işlemleri yapılmaz), yerleştirme ipucuyla birlikte.

```cpp
template <class... Args>
iterator emplace_hint(
    const_iterator where,
    Args&&... args);
```

### <a name="parameters"></a>Parametreler

*args*\
Zaten anahtar equivalently sıralı bir öğe içermiyorsa, eşleme zaten bu öğeyi veya daha genel olarak içermiyorsa, haritaya eklenecek bir öğe oluşturmak için iletilen bağımsız değişkenler.

*olmadığı*\
Doğru ekleme noktasını aramaya başlamak için yer. (Bu nokta hemen bundan önce geliyorsa, ekleme, logaritmik bir süre yerine, sabit *zamanlı olarak gerçekleşebilir*.)

### <a name="return-value"></a>Dönüş Değeri

Yeni eklenmekte olan öğe için bir yineleyici.

Öğe zaten mevcut olduğundan ekleme başarısız olursa, var olan öğeye anahtarı ile bir yineleyici döndürür.

### <a name="remarks"></a>Açıklamalar

Bu işlev tarafından hiçbir yineleyiciler veya başvuru geçersiz kılınmamıştır.

Emplamak sırasında, bir özel durum oluşturulursa kapsayıcının durumu değiştirilmez.

Bir öğe [value_type](#value_type) bir çifdir, böylece bir öğe değeri, ilk bileşeni anahtar değerine eşit olan ve ikinci bileşen öğenin veri değerine eşit olan bir sıralı çift olacaktır.

### <a name="example"></a>Örnek

```cpp
// map_emplace.cpp
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
    map<string, string> m1;

    // Emplace some test data
    m1.emplace("Anna", "Accounting");
    m1.emplace("Bob", "Accounting");
    m1.emplace("Carmine", "Engineering");

    cout << "map starting data: ";
    print(m1);
    cout << endl;

    // Emplace with hint
    // m1.end() should be the "next" element after this emplacement
    m1.emplace_hint(m1.end(), "Doug", "Engineering");

    cout << "map modified, now contains ";
    print(m1);
    cout << endl;
}
```

## <a name="empty"></a><a name="empty"></a>olmamalıdır

Bir haritanın boş olup olmadığını sınar.

```cpp
bool empty() const;
```

### <a name="return-value"></a>Dönüş Değeri

**`true`** eşleme boşsa; **`false`** eşleme boş değilse.

### <a name="example"></a>Örnek

```cpp
// map_empty.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;
   map <int, int> m1, m2;

   typedef pair <int, int> Int_Pair;
   m1.insert ( Int_Pair ( 1, 1 ) );

   if ( m1.empty( ) )
      cout << "The map m1 is empty." << endl;
   else
      cout << "The map m1 is not empty." << endl;

   if ( m2.empty( ) )
      cout << "The map m2 is empty." << endl;
   else
      cout << "The map m2 is not empty." << endl;
}
```

```Output
The map m1 is not empty.
The map m2 is empty.
```

## <a name="end"></a><a name="end"></a>erer

past-the-end yineleyici döndürür.

```cpp
const_iterator end() const;

iterator end();
```

### <a name="return-value"></a>Dönüş Değeri

Son uca Yineleyici. Eşleme boşsa, `map::end() == map::begin()` .

### <a name="remarks"></a>Açıklamalar

`end`, bir yineleyicinin haritanın sonunu geçtiğini test etmek için kullanılır.

Tarafından döndürülen değer `end` başvurulmamalıdır.

Kod örneği için bkz. [map:: Find](#find).

## <a name="equal_range"></a><a name="equal_range"></a>equal_range

Anahtarın [lower_bound](#lower_bound) ve anahtarın [upper_bound](#upper_bound) temsil eden yineleyicilerin bir çiftini döndürür.

```cpp
pair <const_iterator, const_iterator> equal_range (const Key& key) const;

pair <iterator, iterator> equal_range (const Key& key);
```

### <a name="parameters"></a>Parametreler

*anahtar*\
Aranmakta olan eşlemdeki bir öğenin sıralama anahtarıyla Karşılaştırılacak bağımsız değişken anahtar değeri.

### <a name="return-value"></a>Dönüş Değeri

Üye işlevi tarafından döndürülen bir çiftin ilk Yineleyici öğesine erişmek için `pr` kullanın `pr` . **ilk**olarak, alt sınır Yineleyici için başvuru yapmak üzere \* ( `pr` . **ilk**). Üye işlevi tarafından döndürülen bir çiftin ikinci Yineleyici öğesine erişmek için `pr` kullanın `pr` . **ikincisi**ve üst sınır yineleyicisini başvuru yapmak için \* ( `pr` . **ikinci**).

### <a name="example"></a>Örnek

```cpp
// map_equal_range.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;
   typedef map <int, int, less<int> > IntMap;
   IntMap m1;
   map <int, int> :: const_iterator m1_RcIter;
   typedef pair <int, int> Int_Pair;

   m1.insert ( Int_Pair ( 1, 10 ) );
   m1.insert ( Int_Pair ( 2, 20 ) );
   m1.insert ( Int_Pair ( 3, 30 ) );

   pair <IntMap::const_iterator, IntMap::const_iterator> p1, p2;
   p1 = m1.equal_range( 2 );

   cout << "The lower bound of the element with "
        << "a key of 2 in the map m1 is: "
        << p1.first -> second << "." << endl;

   cout << "The upper bound of the element with "
        << "a key of 2 in the map m1 is: "
        << p1.second -> second << "." << endl;

   // Compare the upper_bound called directly
   m1_RcIter = m1.upper_bound( 2 );

   cout << "A direct call of upper_bound( 2 ) gives "
        << m1_RcIter -> second << "," << endl
        << "matching the 2nd element of the pair"
        << " returned by equal_range( 2 )." << endl;

   p2 = m1.equal_range( 4 );

   // If no match is found for the key,
   // both elements of the pair return end( )
   if ( ( p2.first == m1.end( ) ) && ( p2.second == m1.end( ) ) )
      cout << "The map m1 doesn't have an element "
           << "with a key less than 40." << endl;
   else
      cout << "The element of map m1 with a key >= 40 is: "
           << p2.first -> first << "." << endl;
}
```

```Output
The lower bound of the element with a key of 2 in the map m1 is: 20.
The upper bound of the element with a key of 2 in the map m1 is: 30.
A direct call of upper_bound( 2 ) gives 30,
matching the 2nd element of the pair returned by equal_range( 2 ).
The map m1 doesn't have an element with a key less than 40.
```

## <a name="erase"></a><a name="erase"></a>silme

Bir haritadaki bir öğe veya öğe aralığını belirtilen konumlardan kaldırır veya belirtilen bir anahtarla eşleşen öğeleri kaldırır.

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

İlk iki üye işlevi için, kaldırılan tüm öğelerin ötesinde kalan ilk öğeyi veya böyle bir öğe yoksa haritanın sonu olan bir öğeyi atayan çift yönlü bir yineleyici.

Üçüncü üye işlevi için, eşlemden kaldırılmış olan öğe sayısını döndürür.

### <a name="example"></a>Örnek

```cpp
// map_erase.cpp
// compile with: /EHsc
#include <map>
#include <string>
#include <iostream>
#include <iterator> // next() and prev() helper functions
#include <utility>  // make_pair()

using namespace std;

using mymap = map<int, string>;

void printmap(const mymap& m) {
    for (const auto& elem : m) {
        cout << " [" << elem.first << ", " << elem.second << "]";
    }
    cout << endl << "size() == " << m.size() << endl << endl;
}

int main()
{
    mymap m1;

    // Fill in some data to test with, one at a time
    m1.insert(make_pair(1, "A"));
    m1.insert(make_pair(2, "B"));
    m1.insert(make_pair(3, "C"));
    m1.insert(make_pair(4, "D"));
    m1.insert(make_pair(5, "E"));

    cout << "Starting data of map m1 is:" << endl;
    printmap(m1);
    // The 1st member function removes an element at a given position
    m1.erase(next(m1.begin()));
    cout << "After the 2nd element is deleted, the map m1 is:" << endl;
    printmap(m1);

    // Fill in some data to test with, one at a time, using an initializer list
    mymap m2
    {
        { 10, "Bob" },
        { 11, "Rob" },
        { 12, "Robert" },
        { 13, "Bert" },
        { 14, "Bobby" }
    };

    cout << "Starting data of map m2 is:" << endl;
    printmap(m2);
    // The 2nd member function removes elements
    // in the range [First, Last)
    m2.erase(next(m2.begin()), prev(m2.end()));
    cout << "After the middle elements are deleted, the map m2 is:" << endl;
    printmap(m2);

    mymap m3;

    // Fill in some data to test with, one at a time, using emplace
    m3.emplace(1, "red");
    m3.emplace(2, "yellow");
    m3.emplace(3, "blue");
    m3.emplace(4, "green");
    m3.emplace(5, "orange");
    m3.emplace(6, "purple");
    m3.emplace(7, "pink");

    cout << "Starting data of map m3 is:" << endl;
    printmap(m3);
    // The 3rd member function removes elements with a given Key
    mymap::size_type count = m3.erase(2);
    // The 3rd member function also returns the number of elements removed
    cout << "The number of elements removed from m3 is: " << count << "." << endl;
    cout << "After the element with a key of 2 is deleted, the map m3 is:" << endl;
    printmap(m3);
}
```

## <a name="find"></a><a name="find"></a>bilgi

Belirtilen anahtara eşdeğer bir anahtara sahip bir haritadaki öğenin konumuna başvuran bir yineleyici döndürür.

```cpp
iterator find(const Key& key);

const_iterator find(const Key& key) const;
```

### <a name="parameters"></a>Parametreler

*anahtar*\
Aranmakta olan eşlemdeki bir öğenin sıralama anahtarıyla eşleştirilecek anahtar değeri.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen anahtara sahip bir öğenin konumuna başvuran veya anahtar için eşleşme yoksa eşlemedeki son öğeden sonraki konumda bulunan bir yineleyici `map::end()` .

### <a name="remarks"></a>Açıklamalar

Üye işlevi, sıralama anahtarı, karşılaştırmasından daha az bir ilişkiye göre bir sıralamayı karşılayan bir ikili koşul altındaki bağımsız değişken anahtarına denk gelen bir öğe olan bir yineleyici döndürür.

Dönüş değeri `find` bir öğesine atanırsa `const_iterator` , Map nesnesi değiştirilemez. Dönüş değeri `find` bir öğesine atanırsa `iterator` , Map nesnesi değiştirilebilir

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
    map<int, string> m1({ { 40, "Zr" }, { 45, "Rh" } });
    cout << "The starting map m1 is (key, value):" << endl;
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

    cout << "The modified map m1 is (key, value):" << endl;
    print_collection(m1);
    cout << endl;
    findit(m1, 45);
    findit(m1, 6);
}
```

## <a name="get_allocator"></a><a name="get_allocator"></a>get_allocator

Haritayı oluşturmak için kullanılan ayırıcı nesnesinin bir kopyasını döndürür.

```cpp
allocator_type get_allocator() const;
```

### <a name="return-value"></a>Dönüş Değeri

Harita tarafından kullanılan ayırıcı.

### <a name="remarks"></a>Açıklamalar

Map sınıfı için ayrıcılar, sınıfın depolamayı nasıl yönettiğini belirtir. C++ standart kitaplığı kapsayıcı sınıflarıyla birlikte sağlanan varsayılan ayrıcılar çoğu programlama ihtiyacı için yeterlidir. Kendi ayırıcı sınıfınızı yazmak ve kullanmak, gelişmiş bir C++ konudur.

### <a name="example"></a>Örnek

```cpp
// map_get_allocator.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;
   map <int, int>::allocator_type m1_Alloc;
   map <int, int>::allocator_type m2_Alloc;
   map <int, double>::allocator_type m3_Alloc;
   map <int, int>::allocator_type m4_Alloc;

   // The following lines declare objects
   // that use the default allocator.
   map <int, int> m1;
   map <int, int, allocator<int> > m2;
   map <int, double, allocator<double> > m3;

   m1_Alloc = m1.get_allocator( );
   m2_Alloc = m2.get_allocator( );
   m3_Alloc = m3.get_allocator( );

   cout << "The number of integers that can be allocated\n"
        << "before free memory is exhausted: "
        << m2.max_size( ) << ".\n" << endl;

   cout << "The number of doubles that can be allocated\n"
        << "before free memory is exhausted: "
        << m3.max_size( ) <<  ".\n" << endl;

   // The following line creates a map m4
   // with the allocator of map m1.
   map <int, int> m4( less<int>( ), m1_Alloc );

   m4_Alloc = m4.get_allocator( );

   // Two allocators are interchangeable if
   // storage allocated from each can be
   // deallocated with the other
   if( m1_Alloc == m4_Alloc )
   {
      cout << "The allocators are interchangeable." << endl;
   }
   else
   {
      cout << "The allocators are not interchangeable." << endl;
   }
}
```

## <a name="insert"></a><a name="insert"></a>ekleyin

Haritaya bir öğe veya öğe aralığı ekler.

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
Anahtarı equivalently olarak sıralanmış bir öğe içermiyorsa, haritaya eklenecek öğenin değeri.

*Olmadığı*\
Doğru ekleme noktasını aramaya başlamak için yer. (Bu nokta hemen bundan önce geliyorsa, ekleme, logaritmik bir süre yerine, sabit *zamanlı olarak gerçekleşebilir*.)

*ValTy*\
Eşlemenin [value_type](#value_type)bir öğesi oluşturmak için kullanabileceği bağımsız değişken türünü belirten şablon parametresi ve bağımsız değişken olarak *kusursuz iletme değeri* .

*Adı*\
Kopyalanacak ilk öğenin konumu.

*Soyadına*\
Kopyalanacak son öğenin hemen ötesinde konum.

*InputIterator*\
[Value_type](#value_type) nesneleri oluşturmak için kullanılabilecek bir türün öğelerine işaret eden bir [giriş yineleyicisinin](../standard-library/input-iterator-tag-struct.md) gereksinimlerini karşılayan şablon işlevi bağımsız değişkeni.

*IList*\
Öğelerin kopyalanacağı [initializer_list](../standard-library/initializer-list.md) .

### <a name="return-value"></a>Dönüş Değeri

Tek öğeli üye işlevleri, (1) ve (2), [pair](../standard-library/pair-structure.md) **`bool`** bir ekleme yapılırsa bileşeni doğru olan bir çift döndürür ve eşleme zaten anahtarı sıralamada denk bir değere sahip olan bir öğe içeriyorsa yanlış olur. Return-Value çiftinin yineleyici bileşeni, bileşen true ise yeni ınsertedelement öğesine **`bool`** veya bileşen false ise var olan öğeye işaret eder **`bool`** .

Tek öğeli-ipucu üye işlevleri, (3) ve (4), yeni öğenin haritaya eklendiği konuma işaret eden bir yineleyici döndürür veya eşdeğer bir anahtara sahip bir öğe zaten varsa var olan öğeye.

### <a name="remarks"></a>Açıklamalar

Bu işlev tarafından hiçbir yineleyiciler, işaretçiler veya başvuru geçersiz kılınamaz.

Yalnızca bir öğenin eklenmesi sırasında, bir özel durum oluşturulursa, kapsayıcının durumu değiştirilmez. Birden çok öğenin eklenmesi sırasında, bir özel durum oluşturulursa, kapsayıcı belirtilmemiş ancak geçerli bir durumda bırakılır.

`pair` `pr` Tek öğeli üye işlevleri tarafından döndürülen bir ' ın Yineleyici bileşenine erişmek için, `pr.first` öğesini kullanın; döndürülen çiftin içindeki yineleyiciyi başvuru olarak kullanın `*pr.first` . Bileşene erişmek için **`bool`** kullanın `pr.second` . Örnek için, bu makalenin ilerleyen kısımlarında örnek koda bakın.

Kapsayıcının [value_type](#value_type) , kapsayıcısına ait olan ve Map için olan bir typedef 'dir `map<K, V>::value_type` `pair<const K, V>` . Bir öğenin değeri, ilk bileşenin anahtar değere eşit olduğu ve ikinci bileşenin öğenin veri değerine eşit olduğu sıralı bir çiftidir.

Aralık üye işlevi (5), öğe değerlerinin dizisini aralıktaki bir yineleyici tarafından bahsedilen her öğeye karşılık gelen bir haritaya ekler `[First, Last)` ; Bu nedenle, `Last` eklenmez. Kapsayıcı üye işlevi, `end()` kapsayıcıdaki son öğeden hemen sonra gelen konuma başvurur — Örneğin, ifade öğesine `m.insert(v.begin(), v.end());` tüm öğelerini eklemeye çalışır `v` `m` . Yalnızca aralıktaki benzersiz değerlere sahip öğeler eklenir; yinelemeler yoksayıldı. Hangi öğelerin reddedildiğini gözlemlemek için, öğesinin tek öğeli sürümlerini kullanın `insert` .

Başlatıcı listesi üye işlevi (6), öğeleri haritaya kopyalamak için bir [initializer_list](../standard-library/initializer-list.md) kullanır.

Yerinde oluşturulmuş bir öğenin eklenmesi için — diğer bir deyişle, kopyalama veya taşıma işlemleri yapılmaz — bkz. [map:: emplace](#emplace) ve [map:: emplace_hint](#emplace_hint).

### <a name="example"></a>Örnek

```cpp
// map_insert.cpp
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
    map<int, int> m1;
    // call insert(const value_type&) version
    m1.insert({ 1, 10 });
    // call insert(ValTy&&) version
    m1.insert(make_pair(2, 20));

    cout << "The original key and mapped values of m1 are:" << endl;
    print(m1);

    // intentionally attempt a duplicate, single element
    auto ret = m1.insert(make_pair(1, 111));
    if (!ret.second){
        auto pr = *ret.first;
        cout << "Insert failed, element with key value 1 already exists."
            << endl << "  The existing element is (" << pr.first << ", " << pr.second << ")"
            << endl;
    }
    else{
        cout << "The modified key and mapped values of m1 are:" << endl;
        print(m1);
    }
    cout << endl;

    // single element, with hint
    m1.insert(m1.end(), make_pair(3, 30));
    cout << "The modified key and mapped values of m1 are:" << endl;
    print(m1);
    cout << endl;

    // The templatized version inserting a jumbled range
    map<int, int> m2;
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
    map<int, string>  m3;
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

    map<int, int> m4;
    // Insert the elements from an initializer_list
    m4.insert({ { 4, 44 }, { 2, 22 }, { 3, 33 }, { 1, 11 }, { 5, 55 } });
    cout << "After initializer_list insertion, m4 contains:" << endl;
    print(m4);
    cout << endl;
}
```

## <a name="iterator"></a><a name="iterator"></a>iden

Bir haritadaki herhangi bir öğeyi okuyabilen veya değiştirebilen çift yönlü bir yineleyici sağlayan bir tür.

```cpp
typedef implementation-defined iterator;
```

### <a name="remarks"></a>Açıklamalar

Eşleme tarafından tanımlanan Yineleyici, [value_type](#value_type) `pair<const Key, Type>` ilk üyesi öğe için anahtar olan ve ikinci üye öğesi tarafından tutulan eşlenmiş veri olan, türü value_type nesneler olan öğelerine işaret eder.

Bir haritadaki bir öğeye işaret eden bir yineleyici *Iter* başvurusu yapmak için işlecini kullanın `->` .

Öğesinin anahtar değerine erişmek için, `Iter->first` ile eşdeğer olan öğesini kullanın `(*Iter).first` . Öğesi için eşlenen veri değerine erişmek için, `Iter->second` ile eşdeğer olan öğesini kullanın `(*Iter).second` .

### <a name="example"></a>Örnek

Bildirme ve kullanma hakkında bir örnek için bkz. [Başlangıç](#begin) örneği `iterator` .

## <a name="key_comp"></a><a name="key_comp"></a>key_comp

Bir haritadaki anahtarları sıralamak için kullanılan karşılaştırma nesnesinin bir kopyasını alır.

```cpp
key_compare key_comp() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir haritanın öğelerini sıralamak için kullandığı işlev nesnesini döndürür.

### <a name="remarks"></a>Açıklamalar

Saklı nesne, üye işlevini tanımlar

`bool operator(const Key& left, const Key& right);`

Bu, **`true`** `left` önceki ve sıralama düzeninde eşit değilse döndürür `right` .

### <a name="example"></a>Örnek

```cpp
// map_key_comp.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;

   map <int, int, less<int> > m1;
   map <int, int, less<int> >::key_compare kc1 = m1.key_comp( ) ;
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

   map <int, int, greater<int> > m2;
   map <int, int, greater<int> >::key_compare kc2 = m2.key_comp( );
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

## <a name="key_compare"></a><a name="key_compare"></a>key_compare

Haritadaki iki öğenin göreli sırasını belirleyebilmek için iki sıralama anahtarını karşılaştırabilen bir işlev nesnesi sağlayan bir tür.

```cpp
typedef Traits key_compare;
```

### <a name="remarks"></a>Açıklamalar

`key_compare`, şablon parametresi *nitelikleri*için bir eş anlamlı.

*Nitelikler* hakkında daha fazla bilgi Için [Map Class](../standard-library/map-class.md) konusuna bakın.

### <a name="example"></a>Örnek

Bildirme ve kullanma hakkında bir örnek için bkz. [key_comp](#key_comp) örneği `key_compare` .

## <a name="key_type"></a><a name="key_type"></a>key_type

Haritanın her öğesinde depolanan sıralama anahtarını açıklayan bir tür.

```cpp
typedef Key key_type;
```

### <a name="remarks"></a>Açıklamalar

`key_type`, şablon parametre *anahtarı*için bir eş anlamlı.

*Anahtar*hakkında daha fazla bilgi Için [Map Class](../standard-library/map-class.md) konusunun açıklamalar bölümüne bakın.

### <a name="example"></a>Örnek

Bildirme ve kullanma hakkında bir örnek için bkz. [value_type](#value_type) örneği `key_type` .

## <a name="lower_bound"></a><a name="lower_bound"></a>lower_bound

Bir yineleyiciyi belirtilen anahtardan daha büyük veya ona eşit bir anahtar değeri olan bir eşlem içindeki ilk öğeye döndürür.

```cpp
iterator lower_bound(const Key& key);

const_iterator lower_bound(const Key& key) const;
```

### <a name="parameters"></a>Parametreler

*anahtar*\
Aranmakta olan eşlemdeki bir öğenin sıralama anahtarıyla Karşılaştırılacak bağımsız değişken anahtar değeri.

### <a name="return-value"></a>Dönüş Değeri

Bir `iterator` veya `const_iterator` bağımsız değişken anahtarına eşit veya ondan daha büyük bir anahtarla bir öğenin konumunu ele alan veya anahtar için eşleşme bulunmazsa, eşlemenin içindeki son öğeden sonra gelen konumu ele alan bir öğe.

Dönüş değeri `lower_bound` bir öğesine atanırsa `const_iterator` , Map nesnesi değiştirilemez. Dönüş değeri `lower_bound` bir öğesine atanırsa `iterator` , Map nesnesi değiştirilebilir.

### <a name="example"></a>Örnek

```cpp
// map_lower_bound.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;
   map <int, int> m1;
   map <int, int> :: const_iterator m1_AcIter, m1_RcIter;
   typedef pair <int, int> Int_Pair;

   m1.insert ( Int_Pair ( 1, 10 ) );
   m1.insert ( Int_Pair ( 2, 20 ) );
   m1.insert ( Int_Pair ( 3, 30 ) );

   m1_RcIter = m1.lower_bound( 2 );
   cout << "The first element of map m1 with a key of 2 is: "
        << m1_RcIter -> second << "." << endl;

   // If no match is found for this key, end( ) is returned
   m1_RcIter = m1. lower_bound ( 4 );

   if ( m1_RcIter == m1.end( ) )
      cout << "The map m1 doesn't have an element "
           << "with a key of 4." << endl;
   else
      cout << "The element of map m1 with a key of 4 is: "
           << m1_RcIter -> second << "." << endl;

   // The element at a specific location in the map can be found
   // using a dereferenced iterator addressing the location
   m1_AcIter = m1.end( );
   m1_AcIter--;
   m1_RcIter = m1. lower_bound ( m1_AcIter -> first );
   cout << "The element of m1 with a key matching "
        << "that of the last element is: "
        << m1_RcIter -> second << "." << endl;
}
```

```Output
The first element of map m1 with a key of 2 is: 20.
The map m1 doesn't have an element with a key of 4.
The element of m1 with a key matching that of the last element is: 30.
```

## <a name="map"></a><a name="map"></a>harita

Boş veya başka bir eşlemenin tümünün veya bir kısmının kopyası olan bir harita oluşturur.

```cpp
map();

explicit map(
    const Traits& Comp);

map(
    const Traits& Comp,
    const Allocator& Al);

map(
    const map& Right);

map(
    map&& Right);

map(
    initializer_list<value_type> IList);

map(
    initializer_list<value_type> IList,
    const Traits& Comp);

map(
    initializer_list<value_type> IList,
    const Traits& Comp,
    const Allocator& Allocator);

template <class InputIterator>
map(
    InputIterator First,
    InputIterator Last);

template <class InputIterator>
map(
    InputIterator First,
    InputIterator Last,
    const Traits& Comp);

template <class InputIterator>
map(
    InputIterator First,
    InputIterator Last,
    const Traits& Comp,
    const Allocator& Al);
```

### <a name="parameters"></a>Parametreler

*Eşkenar*\
Varsayılan olan bu Map nesnesi için kullanılacak depolama ayırıcısı sınıfı `Allocator` .

*İnin*\
`const Traits`Haritadaki öğeleri sıralamak için kullanılan türün karşılaştırma işlevi, varsayılan olarak `hash_compare` .

*Right*\
Oluşturulan kümesinin bir kopya olması gereken harita.

*Adı*\
Kopyalanacak öğe aralığındaki ilk öğenin konumu.

*Soyadına*\
Kopyalanacak öğe aralığının ötesinde ilk öğenin konumu.

*IList*\
Öğelerin kopyalanacağı initializer_list.

### <a name="remarks"></a>Açıklamalar

Tüm oluşturucular, eşleme için bellek depolamayı yöneten ve daha sonra [get_allocator](#get_allocator)çağırarak döndürülebilecek bir tür ayırıcı nesnesi depolar. Ayırıcı parametresi, genellikle sınıf bildirimlerinde atlanır ve alternatif ayırıcıları değiştirmek için kullanılan ön işleme makrolarıyla sonuçlanır.

Tüm oluşturucular haritalarını başlatır.

Tüm oluşturucular, eşlemenin anahtarları arasında bir sıra oluşturmak için kullanılan ve daha sonra [key_comp](#key_comp)çağırarak geri döndürülebilecek nitelikler türünde bir işlev nesnesi depolar.

İlk üç Oluşturucu boş bir başlangıç eşlemesi belirtir, ikinci olarak öğelerin sırasını oluşturmak için kullanılacak karşılaştırma işlevinin türünü (*comp*) ve kullanılacak ayırıcı türünü (*Al*) açıkça belirten üçüncü olarak belirtin. Anahtar sözcük, **`explicit`** bazı otomatik tür dönüştürme türlerini bastırır.

Dördüncü Oluşturucu haritanın *sağ*bir kopyasını belirtir.

Beşinci Oluşturucu *sağ*taşıyarak haritanın bir kopyasını belirtir.

Altıncı, yedinci ve sekizinci oluşturucular, üyelerin kopyalanacağı bir initializer_list kullanır.

Sonraki üç Oluşturucu, `[First, Last)` bir haritanın aralığını, sınıfın ve ayırıcının karşılaştırma işlevinin türünü belirtirken açıkça artarak kopyalar `Traits` .

### <a name="example"></a>Örnek

```cpp
// map_map.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main()
{
    using namespace std;
    typedef pair <int, int> Int_Pair;
    map <int, int>::iterator m1_Iter, m3_Iter, m4_Iter, m5_Iter, m6_Iter, m7_Iter;
    map <int, int, less<int> >::iterator m2_Iter;

    // Create an empty map m0 of key type integer
    map <int, int> m0;

    // Create an empty map m1 with the key comparison
    // function of less than, then insert 4 elements
    map <int, int, less<int> > m1;
    m1.insert(Int_Pair(1, 10));
    m1.insert(Int_Pair(2, 20));
    m1.insert(Int_Pair(3, 30));
    m1.insert(Int_Pair(4, 40));

    // Create an empty map m2 with the key comparison
    // function of greater than, then insert 2 elements
    map <int, int, less<int> > m2;
    m2.insert(Int_Pair(1, 10));
    m2.insert(Int_Pair(2, 20));

    // Create a map m3 with the
    // allocator of map m1
    map <int, int>::allocator_type m1_Alloc;
    m1_Alloc = m1.get_allocator();
    map <int, int> m3(less<int>(), m1_Alloc);
    m3.insert(Int_Pair(3, 30));

    // Create a copy, map m4, of map m1
    map <int, int> m4(m1);

    // Create a map m5 by copying the range m1[ first,  last)
    map <int, int>::const_iterator m1_bcIter, m1_ecIter;
    m1_bcIter = m1.begin();
    m1_ecIter = m1.begin();
    m1_ecIter++;
    m1_ecIter++;
    map <int, int> m5(m1_bcIter, m1_ecIter);

    // Create a map m6 by copying the range m4[ first,  last)
    // and with the allocator of map m2
    map <int, int>::allocator_type m2_Alloc;
    m2_Alloc = m2.get_allocator();
    map <int, int> m6(m4.begin(), ++m4.begin(), less<int>(), m2_Alloc);

    cout << "m1 =";
    for (auto i : m1)
        cout << i.first << " " << i.second << ", ";
    cout << endl;

    cout << "m2 =";
    for(auto i : m2)
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

    // Create a map m7 by moving m5
    cout << "m7 =";
    map<int, int> m7(move(m5));
    for (auto i : m7)
        cout << i.first << " " << i.second << ", ";
    cout << endl;

    // Create a map m8 by copying in an initializer_list
    map<int, int> m8{ { { 1, 1 }, { 2, 2 }, { 3, 3 }, { 4, 4 } } };
    cout << "m8: = ";
    for (auto i : m8)
        cout << i.first << " " << i.second << ", ";
    cout << endl;

    // Create a map m9 with an initializer_list and a comparator
    map<int, int> m9({ { 5, 5 }, { 6, 6 }, { 7, 7 }, { 8, 8 } }, less<int>());
    cout << "m9: = ";
    for (auto i : m9)
        cout << i.first << " " << i.second << ", ";
    cout << endl;

    // Create a map m10 with an initializer_list, a comparator, and an allocator
    map<int, int> m10({ { 9, 9 }, { 10, 10 }, { 11, 11 }, { 12, 12 } }, less<int>(), m9.get_allocator());
    cout << "m10: = ";
    for (auto i : m10)
        cout << i.first << " " << i.second << ", ";
    cout << endl;
}
```

## <a name="mapped_type"></a><a name="mapped_type"></a>mapped_type

Bir haritada depolanan verileri temsil eden bir tür.

```cpp
typedef Type mapped_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, `mapped_type` sınıfın *tür* şablonu parametresinin bir eş anlamlısıdır.

*Tür* hakkında daha fazla bilgi Için [Map Class](../standard-library/map-class.md) konusuna bakın.

### <a name="example"></a>Örnek

Bildirme ve kullanma hakkında bir örnek için bkz. [value_type](#value_type) örneği `mapped_type` .

## <a name="max_size"></a><a name="max_size"></a>max_size

Eşlem öğesinin maksimum uzunluğunu döndürür.

```cpp
size_type max_size() const;
```

### <a name="return-value"></a>Dönüş Değeri

Haritanın en büyük olası uzunluğu.

### <a name="example"></a>Örnek

```cpp
// map_max_size.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;
   map <int, int> m1;
   map <int, int> :: size_type i;

   i = m1.max_size( );
   cout << "The maximum possible length "
        << "of the map is " << i << "."
        << endl << "(Magnitude is machine specific.)";
}
```

## <a name="operator"></a><a name="op_at"></a>operator []

Belirtilen bir anahtar değere sahip bir eşleme bir öğe ekler.

```cpp
Type& operator[](const Key& key);

Type& operator[](Key&& key);
```

### <a name="parameters"></a>Parametreler

*anahtar*\
Eklenecek öğenin anahtar değeri.

### <a name="return-value"></a>Dönüş Değeri

Eklenen öğenin veri değerine başvuru.

### <a name="remarks"></a>Açıklamalar

Bağımsız değişken anahtar değeri bulunamazsa, değer veri türünün varsayılan değeriyle birlikte eklenir.

`operator[]`, anahtarın anahtar `m` `m[key] = DataValue;` `DataValue` `mapped_type` değerine sahip öğenin değeri olan *key*' i kullanarak bir haritaya öğe eklemek için kullanılabilir.

`operator[]`Öğeleri eklemek için kullanırken, döndürülen başvuru, bir eklentinin önceden varolan bir öğeyi değiştirip değiştirmediğini veya yeni bir tane oluşturmadığını göstermez. [Bul](#find) ve [Ekle](#insert) üye işlevleri, bir ekleme işleminden önce belirtilen anahtara sahip bir öğenin zaten mevcut olup olmadığını anlamak için kullanılabilir.

### <a name="example"></a>Örnek

```cpp
// map_op_insert.cpp
// compile with: /EHsc
#include <map>
#include <iostream>
#include <string>

int main( )
{
   using namespace std;
   typedef pair <const int, int> cInt2Int;
   map <int, int> m1;
   map <int, int> :: iterator pIter;

   // Insert a data value of 10 with a key of 1
   // into a map using the operator[] member function
   m1[ 1 ] = 10;

   // Compare other ways to insert objects into a map
   m1.insert ( map <int, int> :: value_type ( 2, 20 ) );
   m1.insert ( cInt2Int ( 3, 30 ) );

   cout  << "The keys of the mapped elements are:";
   for ( pIter = m1.begin( ) ; pIter != m1.end( ) ; pIter++ )
      cout << " " << pIter -> first;
   cout << "." << endl;

   cout  << "The values of the mapped elements are:";
   for ( pIter = m1.begin( ) ; pIter != m1.end( ) ; pIter++ )
      cout << " " << pIter -> second;
   cout << "." << endl;

   // If the key already exists, operator[]
   // changes the value of the datum in the element
   m1[ 2 ] = 40;

   // operator[] will also insert the value of the data
   // type's default constructor if the value is unspecified
   m1[5];

   cout  << "The keys of the mapped elements are now:";
   for ( pIter = m1.begin( ) ; pIter != m1.end( ) ; pIter++ )
      cout << " " << pIter -> first;
   cout << "." << endl;

   cout  << "The values of the mapped elements are now:";
   for ( pIter = m1.begin( ) ; pIter != m1.end( ) ; pIter++ )
      cout << " " << pIter -> second;
   cout << "." << endl;

// insert by moving key
    map<string, int> c2;
    string str("abc");
    cout << "c2[move(str)] == " << c2[move(str)] << endl;
    cout << "c2["abc"] == " << c2["abc"] << endl;

    return (0);
}
```

```Output
The keys of the mapped elements are: 1 2 3.
The values of the mapped elements are: 10 20 30.
The keys of the mapped elements are now: 1 2 3 5.
The values of the mapped elements are now: 10 40 30 0.
c2[move(str)] == 0
c2["abc"] == 1
```

## <a name="operator"></a><a name="op_eq"></a>işleç =

Bir eşlemin öğelerini başka bir eşlem kopyasıyla değiştirir.

```cpp
map& operator=(const map& right);
map& operator=(map&& right);
```

### <a name="parameters"></a>Parametreler

*Right*\
Öğesine kopyalandığı [harita](../standard-library/map-class.md) `map` .

### <a name="remarks"></a>Açıklamalar

İçindeki varolan öğeleri sildikten sonra `map` , `operator=` sağ içeriğini haritaya kopyalar veya buraya *taşısa* .

### <a name="example"></a>Örnek

```cpp
// map_operator_as.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
   {
   using namespace std;
   map<int, int> v1, v2, v3;
   map<int, int>::iterator iter;

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

## <a name="pointer"></a><a name="pointer"></a>çağrısı

Haritada bir öğeye işaretçi sağlayan bir tür.

```cpp
typedef typename allocator_type::pointer pointer;
```

### <a name="remarks"></a>Açıklamalar

Bir türü `pointer` , bir öğenin değerini değiştirmek için kullanılabilir.

Çoğu durumda, bir [Yineleyici](#iterator) bir eşleme nesnesindeki öğelere erişmek için kullanılmalıdır.

## <a name="rbegin"></a><a name="rbegin"></a>rbegin

Tersine çevrilmiş haritadaki ilk öğeyi ele alarak bir yineleyici döndürür.

```cpp
const_reverse_iterator rbegin() const;

reverse_iterator rbegin();
```

### <a name="return-value"></a>Dönüş Değeri

Ters çevrilen bir haritadaki ilk öğeyi ele alarak ters çevrilen bir yineleyiciden veya geri çevrilmeyen haritadaki son öğe olduğunu gidermeye yönelik ters yönlü bir yineleyici.

### <a name="remarks"></a>Açıklamalar

`rbegin`, [Begin](#begin) ile birlikte kullanıldığı gibi tersine çevrilmiş bir eşleme ile kullanılır.

Öğesinin dönüş değeri `rbegin` öğesine atanmışsa `const_reverse_iterator` , eşleme nesnesi değiştirilemez. Dönüş değeri `rbegin` bir öğesine atanırsa `reverse_iterator` , eşleme nesnesi değiştirilebilir.

`rbegin`bir haritada geriye doğru yinelemek için kullanılabilir.

### <a name="example"></a>Örnek

```cpp
// map_rbegin.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;
   map <int, int> m1;

   map <int, int> :: iterator m1_Iter;
   map <int, int> :: reverse_iterator m1_rIter;
   map <int, int> :: const_reverse_iterator m1_crIter;
   typedef pair <int, int> Int_Pair;

   m1.insert ( Int_Pair ( 1, 10 ) );
   m1.insert ( Int_Pair ( 2, 20 ) );
   m1.insert ( Int_Pair ( 3, 30 ) );

   m1_rIter = m1.rbegin( );
   cout << "The first element of the reversed map m1 is "
        << m1_rIter -> first << "." << endl;

   // begin can be used to start an iteration
   // through a map in a forward order
   cout << "The map is: ";
   for ( m1_Iter = m1.begin( ) ; m1_Iter != m1.end( ); m1_Iter++)
      cout << m1_Iter -> first << " ";
      cout << "." << endl;

   // rbegin can be used to start an iteration
   // through a map in a reverse order
   cout << "The reversed map is: ";
   for ( m1_rIter = m1.rbegin( ) ; m1_rIter != m1.rend( ); m1_rIter++)
      cout << m1_rIter -> first << " ";
      cout << "." << endl;

   // A map element can be erased by dereferencing to its key
   m1_rIter = m1.rbegin( );
   m1.erase ( m1_rIter -> first );

   m1_rIter = m1.rbegin( );
   cout << "After the erasure, the first element "
        << "in the reversed map is "
        << m1_rIter -> first << "." << endl;
}
```

```Output
The first element of the reversed map m1 is 3.
The map is: 1 2 3 .
The reversed map is: 3 2 1 .
After the erasure, the first element in the reversed map is 2.
```

## <a name="reference"></a><a name="reference"></a>başvurunun

Haritada depolanan bir öğeye başvuru sağlayan bir tür.

```cpp
typedef typename allocator_type::reference reference;
```

### <a name="example"></a>Örnek

```cpp
// map_reference.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;
   map <int, int> m1;
   typedef pair <int, int> Int_Pair;

   m1.insert ( Int_Pair ( 1, 10 ) );
   m1.insert ( Int_Pair ( 2, 20 ) );

   // Declare and initialize a const_reference &Ref1
   // to the key of the first element
   const int &Ref1 = ( m1.begin( ) -> first );

   // The following line would cause an error because the
   // non-const_reference cannot be used to access the key
   // int &Ref1 = ( m1.begin( ) -> first );

   cout << "The key of first element in the map is "
        << Ref1 << "." << endl;

   // Declare and initialize a reference &Ref2
   // to the data value of the first element
   int &Ref2 = ( m1.begin( ) -> second );

   cout << "The data value of first element in the map is "
        << Ref2 << "." << endl;

   //The non-const_reference can be used to modify the
   //data value of the first element
   Ref2 = Ref2 + 5;
   cout << "The modified data value of first element is "
        << Ref2 << "." << endl;
}
```

```Output
The key of first element in the map is 1.
The data value of first element in the map is 10.
The modified data value of first element is 15.
```

## <a name="rend"></a><a name="rend"></a>rend

Tersine çevrilmiş eşlemedeki son öğeden sonraki konumu ele alan bir yineleyici döndürür.

```cpp
const_reverse_iterator rend() const;

reverse_iterator rend();
```

### <a name="return-value"></a>Dönüş Değeri

Ters çevrilen bir haritadaki son öğeden sonra gelen konumu ele alan ters çift yönlü yineleyici (geri çevrilmeyen haritadaki ilk öğeden önce gelen konum).

### <a name="remarks"></a>Açıklamalar

`rend`[End](#end) , bir eşleme ile birlikte kullanıldığı gibi, bir ters eşleme ile kullanılır.

Öğesinin dönüş değeri `rend` öğesine atanmışsa `const_reverse_iterator` , eşleme nesnesi değiştirilemez. Dönüş değeri `rend` bir öğesine atanırsa `reverse_iterator` , eşleme nesnesi değiştirilebilir.

`rend`, bir ters yineleyicinin haritanın sonuna ulaşıp ulaşılmadığını test etmek için kullanılabilir.

Tarafından döndürülen değer `rend` başvurulmamalıdır.

### <a name="example"></a>Örnek

```cpp
// map_rend.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;
   map <int, int> m1;

   map <int, int> :: iterator m1_Iter;
   map <int, int> :: reverse_iterator m1_rIter;
   map <int, int> :: const_reverse_iterator m1_crIter;
   typedef pair <int, int> Int_Pair;

   m1.insert ( Int_Pair ( 1, 10 ) );
   m1.insert ( Int_Pair ( 2, 20 ) );
   m1.insert ( Int_Pair ( 3, 30 ) );

   m1_rIter = m1.rend( );
   m1_rIter--;
   cout << "The last element of the reversed map m1 is "
        << m1_rIter -> first << "." << endl;

   // begin can be used to start an iteration
   // through a map in a forward order
   cout << "The map is: ";
   for ( m1_Iter = m1.begin( ) ; m1_Iter != m1.end( ); m1_Iter++)
      cout << m1_Iter -> first << " ";
      cout << "." << endl;

   // rbegin can be used to start an iteration
   // through a map in a reverse order
   cout << "The reversed map is: ";
   for ( m1_rIter = m1.rbegin( ) ; m1_rIter != m1.rend( ); m1_rIter++)
      cout << m1_rIter -> first << " ";
      cout << "." << endl;

   // A map element can be erased by dereferencing to its key
   m1_rIter = --m1.rend( );
   m1.erase ( m1_rIter -> first );

   m1_rIter = m1.rend( );
   m1_rIter--;
   cout << "After the erasure, the last element "
        << "in the reversed map is "
        << m1_rIter -> first << "." << endl;
}
```

```Output
The last element of the reversed map m1 is 1.
The map is: 1 2 3 .
The reversed map is: 3 2 1 .
After the erasure, the last element in the reversed map is 2.
```

## <a name="reverse_iterator"></a><a name="reverse_iterator"></a>reverse_iterator

Tersine çevrilmiş bir haritadaki bir öğeyi okuyabilen veya değiştirebilen çift yönlü bir yineleyici sağlayan bir tür.

```cpp
typedef std::reverse_iterator<iterator> reverse_iterator;
```

### <a name="remarks"></a>Açıklamalar

Bir tür `reverse_iterator` , bir öğenin değerini değiştiremez ve eşleme boyunca ters yönde yinelemek için kullanılır.

`reverse_iterator`Tarafından tanımlanan eşleme, [value_type](#value_type) `pair<const Key, Type>` ilk üyesi öğe için anahtar olan ve ikinci üye öğesi tarafından tutulan eşlenmiş veri olan, türü value_type nesneler olan öğeleri gösterir.

Bir `reverse_iterator` haritadaki bir öğeye işaret eden bir *Grup* başvurusu için `->` işlecini kullanın.

Öğesinin anahtar değerine erişmek için, `rIter`  ->  () ile eşdeğer olan **ilk**öğesini kullanın \* `rIter` . **ilk**olarak. Öğesi için eşlenen veri değerine erişmek için, `rIter`  ->  () eşdeğeri olan **ikincisini**kullanın \* `rIter` . **ilk**olarak.

### <a name="example"></a>Örnek

Bildirme ve kullanma hakkında bir örnek için bkz. [rbegin](#rbegin) örneği `reverse_iterator` .

## <a name="size"></a><a name="size"></a>boyutla

Eşlem içindeki öğelerin sayısını döndürür.

```cpp
size_type size() const;
```

### <a name="return-value"></a>Dönüş Değeri

Haritanın geçerli uzunluğu.

### <a name="example"></a>Örnek

Aşağıdaki örnek, map:: size üye işlevinin kullanımını gösterir.

```cpp
// map_size.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main()
{
    using namespace std;
    map<int, int> m1, m2;
    map<int, int>::size_type i;
    typedef pair<int, int> Int_Pair;

    m1.insert(Int_Pair(1, 1));
    i = m1.size();
    cout << "The map length is " << i << "." << endl;

    m1.insert(Int_Pair(2, 4));
    i = m1.size();
    cout << "The map length is now " << i << "." << endl;
}
```

```Output
The map length is 1.
The map length is now 2.
```

## <a name="size_type"></a><a name="size_type"></a>size_type

Bir haritadaki öğelerin sayısını temsil eden işaretsiz bir tamsayı türü.

```cpp
typedef typename allocator_type::size_type size_type;
```

### <a name="example"></a>Örnek

Nasıl bildirilemeyeceğini ve kullanılacağına ilişkin bir örnek için [Boyut](#size) örneğine bakın `size_type` .

## <a name="swap"></a><a name="swap"></a>Kur

İki eşlemin öğelerini birbiriyle değiştirir.

```cpp
void swap(
    map<Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*Right*\
Hedef eşleme ile takas edilecek öğeleri sağlayan bağımsız değişken eşlemesi.

### <a name="remarks"></a>Açıklamalar

Üye işlevi, öğeleri takas edilmekte olan iki haritadaki öğeleri belirten başvuruları, işaretçileri veya yineleyicileri geçersiz kılar.

### <a name="example"></a>Örnek

```cpp
// map_swap.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;
   map <int, int> m1, m2, m3;
   map <int, int>::iterator m1_Iter;
   typedef pair <int, int> Int_Pair;

   m1.insert ( Int_Pair ( 1, 10 ) );
   m1.insert ( Int_Pair ( 2, 20 ) );
   m1.insert ( Int_Pair ( 3, 30 ) );
   m2.insert ( Int_Pair ( 10, 100 ) );
   m2.insert ( Int_Pair ( 20, 200 ) );
   m3.insert ( Int_Pair ( 30, 300 ) );

   cout << "The original map m1 is:";
   for ( m1_Iter = m1.begin( ); m1_Iter != m1.end( ); m1_Iter++ )
      cout << " " << m1_Iter -> second;
   cout   << "." << endl;

   // This is the member function version of swap
   //m2 is said to be the argument map; m1 the target map
   m1.swap( m2 );

   cout << "After swapping with m2, map m1 is:";
   for ( m1_Iter = m1.begin( ); m1_Iter != m1.end( ); m1_Iter++ )
      cout << " " << m1_Iter -> second;
   cout  << "." << endl;

   // This is the specialized template version of swap
   swap( m1, m3 );

   cout << "After swapping with m3, map m1 is:";
   for ( m1_Iter = m1.begin( ); m1_Iter != m1.end( ); m1_Iter++ )
      cout << " " << m1_Iter -> second;
   cout   << "." << endl;
}
```

```Output
The original map m1 is: 10 20 30.
After swapping with m2, map m1 is: 100 200.
After swapping with m3, map m1 is: 300.
```

## <a name="upper_bound"></a><a name="upper_bound"></a>upper_bound

Bir yineleyiciyi, belirtilen anahtardan daha büyük bir değere sahip bir anahtara sahip olan eşlemedeki ilk öğeye döndürür.

```cpp
iterator upper_bound(const Key& key);

const_iterator upper_bound(const Key& key) const;
```

### <a name="parameters"></a>Parametreler

*anahtar*\
Aranmakta olan eşlemdeki bir öğenin sıralama anahtarı değeriyle Karşılaştırılacak bağımsız değişken anahtar değeri.

### <a name="return-value"></a>Dönüş Değeri

Bir `iterator` veya `const_iterator` bağımsız değişken anahtarından daha büyük bir anahtara sahip olan bir haritadaki bir öğenin konumunu ele alan veya anahtar için eşleşme bulunmazsa haritanın son öğeden sonra gelen konumu ele alan bir öğe.

Dönüş değeri bir öğesine atanırsa `const_iterator` , Map nesnesi değiştirilemez. Dönüş değeri bir öğesine atanırsa `iterator` , Map nesnesi değiştirilebilir.

### <a name="example"></a>Örnek

```cpp
// map_upper_bound.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;
   map <int, int> m1;
   map <int, int> :: const_iterator m1_AcIter, m1_RcIter;
   typedef pair <int, int> Int_Pair;

   m1.insert ( Int_Pair ( 1, 10 ) );
   m1.insert ( Int_Pair ( 2, 20 ) );
   m1.insert ( Int_Pair ( 3, 30 ) );

   m1_RcIter = m1.upper_bound( 2 );
   cout << "The first element of map m1 with a key "
        << "greater than 2 is: "
        << m1_RcIter -> second << "." << endl;

   // If no match is found for the key, end is returned
   m1_RcIter = m1. upper_bound ( 4 );

   if ( m1_RcIter == m1.end( ) )
      cout << "The map m1 doesn't have an element "
           << "with a key greater than 4." << endl;
   else
      cout << "The element of map m1 with a key > 4 is: "
           << m1_RcIter -> second << "." << endl;

   // The element at a specific location in the map can be found
   // using a dereferenced iterator addressing the location
   m1_AcIter = m1.begin( );
   m1_RcIter = m1. upper_bound ( m1_AcIter -> first );
   cout << "The 1st element of m1 with a key greater than\n"
        << "that of the initial element of m1 is: "
        << m1_RcIter -> second << "." << endl;
}
```

```Output
The first element of map m1 with a key greater than 2 is: 30.
The map m1 doesn't have an element with a key greater than 4.
The 1st element of m1 with a key greater than
that of the initial element of m1 is: 20.
```

## <a name="value_comp"></a><a name="value_comp"></a>value_comp

Üye işlevi, anahtar değerlerini karşılaştırarak bir haritadaki öğelerin sırasını belirleyen bir işlev nesnesi döndürür.

```cpp
value_compare value_comp() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir haritanın öğelerini sıralamak için kullandığı karşılaştırma işlevi nesnesini döndürür.

### <a name="remarks"></a>Açıklamalar

Bir harita *d*için, iki öğe *E1*(*K1*, *D1*) ve *E2*(*K2*, *D2*) türündeki nesnelerdir; `value_type` burada *K1* ve *K1* , türü `key_type` ve *D1* ve *D2* değerlerinin türü,,, ile `mapped_type` `m.value_comp(e1, e2)` eşdeğerdir `m.key_comp(k1, k2)` . Saklı nesne üye işlevini tanımlar

`bool operator( value_type& left, value_type& right);`

Bu **`true`** , anahtar değerinin `left` önce ve ' nin sıralama düzeninde anahtar değerine eşit olmaması halinde döndürür `right` .

### <a name="example"></a>Örnek

```cpp
// map_value_comp.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;

   map <int, int, less<int> > m1;
   map <int, int, less<int> >::value_compare vc1 = m1.value_comp( );
   pair< map<int,int>::iterator, bool > pr1, pr2;

   pr1= m1.insert ( map <int, int> :: value_type ( 1, 10 ) );
   pr2= m1.insert ( map <int, int> :: value_type ( 2, 5 ) );

   if( vc1( *pr1.first, *pr2.first ) == true )
   {
      cout << "The element ( 1,10 ) precedes the element ( 2,5 )."
           << endl;
   }
   else
   {
      cout << "The element ( 1,10 ) does not precede the element ( 2,5 )."
           << endl;
   }

   if(vc1( *pr2.first, *pr1.first ) == true )
   {
      cout << "The element ( 2,5 ) precedes the element ( 1,10 )."
           << endl;
   }
   else
   {
      cout << "The element ( 2,5 ) does not precede the element ( 1,10 )."
           << endl;
   }
}
```

```Output
The element ( 1,10 ) precedes the element ( 2,5 ).
The element ( 2,5 ) does not precede the element ( 1,10 ).
```

## <a name="value_type"></a><a name="value_type"></a>value_type

Haritada bir öğe olarak depolanan nesne türü.

```cpp
typedef pair<const Key, Type> value_type;
```

### <a name="example"></a>Örnek

```cpp
// map_value_type.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;
   typedef pair <const int, int> cInt2Int;
   map <int, int> m1;
   map <int, int> :: key_type key1;
   map <int, int> :: mapped_type mapped1;
   map <int, int> :: value_type value1;
   map <int, int> :: iterator pIter;

   // value_type can be used to pass the correct type
   // explicitly to avoid implicit type conversion
   m1.insert ( map <int, int> :: value_type ( 1, 10 ) );

   // Compare other ways to insert objects into a map
   m1.insert ( cInt2Int ( 2, 20 ) );
   m1[ 3 ] = 30;

   // Initializing key1 and mapped1
   key1 = ( m1.begin( ) -> first );
   mapped1 = ( m1.begin( ) -> second );

   cout << "The key of first element in the map is "
        << key1 << "." << endl;

   cout << "The data value of first element in the map is "
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

## <a name="see-also"></a>Ayrıca bkz.

[Kapsayıcıları](../cpp/containers-modern-cpp.md)\
[C++ standart kitaplığı 'nda iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[C++ standart kitaplığı başvurusu](../standard-library/cpp-standard-library-reference.md)
