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
ms.openlocfilehash: 8694d554261468c4e828936f6a999f073e98849f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50429698"
---
# <a name="map-class"></a>map Sınıfı

Her bir öğenin hem veri değerine hem de sıralama anahtarına sahip olduğu bir çift olan bir koleksiyondaki verileri alma ve depolama için kullanılır. Anahtarın değeri benzersizdir ve verileri otomatik olarak sıralamak için kullanılır.

Bir eşlemdeki bir öğenin değeri doğrudan değiştirilemez. Anahtar değeri sabittir ve değiştirilemez. Bunun yerine, eski öğelerle ilişkili anahtar değerleri silinmeli ve yeni öğeler için yeni anahtar değerleri eklenmelidir.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Key,
    class Type,
    class Traits = less<Key>,
    class Allocator=allocator<pair <const Key, Type>>>
class map;
```

### <a name="parameters"></a>Parametreler

*Key*<br/>
Eşlemde depolanacak anahtar veri türü.

*Türü*<br/>
Eşlemde depolanacak öğe veri türü.

*Nitelikler*<br/>
İki öğenin değerlerini eşlemde kendi göreli sıralarını belirlemek için sıralama anahtarları olarak karşılaştırabilen bir işlev nesnesi sağlayan tür. Bu bağımsız değişken isteğe bağlıdır ve ikili koşul `less<Key>` varsayılan değerdir.

C ++ 14 sürümünde türü parametresi yok std::less <> koşul belirterek heterojen arama etkinleştirebilirsiniz. Daha fazla bilgi için [, ilişkili kapsayıcılar için heterojen arama](../standard-library/stl-containers.md#sequence_containers)

*Ayırıcı*<br/>
Eşlemin bellek ayırmayı ve ayırmayı kaldırma hakkındaki ayrıntıları içeren saklı ayırıcı nesnesini gösteren tür. Bu bağımsız değişken isteğe bağlıdır ve varsayılan değer `allocator<pair<const Key, Type> >`.

## <a name="remarks"></a>Açıklamalar

C++ Standart Kitaplığı eşlemi sınıfı şöyledir:

- Öğe değerlerini etkin olarak alan değişken boyutunun bir kapsayıcısı ilişkili anahtar değerlerine dayalıdır.

- Çift yönlüdür, çünkü öğelerine erişmek için çift yönlü yineleyiciler sağlar.

- Sıralıdır, çünkü öğeleri belirtilen karşılaştırma işlevine uygun olarak anahtar değerlere göre sıralanır.

- Benzersiz. öğelerinin her birinde benzersiz bir anahtar olması gerektiğinden.

- Bir çift ilişkilendirilebilir kapsayıcıdır, çünkü veri öğelerinin değerleri kendi anahtar değerlerinden farklıdır.

- Bir şablon sınıfıdır, çünkü sağladığı işlevsellik geneldir ve öğe ve anahtar türünden bağımsızdır. Öğeler ve anahtarlar için kullanılan veri türleri, karşılaştırma işlevi ve ayırıcı ile birlikte bir sınıf şablonunda parametreler olarak belirtilir.

Eşlem sınıfı tarafından sağlanan yineleyici çift yönlüdür, olan ancak [Ekle](#insert) ve [harita](#map) sınıf üyesi işlevleri, şablon parametresi olarak daha zayıf bir giriş yineleyicisini alan sürümleri sahip olan işlevsellik gereksinimleri az tarafından çift yönlü Yineleyicilerin sınıfında garanti edilene. Farklı yineleyici kavramları, işlevselliklerindeki iyileştirmelerle ilgilidir. Her yineleyici kavramı kendi gereksinimler kümesine sahiptir ve onunla çalışan algoritmalar bu gereksinimler ile sınırlı olmalıdır. Bir giriş yineleyicinin bazı nesnelere başvurusu kaldırılabilir ve dizideki sonraki yineleyiciye artırılabilir.

Kapsayıcı türünün seçimini uygulamanın gerektirdiği arama ve ekleme türüne dayalı yapmanız önerilir. İlişkilendirilebilir kapsayıcılar, arama, ekleme ve kaldırma işlemleri için en iyi duruma getirilir. Bu işlemleri açıkça destekleyen üye işlevleri, işlevlerini kapsayıcıdaki öğelerin sayısının logaritmasına ortalama orantılı en kötü sürede gerçekleştirir. Öğelerin eklenmesi hiçbir yineleyiciyi geçersiz kılmaz; öğelerin kaldırılması yalnızca özellikle kaldırılan öğeleri gösteren yineleyicileri geçersiz kılar.

Eşlemi, değerleri anahtarlarıyla ilişkilendiren koşullar uygulama tarafından karşılandığında seçimin ilişkili kapsayıcısı yapmanız önerilir. Bu tür bir yapı modeli, tanımlar sağlayan ilişkilendirmiş dize değerlerine sahip benzersiz oluşan anahtar sözcüklerin sıralı bir listesidir. Bir sözcüğün birden fazla doğru tanımı varsa, anahtar benzersiz olmadığından, çoklu eşlem kapsayıcı seçimi olacaktır. Yalnızca sözcüklerin listesi depolanmaktaysa, uygun kapsayıcı bir küme olacaktır. Sözcüklerin birden çok defa geçmelerine izin verilirse, bir çoklu küme uygun olacaktır.

Eşleme türü bir depolanmış bir işlev nesnesi çağırarak denetlediği öğeleri sıralar [key_compare](#key_compare). Depolanan bu nesne çağrılarak erişilen bir karşılaştırma işlevidir [key_comp](#key_comp) yöntemi. Genelde, verilen herhangi iki öğe, birinin diğerinden daha küçük olup olmadığının veya denk olup olmadıklarının belirlenmesi için karşılaştırılır. Tüm öğeler karşılaştırıldığında, denk olmayan öğelerin sıralı bir dizisi oluşturulur.

> [!NOTE]
> Karşılaştırma işlevi standart matematiksel anlamda katı bir zayıf sıralama sevk eden ikili bir koşuldur. Bir ikili koşul f(x,y) iki bağımsız değişken nesnelere sahip bir işlev nesnesidir x ve y ve dönüş değeri **true** veya **false**. Bir kümesinde ikili koşul dönüşsüz, ters ve geçişli ve denklik geçişli ise, burada iki nesne sıralama katı zayıf sıralamadır x ve y f(x,y) hem f(y,x) olduğunda denk olarak tanımlanırlar **false** . Anahtarlar arasındaki eşitliğinin daha güçlü koşulu bu denkliğin yerini alırsa, sıralama (içindeki tüm öğelerin birbirine göre sıralanması anlamında) toplam haline gelir ve eşleşen anahtarlar birbirinden ayırt edilemez olacaktır.
>
> C ++ 14'te belirterek heterojen arama etkinleştirebilirsiniz `std::less<>` veya `std::greater<>` hiçbir tür parametreleri olan koşul. Daha fazla bilgi için [, ilişkili kapsayıcılar için heterojen arama](../standard-library/stl-containers.md#sequence_containers)

## <a name="members"></a>Üyeler

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[Harita](#map)|Belirli bir boyut veya belirli bir değer öğeleriyle veya belirli bir ile bir liste oluşturur `allocator` veya başka bir eşlemin bir kopyasını olarak.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[allocator_type](#allocator_type)|İçin bir typedef `allocator` harita nesnesi için sınıf.|
|[const_iterator](#const_iterator)|Okuyabilen çift yönlü yineleyiciler için typedef bir **const** haritadaki öğe.|
|[const_pointer](#const_pointer)|İşaretçisi için bir typedef bir **const** bir eşlem içindeki öğe.|
|[const_reference](#const_reference)|Başvuru için bir typedef bir **const** okumak ve gerçekleştirmek için bir eşlem içinde depolanan öğenin **const** operations.|
|[const_reverse_iterator](#const_reverse_iterator)|Çift yönlü bir yineleyici sağlayan tür herhangi okuma **const** haritadaki öğe.|
|[difference_type](#difference_type)|Yineleyiciler tarafından gösterilen öğeler arasındaki bir aralıktaki eşlemin öğelerinin işaretli bir tamsayı typedef'i.|
|[Yineleyici](#iterator)|Eşlem içindeki herhangi bir öğeyi okuyabilen veya değiştirebilen çift yönlü yineleyiciler için typedef.|
|[key_compare](#key_compare)|Eşlem içindeki iki öğenin göreli sırasını belirlemek için iki sıralama anahtarını karşılaştıran işlev nesnesi için bir typedef.|
|[key_type](#key_type)|Eşlemin her öğesinde depolanan sıralama anahtarı için bir typedef.|
|[mapped_type](#mapped_type)|Bir eşlemin her öğesinde depolanan veriler için bir typedef.|
|[İşaretçi](#pointer)|İşaretçisi için bir typedef bir **const** bir eşlem içindeki öğe.|
|[Başvuru](#reference)|Bir eşlem içinde depolan bir öğeye başvuru için bir typedef.|
|[reverse_iterator](#reverse_iterator)|Ters döndürülmüş eşlem içindeki bir öğeyi okuyabilen veya değiştirebilen çift yönlü yineleyiciler için typedef.|
|[size_type](#size_type)|Bir eşlemdeki öğe sayısı için işaretsiz tamsayı typedef'i.|
|[value_type](#value_type)|Bir eşlem içinde bir öğe olarak depolanan nesne türü için bir typedef.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[konumunda](#at)|Belirtilen anahtar değere sahip bir öğe bulur.|
|[başlayın](#begin)|Eşlem içindeki ilk öğeyi gösteren bir yineleyici döndürür.|
|[cbegin](#cbegin)|Eşlem içindeki ilk öğeyi gösteren sabit bir yineleyici döndürür.|
|[cend](#cend)|Bir sabit past-the-end yineleyici döndürür.|
|[Temizle](#clear)|Eşlemin tüm öğelerini siler.|
|[Sayısı](#count)|Anahtarı bir parametre içinde belirtilen anahtarla eşleşen eşlem içindeki öğelerin sayısını döndürür.|
|[crbegin](#crbegin)|Ters döndürülmüş bir eşlem içindeki ilk öğeyi gösteren sabit bir yineleyici döndürür.|
|[crend](#crend)|Ters döndürülmüş bir eşlem içindeki son öğenin ardındaki konumu gösteren sabit bir yineleyici döndürür.|
|[emplace](#emplace)|Eşlem içine yerinde oluşturulmuş bir öğe ekler.|
|[emplace_hint](#emplace_hint)|Eşlem içine, bir yerleşim ipucuyla birlikte yerinde oluşturulmuş bir öğe ekler.|
|[boş](#empty)|Döndürür **true** bir eşlem boşsa.|
|[Son](#end)|past-the-end yineleyici döndürür.|
|[equal_range](#equal_range)|Yineleyicilerin bir çiftini döndürür. İlk yineleyicisi çifti içindeki ilk öğeye bir `map` belirtilen anahtardan daha büyük bir anahtarla. İkinci yineleyicisi çifti içindeki ilk öğeyi `map` anahtardan daha büyük veya ona eşit bir anahtara sahip.|
|[silme](#erase)|Bir eşlemdeki bir öğe veya öğe aralığını belirtilen konumdan kaldırır.|
|[Bul](#find)|Belirtilen anahtara eşit bir anahtara sahip bir eşlem içindeki bir öğenin konumunu gösteren bir yineleyici döndürür.|
|[get_allocator](#get_allocator)|Bir kopyasını döndürür `allocator` harita oluşturmak için kullanılan nesne.|
|[Ekle](#insert)|Bir eşlemdeki bir öğeyi veya öğe aralığını belirtilen konumda ekler.|
|[key_comp](#key_comp)|Bir eşlem içindeki anahtarları sıralamak için kullanılan karşılaştırma nesnesinin bir kopyasını döndürür.|
|[lower_bound](#lower_bound)|Bir yineleyiciyi belirtilen anahtardan daha büyük veya ona eşit bir anahtar değere sahip bir eşlem içindeki ilk öğeye döndürür.|
|[max_size](#max_size)|Eşlem öğesinin maksimum uzunluğunu döndürür.|
|[rbegin](#rbegin)|Ters döndürülmüş eşlem içindeki ilk öğeyi gösteren bir yineleyici döndürür.|
|[rend](#rend)|Ters döndürülmüş bir eşlem içindeki son öğenin ardındaki konumu gösteren bir yineleyici döndürür.|
|[Boyutu](#size)|Eşlem içindeki öğelerin sayısını döndürür.|
|[değiştirme](#swap)|İki eşlemin öğelerini birbiriyle değiştirir.|
|[upper_bound](#upper_bound)|Bir yineleyiciyi belirtilen anahtardan daha büyükse bir anahtar değere sahip bir eşlem içindeki ilk öğeye döndürür.|
|[value_comp](#value_comp)|Bir eşlem içindeki öğe değerlerini sıralamak için kullanılan karşılaştırma nesnesinin bir kopyasını alır.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[işleci&#91;&#93;](#op_at)|Belirtilen bir anahtar değere sahip bir eşleme bir öğe ekler.|
|[operator=](#op_eq)|Bir eşlemin öğelerini başka bir eşlem kopyasıyla değiştirir.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<harita >

**Namespace:** std

## <a name="allocator_type"></a>  Map::allocator_type

Harita nesnesi için ayırıcı sınıf temsil eden tür.

```cpp
typedef Allocator allocator_type;
```

### <a name="example"></a>Örnek

Örneğin bakın [get_allocator](#get_allocator) kullanan bir örnek için `allocator_type`.

## <a name="at"></a>  Map::AT

Belirtilen anahtar değere sahip bir öğe bulur.

```cpp
Type& at(const Key& key);

