---
description: 'Daha fazla bilgi edinin: &lt; yardımcı program &gt; işleçleri'
title: '&lt;yardımcı program &gt; işleçleri'
ms.date: 11/04/2016
f1_keywords:
- utility/std::operator!=
- utility/std::operator&gt;
- utility/std::operator&gt;=
- utility/std::operator&lt;
- utility/std::operator&lt;=
- utility/std::operator==
ms.assetid: a6617109-2cec-4a69-948f-6c87116eda5f
helpviewer_keywords:
- std::operator!= (utility)
- std::operator&gt; (utility)
- std::operator&gt;= (utility)
- std::operator&lt; (utility)
- std::operator&lt;= (utility)
- std::operator== (utility)
ms.openlocfilehash: 0db6f5b18708052964353687190295084886c928
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97153466"
---
# <a name="ltutilitygt-operators"></a>&lt;yardımcı program &gt; işleçleri

> [!NOTE]
> Using işleçleri `Type&` altına dahildir `namespace rel_ops` .

## <a name="operator"></a><a name="op_neq"></a> işleç! =

İşlecin sol tarafındaki çift nesnenin sağ taraftaki çift nesneye eşit olup olmadığını sınar.

```cpp
template <class Type>
    constexpr bool operator!=(const Type& left, const Type& right);

template <class T, class U>
    constexpr bool operator!=(const pair<T, U>& left, const pair<T, U>& right);
```

### <a name="parameters"></a>Parametreler

*tarafta*\
`pair` türünün bir nesnesi.

*Right*\
`pair` türünün bir nesnesi.

### <a name="return-value"></a>Dönüş Değeri

**`true`** çiftler eşitse; **`false`** çiftler eşitse.

### <a name="remarks"></a>Açıklamalar

Bir çift, ilgili öğelerinin her biri eşitse başka bir çiftiyle eşittir. Birinci veya ikinci öğesi diğer çiftin karşılık gelen öğesine eşit değilse iki çift çifti eşit değildir.

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

## <a name="operator"></a><a name="op_eq_eq"></a> işleç = =

İşlecin sol tarafındaki çift nesnenin sağ taraftaki çift nesneye eşit olup olmadığını sınar.

```cpp
template <class T, class U>
constexpr bool operator==(const pair<T, U>& left, const pair<T, U>& right);
```

### <a name="parameters"></a>Parametreler

*tarafta*\
`pair` türünün bir nesnesi.

*Right*\
`pair` türünün bir nesnesi.

### <a name="return-value"></a>Dönüş Değeri

**`true`** çiftler eşitse; Çünkü **`false`** `pair` s eşit değildir.

### <a name="remarks"></a>Açıklamalar

Bir çift, ilgili öğelerinin her biri eşitse başka bir çiftiyle eşittir. İşlev döndürür `left` . **ilk** olarak  ==  `right` . **ilk** olarak  &&  `left` . **ikinci**  ==  `right` . **ikinci**. Birinci veya ikinci öğesi diğer çiftin karşılık gelen öğesine eşit değilse iki çift çifti eşit değildir.

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

## <a name="operatorlt"></a><a name="op_lt"></a> işlecinde&lt;

İşlecin sol tarafındaki çift nesnenin sağ taraftaki çift nesneden daha az olup olmadığını sınar.

```cpp
template <class T, class U>
constexpr bool operator<(const pair<T, U>& left, const pair<T, U>& right);
```

### <a name="parameters"></a>Parametreler

*tarafta*\
`pair`İşlecin sol tarafındaki türünde bir nesne.

*Right*\
`pair`İşlecin sağ tarafındaki türünde bir nesne.

### <a name="return-value"></a>Dönüş Değeri

**`true`**`pair`işlecin sol tarafındaki işlecinin, işlecin sağ tarafındaki öğesinden tamamen daha azı varsa, `pair` Aksi halde **`false`** .

### <a name="remarks"></a>Açıklamalar

`left` `pair` `right` `pair` *Sol* , *sağ* eşitse nesne nesneden kesinlikle küçüktür olarak kabul edilir.

Çiftler karşılaştırmasına göre, iki çifte bulunan değerlerin ' ilk öğesi en yüksek önceliğe sahiptir. Farklıysa, çiftin sonucu, çiftin karşılaştırmasının sonucu olarak alınır. İlk öğelerin değerleri farklı değilse, ikinci öğelerin değerleri karşılaştırılır ve Karşılaştırmanın sonucu, çiftin karşılaştırmasının sonucu olarak alınır.

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

