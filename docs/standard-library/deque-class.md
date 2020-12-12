---
description: 'Daha fazla bilgi edinin: deque Class'
title: deque Sınıfı
ms.date: 11/04/2016
f1_keywords:
- deque/std::deque
- deque/std::deque::allocator_type
- deque/std::deque::const_iterator
- deque/std::deque::const_pointer
- deque/std::deque::const_reference
- deque/std::deque::const_reverse_iterator
- deque/std::deque::difference_type
- deque/std::deque::iterator
- deque/std::deque::pointer
- deque/std::deque::reference
- deque/std::deque::reverse_iterator
- deque/std::deque::size_type
- deque/std::deque::value_type
- deque/std::deque::assign
- deque/std::deque::at
- deque/std::deque::back
- deque/std::deque::begin
- deque/std::deque::cbegin
- deque/std::deque::cend
- deque/std::deque::clear
- deque/std::deque::crbegin
- deque/std::deque::crend
- deque/std::deque::emplace
- deque/std::deque::emplace_back
- deque/std::deque::emplace_front
- deque/std::deque::empty
- deque/std::deque::end
- deque/std::deque::erase
- deque/std::deque::front
- deque/std::deque::get_allocator
- deque/std::deque::insert
- deque/std::deque::max_size
- deque/std::deque::pop_back
- deque/std::deque::pop_front
- deque/std::deque::push_back
- deque/std::deque::push_front
- deque/std::deque::rbegin
- deque/std::deque::rend
- deque/std::deque::resize
- deque/std::deque::shrink_to_fit
- deque/std::deque::size
- deque/std::deque::swap
helpviewer_keywords:
- std::deque [C++]
- std::deque [C++], allocator_type
- std::deque [C++], const_iterator
- std::deque [C++], const_pointer
- std::deque [C++], const_reference
- std::deque [C++], const_reverse_iterator
- std::deque [C++], difference_type
- std::deque [C++], iterator
- std::deque [C++], pointer
- std::deque [C++], reference
- std::deque [C++], reverse_iterator
- std::deque [C++], size_type
- std::deque [C++], value_type
- std::deque [C++], assign
- std::deque [C++], at
- std::deque [C++], back
- std::deque [C++], begin
- std::deque [C++], cbegin
- std::deque [C++], cend
- std::deque [C++], clear
- std::deque [C++], crbegin
- std::deque [C++], crend
- std::deque [C++], emplace
- std::deque [C++], emplace_back
- std::deque [C++], emplace_front
- std::deque [C++], empty
- std::deque [C++], end
- std::deque [C++], erase
- std::deque [C++], front
- std::deque [C++], get_allocator
- std::deque [C++], insert
- std::deque [C++], max_size
- std::deque [C++], pop_back
- std::deque [C++], pop_front
- std::deque [C++], push_back
- std::deque [C++], push_front
- std::deque [C++], rbegin
- std::deque [C++], rend
- std::deque [C++], resize
- std::deque [C++], shrink_to_fit
- std::deque [C++], size
- std::deque [C++], swap
ms.assetid: 64842ee5-057a-4063-8c16-4267a0332584
ms.openlocfilehash: f46c3c31dd23f7603a1d4ef6289e435c9b38e823
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97324581"
---
# <a name="deque-class"></a>deque Sınıfı

Belirli bir türün öğelerini doğrusal bir düzenlemede ve vektör gibi, herhangi bir öğeye hızlı bir şekilde rastgele erişim sağlar ve kapsayıcının arkasında etkili ekleme ve silme işlemi yapılır. Ancak, vector öğesinin aksine, `deque` sınıf kapsayıcının önündeki etkin ekleme ve silme işlemini de destekler.

## <a name="syntax"></a>Sözdizimi

```unstlib
template <class Type, class Allocator =allocator<Type>>
class deque
```

### <a name="parameters"></a>Parametreler

*Türüyle*\
Deque içinde depolanacak öğe veri türü.

*Öğe*\
Belleğin ayrılma ve ayırmayı kaldırma hakkındaki ayrıntıları kapsülleyen saklı ayırıcı nesnesini temsil eden tür. Bu bağımsız değişken isteğe bağlıdır ve varsayılan değer **ayırıcı \<Type>**' dır.

## <a name="remarks"></a>Açıklamalar

Kapsayıcı türünün seçimi genelde uygulamanın gerektirdiği arama ve ekleme türüne dayalı olmalıdır. Herhangi bir öğeye rastgele erişim bir Premium olduğunda ve öğe eklemeleri veya silinmeleri yalnızca bir sıranın sonunda gerekliyse, [vektörlerin](../standard-library/vector-class.md) yönetilmesi için tercih edilen kapsayıcı olmalıdır. Sıra içinde herhangi bir konumda etkili eklemeler ve silmeler (Sabit zamanlı) olduğunda liste kapsayıcısının performansı üstün bir yoldur. Sıranın ortasında bu gibi işlemler, öğe kopyaları ve atamaların dizideki öğelerin sayısıyla orantılı (doğrusal saat) olmasını gerektirir.

Bir üye işlevi, sıranın öğelerini eklemesi veya silmeniz gerektiğinde, deque yeniden ayırma gerçekleşir:

