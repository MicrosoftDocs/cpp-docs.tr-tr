---
title: '&lt;yardımcı programı&gt; işleçleri'
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
ms.openlocfilehash: 418b18851aaf8da44ee0ed2df7ff9e60a0b5ef1f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50653693"
---
# <a name="ltutilitygt-operators"></a>&lt;yardımcı programı&gt; işleçleri

||||
|-|-|-|
|[operator!=](#op_neq)|[İşleci&gt;](#op_gt)|[İşleci&gt;=](#op_gt_eq)|
|[İşleci&lt;](#op_lt)|[İşleci&lt;=](#op_lt_eq)|[operator==](#op_eq_eq)|

## <a name="op_neq"></a>  işleç! =

İşlecin sol tarafındaki çift nesnesi işlecin sağ tarafındaki çifti nesneye eşit olup olmadığını sınar.

```cpp
template <class Type>
constexpr bool operator!=(const Type& left, const Type& right);

template <class T, class U>
constexpr bool operator!=(const pair<T, U>& left, const pair<T, U>& right);
```

### <a name="parameters"></a>Parametreler

*Sol*<br/>
Bir nesne türü `pair`.

*sağ*<br/>
Bir nesne türü `pair`.

### <a name="return-value"></a>Dönüş Değeri

**doğru** çiftleri eşit; değilse, **false** çiftleri eşitse.

### <a name="remarks"></a>Açıklamalar

Her bir ilgili öğeleri eşitse bir çifti için başka bir çift eşittir. İki ilk veya ikinci öğe bir diğer çifti karşılık gelen öğesine eşit değilse eşit çiftleridir.

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

## <a name="op_eq_eq"></a>  işleç ==

İşlecin sol tarafındaki çifti nesnesinin işlecin sağ tarafındaki çifti nesneye eşit olup olmadığını sınar.

```cpp
template <class T, class U>
constexpr bool operator==(const pair<T, U>& left, const pair<T, U>& right);
```

### <a name="parameters"></a>Parametreler

*Sol*<br/>
Bir nesne türü `pair`.

*sağ*<br/>
Bir nesne türü `pair`.

### <a name="return-value"></a>Dönüş Değeri

**doğru** çiftleri eşitse; **false** varsa `pair`s eşit değildir.

### <a name="remarks"></a>Açıklamalar

Her bir ilgili öğeleri eşitse bir çifti için başka bir çift eşittir. İşlev döndürür `left`. **İlk** == `right`. **İlk** && `left`. **İkinci** == `right`. **İkinci**. İki ilk veya ikinci öğe bir diğer çifti karşılık gelen öğesine eşit değilse eşit çiftleridir.

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

## <a name="op_lt"></a>  İşleci&lt;

İşlecin sol tarafta çift nesnesi olup olmadığını test eder çifti nesnesinin işlecin sağ tarafındaki küçüktür.

```cpp
template <class T, class U>
constexpr bool operator<(const pair<T, U>& left, const pair<T, U>& right);
```

### <a name="parameters"></a>Parametreler

*Sol*<br/>
Bir nesne türü `pair` işlecinin sol tarafındaki.

*sağ*<br/>
Bir nesne türü `pair` işlecin sağ tarafındaki.

### <a name="return-value"></a>Dönüş Değeri

**doğru** varsa `pair` işlecinin sol tarafında kesinlikle olan küçüktür `pair` ; işlecin sağ tarafındaki aksi **false**.

### <a name="remarks"></a>Açıklamalar

`left` `pair` Nesne söyledi kesinlikle olacak şekilde küçüktür `right` `pair` , nesne *sol* eşit değildir ve küçük *doğru*.

Çiftleri Karşılaştırmada değerlerin ilk öğesini iki çiftleri en yüksek önceliğe sahiptir. Bunlar farklıysa, Karşılaştırmanın sonucu çiftinin Karşılaştırmanın sonucu kabul edilir. İlk öğe değerlerini farklı değilse, ikinci öğe değerlerini karşılaştırılır ve bunların karşılaştırma sonucu çiftinin Karşılaştırmanın sonucu alınır.

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

## <a name="op_lt_eq"></a>  İşleci&lt;=

İşlecinin sol tarafta çift nesnesi küçük olup olmadığını sınar veya işlecin sağ tarafındaki çift nesnesi eşittir.

```cpp
template <class Type>
constexpr bool operator<=(const Type& left, const Type& right);

template <class T, class U>
constexpr bool operator<=(const pair<T, U>& left, const pair<T, U>& right);
```

### <a name="parameters"></a>Parametreler

*Sol*<br/>
Bir nesne türü `pair` işlecinin sol tarafındaki.

*sağ*<br/>
Bir nesne türü `pair` işlecin sağ tarafındaki.

### <a name="return-value"></a>Dönüş Değeri

**doğru** varsa `pair` işlecinin sol tarafında daha az veya buna eşit olan `pair` ; işlecin sağ tarafındaki aksi **false**.

### <a name="remarks"></a>Açıklamalar

Çiftleri Karşılaştırmada değerlerin ilk öğesini iki çiftleri en yüksek önceliğe sahiptir. Bunlar farklıysa, Karşılaştırmanın sonucu çiftinin Karşılaştırmanın sonucu kabul edilir. İlk öğe değerlerini farklı değilse, ikinci öğe değerlerini karşılaştırılır ve bunların karşılaştırma sonucu çiftinin Karşılaştırmanın sonucu alınır.

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

## <a name="op_gt"></a>  İşleci&gt;

İşlecin sol tarafındaki çifti nesnesinin işlecin sağ tarafındaki çift nesnesi büyük olup olmadığını sınar.

```cpp
template <class Type>
constexpr bool operator>(const Type& left, const Type& right);

template <class T, class U>
constexpr bool operator>(const pair<T, U>& left, const pair<T, U>& right);
```

### <a name="parameters"></a>Parametreler

*Sol*<br/>
Bir nesne türü `pair` işlecinin sol tarafındaki.

*sağ*<br/>
Bir nesne türü `pair` işlecin sağ tarafındaki.

### <a name="return-value"></a>Dönüş Değeri

**doğru** varsa `pair` işlecinin sol tarafında değerinden kesinlikle büyük olan `pair` ; işlecin sağ tarafındaki aksi **false**.

### <a name="remarks"></a>Açıklamalar

`left` `pair` Nesne değerinden kesinlikle büyük olacak şekilde söyledi `right` `pair` , nesne *sol* büyükse ve eşit değildir *doğru*.

Çiftleri Karşılaştırmada değerlerin ilk öğesini iki çiftleri en yüksek önceliğe sahiptir. Bunlar farklıysa, Karşılaştırmanın sonucu çiftinin Karşılaştırmanın sonucu kabul edilir. İlk öğe değerlerini farklı değilse, ikinci öğe değerlerini karşılaştırılır ve bunların karşılaştırma sonucu çiftinin Karşılaştırmanın sonucu alınır.

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

## <a name="op_gt_eq"></a>  İşleci&gt;=

İşlecin sol tarafındaki çift nesnesi büyük veya işlecin sağ tarafındaki çifti nesneye eşit olup olmadığını sınar.

```cpp
template <class Type>
constexpr bool operator>=(const Type& left, const Type& right);

template <class T, class U>
constexpr bool operator>=(const pair<T, U>& left, const pair<T, U>& right);
```

### <a name="parameters"></a>Parametreler

*Sol*<br/>
Bir nesne türü `pair` işlecinin sol tarafındaki.

*sağ*<br/>
Bir nesne türü `pair` işlecin sağ tarafındaki.

### <a name="return-value"></a>Dönüş Değeri

**doğru** varsa `pair` büyüktür veya eşittir işleci sol tarafında olduğu `pair` ; işlecin sağ tarafındaki aksi **false**.

### <a name="remarks"></a>Açıklamalar

Çiftleri Karşılaştırmada değerlerin ilk öğesini iki çiftleri en yüksek önceliğe sahiptir. Bunlar farklıysa, Karşılaştırmanın sonucu çiftinin Karşılaştırmanın sonucu kabul edilir. İlk öğe değerlerini farklı değilse, ikinci öğe değerlerini karşılaştırılır ve bunların karşılaştırma sonucu çiftinin Karşılaştırmanın sonucu alınır.

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
