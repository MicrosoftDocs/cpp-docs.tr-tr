---
description: 'Daha fazla bilgi için: List sınıfı'
title: list Sınıfı
ms.date: 11/04/2016
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
ms.openlocfilehash: 9d73c1c61cb7e630ea936685aeaab20f778340ed
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97284843"
---
# <a name="list-class"></a>list Sınıfı

C++ standart kitaplık listesi sınıfı, öğelerini doğrusal bir düzenlemede koruyacak ve dizideki herhangi bir konumda etkili eklemeler ve silmeler sağlayan bir dizi kapsayıcıların sınıf şablonudur. Sıra, her biri bir tür *türünün* üyesini içeren çift yönlü bağlantılı öğelerin bir listesi olarak depolanır.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Type, class Allocator= allocator<Type>>
class list
```

### <a name="parameters"></a>Parametreler

*Türüyle*\
Listede depolanacak öğe veri türü.

*Öğe*\
Listenin bellek ayırmayı ve ayırmayı kaldırma hakkındaki ayrıntıları kapsülleyen saklı ayırıcı nesnesini temsil eden tür. Bu bağımsız değişken isteğe bağlıdır ve varsayılan değerdir `allocator<Type>` .

## <a name="remarks"></a>Açıklamalar

Kapsayıcı türünün seçimi genelde uygulamanın gerektirdiği arama ve ekleme türüne dayalı olmalıdır. Herhangi bir öğeye rastgele erişim bir Premium olduğunda ve öğe eklemeleri veya silinmeleri yalnızca bir sıranın sonunda gerekliyse, vektörlerin yönetilmesi için tercih edilen kapsayıcı olmalıdır. Rastgele erişim gerektiğinde Sınıf deque kapsayıcısının performansı üstün, bir sıranın her ikisinde ve sonundaki ekleme ve silme işlemleri de Premium düzeydir.

Liste üyesi işlevleri [birleştirme](#merge), [ters](#reverse), [benzersiz](#unique), [kaldırma](#remove)ve [remove_if](#remove_if) , liste nesnelerinde işlem için iyileştirildi ve kendi genel ortaklarınıza yüksek performanslı bir alternatif sunmaktadır.

Bir üye işlevin liste öğelerini eklemesi veya silmeli olması gerektiğinde liste yeniden ayırma gerçekleşir. Bu tür durumlarda, yalnızca yineleyiciler veya denetlenen sıranın silinen bölümlerini işaret eden başvurular geçersiz olur.

\<list> [Kapsayıcı](../standard-library/stl-containers.md) sınıfı şablon listesini ve çeşitli destekleyici şablonları tanımlamak Için C++ standart kitaplığı standart üstbilgisini ekleyin.

## <a name="members"></a>Üyeler

### <a name="constructors"></a>Oluşturucular

|Ad|Açıklama|
|-|-|
|[list](#list)|Belirli bir boyutun veya belirli bir değerin veya belirli bir listenin bir kopyasının bir listesini oluşturur `allocator` .|

### <a name="typedefs"></a>Tür tanımları

|Ad|Açıklama|
|-|-|
|[allocator_type](#allocator_type)|`allocator`Bir liste nesnesi için sınıfını temsil eden bir tür.|
|[const_iterator](#const_iterator)|Bir listedeki bir öğeyi okuyabilen çift yönlü bir yineleyici sağlayan bir tür **`const`** .|
|[const_pointer](#const_pointer)|Listedeki bir öğeye işaretçi sağlayan bir tür **`const`** .|
|[const_reference](#const_reference)|**`const`** İşlemleri okumak ve gerçekleştirmek için bir listede depolanan öğeye başvuru sağlayan bir tür **`const`** .|
|[const_reverse_iterator](#const_reverse_iterator)|Bir listedeki herhangi bir öğeyi okuyabilen çift yönlü bir yineleyici sağlayan bir tür **`const`** .|
|[difference_type](#difference_type)|Aynı liste içindeki öğelere başvuran iki yineleyiciler arasındaki farkı sağlayan bir tür.|
|[iden](#iterator)|Bir listedeki herhangi bir öğeyi okuyabilen veya değiştirebilen çift yönlü bir yineleyici sağlayan bir tür.|
|[pointer](#pointer)|Listedeki bir öğeye işaretçi sağlayan bir tür.|
|[başvurunun](#reference)|**`const`** İşlemleri okumak ve gerçekleştirmek için bir listede depolanan öğeye başvuru sağlayan bir tür **`const`** .|
|[reverse_iterator](#reverse_iterator)|Ters çevrilen bir listedeki bir öğeyi okuyabilen veya değiştirebilen çift yönlü bir yineleyici sağlayan bir tür.|
|[size_type](#size_type)|Bir listedeki öğelerin sayısını sayan bir tür.|
|[value_type](#value_type)|Bir listede depolanan veri türünü temsil eden bir tür.|

### <a name="functions"></a>İşlevler

|Ad|Açıklama|
|-|-|
|[assign (atamak)](#assign) |Bir listedeki öğeleri siler ve yeni bir öğe kümesini hedef listeye kopyalar.|
|[Geri](#back)|Listenin son öğesine bir başvuru döndürür.|
|[başladı](#begin)|Listedeki ilk öğeyi adresleyen bir yineleyici döndürür.|
|[cbegin](#cbegin)|Bir listedeki ilk öğeyi adresleyen bir const yineleyici döndürür.|
|[cend](#cend)|Bir listedeki son öğeden sonraki konumu ele alan bir const yineleyici döndürür.|
|[lediğiniz](#clear)|Bir listenin tüm öğelerini siler.|
|[crbegin](#crbegin)|Ters çevrilen bir listedeki ilk öğeyi adresleyen bir const yineleyici döndürür.|
|[crend](#crend)|Ters çevrilen bir listedeki son öğeden sonraki konumu adresleyen bir const yineleyici döndürür.|
|[Emplace](#emplace)|Belirtilen konumdaki bir listeye yerinde oluşturulmuş bir öğe ekler.|
|[emplace_back](#emplace_back)|Bir listenin sonuna yerinde oluşturulmuş bir öğe ekler.|
|[emplace_front](#emplace_front)|Bir listenin başına yerinde oluşturulmuş bir öğe ekler.|
|[empty](#empty)|Bir liste boşsa sınar.|
|[erer](#end)|Bir listedeki son öğeden sonraki konumu ele alan bir yineleyici döndürür.|
|[silme](#erase)|Bir listedeki öğe veya öğe aralığını belirtilen konumlardan kaldırır.|
|[yapılan](#front)|Listedeki ilk öğeye bir başvuru döndürür.|
|[get_allocator](#get_allocator)|`allocator`Bir liste oluşturmak için kullanılan nesnenin bir kopyasını döndürür.|
|[ekleyin](#insert)|Belirtilen konumda bir öğe veya bir dizi öğe veya bir öğe aralığını bir listeye ekler.|
|[max_size](#max_size)|Listenin maksimum uzunluğunu döndürür.|
|[birleþtirmek](#merge)|Bağımsız değişken listesinden öğeleri kaldırır, bunları hedef listeye ekler ve yeni, Birleşik öğe kümesini artan sırada veya belirli bir sıraya göre sıralar.|
|[pop_back](#pop_back)|Listenin sonundaki öğeyi siler.|
|[pop_front](#pop_front)|Listenin başındaki öğeyi siler.|
|[push_back](#push_back)|Listenin sonuna bir öğe ekler.|
|[push_front](#push_front)|Listenin başlangıcına bir öğe ekler.|
|[rbegin](#rbegin)|Ters çevrilen bir listedeki ilk öğeyi adresleyen bir yineleyici döndürür.|
|[temizlenmesine](#remove)|Bir listedeki belirtilen değerle eşleşen öğeleri siler.|
|[remove_if](#remove_if)|Belirtilen koşulun karşılanması için listedeki öğeleri siler.|
|[rend](#rend)|Ters çevrilen bir listedeki son öğeden sonraki konumu ele alan bir yineleyici döndürür.|
|[yeniden boyutlandırma](#resize)|Bir liste için yeni bir boyut belirtir.|
|[tersini](#reverse)|Öğelerin bir listede oluştuğu sırayı tersine çevirir.|
|[boyutla](#size)|Bir listedeki öğe sayısını döndürür.|
|[düzenine](#sort)|Bir listenin öğelerini artan sırada veya diğer bir sıra ilişkisine göre düzenler.|
|[splice](#splice)|Bağımsız değişken listesindeki öğeleri kaldırır ve bunları hedef listeye ekler.|
|[Kur](#swap)|İki listenin öğelerini değiş tokuş eder.|
|[eşi](#unique)|Listedeki diğer bir ikili koşula uyan bitişik yinelenen öğeleri veya bitişik öğeleri kaldırır.|

### <a name="operators"></a>İşleçler

|Ad|Açıklama|
|-|-|
|[işleç =](#op_eq)|Liste öğelerini başka bir listenin kopyasıyla değiştirir.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi**: \<list>

## <a name="allocator_type"></a><a name="allocator_type"></a> allocator_type

Bir liste nesnesi için ayırıcı sınıfını temsil eden bir tür.

```cpp
typedef Allocator allocator_type;
```

### <a name="remarks"></a>Açıklamalar

`allocator_type` , şablon parametre *ayırıcısı* için bir eş anlamlı.

### <a name="example"></a>Örnek

[Get_allocator](#get_allocator)için örneğe bakın.

## <a name="assign"></a><a name="assign"></a> ata

Bir listedeki öğeleri siler ve yeni bir öğe kümesini hedef listeye kopyalar.

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

*Adı*\
Bağımsız değişken listesinden kopyalanacak öğe aralığındaki ilk öğenin konumu.

*Soyadına*\
Bağımsız değişken listesinden kopyalanacak öğe aralığının hemen ötesinde ilk öğenin konumu.

*Biriktirme*\
Listeye eklenmekte olan bir öğenin kopya sayısı.

*Acil*\
Listeye eklenmekte olan öğenin değeri.

*IList*\
Eklenecek öğeleri içeren initializer_list.

### <a name="remarks"></a>Açıklamalar

Hedef listede var olan öğeleri sildikten sonra, atama, özgün listeden belirli bir öğe aralığı ya da başka bir listeden hedef listeye ekler veya belirtilen değerin yeni bir öğesinin kopyalarını hedef listeye ekler

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

## <a name="back"></a><a name="back"></a> Geri

Listenin son öğesine bir başvuru döndürür.

```cpp
reference back();

