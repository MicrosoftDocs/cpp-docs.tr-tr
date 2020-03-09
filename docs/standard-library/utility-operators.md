---
title: '&lt;yardımcı program&gt; işleçler'
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
ms.openlocfilehash: ec6c996487dc2e6c5ce628fe5e080b4f601479d9
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/06/2020
ms.locfileid: "78854880"
---
# <a name="ltutilitygt-operators"></a>&lt;yardımcı program&gt; işleçler

> [!NOTE]
> `Type&` kullanan işleçler `namespace rel_ops`altına dahildir.

## <a name="op_neq"></a>işleç! =

İşlecin sol tarafındaki çift nesnenin sağ taraftaki çift nesneye eşit olup olmadığını sınar.

```cpp
template <class Type>
    constexpr bool operator!=(const Type& left, const Type& right);

template <class T, class U>
    constexpr bool operator!=(const pair<T, U>& left, const pair<T, U>& right);
```

### <a name="parameters"></a>Parametreler

*sol*\
`pair` türünün bir nesnesi.

*sağ*\
`pair` türünün bir nesnesi.

### <a name="return-value"></a>Dönüş Değeri

çiftler eşit değilse **doğru** ; çiftler eşitse **false** .

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

## <a name="op_eq_eq"></a>işleç = =

İşlecin sol tarafındaki çift nesnenin sağ taraftaki çift nesneye eşit olup olmadığını sınar.

```cpp
template <class T, class U>
constexpr bool operator==(const pair<T, U>& left, const pair<T, U>& right);
```

### <a name="parameters"></a>Parametreler

*sol*\
`pair` türünün bir nesnesi.

*sağ*\
`pair` türünün bir nesnesi.

### <a name="return-value"></a>Dönüş Değeri

çiftler eşitse **true** ; `pair`s **değeri eşitse false** .

### <a name="remarks"></a>Açıklamalar

Bir çift, ilgili öğelerinin her biri eşitse başka bir çiftiyle eşittir. İşlev `left`döndürür. **ilk** == `right`. **ilk** && `left`. **ikinci** == `right`. **ikinci**. Birinci veya ikinci öğesi diğer çiftin karşılık gelen öğesine eşit değilse iki çift çifti eşit değildir.

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

## <a name="op_lt"></a>işleç&lt;

İşlecin sol tarafındaki çift nesnenin sağ taraftaki çift nesneden daha az olup olmadığını sınar.

```cpp
template <class T, class U>
constexpr bool operator<(const pair<T, U>& left, const pair<T, U>& right);
```

### <a name="parameters"></a>Parametreler

*sol*\
İşlecin sol tarafındaki `pair` türünde bir nesne.

*sağ*\
İşlecinin sağ tarafında `pair` türünde bir nesne.

### <a name="return-value"></a>Dönüş Değeri

işlecin sol tarafındaki `pair` işlecin sağ tarafındaki `pair` tamamen daha küçükse **true** ; Aksi halde **yanlış**.

### <a name="remarks"></a>Açıklamalar

`left` `pair` nesnesinin, *sol* , *sağdan*eşit olmayan `right` `pair` nesnesinden kesinlikle daha az olduğu söylenir.

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

## <a name="op_lt_eq"></a>işleç&lt;=

İşlecin sol tarafındaki çift nesnenin sağ taraftaki çift nesneden küçük veya ona eşit olup olmadığını sınar.

```cpp
template <class Type>
constexpr bool operator<=(const Type& left, const Type& right);

template <class T, class U>
constexpr bool operator<=(const pair<T, U>& left, const pair<T, U>& right);
```

### <a name="parameters"></a>Parametreler

*sol*\
İşlecin sol tarafındaki `pair` türünde bir nesne.

*sağ*\
İşlecinin sağ tarafında `pair` türünde bir nesne.

### <a name="return-value"></a>Dönüş Değeri

işlecin sol tarafındaki `pair` işlecin sağ tarafındaki `pair` küçük veya bu değere eşitse **true** ; Aksi halde **yanlış**.

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

## <a name="op_gt"></a>işleç&gt;

İşlecin sol tarafındaki çift nesnenin sağ taraftaki çift nesneden büyük olup olmadığını sınar.

```cpp
template <class Type>
constexpr bool operator>(const Type& left, const Type& right);

template <class T, class U>
constexpr bool operator>(const pair<T, U>& left, const pair<T, U>& right);
```

### <a name="parameters"></a>Parametreler

*sol*\
İşlecin sol tarafındaki `pair` türünde bir nesne.

*sağ*\
İşlecinin sağ tarafında `pair` türünde bir nesne.

### <a name="return-value"></a>Dönüş Değeri

işlecin sol tarafındaki `pair`, işlecin sağ tarafındaki `pair` tamamen daha büyükse **true** ; Aksi halde **yanlış**.

### <a name="remarks"></a>Açıklamalar

*Sol* tarafta `left` `pair` nesne `right` `pair` nesnesinden kesinlikle daha büyük olarak kabul *edilir.*

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

## <a name="op_gt_eq"></a>işleç&gt;=

İşlecin sol tarafındaki çift nesnenin sağ taraftaki çift nesneden büyük veya ona eşit olup olmadığını sınar.

```cpp
template <class Type>
    constexpr bool operator>=(const Type& left, const Type& right);

template <class T, class U>
    constexpr bool operator>=(const pair<T, U>& left, const pair<T, U>& right);
```

### <a name="parameters"></a>Parametreler

*sol*\
İşlecin sol tarafındaki `pair` türünde bir nesne.

*sağ*\
İşlecinin sağ tarafında `pair` türünde bir nesne.

### <a name="return-value"></a>Dönüş Değeri

işlecin sol tarafındaki `pair` işlecin sağ tarafındaki `pair` daha büyükse veya buna eşitse **true** ; Aksi halde **yanlış**.

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
