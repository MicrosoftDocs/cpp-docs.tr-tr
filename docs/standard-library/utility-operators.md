---
title: '&lt;yardımcı programı&gt; işleçleri | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- utility/std::operator!=
- utility/std::operator&gt;
- utility/std::operator&gt;=
- utility/std::operator&lt;
- utility/std::operator&lt;=
- utility/std::operator==
dev_langs:
- C++
ms.assetid: a6617109-2cec-4a69-948f-6c87116eda5f
helpviewer_keywords:
- std::operator!= (utility)
- std::operator&gt; (utility)
- std::operator&gt;= (utility)
- std::operator&lt; (utility)
- std::operator&lt;= (utility)
- std::operator== (utility)
ms.openlocfilehash: e5ed9d81e4b63dd57ebaf5f41ecc8422eaf166dd
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33861616"
---
# <a name="ltutilitygt-operators"></a>&lt;yardımcı programı&gt; işleçleri

||||
|-|-|-|
|[operator!=](#op_neq)|[işleci&gt;](#op_gt)|[işleci&gt;=](#op_gt_eq)|
|[işleci&lt;](#op_lt)|[işleci&lt;=](#op_lt_eq)|[operator==](#op_eq_eq)|

## <a name="op_neq"></a>  operator! =

Testleri işlecinin sol tarafındaki çifti nesnesi sağ tarafında çifti nesnesi eşit değil.

```cpp
template <class Type>
constexpr bool operator!=(const Type& left, const Type& right);

template <class T, class U>
constexpr bool operator!=(const pair<T, U>& left, const pair<T, U>& right);
```

### <a name="parameters"></a>Parametreler

`left` Türünde bir nesne **çifti.**

`right` Türünde bir nesne `pair`.

### <a name="return-value"></a>Dönüş Değeri

**doğru** çiftleri eşit; değilse **false** çiftleri eşit olması durumunda.

### <a name="remarks"></a>Açıklamalar

Kendi ilgili öğelerin her birini eşitse tek çifti için başka bir çift eşittir. İki ilk veya ikinci öğesi bir diğer çifti karşılık gelen öğesine eşit değilse eşit olmayan çiftleridir.

### <a name="example"></a>Örnek

```cpp
// utility_op_ne.cpp
// compile with: /EHsc
#include <utility>
#include <iomanip>
#include <iostream>

int main( )
{
   using namespace std;
   pair <int, double> p1, p2, p3;

   p1 = make_pair ( 10, 1.11e-1 );
   p2 = make_pair ( 1000, 1.11e-3 );
   p3 = make_pair ( 10, 1.11e-1 );

   cout.precision ( 3 );
   cout << "The pair p1 is: ( " << p1.first << ", "
        << p1.second << " )." << endl;
   cout << "The pair p2 is: ( " << p2.first << ", "
        << p2.second << " )." << endl;
   cout << "The pair p3 is: ( " << p3.first << ", "
        << p3.second << " )." << endl << endl;

   if ( p1 != p2 )
      cout << "The pairs p1 and p2 are not equal." << endl;
   else
      cout << "The pairs p1 and p2 are equal." << endl;

   if ( p1 != p3 )
      cout << "The pairs p1 and p3 are not equal." << endl;
   else
      cout << "The pairs p1 and p3 are equal." << endl;
}
```

```Output
The pair p1 is: ( 10, 0.111 ).
The pair p2 is: ( 1000, 0.00111 ).
The pair p3 is: ( 10, 0.111 ).

The pairs p1 and p2 are not equal.
The pairs p1 and p3 are equal.
```

## <a name="op_eq_eq"></a>  operator ==

Sağ taraftaki çifti nesnesi işlecinin sol tarafındaki çifti nesnesi eşitse testleri.

```cpp
template <class T, class U>
constexpr bool operator==(const pair<T, U>& left, const pair<T, U>& right);
```

### <a name="parameters"></a>Parametreler

`left` Türünde bir nesne **çifti.**

`right` Türünde bir nesne `pair`.

### <a name="return-value"></a>Dönüş Değeri

**doğru** çiftleri eşitse; **false** varsa `pair`s eşit değildir.

### <a name="remarks"></a>Açıklamalar

Kendi ilgili öğelerin her birini eşitse tek çifti için başka bir çift eşittir. İşlevi döndürür `left`. **İlk** == `right`. **İlk** && `left`. **İkinci** == `right`. **İkinci**. İki ilk veya ikinci öğesi bir diğer çifti karşılık gelen öğesine eşit değilse eşit olmayan çiftleridir.

### <a name="example"></a>Örnek

```cpp
// utility_op_eq.cpp
// compile with: /EHsc
#include <utility>
#include <iomanip>
#include <iostream>

int main( )
{
   using namespace std;
   pair <int, double> p1, p2, p3;

   p1 = make_pair ( 10, 1.11e-1 );
   p2 = make_pair ( 1000, 1.11e-3 );
   p3 = make_pair ( 10, 1.11e-1 );

   cout.precision ( 3 );
   cout << "The pair p1 is: ( " << p1.first << ", "
        << p1.second << " )." << endl;
   cout << "The pair p2 is: ( " << p2.first << ", "
        << p2.second << " )." << endl;
   cout << "The pair p3 is: ( " << p3.first << ", "
        << p3.second << " )." << endl << endl;

   if ( p1 == p2 )
      cout << "The pairs p1 and p2 are equal." << endl;
   else
      cout << "The pairs p1 and p2 are not equal." << endl;

   if ( p1 == p3 )
      cout << "The pairs p1 and p3 are equal." << endl;
   else
      cout << "The pairs p1 and p3 are not equal." << endl;
}
```

## <a name="op_lt"></a>  işleci&lt;

Çift işlecinin sol tarafında nesne sağlayıp sağlamadığını test azdır sağ tarafında çifti nesnesi.

```cpp
template <class T, class U>
constexpr bool operator<(const pair<T, U>& left, const pair<T, U>& right);
```

### <a name="parameters"></a>Parametreler

`left` Türünde bir nesne `pair` işlecinin sol tarafındaki.

`right` Türünde bir nesne `pair` işlecinin sağ tarafında.

### <a name="return-value"></a>Dönüş Değeri

**doğru** varsa `pair` işlecinin sol tarafında kesinlikle olan küçük `pair` ; işlecinin sağ tarafında aksi **false**.

### <a name="remarks"></a>Açıklamalar

`left` `pair` Nesne kesinlikle olmasını söyledi küçük `right` `pair` , nesne `left` eşit değildir ve küçük `right`.

Çiftleri Karşılaştırmada değerleri ilk iki çift öğelerden en yüksek önceliğe sahiptir. Bunlar farklıysa, karşılaştırma sonucu çifti karşılaştırması sonucu olarak alınır. İlk öğelerinin değerlerini farklı değilse, ikinci öğelerinin değerlerini karşılaştırılır ve bunların karşılaştırma sonucu çifti karşılaştırması sonucu olarak alınır.

### <a name="example"></a>Örnek

```cpp
// utility_op_lt.cpp
// compile with: /EHsc
#include <utility>
#include <iomanip>
#include <iostream>

int main( )
{
   using namespace std;
   pair <int, double> p1, p2, p3;

   p1 = make_pair ( 10, 2.22e-1 );
   p2 = make_pair ( 100, 1.11e-1 );
   p3 = make_pair ( 10, 1.11e-1 );

   cout.precision ( 3 );
   cout << "The pair p1 is: ( " << p1.first << ", "
        << p1.second << " )." << endl;
   cout << "The pair p2 is: ( " << p2.first << ", "
        << p2.second << " )." << endl;
   cout << "The pair p3 is: ( " << p3.first << ", "
        << p3.second << " )." << endl << endl;

   if ( p1 < p2 )
      cout << "The pair p1 is less than the pair p2." << endl;
   else
      cout << "The pair p1 is not less than the pair p2." << endl;

   if ( p1 < p3 )
      cout << "The pair p1 is less than the pair p3." << endl;
   else
      cout << "The pair p1 is not less than the pair p3." << endl;
}
```

```Output
The pair p1 is: ( 10, 0.222 ).
The pair p2 is: ( 100, 0.111 ).
The pair p3 is: ( 10, 0.111 ).

The pair p1 is less than the pair p2.
The pair p1 is not less than the pair p3.
```

## <a name="op_lt_eq"></a>  işleci&lt;=

Çift işlecinin sol tarafında nesne sağlayıp sağlamadığını test sağ tarafında çifti nesnesi eşit veya daha az olur.

```cpp
template <class Type>
constexpr bool operator<=(const Type& left, const Type& right);

template <class T, class U>
constexpr bool operator<=(const pair<T, U>& left, const pair<T, U>& right);
```

### <a name="parameters"></a>Parametreler

`left` Türünde bir nesne `pair` işlecinin sol tarafındaki.

`right` Türünde bir nesne `pair` işlecinin sağ tarafında.

### <a name="return-value"></a>Dönüş Değeri

**doğru** varsa `pair` işlecinin sol tarafında küçük veya buna eşit olduğundan `pair` ; işlecinin sağ tarafında aksi **false**.

### <a name="remarks"></a>Açıklamalar

Çiftleri Karşılaştırmada değerleri ilk iki çift öğelerden en yüksek önceliğe sahiptir. Bunlar farklıysa, karşılaştırma sonucu çifti karşılaştırması sonucu olarak alınır. İlk öğelerinin değerlerini farklı değilse, ikinci öğelerinin değerlerini karşılaştırılır ve bunların karşılaştırma sonucu çifti karşılaştırması sonucu olarak alınır.

### <a name="example"></a>Örnek

```cpp
// utility_op_le.cpp
// compile with: /EHsc
#include <utility>
#include <iomanip>
#include <iostream>

int main( )
{
   using namespace std;
   pair <int, double> p1, p2, p3, p4;

   p1 = make_pair ( 10, 2.22e-1 );
   p2 = make_pair ( 100, 1.11e-1 );
   p3 = make_pair ( 10, 1.11e-1 );
   p4 = make_pair ( 10, 2.22e-1 );

   cout.precision ( 3 );
   cout << "The pair p1 is: ( " << p1.first << ", "
        << p1.second << " )." << endl;
   cout << "The pair p2 is: ( " << p2.first << ", "
        << p2.second << " )." << endl;
   cout << "The pair p3 is: ( " << p3.first << ", "
        << p3.second << " )." << endl;
   cout << "The pair p4 is: ( " << p4.first << ", "
        << p4.second << " )." << endl << endl;

   if ( p1 <= p2 )
      cout << "The pair p1 is less than or equal to the pair p2." << endl;
   else
      cout << "The pair p1 is greater than the pair p2." << endl;

   if ( p1 <= p3 )
      cout << "The pair p1 is less than or equal to the pair p3." << endl;
   else
      cout << "The pair p1 is greater than the pair p3." << endl;

   if ( p1 <= p4 )
      cout << "The pair p1 is less than or equal to the pair p4." << endl;
   else
      cout << "The pair p1 is greater than the pair p4." << endl;
}
```

```Output
The pair p1 is: ( 10, 0.222 ).
The pair p2 is: ( 100, 0.111 ).
The pair p3 is: ( 10, 0.111 ).
The pair p4 is: ( 10, 0.222 ).

The pair p1 is less than or equal to the pair p2.
The pair p1 is greater than the pair p3.
The pair p1 is less than or equal to the pair p4.
```

## <a name="op_gt"></a>  işleci&gt;

Testleri işlecinin sol tarafındaki çifti nesnesi sağ tarafında çifti nesnesi değerinden daha büyük.

```cpp
template <class Type>
constexpr bool operator>(const Type& left, const Type& right);

template <class T, class U>
constexpr bool operator>(const pair<T, U>& left, const pair<T, U>& right);
```

### <a name="parameters"></a>Parametreler

`left` Türünde bir nesne `pair` işlecinin sol tarafındaki.

`right` Türünde bir nesne `pair` işlecinin sağ tarafında.

### <a name="return-value"></a>Dönüş Değeri

**doğru** varsa `pair` işlecinin sol tarafında değerinden kesinlikle büyük olan `pair` ; işlecinin sağ tarafında aksi **false**.

### <a name="remarks"></a>Açıklamalar

`left` `pair` Nesne değerinden kesinlikle büyük olacak şekilde söyledi `right` `pair` , nesne `left` daha büyük ve eşit değil `right`.

Çiftleri Karşılaştırmada değerleri ilk iki çift öğelerden en yüksek önceliğe sahiptir. Bunlar farklıysa, karşılaştırma sonucu çifti karşılaştırması sonucu olarak alınır. İlk öğelerinin değerlerini farklı değilse, ikinci öğelerinin değerlerini karşılaştırılır ve bunların karşılaştırma sonucu çifti karşılaştırması sonucu olarak alınır.

### <a name="example"></a>Örnek

```cpp
// utility_op_gt.cpp
// compile with: /EHsc
#include <utility>
#include <iomanip>
#include <iostream>

int main( )
{
   using namespace std;
   pair <int, double> p1, p2, p3, p4;

   p1 = make_pair ( 10, 2.22e-1 );
   p2 = make_pair ( 100, 1.11e-1 );
   p3 = make_pair ( 10, 1.11e-1 );
   p4 = make_pair ( 10, 2.22e-1 );

   cout.precision ( 3 );
   cout << "The pair p1 is: ( " << p1.first << ", "
        << p1.second << " )." << endl;
   cout << "The pair p2 is: ( " << p2.first << ", "
        << p2.second << " )." << endl;
   cout << "The pair p3 is: ( " << p3.first << ", "
        << p3.second << " )." << endl;
   cout << "The pair p4 is: ( " << p4.first << ", "
        << p4.second << " )." << endl << endl;

   if ( p1 > p2 )
      cout << "The pair p1 is greater than the pair p2." << endl;
   else
      cout << "The pair p1 is not greater than the pair p2." << endl;

   if ( p1 > p3 )
      cout << "The pair p1 is greater than the pair p3." << endl;
   else
      cout << "The pair p1 is not greater than the pair p3." << endl;

   if ( p1 > p4 )
      cout << "The pair p1 is greater than the pair p4." << endl;
   else
      cout << "The pair p1 is not greater than the pair p4." << endl;
}
```

```Output
The pair p1 is: ( 10, 0.222 ).
The pair p2 is: ( 100, 0.111 ).
The pair p3 is: ( 10, 0.111 ).
The pair p4 is: ( 10, 0.222 ).

The pair p1 is not greater than the pair p2.
The pair p1 is greater than the pair p3.
The pair p1 is not greater than the pair p4.
```

## <a name="op_gt_eq"></a>  işleci&gt;=

Testleri işlecinin sol tarafındaki çifti nesnesi sağ tarafında çifti nesnesi eşit veya daha büyük.

```cpp
template <class Type>
constexpr bool operator>=(const Type& left, const Type& right);

template <class T, class U>
constexpr bool operator>=(const pair<T, U>& left, const pair<T, U>& right);
```

### <a name="parameters"></a>Parametreler

`left` Türünde bir nesne `pair` işlecinin sol tarafındaki.

`right` Türünde bir nesne `pair` işlecinin sağ tarafında.

### <a name="return-value"></a>Dönüş Değeri

**doğru** varsa `pair` işlecinin sol tarafında büyüktür veya şuna eşittir: `pair` ; işlecinin sağ tarafında aksi **false**.

### <a name="remarks"></a>Açıklamalar

Çiftleri Karşılaştırmada değerleri ilk iki çift öğelerden en yüksek önceliğe sahiptir. Bunlar farklıysa, karşılaştırma sonucu çifti karşılaştırması sonucu olarak alınır. İlk öğelerinin değerlerini farklı değilse, ikinci öğelerinin değerlerini karşılaştırılır ve bunların karşılaştırma sonucu çifti karşılaştırması sonucu olarak alınır.

### <a name="example"></a>Örnek

```cpp
// utility_op_ge.cpp
// compile with: /EHsc
#include <utility>
#include <iomanip>
#include <iostream>

int main( )
{
   using namespace std;
   pair <int, double> p1, p2, p3, p4;

   p1 = make_pair ( 10, 2.22e-1 );
   p2 = make_pair ( 100, 1.11e-1 );
   p3 = make_pair ( 10, 1.11e-1 );
   p4 = make_pair ( 10, 2.22e-1 );

   cout.precision ( 3 );
   cout << "The pair p1 is: ( " << p1.first << ", "
        << p1.second << " )." << endl;
   cout << "The pair p2 is: ( " << p2.first << ", "
        << p2.second << " )." << endl;
   cout << "The pair p3 is: ( " << p3.first << ", "
        << p3.second << " )." << endl;
   cout << "The pair p4 is: ( " << p4.first << ", "
        << p4.second << " )." << endl << endl;

   if ( p1 >= p2 )
      cout << "Pair p1 is greater than or equal to pair p2." << endl;
   else
      cout << "The pair p1 is less than the pair p2." << endl;

   if ( p1 >= p3 )
      cout << "Pair p1 is greater than or equal to pair p3." << endl;
   else
      cout << "The pair p1 is less than the pair p3." << endl;

   if ( p1 >= p4 )
      cout << "Pair p1 is greater than or equal to pair p4." << endl;
   else
      cout << "The pair p1 is less than the pair p4." << endl;
}
```

```Output
The pair p1 is: ( 10, 0.222 ).
The pair p2 is: ( 100, 0.111 ).
The pair p3 is: ( 10, 0.111 ).
The pair p4 is: ( 10, 0.222 ).

The pair p1 is less than the pair p2.
Pair p1 is greater than or equal to pair p3.
Pair p1 is greater than or equal to pair p4.
```

## <a name="see-also"></a>Ayrıca bkz.

[\<yardımcı programı >](../standard-library/utility.md)<br/>