- Bir öğe boş bir diziye eklenirse veya bir öğe boş bir sıra bırakmak üzere silinirse, daha önce [BEGIN](#begin) ve [End](#end) tarafından döndürülen yineleyiciler geçersiz olur.

- Bir öğe, deque 'ın ilk konumuna eklenirse, tüm yineleyiciler, ancak var olan öğeleri belirten hiçbir başvuru, geçersiz hale gelir.

- Bir öğe, deque 'ın sonuna eklenirse, [son](#end) ve tüm yineleyiciler, ancak var olan öğeleri belirten hiçbir başvuru yok olur.

- Bir öğe deque 'ın önünde silinirse, yalnızca bu yineleyici ve silinen öğeye yapılan başvurular geçersiz olur.

- Son öğe, deque 'ın sonundan silinirse, yalnızca son öğe için olan yineleyici ve silinen öğeye yapılan başvurular geçersiz olur.

Aksi takdirde, bir öğe eklemek veya silmek tüm yineleyiciler ve başvuruları geçersiz kılar.

## <a name="members"></a>Üyeler

### <a name="constructors"></a>Oluşturucular

|Ad|Açıklama|
|-|-|
|[deque](#deque)|Bir oluşturur `deque` . Yeni ' nin içeriğini farklı yollarla ayarlamak için çeşitli oluşturucular verilmiştir `deque` : Empty; belirtilen sayıda boş öğe ile yüklendi; içerik taşınmış ya da kopyalanmış; bir `deque` Yineleyici kullanılarak kopyalanmış ya da taşınmış içerikler ve saatlere kopyalanmış bir öğe `deque` `count` . Kuruculardan bazıları, `allocator` öğeleri oluşturmak için özel kullanımı etkinleştirir.|

### <a name="typedefs"></a>Tür tanımları

|Ad|Açıklama|
|-|-|
|[allocator_type](#allocator_type)|Nesnenin sınıfını temsil eden bir tür `allocator` `deque` .|
|[const_iterator](#const_iterator)|As içindeki öğelere erişebilen ve okuyabilen bir rastgele erişim yineleyici sağlayan bir tür `deque`**`const`**|
|[const_pointer](#const_pointer)|İçindeki bir öğe için bir işaretçi sağlayan bir tür `deque``const.`|
|[const_reference](#const_reference)|`deque`Okuma ve diğer işlemler için bir öğesine başvuru sağlayan bir tür`const.`|
|[const_reverse_iterator](#const_reverse_iterator)|As içindeki öğelere erişebilen ve okuyabilen bir rastgele erişim yineleyici sağlayan bir tür `deque` **`const`** . Deque, ters ' de görüntülenir. Daha fazla bilgi için bkz. [reverse_iterator sınıfı](../standard-library/reverse-iterator-class.md)|
|[difference_type](#difference_type)|Aynı olan öğelere başvuran iki rastgele erişim yineleyiciler arasındaki farkı sağlayan bir tür `deque` .|
|[iden](#iterator)|İçindeki herhangi bir öğeyi okuyabilen veya değiştirebilen bir rastgele erişim yineleyici sağlayan bir tür `deque` .|
|[pointer](#pointer)|İçindeki bir öğeye işaretçi sağlayan bir tür `deque` .|
|[başvurunun](#reference)|İçinde depolanan bir öğeye başvuru sağlayan bir tür `deque` .|
|[reverse_iterator](#reverse_iterator)|İçindeki bir öğeyi okuyabilen veya değiştirebilen bir rastgele erişim yineleyici sağlayan bir tür `deque` . Deque ters sırada görüntülenir.|
|[size_type](#size_type)|İçindeki öğe sayısını sayan bir tür `deque` .|
|[value_type](#value_type)|İçinde depolanan veri türünü temsil eden bir tür `deque` .|

### <a name="functions"></a>İşlevler

|Ad|Açıklama|
|-|-|
|[assign (atamak)](#assign) |Öğelerinden öğeleri siler `deque` ve yeni bir öğe dizisini hedefe kopyalar `deque` .|
|[hızı](#at)|İçinde belirtilen konumdaki öğesine bir başvuru döndürür `deque` .|
|[Geri](#back)|Öğesinin son öğesine bir başvuru döndürür `deque` .|
|[başladı](#begin)|İçindeki ilk öğeyi ele alarak rastgele erişimli bir yineleyici döndürür `deque` .|
|[cbegin](#cbegin)|İçindeki ilk öğeye bir const yineleyici döndürür `deque` .|
|[cend](#cend)|**`const`** Yalnızca sonunu işaret eden bir rastgele erişim yineleyici döndürür `deque` .|
|[lediğiniz](#clear)|Tüm öğelerini siler `deque` .|
|[crbegin](#crbegin)|Ters sırada görüntülenen ilk öğeye Rastgele erişimli bir const yineleyici döndürür `deque` .|
|[crend](#crend)|Ters sırada görüntülenen ilk öğeye Rastgele erişimli bir const yineleyici döndürür `deque` .|
|[Emplace](#emplace)|Belirtilen konumda içine oluşturulmuş bir öğe ekler `deque` .|
|[emplace_back](#emplace_back)|' Nin sonuna yerinde oluşturulmuş bir öğe ekler `deque` .|
|[emplace_front](#emplace_front)|Öğesinin başlangıcına yerinde oluşturulmuş bir öğe ekler `deque` .|
|[empty](#empty)|**`true`** `deque` Sıfır öğe içeriyorsa ve **`false`** bir veya daha fazla öğe içeriyorsa döndürür.|
|[erer](#end)|Yalnızca sonunu işaret eden bir rastgele erişim yineleyici döndürür `deque` .|
|[silme](#erase)|Belirtilen konumlardan bir öğeyi veya öğe aralığını kaldırır `deque` .|
|[yapılan](#front)|İçindeki ilk öğeye bir başvuru döndürür `deque` .|
|[get_allocator](#get_allocator)|`allocator`Oluşturmak için kullanılan nesnesinin bir kopyasını döndürür `deque` .|
|[ekleyin](#insert)|Belirtilen konuma bir öğe, birkaç öğe veya öğe aralığı ekler `deque` .|
|[max_size](#max_size)|Olası en yüksek uzunluğu döndürür `deque` .|
|[pop_back](#pop_back)|Öğesinin sonundaki öğeyi siler `deque` .|
|[pop_front](#pop_front)|Öğesinin başlangıcında öğesini siler `deque` .|
|[push_back](#push_back)|Sonuna bir öğesi ekler `deque` .|
|[push_front](#push_front)|Öğesinin başlangıcına bir öğesi ekler `deque` .|
|[rbegin](#rbegin)|Ters çevrilen ilk öğeye Rastgele erişimli bir yineleyici döndürür `deque` .|
|[rend](#rend)|Ters çevrilen son öğenin hemen ötesine işaret eden bir rastgele erişim yineleyicisi döndürür `deque` .|
|[yeniden boyutlandırma](#resize)|İçin yeni bir boyut belirtir `deque` .|
|[shrink_to_fit](#shrink_to_fit)|Fazla kapasiteyi atar.|
|[boyutla](#size)|İçindeki öğelerin sayısını döndürür `deque` .|
|[Kur](#swap)|İki öğenin öğelerini değiş tokuş eder `deque` .|

### <a name="operators"></a>İşleçler

|Ad|Açıklama|
|-|-|
|[işleç&#91;&#93;](#op_at)|`deque`Belirtilen konumdaki öğeye bir başvuru döndürür.|
|[işleç =](#op_eq)|Öğesinin öğelerini `deque` başka bir kopyasıyla değiştirir `deque` .|

## <a name="allocator_type"></a><a name="allocator_type"></a> allocator_type

Deque nesnesinin ayırıcı sınıfını temsil eden bir tür.

```cpp
typedef Allocator allocator_type;
```

### <a name="remarks"></a>Açıklamalar

`allocator_type` , şablon parametresinin eşanlamlısıdır `Allocator` .

### <a name="example"></a>Örnek

[Get_allocator](#get_allocator)için örneğe bakın.

## <a name="assign"></a><a name="assign"></a> ata

Bir deque öğelerini siler ve yeni bir öğe kümesini hedef Deke kopyalar.

```cpp
template <class InputIterator>
void assign(
    InputIterator First,
    InputIterator Last);

void assign(
    size_type Count,
    const Type& Val);

void assign(initializer_list<Type> IList);
```

### <a name="parameters"></a>Parametreler

*Adı*\
Bağımsız değişkenden kopyalanacak öğe aralığındaki ilk öğenin konumu.

*Soyadına*\
Bağımsız değişkenden kopyalanacak öğe aralığının ötesinde ilk öğenin konumu.

*Biriktirme*\
Deque 'a eklenmekte olan bir öğenin kopya sayısı.

*Acil*\
Deque içine eklenmekte olan öğenin değeri.

*IList*\
İnitializer_list, deque 'a eklenmekte.

### <a name="remarks"></a>Açıklamalar

Hedef parçalandığında var olan herhangi bir öğe silindikten sonra, `assign` Özgün deque 'dan veya başka bir değerden belirli bir öğe aralığını hedef deque içine ekler ya da belirtilen bir değerin yeni bir öğesinin kopyasını hedef deque içine ekler.

### <a name="example"></a>Örnek

```cpp
// deque_assign.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>
#include <initializer_list>

int main()
{
    using namespace std;
    deque <int> c1, c2;
    deque <int>::const_iterator cIter;

    c1.push_back(10);
    c1.push_back(20);
    c1.push_back(30);
    c2.push_back(40);
    c2.push_back(50);
    c2.push_back(60);

    deque<int> d1{ 1, 2, 3, 4 };
    initializer_list<int> iList{ 5, 6, 7, 8 };
    d1.assign(iList);

    cout << "d1 = ";
    for (int i : d1)
        cout << i;
    cout << endl;

    cout << "c1 =";
    for (int i : c1)
        cout << i;
    cout << endl;

    c1.assign(++c2.begin(), c2.end());
    cout << "c1 =";
    for (int i : c1)
        cout << i;
    cout << endl;

    c1.assign(7, 4);
    cout << "c1 =";
    for (int i : c1)
        cout << i;
    cout << endl;
}
```

```Output
d1 = 5678c1 =102030c1 =5060c1 =4444444
```

## <a name="at"></a><a name="at"></a> hızı

Deque 'da belirtilen konumdaki öğeye bir başvuru döndürür.

```cpp
reference at(size_type pos);

const_reference at(size_type pos) const;
```

### <a name="parameters"></a>Parametreler

*'un*\
Deque içinde başvurulacak öğenin alt indisi (veya konum numarası).

### <a name="return-value"></a>Dönüş Değeri

*POS* , deque 'ın boyutundan büyükse `at` bir özel durum oluşturur.

### <a name="return-value"></a>Dönüş Değeri

Dönüş değeri `at` öğesine atanırsa `const_reference` , deque nesnesi değiştirilemez. Dönüş değeri `at` öğesine atanırsa `reference` , deque nesnesi değiştirilebilir.

### <a name="example"></a>Örnek

```cpp
// deque_at.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>

int main( )
{
   using namespace std;
   deque <int> c1;

   c1.push_back( 10 );
   c1.push_back( 20 );

   const int& i = c1.at( 0 );
   int& j = c1.at( 1 );
   cout << "The first element is " << i << endl;
   cout << "The second element is " << j << endl;
}
```

```Output
The first element is 10
The second element is 20
```

## <a name="back"></a><a name="back"></a> Geri

Deque 'in son öğesine bir başvuru döndürür.

```cpp
reference back();
const_reference back() const;
```

### <a name="return-value"></a>Dönüş Değeri

Deque 'ın son öğesi. Deque boşsa, dönüş değeri tanımsızdır.

### <a name="remarks"></a>Açıklamalar

Dönüş değeri `back` öğesine atanırsa `const_reference` , deque nesnesi değiştirilemez. Dönüş değeri `back` öğesine atanırsa `reference` , deque nesnesi değiştirilebilir.

1 veya 2 olarak tanımlanan [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md) kullanılarak derlendiğinde, boş bir deque içindeki bir öğeye erişmeyi denerseniz bir çalışma zamanı hatası oluşur.  Daha fazla bilgi için bkz. [Checked Iterators](../standard-library/checked-iterators.md) .

### <a name="example"></a>Örnek

```cpp
// deque_back.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>

int main( )
{
   using namespace std;
   deque <int> c1;

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

Deque içindeki ilk öğeyi adresleyen bir yineleyici döndürür.

```cpp
const_iterator begin() const;
iterator begin();
```

### <a name="return-value"></a>Dönüş Değeri

Deque içindeki ilk öğeyi veya boş bir deque 'ı izleyen konumu ele alarak rastgele erişimli bir yineleyici.

### <a name="remarks"></a>Açıklamalar

Dönüş değeri `begin` öğesine atanırsa `const_iterator` , deque nesnesi değiştirilemez. Dönüş değeri `begin` bir öğesine atanırsa `iterator` , deque nesnesi değiştirilebilir.

### <a name="example"></a>Örnek

```cpp
// deque_begin.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>

int main( )
{
   using namespace std;
   deque <int> c1;
   deque <int>::iterator c1_Iter;
   deque <int>::const_iterator c1_cIter;

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

## <a name="cend"></a><a name="cend"></a> cend

**`const`** Bir aralıktaki son öğenin ötesinde konumu ele alan bir yineleyici döndürür.

```cpp
const_iterator cend() const;
```

### <a name="return-value"></a>Dönüş Değeri

Aralığın hemen sonunu gösteren bir rastgele erişim yineleyicisi.

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

Bir deque öğesinin tüm öğelerini siler.

```cpp
void clear();
```

### <a name="example"></a>Örnek

```cpp
// deque_clear.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>

int main( )
{
   using namespace std;
   deque <int> c1;

   c1.push_back( 10 );
   c1.push_back( 20 );
   c1.push_back( 30 );

   cout << "The size of the deque is initially " << c1.size( ) << endl;
   c1.clear( );
   cout << "The size of the deque after clearing is " << c1.size( ) << endl;
}
```

```Output
The size of the deque is initially 3
The size of the deque after clearing is 0
```

## <a name="const_iterator"></a><a name="const_iterator"></a> const_iterator

Deque içindeki bir öğeye erişebilen ve okuyabilen bir rastgele erişim yineleyici sağlayan bir tür **`const`** .

```cpp
typedef implementation-defined const_iterator;
```

### <a name="remarks"></a>Açıklamalar

Bir tür `const_iterator` , bir öğenin değerini değiştirmek için kullanılamaz.

### <a name="example"></a>Örnek

[Geri](#back)örneğe bakın.

## <a name="const_pointer"></a><a name="const_pointer"></a> const_pointer

Bir deque içindeki bir öğe için bir işaretçi sağlar **`const`** .

```cpp
typedef typename Allocator::const_pointer const_pointer;
```

### <a name="remarks"></a>Açıklamalar

Bir tür `const_pointer` , bir öğenin değerini değiştirmek için kullanılamaz. Bir [Yineleyici](#iterator) , bir deque öğesine erişmek için daha yaygın olarak kullanılır.

## <a name="const_reference"></a><a name="const_reference"></a> const_reference

**`const`** İşlem okumak ve gerçekleştirmek için bir deque içinde depolanan bir öğeye başvuru sağlayan bir tür **`const`** .

```cpp
typedef typename Allocator::const_reference const_reference;
```

### <a name="remarks"></a>Açıklamalar

Bir tür `const_reference` , bir öğenin değerini değiştirmek için kullanılamaz.

### <a name="example"></a>Örnek

```cpp
// deque_const_ref.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>

int main( )
{
   using namespace std;
   deque <int> c1;

   c1.push_back( 10 );
   c1.push_back( 20 );

   const deque <int> c2 = c1;
   const int &i = c2.front( );
   const int &j = c2.back( );
   cout << "The first element is " << i << endl;
   cout << "The second element is " << j << endl;

   // The following line would cause an error as c2 is const
   // c2.push_back( 30 );
}
```

```Output
The first element is 10
The second element is 20
```

## <a name="const_reverse_iterator"></a><a name="const_reverse_iterator"></a> const_reverse_iterator

Deque içindeki herhangi bir öğeyi okuyabilen bir rastgele erişim yineleyici sağlayan bir tür **`const`** .

```cpp
typedef std::reverse_iterator<const_iterator> const_reverse_iterator;
```

### <a name="remarks"></a>Açıklamalar

Bir tür, `const_reverse_iterator` bir öğenin değerini değiştiremez ve ters içinde deque üzerinde yinelemek için kullanılır.

### <a name="example"></a>Örnek

Yineleyici bildirme ve kullanma hakkında bir örnek için bkz. [rbegin](#rbegin) örneği.

## <a name="crbegin"></a><a name="crbegin"></a> crbegin

Ters çevrilen bir deque içindeki ilk öğeye bir const yineleyici döndürür.

```cpp
const_reverse_iterator crbegin() const;
```

### <a name="return-value"></a>Dönüş Değeri

[Ters çevrilen bir veya daha](../standard-library/deque-class.md) sonra geri çevrilme içindeki son öğe olduğunu ele alarak, bir sabit ters rastgele erişim Yineleyici `deque` .

### <a name="remarks"></a>Açıklamalar

Dönüş değeri ile `crbegin` `deque` nesne değiştirilemez.

### <a name="example"></a>Örnek

```cpp
// deque_crbegin.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>

int main( )
{
   using namespace std;
   deque <int> v1;
   deque <int>::iterator v1_Iter;
   deque <int>::const_reverse_iterator v1_rIter;

   v1.push_back( 1 );
   v1.push_back( 2 );

   v1_Iter = v1.begin( );
   cout << "The first element of deque is "
        << *v1_Iter << "." << endl;

   v1_rIter = v1.crbegin( );
   cout << "The first element of the reversed deque is "
        << *v1_rIter << "." << endl;
}
```

```Output
The first element of deque is 1.
The first element of the reversed deque is 2.
```

## <a name="crend"></a><a name="crend"></a> crend

Ters çevrilen bir deque içindeki son öğeden sonraki konumu ele alan bir const yineleyici döndürür.

```cpp
const_reverse_iterator crend() const;
```

### <a name="return-value"></a>Dönüş Değeri

Ters çevrilen bir [deque](../standard-library/deque-class.md) içindeki son öğeden sonra gelen konumu ele alan bir sabit ters rastgele erişim yineleyici (geri çevrilmeyen deque 'ın önünde ilk öğesi olan konum).

### <a name="remarks"></a>Açıklamalar

`crend``deque` [Array:: cend](../standard-library/array-class-stl.md#cend) ile birlikte kullanılan bir ters çevrilmelerle birlikte kullanılır `deque` .

Dönüş değeri `crend` (uygun şekilde azaltılır) ile `deque` nesne değiştirilemez.

`crend` ters bir yineleyicinin kendisinin sonuna kadar ulaştığı konusunda test etmek için kullanılabilir.

Tarafından döndürülen değer `crend` başvurulmamalıdır.

### <a name="example"></a>Örnek

```cpp
// deque_crend.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>

int main( )
{
   using namespace std;
   deque <int> v1;
   deque <int>::const_reverse_iterator v1_rIter;

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

## <a name="deque"></a><a name="deque"></a> deque

Belirli bir boyutun veya belirli bir değere sahip olan ya da belirli bir ayırıcıya ya da başka bir kısmının bir kopyası olarak ya da bir kopyasının bir kopyasını oluşturur.

```cpp
deque();

explicit deque(const Allocator& Al);
explicit deque(size_type Count);
deque(size_type Count, const Type& Val);

deque(
    size_type Count,
    const Type& Val,
    const Allocator& Al);

deque(const deque& Right);

template <class InputIterator>
deque(InputIterator First,  InputIterator Last);

template <class InputIterator>
deque(
   InputIterator First,
   InputIterator Last,
   const Allocator& Al);

deque(initializer_list<value_type> IList, const Allocator& Al);
```

### <a name="parameters"></a>Parametreler

*Eşkenar*\
Bu nesneyle kullanılacak kaynak ayırıcı sınıfı.

*Biriktirme*\
Oluşturulan deque içindeki öğe sayısı.

*Acil*\
Oluşturulan deque öğelerinin değeri.

*Right*\
Oluşturulan deque 'in bir kopya olduğu deque.

*Adı*\
Kopyalanacak öğe aralığındaki ilk öğenin konumu.

*Soyadına*\
Kopyalanacak öğe aralığının ötesinde ilk öğenin konumu.

*IList*\
Kopyalanacak initializer_list.

### <a name="remarks"></a>Açıklamalar

Tüm oluşturucular bir ayırıcı nesnesi (*Al*) depolar ve deque 'yi başlatır.

İlk iki Oluşturucu boş bir ilk deque belirtir; İkincisi Ayrıca kullanılacak ayırıcı türünü ( `_Al` ) belirtir.

Üçüncü Oluşturucu, `count` sınıfının varsayılan değerinin belirtilen () öğelerinin bir tekrarını belirtir `Type` .

Dördüncü ve beşinci oluşturucular değer (*Count*) öğelerinin tekrarlarını belirtir `val` .

Altıncı Oluşturucu, *sağ* ucunun bir kopyasını belirtir.

Yedinci ve sekizinci oluşturucular, `[First, Last)` bir deque aralığını kopyalar.

Yedinci Oluşturucu, *sağa doğru* gider.

Sekizinci Oluşturucu bir initializer_list içeriğini kopyalar.

Oluşturuculardan hiçbiri geçici realkonum gerçekleştirmez.

### <a name="example"></a>Örnek

```cpp
/ compile with: /EHsc
#include <deque>
#include <iostream>
#include <forward_list>

int main()
{
    using namespace std;

    forward_list<int> f1{ 1, 2, 3, 4 };

    f1.insert_after(f1.begin(), { 5, 6, 7, 8 });

    deque <int>::iterator c1_Iter, c2_Iter, c3_Iter, c4_Iter, c5_Iter, c6_Iter;

    // Create an empty deque c0
    deque <int> c0;

    // Create a deque c1 with 3 elements of default value 0
    deque <int> c1(3);

    // Create a deque c2 with 5 elements of value 2
    deque <int> c2(5, 2);

    // Create a deque c3 with 3 elements of value 1 and with the
    // allocator of deque c2
    deque <int> c3(3, 1, c2.get_allocator());

    // Create a copy, deque c4, of deque c2
    deque <int> c4(c2);

    // Create a deque c5 by copying the range c4[ first,  last)
    c4_Iter = c4.begin();
    c4_Iter++;
    c4_Iter++;
    deque <int> c5(c4.begin(), c4_Iter);

    // Create a deque c6 by copying the range c4[ first,  last) and
    // c2 with the allocator of deque
    c4_Iter = c4.begin();
    c4_Iter++;
    c4_Iter++;
    c4_Iter++;
    deque <int> c6(c4.begin(), c4_Iter, c2.get_allocator());

    // Create a deque c8 by copying the contents of an initializer_list
    // using brace initialization
    deque<int> c8({ 1, 2, 3, 4 });

    initializer_list<int> iList{ 5, 6, 7, 8 };
    deque<int> c9( iList);

    cout << "c1 = ";
    for (int i : c1)
        cout << i << " ";
    cout << endl;

    cout << "c2 = ";
    for (int i : c2)
        cout << i << " ";
    cout << endl;

    cout << "c3 = ";
    for (int i : c3)
        cout << i << " ";
    cout << endl;

    cout << "c4 = ";
    for (int i : c4)
        cout << i << " ";
    cout << endl;

    cout << "c5 = ";
    for (int i : c5)
        cout << i << " ";
    cout << endl;

    cout << "c6 = ";
    for (int i : c6)
        cout << i << " ";
    cout << endl;

    // Move deque c6 to deque c7
    deque <int> c7(move(c6));
    deque <int>::iterator c7_Iter;

    cout << "c7 =";
    for (int i : c7)
        cout << i << " ";
    cout << endl;

    cout << "c8 = ";
    for (int i : c8)
        cout << i << " ";
    cout << endl;

    cout << "c9 = ";
    for (int i : c9)
        cout << i << " ";
    cout << endl;

    int x = 3;
}
// deque_deque.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>

int main( )
{
    using namespace std;
   deque <int>::iterator c1_Iter, c2_Iter, c3_Iter, c4_Iter, c5_Iter, c6_Iter;

    // Create an empty deque c0
    deque <int> c0;

    // Create a deque c1 with 3 elements of default value 0
    deque <int> c1( 3 );

    // Create a deque c2 with 5 elements of value 2
    deque <int> c2( 5, 2 );

    // Create a deque c3 with 3 elements of value 1 and with the
    // allocator of deque c2
    deque <int> c3( 3, 1, c2.get_allocator( ) );

    // Create a copy, deque c4, of deque c2
    deque <int> c4( c2 );

    // Create a deque c5 by copying the range c4[ first,  last)
    c4_Iter = c4.begin( );
    c4_Iter++;
    c4_Iter++;
    deque <int> c5( c4.begin( ), c4_Iter );

    // Create a deque c6 by copying the range c4[ first,  last) and
    // c2 with the allocator of deque
    c4_Iter = c4.begin( );
   c4_Iter++;
   c4_Iter++;
   c4_Iter++;
   deque <int> c6( c4.begin( ), c4_Iter, c2.get_allocator( ) );

    // Create a deque c8 by copying the contents of an initializer_list
    // using brace initialization
    deque<int> c8({ 1, 2, 3, 4 });

        initializer_list<int> iList{ 5, 6, 7, 8 };
    deque<int> c9( iList);

    cout << "c1 = ";
    for ( c1_Iter = c1.begin( ); c1_Iter != c1.end( ); c1_Iter++ )
        cout << *c1_Iter << " ";
    cout << endl;

    cout << "c2 = ";
    for ( c2_Iter = c2.begin( ); c2_Iter != c2.end( ); c2_Iter++ )
        cout << *c2_Iter << " ";
    cout << endl;

    cout << "c3 = ";
    for ( c3_Iter = c3.begin( ); c3_Iter != c3.end( ); c3_Iter++ )
        cout << *c3_Iter << " ";
    cout << endl;

    cout << "c4 = ";
    for ( c4_Iter = c4.begin( ); c4_Iter != c4.end( ); c4_Iter++ )
        cout << *c4_Iter << " ";
    cout << endl;

    cout << "c5 = ";
    for ( c5_Iter = c5.begin( ); c5_Iter != c5.end( ); c5_Iter++ )
        cout << *c5_Iter << " ";
    cout << endl;

    cout << "c6 = ";
    for ( c6_Iter = c6.begin( ); c6_Iter != c6.end( ); c6_Iter++ )
        cout << *c6_Iter << " ";
    cout << endl;

    // Move deque c6 to deque c7
    deque <int> c7( move(c6) );
    deque <int>::iterator c7_Iter;

    cout << "c7 =" ;
    for ( c7_Iter = c7.begin( ) ; c7_Iter != c7.end( ) ; c7_Iter++ )
        cout << " " << *c7_Iter;
    cout << endl;

    cout << "c8 = ";
    for (int i : c8)
        cout << i << " ";
    cout << endl;

    cout << "c9 = ";
    or (int i : c9)
        cout << i << " ";
    cout << endl;
}
```

## <a name="difference_type"></a><a name="difference_type"></a> difference_type

Aynı deque içindeki öğelere başvuran iki yineleyiciler arasındaki farkı sağlayan bir tür.

```cpp
typedef typename Allocator::difference_type difference_type;
```

### <a name="remarks"></a>Açıklamalar

`difference_type`Ayrıca, iki işaretçi arasındaki öğe sayısı olarak da açıklanabilir.

### <a name="example"></a>Örnek

```cpp
// deque_diff_type.cpp
// compile with: /EHsc
#include <iostream>
#include <deque>
#include <algorithm>

int main( )
{
   using namespace std;

   deque <int> c1;
   deque <int>::iterator c1_Iter, c2_Iter;

   c1.push_back( 30 );
   c1.push_back( 20 );
   c1.push_back( 30 );
   c1.push_back( 10 );
   c1.push_back( 30 );
   c1.push_back( 20 );

   c1_Iter = c1.begin( );
   c2_Iter = c1.end( );

   deque <int>::difference_type df_typ1, df_typ2, df_typ3;

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

Belirtilen konumdaki deque içine yerinde oluşturulmuş bir öğe ekler.

```cpp
iterator emplace(
    const_iterator _Where,
    Type&& val);
```

### <a name="parameters"></a>Parametreler

*_Where*\
İlk öğenin eklendiği [deque](../standard-library/deque-class.md) konumu.

*Acil*\
İçine eklenmekte olan öğenin değeri `deque` .

### <a name="return-value"></a>Dönüş Değeri

İşlevi, yeni öğenin deque içine eklendiği konuma işaret eden bir yineleyici döndürür.

### <a name="remarks"></a>Açıklamalar

Herhangi bir ekleme işlemi pahalı olabilir ve `deque` performans tartışması için bkz `deque` ..

### <a name="example"></a>Örnek

```cpp
// deque_emplace.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>

int main( )
{
   using namespace std;
   deque <int> v1;
   deque <int>::iterator Iter;

   v1.push_back( 10 );
   v1.push_back( 20 );
   v1.push_back( 30 );

   cout << "v1 =" ;
   for ( Iter = v1.begin( ) ; Iter != v1.end( ) ; Iter++ )
      cout << " " << *Iter;
   cout << endl;

// initialize a deque of deques by moving v1
   deque < deque <int> > vv1;

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

## <a name="emplace_back"></a><a name="emplace_back"></a> emplace_back

Deque 'in sonuna yerinde oluşturulmuş bir öğe ekler.

```cpp
void emplace_back(Type&& val);
```

### <a name="parameters"></a>Parametreler

*Acil*\
[Deque](../standard-library/deque-class.md)'un sonuna eklenen öğe.

### <a name="example"></a>Örnek

```cpp
// deque_emplace_back.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>

int main( )
{
   using namespace std;
   deque <int> v1;

   v1.push_back( 1 );
   if ( v1.size( ) != 0 )
      cout << "Last element: " << v1.back( ) << endl;

   v1.push_back( 2 );
   if ( v1.size( ) != 0 )
      cout << "New last element: " << v1.back( ) << endl;

// initialize a deque of deques by moving v1
   deque < deque <int> > vv1;

   vv1.emplace_back( move( v1 ) );
   if ( vv1.size( ) != 0 && vv1[0].size( ) != 0 )
      cout << "Moved last element: " << vv1[0].back( ) << endl;
}
```

```Output
Last element: 1
New last element: 2
Moved last element: 2
```

## <a name="emplace_front"></a><a name="emplace_front"></a> emplace_front

Deque 'in sonuna yerinde oluşturulmuş bir öğe ekler.

```cpp
void emplace_front(Type&& val);
```

### <a name="parameters"></a>Parametreler

*Acil*\
[Deque](../standard-library/deque-class.md)'ın başlangıcına eklenen öğe.

### <a name="example"></a>Örnek

```cpp
// deque_emplace_front.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>

int main( )
{
   using namespace std;
   deque <int> v1;

   v1.push_back( 1 );
   if ( v1.size( ) != 0 )
      cout << "Last element: " << v1.back( ) << endl;

   v1.push_back( 2 );
   if ( v1.size( ) != 0 )
      cout << "New last element: " << v1.back( ) << endl;

// initialize a deque of deques by moving v1
   deque < deque <int> > vv1;

   vv1.emplace_front( move( v1 ) );
   if ( vv1.size( ) != 0 && vv1[0].size( ) != 0 )
      cout << "Moved last element: " << vv1[0].back( ) << endl;
}
```

```Output
Last element: 1
New last element: 2
Moved last element: 2
```

## <a name="empty"></a><a name="empty"></a> olmamalıdır

Bir deque boş ise sınar.

```cpp
bool empty() const;
```

### <a name="return-value"></a>Dönüş Değeri

**`true`** deque boşsa; **`false`** Deque boş değilse.

### <a name="example"></a>Örnek

```cpp
// deque_empty.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>

int main( )
{
   using namespace std;
   deque <int> c1;

   c1.push_back( 10 );
   if ( c1.empty( ) )
      cout << "The deque is empty." << endl;
   else
      cout << "The deque is not empty." << endl;
}
```

```Output
The deque is not empty.
```

## <a name="end"></a><a name="end"></a> erer

Bir deque içindeki son öğeden sonraki konumu ele alan bir yineleyici döndürür.

```cpp
const_iterator end() const;

iterator end();
```

### <a name="return-value"></a>Dönüş Değeri

Bir deque içindeki son öğeden sonra gelen konumu ele alan bir rastgele erişim Yineleyici. Deque boşsa, deque:: End = = deque:: Begin.

### <a name="remarks"></a>Açıklamalar

`end` bir yineleyicinin kendisinin sonuna kadar ulaştığı bir yineleyici olup olmadığını test etmek için kullanılır.

### <a name="example"></a>Örnek

```cpp
// deque_end.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>

int main( )
{
   using namespace std;
   deque <int> c1;
   deque <int>::iterator c1_Iter;

   c1.push_back( 10 );
   c1.push_back( 20 );
   c1.push_back( 30 );

   c1_Iter = c1.end( );
   c1_Iter--;
   cout << "The last integer of c1 is " << *c1_Iter << endl;

   c1_Iter--;
   *c1_Iter = 400;
   cout << "The new next-to-last integer of c1 is " << *c1_Iter << endl;

   // If a const iterator had been declared instead with the line:
   // deque <int>::const_iterator c1_Iter;
   // an error would have resulted when inserting the 400

   cout << "The deque is now:";
   for ( c1_Iter = c1.begin( ); c1_Iter != c1.end( ); c1_Iter++ )
      cout << " " << *c1_Iter;
}
```

```Output
The last integer of c1 is 30
The new next-to-last integer of c1 is 400
The deque is now: 10 400 30
```

## <a name="erase"></a><a name="erase"></a> silme

Bir öğeyi veya öğe aralığını belirtilen konumlardan kaldırır.

```cpp
iterator erase(iterator _Where);

iterator erase(iterator first, iterator last);
```

### <a name="parameters"></a>Parametreler

*_Where*\
Deque kaldırılacak öğenin konumu.

*adı*\
Deque öğesinden kaldırılan ilk öğenin konumu.

*soyadına*\
Deque 'dan çıkarılan son öğenin hemen ötesinde konumlandır.

### <a name="return-value"></a>Dönüş Değeri

Kaldırılan tüm öğelerin ötesinde kalan ilk öğeyi veya böyle bir öğe yoksa deque 'nın sonuna bir işaretçiyi atayan bir rastgele erişim Yineleyici.

### <a name="remarks"></a>Açıklamalar

`erase` hiçbir koşulda özel durum oluşturmaz.

### <a name="example"></a>Örnek

```cpp
// deque_erase.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>

int main( )
{
   using namespace std;
   deque <int> c1;
   deque <int>::iterator Iter;

   c1.push_back( 10 );
   c1.push_back( 20 );
   c1.push_back( 30 );
   c1.push_back( 40 );
   c1.push_back( 50 );
   cout << "The initial deque is: ";
   for ( Iter = c1.begin( ); Iter != c1.end( ); Iter++ )
      cout << *Iter << " ";
   cout << endl;
   c1.erase( c1.begin( ) );
   cout << "After erasing the first element, the deque becomes:  ";
   for ( Iter = c1.begin( ); Iter != c1.end( ); Iter++ )
      cout << *Iter << " ";
   cout << endl;
   Iter = c1.begin( );
   Iter++;
   c1.erase( Iter, c1.end( ) );
   cout << "After erasing all elements but the first, deque becomes: ";
   for ( Iter = c1.begin( ); Iter != c1.end( ); Iter++ )
      cout << *Iter << " ";
   cout << endl;
}
```

```Output
The initial deque is: 10 20 30 40 50
After erasing the first element, the deque becomes:  20 30 40 50
After erasing all elements but the first, deque becomes: 20
```

## <a name="front"></a><a name="front"></a> yapılan

Bir deque içindeki ilk öğeye bir başvuru döndürür.

```cpp
reference front();

const_reference front() const;
```

### <a name="return-value"></a>Dönüş Değeri

Deque boşsa, dönüş tanımsızdır.

### <a name="remarks"></a>Açıklamalar

Dönüş değeri `front` öğesine atanırsa `const_reference` , deque nesnesi değiştirilemez. Dönüş değeri `front` öğesine atanırsa `reference` , deque nesnesi değiştirilebilir.

1 veya 2 olarak tanımlanan [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md) kullanılarak derlendiğinde, boş bir deque içindeki bir öğeye erişmeyi denerseniz bir çalışma zamanı hatası oluşur.  Daha fazla bilgi için bkz. [Checked Iterators](../standard-library/checked-iterators.md) .

### <a name="example"></a>Örnek

```cpp
// deque_front.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>

int main( )
{
   using namespace std;
   deque <int> c1;

   c1.push_back( 10 );
   c1.push_back( 11 );

   int& i = c1.front( );
   const int& ii = c1.front( );

   cout << "The first integer of c1 is " << i << endl;
   i++;
   cout << "The second integer of c1 is " << ii << endl;
}
```

```Output
The first integer of c1 is 10
The second integer of c1 is 11
```

## <a name="get_allocator"></a><a name="get_allocator"></a> get_allocator

Deque oluşturmak için kullanılan ayırıcı nesnesinin bir kopyasını döndürür.

```cpp
Allocator get_allocator() const;
```

### <a name="return-value"></a>Dönüş Değeri

Deque tarafından kullanılan ayırıcı.

### <a name="remarks"></a>Açıklamalar

Deque sınıfı için ayrıcılar, sınıfın depolamayı nasıl yönettiğini belirtir. C++ standart kitaplığı kapsayıcı sınıflarıyla birlikte sağlanan varsayılan ayrıcılar çoğu programlama ihtiyacı için yeterlidir. Kendi ayırıcı sınıfınızı yazmak ve kullanmak, gelişmiş bir C++ konudur.

### <a name="example"></a>Örnek

```cpp
// deque_get_allocator.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>

int main( )
{
   using namespace std;
   // The following lines declare objects that use the default allocator.
   deque <int> c1;
   deque <int, allocator<int> > c2 = deque <int, allocator<int> >( allocator<int>( ) );

   // c3 will use the same allocator class as c1
   deque <int> c3( c1.get_allocator( ) );

   deque <int>::allocator_type xlst = c1.get_allocator( );
   // You can now call functions on the allocator class used by c1
}
```

## <a name="insert"></a><a name="insert"></a> ekleyin

Belirli bir konumda bir öğe veya dizi öğe ya da bir dizi öğe ekler.

```cpp
iterator insert(
    const_iterator Where,
    const Type& Val);

iterator insert(
    const_iterator Where,
    Type&& Val);

void insert(
    iterator Where,
    size_type Count,
    const Type& Val);

template <class InputIterator>
void insert(
    iterator Where,
    InputIterator First,
    InputIterator Last);

iterator insert(
    iterator Where,initializer_list<Type>
IList);
```

### <a name="parameters"></a>Parametreler

*Olmadığı*\
İlk öğenin eklendiği hedef deque konumu.

*Acil*\
Deque içine eklenmekte olan öğenin değeri.

*Biriktirme*\
Deque içine eklenmekte olan öğe sayısı.

*Adı*\
Bağımsız değişken içinde kopyalanacak öğe aralığındaki ilk öğenin konumu.

*Soyadına*\
Bağımsız değişken içinde kopyalanacak öğe aralığının ötesinde ilk öğenin konumu.

*IList*\
Eklenecek öğelerin initializer_list.

### <a name="return-value"></a>Dönüş Değeri

İlk iki INSERT işlevi, yeni öğenin deque içine eklendiği konuma işaret eden bir yineleyici döndürür.

### <a name="remarks"></a>Açıklamalar

Herhangi bir ekleme işlemi pahalı olabilir.

## <a name="iterator"></a><a name="iterator"></a> iden

Bir deque içinde herhangi bir öğeyi okuyabilen veya değiştirebilen bir rastgele erişim yineleyici sağlayan bir tür.

```cpp
typedef implementation-defined iterator;
```

### <a name="remarks"></a>Açıklamalar

Bir türü `iterator` , bir öğenin değerini değiştirmek için kullanılabilir.

### <a name="example"></a>Örnek

[Begin](#begin)örneğine bakın.

## <a name="max_size"></a><a name="max_size"></a> max_size

Deque 'ın en büyük uzunluğunu döndürür.

```cpp
size_type max_size() const;
```

### <a name="return-value"></a>Dönüş Değeri

En büyük olası uzunluk uzunluğu.

### <a name="example"></a>Örnek

```cpp
// deque_max_size.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>

int main( )
{
   using namespace std;
   deque <int> c1;
   deque <int>::size_type i;

   i = c1.max_size( );
   cout << "The maximum possible length of the deque is " << i << "." << endl;
}
```

## <a name="operator"></a><a name="op_at"></a> operator []

Belirtilen konumdaki deque öğesine bir başvuru döndürür.

```cpp
reference operator[](size_type pos);

const_reference operator[](size_type pos) const;
```

### <a name="parameters"></a>Parametreler

*'un*\
Başvurulacak deque öğesinin konumu.

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkeninde konumu belirtilen öğeye başvuru. Belirtilen konum, deque 'ın boyutundan büyükse, sonuç tanımsızdır.

### <a name="remarks"></a>Açıklamalar

Dönüş değeri `operator[]` öğesine atanırsa `const_reference` , deque nesnesi değiştirilemez. Dönüş değeri `operator[]` öğesine atanırsa `reference` , deque nesnesi değiştirilebilir.

1 veya 2 olarak tanımlanan [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md) kullanılarak derlendiğinde, deque sınırları dışında bir öğeye erişmeyi denerseniz bir çalışma zamanı hatası oluşur.  Daha fazla bilgi için bkz. [Checked Iterators](../standard-library/checked-iterators.md) .

### <a name="example"></a>Örnek

```cpp
// deque_op_ref.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>

int main( )
{
   using namespace std;
   deque <int> c1;

   c1.push_back( 10 );
   c1.push_back( 20 );
   cout << "The first integer of c1 is " << c1[0] << endl;
   int& i = c1[1];
   cout << "The second integer of c1 is " << i << endl;
}
```

```Output
The first integer of c1 is 10
The second integer of c1 is 20
```

## <a name="operator"></a><a name="op_eq"></a> işleç =

Diğer bir deque öğelerini kullanarak bu deque öğelerinin yerini alır.

```cpp
deque& operator=(const deque& right);

deque& operator=(deque&& right);
```

### <a name="parameters"></a>Parametreler

*Right*\
Yeni içeriği sağlayan deque.

### <a name="remarks"></a>Açıklamalar

İlk geçersiz kılma öğeleri, atamanın kaynağı olan *sağdaki* Bu deque öğesine kopyalar. İkinci geçersiz kılma öğeleri *sağdaki* Bu deque öğesine taşımalıdır.

İşleç yürütmeden önce bu dede içerilen öğeler kaldırılır.

### <a name="example"></a>Örnek

```cpp
// deque_operator_as.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>
using namespace std;

typedef deque<int> MyDeque;

template<typename MyDeque> struct S;

template<typename MyDeque> struct S<MyDeque&> {
  static void show( MyDeque& d ) {
    MyDeque::const_iterator iter;
    for (iter = d.cbegin(); iter != d.cend(); iter++)
       cout << *iter << " ";
    cout << endl;
  }
};

template<typename MyDeque> struct S<MyDeque&&> {
  static void show( MyDeque&& d ) {
    MyDeque::const_iterator iter;
    for (iter = d.cbegin(); iter != d.cend(); iter++)
       cout << *iter << " ";
cout << " via unnamed rvalue reference " << endl;
  }
};

int main( )
{
   MyDeque d1, d2;

   d1.push_back(10);
   d1.push_back(20);
   d1.push_back(30);
   d1.push_back(40);
   d1.push_back(50);

   cout << "d1 = " ;
   S<MyDeque&>::show( d1 );

   d2 = d1;
   cout << "d2 = ";
   S<MyDeque&>::show( d2 );

   cout << "     ";
   S<MyDeque&&>::show ( move< MyDeque& > (d1) );
}
```

## <a name="pointer"></a><a name="pointer"></a> çağrısı

[Deque](../standard-library/deque-class.md)içindeki bir öğe için bir işaretçi sağlar.

```unstlib
typedef typename Allocator::pointer pointer;
```

### <a name="remarks"></a>Açıklamalar

Bir türü `pointer` , bir öğenin değerini değiştirmek için kullanılabilir. Bir [Yineleyici](#iterator) , bir deque öğesine erişmek için daha yaygın olarak kullanılır.

## <a name="pop_back"></a><a name="pop_back"></a> pop_back

Deque 'ın sonundaki öğeyi siler.

```cpp
void pop_back();
```

### <a name="remarks"></a>Açıklamalar

Son öğe boş olmamalıdır. `pop_back` hiçbir koşulda özel durum oluşturmaz.

### <a name="example"></a>Örnek

```cpp
// deque_pop_back.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>

int main( )
{
   using namespace std;
   deque <int> c1;

   c1.push_back( 1 );
   c1.push_back( 2 );
   cout << "The first element is: " << c1.front( ) << endl;
   cout << "The last element is: " << c1.back( ) << endl;

   c1.pop_back( );
   cout << "After deleting the element at the end of the deque, the "
      "last element is: " << c1.back( ) << endl;
}
```

```Output
The first element is: 1
The last element is: 2
After deleting the element at the end of the deque, the last element is: 1
```

## <a name="pop_front"></a><a name="pop_front"></a> pop_front

Deque 'ın başındaki öğeyi siler.

```cpp
void pop_front();
```

### <a name="remarks"></a>Açıklamalar

İlk öğe boş olmamalıdır. `pop_front` hiçbir koşulda özel durum oluşturmaz.

### <a name="example"></a>Örnek

```cpp
// deque_pop_front.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>

int main( )
{
   using namespace std;
   deque <int> c1;

   c1.push_back( 1 );
   c1.push_back( 2 );
   cout << "The first element is: " << c1.front( ) << endl;
   cout << "The second element is: " << c1.back( ) << endl;

   c1.pop_front( );
   cout << "After deleting the element at the beginning of the "
      "deque, the first element is: " << c1.front( ) << endl;
}
```

```Output
The first element is: 1
The second element is: 2
After deleting the element at the beginning of the deque, the first element is: 2
```

## <a name="push_back"></a><a name="push_back"></a> push_back

Deque 'un sonuna bir öğesi ekler.

```cpp
void push_back(const Type& val);

void push_back(Type&& val);
```

### <a name="parameters"></a>Parametreler

*Acil*\
Deque 'un sonuna eklenen öğe.

### <a name="remarks"></a>Açıklamalar

Bir özel durum oluşursa, deque değiştirilmemiş olarak kalır ve özel durum yeniden oluşturulur.

## <a name="push_front"></a><a name="push_front"></a> push_front

Deque 'ın başlangıcına bir öğesi ekler.

```cpp
void push_front(const Type& val);
void push_front(Type&& val);
```

### <a name="parameters"></a>Parametreler

*Acil*\
Deque 'ın başlangıcına eklenen öğe.

### <a name="remarks"></a>Açıklamalar

Bir özel durum oluşursa, deque değiştirilmemiş olarak kalır ve özel durum yeniden oluşturulur.

### <a name="example"></a>Örnek

```cpp
// deque_push_front.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>
#include <string>

int main( )
{
   using namespace std;
   deque <int> c1;

   c1.push_front( 1 );
   if ( c1.size( ) != 0 )
      cout << "First element: " << c1.front( ) << endl;

   c1.push_front( 2 );
   if ( c1.size( ) != 0 )
      cout << "New first element: " << c1.front( ) << endl;

// move initialize a deque of strings
   deque <string> c2;
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

Tersine çevrilmiş bir deque içindeki ilk öğeye bir yineleyici döndürür.

```cpp
const_reverse_iterator rbegin() const;

reverse_iterator rbegin();
```

### <a name="return-value"></a>Dönüş Değeri

Ters bir rastgele erişim Yineleyici, ters çevrilen bir deque içindeki ilk öğeyi ele alıyor veya geri çevrilmeyen en son öğe olan adresleme.

### <a name="remarks"></a>Açıklamalar

`rbegin`[Begin](#begin) , bir deque ile birlikte kullanıldığında, ters çevrilmiş bir dekiyle kullanılır.

Dönüş değeri `rbegin` öğesine atanırsa `const_reverse_iterator` , deque nesnesi değiştirilemez. Dönüş değeri `rbegin` öğesine atanırsa `reverse_iterator` , deque nesnesi değiştirilebilir.

`rbegin` , geriye doğru yinelemek için kullanılabilir.

### <a name="example"></a>Örnek

```cpp
// deque_rbegin.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>

int main( )
{
   using namespace std;
   deque <int> c1;
   deque <int>::iterator c1_Iter;
   deque <int>::reverse_iterator c1_rIter;

   // If the following line had replaced the line above, an error
   // would have resulted in the line modifying an element
   // (commented below) because the iterator would have been const
   // deque <int>::const_reverse_iterator c1_rIter;

   c1.push_back( 10 );
   c1.push_back( 20 );
   c1.push_back( 30 );

   c1_rIter = c1.rbegin( );
   cout << "Last element in the deque is " << *c1_rIter << "." << endl;

   cout << "The deque contains the elements: ";
   for ( c1_Iter = c1.begin( ); c1_Iter != c1.end( ); c1_Iter++ )
      cout << *c1_Iter << " ";
   cout << "in that order.";
   cout << endl;

   // rbegin can be used to iterate through a deque in reverse order
   cout << "The reversed deque is: ";
   for ( c1_rIter = c1.rbegin( ); c1_rIter != c1.rend( ); c1_rIter++ )
      cout << *c1_rIter << " ";
   cout << endl;

   c1_rIter = c1.rbegin( );
   *c1_rIter = 40;  // This would have caused an error if a
                    // const_reverse iterator had been declared as
                    // noted above
   cout << "Last element in deque is now " << *c1_rIter << "." << endl;
}
```

```Output
Last element in the deque is 30.
The deque contains the elements: 10 20 30 in that order.
The reversed deque is: 30 20 10
Last element in deque is now 40.
```

## <a name="reference"></a><a name="reference"></a> başvurunun

Bir deque içinde depolanan bir öğeye başvuru sağlayan bir tür.

```cpp
typedef typename Allocator::reference reference;
```

### <a name="example"></a>Örnek

```cpp
// deque_reference.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>

int main( )
{
   using namespace std;
   deque <int> c1;

   c1.push_back( 10 );
   c1.push_back( 20 );

   const int &i = c1.front( );
   int &j = c1.back( );
   cout << "The first element is " << i << endl;
   cout << "The second element is " << j << endl;
}
```

```Output
The first element is 10
The second element is 20
```

## <a name="rend"></a><a name="rend"></a> rend

Ters çevrilen bir deque içindeki son öğeden sonraki konumu ele alan bir yineleyici döndürür.

```cpp
const_reverse_iterator rend() const;

reverse_iterator rend();
```

### <a name="return-value"></a>Dönüş Değeri

Ters çevrilen bir deque içindeki son öğeden sonra gelen konumu ele alan ters bir rastgele erişim yineleyici (geri çevrilmeyen deque 'un önünde ilk öğeden önce gelen konum).

### <a name="remarks"></a>Açıklamalar

`rend` , [End](#end) bir deque ile kullanıldığı gibi ters bir deque ile kullanılır.

Dönüş değeri `rend` öğesine atanırsa `const_reverse_iterator` , deque nesnesi değiştirilemez. Dönüş değeri `rend` öğesine atanırsa `reverse_iterator` , deque nesnesi değiştirilebilir.

`rend` geriye doğru bir yineleyicinin kendisinin sonuna kadar ulaştığı bir işlem olup olmadığını test etmek için kullanılabilir.

Tarafından döndürülen değer `rend` başvurulmamalıdır.

### <a name="example"></a>Örnek

```cpp
// deque_rend.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>

int main( )
{
   using namespace std;

   deque <int> c1;
   deque <int>::iterator c1_Iter;
   deque <int>::reverse_iterator c1_rIter;
   // If the following line had replaced the line above, an error
   // would have resulted in the line modifying an element
   // (commented below) because the iterator would have been const
   // deque <int>::const_reverse_iterator c1_rIter;

   c1.push_back( 10 );
   c1.push_back( 20 );
   c1.push_back( 30 );

   c1_rIter = c1.rend( );
   c1_rIter --; // Decrementing a reverse iterator moves it forward
                // in the deque (to point to the first element here)
   cout << "The first element in the deque is: " << *c1_rIter << endl;

   cout << "The deque is: ";
   for ( c1_Iter = c1.begin( ); c1_Iter != c1.end( ); c1_Iter++ )
      cout << *c1_Iter << " ";
   cout << endl;

   // rend can be used to test if an iteration is through all of
   // the elements of a reversed deque
   cout << "The reversed deque is: ";
   for ( c1_rIter = c1.rbegin( ); c1_rIter != c1.rend( ); c1_rIter++ )
      cout << *c1_rIter << " ";
   cout << endl;

   c1_rIter = c1.rend( );
   c1_rIter--; // Decrementing the reverse iterator moves it backward
               // in the reversed deque (to the last element here)
   *c1_rIter = 40; // This modification of the last element would
                   // have caused an error if a const_reverse
                   // iterator had been declared (as noted above)
   cout << "The modified reversed deque is: ";
   for ( c1_rIter = c1.rbegin( ); c1_rIter != c1.rend( ); c1_rIter++ )
      cout << *c1_rIter << " ";
   cout << endl;
}
```

```Output
The first element in the deque is: 10
The deque is: 10 20 30
The reversed deque is: 30 20 10
The modified reversed deque is: 30 20 40
```

## <a name="resize"></a><a name="resize"></a> yeniden boyutlandırma

Bir deque için yeni bir boyut belirtir.

```cpp
void resize(size_type _Newsize);

void resize(size_type _Newsize, Type val);
```

### <a name="parameters"></a>Parametreler

*_Newsize*\
Deque 'ın yeni boyutu.

*Acil*\
Yeni boyut orijinal boyuttan daha büyükse, deque 'a eklenecek yeni öğelerin değeri. Değer atlanırsa, yeni öğelere sınıfı için varsayılan değer atanır.

### <a name="remarks"></a>Açıklamalar

Deque 'ın boyutu istenen boyuttan küçükse *_Newsize*, öğeler istenen boyuta ulaşıncaya kadar en que öğesine eklenir.

Deque 'ın boyutu istenen boyuttan daha büyükse, deque 'un sonuna en yakın olan öğeler *_Newsize* boyutuna ulaşana kadar silinir.

Deque 'ın mevcut boyutu istenen boyutla aynıysa, hiçbir işlem yapılmaz.

[Boyut](#size) , deque 'in geçerli boyutunu yansıtır.

### <a name="example"></a>Örnek

```cpp
// deque_resize.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>

int main( )
{
   using namespace std;
   deque <int> c1;

   c1.push_back( 10 );
   c1.push_back( 20 );
   c1.push_back( 30 );

   c1.resize( 4,40 );
   cout << "The size of c1 is: " << c1.size( ) << endl;
   cout << "The value of the last element is " << c1.back( ) << endl;

   c1.resize( 5 );
   cout << "The size of c1 is now: " << c1.size( ) << endl;
   cout << "The value of the last element is now " << c1.back( ) << endl;

   c1.resize( 2 );
   cout << "The reduced size of c1 is: " << c1.size( ) << endl;
   cout << "The value of the last element is now " << c1.back( ) << endl;
}
```

```Output
The size of c1 is: 4
The value of the last element is 40
The size of c1 is now: 5
The value of the last element is now 0
The reduced size of c1 is: 2
The value of the last element is now 20
```

## <a name="reverse_iterator"></a><a name="reverse_iterator"></a> reverse_iterator

Ters çevrilen bir öğeyi okuyabilen veya değiştirebilen bir rasgele erişim yineleyicisi sağlayan bir tür.

```cpp
typedef std::reverse_iterator<iterator> reverse_iterator;
```

### <a name="remarks"></a>Açıklamalar

Bir tür `reverse_iterator` , deque ile yinelemek için kullanılır.

### <a name="example"></a>Örnek

Rbegin örneğine bakın.

## <a name="shrink_to_fit"></a><a name="shrink_to_fit"></a> shrink_to_fit

Fazla kapasiteyi atar.

```cpp
void shrink_to_fit();
```

### <a name="remarks"></a>Açıklamalar

`shrink_to_fit`Bir [deque](../standard-library/deque-class.md)tarafından kullanılan depolamanın azaltıyor olup olmadığını belirlemenin taşınabilir bir yolu yoktur.

### <a name="example"></a>Örnek

```cpp
// deque_shrink_to_fit.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>

int main( )
{
   using namespace std;
   deque <int> v1;
   //deque <int>::iterator Iter;

   v1.push_back( 1 );
   v1.push_back( 2 );
   cout << "Current size of v1 = "
      << v1.size( ) << endl;
   v1.shrink_to_fit();
   cout << "Current size of v1 = "
      << v1.size( ) << endl;
}
```

```Output
Current size of v1 = 1
Current size of v1 = 1
```

## <a name="size"></a><a name="size"></a> boyutla

Deque içindeki öğelerin sayısını döndürür.

```cpp
size_type size() const;
```

### <a name="return-value"></a>Dönüş Değeri

Deque 'ın geçerli uzunluğu.

### <a name="example"></a>Örnek

```cpp
// deque_size.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>

int main( )
{
   using namespace std;
   deque <int> c1;
   deque <int>::size_type i;

   c1.push_back( 1 );
   i = c1.size( );
   cout << "The deque length is " << i << "." << endl;

   c1.push_back( 2 );
   i = c1.size( );
   cout << "The deque length is now " << i << "." << endl;
}
```

```Output
The deque length is 1.
The deque length is now 2.
```

## <a name="size_type"></a><a name="size_type"></a> size_type

Bir deque içindeki öğe sayısını sayan bir tür.

```cpp
typedef typename Allocator::size_type size_type;
```

### <a name="example"></a>Örnek

[Boyut](#size)örneğine bakın.

## <a name="swap"></a><a name="swap"></a> Kur

İki deques öğelerini değiş tokuş eder.

```cpp
void swap(deque<Type, Allocator>& right);

friend void swap(deque<Type, Allocator>& left, deque<Type, Allocator>& right) template <class Type, class Allocator>
void swap(deque<Type, Allocator>& left, deque<Type, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*Right*\
Değiştirilecek öğelerin sağlanması veya öğeleri deque ile değiş tokuş edilecek şekilde değiştirilecek olan deque `left` .

*tarafta*\
Öğeleri, yukarı *doğru ve sağ* ile değiş tokuş edilecek bir deque.

### <a name="example"></a>Örnek

```cpp
// deque_swap.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>

int main( )
{
   using namespace std;
   deque <int> c1, c2, c3;
   deque <int>::iterator c1_Iter;

   c1.push_back( 1 );
   c1.push_back( 2 );
   c1.push_back( 3 );
   c2.push_back( 10 );
   c2.push_back( 20 );
   c3.push_back( 100 );

   cout << "The original deque c1 is:";
   for ( c1_Iter = c1.begin( ); c1_Iter != c1.end( ); c1_Iter++ )
      cout << " " << *c1_Iter;
   cout << endl;

   c1.swap( c2 );

   cout << "After swapping with c2, deque c1 is:";
   for ( c1_Iter = c1.begin( ); c1_Iter != c1.end( ); c1_Iter++ )
      cout << " " << *c1_Iter;
   cout << endl;

   swap( c1,c3 );

   cout << "After swapping with c3, deque c1 is:";
   for ( c1_Iter = c1.begin( ); c1_Iter != c1.end( ); c1_Iter++ )
      cout << " " << *c1_Iter;
   cout << endl;

   swap<>(c1, c2);
   cout << "After swapping with c2, deque c1 is:";
   for ( c1_Iter = c1.begin( ); c1_Iter != c1.end( ); c1_Iter++ )
      cout << " " << *c1_Iter;
   cout << endl;
}
```

```Output
The original deque c1 is: 1 2 3
After swapping with c2, deque c1 is: 10 20
After swapping with c3, deque c1 is: 100
After swapping with c2, deque c1 is: 1 2 3
```

## <a name="value_type"></a><a name="value_type"></a> value_type

Bir deque içinde depolanan veri türünü temsil eden bir tür.

```cpp
typedef typename Allocator::value_type value_type;
```

### <a name="remarks"></a>Açıklamalar

`value_type` , şablon parametresinin eşanlamlısıdır `Type` .

### <a name="example"></a>Örnek

```cpp
// deque_value_type.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>
int main( )
{
   using namespace std;
   deque<int>::value_type AnInt;
   AnInt = 44;
   cout << AnInt << endl;
}
```

```Output
44
```

## <a name="see-also"></a>Ayrıca bkz.

[C++ standart kitaplığı 'nda iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[C++ standart kitaplığı başvurusu](../standard-library/cpp-standard-library-reference.md)
