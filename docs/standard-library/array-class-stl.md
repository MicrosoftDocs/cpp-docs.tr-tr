---
title: Array sınıfı (C++ Standart Kitaplığı) | Microsoft Docs
ms.date: 11/13/2019
f1_keywords:
- array/std::array
- array/std::array::const_iterator
- array/std::array::const_pointer
- array/std::array::const_reference
- array/std::array::const_reverse_iterator
- array/std::array::difference_type
- array/std::array::iterator
- array/std::array::pointer
- array/std::array::reference
- array/std::array::reverse_iterator
- array/std::array::size_type
- array/std::array::value_type
- array/std::array::assign
- array/std::array::at
- array/std::array::back
- array/std::array::begin
- array/std::array::cbegin
- array/std::array::cend
- array/std::array::crbegin
- array/std::array::crend
- array/std::array::data
- array/std::array::empty
- array/std::array::end
- array/std::array::fill
- array/std::array::front
- array/std::array::max_size
- array/std::array::rbegin
- array/std::array::rend
- array/std::array::size
- array/std::array::swap
- array/std::array::operator=
- array/std::array::operator[]
helpviewer_keywords:
- std::array [C++]
- std::array [C++], const_iterator
- std::array [C++], const_pointer
- std::array [C++], const_reference
- std::array [C++], const_reverse_iterator
- std::array [C++], difference_type
- std::array [C++], iterator
- std::array [C++], pointer
- std::array [C++], reference
- std::array [C++], reverse_iterator
- std::array [C++], size_type
- std::array [C++], value_type
- std::array [C++], assign
- std::array [C++], at
- std::array [C++], back
- std::array [C++], begin
- std::array [C++], cbegin
- std::array [C++], cend
- std::array [C++], crbegin
- std::array [C++], crend
- std::array [C++], data
- std::array [C++], empty
- std::array [C++], end
- std::array [C++], fill
- std::array [C++], front
- std::array [C++], max_size
- std::array [C++], rbegin
- std::array [C++], rend
- std::array [C++], size
- std::array [C++], swap
- ', '
- std::array [C++], const_iterator
- std::array [C++], const_pointer
- std::array [C++], const_reference
- std::array [C++], const_reverse_iterator
- std::array [C++], difference_type
- std::array [C++], iterator
- std::array [C++], pointer
- std::array [C++], reference
- std::array [C++], reverse_iterator
- std::array [C++], size_type
- std::array [C++], value_type
- std::array [C++], assign
- std::array [C++], at
- std::array [C++], back
- std::array [C++], begin
- std::array [C++], cbegin
- std::array [C++], cend
- std::array [C++], crbegin
- std::array [C++], crend
- std::array [C++], data
- std::array [C++], empty
- std::array [C++], end
- std::array [C++], fill
- std::array [C++], front
- std::array [C++], max_size
- std::array [C++], rbegin
- std::array [C++], rend
- std::array [C++], size
- std::array [C++], swap
ms.assetid: fdfd43a5-b2b5-4b9e-991f-93bf10fb4293
ms.openlocfilehash: 9cde21624e3a8d4cce6db9cdc054bad427340f31
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87203916"
---
# <a name="array-class-c-standard-library"></a>Array sınıfı (C++ Standart Kitaplığı)

Türündeki öğelerin uzunluğunu denetleyen nesneyi tanımlar `N` `Ty` . Dizi, nesnesinde bulunan bir dizisi olarak depolanır `Ty` `array<Ty, N>` .

## <a name="syntax"></a>Söz dizimi

