---
title: '&lt;demet &gt; işleçleri'
ms.date: 11/04/2016
f1_keywords:
- tuple/std::operator!=
- tuple/std::operator>
- tuple/std::operator>=
- tuple/std::operator<
- tuple/std::operator<=
- tuple/std::operator==
ms.assetid: f25752dc-d3e2-4e12-b5ac-9a8682ca60ed
ms.openlocfilehash: 5554f08f32048bafde5bdb2c316e12e1e01c6ffb
ms.sourcegitcommit: 19016630f9d35f365e9ba249e0f3617515d7ca33
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/20/2020
ms.locfileid: "92274626"
---
# <a name="lttuplegt-operators"></a>&lt;demet &gt; işleçleri

## <a name="operator"></a><a name="op_neq"></a> işleç! =

`tuple`Eşitsizlik için nesneleri karşılaştırın.

```cpp
template <class T1, class T2, ..., class TN,
    class U1, class U2, ..., class UN>
bool operator!=(const tuple<T1, T2, ..., TN>& tpl1,
    const tuple<U1, U2, ..., UN>& tpl2);
```

### <a name="parameters"></a>Parametreler

*TN*\
Nth demet öğesinin türü.

### <a name="remarks"></a>Açıklamalar

İşlev 0 olduğunda false `N` , aksi durumda false değerini döndürür `get<0>(tpl1) != get<0>(tpl2) || get<1>(tpl1) != get<1>(tpl2) || ... || get<N - 1>(tpl1) == get<N - 1>(tpl2)` .

### <a name="example"></a>Örnek

```cpp
// std__tuple__operator_ne.cpp
// compile with: /EHsc
#include <tuple>
#include <iostream>

typedef std::tuple<int, double, int, double> Mytuple;
int main() {
    Mytuple c0(0, 1, 2, 3);

// display contents " 0 1 2 3"
    std::cout << " " << std::get<0>(c0);
    std::cout << " " << std::get<1>(c0);
    std::cout << " " << std::get<2>(c0);
    std::cout << " " << std::get<3>(c0);
    std::cout << std::endl;

    Mytuple c1 = std::make_tuple(4, 5, 6, 7);

// display contents " 4 5 6 7"
    std::cout << " " << std::get<0>(c0);
    std::cout << " " << std::get<1>(c0);
    std::cout << " " << std::get<2>(c0);
    std::cout << " " << std::get<3>(c0);
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
0 1 2 3
false
true
```

## <a name="operatorlt"></a><a name="op_lt"></a> işlecinde&lt;

`tuple`Nesneleri daha az olacak şekilde karşılaştırın.

```cpp
template <class T1, class T2, ..., class TN,
    class U1, class U2, ..., class UN>
bool operator<(const tuple<T1, T2, ..., TN>& tpl1,
    const tuple<U1, U2, ..., UN>& tpl2);
```

### <a name="parameters"></a>Parametreler

*TN*\
Nth demet öğesinin türü.

### <a name="remarks"></a>Açıklamalar

İşlevi, `N` 0 ' dan büyük olduğunda ve içindeki ilk farklı değer `tpl1` içindeki karşılık gelen değerden daha az karşılaştırıldığı zaman true değerini döndürür `tpl2` , aksi takdirde false döndürür.

### <a name="example"></a>Örnek

```cpp
// std__tuple__operator_lt.cpp
// compile with: /EHsc
#include <tuple>
#include <iostream>

typedef std::tuple<int, double, int, double> Mytuple;
int main() {
    Mytuple c0(0, 1, 2, 3);

// display contents " 0 1 2 3"
    std::cout << " " << std::get<0>(c0);
    std::cout << " " << std::get<1>(c0);
    std::cout << " " << std::get<2>(c0);
    std::cout << " " << std::get<3>(c0);
    std::cout << std::endl;

    Mytuple c1 = std::make_tuple(4, 5, 6, 7);

// display contents " 4 5 6 7"
    std::cout << " " << std::get<0>(c0);
    std::cout << " " << std::get<1>(c0);
    std::cout << " " << std::get<2>(c0);
    std::cout << " " << std::get<3>(c0);
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
0 1 2 3
false
true
```

## <a name="operatorlt"></a><a name="op_lt_eq"></a> işlecinde&lt;=

`tuple`Nesneleri daha az veya eşit olacak şekilde karşılaştırın.

```cpp
template <class T1, class T2, ..., class TN,
    class U1, class U2, ..., class UN>
bool operator<=(const tuple<T1, T2, ..., TN>& tpl1,
    const tuple<U1, U2, ..., UN>& tpl2);
```

### <a name="parameters"></a>Parametreler

*TN*\
Nth demet öğesinin türü.

### <a name="remarks"></a>Açıklamalar

İşlev döndürür `!(tpl2 < tpl1)` .

### <a name="example"></a>Örnek

