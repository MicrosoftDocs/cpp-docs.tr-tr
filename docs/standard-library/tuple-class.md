---
title: tuple Sınıfı
ms.date: 11/04/2016
f1_keywords:
- tuple/std::tuple
- tuple/std::tuple::operator=
helpviewer_keywords:
- tuple class
ms.assetid: c38749be-ae4d-41f3-98ea-6aa3250de9a3
ms.openlocfilehash: 1727d3a12b7186d3cc868ef6bb78711774057407
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2019
ms.locfileid: "72688873"
---
# <a name="tuple-class"></a>tuple Sınıfı

Sabit uzunluklu bir öğe dizisini sarmalanmış.

## <a name="syntax"></a>Sözdizimi

```
class tuple {
   tuple();
   explicit tuple(P1, P2, ..., PN); // 0 < N
   tuple(const tuple&);
   template <class U1, class U2, ..., class UN>
      tuple(const tuple<U1, U2, ..., UN>&);
   template <class U1, class U2>
      tuple(const pair<U1, U2>&); // N == 2

   void swap(tuple& right);
   tuple& operator=(const tuple&);
   template <class U1, class U2, ..., class UN>
      tuple& operator=(const tuple<U1, U2, ..., UN>&);
   template <class U1, class U2>
      tuple& operator=(const pair<U1, U2>&); // N == 2
};
```

### <a name="parameters"></a>Parametreler

*TN* \
Nth demet öğesinin türü.

## <a name="remarks"></a>Açıklamalar

Sınıf şablonu, `T1`, `T2`,... `TN`, sırasıyla `0 <= N <= Nmax`. @No__t_0 demet örneğinin kapsamı, şablon bağımsız değişkenlerinin `N` sayıdır. @No__t_0 şablon bağımsız değişkeninin dizini ve bu türün karşılık gelen depolanmış değeri `i - 1`. Bu nedenle, bu belgede 1 ile N arasında bir sayı olarak değer olarak, karşılık gelen dizin değerleri 0 ' dan N-1 ' e kadar değişir.

## <a name="example"></a>Örnek

```cpp
// tuple.cpp
// compile with: /EHsc

#include <vector>
#include <iomanip>
#include <iostream>
#include <tuple>
#include <string>

using namespace std;

typedef tuple <int, double, string> ids;

void print_ids(const ids& i)
{
   cout << "( "
        << get<0>(i) << ", "
        << get<1>(i) << ", "
        << get<2>(i) << " )." << endl;
}

int main( )
{
   // Using the constructor to declare and initialize a tuple
   ids p1(10, 1.1e-2, "one");

   // Compare using the helper function to declare and initialize a tuple
   ids p2;
   p2 = make_tuple(10, 2.22e-1, "two");

   // Making a copy of a tuple
   ids p3(p1);

   cout.precision(3);
   cout << "The tuple p1 is: ( ";
   print_ids(p1);
   cout << "The tuple p2 is: ( ";
   print_ids(p2);
   cout << "The tuple p3 is: ( ";
   print_ids(p3);

   vector<ids> v;

   v.push_back(p1);
   v.push_back(p2);
   v.push_back(make_tuple(3, 3.3e-2, "three"));

   cout << "The tuples in the vector are" << endl;
   for(vector<ids>::const_iterator i = v.begin(); i != v.end(); ++i)
   {
      print_ids(*i);
   }
}
```

```Output
The tuple p1 is: ( 10, 0.011, one ).
The tuple p2 is: ( 10, 0.222, two ).
The tuple p3 is: ( 10, 0.011, one ).
The tuples in the vector are
( 10, 0.011, one ).
( 10, 0.222, two ).
( 3, 0.033, three ).
```

## <a name="op_eq"></a>işleç =

Bir `tuple` nesnesi atar.

```cpp
tuple& operator=(const tuple& right);

template <class U1, class U2, ..., class UN>
   tuple& operator=(const tuple<U1, U2, ..., UN>& right);

template <class U1, class U2>
   tuple& operator=(const pair<U1, U2>& right); // N == 2

tuple& operator=(tuple&& right);

template <class U1, class U2>
   tuple& operator=(pair<U1, U2>&& right);
```

### <a name="parameters"></a>Parametreler

@No__t_1 *Al*
N. kopya demet öğesinin türü.

*sağ* \
Kopyalamanın bulunduğu kayıt düzeni.

### <a name="remarks"></a>Açıklamalar

İlk iki üye işleci, *sağdaki* öğeleri `*this` karşılık gelen öğelerine atar. Üçüncü üye işleci, `*this` 0 ' ın dizinindeki öğeye `right.first` atar ve Dizin 1 ' deki öğeye `right.second`. Üç üye işleci `*this` döndürür.

Kalan üye işleçleri analoglarından, ancak [rvalue başvuru bildirimci: & &](../cpp/rvalue-reference-declarator-amp-amp.md).

### <a name="example"></a>Örnek

