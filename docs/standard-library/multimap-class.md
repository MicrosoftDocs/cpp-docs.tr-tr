---
title: multimap Sınıfı
ms.date: 10/18/2018
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
ms.openlocfilehash: caffa84052f774803b92730f7906bf53cb3c824a
ms.sourcegitcommit: d441305fb19131afbd7fc259d8cda63ea26f2343
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/15/2018
ms.locfileid: "51678528"
---
# <a name="multimap-class"></a>multimap Sınıfı

C++ Standart Kitaplığı multimap sınıfı her bir öğenin hem veri değerine hem de sıralama anahtarına sahip olduğu bir çift olan bir koleksiyondaki verileri alma ve depolama için kullanılır. Anahtarın değerinin benzersiz olması gerekmez ve verileri otomatik olarak sıralamak için kullanılır. Çoklu eşlemdeki bir öğenin değeri doğrudan değiştirilebilir, ancak ilişkili anahtar değeri doğrudan değiştirilemez. Bunun yerine, eski öğelerle ilişkili anahtar değerleri silinmeli ve eklenen yeni öğelerle ilişkili yeni anahtar değerleri eklenmelidir.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Key,
    class Type,
    class Traits=less <Key>,
    class Allocator=allocator <pair  <const Key, Type>>>
class multimap;
```

### <a name="parameters"></a>Parametreler

*Key*<br/>
Çoklu eşlemde depolanacak anahtar veri türü.

*Türü*<br/>
Çoklu eşlemde depolanacak öğe veri türü.

*Nitelikler*<br/>
İki öğenin değerlerini çoklu eşlemde kendi göreli sıralarını belirlemek için sıralama anahtarları olarak karşılaştırabilen bir işlev nesnesi sağlayan tür. İkili koşul `less<Key>` varsayılan değerdir.

C ++ 14'te belirterek heterojen arama etkinleştirebilirsiniz `std::less<>` veya `std::greater<>` hiçbir tür parametreleri olan koşul. Daha fazla bilgi için [, ilişkili kapsayıcılar için heterojen arama](../standard-library/stl-containers.md#heterogeneous-lookup-in-associative-containers-c14)

*Ayırıcı*<br/>
Eşlemin bellek ayırmayı ve ayırmayı kaldırma hakkındaki ayrıntıları içeren saklı ayırıcı nesnesini gösteren tür. Bu bağımsız değişken isteğe bağlıdır ve varsayılan değer `allocator<pair <const Key, Type> >`.

## <a name="remarks"></a>Açıklamalar

C++ Standart Kitaplığı çoklu eşlemi şöyledir:

- İlişkili bir anahtar değerine dayalı öğe değerlerinin verimli alınmasını destekleyen bir değişken boyutu kapsayıcı olan ilişkilendirilebilir bir kapsayıcı.

- Çift yönlüdür, çünkü öğelerine erişmek için çift yönlü yineleyiciler sağlar.

- Sıralıdır, çünkü öğeleri belirtilen karşılaştırma işlevine uygun olarak kapsayıcı içindeki anahtar değerlere göre sıralanır.

- Öğelerinin benzersiz anahtarlara ihtiyacı olmaması için çokludur, böylece bir anahtar değer onunla ilişkili çok sayıda öğe verisi değerine sahip olabilir.

- Bir çift ilişkilendirilebilir kapsayıcıdır, çünkü veri öğelerinin değerleri kendi anahtar değerlerinden farklıdır.

- Bir şablon sınıfıdır, çünkü sağladığı işlevsellik geneldir ve böylece öğeler veya anahtarlar olarak kapsanan belirli veri türünden bağımsızdır. Öğeler ve anahtarlar için kullanılacak veri türleri, karşılaştırma işlevi ve ayırıcı ile birlikte bir sınıf şablonunda parametreler olarak belirtilir.

Eşlem sınıfı tarafından sağlanan yineleyici çift yönlüdür, ancak sınıf üyesi işlevleri olan [Ekle](#insert) ve [multimap](#multimap) şablon parametresi olarak daha zayıf bir giriş yineleyicisini alan sürümlere sahip olan işlevsellik gereksinimleri tarafından çift yönlü Yineleyicilerin sınıfında garanti daha düşüktür. Farklı yineleyici kavramları, işlevselliklerindeki iyileştirmelere göre ilgili bir aile biçimlendirir. Her yineleyici kavramının kendi gereksinimler kümesi vardır ve bunlarla çalışan algoritmaların kendi varsayımlarını yineleyici türü tarafından sağlanan gereksinimlerle sınırlaması gerekir. Bir giriş yineleyicinin bazı nesnelere başvurusunun kaldırılacağı ve dizideki sonraki yineleyiciye artırılabileceği varsayılabilir. Bu bir en düşük işlevsellik kümesidir, ancak Yineleyicilerin aralığı hakkında konuşabilmek için yeterlidir `[First, Last)` sınıfın üye işlevleri bağlamında.

Kapsayıcı türünün seçimi genelde uygulamanın gerektirdiği arama ve ekleme türüne dayalı olmalıdır. İlişkilendirilebilir kapsayıcılar, arama, ekleme ve kaldırma işlemleri için en iyi duruma getirilir. Bu işlemleri açıkça destekleyen üye işlevleri, işlevlerini kapsayıcıdaki öğelerin sayısının logaritmasına ortalama orantılı bir sürede gerçekleştirir ve verimlidir. Öğelerin eklenmesi hiçbir yineleyiciyi geçersiz kılmaz; öğelerin kaldırılması yalnızca özellikle kaldırılan öğeleri gösteren yineleyicileri geçersiz kılar.

Çoklu eşlem, değerleri onların kendi anahtarlarıyla ilişkilendiren koşullar uygulama tarafından karşılandığında seçimin ilişkili kapsayıcısı olmalıdır. Bu tür bir yapı için model, mesela açıklamalar sağlayan dize değerleriyle ilişkili anahtar sözcüklerin sıralı bir listesidir, burada sözcükler her zaman benzersiz olarak tanımlanmamıştır. Bunun yerine anahtar sözcükler benzersiz olarak tanımlanırsa, seçilecek kapsayıcı bir eşlem olurdu. Diğer taraftan, yalnızca sözcüklerin listesi depolanmaktadır, ardından bir küme doğru kapsayıcı olacaktır. Sözcüklerin birden çok defa geçmelerine izin verilirse, bir çoklu küme uygun bir kapsayıcı yapısı olacaktır.

Multimap türünde bir depolanmış bir işlev nesnesi çağırarak denetlediği diziyi sıralar [key_compare](#key_compare). Depolanan bu nesne işlevi çağrılarak erişilebilen bir karşılaştırma işlevidir [key_comp](#key_comp). Genelde, bu sıralamayı oluşturmak için öğelerin yalnızca küçüktür biçiminde karşılaştırılabilir olması gerekir; böylece, herhangi iki öğe belirtildiğinde, eşit oldukları (yani birinin diğerinden daha küçük olmadığı anlamında) veya birinin diğerinden küçük olduğu belirlenebilir. Bu, denk olmayan öğeler arasında bir sıralamaya neden olur. Daha teknik bir not üzerinde, karşılaştırma işlevi standart matematiksel anlamda katı bir zayıf sıralama sevk eden ikili bir koşuldur. Bir ikili koşula `f(x,y)` iki bağımsız değişken nesnelere sahip bir işlev nesnesidir `x` ve `y` ve dönüş değeri true veya false. Bir kümesinde ikili koşul dönüşsüz, ters ve geçişli ve denklik geçişli ise, burada iki nesne sıralama katı zayıf sıralamadır `x` ve `y` olduğunda denk olarak tanımlanan her iki `f(x,y)`ve `f(y,x)` false. Anahtarlar arasındaki eşitliğinin daha güçlü koşulu bu denkliğin yerini alırsa, sıralama (içindeki tüm öğelerin birbirine göre sıralanması anlamında) toplam haline gelir ve eşleşen anahtarlar birbirinden ayırt edilemez olacaktır.

C ++ 14'te belirterek heterojen arama etkinleştirebilirsiniz `std::less<>` veya `std::greater<>` hiçbir tür parametreleri olan koşul. Daha fazla bilgi için [, ilişkili kapsayıcılar için heterojen arama](../standard-library/stl-containers.md#sequence_containers)

## <a name="members"></a>Üyeler

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[multimap](#multimap)|Oluşturur bir `multimap` boş veya diğer bir deyişle bir kopyasını tüm veya diğer bir kısmının parçası `multimap`.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[allocator_type](#allocator_type)|Temsil eden bir tür `allocator` sınıfının `multimap` nesne.|
|[const_iterator](#const_iterator)|Çift yönlü bir yineleyici sağlayan tür okuma bir **const** öğesinde `multimap`.|
|[const_pointer](#const_pointer)|Bir işaretçi sağlayan bir tür bir **const** öğesinde bir `multimap`.|
|[const_reference](#const_reference)|Bir başvuru sağlayan bir tür bir **const** öğesi içinde depolanan bir `multimap` okumak ve gerçekleştirmek için **const** operations.|
|[const_reverse_iterator](#const_reverse_iterator)|Çift yönlü bir yineleyici sağlayan tür herhangi okuma **const** öğesinde `multimap`.|
|[difference_type](#difference_type)|Öğelerin sayısını temsil etmek için kullanılabilen işaretli bir tamsayı türü bir `multimap` yineleyiciler tarafından gösterilen öğeler arasındaki bir aralıktaki.|
|[Yineleyici](#iterator)|Aynı içindeki öğelere başvuran iki yineleyici arasındaki farkı sağlayan bir tür `multimap`.|
|[key_compare](#key_compare)|İki öğenin göreli sırasını belirlemek için iki sıralama anahtarını karşılaştıran işlev nesnesi sağlayan bir tür `multimap`.|
|[key_type](#key_type)|Her öğesini oluşturan sıralama anahtarını nesnesini tanımlayan bir tür `multimap`.|
|[mapped_type](#mapped_type)|İçinde depolanan veri türünü temsil eden bir tür bir `multimap`.|
|[İşaretçi](#pointer)|Bir işaretçi sağlayan bir tür bir **const** öğesinde bir `multimap`.|
|[Başvuru](#reference)|İçinde depolanan öğeye başvuru sağlayan bir tür bir `multimap`.|
|[reverse_iterator](#reverse_iterator)|Çift yönlü bir yineleyici sağlayan bir tür okuyabilen veya değiştirebilen ters döndürülmüş bir öğe `multimap`.|
|[size_type](#size_type)|İşaretçi sağlayan bir işaretsiz tamsayı türü bir **const** öğesinde bir `multimap`.|
|[value_type](#value_type)|İki öğenin kendi göreli sıralarını belirlemek için sıralama anahtarları olarak karşılaştırabilen bir işlev nesnesi sağlayan bir tür `multimap`.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[başlayın](#begin)|İçindeki ilk öğeyi adresleyen bir yineleyici döndürür `multimap`.|
|[cbegin](#cbegin)|İçindeki ilk öğeyi adresleyerek bir const yineleyici döndürür `multimap`.|
|[cend](#cend)|İçindeki son öğeyi takip eden konumu ele alan sabit bir yineleyici döndüren bir `multimap`.|
|[Temizle](#clear)|Tüm öğelerini siler bir `multimap`.|
|[Sayısı](#count)|İçindeki öğelerin sayısını döndüren bir `multimap` anahtarı parametre tarafından belirtilen bir anahtarla eşleşen.|
|[crbegin](#crbegin)|Ters çevrilen içindeki ilk öğeyi adresleyerek bir const yineleyici döndürür `multimap`.|
|[crend](#crend)|Ters çevrilen içindeki son öğeyi takip eden konumu ele alan sabit bir yineleyici döndürür `multimap`.|
|[emplace](#emplace)|İçine yerinde oluşturulmuş bir öğe ekler bir `multimap`.|
|[emplace_hint](#emplace_hint)|İçine yerinde oluşturulmuş bir öğe ekler bir `multimap`, bir yerleşim ipucuyla birlikte|
|[boş](#empty)|Testleri bir `multimap` boştur.|
|[Son](#end)|İçindeki son öğeyi takip eden konumu ele alan bir yineleyici döndüren bir `multimap`.|
|[equal_range](#equal_range)|Öğenin anahtarının belirtilen değerle eşleştiği öğeler aralığını bulur.|
|[silme](#erase)|Bir öğenin veya öğelerin aralığını kaldırır bir `multimap` belirtilen konumları veya belirtilen bir anahtarla eşleşen öğeleri kaldırır.|
|[Bul](#find)|İçindeki bir öğenin birinci konumunu ele alan bir yineleyici döndüren bir `multimap` belirtilen anahtara denk bir anahtara sahip.|
|[get_allocator](#get_allocator)|Bir kopyasını döndürür `allocator` oluşturmak için kullanılan nesne `multimap`.|
|[Ekle](#insert)|Bir öğe veya bir dizi öğelerine ekler bir `multimap`.|
|[key_comp](#key_comp)|İçindeki anahtarları sıralamak için kullanılan karşılaştırma nesnesinin bir kopyasını alır bir `multimap`.|
|[lower_bound](#lower_bound)|İçindeki ilk öğeye bir yineleyici döndüren bir `multimap` belirtilen anahtardan daha büyük veya ona eşit bir anahtarla.|
|[max_size](#max_size)|Öğesinin maksimum uzunluğunu döndürür `multimap`.|
|[rbegin](#rbegin)|Ters çevrilen içindeki ilk öğeyi adresleyen bir yineleyici döndürür `multimap`.|
|[rend](#rend)|Ters çevrilen içindeki son öğeden sonra gelen konumu ele alan bir yineleyici döndürür `multimap`.|
|[Boyutu](#size)|İçindeki öğelerin sayısını döndürür `multimap`.|
|[değiştirme](#swap)|İki öğeleri birbiriyle değiştirir `multimap`s.|
|[upper_bound](#upper_bound)|İçindeki ilk öğeye bir yineleyici döndüren bir `multimap` belirtilen anahtardan daha büyük bir anahtarla.|
|[value_comp](#value_comp)|Üye işlevi öğelerin sırasını belirleyen bir işlev nesnesi döndüren bir `multimap` anahtar değerlerini karşılaştırarak.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[operator=](#op_eq)|Öğelerinin yerini alan bir `multimap` başka bir kopyasına sahip olan `multimap`.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<harita >

**Namespace:** std

( **Anahtarı**, **değer**) çiftleri türünün nesneleri olarak bir çoklu eşlemde depolanır `pair`. Pair sınıfı üst bilgisi gerektiren \<yardımcı programı >, hangi otomatik olarak dahil tarafından \<harita >.

## <a name="allocator_type"></a>  multimap::allocator_type

Multimap nesne için ayırıcı sınıf temsil eden tür.

```cpp
typedef Allocator allocator_type;
```

### <a name="example"></a>Örnek

Örneğin bakın [get_allocator](#get_allocator) bir örnek için `allocator_type`.

## <a name="begin"></a>  multimap::Begin

Çoklu eşlem ilk öğeyi adresleyen bir yineleyici döndürür.

```cpp
const_iterator begin() const;