const Type& at(const Key& key) const;
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|-|-|
|Parametre|Açıklama|
|*Anahtarı*|Bulunacak anahtar değer.|

### <a name="return-value"></a>Dönüş Değeri

Bulunan elemanın veri değerine başvuru.

### <a name="remarks"></a>Açıklamalar

Bağımsız değişken anahtarı değeri bulunamazsa sonra işlevin sınıfın bir nesnesi atar [out_of_range sınıfı](../standard-library/out-of-range-class.md).

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

## <a name="begin"></a>  Map::Begin

Eşlem içindeki ilk öğeyi ele alan bir yineleyici döndürür.

```cpp
const_iterator begin() const;

iterator begin();
```

### <a name="return-value"></a>Dönüş Değeri

Harita veya sonra gelen konumu adresleyen doldurulacak bir harita içindeki ilk öğeyi ele alan bir çift yönlü yineleyici.

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

## <a name="cbegin"></a>  Map::cbegin

Döndürür bir **const** konuma bir aralıktaki son öğeyi ele alan bir yineleyici.

```cpp
const_iterator cbegin() const;
```

### <a name="return-value"></a>Dönüş Değeri

A **const** aralığı veya konuma boş bir aralığın ilk öğeyi ele alan çift yönlü yineleyici (boş bir aralık için `cbegin() == cend()`).

