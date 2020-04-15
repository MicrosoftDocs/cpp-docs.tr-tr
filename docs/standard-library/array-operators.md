---
title: '&lt;dizi&gt; işleçleri'
ms.date: 11/04/2016
f1_keywords:
- array/std::array::operator!=
- array/std::array::operator<
- array/std::array::operator<=
- array/std::array::operator>
- array/std::array::operator>=
- array/std::array::operator==
ms.assetid: c8f46282-f179-4909-9a01-639cb8e18c27
ms.openlocfilehash: 531ad2936322f90a38631a9450e0ad8a210fdd87
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364906"
---
# <a name="ltarraygt-operators"></a>&lt;dizi&gt; işleçleri

Dizi \<> üstbilgi bu **dizi** üye olmayan karşılaştırma şablonu işlevlerini içerir.

||||
|-|-|-|
|[işleç!=](#op_neq)|[Işleç&gt;](#op_gt)|[Işleç&gt;=](#op_gt_eq)|
|[Işleç&lt;](#op_lt)|[Işleç&lt;=](#op_lt_eq)|[işleç==](#op_eq_eq)|

## <a name="operator"></a><a name="op_neq"></a>işleç!=

Dizi karşılaştırması, eşit değil.

```cpp
template <Ty, std::size_t N>
bool operator!=(
    const array<Ty, N>& left,
    const array<Ty, N>& right);
```

### <a name="parameters"></a>Parametreler

*Ty*\
Öğenin türü.

*N*\
Dizinin boyutu.

*Sol*\
Karşılaştırmak için sol konteyner.

*Doğru*\
Karşılaştırmak için doğru konteyner.

### <a name="remarks"></a>Açıklamalar

Şablon işlevi `!(left == right)`döndürür.

### <a name="example"></a>Örnek

```cpp
// std__array__operator_ne.cpp
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

// display contents " 4 5 6 7"
    for (Myarray::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << " " << *it;
    std::cout << std::endl;

// display results of comparisons
    std::cout << std::boolalpha << " " << (c0 != c0);
    std::cout << std::endl;
    std::cout << std::boolalpha << " " << (c0 != c1);
    std::cout << std::endl;

    return (0);
    }
```

```Output
0 1 2 3
4 5 6 7
false
true
```

## <a name="operatorlt"></a><a name="op_lt"></a>Işleç&lt;

Dizi karşılaştırması, daha az.

```cpp
template <Ty, std::size_t N>
bool operator<(
    const array<Ty, N>& left,
    const array<Ty, N>& right);
```

### <a name="parameters"></a>Parametreler

*Ty*\
Öğenin türü.

*N*\
Dizinin boyutu.

*Sol*\
Karşılaştırmak için sol konteyner.

*Doğru*\
Karşılaştırmak için doğru konteyner.

### <a name="remarks"></a>Açıklamalar

Şablon işlevi sınıf `operator<` şablon [dizisi Sınıf](../standard-library/array-class-stl.md)iki nesnekarşılaştırmak için overloads . İşlev `lexicographical_compare(left.begin(), left.end(), right.begin())`döndürür.

### <a name="example"></a>Örnek

```cpp
// std__array__operator_lt.cpp
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

// display contents " 4 5 6 7"
    for (Myarray::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << " " << *it;
    std::cout << std::endl;

// display results of comparisons
    std::cout << std::boolalpha << " " << (c0 < c0);
    std::cout << std::endl;
    std::cout << std::boolalpha << " " << (c0 < c1);
    std::cout << std::endl;

    return (0);
    }
```

```Output
0 1 2 3
4 5 6 7
false
true
```

## <a name="operatorlt"></a><a name="op_lt_eq"></a>Işleç&lt;=

Dizi karşılaştırması, daha az veya eşit.

```cpp
template <Ty, std::size_t N>
bool operator<=(
    const array<Ty, N>& left,
    const array<Ty, N>& right);
```

### <a name="parameters"></a>Parametreler

*Ty*\
Öğenin türü.

*N*\
Dizinin boyutu.

*Sol*\
Karşılaştırmak için sol konteyner.

*Doğru*\
Karşılaştırmak için doğru konteyner.

### <a name="remarks"></a>Açıklamalar

Şablon işlevi `!(right < left)`döndürür.

### <a name="example"></a>Örnek

```cpp
// std__array__operator_le.cpp
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

// display contents " 4 5 6 7"
    for (Myarray::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << " " << *it;
    std::cout << std::endl;

// display results of comparisons
    std::cout << std::boolalpha << " " << (c0 <= c0);
    std::cout << std::endl;
    std::cout << std::boolalpha << " " << (c1 <= c0);
    std::cout << std::endl;

    return (0);
    }
```

```Output
0 1 2 3
4 5 6 7
true
false
```

## <a name="operator"></a><a name="op_eq_eq"></a>işleç==

Dizi karşılaştırması, eşit.

```cpp
template <Ty, std::size_t N>
bool operator==(
    const array<Ty, N>& left,
    const array<Ty, N>& right);
```

### <a name="parameters"></a>Parametreler

*Ty*\
Öğenin türü.

*N*\
Dizinin boyutu.

*Sol*\
Karşılaştırmak için sol konteyner.

*Doğru*\
Karşılaştırmak için doğru konteyner.

### <a name="remarks"></a>Açıklamalar

Şablon işlevi sınıf `operator==` şablon [dizisi Sınıf](../standard-library/array-class-stl.md)iki nesnekarşılaştırmak için overloads . İşlev `equal(left.begin(), left.end(), right.begin())`döndürür.

### <a name="example"></a>Örnek

```cpp
// std__array__operator_eq.cpp
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

// display contents " 4 5 6 7"
    for (Myarray::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << " " << *it;
    std::cout << std::endl;

// display results of comparisons
    std::cout << std::boolalpha << " " << (c0 == c0);
    std::cout << std::endl;
    std::cout << std::boolalpha << " " << (c0 == c1);
    std::cout << std::endl;

    return (0);
    }
```

```Output
0 1 2 3
4 5 6 7
true
false
```

## <a name="operatorgt"></a><a name="op_gt"></a>Işleç&gt;

Dizi karşılaştırması, daha büyük.

```cpp
template <Ty, std::size_t N>
bool operator>(
    const array<Ty, N>& left,
    const array<Ty, N>& right);
```

### <a name="parameters"></a>Parametreler

*Ty*\
Öğenin türü.

*N*\
Dizinin boyutu.

*Sol*\
Karşılaştırmak için sol konteyner.

*Doğru*\
Karşılaştırmak için doğru konteyner.

### <a name="remarks"></a>Açıklamalar

Şablon işlevi `(right < left)`döndürür.

### <a name="example"></a>Örnek

```cpp
// std__array__operator_gt.cpp
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

// display contents " 4 5 6 7"
    for (Myarray::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << " " << *it;
    std::cout << std::endl;

// display results of comparisons
    std::cout << std::boolalpha << " " << (c0 > c0);
    std::cout << std::endl;
    std::cout << std::boolalpha << " " << (c1 > c0);
    std::cout << std::endl;

    return (0);
    }
```

```Output
0 1 2 3
4 5 6 7
false
true
```

## <a name="operatorgt"></a><a name="op_gt_eq"></a>Işleç&gt;=

Dizi karşılaştırması, büyük veya eşit.

```cpp
template <Ty, std::size_t N>
bool operator>=(
    const array<Ty, N>& left,
    const array<Ty, N>& right);
```

### <a name="parameters"></a>Parametreler

*Ty*\
Öğenin türü.

*N*\
Dizinin boyutu.

*Sol*\
Karşılaştırmak için sol konteyner.

*Doğru*\
Karşılaştırmak için doğru konteyner.

### <a name="remarks"></a>Açıklamalar

Şablon işlevi `!(left < right)`döndürür.

### <a name="example"></a>Örnek

```cpp
// std__array__operator_ge.cpp
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

// display contents " 4 5 6 7"
    for (Myarray::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << " " << *it;
    std::cout << std::endl;

// display results of comparisons
    std::cout << std::boolalpha << " " << (c0 >= c0);
    std::cout << std::endl;
    std::cout << std::boolalpha << " " << (c0 >= c1);
    std::cout << std::endl;

    return (0);
    }
```

```Output
0 1 2 3
4 5 6 7
true
false
```

## <a name="see-also"></a>Ayrıca bkz.

[\<dizi>](../standard-library/array.md)
