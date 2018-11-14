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
ms.openlocfilehash: 1bbf0e706939ccd61e8e7944f6f8a05d5aa92498
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/10/2018
ms.locfileid: "51525450"
---
# <a name="multiset-class"></a>multiset Sınıfı

C++ Standart multiset sınıfı, içerdiği öğelerin değerlerinin benzersiz olması gerekmez ve hangi verilerin otomatik sıralamasına göre anahtar değerler olarak verdikleri bir koleksiyondan verilerin alınmasını ve depolama için kullanılan kitaplık. Çoklu kümedeki bir öğenin anahtar değeri doğrudan değiştirilemez. Bunun yerine, eski değerlerin silinmesi ve yeni değerlerle sahip öğelerin eklenmesi gerekir.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Key, class Compare =less <Key>, class Allocator =allocator <Key>>
class multiset
```

### <a name="parameters"></a>Parametreler

*Key*<br/>
Çoklu kümede depolanacak öğe veri türü.

*Compare*<br/>
İki öğenin değerlerini çoklu kümedeki kendi göreli sıralarını belirlemek için sıralama anahtarları olarak karşılaştırabilen bir işlev nesnesi sağlayan tür. İkili koşul **daha az**\<Key > varsayılan değerdir.

C ++ 14'te belirterek heterojen arama etkinleştirebilirsiniz `std::less<>` veya `std::greater<>` hiçbir tür parametreleri olan koşul. Daha fazla bilgi için [, ilişkili kapsayıcılar için heterojen arama](../standard-library/stl-containers.md#sequence_containers)

*Ayırıcı*<br/>
Çoklu küme için bellek ayırmayı ve ayırmayı kaldırma hakkındaki ayrıntıları içeren saklı ayırıcı nesnesini gösteren tür. Varsayılan değer `allocator<Key>` şeklindedir.

## <a name="remarks"></a>Açıklamalar

C++ Standart çoklu küme sınıfı şöyledir kitaplığı:

- İlişkili bir anahtar değerine dayalı öğe değerlerinin verimli alınmasını destekleyen bir değişken boyutu kapsayıcı olan ilişkilendirilebilir bir kapsayıcı.

- Çift yönlüdür, çünkü öğelerine erişmek için çift yönlü yineleyiciler sağlar.

- Sıralıdır, çünkü öğeleri belirtilen karşılaştırma işlevine uygun olarak kapsayıcı içindeki anahtar değerlere göre sıralanır.

- Öğelerinin benzersiz anahtarlara ihtiyacı olmaması bakımından çokludur, böylece bir anahtar değer onunla ilişkili çok sayıda öğe değerine sahip olabilir.

- Basit bir ilişkilendirilebilir kapsayıcıdır, çünkü öğelerinin değerleri kendi anahtar değerleridir.

- Bir şablon sınıfıdır, çünkü sağladığı işlevsellik geneldir ve böylece öğeler olarak kapsanan belirli veri türünden bağımsızdır. Kullanılacak veri türü, karşılaştırma işlevi ve ayırıcı ile birlikte bir sınıf şablonunda bir parametre olarak belirtilir.

Çoklu küme sınıfı tarafından sağlanan yineleyici çift yönlüdür, ancak sınıf üyesi işlevleri olan [Ekle](#insert) ve [multiset](#multiset) şablon parametresi olarak daha zayıf bir giriş yineleyicisini alan sürümlere sahip işlevsellik gereksinimleri daha az tarafından çift yönlü Yineleyicilerin sınıfında garanti edilene. Farklı yineleyici kavramları, işlevselliklerindeki iyileştirmelere göre ilgili bir aile biçimlendirir. Her yineleyici kavramının kendi gereksinimler kümesi vardır ve bunlarla çalışan algoritmaların kendi varsayımlarını yineleyici türü tarafından sağlanan gereksinimlerle sınırlaması gerekir. Bir giriş yineleyicinin bazı nesnelere başvurusunun kaldırılacağı ve dizideki sonraki yineleyiciye artırılabileceği varsayılabilir. Bu bir en düşük işlevsellik kümesidir, ancak Yineleyicilerin aralığı hakkında konuşabilmek için yeterlidir [ `First`, `Last`) sınıfın üye işlevleri bağlamında.

Kapsayıcı türünün seçimi genelde uygulamanın gerektirdiği arama ve ekleme türüne dayalı olmalıdır. İlişkilendirilebilir kapsayıcılar, arama, ekleme ve kaldırma işlemleri için en iyi duruma getirilir. Bu işlemleri açıkça destekleyen üye işlevleri, işlevlerini kapsayıcıdaki öğelerin sayısının logaritmasına ortalama orantılı bir sürede gerçekleştirir ve verimlidir. Öğelerin eklenmesi hiçbir yineleyiciyi geçersiz kılmaz; öğelerin kaldırılması yalnızca özellikle kaldırılan öğeleri gösteren yineleyicileri geçersiz kılar.

Çoklu küme, değerleri onların kendi anahtarlarıyla ilişkilendiren koşullar uygulama tarafından karşılandığında seçimin ilişkili kapsayıcısı olmalıdır. Bir çoklu kümenin öğeleri birden çok olabilir ve anahtarlar benzersiz olmadıklarından kendi sıralama anahtarları olarak hizmet verebilir. Bu tür bir yapı modeli, sözcüklerin birden çok defa geçebildiği sıralı bir sözcükler listesindedir. Sözcüklerin birden çok defa geçmelerine izin verilmediğinde, bir küme uygun bir kapsayıcı yapısı olacaktır. Benzersiz tanımlar benzersiz anahtar sözcükler listesine değerler olarak eklendiyse, bir eşlem verileri kapsayacak uygun bir yapı olacaktır. Bunun yerine tanımlar benzersiz değilse, seçilecek kapsayıcı bir çoklu eşlem olurdu.

Çoklu küme türünde bir depolanmış bir işlev nesnesi çağırarak denetlediği diziyi sıralar *karşılaştırma*. Depolanan bu nesne işlevi çağrılarak erişilebilen bir karşılaştırma işlevidir [key_comp](#key_comp). Genelde, bu sıralamayı oluşturmak için öğelerin yalnızca küçüktür biçiminde karşılaştırılabilir olması gerekir; böylece, herhangi iki öğe belirtildiğinde, eşit oldukları (yani birinin diğerinden daha küçük olmadığı anlamında) veya birinin diğerinden küçük olduğu belirlenebilir. Bu, denk olmayan öğeler arasında bir sıralamaya neden olur. Daha teknik bir not üzerinde, karşılaştırma işlevi standart matematiksel anlamda katı bir zayıf sıralama sevk eden ikili bir koşuldur. Bir ikili koşula *f*( *x*, *y*) iki bağımsız değişken nesnelere sahip bir işlev nesnesidir *x* ve *y* dönüş değerini **true** veya **false**. Bir kümesinde ikili koşul dönüşsüz, ters ve geçişli ve denklik geçişli ise, burada iki nesne sıralama katı zayıf sıralamadır x ve y olduğunda denk olarak tanımlanan her ikisi de *f*( *x, y*) ve *f*( *y, x*) false. Anahtarlar arasındaki eşitliğinin daha güçlü koşulu bu denkliğin yerini alırsa, sıralama (içindeki tüm öğelerin birbirine göre sıralanması anlamında) toplam haline gelir ve eşleşen anahtarlar birbirinden ayırt edilemez olacaktır.

C ++ 14'te belirterek heterojen arama etkinleştirebilirsiniz `std::less<>` veya `std::greater<>` hiçbir tür parametreleri olan koşul. Daha fazla bilgi için [, ilişkili kapsayıcılar için heterojen arama](../standard-library/stl-containers.md#sequence_containers)

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[multiset](#multiset)|Oluşturur bir `multiset` boş veya diğer bir deyişle bir kopyasını tüm veya bir kısmının `multiset`.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[allocator_type](#allocator_type)|İçin bir typedef `allocator` sınıfının `multiset` nesne.|
|[const_iterator](#const_iterator)|Okuyabilen çift yönlü yineleyiciler için typedef bir **const** öğesinde `multiset`.|
|[const_pointer](#const_pointer)|İşaretçisi için bir typedef bir **const** öğesinde bir `multiset`.|
|[const_reference](#const_reference)|Başvuru için bir typedef bir **const** öğesi içinde depolanan bir `multiset` okumak ve gerçekleştirmek için **const** operations.|
|[const_reverse_iterator](#const_reverse_iterator)|Tüm okuyabilen çift yönlü yineleyiciler için typedef **const** öğesinde `multiset`.|
|[difference_type](#difference_type)|Bir işaretli tamsayı TypeDef'i öğelerinin bir `multiset` yineleyiciler tarafından gösterilen öğeler arasındaki bir aralıktaki.|
|[Yineleyici](#iterator)|Okuyabilen veya değiştirebilen herhangi bir öğenin çift yönlü yineleyiciler için typedef bir `multiset`.|
|[key_compare](#key_compare)|İki öğenin göreli sırasını belirlemek için iki anahtarı karşılaştıran işlev nesnesi için bir typedef `multiset`.|
|[key_type](#key_type)|İki öğenin göreli sırasını belirlemek için iki sıralama anahtarını karşılaştıran işlev nesnesi için bir typedef `multiset`.|
|[İşaretçi](#pointer)|Bir öğe işaretçisi için bir typedef bir `multiset`.|
|[Başvuru](#reference)|İçinde depolanan öğeye başvuru için bir typedef bir `multiset`.|
|[reverse_iterator](#reverse_iterator)|Okuyabilen veya değiştirebilen tersine çevrilmiş bir öğeye çift yönlü yineleyiciler için typedef `multiset`.|
|[size_type](#size_type)|İçindeki öğelerin sayısını temsil edebilen bir işaretsiz tamsayı türü bir `multiset`.|
|[value_compare](#value_compare)|İki öğenin kendi göreli sıralarını belirlemek için sıralama anahtarları olarak karşılaştırabilen bir işlev nesnesi için typedef `multiset`.|
|[value_type](#value_type)|Öğe şeklinde depolanan nesneyi tanımlayan bir typedef bir `multiset` bir değer olarak kapasitesi dahilinde.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[başlayın](#begin)|İçindeki ilk öğeyi gösteren bir yineleyici döndüren `multiset`.|
|[cbegin](#cbegin)|İlk öğeyi adresleyen bir const yineleyici döndürür `multiset`.|
|[cend](#cend)|İçindeki son öğeyi takip eden konumu ele alan sabit bir yineleyici döndüren bir `multiset`.|
|[Temizle](#clear)|Tüm öğelerini siler bir `multiset`.|
|[Sayısı](#count)|İçindeki öğelerin sayısını döndüren bir `multiset` anahtarı bir parametre olarak belirtilen anahtarla eşleşen.|
|[crbegin](#crbegin)|Ters çevrilen kümedeki ilk öğeyi ele alan bir sabit yineleyici döndürür.|
|[crend](#crend)|Ters çevrilen kümedeki son öğeden sonra gelen konumu ele alan bir sabit yineleyici döndürür.|
|[emplace](#emplace)|İçine yerinde oluşturulmuş bir öğe ekler bir `multiset`.|
|[emplace_hint](#emplace_hint)|İçine yerinde oluşturulmuş bir öğe ekler bir `multiset`, bir yerleşim ipucuyla birlikte.|
|[boş](#empty)|Testleri bir `multiset` boştur.|
|[Son](#end)|İçindeki son öğenin ardındaki konumu gösteren bir yineleyici döndüren bir `multiset`.|
|[equal_range](#equal_range)|Yineleyicilerin bir çiftini döndürür. İlk yineleyicisi çifti içindeki ilk öğeye bir `multiset` belirtilen anahtardan daha büyük bir anahtarla. İkinci yineleyicisi çifti içindeki ilk öğeye `multiset` anahtardan daha büyük veya ona eşit bir anahtara sahip.|
|[silme](#erase)|Bir öğenin veya öğelerin aralığını kaldırır bir `multiset` belirtilen konumları veya belirtilen bir anahtarla eşleşen öğeleri kaldırır.|
|[Bul](#find)|İçindeki bir öğenin birinci konumunu gösteren bir yineleyici döndüren bir `multiset` belirtilen anahtara eşit olan.|
|[get_allocator](#get_allocator)|Bir kopyasını döndürür `allocator` oluşturmak için kullanılan nesne `multiset`.|
|[Ekle](#insert)|Bir öğe veya bir dizi öğelerine ekler bir `multiset`.|
|[key_comp](#key_comp)|İki öğenin göreli sırasını belirlemek için iki sıralama anahtarını karşılaştıran bir işlev nesnesi sağlayan `multiset`.|
|[lower_bound](#lower_bound)|İçindeki ilk öğeye bir yineleyici döndüren bir `multiset` belirtilen anahtardan daha büyük veya ona eşit bir anahtara sahip.|
|[max_size](#max_size)|Öğesinin maksimum uzunluğunu döndürür `multiset`.|
|[rbegin](#rbegin)|Ters çevrilen içindeki ilk öğeyi gösteren bir yineleyici döndüren `multiset`.|
|[rend](#rend)|Ters çevrilen içindeki son öğeyi takip eden konumu gösteren bir yineleyici döndüren `multiset`.|
|[Boyutu](#size)|İçindeki öğelerin sayısını döndüren bir `multiset`.|
|[değiştirme](#swap)|İki öğeleri birbiriyle değiştirir `multiset`s.|
|[upper_bound](#upper_bound)|İçindeki ilk öğeye bir yineleyici döndüren bir `multiset` belirtilen anahtardan daha büyük bir anahtarla.|
|[value_comp](#value_comp)|İçindeki öğe değerlerini sıralamak için kullanılan karşılaştırma nesnesinin bir kopyasını alır bir `multiset`.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[operator=](#op_eq)|Öğelerinin yerini alan bir `multiset` başka bir kopyasına sahip olan `multiset`.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<kümesi >

**Namespace:** std

## <a name="allocator_type"></a>  multiset::allocator_type

Multiset nesne için ayırıcı sınıf temsil eden bir tür

```cpp
typedef Allocator allocator_type;
```

### <a name="remarks"></a>Açıklamalar

`allocator_type` Şablon parametresi için bir eşanlamlı olduğu `Allocator`.

Daha fazla bilgi için `Allocator`, Açıklamalar bölümüne bakın [multiset sınıfı](../standard-library/multiset-class.md) konu.

### <a name="example"></a>Örnek

Örneğin bakın [get_allocator](#get_allocator) bir örnek için `allocator_type`

## <a name="begin"></a>  multiset::Begin

Çoklu kümedeki ilk öğeyi adresleyen bir yineleyici döndürür.

```cpp
const_iterator begin() const;

