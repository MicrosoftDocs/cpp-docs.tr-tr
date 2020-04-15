---
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
ms.openlocfilehash: 7e30583a185a46e5e0f0544ac2b00848dc989f26
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81377320"
---
# <a name="list-class"></a>list Sınıfı

C++ Standart Kitaplık listesi sınıfı, öğelerini doğrusal bir düzenlemede koruyan ve dizi içindeki herhangi bir konumda verimli eklemelere ve silmelere izin veren sıra kapsayıcılarından oluşan bir sınıf şablonudur. Dizi, her biri belirli tür *türünden*bir üye içeren çift yönlü bağlantılı öğeler listesi olarak depolanır.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Type, class Allocator= allocator<Type>>
class list
```

### <a name="parameters"></a>Parametreler

*Türü*\
Listede depolanacak öğe veri türü.

*Ayırıcı*\
Listeayırma ve bellek deallocation hakkında ayrıntıları kapsülleyen depolanan ayırıcı nesneyi temsil eden türü. Bu bağımsız değişken isteğe bağlıdır ve varsayılan değer **ayırıcı**\<*Türü*>.

## <a name="remarks"></a>Açıklamalar

Kapsayıcı türünün seçimi genelde uygulamanın gerektirdiği arama ve ekleme türüne dayalı olmalıdır. Vektörler, herhangi bir öğeye rasgele erişim bir prim olduğunda bir dizi yönetmek için tercih edilen kapsayıcı olmalı ve öğelerin eklemeleri veya silmeleri yalnızca bir dizinin sonunda gereklidir. Rasgele erişim gerektiğinde sınıf deque kapsayıcının performansı üstündür ve bir dizinin hem başında hem de sonunda eklemeler ve silmeler bir prim vardır.

Liste üye işlevleri [birleştirme](#merge), [ters](#reverse), [benzersiz](#unique), [kaldırmak](#remove), ve [remove_if](#remove_if) liste nesneleri üzerinde işlem için optimize edilmiş ve genel muadilleri için yüksek performanslı bir alternatif sunuyoruz.

Liste yeniden tahsisi, bir üye işlevin listenin öğelerini eklemesi veya silmesi gerektiğinde oluşur. Tüm bu gibi durumlarda, yalnızca yineleyiciler veya denetlenmiş sıranın silinmiş bölümlerini işaret eden başvurular geçersiz olur.

\< [Kapsayıcı](../standard-library/stl-containers.md) sınıfı şablon listesini ve birkaç destekleyici şablonu tanımlamak için> C++ Standart Kitaplık standart üstbilgi listesini ekleyin.

## <a name="members"></a>Üyeler

### <a name="constructors"></a>Oluşturucular

|||
|-|-|
|[list](#list)|Belirli bir boyutun veya belirli bir değerin öğeleriyle `allocator` veya belirli bir veya başka bir listenin kopyası olarak bir liste oluşur.|

### <a name="typedefs"></a>Tür tanımları

|||
|-|-|
|[Allocator_type](#allocator_type)|Liste nesnesi `allocator` için sınıfı temsil eden bir tür.|
|[const_iterator](#const_iterator)|Bir listedeki **const** öğeyi okuyabilen çift yönlü bir yineleme sağlayan bir tür.|
|[Const_pointer](#const_pointer)|Bir listedeki **const** öğesine işaretçi sağlayan bir tür.|
|[const_reference](#const_reference)|**Const** işlemleri okumak ve gerçekleştirmek için listede depolanan **bir const** öğesine başvuru sağlayan bir tür.|
|[Const_reverse_iterator](#const_reverse_iterator)|Bir listedeki herhangi bir **const** öğeyi okuyabilen çift yönlü bir yineleme sağlayan bir tür.|
|[difference_type](#difference_type)|Aynı liste içindeki öğelere başvuran iki yineleyici arasındaki farkı sağlayan bir tür.|
|[Yineleyici](#iterator)|Bir listedeki herhangi bir öğeyi okuyabilen veya değiştirebilen çift yönlü bir yineleme sağlayan bir tür.|
|[pointer](#pointer)|Listedeki bir öğeye işaretçi sağlayan bir tür.|
|[Başvuru](#reference)|**Const** işlemleri okumak ve gerçekleştirmek için listede depolanan **bir const** öğesine başvuru sağlayan bir tür.|
|[Reverse_iterator](#reverse_iterator)|Ters bir listedeki bir öğeyi okuyabilen veya değiştirebilen çift yönlü bir yineleme sağlayan bir tür.|
|[size_type](#size_type)|Listedeki öğe sayısını sayan bir tür.|
|[value_type](#value_type)|Listede depolanan veri türünü temsil eden bir tür.|

### <a name="functions"></a>İşlevler

|||
|-|-|
|[Atamak](#assign)|Öğeleri bir listeden siler ve hedef listeye yeni bir öğe kümesi kopyalar.|
|[Geri](#back)|Listenin son öğesine başvuru verir.|
|[Başlamak](#begin)|Listedeki ilk öğeyi ele alan bir yineleyici döndürür.|
|[cbegin](#cbegin)|Bir listedeki ilk öğeyi ele alan bir const yineleyici döndürür.|
|[cend](#cend)|Bir listedeki son öğeyi yerine getiren konumu gideren bir const yineleyici döndürür.|
|[Temizleyin](#clear)|Listenin tüm öğelerini siler.|
|[crbegin](#crbegin)|Ters bir listedeki ilk öğeyi ele alan bir const yineleyici döndürür.|
|[crend](#crend)|Ters bir listedeki son öğeyi yerine getiren konumu gideren bir const yineleyici döndürür.|
|[emplace](#emplace)|Yerinde oluşturulmuş bir öğeyi belirli bir konumda ki listeye ekler.|
|[emplace_back](#emplace_back)|Bir listenin sonuna yerinde oluşturulmuş bir öğe ekler.|
|[emplace_front](#emplace_front)|Bir listenin başına yerinde oluşturulmuş bir öğe ekler.|
|[empty](#empty)|Bir liste boşsa sınar.|
|[Son -unda](#end)|Bir listedeki son öğeyi yerine getiren konumu adresleyen bir yineleyici döndürür.|
|[Silmek](#erase)|Bir listedeki bir öğeyi veya dizi öğeyi belirtilen konumlardan kaldırır.|
|[Ön](#front)|Bir listedeki ilk öğeye başvuru verir.|
|[Get_allocator](#get_allocator)|Liste oluşturmak için `allocator` kullanılan nesnenin bir kopyasını döndürür.|
|[Ekle](#insert)|Belirli bir konumda bir listeye bir öğe veya bir dizi öğe veya öğe aralığı ekler.|
|[max_size](#max_size)|Listenin en uzunluğunu verir.|
|[Birleştirme](#merge)|Öğeleri bağımsız değişken listesinden kaldırır, hedef listesine ekler ve artan sırada veya başka bir belirtilen sırada yeni, birleştirilmiş öğeler kümesini sıralar.|
|[pop_back](#pop_back)|Listenin sonundaki öğeyi siler.|
|[pop_front](#pop_front)|Listenin başındaki öğeyi siler.|
|[push_back](#push_back)|Listenin sonuna bir öğe ekler.|
|[push_front](#push_front)|Listenin başına bir öğe ekler.|
|[rbegin](#rbegin)|Ters bir listedeki ilk öğeyi ele alan bir yineleyici döndürür.|
|[remove](#remove)|Belirli bir değerle eşleşen bir listedeki öğeleri siler.|
|[remove_if](#remove_if)|Belirli bir yüklemin karşılandığı listeden öğeleri siler.|
|[Rend](#rend)|Ters bir listedeki son öğeyi yerine getiren konumu adresleyen bir yineleyici döndürür.|
|[Yeni -den boyutlandırmak](#resize)|Bir liste için yeni bir boyut belirtir.|
|[Ters](#reverse)|Öğelerin bir listede oluşma sırasını tersine çevirir.|
|[Boyutu](#size)|Listedeki öğe sayısını döndürür.|
|[Sıralama](#sort)|Bir listenin öğelerini artan sırada veya başka bir sipariş ilişkisiyle ilgili olarak düzenler.|
|[Splice](#splice)|Öğeleri bağımsız değişken listesinden kaldırır ve hedef listeye ekler.|
|[Takas](#swap)|İki liste öğelerini değiştirir.|
|[Benzer -siz](#unique)|Diğer bazı ikili yüklemi listeden karşılayan bitişik yinelenen öğeleri veya bitişik öğeleri kaldırır.|

### <a name="operators"></a>İşleçler

|||
|-|-|
|[işleç=](#op_eq)|Listenin öğelerini başka bir listenin kopyasıyla değiştirir.|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi** \<: liste>

## <a name="allocator_type"></a><a name="allocator_type"></a>Allocator_type

Liste nesnesi için ayırıcı sınıfı temsil eden bir tür.

```cpp
typedef Allocator allocator_type;
```

### <a name="remarks"></a>Açıklamalar

`allocator_type`şablon parametre *Ayırıcısı*ile eş anlamlıdır.

### <a name="example"></a>Örnek

[get_allocator](#get_allocator)için örneğe bakın.

## <a name="assign"></a><a name="assign"></a>Atamak

Öğeleri bir listeden siler ve yeni bir öğe kümesini hedef listeye kopyalar.

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

*Ilk*\
Bağımsız değişken listesinden kopyalanacak öğeler aralığındaki ilk öğenin konumu.

*Son*\
İlk öğenin bağımsız değişken listesinden kopyalanacak öğelerin hemen ötesindeki konumu.

*Sayısı*\
Listeye eklenen bir öğenin kopya sayısı.

*Val*\
Listeye eklenen öğenin değeri.

*ılist*\
Eklenecek öğeleri içeren initializer_list.

### <a name="remarks"></a>Açıklamalar

Hedef listedeki varolan öğeleri siler sonra, özgün listeden veya başka bir listeden hedef listeye belirli bir öğe aralığı ekler veya hedef listeye belirli bir değerin yeni bir öğesinin kopyalarını ekler

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

## <a name="back"></a><a name="back"></a>Geri

Listenin son öğesine başvuru verir.

```cpp
reference back();

