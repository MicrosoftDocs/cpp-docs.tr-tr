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
ms.openlocfilehash: 83980094562e1c0083a879d1dc9aab591dc52d02
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/16/2020
ms.locfileid: "79419835"
---
# <a name="multiset-class"></a>multiset Sınıfı

C++ Standart kitaplık çoklu küme sınıfı, içerdiği öğelerin değerlerinin benzersiz olmaması ve verilerin otomatik olarak sıralanma göre anahtar değerler olarak kullanıldığı bir koleksiyondaki verilerin depolanması ve alınması için kullanılır. Çoklu kümedeki bir öğenin anahtar değeri doğrudan değiştirilemez. Bunun yerine, eski değerlerin silinmesi ve yeni değerlerle sahip öğelerin eklenmesi gerekir.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Key, class Compare =less <Key>, class Allocator =allocator <Key>>
class multiset
```

### <a name="parameters"></a>Parametreler

*Anahtar*\
Çoklu kümede depolanacak öğe veri türü.

\ *Karşılaştır*
İki öğenin değerlerini çoklu kümedeki kendi göreli sıralarını belirlemek için sıralama anahtarları olarak karşılaştırabilen bir işlev nesnesi sağlayan tür. İkili koşul **daha az**\<Key > varsayılan değerdir.

C++ 14 ' te, tür parametreleri olmayan `std::less<>` veya `std::greater<>` koşulunu belirterek heterojen aramayı etkinleştirebilirsiniz. Daha fazla bilgi için bkz. [Ilişkilendirilebilir kapsayıcılarda heterojen arama](../standard-library/stl-containers.md#sequence_containers)

*Ayırıcı*\
Çoklu küme için bellek ayırmayı ve ayırmayı kaldırma hakkındaki ayrıntıları içeren saklı ayırıcı nesnesini gösteren tür. Varsayılan değer: `allocator<Key>`.

## <a name="remarks"></a>Açıklamalar

C++ Standart kitaplık çoklu küme Sınıfı:

- İlişkili bir anahtar değerine dayalı öğe değerlerinin verimli alınmasını destekleyen bir değişken boyutu kapsayıcı olan ilişkilendirilebilir bir kapsayıcı.

- Çift yönlüdür, çünkü öğelerine erişmek için çift yönlü yineleyiciler sağlar.

- Sıralıdır, çünkü öğeleri belirtilen karşılaştırma işlevine uygun olarak kapsayıcı içindeki anahtar değerlere göre sıralanır.

- Öğelerinin benzersiz anahtarlara ihtiyacı olmaması bakımından çokludur, böylece bir anahtar değer onunla ilişkili çok sayıda öğe değerine sahip olabilir.

- Basit bir ilişkilendirilebilir kapsayıcıdır, çünkü öğelerinin değerleri kendi anahtar değerleridir.

- Bir sınıf şablonu, sağladığı işlevsellik geneldir ve bu nedenle öğe olarak içerilen belirli veri türünden bağımsızdır. Kullanılacak veri türü, karşılaştırma işlevi ve ayırıcı ile birlikte bir sınıf şablonunda bir parametre olarak belirtilir.

Çoklu küme sınıfı tarafından verilen yineleyici çift yönlü bir yineleyicidir, ancak [Insert](#insert) ve [MULTICLASS](#multiset) üye işlevleri, şablon parametresi olarak daha zayıf bir giriş yineleyicisini alan, işlevsellik gereksinimleri çift yönlü yineleyicilerin sınıfının garantiden daha düşük olan sürümlere sahiptir. Farklı yineleyici kavramları, işlevselliklerindeki iyileştirmelere göre ilgili bir aile biçimlendirir. Her yineleyici kavramının kendi gereksinimler kümesi vardır ve bunlarla çalışan algoritmaların kendi varsayımlarını yineleyici türü tarafından sağlanan gereksinimlerle sınırlaması gerekir. Bir giriş yineleyicinin bazı nesnelere başvurusunun kaldırılacağı ve dizideki sonraki yineleyiciye artırılabileceği varsayılabilir. Bu en düşük işlevsellik kümesidir, ancak sınıfın üye işlevleri bağlamında yineleyicilerin bir aralığı [`First`, `Last`) hakkında anlamlı bir şekilde konuşabilmek yeterlidir.

Kapsayıcı türünün seçimi genelde uygulamanın gerektirdiği arama ve ekleme türüne dayalı olmalıdır. İlişkilendirilebilir kapsayıcılar, arama, ekleme ve kaldırma işlemleri için en iyi duruma getirilir. Bu işlemleri açıkça destekleyen üye işlevleri, işlevlerini kapsayıcıdaki öğelerin sayısının logaritmasına ortalama orantılı bir sürede gerçekleştirir ve verimlidir. Öğelerin eklenmesi hiçbir yineleyiciyi geçersiz kılmaz; öğelerin kaldırılması yalnızca özellikle kaldırılan öğeleri gösteren yineleyicileri geçersiz kılar.

Çoklu küme, değerleri onların kendi anahtarlarıyla ilişkilendiren koşullar uygulama tarafından karşılandığında seçimin ilişkili kapsayıcısı olmalıdır. Bir çoklu kümenin öğeleri birden çok olabilir ve anahtarlar benzersiz olmadıklarından kendi sıralama anahtarları olarak hizmet verebilir. Bu tür bir yapı modeli, sözcüklerin birden çok defa geçebildiği sıralı bir sözcükler listesindedir. Sözcüklerin birden çok defa geçmelerine izin verilmediğinde, bir küme uygun bir kapsayıcı yapısı olacaktır. Benzersiz tanımlar benzersiz anahtar sözcükler listesine değerler olarak eklendiyse, bir eşlem verileri kapsayacak uygun bir yapı olacaktır. Bunun yerine tanımlar benzersiz değilse, seçilecek kapsayıcı bir çoklu eşlem olurdu.

Çoklu küme, *Compare*türünde bir saklı işlev nesnesi çağırarak denetlediği diziyi sıralar. Bu saklı nesne, [key_comp](#key_comp)üye işlevi çağırarak erişilebilen bir karşılaştırma işlevidir. Genelde, bu sıralamayı oluşturmak için öğelerin yalnızca küçüktür biçiminde karşılaştırılabilir olması gerekir; böylece, herhangi iki öğe belirtildiğinde, eşit oldukları (yani birinin diğerinden daha küçük olmadığı anlamında) veya birinin diğerinden küçük olduğu belirlenebilir. Bu, denk olmayan öğeler arasında bir sıralamaya neden olur. Daha teknik bir not üzerinde, karşılaştırma işlevi standart matematiksel anlamda katı bir zayıf sıralama sevk eden ikili bir koşuldur. Bir ikili koşul *f*( *x*, *y*) iki bağımsız değişken nesnesi olan *x* ve *y* ve **true** ya da **false**dönüş değerine sahip bir işlev nesnesidir. İkili koşul geri dönüşsüz, antisimetrik ve geçişli ve denklik geçişli ise, küme üzerinde yer alan bir sıralama katı zayıf bir sıradır, burada iki nesne x ve y, her ikisi de *f*( *x, y*) ve *f*( *y, x*) false olduğunda denk olarak tanımlanır. Anahtarlar arasındaki eşitliğinin daha güçlü koşulu bu denkliğin yerini alırsa, sıralama (içindeki tüm öğelerin birbirine göre sıralanması anlamında) toplam haline gelir ve eşleşen anahtarlar birbirinden ayırt edilemez olacaktır.

C++ 14 ' te, tür parametreleri olmayan `std::less<>` veya `std::greater<>` koşulunu belirterek heterojen aramayı etkinleştirebilirsiniz. Daha fazla bilgi için bkz. [Ilişkilendirilebilir kapsayıcılarda heterojen arama](../standard-library/stl-containers.md#sequence_containers)

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[değerlerden](#multiset)|Boş olan veya belirtilen `multiset`tümünün veya bir kısmının kopyası olan bir `multiset` oluşturur.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[allocator_type](#allocator_type)|`multiset` nesnesi için `allocator` sınıfı için bir typedef.|
|[const_iterator](#const_iterator)|`multiset`bir **const** öğesini okuyabilen çift yönlü Yineleyici için bir typedef.|
|[const_pointer](#const_pointer)|`multiset`bir **const** öğesi işaretçisi için bir typedef.|
|[const_reference](#const_reference)|**Const** işlemlerini okumak ve gerçekleştirmek için bir `multiset` depolanan **const** öğesine başvuru için bir typedef.|
|[const_reverse_iterator](#const_reverse_iterator)|`multiset`herhangi bir **const** öğesini okuyabilen çift yönlü Yineleyici için bir typedef.|
|[difference_type](#difference_type)|Yineleyiciler tarafından gösterilen öğeler arasındaki bir aralıktaki `multiset` öğelerinin sayısı için işaretli bir tamsayı typedef.|
|[iden](#iterator)|Bir `multiset`herhangi bir öğeyi okuyabilen veya değiştirebilen çift yönlü Yineleyici için bir typedef.|
|[key_compare](#key_compare)|`multiset`iki anahtarı karşılaştıran bir işlev nesnesi için bir typedef, iki öğenin göreli sırasını tespit edebilir.|
|[key_type](#key_type)|İki sıralama anahtarını karşılaştıran bir işlev nesnesi için bir typedef, `multiset`iki öğenin göreli sırasını tespit edebilir.|
|[çağrısı](#pointer)|Bir `multiset`öğe işaretçisi için bir typedef.|
|[başvurunun](#reference)|`multiset`depolanan bir öğeye başvuru için bir typedef.|
|[reverse_iterator](#reverse_iterator)|Ters çevrilen bir `multiset`bir öğeyi okuyabilen veya değiştirebilen çift yönlü Yineleyici için bir typedef.|
|[size_type](#size_type)|Bir `multiset`öğe sayısını temsil eden işaretsiz bir tamsayı türü.|
|[value_compare](#value_compare)|İki öğeyi, `multiset`göreli sıralarını belirleyebilmek için sıralama anahtarları olarak karşılaştırabilen bir işlev nesnesi için typedef.|
|[value_type](#value_type)|Bir nesne olarak, bir değer olarak `multiset` bir öğe olarak depolanan bir nesneyi açıklayan bir typedef.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[başladı](#begin)|`multiset`ilk öğeyi gösteren bir yineleyici döndürür.|
|[cbegin](#cbegin)|`multiset`ilk öğeyi ele alan bir const yineleyici döndürür.|
|[cend](#cend)|`multiset`son öğeden sonraki konumu ele alan bir const yineleyici döndürür.|
|[lediğiniz](#clear)|`multiset`tüm öğelerini siler.|
|[count](#count)|Anahtarı bir parametre olarak belirtilen anahtarla eşleşen bir `multiset` öğe sayısını döndürür.|
|[crbegin](#crbegin)|Ters çevrilen kümedeki ilk öğeyi ele alan bir sabit yineleyici döndürür.|
|[crend](#crend)|Ters çevrilen kümedeki son öğeden sonra gelen konumu ele alan bir sabit yineleyici döndürür.|
|[Emplace](#emplace)|Bir `multiset`içinde oluşturulmuş bir öğe ekler.|
|[emplace_hint](#emplace_hint)|Yerleştirme ipucuyla birlikte `multiset`oluşturulan bir öğe ekler.|
|[olmamalıdır](#empty)|`multiset` boş ise sınar.|
|[erer](#end)|`multiset`son öğeden sonraki konuma işaret eden bir yineleyici döndürür.|
|[equal_range](#equal_range)|Yineleyicilerin bir çiftini döndürür. Çiftin ilk yineleyicisi, belirtilen anahtardan daha büyük bir anahtarla bir `multiset` ilk öğeyi gösterir. Çiftin ikinci yineleyicisi, anahtardan daha büyük veya ona eşit olan bir anahtarla `multiset` ilk öğeyi gösterir.|
|[silme](#erase)|Belirtilen konumlardan bir `multiset` öğeyi veya öğe aralığını kaldırır veya belirtilen bir anahtarla eşleşen öğeleri kaldırır.|
|[find](#find)|Belirtilen anahtara eşit bir anahtara sahip bir `multiset` öğenin ilk konumunu gösteren bir yineleyici döndürür.|
|[get_allocator](#get_allocator)|`multiset`oluşturmak için kullanılan `allocator` nesnesinin bir kopyasını döndürür.|
|[ekleyin](#insert)|Bir `multiset`öğe veya öğe aralığı ekler.|
|[key_comp](#key_comp)|`multiset`iki öğenin göreli sırasını belirleyebilmek için iki sıralama anahtarını karşılaştırabilen bir işlev nesnesi sağlar.|
|[lower_bound](#lower_bound)|Bir yineleyiciyi belirtilen anahtardan daha büyük veya ona eşit bir anahtarla bir `multiset` ilk öğeye döndürür.|
|[max_size](#max_size)|`multiset`maksimum uzunluğunu döndürür.|
|[rbegin](#rbegin)|Ters çevrilen `multiset`ilk öğeyi gösteren bir yineleyici döndürür.|
|[rend](#rend)|Ters çevrilen `multiset`son öğeden sonraki konuma işaret eden bir yineleyici döndürür.|
|[boyutla](#size)|Bir `multiset`öğe sayısını döndürür.|
|[Kur](#swap)|İki `multiset`öğelerini değiş tokuş eder.|
|[upper_bound](#upper_bound)|Bir yineleyiciyi belirtilen anahtardan daha büyük bir anahtarla bir `multiset` ilk öğeye döndürür.|
|[value_comp](#value_comp)|Bir `multiset`öğe değerlerini sıralamak için kullanılan karşılaştırma nesnesinin bir kopyasını alır.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[işleç =](#op_eq)|`multiset` öğelerini başka bir `multiset`kopyasıyla değiştirir.|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** \<set >

**Ad alanı:** std

## <a name="allocator_type"></a>Çoklu küme:: allocator_type

Çoklu küme nesnesinin ayırıcı sınıfını temsil eden tür

```cpp
typedef Allocator allocator_type;
```

### <a name="remarks"></a>Açıklamalar

`allocator_type`, şablon parametresi `Allocator`için bir eş anlamlı.

`Allocator`hakkında daha fazla bilgi için, [Çoklu küme sınıfı](../standard-library/multiset-class.md) konusunun açıklamalar bölümüne bakın.

### <a name="example"></a>Örnek

Bir örnek için [get_allocator](#get_allocator) örneğine bakın `allocator_type`

## <a name="begin"></a>Çoklu küme:: Begin

Çoklu küme içindeki ilk öğeyi adresleyen bir yineleyici döndürür.

```cpp
const_iterator begin() const;