```cpp
// std__tuple__tuple_operator_as.cpp
// compile with: /EHsc
#include <tuple>
#include <iostream>
#include <utility>

typedef std::tuple<int, double, int, double> Mytuple;
int main()
    {
    Mytuple c0(0, 1, 2, 3);

// display contents " 0 1 2 3"
    std::cout << " " << std::get<0>(c0);
    std::cout << " " << std::get<1>(c0);
    std::cout << " " << std::get<2>(c0);
    std::cout << " " << std::get<3>(c0);
    std::cout << std::endl;

    Mytuple c1;
    c1 = c0;

// display contents " 0 1 2 3"
    std::cout << " " << std::get<0>(c1);
    std::cout << " " << std::get<1>(c1);
    std::cout << " " << std::get<2>(c1);
    std::cout << " " << std::get<3>(c1);
    std::cout << std::endl;

    std::tuple<char, int> c2;
    c2 = std::make_pair('x', 4);

// display contents " x 4"
    std::cout << " " << std::get<0>(c2);
    std::cout << " " << std::get<1>(c2);
    std::cout << std::endl;

    return (0);
}
```

```Output
0 1 2 3
0 1 2 3
x 4
```

## <a name="tuple_swap"></a>Kur

İki tanımlama alanının öğelerini değiş tokuş eder.

```cpp
template <class... Types>
   void swap(tuple<Types...&> left, tuple<Types...&> right);
```

### <a name="parameters"></a>Parametreler

*sol* \
Öğeleri demet ile değiş tokuş edilecek şekilde değiştirilecek olan bir kayıt *düzeni.*

*sağ* \
Öğeleri *sol*kayıt düzeni ile değiş tokuş edilecek bir kayıt düzeni.

### <a name="remarks"></a>Açıklamalar

İşlev `left.swap(right)` yürütür.

## <a name="tuple"></a>Le

@No__t_0 nesnesi oluşturur.

```cpp
constexpr tuple();
explicit constexpr tuple(const Types&...);
template <class... UTypes>
   explicit constexpr tuple(UTypes&&...);

tuple(const tuple&) = default;
tuple(tuple&&) = default;

template <class... UTypes>
   constexpr tuple(const tuple<UTypes...>&);
template <class... UTypes>
   constexpr tuple(tuple<UTypes...>&&);

// only if sizeof...(Types) == 2
template <class U1, class U2>
   constexpr tuple(const pair<U1, U2>&);
template <class U1, class U2>
   constexpr tuple(pair<U1, U2>&&);
```

### <a name="parameters"></a>Parametreler

@No__t_1 *Al*
N. kopya demet öğesinin türü.

*sağ* \
Kopyalamanın bulunduğu kayıt düzeni.

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu, öğeleri varsayılan olarak oluşturulan bir nesne oluşturur.

İkinci Oluşturucu, öğeleri dizin `i - 1` `P1`, `P2`,... `PN` her `Pi` bağımsız değişkenlerden oluşturulan bir nesne oluşturur.

Üçüncü ve dördüncü oluşturucular, öğeleri ilişkili *sağ*öğeden oluşturulmuş olan bir nesne oluşturur.

Beşinci Oluşturucu, dizin 0 ' daki öğesi `right.first` oluşturulduğu ve Dizin 1 ' deki öğesi `right.second` oluşturulan kopya olan bir nesne oluşturur.

Kalan oluşturucular analoglarından daha önceki bir deyişle, [rvalue başvuru bildirimci: & &](../cpp/rvalue-reference-declarator-amp-amp.md).

### <a name="example"></a>Örnek

```cpp
// std__tuple__tuple_tuple.cpp
// compile with: /EHsc
#include <tuple>
#include <iostream>
#include <utility>

typedef std::tuple<int, double, int, double> Mytuple;
int main()
{
    Mytuple c0(0, 1, 2, 3);

    // display contents "0 1 2 3"
    std::cout << std::get<0>(c0) << " ";
    std::cout << std::get<1>(c0) << " ";
    std::cout << std::get<2>(c0) << " ";
    std::cout << std::get<3>(c0);
    std::cout << std::endl;

    Mytuple c1;
    c1 = c0;

    // display contents "0 1 2 3"
    std::cout << std::get<0>(c1) << " ";
    std::cout << std::get<1>(c1) << " ";
    std::cout << std::get<2>(c1) << " ";
    std::cout << std::get<3>(c1);
    std::cout << std::endl;

    std::tuple<char, int> c2(std::make_pair('x', 4));

    // display contents "x 4"
    std::cout << std::get<0>(c2) << " ";
    std::cout << std::get<1>(c2);
    std::cout << std::endl;

    Mytuple c3(c0);

    // display contents "0 1 2 3"
    std::cout << std::get<0>(c3) << " ";
    std::cout << std::get<1>(c3) << " ";
    std::cout << std::get<2>(c3) << " ";
    std::cout << std::get<3>(c3);
    std::cout << std::endl;

    typedef std::tuple<int, float, int, float> Mytuple2;
    Mytuple c4(Mytuple2(4, 5, 6, 7));

    // display contents "4 5 6 7"
    std::cout << std::get<0>(c4) << " ";
    std::cout << std::get<1>(c4) << " ";
    std::cout << std::get<2>(c4) << " ";
    std::cout << std::get<3>(c4);
    std::cout << std::endl;

    return (0);
}
```

```Output
0 1 2 3
0 1 2 3
x 4
0 1 2 3
4 5 6 7
```