iterator begin();
```

### <a name="return-value"></a>Dönüş Değeri

Multiset veya sonra gelen konumu adresleyen boş çoklu küme ilk öğeyi adresleyen bir çift yönlü yineleyici.

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

## <a name="cbegin"></a>  multiset::cbegin

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

## <a name="cend"></a>  multiset::cend

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

## <a name="clear"></a>  multiset::Clear

Bir çoklu kümenin tüm öğelerini siler.

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

## <a name="const_iterator"></a>  multiset::const_iterator

Çift yönlü bir yineleyici sağlayan tür okuma bir **const** çoklu öğe.

```cpp
typedef implementation-defined const_iterator;
```

### <a name="remarks"></a>Açıklamalar

Bir tür `const_iterator` bir öğenin değerini değiştirmek için kullanılamaz.

### <a name="example"></a>Örnek

Örneğin bakın [başlamak](#begin) bir örnek için `const_iterator`.

## <a name="const_pointer"></a>  multiset::const_pointer

Bir işaretçi sağlayan bir tür bir **const** çoklu kümedeki öğe.

```cpp
typedef typename allocator_type::const_pointer const_pointer;
```

### <a name="remarks"></a>Açıklamalar

Bir tür `const_pointer` bir öğenin değerini değiştirmek için kullanılamaz.

Çoğu durumda bir [yineleyici](#iterator) multiset nesnesindeki öğelere erişmek için kullanılmalıdır.

## <a name="const_reference"></a>  multiset::const_reference

Bir başvuru sağlayan bir tür bir **const** okumak ve gerçekleştirmek için bir çoklu küme içinde depolanan öğenin **const** operations.

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

## <a name="const_reverse_iterator"></a>  multiset::const_reverse_iterator

Çift yönlü bir yineleyici sağlayan tür herhangi okuma **const** çoklu öğe.

```cpp
typedef std::reverse_iterator<const_iterator> const_reverse_iterator;
```

### <a name="remarks"></a>Açıklamalar

Bir tür `const_reverse_iterator` kullanın çoklu ters yinelemek için ve bir öğenin değerini değiştiremezsiniz.

### <a name="example"></a>Örnek

Örneğin bakın [rend](#rend) bildirme ve kullanma konusunda bir örnek için `const_reverse_iterator`.

## <a name="count"></a>  multiset::Count

Anahtarı parametre tarafından belirtilen bir anahtarla eşleşen bir çoklu küme öğelerin sayısını döndürür.

```cpp
size_type count(const Key& key) const;
```

### <a name="parameters"></a>Parametreler

*Anahtarı*<br/>
Multiset eşleştirilecek öğe anahtarı.

### <a name="return-value"></a>Dönüş Değeri

Sıralama anahtarı parametresi anahtarla eşleşen çoklu küme içindeki öğelerin sayısını.

### <a name="remarks"></a>Açıklamalar

Üye işlevi öğelerin sayısını döndürür *x* aralığında

\[ lower_bound (*anahtarı*), upper_bound (*anahtarı*))

### <a name="example"></a>Örnek

Aşağıdaki örnek, multiset::count üye işlevinin kullanımını gösterir.

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

## <a name="crbegin"></a>  multiset::crbegin

Ters çevrilen bir çoklu küme ilk öğeyi adresleyen bir const yineleyici döndürür.

```cpp
const_reverse_iterator crbegin() const;
```

### <a name="return-value"></a>Dönüş Değeri

Çift yönlü yineleyici tersine çevrilmiş bir çoklu küme ilk öğeyi ele alan veya ne son öğeyi ters çevrilmeyen çoklu kümedeki adresleyen bir const tersine çevirir.

### <a name="remarks"></a>Açıklamalar

`crbegin` ile kullanılan bir ters multiset başlatmak gibi bir çoklu küme ile kullanılır.

Dönüş değeri ile `crbegin`, çoklu küme nesnesi değiştirilemez.

`crbegin` bir çoklu küme geriye doğru gezinmek için kullanılabilir.

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

## <a name="crend"></a>  multiset::crend

Ters çevrilen bir çoklu küme son öğeden sonra gelen konumu ele sabit bir yineleyici döndürür.

```cpp
const_reverse_iterator crend() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir const çift yönlü yineleyici (ters çevrilmeyen çoklu kümedeki ilk öğeyi önce gelen konum) ters çevrilen kümedeki son öğeden sonra gelen konumu ele tersine çevirir.

