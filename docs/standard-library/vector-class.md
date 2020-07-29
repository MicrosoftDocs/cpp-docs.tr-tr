---
title: vector sınıfı
description: Sınıf vektörünün Microsoft C++ standart kitaplık uygulamasına yönelik başvuru.
ms.date: 02/07/2020
f1_keywords:
- vector/std::vector::allocator_type
- vector/std::vector::const_iterator
- vector/std::vector::const_pointer
- vector/std::vector::const_reference
- vector/std::vector::const_reverse_iterator
- vector/std::vector::difference_type
- vector/std::vector::iterator
- vector/std::vector::pointer
- vector/std::vector::reference
- vector/std::vector::reverse_iterator
- vector/std::vector::size_type
- vector/std::vector::value_type
- vector/std::vector::assign
- vector/std::vector::at
- vector/std::vector::back
- vector/std::vector::begin
- vector/std::vector::capacity
- vector/std::vector::cbegin
- vector/std::vector::cend
- vector/std::vector::crbegin
- vector/std::vector::crend
- vector/std::vector::clear
- vector/std::vector::data
- vector/std::vector::emplace
- vector/std::vector::emplace_back
- vector/std::vector::empty
- vector/std::vector::end
- vector/std::vector::erase
- vector/std::vector::front
- vector/std::vector::get_allocator
- vector/std::vector::insert
- vector/std::vector::max_size
- vector/std::vector::pop_back
- vector/std::vector::push_back
- vector/std::vector::rbegin
- vector/std::vector::rend
- vector/std::vector::reserve
- vector/std::vector::resize
- vector/std::vector::shrink_to_fit
- vector/std::vector::size
- vector/std::vector::swap
helpviewer_keywords:
- std::vector [C++], allocator_type
- std::vector [C++], const_iterator
- std::vector [C++], const_pointer
- std::vector [C++], const_reference
- std::vector [C++], const_reverse_iterator
- std::vector [C++], difference_type
- std::vector [C++], iterator
- std::vector [C++], pointer
- std::vector [C++], reference
- std::vector [C++], reverse_iterator
- std::vector [C++], size_type
- std::vector [C++], value_type
- std::vector [C++], assign
- std::vector [C++], at
- std::vector [C++], back
- std::vector [C++], begin
- std::vector [C++], capacity
- std::vector [C++], cbegin
- std::vector [C++], cend
- std::vector [C++], crbegin
- std::vector [C++], crend
- std::vector [C++], clear
- std::vector [C++], data
- std::vector [C++], emplace
- std::vector [C++], emplace_back
- std::vector [C++], empty
- std::vector [C++], end
- std::vector [C++], erase
- std::vector [C++], front
- std::vector [C++], get_allocator
- std::vector [C++], insert
- std::vector [C++], max_size
- std::vector [C++], pop_back
- std::vector [C++], push_back
- std::vector [C++], rbegin
- std::vector [C++], rend
- std::vector [C++], reserve
- std::vector [C++], resize
- std::vector [C++], shrink_to_fit
- std::vector [C++], size
- std::vector [C++], swap
ms.assetid: a3e0a8f8-7565-4fe0-93e4-e4d74ae1b70d
ms.openlocfilehash: 71b55b4af44a641846ca7b8706bee420887950c5
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87224571"
---
# <a name="vector-class"></a>vector sınıfı

C++ standart kitaplığı vektör sınıfı, dizi kapsayıcıları için bir sınıf şablonudur. Vektör, belirli bir türdeki öğeleri doğrusal bir düzenlemede depolar ve herhangi bir öğeye hızlı rastgele erişim sağlar. Bir vektör, rastgele erişim performansı Premium olduğunda bir dizi için tercih edilen kapsayıcıdır.

## <a name="syntax"></a>Söz dizimi

```cpp
template <class Type, class Allocator = allocator<Type>>
class vector
```

### <a name="parameters"></a>Parametreler

*Türüyle*\
Vektörde depolanacak öğe veri türü

*Öğe*\
Vektör 'nin bellek ayırmayı ve ayırmayı kaldırma hakkındaki ayrıntıları kapsülleyen saklı ayırıcı nesnesini temsil eden tür. Bu bağımsız değişken isteğe bağlıdır ve varsayılan değerdir `allocator<Type>` .

## <a name="remarks"></a>Açıklamalar

Vektörler, sıranın sonunda sabit zaman ekleme ve silme işlemlerine izin verir. Vektör ortasında öğe eklemek veya silmek doğrusal bir süre gerektirir. [Deque Sınıfı](../standard-library/deque-class.md) kapsayıcısı, bir sıranın başındaki ve sonundaki ekleme ve silme işlemleri sırasında daha hızlıdır. [Liste sınıfı](../standard-library/list-class.md) kapsayıcısı, bir dizi içinde herhangi bir konumda eklemeler ve silinmelerden daha hızlıdır.

Vektör yeniden ayırma, bir üye işlevi, vektör nesnesinde bulunan sırayı geçerli depolama kapasitesinin ötesinde artırması gerektiğinde gerçekleşir. Diğer Eklenenler ve erasures dizi içindeki çeşitli depolama adreslerini değiştirebilir. Bu gibi durumlarda, yineleyiciler veya dizinin değiştirilen bölümlerini işaret eden başvurular geçersiz hale gelir. Yeniden ayırma işlemi gerçekleşmeden sonra, yalnızca yineleyiciler ve ekleme/silme noktası ile yapılan başvurular geçerli kalır.

[Vector \<bool> sınıfı](../standard-library/vector-bool-class.md) , türündeki öğeler için sınıf şablonu vektörünün tam bir özelleştirmesi **`bool`** . Özelleşmenin kullandığı temel tür için bir ayırıcısı vardır.