const_reference back() const;
```

### <a name="return-value"></a>Dönüş Değeri

Listenin son öğesi. Liste boşsa, dönüş değeri tanımsızdır.

### <a name="remarks"></a>Açıklamalar

Dönüş değeri `back` bir öğesine atanırsa `const_reference` , liste nesnesi değiştirilemez. Dönüş değeri `back` bir öğesine atanırsa `reference` , liste nesnesi değiştirilebilir.

1 veya 2 olarak tanımlanan [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md) kullanılarak derlendiğinde, boş bir listedeki bir öğeye erişmeyi denerseniz bir çalışma zamanı hatası oluşur.  Daha fazla bilgi için bkz. [Checked Iterators](../standard-library/checked-iterators.md) .

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

## <a name="begin"></a><a name="begin"></a> başladı

Listedeki ilk öğeyi adresleyen bir yineleyici döndürür.

```cpp
const_iterator begin() const;

iterator begin();
```

### <a name="return-value"></a>Dönüş Değeri

Listedeki ilk öğeyi veya boş bir listeyi izleyen konumu ele alarak çift yönlü bir yineleyici.

### <a name="remarks"></a>Açıklamalar

Dönüş değeri `begin` öğesine atanmışsa `const_iterator` , liste nesnesindeki öğeler değiştirilemez. Dönüş değeri `begin` bir öğesine atanırsa `iterator` , liste nesnesindeki öğeler değiştirilebilir.

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

## <a name="const_iterator"></a><a name="const_iterator"></a> const_iterator

Bir listedeki bir öğeyi okuyabilen çift yönlü bir yineleyici sağlayan bir tür **`const`** .

```cpp
typedef implementation-defined const_iterator;
```

### <a name="remarks"></a>Açıklamalar

Bir tür `const_iterator` , bir öğenin değerini değiştirmek için kullanılamaz.

### <a name="example"></a>Örnek

[Geri](#back)örneğe bakın.

## <a name="const_pointer"></a><a name="const_pointer"></a> const_pointer

Listedeki bir öğe için bir işaretçi sağlar **`const`** .

```cpp
typedef typename Allocator::const_pointer const_pointer;
```

### <a name="remarks"></a>Açıklamalar

Bir tür `const_pointer` , bir öğenin değerini değiştirmek için kullanılamaz.

Çoğu durumda, bir [Yineleyici](#iterator) bir liste nesnesindeki öğelere erişmek için kullanılmalıdır.

## <a name="const_reference"></a><a name="const_reference"></a> const_reference

**`const`** İşlemleri okumak ve gerçekleştirmek için bir listede depolanan öğeye başvuru sağlayan bir tür **`const`** .

```cpp
typedef typename Allocator::const_reference const_reference;
```

### <a name="remarks"></a>Açıklamalar

Bir tür `const_reference` , bir öğenin değerini değiştirmek için kullanılamaz.

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

## <a name="const_reverse_iterator"></a><a name="const_reverse_iterator"></a> const_reverse_iterator

Bir listedeki herhangi bir öğeyi okuyabilen çift yönlü bir yineleyici sağlayan bir tür **`const`** .

```cpp
typedef std::reverse_iterator<const_iterator> const_reverse_iterator;
```

### <a name="remarks"></a>Açıklamalar

Bir tür `const_reverse_iterator` , bir öğenin değerini değiştiremez ve ters içindeki listede yinelemek için kullanılır.

### <a name="example"></a>Örnek

[Rbegin](#rbegin)örneğine bakın.

## <a name="crbegin"></a><a name="crbegin"></a> crbegin

Ters çevrilen bir listedeki ilk öğeyi adresleyen bir const yineleyici döndürür.

```cpp
const_reverse_iterator rbegin() const;
```

### <a name="return-value"></a>Dönüş Değeri

Ters çevrilen bir listedeki ilk öğeyi ele alarak (veya geri çevrilmede son öğe olduğunu adresleyen) bir const ters çift yönlü Yineleyici `list` .

### <a name="remarks"></a>Açıklamalar

`crbegin`[LIST:: Begin](#begin) ile birlikte kullanılan bir ters liste ile kullanılır `list` .

Dönüş değeri ile `crbegin` , liste nesnesi değiştirilemez. [list:: rbegin](#rbegin) , bir listede geriye doğru yinelemek için kullanılabilir.

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

## <a name="crend"></a><a name="crend"></a> crend

Ters çevrilen bir listedeki son öğeden sonraki konumu adresleyen bir const yineleyici döndürür.

```cpp
const_reverse_iterator rend() const;
```

### <a name="return-value"></a>Dönüş Değeri

Ters çevrilen bir [listedeki](../standard-library/list-class.md) son öğeden sonra gelen konumu ele alan bir sabit ters çift yönlü yineleyici (geri çevrilmede ilk öğeden önce gelen konum `list` ).

### <a name="remarks"></a>Açıklamalar

`crend`[list:: End](#end) , ile birlikte kullanılan bir ters liste ile kullanılır `list` .

Dönüş değeri ile `crend` `list` nesne değiştirilemez.

`crend` , geriye doğru bir yineleyicinin sonuna ulaşılıp ulaşılmadığını test etmek için kullanılabilir `list` .

Tarafından döndürülen değer `crend` başvurulmamalıdır.

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

## <a name="difference_type"></a><a name="difference_type"></a> difference_type

Yineleyiciler tarafından gösterilen öğeler arasındaki bir aralıktaki bir listenin öğelerinin sayısını temsil etmek için kullanılabilen işaretli bir tamsayı türü.

```cpp
typedef typename Allocator::difference_type difference_type;
```

### <a name="remarks"></a>Açıklamalar

`difference_type`Kapsayıcının yineleyiciler aracılığıyla çıkartılacak veya artırılarak döndürülen türdür. , `difference_type` Genellikle yineleyiciler arasındaki [,) aralıktaki öğelerin sayısını temsil etmek için kullanılır ve öğesi tarafından işaret edilen öğe `first` `last` `first` `last` `first` ve dahil `last` olmak üzere öğe aralığı ile işaret eder.

`difference_type`Küme gibi ters çevrilebilir kapsayıcılar tarafından desteklenen çift yönlü yineleyicilerin sınıfını içeren bir giriş yineleyicisinin gereksinimlerini karşılayan tüm yineleyiciler için kullanılabilir olsa da, yineleyiciler arasında çıkarma yalnızca, [vektör sınıfı](../standard-library/vector-class.md)gibi bir rastgele erişim kapsayıcısı tarafından sağlanan rastgele erişim yineleyiciler tarafından desteklenir.

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

## <a name="emplace"></a><a name="emplace"></a> Emplace

Belirtilen konumdaki bir listeye yerinde oluşturulmuş bir öğe ekler.

```cpp
void emplace(iterator Where, Type&& val);
```

### <a name="parameters"></a>Parametreler

*Olmadığı*\
Hedef [listedeki](../standard-library/list-class.md) ilk öğenin eklendiği konum.

*Acil*\
Öğesinin sonuna eklenen öğesi `list` .

### <a name="remarks"></a>Açıklamalar

Bir özel durum oluşturulursa, değiştirilmemiş olarak `list` kalır ve özel durum yeniden oluşturulur.

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

## <a name="emplace_back"></a><a name="emplace_back"></a> emplace_back

Bir listenin sonuna yerinde oluşturulmuş bir öğe ekler.

```cpp
void emplace_back(Type&& val);
```

### <a name="parameters"></a>Parametreler

*Acil*\
[Listenin](../standard-library/list-class.md)sonuna eklenen öğe.

### <a name="remarks"></a>Açıklamalar

Bir özel durum oluşturulursa, değiştirilmemiş olarak `list` kalır ve özel durum yeniden oluşturulur.

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

## <a name="emplace_front"></a><a name="emplace_front"></a> emplace_front

Bir listenin başına yerinde oluşturulmuş bir öğe ekler.

```cpp
void emplace_front(Type&& val);
```

### <a name="parameters"></a>Parametreler

*Acil*\
[Listenin](../standard-library/list-class.md)başlangıcına eklenen öğe.

### <a name="remarks"></a>Açıklamalar

Bir özel durum oluşturulursa, değiştirilmemiş olarak `list` kalır ve özel durum yeniden oluşturulur.

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

## <a name="empty"></a><a name="empty"></a> olmamalıdır

Bir liste boşsa sınar.

```cpp
bool empty() const;
```

### <a name="return-value"></a>Dönüş Değeri

**`true`** Liste boşsa; **`false`** liste boş değilse.

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

## <a name="end"></a><a name="end"></a> erer

Bir listedeki son öğeden sonraki konumu ele alan bir yineleyici döndürür.

```cpp
const_iterator end() const;
iterator end();
```

### <a name="return-value"></a>Dönüş Değeri

Bir listedeki son öğeden sonraki konumu ele alan çift yönlü bir yineleyici. Liste boşsa, `list::end == list::begin` .

### <a name="remarks"></a>Açıklamalar

`end` , bir yineleyicinin listenin sonuna ulaşıp ulaşılmadığını test etmek için kullanılır.

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

## <a name="erase"></a><a name="erase"></a> silme

Bir listedeki öğe veya öğe aralığını belirtilen konumlardan kaldırır.

```cpp
iterator erase(iterator Where);
iterator erase(iterator first, iterator last);
```

### <a name="parameters"></a>Parametreler

*Olmadığı*\
Listeden kaldırılacak öğenin konumu.

*adı*\
Listeden kaldırılan ilk öğenin konumu.

*soyadına*\
Listeden kaldırılan son öğenin hemen ötesinde konumlandır.

### <a name="return-value"></a>Dönüş Değeri

Kaldırılan öğelerin dışında kalan ilk öğeyi veya böyle bir öğe yoksa listenin sonuna bir işaretçiyi atayan çift yönlü bir yineleyici.

### <a name="remarks"></a>Açıklamalar

Yeniden ayırma gerçekleşmez, yineleyiciler ve başvurular yalnızca silinen öğeler için geçersiz hale gelir.

`erase` hiçbir koşulda özel durum oluşturmaz.

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

## <a name="front"></a><a name="front"></a> yapılan

Listedeki ilk öğeye bir başvuru döndürür.

```cpp
reference front();
const_reference front() const;
```

### <a name="return-value"></a>Dönüş Değeri

Liste boşsa, dönüş tanımsızdır.

### <a name="remarks"></a>Açıklamalar

Dönüş değeri `front` bir öğesine atanırsa `const_reference` , liste nesnesi değiştirilemez. Dönüş değeri `front` bir öğesine atanırsa `reference` , liste nesnesi değiştirilebilir.

1 veya 2 olarak tanımlanan [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md) kullanılarak derlendiğinde, boş bir listedeki bir öğeye erişmeyi denerseniz bir çalışma zamanı hatası oluşur.  Daha fazla bilgi için bkz. [Checked Iterators](../standard-library/checked-iterators.md) .

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

## <a name="get_allocator"></a><a name="get_allocator"></a> get_allocator

Bir liste oluşturmak için kullanılan ayırıcı nesnesinin bir kopyasını döndürür.

```cpp
Allocator get_allocator() const;
```

### <a name="return-value"></a>Dönüş Değeri

Listenin kullandığı ayırıcı.

### <a name="remarks"></a>Açıklamalar

Liste sınıfı için ayrıcılar, sınıfın depolamayı nasıl yönettiğini belirtir. C++ standart kitaplığı kapsayıcı sınıflarıyla birlikte sağlanan varsayılan ayrıcılar çoğu programlama ihtiyacı için yeterlidir. Kendi ayırıcı sınıfınızı yazmak ve kullanmak, gelişmiş bir C++ konudur.

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

## <a name="insert"></a><a name="insert"></a> ekleyin

Belirtilen konumda bir öğe veya bir dizi öğe veya bir öğe aralığını bir listeye ekler.

```cpp
iterator insert(iterator Where, const Type& Val);
iterator insert(iterator Where, Type&& Val);

