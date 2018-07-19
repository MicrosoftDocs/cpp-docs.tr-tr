---
title: list sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- list/std::list
- list/std::list::allocator_type
- list/std::list::const_iterator
- list/std::list::const_pointer
- list/std::list::const_reference
- list/std::list::const_reverse_iterator
- list/std::list::difference_type
- list/std::list::iterator
- list/std::list::pointer
- list/std::list::reference
- list/std::list::reverse_iterator
- list/std::list::size_type
- list/std::list::value_type
- list/std::list::assign
- list/std::list::back
- list/std::list::begin
- list/std::list::cbegin
- list/std::list::cend
- list/std::list::clear
- list/std::list::crbegin
- list/std::list::crend
- list/std::list::emplace
- list/std::list::emplace_back
- list/std::list::emplace_front
- list/std::list::empty
- list/std::list::end
- list/std::list::erase
- list/std::list::front
- list/std::list::get_allocator
- list/std::list::insert
- list/std::list::max_size
- list/std::list::merge
- list/std::list::pop_back
- list/std::list::pop_front
- list/std::list::push_back
- list/std::list::push_front
- list/std::list::rbegin
- list/std::list::remove
- list/std::list::remove_if
- list/std::list::rend
- list/std::list::resize
- list/std::list::reverse
- list/std::list::size
- list/std::list::sort
- list/std::list::splice
- list/std::list::swap
- list/std::list::unique
dev_langs:
- C++
helpviewer_keywords:
- std::list [C++]
- std::list [C++], allocator_type
- std::list [C++], const_iterator
- std::list [C++], const_pointer
- std::list [C++], const_reference
- std::list [C++], const_reverse_iterator
- std::list [C++], difference_type
- std::list [C++], iterator
- std::list [C++], pointer
- std::list [C++], reference
- std::list [C++], reverse_iterator
- std::list [C++], size_type
- std::list [C++], value_type
- std::list [C++], assign
- std::list [C++], back
- std::list [C++], begin
- std::list [C++], cbegin
- std::list [C++], cend
- std::list [C++], clear
- std::list [C++], crbegin
- std::list [C++], crend
- std::list [C++], emplace
- std::list [C++], emplace_back
- std::list [C++], emplace_front
- std::list [C++], empty
- std::list [C++], end
- std::list [C++], erase
- std::list [C++], front
- std::list [C++], get_allocator
- std::list [C++], insert
- std::list [C++], max_size
- std::list [C++], merge
- std::list [C++], pop_back
- std::list [C++], pop_front
- std::list [C++], push_back
- std::list [C++], push_front
- std::list [C++], rbegin
- std::list [C++], remove
- std::list [C++], remove_if
- std::list [C++], rend
- std::list [C++], resize
- std::list [C++], reverse
- std::list [C++], size
- std::list [C++], sort
- std::list [C++], splice
- std::list [C++], swap
- std::list [C++], unique
ms.assetid: d3707f4a-10fd-444f-b856-f9ca2077c1cd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b31f1562e5db85f0638dfd32ba6e2db0f6f70fea
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38962923"
---
# <a name="list-class"></a>list Sınıfı

C++ Standart Kitaplığı listesi sınıfı, doğrusal bir düzenleme içinde öğeleri korumak ve verimli eklemeler ve silmeler dizisi içindeki herhangi bir yere izin veren bir dizi kapsayıcılarının bir şablon sınıfıdır. Dizinin her tür üyesi içeren öğe, çift yönlü bağlantılı liste olarak depolanan *türü*.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Type, class Allocator= allocator<Type>>
class list
```

### <a name="parameters"></a>Parametreler

*Tür* listesinde depolanacak öğe veri türü.

*Allocator* listenin ayırma ve bellek ayırmayı kaldırma hakkındaki ayrıntıları içeren saklı ayırıcı nesnesini gösteren tür. Bu bağımsız değişken isteğe bağlıdır ve varsayılan değer **ayırıcı**\<*türü*>.

## <a name="remarks"></a>Açıklamalar

Kapsayıcı türünün seçimi genelde uygulamanın gerektirdiği arama ve ekleme türüne dayalı olmalıdır. Vektör herhangi bir öğeye rastgele erişim, bir premium olduğunda ve eklemeler ve silmeleri öğelerin, yalnızca bir sıralı yönetmek için tercih edilen kapsayıcı olmalıdır sıralamadaki sonunda gereklidir. Sınıf deque kapsayıcı performansını eklemeler ve silmeler başlangıcı ve son sırasının rastgele erişim gereklidir ve bir premium üstündedir.

Liste üye işlevleri [birleştirme](#merge), [ters](#reverse), [benzersiz](#unique), [Kaldır](#remove), ve [remove_if](#remove_if) silinmiş işlem listesi nesneleri ve teklif genel karşılıkları yüksek performanslı bir alternatif için en iyi duruma getirilmiş.

Liste reallocation bir üye işlevi ekleme veya listenin öğelerini silmek oluşur. Böyle durumlarda, yalnızca Yineleyicilerin veya üzerine başvuru geçersiz hale denetlenen dizinin bölümleri silinir.

C++ Standart Kitaplığı standart üstbilgisini \<listesi > tanımlamak için [kapsayıcı](../standard-library/stl-containers.md) şablon sınıf listesi ve çeşitli destek şablonları.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[list](#list)|Belirli bir boyut veya belirli bir değer öğeleriyle veya belirli bir ile bir liste oluşturur `allocator` veya bir kopyasını başka bir liste olarak.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[allocator_type](#allocator_type)|Temsil eden bir tür `allocator` liste nesnesi için sınıf.|
|[const_iterator](#const_iterator)|Çift yönlü bir yineleyici sağlayan tür okuma bir **const** bir liste öğesi.|
|[const_pointer](#const_pointer)|Bir işaretçi sağlayan bir tür bir **const** bir liste öğesi.|
|[const_reference](#const_reference)|Bir başvuru sağlayan bir tür bir **const** okumak ve gerçekleştirmek için bir liste içinde depolanan öğenin **const** operations.|
|[const_reverse_iterator](#const_reverse_iterator)|Çift yönlü bir yineleyici sağlayan tür herhangi okuma **const** bir liste öğesi.|
|[difference_type](#difference_type)|Aynı liste içindeki öğelere başvuran iki yineleyici arasındaki farkı sağlayan bir tür.|
|[Yineleyici](#iterator)|Okuyabilen veya değiştirebilen bir listedeki herhangi bir öğeyi çift yönlü yineleyiciler sağlayan tür.|
|[İşaretçi](#pointer)|Bir listedeki bir öğeye işaretçi sağlayan bir tür.|
|[Başvuru](#reference)|Bir başvuru sağlayan bir tür bir **const** okumak ve gerçekleştirmek için bir liste içinde depolanan öğenin **const** operations.|
|[reverse_iterator](#reverse_iterator)|Okuyabilen veya değiştirebilen ters çevrilen bir listedeki bir öğe çift yönlü yineleyiciler sağlayan tür.|
|[size_type](#size_type)|Bir listedeki öğeleri sayar türü.|
|[value_type](#value_type)|Bir liste içinde depolanan veri türünü temsil eden tür.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[Ata](#assign)|Listeden öğeleri siler ve yeni bir öğe kümesini hedef listenin kopyalar.|
|[Geri](#back)|Bir liste öğesinin son öğesinin bir başvuru döndürür.|
|[başlayın](#begin)|Bir listedeki ilk öğeyi ele alan bir yineleyici döndürür.|
|[cbegin](#cbegin)|Bir listedeki ilk öğeyi adresleyerek bir const yineleyici döndürür.|
|[cend](#cend)|Bir listedeki son öğeyi takip eden konumu ele alan sabit bir yineleyici döndürür.|
|[Temizle](#clear)|Bir listenin tüm öğelerini siler.|
|[crbegin](#crbegin)|Ters çevrilen bir listedeki ilk öğeyi ele alan sabit bir yineleyici döndürür.|
|[crend](#crend)|Ters çevrilen bir listedeki son öğeden sonra gelen konumu ele alan bir sabit yineleyici döndürür.|
|[emplace](#emplace)|Belirtilen konumda bir liste içine yerinde oluşturulmuş bir öğe ekler.|
|[emplace_back](#emplace_back)|Bir listenin sonuna yerinde oluşturulmuş bir öğe ekler.|
|[emplace_front](#emplace_front)|Bir listenin başına yerinde oluşturulmuş bir öğe ekler.|
|[boş](#empty)|Liste boş olup olmadığını sınar.|
|[Son](#end)|Bir listedeki son öğeden sonra gelen konumu ele alan bir yineleyici döndürür.|
|[silme](#erase)|Bir öğenin veya öğelerin aralığını belirtilen konumlardan listesindeki kaldırır.|
|[Ön](#front)|Bir listedeki ilk öğeye bir başvuru döndürür.|
|[get_allocator](#get_allocator)|Bir kopyasını döndürür `allocator` listesini oluşturmak için kullanılan nesne.|
|[Ekle](#insert)|Bir öğenin veya öğelerin bir sayı veya öğe aralığını belirtilen konumda bir liste ekler.|
|[max_size](#max_size)|Bir listenin maksimum uzunluğunu döndürür.|
|[Birleştirme](#merge)|Bağımsız değişken listeden öğeleri kaldırır, bunları hedef listesine ekler ve yeni birleşik öğeleri artan sırada veya başka bir belirtilen sırayla kümesini sıralar.|
|[pop_back](#pop_back)|Bir liste sonundaki öğeyi silin.|
|[pop_front](#pop_front)|Bir liste başındaki öğeyi silin.|
|[push_back](#push_back)|Bir öğe listesinin sonuna ekler.|
|[push_front](#push_front)|Bir listenin başına bir öğe ekler.|
|[rbegin](#rbegin)|Ters çevrilen bir listedeki ilk öğeyi adresleyen bir yineleyici döndürür.|
|[remove](#remove)|Belirtilen bir değerle eşleşen bir listedeki öğeleri siler.|
|[remove_if](#remove_if)|Kendisi için belirtilen bir koşul sağlanırsa listeden öğeleri siler.|
|[rend](#rend)|Ters çevrilen bir listedeki son öğeden sonra gelen konumu ele alan bir yineleyici döndürür.|
|[yeniden boyutlandırma](#resize)|Bir liste için yeni bir boyut belirtir.|
|[geriye doğru](#reverse)|Öğeleri listede oluşabilen sırasını tersine çevirir.|
|[Boyutu](#size)|Bir listedeki öğelerin sayısını döndürür.|
|[Sıralama](#sort)|Öğeleri artan sırada veya başka bir sipariş ilişkisine göre düzenler.|
|[splice](#splice)|Bağımsız değişken listeden öğeleri kaldırır ve bunları hedef listesine ekler.|
|[değiştirme](#swap)|İki listenin öğelerini değiştirir.|
|[benzersiz](#unique)|Bitişik yinelenen öğeler veya bazı diğer ikili koşul listeden karşılayan bitişik öğeyi kaldırır.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[list::operator=](#op_eq)|Listenin öğelerini başka bir liste kopyasıyla değiştirir.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi**: \<listesi >

## <a name="allocator_type"></a>  list::allocator_type

Bir liste nesnesi için ayırıcı sınıf temsil eden tür.

```cpp
typedef Allocator allocator_type;
```

### <a name="remarks"></a>Açıklamalar

`allocator_type` Şablon parametresi için bir eşanlamlı olduğu *ayırıcı*.

### <a name="example"></a>Örnek

Örneğin bakın [get_allocator](#get_allocator).

## <a name="assign"></a>  List::Assign

Listeden öğeleri siler ve bir hedef listesine yeni bir öğe kümesini kopyalar.

```cpp
void assign(
    size_type Count,
    const Type& Val);