```cpp
template <class Ty, std::size_t N>
class array;
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|-|-|
|`Ty`|Öğenin türü.|
|`N`|Öğe sayısı.|

## <a name="members"></a>Üyeler

|Tür Tanımı|Açıklama|
|-|-|
|[const_iterator](#const_iterator)|Denetlenen dizi için bir sabit yineleyici türü.|
|[const_pointer](#const_pointer)|Bir öğe için sabit bir işaretçi türü.|
|[const_reference](#const_reference)|Bir öğe için sabit bir başvuru türü.|
|[const_reverse_iterator](#const_reverse_iterator)|Denetlenen sıra için bir sabit ters yineleyicinin türü.|
|[difference_type](#difference_type)|İki öğe arasındaki işaretli mesafenin türü.|
|[iden](#iterator)|Denetlenen dizi için bir yineleyici türü.|
|[pointer](#pointer)|Bir öğe için bir işaretçi türü.|
|[başvurunun](#reference)|Bir öğe için bir başvuru türü.|
|[reverse_iterator](#reverse_iterator)|Denetlenen sıra için ters yineleyicinin türü.|
|[size_type](#size_type)|İki öğe arasındaki işaretsiz bir mesafenin türü.|
|[value_type](#value_type)|Öğenin türü.|

|Üye İşlevi|Açıklama|
|-|-|
|[array](#array)|Bir dizi nesnesi oluşturur.|
|[assign (atamak)](#assign) |Dışı. Kullanın `fill` .) Tüm öğeleri değiştirir.|
|[hızı](#at)|Belirtilen konumdaki bir öğeye erişir.|
|[Geri](#back)|Son öğeye erişir.|
|[başladı](#begin)|Denetlenen dizinin başlangıcını belirtir.|
|[cbegin](#cbegin)|Dizideki ilk öğeye Rastgele erişimli bir const yineleyicisi döndürür.|
|[cend](#cend)|Dizinin sonunun hemen ötesinde işaret eden Rastgele erişimli bir const yineleyici döndürür.|
|[crbegin](#crbegin)|Ters çevrilen dizideki ilk öğeye bir const yineleyici döndürür.|
|[crend](#crend)|Ters çevrilen dizinin sonuna bir const yineleyici döndürür.|
|[data](#data)|İlk öğenin adresini alır.|
|[empty](#empty)|Öğelerin mevcut olup olmadığını sınar.|
|[erer](#end)|Denetlenen dizinin bitişini belirtir.|
|[doldurması](#fill)|Tüm öğeleri belirtilen değerle değiştirir.|
|[yapılan](#front)|İlk öğeye erişir.|
|[max_size](#max_size)|Öğe sayısını sayar.|
|[rbegin](#rbegin)|Ters denetlenen sıranın başlangıcını belirtir.|
|[rend](#rend)|Ters denetlenen sıranın sonunu belirtir.|
|[boyutla](#size)|Öğe sayısını sayar.|
|[Kur](#swap)|İki kapsayıcının içeriğinin yerini değiştirir.|

|İşleç|Açıklama|
|-|-|
|[Array:: operator =](#op_eq)|Denetlenen sırayı değiştirir.|
|[Array:: operator\[\]](#op_at)|Belirtilen konumdaki bir öğeye erişir.|

## <a name="remarks"></a>Açıklamalar

Türün varsayılan oluşturucusu `array()` ve varsayılan atama işleci vardır `operator=` ve bir için gereksinimleri karşılar `aggregate` . Bu nedenle, türündeki nesneler `array<Ty, N>` bir toplama başlatıcısı kullanılarak başlatılabilir. Örneğin,

```cpp
array<int, 4> ai = { 1, 2, 3 };
```

`ai`dört tamsayı değerini tutan nesneyi oluşturur, sırasıyla ilk üç öğeyi 1, 2 ve 3 değerlerine başlatır ve dördüncü öğeyi 0 olarak başlatır.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<array>

**Ad alanı:** std

## <a name="arrayarray"></a><a name="array"></a>Array:: Array

Bir dizi nesnesi oluşturur.

```cpp
array();

array(const array& right);
```

### <a name="parameters"></a>Parametreler

*Right*\
Eklenecek nesne veya Aralık.

### <a name="remarks"></a>Açıklamalar

Varsayılan Oluşturucu `array()` denetimli sırayı başlatılmamış olarak bırakır (veya varsayılan olarak başlatılır). Başlatılmamış bir denetim sırası belirtmek için bunu kullanırsınız.

Kopya Oluşturucu, `array(const array& right)` denetimli sırayı sırasıyla [*Right* `.begin()` , *Right* `.end()` ) başlatır. Dizi nesnesi *sağa*tarafından denetlenen sıranın bir kopyası olan ilk denetimli bir sıra belirtmek için bunu kullanırsınız.

### <a name="example"></a>Örnek

```cpp
#include <array>
#include <iostream>

typedef std::array<int, 4> Myarray;
int main()
{
    typedef std::array<int, 4> Myarray;

    Myarray c0 = { 0, 1, 2, 3 };

    // display contents " 0 1 2 3"
    for (const auto& it : c0)
    {
        std::cout << " " << it;
    }
    std::cout << std::endl;

    Myarray c1(c0);

    // display contents " 0 1 2 3"
    for (const auto& it : c1)
    {
        std::cout << " " << it;
    }
    std::cout << std::endl;

    return (0);
}
```

```Output
0 1 2 3
0 1 2 3
```

## <a name="arrayassign"></a><a name="assign"></a>Array:: Assign

C++ 11 ' de kullanılmıyor, [Fill](#fill)ile değiştirilmiştir. Tüm öğeleri değiştirir.

## <a name="arrayat"></a><a name="at"></a>Array:: at

Belirtilen konumdaki bir öğeye erişir.

```cpp
reference at(size_type off);

constexpr const_reference at(size_type off) const;
```

### <a name="parameters"></a>Parametreler

*dışına*\
Erişim için öğenin konumu.

### <a name="remarks"></a>Açıklamalar

Üye işlevleri, konumundaki denetimli sıranın öğesine bir başvuru *döndürür.* Bu konum geçersizse, işlev sınıfının bir nesnesini oluşturur `out_of_range` .

### <a name="example"></a>Örnek

```cpp
#include <array>
#include <iostream>

