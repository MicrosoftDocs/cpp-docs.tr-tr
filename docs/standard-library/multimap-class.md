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
ms.openlocfilehash: 2f6ae50a825d6eff2eb64c84b209fa81c4b7949f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81363849"
---
# <a name="multimap-class"></a>multimap Sınıfı

C++ Standart Kitaplığı çok eşlemeli sınıf, her öğenin hem veri değeri hem de sıralama anahtarı olan bir çift olduğu bir koleksiyondan veri depolamave alma için kullanılır. Anahtarın değerinin benzersiz olması gerekmez ve verileri otomatik olarak sıralamak için kullanılır. Çoklu eşlemdeki bir öğenin değeri doğrudan değiştirilebilir, ancak ilişkili anahtar değeri doğrudan değiştirilemez. Bunun yerine, eski öğelerle ilişkili anahtar değerleri silinmeli ve eklenen yeni öğelerle ilişkili yeni anahtar değerleri eklenmelidir.

## <a name="syntax"></a>Sözdizimi

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

*Türü*\
Çoklu eşlemde depolanacak öğe veri türü.

*Özellik*\
İki öğenin değerlerini çoklu eşlemde kendi göreli sıralarını belirlemek için sıralama anahtarları olarak karşılaştırabilen bir işlev nesnesi sağlayan tür. İkili yüklem `less<Key>` varsayılan değerdir.

C++14'te, tür parametreleri olmayan yüklemi `std::less<>` `std::greater<>` veya yüklemi belirterek heterojen bir arama yı etkinleştirebilirsiniz. Daha fazla bilgi için [Bkz. Bağşanlı Kaplarda Heterojen Arama](../standard-library/stl-containers.md#heterogeneous-lookup-in-associative-containers-c14)

*Ayırıcı*\
Eşlemin bellek ayırmayı ve ayırmayı kaldırma hakkındaki ayrıntıları içeren saklı ayırıcı nesnesini gösteren tür. Bu bağımsız değişken isteğe `allocator<pair <const Key, Type> >`bağlıdır ve varsayılan değer .

## <a name="remarks"></a>Açıklamalar

C++ Standart Kitaplığı çok haritalı sınıf

- İlişkili bir anahtar değerine dayalı öğe değerlerinin verimli alınmasını destekleyen bir değişken boyutu kapsayıcı olan ilişkilendirilebilir bir kapsayıcı.

- Çift yönlüdür, çünkü öğelerine erişmek için çift yönlü yineleyiciler sağlar.

- Sıralıdır, çünkü öğeleri belirtilen karşılaştırma işlevine uygun olarak kapsayıcı içindeki anahtar değerlere göre sıralanır.

- Öğelerinin benzersiz anahtarlara ihtiyacı olmaması için çokludur, böylece bir anahtar değer onunla ilişkili çok sayıda öğe verisi değerine sahip olabilir.

- Bir çift ilişkilendirilebilir kapsayıcıdır, çünkü veri öğelerinin değerleri kendi anahtar değerlerinden farklıdır.

- Sağladığı işlevsellik genel olduğundan ve öğe veya anahtar olarak bulunan belirli veri türünden bağımsız olduğundan, sınıf şablonu. Öğeler ve anahtarlar için kullanılacak veri türleri, karşılaştırma işlevi ve ayırıcı ile birlikte bir sınıf şablonunda parametreler olarak belirtilir.