iterator begin();
```

### <a name="return-value"></a>Dönüş Değeri

Çoklu küme içindeki ilk öğeyi ele alarak çift yönlü bir yineleyici veya boş bir çoklu kümeli başarılı bir yerde.

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

## <a name="cbegin"></a>Çoklu küme:: cbegin

Aralıktaki ilk öğeyi ele alan bir **sabit** yineleyici döndürür.

```cpp
const_iterator cbegin() const;
```

### <a name="return-value"></a>Dönüş Değeri

Aralığın ilk öğesine veya boş bir aralığın sonundaki konuma (boş bir Aralık için `cbegin() == cend()`) işaret eden bir **const** çift yönlü erişim yineleyicisi.

### <a name="remarks"></a>Açıklamalar

`cbegin`dönüş değeri ile aralıktaki öğeler değiştirilemez.

Dönüş değerinin `const_iterator`olduğunu garantilemek için `begin()` member işlevinin yerine bu üye işlevi kullanabilirsiniz. Genellikle, aşağıdaki örnekte gösterildiği gibi [Otomatik](../cpp/auto-cpp.md) tür kesintisi anahtar sözcüğüyle birlikte kullanılır. Örnekte, `begin()` ve `cbegin()`destekleyen herhangi bir türdeki değiştirilebilir ( **const**olmayan) bir kapsayıcı olarak `Container` düşünün.

```cpp
auto i1 = Container.begin();
// i1 is Container<T>::iterator
auto i2 = Container.cbegin();

