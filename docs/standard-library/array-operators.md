---
description: 'Daha fazla bilgi edinin: &lt; dizi &gt; işleçleri'
title: '&lt;dizi &gt; işleçleri'
ms.date: 11/04/2016
f1_keywords:
- array/std::array::operator!=
- array/std::array::operator<
- array/std::array::operator<=
- array/std::array::operator>
- array/std::array::operator>=
- array/std::array::operator==
ms.assetid: c8f46282-f179-4909-9a01-639cb8e18c27
ms.openlocfilehash: 1cd51fa2a4a34dfa4fb8548ef3437662abce401b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97205531"
---
# <a name="ltarraygt-operators"></a>&lt;dizi &gt; işleçleri

\<array>Üst bilgi bu **dizi** üye olmayan karşılaştırma şablonu işlevlerini içerir.

[işleç! =](#op_neq)\
[işlecinde&gt;](#op_gt)\
[işlecinde&gt;=](#op_gt_eq)\
[işlecinde&lt;](#op_lt)\
[işlecinde&lt;=](#op_lt_eq)\
[işleç = =](#op_eq_eq)

## <a name="operator"></a><a name="op_neq"></a> işleç! =

Dizi karşılaştırması, eşit değildir.

```cpp
template <Ty, std::size_t N>
bool operator!=(
    const array<Ty, N>& left,
    const array<Ty, N>& right);
```

### <a name="parameters"></a>Parametreler

*Kalite*\
Öğenin türü.

*No*\
Dizinin boyutu.

*tarafta*\
Karşılaştırılacak sol kapsayıcı.

*Right*\
Karşılaştırılacak doğru kapsayıcı.

### <a name="remarks"></a>Açıklamalar

Şablon işlevi döndürür `!(left == right)` .

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

## <a name="operatorlt"></a><a name="op_lt"></a> işlecinde&lt;

Dizi karşılaştırması, küçüktür.

```cpp
template <Ty, std::size_t N>
bool operator<(
    const array<Ty, N>& left,
    const array<Ty, N>& right);
```

### <a name="parameters"></a>Parametreler

*Kalite*\
Öğenin türü.

*No*\
Dizinin boyutu.

*tarafta*\
Karşılaştırılacak sol kapsayıcı.

*Right*\
Karşılaştırılacak doğru kapsayıcı.

### <a name="remarks"></a>Açıklamalar

Şablon işlevi, `operator<` sınıf şablonu [dizi sınıfının](../standard-library/array-class-stl.md)iki nesnesini karşılaştırmak için aşırı yükler. İşlev döndürür `lexicographical_compare(left.begin(), left.end(), right.begin())` .

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

## <a name="operatorlt"></a><a name="op_lt_eq"></a> işlecinde&lt;=

Dizi karşılaştırması, küçüktür veya eşittir.

```cpp
template <Ty, std::size_t N>
bool operator<=(
    const array<Ty, N>& left,
    const array<Ty, N>& right);
```

### <a name="parameters"></a>Parametreler

*Kalite*\
Öğenin türü.

*No*\
Dizinin boyutu.

*tarafta*\
Karşılaştırılacak sol kapsayıcı.

*Right*\
Karşılaştırılacak doğru kapsayıcı.

### <a name="remarks"></a>Açıklamalar

Şablon işlevi döndürür `!(right < left)` .

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

## <a name="operator"></a><a name="op_eq_eq"></a> işleç = =

Dizi karşılaştırması, eşittir.

```cpp
template <Ty, std::size_t N>
bool operator==(
    const array<Ty, N>& left,
    const array<Ty, N>& right);
```

### <a name="parameters"></a>Parametreler

*Kalite*\
Öğenin türü.

*No*\
Dizinin boyutu.

*tarafta*\
Karşılaştırılacak sol kapsayıcı.

*Right*\
Karşılaştırılacak doğru kapsayıcı.

### <a name="remarks"></a>Açıklamalar

Şablon işlevi, `operator==` sınıf şablonu [dizi sınıfının](../standard-library/array-class-stl.md)iki nesnesini karşılaştırmak için aşırı yükler. İşlev döndürür `equal(left.begin(), left.end(), right.begin())` .

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

## <a name="operatorgt"></a><a name="op_gt"></a> işlecinde&gt;

Dizi karşılaştırması, büyüktür.

```cpp
template <Ty, std::size_t N>
bool operator>(
    const array<Ty, N>& left,
    const array<Ty, N>& right);
```

### <a name="parameters"></a>Parametreler

*Kalite*\
Öğenin türü.

*No*\
Dizinin boyutu.

*tarafta*\
Karşılaştırılacak sol kapsayıcı.

*Right*\
Karşılaştırılacak doğru kapsayıcı.

### <a name="remarks"></a>Açıklamalar

Şablon işlevi döndürür `(right < left)` .

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

## <a name="operatorgt"></a><a name="op_gt_eq"></a> işlecinde&gt;=

Dizi karşılaştırması, büyüktür veya eşittir.

```cpp
template <Ty, std::size_t N>
bool operator>=(
    const array<Ty, N>& left,
    const array<Ty, N>& right);
```

### <a name="parameters"></a>Parametreler

*Kalite*\
Öğenin türü.

*No*\
Dizinin boyutu.

*tarafta*\
Karşılaştırılacak sol kapsayıcı.

*Right*\
Karşılaştırılacak doğru kapsayıcı.

### <a name="remarks"></a>Açıklamalar

Şablon işlevi döndürür `!(left < right)` .

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

[\<array>](../standard-library/array.md)