void assign
    initializer_list<Type> IList);

template <class InputIterator>
void assign(
    InputIterator First,
    InputIterator Last);
```

### <a name="parameters"></a>Parametreler

*İlk* bağımsız değişken listesinden kopyalanacak ilk öğenin aralığındaki öğelerin konumu.

*Son* bağımsız değişken listesinden kopyalanacak yalnızca öğe aralığının dışındaki ilk öğenin konumu.

*Sayısı* listesine eklenen öğenin kopyası sayısı.

*VAL* listesine eklenen öğenin değeri.

*IList* eklenecek öğeleri içeren initializer_list.

### <a name="remarks"></a>Açıklamalar

Hedef listedeki var olan öğeleri silme sonra Ata belirtilen bir aralıktaki öğelerin özgün listesinden veya başka bir liste hedef listesine ekler ya da yeni bir öğe belirli bir değerin bir kopyasını hedef listesine ekler.

### <a name="example"></a>Örnek

```cpp
// list_assign.cpp
// compile with: /EHsc
#include <list>
#include <iostream>

int main()
{
    using namespace std;
    list<int> c1, c2;
    list<int>::const_iterator cIter;

    c1.push_back(10);
    c1.push_back(20);
    c1.push_back(30);
    c2.push_back(40);
    c2.push_back(50);
    c2.push_back(60);

    cout << "c1 =";
    for (auto c : c1)
        cout << " " << c;
    cout << endl;

    c1.assign(++c2.begin(), c2.end());
    cout << "c1 =";
    for (auto c : c1)
        cout << " " << c;
    cout << endl;

    c1.assign(7, 4);
    cout << "c1 =";
    for (auto c : c1)
        cout << " " << c;
    cout << endl;

    c1.assign({ 10, 20, 30, 40 });
    cout << "c1 =";
    for (auto c : c1)
        cout << " " << c;
    cout << endl;
}
```

```Output
c1 = 10 20 30c1 = 50 60c1 = 4 4 4 4 4 4 4c1 = 10 20 30 40
```

## <a name="back"></a>  List::Back

Bir liste öğesinin son öğesinin bir başvuru döndürür.

```cpp
reference back();

const_reference back() const;
```

### <a name="return-value"></a>Dönüş Değeri

Listedeki son öğe. Liste boş ise, dönüş değeri tanımsızdır.

### <a name="remarks"></a>Açıklamalar

Varsa dönüş değerinin `back` atanan bir `const_reference`, liste nesnesi değiştirilemez. Varsa dönüş değerinin `back` atanan bir `reference`, liste nesnesi değiştirilebilir.

Kullanılarak derlendiğinde [_ıterator_debug_level](../standard-library/iterator-debug-level.md) 1 veya 2 ' tanımlı, boş bir listedeki bir öğeye erişmeyi denerseniz bir çalışma zamanı hatası oluşur.  Bkz: [Checked Iterators](../standard-library/checked-iterators.md) daha fazla bilgi için.

### <a name="example"></a>Örnek

```cpp
// list_back.cpp
// compile with: /EHsc
#include <list>
#include <iostream>

int main( )
{
   using namespace std;
   list <int> c1;

   c1.push_back( 10 );
   c1.push_back( 11 );

   int& i = c1.back( );
   const int& ii = c1.front( );

   cout << "The last integer of c1 is " << i << endl;
   i--;
   cout << "The next-to-last integer of c1 is " << ii << endl;
}
```

```Output
The last integer of c1 is 11
The next-to-last integer of c1 is 10
```

## <a name="begin"></a>  List::Begin

Bir listedeki ilk öğeyi ele alan bir yineleyici döndürür.

```cpp
const_iterator begin() const;

iterator begin();
```

### <a name="return-value"></a>Dönüş Değeri

Listesinde veya sonra gelen konumu adresleyen boş bir liste için ilk öğeyi ele alan bir çift yönlü yineleyici.

### <a name="remarks"></a>Açıklamalar

Varsa dönüş değerinin `begin` atanan bir `const_iterator`, öğeleri liste nesnesi değiştirilemez. Varsa dönüş değerinin `begin` atanan bir `iterator`, öğeleri liste nesnesi değiştirilebilir.

### <a name="example"></a>Örnek

```cpp
// list_begin.cpp
// compile with: /EHsc
#include <list>
#include <iostream>

int main( )
{
   using namespace std;
   list <int> c1;
   list <int>::iterator c1_Iter;
   list <int>::const_iterator c1_cIter;

   c1.push_back( 1 );
   c1.push_back( 2 );

   c1_Iter = c1.begin( );
   cout << "The first element of c1 is " << *c1_Iter << endl;

*c1_Iter = 20;
   c1_Iter = c1.begin( );
   cout << "The first element of c1 is now " << *c1_Iter << endl;

   // The following line would be an error because iterator is const
   // *c1_cIter = 200;
}
```

```Output
The first element of c1 is 1
The first element of c1 is now 20
```

## <a name="cbegin"></a>  List::cbegin

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

## <a name="cend"></a>  List::cend

Döndürür bir `const` konuma bir aralıktaki son öğeyi ele alan bir yineleyici.

```cpp
const_iterator cend() const;
```

### <a name="return-value"></a>Dönüş Değeri

A `const` aralığın sonunu yalnızca çift yönlü erişim yineleyicisi.

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

## <a name="clear"></a>  List::Clear

Bir listenin tüm öğelerini siler.

```cpp
void clear();
```

### <a name="example"></a>Örnek

```cpp
// list_clear.cpp
// compile with: /EHsc
#include <list>
#include <iostream>

int main() {
   using namespace std;
   list <int> c1;

   c1.push_back( 10 );
   c1.push_back( 20 );
   c1.push_back( 30 );

   cout << "The size of the list is initially " << c1.size( ) << endl;
   c1.clear( );
   cout << "The size of list after clearing is " << c1.size( ) << endl;
}
```

```Output
The size of the list is initially 3
The size of list after clearing is 0
```

## <a name="const_iterator"></a>  List::const_iterator

Çift yönlü bir yineleyici sağlayan tür okuma bir **const** bir liste öğesi.

```cpp
typedef implementation-defined const_iterator;
```

### <a name="remarks"></a>Açıklamalar

Bir tür `const_iterator` bir öğenin değerini değiştirmek için kullanılamaz.

### <a name="example"></a>Örnek

Örneğin bakın [geri](#back).

## <a name="const_pointer"></a>  list::const_pointer

İşaretçi sağlayan bir **const** bir liste öğesi.

```cpp
typedef typename Allocator::const_pointer const_pointer;
```

### <a name="remarks"></a>Açıklamalar

Bir tür `const_pointer` bir öğenin değerini değiştirmek için kullanılamaz.

Çoğu durumda bir [yineleyici](#iterator) bir liste nesnesindeki öğelere erişmek için kullanılmalıdır.

## <a name="const_reference"></a>  List::const_reference

Bir başvuru sağlayan bir tür bir **const** okumak ve gerçekleştirmek için bir liste içinde depolanan öğenin **const** operations.

```cpp
typedef typename Allocator::const_reference const_reference;
```

### <a name="remarks"></a>Açıklamalar

Bir tür `const_reference` bir öğenin değerini değiştirmek için kullanılamaz.

### <a name="example"></a>Örnek

```cpp
// list_const_ref.cpp
// compile with: /EHsc
#include <list>
#include <iostream>