const_reference back() const;
```

### <a name="return-value"></a>Dönüş Değeri

Listenin son öğesi. Liste boşsa, iade değeri tanımsız.

### <a name="remarks"></a>Açıklamalar

Bir `const_reference`, liste `back` nesnesi için return value atanırsa değiştirilemez. Bir `reference`, liste `back` nesnesi için return value atanır.

1 veya 2 olarak tanımlanan [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md) kullanılarak derlendiğinde, boş bir listedeki bir öğeye erişmeye çalışırsanız çalışma zamanı hatası oluşur.  Daha fazla bilgi için [Kontrol Edilmiş Yinelemeciler'e](../standard-library/checked-iterators.md) bakın.

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

## <a name="begin"></a><a name="begin"></a>Başlamak

Listedeki ilk öğeyi ele alan bir yineleyici döndürür.

```cpp
const_iterator begin() const;

iterator begin();
```

### <a name="return-value"></a>Dönüş Değeri

Listedeki ilk öğeyi veya boş bir listeyi başaran konuma hitap eden çift yönlü bir yineleyici.

### <a name="remarks"></a>Açıklamalar

Bir `begin` `const_iterator`, liste nesnesindeki öğelere atanmışsa değiştirilemez. Bir `begin` `iterator`, liste nesnesindeki öğelere atanmışsa değiştirilebilir.

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

## <a name="cbegin"></a><a name="cbegin"></a>cbegin

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

## <a name="cend"></a><a name="cend"></a>cend

Bir `const` aralıktaki son öğenin hemen ötesinde konuma hitap eden bir yineleyici döndürür.

```cpp
const_iterator cend() const;
```

### <a name="return-value"></a>Dönüş Değeri

Aralığın `const` sonundan hemen ötesine işaret eden çift yönlü erişim yineleyicisi.

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

## <a name="clear"></a><a name="clear"></a>Temizleyin

Listenin tüm öğelerini siler.

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

## <a name="const_iterator"></a><a name="const_iterator"></a>Const_iterator

Bir listedeki **const** öğeyi okuyabilen çift yönlü bir yineleme sağlayan bir tür.

```cpp
typedef implementation-defined const_iterator;
```

### <a name="remarks"></a>Açıklamalar

Bir `const_iterator` tür, bir öğenin değerini değiştirmek için kullanılamaz.

### <a name="example"></a>Örnek

[Geri](#back)için örneğe bakın.

## <a name="const_pointer"></a><a name="const_pointer"></a>Const_pointer

Bir listedeki **const** öğesine işaretçi sağlar.

```cpp
typedef typename Allocator::const_pointer const_pointer;
```

### <a name="remarks"></a>Açıklamalar

Bir `const_pointer` tür, bir öğenin değerini değiştirmek için kullanılamaz.

Çoğu durumda, bir [yineleyici](#iterator) bir liste nesnesindeki öğelere erişmek için kullanılmalıdır.

## <a name="const_reference"></a><a name="const_reference"></a>Const_reference

**Const** işlemleri okumak ve gerçekleştirmek için listede depolanan **bir const** öğesine başvuru sağlayan bir tür.

```cpp
typedef typename Allocator::const_reference const_reference;
```

### <a name="remarks"></a>Açıklamalar

Bir `const_reference` tür, bir öğenin değerini değiştirmek için kullanılamaz.

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

## <a name="const_reverse_iterator"></a><a name="const_reverse_iterator"></a>Const_reverse_iterator

Bir listedeki herhangi bir **const** öğeyi okuyabilen çift yönlü bir yineleme sağlayan bir tür.

```cpp
typedef std::reverse_iterator<const_iterator> const_reverse_iterator;
```

### <a name="remarks"></a>Açıklamalar

Bir `const_reverse_iterator` tür bir öğenin değerini değiştiremez ve liste yi ters teslesile getirmek için kullanılır.

### <a name="example"></a>Örnek

[rbegin](#rbegin)için örneğe bakın.

## <a name="crbegin"></a><a name="crbegin"></a>crbegin

Ters bir listedeki ilk öğeyi ele alan bir const yineleyici döndürür.

```cpp
const_reverse_iterator rbegin() const;
```

### <a name="return-value"></a>Dönüş Değeri

Ters bir listedeki ilk öğeyi ele alan (veya tersine çevrilmemiş `list`son öğeyi ele alan) const ters yönlü bir yineleme.

### <a name="remarks"></a>Açıklamalar

`crbegin`liste gibi ters bir liste ile [kullanılır::begin](#begin) ile kullanılır . `list`

İade değeri ile `crbegin`liste nesnesi değiştirilemez. [liste::rbegin](#rbegin) bir liste geriye doğru doğrulamak için kullanılabilir.

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

## <a name="crend"></a><a name="crend"></a>crend

Ters bir listedeki son öğeyi yerine getiren konumu gideren bir const yineleyici döndürür.

```cpp
const_reverse_iterator rend() const;
```

### <a name="return-value"></a>Dönüş Değeri

Ters bir [listedeki](../standard-library/list-class.md) son öğeyi başaran konumu gideren bir const ters çift yönlü yineleme (ters çevrilmemiş `list`ilk öğeden önce gelen konum).

### <a name="remarks"></a>Açıklamalar

`crend`liste gibi ters bir liste ile [kullanılır::end](#end) ile kullanılır . `list`

İade değeri ile `crend` `list` nesne değiştirilemez.

`crend`ters yineleyicinin sonuna ulaşıp ulaşmadığını test etmek için `list`kullanılabilir.

Döndürülen `crend` değer dereferenced olmamalıdır.

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

## <a name="difference_type"></a><a name="difference_type"></a>difference_type

Yineleyiciler tarafından işaret edilen öğeler arasındaki aralıktaki bir liste öğesi sayısını temsil etmek için kullanılabilecek imzalı bir tamsayı türü.

```cpp
typedef typename Allocator::difference_type difference_type;
```

### <a name="remarks"></a>Açıklamalar

Kapsayıcının `difference_type` yineleyicileri arasından çıkarılırken veya artarken döndürülen türdür. Genellikle `difference_type` yinelemeciler `first` arasındaki aralıktaki öğe sayısını temsil `first` `last`etmek için kullanılır [ `last`, ) ve `first` , tarafından işaret edilen öğe ve elemanların aralığı kadar, ancak dahil değil, öğe tarafından `last`işaret .

Küme gibi `difference_type` geri döndürülebilir kapsayıcılar tarafından desteklenen çift yönlü yineleyiciler sınıfını içeren bir giriş yineleyicisinin gereksinimlerini karşılayan tüm yineleyiciler için kullanılabilir olmasına rağmen, yineleyiciler arasındaki çıkarma nın yalnızca [vektör sınıfı](../standard-library/vector-class.md)gibi rasgele erişimli bir kapsayıcı tarafından sağlanan rasgele erişim yinelemeleri tarafından desteklendiğine dikkat edin.

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

## <a name="emplace"></a><a name="emplace"></a>emplace

Yerinde oluşturulmuş bir öğeyi belirli bir konumda ki listeye ekler.

```cpp
void emplace(iterator Where, Type&& val);
```

### <a name="parameters"></a>Parametreler

*Nerede*\
İlk öğenin eklendiği hedef [listesindeki](../standard-library/list-class.md) konum.

*Val*\
Sonuna eklenen `list`öğe.

### <a name="remarks"></a>Açıklamalar

Bir özel durum atılırsa, `list` değiştirilmeden bırakılır ve özel durum yeniden atılır.

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

## <a name="emplace_back"></a><a name="emplace_back"></a>emplace_back

Bir listenin sonuna yerinde oluşturulmuş bir öğe ekler.

```cpp
void emplace_back(Type&& val);
```

### <a name="parameters"></a>Parametreler

*Val*\
[Listenin](../standard-library/list-class.md)sonuna eklenen öğe.

### <a name="remarks"></a>Açıklamalar

Bir özel durum atılırsa, `list` değiştirilmeden bırakılır ve özel durum yeniden atılır.

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

## <a name="emplace_front"></a><a name="emplace_front"></a>emplace_front

Bir listenin başına yerinde oluşturulmuş bir öğe ekler.

```cpp
void emplace_front(Type&& val);
```

### <a name="parameters"></a>Parametreler

*Val*\
Öğe nin başına [eklenen.](../standard-library/list-class.md)

### <a name="remarks"></a>Açıklamalar

Bir özel durum atılırsa, `list` değiştirilmeden bırakılır ve özel durum yeniden atılır.

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

## <a name="empty"></a><a name="empty"></a>Boş

Bir liste boşsa sınar.

```cpp
bool empty() const;
```

### <a name="return-value"></a>Dönüş Değeri

liste boşsa **doğrudur;** liste boş değilse **false.**

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

## <a name="end"></a><a name="end"></a>Son -unda

Bir listedeki son öğeyi yerine getiren konumu adresleyen bir yineleyici döndürür.

```cpp
const_iterator end() const;
iterator end();
```

### <a name="return-value"></a>Dönüş Değeri

Bir listedeki son öğeyi yerine getiren konumu gideren çift yönlü bir yineleyici. Liste boşsa, `list::end == list::begin`o zaman.

### <a name="remarks"></a>Açıklamalar

`end`bir yineleyicinin listenin sonuna ulaşıp ulaşmadığını test etmek için kullanılır.

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

## <a name="erase"></a><a name="erase"></a>Silmek

Bir listedeki bir öğeyi veya dizi öğeyi belirtilen konumlardan kaldırır.

```cpp
iterator erase(iterator Where);
iterator erase(iterator first, iterator last);
```

### <a name="parameters"></a>Parametreler

*Nerede*\
Öğenin listeden kaldırılacak konumu.

*Ilk*\
Listeden kaldırılan ilk öğenin konumu.

*Son*\
Listeden kaldırılan son öğenin hemen ötesine yerleştirin.

### <a name="return-value"></a>Dönüş Değeri

Kaldırılan öğelerin ötesinde kalan ilk öğeyi belirleyen çift yönlü bir yineleyici veya böyle bir öğe yoksa listenin sonuna işaretçi.

### <a name="remarks"></a>Açıklamalar

Yeniden ayırma oluşmaz, bu nedenle yineleyiciler ve başvurular yalnızca silinen öğeler için geçersiz hale gelir.

`erase`asla bir istisna atmaz.

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

## <a name="front"></a><a name="front"></a>Ön

Bir listedeki ilk öğeye başvuru verir.

```cpp
reference front();
const_reference front() const;
```

### <a name="return-value"></a>Dönüş Değeri

Liste boşsa, iade tanımsız.

### <a name="remarks"></a>Açıklamalar

Bir `const_reference`, liste `front` nesnesi için return value atanırsa değiştirilemez. Bir `reference`, liste `front` nesnesi için return value atanır.

1 veya 2 olarak tanımlanan [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md) kullanılarak derlendiğinde, boş bir listedeki bir öğeye erişmeye çalışırsanız çalışma zamanı hatası oluşur.  Daha fazla bilgi için [Kontrol Edilmiş Yinelemeciler'e](../standard-library/checked-iterators.md) bakın.

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

## <a name="get_allocator"></a><a name="get_allocator"></a>Get_allocator

Bir liste oluşturmak için kullanılan ayırıcı nesnenin bir kopyasını döndürür.

```cpp
Allocator get_allocator() const;
```

### <a name="return-value"></a>Dönüş Değeri

Liste tarafından kullanılan ayırıcı.

### <a name="remarks"></a>Açıklamalar

Liste sınıfının ayırıcıları sınıfın depolamayı nasıl yönettiğini belirtir. C++ Standart Kitaplık kapsayıcı sınıfları ile birlikte verilen varsayılan ayırıcılar çoğu programlama gereksinimleri için yeterlidir. Kendi ayırıcı sınıfınızı yazmak ve kullanmak gelişmiş bir C++ konusudur.

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

## <a name="insert"></a><a name="insert"></a>Ekle

Belirli bir konumda bir listeye bir öğe veya bir dizi öğe veya öğe aralığı ekler.

```cpp
iterator insert(iterator Where, const Type& Val);
iterator insert(iterator Where, Type&& Val);