```cpp
// std__tuple__operator_le.cpp
// compile with: /EHsc
#include <tuple>
#include <iostream>

typedef std::tuple<int, double, int, double> Mytuple;
int main() {
    Mytuple c0(0, 1, 2, 3);

// display contents " 0 1 2 3"
    std::cout << " " << std::get<0>(c0);
    std::cout << " " << std::get<1>(c0);
    std::cout << " " << std::get<2>(c0);
    std::cout << " " << std::get<3>(c0);
    std::cout << std::endl;

    Mytuple c1 = std::make_tuple(4, 5, 6, 7);

// display contents " 4 5 6 7"
    std::cout << " " << std::get<0>(c0);
    std::cout << " " << std::get<1>(c0);
    std::cout << " " << std::get<2>(c0);
    std::cout << " " << std::get<3>(c0);
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
0 1 2 3
true
false
```

## <a name="operator"></a><a name="op_eq_eq"></a> işleç = =

`tuple`Nesneleri eşitlik için karşılaştırın.

```cpp
template <class T1, class T2, ..., class TN,
    class U1, class U2, ..., class UN>
bool operator==(const tuple<T1, T2, ..., TN>& tpl1,
    const tuple<U1, U2, ..., UN>& tpl2);
```

### <a name="parameters"></a>Parametreler

*TN*\
Nth demet öğesinin türü.

### <a name="remarks"></a>Açıklamalar

İşlevi 0 olduğunda true `N` , aksi takdirde döndürür `get<0>(tpl1) == get<0>(tpl2) && get<1>(tpl1) == get<1>(tpl2) && ... && get<N - 1>(tpl1) == get<N - 1>(tpl2)` .

### <a name="example"></a>Örnek

```cpp
// std__tuple__operator_eq.cpp
// compile with: /EHsc
#include <tuple>
#include <iostream>

typedef std::tuple<int, double, int, double> Mytuple;
int main() {
    Mytuple c0(0, 1, 2, 3);

// display contents " 0 1 2 3"
    std::cout << " " << std::get<0>(c0);
    std::cout << " " << std::get<1>(c0);
    std::cout << " " << std::get<2>(c0);
    std::cout << " " << std::get<3>(c0);
    std::cout << std::endl;

    Mytuple c1 = std::make_tuple(4, 5, 6, 7);

// display contents " 4 5 6 7"
    std::cout << " " << std::get<0>(c0);
    std::cout << " " << std::get<1>(c0);
    std::cout << " " << std::get<2>(c0);
    std::cout << " " << std::get<3>(c0);
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
0 1 2 3
true
false
```

## <a name="operatorgt"></a><a name="op_gt"></a> işlecinde&gt;

`tuple`Nesneleri daha fazla karşılaştırın.

```cpp
template <class T1, class T2, ..., class TN,
    class U1, class U2, ..., class UN>
bool operator>(const tuple<T1, T2, ..., TN>& tpl1,
    const tuple<U1, U2, ..., UN>& tpl2);
```

### <a name="parameters"></a>Parametreler

*TN*\
Nth demet öğesinin türü.

### <a name="remarks"></a>Açıklamalar

İşlev döndürür `tpl2 < tpl1` .

### <a name="example"></a>Örnek

```cpp
// std__tuple__operator_gt.cpp
// compile with: /EHsc
#include <tuple>
#include <iostream>

typedef std::tuple<int, double, int, double> Mytuple;
int main() {
    Mytuple c0(0, 1, 2, 3);

// display contents " 0 1 2 3"
    std::cout << " " << std::get<0>(c0);
    std::cout << " " << std::get<1>(c0);
    std::cout << " " << std::get<2>(c0);
    std::cout << " " << std::get<3>(c0);
    std::cout << std::endl;

    Mytuple c1 = std::make_tuple(4, 5, 6, 7);

// display contents " 4 5 6 7"
    std::cout << " " << std::get<0>(c0);
    std::cout << " " << std::get<1>(c0);
    std::cout << " " << std::get<2>(c0);
    std::cout << " " << std::get<3>(c0);
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
0 1 2 3
false
true
```

## <a name="operatorgt"></a><a name="op_gt_eq"></a> işlecinde&gt;=

`tuple`Nesneleri daha büyük veya eşit olacak şekilde karşılaştırın.

```cpp
template <class T1, class T2, ..., class TN,
    class U1, class U2, ..., class UN>
bool operator>=(const tuple<T1, T2, ..., TN>& tpl1,
    const tuple<U1, U2, ..., UN>& tpl2);
```

### <a name="parameters"></a>Parametreler

*TN*\
Nth demet öğesinin türü.

### <a name="remarks"></a>Açıklamalar

İşlev döndürür `!(tpl1 < tpl2)` .

### <a name="example"></a>Örnek

```cpp
// std__tuple__operator_ge.cpp
// compile with: /EHsc
#include <tuple>
#include <iostream>

typedef std::tuple<int, double, int, double> Mytuple;
int main() {
    Mytuple c0(0, 1, 2, 3);

// display contents " 0 1 2 3"
    std::cout << " " << std::get<0>(c0);
    std::cout << " " << std::get<1>(c0);
    std::cout << " " << std::get<2>(c0);
    std::cout << " " << std::get<3>(c0);
    std::cout << std::endl;

    Mytuple c1 = std::make_tuple(4, 5, 6, 7);

// display contents " 4 5 6 7"
    std::cout << " " << std::get<0>(c0);
    std::cout << " " << std::get<1>(c0);
    std::cout << " " << std::get<2>(c0);
    std::cout << " " << std::get<3>(c0);
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
0 1 2 3
true
false
```