iterator begin();
```

### <a name="return-value"></a>Dönüş Değeri

Multimap veya sonra gelen konumu adresleyen boş bir çoklu eşlem ilk öğeyi adresleyen bir çift yönlü yineleyici.

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

## <a name="cbegin"></a>  multimap::cbegin

Döndürür bir **const** aralıktaki ilk öğeyi adresleyen bir yineleyici.

```cpp
const_iterator cbegin() const;
```

### <a name="return-value"></a>Dönüş Değeri

A **const** aralığı veya konuma boş bir aralığın ilk öğesine, çift yönlü erişim yineleyicisi (boş bir aralık için `cbegin() == cend()`).

### <a name="remarks"></a>Açıklamalar

Dönüş değeri ile `cbegin`, aralıktaki öğeler değiştirilemez.

Bu üye işlevi yerine kullanabileceğiniz `begin()` üye işlev dönüş değeri olacağını garanti etmek için `const_iterator`. Genellikle birlikte kullanılır [otomatik](../cpp/auto-cpp.md) kesinti anahtar sözcüğü, aşağıdaki örnekte gösterildiği gibi yazın. Örnekte, göz önünde bulundurun `Container` değiştirilebilir (olmayan **const**) destekleyen herhangi bir türdeki kapsayıcı `begin()` ve `cbegin()`.

```cpp
auto i1 = Container.begin();
// i1 is Container<T>::iterator
auto i2 = Container.cbegin();