void insert(iterator Where, size_type Count, const Type& Val);
iterator insert(iterator Where, initializer_list<Type> IList);

template <class InputIterator>
void insert(iterator Where, InputIterator First, InputIterator Last);
```

### <a name="parameters"></a>Parametreler

*Nerede*\
İlk öğenin eklendiği hedef listesindeki konum.

*Val*\
Listeye eklenen öğenin değeri.

*Sayısı*\
Listeye eklenen öğe sayısı.

*Ilk*\
Bağımsız değişken listesindeki öğeler aralığındaki ilk öğenin konumu kopyalanacak.

*Son*\
İlk öğenin bağımsız değişken listesindeki öğelerin kapsamı dışındaki konumu kopyalanacak.

### <a name="return-value"></a>Dönüş Değeri

İlk iki ekleme işlevi, yeni öğenin listeye eklendiği konumu gösteren bir yineleyici döndürür.

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

## <a name="iterator"></a><a name="iterator"></a>Yineleyici

Bir listedeki herhangi bir öğeyi okuyabilen veya değiştirebilen çift yönlü bir yineleme sağlayan bir tür.

```cpp
typedef implementation-defined iterator;
```

### <a name="remarks"></a>Açıklamalar

Bir `iterator` tür, bir öğenin değerini değiştirmek için kullanılabilir.

### <a name="example"></a>Örnek

[Başlangıç](#begin)için örneğe bakın.

## <a name="list"></a><a name="list"></a>Liste

Belirli bir boyutun veya belirli bir değerin öğeleriyle veya belirli bir ayırıcının veya başka bir listenin tamamının veya bir kısmının kopyası olarak bir liste oluşur.

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

*Al*\
Bu nesneyle kullanılacak kaynak ayırıcı sınıfı.

*Sayısı*\
Yapılandırılan listedeki öğe sayısı.

*Val*\
Listedeki öğelerin değeri.

*Doğru*\
Yapılandırılan listenin bir kopyası olması için yapılan liste.

*Ilk*\
Kopyalanacak öğeler aralığındaki ilk öğenin konumu.

*Son*\
İlk öğenin kopyalanacak öğe aralığının ötesindeki konumu.

*ılist*\
Kopyalanacak öğeleri içeren initializer_list.

### <a name="remarks"></a>Açıklamalar

Tüm kurucular bir ayırıcı nesne *(Al)* depolar ve listeyi başharfe alar.

[get_allocator,](#get_allocator) liste oluşturmak için kullanılan ayırıcı nesnenin bir kopyasını döndürür.

İlk iki oluşturucu boş bir başlangıç listesi belirtir, ikinci allocator türünü belirten *(Al)* kullanılacak.

Üçüncü oluşturucu, sınıf `Type`için varsayılan değerin öğelerinin belirli bir sayının *(Count)* tekrarını belirtir.

Dördüncü ve beşinci kurucular *, Val*değeri (*Count*) öğelerinin bir tekrarını belirtirler.

Altıncı oluşturucu, *Sağ*listenin bir kopyasını belirtir.

Yedinci yapıcı *listeyi Sağa*taşır.

Sekizinci oluşturucu öğeleri belirtmek için bir initializer_list kullanır.

Sonraki iki oluşturucu bir `[First, Last)` listenin aralığını kopyalar.

Yapıcıların hiçbiri geçici yer değiştirme ler gerçekleştirmez.

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

## <a name="max_size"></a><a name="max_size"></a>max_size

Listenin en uzunluğunu verir.

```cpp
size_type max_size() const;
```

### <a name="return-value"></a>Dönüş Değeri

Listenin mümkün olan en yüksek uzunluğu.

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

## <a name="merge"></a><a name="merge"></a>Birleştirme

Öğeleri bağımsız değişken listesinden kaldırır, hedef listesine ekler ve artan sırada veya başka bir belirtilen sırada yeni, birleştirilmiş öğeler kümesini sıralar.

```cpp
void merge(list<Type, Allocator>& right);