// i2 is Container<T>::const_iterator
```

## <a name="cend"></a>Çoklu küme:: cend

Bir aralıktaki son öğeden hemen sonra gelen konumu ele alan bir **const** yineleyici döndürür.

```cpp
const_iterator cend() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yalnızca aralığın sonunu işaret eden bir **const** çift yönlü erişim yineleyicisi.

### <a name="remarks"></a>Açıklamalar

`cend`, bir yineleyicinin aralığın sonunu geçtiğini test etmek için kullanılır.

Dönüş değerinin `const_iterator`olduğunu garantilemek için `end()` member işlevinin yerine bu üye işlevi kullanabilirsiniz. Genellikle, aşağıdaki örnekte gösterildiği gibi [Otomatik](../cpp/auto-cpp.md) tür kesintisi anahtar sözcüğüyle birlikte kullanılır. Örnekte, `end()` ve `cend()`destekleyen herhangi bir türdeki değiştirilebilir ( **const**olmayan) bir kapsayıcı olarak `Container` düşünün.

```cpp
auto i1 = Container.end();
// i1 is Container<T>::iterator
auto i2 = Container.cend();

// i2 is Container<T>::const_iterator
```

`cend` tarafından döndürülen değer başvurulmamalıdır.

## <a name="clear"></a>Çoklu küme:: Clear

Çoklu kümeli öğelerin tümünü siler.

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

## <a name="const_iterator"></a>Çoklu küme:: const_iterator

Çoklu kümeli bir **const** öğesini okuyabilen çift yönlü bir yineleyici sağlayan bir tür.

```cpp
typedef implementation-defined const_iterator;
```

### <a name="remarks"></a>Açıklamalar

Bir tür `const_iterator`, bir öğenin değerini değiştirmek için kullanılamaz.

### <a name="example"></a>Örnek