int main( )
{
   using namespace std;
   list <int> c1;

   c1.push_back( 10 );
   c1.push_back( 20 );

   const list <int> c2 = c1;
   const int &i = c2.front( );
   const int &j = c2.back( );
   cout << "The first element is " << i << endl;
   cout << "The second element is " << j << endl;

   // The following line would cause an error because c2 is const
   // c2.push_back( 30 );
}
```

```Output
The first element is 10
The second element is 20
```

## <a name="const_reverse_iterator"></a>  List::const_reverse_iterator

Çift yönlü bir yineleyici sağlayan tür herhangi okuma **const** bir liste öğesi.

```cpp
typedef std::reverse_iterator<const_iterator> const_reverse_iterator;
```

### <a name="remarks"></a>Açıklamalar

Bir tür `const_reverse_iterator` bir öğenin değerini değiştiremez ve ters listesinde yinelemek için kullanılır.

### <a name="example"></a>Örnek

Örneğin bakın [rbegin](#rbegin).

## <a name="crbegin"></a>  List::crbegin

Ters çevrilen bir listedeki ilk öğeyi ele alan sabit bir yineleyici döndürür.

```cpp
const_reverse_iterator rbegin() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir sabit ters çevrilen bir listedeki ilk öğeyi ele alan çift yönlü yineleyici (veya ne ters çevrilmeyen içindeki son öğeyi adresleyen `list`).

### <a name="remarks"></a>Açıklamalar