## <a name="operatorlt"></a><a name="op_lt_eq"></a> işlecinde&lt;=

İşlecin sol tarafındaki çift nesnenin sağ taraftaki çift nesneden küçük veya ona eşit olup olmadığını sınar.

```cpp
template <class Type>
constexpr bool operator<=(const Type& left, const Type& right);

template <class T, class U>
constexpr bool operator<=(const pair<T, U>& left, const pair<T, U>& right);
```

### <a name="parameters"></a>Parametreler

*tarafta*\
`pair`İşlecin sol tarafındaki türünde bir nesne.

*Right*\
`pair`İşlecin sağ tarafındaki türünde bir nesne.

### <a name="return-value"></a>Dönüş Değeri

**`true`**`pair`işlecin sol tarafındaki işleci `pair` işlecin sağ tarafından küçük veya ona eşitse; Aksi takdirde **`false`** .

### <a name="remarks"></a>Açıklamalar

Çiftler karşılaştırmasına göre, iki çifte bulunan değerlerin ' ilk öğesi en yüksek önceliğe sahiptir. Farklıysa, çiftin sonucu, çiftin karşılaştırmasının sonucu olarak alınır. İlk öğelerin değerleri farklı değilse, ikinci öğelerin değerleri karşılaştırılır ve Karşılaştırmanın sonucu, çiftin karşılaştırmasının sonucu olarak alınır.

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

## <a name="operatorgt"></a><a name="op_gt"></a> işlecinde&gt;

İşlecin sol tarafındaki çift nesnenin sağ taraftaki çift nesneden büyük olup olmadığını sınar.

```cpp
template <class Type>
constexpr bool operator>(const Type& left, const Type& right);

template <class T, class U>
constexpr bool operator>(const pair<T, U>& left, const pair<T, U>& right);
```

### <a name="parameters"></a>Parametreler

*tarafta*\
`pair`İşlecin sol tarafındaki türünde bir nesne.

*Right*\
`pair`İşlecin sağ tarafındaki türünde bir nesne.

### <a name="return-value"></a>Dönüş Değeri

**`true`**`pair`işlecin sol tarafındaki işlecinin, işlecin sağ tarafındaki öğesinden kesinlikle büyük olması, `pair` Aksi halde **`false`** .

### <a name="remarks"></a>Açıklamalar

`left` `pair` `right` `pair` *Sol* , *sağ* eşitse nesne nesneden kesinlikle daha büyük olarak kabul edilir.

Çiftler karşılaştırmasına göre, iki çifte bulunan değerlerin ' ilk öğesi en yüksek önceliğe sahiptir. Farklıysa, çiftin sonucu, çiftin karşılaştırmasının sonucu olarak alınır. İlk öğelerin değerleri farklı değilse, ikinci öğelerin değerleri karşılaştırılır ve Karşılaştırmanın sonucu, çiftin karşılaştırmasının sonucu olarak alınır.

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

## <a name="operatorgt"></a><a name="op_gt_eq"></a> işlecinde&gt;=

İşlecin sol tarafındaki çift nesnenin sağ taraftaki çift nesneden büyük veya ona eşit olup olmadığını sınar.

```cpp
template <class Type>
    constexpr bool operator>=(const Type& left, const Type& right);

template <class T, class U>
    constexpr bool operator>=(const pair<T, U>& left, const pair<T, U>& right);
```

### <a name="parameters"></a>Parametreler

*tarafta*\
`pair`İşlecin sol tarafındaki türünde bir nesne.

*Right*\
`pair`İşlecin sağ tarafındaki türünde bir nesne.

### <a name="return-value"></a>Dönüş Değeri

**`true`**`pair`işlecin sol tarafındaki işlecinin sağ tarafından büyük veya ona eşitse `pair` ; Aksi takdirde **`false`** .

### <a name="remarks"></a>Açıklamalar

Çiftler karşılaştırmasına göre, iki çifte bulunan değerlerin ' ilk öğesi en yüksek önceliğe sahiptir. Farklıysa, çiftin sonucu, çiftin karşılaştırmasının sonucu olarak alınır. İlk öğelerin değerleri farklı değilse, ikinci öğelerin değerleri karşılaştırılır ve Karşılaştırmanın sonucu, çiftin karşılaştırmasının sonucu olarak alınır.

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