`const_iterator`kullanarak bir örnek için [Begin](#begin) örneğine bakın.

## <a name="const_pointer"></a>Çoklu küme:: const_pointer

Çoklu kümeli bir **const** öğesine işaretçi sağlayan bir tür.

```cpp
typedef typename allocator_type::const_pointer const_pointer;
```

### <a name="remarks"></a>Açıklamalar

Bir tür `const_pointer`, bir öğenin değerini değiştirmek için kullanılamaz.

Çoğu durumda, bir [Yineleyici](#iterator) bir çoklu küme nesnesindeki öğelere erişmek için kullanılmalıdır.

## <a name="const_reference"></a>Çoklu küme:: const_reference

**Const** işlemlerini okumak ve gerçekleştirmek için bir çoklu kümeli depolanan **const** öğesine başvuru sağlayan bir tür.

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

## <a name="const_reverse_iterator"></a>Çoklu küme:: const_reverse_iterator

Çoklu kümeli herhangi bir **const** öğesini okuyabilen çift yönlü bir yineleyici sağlayan bir tür.

```cpp
typedef std::reverse_iterator<const_iterator> const_reverse_iterator;
```

### <a name="remarks"></a>Açıklamalar

Bir tür `const_reverse_iterator`, bir öğenin değerini değiştiremiyor ve bu, daha önce çoklu küme üzerinden yinelemek için kullanılır.

### <a name="example"></a>Örnek

`const_reverse_iterator`bildirme ve kullanma hakkında bir örnek için bkz. [rend](#rend) örneği.

## <a name="count"></a>Çoklu küme:: Count

Bir çoklu kümeli, anahtarı parametre belirtilen anahtarla eşleşen öğe sayısını döndürür.

```cpp
size_type count(const Key& key) const;
```

### <a name="parameters"></a>Parametreler

*anahtar*\
Çoklu kümeli eşleştirilecek öğelerin anahtarı.

### <a name="return-value"></a>Dönüş Değeri

Birden çok küme içindeki sıralama anahtarı parametre anahtarıyla eşleşen öğe sayısı.

### <a name="remarks"></a>Açıklamalar

Üye işlevi aralıktaki *x* öğelerinin sayısını döndürür

\[ lower_bound (*anahtar*), upper_bound (*anahtar*))

### <a name="example"></a>Örnek

Aşağıdaki örnek, çoklu küme:: Count üye işlevinin kullanımını gösterir.

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

## <a name="crbegin"></a>Çoklu küme:: crbegin

Ters çevrilen bir çoklu küme içindeki ilk öğeyi adresleyen bir const yineleyici döndürür.

```cpp
const_reverse_iterator crbegin() const;
```

### <a name="return-value"></a>Dönüş Değeri

Ters çevrilen bir çoklu küme içindeki ilk öğeyi ele alarak veya geri çevrilmeyen çoklu kümeli en son öğe olduğunu adresleyen bir const ters çift yönlü Yineleyici.

### <a name="remarks"></a>Açıklamalar

`crbegin`, başlangıç olarak bir çoklu kümeli kullanıldığı gibi, ters kullanılan bir çoklu kümeli birlikte kullanılır.

`crbegin`dönüş değeri ile, çok kümeli nesne değiştirilemez.

`crbegin`, bir çoklu kümeli geri doğru yinelemek için kullanılabilir.

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

## <a name="crend"></a>Çoklu küme:: crend

Ters çevrilen bir çoklu küme içindeki son öğeden sonra gelen konumu ele alan bir const yineleyici döndürür.

```cpp
const_reverse_iterator crend() const;
```

### <a name="return-value"></a>Dönüş Değeri

Ters çevrilen bir çoklu küme içindeki son öğeden sonra gelen konumu ele alan bir sabit ters çift yönlü yineleyici (geri çevrilmeyen çok kümeli ilk öğeden önce gelen konum).

### <a name="remarks"></a>Açıklamalar

`crend`, [uçtan uca](#end) bir çoklu küme ile kullanıldığı gibi, ters kullanılan bir çoklu küme ile kullanılır.

`crend`dönüş değeri ile, çok kümeli nesne değiştirilemez.

`crend`, bir ters yineleyicinin kendi çoklu küme sonuna ulaşılıp ulaşılmadığını test etmek için kullanılabilir.

`crend` tarafından döndürülen değer başvurulmamalıdır.

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

## <a name="difference_type"></a>Çoklu küme::d ifference_type

Yineleyiciler tarafından gösterilen öğeler arasındaki bir aralıktaki bir çoklu küme öğelerinin sayısını temsil etmek için kullanılabilen işaretli bir tamsayı türü.

```cpp
typedef typename allocator_type::difference_type difference_type;
```

### <a name="remarks"></a>Açıklamalar

`difference_type` kapsayıcının yineleyiciler aracılığıyla çıkartılacak veya arttırılarak döndürülen türdür. `difference_type`, genellikle yineleyiciler `first` ve `last`arasındaki [`first`, `last`) aralıktaki öğelerin sayısını temsil etmek için kullanılır, `first` tarafından işaret edilen öğeyi ve dahil değil, öğe aralığını, `last`tarafından işaret edilen öğeyi içerir.

Küme gibi ters çevrilebilir kapsayıcılar tarafından desteklenen çift yönlü yineleyicilerin sınıfını içeren bir giriş yineleyicisinin gereksinimlerini karşılayan tüm yineleyiciler için `difference_type` kullanılabilir olsa da, yineleyiciler arasında çıkarma yalnızca vektör gibi bir rastgele erişim kapsayıcısı tarafından sağlanan rastgele erişim yineleyiciler tarafından desteklenir.

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

## <a name="emplace"></a>Çoklu küme:: emplace

Yerinde oluşturulmuş bir öğe ekler (kopyalama veya taşıma işlemleri yapılmaz), yerleştirme ipucuyla birlikte.

```cpp
template <class... Args>
iterator emplace(Args&&... args);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|-|-|
|*args*|Çoklu kümeli içine eklenecek bir öğe oluşturmak için iletilen bağımsız değişkenler.|

### <a name="return-value"></a>Dönüş Değeri

Yeni eklenmekte olan öğe için bir yineleyici.

### <a name="remarks"></a>Açıklamalar

Bu işlev tarafından kapsayıcı öğelerine yönelik başvuru geçersiz kılınmamıştır, ancak kapsayıcı için tüm yineleyiciler geçersiz kılınabilir.

Emplamak sırasında, bir özel durum oluşturulursa kapsayıcının durumu değiştirilmez.

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

## <a name="emplace_hint"></a>Çoklu küme:: emplace_hint

Yerinde oluşturulmuş bir öğe ekler (kopyalama veya taşıma işlemleri yapılmaz), yerleştirme ipucuyla birlikte.

```cpp
template <class... Args>
iterator emplace_hint(
    const_iterator where,
    Args&&... args);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|-|-|
|*args*|Çoklu kümeli içine eklenecek bir öğe oluşturmak için iletilen bağımsız değişkenler.|
|*olmadığı*|Doğru ekleme noktasını aramaya başlamak için yer. (Bu nokta hemen bundan önce geliyorsa, ekleme, logaritmik bir süre yerine, sabit *zamanlı olarak gerçekleşebilir*.)|

### <a name="return-value"></a>Dönüş Değeri

Yeni eklenmekte olan öğe için bir yineleyici.

### <a name="remarks"></a>Açıklamalar

Bu işlev tarafından kapsayıcı öğelerine yönelik başvuru geçersiz kılınmamıştır, ancak kapsayıcı için tüm yineleyiciler geçersiz kılınabilir.

Emplamak sırasında, bir özel durum oluşturulursa kapsayıcının durumu değiştirilmez.

Kod örneği için bkz. [set:: emplace_hint](../standard-library/set-class.md#emplace_hint).

## <a name="empty"></a>Çoklu küme:: boş

Çoklu küme boş ise sınar.

```cpp
bool empty() const;
```

### <a name="return-value"></a>Dönüş Değeri

Çoklu küme boşsa **doğru** ; Çoklu küme boş değilse **false** .

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

## <a name="end"></a>Çoklu küme:: bitiş

past-the-end yineleyici döndürür.

```cpp
const_iterator end() const;

iterator end();
```

### <a name="return-value"></a>Dönüş Değeri

Son uca Yineleyici. Çoklu küme boşsa `multiset::end() == multiset::begin()`.

### <a name="remarks"></a>Açıklamalar

**son** , bir yineleyicinin kendi çoklu küme sonunu geçtiğini test etmek için kullanılır.

**End** tarafından döndürülen değer başvurulmamalıdır.

Kod örneği için bkz. [Çoklu küme:: bul](#find).

## <a name="equal_range"></a>Çoklu küme:: equal_range

Belirtilen anahtardan daha büyük bir anahtarla ve bu anahtarla eşit veya daha büyük olan bir anahtarla birlikte çoklu küme içindeki ilk öğeye sahip bir çoklu küme içindeki ilk öğeye, yineleyicilerin çiftini döndürür.

```cpp
pair <const_iterator, const_iterator> equal_range (const Key& key) const;

pair <iterator, iterator> equal_range (const Key& key);
```

### <a name="parameters"></a>Parametreler

*anahtar*\
Aranan çok kümeli bir öğenin sıralama anahtarıyla Karşılaştırılacak bağımsız değişken anahtarı.

### <a name="return-value"></a>Dönüş Değeri

Birincisi anahtarın [lower_bound](#lower_bound) , ikincisi ise anahtarın [upper_bound](#upper_bound) olan yinelemelerin bir çiftinden biridir.

Üye işlevi tarafından döndürülen bir çiftin ilk Yineleyici `pr` erişmek için `pr`kullanın. **ilk**olarak, alt sınır yineleyicisini başvuru için \*(`pr`kullanın. **ilk**). Üye işlevi tarafından döndürülen bir çiftin ikinci Yineleyici `pr` erişmek için `pr`kullanın. **ikinci**olarak, üst sınır yineleyicisinin başvurusu için \*(`pr`kullanın. **ikinci**).

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

## <a name="erase"></a>Çoklu küme:: Erase

Bir öğeyi veya öğe aralığını belirtilen konumlardan kaldırır veya belirtilen bir anahtarla eşleşen öğeleri kaldırır.

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

*Burada*\
Kaldırılacak öğenin konumu.

*İlk*\
Kaldırılacak ilk öğenin konumu.

*Son*\
Kaldırılacak son öğenin hemen ötesinde konumlandır.

*Anahtar*\
Kaldırılacak öğelerin anahtar değeri.

### <a name="return-value"></a>Dönüş Değeri

İlk iki üye işlevi için, kaldırılan öğelerin dışında kalan ilk öğeyi veya böyle bir öğe yoksa çok kümeli bir öğeyi belirten çift yönlü bir yineleyici.

Üçüncü üye işlevi için, çoklu kümeli kaldırılmış olan öğe sayısını döndürür.

### <a name="remarks"></a>Açıklamalar

Kod örneği için bkz. [set:: Erase](../standard-library/set-class.md#erase).

## <a name="find"></a>Çoklu küme:: bul

Belirtilen anahtara eşdeğer bir anahtara sahip bir çoklu küme içindeki bir öğenin konumuna başvuran bir yineleyici döndürür.

```cpp
iterator find(const Key& key);

const_iterator find(const Key& key) const;
```

### <a name="parameters"></a>Parametreler

*anahtar*\
Aranan çok kümeli bir öğenin sıralama anahtarıyla eşleştirilecek anahtar değeri.

### <a name="return-value"></a>Dönüş Değeri

Anahtar için hiçbir eşleşme bulunmazsa, belirtilen anahtara sahip bir öğenin konumunu veya çok kümeli (`multiset::end()`) son öğeden sonraki konumu belirten bir yineleyici.

### <a name="remarks"></a>Açıklamalar

Üye işlevi, anahtarı karşılaştırıdan daha az bir ilişkiye göre bir sıralamayı karşılayan bir ikili koşul altındaki bağımsız değişken *anahtarına* denk gelen çoklu küme içindeki bir öğeye başvuran bir yineleyici döndürür.

`find` dönüş değeri bir `const_iterator`atanırsa, çok kümeli nesne değiştirilemez. `find` dönüş değeri bir `iterator`atanırsa, çok kümeli nesne değiştirilebilir

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

## <a name="get_allocator"></a>Çoklu küme:: get_allocator

Çoklu küme oluşturmak için kullanılan ayırıcı nesnesinin bir kopyasını döndürür.

```cpp
allocator_type get_allocator() const;
```

### <a name="return-value"></a>Dönüş Değeri

Çoklu küme tarafından kullanılan ayırıcı.

### <a name="remarks"></a>Açıklamalar

Çoklu küme sınıfı için ayrıcılar, sınıfın depolamayı nasıl yönettiğini belirtir. C++ Standart kitaplık kapsayıcı sınıflarıyla sağlanan varsayılan ayrıcılar çoğu programlama ihtiyacı için yeterlidir. Kendi ayırıcı sınıfınızı yazmak ve kullanmak Gelişmiş C++ bir konudur.

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

## <a name="insert"></a>Çoklu küme:: INSERT

Çoklu kümeli bir öğe veya öğe aralığı ekler.

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
|*Acil*|Çoklu kümeli eklenecek öğenin değeri.|
|*Olmadığı*|Doğru ekleme noktasını aramaya başlamak için yer. (Bu nokta hemen bundan önce geliyorsa, ekleme, logaritmik bir süre yerine, sabit *zamanlı olarak gerçekleşebilir*.)|
|*ValTy*|Çoklu küme 'nın [value_type](../standard-library/map-class.md#value_type)bir öğesi oluşturmak için kullanabileceği bağımsız değişken türünü ve bir bağımsız *değişken olarak kusursuz* iletme değerini belirten şablon parametresi.|
|*Adı*|Kopyalanacak ilk öğenin konumu.|
|*Soyadına*|Kopyalanacak son öğenin hemen ötesinde konum.|
|*InputIterator*|[Value_type](../standard-library/map-class.md#value_type) nesneleri oluşturmak için kullanılabilecek bir türün öğelerine işaret eden bir [giriş yineleyicisinin](../standard-library/input-iterator-tag-struct.md) gereksinimlerini karşılayan şablon işlevi bağımsız değişkeni.|
|*IList*|Öğelerin kopyalanacağı [initializer_list](../standard-library/initializer-list.md) .|

### <a name="return-value"></a>Dönüş Değeri

Tek öğeli-ekleme üye işlevleri, (1) ve (2), yeni öğenin çoklu kümeli içine eklendiği konuma bir yineleyici döndürür.

Tek öğeli-ipucu üye işlevleri, (3) ve (4), yeni öğenin çoklu küme içine eklendiği konuma işaret eden bir yineleyici döndürür.

### <a name="remarks"></a>Açıklamalar

Bu işlev tarafından geçersiz kılınan işaretçiler veya başvurular yok, ancak kapsayıcı için tüm yineleyiciler geçersiz kılınabilir.

Yalnızca bir öğenin eklenmesi sırasında, bir özel durum oluşturulursa, kapsayıcının durumu değiştirilmez. Birden çok öğenin eklenmesi sırasında, bir özel durum oluşturulursa, kapsayıcı belirtilmemiş ancak geçerli bir durumda bırakılır.

Kapsayıcının [value_type](../standard-library/map-class.md#value_type) , kapsayıcıya ait olan bir typedef ve set için `multiset<V>::value_type` tür `const V`.

Aralık üye işlevi (5), öğe değerlerinin dizisini aralıktaki bir yineleyici tarafından bahsedilen her öğeye karşılık gelen bir çoklu küme içine ekler `[First, Last)`; Bu nedenle `Last` eklenmez. Kapsayıcı üye işlevi `end()` kapsayıcıdaki son öğeden hemen sonra gelen konuma başvurur — Örneğin, `s.insert(v.begin(), v.end());` deyimin tüm öğelerini `s``v` ekler.

Başlatıcı listesi üye işlevi (6) çoklu kümeli öğeleri kopyalamak için bir [initializer_list](../standard-library/initializer-list.md) kullanır.

Yerinde oluşturulmuş bir öğenin eklenmesi için — yani, kopyalama veya taşıma işlemleri yapılmaz; bkz. [Çoklu küme:: emplace](#emplace) ve [Çoklu küme:: emplace_hint](#emplace_hint).

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

## <a name="iterator"></a>Çoklu küme:: Yineleyici

Çoklu kümeli bir öğeyi okuyabilen sabit [çift yönlü Yineleyici](../standard-library/bidirectional-iterator-tag-struct.md) sağlayan bir tür.

```cpp
typedef implementation-defined iterator;
```

### <a name="example"></a>Örnek

`iterator`bildirme ve kullanma hakkında bir örnek için bkz. [Başlangıç](#begin) örneği.

## <a name="key_comp"></a>Çoklu küme:: key_comp

Bir çoklu kümeli anahtarları sıralamak için kullanılan karşılaştırma nesnesinin bir kopyasını alır.

```cpp
key_compare key_comp() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir çoklu küme, öğesini sıralamak için kullanılan, şablon parametresi `Compare`olan işlev nesnesini döndürür.

`Compare`hakkında daha fazla bilgi için, [Çoklu küme sınıfı](../standard-library/multiset-class.md) konusunun açıklamalar bölümüne bakın.

### <a name="remarks"></a>Açıklamalar

Saklı nesne, üye işlevini tanımlar:

**bool işleci**( **const Key &** *x*, **const Key &** *y*);

*x* sıralamayı sıralama düzeninde *tam olarak önce geliyorsa true* döndürür.

Hem [key_compare](#key_compare) hem de [value_compare](#value_compare) şablon parametresi `Compare`için eş anlamlı olduğunu unutmayın. Her iki tür de, sınıfları ve çoklu küme için, her ikisi de birbirinden farklı oldukları sınıflar haritalarının ve multimap ile uyumluluk için sağlanır.

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

## <a name="key_compare"></a>Çoklu küme:: key_compare

Çoklu küme içindeki iki öğenin göreli sırasını belirleyebilmek için iki sıralama anahtarını karşılaştırabilen bir işlev nesnesi sağlayan bir tür.

```cpp
typedef Compare key_compare;
```

### <a name="remarks"></a>Açıklamalar

`key_compare`, şablon parametresi `Compare`için bir eş anlamlı.

`Compare`hakkında daha fazla bilgi için, [Çoklu küme sınıfı](../standard-library/multiset-class.md) konusunun açıklamalar bölümüne bakın.

### <a name="example"></a>Örnek

`key_compare`bildirme ve kullanma hakkında bir örnek için bkz. [key_comp](#key_comp) örneği.

## <a name="key_type"></a>Çoklu küme:: key_type

Çoklu küme içindeki iki öğenin göreli sırasını belirlemede sıralama anahtarlarını karşılaştırabilen bir işlev nesnesi sağlayan bir tür.

```cpp
typedef Key key_type;
```

### <a name="remarks"></a>Açıklamalar

`key_type`, şablon parametresi `Key`için bir eş anlamlı.

`Key`hakkında daha fazla bilgi için, [Çoklu küme sınıfı](../standard-library/multiset-class.md) konusunun açıklamalar bölümüne bakın.

### <a name="example"></a>Örnek

`key_type`bildirme ve kullanma hakkında bir örnek için bkz. [value_type](#value_type) örneği.

## <a name="lower_bound"></a>Çoklu küme:: lower_bound

Bir yineleyiciyi belirtilen anahtardan daha büyük veya ona eşit bir anahtarla bir çoklu küme içindeki ilk öğeye döndürür.

```cpp
const_iterator lower_bound(const Key& key) const;

iterator lower_bound(const Key& key);
```

### <a name="parameters"></a>Parametreler

*anahtar*\
Aranan çok kümeli bir öğenin sıralama anahtarıyla Karşılaştırılacak bağımsız değişken anahtarı.

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişken anahtarına eşit veya ondan daha büyük bir anahtara sahip olan, ya da anahtar için eşleşme bulunmazsa konumda bulunan son öğeden sonra gelen bir öğenin konumunu ele alan bir `iterator` veya `const_iterator`.

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

## <a name="max_size"></a>Çoklu küme:: max_size

Çoklu küme en büyük uzunluğunu döndürür.

```cpp
size_type max_size() const;
```

### <a name="return-value"></a>Dönüş Değeri

Çoklu küme için olası maksimum uzunluk.

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

## <a name="multiset"></a>Çoklu küme:: çoklu küme

Boş bir çoklu küme oluşturur veya başka bir çoklu kümeli birinin veya bir kısmının kopyasıdır.

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
|*Eşkenar*|Bu çok kümeli nesne için kullanılacak depolama ayırıcısı sınıfı, varsayılan olarak `Allocator`.|
|*İnin*|`Compare`varsayılan olarak kullanılan çoklu küme içindeki öğeleri sıralamak için `const Compare` türündeki karşılaştırma işlevi.|
|*Right*|Oluşturulmuş çoklu küme, bir kopya olacak çok kümeli.|
|*Adı*|Kopyalanacak öğe aralığındaki ilk öğenin konumu.|
|*Soyadına*|Kopyalanacak öğe aralığının ötesinde ilk öğenin konumu.|
|*IList*|Öğelerin kopyalanacağı initializer_list.|

### <a name="remarks"></a>Açıklamalar

Tüm oluşturucular, çoklu küme için bellek depolamayı yöneten ve daha sonra [get_allocator](#get_allocator)çağırarak döndürülebilecek bir tür ayırıcı nesnesi depolar. Ayırıcı parametresi, genellikle sınıf bildirimlerinde atlanır ve alternatif ayırıcıları değiştirmek için kullanılan ön işleme makrolarıyla sonuçlanır.

Tüm oluşturucular çoklu kümeli bir başlangıç yapın.

Tüm oluşturucular, çoklu küme anahtarları arasında bir sıra oluşturmak için kullanılan ve daha sonra [key_comp](#key_comp)çağırarak geri döndürülebilecek bir işlev nesnesi.

İlk üç Oluşturucu boş bir ilk çoklu küme, öğelerin sırasını oluşturmak için kullanılan karşılaştırma işlevinin türünü (*comp*) ve kullanılacak ayırıcı türünü (*Al*) açıkça belirten, ikincisini belirtir. **Explicit** anahtar sözcüğü, bazı otomatik tür dönüştürme türlerini bastırır.

Dördüncü Oluşturucu, çok kümeli *sağ*bir kopyasını belirtir.

Beşinci Oluşturucu, *sağ*taşıyarak çok kümeli bir kopyasını belirtir.

Altıncı, yedinci ve sekizinci oluşturucular, öğelerin kopyalanacağı bir initializer_list belirtir.

Sonraki üç Oluşturucu, karşılaştırma işlevi ve ayırıcı türünü belirtirken açıkça artan bir çoklu küme `[First, Last)` aralığını kopyalar.

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

## <a name="op_eq"></a>Çoklu küme:: operator =

Bu `multiset` öğelerini başka bir `multiset`öğeleri kullanarak değiştirir.

```cpp
multiset& operator=(const multiset& right);

multiset& operator=(multiset&& right);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|-|-|
|*Right*|Öğelerin kopyalandığı veya taşındığı `multiset`.|

### <a name="remarks"></a>Açıklamalar

`operator=`, kullanılan başvuru türüne (lvalue veya rvalue) bağlı olarak, öğeleri *doğrudan* bu `multiset`içine taşıtır veya kopyalar. `operator=` yürütmeden önce bu `multiset` olan öğeler atılır.

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

## <a name="pointer"></a>Çoklu küme::p oınter

Çoklu kümeli bir öğeye işaretçi sağlayan bir tür.

```cpp
typedef typename allocator_type::pointer pointer;
```

### <a name="remarks"></a>Açıklamalar

Bir tür **işaretçisi** bir öğenin değerini değiştirmek için kullanılabilir.

Çoğu durumda, bir [Yineleyici](#iterator) bir çoklu küme nesnesindeki öğelere erişmek için kullanılmalıdır.

## <a name="rbegin"></a>Çoklu küme:: rbegin

Ters çevrilen bir çoklu küme içindeki ilk öğeyi adresleyen bir yineleyici döndürür.

```cpp
const_reverse_iterator rbegin() const;

reverse_iterator rbegin();
```

### <a name="return-value"></a>Dönüş Değeri

Ters çevrilen bir çoklu küme içindeki ilk öğeyi adresleyen veya geri çevrilmeyen çok kümeli en son öğe olan adresi ele almak için ters çift yönlü Yineleyici.

### <a name="remarks"></a>Açıklamalar

`rbegin`, ters kümeli bir çoklu küme ile birlikte kullanıldığında, yalnızca rbegin bir çoklu küme ile kullanılır.

`rbegin` dönüş değeri bir `const_reverse_iterator`atanırsa, çok kümeli nesne değiştirilemez. `rbegin` dönüş değeri bir `reverse_iterator`atanırsa, çok kümeli nesne değiştirilebilir.

`rbegin`, bir çoklu kümeli geri doğru yinelemek için kullanılabilir.

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

## <a name="reference"></a>Çoklu küme:: başvuru

Çoklu kümeli depolanan bir öğeye başvuru sağlayan bir tür.

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

## <a name="rend"></a>Çoklu küme:: rend

Ters çevrilen bir çoklu küme içindeki son öğeden sonra gelen konumu ele alan bir yineleyici döndürür.

```cpp
const_reverse_iterator rend() const;

reverse_iterator rend();
```

### <a name="return-value"></a>Dönüş Değeri

Ters çevrilen bir çoklu küme içindeki son öğeden sonra gelen konumu ele alan ters çift yönlü yineleyici (geri çevrilmeyen çok kümeli ilk öğeden önce gelen konum).

### <a name="remarks"></a>Açıklamalar

`rend`, [uçtan uca](#end) bir çoklu küme ile kullanıldığı gibi, ters kullanılan bir çoklu küme ile kullanılır.

`rend` dönüş değeri bir `const_reverse_iterator`atanırsa, çok kümeli nesne değiştirilemez. `rend` dönüş değeri bir `reverse_iterator`atanırsa, çok kümeli nesne değiştirilebilir.

`rend`, bir ters yineleyicinin kendi çoklu küme sonuna ulaşılıp ulaşılmadığını test etmek için kullanılabilir.

`rend` tarafından döndürülen değer başvurulmamalıdır.

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

## <a name="reverse_iterator"></a>Çoklu küme:: reverse_iterator

Ters çevrilen bir çoklu küme içindeki bir öğeyi okuyabilen veya değiştirebilen çift yönlü bir yineleyici sağlayan bir tür.

```cpp
typedef std::reverse_iterator<iterator> reverse_iterator;
```

### <a name="remarks"></a>Açıklamalar

Bir tür `reverse_iterator`, geri kümeli bir şekilde ters yönde yinelemek için kullanılır.

### <a name="example"></a>Örnek

`reverse_iterator`bildirme ve kullanma hakkında bir örnek için bkz. [rbegin](#rbegin) örneği.

## <a name="size"></a>Çoklu küme:: size

Çoklu kümeli öğe sayısını döndürür.

```cpp
size_type size() const;
```

### <a name="return-value"></a>Dönüş Değeri

Çoklu küme için geçerli uzunluk.

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

## <a name="size_type"></a>Çoklu küme:: size_type

Çoklu kümeli öğe sayısını temsil eden işaretsiz bir tamsayı türü.

```cpp
typedef typename allocator_type::size_type size_type;
```

### <a name="example"></a>Örnek

`size_type` bildirme ve kullanma örneği için bkz. örnek [boyutu](#size) .

## <a name="swap"></a>Çoklu küme:: takas

İki multiset 'in öğelerini değiş tokuş eder.

```cpp
void swap(
    multiset<Key, Compare, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*sağ*\
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

## <a name="upper_bound"></a>Çoklu küme:: upper_bound

Bir yineleyiciyi belirtilen anahtardan daha büyük bir anahtarla bir çoklu küme içindeki ilk öğeye döndürür.

```cpp
const_iterator upper_bound(const Key& key) const;

iterator upper_bound(const Key& key);
```

### <a name="parameters"></a>Parametreler

*anahtar*\
Aranan çok kümeli bir öğenin sıralama anahtarıyla Karşılaştırılacak bağımsız değişken anahtarı.

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişken anahtarından daha büyük bir anahtarla bir çoklu küme içindeki bir öğenin konumunu adresleyen veya anahtar için eşleşme bulunamazsa, çok kümeli olan en son öğeden sonraki konumu ele alan bir **Yineleyici** veya `const_iterator`.

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

## <a name="value_comp"></a>Çoklu küme:: value_comp

Çoklu kümeli öğe değerlerini sıralamak için kullanılan karşılaştırma nesnesinin bir kopyasını alır.

```cpp
value_compare value_comp() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir çoklu küme, öğesini sıralamak için kullanılan, şablon parametresi `Compare`olan işlev nesnesini döndürür.

`Compare`hakkında daha fazla bilgi için, [Çoklu küme sınıfı](../standard-library/multiset-class.md) konusunun açıklamalar bölümüne bakın.

### <a name="remarks"></a>Açıklamalar

Saklı nesne, üye işlevini tanımlar:

**bool işleci**( **const Key &** `_xVal`, **const Key &** `_yVal`);

`_xVal` önce varsa true, sıralama düzeninde `_yVal` eşit değildir.

Hem [key_compare](#key_compare) hem de [value_compare](#value_compare) şablon parametresi `Compare`için eş anlamlı olduğunu unutmayın. Her iki tür de, sınıfları ve çoklu küme için, her ikisi de birbirinden farklı oldukları sınıflar haritalarının ve multimap ile uyumluluk için sağlanır.

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

## <a name="value_compare"></a>Çoklu küme:: value_compare

İki sıralama anahtarını karşılaştıran bir işlev nesnesi sağlayan tür, birden çok küme üzerinde kendi göreli sıralarını tespit edebilir.

```cpp
typedef key_compare value_compare;
```

### <a name="remarks"></a>Açıklamalar

`value_compare`, şablon parametresi `Compare`için bir eş anlamlı.

Hem [key_compare](#key_compare) hem de `value_compare` şablon parametresi `Compare`için eş anlamlı olduğunu unutmayın. Her iki tür de, sınıfları ve çoklu küme için, her ikisi de birbirinden farklı oldukları sınıflar haritalarının ve multimap ile uyumluluk için sağlanır.

`Compare`hakkında daha fazla bilgi için, [Çoklu küme sınıfı](../standard-library/multiset-class.md) konusunun açıklamalar bölümüne bakın.

### <a name="example"></a>Örnek

`value_compare`bildirme ve kullanma hakkında bir örnek için bkz. [value_comp](#value_comp) örneği.

## <a name="value_type"></a>Çoklu küme:: value_type

Bir nesne olarak, bir değer olarak kapasitesinde bir çoklu küme olarak depolanan bir nesneyi açıklayan bir tür.

```cpp
typedef Key value_type;
```

### <a name="remarks"></a>Açıklamalar

`value_type`, şablon parametresi `Key`için bir eş anlamlı.

Hem [key_type](#key_type) hem de `value_type` şablon parametresi `Key`için eş anlamlı olduğunu unutmayın. Her iki tür de, sınıfları ve çoklu küme için, her ikisi de birbirinden farklı oldukları sınıflar haritalarının ve multimap ile uyumluluk için sağlanır.

`Key`hakkında daha fazla bilgi için konusunun açıklamalar bölümüne bakın.

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

[Kapsayıcılar](../cpp/containers-modern-cpp.md)\
[Standart kitaplıkta Iş parçacığı güvenliği\ C++ ](../standard-library/thread-safety-in-the-cpp-standard-library.md)
[C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)
