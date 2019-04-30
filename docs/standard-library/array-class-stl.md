---
title: array sınıfı (Standart C++ Kitaplığı) | Microsoft Docs
ms.date: 11/04/2016
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
ms.openlocfilehash: fdc3705980ac8f763e0438f19920148437e7ed27
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62377510"
---
# <a name="array-class-c-standard-library"></a>array sınıfı (Standart C++ Kitaplığı)

Bir dizi uzunluğu denetleyen bir nesneyi tanımlayan `N` türdeki öğelerin `Ty`. Sıralı bir dizi olarak depolanan `Ty`, içerdiği `array<Ty, N>` nesne.

## <a name="syntax"></a>Sözdizimi

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

|Tür Tanımlaması|Açıklama|
|-|-|
|[const_iterator](#const_iterator)|Denetlenen dizi için bir sabit yineleyici türü.|
|[const_pointer](#const_pointer)|Bir öğe için sabit bir işaretçi türü.|
|[const_reference](#const_reference)|Bir öğe için sabit bir başvuru türü.|
|[const_reverse_iterator](#const_reverse_iterator)|Denetlenen dizi için bir sabit ters yineleyici türü.|
|[difference_type](#difference_type)|İki öğe arasındaki işaretli mesafenin türü.|
|[Yineleyici](#iterator)|Denetlenen dizi için bir yineleyici türü.|
|[İşaretçi](#pointer)|Bir öğe için bir işaretçi türü.|
|[Başvuru](#reference)|Bir öğe için bir başvuru türü.|
|[reverse_iterator](#reverse_iterator)|Denetlenen dizi için bir ters yineleyici türü.|
|[size_type](#size_type)|İki öğe arasındaki işaretsiz bir mesafenin türü.|
|[value_type](#value_type)|Öğenin türü.|

|Üye İşlevi|Açıklama|
|-|-|
|[Dizi](#array)|Bir dizi nesnesi oluşturur.|
|[Ata](#assign)|Tüm öğeleri değiştirir.|
|[konumunda](#at)|Belirtilen konumda bir öğe erişir.|
|[Geri](#back)|Son öğeyi erişir.|
|[başlayın](#begin)|Denetlenen dizinin başlangıcını belirtir.|
|[cbegin](#cbegin)|Dizideki ilk öğe için sabit bir rastgele erişim yineleyici döndürür.|
|[cend](#cend)|Dizinin sonuna hemen ötesine işaret eden sabit bir rastgele erişim yineleyici döndürür.|
|[crbegin](#crbegin)|Ters dizideki ilk öğe için sabit bir yineleyici döndürür.|
|[crend](#crend)|Ters çevrilen bir dizinin sonuna bir const yineleyici döndürür.|
|[Veri](#data)|İlk öğenin adresi alır.|
|[boş](#empty)|Bir öğe olup olmadığını sınar.|
|[Son](#end)|Denetlenen dizinin bitişini belirtir.|
|[Dolgu](#fill)|Tüm öğeleri belirli bir değerle değiştirir.|
|[Ön](#front)|İlk öğeyi erişir.|
|[max_size](#max_size)|Öğe sayısını sayar.|
|[rbegin](#rbegin)|Ters çevrilen denetlenen dizinin başlangıç belirler.|
|[rend](#rend)|Ters çevrilen denetlenen dizinin sonuna belirler.|
|[Boyutu](#size)|Öğe sayısını sayar.|
|[değiştirme](#swap)|İki kapsayıcının içeriğinin yerini değiştirir.|

|İşleç|Açıklama|
|-|-|
|[array::operator=](#op_eq)|Denetlenen dizi değiştirir.|
|[Array::operator\[\]](#op_at)|Belirtilen konumda bir öğe erişir.|

## <a name="remarks"></a>Açıklamalar

Varsayılan bir oluşturucu türüne sahip `array()` ve varsayılan atama işleci `operator=`ve gereksinimlerini karşılayan bir `aggregate`. Bu nedenle bu türdeki nesneler `array<Ty, N>` bir toplu Başlatıcı kullanılarak başlatılabilir. Örneğin,

```cpp
array<int, 4> ai = { 1, 2, 3 };
```

Nesneyi oluşturur `ai` tutan dört tamsayı değerleri, 1, 2 ve 3, değerler için ilk üç öğeleri sırasıyla başlatır ve dördüncü öğe 0 başlatır.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<array >

**Namespace:** std

## <a name="array"></a>  Array::Array

Bir dizi nesnesi oluşturur.

```cpp
array();

array(const array& right);
```

### <a name="parameters"></a>Parametreler

*sağ*<br/>
Nesne veya eklenecek aralık.

### <a name="remarks"></a>Açıklamalar

Varsayılan Oluşturucu `array()` denetimli başlatılmamış dizisi (veya varsayılan) bırakır. Başlatılmamış bir denetlenen sıra belirtmek için kullanın.

Kopya Oluşturucu `array(const array& right)` dizisi ile denetlenen dizideki başlatır [*doğru*`.begin()`, *doğru*`.end()`). Dizi nesnesi tarafından denetlenen dizinin bir kopyasını olan ilk denetimli bir sıra belirtmek için kullandığınız *doğru*.

### <a name="example"></a>Örnek

```cpp
// std__array__array_array.cpp
// compile with: /EHsc
#include <array>
#include <iostream>

typedef std::array<int, 4> Myarray;
int main()
    {
    Myarray c0 = {0, 1, 2, 3};

// display contents " 0 1 2 3"
    for (Myarray::const_iterator it = c0.begin();
        it != c0.end(); ++it)
        std::cout << " " << *it;
    std::cout << std::endl;

    Myarray c1(c0);

// display contents " 0 1 2 3"
    for (Myarray::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << " " << *it;
    std::cout << std::endl;

    return (0);
    }
```

```Output
0 1 2 3
0 1 2 3
```

## <a name="assign"></a>  Array::Assign

Değiştirilen C ++ 11, eski [dolgu](#fill). Tüm öğeleri değiştirir.

```cpp
void assign(const Ty& val);
```

### <a name="parameters"></a>Parametreler

*VAL*<br/>
Atanacak değer.

### <a name="remarks"></a>Açıklamalar

Üye işlevi tarafından denetlenen dizinin değiştirir `*this` tekrarını ile `N` değerin *val*.

### <a name="example"></a>Örnek

```cpp
// std__array__array_assign.cpp
// compile with: /EHsc
#include <array>
#include <iostream>

typedef std::array<int, 4> Myarray;
int main()
    {
    Myarray c0 = {0, 1, 2, 3};

// display contents " 0 1 2 3"
    for (Myarray::const_iterator it = c0.begin();
        it != c0.end(); ++it)
        std::cout << " " << *it;
    std::cout << std::endl;

    Myarray c1;
    c1.assign(4);

// display contents " 4 4 4 4"
    for (Myarray::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << " " << *it;
    std::cout << std::endl;

    return (0);
    }
```

```Output
0 1 2 3
4 4 4 4
```

## <a name="at"></a>  Array::AT

Belirtilen konumda bir öğe erişir.

```cpp
reference at(size_type off);

constexpr const_reference at(size_type off) const;
```

### <a name="parameters"></a>Parametreler

*Kapalı*<br/>
Erişim öğenin konumu.

### <a name="remarks"></a>Açıklamalar

Üye işlevleri konumunda denetlenen dizinin öğe bir başvuru döndürmeyi *kapalı*. Bu konumu geçersiz ise, işlev sınıfın bir nesnesi oluşturur. `out_of_range`.

### <a name="example"></a>Örnek

```cpp
// std__array__array_at.cpp
// compile with: /EHsc
#include <array>
#include <iostream>

typedef std::array<int, 4> Myarray;
int main()
    {
    Myarray c0 = {0, 1, 2, 3};

// display contents " 0 1 2 3"
    for (Myarray::const_iterator it = c0.begin();
        it != c0.end(); ++it)
        std::cout << " " << *it;
    std::cout << std::endl;

// display odd elements " 1 3"
    std::cout << " " << c0.at(1);
    std::cout << " " << c0.at(3);
    std::cout << std::endl;

    return (0);
    }
```

## <a name="back"></a>  Array::Back

Son öğeyi erişir.

```cpp
reference back();

constexpr const_reference back() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevleri, son öğe boş olmalıdır denetlenen dizinin bir başvuru döndürür.

### <a name="example"></a>Örnek

```cpp
// std__array__array_back.cpp
// compile with: /EHsc
#include <array>
#include <iostream>

typedef std::array<int, 4> Myarray;
int main()
    {
    Myarray c0 = {0, 1, 2, 3};

// display contents " 0 1 2 3"
    for (Myarray::const_iterator it = c0.begin();
        it != c0.end(); ++it)
        std::cout << " " << *it;
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

## <a name="begin"></a>  Array::Begin

Denetlenen dizinin başlangıcını belirtir.

```cpp
iterator begin() noexcept;
const_iterator begin() const noexcept;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevleri, bu noktalarda ilk öğe dizisi (veya yalnızca boş bir dizi bitiminin ötesinde) bir rastgele erişim yineleyici döndürür.

### <a name="example"></a>Örnek

```cpp
// std__array__array_begin.cpp
// compile with: /EHsc
#include <array>
#include <iostream>

typedef std::array<int, 4> Myarray;
int main()
    {
    Myarray c0 = {0, 1, 2, 3};

// display contents " 0 1 2 3"
    for (Myarray::const_iterator it = c0.begin();
        it != c0.end(); ++it)
        std::cout << " " << *it;
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

## <a name="cbegin"></a>  Array::cbegin

Döndürür bir **const** aralıktaki ilk öğeyi adresleyen bir yineleyici.

```cpp
const_iterator cbegin() const noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

A **const** aralığı veya konuma boş bir aralığın ilk öğesine, rasgele erişim yineleyicisi (boş bir aralık için `cbegin() == cend()`).

### <a name="remarks"></a>Açıklamalar

Dönüş değeri ile `cbegin`, aralıktaki öğeler değiştirilemez.

Bu üye işlevi yerine kullanabileceğiniz `begin()` üye işlev dönüş değeri olacağını garanti etmek için `const_iterator`. Genellikle birlikte kullanılır [otomatik](../cpp/auto-cpp.md) kesinti anahtar sözcüğü, aşağıdaki örnekte gösterildiği gibi yazın. Örnekte, göz önünde bulundurun `Container` değiştirilebilir (olmayan **const**) destekleyen herhangi bir türdeki kapsayıcı `begin()` ve `cbegin()`.

```cpp
auto i1 = Container.begin();
// i1 is Container<T>::iterator
auto i2 = Container.cbegin();

// i2 is Container<T>::const_iterator
```

## <a name="cend"></a>  Array::cend

Döndürür bir **const** konuma bir aralıktaki son öğeyi ele alan bir yineleyici.

```cpp
const_iterator cend() const noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

Aralığın hemen sonunu gösteren bir rastgele erişim yineleyicisi.

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

## <a name="const_iterator"></a>  Array::const_iterator

Denetlenen dizi için bir sabit yineleyici türü.

```cpp
typedef implementation-defined const_iterator;
```

### <a name="remarks"></a>Açıklamalar

Denetlenen dizi için sabit bir rastgele erişim yineleyici olarak hizmet verebilen bir nesneyi tanımlayan bir tür.

### <a name="example"></a>Örnek

```cpp
// std__array__array_const_iterator.cpp
// compile with: /EHsc /W4
#include <array>
#include <iostream>

typedef std::array<int, 4> MyArray;

int main()
{
    MyArray c0 = {0, 1, 2, 3};

    // display contents " 0 1 2 3"
    std::cout << "it1:";
    for ( MyArray::const_iterator it1 = c0.begin();
          it1 != c0.end();
          ++it1 ) {
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

## <a name="const_pointer"></a>  Array::const_pointer

Bir öğe için sabit bir işaretçi türü.

```cpp
typedef const Ty *const_pointer;
```

### <a name="remarks"></a>Açıklamalar

Dizinin öğeleri için sabit bir işaretçi olarak hizmet verebilen bir nesneyi tanımlayan bir tür.

### <a name="example"></a>Örnek

```cpp
// std__array__array_const_pointer.cpp
// compile with: /EHsc
#include <array>
#include <iostream>

typedef std::array<int, 4> Myarray;
int main()
    {
    Myarray c0 = {0, 1, 2, 3};

// display contents " 0 1 2 3"
    for (Myarray::const_iterator it = c0.begin();
        it != c0.end(); ++it)
        std::cout << " " << *it;
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

## <a name="const_reference"></a>  Array::const_reference

Bir öğe için sabit bir başvuru türü.

```cpp
typedef const Ty& const_reference;
```

### <a name="remarks"></a>Açıklamalar

Denetlenen dizinin bir öğe için sabit bir başvuru olarak hizmet verebilen bir nesneyi tanımlayan bir tür.

### <a name="example"></a>Örnek

```cpp
// std__array__array_const_reference.cpp
// compile with: /EHsc
#include <array>
#include <iostream>

typedef std::array<int, 4> Myarray;
int main()
    {
    Myarray c0 = {0, 1, 2, 3};

// display contents " 0 1 2 3"
    for (Myarray::const_iterator it = c0.begin();
        it != c0.end(); ++it)
        std::cout << " " << *it;
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

## <a name="const_reverse_iterator"></a>  Array::const_reverse_iterator

Denetlenen dizi için bir sabit ters yineleyici türü.

```cpp
typedef std::reverse_iterator<const_iterator> const_reverse_iterator;
```

### <a name="remarks"></a>Açıklamalar

Denetlenen dizi için bir sabit ters yineleyici olarak hizmet verebilen bir nesneyi tanımlayan bir tür.

### <a name="example"></a>Örnek

```cpp
// std__array__array_const_reverse_iterator.cpp
// compile with: /EHsc
#include <array>
#include <iostream>

typedef std::array<int, 4> Myarray;
int main()
    {
    Myarray c0 = {0, 1, 2, 3};

// display contents " 0 1 2 3"
    for (Myarray::const_iterator it = c0.begin();
        it != c0.end(); ++it)
        std::cout << " " << *it;
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

## <a name="crbegin"></a>  Array::crbegin

Ters dizideki ilk öğe için sabit bir yineleyici döndürür.

```cpp
const_reverse_iterator crbegin() const;
```

### <a name="return-value"></a>Dönüş Değeri

Rastgele erişim yineleyicisini ters dizideki ilk öğeyi ele alan veya ne ters çevrilmeyen dizi içindeki son öğeyi adresleyen bir const tersine çevirir.

### <a name="remarks"></a>Açıklamalar

Dönüş değeri ile `crbegin`, dizi nesnesi değiştirilemez.

### <a name="example"></a>Örnek

```cpp
// array_crbegin.cpp
// compile with: /EHsc
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

## <a name="crend"></a>  Array::crend

Ters çevrilen bir dizi içindeki son öğeyi takip eden konumu ele alan sabit bir yineleyici döndürür.

```cpp
const_reverse_iterator crend() const noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

Bir const ters döndürülmüş bir dizi (ters çevrilmeyen dizideki ilk öğe önce gelen konum) içindeki son öğeden sonra gelen konumu ele rasgele erişim yineleyicisi.

### <a name="remarks"></a>Açıklamalar

`crend` ters çevrilen bir dizi ile kullanılan gibi [array::cend](#cend) ile bir dizi kullanılır.

Dönüş değeri ile `crend` (uygun şekilde indirildiği), dizi nesnesi değiştirilemez.

`crend` olup ters Yineleyici, dizinin sonuna ulaşıp ulaşmadığını test etmek için kullanılabilir.

Tarafından döndürülen değer `crend` kaldırılmamalıdır.

### <a name="example"></a>Örnek

```cpp
// array_crend.cpp
// compile with: /EHsc
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

## <a name="data"></a>  Array::Data

İlk öğenin adresi alır.

```cpp
Ty *data();

const Ty *data() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevleri, denetlenen dizide ilk öğenin adresi döndürür.

### <a name="example"></a>Örnek

```cpp
// std__array__array_data.cpp
// compile with: /EHsc
#include <array>
#include <iostream>

typedef std::array<int, 4> Myarray;
int main()
    {
    Myarray c0 = {0, 1, 2, 3};

// display contents " 0 1 2 3"
    for (Myarray::const_iterator it = c0.begin();
        it != c0.end(); ++it)
        std::cout << " " << *it;
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

## <a name="difference_type"></a>  Array::difference_type

İki öğe arasındaki işaretli mesafenin türü.

```cpp
typedef std::ptrdiff_t difference_type;
```

### <a name="remarks"></a>Açıklamalar

İmzalı bir tamsayı türü adreslerini denetlenen dizideki herhangi iki öğe arasındaki farkı temsil edebilen bir nesneyi tanımlar. Türü eşanlamlıdır `std::ptrdiff_t`.

### <a name="example"></a>Örnek

```cpp
// std__array__array_difference_type.cpp
// compile with: /EHsc
#include <array>
#include <iostream>

typedef std::array<int, 4> Myarray;
int main()
    {
    Myarray c0 = {0, 1, 2, 3};

// display contents " 0 1 2 3"
    for (Myarray::const_iterator it = c0.begin();
        it != c0.end(); ++it)
        std::cout << " " << *it;
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

## <a name="empty"></a>  Array::empty

Bir öğe olup olmadığını sınar.

```cpp
constexpr bool empty() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi yalnızca, true döndürür `N == 0`.

### <a name="example"></a>Örnek

```cpp
// std__array__array_empty.cpp
// compile with: /EHsc
#include <array>
#include <iostream>

typedef std::array<int, 4> Myarray;
int main()
    {
    Myarray c0 = {0, 1, 2, 3};

// display contents " 0 1 2 3"
    for (Myarray::const_iterator it = c0.begin();
        it != c0.end(); ++it)
        std::cout << " " << *it;
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

## <a name="end"></a>  Array::End

Denetlenen dizinin bitişini belirtir.

```cpp
reference end();

const_reference end() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevleri, son sırasının hemen ötesine işaret eden bir rastgele erişim yineleyici döndürür.

### <a name="example"></a>Örnek

```cpp
// std__array__array_end.cpp
// compile with: /EHsc
#include <array>
#include <iostream>

typedef std::array<int, 4> Myarray;
int main()
    {
    Myarray c0 = {0, 1, 2, 3};

// display contents " 0 1 2 3"
    for (Myarray::const_iterator it = c0.begin();
        it != c0.end(); ++it)
        std::cout << " " << *it;
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

## <a name="fill"></a>  Array::Fill

Bir dizi siler ve boş bir dizi için belirtilen öğeleri kopyalar.

```cpp
void fill(const Type& val);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|-|-|
|*VAL*|Diziye eklenen öğe değeri.|

### <a name="remarks"></a>Açıklamalar

`fill` Dizideki her öğeye belirtilen değerle değiştirir.

### <a name="example"></a>Örnek

```cpp
// array_fill.cpp
// compile with: /EHsc
#include <array>
#include <iostream>

int main( )
{
   using namespace std;
   array<int, 2> v1 = {1, 2};
   array<int, 2>::iterator iter;

   cout << "v1 = " ;
   for (iter = v1.begin(); iter != v1.end(); iter++)
      cout << *iter << " ";
   cout << endl;

   v1.fill(3);
   cout << "v1 = " ;
   for (iter = v1.begin(); iter != v1.end(); iter++)
      cout << *iter << " ";
   cout << endl;
}
```

## <a name="front"></a>  Array::Front

İlk öğeyi erişir.

```cpp
reference front();

constexpr const_reference front() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevleri, denetlenen dizinin boş olması gereken ilk öğeye bir başvuru döndürür.

### <a name="example"></a>Örnek

```cpp
// std__array__array_front.cpp
// compile with: /EHsc
#include <array>
#include <iostream>

typedef std::array<int, 4> Myarray;
int main()
    {
    Myarray c0 = {0, 1, 2, 3};

// display contents " 0 1 2 3"
    for (Myarray::const_iterator it = c0.begin();
        it != c0.end(); ++it)
        std::cout << " " << *it;
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

## <a name="iterator"></a>  Array::iterator

Denetlenen dizi için bir yineleyici türü.

```cpp
typedef implementation-defined iterator;
```

### <a name="remarks"></a>Açıklamalar

Denetlenen dizi için bir rastgele erişim yineleyici olarak hizmet verebilen bir nesneyi tanımlayan bir tür.

### <a name="example"></a>Örnek

```cpp
// std__array__array_iterator.cpp
// compile with: /EHsc /W4
#include <array>
#include <iostream>

typedef std::array<int, 4> MyArray;

int main()
{
    MyArray c0 = {0, 1, 2, 3};

    // display contents " 0 1 2 3"
    std::cout << "it1:";
    for ( MyArray::iterator it1 = c0.begin();
          it1 != c0.end();
          ++it1 ) {
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

## <a name="max_size"></a>  Array::max_size

Öğe sayısını sayar.

```cpp
constexpr size_type max_size() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevinin döndürdüğü `N`.

### <a name="example"></a>Örnek

```cpp
// std__array__array_max_size.cpp
// compile with: /EHsc
#include <array>
#include <iostream>

typedef std::array<int, 4> Myarray;
int main()
    {
    Myarray c0 = {0, 1, 2, 3};

// display contents " 0 1 2 3"
    for (Myarray::const_iterator it = c0.begin();
        it != c0.end(); ++it)
        std::cout << " " << *it;
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

## <a name="op_at"></a>  Array::operator]

Belirtilen konumda bir öğe erişir.

```cpp
reference operator[](size_type off);

constexpr const_reference operator[](size_type off) const;
```

### <a name="parameters"></a>Parametreler

*Kapalı*<br/>
Erişim öğenin konumu.

### <a name="remarks"></a>Açıklamalar

Üye işlevleri konumunda denetlenen dizinin öğe bir başvuru döndürmeyi *kapalı*. Bu konum geçersiz, tanımsız bir davranıştır.

Üye olmayan bulunmaktadır [alma](array-functions.md#get) işlevi bir öğesine bir başvuru almak kullanılabilir bir **dizi**.

### <a name="example"></a>Örnek

```cpp
// std__array__array_operator_sub.cpp
// compile with: /EHsc
#include <array>
#include <iostream>

typedef std::array<int, 4> Myarray;
int main()
    {
    Myarray c0 = {0, 1, 2, 3};

// display contents " 0 1 2 3"
    for (Myarray::const_iterator it = c0.begin();
        it != c0.end(); ++it)
        std::cout << " " << *it;
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

## <a name="op_eq"></a>  Array::operator =

Denetlenen dizi değiştirir.

```cpp
array<Value> operator=(array<Value> right);
```

### <a name="parameters"></a>Parametreler

*sağ*<br/>
Kopyalanacak kapsayıcı.

### <a name="remarks"></a>Açıklamalar

Üye işleci her öğeye atar *doğru* için karşılık gelen öğe denetlenen dizinin ardından döndürür `*this`. Denetlenen dizi denetlenen dizide bir kopyasını değiştirmek için kullandığınız *doğru*.

### <a name="example"></a>Örnek

```cpp
// std__array__array_operator_as.cpp
// compile with: /EHsc
#include <array>
#include <iostream>

typedef std::array<int, 4> Myarray;
int main()
    {
    Myarray c0 = {0, 1, 2, 3};

// display contents " 0 1 2 3"
    for (Myarray::const_iterator it = c0.begin();
        it != c0.end(); ++it)
        std::cout << " " << *it;
    std::cout << std::endl;

    Myarray c1;
    c1 = c0;

// display copied contents " 0 1 2 3"
    for (Myarray::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << " " << *it;
    std::cout << std::endl;

    return (0);
    }
```

```Output
0 1 2 3
0 1 2 3
```

## <a name="pointer"></a>  Array::pointer

Bir öğe için bir işaretçi türü.

```cpp
typedef Ty *pointer;
```

### <a name="remarks"></a>Açıklamalar

Dizinin öğeleri için bir işaretçi olarak hizmet verebilen nesneyi tanımlayan bir tür.

### <a name="example"></a>Örnek

```cpp
// std__array__array_pointer.cpp
// compile with: /EHsc
#include <array>
#include <iostream>

typedef std::array<int, 4> Myarray;
int main()
    {
    Myarray c0 = {0, 1, 2, 3};

// display contents " 0 1 2 3"
    for (Myarray::const_iterator it = c0.begin();
        it != c0.end(); ++it)
        std::cout << " " << *it;
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

## <a name="rbegin"></a>  Array::rbegin

Ters çevrilen denetlenen dizinin başlangıç belirler.

```cpp
reverse_iterator rbegin()noexcept;
const_reverse_iterator rbegin() const noexcept;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevleri, denetlenen dizinin sonuna hemen ötesine işaret eden bir ters yineleyici döndürür. Bu nedenle, ters dizinin başlangıcını belirtir.

### <a name="example"></a>Örnek

```cpp
// std__array__array_rbegin.cpp
// compile with: /EHsc
#include <array>
#include <iostream>

typedef std::array<int, 4> Myarray;
int main()
    {
    Myarray c0 = {0, 1, 2, 3};

// display contents " 0 1 2 3"
    for (Myarray::const_iterator it = c0.begin();
        it != c0.end(); ++it)
        std::cout << " " << *it;
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

## <a name="reference"></a>  Array::Reference

Bir öğe için bir başvuru türü.

```cpp
typedef Ty& reference;
```

### <a name="remarks"></a>Açıklamalar

Denetlenen dizinin bir öğesine bir başvuru olarak hizmet verebilen bir nesneyi tanımlayan bir tür.

### <a name="example"></a>Örnek

```cpp
// std__array__array_reference.cpp
// compile with: /EHsc
#include <array>
#include <iostream>

typedef std::array<int, 4> Myarray;
int main()
    {
    Myarray c0 = {0, 1, 2, 3};

// display contents " 0 1 2 3"
    for (Myarray::const_iterator it = c0.begin();
        it != c0.end(); ++it)
        std::cout << " " << *it;
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

## <a name="rend"></a>  Array::rend

Ters çevrilen denetlenen dizinin sonuna belirler.

```cpp
reverse_iterator rend()noexcept;
const_reverse_iterator rend() const noexcept;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevler ters yineleyici bu noktalarda ilk öğe dizisi (veya yalnızca boş bir dizi bitiminin ötesinde) döndürür). Bu nedenle, ters dizideki son belirler.

### <a name="example"></a>Örnek

```cpp
// std__array__array_rend.cpp
// compile with: /EHsc
#include <array>
#include <iostream>

typedef std::array<int, 4> Myarray;
int main()
    {
    Myarray c0 = {0, 1, 2, 3};

// display contents " 0 1 2 3"
    for (Myarray::const_iterator it = c0.begin();
        it != c0.end(); ++it)
        std::cout << " " << *it;
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

## <a name="reverse_iterator"></a>  Array::reverse_iterator

Denetlenen dizi için bir ters yineleyici türü.

```cpp
typedef std::reverse_iterator<iterator> reverse_iterator;
```

### <a name="remarks"></a>Açıklamalar

Denetlenen dizi için bir ters yineleyici olarak hizmet verebilen bir nesneyi tanımlayan bir tür.

### <a name="example"></a>Örnek

```cpp
// std__array__array_reverse_iterator.cpp
// compile with: /EHsc
#include <array>
#include <iostream>

typedef std::array<int, 4> Myarray;
int main()
    {
    Myarray c0 = {0, 1, 2, 3};

// display contents " 0 1 2 3"
    for (Myarray::const_iterator it = c0.begin();
        it != c0.end(); ++it)
        std::cout << " " << *it;
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

## <a name="size"></a>  Array::size

Öğe sayısını sayar.

```cpp
constexpr size_type size() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevinin döndürdüğü `N`.

### <a name="example"></a>Örnek

```cpp
// std__array__array_size.cpp
// compile with: /EHsc
#include <array>
#include <iostream>

typedef std::array<int, 4> Myarray;
int main()
    {
    Myarray c0 = {0, 1, 2, 3};

// display contents " 0 1 2 3"
    for (Myarray::const_iterator it = c0.begin();
        it != c0.end(); ++it)
        std::cout << " " << *it;
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

## <a name="size_type"></a>  Array::size_type

İki öğe arasındaki işaretsiz bir mesafenin türü.

```cpp
typedef std::size_t size_type;
```

### <a name="remarks"></a>Açıklamalar

İşaretsiz tamsayı türü, denetlenen bir dizi uzunluğunu temsil edebilen bir nesneyi tanımlar. Türü eşanlamlıdır `std::size_t`.

### <a name="example"></a>Örnek

```cpp
// std__array__array_size_type.cpp
// compile with: /EHsc
#include <array>
#include <iostream>

typedef std::array<int, 4> Myarray;
int main()
    {
    Myarray c0 = {0, 1, 2, 3};

// display contents " 0 1 2 3"
    for (Myarray::const_iterator it = c0.begin();
        it != c0.end(); ++it)
        std::cout << " " << *it;
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

## <a name="swap"></a>  Array::Swap

Başka bir diziye sahip bu dizinin içeriğini değiştirir.

```cpp
void swap(array& right);
```

### <a name="parameters"></a>Parametreler

*sağ*<br/>
İle içeriklerini Takas Et dizisi.

### <a name="remarks"></a>Açıklamalar

Denetlenen diziyi üye işlevi değiştirir `*this` ve *doğru*. Öğe atamaları sayısı gerçekleştirir ve oluşturucu çağrıları orantılı `N`.

Üye olmayan bulunmaktadır [takas](array-functions.md#swap) işlevi iki takas için kullanılabilir **dizi** örnekleri.

### <a name="example"></a>Örnek

```cpp
// std__array__array_swap.cpp
// compile with: /EHsc
#include <array>
#include <iostream>

typedef std::array<int, 4> Myarray;
int main()
    {
    Myarray c0 = {0, 1, 2, 3};

// display contents " 0 1 2 3"
    for (Myarray::const_iterator it = c0.begin();
        it != c0.end(); ++it)
        std::cout << " " << *it;
    std::cout << std::endl;

    Myarray c1 = {4, 5, 6, 7};
    c0.swap(c1);

// display swapped contents " 4 5 6 7"
    for (Myarray::const_iterator it = c0.begin();
        it != c0.end(); ++it)
        std::cout << " " << *it;
    std::cout << std::endl;

    swap(c0, c1);

// display swapped contents " 0 1 2 3"
    for (Myarray::const_iterator it = c0.begin();
        it != c0.end(); ++it)
        std::cout << " " << *it;
    std::cout << std::endl;

    return (0);
    }
```

```Output
0 1 2 3
4 5 6 7
0 1 2 3
```

## <a name="value_type"></a>  Array::value_type

Öğenin türü.

```cpp
typedef Ty value_type;
```

### <a name="remarks"></a>Açıklamalar

Şablon parametresi için bir eşanlamlı türüdür `Ty`.

### <a name="example"></a>Örnek

```cpp
// std__array__array_value_type.cpp
// compile with: /EHsc
#include <array>
#include <iostream>

typedef std::array<int, 4> Myarray;
int main()
    {
    Myarray c0 = {0, 1, 2, 3};

// display contents " 0 1 2 3"
    for (Myarray::const_iterator it = c0.begin();
        it != c0.end(); ++it)
        std::cout << " " << *it;
    std::cout << std::endl;

// display contents " 0 1 2 3"
    for (Myarray::const_iterator it = c0.begin();
        it != c0.end(); ++it)
        {
        Myarray::value_type val = *it;
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

[\<Array >](../standard-library/array.md)<br/>