void insert(iterator Where, size_type Count, const Type& Val);
iterator insert(iterator Where, initializer_list<Type> IList);

template <class InputIterator>
void insert(iterator Where, InputIterator First, InputIterator Last);
```

### <a name="parameters"></a>Parametreler

*Olmadığı*\
Hedef listedeki ilk öğenin eklendiği konum.

*Acil*\
Listeye eklenmekte olan öğenin değeri.

*Biriktirme*\
Listeye eklenmekte olan öğe sayısı.

*Adı*\
Kopyalanacak bağımsız değişken listesindeki öğe aralığındaki ilk öğenin konumu.

*Soyadına*\
Kopyalamak için bağımsız değişken listesindeki öğe aralığının ötesinde ilk öğenin konumu.

### <a name="return-value"></a>Dönüş Değeri

İlk iki INSERT işlevi, yeni öğenin listeye eklendiği konuma işaret eden bir yineleyici döndürür.

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

## <a name="iterator"></a><a name="iterator"></a> iden

Bir listedeki herhangi bir öğeyi okuyabilen veya değiştirebilen çift yönlü bir yineleyici sağlayan bir tür.

```cpp
typedef implementation-defined iterator;
```

### <a name="remarks"></a>Açıklamalar

Bir türü `iterator` , bir öğenin değerini değiştirmek için kullanılabilir.

### <a name="example"></a>Örnek

[Begin](#begin)örneğine bakın.

## <a name="list"></a><a name="list"></a> Listele

Belirli bir boyutun veya belirli bir değere sahip ya da belirli bir ayırıcıya ya da başka bir listenin tümünün veya bir kısmının bir kopyasının bir listesini oluşturur.

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

*Eşkenar*\
Bu nesneyle kullanılacak kaynak ayırıcı sınıfı.

*Biriktirme*\
Oluşturulan listedeki öğelerin sayısı.

*Acil*\
Listedeki öğelerin değeri.

*Right*\
Oluşturulan listenin bir kopya olduğu liste.

*Adı*\
Kopyalanacak öğe aralığındaki ilk öğenin konumu.

*Soyadına*\
Kopyalanacak öğe aralığının ötesinde ilk öğenin konumu.

*IList*\
Kopyalanacak öğeleri içeren initializer_list.

### <a name="remarks"></a>Açıklamalar

Tüm oluşturucular bir ayırıcı nesnesi (*Al*) depolar ve listeyi başlatır.

[get_allocator](#get_allocator) , bir liste oluşturmak için kullanılan ayırıcı nesnesinin bir kopyasını döndürür.

İlk iki Oluşturucu boş bir başlangıç listesi belirtir, ikincisi kullanılacak ayırıcı türünü (*Al*) belirtir.

Üçüncü Oluşturucu, sınıfının varsayılan değeri için belirtilen sayının (*Count*) bir tekrarını belirtir `Type` .

Dördüncü ve beşinci oluşturucular değer *Val*(*Count*) öğelerinin tekrarlarını belirtir.

Altıncı Oluşturucu, listenin *sağ* bir kopyasını belirtir.

Yedinci Oluşturucu listeyi *sağa* taşımaktır.

Sekizinci Oluşturucu öğeleri belirtmek için bir initializer_list kullanır.

Sonraki iki Oluşturucu bir listenin aralığını kopyalar `[First, Last)` .

Oluşturuculardan hiçbiri geçici realkonum gerçekleştirmez.

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

## <a name="max_size"></a><a name="max_size"></a> max_size

Listenin maksimum uzunluğunu döndürür.

```cpp
size_type max_size() const;
```

### <a name="return-value"></a>Dönüş Değeri

Listenin olası en yüksek uzunluğu.

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

## <a name="merge"></a><a name="merge"></a> birleþtirmek

Bağımsız değişken listesinden öğeleri kaldırır, bunları hedef listeye ekler ve yeni, Birleşik öğe kümesini artan sırada veya belirli bir sıraya göre sıralar.

```cpp
void merge(list<Type, Allocator>& right);