typedef std::array<int, 4> Myarray;
int main()
{
    Myarray c0 = { 0, 1, 2, 3 };

    // display contents " 0 1 2 3"
    for (const auto& it : c0)
    {
        std::cout << " " << it;
    }
    std::cout << std::endl;

    // display odd elements " 1 3"
    std::cout << " " << c0.at(1);
    std::cout << " " << c0.at(3);
    std::cout << std::endl;

    return (0);
}
```

## <a name="arrayback"></a><a name="back"></a>Array:: Back

Son öğeye erişir.

```cpp
reference back();

constexpr const_reference back() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevleri denetlenen sıranın son öğesine bir başvuru döndürür, bu da boş olmamalıdır.

### <a name="example"></a>Örnek

```cpp
#include <array>
#include <iostream>

typedef std::array<int, 4> Myarray;
int main()
{
    Myarray c0 = { 0, 1, 2, 3 };

    // display contents " 0 1 2 3"
    for (const auto& it : c0)
    {
        std::cout << " " << it;
    }
    std::cout << std::endl;

    // display last element " 3"
    std::cout << " " << c0.back();
    std::cout << std::endl;

    return (0);
}
```

```Output
0 1 2 3
3
```

## <a name="arraybegin"></a><a name="begin"></a>Array:: Begin

Denetlenen dizinin başlangıcını belirtir.

```cpp
iterator begin() noexcept;
const_iterator begin() const noexcept;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevleri, dizinin ilk öğesini işaret eden (veya boş bir dizinin sonunun ötesinde) bir rastgele erişim yineleyici döndürür.

### <a name="example"></a>Örnek

```cpp
#include <array>
#include <iostream>

typedef std::array<int, 4> Myarray;
int main()
{
    Myarray c0 = { 0, 1, 2, 3 };

    // display contents " 0 1 2 3"
    for (const auto& it : c0)
    {
        std::cout << " " << it;
    }
    std::cout << std::endl;

    // display first element " 0"
    Myarray::iterator it2 = c0.begin();
    std::cout << " " << *it2;
    std::cout << std::endl;

    return (0);
}
```

```Output
0 1 2 3
0
```

## <a name="arraycbegin"></a><a name="cbegin"></a>Array:: cbegin

**`const`** Aralıktaki ilk öğeyi ele alan bir yineleyici döndürür.

```cpp
const_iterator cbegin() const noexcept;
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

## <a name="arraycend"></a><a name="cend"></a>Array:: cend

**`const`** Bir aralıktaki son öğenin ötesinde konumu ele alan bir yineleyici döndürür.

```cpp
const_iterator cend() const noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

Aralığın hemen sonunu gösteren bir rastgele erişim yineleyicisi.

### <a name="remarks"></a>Açıklamalar

`cend`, bir yineleyicinin aralığın sonunu geçtiğini test etmek için kullanılır.

`end()`Dönüş değerinin olduğunu garantilemek için üye işlevin yerine bu üye işlevi kullanabilirsiniz `const_iterator` . Genellikle, aşağıdaki örnekte gösterildiği gibi [Otomatik](../cpp/auto-cpp.md) tür kesintisi anahtar sözcüğüyle birlikte kullanılır. Örnekte, ve ' ı `Container` destekleyen herhangi bir türde değiştirilebilir (olmayan) bir kapsayıcı olarak göz önünde bulundurun **`const`** `end()` `cend()` .

```cpp
auto i1 = Container.end();
// i1 is Container<T>::iterator
auto i2 = Container.cend();

// i2 is Container<T>::const_iterator
```

Tarafından döndürülen değer `cend` başvurulmamalıdır.

## <a name="arrayconst_iterator"></a><a name="const_iterator"></a>dizi:: const_iterator

Denetlenen dizi için bir sabit yineleyici türü.

```cpp
typedef implementation-defined const_iterator;
```

### <a name="remarks"></a>Açıklamalar

Türü, denetimli sıra için sabit bir rastgele erişim Yineleyici işlevi görebilecek bir nesneyi tanımlar.

### <a name="example"></a>Örnek

```cpp
#include <array>
#include <iostream>

typedef std::array<int, 4> MyArray;

int main()
{
    MyArray c0 = { 0, 1, 2, 3 };

    // display contents " 0 1 2 3"
    std::cout << "it1:";
    for (MyArray::const_iterator it1 = c0.begin();
        it1 != c0.end();
        ++it1) {
        std::cout << " " << *it1;
    }
    std::cout << std::endl;

    // display first element " 0"
    MyArray::const_iterator it2 = c0.begin();
    std::cout << "it2:";
    std::cout << " " << *it2;
    std::cout << std::endl;

    return (0);
}
```

```Output
it1: 0 1 2 3
it2: 0
```

## <a name="arrayconst_pointer"></a><a name="const_pointer"></a>dizi:: const_pointer

Bir öğe için sabit bir işaretçi türü.

```cpp
typedef const Ty *const_pointer;
```

### <a name="remarks"></a>Açıklamalar

Türü, sıranın öğelerine sabit bir işaretçi olarak kullanılabilecek bir nesneyi tanımlar.

### <a name="example"></a>Örnek

```cpp
#include <array>
#include <iostream>