`crbegin` bir listeyle kullanılır gibi [list::begin](#begin) ile kullanılan bir `list`.

Dönüş değeri ile `crbegin`, liste nesnesi değiştirilemez. [List::rbegin](#rbegin) bir listede geriye doğru gezinmek için kullanılabilir.

### <a name="example"></a>Örnek

```cpp
// list_crbegin.cpp
// compile with: /EHsc
#include <list>
#include <iostream>

int main( )
{
   using namespace std;
   list <int> c1;
   list <int>::const_reverse_iterator c1_crIter;

   c1.push_back( 10 );
   c1.push_back( 20 );
   c1.push_back( 30 );
   c1_crIter = c1.crbegin( );
   cout << "The last element in the list is " << *c1_crIter << "." << endl;
}
```

```Output
The last element in the list is 30.
```

## <a name="crend"></a>  List::crend

Ters çevrilen bir listedeki son öğeden sonra gelen konumu ele alan bir sabit yineleyici döndürür.

```cpp
const_reverse_iterator rend() const;
```

### <a name="return-value"></a>Dönüş Değeri

Ters çevrilen bir içindeki son öğeden sonra gelen konumu ele çift yönlü yineleyici bir const [listesi](../standard-library/list-class.md) (ilk öğeyi çevrilmeyen önce gelen konum `list`).

### <a name="remarks"></a>Açıklamalar

`crend` bir listeyle kullanılır gibi [list::end](#end) ile kullanılan bir `list`.

Dönüş değeri ile `crend`, `list` nesnesi değiştirilemez.

`crend` olup ters yineleyici sonuna ulaşıp ulaşmadığını test etmek için kullanılan kendi `list`.

Tarafından döndürülen değer `crend` kaldırılmamalıdır.

### <a name="example"></a>Örnek

```cpp
// list_crend.cpp
// compile with: /EHsc
#include <list>
#include <iostream>

int main( )
{
   using namespace std;
   list <int> c1;
   list <int>::const_reverse_iterator c1_crIter;

   c1.push_back( 10 );
   c1.push_back( 20 );
   c1.push_back( 30 );

   c1_crIter = c1.crend( );
   c1_crIter --;  // Decrementing a reverse iterator moves it forward in
                 // the list (to point to the first element here)
   cout << "The first element in the list is: " << *c1_crIter << endl;
}
```

```Output
The first element in the list is: 10
```

## <a name="difference_type"></a>  List::difference_type

Bir listenin yineleyiciler tarafından gösterilen öğeler arasındaki bir aralıktaki öğelerin sayısını temsil etmek için kullanılabilen işaretli bir tamsayı türü.

```cpp
typedef typename Allocator::difference_type difference_type;
```

### <a name="remarks"></a>Açıklamalar

`difference_type` Türü çıkarma veya kapsayıcının yineleyiciler artan döndürülür. `difference_type` Genellikle aralık içindeki öğelerin sayısını temsil etmek için kullanılan [ `first`, `last`) yineleyici arasındaki `first` ve `last`, işaret ettiği öğe içerir `first` ve en fazla öğe aralığı , ancak dahil değil tarafından işaret edilen öğeyi `last`.

Ancak dikkat `difference_type` kümesi, yineleyici arasındaki çıkarma yalnızca gibi ters çevrilebilir kapsayıcıları tarafından desteklenen çift yönlü Yineleyicilerin sınıfında içeren bir giriş yineleyici gereksinimlerini karşılayan tüm yineleyiciler için kullanılabilir gibi bir rastgele erişim kapsayıcı tarafından sağlanan rasgele erişim yineleyicileri tarafından desteklenen [vector sınıfı](../standard-library/vector-class.md).

### <a name="example"></a>Örnek

```cpp
// list_diff_type.cpp
// compile with: /EHsc
#include <iostream>
#include <list>
#include <algorithm>

int main( )
{
   using namespace std;

   list <int> c1;
   list <int>::iterator   c1_Iter, c2_Iter;

   c1.push_back( 30 );
   c1.push_back( 20 );
   c1.push_back( 30 );
   c1.push_back( 10 );
   c1.push_back( 30 );
   c1.push_back( 20 );

   c1_Iter = c1.begin( );
   c2_Iter = c1.end( );

    list <int>::difference_type df_typ1, df_typ2, df_typ3;

   df_typ1 = count( c1_Iter, c2_Iter, 10 );
   df_typ2 = count( c1_Iter, c2_Iter, 20 );
   df_typ3 = count( c1_Iter, c2_Iter, 30 );
   cout << "The number '10' is in c1 collection " << df_typ1 << " times.\n";
   cout << "The number '20' is in c1 collection " << df_typ2 << " times.\n";
   cout << "The number '30' is in c1 collection " << df_typ3 << " times.\n";
}
```

```Output
The number '10' is in c1 collection 1 times.
The number '20' is in c1 collection 2 times.
The number '30' is in c1 collection 3 times.
```

## <a name="emplace"></a>  List::emplace

Belirtilen konumda bir liste içine yerinde oluşturulmuş bir öğe ekler.

```cpp
void emplace(iterator Where, Type&& val);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|-|-|
|*Burada*|Hedef konumda [listesi](../standard-library/list-class.md) ilk öğeyi burada eklenir.|
|*VAL*|Sonuna eklenen öğe `list`.|

### <a name="remarks"></a>Açıklamalar

Bir özel durum oluşturulursa `list` sol değiştirilmeden ve özel durum yeniden oluşur.

### <a name="example"></a>Örnek

```cpp
// list_emplace.cpp
// compile with: /EHsc
#include <list>
#include <iostream>
#include <string>

int main( )
{
   using namespace std;
   list <string> c2;
   string str("a");

   c2.emplace(c2.begin(), move( str ) );
   cout << "Moved first element: " << c2.back( ) << endl;
}
```

```Output
Moved first element: a
```

## <a name="emplace_back"></a>  List::emplace_back

Bir listenin sonuna yerinde oluşturulmuş bir öğe ekler.

```cpp
void emplace_back(Type&& val);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|-|-|
|*VAL*|Sonuna eklenen öğe [listesi](../standard-library/list-class.md).|

### <a name="remarks"></a>Açıklamalar

Bir özel durum oluşturulursa `list` sol değiştirilmeden ve özel durum yeniden oluşur.

### <a name="example"></a>Örnek

```cpp
// list_emplace_back.cpp
// compile with: /EHsc
#include <list>
#include <iostream>
#include <string>

int main( )
{
   using namespace std;
   list <string> c2;
   string str("a");

   c2.emplace_back( move( str ) );
   cout << "Moved first element: " << c2.back( ) << endl;
}
```

```Output
Moved first element: a
```

## <a name="emplace_front"></a>  List::emplace_front

Bir listenin başına yerinde oluşturulmuş bir öğe ekler.

```cpp
void emplace_front(Type&& val);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|-|-|
|*VAL*|Başlangıcına eklenen öğe [listesi](../standard-library/list-class.md).|

### <a name="remarks"></a>Açıklamalar

Bir özel durum oluşturulursa `list` sol değiştirilmeden ve özel durum yeniden oluşur.

### <a name="example"></a>Örnek

```cpp
// list_emplace_front.cpp
// compile with: /EHsc
#include <list>
#include <iostream>
#include <string>

int main( )
{
   using namespace std;
   list <string> c2;
   string str("a");

   c2.emplace_front( move( str ) );
   cout << "Moved first element: " << c2.front( ) << endl;
}
```

```Output
Moved first element: a
```

## <a name="empty"></a>  List::empty

Liste boş olup olmadığını sınar.

```cpp
bool empty() const;
```

### <a name="return-value"></a>Dönüş Değeri

**doğru** liste boşsa; **false** listesi boş değilse.

### <a name="example"></a>Örnek

```cpp
// list_empty.cpp
// compile with: /EHsc
#include <list>
#include <iostream>

int main( )
{
   using namespace std;
   list <int> c1;

   c1.push_back( 10 );
   if ( c1.empty( ) )
      cout << "The list is empty." << endl;
   else
      cout << "The list is not empty." << endl;
}
```

```Output
The list is not empty.
```

## <a name="end"></a>  List::End

Bir listedeki son öğeden sonra gelen konumu ele alan bir yineleyici döndürür.

```cpp
const_iterator end() const;
iterator end();
```

### <a name="return-value"></a>Dönüş Değeri

Bir listedeki son öğeden sonra gelen konumu ele çift yönlü bir yineleyici. Liste boş ise, `list::end == list::begin`.

### <a name="remarks"></a>Açıklamalar

`end` bir yineleyicinin listesinin sonuna ulaştı olup olmadığını sınamak için kullanılır.

### <a name="example"></a>Örnek

```cpp
// list_end.cpp
// compile with: /EHsc
#include <list>
#include <iostream>

int main( )
{
   using namespace std;
   list <int> c1;
   list <int>::iterator c1_Iter;

   c1.push_back( 10 );
   c1.push_back( 20 );
   c1.push_back( 30 );

   c1_Iter = c1.end( );
   c1_Iter--;
   cout << "The last integer of c1 is " << *c1_Iter << endl;

   c1_Iter--;
 *c1_Iter = 400;
   cout << "The new next-to-last integer of c1 is "
        << *c1_Iter << endl;

   // If a const iterator had been declared instead with the line:
   // list <int>::const_iterator c1_Iter;
   // an error would have resulted when inserting the 400

   cout << "The list is now:";
   for ( c1_Iter = c1.begin( ); c1_Iter != c1.end( ); c1_Iter++ )
      cout << " " << *c1_Iter;
}
```

```Output
The last integer of c1 is 30
The new next-to-last integer of c1 is 400
The list is now: 10 400 30
```

## <a name="erase"></a>  List::ERASE

Bir öğenin veya öğelerin aralığını belirtilen konumlardan listesindeki kaldırır.

```cpp
iterator erase(iterator Where);
iterator erase(iterator first, iterator last);
```

### <a name="parameters"></a>Parametreler

*Burada* listeden kaldırılacak öğenin konumu.

*İlk* ilk öğenin konumunu listeden kaldırıldı.

*Son* yalnızca son öğenin ötesinde listeden kaldırıldı.

### <a name="return-value"></a>Dönüş Değeri

Kaldırılan tüm öğelerin ötesindeki ilk öğeyi belirleyen çift yönlü bir yineleyici, veya böyle bir öğe varsa, listenin sonuna bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Yineleyiciler ve başvurular için yalnızca silinen öğeleri geçersiz eşlenmelerine hiçbir reallocation gerçekleşir.

`erase` hiçbir zaman bir özel durum oluşturur.

### <a name="example"></a>Örnek

```cpp
// list_erase.cpp
// compile with: /EHsc
#include <list>
#include <iostream>

int main( )
{
   using namespace std;
   list <int> c1;
   list <int>::iterator Iter;

   c1.push_back( 10 );
   c1.push_back( 20 );
   c1.push_back( 30 );
   c1.push_back( 40 );
   c1.push_back( 50 );
   cout << "The initial list is:";
   for ( Iter = c1.begin( ); Iter != c1.end( ); Iter++ )
      cout << " " << *Iter;
   cout << endl;

   c1.erase( c1.begin( ) );
   cout << "After erasing the first element, the list becomes:";
   for ( Iter = c1.begin( ); Iter != c1.end( ); Iter++ )
      cout << " " << *Iter;
   cout << endl;
   Iter = c1.begin( );
   Iter++;
   c1.erase( Iter, c1.end( ) );
   cout << "After erasing all elements but the first, the list becomes: ";
   for (Iter = c1.begin( ); Iter != c1.end( ); Iter++ )
      cout << " " << *Iter;
   cout << endl;
}
```

```Output
The initial list is: 10 20 30 40 50
After erasing the first element, the list becomes: 20 30 40 50
After erasing all elements but the first, the list becomes:  20
```

## <a name="front"></a>  List::Front

Bir listedeki ilk öğeye bir başvuru döndürür.

```cpp
reference front();
const_reference front() const;
```

### <a name="return-value"></a>Dönüş Değeri

Liste boş ise, dönüş tanımsızdır.

### <a name="remarks"></a>Açıklamalar

Varsa dönüş değerinin `front` atanan bir `const_reference`, liste nesnesi değiştirilemez. Varsa dönüş değerinin `front` atanan bir `reference`, liste nesnesi değiştirilebilir.

Kullanılarak derlendiğinde [_ıterator_debug_level](../standard-library/iterator-debug-level.md) 1 veya 2 ' tanımlı, boş bir listedeki bir öğeye erişmeyi denerseniz bir çalışma zamanı hatası oluşur.  Bkz: [Checked Iterators](../standard-library/checked-iterators.md) daha fazla bilgi için.

### <a name="example"></a>Örnek

```cpp
// list_front.cpp
// compile with: /EHsc
#include <list>
#include <iostream>

int main() {
   using namespace std;
   list <int> c1;

   c1.push_back( 10 );

   int& i = c1.front();
   const int& ii = c1.front();

   cout << "The first integer of c1 is " << i << endl;
   i++;
   cout << "The first integer of c1 is " << ii << endl;
}
```

```Output
The first integer of c1 is 10
The first integer of c1 is 11
```

## <a name="get_allocator"></a>  List::get_allocator

Bir liste oluşturmak için kullanılan ayırıcı nesnesinin bir kopyasını döndürür.

```cpp
Allocator get_allocator() const;
```

### <a name="return-value"></a>Dönüş Değeri

Liste tarafından kullanılan ayırıcı.

### <a name="remarks"></a>Açıklamalar

Ayırıcılar listesi sınıfı için sınıf depolama nasıl yönettiğini belirtin. C++ Standart Kitaplığı kapsayıcı sınıfları ile sağlanan varsayılan ayırıcılar çoğu programlama ihtiyaçları için yeterli. Yazma ve kendi allocator sınıfı kullanarak bir Gelişmiş C++ konudur.

### <a name="example"></a>Örnek

```cpp
// list_get_allocator.cpp
// compile with: /EHsc
#include <list>
#include <iostream>

int main( )
{
   using namespace std;
   // The following lines declare objects
   // that use the default allocator.
   list <int> c1;
   list <int, allocator<int> > c2 = list <int, allocator<int> >( allocator<int>( ) );

   // c3 will use the same allocator class as c1
   list <int> c3( c1.get_allocator( ) );

   list<int>::allocator_type xlst = c1.get_allocator( );
   // You can now call functions on the allocator class used by c1
}
```

## <a name="insert"></a>  List::insert

Bir öğenin veya öğelerin bir sayı veya öğe aralığını belirtilen konumda bir liste ekler.

```cpp
iterator insert(iterator Where, const Type& Val);
iterator insert(iterator Where, Type&& Val);

void insert(iterator Where, size_type Count, const Type& Val);
iterator insert(iterator Where, initializer_list<Type> IList);

template <class InputIterator>
void insert(iterator Where, InputIterator First, InputIterator Last);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|-|-|
|*Burada*|Hedef listedeki ilk öğeyi burada eklenir konumu.|
|*VAL*|Listeye eklenen öğe değeri.|
|*Sayısı*|Listeye eklenen öğe sayısı.|
|*ilk*|İçindeki bağımsız değişken listesinde kopyalanacak öğe aralığının ilk öğenin konumu.|
|*Son*|Bağımsız değişken listesinde kopyalanacak öğe aralığının dışındaki ilk öğenin konumu.|

### <a name="return-value"></a>Dönüş Değeri

İlk iki INSERT işlevler burada yeni bir öğe listesine eklenmiş konumu gösteren bir yineleyici döndürür.

### <a name="example"></a>Örnek

```cpp
// list_class_insert.cpp
// compile with: /EHsc
#include <list>
#include <iostream>
#include <string>

int main()
{
    using namespace std;
    list <int> c1, c2;
    list <int>::iterator Iter;

    c1.push_back(10);
    c1.push_back(20);
    c1.push_back(30);
    c2.push_back(40);
    c2.push_back(50);
    c2.push_back(60);

    cout << "c1 =";
    for (auto c : c1)
        cout << " " << c;
    cout << endl;

    Iter = c1.begin();
    Iter++;
    c1.insert(Iter, 100);
    cout << "c1 =";
    for (auto c : c1)
        cout << " " << c;
    cout << endl;

    Iter = c1.begin();
    Iter++;
    Iter++;
    c1.insert(Iter, 2, 200);

    cout << "c1 =";
    for(auto c : c1)
        cout << " " << c;
    cout << endl;

    c1.insert(++c1.begin(), c2.begin(), --c2.end());

    cout << "c1 =";
    for (auto c : c1)
        cout << " " << c;
    cout << endl;

    // initialize a list of strings by moving
    list < string > c3;
    string str("a");

    c3.insert(c3.begin(), move(str));
    cout << "Moved first element: " << c3.front() << endl;

    // Assign with an initializer_list
    list <int> c4{ {1, 2, 3, 4} };
    c4.insert(c4.begin(), { 5, 6, 7, 8 });

    cout << "c4 =";
    for (auto c : c4)
        cout << " " << c;
    cout << endl;
}
```

## <a name="iterator"></a>  List::iterator

Okuyabilen veya değiştirebilen bir listedeki herhangi bir öğeyi çift yönlü yineleyiciler sağlayan tür.

```cpp
typedef implementation-defined iterator;
```

### <a name="remarks"></a>Açıklamalar

Bir tür `iterator` bir öğenin değerini değiştirmek için kullanılabilir.

### <a name="example"></a>Örnek

Örneğin bakın [başlamak](#begin).

## <a name="list"></a>  List::List

Belirli bir boyut veya belirli bir değer veya belirli bir ayırıcı veya tüm kopyalama veya başka bir listenin bir parçası olarak öğeleri içeren bir liste oluşturur.

```cpp
list();
explicit list(const Allocator& Al);
explicit list(size_type Count);
list(size_type Count, const Type& Val);
list(size_type Count, const Type& Val, const Allocator& Al);

list(const list& Right);
list(list&& Right);
list(initializer_list<Type> IList, const Allocator& Al);

template <class InputIterator>
list(InputIterator First, InputIterator Last);

template <class InputIterator>
list(InputIterator First, InputIterator Last, const Allocator& Al);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|-|-|
|*Al*|Bu nesneyle kullanılacak kaynak ayırıcı sınıfı.|
|*Sayısı*|Oluşturulan listedeki öğelerin sayısı.|
|*VAL*|Listedeki öğelerin değeri.|
|*Sağ*|Oluşturulan listenin kopyası olacak olduğu listesi.|
|*ilk*|Kopyalanacak öğe aralığındaki ilk öğenin konumu.|
|*Son*|Kopyalanacak öğe aralığının dışındaki ilk öğenin konumu.|
|*IList*|Kopyalanacak öğe içeren initializer_list.|

### <a name="remarks"></a>Açıklamalar

Tüm oluşturucular ayırıcı nesnesini depolar (*Al*) ve listeyi başlatır.

[get_allocator](#get_allocator) listesini oluşturmak için kullanılan ayırıcı nesnesinin bir kopyasını döndürür.

İlk iki Oluşturucu bir boş bir başlangıç listesi, ikinci belirtin ayırıcı türünü (*Al*) kullanılacak.

Üçüncü Oluşturucu, belirtilen bir tekrarını belirtir (*sayısı*) sınıfı için varsayılan değer öğelerinin `Type`.

Dördüncü ve beşinci oluşturucular yineleneceğini belirtir (*sayısı*) değerinin öğelerinin *Val*.

Altıncı Oluşturucu listesinin bir kopyasını belirtir *sağ*.

Liste yedinci Oluşturucusu taşınır *sağ*.

Sekizinci Oluşturucusu öğeleri belirtmek için bir initializer_list kullanır.

Sıradaki iki Oluşturucu aralığını kopyalamaktadır `[First, Last)` listesi.

Hiçbiri, herhangi bir geçici yapıcıların gerçekleştirin.

### <a name="example"></a>Örnek

```cpp
// list_class_list.cpp
// compile with: /EHsc
#include <list>
#include <iostream>

int main()
{
    using namespace std;
    // Create an empty list c0
    list <int> c0;

    // Create a list c1 with 3 elements of default value 0
    list <int> c1(3);

    // Create a list c2 with 5 elements of value 2
    list <int> c2(5, 2);

    // Create a list c3 with 3 elements of value 1 and with the
    // allocator of list c2
    list <int> c3(3, 1, c2.get_allocator());

    // Create a copy, list c4, of list c2
    list <int> c4(c2);

    // Create a list c5 by copying the range c4[ first,  last)
    list <int>::iterator c4_Iter = c4.begin();
    c4_Iter++;
    c4_Iter++;
    list <int> c5(c4.begin(), c4_Iter);

    // Create a list c6 by copying the range c4[ first,  last) and with
    // the allocator of list c2
    c4_Iter = c4.begin();
    c4_Iter++;
    c4_Iter++;
    c4_Iter++;
    list <int> c6(c4.begin(), c4_Iter, c2.get_allocator());

    cout << "c1 =";
    for (auto c : c1)
        cout << " " << c;
    cout << endl;

    cout << "c2 =";
    for (auto c : c2)
        cout << " " << c;
    cout << endl;

    cout << "c3 =";
    for (auto c : c3)
        cout << " " << c;
    cout << endl;

    cout << "c4 =";
    for (auto c : c4)
        cout << " " << c;
    cout << endl;

    cout << "c5 =";
    for (auto c : c5)
        cout << " " << c;
    cout << endl;

    cout << "c6 =";
    for (auto c : c6)
        cout << " " << c;
    cout << endl;

    // Move list c6 to list c7
    list <int> c7(move(c6));
    cout << "c7 =";
    for (auto c : c7)
        cout << " " << c;
    cout << endl;

    // Construct with initializer_list
    list<int> c8({ 1, 2, 3, 4 });
    cout << "c8 =";
    for (auto c : c8)
        cout << " " << c;
    cout << endl;
}
```

```Output
c1 = 0 0 0c2 = 2 2 2 2 2c3 = 1 1 1c4 = 2 2 2 2 2c5 = 2 2c6 = 2 2 2c7 = 2 2 2c8 = 1 2 3 4
```

## <a name="max_size"></a>  List::max_size

Bir listenin maksimum uzunluğunu döndürür.

```cpp
size_type max_size() const;
```

### <a name="return-value"></a>Dönüş Değeri

Listenin maksimum olası uzunluğu.

### <a name="example"></a>Örnek

```cpp
// list_max_size.cpp
// compile with: /EHsc
#include <list>
#include <iostream>

int main( )
{
   using namespace std;
   list <int> c1;
   list <int>::size_type i;

   i = c1.max_size( );
   cout << "Maximum possible length of the list is " << i << "." << endl;
}
```

## <a name="merge"></a>  List::Merge

Bağımsız değişken listeden öğeleri kaldırır, bunları hedef listesine ekler ve yeni birleşik öğeleri artan sırada veya başka bir belirtilen sırayla kümesini sıralar.

```cpp
void merge(list<Type, Allocator>& right);

template <class Traits>
void merge(list<Type, Allocator>& right, Traits comp);
```

### <a name="parameters"></a>Parametreler

*doğru* hedef listenin ile birleştirilecek bağımsız değişken listesi.

*comp* hedef listenin öğelerini sıralamak için kullanılan karşılaştırma işleci.

### <a name="remarks"></a>Açıklamalar

Bağımsız değişken listesi *doğru* hedef listenin ile birleştirilir.

Bağımsız değişken hem de hedef listeleri karşılaştırma aynı ilişki tarafından oluşturulan dizisi sıralanabilmesi olan sıralanmış olmaları gerekmektedir. İlk üye işlevi için varsayılan düzeni, artan. İkinci üye işlevi, kullanıcı tarafından belirtilen karşılaştırma işlemi uygular *comp* sınıfın `Traits`.

### <a name="example"></a>Örnek

```cpp
// list_merge.cpp
// compile with: /EHsc
#include <list>
#include <iostream>

int main( )
{
   using namespace std;
   list <int> c1, c2, c3;
   list <int>::iterator c1_Iter, c2_Iter, c3_Iter;

   c1.push_back( 3 );
   c1.push_back( 6 );
   c2.push_back( 2 );
   c2.push_back( 4 );
   c3.push_back( 5 );
   c3.push_back( 1 );

   cout << "c1 =";
   for ( c1_Iter = c1.begin( ); c1_Iter != c1.end( ); c1_Iter++ )
      cout << " " << *c1_Iter;
   cout << endl;

   cout << "c2 =";
   for ( c2_Iter = c2.begin( ); c2_Iter != c2.end( ); c2_Iter++ )
      cout << " " << *c2_Iter;
   cout << endl;

   c2.merge( c1 );  // Merge c1 into c2 in (default) ascending order
   c2.sort( greater<int>( ) );
   cout << "After merging c1 with c2 and sorting with >: c2 =";
   for ( c2_Iter = c2.begin( ); c2_Iter != c2.end( ); c2_Iter++ )
      cout << " " << *c2_Iter;
   cout << endl;

   cout << "c3 =";
   for ( c3_Iter = c3.begin( ); c3_Iter != c3.end( ); c3_Iter++ )
      cout << " " << *c3_Iter;
   cout << endl;

   c2.merge( c3, greater<int>( ) );
   cout << "After merging c3 with c2 according to the '>' comparison relation: c2 =";
   for ( c2_Iter = c2.begin( ); c2_Iter != c2.end( ); c2_Iter++ )
      cout << " " << *c2_Iter;
   cout << endl;
}
```

```Output
c1 = 3 6
c2 = 2 4
After merging c1 with c2 and sorting with >: c2 = 6 4 3 2
c3 = 5 1
After merging c3 with c2 according to the '>' comparison relation: c2 = 6 5 4 3 2 1
```

## <a name="op_eq"></a>  List::operator =

Listenin öğelerini başka bir liste kopyasıyla değiştirir.

```cpp
list& operator=(const list& right);
list& operator=(list&& right);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|-|-|
|*sağ*|[Listesi](../standard-library/list-class.md) içine kopyalanan `list`.|

### <a name="remarks"></a>Açıklamalar

Var olan tüm öğeleri silme sonra bir `list`, işlecin kopyalar veya içeriğini hareket *doğru* içine `list`.

### <a name="example"></a>Örnek

```cpp
// list_operator_as.cpp
// compile with: /EHsc
#include <list>
#include <iostream>

int main( )
{
   using namespace std;
   list<int> v1, v2, v3;
   list<int>::iterator iter;

   v1.push_back(10);
   v1.push_back(20);
   v1.push_back(30);
   v1.push_back(40);
   v1.push_back(50);

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
   v2 = forward< list<int> >(v1);
   cout << "v2 = ";
   for (iter = v2.begin(); iter != v2.end(); iter++)
      cout << *iter << " ";
   cout << endl;
}
```

## <a name="pointer"></a>  List::pointer

Listedeki bir öğeye bir işaretçi sağlar.

```cpp
typedef typename Allocator::pointer pointer;
```

### <a name="remarks"></a>Açıklamalar

Bir tür `pointer` bir öğenin değerini değiştirmek için kullanılabilir.

Çoğu durumda bir [yineleyici](#iterator) bir liste nesnesindeki öğelere erişmek için kullanılmalıdır.

## <a name="pop_back"></a>  List::pop_back

Bir liste sonundaki öğeyi silin.

```cpp
void pop_back();
```

### <a name="remarks"></a>Açıklamalar

Son öğe boş olmamalıdır. `pop_back` hiçbir zaman bir özel durum oluşturur.

### <a name="example"></a>Örnek

```cpp
// list_pop_back.cpp
// compile with: /EHsc
#include <list>
#include <iostream>

int main( )
{
   using namespace std;
   list <int> c1;

   c1.push_back( 1 );
   c1.push_back( 2 );
   cout << "The first element is: " << c1.front( ) << endl;
   cout << "The last element is: " << c1.back( ) << endl;

   c1.pop_back( );
   cout << "After deleting the element at the end of the list, "
           "the last element is: " << c1.back( ) << endl;
}
```

```Output
The first element is: 1
The last element is: 2
After deleting the element at the end of the list, the last element is: 1
```

## <a name="pop_front"></a>  List::pop_front

Bir liste başındaki öğeyi silin.

```cpp
void pop_front();
```

### <a name="remarks"></a>Açıklamalar

İlk öğe boş olmamalıdır. `pop_front` hiçbir zaman bir özel durum oluşturur.

### <a name="example"></a>Örnek

```cpp
// list_pop_front.cpp
// compile with: /EHsc
#include <list>
#include <iostream>

int main( )
{
   using namespace std;
   list <int> c1;

   c1.push_back( 1 );
   c1.push_back( 2 );
   cout << "The first element is: " << c1.front( ) << endl;
   cout << "The second element is: " << c1.back( ) << endl;

   c1.pop_front( );
   cout << "After deleting the element at the beginning of the list, "
         "the first element is: " << c1.front( ) << endl;
}
```

```Output
The first element is: 1
The second element is: 2
After deleting the element at the beginning of the list, the first element is: 2
```

## <a name="push_back"></a>  List::push_back

Bir öğe listesinin sonuna ekler.

```cpp
void push_back(void push_back(Type&& val);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|-|-|
|*VAL*|Öğe listesinin sonuna eklenir.|

### <a name="remarks"></a>Açıklamalar

Bir özel durum oluşturulursa, listenin bırakılır değiştirilmeden ve özel durum yeniden oluşur.

### <a name="example"></a>Örnek

```cpp
// list_push_back.cpp
// compile with: /EHsc
#include <list>
#include <iostream>
#include <string>

int main( )
{
   using namespace std;
   list <int> c1;

   c1.push_back( 1 );
   if ( c1.size( ) != 0 )
      cout << "Last element: " << c1.back( ) << endl;

   c1.push_back( 2 );
   if ( c1.size( ) != 0 )
      cout << "New last element: " << c1.back( ) << endl;

// move initialize a list of strings
   list <string> c2;
   string str("a");

   c2.push_back( move( str ) );
   cout << "Moved first element: " << c2.back( ) << endl;
}
```

```Output
Last element: 1
New last element: 2
Moved first element: a
```

## <a name="push_front"></a>  List::push_front

Bir listenin başına bir öğe ekler.

```cpp
void push_front(const Type& val);
void push_front(Type&& val);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|-|-|
|*VAL*|Öğesi listenin başına eklenir.|

### <a name="remarks"></a>Açıklamalar

Bir özel durum oluşturulursa, listenin bırakılır değiştirilmeden ve özel durum yeniden oluşur.

### <a name="example"></a>Örnek

```cpp
// list_push_front.cpp
// compile with: /EHsc
#include <list>
#include <iostream>
#include <string>

int main( )
{
   using namespace std;
   list <int> c1;

   c1.push_front( 1 );
   if ( c1.size( ) != 0 )
      cout << "First element: " << c1.front( ) << endl;

   c1.push_front( 2 );
   if ( c1.size( ) != 0 )
      cout << "New first element: " << c1.front( ) << endl;

// move initialize a list of strings
   list <string> c2;
   string str("a");

   c2.push_front( move( str ) );
   cout << "Moved first element: " << c2.front( ) << endl;
}
```

```Output
First element: 1
New first element: 2
Moved first element: a
```

## <a name="rbegin"></a>  List::rbegin

Ters çevrilen bir listedeki ilk öğeyi adresleyen bir yineleyici döndürür.

```cpp
const_reverse_iterator rbegin() const;
reverse_iterator rbegin();
```

### <a name="return-value"></a>Dönüş Değeri

Bir geriye doğru çift yönlü yineleyici ters çevrilen bir listedeki ilk öğeyi ele alan (veya ne ters çevrilmeyen listedeki son öğeyi adresleyen).

### <a name="remarks"></a>Açıklamalar

`rbegin` bir listeyle kullanılır gibi [başlamak](#begin) bir listesiyle kullanılır.

Varsa dönüş değerinin `rbegin` atanan bir `const_reverse_iterator`, liste nesnesi değiştirilemez. Varsa dönüş değerinin `rbegin` atanan bir `reverse_iterator`, liste nesnesi değiştirilebilir.

`rbegin` bir listede geriye doğru gezinmek için kullanılabilir.

### <a name="example"></a>Örnek

```cpp
// list_rbegin.cpp
// compile with: /EHsc
#include <list>
#include <iostream>

int main( )
{
   using namespace std;
   list <int> c1;
   list <int>::iterator c1_Iter;
   list <int>::reverse_iterator c1_rIter;

   // If the following line replaced the line above, *c1_rIter = 40;
   // (below) would be an error
   //list <int>::const_reverse_iterator c1_rIter;

   c1.push_back( 10 );
   c1.push_back( 20 );
   c1.push_back( 30 );
   c1_rIter = c1.rbegin( );
   cout << "The last element in the list is " << *c1_rIter << "." << endl;

   cout << "The list is:";
   for ( c1_Iter = c1.begin( ); c1_Iter != c1.end( ); c1_Iter++ )
      cout << " " << *c1_Iter;
   cout << endl;

   // rbegin can be used to start an iteration through a list in
   // reverse order
   cout << "The reversed list is:";
   for ( c1_rIter = c1.rbegin( ); c1_rIter != c1.rend( ); c1_rIter++ )
      cout << " " << *c1_rIter;
   cout << endl;

   c1_rIter = c1.rbegin( );
 *c1_rIter = 40;
   cout << "The last element in the list is now " << *c1_rIter << "." << endl;
}
```

```Output
The last element in the list is 30.
The list is: 10 20 30
The reversed list is: 30 20 10
The last element in the list is now 40.
```

## <a name="reference"></a>  List::Reference

Bir liste içinde depolanan öğeye başvuru sağlayan bir tür.

```cpp
typedef typename Allocator::reference reference;
```

### <a name="example"></a>Örnek

```cpp
// list_ref.cpp
// compile with: /EHsc
#include <list>
#include <iostream>

int main( )
{
   using namespace std;
   list <int> c1;

   c1.push_back( 10 );
   c1.push_back( 20 );

   int &i = c1.front( );
   int &j = c1.back( );
   cout << "The first element is " << i << endl;
   cout << "The second element is " << j << endl;
}
```

```Output
The first element is 10
The second element is 20
```

## <a name="remove"></a>  List::Remove

Belirtilen bir değerle eşleşen bir listedeki öğeleri siler.

```cpp
void remove(const Type& val);
```

### <a name="parameters"></a>Parametreler

*VAL* değerin, bir öğe tarafından tutulan, o öğenin listeden kaldırılmasıyla sonuçlanır.

### <a name="remarks"></a>Açıklamalar

Kalan öğelerin sırası etkilenmez.

### <a name="example"></a>Örnek

```cpp
// list_remove.cpp
// compile with: /EHsc
#include <list>
#include <iostream>

int main( )
{
   using namespace std;
   list <int> c1;
   list <int>::iterator c1_Iter, c2_Iter;

   c1.push_back( 5 );
   c1.push_back( 100 );
   c1.push_back( 5 );
   c1.push_back( 200 );
   c1.push_back( 5 );
   c1.push_back( 300 );

   cout << "The initial list is c1 =";
   for ( c1_Iter = c1.begin( ); c1_Iter != c1.end( ); c1_Iter++ )
      cout << " " << *c1_Iter;
   cout << endl;

   list <int> c2 = c1;
   c2.remove( 5 );
   cout << "After removing elements with value 5, the list becomes c2 =";
   for ( c2_Iter = c2.begin( ); c2_Iter != c2.end( ); c2_Iter++ )
      cout << " " << *c2_Iter;
   cout << endl;
}
```

```Output
The initial list is c1 = 5 100 5 200 5 300
After removing elements with value 5, the list becomes c2 = 100 200 300
```

## <a name="remove_if"></a>  List::remove_if

Kendisi için belirtilen bir koşul sağlanırsa listeden öğeleri siler.

```cpp
template <class Predicate>
void remove_if(Predicate pred)
```

### <a name="parameters"></a>Parametreler

*Pred* birli koşul, o öğenin listeden silme işlemi, bir öğe tarafından karşılanan sonuçlanır.

### <a name="example"></a>Örnek

```cpp
// list_remove_if.cpp
// compile with: /EHsc
#include <list>
#include <iostream>

template <class T> class is_odd : public std::unary_function<T, bool>
{
public:
   bool operator( ) ( T& val )
   {
   return ( val % 2 ) == 1;
   }
};

int main( )
{
   using namespace std;
   list <int> c1;
   list <int>::iterator c1_Iter, c2_Iter;

   c1.push_back( 3 );
   c1.push_back( 4 );
   c1.push_back( 5 );
   c1.push_back( 6 );
   c1.push_back( 7 );
   c1.push_back( 8 );

   cout << "The initial list is c1 =";
   for ( c1_Iter = c1.begin( ); c1_Iter != c1.end( ); c1_Iter++ )
      cout << " " << *c1_Iter;
   cout << endl;

   list <int> c2 = c1;
   c2.remove_if( is_odd<int>( ) );

   cout << "After removing the odd elements, "
        << "the list becomes c2 =";
   for ( c2_Iter = c2.begin( ); c2_Iter != c2.end( ); c2_Iter++ )
      cout << " " << *c2_Iter;
   cout << endl;
}
```

```Output
The initial list is c1 = 3 4 5 6 7 8
After removing the odd elements, the list becomes c2 = 4 6 8
```

## <a name="rend"></a>  List::rend

Ters çevrilen bir listedeki son öğeyi takip eden konumu adresleyen bir yineleyici döndürür.

```cpp
const_reverse_iterator rend() const;
reverse_iterator rend();
```

### <a name="return-value"></a>Dönüş Değeri

Konumu (çevrilmeyen listedeki ilk öğeyi önce gelen konum) ters çevrilen bir listedeki son öğeyi adresleyen ters iki yönlü yineleyici.

### <a name="remarks"></a>Açıklamalar

`rend` bir listeyle kullanılır gibi [son](#end) bir listesiyle kullanılır.

Varsa dönüş değerinin `rend` atanan bir `const_reverse_iterator`, liste nesnesi değiştirilemez. Varsa dönüş değerinin `rend` atanan bir `reverse_iterator`, liste nesnesi değiştirilebilir.

`rend` olup geriye doğru bir yineleyicinin listesinin sonuna ulaşıp ulaşmadığını test etmek için kullanılabilir.

Tarafından döndürülen değer `rend` kaldırılmamalıdır.

### <a name="example"></a>Örnek

```cpp
// list_rend.cpp
// compile with: /EHsc
#include <list>
#include <iostream>

int main( )
{
   using namespace std;
   list <int> c1;
   list <int>::iterator c1_Iter;
   list <int>::reverse_iterator c1_rIter;

   // If the following line had replaced the line above, an error would
   // have resulted in the line modifying an element (commented below)
   // because the iterator would have been const
   // list <int>::const_reverse_iterator c1_rIter;

   c1.push_back( 10 );
   c1.push_back( 20 );
   c1.push_back( 30 );

   c1_rIter = c1.rend( );
   c1_rIter --;  // Decrementing a reverse iterator moves it forward in
                 // the list (to point to the first element here)
   cout << "The first element in the list is: " << *c1_rIter << endl;

   cout << "The list is:";
   for ( c1_Iter = c1.begin( ); c1_Iter != c1.end( ); c1_Iter++ )
      cout << " " << *c1_Iter;
   cout << endl;

   // rend can be used to test if an iteration is through all of the
   // elements of a reversed list
   cout << "The reversed list is:";
   for ( c1_rIter = c1.rbegin( ); c1_rIter != c1.rend( ); c1_rIter++ )
      cout << " " << *c1_rIter;
   cout << endl;

   c1_rIter = c1.rend( );
   c1_rIter--;  // Decrementing the reverse iterator moves it backward
                // in the reversed list (to the last element here)

*c1_rIter = 40;  // This modification of the last element would have
                    // caused an error if a const_reverse iterator had
                    // been declared (as noted above)

   cout << "The modified reversed list is:";
   for ( c1_rIter = c1.rbegin( ); c1_rIter != c1.rend( ); c1_rIter++ )
      cout << " " << *c1_rIter;
   cout << endl;
}
```

```Output
The first element in the list is: 10
The list is: 10 20 30
The reversed list is: 30 20 10
The modified reversed list is: 30 20 40
```

## <a name="resize"></a>  List::Resize

Bir liste için yeni bir boyut belirtir.

```cpp
void resize(size_type _Newsize);
void resize(size_type _Newsize, Type val);
```

### <a name="parameters"></a>Parametreler

*_Newsize* listenin yeni boyutu.

*VAL* yeni boyutu büyükse, listeye eklenecek yeni öğelerin değeri, özgün boyutu. Değer atlanırsa yeni öğeler sınıfı için varsayılan değer atanır.

### <a name="remarks"></a>Açıklamalar

Listenin boyutu istenen boyuttan daha az ise *_Newsize*, öğeleri boyutuna erişene kadar listeye eklenir.

Listenin boyutu istenen boyuttan daha büyük ise, liste boyutuna erişene kadar listenin sonuna yakın öğeler silinir *_Newsize*.

Listenin mevcut boyutu istenen boyutla aynıysa hiçbir işlem yapılmaz.

[boyutu](#size) listenin geçerli boyutunu yansıtır.

### <a name="example"></a>Örnek

```cpp
// list_resize.cpp
// compile with: /EHsc
#include <list>
#include <iostream>

int main( )
{
   using namespace std;
   list <int> c1;

   c1.push_back( 10 );
   c1.push_back( 20 );
   c1.push_back( 30 );

   c1.resize( 4,40 );
   cout << "The size of c1 is " << c1.size( ) << endl;
   cout << "The value of the last element is " << c1.back( ) << endl;

   c1.resize( 5 );
   cout << "The size of c1 is now " << c1.size( ) << endl;
   cout << "The value of the last element is now " << c1.back( ) << endl;

   c1.resize( 2 );
   cout << "The reduced size of c1 is: " << c1.size( ) << endl;
   cout << "The value of the last element is now " << c1.back( ) << endl;
}
```

```Output
The size of c1 is 4
The value of the last element is 40
The size of c1 is now 5
The value of the last element is now 0
The reduced size of c1 is: 2
The value of the last element is now 20
```

## <a name="reverse"></a>  List::reverse

Öğeleri listede oluşabilen sırasını tersine çevirir.

```cpp
void reverse();
```

### <a name="example"></a>Örnek

```cpp
// list_reverse.cpp
// compile with: /EHsc
#include <list>
#include <iostream>

int main( )
{
   using namespace std;
   list <int> c1;
   list <int>::iterator c1_Iter;

   c1.push_back( 10 );
   c1.push_back( 20 );
   c1.push_back( 30 );

   cout << "c1 =";
   for ( c1_Iter = c1.begin( ); c1_Iter != c1.end( ); c1_Iter++ )
      cout << " " << *c1_Iter;
   cout << endl;

   c1.reverse( );
   cout << "Reversed c1 =";
   for ( c1_Iter = c1.begin( ); c1_Iter != c1.end( ); c1_Iter++ )
      cout << " " << *c1_Iter;
   cout << endl;
}
```

```Output
c1 = 10 20 30
Reversed c1 = 30 20 10
```

## <a name="reverse_iterator"></a>  List::reverse_iterator

Okuyabilen veya değiştirebilen ters çevrilen bir listedeki bir öğe çift yönlü yineleyiciler sağlayan tür.

```cpp
typedef std::reverse_iterator<iterator> reverse_iterator;
```

### <a name="remarks"></a>Açıklamalar

Bir tür `reverse_iterator` ters listesinde yinelemek için kullanılır.

### <a name="example"></a>Örnek

Örneğin bakın [rbegin](#rbegin).

## <a name="size"></a>  List::size

Bir listedeki öğelerin sayısını döndürür.

```cpp
size_type size() const;
```

### <a name="return-value"></a>Dönüş Değeri

Listenin geçerli uzunluğu.

### <a name="example"></a>Örnek

```cpp
// list_size.cpp
// compile with: /EHsc
#include <list>
#include <iostream>

int main( )
{
   using namespace std;
   list <int> c1;
   list <int>::size_type i;

   c1.push_back( 5 );
   i = c1.size( );
   cout << "List length is " << i << "." << endl;

   c1.push_back( 7 );
   i = c1.size( );
   cout << "List length is now " << i << "." << endl;
}
```

```Output
List length is 1.
List length is now 2.
```

## <a name="size_type"></a>  List::size_type

Bir listedeki öğeleri sayar türü.

```cpp
typedef typename Allocator::size_type size_type;
```

### <a name="example"></a>Örnek

Örneğin bakın [boyutu](#size).

## <a name="sort"></a>  List::sort

Öğeleri artan sırada veya başka bir kullanıcı tarafından belirtilen sıraya göre düzenler.

```cpp
void sort();

template <class Traits>
void sort(Traits comp);
```

### <a name="parameters"></a>Parametreler

*comp* ardışık öğeleri sıralamak için kullanılan karşılaştırma işleci.

### <a name="remarks"></a>Açıklamalar

İlk üye işlevi öğeleri varsayılan olarak artan düzende yerleştirir.

Üye şablon işlevi kullanıcı tarafından belirtilen karşılaştırma işlemine göre öğeleri sıralar *comp* sınıfın `Traits`.

### <a name="example"></a>Örnek

```cpp
// list_sort.cpp
// compile with: /EHsc
#include <list>
#include <iostream>

int main( )
{
   using namespace std;
   list <int> c1;
   list <int>::iterator c1_Iter;

   c1.push_back( 20 );
   c1.push_back( 10 );
   c1.push_back( 30 );

   cout << "Before sorting: c1 =";
   for ( c1_Iter = c1.begin( ); c1_Iter != c1.end( ); c1_Iter++ )
      cout << " " << *c1_Iter;
   cout << endl;

   c1.sort( );
   cout << "After sorting c1 =";
   for ( c1_Iter = c1.begin( ); c1_Iter != c1.end( ); c1_Iter++ )
      cout << " " << *c1_Iter;
   cout << endl;

   c1.sort( greater<int>( ) );
   cout << "After sorting with 'greater than' operation, c1 =";
   for ( c1_Iter = c1.begin( ); c1_Iter != c1.end( ); c1_Iter++ )
      cout << " " << *c1_Iter;
   cout << endl;
}
```

```Output
Before sorting: c1 = 20 10 30
After sorting c1 = 10 20 30
After sorting with 'greater than' operation, c1 = 30 20 10
```

## <a name="splice"></a>  List::splice

Bir kaynak listeden öğeleri kaldırır ve bunları bir hedef listesine ekler.

```cpp
// insert the entire source list
void splice(const_iterator Where, list<Type, Allocator>& Source);
void splice(const_iterator Where, list<Type, Allocator>&& Source);

// insert one element of the source list
void splice(const_iterator Where, list<Type, Allocator>& Source, const_iterator Iter);
void splice(const_iterator Where, list<Type, Allocator>&& Source, const_iterator Iter);

// insert a range of elements from the source list
void splice(const_iterator Where, list<Type, Allocator>& Source, const_iterator First, const_iterator Last);
void splice(const_iterator Where, list<Type, Allocator>&& Source, const_iterator First, const_iterator Last);
```

### <a name="parameters"></a>Parametreler

*Burada* eklenecek önce hedef listenin konumu.

*Kaynak* hedef listeye eklenecek olan kaynak listesi.

*Iter* kaynak listeden eklenecek öğe.

*İlk* kaynak listeden eklenecek aralıktaki ilk öğeyi.

*Son* kaynak listeden eklenecek aralıktaki son öğeden ötesindeki ilk konumu.

### <a name="remarks"></a>Açıklamalar

Üye işlevleri ilk çifti tarafından başvurulan konumu önce hedef liste ve kaynak listesinden tüm öğeleri ekler *burada* ve kaynak listesinden tüm öğeleri kaldırır. (`&Source` değil olmalıdır `this`.)

İkinci üye işlevleri çifti tarafından başvurulan öğenin ekler *Iter* önce hedef liste konumu ifade *burada* ve kaldırır *Iter* gelen kaynak listesi. (Varsa `Where == Iter || Where == ++Iter`, herhangi bir değişiklik meydana gelir.)

Üçüncü çift üye işlevleri tarafından belirtilen aralığı ekler [ `First`, `Last`) hedef listedeki bir öğe tarafından başvurulan önce *burada* ve kaynak listesinden öğe aralığını kaldırır. (Varsa `&Source == this`, aralığın `[First, Last)` işaret ettiği öğe içermemelidir *nerede*.)

Ranged splice ekliyorsa `N` öğeleri ve `&Source != this`, sınıfın bir nesnesi [yineleyici](../standard-library/forward-list-class.md#iterator) artırılır `N` kez.

Tüm durumlarda yineleyiciler, spliced öğelerine başvuran başvuruları veya işaretçileri geçerli kalır ve hedef kapsayıcıya aktarılır.

### <a name="example"></a>Örnek

```cpp
// list_splice.cpp
// compile with: /EHsc /W4
#include <list>
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
    list<int> c1{10,11};
    list<int> c2{20,21,22};
    list<int> c3{30,31};
    list<int> c4{40,41,42,43};

    list<int>::iterator where_iter;
    list<int>::iterator first_iter;
    list<int>::iterator last_iter;

    cout << "Beginning state of lists:" << endl;
    cout << "c1 = ";
    print(c1);
    cout << "c2 = ";
    print(c2);
    cout << "c3 = ";
    print(c3);
    cout << "c4 = ";
    print(c4);

    where_iter = c2.begin();
    ++where_iter; // start at second element
    c2.splice(where_iter, c1);
    cout << "After splicing c1 into c2:" << endl;
    cout << "c1 = ";
    print(c1);
    cout << "c2 = ";
    print(c2);

    first_iter = c3.begin();
    c2.splice(where_iter, c3, first_iter);
    cout << "After splicing the first element of c3 into c2:" << endl;
    cout << "c3 = ";
    print(c3);
    cout << "c2 = ";
    print(c2);

    first_iter = c4.begin();
    last_iter = c4.end();
    // set up to get the middle elements
    ++first_iter;
    --last_iter;
    c2.splice(where_iter, c4, first_iter, last_iter);
    cout << "After splicing a range of c4 into c2:" << endl;
    cout << "c4 = ";
    print(c4);
    cout << "c2 = ";
    print(c2);
}

```

```Output
Beginning state of lists:c1 = 2 elements: (10) (11)c2 = 3 elements: (20) (21) (22)c3 = 2 elements: (30) (31)c4 = 4 elements: (40) (41) (42) (43)After splicing c1 into c2:c1 = 0 elements:c2 = 5 elements: (20) (10) (11) (21) (22)After splicing the first element of c3 into c2:c3 = 1 elements: (31)c2 = 6 elements: (20) (10) (11) (30) (21) (22)After splicing a range of c4 into c2:c4 = 2 elements: (40) (43)c2 = 8 elements: (20) (10) (11) (30) (41) (42) (21) (22)
```

## <a name="swap"></a>  List::Swap

İki listenin öğelerini değiştirir.

```cpp
void swap(list<Type, Allocator>& right);
friend void swap(list<Type, Allocator>& left, list<Type, Allocator>& right)
```

### <a name="parameters"></a>Parametreler

*doğru* değiştirilecek öğeleri sağlayan liste veya liste öğeleri listenin öğelerle ilişkili *sol*.

*Sol* öğeleri listenin öğelerle ilişkili bir liste *doğru*.

### <a name="example"></a>Örnek

```cpp
// list_swap.cpp
// compile with: /EHsc
#include <list>
#include <iostream>

int main( )
{
   using namespace std;
   list <int> c1, c2, c3;
   list <int>::iterator c1_Iter;

   c1.push_back( 1 );
   c1.push_back( 2 );
   c1.push_back( 3 );
   c2.push_back( 10 );
   c2.push_back( 20 );
   c3.push_back( 100 );

   cout << "The original list c1 is:";
   for ( c1_Iter = c1.begin( ); c1_Iter != c1.end( ); c1_Iter++ )
      cout << " " << *c1_Iter;
   cout << endl;

   c1.swap( c2 );

   cout << "After swapping with c2, list c1 is:";
   for ( c1_Iter = c1.begin( ); c1_Iter != c1.end( ); c1_Iter++ )
      cout << " " << *c1_Iter;
   cout << endl;

   swap( c1,c3 );

   cout << "After swapping with c3, list c1 is:";
   for ( c1_Iter = c1.begin( ); c1_Iter != c1.end( ); c1_Iter++ )
      cout << " " << *c1_Iter;
   cout << endl;
}
```

```Output
The original list c1 is: 1 2 3
After swapping with c2, list c1 is: 10 20
After swapping with c3, list c1 is: 100
```

## <a name="unique"></a>  List::Unique

Bitişik yinelenen öğeler veya bir listeden bazı diğer ikili koşulu karşılayan bitişik öğeyi kaldırır.

```cpp
void unique();

template <class BinaryPredicate>
void unique(BinaryPredicate pred);
```

### <a name="parameters"></a>Parametreler

*Pred* ardışık öğeleri karşılaştırmak için kullanılan ikili koşul.

### <a name="remarks"></a>Açıklamalar

Tüm yinelenen öğeleri bitişik olacak şekilde bu işlev, listede sıralanan varsayar. Bitişik olmayan çoğaltmaları silinmez.

İlk üye işlevi, önceki öğesine eşit karşılaştıran her öğeyi kaldırır.

İkinci üye işlevi koşul işlevini karşılayan her öğeyi kaldırır *pred* , önceki öğesi ile karşılaştırıldığında. Bildirilen ikili fonksiyon nesnelerden herhangi birini kullanabilirsiniz \<işlevsel > bağımsız değişkeni için üst bilgi *pred* veya kendi oluşturabilirsiniz.

### <a name="example"></a>Örnek

```cpp
// list_unique.cpp
// compile with: /EHsc
#include <list>
#include <iostream>

int main( )
{
   using namespace std;
   list <int> c1;
   list <int>::iterator c1_Iter, c2_Iter,c3_Iter;
   not_equal_to<int> mypred;

   c1.push_back( -10 );
   c1.push_back( 10 );
   c1.push_back( 10 );
   c1.push_back( 20 );
   c1.push_back( 20 );
   c1.push_back( -10 );

   cout << "The initial list is c1 =";
   for ( c1_Iter = c1.begin( ); c1_Iter != c1.end( ); c1_Iter++ )
      cout << " " << *c1_Iter;
   cout << endl;

   list <int> c2 = c1;
   c2.unique( );
   cout << "After removing successive duplicate elements, c2 =";
   for ( c2_Iter = c2.begin( ); c2_Iter != c2.end( ); c2_Iter++ )
      cout << " " << *c2_Iter;
   cout << endl;

   list <int> c3 = c2;
   c3.unique( mypred );
   cout << "After removing successive unequal elements, c3 =";
   for ( c3_Iter = c3.begin( ); c3_Iter != c3.end( ); c3_Iter++ )
      cout << " " << *c3_Iter;
   cout << endl;
}
```

```Output
The initial list is c1 = -10 10 10 20 20 -10
After removing successive duplicate elements, c2 = -10 10 20 -10
After removing successive unequal elements, c3 = -10 -10
```

## <a name="value_type"></a>  List::value_type

Bir liste içinde depolanan veri türünü temsil eden tür.

```cpp
typedef typename Allocator::value_type value_type;
```

### <a name="remarks"></a>Açıklamalar

`value_type` Şablon parametresi için bir eşanlamlı olduğu *türü*.

### <a name="example"></a>Örnek

```cpp
// list_value_type.cpp
// compile with: /EHsc
#include <list>
#include <iostream>

int main( )
{
   using namespace std;
   list<int>::value_type AnInt;
   AnInt = 44;
   cout << AnInt << endl;
}
```

```Output
44
```

## <a name="see-also"></a>Ayrıca bkz.

[\<listesi >](../standard-library/list.md)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)<br/>
