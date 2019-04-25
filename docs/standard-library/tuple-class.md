---
title: tuple Sınıfı
ms.date: 11/04/2016
f1_keywords:
- tuple/std::tuple
- tuple/std::tuple::operator=
helpviewer_keywords:
- tuple class
ms.assetid: c38749be-ae4d-41f3-98ea-6aa3250de9a3
ms.openlocfilehash: 7e85ad445743cc02ba078eb3c09342f69915c09c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62279068"
---
# <a name="tuple-class"></a>tuple Sınıfı

Sabit uzunluklu dizi öğe sarmalar.

## <a name="syntax"></a>Sözdizimi

```
class tuple {
public:
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

*TN*<br/>
Nth demet öğesi türü.

## <a name="remarks"></a>Açıklamalar

Şablon sınıfı türlerinin N nesnelerini depolayan bir nesneyi tanımlayan `T1`, `T2`,..., `TN`sırasıyla burada `0 <= N <= Nmax`. Bir tanımlama grubu örneği kapsamını `tuple<T1, T2, ..., TN>` sayı `N` , şablon bağımsız değişkenlerinin. Şablon bağımsız değişkeni dizinini `Ti` ve karşılık gelen depolanan değeri o türün `i - 1`. Bu nedenle, biz 1 Bu belgelerindeki türleri n numara, ancak karşılık gelen dizin aralığı 0-N - 1 değerleri.

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

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<kayıt >

**Namespace:** std

## <a name="op_eq"></a>  tuple::operator=

Atayan bir `tuple` nesne.

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

*GERİ AL*<br/>
Demet öğesi türü n. kopyalanır.

*sağ*<br/>
Kopyalamak için kayıt düzeni.

### <a name="remarks"></a>Açıklamalar

İlk iki üye işleçleri öğelerini atama *doğru* ilgili öğelerin `*this`. Üçüncü üye işleci atar `right.first` dizini 0 öğe için `*this` ve `right.second` için 1 dizindeki öğe. Tüm üç üye işleçleri dönüş `*this`.

Kalan üye işleçleri analogs öncekileri, ancak sahip olduğunuz [Rvalue başvuru Bildirimcisi: & &](../cpp/rvalue-reference-declarator-amp-amp.md).

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

## <a name="tuple_swap"></a>  tuple:swap

İki öğelerini birbiriyle değiştirir.

```cpp
template <class... Types>
   void swap(tuple<Types...&> left, tuple<Types...&> right);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*Sol*|Kayıt düzeninin öğelerle için öğeleri olan tanımlama grubu *doğru*.|
|*sağ*|Kayıt düzeninin öğelerle için öğeleri olan tanımlama grubu *sol*.|

### <a name="remarks"></a>Açıklamalar

İşlevi yürütür `left.swap(right)`.

## <a name="tuple"></a>  Tuple::Tuple

Oluşturur bir `tuple` nesne.

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

*GERİ AL*<br/>
Demet öğesi türü n. kopyalanır.

*sağ*<br/>
Kopyalamak için kayıt düzeni.

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu, varsayılan oluşturulmuş öğeleri olan bir nesne oluşturur.

İkinci oluşturucu bağımsız değişkenden oluşan kopyalama, öğeleri olan bir nesne oluşturur `P1`, `P2`,..., `PN` her `Pi` dizinindeki öğeyi başlatma `i - 1`.

Üçüncü ve dördüncü oluşturucuları kopya karşılık gelen öğeden öğeleri olan bir nesne oluşturmak *doğru*.

Oluşturulan dizini 0 olan bir öğede kopyası olan bir nesne öğesinden beşinci Oluşturucu yapıları `right.first` ve dizini 1 olan bir öğede kopyalama nesnesinden oluşturulan `right.second`.

Kalan oluşturucular analogs öncekileri, ancak sahip olduğunuz [Rvalue başvuru Bildirimcisi: & &](../cpp/rvalue-reference-declarator-amp-amp.md).

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

## <a name="see-also"></a>Ayrıca bkz.

[\<Tanımlama grubu >](../standard-library/tuple.md)<br/>
[make_tuple](../standard-library/tuple-functions.md#make_tuple)<br/>