typedef std::array<int, 4> Myarray;
int main()
{
    Myarray c0 = { 0, 1, 2, 3 };

    // display contents " 0 1 2 3"
    for (const auto& it : c0)
    {
        std::cout << " " << it;
    }
    std::cout << std::endl;

    // display first element " 0"
    Myarray::const_pointer ptr = &*c0.begin();
    std::cout << " " << *ptr;
    std::cout << std::endl;

    return (0);
}
```

```Output
0 1 2 3
0
```

## <a name="arrayconst_reference"></a><a name="const_reference"></a>dizi:: const_reference

Bir öğe için sabit bir başvuru türü.

```cpp
typedef const Ty& const_reference;
```

### <a name="remarks"></a>Açıklamalar

Türü, denetlenen dizinin bir öğesine sabit başvuru olarak işlev yapabilecek bir nesneyi tanımlar.

### <a name="example"></a>Örnek

```cpp
#include <array>
#include <iostream>

typedef std::array<int, 4> Myarray;
int main()
{
    Myarray c0 = { 0, 1, 2, 3 };

    // display contents " 0 1 2 3"
    for (const auto& it : c0)
    {
        std::cout << " " << it;
    }
    std::cout << std::endl;

    // display first element " 0"
    Myarray::const_reference ref = *c0.begin();
    std::cout << " " << ref;
    std::cout << std::endl;

    return (0);
}
```

```Output
0 1 2 3
0
```

## <a name="arrayconst_reverse_iterator"></a><a name="const_reverse_iterator"></a>dizi:: const_reverse_iterator

Denetlenen sıra için bir sabit ters yineleyicinin türü.

```cpp
typedef std::reverse_iterator<const_iterator> const_reverse_iterator;
```

### <a name="remarks"></a>Açıklamalar

Türü, denetimli sıra için sabit bir ters Yineleyici işlevi görebilecek bir nesneyi tanımlar.

### <a name="example"></a>Örnek

```cpp
#include <array>
#include <iostream>

typedef std::array<int, 4> Myarray;
int main()
{
    Myarray c0 = { 0, 1, 2, 3 };

    // display contents " 0 1 2 3"
    for (const auto& it : c0)
    {
        std::cout << " " << it;
    }
    std::cout << std::endl;

    // display last element " 3"
    Myarray::const_reverse_iterator it2 = c0.rbegin();
    std::cout << " " << *it2;
    std::cout << std::endl;

    return (0);
}
```

```Output
0 1 2 3
3
```

## <a name="arraycrbegin"></a><a name="crbegin"></a>Array:: crbegin

Ters çevrilen dizideki ilk öğeye bir const yineleyici döndürür.

```cpp
const_reverse_iterator crbegin() const;
```

### <a name="return-value"></a>Dönüş Değeri

Ters çevrilen dizideki ilk öğeyi ele alarak veya geri çevrilmeyen dizide son öğenin ne olduğunu adresleyen bir const ters rasgele erişim Yineleyici.

### <a name="remarks"></a>Açıklamalar

Dönüş değeri ile `crbegin` , dizi nesnesi değiştirilemez.

### <a name="example"></a>Örnek

```cpp
#include <array>
#include <iostream>

int main( )
{
   using namespace std;
   array<int, 2> v1 = {1, 2};
   array<int, 2>::iterator v1_Iter;
   array<int, 2>::const_reverse_iterator v1_rIter;

   v1_Iter = v1.begin( );
   cout << "The first element of array is "
        << *v1_Iter << "." << endl;

   v1_rIter = v1.crbegin( );
   cout << "The first element of the reversed array is "
        << *v1_rIter << "." << endl;
}
```

```Output
The first element of array is 1.
The first element of the reversed array is 2.
```

## <a name="arraycrend"></a><a name="crend"></a>dizi:: crend

Ters çevrilen dizideki son öğeden sonraki konumu ele alan bir const yineleyici döndürür.

```cpp
const_reverse_iterator crend() const noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

Ters çevrilen bir dizideki son öğeden sonra gelen konumu ele alan bir sabit ters rastgele erişim yineleyici (geri çevrilmeyen dizide ilk öğeden önce gelen konum).

### <a name="remarks"></a>Açıklamalar