Harita sınıfı tarafından sağlanan yineleme çift yönlü bir yinelemedir, ancak sınıf üye işlevleri [ekleme](#insert) ve [çoklu harita,](#multimap) işlevsellik gereksinimleri çift yönlü yineleyiciler sınıfı tarafından garanti edilenden daha az olan şablon parametreleri olarak daha zayıf bir giriş yineleyicisi alan sürümleri vardır. Farklı yineleyici kavramları, işlevselliklerindeki iyileştirmelere göre ilgili bir aile biçimlendirir. Her yineleyici kavramının kendi gereksinimler kümesi vardır ve bunlarla çalışan algoritmaların kendi varsayımlarını yineleyici türü tarafından sağlanan gereksinimlerle sınırlaması gerekir. Bir giriş yineleyicinin bazı nesnelere başvurusunun kaldırılacağı ve dizideki sonraki yineleyiciye artırılabileceği varsayılabilir. Bu en az işlevsellik kümesidir, ancak sınıfın üye işlevleri bağlamında bir dizi `[First, Last)` yineleyici hakkında anlamlı bir şekilde konuşabilmek yeterlidir.

Kapsayıcı türünün seçimi genelde uygulamanın gerektirdiği arama ve ekleme türüne dayalı olmalıdır. İlişkilendirilebilir kapsayıcılar, arama, ekleme ve kaldırma işlemleri için en iyi duruma getirilir. Bu işlemleri açıkça destekleyen üye işlevleri, işlevlerini kapsayıcıdaki öğelerin sayısının logaritmasına ortalama orantılı bir sürede gerçekleştirir ve verimlidir. Öğelerin eklenmesi hiçbir yineleyiciyi geçersiz kılmaz; öğelerin kaldırılması yalnızca özellikle kaldırılan öğeleri gösteren yineleyicileri geçersiz kılar.

Çoklu eşlem, değerleri onların kendi anahtarlarıyla ilişkilendiren koşullar uygulama tarafından karşılandığında seçimin ilişkili kapsayıcısı olmalıdır. Bu tür bir yapı için model, mesela açıklamalar sağlayan dize değerleriyle ilişkili anahtar sözcüklerin sıralı bir listesidir, burada sözcükler her zaman benzersiz olarak tanımlanmamıştır. Bunun yerine anahtar sözcükler benzersiz olarak tanımlanırsa, seçilecek kapsayıcı bir eşlem olurdu. Diğer taraftan, yalnızca sözcüklerin listesi depolanmaktadır, ardından bir küme doğru kapsayıcı olacaktır. Sözcüklerin birden çok defa geçmelerine izin verilirse, bir çoklu küme uygun bir kapsayıcı yapısı olacaktır.

Çok eşli, denetlenen [sırayı,](#key_compare)key_compare türünde depolanmış bir işlev nesnesini çağırarak sıralar. Bu depolanan nesne, üye işlevi [key_comp](#key_comp)çağırarak erişilebilen bir karşılaştırma işlevidir. Genelde, bu sıralamayı oluşturmak için öğelerin yalnızca küçüktür biçiminde karşılaştırılabilir olması gerekir; böylece, herhangi iki öğe belirtildiğinde, eşit oldukları (yani birinin diğerinden daha küçük olmadığı anlamında) veya birinin diğerinden küçük olduğu belirlenebilir. Bu, denk olmayan öğeler arasında bir sıralamaya neden olur. Daha teknik bir not üzerinde, karşılaştırma işlevi standart matematiksel anlamda katı bir zayıf sıralama sevk eden ikili bir koşuldur. İkili yüklem, `f(x,y)` iki bağımsız değişken nesnesi `x` `y` ve doğru veya yanlışın dönüş değeri olan bir işlev nesnesidir. İkili yüklem refleksif, antisimetrik ve geçişli ise ve eşdeğerlik geçişli ise, iki nesne `x` ve `y` her ikisi de `f(x,y)` `f(y,x)` ve yanlış olduğunda eşdeğer olarak tanımlanan bir diziliş sıkı bir zayıf sıralamadır. Anahtarlar arasındaki eşitliğinin daha güçlü koşulu bu denkliğin yerini alırsa, sıralama (içindeki tüm öğelerin birbirine göre sıralanması anlamında) toplam haline gelir ve eşleşen anahtarlar birbirinden ayırt edilemez olacaktır.

C++14'te, tür parametreleri olmayan yüklemi `std::less<>` `std::greater<>` veya yüklemi belirterek heterojen bir arama yı etkinleştirebilirsiniz. Daha fazla bilgi için [Bkz. Bağşanlı Kaplarda Heterojen Arama](../standard-library/stl-containers.md#sequence_containers)

## <a name="members"></a>Üyeler

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[Multimap](#multimap)|Boş olan `multimap` veya başka `multimap`bir şeyin tamamının veya bir kısmının kopyası olan bir yapı.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[Allocator_type](#allocator_type)|Nesnenin sınıfını `allocator` `multimap` temsil eden bir tür.|
|[const_iterator](#const_iterator)|`multimap`Bir **const** öğesi okuyabilen çift yönlü bir yineleme sağlayan bir tür.|
|[Const_pointer](#const_pointer)|Bir **const** öğesine işaretçi sağlayan `multimap`bir tür .|
|[const_reference](#const_reference)|Const **işlemleri** okumak ve gerçekleştirmek için bir `multimap` **const** öğesinde depolanan bir öğeye başvuru sağlayan bir tür.|
|[Const_reverse_iterator](#const_reverse_iterator)|Herhangi bir const öğeyi okuyabilen çift yönlü bir yineleme sağlayan bir tür. **const** `multimap`|
|[difference_type](#difference_type)|Yineleyiciler tarafından işaret edilen öğeler arasındaki aralıktaki bir `multimap` aralığın öğelerinin sayısını temsil etmek için kullanılabilecek imzalı bir tamsayı türü.|
|[Yineleyici](#iterator)|Aynı `multimap`içindeki öğelere başvuran iki yineleyici arasındaki farkı sağlayan bir tür.|
|[Key_compare](#key_compare)|İki öğenin göreli sırasını belirlemek için iki sıralama anahtarını karşılaştırabilen bir işlev nesnesi `multimap`sağlayan bir tür.|
|[Key_type](#key_type)|`multimap`Her öğeyi oluşturan sıralama anahtar nesnesini açıklayan bir tür.|
|[mapped_type](#mapped_type)|Bir 'de depolanan veri türünü `multimap`temsil eden bir tür|
|[pointer](#pointer)|Bir **const** öğesine işaretçi sağlayan `multimap`bir tür .|
|[Başvuru](#reference)|Bir 'de depolanan bir öğeye `multimap`başvuru sağlayan bir tür|
|[Reverse_iterator](#reverse_iterator)|Ters bir öğedeki bir öğeyi okuyabilen veya değiştirebilen `multimap`çift yönlü bir yineleme sağlayan bir tür.|
|[size_type](#size_type)|Bir `multimap`'deki **const** öğesine işaretçi sağlayan imzasız bir tamsayı türü|
|[value_type](#value_type)|İki öğeyi sıraanahtarları olarak karşılaştırabilen bir işlev nesnesi `multimap`sağlayan bir tür.|

### <a name="member-functions"></a>Üye işlevler

|Üye fonksiyonu|Açıklama|
|-|-|
|[Başlamak](#begin)|'deki ilk öğeyi ele alan bir `multimap`yineleyici döndürür.|
|[cbegin](#cbegin)|'deki ilk öğeyi ele alan bir const yineleyici döndürür. `multimap`|
|[cend](#cend)|Bir `multimap`'deki son öğeyi yerine getiren konumu gideren bir const yineleyici döndürür.|
|[Temizleyin](#clear)|Bir' `multimap`nin tüm öğelerini siler.|
|[Sayısı](#count)|Anahtarı parametre yle `multimap` belirtilen bir anahtarla eşleşen bir öğedeki öğe sayısını döndürür.|
|[crbegin](#crbegin)|Ters bir ilk öğeyi ele alan bir const yineleyici döndürür. `multimap`|
|[crend](#crend)|Ters bir önceki son öğeyi yerine getiren konumu gideren bir `multimap`const yineleyici döndürür.|
|[emplace](#emplace)|Yerinde inşa edilmiş bir öğeyi `multimap`bir .|
|[emplace_hint](#emplace_hint)|Yerinde `multimap`inşa edilmiş bir öğeyi yerleştirme ipucuyla ekler|
|[empty](#empty)|A boşsa `multimap` sınar.|
|[Son -unda](#end)|Bir 'deki son öğeyi yerine getiren konumu adresleyen `multimap`bir yineleyici döndürür.|
|[equal_range](#equal_range)|Öğenin anahtarının belirtilen değerle eşleştiği öğeler aralığını bulur.|
|[Silmek](#erase)|Belirtilen konumlardaki `multimap` bir öğeyi veya bir dizi öğeyi kaldırır veya belirtilen anahtarla eşleşen öğeleri kaldırır.|
|[find](#find)|Belirli bir anahtara eşdeğer `multimap` anahtara sahip bir öğenin ilk konumunu ele alan bir yineleyici döndürür.|
|[Get_allocator](#get_allocator)|Oluşturmak için kullanılan `allocator` nesnenin bir `multimap`kopyasını döndürür.|
|[Ekle](#insert)|Bir öğeye veya bir dizi öğeye `multimap`bir öğe ekler.|
|[Key_comp](#key_comp)|Bir `multimap`'deki anahtarları sipariş etmek için kullanılan karşılaştırma nesnesinin bir kopyasını alır.|
|[lower_bound](#lower_bound)|Bir yineleyiciyi, belirtilen bir anahtara eşit veya daha büyük bir anahtarla bir ilk öğeye `multimap` döndürür.|
|[max_size](#max_size)|Maksimum uzunluğu `multimap`verir.|
|[rbegin](#rbegin)|Ters bir ilk öğeyi ele alan bir `multimap`yineleyici döndürür.|
|[Rend](#rend)|Ters çevrilmiş bir son öğedeki son öğeyi yerine `multimap`getiren konumu adresleyen bir yineleyici döndürür.|
|[Boyutu](#size)|`multimap`'deki öğe sayısını verir.|
|[Takas](#swap)|İki `multimap`s'nin öğelerini değiştirir.|
|[upper_bound](#upper_bound)|Bir yineleyiciyi, belirtilen bir anahtardan büyük bir anahtarla ilk öğeye `multimap` döndürür.|
|[value_comp](#value_comp)|Üye işlev, anahtar değerlerini karşılaştırarak bir `multimap` öğedeki öğelerin sırasını belirleyen bir işlev nesnesi döndürür.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[işleç=](#op_eq)|Bir `multimap` öğenin öğelerini başka `multimap`bir kopyayla değiştirir.|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** \<harita>

**Ad alanı:** std

( **anahtar**, **değer**) çiftleri, tür `pair`nesneleri olarak çok eşlilik içinde depolanır. Çift sınıfı, \< \<harita> tarafından otomatik olarak dahil edilen başlık yardımcı> gerektirir.

## <a name="multimapallocator_type"></a><a name="allocator_type"></a>çok harita::allocator_type

Çok eşli nesnesi için ayırıcı sınıfını temsil eden bir tür.

```cpp
typedef Allocator allocator_type;
```

### <a name="example"></a>Örnek

get_allocator örneğini [get_allocator](#get_allocator) kullanarak `allocator_type`bir örneğe bakın.

## <a name="multimapbegin"></a><a name="begin"></a>çok eşli::başla

Çok haritadaki ilk öğeyi ele alan bir yineleyici döndürür.

```cpp
const_iterator begin() const;

iterator begin();
```

### <a name="return-value"></a>Dönüş Değeri

Çoklu haritadaki ilk öğeyi veya boş bir çoklu haritayı başaran konumu ele alan çift yönlü bir yineleyici.

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

## <a name="multimapcbegin"></a><a name="cbegin"></a>çok harita::cbegin

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

## <a name="multimapcend"></a><a name="cend"></a>çok eşli::cend

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

## <a name="multimapclear"></a><a name="clear"></a>çok harita::net

Çoklu haritanın tüm öğelerini siler.

```cpp
void clear();
```

### <a name="example"></a>Örnek

Aşağıdaki örnek, çoklu haritanın kullanımını göstermektedir::net üye işlevi.

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

## <a name="multimapconst_iterator"></a><a name="const_iterator"></a>çok harita::const_iterator

Çok haritada bir **const** öğesi okuyabilen çift yönlü bir yineleme sağlayan bir tür.

```cpp
typedef implementation-defined const_iterator;
```

### <a name="remarks"></a>Açıklamalar

Bir `const_iterator` tür, bir öğenin değerini değiştirmek için kullanılamaz.

Çok `const_iterator` eşli noktalarla tanımlanan [value_type](#value_type)nesneleri , `pair<const Key, Type>`türü vardır . Anahtarın değeri ilk üye çift aracılığıyla kullanılabilir ve eşlenen öğenin değeri çiftin ikinci üyesi aracılığıyla kullanılabilir.

Çok haritadaki `const_iterator` bir öğeyi işaret eden bir *cIter'ı* belirtmek için **->** işleci kullanın.

Öğe için anahtarın değerine erişmek `cIter->first`için, 'ye `(*cIter).first`eşdeğer olan ' ı kullanın. Öğe için eşlenen datum değerine erişmek için, 'ye `cIter->second` `(*cIter).second`eşdeğer olan ' ı kullanın.

### <a name="example"></a>Örnek

Bir örneğin [ikullanarak](#begin) `const_iterator`başlatılamıörneğine bakın.

## <a name="multimapconst_pointer"></a><a name="const_pointer"></a>çok harita::const_pointer

Çok eşlilikteki **const** öğesine işaretçi sağlayan bir tür.

```cpp
typedef typename allocator_type::const_pointer const_pointer;
```

### <a name="remarks"></a>Açıklamalar

Bir `const_pointer` tür, bir öğenin değerini değiştirmek için kullanılamaz.

Çoğu durumda, çok eşli bir nesnedeki öğelere erişmek için bir [yineleyici](#iterator) kullanılmalıdır.

## <a name="multimapconst_reference"></a><a name="const_reference"></a>çok harita::const_reference

**Const** işlemleri okumak ve gerçekleştirmek için çok eşlilikte depolanan **bir const** öğesine başvuru sağlayan bir tür.

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

## <a name="multimapconst_reverse_iterator"></a><a name="const_reverse_iterator"></a>çok harita::const_reverse_iterator

Çoklu haritadaki herhangi bir **const** öğeyi okuyabilen çift yönlü bir yineleme sağlayan bir tür.

```cpp
typedef std::reverse_iterator<const_iterator> const_reverse_iterator;
```

### <a name="remarks"></a>Açıklamalar

Bir `const_reverse_iterator` tür bir öğenin değerini değiştiremez ve çoklu harita üzerinden ters olarak yinelemek için kullanılır.

Çok `const_reverse_iterator` eşli noktalarla tanımlanan [value_type](#value_type)nesneleri , `pair<const Key, Type>`türü vardır . Anahtarın değeri ilk üye çift aracılığıyla kullanılabilir ve eşlenen öğenin değeri çiftin ikinci üyesi aracılığıyla kullanılabilir.

Çok eşlemedeki bir öğeyi işaret eden bir `const_reverse_iterator` *crIter'ı* belirtmek için **->** işleci kullanın.

Öğe için anahtarın değerine erişmek `crIter->first`için, 'ye `(*crIter).first`eşdeğer olan ' ı kullanın. Öğe için eşlenen datum değerine erişmek için, 'ye `crIter->second` `(*crIter).first`eşdeğer olan ' ı kullanın.

### <a name="example"></a>Örnek

Nasıl bildirilir ve kullanılacağına `const_reverse_iterator`bir örnek için [rend](#rend) örneğine bakın.

## <a name="multimapcount"></a><a name="count"></a>çok eşli::say

Anahtarları parametre belirtilen bir anahtarla eşleşen bir çok eşlemedeki eleman sayısını döndürür.

```cpp
size_type count(const Key& key) const;
```

### <a name="parameters"></a>Parametreler

*Anahtar*\
Çoklu haritadan eşleşecek öğelerin anahtarı.

### <a name="return-value"></a>Dönüş Değeri

Sıralama anahtarları parametre anahtarıyla eşleşen öğelerin sayısı; 0 multimap eşleşen bir anahtar ile bir öğe içermiyorsa.

### <a name="remarks"></a>Açıklamalar

Üye işlev aralıktaki eleman sayısını döndürür

\[lower_bound (*anahtar*), upper_bound (*anahtar*)

bir anahtar *değeri anahtarı*var.

### <a name="example"></a>Örnek

Aşağıdaki örnek, çoklu haritanın kullanımını gösterir::count üye işlevi.

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

## <a name="multimapcrbegin"></a><a name="crbegin"></a>çok harita::crbegin

Ters bir çoklu haritadaki ilk öğeyi ele alan bir const yineleyici döndürür.

```cpp
const_reverse_iterator crbegin() const;
```

### <a name="return-value"></a>Dönüş Değeri

Ters bir [çok haritadaki](../standard-library/multimap-class.md) ilk öğeyi ele alan veya ters çevrilmemiş `multimap`son öğeyi ele alan const ters yönlü bir yineleme.

### <a name="remarks"></a>Açıklamalar

`crbegin`bir ile kullanılır `multimap` gibi [begin](#begin) bir ters `multimap`kullanılır .

İade değeri ile `crbegin` `multimap` nesne değiştirilemez.

`crbegin``multimap` geriye doğru doğrulamak için kullanılabilir.

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

## <a name="multimapcrend"></a><a name="crend"></a>çok eşli::crend

Ters bir çok haritada son öğeyi yerine getiren konumu gideren bir const yineleyici döndürür.

```cpp
const_reverse_iterator crend() const;
```

### <a name="return-value"></a>Dönüş Değeri

Ters bir [çok haritadaki](../standard-library/multimap-class.md) son öğeyi başaran konumu gideren const ters çift yönlü yineleme (ters çevrilmemiş `multimap`ilk öğeden önce gelen konum).

### <a name="remarks"></a>Açıklamalar

`crend`multimap gibi `multimap` ters [kullanılır::end](#end) ile kullanılır `multimap`.

İade değeri ile `crend` `multimap` nesne değiştirilemez.

`crend`ters yineleyicinin sonuna ulaşıp ulaşmadığını test etmek için `multimap`kullanılabilir.

Döndürülen `crend` değer dereferenced olmamalıdır.

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

## <a name="multimapdifference_type"></a><a name="difference_type"></a>çok eşli::difference_type

Yineleyiciler tarafından işaret edilen öğeler arasındaki aralıkta bir çok haritanın eleman sayısını temsil etmek için kullanılabilecek imzalı bir tamsayı türü.

```cpp
typedef typename allocator_type::difference_type difference_type;
```

### <a name="remarks"></a>Açıklamalar

Kapsayıcının `difference_type` yineleyicileri arasından çıkarılırken veya artarken döndürülen türdür. Genellikle `difference_type` yinelemeciler `first` arasındaki *[ilk*, *son*) aralığındaki öğelerin sayısını temsil `last`etmek için kullanılır `first` ve , tarafından işaret edilen öğe ve öğe aralığı `last`kadar, ancak dahil değil, öğe tarafından işaret içerir.

Küme gibi `difference_type` geri döndürülebilir kapsayıcılar tarafından desteklenen çift yönlü yineleyiciler sınıfını içeren bir giriş yineleyicisinin gereksinimlerini karşılayan tüm yineleyiciler için kullanılabilir olmasına rağmen, yineleyiciler arasındaki çıkarma yalnızca vektör gibi rasgele erişimli bir kapsayıcı tarafından sağlanan rasgele erişim yinelemeleri tarafından desteklenir.

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

## <a name="multimapemplace"></a><a name="emplace"></a>çok harita::emplace

Yerinde oluşturulmuş bir öğe ekler (kopyalama veya taşıma işlemleri yapılmaz).

```cpp
template <class... Args>
iterator emplace(Args&&... args);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|-|-|
|*Args*|Çok eşliliğe eklenecek bir öğe oluşturmak için iletilen bağımsız değişkenler.|

### <a name="return-value"></a>Dönüş Değeri

Yeni eklenen öğeiçin bir yineleyici.

### <a name="remarks"></a>Açıklamalar

Kapsayıcı öğelere yapılan başvurular bu işlev tarafından geçersiz kılınz, ancak kapsayıcıya tüm yineleyicileri geçersiz kılabilir.

Ekleme sırasında bir özel durum atılırsa, kapsayıcı değiştirilmeden bırakılır ve özel durum yeniden atılır.

Bir öğenin [value_type](../standard-library/map-class.md#value_type) bir çifttir, böylece bir öğenin değeri ilk bileşen anahtar değerine eşit, ikinci bileşen ise öğenin veri değerine eşit sıralı bir çift olacaktır.

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

## <a name="multimapemplace_hint"></a><a name="emplace_hint"></a>çok harita::emplace_hint

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
|*Args*|Çok eşliliğe eklenecek bir öğe oluşturmak için iletilen bağımsız değişkenler.|
|*Nerede*|Doğru ekleme noktasını aramaya başlamak için yer. (Bu nokta hemen *önce,* ekleme logaritmik zaman yerine amortismanlı sabit zaman oluşabilir.)|

### <a name="return-value"></a>Dönüş Değeri

Yeni eklenen öğeiçin bir yineleyici.

### <a name="remarks"></a>Açıklamalar

Kapsayıcı öğelere yapılan başvurular bu işlev tarafından geçersiz kılınz, ancak kapsayıcıya tüm yineleyicileri geçersiz kılabilir.

Yerleşim sırasında, bir özel durum atılırsa, kapsayıcının durumu değiştirilmez.

Bir öğenin [value_type](../standard-library/map-class.md#value_type) bir çifttir, böylece bir öğenin değeri ilk bileşen anahtar değerine eşit, ikinci bileşen ise öğenin veri değerine eşit sıralı bir çift olacaktır.

Kod örneği için [bkz: harita::emplace_hint](../standard-library/map-class.md#emplace_hint).

## <a name="multimapempty"></a><a name="empty"></a>çok eşli::boş

Çok eşliboşsa sınar.

```cpp
bool empty() const;
```

### <a name="return-value"></a>Dönüş Değeri

çoklu harita boşsa **doğrudur;** çoklu harita boş değilse **false.**

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

## <a name="multimapend"></a><a name="end"></a>çok eşli::uç

past-the-end yineleyici döndürür.

```cpp
const_iterator end() const;

iterator end();
```

### <a name="return-value"></a>Dönüş Değeri

Son sınıf yineleme. Çoklu harita boşsa, `multimap::end() == multimap::begin()`o zaman.

### <a name="remarks"></a>Açıklamalar

**sonu,** bir yineleyicinin çoklu haritasının sonundan geçip geçmediğini test etmek için kullanılır.

**Sonuna kadar** döndürülen değer dereferenced olmamalıdır.

Kod örneği [için, bkz.](#find)

## <a name="multimapequal_range"></a><a name="equal_range"></a>çok harita::equal_range

Öğenin anahtarının belirtilen değerle eşleştiği öğeler aralığını bulur.

```cpp
pair <const_iterator, const_iterator> equal_range (const Key& key) const;

pair <iterator, iterator> equal_range (const Key& key);
```

### <a name="parameters"></a>Parametreler

*Anahtar*\
Aralanan çoklu haritadaki bir öğenin tür anahtarıyla karşılaştırılacak bağımsız değişken anahtarı.

### <a name="return-value"></a>Dönüş Değeri

İlki anahtarın [lower_bound,](#lower_bound) ikincisi anahtarın [upper_bound](#upper_bound) olacak şekilde bir çift yineleyici.

Üye işlev tarafından döndürülen bir `pr` çiftin ilk yineleyicisine `pr`erişmek için. **ilk** ve alt sınır yineleyici dereference \*için, kullanın ( `pr`. **ilk**). Üye işlev tarafından döndürülen bir `pr` çiftin ikinci yineleyicisine `pr`erişmek için. **ikinci** ve üst sınır yineleyici dereference \*için, kullanın ( `pr`. **ikinci**).

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

## <a name="multimaperase"></a><a name="erase"></a>çok eşli::silme

Çok eşlemeli bir öğeyi veya bir dizi öğeyi belirtilen konumlardan kaldırır veya belirtilen anahtarla eşleşen öğeleri kaldırır.

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
Kaldırılacak öğelerin anahtarı.

### <a name="return-value"></a>Dönüş Değeri

İlk iki üye işlev için, kaldırılan öğelerin ötesinde kalan ilk öğeyi belirleyen çift yönlü bir yineleyici veya böyle bir öğe yoksa haritanın sonu olan bir öğe.

Üçüncü üye işlev için, çoklu haritadan kaldırılan öğe sayısını döndürür.

### <a name="remarks"></a>Açıklamalar

Kod örneği için [bkz: harita::sil](../standard-library/map-class.md#erase).

## <a name="multimapfind"></a><a name="find"></a>çok harita::bul

Belirli bir anahtara eşdeğer anahtara sahip bir çok haritadaki bir öğenin ilk konumunu ifade eden bir yineleyici döndürür.

```cpp
iterator find(const Key& key);

const_iterator find(const Key& key) const;
```

### <a name="parameters"></a>Parametreler

*Anahtar*\
Aranmakta olan çoklu haritadaki bir öğenin sıralama anahtarıyla eşleşecek anahtar değeri.

### <a name="return-value"></a>Dönüş Değeri

Belirli bir anahtara sahip bir öğenin konumunu veya anahtar için eşleşme bulunamazsa multimap`multimap::end()`()deki son öğeyi başaran konumu ifade eden bir yineleyici.

### <a name="remarks"></a>Açıklamalar

Üye işlev, çoklu haritadaki bir öğeyi ifade eden ve sıralama anahtarı, karşılaştırılabilirlik ilişkisinden daha az bir ilişkiye dayalı bir sıralamayı neden eden ikili bir yüklem altında bağımsız değişken anahtarına eşdeğer olan bir öğeyi döndürür.

Bir `find` `const_iterator`, multimap nesnesi için return value atanırsa değiştirilemez. Bir `find` `iterator`, multimap nesnesi için return value atanırsa değiştirilebilir.

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

## <a name="multimapget_allocator"></a><a name="get_allocator"></a>çok eşli::get_allocator

Çok haritayı oluşturmak için kullanılan ayırıcı nesnenin bir kopyasını döndürür.

```cpp
allocator_type get_allocator() const;
```

### <a name="return-value"></a>Dönüş Değeri

Çok harita tarafından kullanılan ayırıcı.

### <a name="remarks"></a>Açıklamalar

Çok eşli sınıfının ayırıcıları sınıfın depolamayı nasıl yönettiğini belirtir. C++ Standart Kitaplık kapsayıcı sınıfları ile birlikte verilen varsayılan ayırıcılar çoğu programlama gereksinimleri için yeterlidir. Kendi ayırıcı sınıfınızı yazmak ve kullanmak gelişmiş bir C++ konusudur.

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

## <a name="multimapinsert"></a><a name="insert"></a>çok eşli::insert

Bir öğeyi veya bir dizi öğeyi çok eşliliğe ekler.

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
|*Val*|Çoklu haritaya eklenecek bir öğenin değeri.|
|*Nerede*|Doğru ekleme noktasını aramaya başlamak için yer. (Bu nokta hemen *nerede,* ekleme logaritmik zaman yerine amortismanlı sabit zaman oluşabilir önce gelir.)|
|*Valty*|Haritanın [value_type](../standard-library/map-class.md#value_type)bir öğe oluşturmak için kullanabileceği bağımsız değişken türünü belirten şablon parametresi ve val'i *Val* bağımsız değişken olarak mükemmel iletme.|
|*Ilk*|Kopyalanacak ilk öğenin konumu.|
|*Son*|Kopyalanacak son öğenin hemen ötesindeki konum.|
|*GirişIterator*|Value_type [nesneleri](../standard-library/map-class.md#value_type) oluşturmak için kullanılabilecek bir tür öğeleri işaret eden bir [giriş yineleyici](../standard-library/input-iterator-tag-struct.md) gereksinimlerini karşılayan şablon işlev bağımsız değişkeni.|
|*ılist*|Öğeleri kopyalamak için [initializer_list.](../standard-library/initializer-list.md)|

### <a name="return-value"></a>Dönüş Değeri

Tek öğeeklemeli üye işlevler (1) ve (2), bir yineleyiciyi yeni öğenin çoklu eşeme eklendiği konuma döndürür.

İpucu ile tek elemanlı üye işlevler( 3) ve (4), yeni öğenin çoklu haritaya eklendiği konuma işaret eden bir yineleyici döndürür.

### <a name="remarks"></a>Açıklamalar

Bu işlev tarafından hiçbir işaretçi veya başvuru geçersiz kılındı, ancak kapsayıcıya tüm yineleyicileri geçersiz kılabilir.

Tek bir öğenin eklenmesi sırasında, bir özel durum atılırsa, kapsayıcının durumu değiştirilmez. Birden çok öğe nin eklenmesi sırasında, bir özel durum atılırsa, kapsayıcı belirtilmemiş ancak geçerli bir durumda bırakılır.

Bir kapsayıcının [value_type](../standard-library/map-class.md#value_type) kapsayıcıya ait bir typedef ve `multimap<K, V>::value_type` harita `pair<const K, V>`için, . Bir öğenin değeri, ilk bileşenin anahtar değerine eşit, ikinci bileşenin ise öğenin veri değerine eşit olduğu sıralı bir çifttir.

Aralık üye işlevi (5), aralıktaki bir yineleyici tarafından ele verilen her öğeye karşılık gelen bir çok `[First, Last)`haritaya öğe değerlerinin sırasını ekler; bu nedenle, *Son* takılı almaz. Kapsayıcı üye `end()` işlevi, kapsayıcıdaki son öğeden hemen sonra konumu ifade `m.insert(v.begin(), v.end());` eder—örneğin, `v` deyim `m`tüm öğeleri .

Initializer list üye işlevi (6) öğeleri haritaya kopyalamak için bir [initializer_list](../standard-library/initializer-list.md) kullanır.

Yerinde inşa edilmiş bir öğenin eklenmesi için-yani, hiçbir kopyalama veya taşıma işlemleri gerçekleştirilir—bkz. [multimap::emplace](#emplace) ve [multimap::emplace_hint](#emplace_hint).

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

## <a name="multimapiterator"></a><a name="iterator"></a>çok harita::iterator

Çok eşlilikteki herhangi bir öğeyi okuyabilen veya değiştirebilen çift yönlü bir yineleme sağlayan bir tür.

```cpp
typedef implementation-defined iterator;
```

### <a name="remarks"></a>Açıklamalar

Çok `iterator` eşli noktalarla tanımlanan [value_type](#value_type)nesneleri , `pair<const Key, Type>`türü vardır . Anahtarın değeri ilk üye çift aracılığıyla kullanılabilir ve eşlenen öğenin değeri çiftin ikinci üyesi aracılığıyla kullanılabilir.

Çok eşlemeli bir öğeyi işaret eden bir `iterator` **->** *Iter'ı* belirtmek için işleci kullanın.

Öğe için anahtarın değerine erişmek `Iter->first`için, 'ye `(*Iter).first`eşdeğer olan ' ı kullanın. Öğe için eşlenen datum değerine erişmek için, 'ye `Iter->second` `(*Iter).second`eşdeğer olan ' ı kullanın.

Bir `iterator` tür, bir öğenin değerini değiştirmek için kullanılabilir.

### <a name="example"></a>Örnek

Nasıl bildirilir [begin](#begin) ve kullanılacağına `iterator`bir örnek için başlangıç örneğine bakın.

## <a name="multimapkey_comp"></a><a name="key_comp"></a>çok harita::key_comp

Çok eşlilikte anahtarları sipariş etmek için kullanılan karşılaştırma nesnesinin bir kopyasını alır.

```cpp
key_compare key_comp() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir çok haritanın öğelerini sıralamak için kullandığı işlev nesnesini döndürür.

### <a name="remarks"></a>Açıklamalar

Depolanan nesne üye işlevi tanımlar

`bool operator( const Key& x, const Key& y);`

*x* kesinlikle sıralama sırasına göre *y'den* önce yse doğru döner.

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

## <a name="multimapkey_compare"></a><a name="key_compare"></a>çok harita::key_compare

Çoklu eşmedeki iki öğenin göreli sırasını belirlemek için iki sıralama anahtarını karşılaştırabilen bir işlev nesnesi sağlayan bir tür.

```cpp
typedef Traits key_compare;
```

### <a name="remarks"></a>Açıklamalar

`key_compare`şablon parametresi `Traits`ile eş anlamlıdır.

[Çok eşli Sınıf](../standard-library/multimap-class.md) konusu hakkında `Traits` daha fazla bilgi için bkz.

### <a name="example"></a>Örnek

Nasıl bildirilir [key_comp](#key_comp) ve kullanılacağına `key_compare`ilgili bir örnek için key_comp örneğine bakın.

## <a name="multimapkey_type"></a><a name="key_type"></a>çok harita::key_type

Çok eşliliğin her öğesini oluşturan sıralama anahtar nesnesini açıklayan bir tür.

```cpp
typedef Key key_type;
```

### <a name="remarks"></a>Açıklamalar

`key_type`şablon parametresi `Key`ile eş anlamlıdır.

Daha fazla `Key`bilgi [için, çok eşli sınıf](../standard-library/multimap-class.md) konusunun Açıklamalar bölümüne bakın.

### <a name="example"></a>Örnek

[Nasıl](#value_type) beyan value_type ve kullanılacağına `key_type`bir örnek için bkz.

## <a name="multimaplower_bound"></a><a name="lower_bound"></a>çok harita::lower_bound

Bir çok eşlemedeki ilk öğeye, belirtilen anahtara eşit veya daha büyük bir anahtarla bir yineleyici döndürür.

```cpp
iterator lower_bound(const Key& key);

const_iterator lower_bound(const Key& key) const;
```

### <a name="parameters"></a>Parametreler

*Anahtar*\
Aralanan çoklu haritadaki bir öğenin tür anahtarıyla karşılaştırılacak bağımsız değişken anahtarı.

### <a name="return-value"></a>Dönüş Değeri

Bir yineleyici veya `const_iterator` bağımsız değişken anahtarına eşit veya daha büyük bir anahtarla veya anahtar için eşleşme bulunamazsa çok eşlemedeki son öğeyi başaran konumu ele alan bir çok eşlilikteki öğenin konumunu gideren.

Bir `lower_bound` `const_iterator`, multimap nesnesi için return value atanırsa değiştirilemez. Bir `lower_bound` **yineleyiciye**atanırsa, çok eşlilik nesnesi değiştirilebilir.

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

## <a name="multimapmapped_type"></a><a name="mapped_type"></a>çok harita::mapped_type

Çoklu haritada depolanan veri türünü temsil eden bir tür.

```cpp
typedef Type mapped_type;
```

### <a name="remarks"></a>Açıklamalar

`mapped_type`şablon parametresi `Type`ile eş anlamlıdır.

[Çok eşli Sınıf](../standard-library/multimap-class.md) konusu hakkında `Type` daha fazla bilgi için bkz.

### <a name="example"></a>Örnek

[Nasıl](#value_type) beyan value_type ve kullanılacağına `key_type`bir örnek için bkz.

## <a name="multimapmax_size"></a><a name="max_size"></a>çok eşli::max_size

Çoklu haritanın maksimum uzunluğunu verir.

```cpp
size_type max_size() const;
```

### <a name="return-value"></a>Dönüş Değeri

Çoklu haritanın mümkün olan en yüksek uzunluğu.

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

## <a name="multimapmultimap"></a><a name="multimap"></a>çok harita::multimap

Boş veya başka bir çok haritanın tamamının veya bir kısmının kopyası olan bir çok eşlilik oluşturur.

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
|*Al*|Bu çok eşli nesne için kullanılacak depolama ayırıcı sınıfı, bu allocator varsayılan.|
|*Comp*|Eşdeki öğeleri `constTraits` sıralamak için kullanılan tür deki karşılaştırma `Traits`işlevi, varsayılan olarak .|
|*Doğru*|Yapılandırılan kümenin bir kopyası olması gereken harita.|
|*Ilk*|Kopyalanacak öğeler aralığındaki ilk öğenin konumu.|
|*Son*|İlk öğenin kopyalanacak öğe aralığının ötesindeki konumu.|
|*ılist*|Öğelerin kopyalanacağı initializer_list.|

### <a name="remarks"></a>Açıklamalar

Tüm oluşturucular, çok eşlilik için bellek depolamayı yöneten ve daha sonra [get_allocator](#get_allocator)çağırarak döndürülebilen bir allocator nesnesi türünü depolar. Ayırıcı parametresi genellikle sınıf bildirimlerinde ve alternatif ayırıcıların yerine kullanılan ön işleme makrolarında atlanır.

Tüm yapıcılar kendi çoklu haritalarını baş harfe salarlar.

Tüm oluşturucular, çok haritanın anahtarları arasında bir düzen oluşturmak için kullanılan ve daha sonra `Traits` [key_comp](#key_comp)çağırarak döndürülebilen bir işlev nesnesi depolar.

İlk üç oluşturucu boş bir ilk çoklu harita belirtir, ikinci karşılaştırma fonksiyonunun türünü belirten *(Comp*) elemanların sırasını oluştururken kullanılacak ve üçüncü açıkça tahsis türü *(Al)* kullanılacak belirterek. **Açık** anahtar, belirli türde otomatik tür dönüştürmeyi bastırır.

Dördüncü oluşturucu, çok eşli *Sağ'ın*bir kopyasını belirtir.

Beşinci oluşturucu *Sağ*hareket ettirerek çoklu haritanın bir kopyasını belirtir.

Altıncı, yedinci ve sekizinci yapıcılar bir initializer_list üyelerini kopyalarlar.

Sonraki üç oluşturucu, sınıf `[First, Last)` `Traits` ve ayırıcının karşılaştırma işlevinin türünü belirtirken artan açıklıkla bir haritanın aralığını kopyalar.

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

## <a name="multimapoperator"></a><a name="op_eq"></a>çok harita::operator=

Çok eşliliğin öğelerini başka bir çok haritanın kopyasıyla değiştirir.

```cpp
multimap& operator=(const multimap& right);

multimap& operator=(multimap&& right);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|-|-|
|*Doğru*|[Çoklu harita](../standard-library/multimap-class.md) `multimap`kopyalanır.|

### <a name="remarks"></a>Açıklamalar

Bir'deki varolan öğeleri `multimap`silersonra , `operator=` *''nin* içeriğini `multimap`kopyalar veya 'ye taşır.

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

## <a name="multimappointer"></a><a name="pointer"></a>çok harita::pointer

Çok eşlilikteki bir öğeye işaretçi sağlayan bir tür.

```cpp
typedef typename allocator_type::pointer pointer;
```

### <a name="remarks"></a>Açıklamalar

Bir `pointer` tür, bir öğenin değerini değiştirmek için kullanılabilir.

Çoğu durumda, çok eşli bir nesnedeki öğelere erişmek için bir [yineleyici](#iterator) kullanılmalıdır.

## <a name="multimaprbegin"></a><a name="rbegin"></a>çok harita::rbegin

Ters bir çok haritadaki ilk öğeyi ele alan bir yineleyici döndürür.

```cpp
const_reverse_iterator rbegin() const;

reverse_iterator rbegin();
```

### <a name="return-value"></a>Dönüş Değeri

Ters bir çoklu haritadaki ilk öğeyi ele alan veya ters çevrilmemiş çoklu haritadaki son öğeyi ele alan ters çift yönlü bir yineleme.

### <a name="remarks"></a>Açıklamalar

`rbegin`[begin](#begin) bir çok harita ile kullanıldığı gibi ters bir çoklu harita ile kullanılır.

Bir `const_reverse_iterator`, çok `rbegin` eşli nesnesi için return value atanırsa değiştirilemez. Bir `reverse_iterator`, çok `rbegin` eşli nesnesi için döndürülen değeri atanmışsa değiştirilebilir.

`rbegin`geriye doğru çok harita üzerinden yinelemek için kullanılabilir.

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

## <a name="multimapreference"></a><a name="reference"></a>çok harita::referans

Çok eşlemede depolanan bir öğeye başvuru sağlayan bir tür.

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

## <a name="multimaprend"></a><a name="rend"></a>çok eşli::rend

Ters bir çok haritada son öğeyi yerine getiren konumu adresleyen bir yineleyici döndürür.

```cpp
const_reverse_iterator rend() const;

reverse_iterator rend();
```

### <a name="return-value"></a>Dönüş Değeri

Ters bir çok haritadaki son öğeyi (ters çevrilmemiş çoklu eşlemedeki ilk öğeden önce gelen konum) yerine gelen konumu gideren ters çift yönlü bir yineleme.

### <a name="remarks"></a>Açıklamalar

`rend`[uç](../standard-library/map-class.md#end) bir çok harita ile kullanıldığı gibi ters bir multimap ile kullanılır.

Bir `const_reverse_iterator`, çok `rend` eşli nesnesi için return value atanırsa değiştirilemez. Bir `reverse_iterator`, çok `rend` eşli nesnesi için döndürülen değeri atanmışsa değiştirilebilir.

`rend`ters yineleyicinin çoklu haritasının sonuna ulaşıp ulaşmadığını test etmek için kullanılabilir.

Döndürülen `rend` değer dereferenced olmamalıdır.

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

## <a name="multimapreverse_iterator"></a><a name="reverse_iterator"></a>çok eşli::reverse_iterator

Ters bir çok haritadaki bir öğeyi okuyabilen veya değiştirebilen çift yönlü bir yineleme sağlayan bir tür.

```cpp
typedef std::reverse_iterator<iterator> reverse_iterator;
```

### <a name="remarks"></a>Açıklamalar

Bir `reverse_iterator` tür, çoklu haritayı ters ten tesbit etmek için kullanılır.

Çok `reverse_iterator` eşli noktalarla tanımlanan [value_type](#value_type)nesneleri , `pair<const Key, Type>`türü vardır . Anahtarın değeri ilk üye çift aracılığıyla kullanılabilir ve eşlenen öğenin değeri çiftin ikinci üyesi aracılığıyla kullanılabilir.

Çok haritadaki `reverse_iterator` bir öğeyi işaret eden bir *rIter'ı* belirtmek için **->** işleci kullanın.

Öğe için anahtarın değerine erişmek `rIter->first`için, 'ye `(*rIter).first`eşdeğer olan ' ı kullanın. Öğe için eşlenen datum değerine erişmek için, 'ye `rIter->second` `(*rIter).second`eşdeğer olan ' ı kullanın.

### <a name="example"></a>Örnek

Nasıl bildirilir ve kullanılacağına `reverse_iterator`bir örnek için [rbegin](#rbegin) örneğine bakın.

## <a name="multimapsize"></a><a name="size"></a>çok eşli::boyut

Çoklu haritadaki öğe sayısını verir.

```cpp
size_type size() const;
```

### <a name="return-value"></a>Dönüş Değeri

Çoklu haritanın geçerli uzunluğu.

### <a name="example"></a>Örnek

Aşağıdaki örnek, çoklu harita::size üye işlevin kullanımını göstermektedir.

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

## <a name="multimapsize_type"></a><a name="size_type"></a>çok harita::size_type

Çok eşlilikteki öğe sayısını sayan imzasız bir tamsayı türü.

```cpp
typedef typename allocator_type::size_type size_type;
```

### <a name="example"></a>Örnek

Nasıl beyan edilip kullanılacağına ilgili bir örnek için [boyut](#size) örneğine bakın`size_type`

## <a name="multimapswap"></a><a name="swap"></a>çok harita::takas

İki çok eşin öğelerini değiştirir.

```cpp
void swap(
    multimap<Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*Doğru*\
Değiştirilecek öğeleri sağlayan çoklu harita veya öğeleri çok haritalı `left`olanlarla değiştirilecek olan çoklu harita.

### <a name="remarks"></a>Açıklamalar

Üye işlev, öğeleri değiştirilen iki çok eşlemdeki öğeleri belirleyen hiçbir başvuruyu, işaretçiyi veya yineleyiciyi geçersiz kılmaz.

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

## <a name="multimapupper_bound"></a><a name="upper_bound"></a>çok eşli::upper_bound

Bir çok eşlemedeki ilk öğeye belirtilen anahtardan daha büyük bir anahtarla bir yineleyici döndürür.

```cpp
iterator upper_bound(const Key& key);

const_iterator upper_bound(const Key& key) const;
```

### <a name="parameters"></a>Parametreler

*Anahtar*\
Aralanan çoklu haritadaki bir öğenin tür anahtarıyla karşılaştırılacak bağımsız değişken anahtarı.

### <a name="return-value"></a>Dönüş Değeri

Bir yineleyici veya `const_iterator` bağımsız değişken anahtarından daha büyük bir anahtarla veya anahtar için eşleşme bulunamazsa çoklu haritadaki son öğeyi başaran konumu ele alan bir çok eşteki öğenin konumunu gideren bir öğe.

İade değeri bir `const_iterator`, multimap nesnesi değiştirilemez atanır. İade değeri bir `iterator`, multimap nesnesi değiştirilebilir atanır.

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

## <a name="multimapvalue_comp"></a><a name="value_comp"></a>çok harita::value_comp

Üye işlev, anahtar değerlerini karşılaştırarak çok eşlemedeki öğelerin sırasını belirleyen bir işlev nesnesi döndürür.

```cpp
value_compare value_comp() const;
```

### <a name="return-value"></a>Dönüş Değeri

Çoklu haritanın öğelerini sıralamak için kullandığı karşılaştırma işlevi nesnesini döndürür.

### <a name="remarks"></a>Açıklamalar

Bir çok harita *m*için , eğer iki eleman *e1*(*k1*, *d1*) `value_type`ve *e2*(*k2*, *d2*) türü nesneleri, *k1* ve `m.key_comp(k1, k2)` *k2* türü `key_type` anahtarları ve *d1* ve *d2* türü `mapped_type`kendi verileri, o zaman `m.value_comp(e1, e2)` eşdeğerdir .

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

## <a name="multimapvalue_type"></a><a name="value_type"></a>çok harita::value_type

Bir haritada öğe olarak depolanan nesne türünü temsil eden bir tür.

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

[Konteyner](../cpp/containers-modern-cpp.md)\
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[C++ Standart Kütüphane Başvurusu](../standard-library/cpp-standard-library-reference.md)