template <class Traits>
void merge(list<Type, Allocator>& right, Traits comp);
```

### <a name="parameters"></a>Parametreler

*Right*\
Hedef listeyle birleştirilecek bağımsız değişken listesi.

*inin*\
Hedef listenin öğelerini sıralamak için kullanılan karşılaştırma işleci.

### <a name="remarks"></a>Açıklamalar

Bağımsız değişken listesi *hakkı* hedef listeyle birleştirilir.

Hem bağımsız değişken hem de hedef listeler, sonuçta elde edilen sıranın sıralanabilmesi için aynı karşılaştırma ilişkisiyle birlikte sıralanmalıdır. İlk üye işlevi için varsayılan sıra artan sıradır. İkinci üye işlevi, sınıfının Kullanıcı tarafından belirtilen *karşılaştırma işlemini uygular* `Traits` .

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

## <a name="operator"></a><a name="op_eq"></a> işleç =

Liste öğelerini başka bir listenin kopyasıyla değiştirir.

```cpp
list& operator=(const list& right);
list& operator=(list&& right);
```

### <a name="parameters"></a>Parametreler

*Right*\
İçine kopyalandığı [liste](../standard-library/list-class.md) `list` .

### <a name="remarks"></a>Açıklamalar

İçindeki var olan öğeleri sildikten sonra `list` , işleç içeriğini kopyalar ya da içine *taşısa* `list` .

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

## <a name="pointer"></a><a name="pointer"></a> çağrısı

Listedeki bir öğe için bir işaretçi sağlar.

```cpp
typedef typename Allocator::pointer pointer;
```

### <a name="remarks"></a>Açıklamalar

Bir türü `pointer` , bir öğenin değerini değiştirmek için kullanılabilir.

Çoğu durumda, bir [Yineleyici](#iterator) bir liste nesnesindeki öğelere erişmek için kullanılmalıdır.

## <a name="pop_back"></a><a name="pop_back"></a> pop_back

Listenin sonundaki öğeyi siler.

```cpp
void pop_back();
```

### <a name="remarks"></a>Açıklamalar

Son öğe boş olmamalıdır. `pop_back` hiçbir koşulda özel durum oluşturmaz.

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

## <a name="pop_front"></a><a name="pop_front"></a> pop_front

Listenin başındaki öğeyi siler.

```cpp
void pop_front();
```

### <a name="remarks"></a>Açıklamalar

İlk öğe boş olmamalıdır. `pop_front` hiçbir koşulda özel durum oluşturmaz.

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

## <a name="push_back"></a><a name="push_back"></a> push_back

Listenin sonuna bir öğe ekler.

```cpp
void push_back(const Type& val);
void push_back(Type&& val);
```

### <a name="parameters"></a>Parametreler

*Acil*\
Listenin sonuna eklenen öğe.

### <a name="remarks"></a>Açıklamalar

Bir özel durum oluşturulursa, liste değiştirilmemiş olarak kalır ve özel durum yeniden oluşturulur.

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

## <a name="push_front"></a><a name="push_front"></a> push_front

Listenin başlangıcına bir öğe ekler.

```cpp
void push_front(const Type& val);
void push_front(Type&& val);
```

### <a name="parameters"></a>Parametreler

*Acil*\
Listenin başlangıcına eklenen öğe.

### <a name="remarks"></a>Açıklamalar

Bir özel durum oluşturulursa, liste değiştirilmemiş olarak kalır ve özel durum yeniden oluşturulur.

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

## <a name="rbegin"></a><a name="rbegin"></a> rbegin

Ters çevrilen bir listedeki ilk öğeyi ele alan bir yineleyici döndürür.

```cpp
const_reverse_iterator rbegin() const;
reverse_iterator rbegin();
```

### <a name="return-value"></a>Dönüş Değeri

Ters çevrilen bir listedeki ilk öğeyi ele alarak ters çift yönlü yineleyici (veya geri çevrilmeyen listedeki son öğe olduğunu adresleme).

### <a name="remarks"></a>Açıklamalar

`rbegin`[Begin](#begin) , bir listeyle birlikte kullanıldığı gibi, ters çevrilmiş bir listeyle kullanılır.

Dönüş değeri `rbegin` bir öğesine atanırsa `const_reverse_iterator` , liste nesnesi değiştirilemez. Dönüş değeri `rbegin` bir öğesine atanırsa `reverse_iterator` , liste nesnesi değiştirilebilir.

`rbegin` bir listede geriye doğru yinelemek için kullanılabilir.

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

## <a name="reference"></a><a name="reference"></a> başvurunun

Listede depolanan bir öğeye başvuru sağlayan bir tür.

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

## <a name="remove"></a><a name="remove"></a> temizlenmesine

Bir listedeki belirtilen değerle eşleşen öğeleri siler.

```cpp
void remove(const Type& val);
```

### <a name="parameters"></a>Parametreler

*Acil*\
Bir öğe tarafından tutuluyorsa, bu öğenin listeden kaldırılmasına neden olur.

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

## <a name="remove_if"></a><a name="remove_if"></a> remove_if

Belirtilen koşulun karşılanmadığı bir listeden öğeleri siler.

```cpp
template <class Predicate>
void remove_if(Predicate pred)
```

### <a name="parameters"></a>Parametreler

*pred*\
Bir öğe tarafından karşılanmadığı birli koşul, bu öğenin listeden silinmesine neden olur.

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

## <a name="rend"></a><a name="rend"></a> rend

Ters çevrilen bir listedeki son öğeyi takip eden konumu ele alan bir yineleyici döndürür.

```cpp
const_reverse_iterator rend() const;
reverse_iterator rend();
```

### <a name="return-value"></a>Dönüş Değeri

Ters çevrilen bir listedeki son öğeden sonra gelen konumu ele alan bir ters çift yönlü yineleyici (geri çevrilmeyen listedeki ilk öğeden önce gelen konum).

### <a name="remarks"></a>Açıklamalar

`rend`[End](#end) bir listeyle kullanıldığı gibi, ters çevrilmiş bir listeyle kullanılır.

Dönüş değeri `rend` bir öğesine atanırsa `const_reverse_iterator` , liste nesnesi değiştirilemez. Dönüş değeri `rend` bir öğesine atanırsa `reverse_iterator` , liste nesnesi değiştirilebilir.

`rend` geriye doğru bir yineleyicinin listenin sonuna ulaşıp ulaşılmadığını test etmek için kullanılabilir.

Tarafından döndürülen değer `rend` başvurulmamalıdır.

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

## <a name="resize"></a><a name="resize"></a> yeniden boyutlandırma

Bir liste için yeni bir boyut belirtir.

```cpp
void resize(size_type _Newsize);
void resize(size_type _Newsize, Type val);
```

### <a name="parameters"></a>Parametreler

*_Newsize*\
Listenin yeni boyutu.

*Acil*\
Yeni boyut orijinal boyuttan daha büyükse listeye eklenecek yeni öğelerin değeri. Değer atlanırsa, yeni öğelere sınıfı için varsayılan değer atanır.

### <a name="remarks"></a>Açıklamalar

Listenin boyutu istenen boyuttan daha küçükse *_Newsize*, öğeler istenen boyuta ulaşıncaya kadar listeye eklenir.

Listenin boyutu istenen boyuttan daha büyükse, listenin sonuna en yakın olan öğeler, liste *_Newsize* boyutuna ulaşıncaya kadar silinir.

Listenin mevcut boyutu istenen boyutla aynı ise, herhangi bir eylem yapılmaz.

[Boyut](#size) , listenin geçerli boyutunu yansıtır.

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

## <a name="reverse"></a><a name="reverse"></a> tersini

Öğelerin bir listede oluştuğu sırayı tersine çevirir.

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

## <a name="reverse_iterator"></a><a name="reverse_iterator"></a> reverse_iterator

Ters çevrilen bir listedeki bir öğeyi okuyabilen veya değiştirebilen çift yönlü bir yineleyici sağlayan bir tür.

```cpp
typedef std::reverse_iterator<iterator> reverse_iterator;
```

### <a name="remarks"></a>Açıklamalar

Bir tür, `reverse_iterator` geriye doğru listede yinelemek için kullanılır.

### <a name="example"></a>Örnek

[Rbegin](#rbegin)örneğine bakın.

## <a name="size"></a><a name="size"></a> boyutla

Bir listedeki öğe sayısını döndürür.

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

## <a name="size_type"></a><a name="size_type"></a> size_type

Bir listedeki öğelerin sayısını sayan bir tür.

```cpp
typedef typename Allocator::size_type size_type;
```

### <a name="example"></a>Örnek

[Boyut](#size)örneğine bakın.

## <a name="sort"></a><a name="sort"></a> düzenine

Bir listenin öğelerini artan sırada veya Kullanıcı tarafından belirtilen başka bir sıraya göre düzenler.

```cpp
void sort();

