---
title: dizi Sınıfı (C++ Standart Kitaplık)| Microsoft Dokümanlar
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
ms.openlocfilehash: 90c68d00475a622ec89b81cc86639f63b1190d02
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364953"
---
# <a name="array-class-c-standard-library"></a>dizi Sınıfı (C++ Standart Kitaplık)

Tür `N` `Ty`öğelerinin uzunluk sırasını denetleyen bir nesneyi açıklar. `Ty`Dizi, `array<Ty, N>` nesnenin içinde bulunan bir dizi olarak depolanır.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Ty, std::size_t N>
class array;
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|-|-|
|`Ty`|Öğenin türü.|
|`N`|Öğelerin sayısı.|

## <a name="members"></a>Üyeler

|Tür Tanımlaması|Açıklama|
|-|-|
|[const_iterator](#const_iterator)|Denetlenen dizi için bir sabit yineleyici türü.|
|[Const_pointer](#const_pointer)|Bir öğe için sabit bir işaretçi türü.|
|[const_reference](#const_reference)|Bir öğe için sabit bir başvuru türü.|
|[Const_reverse_iterator](#const_reverse_iterator)|Denetlenmeyen dizi için sabit bir ters yineleyici türü.|
|[difference_type](#difference_type)|İki öğe arasındaki işaretli mesafenin türü.|
|[Yineleyici](#iterator)|Denetlenen dizi için bir yineleyici türü.|
|[pointer](#pointer)|Bir öğe için bir işaretçi türü.|
|[Başvuru](#reference)|Bir öğe için bir başvuru türü.|
|[Reverse_iterator](#reverse_iterator)|Denetlenen dizi için ters yineleyici türü.|
|[size_type](#size_type)|İki öğe arasındaki işaretsiz bir mesafenin türü.|
|[value_type](#value_type)|Öğenin türü.|

|Üye İşlevi|Açıklama|
|-|-|
|[Dizi](#array)|Bir dizi nesnesi oluşturuyor.|
|[Atamak](#assign)|(Eski. Kullanın `fill`.) Tüm öğeleri değiştirir.|
|[at](#at)|Belirli bir konumda bir öğeye erişir.|
|[Geri](#back)|Son öğeye erişir.|
|[Başlamak](#begin)|Denetlenen dizinin başlangıcını belirtir.|
|[cbegin](#cbegin)|Dizideki ilk öğeye rasgele erişimli bir const yineleyici döndürür.|
|[cend](#cend)|Dizinin sonunun hemen ötesine işaret eden rasgele erişimli bir const yineleyici döndürür.|
|[crbegin](#crbegin)|Bir const yineleyiciyi ters dizideki ilk öğeye döndürür.|
|[crend](#crend)|Bir const yineleyiciyi ters bir dizinin sonuna döndürür.|
|[Veri](#data)|İlk öğenin adresini alır.|
|[empty](#empty)|Öğelerin var olup olmadığını test edin.|
|[Son -unda](#end)|Denetlenen dizinin bitişini belirtir.|
|[fill](#fill)|Tüm öğeleri belirli bir değerle değiştirir.|
|[Ön](#front)|İlk öğeye erişir.|
|[max_size](#max_size)|Öğe sayısını sayar.|
|[rbegin](#rbegin)|Ters denetimli dizinin başlangıcını belirler.|
|[Rend](#rend)|Ters denetimli dizinin sonunu belirler.|
|[Boyutu](#size)|Öğe sayısını sayar.|
|[Takas](#swap)|İki kapsayıcının içeriğinin yerini değiştirir.|

|İşleç|Açıklama|
|-|-|
|[dizi::operator=](#op_eq)|Denetedilen sırayı değiştirir.|
|[dizi::operatör\[\]](#op_at)|Belirli bir konumda bir öğeye erişir.|

## <a name="remarks"></a>Açıklamalar

Tür, varsayılan bir `array()` oluşturucuya ve `operator=`varsayılan atama işlecine sahiptir `aggregate`ve bir . Bu nedenle, tür `array<Ty, N>` nesneleri bir toplu baş harfi zerre kullanılarak baş harfe çevrilir. Örneğin,

```cpp
array<int, 4> ai = { 1, 2, 3 };
```

dört karşım `ai` değeri tutan nesneyi oluşturur, sırasıyla 1, 2 ve 3 değerlerinin ilk üç öğesini başharfe ve dördüncü öğeyi 0'a başlar.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** \<dizi>

**Ad alanı:** std

## <a name="arrayarray"></a><a name="array"></a>dizi::dizi

Bir dizi nesnesi oluşturuyor.

```cpp
array();

array(const array& right);
```

### <a name="parameters"></a>Parametreler

*Doğru*\
Eklemek için nesne veya aralık.

### <a name="remarks"></a>Açıklamalar

Varsayılan oluşturucu, `array()` denetlenmiş sırayı başharfsiz (veya varsayılan olarak başlatif) bırakır. Başharfe getirilmemiş bir denetim sırası belirtmek için kullanırsınız.

Kopya oluşturucu `array(const array& right)` [ sağ ,*sağ*`.begin()` *right*`.end()`] dizisi ile kontrollü sırayı başlatir. Dizi nesnesi *sağ*tarafından denetlenir dizi bir kopyası olan bir ilk kontrollü dizi belirtmek için kullanabilirsiniz.

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

## <a name="arrayassign"></a><a name="assign"></a>dizi::atama

C++11'de eskimiş, [yerine dolgu](#fill). Tüm öğeleri değiştirir.

## <a name="arrayat"></a><a name="at"></a>dizi::at

Belirli bir konumda bir öğeye erişir.

```cpp
reference at(size_type off);

constexpr const_reference at(size_type off) const;
```

### <a name="parameters"></a>Parametreler

*kapalı*\
Öğenin erişim konumu.

### <a name="remarks"></a>Açıklamalar

Üye *işlevler,* kapalı konumda denetitilen dizinin öğesine bir başvuru döndürür. Bu konum geçersizse, işlev sınıf `out_of_range`nesnesi atar.

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

## <a name="arrayback"></a><a name="back"></a>dizi::geri

Son öğeye erişir.

```cpp
reference back();

constexpr const_reference back() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevler, boş olmayan kontrollü dizinin son öğesine bir başvuru döndürür.

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

## <a name="arraybegin"></a><a name="begin"></a>dizi::başla

Denetlenen dizinin başlangıcını belirtir.

```cpp
iterator begin() noexcept;
const_iterator begin() const noexcept;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevler, dizinin ilk öğesini (veya boş bir dizinin sonundan hemen sonra) işaret eden rasgele erişim yineleyicidöndürür.

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

## <a name="arraycbegin"></a><a name="cbegin"></a>dizi::cbegin

Aralıktaki ilk öğeyi ele alan bir **const** yineleyici döndürür.

```cpp
const_iterator cbegin() const noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

Aralığın ilk öğesini veya boş aralığın sonundaki konumu işaret eden **bir const** rasgele erişim yineleyicisi `cbegin() == cend()`(boş bir aralık için).

### <a name="remarks"></a>Açıklamalar

İade değeri ile `cbegin`aralıktaki öğeler değiştirilemez.

Bu üye `begin()` işlevini, iade değerinin `const_iterator`. Genellikle, aşağıdaki örnekte gösterildiği gibi [otomatik](../cpp/auto-cpp.md) tür kesintisi anahtar sözcüğüyle birlikte kullanılır. Örnekte, herhangi `Container` bir tür değiştirilebilir (non-const) kapsayıcı ve `begin()` destekler `cbegin()`düşünün. **const**

```cpp
auto i1 = Container.begin();
// i1 is Container<T>::iterator
auto i2 = Container.cbegin();

// i2 is Container<T>::const_iterator
```

## <a name="arraycend"></a><a name="cend"></a>dizi::cend

Bir aralıktaki son öğenin hemen ötesinde konuma hitap eden bir **const** yineleyici döndürür.

```cpp
const_iterator cend() const noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

Aralığın hemen sonunu gösteren bir rastgele erişim yineleyicisi.

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

## <a name="arrayconst_iterator"></a><a name="const_iterator"></a>dizi::const_iterator

Denetlenen dizi için bir sabit yineleyici türü.

```cpp
typedef implementation-defined const_iterator;
```

### <a name="remarks"></a>Açıklamalar

Tür, denetlenen dizi için sabit bir rasgele erişim yineleyicisi olarak hizmet verebilen bir nesneyi açıklar.

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

## <a name="arrayconst_pointer"></a><a name="const_pointer"></a>dizi::const_pointer

Bir öğe için sabit bir işaretçi türü.

```cpp
typedef const Ty *const_pointer;
```

### <a name="remarks"></a>Açıklamalar

Tür, dizinin öğelerine sabit bir işaretçi olarak hizmet verebilen bir nesneyi açıklar.

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

## <a name="arrayconst_reference"></a><a name="const_reference"></a>dizi::const_reference

Bir öğe için sabit bir başvuru türü.

```cpp
typedef const Ty& const_reference;
```

### <a name="remarks"></a>Açıklamalar

Tür, denetlenen dizinin bir öğesine sabit bir başvuru olarak hizmet verebilecek bir nesneyi açıklar.

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

## <a name="arrayconst_reverse_iterator"></a><a name="const_reverse_iterator"></a>dizi::const_reverse_iterator

Denetlenmeyen dizi için sabit bir ters yineleyici türü.

```cpp
typedef std::reverse_iterator<const_iterator> const_reverse_iterator;
```

### <a name="remarks"></a>Açıklamalar

Tür, denetlenen dizi için sabit bir ters yineleyici olarak hizmet verebilen bir nesneyi açıklar.

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

## <a name="arraycrbegin"></a><a name="crbegin"></a>dizi::crbegin

Bir const yineleyiciyi ters dizideki ilk öğeye döndürür.

```cpp
const_reverse_iterator crbegin() const;
```

### <a name="return-value"></a>Dönüş Değeri

Ters bir dizideki ilk öğeyi ele alan veya ters çevrilmemiş dizideki son öğeyi ele alan const ters rasgele erişim yineleyici.

### <a name="remarks"></a>Açıklamalar

Return value ile `crbegin`dizi nesnesi değiştirilemez.

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

## <a name="arraycrend"></a><a name="crend"></a>dizi::crend

Ters bir dizideki son öğeyi yerine getiren konumu gideren bir const yineleyici döndürür.

```cpp
const_reverse_iterator crend() const noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

Ters bir dizideki son öğeyi başaran konumu (ters çevrilmemiş dizideki ilk öğeden önce gelen konum) gideren const ters rasgele erişim yinelemesi.

### <a name="remarks"></a>Açıklamalar

`crend`dizi gibi ters bir dizi ile [kullanılır::cend](#cend) bir dizi ile kullanılır.

İade değeri `crend` (uygun şekilde delenmiyet) ile dizi nesnesi değiştirilemez.

`crend`bir ters yineleyicinin dizinin sonuna ulaşıp ulaşmadığını test etmek için kullanılabilir.

Döndürülen `crend` değer dereferenced olmamalıdır.

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

## <a name="arraydata"></a><a name="data"></a>dizi::data

İlk öğenin adresini alır.

```cpp
Ty *data();

const Ty *data() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevler, denetlenen dizideki ilk öğenin adresini döndürür.

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

## <a name="arraydifference_type"></a><a name="difference_type"></a>dizi::difference_type

İki öğe arasındaki işaretli mesafenin türü.

```cpp
typedef std::ptrdiff_t difference_type;
```

### <a name="remarks"></a>Açıklamalar

İmzalı bir sonraki gün türü, denetlenebilir sırada herhangi iki öğenin adresleri arasındaki farkı temsil eden bir nesneyi açıklar. Bu türü `std::ptrdiff_t`için eşanlamlıdır.

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

## <a name="arrayempty"></a><a name="empty"></a>dizi::boş

Bir öğe olup olmadığını sınar.

```cpp
constexpr bool empty() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlev yalnızca `N == 0`.

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

## <a name="arrayend"></a><a name="end"></a>dizi::end

Denetlenen dizinin bitişini belirtir.

```cpp
reference end();

const_reference end() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevler, dizinin sonunun hemen ötesine işaret eden rasgele erişim yinelemesi döndürer.

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

## <a name="arrayfill"></a><a name="fill"></a>dizi::doldurmak

Bir diziyi siler ve belirtilen öğeleri boş diziye kopyalar.

```cpp
void fill(const Type& val);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|-|-|
|*Val*|Diziye eklenen öğenin değeri.|

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
    for (const auto& it : c0)
    {
        std::cout << " " << it;
    }
    cout << endl;
}
```

## <a name="arrayfront"></a><a name="front"></a>dizi::ön

İlk öğeye erişir.

```cpp
reference front();

constexpr const_reference front() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevler, boş olmayan kontrollü dizinin ilk öğesine bir başvuru döndürür.

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

## <a name="arrayiterator"></a><a name="iterator"></a>dizi::iterator

Denetlenen dizi için bir yineleyici türü.

```cpp
typedef implementation-defined iterator;
```

### <a name="remarks"></a>Açıklamalar

Tür, denetlenen dizi için rasgele erişim yineleyicisi olarak hizmet verebilen bir nesneyi açıklar.

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

## <a name="arraymax_size"></a><a name="max_size"></a>dizi::max_size

Öğe sayısını sayar.

```cpp
constexpr size_type max_size() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlev `N`döndürür.

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

## <a name="arrayoperator"></a><a name="op_at"></a>dizi::operatör[]

Belirli bir konumda bir öğeye erişir.

```cpp
reference operator[](size_type off);

constexpr const_reference operator[](size_type off) const;
```

### <a name="parameters"></a>Parametreler

*kapalı*\
Öğenin erişim konumu.

### <a name="remarks"></a>Açıklamalar

Üye *işlevler,* kapalı konumda denetitilen dizinin öğesine bir başvuru döndürür. Bu konum geçersizse, davranış tanımsızdır.

Ayrıca bir **dizi**öğesiiçin bir başvuru almak için kullanılabilir olmayan bir üye [get](array-functions.md#get) işlevi de vardır.

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

## <a name="arrayoperator"></a><a name="op_eq"></a>dizi::operator=

Denetedilen sırayı değiştirir.

```cpp
array<Value> operator=(array<Value> right);
```

### <a name="parameters"></a>Parametreler

*Doğru*\
Kopyalanması gereken konteyner.

### <a name="remarks"></a>Açıklamalar

Üye işleç, her *bir hakkın* öğesini denetlenmeyen `*this`dizinin karşılık gelen öğesine atar ve döndürür. Bunu, denetlenir sırayı *sağdaki*kontrollü dizinin bir kopyasıyla değiştirmek için kullanırsınız.

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

## <a name="arraypointer"></a><a name="pointer"></a>dizi::pointer

Bir öğe için bir işaretçi türü.

```cpp
typedef Ty *pointer;
```

### <a name="remarks"></a>Açıklamalar

Tür, dizinin öğelerine işaretçi olarak hizmet verebilen bir nesneyi açıklar.

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

## <a name="arrayrbegin"></a><a name="rbegin"></a>dizi::rbegin

Ters denetimli dizinin başlangıcını belirler.

```cpp
reverse_iterator rbegin()noexcept;
const_reverse_iterator rbegin() const noexcept;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevler, denetitilen dizinin sonundan hemen ötesine işaret eden bir ters yineleyici döndürer. Bu nedenle, ters sıranın başlangıcını belirtir.

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

## <a name="arrayreference"></a><a name="reference"></a>dizi::başvuru

Bir öğe için bir başvuru türü.

```cpp
typedef Ty& reference;
```

### <a name="remarks"></a>Açıklamalar

Tür, denetlenen dizinin bir öğesine başvuru olarak hizmet verebilecek bir nesneyi açıklar.

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

## <a name="arrayrend"></a><a name="rend"></a>dizi::rend

Ters denetimli dizinin sonunu belirler.

```cpp
reverse_iterator rend()noexcept;
const_reverse_iterator rend() const noexcept;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevler, dizinin ilk öğesini işaret eden bir ters yineleyici döndürür (veya boş bir dizinin sonundan hemen sonra)). Bu nedenle, ters sıranın sonunu belirtir.

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

## <a name="arrayreverse_iterator"></a><a name="reverse_iterator"></a>dizi::reverse_iterator

Denetlenen dizi için ters yineleyici türü.

```cpp
typedef std::reverse_iterator<iterator> reverse_iterator;
```

### <a name="remarks"></a>Açıklamalar

Tür, denetlenen dizi için ters yineleyici olarak hizmet verebilen bir nesneyi açıklar.

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

## <a name="arraysize"></a><a name="size"></a>dizi::boyut

Öğe sayısını sayar.

```cpp
constexpr size_type size() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlev `N`döndürür.

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

## <a name="arraysize_type"></a><a name="size_type"></a>dizi::size_type

İki öğe arasındaki imzasız uzaklık türü.

```cpp
typedef std::size_t size_type;
```

### <a name="remarks"></a>Açıklamalar

İmzasız tümsavar türü, denetlenebilir herhangi bir dizinin uzunluğunu temsil eden bir nesneyi açıklar. Bu türü `std::size_t`için eşanlamlıdır.

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

## <a name="arrayswap"></a><a name="swap"></a>dizi::takas

Bu dizinin içeriğini başka bir diziyle değiştirir.

```cpp
void swap(array& right);
```

### <a name="parameters"></a>Parametreler

*Doğru*\
İçerikleri takas etmek için dizi.

### <a name="remarks"></a>Açıklamalar

Üye işlev, kontrollü dizileri `*this` sağ ve *arasındaki*sıraları değiştirir. Bu öğe atamaları ve kurucu ile orantılı bir `N`dizi gerçekleştirir.

Ayrıca, iki **dizi** örneğini değiştirmek için üye olmayan bir [takas](array-functions.md#swap) işlevi de vardır.

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

## <a name="arrayvalue_type"></a><a name="value_type"></a>dizi::value_type

Öğenin türü.

```cpp
typedef Ty value_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, şablon parametresi `Ty`ile eş anlamlıdır.

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

[\<dizi>](../standard-library/array.md)
