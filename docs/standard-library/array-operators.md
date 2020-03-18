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
ms.openlocfilehash: 3d65cd6b6b8549fd9964f6c5bb6d8b2d3c0a27b6
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/16/2020
ms.locfileid: "79422047"
---
# <a name="ltarraygt-operators"></a>&lt;dizi&gt; işleçleri

\<dizi > üst bilgisi bu **dizi** üye olmayan karşılaştırma şablonu işlevlerini içerir.

||||
|-|-|-|
|[operator!=](#op_neq)|[işleç&gt;](#op_gt)|[işleç&gt;=](#op_gt_eq)|
|[işleç&lt;](#op_lt)|[işleç&lt;=](#op_lt_eq)|[işleç = =](#op_eq_eq)|

## <a name="op_neq"></a>işleç! =

Dizi karşılaştırması, eşit değildir.

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

*sol*\
Karşılaştırılacak sol kapsayıcı.

*sağ*\
Karşılaştırılacak doğru kapsayıcı.

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

## <a name="op_lt"></a>işleç&lt;

Dizi karşılaştırması, küçüktür.

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

*sol*\
Karşılaştırılacak sol kapsayıcı.

*sağ*\
Karşılaştırılacak doğru kapsayıcı.

### <a name="remarks"></a>Açıklamalar

Şablon işlevi, sınıf şablonu [dizi sınıfının](../standard-library/array-class-stl.md)iki nesnesini karşılaştırmak için `operator<` aşırı yükler. İşlev `lexicographical_compare(left.begin(), left.end(), right.begin())`döndürür.

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

## <a name="op_lt_eq"></a>işleç&lt;=

Dizi karşılaştırması, küçüktür veya eşittir.

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

*sol*\
Karşılaştırılacak sol kapsayıcı.

*sağ*\
Karşılaştırılacak doğru kapsayıcı.

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

## <a name="op_eq_eq"></a>işleç = =

Dizi karşılaştırması, eşittir.

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

*sol*\
Karşılaştırılacak sol kapsayıcı.

*sağ*\
Karşılaştırılacak doğru kapsayıcı.

### <a name="remarks"></a>Açıklamalar

Şablon işlevi, sınıf şablonu [dizi sınıfının](../standard-library/array-class-stl.md)iki nesnesini karşılaştırmak için `operator==` aşırı yükler. İşlev `equal(left.begin(), left.end(), right.begin())`döndürür.

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

## <a name="op_gt"></a>işleç&gt;

Dizi karşılaştırması, büyüktür.

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

*sol*\
Karşılaştırılacak sol kapsayıcı.

*sağ*\
Karşılaştırılacak doğru kapsayıcı.

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

## <a name="op_gt_eq"></a>işleç&gt;=

Dizi karşılaştırması, büyüktür veya eşittir.

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

*sol*\
Karşılaştırılacak sol kapsayıcı.

*sağ*\
Karşılaştırılacak doğru kapsayıcı.

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

[\<dizi >](../standard-library/array.md)
