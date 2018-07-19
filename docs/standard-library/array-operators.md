---
title: '&lt;dizi&gt; işleçler | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- array/std::array::operator!=
- array/std::array::operator<
- array/std::array::operator<=
- array/std::array::operator>
- array/std::array::operator>=
- array/std::array::operator==
dev_langs:
- C++
ms.assetid: c8f46282-f179-4909-9a01-639cb8e18c27
ms.openlocfilehash: 782acd7fda671d84252ab226d095fe21c75645bf
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38965464"
---
# <a name="ltarraygt-operators"></a>&lt;dizi&gt; işleçleri

\<Array > Bu içeren üst bilgi **dizi** üye olmayan karşılaştırma şablon işlevleri.

||||
|-|-|-|
|[operator!=](#op_neq)|[İşleci&gt;](#op_gt)|[İşleci&gt;=](#op_gt_eq)|
|[İşleci&lt;](#op_lt)|[İşleci&lt;=](#op_lt_eq)|[operator==](#op_eq_eq)|

## <a name="op_neq"></a>  işleç! =

Dizi karşılaştırması, eşit değil.

```cpp
template <Ty, std::size_t N>
bool operator!=(
    const array<Ty, N>& left,
    const array<Ty, N>& right);
```

### <a name="parameters"></a>Parametreler

*Ty* öğenin türü.

*N* dizinin boyutu.

*Sol* karşılaştırmak için sol kapsayıcı.

*doğru* karşılaştırmak için doğru kapsayıcı.

### <a name="remarks"></a>Açıklamalar

Şablon işlevinin döndürdüğü `!(left == right)`.

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

## <a name="op_lt"></a>  İşleci&lt;

Dizi karşılaştırması, küçüktür.

```cpp
template <Ty, std::size_t N>
bool operator<(
    const array<Ty, N>& left,
    const array<Ty, N>& right);
```

### <a name="parameters"></a>Parametreler

*Ty* öğenin türü.

*N* dizinin boyutu.

*Sol* karşılaştırmak için sol kapsayıcı.

*doğru* karşılaştırmak için doğru kapsayıcı.

### <a name="remarks"></a>Açıklamalar

Şablonu işlev aşırı yüklemelerinin `operator<` şablon sınıfının iki nesneleri karşılaştırmak için [array sınıfı](../standard-library/array-class-stl.md). İşlev döndürür `lexicographical_compare(left.begin(), left.end(), right.begin())`.

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

## <a name="op_lt_eq"></a>  İşleci&lt;=

Dizi karşılaştırması, küçüktür veya eşittir.

```cpp
template <Ty, std::size_t N>
bool operator<=(
    const array<Ty, N>& left,
    const array<Ty, N>& right);
```

### <a name="parameters"></a>Parametreler

*Ty* öğenin türü.

*N* dizinin boyutu.

*Sol* karşılaştırmak için sol kapsayıcı.

*doğru* karşılaştırmak için doğru kapsayıcı.

### <a name="remarks"></a>Açıklamalar

Şablon işlevinin döndürdüğü `!(right < left)`.

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

## <a name="op_eq_eq"></a>  işleç ==

Dizi karşılaştırması, eşit.

```cpp
template <Ty, std::size_t N>
bool operator==(
    const array<Ty, N>& left,
    const array<Ty, N>& right);
```

### <a name="parameters"></a>Parametreler

*Ty* öğenin türü.

*N* dizinin boyutu.

*Sol* karşılaştırmak için sol kapsayıcı.

*doğru* karşılaştırmak için doğru kapsayıcı.

### <a name="remarks"></a>Açıklamalar

Şablonu işlev aşırı yüklemelerinin `operator==` şablon sınıfının iki nesneleri karşılaştırmak için [array sınıfı](../standard-library/array-class-stl.md). İşlev döndürür `equal(left.begin(), left.end(), right.begin())`.

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

## <a name="op_gt"></a>  İşleci&gt;

Dizi karşılaştırması, büyüktür.

```cpp
template <Ty, std::size_t N>
bool operator>(
    const array<Ty, N>& left,
    const array<Ty, N>& right);
```

### <a name="parameters"></a>Parametreler

*Ty* öğenin türü.

*N* dizinin boyutu.

*Sol* karşılaştırmak için sol kapsayıcı.

*doğru* karşılaştırmak için doğru kapsayıcı.

### <a name="remarks"></a>Açıklamalar

Şablon işlevinin döndürdüğü `(right < left)`.

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

## <a name="op_gt_eq"></a>  İşleci&gt;=

Dizi karşılaştırması, büyüktür veya eşittir.

```cpp
template <Ty, std::size_t N>
bool operator>=(
    const array<Ty, N>& left,
    const array<Ty, N>& right);
```

### <a name="parameters"></a>Parametreler

*Ty* öğenin türü.

*N* dizinin boyutu.

*Sol* karşılaştırmak için sol kapsayıcı.

*doğru* karşılaştırmak için doğru kapsayıcı.

### <a name="remarks"></a>Açıklamalar

Şablon işlevinin döndürdüğü `!(left < right)`.

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

[\<Array >](../standard-library/array.md)<br/>