template <class Traits>
void merge(list<Type, Allocator>& right, Traits comp);
```

### <a name="parameters"></a>Parametreler

*Doğru*\
Hedef listeyle birleştirilecek bağımsız değişken listesi.

*Comp*\
Hedef listenin öğelerini sipariş etmek için kullanılan karşılaştırma işleci.

### <a name="remarks"></a>Açıklamalar

Bağımsız değişken listesi *sağ* hedef listesi ile birleştirilir.

Hem bağımsız değişken hem de hedef listeleri, elde edilen sıranın sıralandığı aynı karşılaştırma ilişkisiyle sıralanmalıdır. İlk üye işlev için varsayılan sıra artan sipariştir. İkinci üye işlevi sınıfın `Traits`kullanıcı tarafından belirtilen karşılaştırma işlemi *comp* empoze eder.

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

## <a name="operator"></a><a name="op_eq"></a>işleç=

Listenin öğelerini başka bir listenin kopyasıyla değiştirir.

```cpp
list& operator=(const list& right);
list& operator=(list&& right);
```

### <a name="parameters"></a>Parametreler

*Doğru*\
Liste [list](../standard-library/list-class.md) `list`kopyalanıyor.

### <a name="remarks"></a>Açıklamalar

Bir'deki varolan öğeleri `list`silerken, işleç *hakkın* içeriğini `list`kopyalar veya .'ye taşır.

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

## <a name="pointer"></a><a name="pointer"></a>Işaretçi

Listedeki bir öğeye işaretçi sağlar.

```cpp
typedef typename Allocator::pointer pointer;
```

### <a name="remarks"></a>Açıklamalar

Bir `pointer` tür, bir öğenin değerini değiştirmek için kullanılabilir.

Çoğu durumda, bir [yineleyici](#iterator) bir liste nesnesindeki öğelere erişmek için kullanılmalıdır.

## <a name="pop_back"></a><a name="pop_back"></a>pop_back

Listenin sonundaki öğeyi siler.

```cpp
void pop_back();
```

### <a name="remarks"></a>Açıklamalar

Son öğe boş olmamalıdır. `pop_back`asla bir istisna atmaz.

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

## <a name="pop_front"></a><a name="pop_front"></a>pop_front

Listenin başındaki öğeyi siler.

```cpp
void pop_front();
```

### <a name="remarks"></a>Açıklamalar

İlk öğe boş olmamalıdır. `pop_front`asla bir istisna atmaz.

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

## <a name="push_back"></a><a name="push_back"></a>push_back

Listenin sonuna bir öğe ekler.

```cpp
void push_back(const Type& val);
void push_back(Type&& val);
```

### <a name="parameters"></a>Parametreler

*Val*\
Öğe listenin sonuna eklendi.

### <a name="remarks"></a>Açıklamalar

Bir özel durum atılırsa, liste değiştirilmeden bırakılır ve özel durum yeniden atılır.

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

## <a name="push_front"></a><a name="push_front"></a>push_front

Listenin başına bir öğe ekler.

```cpp
void push_front(const Type& val);
void push_front(Type&& val);
```

### <a name="parameters"></a>Parametreler

*Val*\
Öğe listenin başına eklendi.

### <a name="remarks"></a>Açıklamalar

Bir özel durum atılırsa, liste değiştirilmeden bırakılır ve özel durum yeniden atılır.

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

## <a name="rbegin"></a><a name="rbegin"></a>rbegin

Ters bir listedeki ilk öğeyi ele alan bir yineleyici döndürür.

```cpp
const_reverse_iterator rbegin() const;
reverse_iterator rbegin();
```

### <a name="return-value"></a>Dönüş Değeri

Ters bir listedeki ilk öğeyi ele alan (veya ters çevrilmemiş listedeki son öğeyi ele alan) ters yönlü bir yineleme.

### <a name="remarks"></a>Açıklamalar

`rbegin`bir liste yle birlikte [begin](#begin) olarak ters bir liste ile kullanılır.

Bir `const_reverse_iterator`, liste `rbegin` nesnesi için return value atanırsa değiştirilemez. Bir `reverse_iterator`, liste `rbegin` nesnesi için return value atanır.

`rbegin`bir liste boyunca geriye doğru doğrulamak için kullanılabilir.

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

## <a name="reference"></a><a name="reference"></a>Başvuru

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

## <a name="remove"></a><a name="remove"></a>Kaldırmak

Belirli bir değerle eşleşen bir listedeki öğeleri siler.

```cpp
void remove(const Type& val);
```

### <a name="parameters"></a>Parametreler

*Val*\
Bir öğe tarafından tutulduğunda, bu öğenin listeden çıkarılmasıyla sonuçlanacak değer.

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

## <a name="remove_if"></a><a name="remove_if"></a>remove_if

Belirli bir yüklemin karşılandığı bir listeden öğeleri siler.

```cpp
template <class Predicate>
void remove_if(Predicate pred)
```

### <a name="parameters"></a>Parametreler

*Pred*\
Bir öğe tarafından tatmin edilirse, bu öğenin listeden silinmesine neden olan unary yüklemi.

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

## <a name="rend"></a><a name="rend"></a>Rend

Ters listedeki son öğeyi izleyen konumu adresleyen bir yineleyici döndürür.

```cpp
const_reverse_iterator rend() const;
reverse_iterator rend();
```

### <a name="return-value"></a>Dönüş Değeri

Ters listedeki son öğeyi (ters çevrilmemiş listedeki ilk öğeden önce gelen konum) yerine gelen konumu gideren ters çift yönlü bir yineleme.

### <a name="remarks"></a>Açıklamalar

`rend`[sonu](#end) bir liste ile kullanıldığı gibi ters bir liste ile kullanılır.

Bir `const_reverse_iterator`, liste `rend` nesnesi için return value atanırsa değiştirilemez. Bir `reverse_iterator`, liste `rend` nesnesi için return value atanır.

`rend`ters yineleyicinin listenin sonuna ulaşıp ulaşmadığını test etmek için kullanılabilir.

Döndürülen `rend` değer dereferenced olmamalıdır.

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

## <a name="resize"></a><a name="resize"></a>Yeni -den boyutlandırmak

Bir liste için yeni bir boyut belirtir.

```cpp
void resize(size_type _Newsize);
void resize(size_type _Newsize, Type val);
```

### <a name="parameters"></a>Parametreler

*_Newsize*\
Listenin yeni boyutu.

*Val*\
Yeni boyut orijinal boyutu daha büyükse, listeye eklenecek yeni öğelerin değeri. Değer atlanırsa, yeni öğeler sınıf için varsayılan değer atanır.

### <a name="remarks"></a>Açıklamalar

Listenin boyutu istenen boyuttan küçükse, *_Newsize,* öğeler istenen boyuta ulaşana kadar listeye eklenir.

Listenin boyutu istenen boyuttan büyükse, listenin sonuna en yakın öğeler *liste _Newsize*boyutuna ulaşana kadar silinir.

Listenin mevcut boyutu istenen boyutla aynıysa, hiçbir işlem yapılmaz.

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

## <a name="reverse"></a><a name="reverse"></a>Ters

Öğelerin bir listede oluşma sırasını tersine çevirir.

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

## <a name="reverse_iterator"></a><a name="reverse_iterator"></a>Reverse_iterator

Ters bir listedeki bir öğeyi okuyabilen veya değiştirebilen çift yönlü bir yineleme sağlayan bir tür.

```cpp
typedef std::reverse_iterator<iterator> reverse_iterator;
```

### <a name="remarks"></a>Açıklamalar

Bir `reverse_iterator` tür, listeyi ters olarak yinelemek için kullanılır.

### <a name="example"></a>Örnek

[rbegin](#rbegin)için örneğe bakın.

## <a name="size"></a><a name="size"></a>Boyutu

Listedeki öğe sayısını döndürür.

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

## <a name="size_type"></a><a name="size_type"></a>Size_type

Listedeki öğe sayısını sayan bir tür.

```cpp
typedef typename Allocator::size_type size_type;
```

### <a name="example"></a>Örnek

[Boyut](#size)için örneğe bakın.

## <a name="sort"></a><a name="sort"></a>Sıralama

Bir listenin öğelerini artan sırada veya kullanıcı tarafından belirtilen diğer bazı siparişlerle ilgili olarak düzenler.

```cpp
void sort();