[Vektör \<bool> başvuru sınıfı](../standard-library/vector-bool-class.md#reference_class) , nesneleri bir vektör nesnesi içindeki öğelere (tek bit) başvuru sağlayabilen iç içe bir sınıftır \<bool> .

## <a name="members"></a>Üyeler

### <a name="constructors"></a>Oluşturucular

|||
|-|-|
|[vektör](#vector)|Belirli bir boyutun veya belirli bir değere sahip veya belirli bir vektör kopyası olan öğelerle bir vektör oluşturur `allocator` .|

### <a name="typedefs"></a>Tür tanımları

|||
|-|-|
|[allocator_type](#allocator_type)|Vektör nesnesinin sınıfını temsil eden bir tür `allocator` .|
|[const_iterator](#const_iterator)|Vektördeki bir öğeyi okuyabilen bir rastgele erişim yineleyici sağlayan bir tür **`const`** .|
|[const_pointer](#const_pointer)|Vektörde bir öğeye işaretçi sağlayan bir tür **`const`** .|
|[const_reference](#const_reference)|Vektörde depolanan bir öğeye başvuru sağlayan bir tür **`const`** . İşlem okumak ve gerçekleştirmek için kullanılır **`const`** .|
|[const_reverse_iterator](#const_reverse_iterator)|Vektördeki herhangi bir öğeyi okuyabilen bir rastgele erişim yineleyici sağlayan bir tür **`const`** .|
|[difference_type](#difference_type)|Vektördeki iki öğenin adresleri arasındaki farkı sağlayan bir tür.|
|[iden](#iterator)|Vektördeki herhangi bir öğeyi okuyabilen veya değiştirebilen bir rasgele erişim yineleyicisi sağlayan bir tür.|
|[pointer](#pointer)|Vektörde bir öğeye işaretçi sağlayan bir tür.|
|[başvurunun](#reference)|Vektörde depolanan bir öğeye başvuru sağlayan bir tür.|
|[reverse_iterator](#reverse_iterator)|Tersine çevrilmiş Vektördeki herhangi bir öğeyi okuyabilen veya değiştirebilen bir rasgele erişim yineleyicisi sağlayan bir tür.|
|[size_type](#size_type)|Vektördeki öğelerin sayısını sayan bir tür.|
|[value_type](#value_type)|Vektörde depolanan veri türünü temsil eden bir tür.|

### <a name="functions"></a>İşlevler

|||
|-|-|
|[assign (atamak)](#assign) |Bir vektörü siler ve belirtilen öğeleri boş vektöre kopyalar.|
|[hızı](#at)|Vektörde belirtilen konumdaki öğeye bir başvuru döndürür.|
|[Geri](#back)|Vector öğesinin son öğesine bir başvuru döndürür.|
|[başladı](#begin)|Vektördeki ilk öğeye Rastgele erişimli bir yineleyici döndürür.|
|[kü](#capacity)|Daha fazla depolama alanı ayırmadan vektör içerebilen öğe sayısını döndürür.|
|[cbegin](#cbegin)|Vektör içindeki ilk öğeye Rastgele erişimli bir const yineleyicisi döndürür.|
|[cend](#cend)|Vektör sonunun hemen ötesinde işaret eden Rastgele erişimli bir const yineleyici döndürür.|
|[crbegin](#crbegin)|Ters çevrilen Vektördeki ilk öğeye bir const yineleyici döndürür.|
|[crend](#crend)|Ters çevrilen vector öğesinin sonuna bir const yineleyici döndürür.|
|[lediğiniz](#clear)|Vektör öğelerini siler.|
|[data](#data)|Vektördeki ilk öğeye bir işaretçi döndürür.|
|[Emplace](#emplace)|Belirli bir konumdaki vector öğesine yerinde oluşturulmuş bir öğe ekler.|
|[emplace_back](#emplace_back)|Vector öğesinin sonuna yerinde oluşturulmuş bir öğe ekler.|
|[empty](#empty)|Vektör kapsayıcısının boş olup olmadığını sınar.|
|[erer](#end)|Vektörün sonuna işaret eden bir rastgele erişim yineleyicisi döndürür.|
|[silme](#erase)|Belirtilen konumlardan bir vektör içindeki öğe veya öğe aralığını kaldırır.|
|[yapılan](#front)|Vektördeki ilk öğeye bir başvuru döndürür.|
|[get_allocator](#get_allocator)|`allocator`Vektör tarafından kullanılan sınıfa bir nesne döndürür.|
|[ekleyin](#insert)|Belirli bir konumdaki vektöre bir öğe veya sayıda öğe ekler.|
|[max_size](#max_size)|Vektörün maksimum uzunluğunu döndürür.|
|[pop_back](#pop_back)|Vektör sonundaki öğeyi siler.|
|[push_back](#push_back)|Vektörün sonuna bir öğe ekleyin.|
|[rbegin](#rbegin)|Tersine çevrilmiş Vektördeki ilk öğeye bir yineleyici döndürür.|
|[rend](#rend)|Tersine çevrilmiş vector öğesinin sonuna bir yineleyici döndürür.|
|[Rezerve et](#reserve)|Vektör nesnesi için en düşük depolama uzunluğunu ayırır.|
|[yeniden boyutlandırma](#resize)|Bir vektör için yeni bir boyut belirtir.|
|[shrink_to_fit](#shrink_to_fit)|Fazla kapasiteyi atar.|
|[boyutla](#size)|Vektördeki öğe sayısını döndürür.|
|[Kur](#swap)|İki vektörün öğelerini değiş tokuş eder.|

### <a name="operators"></a>İşleçler

|||
|-|-|
|[işleç&#91;&#93;](#op_at)|Vektör öğesine belirtilen konumda bir başvuru döndürür.|
|[işleç =](#op_eq)|Vektör öğelerini başka bir Vector kopyasıyla değiştirir.|

## <a name="allocator_type"></a><a name="allocator_type"></a>allocator_type

Vektör nesnesinin ayırıcı sınıfını temsil eden bir tür.

```cpp
typedef Allocator allocator_type;
```

### <a name="remarks"></a>Açıklamalar

`allocator_type`, şablon parametresinin eşanlamlısıdır `Allocator` .

### <a name="example"></a>Örnek

Tarafından kullanılan bir örnek için [get_allocator](#get_allocator) örneğe bakın `allocator_type` .

## <a name="assign"></a><a name="assign"></a>ata

Bir vektörü siler ve belirtilen öğeleri boş vektöre kopyalar.

```cpp
void assign(size_type count, const Type& value);
void assign(initializer_list<Type> init_list);

template <class InputIterator>
void assign(InputIterator first, InputIterator last);
```

### <a name="parameters"></a>Parametreler

*adı*\
Kopyalanacak öğe aralığındaki ilk öğenin konumu.

*soyadına*\
Kopyalanacak öğe aralığının ötesinde ilk öğenin konumu.

*biriktirme*\
Vektöre eklenen bir öğenin kopya sayısı.

*deeri*\
Vektöre eklenmekte olan öğenin değeri.

*init_list*\
Eklenecek öğeleri içeren initializer_list.

### <a name="remarks"></a>Açıklamalar

İlk olarak, `assign` bir vektörde bulunan tüm öğeleri siler. Sonra, `assign` özgün vektörden belirtilen bir öğe aralığını bir Vector öğesine ekler ya da yeni bir belirtilen değer öğesinin kopyalarını bir Vector öğesine ekler.

### <a name="example"></a>Örnek

```cpp
/ vector_assign.cpp
// compile with: /EHsc
#include <vector>
#include <iostream>

int main()
{
    using namespace std;
    vector<int> v1, v2, v3;

    v1.push_back(10);
    v1.push_back(20);
    v1.push_back(30);
    v1.push_back(40);
    v1.push_back(50);

    cout << "v1 = ";
    for (auto& v : v1){
        cout << v << " ";
    }
    cout << endl;

    v2.assign(v1.begin(), v1.end());
    cout << "v2 = ";
    for (auto& v : v2){
        cout << v << " ";
    }
    cout << endl;

    v3.assign(7, 4);
    cout << "v3 = ";
    for (auto& v : v3){
        cout << v << " ";
    }
    cout << endl;

    v3.assign({ 5, 6, 7 });
    for (auto& v : v3){
        cout << v << " ";
    }
    cout << endl;
}
```

## <a name="at"></a><a name="at"></a>hızı

Vektörde belirtilen konumdaki öğeye bir başvuru döndürür.

```cpp
reference at(size_type position);

const_reference at(size_type position) const;
```

### <a name="parameters"></a>Parametreler

*yerine*\
Vektörde başvurulacak öğenin alt simge veya konum numarası.

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkende bulunan öğe için bir başvuru. *Konum* vector öğesinin boyutundan büyükse `at` bir özel durum oluşturur.

### <a name="remarks"></a>Açıklamalar

Dönüş değeri `at` bir öğesine atanırsa `const_reference` , vektör nesnesi değiştirilemez. Dönüş değeri `at` öğesine atanırsa `reference` , vektör nesnesi değiştirilebilir.

### <a name="example"></a>Örnek

```cpp
// vector_at.cpp
// compile with: /EHsc
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;
   vector <int> v1;

   v1.push_back( 10 );
   v1.push_back( 20 );

   const int &i = v1.at( 0 );
   int &j = v1.at( 1 );
   cout << "The first element is " << i << endl;
   cout << "The second element is " << j << endl;
}
```

```Output
The first element is 10
The second element is 20
```

## <a name="back"></a><a name="back"></a>Geri

Vector öğesinin son öğesine bir başvuru döndürür.

```cpp
reference back();

const_reference back() const;
```

### <a name="return-value"></a>Dönüş Değeri

Vector öğesinin son öğesi. Vektör boşsa, dönüş değeri tanımsızdır.

### <a name="remarks"></a>Açıklamalar

Dönüş değeri `back` bir öğesine atanırsa `const_reference` , vektör nesnesi değiştirilemez. Dönüş değeri `back` öğesine atanırsa `reference` , vektör nesnesi değiştirilebilir.

1 veya 2 olarak tanımlanan [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md) kullanılarak derlendiğinde, boş bir vektörde bir öğeye erişmeyi denerseniz bir çalışma zamanı hatası oluşur. Daha fazla bilgi için bkz. [Checked Iterators](../standard-library/checked-iterators.md).

### <a name="example"></a>Örnek

```cpp
// vector_back.cpp
// compile with: /EHsc
#include <vector>
#include <iostream>

int main() {
   using namespace std;
   vector <int> v1;

   v1.push_back( 10 );
   v1.push_back( 11 );

   int& i = v1.back( );
   const int& ii = v1.front( );

   cout << "The last integer of v1 is " << i << endl;
   i--;
   cout << "The next-to-last integer of v1 is "<< ii << endl;
}
```

## <a name="begin"></a><a name="begin"></a>başladı

Vektördeki ilk öğeye Rastgele erişimli bir yineleyici döndürür.

```cpp
const_iterator begin() const;

iterator begin();
```

### <a name="return-value"></a>Dönüş Değeri

İçindeki ilk öğeyi `vector` veya bir boş olan konumda bulunan bir rastgele erişim Yineleyici `vector` . Geçerli olduğundan emin olmak için [vektör:: End](#end) ile döndürülen değeri her zaman karşılaştırın.

### <a name="remarks"></a>Açıklamalar

Dönüş değeri `begin` bir [vector:: const_iterator](#const_iterator)öğesine atanmışsa, `vector` nesne değiştirilemez. Dönüş değeri `begin` bir [vector:: Iterator](#iterator)öğesine atanmışsa, `vector` nesne değiştirilebilir.

### <a name="example"></a>Örnek

```cpp
// vector_begin.cpp
// compile with: /EHsc
#include <vector>
#include <iostream>

int main()
{
    using namespace std;
    vector<int> c1;
    vector<int>::iterator c1_Iter;
    vector<int>::const_iterator c1_cIter;

    c1.push_back(1);
    c1.push_back(2);

    cout << "The vector c1 contains elements:";
    c1_Iter = c1.begin();
    for (; c1_Iter != c1.end(); c1_Iter++)
    {
        cout << " " << *c1_Iter;
    }
    cout << endl;

    cout << "The vector c1 now contains elements:";
    c1_Iter = c1.begin();
    *c1_Iter = 20;
    for (; c1_Iter != c1.end(); c1_Iter++)
    {
        cout << " " << *c1_Iter;
    }
    cout << endl;

    // The following line would be an error because iterator is const
    // *c1_cIter = 200;
}
```

```Output
The vector c1 contains elements: 1 2
The vector c1 now contains elements: 20 2
```

## <a name="capacity"></a><a name="capacity"></a>kü

Daha fazla depolama alanı ayırmadan vektör içerebilen öğe sayısını döndürür.

```cpp
size_type capacity() const;
```

### <a name="return-value"></a>Dönüş Değeri

Vektör için ayrılan geçerli depolama alanı uzunluğu.

### <a name="remarks"></a>Açıklamalar

Üye işlevi [yeniden boyutlandırılması](#resize) , yeterli bellek ayrılması durumunda daha etkili olacaktır. Ayrılan bellek miktarını belirtmek [için ayrılmış üye işlevini kullanın](#reserve) .

### <a name="example"></a>Örnek

```cpp
// vector_capacity.cpp
// compile with: /EHsc
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;
   vector <int> v1;

   v1.push_back( 1 );
   cout << "The length of storage allocated is "
        << v1.capacity( ) << "." << endl;

   v1.push_back( 2 );
   cout << "The length of storage allocated is now "
        << v1.capacity( ) << "." << endl;
}
```

```Output
The length of storage allocated is 1.
The length of storage allocated is now 2.
```

## <a name="cbegin"></a><a name="cbegin"></a>cbegin

**`const`** Aralıktaki ilk öğeyi ele alan bir yineleyici döndürür.

```cpp
const_iterator cbegin() const;
```

### <a name="return-value"></a>Dönüş Değeri

**`const`** Aralığın ilk öğesine veya boş bir aralığın sonundaki konuma (boş bir Aralık için) işaret eden bir rastgele erişim Yineleyici `cbegin() == cend()` .

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

**`const`** Yalnızca aralığın sonunu işaret eden bir rastgele erişim Yineleyici.

### <a name="remarks"></a>Açıklamalar

`cend`, bir yineleyicinin aralığın sonunu geçtiğini test etmek için kullanılır.

`end()`Dönüş değerinin olduğunu garantilemek için üye işlevin yerine bu üye işlevi kullanabilirsiniz `const_iterator` . Genellikle, aşağıdaki örnekte gösterildiği gibi [Otomatik](../cpp/auto-cpp.md) tür kesintisi anahtar sözcüğüyle birlikte kullanılır. Örnekte, ve ' ı `Container` destekleyen herhangi bir türde değiştirilebilir (olmayan) bir kapsayıcı olarak göz önünde bulundurun **`const`** `end()` `cend()` .

```cpp
auto i1 = Container.end();
// i1 is Container<T>::iterator
auto i2 = Container.cend();

// i2 is Container<T>::const_iterator
```

Tarafından döndürülen değer `cend` başvurulmamalıdır. Yalnızca karşılaştırma için kullanın.

## <a name="clear"></a><a name="clear"></a>lediğiniz

Vektör öğelerini siler.

```cpp
void clear();
```

### <a name="example"></a>Örnek

```cpp
// vector_clear.cpp
// compile with: /EHsc
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;
   vector <int> v1;

   v1.push_back( 10 );
   v1.push_back( 20 );
   v1.push_back( 30 );

   cout << "The size of v1 is " << v1.size( ) << endl;
   v1.clear( );
   cout << "The size of v1 after clearing is " << v1.size( ) << endl;
}
```

```Output
The size of v1 is 3
The size of v1 after clearing is 0
```

## <a name="const_iterator"></a><a name="const_iterator"></a>const_iterator

Vektördeki bir öğeyi okuyabilen bir rastgele erişim yineleyici sağlayan bir tür **`const`** .

```cpp
typedef implementation-defined const_iterator;
```

### <a name="remarks"></a>Açıklamalar

Bir tür `const_iterator` , bir öğenin değerini değiştirmek için kullanılamaz.

### <a name="example"></a>Örnek

Kullanan bir [örnek için örneğe](#back) bakın `const_iterator` .

## <a name="const_pointer"></a><a name="const_pointer"></a>const_pointer

Vektörde bir öğeye işaretçi sağlayan bir tür **`const`** .

```cpp
typedef typename Allocator::const_pointer const_pointer;
```

### <a name="remarks"></a>Açıklamalar

Bir tür `const_pointer` , bir öğenin değerini değiştirmek için kullanılamaz.

[Yineleyici](#iterator) bir vektör öğesine erişmek için daha yaygın olarak kullanılır.

## <a name="const_reference"></a><a name="const_reference"></a>const_reference

Vektörde depolanan bir öğeye başvuru sağlayan bir tür **`const`** . İşlem okumak ve gerçekleştirmek için kullanılır **`const`** .

```cpp
typedef typename Allocator::const_reference const_reference;
```

### <a name="remarks"></a>Açıklamalar

Bir tür `const_reference` , bir öğenin değerini değiştirmek için kullanılamaz.

### <a name="example"></a>Örnek

```cpp
// vector_const_ref.cpp
// compile with: /EHsc
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;
   vector <int> v1;

   v1.push_back( 10 );
   v1.push_back( 20 );

   const vector <int> v2 = v1;
   const int &i = v2.front( );
   const int &j = v2.back( );
   cout << "The first element is " << i << endl;
   cout << "The second element is " << j << endl;

   // The following line would cause an error as v2 is const
   // v2.push_back( 30 );
}
```

```Output
The first element is 10
The second element is 20
```

## <a name="const_reverse_iterator"></a><a name="const_reverse_iterator"></a>const_reverse_iterator

Vektördeki herhangi bir öğeyi okuyabilen bir rastgele erişim yineleyici sağlayan bir tür **`const`** .

```cpp
typedef std::reverse_iterator<const_iterator> const_reverse_iterator;
```

### <a name="remarks"></a>Açıklamalar

Bir tür `const_reverse_iterator` , bir öğenin değerini değiştiremiyor ve vector öğesinde ters yönde yinelemek için kullanılır.

### <a name="example"></a>Örnek

Yineleyici bildirme ve kullanma hakkında bir örnek için bkz. [rbegin](#rbegin) .

## <a name="crbegin"></a><a name="crbegin"></a>crbegin

Ters çevrilen Vektördeki ilk öğeye bir const yineleyici döndürür.

```cpp
const_reverse_iterator crbegin() const;
```

### <a name="return-value"></a>Dönüş Değeri

Ters çevrilen bir [vektör](../standard-library/vector-class.md) içindeki ilk öğeyi ele almak veya geri çevrilmede son öğe olduğunu ele almak için bir const ters rastgele erişim Yineleyici `vector` .

### <a name="remarks"></a>Açıklamalar

Dönüş değeri ile `crbegin` `vector` nesne değiştirilemez.

### <a name="example"></a>Örnek

```cpp
// vector_crbegin.cpp
// compile with: /EHsc
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;
   vector <int> v1;
   vector <int>::iterator v1_Iter;
   vector <int>::const_reverse_iterator v1_rIter;

   v1.push_back( 1 );
   v1.push_back( 2 );

   v1_Iter = v1.begin( );
   cout << "The first element of vector is "
        << *v1_Iter << "." << endl;

   v1_rIter = v1.crbegin( );
   cout << "The first element of the reversed vector is "
        << *v1_rIter << "." << endl;
}
```

```Output
The first element of vector is 1.
The first element of the reversed vector is 2.
```

## <a name="crend"></a><a name="crend"></a>crend

Ters çevrilen Vektördeki son öğeden sonraki konumu ele alan bir const yineleyici döndürür.

```cpp
const_reverse_iterator crend() const;
```

### <a name="return-value"></a>Dönüş Değeri

Ters çevrilen bir [vektör](../standard-library/vector-class.md) içindeki son öğeden sonra gelen konumu ele alan bir sabit ters rastgele erişim yineleyici (geri çevrilmede ilk öğeden önce gelen konum `vector` ).

### <a name="remarks"></a>Açıklamalar

`crend`, bir ters ile birlikte kullanıldığında, `vector` [vector:: cend](#cend) ile birlikte kullanılır `vector` .

Dönüş değeri `crend` (uygun şekilde azaltılır) ile `vector` nesne değiştirilemez.

`crend`, geriye doğru bir yineleyicinin sonuna ulaşılıp ulaşılmadığını test etmek için kullanılabilir `vector` .

Tarafından döndürülen değer `crend` başvurulmamalıdır. Yalnızca karşılaştırma için kullanın.

### <a name="example"></a>Örnek

```cpp
// vector_crend.cpp
// compile with: /EHsc
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;
   vector <int> v1;
   vector <int>::const_reverse_iterator v1_rIter;

   v1.push_back( 1 );
   v1.push_back( 2 );

   for ( v1_rIter = v1.rbegin( ) ; v1_rIter != v1.rend( ) ; v1_rIter++ )
      cout << *v1_rIter << endl;
}
```

```Output
2
1
```

## <a name="data"></a><a name="data"></a>verileri

Vektördeki ilk öğeye bir işaretçi döndürür.

```cpp
const_pointer data() const;

pointer data();
```

### <a name="return-value"></a>Dönüş Değeri

[Vektördeki](../standard-library/vector-class.md) ilk öğe için veya bir boş olan konuma yönelik bir işaretçi `vector` .

### <a name="example"></a>Örnek

```cpp
// vector_data.cpp
// compile with: /EHsc
#include <vector>
#include <iostream>

int main()
{
    using namespace std;
    vector<int> c1;
    vector<int>::pointer c1_ptr;
    vector<int>::const_pointer c1_cPtr;

    c1.push_back(1);
    c1.push_back(2);

    cout << "The vector c1 contains elements:";
    c1_cPtr = c1.data();
    for (size_t n = c1.size(); 0 < n; --n, c1_cPtr++)
    {
        cout << " " << *c1_cPtr;
    }
    cout << endl;

    cout << "The vector c1 now contains elements:";
    c1_ptr = c1.data();
    *c1_ptr = 20;
    for (size_t n = c1.size(); 0 < n; --n, c1_ptr++)
    {
        cout << " " << *c1_ptr;
    }
    cout << endl;
}
```

```Output
The vector c1 contains elements: 1 2
The vector c1 now contains elements: 20 2
```

## <a name="difference_type"></a><a name="difference_type"></a>difference_type

Aynı vektör içindeki öğelere başvuran iki yineleyiciler arasındaki farkı sağlayan bir tür.

```cpp
typedef typename Allocator::difference_type difference_type;
```

### <a name="remarks"></a>Açıklamalar

Bir `difference_type` öğe için bir işaretçi adresini içerdiğinden, bir, iki işaretçi arasındaki öğe sayısı olarak da açıklanabilir.

[Yineleyici](#iterator) bir vektör öğesine erişmek için daha yaygın olarak kullanılır.

### <a name="example"></a>Örnek

```cpp
// vector_diff_type.cpp
// compile with: /EHsc
#include <iostream>
#include <vector>
#include <algorithm>

int main( )
{
   using namespace std;

   vector <int> c1;
   vector <int>::iterator c1_Iter, c2_Iter;

   c1.push_back( 30 );
   c1.push_back( 20 );
   c1.push_back( 30 );
   c1.push_back( 10 );
   c1.push_back( 30 );
   c1.push_back( 20 );

   c1_Iter = c1.begin( );
   c2_Iter = c1.end( );

   vector <int>::difference_type   df_typ1, df_typ2, df_typ3;

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

## <a name="emplace"></a><a name="emplace"></a>Emplace

Belirli bir konumdaki vector öğesine yerinde oluşturulmuş bir öğe ekler.

```cpp
template <class... Types>
iterator emplace(
    const_iterator position,
    Types&&... args);
```

### <a name="parameters"></a>Parametreler

*yerine*\
[Vektördeki](../standard-library/vector-class.md) ilk öğenin eklendiği konum.

*args*\
Oluşturucu bağımsız değişkenleri. İşlevi, belirtilen bağımsız değişkenlere göre çağırmak için Oluşturucu aşırı yüklemesini haller.

### <a name="return-value"></a>Dönüş Değeri

İşlevi, yeni öğenin içine eklendiği konuma işaret eden bir yineleyici döndürür `vector` .

### <a name="remarks"></a>Açıklamalar

Herhangi bir ekleme işlemi pahalı olabilir, bir performans tartışması için [vektör sınıfına](../standard-library/vector-class.md) bakın `vector` .

### <a name="example"></a>Örnek

```cpp
// vector_emplace.cpp
// compile with: /EHsc
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;
   vector <int> v1;
   vector <int>::iterator Iter;

   v1.push_back( 10 );
   v1.push_back( 20 );
   v1.push_back( 30 );

   cout << "v1 =" ;
   for ( Iter = v1.begin( ) ; Iter != v1.end( ) ; Iter++ )
      cout << " " << *Iter;
   cout << endl;

// initialize a vector of vectors by moving v1
   vector < vector <int> > vv1;

   vv1.emplace( vv1.begin(), move( v1 ) );
   if ( vv1.size( ) != 0 && vv1[0].size( ) != 0 )
      {
      cout << "vv1[0] =";
      for (Iter = vv1[0].begin( ); Iter != vv1[0].end( ); Iter++ )
         cout << " " << *Iter;
      cout << endl;
      }
}
```

```Output
v1 = 10 20 30
vv1[0] = 10 20 30
```

## <a name="emplace_back"></a><a name="emplace_back"></a>emplace_back

Vector öğesinin sonuna yerinde oluşturulmuş bir öğe ekler.

```cpp
template <class... Types>
void emplace_back(Types&&... args);
```

### <a name="parameters"></a>Parametreler

*args*\
Oluşturucu bağımsız değişkenleri. İşlevi, belirtilen bağımsız değişkenlere göre çağırmak için Oluşturucu aşırı yüklemesini haller.

### <a name="example"></a>Örnek

```cpp
#include <vector>
struct obj
{
   obj(int, double) {}
};

int main()
{
   std::vector<obj> v;
   v.emplace_back(1, 3.14); // obj in created in place in the vector
}
```

## <a name="empty"></a><a name="empty"></a>olmamalıdır

Vektör boş ise sınar.

```cpp
bool empty() const;
```

### <a name="return-value"></a>Dönüş Değeri

**`true`** vektör boşsa; **`false`** vektör boş değilse.

### <a name="example"></a>Örnek

```cpp
// vector_empty.cpp
// compile with: /EHsc
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;
   vector <int> v1;

   v1.push_back( 10 );

   if ( v1.empty( ) )
      cout << "The vector is empty." << endl;
   else
      cout << "The vector is not empty." << endl;
}
```

```Output
The vector is not empty.
```

## <a name="end"></a><a name="end"></a>erer

past-the-end yineleyici döndürür.

```cpp
iterator end();

const_iterator end() const;
```

### <a name="return-value"></a>Dönüş Değeri

Vektör için son uca Yineleyici. Vektör boşsa, `vector::end() == vector::begin()` .

### <a name="remarks"></a>Açıklamalar

Dönüş değeri `end` türünde bir değişkene atanırsa `const_iterator` , vektör nesnesi değiştirilemez. Dönüş değeri `end` türünde bir değişkene atanırsa `iterator` , vektör nesnesi değiştirilebilir.

### <a name="example"></a>Örnek

```cpp
// vector_end.cpp
// compile with: /EHsc
#include <vector>
#include <iostream>
int main( )
{
   using namespace std;
   vector <int> v1;
   vector <int>::iterator v1_Iter;

   v1.push_back( 1 );
   v1.push_back( 2 );

   for ( v1_Iter = v1.begin( ) ; v1_Iter != v1.end( ) ; v1_Iter++ )
      cout << *v1_Iter << endl;
}
```

```Output
1
2
```

## <a name="erase"></a><a name="erase"></a>silme

Belirtilen konumlardan bir vektör içindeki öğe veya öğe aralığını kaldırır.

```cpp
iterator erase(
    const_iterator position);

iterator erase(
    const_iterator first,
    const_iterator last);
```

### <a name="parameters"></a>Parametreler

*yerine*\
Vektörden kaldırılacak öğenin konumu.

*adı*\
Vektörden çıkarılan ilk öğenin konumu.

*soyadına*\
Vektörden çıkarılan son öğenin hemen ötesinde konumlandır.

### <a name="return-value"></a>Dönüş Değeri

Kaldırılan tüm öğelerin ötesinde kalan ilk öğeyi veya böyle bir öğe yoksa vector öğesinin sonuna bir işaretçiyi atayan bir yineleyici.

### <a name="example"></a>Örnek

```cpp
// vector_erase.cpp
// compile with: /EHsc
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;
   vector <int> v1;
   vector <int>::iterator Iter;

   v1.push_back( 10 );
   v1.push_back( 20 );
   v1.push_back( 30 );
   v1.push_back( 40 );
   v1.push_back( 50 );

   cout << "v1 =" ;
   for ( Iter = v1.begin( ) ; Iter != v1.end( ) ; Iter++ )
      cout << " " << *Iter;
   cout << endl;

   v1.erase( v1.begin( ) );
   cout << "v1 =";
   for ( Iter = v1.begin( ) ; Iter != v1.end( ) ; Iter++ )
      cout << " " << *Iter;
   cout << endl;

   v1.erase( v1.begin( ) + 1, v1.begin( ) + 3 );
   cout << "v1 =";
   for ( Iter = v1.begin( ) ; Iter != v1.end( ) ; Iter++ )
      cout << " " << *Iter;
   cout << endl;
}
```

```Output
v1 = 10 20 30 40 50
v1 = 20 30 40 50
v1 = 20 50
```

## <a name="front"></a><a name="front"></a>yapılan

Vektördeki ilk öğeye bir başvuru döndürür.

```cpp
reference front();

const_reference front() const;
```

### <a name="return-value"></a>Dönüş Değeri

Vektör nesnesindeki ilk öğeye başvuru. Vektör boşsa, dönüş tanımsızdır.

### <a name="remarks"></a>Açıklamalar

Dönüş değeri `front` bir öğesine atanırsa `const_reference` , vektör nesnesi değiştirilemez. Dönüş değeri `front` bir **başvuruya**atanmışsa, vektör nesnesi değiştirilebilir.

1 veya 2 olarak tanımlanan [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md) kullanılarak derlendiğinde, boş bir vektörde bir öğeye erişmeyi denerseniz bir çalışma zamanı hatası oluşur. Daha fazla bilgi için bkz. [Checked Iterators](../standard-library/checked-iterators.md).

### <a name="example"></a>Örnek

```cpp
// vector_front.cpp
// compile with: /EHsc
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;
   vector <int> v1;

   v1.push_back( 10 );
   v1.push_back( 11 );

   int& i = v1.front( );
   const int& ii = v1.front( );

   cout << "The first integer of v1 is "<< i << endl;
   // by incrementing i, we move the front reference to the second element
   i++;
   cout << "Now, the first integer of v1 is "<< i << endl;
}
```

## <a name="get_allocator"></a><a name="get_allocator"></a>get_allocator

Vektörü oluşturmak için kullanılan ayırıcı nesnesinin bir kopyasını döndürür.

```cpp
Allocator get_allocator() const;
```

### <a name="return-value"></a>Dönüş Değeri

Vektör tarafından kullanılan ayırıcı.

### <a name="remarks"></a>Açıklamalar

Vector sınıfı için ayırıcılar, sınıfın depolamayı nasıl yönettiğini belirtir. C++ standart kitaplığı kapsayıcı sınıflarıyla birlikte sağlanan varsayılan ayrıcılar çoğu programlama ihtiyacı için yeterlidir. Kendi ayırıcı sınıfınızı yazmak ve kullanmak gelişmiş bir C++ özelliğidir.

### <a name="example"></a>Örnek

```cpp
// vector_get_allocator.cpp
// compile with: /EHsc
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;
   // The following lines declare objects that use the default allocator.
   vector<int> v1;
   vector<int, allocator<int> > v2 = vector<int, allocator<int> >(allocator<int>( )) ;

   // v3 will use the same allocator class as v1
   vector <int> v3( v1.get_allocator( ) );

   vector<int>::allocator_type xvec = v3.get_allocator( );
   // You can now call functions on the allocator class used by vec
}
```

## <a name="insert"></a><a name="insert"></a>ekleyin

Belirli bir konumda vektör içine bir öğe, dizi öğe veya öğe aralığı ekler.

```cpp
iterator insert(
    const_iterator position,
    const Type& value);

iterator insert(
    const_iterator position,
    Type&& value);

void insert(
    const_iterator position,
    size_type count,
    const Type& value);

template <class InputIterator>
void insert(
    const_iterator position,
    InputIterator first,
    InputIterator last);
```

### <a name="parameters"></a>Parametreler

*yerine*\
Vektördeki ilk öğenin eklendiği konum.

*deeri*\
Vektöre eklenmekte olan öğenin değeri.

*biriktirme*\
Vektöre eklenmekte olan öğe sayısı.

*adı*\
Kopyalanacak öğe aralığındaki ilk öğenin konumu.

*soyadına*\
Kopyalanacak öğe aralığının ötesinde ilk öğenin konumu.

### <a name="return-value"></a>Dönüş Değeri

İlk iki `insert` işlev, yeni öğenin vektöre eklendiği konuma işaret eden bir yineleyici döndürür.

### <a name="remarks"></a>Açıklamalar

Ön koşul olarak, *ilk* ve *son* , vektörde yineleyiciler olmamalıdır, aksi durumda davranış tanımsızdır. Herhangi bir ekleme işlemi pahalı olabilir, bir performans tartışması için [vektör sınıfına](../standard-library/vector-class.md) bakın `vector` .

### <a name="example"></a>Örnek

```cpp
// vector_insert.cpp
// compile with: /EHsc
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;
   vector <int> v1;
   vector <int>::iterator Iter;

   v1.push_back( 10 );
   v1.push_back( 20 );
   v1.push_back( 30 );

   cout << "v1 =" ;
   for ( Iter = v1.begin( ) ; Iter != v1.end( ) ; Iter++ )
      cout << " " << *Iter;
   cout << endl;

   v1.insert( v1.begin( ) + 1, 40 );
   cout << "v1 =";
   for ( Iter = v1.begin( ) ; Iter != v1.end( ) ; Iter++ )
      cout << " " << *Iter;
   cout << endl;
   v1.insert( v1.begin( ) + 2, 4, 50 );

   cout << "v1 =";
   for ( Iter = v1.begin( ) ; Iter != v1.end( ) ; Iter++ )
      cout << " " << *Iter;
   cout << endl;

   const auto v2 = v1;
   v1.insert( v1.begin( )+1, v2.begin( )+2, v2.begin( )+4 );
   cout << "v1 =";
   for (Iter = v1.begin( ); Iter != v1.end( ); Iter++ )
      cout << " " << *Iter;
   cout << endl;

// initialize a vector of vectors by moving v1
   vector < vector <int> > vv1;

   vv1.insert( vv1.begin(), move( v1 ) );
   if ( vv1.size( ) != 0 && vv1[0].size( ) != 0 )
      {
      cout << "vv1[0] =";
      for (Iter = vv1[0].begin( ); Iter != vv1[0].end( ); Iter++ )
         cout << " " << *Iter;
      cout << endl;
      }
}
```

```Output
v1 = 10 20 30
v1 = 10 40 20 30
v1 = 10 40 50 50 50 50 20 30
v1 = 10 50 50 40 50 50 50 50 20 30
vv1[0] = 10 50 50 40 50 50 50 50 20 30
```

## <a name="iterator"></a><a name="iterator"></a>iden

Vektördeki herhangi bir öğeyi okuyabilen veya değiştirebilen bir rasgele erişim yineleyicisi sağlayan bir tür.

```cpp
typedef implementation-defined iterator;
```

### <a name="remarks"></a>Açıklamalar

Bir tür **yineleyicisi** , bir öğenin değerini değiştirmek için kullanılabilir.

### <a name="example"></a>Örnek

[Begin](#begin)örneğine bakın.

## <a name="max_size"></a><a name="max_size"></a>max_size

Vektörün maksimum uzunluğunu döndürür.

```cpp
size_type max_size() const;
```

### <a name="return-value"></a>Dönüş Değeri

Vektörün olası en yüksek uzunluğu.

### <a name="example"></a>Örnek

```cpp
// vector_max_size.cpp
// compile with: /EHsc
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;
   vector <int> v1;
   vector <int>::size_type i;

   i = v1.max_size( );
   cout << "The maximum possible length of the vector is " << i << "." << endl;
}
```

## <a name="operator"></a><a name="op_at"></a>operator []

Vektör öğesine belirtilen konumda bir başvuru döndürür.

```cpp
reference operator[](size_type position);

const_reference operator[](size_type position) const;
```

### <a name="parameters"></a>Parametreler

*yerine*\
Vektör öğesinin konumu.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen konum kapsayıcısının boyutuna eşit veya ondan daha büyük ise, sonuç tanımsızdır.

### <a name="remarks"></a>Açıklamalar

Dönüş değeri `operator[]` bir öğesine atanırsa `const_reference` , vektör nesnesi değiştirilemez. Dönüş değeri `operator[]` bir başvuruya atanmışsa, vektör nesnesi değiştirilebilir.

1 veya 2 olarak tanımlanan [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md) kullanılarak derlendiğinde, vektör sınırları dışında bir öğeye erişmeyi denerseniz bir çalışma zamanı hatası oluşur. Daha fazla bilgi için bkz. [Checked Iterators](../standard-library/checked-iterators.md).

### <a name="example"></a>Örnek

```cpp
// vector_op_ref.cpp
// compile with: /EHsc
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;
   vector <int> v1;

   v1.push_back( 10 );
   v1.push_back( 20 );

   int& i = v1[1];
   cout << "The second integer of v1 is " << i << endl;
}
```

## <a name="operator"></a><a name="op_eq"></a>işleç =

Vektör öğelerini başka bir Vector kopyasıyla değiştirir.

```cpp
vector& operator=(const vector& right);

vector& operator=(vector&& right);
```

### <a name="parameters"></a>Parametreler

*Right*\
İçine Kopyalanmakta olan [vektör](../standard-library/vector-class.md) `vector` .

### <a name="remarks"></a>Açıklamalar

İçindeki varolan öğeleri sildikten sonra `vector` , ' `operator=` nin içeriğini kopyalar ya da içine *taşısa* `vector` .

### <a name="example"></a>Örnek

```cpp
// vector_operator_as.cpp
// compile with: /EHsc
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;
   vector<int> v1, v2, v3;
   vector<int>::iterator iter;

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
   v2 = move(v1);
   cout << "v2 = ";
   for (iter = v2.begin(); iter != v2.end(); iter++)
      cout << *iter << " ";
   cout << endl;
}
```

## <a name="pointer"></a><a name="pointer"></a>çağrısı

Vektörde bir öğeye işaretçi sağlayan bir tür.

```cpp
typedef typename Allocator::pointer pointer;
```

### <a name="remarks"></a>Açıklamalar

Bir tür **işaretçisi** bir öğenin değerini değiştirmek için kullanılabilir.

### <a name="example"></a>Örnek

```cpp
// vector_pointer.cpp
// compile with: /EHsc
#include <vector>
#include <iostream>

int main( )
{
    using namespace std;
    vector<int> v;
    v.push_back( 11 );
    v.push_back( 22 );

    vector<int>::pointer ptr = &v[0];
    cout << *ptr << endl;
    ptr++;
    cout << *ptr << endl;
    *ptr = 44;
    cout << *ptr << endl;
}
```

```Output
11
22
44
```

## <a name="pop_back"></a><a name="pop_back"></a>pop_back

Vektör sonundaki öğeyi siler.

```cpp
void pop_back();
```

### <a name="remarks"></a>Açıklamalar

Kod örneği için bkz. [vector::p ush_back ()](#push_back).

## <a name="push_back"></a><a name="push_back"></a>push_back

Vector öğesinin sonuna bir öğesi ekler.

```cpp
void push_back(const T& value);

void push_back(T&& value);
```

### <a name="parameters"></a>Parametreler

*deeri*\
Vektörün sonuna eklenen öğeye atanacak değer.

### <a name="example"></a>Örnek

```cpp
// compile with: /EHsc /W4
#include <vector>
#include <iostream>

using namespace std;

template <typename T> void print_elem(const T& t) {
    cout << "(" << t << ") ";
}

template <typename T> void print_collection(const T& t) {
    cout << "  " << t.size() << " elements: ";

    for (const auto& p : t) {
        print_elem(p);
    }
    cout << endl;
}

int main()
{
    vector<int> v;
    for (int i = 0; i < 10; ++i) {
        v.push_back(10 + i);
    }

    cout << "vector data: " << endl;
    print_collection(v);

    // pop_back() until it's empty, printing the last element as we go
    while (v.begin() != v.end()) {
        cout << "v.back(): "; print_elem(v.back()); cout << endl;
        v.pop_back();
    }
}
```

## <a name="rbegin"></a><a name="rbegin"></a>rbegin

Tersine çevrilmiş Vektördeki ilk öğeye bir yineleyici döndürür.

```cpp
reverse_iterator rbegin();
const_reverse_iterator rbegin() const;
```

### <a name="return-value"></a>Dönüş Değeri

Ters çevrilen bir vektör içindeki ilk öğeyi adresleyen veya geri alınamaz Vektördeki son öğe olduğunu ele almak için ters bir rastgele erişim Yineleyici.

### <a name="remarks"></a>Açıklamalar

Dönüş değeri `rbegin` bir öğesine atanırsa `const_reverse_iterator` , vektör nesnesi değiştirilemez. Dönüş değeri `rbegin` öğesine atanırsa `reverse_iterator` , vektör nesnesi değiştirilebilir.

### <a name="example"></a>Örnek

```cpp
// vector_rbegin.cpp
// compile with: /EHsc
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;
   vector <int> v1;
   vector <int>::iterator v1_Iter;
   vector <int>::reverse_iterator v1_rIter;

   v1.push_back( 1 );
   v1.push_back( 2 );

   v1_Iter = v1.begin( );
   cout << "The first element of vector is "
        << *v1_Iter << "." << endl;

   v1_rIter = v1.rbegin( );
   cout << "The first element of the reversed vector is "
        << *v1_rIter << "." << endl;
}
```

```Output
The first element of vector is 1.
The first element of the reversed vector is 2.
```

## <a name="reference"></a><a name="reference"></a>başvurunun

Vektörde depolanan bir öğeye başvuru sağlayan bir tür.

```cpp
typedef typename Allocator::reference reference;
```

### <a name="example"></a>Örnek

Vector sınıfında **başvurunun** nasıl [kullanılacağına ilişkin bir örnek için bkz](#at) ..

## <a name="rend"></a><a name="rend"></a>rend

Ters çevrilen Vektördeki son öğeden sonraki konumu ele alan bir yineleyici döndürür.

```cpp
const_reverse_iterator rend() const;
reverse_iterator rend();
```

### <a name="return-value"></a>Dönüş Değeri

Ters çevrilen bir vektör içindeki son öğeden sonra gelen konumu ele alan ters bir rastgele erişim yineleyici (geri alınamaz vektörde ilk öğeden önce gelen konum).

### <a name="remarks"></a>Açıklamalar

`rend`[son](#end) olarak bir Vector ile kullanıldığı gibi tersine çevrilmiş bir vektörle kullanılır.

Öğesinin dönüş değeri `rend` öğesine atanmışsa `const_reverse_iterator` , vektör nesnesi değiştirilemez. Dönüş değeri `rend` bir öğesine atanırsa `reverse_iterator` , vektör nesnesi değiştirilebilir.

`rend`, bir ters yineleyicinin vektörünün sonuna ulaşıp ulaşılmadığını test etmek için kullanılabilir.

Tarafından döndürülen değer `rend` başvurulmamalıdır. Yalnızca karşılaştırma için kullanın.

### <a name="example"></a>Örnek

```cpp
// vector_rend.cpp
// compile with: /EHsc
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;
   vector <int> v1;
   vector <int>::reverse_iterator v1_rIter;

   v1.push_back( 1 );
   v1.push_back( 2 );

   for ( v1_rIter = v1.rbegin( ) ; v1_rIter != v1.rend( ) ; v1_rIter++ )
      cout << *v1_rIter << endl;
}
```

```Output
2
1
```

## <a name="reserve"></a><a name="reserve"></a>ayırmaya

Bir vektör nesnesi için en az bir depolama uzunluğu ayırır ve gerekirse boşluk ayırır.

```cpp
void reserve(size_type count);
```

### <a name="parameters"></a>Parametreler

*biriktirme*\
Vektör için ayrılacak en düşük depolama alanı uzunluğu.

### <a name="example"></a>Örnek

```cpp
// vector_reserve.cpp
// compile with: /EHsc
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;
   vector <int> v1;
   //vector <int>::iterator Iter;

   v1.push_back( 1 );
   cout << "Current capacity of v1 = "
      << v1.capacity( ) << endl;
   v1.reserve( 20 );
   cout << "Current capacity of v1 = "
      << v1.capacity( ) << endl;
}
```

```Output
Current capacity of v1 = 1
Current capacity of v1 = 20
```

## <a name="resize"></a><a name="resize"></a>yeniden boyutlandırma

Bir vektör için yeni bir boyut belirtir.

```cpp
void resize(size_type new_size);
void resize(size_type new_size, Type value);
```

### <a name="parameters"></a>Parametreler

*new_size*\
Vector öğesinin yeni boyutu.

*deeri*\
Yeni boyut orijinal boyuttan daha büyükse, vektöre eklenen yeni öğelerin başlatma değeri. Değer atlanırsa, yeni nesneler varsayılan oluşturucusunu kullanır.

### <a name="remarks"></a>Açıklamalar

Kapsayıcının boyutu istenen boyuttan küçükse *new_size*, `resize` istenen boyuta ulaşıncaya kadar vektöre öğe ekler. Kapsayıcının boyutu istenen boyuttan daha büyükse, `resize` *new_size*boyutuna ulaşana kadar kapsayıcının sonuna en yakın olan öğeleri siler. Kapsayıcının mevcut boyutu istenen boyutla aynı ise hiçbir eylem yapılmaz.

[Boyut](#size) , vektörün geçerli boyutunu yansıtır.

### <a name="example"></a>Örnek

```cpp
// vectorsizing.cpp
// compile with: /EHsc /W4
// Illustrates vector::reserve, vector::max_size,
// vector::resize, vector::resize, and vector::capacity.
//
// Functions:
//
//    vector::max_size - Returns maximum number of elements vector could
//                       hold.
//
//    vector::capacity - Returns number of elements for which memory has
//                       been allocated.
//
//    vector::size - Returns number of elements in the vector.
//
//    vector::resize - Reallocates memory for vector, preserves its
//                     contents if new size is larger than existing size.
//
//    vector::reserve - Allocates elements for vector to ensure a minimum
//                      size, preserving its contents if the new size is
//                      larger than existing size.
//
//    vector::push_back - Appends (inserts) an element to the end of a
//                        vector, allocating memory for it if necessary.
//
//////////////////////////////////////////////////////////////////////

// The debugger cannot handle symbols more than 255 characters long.
// The C++ Standard Library often creates symbols longer than that.
// The warning can be disabled:
//#pragma warning(disable:4786)

#include <iostream>
#include <vector>
#include <string>

using namespace std;

template <typename C> void print(const string& s, const C& c) {
    cout << s;

    for (const auto& e : c) {
        cout << e << " ";
    }
    cout << endl;
}

void printvstats(const vector<int>& v) {
    cout << "   the vector's size is: " << v.size() << endl;
    cout << "   the vector's capacity is: " << v.capacity() << endl;
    cout << "   the vector's maximum size is: " << v.max_size() << endl;
}

int main()
{
    // declare a vector that begins with 0 elements.
    vector<int> v;

    // Show statistics about vector.
    cout << endl << "After declaring an empty vector:" << endl;
    printvstats(v);
    print("   the vector's contents: ", v);

    // Add one element to the end of the vector.
    v.push_back(-1);
    cout << endl << "After adding an element:" << endl;
    printvstats(v);
    print("   the vector's contents: ", v);

    for (int i = 1; i < 10; ++i) {
        v.push_back(i);
    }
    cout << endl << "After adding 10 elements:" << endl;
    printvstats(v);
    print("   the vector's contents: ", v);

    v.resize(6);
    cout << endl << "After resizing to 6 elements without an initialization value:" << endl;
    printvstats(v);
    print("   the vector's contents: ", v);

    v.resize(9, 999);
    cout << endl << "After resizing to 9 elements with an initialization value of 999:" << endl;
    printvstats(v);
    print("   the vector's contents: ", v);

    v.resize(12);
    cout << endl << "After resizing to 12 elements without an initialization value:" << endl;
    printvstats(v);
    print("   the vector's contents: ", v);

    // Ensure there's room for at least 1000 elements.
    v.reserve(1000);
    cout << endl << "After vector::reserve(1000):" << endl;
    printvstats(v);

    // Ensure there's room for at least 2000 elements.
    v.resize(2000);
    cout << endl << "After vector::resize(2000):" << endl;
    printvstats(v);
}
```

## <a name="reverse_iterator"></a><a name="reverse_iterator"></a>reverse_iterator

Tersine çevrilmiş Vektördeki herhangi bir öğeyi okuyabilen veya değiştirebilen bir rasgele erişim yineleyicisi sağlayan bir tür.

```cpp
typedef std::reverse_iterator<iterator> reverse_iterator;
```

### <a name="remarks"></a>Açıklamalar

Bir tür `reverse_iterator` , geriye doğru vektör üzerinden yinelemek için kullanılır.

### <a name="example"></a>Örnek

[Rbegin](#rbegin)örneğine bakın.

## <a name="shrink_to_fit"></a><a name="shrink_to_fit"></a>shrink_to_fit

Fazla kapasiteyi atar.

```cpp
void shrink_to_fit();
```

### <a name="example"></a>Örnek

```cpp
// vector_shrink_to_fit.cpp
// compile with: /EHsc
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;
   vector <int> v1;
   //vector <int>::iterator Iter;

   v1.push_back( 1 );
   cout << "Current capacity of v1 = "
      << v1.capacity( ) << endl;
   v1.reserve( 20 );
   cout << "Current capacity of v1 = "
      << v1.capacity( ) << endl;
   v1.shrink_to_fit();
   cout << "Current capacity of v1 = "
      << v1.capacity( ) << endl;
}
```

```Output
Current capacity of v1 = 1
Current capacity of v1 = 20
Current capacity of v1 = 1
```

## <a name="size"></a><a name="size"></a>boyutla

Vektördeki öğe sayısını döndürür.

```cpp
size_type size() const;
```

### <a name="return-value"></a>Dönüş Değeri

Vektörün geçerli uzunluğu.

### <a name="example"></a>Örnek

```cpp
// vector_size.cpp
// compile with: /EHsc
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;
   vector <int> v1;
   vector <int>::size_type i;

   v1.push_back( 1 );
   i = v1.size( );
   cout << "Vector length is " << i << "." << endl;

   v1.push_back( 2 );
   i = v1.size( );
   cout << "Vector length is now " << i << "." << endl;
}
```

```Output
Vector length is 1.
Vector length is now 2.
```

## <a name="size_type"></a><a name="size_type"></a>size_type

Vektördeki öğelerin sayısını sayan bir tür.

```cpp
typedef typename Allocator::size_type size_type;
```

### <a name="example"></a>Örnek

[Kapasite](#capacity)örneğine bakın.

## <a name="swap"></a><a name="swap"></a>Kur

İki vektörün öğelerini değiş tokuş eder.

```cpp
void swap(
    vector<Type, Allocator>& right);

friend void swap(
    vector<Type, Allocator>& left,
    vector<Type, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*Right*\
Takas edilecek öğeleri sağlayan bir vektör. Ya da öğeleri vektörde bulunan öğelerle birlikte değiş tokuş edilecek bir *vektör.*

*tarafta*\
Öğeleri vektör *sağ*içindeki öğelerle birlikte alışverişi yapılacak bir vektör.

### <a name="example"></a>Örnek

```cpp
// vector_swap.cpp
// compile with: /EHsc
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;
   vector <int> v1, v2;

   v1.push_back( 1 );
   v1.push_back( 2 );
   v1.push_back( 3 );

   v2.push_back( 10 );
   v2.push_back( 20 );

   cout << "The number of elements in v1 = " << v1.size( ) << endl;
   cout << "The number of elements in v2 = " << v2.size( ) << endl;
   cout << endl;

   v1.swap( v2 );

   cout << "The number of elements in v1 = " << v1.size( ) << endl;
   cout << "The number of elements in v2 = " << v2.size( ) << endl;
}
```

```Output
The number of elements in v1 = 3
The number of elements in v2 = 2

The number of elements in v1 = 2
The number of elements in v2 = 3
```

## <a name="value_type"></a><a name="value_type"></a>value_type

Vektörde depolanan veri türünü temsil eden bir tür.

```cpp
typedef typename Allocator::value_type value_type;
```

### <a name="remarks"></a>Açıklamalar

`value_type`, şablon parametresinin eşanlamlısıdır `Type` .

### <a name="example"></a>Örnek

```cpp
// vector_value_type.cpp
// compile with: /EHsc
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;
   vector<int>::value_type AnInt;
   AnInt = 44;
   cout << AnInt << endl;
}
```

```Output
44
```

## <a name="vector"></a><a name="vector"></a>vektör

Bir vektör oluşturur. Aşırı yüklemeler belirli bir boyut veya belirli bir değer öğeleriyle bir vektör oluşturur. Ya da başka bir vektörün tümünün veya bir kısmının kopyası olarak. Bazı aşırı yüklemeler, kullanılacak ayırıcıyı belirtmenize de olanak tanır.

```cpp
vector();
explicit vector(const Allocator& allocator);
explicit vector(size_type count);
vector(size_type count, const Type& value);
vector(size_type count, const Type& value, const Allocator& allocator);

vector(const vector& source);
vector(vector&& source);
vector(initializer_list<Type> init_list, const Allocator& allocator);

template <class InputIterator>
vector(InputIterator first, InputIterator last);
template <class InputIterator>
vector(InputIterator first, InputIterator last, const Allocator& allocator);
```

### <a name="parameters"></a>Parametreler

*öğe*\
Bu nesneyle kullanılacak kaynak ayırıcı sınıfı. [get_allocator](#get_allocator) nesnenin ayırıcı sınıfını döndürür.

*biriktirme*\
Oluşturulan Vektördeki öğe sayısı.

*deeri*\
Oluşturulan Vektördeki öğelerin değeri.

*kaynaktaki*\
Oluşturulan vektörün bir kopya olması gereken vektör.

*adı*\
Kopyalanacak öğe aralığındaki ilk öğenin konumu.

*soyadına*\
Kopyalanacak öğe aralığının ötesinde ilk öğenin konumu.

*init_list*\
`initializer_list`Kopyalanacak öğeleri içerir.

### <a name="remarks"></a>Açıklamalar

Tüm oluşturucular bir ayırıcı nesne (*ayırıcı*) depolar ve vektörü başlatır.

İlk iki Oluşturucu boş bir ilk vektör belirtir. İkinci Oluşturucu açık olarak kullanılacak ayırıcı türünü (*ayırıcı*) belirtir.

Üçüncü Oluşturucu, sınıfının varsayılan değeri için belirtilen sayının (*Count*) bir tekrarını belirtir `Type` .

Dördüncü ve beşinci oluşturucular değer *değerinin*(*Count*) bir tekrarından oluşan bir yineleme belirtir.

Altıncı Oluşturucu vektör *kaynağının*bir kopyasını belirtir.

Yedinci Oluşturucu vektör *kaynağını*taşımaktır.

Sekizinci Oluşturucu öğeleri belirtmek için bir initializer_list kullanır.

Dokuzuncu ve onuncu oluşturucular, `first` `last` bir vektörün aralığını [,) kopyalar.

### <a name="example"></a>Örnek

```cpp
// vector_ctor.cpp
// compile with: /EHsc
#include <vector>
#include <iostream>

int main()
{
    using namespace std;
    vector <int>::iterator v1_Iter, v2_Iter, v3_Iter, v4_Iter, v5_Iter, v6_Iter;

    // Create an empty vector v0
    vector <int> v0;

    // Create a vector v1 with 3 elements of default value 0
    vector <int> v1(3);

    // Create a vector v2 with 5 elements of value 2
    vector <int> v2(5, 2);

    // Create a vector v3 with 3 elements of value 1 and with the allocator
    // of vector v2
    vector <int> v3(3, 1, v2.get_allocator());

    // Create a copy, vector v4, of vector v2
    vector <int> v4(v2);

    // Create a new temporary vector for demonstrating copying ranges
    vector <int> v5(5);
    for (auto i : v5) {
        v5[i] = i;
    }

    // Create a vector v6 by copying the range v5[ first,  last)
    vector <int> v6(v5.begin() + 1, v5.begin() + 3);

    cout << "v1 =";
    for (auto& v : v1){
        cout << " " << v;
    }
    cout << endl;

    cout << "v2 =";
    for (auto& v : v2){
        cout << " " << v;
    }
    cout << endl;

    cout << "v3 =";
    for (auto& v : v3){
        cout << " " << v;
    }
    cout << endl;
    cout << "v4 =";
    for (auto& v : v4){
        cout << " " << v;
    }
    cout << endl;

    cout << "v5 =";
    for (auto& v : v5){
        cout << " " << v;
    }
    cout << endl;

    cout << "v6 =";
    for (auto& v : v6){
        cout << " " << v;
    }
    cout << endl;

    // Move vector v2 to vector v7
    vector <int> v7(move(v2));
    vector <int>::iterator v7_Iter;

    cout << "v7 =";
    for (auto& v : v7){
        cout << " " << v;
    }
    cout << endl;

    vector<int> v8{ { 1, 2, 3, 4 } };
    for (auto& v : v8){
        cout << " " << v ;
    }
    cout << endl;
}
```

```Output
v1 = 0 0 0v2 = 2 2 2 2 2v3 = 1 1 1v4 = 2 2 2 2 2v5 = 0 1 2 3 4v6 = 1 2v7 = 2 2 2 2 21 2 3 4
```

## <a name="see-also"></a>Ayrıca bkz.

[C++ standart kitaplığı 'nda iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[C++ standart kitaplığı başvurusu](../standard-library/cpp-standard-library-reference.md)