// i2 is Container<T>::const_iterator
```

## <a name="cend"></a>  multimap::cend

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

## <a name="clear"></a>  multimap::Clear

Çoklu eşlem tüm öğelerini siler.

```cpp
void clear();
```

### <a name="example"></a>Örnek

Aşağıdaki örnek, multimap::clear üye işlevinin kullanımını gösterir.

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

## <a name="const_iterator"></a>  multimap::const_iterator

Çift yönlü bir yineleyici sağlayan tür okuma bir **const** multimap öğesinde.

```cpp
typedef implementation-defined const_iterator;
```

### <a name="remarks"></a>Açıklamalar

Bir tür `const_iterator` bir öğenin değerini değiştirmek için kullanılamaz.

`const_iterator` Nesnelerine multimap noktaları tarafından tanımlanan [value_type](#value_type), türü olan `pair<const Key, Type>`. Anahtar değeri ilk üye çift kullanılabilir ve eşlenen öğenin değeri çiftinin ikinci üye kullanılabilir.

Başvurulacak bir `const_iterator` *cIter* öğeye işaret eden bir çoklu eşlemde, kullanın **->** işleci.

Öğenin anahtarının değerini erişmek için `cIter->first`, eşdeğer olan `(*cIter).first`. Eşlenmiş veri öğesi için değeri erişmek için `cIter->second`, eşdeğer olan `(*cIter).second`.

### <a name="example"></a>Örnek

Örneğin bakın [başlamak](#begin) bir örnek için `const_iterator`.

## <a name="const_pointer"></a>  multimap::const_pointer

Bir işaretçi sağlayan bir tür bir **const** eşlemdeki öğe.

```cpp
typedef typename allocator_type::const_pointer const_pointer;
```

### <a name="remarks"></a>Açıklamalar

Bir tür `const_pointer` bir öğenin değerini değiştirmek için kullanılamaz.

Çoğu durumda bir [yineleyici](#iterator) multimap nesnesindeki öğelere erişmek için kullanılmalıdır.

## <a name="const_reference"></a>  multimap::const_reference

Bir başvuru sağlayan bir tür bir **const** okumak ve gerçekleştirmek için bir çoklu eşlem içinde depolanan öğenin **const** operations.

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
   // non-const_reference cannot be used to access the key
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

## <a name="const_reverse_iterator"></a>  multimap::const_reverse_iterator

Çift yönlü bir yineleyici sağlayan tür herhangi okuma **const** multimap öğesinde.

```cpp
typedef std::reverse_iterator<const_iterator> const_reverse_iterator;
```

### <a name="remarks"></a>Açıklamalar

Bir tür `const_reverse_iterator` kullanın ters çoklu eşlemde yinelemek için ve bir öğenin değerini değiştiremezsiniz.

`const_reverse_iterator` Nesnelerine multimap noktaları tarafından tanımlanan [value_type](#value_type), türü olan `pair<const Key, Type>`. Anahtar değeri ilk üye çift kullanılabilir ve eşlenen öğenin değeri çiftinin ikinci üye kullanılabilir.

Başvurulacak bir `const_reverse_iterator` *crIter* öğeye işaret eden bir çoklu eşlemde, kullanın **->** işleci.

Öğenin anahtarının değerini erişmek için `crIter->first`, eşdeğer olan `(*crIter).first`. Eşlenmiş veri öğesi için değeri erişmek için `crIter->second`, eşdeğer olan `(*crIter).first`.

### <a name="example"></a>Örnek

Örneğin bakın [rend](#rend) bildirme ve kullanma konusunda bir örnek için `const_reverse_iterator`.

## <a name="count"></a>  multimap::Count

Bir çoklu eşlemde anahtarları parametre tarafından belirtilen bir anahtarla eşleşen öğelerin sayısını döndürür.

```cpp
size_type count(const Key& key) const;
```

### <a name="parameters"></a>Parametreler

*Anahtarı*<br/>
Multimap eşleştirilecek öğe anahtarı.

### <a name="return-value"></a>Dönüş Değeri

Sıralama anahtarları parametre anahtarı eşleşen öğe sayısı; 0 multimap bir öğesi ile eşleşen bir anahtar içermiyor.

### <a name="remarks"></a>Açıklamalar

Üye işlevi aralıktaki öğelerin sayısını döndürür.

\[ lower_bound (*anahtarı*), upper_bound (*anahtarı*))

bir anahtar değere sahip *anahtar*.

### <a name="example"></a>Örnek

Aşağıdaki örnek, multimap::count üye işlevinin kullanımını gösterir.

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

    // Elements do not need to have unique keys in multimap,
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

## <a name="crbegin"></a>  multimap::crbegin

Ters çevrilen bir çoklu eşlemde ilk öğeyi adresleyen bir const yineleyici döndürür.

```cpp
const_reverse_iterator crbegin() const;
```

### <a name="return-value"></a>Dönüş Değeri

Ters çevrilen bir ilk öğeyi ele alan çift yönlü yineleyici bir const [multimap](../standard-library/multimap-class.md) veya ne ters çevrilmeyen içindeki son öğeyi adresleyen `multimap`.

### <a name="remarks"></a>Açıklamalar

`crbegin` kullanılan bir ters ile `multimap` gibi [başlamak](#begin) ile kullanılan bir `multimap`.

Dönüş değeri ile `crbegin`, `multimap` nesnesi değiştirilemez.

`crbegin` yinelemek için kullanılabilecek bir `multimap` geriye doğru.

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

## <a name="crend"></a>  multimap::crend

Tersine çevrilmiş bir çoklu eşlemde son öğeyi takip eden konumu ele alan sabit bir yineleyici döndürür.

```cpp
const_reverse_iterator crend() const;
```

### <a name="return-value"></a>Dönüş Değeri

Ters çevrilen bir içindeki son öğeden sonra gelen konumu ele çift yönlü yineleyici bir const [multimap](../standard-library/multimap-class.md) (ilk öğeyi çevrilmeyen önce gelen konum `multimap`).

### <a name="remarks"></a>Açıklamalar

`crend` kullanılan bir ters ile `multimap` gibi [multimap::end](#end) ile kullanılan bir `multimap`.

Dönüş değeri ile `crend`, `multimap` nesnesi değiştirilemez.

`crend` olup ters yineleyici sonuna ulaşıp ulaşmadığını test etmek için kullanılan kendi `multimap`.

Tarafından döndürülen değer `crend` kaldırılmamalıdır.

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

## <a name="difference_type"></a>  multimap::difference_type

Bir çoklu eşlemde yineleyiciler tarafından gösterilen öğeler arasındaki bir aralıktaki öğelerin sayısını temsil etmek için kullanılabilen işaretli bir tamsayı türü.

```cpp
typedef typename allocator_type::difference_type difference_type;
```

### <a name="remarks"></a>Açıklamalar

`difference_type` Türü çıkarma veya kapsayıcının yineleyiciler artan döndürülür. `difference_type` Genellikle aralık içindeki öğelerin sayısını temsil etmek için kullanılan [*ilk*, *son*) yineleyici arasındaki `first` ve `last`, işaret öğesi içerir tarafından `first` ve en fazla, ancak dahil değil öğelerin aralığını, öğeyi işaret ettiği `last`.

Ancak dikkat `difference_type` kümesi, yineleyici arasındaki çıkarma yalnızca gibi ters çevrilebilir kapsayıcıları tarafından desteklenen çift yönlü Yineleyicilerin sınıfında içeren bir giriş yineleyici gereksinimlerini karşılayan tüm yineleyiciler için kullanılabilir vektör gibi bir rastgele erişim kapsayıcı tarafından sağlanan rasgele erişim yineleyicileri tarafından desteklenmiyor.

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

## <a name="emplace"></a>  multimap::emplace

(Hiçbir kopyalama veya taşıma işlemleri gerçekleştirilir) yerinde oluşturulmuş bir öğe ekler.

```cpp
template <class... Args>
iterator emplace(Args&&... args);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|-|-|
|*bağımsız değişken*|Çoklu eşlem eklenecek bir öğe oluşturmak için iletilen bağımsız değişkenler.|