### <a name="remarks"></a>Açıklamalar

`crend` ters çevrilen bir çoklu küme ile kullanılan gibi [son](#end) bir çoklu küme ile kullanılır.

Dönüş değeri ile `crend`, çoklu küme nesnesi değiştirilemez.

`crend` olup ters yineleyici kendi multiset sonuna ulaşıp ulaşmadığını test etmek için kullanılabilir.

Tarafından döndürülen değer `crend` kaldırılmamalıdır.

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

## <a name="difference_type"></a>  multiset::difference_type

Bir çoklu küme yineleyiciler tarafından gösterilen öğeler arasındaki bir aralıktaki öğelerin sayısını temsil etmek için kullanılabilen işaretli bir tamsayı türü.

```cpp
typedef typename allocator_type::difference_type difference_type;
```

### <a name="remarks"></a>Açıklamalar

`difference_type` Türü çıkarma veya kapsayıcının yineleyiciler artan döndürülür. `difference_type` Genellikle aralık içindeki öğelerin sayısını temsil etmek için kullanılan [ `first`, `last`) yineleyici arasındaki `first` ve `last`, işaret ettiği öğe içerir `first` ve en fazla öğe aralığı , ancak dahil değil tarafından işaret edilen öğeyi `last`.

Ancak dikkat `difference_type` kümesi, yineleyici arasındaki çıkarma yalnızca gibi ters çevrilebilir kapsayıcıları tarafından desteklenen çift yönlü Yineleyicilerin sınıfında içeren bir giriş yineleyici gereksinimlerini karşılayan tüm yineleyiciler için kullanılabilir vektör gibi bir rastgele erişim kapsayıcı tarafından sağlanan rasgele erişim yineleyicileri tarafından desteklenmiyor.

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

## <a name="emplace"></a>  multiset::emplace

(Hiçbir kopyalama veya taşıma işlemleri gerçekleştirilir) bir yerleşim ipucuyla birlikte yerinde oluşturulmuş bir öğe ekler.

```cpp
template <class... Args>
iterator emplace(Args&&... args);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|-|-|
|*bağımsız değişken*|Multiset eklenecek bir öğe oluşturmak için iletilen bağımsız değişkenler.|

### <a name="return-value"></a>Dönüş Değeri

Yeni eklenen öğeye bir yineleyici.

### <a name="remarks"></a>Açıklamalar

Bu işlev tarafından geçersiz kılınan kapsayıcı öğeleri için başvuru ancak kapsayıcıya tüm yineleyiciler geçersiz kılabilir.

Yerleştirme sırasında bir özel durum oluşturulursa, kapsayıcının durumu değiştirilmez.

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

## <a name="emplace_hint"></a>  multiset::emplace_hint

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
|*bağımsız değişken*|Multiset eklenecek bir öğe oluşturmak için iletilen bağımsız değişkenler.|
|*Burada*|Doğru ekleme noktasını için aramaya başlamak için bir yerde. (Bu noktanın hemen önceyse *burada*, ekleme Logaritmik süre yerine amorti edilmiş sabit zaman meydana gelebilir.)|

### <a name="return-value"></a>Dönüş Değeri

Yeni eklenen öğeye bir yineleyici.

### <a name="remarks"></a>Açıklamalar

Bu işlev tarafından geçersiz kılınan kapsayıcı öğeleri için başvuru ancak kapsayıcıya tüm yineleyiciler geçersiz kılabilir.

Yerleştirme sırasında bir özel durum oluşturulursa, kapsayıcının durumu değiştirilmez.

Kod örneği için bkz: [set::emplace_hint](../standard-library/set-class.md#emplace_hint).

## <a name="empty"></a>  multiset::empty

Bir çoklu küme boş olup olmadığını sınar.

```cpp
bool empty() const;
```

### <a name="return-value"></a>Dönüş Değeri

**doğru** multiset boşsa; **false** multiset boş ise.

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

## <a name="end"></a>  multiset::End

past-the-end yineleyici döndürür.

```cpp
const_iterator end() const;

iterator end();
```

### <a name="return-value"></a>Dönüş Değeri

Past--end yineleyici. Multiset boş ise, `multiset::end() == multiset::begin()`.

### <a name="remarks"></a>Açıklamalar

**Son** kendi multiset sonuna bir yineleyici geçmediğini sınamak için kullanılır.

Tarafından döndürülen değer **son** kaldırılmamalıdır.

Kod örneği için bkz: [multiset::find](#find).

## <a name="equal_range"></a>  multiset::equal_range

Yineleyicilerin bir çiftini, sırasıyla belirtilen anahtardan daha büyük bir anahtarla bir çoklu küme içindeki ilk öğeye ve anahtardan büyük veya ona eşit bir anahtarla multiset içindeki ilk öğeye döndürür.

```cpp
pair <const_iterator, const_iterator> equal_range (const Key& key) const;

pair <iterator, iterator> equal_range (const Key& key);
```

### <a name="parameters"></a>Parametreler

*Anahtarı*<br/>
Bir çoklu küme Aranmakta öğeyi sıralama anahtarı ile Karşılaştırılacak bağımsız değişken anahtarı.

### <a name="return-value"></a>Dönüş Değeri

Yineleyicilerin bir çiftini ilk güvenilecek şekilde [lower_bound](#lower_bound) , anahtar ve ikinci [upper_bound](#upper_bound) anahtarı.

Bir çiftin ilk yineleyicisi erişmeye `pr` üye işlevi tarafından döndürülen, kullanın `pr`. **İlk**ve alt sınır yineleyicinin başvuru kaldırma için \*( `pr`. **İlk**). Bir çiftin ikinci yineleyicisi erişmeye `pr` üye işlevi tarafından döndürülen, kullanın `pr`. **İkinci**ve üst sınır yineleyicinin başvuru kaldırma için \*( `pr`. **İkinci**).

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

## <a name="erase"></a>  multiset::ERASE

Bir öğenin veya öğelerin aralığını belirtilen konumdan bir çoklu küme kaldırır veya belirtilen bir anahtarla eşleşen öğeleri kaldırır.

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

İlk iki üye işlevleri için çift yönlü bir yineleyici, kaldırılan herhangi bir öğe veya böyle bir öğe varsa, çoklu sonuna bir öğe ilk öğeyi belirtir.

Üye işlevi için üçüncü multiset kaldırılan öğelerin sayısını döndürür.

### <a name="remarks"></a>Açıklamalar

Kod örneği için bkz: [set::erase](../standard-library/set-class.md#erase).

## <a name="find"></a>  multiset::Find

Belirtilen anahtara denk bir anahtara sahip bir çoklu küme içindeki öğenin konumunu başvuran bir yineleyici döndürür.

```cpp
iterator find(const Key& key);

const_iterator find(const Key& key) const;
```

### <a name="parameters"></a>Parametreler

*Anahtarı*<br/>
Bir çoklu küme Aranmakta öğeyi sıralama anahtarı tarafından eşleştirilecek anahtar değeri.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen anahtara sahip bir öğenin konumunu veya konumu çoklu kümedeki son öğeyi adresleyen bir yineleyici ( `multiset::end()`) anahtar için bir eşleşme varsa.

### <a name="remarks"></a>Açıklamalar

Çoklu kümedeki anahtarı bir öğeye başvuran bir yineleyici bağımsız değişkenine eşdeğerdir üye işlevinin döndürdüğü *anahtarı* comparability ilişkisi küçüktür göre sıralama sevk eden ikili bir koşul altında.

Varsa dönüş değerinin `find` atanan bir `const_iterator`, multiset nesnesi değiştirilemez. Varsa dönüş değerinin `find` atanan bir `iterator`, multiset nesnesi değiştirilebilir

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

## <a name="get_allocator"></a>  multiset::get_allocator

Çoklu küme oluşturmak için kullanılan ayırıcı nesnesinin bir kopyasını döndürür.

```cpp
allocator_type get_allocator() const;
```

### <a name="return-value"></a>Dönüş Değeri

Çoklu küme tarafından kullanılan ayırıcı.

### <a name="remarks"></a>Açıklamalar

Multiset sınıfı için ayırıcılar sınıfı depolama nasıl yönettiğini belirtin. C++ Standart Kitaplığı kapsayıcı sınıfları ile sağlanan varsayılan ayırıcılar çoğu programlama ihtiyaçları için yeterli. Yazma ve kendi allocator sınıfı kullanarak bir Gelişmiş C++ konudur.

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

## <a name="insert"></a>  multiset::insert

Bir çoklu küme, bir öğenin veya öğelerin aralığını ekler.

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
|*VAL*|Multiset eklenecek bir öğenin değeri.|
|*Burada*|Doğru ekleme noktasını için aramaya başlamak için bir yerde. (Bu noktanın hemen önceyse *burada*, ekleme Logaritmik süre yerine amorti edilmiş sabit zaman meydana gelebilir.)|
|*ValTy*|Multiset öğesi oluşturmak için kullanabileceğiniz bağımsız değişken türü belirten bir şablon parametresi [value_type](../standard-library/map-class.md#value_type)ve mükemmel ileten *Val* bağımsız değişken olarak.|
|*ilk*|Kopyalanacak ilk öğenin konumu.|
|*Son*|Kopyalanacak son öğenin ötesinde konumu.|
|*Inputıterator*|Gereksinimlerini karşılayan şablonu işlev bağımsız değişkeni bir [giriş yineleyici](../standard-library/input-iterator-tag-struct.md) oluşturmak için kullanılan bir tür öğelerine işaret eden [value_type](../standard-library/map-class.md#value_type) nesneleri.|
|*IList*|[İnitializer_list](../standard-library/initializer-list.md) öğeleri kopyalanacak.|

### <a name="return-value"></a>Dönüş Değeri

Tek öğe ekleme üye işlevleri (1) ve (2), yeni bir öğe multiset eklenmiş burada konumuna bir yineleyici döndürür.

İpucu ile tek öğe üye işlevleri, (3) ve (4), yeni bir öğe multiset eklenir burada konumu gösteren bir yineleyici döndürür.

### <a name="remarks"></a>Açıklamalar

Hiçbir işaretçileri veya başvuruları bu işlev tarafından geçersiz kılınan ancak kapsayıcıya tüm yineleyiciler geçersiz kılabilir.

Bir özel durum oluşturulursa, yeni bir öğe ekleme sırasında kapsayıcının durumu değiştirilmez. Bir özel durum oluşturulursa, birden çok öğe ekleme sırasında kapsayıcı belirtilmeyen ancak geçerli bir durumda bırakılır.

[Value_type](../standard-library/map-class.md#value_type) küme ve, kapsayıcıya ait bir tür tanımı, kapsayıcısıdır `multiset<V>::value_type` türü `const V`.

Aralık üye işlevi (5) aralığında bir yineleyici tarafından ele alınan her öğe için karşılık gelen bir çoklu küme öğe değerleri dizisi ekler `[First, Last)`; bu nedenle `Last` takılı. Kapsayıcı üye işlevi `end()` kapsayıcıdaki son öğeden hemen sonra konuma başvuran — Örneğin, deyim `s.insert(v.begin(), v.end());` tüm öğeleri ekler `v` içine `s`.

Başlatıcı listesinde üye işlev (6) kullanan bir [initializer_list](../standard-library/initializer-list.md) öğeleri multiset kopyalanacak.

Yerinde oluşturulmuş bir öğe ekleme — diğer bir deyişle, hiçbir kopyalama veya taşıma işlemleri gerçekleştirilir — bkz [multiset::emplace](#emplace) ve [multiset::emplace_hint](#emplace_hint).

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

## <a name="iterator"></a>  multiset::iterator

Bir sabit sağlayan bir tür [çift yönlü yineleyici](../standard-library/bidirectional-iterator-tag-struct.md) çoklu kümedeki herhangi bir öğe depolayabilen.

```cpp
typedef implementation-defined iterator;
```

### <a name="example"></a>Örnek

Örneğin bakın [başlamak](#begin) bildirme ve kullanma konusunda bir örnek için bir `iterator`.

## <a name="key_comp"></a>  multiset::key_comp

Bir çoklu küme anahtarları sıralamak için kullanılan karşılaştırma nesnesinin bir kopyasını alır.

```cpp
key_compare key_comp() const;
```

### <a name="return-value"></a>Dönüş Değeri

Şablon parametresi olan bir çoklu küme, öğeleri düzenlemek amacıyla kullanan işlev nesnesini döndürür `Compare`.

Daha fazla bilgi için `Compare`, Açıklamalar bölümüne bakın [multiset sınıfı](../standard-library/multiset-class.md) konu.

### <a name="remarks"></a>Açıklamalar

Depolanan nesne üyesi işlevini tanımlar:

**bool işleci**( **const anahtar &** *x*, **const anahtar &** *y*);

hangi döndürür true ise *x* kesinlikle önündeki *y* sıralama düzeninde.

Unutmayın hem [key_compare](#key_compare) ve [value_compare](#value_compare) şablon parametresi için eş anlamlı sözcükler olan `Compare`. Multimap, farklı olduğu ve eşleme sınıfları ile uyumluluk için aynı olan, multiset ve sınıfları kümesi için her iki türü de sağlanır.

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

## <a name="key_compare"></a>  multiset::key_compare

Çoklu küme iki öğenin göreli sırasını belirlemek için iki sıralama anahtarını karşılaştıran işlev nesnesi sağlayan tür.

```cpp
typedef Compare key_compare;
```

### <a name="remarks"></a>Açıklamalar

`key_compare` Şablon parametresi için bir eşanlamlı olduğu `Compare`.

Daha fazla bilgi için `Compare`, Açıklamalar bölümüne bakın [multiset sınıfı](../standard-library/multiset-class.md) konu.

### <a name="example"></a>Örnek

Örneğin bakın [key_comp](#key_comp) bildirme ve kullanma konusunda bir örnek için `key_compare`.

## <a name="key_type"></a>  multiset::key_type

Çoklu küme iki öğenin göreli sırasını belirlemek için sıralama anahtarları olarak karşılaştırabilen bir işlev nesnesi sağlayan tür.

```cpp
typedef Key key_type;
```

### <a name="remarks"></a>Açıklamalar

`key_type` Şablon parametresi için bir eşanlamlı olduğu `Key`.

Daha fazla bilgi için `Key`, Açıklamalar bölümüne bakın [multiset sınıfı](../standard-library/multiset-class.md) konu.

### <a name="example"></a>Örnek

Örneğin bakın [value_type](#value_type) bildirme ve kullanma konusunda bir örnek için `key_type`.

## <a name="lower_bound"></a>  multiset::lower_bound

Bir yineleyiciyi belirtilen anahtardan daha büyük veya ona eşit bir anahtarla çoklu kümedeki ilk öğeye döndürür.

```cpp
const_iterator lower_bound(const Key& key) const;

iterator lower_bound(const Key& key);
```

### <a name="parameters"></a>Parametreler

*Anahtarı*<br/>
Bir çoklu küme Aranmakta öğeyi sıralama anahtarı ile Karşılaştırılacak bağımsız değişken anahtarı.

### <a name="return-value"></a>Dönüş Değeri

Bir `iterator` veya `const_iterator` adresleri anahtar için bağımsız değişken anahtardan daha büyük veya ona eşit olan veya hiçbir çoklu kümedeki son öğeyi takip eden konumu ele bir anahtar ile eşleştiğinden emin çoklu kümedeki bir öğenin konumunu bulunamadı.

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
   // found using a derefenced iterator addressing the location
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

## <a name="max_size"></a>  multiset::max_size

Multiset maksimum uzunluğunu döndürür.

```cpp
size_type max_size() const;
```

### <a name="return-value"></a>Dönüş Değeri

Multiset maksimum olası uzunluğu.

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

## <a name="multiset"></a>  multiset::multiset

Boş veya bir kopyası tüm veya bazı diğer multiset parçası olan bir çoklu küme oluşturur.

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
|*Al*|Varsayılan olarak bu multiset nesne için kullanılacak depolama ayırıcı sınıf `Allocator`.|
|*Comp*|Karşılaştırma işlevi türü `const Compare` için varsayılanlarını Kü içinde öğeleri sıralamak için kullanılan `Compare`.|
|*sağ*|Oluşturulan multiset kopyası olacak olduğu multiset.|
|*ilk*|Kopyalanacak öğe aralığındaki ilk öğenin konumu.|
|*Son*|Kopyalanacak öğe aralığının dışındaki ilk öğenin konumu.|
|*IList*|Öğelerin kopyalanacağı initializer_list.|

### <a name="remarks"></a>Açıklamalar

Tüm oluşturucular ayırıcı nesnesi, bellek, depolama için multiset yönetir ve, daha sonra döndürülmesi çağırarak türü depolamak [get_allocator](#get_allocator). Allocator parametresi, sınıf bildirimleri ve diğer ayırıcılar yerine kullanılan ön işleme makroları genellikle atlanır.

Tüm oluşturucular kendi multiset başlatın.

Bir işlev nesnesi türü multiset anahtarları arasında bir sıralamayı oluşturmak için kullanılan ve, daha sonra döndürülmesi çağırarak karşılaştırma tüm oluşturucular deposu [key_comp](#key_comp).

İlk üç oluşturucular bir ilk boş çoklu küme, ikinci belirtin karşılaştırma işlevinin türü belirtme (*kompozisyonu*) öğeleri ve üçüncüsü sırasını açıkça oluşturmada kullanılacak ayırıcı belirtme yazın (*Al*) kullanılacak. Anahtar sözcüğü **açık** otomatik tür dönüştürme belirli türdeki bastırır.

Dördüncü Oluşturucu çoklu bir kopyasını belirtir *sağ*.

Beşinci Oluşturucu taşıyarak çoklu bir kopyasını belirtir. *sağ*.

Altıncı, yedinci ve sekizinci oluşturucular öğeleri kopyalamak bir initializer_list belirtin.

Sonraki üç oluşturucular aralığını kopyalamaktadır `[First, Last)` karşılaştırma işlevi ve ayırıcı türünü belirtilirken explicitness artan bir çoklu kümenin.

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
    // function of geater than, then insert 2 elements
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

## <a name="op_eq"></a>  multiset::operator =

Bu öğelerini değiştirir `multiset` öğeleri başka bir kullanılarak `multiset`.

```cpp
multiset& operator=(const multiset& right);

multiset& operator=(multiset&& right);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|-|-|
|*sağ*|`multiset` Öğesinden öğeleri kopyalanamaz veya taşınamaz.|

### <a name="remarks"></a>Açıklamalar

`operator=` kopyalar veya öğeleri taşır *doğru* kopyalayıp bu `multiset`kullanılan başvurusu türü (lvalue veya rvalue) bağlı olarak. Bu öğeleri `multiset` önce `operator=` yürütür atılır.

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

## <a name="pointer"></a>  multiset::pointer

Bir çoklu küme bir öğeye işaretçi sağlayan bir tür.

```cpp
typedef typename allocator_type::pointer pointer;
```

### <a name="remarks"></a>Açıklamalar

Bir tür **işaretçi** bir öğenin değerini değiştirmek için kullanılabilir.

Çoğu durumda bir [yineleyici](#iterator) multiset nesnesindeki öğelere erişmek için kullanılmalıdır.

## <a name="rbegin"></a>  multiset::rbegin

Ters çevrilen bir çoklu küme ilk öğeyi adresleyen bir yineleyici döndürür.

```cpp
const_reverse_iterator rbegin() const;

reverse_iterator rbegin();
```

### <a name="return-value"></a>Dönüş Değeri

Ters çevrilen bir çoklu küme ilk öğeyi adresleyen veya ne son öğeyi ters çevrilmeyen çoklu kümedeki adresleyen ters iki yönlü yineleyici.

### <a name="remarks"></a>Açıklamalar

`rbegin` ters çevrilen bir çoklu küme ile rbegin bir çoklu küme ile yalnızca kullanılan olarak kullanılır.

Varsa dönüş değeri `rbegin` atanan bir `const_reverse_iterator`, ardından multiset nesnesi değiştirilemez. Varsa dönüş değeri `rbegin` atanan bir `reverse_iterator`, ardından multiset nesnesi değiştirilebilir.

`rbegin` bir çoklu küme geriye doğru gezinmek için kullanılabilir.

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

   // begin can be used to start an interation
   // throught a multiset in a forward order
   cout << "The multiset is:";
   for ( ms1_Iter = ms1.begin( ) ; ms1_Iter != ms1.end( ); ms1_Iter++ )
      cout << " " << *ms1_Iter;
   cout << endl;

   // rbegin can be used to start an interation
   // throught a multiset in a reverse order
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

## <a name="reference"></a>  multiset::Reference

Bir çoklu küme içinde depolanan öğeye başvuru sağlayan bir tür.

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

## <a name="rend"></a>  multiset::rend

Ters çevrilen bir çoklu küme son öğeden sonra gelen konumu ele alan bir yineleyici döndürür.

```cpp
const_reverse_iterator rend() const;

reverse_iterator rend();
```

### <a name="return-value"></a>Dönüş Değeri

Konumu (ters çevrilmeyen çoklu kümedeki ilk öğeyi önce gelen konum) ters çevrilen kümedeki son öğeyi adresleyen ters iki yönlü yineleyici.

### <a name="remarks"></a>Açıklamalar

`rend` ters çevrilen bir çoklu küme ile kullanılan gibi [son](#end) bir çoklu küme ile kullanılır.

Varsa dönüş değeri `rend` atanan bir `const_reverse_iterator`, ardından multiset nesnesi değiştirilemez. Varsa dönüş değeri `rend` atanan bir `reverse_iterator`, ardından multiset nesnesi değiştirilebilir.

`rend` olup ters yineleyici kendi multiset sonuna ulaşıp ulaşmadığını test etmek için kullanılabilir.

Tarafından döndürülen değer `rend` kaldırılmamalıdır.

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

   // end can be used to terminate an interation
   // throught a multiset in a forward order
   cout << "The multiset is: ";
   for ( ms1_Iter = ms1.begin( ) ; ms1_Iter != ms1.end( ); ms1_Iter++ )
      cout << *ms1_Iter << " ";
   cout << "." << endl;

   // rend can be used to terminate an interation
   // throught a multiset in a reverse order
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

## <a name="reverse_iterator"></a>  multiset::reverse_iterator

Okuma veya tersine çevrilmiş bir çoklu kümedeki bir öğenin değiştirebilen çift yönlü bir yineleyici sağlayan tür.

```cpp
typedef std::reverse_iterator<iterator> reverse_iterator;
```

### <a name="remarks"></a>Açıklamalar

Bir tür `reverse_iterator` kullanın çoklu ters yinelemek için.

### <a name="example"></a>Örnek

Örneğin bakın [rbegin](#rbegin) bildirme ve kullanma konusunda bir örnek için `reverse_iterator`.

## <a name="size"></a>  multiset::size

Çoklu Kümedeki öğelerin sayısını döndürür.

```cpp
size_type size() const;
```

### <a name="return-value"></a>Dönüş Değeri

Çoklu küme geçerli uzunluğu.

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

## <a name="size_type"></a>  multiset::size_type

Bir çoklu küme öğelerin sayısını temsil edebilen bir işaretsiz tamsayı türü.

```cpp
typedef typename allocator_type::size_type size_type;
```

### <a name="example"></a>Örnek

Örneğin bakın [boyutu](#size) bildirme ve kullanma örneği `size_type`

## <a name="swap"></a>  multiset::Swap

İki multisets öğelerini birbiriyle değiştirir.

```cpp
void swap(
    multiset<Key, Compare, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*sağ*<br/>
Hedef multiset ile değiştirilecek öğeleri sağlayan bağımsız değişken multiset.

### <a name="remarks"></a>Açıklamalar

Üye işlev hiçbir başvurular, işaretçiler veya öğeleri değiştirilen iki multisets öğeleri belirlemek yineleyicileri geçersiz kılar.

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

## <a name="upper_bound"></a>  multiset::upper_bound

Bir yineleyiciyi belirtilen anahtardan daha büyük bir anahtarla çoklu kümedeki ilk öğeye döndürür.

```cpp
const_iterator upper_bound(const Key& key) const;

iterator upper_bound(const Key& key);
```

### <a name="parameters"></a>Parametreler

*Anahtarı*<br/>
Bir çoklu küme Aranmakta öğeyi sıralama anahtarı ile Karşılaştırılacak bağımsız değişken anahtarı.

### <a name="return-value"></a>Dönüş Değeri

Bir **yineleyici** veya `const_iterator` adresleri bir öğenin konumunu çoklu kümedeki bir anahtar bağımsız değişkeni anahtardan daha büyük ya da için eşleşme bulunursa çoklu kümedeki son öğeyi takip eden konumu ele anahtarı.

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

## <a name="value_comp"></a>  multiset::value_comp

Bir çoklu küme öğe değerlerini sıralamak için kullanılan karşılaştırma nesnesinin bir kopyasını alır.

```cpp
value_compare value_comp() const;
```

### <a name="return-value"></a>Dönüş Değeri

Şablon parametresi olan bir çoklu küme, öğeleri düzenlemek amacıyla kullanan işlev nesnesini döndürür `Compare`.

Daha fazla bilgi için `Compare`, Açıklamalar bölümüne bakın [multiset sınıfı](../standard-library/multiset-class.md) konu.

### <a name="remarks"></a>Açıklamalar

Depolanan nesne üyesi işlevini tanımlar:

**bool işleci**( **const anahtar &**`_xVal`, **const anahtar &**`_yVal`);

hangi döndürür true ise `_xVal` önündeki ve eşit değildir `_yVal` sıralama düzeninde.

Unutmayın hem [key_compare](#key_compare) ve [value_compare](#value_compare) şablon parametresi için eş anlamlı sözcükler olan `Compare`. Multimap, farklı olduğu ve eşleme sınıfları ile uyumluluk için aynı olan, multiset ve sınıfları kümesi için her iki türü de sağlanır.

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

## <a name="value_compare"></a>  multiset::value_compare

Çoklu kümedeki kendi göreli sıralarını belirlemek için iki sıralama anahtarını karşılaştıran işlev nesnesi sağlayan tür.

```cpp
typedef key_compare value_compare;
```

### <a name="remarks"></a>Açıklamalar

`value_compare` Şablon parametresi için bir eşanlamlı olduğu `Compare`.

Unutmayın hem [key_compare](#key_compare) ve `value_compare` şablon parametresi için eş anlamlı sözcükler olan `Compare`. Multimap, farklı olduğu ve eşleme sınıfları ile uyumluluk için aynı olan, multiset ve sınıfları kümesi için her iki türü de sağlanır.

Daha fazla bilgi için `Compare`, Açıklamalar bölümüne bakın [multiset sınıfı](../standard-library/multiset-class.md) konu.

### <a name="example"></a>Örnek

Örneğin bakın [value_comp](#value_comp) bildirme ve kullanma konusunda bir örnek için `value_compare`.

## <a name="value_type"></a>  multiset::value_type

Öğe bir değer olarak kapasitesi dahilinde bir çoklu küme şeklinde depolanan nesneyi tanımlayan tür.

```cpp
typedef Key value_type;
```

### <a name="remarks"></a>Açıklamalar

`value_type` Şablon parametresi için bir eşanlamlı olduğu `Key`.

Unutmayın hem [key_type](#key_type) ve `value_type` şablon parametresi için eş anlamlı sözcükler olan `Key`. Multimap, farklı olduğu ve eşleme sınıfları ile uyumluluk için aynı olan, multiset ve sınıfları kümesi için her iki türü de sağlanır.

Daha fazla bilgi için `Key`, Açıklamalar bölümüne bakın.

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

[Kapsayıcılar](../cpp/containers-modern-cpp.md)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)<br/>