template <class Traits>
    void sort(Traits comp);
```

### <a name="parameters"></a>Parametreler

*Comp*\
Ardışık öğeleri sipariş etmek için kullanılan karşılaştırma işleci.

### <a name="remarks"></a>Açıklamalar

İlk üye işlev öğeleri varsayılan olarak artan sırada koyar.

Üye şablon işlevi sınıfın `Traits`kullanıcı tarafından belirtilen karşılaştırma işlemi *comp* göre öğeleri siparişleri.

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

## <a name="splice"></a><a name="splice"></a>Splice

Öğeleri kaynak listesinden kaldırır ve hedef listesine ekler.

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

*Nerede*\
Eklenecek önce hedef listesindeki konum.

*Kaynak*\
Hedef listeye eklenecek kaynak listesi.

*ıter*\
Kaynak listeden eklenecek öğe.

*Ilk*\
Aralıktaki ilk öğe kaynak listeden eklenecek.

*Son*\
Kaynak listeden eklenecek aralıktaki son öğenin ötesindeki ilk konum.

### <a name="remarks"></a>Açıklamalar

İlk üye işlev çifti, *Nerede* tarafından atıfta bulunulan konumdan önce kaynak listesindeki tüm öğeleri hedef listeye ekler ve tüm öğeleri kaynak listeden kaldırır. (`&Source` eşit `this`olmamalıdır .)

İkinci üye işlev çifti, *Nerede* tarafından başvurulan hedef listesindeki konumdan önce *Iter* tarafından atıfta bulunulan öğeyi ekler ve *Iter'ı* kaynak listesinden kaldırır. (Değişiklik `Where == Iter || Where == ++Iter`olmazsa.)

Üçüncü üye işlev çifti, *Nerede* tarafından atıfta `First` `Last`bulunulan hedef listesindeki öğeden önce [ , ) tarafından belirlenen aralığı ekler ve bu öğe aralığını kaynak listesinden kaldırır. (Eğer, `&Source == this`aralık `[First, Last)` *Nerede*tarafından işaret öğeiçermemelidir .)

Aralıklı `N` splice öğeleri ekler ve `&Source != this`, sınıf [yineleyici](../standard-library/forward-list-class.md#iterator) bir nesne `N` artışlı kez.

Tüm durumlarda yineleyiciler, işaretçiler veya birleştirilmiş öğelere başvuran başvurular geçerli kalır ve hedef kapsayıcıya aktarılır.

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

## <a name="swap"></a><a name="swap"></a>Takas

İki liste öğelerini değiştirir.

```cpp
void swap(list<Type, Allocator>& right);
friend void swap(list<Type, Allocator>& left, list<Type, Allocator>& right)
```

### <a name="parameters"></a>Parametreler

*Doğru*\
Değiştirilecek öğeleri sağlayan liste veya *öğeleri bırakılan*listeyle değiştirilecek liste.

*Sol*\
Öğeleri *doğru*liste dekilerle değiştirilecek bir liste.

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

## <a name="unique"></a><a name="unique"></a>Benzer -siz

Bir listeden diğer bazı ikili yüklemi karşılayan bitişik yinelenen öğeleri veya bitişik öğeleri kaldırır.

```cpp
void unique();

template <class BinaryPredicate>
void unique(BinaryPredicate pred);
```

### <a name="parameters"></a>Parametreler

*Pred*\
Ardışık öğeleri karşılaştırmak için kullanılan ikili yüklem.

### <a name="remarks"></a>Açıklamalar

Bu işlev, tüm yinelenen öğelerin bitişik olması için listenin sıralanmış olduğunu varsayar. Bitişik olmayan yinelemeler silinmez.

İlk üye işlev, önceki öğeyle eşit karşılaştırılabilen her öğeyi kaldırır.

İkinci üye işlev, önceki öğesi ile karşılaştırıldığında yüklem işlevi *pred'ini* tatmin eden her öğeyi kaldırır. Bağımsız değişken \< *pred* için işlevsel> üstbilgisinde bildirilen ikili işlev nesnelerinden herhangi birini kullanabilir veya kendi nesnenizi oluşturabilirsiniz.

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

## <a name="value_type"></a><a name="value_type"></a>Value_type

Listede depolanan veri türünü temsil eden bir tür.

```cpp
typedef typename Allocator::value_type value_type;
```

### <a name="remarks"></a>Açıklamalar

`value_type`şablon parametresi *Türü*ile eş anlamlıdır.

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