### <a name="return-value"></a>Dönüş Değeri

Yeni eklenen öğeye bir yineleyici.

### <a name="remarks"></a>Açıklamalar

Bu işlev tarafından geçersiz kılınan kapsayıcı öğeleri için başvuru ancak kapsayıcıya tüm yineleyiciler geçersiz kılabilir.

Ekleme sırasında bir özel durum oluşturulursa, kapsayıcı bırakılır değiştirilmeden ve özel durum yeniden oluşur.

[Value_type](../standard-library/map-class.md#value_type) böylece bir öğenin değerini sıralı bir çift anahtar değerine eşit olan ilk bileşen ve saniye bileşenini öğenin veri değerine eşit olan bir çift öğesidir.

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

## <a name="emplace_hint"></a>  multimap::emplace_hint

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
|*bağımsız değişken*|Çoklu eşlem eklenecek bir öğe oluşturmak için iletilen bağımsız değişkenler.|
|*Burada*|Doğru ekleme noktasını için aramaya başlamak için bir yerde. (Bu noktanın hemen önceyse *burada*, ekleme Logaritmik süre yerine amorti edilmiş sabit zaman meydana gelebilir.)|

### <a name="return-value"></a>Dönüş Değeri

Yeni eklenen öğeye bir yineleyici.

### <a name="remarks"></a>Açıklamalar

Bu işlev tarafından geçersiz kılınan kapsayıcı öğeleri için başvuru ancak kapsayıcıya tüm yineleyiciler geçersiz kılabilir.

Yerleştirme sırasında bir özel durum oluşturulursa, kapsayıcının durumu değiştirilmez.

[Value_type](../standard-library/map-class.md#value_type) böylece bir öğenin değerini sıralı bir çift anahtar değerine eşit olan ilk bileşen ve saniye bileşenini öğenin veri değerine eşit olan bir çift öğesidir.

Kod örneği için bkz: [map::emplace_hint](../standard-library/map-class.md#emplace_hint).

## <a name="empty"></a>  multimap::empty

Çoklu eşlem boş olup olmadığını sınar.

```cpp
bool empty() const;
```

### <a name="return-value"></a>Dönüş Değeri

**doğru** çoklu eşlem boşsa; **false** multimap boş ise.

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

## <a name="end"></a>  multimap::End

past-the-end yineleyici döndürür.

```cpp
const_iterator end() const;

iterator end();
```

### <a name="return-value"></a>Dönüş Değeri

Past--end yineleyici. Ardından çoklu eşlem boşsa, `multimap::end() == multimap::begin()`.

### <a name="remarks"></a>Açıklamalar

**Son** kendi multimap sonuna bir yineleyici geçmediğini sınamak için kullanılır.

Tarafından döndürülen değer **son** kaldırılmamalıdır.

Kod örneği için bkz: [multimap::find](#find).

## <a name="equal_range"></a>  multimap::equal_range

Öğenin anahtarının belirtilen değerle eşleştiği öğeler aralığını bulur.

```cpp
pair <const_iterator, const_iterator> equal_range (const Key& key) const;

pair <iterator, iterator> equal_range (const Key& key);
```

### <a name="parameters"></a>Parametreler

*Anahtarı*<br/>
Aranan multimap bir öğeyi sıralama anahtarı ile Karşılaştırılacak bağımsız değişken anahtarı.

### <a name="return-value"></a>Dönüş Değeri

Yineleyicilerin bir çiftini ilk güvenilecek şekilde [lower_bound](#lower_bound) , anahtar ve ikinci [upper_bound](#upper_bound) anahtarı.

Bir çiftin ilk yineleyicisi erişmeye `pr` üye işlevi tarafından döndürülen, kullanın `pr`. **İlk** ve alt sınır yineleyicinin başvuru kaldırma için \*( `pr`. **İlk**). Bir çiftin ikinci yineleyicisi erişmeye `pr` üye işlevi tarafından döndürülen, kullanın `pr`. **İkinci** ve üst sınır yineleyicinin başvuru kaldırma için \*( `pr`. **İkinci**).

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

## <a name="erase"></a>  multimap::ERASE

Bir öğenin veya öğelerin aralığını belirtilen konumdan bir çoklu eşlemde kaldırır veya belirtilen bir anahtarla eşleşen öğeleri kaldırır.

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
Kaldırılacak öğe anahtarı.

### <a name="return-value"></a>Dönüş Değeri

İlk iki üye işlevleri için çift yönlü bir yineleyici, kaldırılan herhangi bir öğe veya böyle bir öğe yoksa eşleme sonuna bir öğeyi ilk öğeyi belirtir.

Üye işlevi için üçüncü multimap kaldırılan öğelerin sayısını döndürür.

### <a name="remarks"></a>Açıklamalar

Kod örneği için bkz: [map::erase](../standard-library/map-class.md#erase).

## <a name="find"></a>  multimap::Find

Belirtilen anahtara denk bir anahtara sahip çoklu eşlemdeki bir öğenin ilk konuma başvuran bir yineleyici döndürür.

```cpp
iterator find(const Key& key);

const_iterator find(const Key& key) const;
```

### <a name="parameters"></a>Parametreler

*Anahtarı*<br/>
Aranan multimap bir öğeyi sıralama anahtarı tarafından eşleştirilecek anahtar değeri.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen anahtara sahip bir öğenin konumunu veya konumu eşlemde son öğeyi adresleyen bir yineleyici (`multimap::end()`) anahtar için bir eşleşme varsa.

### <a name="remarks"></a>Açıklamalar

Üye işlevi, bağımsız değişken anahtarı altındaki bir comparability ilişkisi küçüktür göre sıralama sevk eden ikili bir koşula eşlemde sıralama anahtarı bir öğeye başvuran bir yineleyici eşdeğerdir döndürür.

Varsa dönüş değerinin `find` atanan bir `const_iterator`, multimap nesnesi değiştirilemez. Varsa dönüş değerinin `find` atanan bir `iterator`, multimap nesnesi değiştirilebilir.

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

## <a name="get_allocator"></a>  multimap::get_allocator

Çoklu eşlem oluşturmak için kullanılan ayırıcı nesnesinin bir kopyasını döndürür.

```cpp
allocator_type get_allocator() const;
```

### <a name="return-value"></a>Dönüş Değeri

Multimap tarafından kullanılan ayırıcı.

### <a name="remarks"></a>Açıklamalar

Multimap sınıfı için ayırıcılar sınıfı depolama nasıl yönettiğini belirtin. C++ Standart Kitaplığı kapsayıcı sınıfları ile sağlanan varsayılan ayırıcılar çoğu programlama ihtiyaçları için yeterli. Yazma ve kendi allocator sınıfı kullanarak bir Gelişmiş C++ konudur.

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

## <a name="insert"></a>  multimap::insert

Çoklu eşlem, bir öğenin veya öğelerin aralığını ekler.

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
|*VAL*|Çoklu eşlem eklenecek bir öğenin değeri.|
|*Burada*|Doğru ekleme noktasını için aramaya başlamak için bir yerde. (Bu noktanın hemen önceyse *burada*, ekleme Logaritmik süre yerine amorti edilmiş sabit zaman meydana gelebilir.)|
|*ValTy*|Eşleme öğesi oluşturmak için kullanabileceğiniz bağımsız değişken türü belirten bir şablon parametresi [value_type](../standard-library/map-class.md#value_type)ve mükemmel ileten *Val* bağımsız değişken olarak.|
|*ilk*|Kopyalanacak ilk öğenin konumu.|
|*Son*|Kopyalanacak son öğenin ötesinde konumu.|
|*Inputıterator*|Gereksinimlerini karşılayan şablonu işlev bağımsız değişkeni bir [giriş yineleyici](../standard-library/input-iterator-tag-struct.md) oluşturmak için kullanılan bir tür öğelerine işaret eden [value_type](../standard-library/map-class.md#value_type) nesneleri.|
|*IList*|[İnitializer_list](../standard-library/initializer-list.md) öğeleri kopyalanacak.|

### <a name="return-value"></a>Dönüş Değeri

Tek öğe ekleme üye işlevleri (1) ve (2), yeni öğe çoklu eşlem eklenmiş olduğu konuma bir yineleyici döndürür.

İpucu ile tek öğe üye işlevleri, (3) ve (4), yeni bir öğe çoklu eşlem eklenir burada konumu gösteren bir yineleyici döndürür.

### <a name="remarks"></a>Açıklamalar

Hiçbir işaretçileri veya başvuruları bu işlev tarafından geçersiz kılınan ancak kapsayıcıya tüm yineleyiciler geçersiz kılabilir.

Bir özel durum oluşturulursa, yeni bir öğe ekleme sırasında kapsayıcının durumu değiştirilmez. Bir özel durum oluşturulursa, birden çok öğe ekleme sırasında kapsayıcı belirtilmeyen ancak geçerli bir durumda bırakılır.

[Value_type](../standard-library/map-class.md#value_type) eşlemesini yanı sıra, kapsayıcıya ait bir tür tanımı, kapsayıcısıdır `multimap<K, V>::value_type` olduğu `pair<const K, V>`. Bir öğenin ilk bileşen anahtar değerine eşittir ve ikinci bileşen öğenin veri değerine eşit olan sıralı bir çift değerdir.

Aralık üye işlevi (5) aralığında bir yineleyici tarafından ele alınan her öğe için karşılık gelen bir multimap öğe değerleri dizisi ekler `[First, Last)`; bu nedenle *son* takılı. Kapsayıcı üye işlevi `end()` kapsayıcıdaki son öğeden hemen sonra konuma başvuran — Örneğin, deyim `m.insert(v.begin(), v.end());` tüm öğeleri ekler `v` içine `m`.

Başlatıcı listesinde üye işlev (6) kullanan bir [initializer_list](../standard-library/initializer-list.md) öğeleri eşlemeye kopyalamak için.

Yerinde oluşturulmuş bir öğe ekleme — diğer bir deyişle, hiçbir kopyalama veya taşıma işlemleri gerçekleştirilir — bkz [multimap::emplace](#emplace) ve [multimap::emplace_hint](#emplace_hint).

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

## <a name="iterator"></a>  multimap::iterator

Okuma veya herhangi bir öğenin bir çoklu eşlemde değiştirebilen çift yönlü bir yineleyici sağlayan tür.

```cpp
typedef implementation-defined iterator;
```

### <a name="remarks"></a>Açıklamalar

`iterator` Nesnelerine multimap noktaları tarafından tanımlanan [value_type](#value_type), türü olan `pair<const Key, Type>`. Anahtar değeri ilk üye çift kullanılabilir ve eşlenen öğenin değeri çiftinin ikinci üye kullanılabilir.

Başvurulacak bir `iterator` *Iter* öğeye işaret eden bir çoklu eşlemde, kullanın **->** işleci.

Öğenin anahtarının değerini erişmek için `Iter->first`, eşdeğer olan `(*Iter).first`. Eşlenmiş veri öğesi için değeri erişmek için `Iter->second`, eşdeğer olan `(*Iter).second`.

Bir tür `iterator` bir öğenin değerini değiştirmek için kullanılabilir.

### <a name="example"></a>Örnek

Örneğin bakın [başlamak](#begin) bildirme ve kullanma konusunda bir örnek için `iterator`.

## <a name="key_comp"></a>  multimap::key_comp

Çoklu eşlem anahtarları sıralamak için kullanılan karşılaştırma nesnesinin bir kopyasını alır.

```cpp
key_compare key_comp() const;
```

### <a name="return-value"></a>Dönüş Değeri

Çoklu eşlem öğeleri sıralamak için kullandığı işlevi nesnesini döndürür.

### <a name="remarks"></a>Açıklamalar

Depolanan nesne üyesi işlevini tanımlar.

`bool operator( const Key& x, const Key& y);`

hangi döndürür true ise *x* kesinlikle önündeki *y* sıralama düzeninde.

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

## <a name="key_compare"></a>  multimap::key_compare

Çoklu eşlem iki öğenin göreli sırasını belirlemek için iki sıralama anahtarını karşılaştıran işlev nesnesi sağlayan tür.

```cpp
typedef Traits key_compare;
```

### <a name="remarks"></a>Açıklamalar

`key_compare` Şablon parametresi için bir eşanlamlı olduğu `Traits`.

Daha fazla bilgi için `Traits` bkz [multimap sınıfı](../standard-library/multimap-class.md) konu.

### <a name="example"></a>Örnek

Örneğin bakın [key_comp](#key_comp) bildirme ve kullanma konusunda bir örnek için `key_compare`.

## <a name="key_type"></a>  multimap::key_type

Multimap her öğesini oluşturan sıralama anahtarını nesnesini tanımlayan bir tür.

```cpp
typedef Key key_type;
```

### <a name="remarks"></a>Açıklamalar

`key_type` Şablon parametresi için bir eşanlamlı olduğu `Key`.

Daha fazla bilgi için `Key`, Açıklamalar bölümüne bakın [multimap sınıfı](../standard-library/multimap-class.md) konu.

### <a name="example"></a>Örnek

Örneğin bakın [value_type](#value_type) bildirme ve kullanma konusunda bir örnek için `key_type`.

## <a name="lower_bound"></a>  multimap::lower_bound

Bir yineleyicinin ilk öğeye bir çoklu eşlemde belirtilen anahtardan daha büyük veya ona eşit bir anahtarla döndürür.

```cpp
iterator lower_bound(const Key& key);

const_iterator lower_bound(const Key& key) const;
```

### <a name="parameters"></a>Parametreler

*Anahtarı*<br/>
Aranan multimap bir öğeyi sıralama anahtarı ile Karşılaştırılacak bağımsız değişken anahtarı.

### <a name="return-value"></a>Dönüş Değeri

Bir yineleyici veya `const_iterator` adresleri anahtar için bağımsız değişken anahtardan daha büyük veya ona eşit olan veya hiçbir eşlemde son öğeyi takip eden konumu ele bir anahtar ile eşleştiğinden emin çoklu eşlemdeki bir öğenin konumunu bulunamadı.

Varsa dönüş değerinin `lower_bound` atanan bir `const_iterator`, multimap nesnesi değiştirilemez. Varsa dönüş değerinin `lower_bound` atanan bir **yineleyici**, multimap nesnesi değiştirilebilir.

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

## <a name="mapped_type"></a>  multimap::mapped_type

Bir çoklu eşlemde depolanan veri türünü temsil eden tür.

```cpp
typedef Type mapped_type;
```

### <a name="remarks"></a>Açıklamalar

`mapped_type` Şablon parametresi için bir eşanlamlı olduğu `Type`.

Daha fazla bilgi için `Type` bkz [multimap sınıfı](../standard-library/multimap-class.md) konu.

### <a name="example"></a>Örnek

Örneğin bakın [value_type](#value_type) bildirme ve kullanma konusunda bir örnek için `key_type`.

## <a name="max_size"></a>  multimap::max_size

Çoklu eşlem öğesinin maksimum uzunluğunu döndürür.

```cpp
size_type max_size() const;
```

### <a name="return-value"></a>Dönüş Değeri

Multimap maksimum olası uzunluğu.

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

## <a name="multimap"></a>  multimap::multimap

Boş veya bir kopyası tüm veya bazı diğer multimap parçası olan bir eşleme oluşturur.

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

|Parametre|Açıklama|
|-|-|
|*Al*|Ayırıcı için varsayılan olarak bu multimap nesne için kullanılacak depolama ayırıcı sınıf.|
|*Comp*|Karşılaştırma işlevi türü `constTraits` varsayılan olarak haritada öğeleri sıralamak için kullanılan `Traits`.|
|*sağ*|Oluşturulan kümesi kopyası olacak olduğu eşlemesi.|
|*ilk*|Kopyalanacak öğe aralığındaki ilk öğenin konumu.|
|*Son*|Kopyalanacak öğe aralığının dışındaki ilk öğenin konumu.|
|*IList*|Öğelerin kopyalanacağı initializer_list.|

### <a name="remarks"></a>Açıklamalar

Tüm oluşturucular ayırıcı nesnesi, bellek, depolama için multimap yönetir ve, daha sonra döndürülmesi çağırarak türü depolamak [get_allocator](#get_allocator). Allocator parametresi, sınıf bildirimleri ve diğer ayırıcılar yerine kullanılan ön işleme makroları genellikle atlanır.

Tüm oluşturucular kendi multimap başlatın.

Tüm oluşturucular türünün işlev nesnesini depolamak `Traits` multimap anahtarları arasında bir sıralamayı oluşturmak için kullanılan ve, daha sonra döndürülmesi çağırarak [key_comp](#key_comp).

İlk üç Oluşturucular, bir boş ilk multimap, ikinci belirtin karşılaştırma işlevinin türü belirtme (*kompozisyonu*) öğeleri ve üçüncüsü sırasını açıkça oluşturmada kullanılacak ayırıcı belirtme yazın (*Al*) kullanılacak. Anahtar sözcük **açık** otomatik tür dönüştürme belirli türdeki bastırır.

Dördüncü Oluşturucu multimap bir kopyasını belirtir *sağ*.

Beşinci Oluşturucu taşıyarak multimap bir kopyasını belirtir. *sağ*.

Altıncı, yedinci ve sekizinci oluşturucular bir initializer_list üyelerinin kopyalayın.

Sonraki üç oluşturucular aralığını kopyalamaktadır `[First, Last)` sınıfın karşılaştırma işlevinin türü belirtilirken explicitness artan eşleme `Traits` ve ayırıcı.

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

## <a name="op_eq"></a>  multimap::operator =

Çoklu eşlem öğelerini başka bir çoklu eşlem kopyasıyla değiştirir.

```cpp
multimap& operator=(const multimap& right);

multimap& operator=(multimap&& right);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|-|-|
|*sağ*|[Multimap](../standard-library/multimap-class.md) içine kopyalanan `multimap`.|

### <a name="remarks"></a>Açıklamalar

Var olan tüm öğeleri silme sonra bir `multimap`, `operator=` kopyalar veya içeriğini hareket *doğru* içine `multimap`.

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

## <a name="pointer"></a>  multimap::pointer

Bir çoklu eşlemde bir öğeye işaretçi sağlayan bir tür.

```cpp
typedef typename allocator_type::pointer pointer;
```

### <a name="remarks"></a>Açıklamalar

Bir tür `pointer` bir öğenin değerini değiştirmek için kullanılabilir.

Çoğu durumda bir [yineleyici](#iterator) multimap nesnesindeki öğelere erişmek için kullanılmalıdır.

## <a name="rbegin"></a>  multimap::rbegin

Ters çevrilen bir çoklu eşlemde ilk öğeyi adresleyen bir yineleyici döndürür.

```cpp
const_reverse_iterator rbegin() const;

reverse_iterator rbegin();
```

### <a name="return-value"></a>Dönüş Değeri

Ters çevrilen bir çoklu eşlemde ilk öğeyi ele alan veya ne son öğeyi ters çevrilmeyen çoklu eşlemde adresleyen ters iki yönlü yineleyici.

### <a name="remarks"></a>Açıklamalar

`rbegin` ters çevrilen bir multimap ile kullanılan gibi [başlamak](#begin) ile çoklu eşlem kullanılır.

Varsa dönüş değeri `rbegin` atanan bir `const_reverse_iterator`, sonra da multimap nesnesi değiştirilemez. Varsa dönüş değeri `rbegin` atanan bir `reverse_iterator`, ardından multimap nesnesi değiştirilebilir.

`rbegin` bir çoklu eşlemde geriye doğru gezinmek için kullanılabilir.

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

## <a name="reference"></a>  multimap::Reference

Çoklu eşlem içinde depolan bir öğeye başvuru sağlayan bir tür.

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
   // non-const_reference cannot be used to access the key
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

## <a name="rend"></a>  multimap::rend

Ters çevrilen bir çoklu eşlemde son öğeden sonra gelen konumu ele alan bir yineleyici döndürür.

```cpp
const_reverse_iterator rend() const;

reverse_iterator rend();
```

### <a name="return-value"></a>Dönüş Değeri

(Ters çevrilmeyen çoklu eşlem ilk öğeyi önce gelen konum) ters çoklu eşlem içindeki son öğeden sonra gelen konumu ele ters iki yönlü yineleyici.

### <a name="remarks"></a>Açıklamalar

`rend` ters çevrilen bir multimap ile kullanılan gibi [son](../standard-library/map-class.md#end) ile çoklu eşlem kullanılır.

Varsa dönüş değeri `rend` atanan bir `const_reverse_iterator`, sonra da multimap nesnesi değiştirilemez. Varsa dönüş değeri `rend` atanan bir `reverse_iterator`, ardından multimap nesnesi değiştirilebilir.

`rend` olup ters yineleyici kendi multimap sonuna ulaşıp ulaşmadığını test etmek için kullanılabilir.

Tarafından döndürülen değer `rend` kaldırılmamalıdır.

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

## <a name="reverse_iterator"></a>  multimap::reverse_iterator

Okuma veya tersine çevrilmiş bir çoklu eşlemde bir öğe değiştirebilen çift yönlü bir yineleyici sağlayan tür.

```cpp
typedef std::reverse_iterator<iterator> reverse_iterator;
```

### <a name="remarks"></a>Açıklamalar

Bir tür `reverse_iterator` kullanın ters çoklu eşlemde yinelemek için.

`reverse_iterator` Nesnelerine multimap noktaları tarafından tanımlanan [value_type](#value_type), türü olan `pair<const Key, Type>`. Anahtar değeri ilk üye çift kullanılabilir ve eşlenen öğenin değeri çiftinin ikinci üye kullanılabilir.

Başvurulacak bir `reverse_iterator` *rIter* öğeye işaret eden bir çoklu eşlemde, kullanın **->** işleci.

Öğenin anahtarının değerini erişmek için `rIter->first`, eşdeğer olan `(*rIter).first`. Eşlenmiş veri öğesi için değeri erişmek için `rIter->second`, eşdeğer olan `(*rIter).second`.

### <a name="example"></a>Örnek

Örneğin bakın [rbegin](#rbegin) bildirme ve kullanma konusunda bir örnek için `reverse_iterator`.

## <a name="size"></a>  multimap::size

Çoklu eşlem öğelerin sayısını döndürür.

```cpp
size_type size() const;
```

### <a name="return-value"></a>Dönüş Değeri

Multimap geçerli uzunluğu.

### <a name="example"></a>Örnek

Aşağıdaki örnek, multimap::size üye işlevinin kullanımını gösterir.

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

## <a name="size_type"></a>  multimap::size_type

Bir çoklu eşlemde öğeleri sayar bir işaretsiz tamsayı türü.

```cpp
typedef typename allocator_type::size_type size_type;
```

### <a name="example"></a>Örnek

Örneğin bakın [boyutu](#size) bildirme ve kullanma örneği `size_type`

## <a name="swap"></a>  multimap::Swap

İki multimaps öğelerini birbiriyle değiştirir.

```cpp
void swap(
    multimap<Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*sağ*<br/>
Değiştirilecek öğeleri sağlayan multimap veya öğeleri olan çoklu eşlem olanlar değiştirilecek multimap `left`.

### <a name="remarks"></a>Açıklamalar

Üye işlev hiçbir başvurular, işaretçiler veya öğeleri değiştirilen iki multimaps öğeleri belirlemek yineleyicileri geçersiz kılar.

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

## <a name="upper_bound"></a>  multimap::upper_bound

Bir yineleyicinin ilk öğeye bir çoklu eşlemde belirtilen anahtardan daha büyük bir anahtarla döndürür.

```cpp
iterator upper_bound(const Key& key);

const_iterator upper_bound(const Key& key) const;
```

### <a name="parameters"></a>Parametreler

*Anahtarı*<br/>
Aranan multimap bir öğeyi sıralama anahtarı ile Karşılaştırılacak bağımsız değişken anahtarı.

### <a name="return-value"></a>Dönüş Değeri

Bir yineleyici veya `const_iterator` adresleri anahtar için bağımsız değişken anahtardan daha büyük ya da hiçbir eşlemde son öğeyi takip eden konumu ele bir anahtar ile eşleştiğinden emin çoklu eşlemdeki bir öğenin konumunu bulunamadı.

Dönüş değeri atanır, bir `const_iterator`, multimap nesnesi değiştirilemez. Dönüş değeri atanır, bir `iterator`, multimap nesnesi değiştirilebilir.

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

## <a name="value_comp"></a>  multimap::value_comp

Üye işlevi, anahtar değerlerini karşılaştırarak çoklu eşlem öğelerin sırasını belirleyen bir işlev nesnesi döndürür.

```cpp
value_compare value_comp() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir çoklu eşlemde kendi öğeleri sıralamak için kullanan bir karşılaştırma işlevi nesnesini döndürür.

### <a name="remarks"></a>Açıklamalar

Çoklu eşlem için *m*, iki öğe *e1*(*k1*, *d1*) ve *e2*(*k2*, *d2*) türündeki nesneler `value_type`burada *k1* ve *k2* türü kendi anahtarları `key_type` ve *d1*  ve *d2* kendi veri türü olan `mapped_type`, ardından `m.value_comp(e1, e2)` eşdeğerdir `m.key_comp(k1, k2)`.

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

## <a name="value_type"></a>  multimap::value_type

Bir eşlemdeki bir öğe olarak depolanan nesne türünü temsil eden tür.

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

[Kapsayıcılar](../cpp/containers-modern-cpp.md)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)<br/>