`crend`[Array:: cend](#cend) , bir dizi ile birlikte kullanıldığında, ters çevrilmiş bir dizi ile birlikte kullanılır.

Dönüş değeri `crend` (uygun şekilde azaltılır) ile dizi nesnesi değiştirilemez.

`crend`, bir ters yineleyicinin dizisinin sonuna ulaşıp ulaşılmadığını test etmek için kullanılabilir.

Tarafından döndürülen değer `crend` başvurulmamalıdır.

### <a name="example"></a>Örnek

```cpp
#include <array>
#include <iostream>

int main( )
{
   using namespace std;
   array<int, 2> v1 = {1, 2};
   array<int, 2>::const_reverse_iterator v1_rIter;

   for ( v1_rIter = v1.rbegin( ) ; v1_rIter != v1.rend( ) ; v1_rIter++ )
      cout << *v1_rIter << endl;
}
```

```Output
2
1
```

## <a name="arraydata"></a><a name="data"></a>dizi: ata:d

İlk öğenin adresini alır.

```cpp
Ty *data();

const Ty *data() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevleri denetlenen dizideki ilk öğenin adresini döndürür.

### <a name="example"></a>Örnek

```cpp
#include <array>
#include <iostream>

typedef std::array<int, 4> Myarray;
int main()
{
    Myarray c0 = { 0, 1, 2, 3 };

    // display contents " 0 1 2 3"
    for (const auto& it : c0)
    {
        std::cout << " " << it;
    }
    std::cout << std::endl;

    // display first element " 0"
    Myarray::pointer ptr = c0.data();
    std::cout << " " << *ptr;
    std::cout << std::endl;

    return (0);
}
```

```Output
0 1 2 3
0
```

## <a name="arraydifference_type"></a><a name="difference_type"></a>dizi::d ifference_type

İki öğe arasındaki işaretli mesafenin türü.

```cpp
typedef std::ptrdiff_t difference_type;
```

### <a name="remarks"></a>Açıklamalar

İmzalanan tamsayı türü, denetlenen dizideki herhangi iki öğenin adresleri arasındaki farkı temsil eden bir nesneyi tanımlar. Türün eşanlamlısıdır `std::ptrdiff_t` .

### <a name="example"></a>Örnek

```cpp
#include <array>
#include <iostream>

typedef std::array<int, 4> Myarray;
int main()
{
    Myarray c0 = { 0, 1, 2, 3 };

    // display contents " 0 1 2 3"
    for (const auto& it : c0)
    {
        std::cout << " " << it;
    }
    std::cout << std::endl;

    // display distance first-last " -4"
    Myarray::difference_type diff = c0.begin() - c0.end();
    std::cout << " " << diff;
    std::cout << std::endl;

    return (0);
}
```

```Output
0 1 2 3
-4
```

## <a name="arrayempty"></a><a name="empty"></a>Array:: Empty

Bir öğe olup olmadığını sınar.

```cpp
constexpr bool empty() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi yalnızca ise true değerini döndürür `N == 0` .

### <a name="example"></a>Örnek

```cpp
#include <array>
#include <iostream>

typedef std::array<int, 4> Myarray;
int main()
{
    Myarray c0 = { 0, 1, 2, 3 };

    // display contents " 0 1 2 3"
    for (const auto& it : c0)
    {
        std::cout << " " << it;
    }
    std::cout << std::endl;

    // display whether c0 is empty " false"
    std::cout << std::boolalpha << " " << c0.empty();
    std::cout << std::endl;

    std::array<int, 0> c1;

    // display whether c1 is empty " true"
    std::cout << std::boolalpha << " " << c1.empty();
    std::cout << std::endl;

    return (0);
}
```

```Output
0 1 2 3
false
true
```

## <a name="arrayend"></a><a name="end"></a>Array:: End

Denetlenen dizinin bitişini belirtir.

```cpp
reference end();

const_reference end() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevleri, dizinin sonunun hemen ötesinde işaret eden bir rastgele erişim yineleyici döndürür.

### <a name="example"></a>Örnek

```cpp
#include <array>
#include <iostream>

typedef std::array<int, 4> Myarray;
int main()
{
    Myarray c0 = { 0, 1, 2, 3 };

    // display contents " 0 1 2 3"
    for (const auto& it : c0)
    {
        std::cout << " " << it;
    }
    std::cout << std::endl;

    // display last element " 3"
    Myarray::iterator it2 = c0.end();
    std::cout << " " << *--it2;
    std::cout << std::endl;

    return (0);
}
```

```Output
0 1 2 3
3
```

## <a name="arrayfill"></a><a name="fill"></a>Array:: Fill

Bir diziyi siler ve belirtilen öğeleri boş diziye kopyalar.

```cpp
void fill(const Type& val);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|-|-|
|*Acil*|Diziye eklenmekte olan öğenin değeri.|

### <a name="remarks"></a>Açıklamalar

`fill`dizinin her öğesini belirtilen değerle değiştirir.

### <a name="example"></a>Örnek

```cpp
#include <array>
#include <iostream>

int main()
{
    using namespace std;
    array<int, 2> v1 = { 1, 2 };

    cout << "v1 = ";
    for (const auto& it : v1)
    {
        std::cout << " " << it;
    }
    cout << endl;

    v1.fill(3);
    cout << "v1 = ";
    for (const auto& it : v1)
    {
        std::cout << " " << it;
    }
    cout << endl;
}
```

## <a name="arrayfront"></a><a name="front"></a>Array:: Front

İlk öğeye erişir.

```cpp
reference front();

constexpr const_reference front() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevleri denetlenen sıranın ilk öğesine bir başvuru döndürür ve bu boş olmamalıdır.

### <a name="example"></a>Örnek

```cpp
#include <array>
#include <iostream>

typedef std::array<int, 4> Myarray;
int main()
{
    Myarray c0 = { 0, 1, 2, 3 };

    // display contents " 0 1 2 3"
    for (const auto& it : c0)
    {
        std::cout << " " << it;
    }
    std::cout << std::endl;

    // display first element " 0"
    std::cout << " " << c0.front();
    std::cout << std::endl;

    return (0);
}
```

```Output
0 1 2 3
0
```

## <a name="arrayiterator"></a><a name="iterator"></a>Array:: Yineleyici

Denetlenen dizi için bir yineleyici türü.

```cpp
typedef implementation-defined iterator;
```

### <a name="remarks"></a>Açıklamalar

Türü, denetimli sıra için rastgele erişim Yineleyici işlevi görebilecek bir nesneyi tanımlar.

### <a name="example"></a>Örnek

```cpp
#include <array>
#include <iostream>

typedef std::array<int, 4> MyArray;

int main()
{
    MyArray c0 = { 0, 1, 2, 3 };

    // display contents " 0 1 2 3"
    std::cout << "it1:";
    for (MyArray::iterator it1 = c0.begin();
        it1 != c0.end();
        ++it1) {
        std::cout << " " << *it1;
    }
    std::cout << std::endl;

    // display first element " 0"
    MyArray::iterator it2 = c0.begin();
    std::cout << "it2:";
    std::cout << " " << *it2;
    std::cout << std::endl;

    return (0);
}
```

```Output
it1: 0 1 2 3

it2: 0
```

## <a name="arraymax_size"></a><a name="max_size"></a>dizi:: max_size

Öğe sayısını sayar.

```cpp
constexpr size_type max_size() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi döndürür `N` .

### <a name="example"></a>Örnek

```cpp
#include <array>
#include <iostream>

typedef std::array<int, 4> Myarray;
int main()
{
    Myarray c0 = { 0, 1, 2, 3 };

    // display contents " 0 1 2 3"
    for (const auto& it : c0)
    {
        std::cout << " " << it;
    }
    std::cout << std::endl;

    // display (maximum) size " 4"
    std::cout << " " << c0.max_size();
    std::cout << std::endl;

    return (0);
}
```

```Output
0 1 2 3
4
```

## <a name="arrayoperator"></a><a name="op_at"></a>Array:: operator []

Belirtilen konumdaki bir öğeye erişir.

```cpp
reference operator[](size_type off);

constexpr const_reference operator[](size_type off) const;
```

### <a name="parameters"></a>Parametreler

*dışına*\
Erişim için öğenin konumu.

### <a name="remarks"></a>Açıklamalar

Üye işlevleri, konumundaki denetimli sıranın öğesine bir başvuru *döndürür.* Bu konum geçersizse, davranış tanımsızdır.

Ayrıca, bir **dizinin**öğesine başvuru almak için üye olmayan bir [Get](array-functions.md#get) işlevi de mevcuttur.

### <a name="example"></a>Örnek

```cpp
#include <array>
#include <iostream>

typedef std::array<int, 4> Myarray;
int main()
{
    Myarray c0 = { 0, 1, 2, 3 };

    // display contents " 0 1 2 3"
    for (const auto& it : c0)
    {
        std::cout << " " << it;
    }
    std::cout << std::endl;

    // display odd elements " 1 3"
    std::cout << " " << c0[1];
    std::cout << " " << c0[3];
    std::cout << std::endl;

    return (0);
}
```

```Output
0 1 2 3
1 3
```

## <a name="arrayoperator"></a><a name="op_eq"></a>Array:: operator =

Denetlenen sırayı değiştirir.

```cpp
array<Value> operator=(array<Value> right);
```

### <a name="parameters"></a>Parametreler

*Right*\
Kopyalanacak kapsayıcı.

### <a name="remarks"></a>Açıklamalar

Member işleci, her bir öğesini denetimli sıranın karşılık *gelen öğesine atar* ve ardından döndürür **`*this`** . Denetlenen diziyi, denetimli sıranın bir kopyasıyla değiştirmek için bunu *kullanırsınız.*

### <a name="example"></a>Örnek

```cpp
#include <array>
#include <iostream>

typedef std::array<int, 4> Myarray;
int main()
{
    Myarray c0 = { 0, 1, 2, 3 };

    // display contents " 0 1 2 3"
    for (const auto& it : c0)
    {
        std::cout << " " << it;
    }
    std::cout << std::endl;

    Myarray c1;
    c1 = c0;

    // display copied contents " 0 1 2 3"
        // display contents " 0 1 2 3"
    for (auto it : c1)
    {
        std::cout << " " << it;
    }
    std::cout << std::endl;

    return (0);
}
```

```Output
0 1 2 3
0 1 2 3
```

## <a name="arraypointer"></a><a name="pointer"></a>dizi::p oınter

Bir öğe için bir işaretçi türü.

```cpp
typedef Ty *pointer;
```

### <a name="remarks"></a>Açıklamalar

Türü, sıranın öğelerinin işaretçisi olarak işlev görebilecek bir nesne tanımlar.

### <a name="example"></a>Örnek

```cpp
#include <array>
#include <iostream>

typedef std::array<int, 4> Myarray;
int main()
{
    Myarray c0 = { 0, 1, 2, 3 };

    // display contents " 0 1 2 3"
    for (const auto& it : c0)
    {
        std::cout << " " << it;
    }
    std::cout << std::endl;

    // display first element " 0"
    Myarray::pointer ptr = &*c0.begin();
    std::cout << " " << *ptr;
    std::cout << std::endl;

    return (0);
}
```

```Output
0 1 2 3
0
```

## <a name="arrayrbegin"></a><a name="rbegin"></a>Array:: rbegin

Ters denetlenen sıranın başlangıcını belirtir.

```cpp
reverse_iterator rbegin()noexcept;
const_reverse_iterator rbegin() const noexcept;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevleri, denetimli dizinin sonunun hemen ötesinde bir ters yineleyici döndürür. Bu nedenle, ters sıranın başlangıcını belirler.

### <a name="example"></a>Örnek

```cpp
#include <array>
#include <iostream>

typedef std::array<int, 4> Myarray;
int main()
{
    Myarray c0 = { 0, 1, 2, 3 };

    // display contents " 0 1 2 3"
    for (const auto& it : c0)
    {
        std::cout << " " << it;
    }
    std::cout << std::endl;

    // display last element " 3"
    Myarray::const_reverse_iterator it2 = c0.rbegin();
    std::cout << " " << *it2;
    std::cout << std::endl;

    return (0);
}
```

```Output
0 1 2 3
3
```

## <a name="arrayreference"></a><a name="reference"></a>Array:: Reference

Bir öğe için bir başvuru türü.

```cpp
typedef Ty& reference;
```

### <a name="remarks"></a>Açıklamalar

Türü, denetlenen sıranın bir öğesine başvuru olarak işlev görebilecek bir nesne tanımlar.

### <a name="example"></a>Örnek

```cpp
#include <array>
#include <iostream>

typedef std::array<int, 4> Myarray;
int main()
{
    Myarray c0 = { 0, 1, 2, 3 };

    // display contents " 0 1 2 3"
    for (const auto& it : c0)
    {
        std::cout << " " << it;
    }
    std::cout << std::endl;

    // display first element " 0"
    Myarray::reference ref = *c0.begin();
    std::cout << " " << ref;
    std::cout << std::endl;

    return (0);
}
```

```Output
0 1 2 3
0
```

## <a name="arrayrend"></a><a name="rend"></a>dizi:: rend

Ters denetlenen sıranın sonunu belirtir.

```cpp
reverse_iterator rend()noexcept;
const_reverse_iterator rend() const noexcept;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevleri, sıranın ilk öğesini işaret eden bir ters yineleyici döndürür (veya bir boş dizinin sonunun ötesinde)). Bu nedenle, ters sıranın sonunu belirler.

### <a name="example"></a>Örnek

```cpp
#include <array>
#include <iostream>

typedef std::array<int, 4> Myarray;
int main()
{
    Myarray c0 = { 0, 1, 2, 3 };

    // display contents " 0 1 2 3"
    for (const auto& it : c0)
    {
        std::cout << " " << it;
    }
    std::cout << std::endl;

    // display first element " 0"
    Myarray::const_reverse_iterator it2 = c0.rend();
    std::cout << " " << *--it2;
    std::cout << std::endl;

    return (0);
}
```

```Output
0 1 2 3
0
```

## <a name="arrayreverse_iterator"></a><a name="reverse_iterator"></a>dizi:: reverse_iterator

Denetlenen sıra için ters yineleyicinin türü.

```cpp
typedef std::reverse_iterator<iterator> reverse_iterator;
```

### <a name="remarks"></a>Açıklamalar

Türü, denetimli sıra için ters Yineleyici işlevi görebilecek bir nesneyi tanımlar.

### <a name="example"></a>Örnek

```cpp
#include <array>
#include <iostream>

typedef std::array<int, 4> Myarray;
int main()
{
    Myarray c0 = { 0, 1, 2, 3 };

    // display contents " 0 1 2 3"
    for (const auto& it : c0)
    {
        std::cout << " " << it;
    }
    std::cout << std::endl;

    // display last element " 3"
    Myarray::reverse_iterator it2 = c0.rbegin();
    std::cout << " " << *it2;
    std::cout << std::endl;

    return (0);
}
```

```Output
0 1 2 3
3
```

## <a name="arraysize"></a><a name="size"></a>Array:: size

Öğe sayısını sayar.

```cpp
constexpr size_type size() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi döndürür `N` .

### <a name="example"></a>Örnek

```cpp
#include <array>
#include <iostream>

typedef std::array<int, 4> Myarray;
int main()
{
    Myarray c0 = { 0, 1, 2, 3 };

    // display contents " 0 1 2 3"
    for (const auto& it : c0)
    {
        std::cout << " " << it;
    }
    std::cout << std::endl;

    // display size " 4"
    std::cout << " " << c0.size();
    std::cout << std::endl;

    return (0);
}
```

```Output
0 1 2 3
4
```

## <a name="arraysize_type"></a><a name="size_type"></a>dizi:: size_type

İki öğe arasındaki işaretsiz mesafe türü.

```cpp
typedef std::size_t size_type;
```

### <a name="remarks"></a>Açıklamalar

İşaretsiz tamsayı türü, denetlenen bir dizinin uzunluğunu temsil eden bir nesneyi tanımlar. Türün eşanlamlısıdır `std::size_t` .

### <a name="example"></a>Örnek

```cpp
#include <array>
#include <iostream>

typedef std::array<int, 4> Myarray;
int main()
{
    Myarray c0 = { 0, 1, 2, 3 };

    // display contents " 0 1 2 3"
    for (const auto& it : c0)
    {
        std::cout << " " << it;
    }
    std::cout << std::endl;

    // display distance last-first " 4"
    Myarray::size_type diff = c0.end() - c0.begin();
    std::cout << " " << diff;
    std::cout << std::endl;

    return (0);
}
```

```Output
0 1 2 3
4
```

## <a name="arrayswap"></a><a name="swap"></a>Array:: swap

Bu dizinin içeriğini başka bir dizi ile değiştirir.

```cpp
void swap(array& right);
```

### <a name="parameters"></a>Parametreler

*Right*\
İçeriği takas eden dizi.

### <a name="remarks"></a>Açıklamalar

Üye işlevi, ve sağ arasındaki denetlenen dizileri **`*this`** değiştirir *right*. Bir dizi öğe ataması gerçekleştirir ve Oluşturucu çağrıları ile orantılıdır `N` .

Ayrıca, iki **dizi** örneğini değiştirmek için üye olmayan bir [değiştirme](array-functions.md#swap) işlevi de mevcuttur.

### <a name="example"></a>Örnek

```cpp
#include <array>
#include <iostream>

typedef std::array<int, 4> Myarray;
int main()
{
    Myarray c0 = { 0, 1, 2, 3 };

    // display contents " 0 1 2 3"
    for (const auto& it : c0)
    {
        std::cout << " " << it;
    }
    std::cout << std::endl;

    Myarray c1 = { 4, 5, 6, 7 };
    c0.swap(c1);

    // display swapped contents " 4 5 6 7"
    for (const auto& it : c0)
    {
        std::cout << " " << it;
    }
    std::cout << std::endl;

    swap(c0, c1);

    // display swapped contents " 0 1 2 3"
    for (const auto& it : c0)
    {
        std::cout << " " << it;
    }
    std::cout << std::endl;

    return (0);
}
```

```Output
0 1 2 3
4 5 6 7
0 1 2 3
```

## <a name="arrayvalue_type"></a><a name="value_type"></a>dizi:: value_type

Öğenin türü.

```cpp
typedef Ty value_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, şablon parametresi için bir eş anlamlı `Ty` .

### <a name="example"></a>Örnek

```cpp
#include <array>
#include <iostream>

typedef std::array<int, 4> Myarray;
int main()
{
    Myarray c0 = { 0, 1, 2, 3 };

    // display contents " 0 1 2 3"
    for (const auto& it : c0)
    {
        std::cout << " " << it;
    }
    std::cout << std::endl;

    // display contents " 0 1 2 3"
    for (const auto& it : c0)
    {
        Myarray::value_type val = it;
        std::cout << " " << val;
    }
    std::cout << std::endl;

    return (0);
}
```

```Output
0 1 2 3
0 1 2 3
```

## <a name="see-also"></a>Ayrıca bkz.

[\<array>](../standard-library/array.md)