template <class Traits>
    void sort(Traits comp);
```

### <a name="parameters"></a>Parametreler

*inin*\
Birbirini izleyen öğeleri sıralamak için kullanılan karşılaştırma işleci.

### <a name="remarks"></a>Açıklamalar

İlk üye işlevi, varsayılan olarak öğeleri artan sırada koyar.

Üye şablonu işlevi, öğeleri Kullanıcı tarafından belirtilen *karşılaştırma işlemi sınıfına* göre sıralar `Traits` .

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

## <a name="splice"></a><a name="splice"></a> splice

Bir kaynak listesinden öğeleri kaldırır ve bunları bir hedef listesine ekler.

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

*Olmadığı*\
Eklenecek hedef listedeki konum.

*Kaynaktaki*\
Hedef listesine eklenecek kaynak listesi.

*Pi*\
Kaynak listesinden eklenecek öğe.

*Adı*\
Kaynak listesinden eklenecek aralıktaki ilk öğe.

*Soyadına*\
Kaynak listesinden eklenecek aralıktaki son öğenin ötesinde ilk konum.

### <a name="remarks"></a>Açıklamalar

İlk üye işlevi çifti, kaynak listedeki tüm öğeleri, *konum tarafından başvurulan* konumdan önce hedef listeye ekler ve tüm öğeleri kaynak listesinden kaldırır. ( `&Source` eşit olmamalı **`this`** .)

Üye işlevlerinin ikinci çifti, hedef listedeki *konumdan önce, konum tarafından başvurulan* *ve kaynak* listeden *iter* 'yi kaldıran bir öğe ekler. (Varsa `Where == Iter || Where == ++Iter` , hiçbir değişiklik gerçekleşmez.)

Üçüncü üye işlevi çifti, [,) tarafından belirlenen aralığı, `First` `Last` hedef listedeki öğeden önce gelen ve kaynak listedeki öğe aralığını kaldıran bir *yere* ekler. (IF ise `&Source == this` , Aralık `[First, Last)` tarafından işaret edilen öğeyi içermemelidir.) 

Ranşlı splice `N` öğeleri ekler ve `&Source != this` sınıf [Yineleyici](../standard-library/forward-list-class.md#iterator) bir nesne artırılır `N` .

Her durumda yineleyiciler, işaretçiler veya vliced öğelerine başvuran başvurular geçerli kalır ve hedef kapsayıcıya aktarılır.

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

## <a name="swap"></a><a name="swap"></a> Kur

İki listenin öğelerini değiş tokuş eder.

```cpp
void swap(list<Type, Allocator>& right);
friend void swap(list<Type, Allocator>& left, list<Type, Allocator>& right)
```

### <a name="parameters"></a>Parametreler

*Right*\
Değiştirilecek öğeleri *sağlayan liste veya* öğeleri listedeki değişikliklerle değiştirilecek olan liste.

*tarafta*\
Öğeleri liste *hakkı* ile değiş tokuş edilecek olan bir liste.

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

## <a name="unique"></a><a name="unique"></a> eşi

Bir listeden diğer bir ikili koşula uyan bitişik yinelenen öğeleri veya bitişik öğeleri kaldırır.

```cpp
void unique();

template <class BinaryPredicate>
void unique(BinaryPredicate pred);
```

### <a name="parameters"></a>Parametreler

*pred*\
Birbirini izleyen öğeleri karşılaştırmak için kullanılan ikili koşul.

### <a name="remarks"></a>Açıklamalar

Bu işlev, tüm yinelenen öğelerin bitişik olması için listenin sıralandığı varsayılır. Bitişik olmayan yinelemeler silinmeyecektir.

İlk üye işlevi, önceki öğesiyle eşit olarak karşılaştırıldığı her öğeyi kaldırır.

İkinci üye işlevi, önceki öğesiyle karşılaştırıldığı zaman *Pred* koşul işlevini karşılayan her öğeyi kaldırır. \<functional> *Pred* bağımsız değişkeni için üst bilgide tanımlanmış herhangi bir ikili işlev nesnesinden herhangi birini kullanabilir veya kendi kendinize oluşturabilirsiniz.

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

## <a name="value_type"></a><a name="value_type"></a> value_type

Bir listede depolanan veri türünü temsil eden bir tür.

```cpp
typedef typename Allocator::value_type value_type;
```

### <a name="remarks"></a>Açıklamalar

`value_type` şablon parametre *türü* için bir eş anlamlı.

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