### <a name="remarks"></a>Açıklamalar

Dönüş değeri ile `cbegin`, aralıktaki öğeler değiştirilemez.

Bu üye işlevi yerine kullanabileceğiniz `begin()` üye işlev dönüş değeri olacağını garanti etmek için `const_iterator`. Genellikle birlikte kullanılır [otomatik](../cpp/auto-cpp.md) kesinti anahtar sözcüğü, aşağıdaki örnekte gösterildiği gibi yazın. Örnekte, göz önünde bulundurun `Container` değiştirilebilir (olmayan **const**) destekleyen herhangi bir türdeki kapsayıcı `begin()` ve `cbegin()`.

```cpp
auto i1 = Container.begin();
// i1 is Container<T>::iterator
auto i2 = Container.cbegin();

// i2 is Container<T>::const_iterator
```

## <a name="cend"></a>  Map::cend

Döndürür bir **const** konuma bir aralıktaki son öğeyi ele alan bir yineleyici.

```cpp
const_iterator cend() const;
```

### <a name="return-value"></a>Dönüş Değeri

A **const** aralığın sonunu yalnızca çift yönlü erişim yineleyicisi.

### <a name="remarks"></a>Açıklamalar

`cend` bir yineleyicinin kendi aralığının sonunu geçmediğini sınamak için kullanılır.

Bu üye işlevi yerine kullanabileceğiniz `end()` üye işlev dönüş değeri olacağını garanti etmek için `const_iterator`. Genellikle birlikte kullanılır [otomatik](../cpp/auto-cpp.md) kesinti anahtar sözcüğü, aşağıdaki örnekte gösterildiği gibi yazın. Örnekte, göz önünde bulundurun `Container` değiştirilebilir (olmayan **const**) destekleyen herhangi bir türdeki kapsayıcı `end()` ve `cend()`.

```cpp
auto i1 = Container.end();
// i1 is Container<T>::iterator
auto i2 = Container.cend();

// i2 is Container<T>::const_iterator
```

Tarafından döndürülen değer `cend` kaldırılmamalıdır.

## <a name="clear"></a>  Map::Clear

Eşlemin tüm öğelerini siler.

```cpp
void clear();
```

### <a name="example"></a>Örnek

Aşağıdaki örnek, map::clear üye işlevinin kullanımını gösterir.

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

## <a name="const_iterator"></a>  Map::const_iterator

Çift yönlü bir yineleyici sağlayan tür okuma bir **const** haritadaki öğe.

```cpp
typedef implementation-defined const_iterator;
```

### <a name="remarks"></a>Açıklamalar

Bir tür `const_iterator` bir öğenin değerini değiştirmek için kullanılamaz.

`const_iterator` Nesnelerin olan öğeler için harita noktaları tarafından tanımlanan [value_type](#value_type), diğer bir deyişle tür `pair` \< **constKey**, **türü**> , olan ilk üye öğe anahtarıdır ve ikinci öğe tarafından tutulan bir eşlenmiş veri üyesi olan.

Başvurulacak bir `const_iterator` `cIter` bir eşlem içindeki bir öğeyi işaret eden, kullanın `->` işleci.

Öğenin anahtarının değerini erişmek için `cIter`  ->  **ilk**, eşit olduğu (\* `cIter`). **İlk**.

Eşlenmiş veri öğesi için değeri erişmek için `cIter`  ->  **ikinci**, eşit olduğu (\* `cIter`). **İkinci**.

### <a name="example"></a>Örnek

Örneğin bakın [başlamak](#begin) kullanan bir örnek için `const_iterator`.

## <a name="const_pointer"></a>  Map::const_pointer

Bir işaretçi sağlayan bir tür bir **const** bir eşlem içindeki öğe.

```cpp
typedef typename allocator_type::const_pointer const_pointer;
```

### <a name="remarks"></a>Açıklamalar

Bir tür `const_pointer` bir öğenin değerini değiştirmek için kullanılamaz.

Çoğu durumda bir [yineleyici](#iterator) harita nesnesindeki öğelere erişmek için kullanılmalıdır.

## <a name="const_reference"></a>  Map::const_reference

Bir başvuru sağlayan bir tür bir **const** okumak ve gerçekleştirmek için bir eşlem içinde depolanan öğenin **const** operations.

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

## <a name="const_reverse_iterator"></a>  Map::const_reverse_iterator

Çift yönlü bir yineleyici sağlayan tür herhangi okuma **const** haritadaki öğe.

```cpp
typedef std::reverse_iterator<const_iterator> const_reverse_iterator;
```

### <a name="remarks"></a>Açıklamalar

Bir tür `const_reverse_iterator` kullanın ters haritada yinelemek için ve bir öğenin değerini değiştiremezsiniz.

`const_reverse_iterator` Nesnelerin olan öğeler için harita noktaları tarafından tanımlanan [value_type](#value_type), diğer bir deyişle tür `pair<const Key, Type>`olan ilk üye öğe anahtarıdır ve ikinci öğe tarafından tutulan eşlenen datum üyesidir.

Başvurulacak bir `const_reverse_iterator crIter` bir eşlem içindeki bir öğeyi işaret eden, kullanın `->` işleci.

Öğenin anahtarının değerini erişmek için `crIter`  ->  **ilk**, eşit olduğu (\* `crIter`). **İlk**.

Eşlenmiş veri öğesi için değeri erişmek için `crIter`  ->  **ikinci**, eşit olduğu (\* `crIter`). **İlk**.

### <a name="example"></a>Örnek

Örneğin bakın [rend](#rend) bildirme ve kullanma konusunda bir örnek için `const_reverse_iterator`.

## <a name="count"></a>  Map::Count

Anahtarı parametre tarafından belirtilen bir anahtarla eşleşen bir eşlem öğelerin sayısını döndürür.

```cpp
size_type count(const Key& key) const;
```

### <a name="parameters"></a>Parametreler

*Anahtarı*<br/>
Öğeleri eşlemden eşleştirilmesi için anahtar değeri.

### <a name="return-value"></a>Dönüş Değeri

1 eşleme sıralama anahtarı parametresi anahtarla eşleşen bir öğe içeriyorsa; 0 eşleme bir öğe ile eşleşen bir anahtar içermiyor.

### <a name="remarks"></a>Açıklamalar

Üye işlevi öğelerin sayısını döndürür *x* aralığında

[ `lower_bound` (_ *Anahtarı* ), `upper_bound` (\_ *anahtarı* ))

0 veya 1 benzersiz bir ilişkilendirilebilir kapsayıcıdır eşlemesi, söz konusu olduğunda olduğu.

### <a name="example"></a>Örnek

Aşağıdaki örnek, map::count üye işlevinin kullanımını gösterir.

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

## <a name="crbegin"></a>  Map::crbegin

Ters Döndürülmüş eşlem içindeki ilk öğeyi ele alan sabit bir yineleyici döndürür.

```cpp
const_reverse_iterator crbegin() const;
```

### <a name="return-value"></a>Dönüş Değeri

Ters çevrilen bir ilk öğeyi ele alan çift yönlü yineleyici bir const [harita](../standard-library/map-class.md) veya ne ters çevrilmeyen içindeki son öğeyi adresleyen `map`.

### <a name="remarks"></a>Açıklamalar

`crbegin` kullanılan bir ters ile `map` gibi [başlamak](#begin) ile kullanılan bir `map`.

Dönüş değeri ile `crbegin`, `map` nesnesi değiştirilemez

`crbegin` yinelemek için kullanılabilecek bir `map` geriye doğru.

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

## <a name="crend"></a>  Map::crend

Ters Döndürülmüş eşlem içindeki son öğeyi takip eden konumu ele alan sabit bir yineleyici döndürür.

```cpp
const_reverse_iterator crend() const;
```

### <a name="return-value"></a>Dönüş Değeri

Ters çevrilen bir içindeki son öğeden sonra gelen konumu ele çift yönlü yineleyici bir const [harita](../standard-library/map-class.md) (ilk öğeyi çevrilmeyen önce gelen konum `map`).

### <a name="remarks"></a>Açıklamalar

`crend` Ters döndürülmüş bir eşlem ile kullanılan gibi [son](#end) ile kullanılan bir `map`.

Dönüş değeri ile `crend`, `map` nesnesi değiştirilemez.

`crend` olup ters yineleyici sonuna ulaşıp ulaşmadığını test etmek için kullanılan kendi `map`.

Tarafından döndürülen değer `crend` kaldırılmamalıdır.

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

## <a name="difference_type"></a>  Map::difference_type

Yineleyiciler tarafından gösterilen öğeler arasındaki bir aralıktaki eşlemin öğelerinin sayısını temsil etmek için kullanılabilen işaretli bir tamsayı türü.

```cpp
typedef allocator_type::difference_type difference_type;
```

### <a name="remarks"></a>Açıklamalar

`difference_type` Türü çıkarma veya kapsayıcının yineleyiciler artan döndürülür. `difference_type` Genellikle aralık içindeki öğelerin sayısını temsil etmek için kullanılan *[Soyadı)* yineleyici arasındaki `first` ve `last`, işaret ettiği öğe içeren `first` ve aralığı öğeleri kadar ancak dahil değil, öğe tarafından işaret edilen `last`.

Ancak dikkat `difference_type` kümesi, yineleyici arasındaki çıkarma yalnızca gibi ters çevrilebilir kapsayıcıları tarafından desteklenen çift yönlü Yineleyicilerin sınıfında içeren bir giriş yineleyici gereksinimlerini karşılayan tüm yineleyiciler için kullanılabilir vektör gibi bir rastgele erişim kapsayıcı tarafından sağlanan rasgele erişim yineleyicileri tarafından desteklenmiyor.

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

## <a name="emplace"></a>  Map::emplace

Bir haritayı (hiçbir kopyalama veya taşıma işlemleri gerçekleştirilir) yerinde oluşturulmuş bir öğe ekler.

```cpp
template <class... Args>
pair<iterator, bool>
emplace(
    Args&&... args);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|-|-|
|Parametre|Açıklama|
|*bağımsız değişken*|Bir öğenin değerini eşdeğer sıralı bir öğe içermiyorsa eşlemeye eklenecek oluşturmak için iletilen bağımsız değişkenler.|

### <a name="return-value"></a>Dönüş Değeri

A [çifti](../standard-library/pair-structure.md) olan **bool** bileşendir ekleme yaptıysanız true ve false harita sıralama, eşdeğer değerinin bir öğe içeriyorsa. Yineleyici bileşeni dönüş değeri çiftinin yeni eklenen öğeye işaret ederse **bool** bileşendir true veya var olan öğeye varsa **bool** bileşen değer false.

Yineleyici bileşeni erişmek için bir `pair` `pr`, kullanın `pr.first`; başvurabilir, kullanın `*pr.first`. Erişim için **bool** bileşeni, kullanım `pr.second`. Bu makaledeki örnek kod örneği için bkz.

### <a name="remarks"></a>Açıklamalar

Yineleyiciler ya da başvuruları, bu işlev tarafından geçersiz kılınır.

Yerleştirme sırasında bir özel durum oluşturulursa, kapsayıcının durumu değiştirilmez.

[Value_type](#value_type) böylece bir öğenin değerini sıralı bir çift anahtar değerine eşit olan ilk bileşen ve saniye bileşenini öğenin veri değerine eşit olan bir çift öğesidir.

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

## <a name="emplace_hint"></a>  Map::emplace_hint

(Hiçbir kopyalama veya taşıma işlemleri gerçekleştirilir) bir yerleşim ipucuyla birlikte yerinde oluşturulmuş bir öğe ekler.

```cpp
template <class... Args>
iterator emplace_hint(
    const_iterator where,
    Args&&... args);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|-|-|
|Parametre|Açıklama|
|*bağımsız değişken*|Harita, bu öğeyi zaten içeriyor veya zaten anahtarı bir öğe içeriyorsa sürece daha genel olarak, eşdeğer sıralanır sürece eşlemeye eklenecek bir öğe oluşturmak için iletilen bağımsız değişkenler.|
|*Burada*|Doğru ekleme noktasını için aramaya başlamak için bir yerde. (Bu noktanın hemen önceyse *burada*, ekleme Logaritmik süre yerine amorti edilmiş sabit zaman meydana gelebilir.)|

### <a name="return-value"></a>Dönüş Değeri

Yeni eklenen öğeye bir yineleyici.

Öğe zaten var olduğundan ekleme başarısız olursa bir yineleyici anahtarıyla var olan öğeyi döndürür.

### <a name="remarks"></a>Açıklamalar

Yineleyiciler ya da başvuruları, bu işlev tarafından geçersiz kılınır.

Yerleştirme sırasında bir özel durum oluşturulursa, kapsayıcının durumu değiştirilmez.

[Value_type](#value_type) böylece bir öğenin değerini sıralı bir çift anahtar değerine eşit olan ilk bileşen ve saniye bileşenini öğenin veri değerine eşit olan bir çift öğesidir.

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

## <a name="empty"></a>  Map::empty

Bir harita boş olup olmadığını sınar.

```cpp
bool empty() const;
```

### <a name="return-value"></a>Dönüş Değeri

**doğru** eşlem boşsa; **false** eşleme boş ise.

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

## <a name="end"></a>  Map::End

past-the-end yineleyici döndürür.

```cpp
const_iterator end() const;

iterator end();
```

### <a name="return-value"></a>Dönüş Değeri

Past--end yineleyici. Harita boş ise, `map::end() == map::begin()`.

### <a name="remarks"></a>Açıklamalar

`end` bir yineleyicinin kendi eşleme sonuna geçmediğini sınamak için kullanılır.

Tarafından döndürülen değer `end` kaldırılmamalıdır.

Kod örneği için bkz: [map::find](#find).

## <a name="equal_range"></a>  Map::equal_range

Yineleyicilerin bir çiftini temsil eden döndürür [lower_bound](#lower_bound) anahtarının ve [upper_bound](#upper_bound) anahtarı.

```cpp
pair <const_iterator, const_iterator> equal_range (const Key& key) const;

pair <iterator, iterator> equal_range (const Key& key);
```

### <a name="parameters"></a>Parametreler

*Anahtarı*<br/>
Bir öğenin Aranan eşlemesinden sıralama anahtarı ile Karşılaştırılacak bağımsız değişken anahtar değeri.

### <a name="return-value"></a>Dönüş Değeri

Bir çiftin ilk yineleyicisi erişmeye `pr` üye işlevi tarafından döndürülen, kullanın `pr`. **İlk**ve alt sınır yineleyicinin başvuru kaldırma için \*( `pr`. **İlk**). Bir çiftin ikinci yineleyicisi erişmeye `pr` üye işlevi tarafından döndürülen, kullanın `pr`. **İkinci**ve üst sınır yineleyicinin başvuru kaldırma için \*( `pr`. **İkinci**).

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

## <a name="erase"></a>  Map::ERASE

Bir öğenin veya öğelerin aralığını belirtilen konumlardan bir eşlem içindeki kaldırır veya belirtilen bir anahtarla eşleşen öğeleri kaldırır.

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

*Burada*<br/>
Kaldırılacak öğenin konumu.

*ilk*<br/>
Kaldırılacak ilk öğenin konumu.

*Son*<br/>
Kaldırılacak yalnızca son öğenin ötesinde konumu.

*Key*<br/>
Kaldırılacak öğe anahtar değeri.

### <a name="return-value"></a>Dönüş Değeri

İlk iki üye işlevleri için çift yönlü bir yineleyici, kaldırılan herhangi bir öğe veya böyle bir öğe yoksa eşleme sonuna bir öğeyi ilk öğeyi belirtir.

Üye işlevi için üçüncü eşleme kaldırılmış olan öğelerin sayısını döndürür.

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

    // Fill in some data to test with, one at a time, using an intializer list
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

## <a name="find"></a>  Map::Find

Belirtilen anahtara denk bir anahtara sahip bir eşlem içindeki bir öğenin konumunu gösteren bir yineleyici döndürür.

```cpp
iterator find(const Key& key);

const_iterator find(const Key& key) const;
```

### <a name="parameters"></a>Parametreler

*Anahtarı*<br/>
Bir öğenin Aranan eşlemesinden sıralama anahtarı tarafından eşleştirilecek anahtar değeri.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen anahtara sahip bir öğenin konumunu veya sonra gelen konumu adresleyen bir eşlem içindeki son öğenin başvuran bir yineleyici (`map::end()`) anahtar için bir eşleşme varsa.

### <a name="remarks"></a>Açıklamalar

Üye işlevi, bir eşlem içindeki bir öğeyi sıralama anahtarı başvuran bir yineleyici bağımsız değişken anahtarı altındaki bir comparability ilişkisi küçüktür göre sıralama sevk eden ikili bir koşula eşdeğerdir döndürür.

Varsa dönüş değerinin `find` atanan bir `const_iterator`, harita nesnesi değiştirilemez. Varsa dönüş değerinin `find` atanan bir `iterator`, harita nesnesi değiştirilebilir

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

## <a name="get_allocator"></a>  Map::get_allocator

Eşlem oluşturmak için kullanılan ayırıcı nesnesinin bir kopyasını döndürür.

```cpp
allocator_type get_allocator() const;
```

### <a name="return-value"></a>Dönüş Değeri

Eşleme tarafından kullanılan ayırıcı.

### <a name="remarks"></a>Açıklamalar

Ayırıcılar eşlem sınıfı için sınıf depolama nasıl yönettiğini belirtin. C++ Standart Kitaplığı kapsayıcı sınıfları ile sağlanan varsayılan ayırıcılar çoğu programlama ihtiyaçları için yeterli. Yazma ve kendi allocator sınıfı kullanarak bir Gelişmiş C++ konudur.

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

## <a name="insert"></a>  Map::insert

Bir öğenin veya öğelerin aralığını bir eşlemeye ekler.

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
|Parametre|Açıklama|
|*VAL*|Anahtarı eşdeğer sıralı bir öğe içermiyorsa eşlemeye eklenecek bir öğenin değeri.|
|*Burada*|Doğru ekleme noktasını için aramaya başlamak için bir yerde. (Bu noktanın hemen önceyse *burada*, ekleme Logaritmik süre yerine amorti edilmiş sabit zaman meydana gelebilir.)|
|*ValTy*|Eşleme öğesi oluşturmak için kullanabileceğiniz bağımsız değişken türü belirten bir şablon parametresi [value_type](#value_type)ve mükemmel ileten *Val* bağımsız değişken olarak.|
|*ilk*|Kopyalanacak ilk öğenin konumu.|
|*Son*|Kopyalanacak son öğenin ötesinde konumu.|
|*Inputıterator*|Gereksinimlerini karşılayan şablonu işlev bağımsız değişkeni bir [giriş yineleyici](../standard-library/input-iterator-tag-struct.md) oluşturmak için kullanılan bir tür öğelerine işaret eden [value_type](#value_type) nesneleri.|
|*IList*|[İnitializer_list](../standard-library/initializer-list.md) öğeleri kopyalanacak.|

### <a name="return-value"></a>Dönüş Değeri

Tek öğeli üye işlevleri (1) ve (2) iade bir [çifti](../standard-library/pair-structure.md) olan **bool** bileşendir ekleme yaptıysanız true ve false harita anahtarı eşdeğer bir değer olan bir öğe içeriyorsa sıralamada. Yineleyici bileşeni dönüş değeri çiftinin yeni eklenen öğeye işaret ederse **bool** bileşendir true veya var olan öğeye varsa **bool** bileşen değer false.

İpucu ile tek öğe üye işlevleri, (3) ve (4), yeni bir öğe eşlemeye eklenen burada veya eşdeğer bir anahtara sahip bir öğe zaten var olan öğeye varsa konuma gösteren bir yineleyici döndürür.

### <a name="remarks"></a>Açıklamalar

Hiçbir yineleyiciler, işaretçiler veya başvurular, bu işlev tarafından geçersiz kılınır.

Bir özel durum oluşturulursa, yeni bir öğe ekleme sırasında kapsayıcının durumu değiştirilmez. Bir özel durum oluşturulursa, birden çok öğe ekleme sırasında kapsayıcı belirtilmeyen ancak geçerli bir durumda bırakılır.

Yineleyici bileşeni erişmek için bir `pair` `pr` kullanın, tek öğeli üye işlevleri tarafından döndürülen `pr.first`; döndürülen çiftin içinde yineleyicinin başvuru kaldırma, kullanın `*pr.first`, size bir öğe sağlar. Erişim için **bool** bileşeni, kullanım `pr.second`. Bu makaledeki örnek kod örneği için bkz.

[Value_type](#value_type) eşlemesini yanı sıra, kapsayıcıya ait bir tür tanımı, kapsayıcısıdır `map<K, V>::value_type` olduğu `pair<const K, V>`. Bir öğenin ilk bileşen anahtar değerine eşittir ve ikinci bileşen öğenin veri değerine eşit olan sıralı bir çift değerdir.

Aralık üye işlevi (5) aralığında bir yineleyici tarafından ele alınan her öğe için karşılık gelen bir harita öğe değerleri dizisi ekler `[First, Last)`; bu nedenle `Last` takılı. Kapsayıcı üye işlevi `end()` kapsayıcıdaki son öğeden hemen sonra konuma başvuran — Örneğin, deyim `m.insert(v.begin(), v.end());` tüm öğeleri ekleme girişiminde `v` içine `m`. Yalnızca benzersiz değerler aralığında olan öğeler eklenir; Yinelenen göz ardı edilir. Hangi öğelerin reddedilir gözlemlemek için tek öğeli sürümleri kullanın `insert`.

Başlatıcı listesinde üye işlev (6) kullanan bir [initializer_list](../standard-library/initializer-list.md) öğeleri eşlemeye kopyalamak için.

Yerinde oluşturulmuş bir öğe ekleme — diğer bir deyişle, hiçbir kopyalama veya taşıma işlemleri gerçekleştirilir — bkz [map::emplace](#emplace) ve [map::emplace_hint](#emplace_hint).

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

## <a name="iterator"></a>  Map::iterator

Okuyabilen veya değiştirebilen bir eşlem içindeki herhangi bir öğeye çift yönlü yineleyiciler sağlayan tür.

```cpp
typedef implementation-defined iterator;
```

### <a name="remarks"></a>Açıklamalar

Harita noktalarına nesnelerin olan öğeler tarafından tanımlanan yineleyici [value_type](#value_type), yani türü `pair<const Key, Type>`olan ilk üye öğe anahtarıdır ve ikinci öğe tarafından tutulan eşlenen datum üyesidir.

Bir yineleyicinin başvuru kaldırma için *Iter* bir eşlem içindeki bir öğeyi işaret eden, kullanın `->` işleci.

Öğenin anahtarının değerini erişmek için `Iter->first`, eşdeğer olan `(*Iter).first`. Eşlenmiş veri öğesi için değeri erişmek için `Iter->second`, eşdeğer olan `(*Iter).second`.

### <a name="example"></a>Örnek

Örneğin bakın [başlamak](#begin) bildirme ve kullanma konusunda bir örnek için `iterator`.

## <a name="key_comp"></a>  Map::key_comp

Bir eşlem içindeki anahtarları sıralamak için kullanılan karşılaştırma nesnesinin bir kopyasını alır.

```cpp
key_compare key_comp() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir harita alt öğeleri düzenlemek amacıyla kullanan bir işlev nesnesi döndürür.

### <a name="remarks"></a>Açıklamalar

Depolanan nesne üyesi işlevini tanımlar.

`bool operator(const Key& left, const Key& right);`

döndüren **true** varsa `left` önündeki ve eşit değildir `right` sıralama düzeninde.

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

## <a name="key_compare"></a>  Map::key_compare

Eşlem içindeki iki öğenin göreli sırasını belirlemek için iki sıralama anahtarını karşılaştıran işlev nesnesi sağlayan tür.

```cpp
typedef Traits key_compare;
```

### <a name="remarks"></a>Açıklamalar

`key_compare` Şablon parametresi için bir eşanlamlı olduğu *nitelikler*.

Daha fazla bilgi için *nitelikler* bkz [map sınıfı](../standard-library/map-class.md) konu.

### <a name="example"></a>Örnek

Örneğin bakın [key_comp](#key_comp) bildirme ve kullanma konusunda bir örnek için `key_compare`.

## <a name="key_type"></a>  Map::key_type

Eşlemin her öğesinde depolanan sıralama anahtarı tanımlayan tür.

```cpp
typedef Key key_type;
```

### <a name="remarks"></a>Açıklamalar

`key_type` Şablon parametresi için bir eşanlamlı olduğu *anahtar*.

Daha fazla bilgi için *anahtarı*, Açıklamalar bölümüne bakın [map sınıfı](../standard-library/map-class.md) konu.

### <a name="example"></a>Örnek

Örneğin bakın [value_type](#value_type) bildirme ve kullanma konusunda bir örnek için `key_type`.

## <a name="lower_bound"></a>  Map::lower_bound

Bir yineleyiciyi belirtilen anahtardan daha büyük veya ona eşit bir anahtar değere sahip bir eşlem içindeki ilk öğeye döndürür.

```cpp
iterator lower_bound(const Key& key);

const_iterator lower_bound(const Key& key) const;
```

### <a name="parameters"></a>Parametreler

*Anahtarı*<br/>
Bir öğenin Aranan eşlemesinden sıralama anahtarı ile Karşılaştırılacak bağımsız değişken anahtar değeri.

### <a name="return-value"></a>Dönüş Değeri

Bir `iterator` veya `const_iterator` adresleri anahtar için bağımsız değişken anahtardan daha büyük veya ona eşit olan veya hiçbir eşlem içindeki son öğeyi takip eden konumu ele bir anahtar ile eşleştiğinden emin bir eşlem içindeki bir öğenin konumunu bulunamadı.

Varsa dönüş değerinin `lower_bound` atanan bir `const_iterator`, harita nesnesi değiştirilemez. Varsa dönüş değerinin `lower_bound` atanan bir `iterator`, harita nesnesi değiştirilebilir.

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

## <a name="map"></a>  Map::Map

Boş veya bir kopyası tüm veya başka bir eşlemin bir parçası olan bir harita oluşturur.

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

|Parametre|Açıklama|
|-|-|
|Parametre|Açıklama|
|*Al*|Varsayılan olarak bu harita nesnesi için kullanılacak depolama ayırıcı sınıf `Allocator`.|
|*Comp*|Karşılaştırma işlevi türü `const Traits` varsayılan olarak haritada öğeleri sıralamak için kullanılan `hash_compare`.|
|*sağ*|Oluşturulan kümesi kopyası olacak olduğu eşlemesi.|
|*ilk*|Kopyalanacak öğe aralığındaki ilk öğenin konumu.|
|*Son*|Kopyalanacak öğe aralığının dışındaki ilk öğenin konumu.|
|*IList*|İçerdiği öğeleri kopyalanacak olan initializer_list.|

### <a name="remarks"></a>Açıklamalar

Tüm Oluşturucular, eşleme için bellek depolama yönetir ve bu daha sonra döndürülmesi çağırarak ayırıcı nesnesi türü depolamak [get_allocator](#get_allocator). Allocator parametresi, sınıf bildirimleri ve diğer ayırıcılar yerine kullanılan ön işleme makroları genellikle atlanır.

Tüm Oluşturucular, eşleşme başlatır.

Tüm oluşturucular bir işlev nesnesi harita anahtarları arasında bir sıralamayı oluşturmak için kullanılan ve, daha sonra döndürülmesi çağırarak türü nitelikler depolamak [key_comp](#key_comp).

İlk üç Oluşturucular, bir boş ilk eşleme, ikinci belirtin karşılaştırma işlevinin türü belirtme (*kompozisyonu*) öğeleri ve üçüncüsü sırasını açıkça oluşturmada kullanılacak ayırıcı belirtme yazın ( *Al*) kullanılacak. Anahtar sözcük **açık** otomatik tür dönüştürme belirli türdeki bastırır.

Dördüncü Oluşturucu haritayı bir kopyasını belirtir *sağ*.

Beşinci Oluşturucu taşıyarak harita bir kopyasını belirtir. *sağ*.

Altıncı, yedinci ve sekizinci oluşturucular üyeler kopyalamak bir initializer_list kullanın.

Sonraki üç oluşturucular aralığını kopyalamaktadır `[First, Last)` sınıfın karşılaştırma işlevinin türü belirtilirken explicitness artan eşleme `Traits` ve ayırıcı.

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
    // function of geater than, then insert 2 elements
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

## <a name="mapped_type"></a>  Map::mapped_type

Bir eşlem içinde depolanan verileri temsil eden tür.

```cpp
typedef Type mapped_type;
```

### <a name="remarks"></a>Açıklamalar

Türü `mapped_type` sınıfın eşanlamlıdır *türü* şablon parametresi.

Daha fazla bilgi için *türü* bkz [map sınıfı](../standard-library/map-class.md) konu.

### <a name="example"></a>Örnek

Örneğin bakın [value_type](#value_type) bildirme ve kullanma konusunda bir örnek için `mapped_type`.

## <a name="max_size"></a>  Map::max_size

Eşlem öğesinin maksimum uzunluğunu döndürür.

```cpp
size_type max_size() const;
```

### <a name="return-value"></a>Dönüş Değeri

Haritanın maksimum olası uzunluğu.

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

## <a name="op_at"></a>  Map::operator]

Belirtilen bir anahtar değere sahip bir eşleme bir öğe ekler.

```cpp
Type& operator[](const Key& key);

Type& operator[](Key&& key);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|-|-|
|Parametre|Açıklama|
|*Anahtarı*|Eklenecek öğenin anahtar değeri.|

### <a name="return-value"></a>Dönüş Değeri

Eklenen öğenin veri değerine başvuru.

### <a name="remarks"></a>Açıklamalar

Bağımsız değişken anahtar değeri bulunamazsa, değer veri türünün varsayılan değeriyle birlikte eklenir.

`operator[]` öğe bir eşlemeye eklemek için kullanılabilir `m` kullanarak `m[ key] = DataValue;` burada `DataValue` değeri `mapped_type` öğenin anahtar değeri ile *anahtar*.

Kullanırken `operator[]` öğeleri eklemek için döndürülen başvuru ekleme önceden varolan bir öğeyi değiştirmek veya yeni bir tane oluşturmak anlamına gelmez. Üye işlevleri [Bul](#find) ve [Ekle](#insert) belirtilen anahtara sahip bir öğe zaten bir ekleme mevcut olup olmadığını belirlemek için kullanılabilir.

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

## <a name="op_eq"></a>  Map::operator =

Bir eşlemin öğelerini başka bir eşlem kopyasıyla değiştirir.

```cpp
map& operator=(const map& right);

map& operator=(map&& right);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|-|-|
|Parametre|Açıklama|
|*sağ*|[Harita](../standard-library/map-class.md) içine kopyalanan `map`.|

### <a name="remarks"></a>Açıklamalar

Var olan tüm öğeleri silme sonra bir `map`, `operator=` kopyalar veya içeriğini hareket *doğru* eşlem içine.

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

## <a name="pointer"></a>  Map::pointer

Bir eşlem içindeki bir öğeye işaretçi sağlayan bir tür.

```cpp
typedef typename allocator_type::pointer pointer;
```

### <a name="remarks"></a>Açıklamalar

Bir tür `pointer` bir öğenin değerini değiştirmek için kullanılabilir.

Çoğu durumda bir [yineleyici](#iterator) harita nesnesindeki öğelere erişmek için kullanılmalıdır.

## <a name="rbegin"></a>  Map::rbegin

Ters Döndürülmüş eşlem içindeki ilk öğeyi adresleyen bir yineleyici döndürür.

```cpp
const_reverse_iterator rbegin() const;

reverse_iterator rbegin();
```

### <a name="return-value"></a>Dönüş Değeri

Ters Döndürülmüş eşlem içindeki ilk öğeyi ele alan veya ne ters çevrilmeyen eşlem içindeki son öğeyi adresleyen ters iki yönlü yineleyici.

### <a name="remarks"></a>Açıklamalar

`rbegin` Ters döndürülmüş bir eşlem ile kullanılan gibi [başlamak](#begin) sahip bir eşleme kullanılır.

Varsa dönüş değeri `rbegin` atanan bir `const_reverse_iterator`, sonra da eşleme nesnesi değiştirilemez. Varsa dönüş değeri `rbegin` atanan bir `reverse_iterator`, sonra eşleme nesnesi değiştirilebilir.

`rbegin` bir eşleme geriye doğru gezinmek için kullanılabilir.

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

## <a name="reference"></a>  Map::Reference

Bir eşlem içinde depolan bir öğeye başvuru sağlayan bir tür.

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

## <a name="rend"></a>  Map::rend

Ters Döndürülmüş eşlem içindeki son öğeyi takip eden konumu adresleyen bir yineleyici döndürür.

```cpp
const_reverse_iterator rend() const;

reverse_iterator rend();
```

### <a name="return-value"></a>Dönüş Değeri

Konumu (ters çevrilmeyen haritada ilk öğeyi önce gelen konum) ters Döndürülmüş eşlem içindeki son öğeyi adresleyen ters iki yönlü yineleyici.

### <a name="remarks"></a>Açıklamalar

`rend` Ters döndürülmüş bir eşlem ile kullanılan gibi [son](#end) sahip bir eşleme kullanılır.

Varsa dönüş değeri `rend` atanan bir `const_reverse_iterator`, sonra da eşleme nesnesi değiştirilemez. Varsa dönüş değeri `rend` atanan bir `reverse_iterator`, sonra eşleme nesnesi değiştirilebilir.

`rend` olup ters yineleyici kendi eşleme sonuna ulaşıp ulaşmadığını test etmek için kullanılabilir.

Tarafından döndürülen değer `rend` kaldırılmamalıdır.

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

## <a name="reverse_iterator"></a>  Map::reverse_iterator

Okuyabilen veya değiştirebilen döndürülmüş bir eşlem içindeki bir öğeyi çift yönlü yineleyiciler sağlayan tür.

```cpp
typedef std::reverse_iterator<iterator> reverse_iterator;
```

### <a name="remarks"></a>Açıklamalar

Bir tür `reverse_iterator` kullanın ters haritada yinelemek için ve bir öğenin değerini değiştiremezsiniz.

`reverse_iterator` Nesnelerin olan öğeler için harita noktaları tarafından tanımlanan [value_type](#value_type), diğer bir deyişle tür `pair<const Key, Type>`olan ilk üye öğe anahtarıdır ve ikinci öğe tarafından tutulan eşlenen datum üyesidir.

Başvurulacak bir `reverse_iterator` *rIter* bir eşlem içindeki bir öğeyi işaret eden, kullanın `->` işleci.

Öğenin anahtarının değerini erişmek için `rIter`  ->  **ilk**, eşit olduğu (\* `rIter`). **İlk**. Eşlenmiş veri öğesi için değeri erişmek için `rIter`  ->  **ikinci**, eşit olduğu (\* `rIter`). **İlk**.

### <a name="example"></a>Örnek

Örneğin bakın [rbegin](#rbegin) bildirme ve kullanma konusunda bir örnek için `reverse_iterator`.

## <a name="size"></a>  Map::size

Eşlem içindeki öğelerin sayısını döndürür.

```cpp
size_type size() const;
```

### <a name="return-value"></a>Dönüş Değeri

Haritanın geçerli uzunluğu.

### <a name="example"></a>Örnek

Aşağıdaki örnek, map::size üye işlevinin kullanımını gösterir.

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

## <a name="size_type"></a>  Map::size_type

Bir eşlem içindeki öğelerin sayısını temsil edebilen bir işaretsiz tamsayı türü.

```cpp
typedef typename allocator_type::size_type size_type;
```

### <a name="example"></a>Örnek

Örneğin bakın [boyutu](#size) bildirme ve kullanma konusunda bir örnek için `size_type`.

## <a name="swap"></a>  Map::Swap

İki eşlemin öğelerini birbiriyle değiştirir.

```cpp
void swap(
    map<Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*sağ*<br/>
Hedef haritayla değiştirilecek öğeleri sağlayan bağımsız değişken eşleme.

### <a name="remarks"></a>Açıklamalar

Üye işlev hiçbir başvurular, işaretçiler veya öğeleri değiştirilen iki haritalar öğelerini belirlemek yineleyicileri geçersiz kılar.

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

## <a name="upper_bound"></a>  Map::upper_bound

Bir anahtar ile belirtilen anahtardan büyük bir değere sahip bir eşlem içindeki ilk öğeye bir yineleyici döndürür.

```cpp
iterator upper_bound(const Key& key);

const_iterator upper_bound(const Key& key) const;
```

### <a name="parameters"></a>Parametreler

*Anahtarı*<br/>
Bir öğenin Aranan eşlemesinden sıralama anahtar değeri ile Karşılaştırılacak bağımsız değişken anahtar değeri.

### <a name="return-value"></a>Dönüş Değeri

Bir `iterator` veya `const_iterator` adresleri anahtar için bağımsız değişken anahtardan daha büyük ya da hiçbir eşlem içindeki son öğeyi takip eden konumu ele bir anahtar ile eşleştiğinden emin bir eşlem içindeki bir öğenin konumunu bulunamadı.

Dönüş değeri atanır, bir `const_iterator`, harita nesnesi değiştirilemez. Dönüş değeri atanır, bir `iterator`, harita nesnesi değiştirilebilir.

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

## <a name="value_comp"></a>  Map::value_comp

Üye işlevi, anahtar değerlerini karşılaştırarak bir eşlem içindeki öğelerin sırasını belirleyen bir işlev nesnesi döndürür.

```cpp
value_compare value_comp() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir harita alt öğeleri düzenlemek amacıyla kullanan bir karşılaştırma işlevi nesnesini döndürür.

### <a name="remarks"></a>Açıklamalar

Bir eşleme için *m*, iki öğe *e1*(*k1*, *d1*) ve *e2*(*k2*, *d2*) türündeki nesneler `value_type`burada *k1* ve *k1* türü kendi anahtarları `key_type` ve *d1* ve *d2* kendi veri türü olan `mapped_type`, ardından `m.value_comp(e1, e2)` eşdeğerdir `m.key_comp(k1, k2)`. Depolanan bir nesne üye işlevini tanımlar.

`bool operator( value_type& left, value_type& right);`

döndüren **true** , anahtar değerini `left` önündeki ve anahtar değerine eşit değil `right` sıralama düzeninde.

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

## <a name="value_type"></a>  Map::value_type

Bir eşlemdeki bir öğe olarak depolanan nesne türü.

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

[Kapsayıcılar](../cpp/containers-modern-cpp.md)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)<br/>
