---
title: '&lt;Liste&gt; işleçleri | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- list/std::operator!=
- list/std::operator&gt;
- list/std::operator&gt;=
- list/std::operator&lt;
- list/std::operator&lt;=
- list/std::operator==
dev_langs:
- C++
ms.assetid: 8103d8f2-c30f-49ad-ac50-b3ba6a907ebe
helpviewer_keywords:
- std::operator!= (list)
- std::operator&gt; (list)
- std::operator&gt;= (list)
- std::operator&lt; (list)
- std::operator&lt;= (list)
- std::operator== (list)
ms.openlocfilehash: b2647cf836fb565115b8a582085b6108c01a3420
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
---
# <a name="ltlistgt-operators"></a>&lt;Liste&gt; işleçleri

||||
|-|-|-|
|[operator!=](#op_neq)|[işleci&gt;](#op_gt)|[işleci&gt;=](#op_gt_eq)|
|[işleci&lt;](#op_lt)|[işleci&lt;=](#op_lt_eq)|[operator==](#op_eq_eq)|

## <a name="op_neq"></a>  operator! =

Testleri işlecinin sol tarafındaki liste nesnesi sağ tarafında listesi nesnesine eşit değil.

```cpp
bool operator!=(
    const list<Type, Allocator>& left,
    const list<Type, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

`left` Türünde bir nesne **listesi**.

`right` Türünde bir nesne **listesi**.

### <a name="return-value"></a>Dönüş Değeri

**doğru** listeler eşit; değilse **false** listeler eşit olması durumunda.

### <a name="remarks"></a>Açıklamalar

List nesneleri arasındaki karşılaştırma öğelerini pairwise karşılaştırması hakkında temel alır. İki liste aynı sayıda öğe varsa ve bunların ilgili öğeleri aynı değerlere eşittir. Aksi takdirde, bunlar eşit.

### <a name="example"></a>Örnek

```cpp
// list_op_ne.cpp
// compile with: /EHsc
#include <list>
#include <iostream>

int main( )
{
using namespace std;
list <int> c1, c2;
c1.push_back( 1 );
c2.push_back( 2 );

if ( c1 != c2 )
cout << "Lists not equal." << endl;
else
cout << "Lists equal." << endl;
}
\* Output:
Lists not equal.
*\
```

## <a name="op_lt"></a>  işleci&lt;

Liste nesnesi işlecinin sol tarafındaki liste nesnesi sağ tarafında küçükse testleri.

```cpp
bool operator<(
    const list<Type, Allocator>& left,
    const list<Type, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

`left` Türünde bir nesne **listesi**.

`right` Türünde bir nesne **listesi**.

### <a name="return-value"></a>Dönüş Değeri

**doğru** listenin işlecinin sol tarafındaki ancak değil listenin işlecinin sağ tarafında eşit; Aksi takdirde düşükse **false**.

### <a name="remarks"></a>Açıklamalar

List nesneleri arasındaki karşılaştırma öğelerini pairwise karşılaştırması hakkında temel alır. Küçüktür-iki nesne arasındaki ilişki ilk çiftlerini eşit olmayan bir karşılaştırmasını alan daha.

### <a name="example"></a>Örnek

```cpp
// list_op_lt.cpp
// compile with: /EHsc
#include <list>
#include <iostream>

int main( )
{
   using namespace std;
   list <int> c1, c2;
   c1.push_back( 1 );
   c1.push_back( 2 );
   c1.push_back( 4 );

   c2.push_back( 1 );
   c2.push_back( 3 );

   if ( c1 < c2 )
      cout << "List c1 is less than list c2." << endl;
   else
      cout << "List c1 is not less than list c2." << endl;
}
\* Output:
List c1 is less than list c2.
*\
```

## <a name="op_lt_eq"></a>  işleci&lt;=

Listenin işlecinin sol tarafında nesne sağlayıp sağlamadığını test sağ tarafında liste nesnesi eşit veya daha az olur.

```cpp
bool operator<=(
    const list<Type, Allocator>& left,
    const list<Type, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

`left` Türünde bir nesne **listesi**.

`right` Türünde bir nesne **listesi**.

### <a name="return-value"></a>Dönüş Değeri

**doğru** işlecinin sol tarafındaki liste veya liste işlecinin sağ tarafında eşit; aksi düşükse **false**.

### <a name="remarks"></a>Açıklamalar

List nesneleri arasındaki karşılaştırma öğelerini pairwise karşılaştırması hakkında temel alır. İki nesne arasındaki ilişki için küçük veya eşittir ilk çiftlerini eşit olmayan bir karşılaştırmasını temel alır.

### <a name="example"></a>Örnek

```cpp
// list_op_le.cpp
// compile with: /EHsc
#include <list>
#include <iostream>

int main( )
{
   using namespace std;
   list <int> c1, c2;
   c1.push_back( 1 );
   c1.push_back( 2 );
   c1.push_back( 4 );

   c2.push_back( 1 );
   c2.push_back( 3 );

   if ( c1 <= c2 )
      cout << "List c1 is less than or equal to list c2." << endl;
   else
      cout << "List c1 is greater than list c2." << endl;
}
\* Output:
List c1 is less than or equal to list c2.
*\
```

## <a name="op_eq_eq"></a>  operator ==

Liste nesnesi işlecinin sol tarafındaki sağ tarafında listesi nesnesine eşitse testleri.

```cpp
bool operator==(
    const list<Type, Allocator>& left,
    const list<Type, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

`left` Türünde bir nesne **listesi**.

`right` Türünde bir nesne **listesi**.

### <a name="return-value"></a>Dönüş Değeri

**doğru** listenin işlecinin sol tarafındaki eşitse işlecinin sağ tarafında listesine aksi **false**.

### <a name="remarks"></a>Açıklamalar

List nesneleri arasındaki karşılaştırma öğelerini pairwise karşılaştırması hakkında temel alır. İki liste aynı sayıda öğe varsa ve bunların ilgili öğeleri aynı değerlere eşittir. Aksi takdirde, bunlar eşit.

### <a name="example"></a>Örnek

```cpp
// list_op_eq.cpp
// compile with: /EHsc
#include <list>
#include <iostream>
int main( )
{
   using namespace std;

   list <int> c1, c2;
   c1.push_back( 1 );
   c2.push_back( 1 );

   if ( c1 == c2 )
      cout << "The lists are equal." << endl;
   else
      cout << "The lists are not equal." << endl;
}
\* Output:
The lists are equal.
*\
```

## <a name="op_gt"></a>  işleci&gt;

Testleri işlecinin sol tarafındaki liste nesnesi sağ taraftaki liste nesnesi değerinden daha büyük.

```cpp
bool operator>(
    const list<Type, Allocator>& left,
    const list<Type, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

`left` Türünde bir nesne **listesi**.

`right` Türünde bir nesne **listesi**.

### <a name="return-value"></a>Dönüş Değeri

**doğru** işlecinin sol tarafındaki listesi ise, listenin işlecinin sağ tarafında büyük; Aksi takdirde **false**.

### <a name="remarks"></a>Açıklamalar

List nesneleri arasındaki karşılaştırma öğelerini pairwise karşılaştırması hakkında temel alır. Büyük-iki nesne arasındaki ilişki ilk çiftlerini eşit olmayan bir karşılaştırmasını alan daha.

### <a name="example"></a>Örnek

```cpp
// list_op_gt.cpp
// compile with: /EHsc
#include <list>
#include <iostream>
int main( )
{
   using namespace std;
   list <int> c1, c2;
   c1.push_back( 1 );
   c1.push_back( 3 );
   c1.push_back( 1 );

   c2.push_back( 1 );
   c2.push_back( 2 );
   c2.push_back( 2 );

   if ( c1 > c2 )
      cout << "List c1 is greater than list c2." << endl;
   else
      cout << "List c1 is not greater than list c2." << endl;
}
\* Output:
List c1 is greater than list c2.
*\
```

## <a name="op_gt_eq"></a>  işleci&gt;=

Testleri listesi işlecinin sol tarafındaki büyük veya ona eşit listesi nesnesine sağ tarafında nesnesidir.

```cpp
bool operator>=(
    const list<Type, Allocator>& left,
    const list<Type, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

`left` Türünde bir nesne **listesi**.

`right` Türünde bir nesne **listesi**.

### <a name="return-value"></a>Dönüş Değeri

**doğru** işlecinin sol tarafındaki liste büyük veya eşit işlecinin sağ tarafında listesine; tersi durumda ise **false**.

### <a name="remarks"></a>Açıklamalar

List nesneleri arasındaki karşılaştırma öğelerini pairwise karşılaştırması hakkında temel alır. Büyük veya ona eşit iki nesne arasındaki ilişki için ilk çiftlerini eşit olmayan bir karşılaştırmasını temel alır.

### <a name="example"></a>Örnek

```cpp
// list_op_ge.cpp
// compile with: /EHsc
#include <list>
#include <iostream>

int main( )
{
   using namespace std;
   list <int> c1, c2;
   c1.push_back( 1 );
   c1.push_back( 3 );
   c1.push_back( 1 );

   c2.push_back( 1 );
   c2.push_back( 2 );
   c2.push_back( 2 );

   if ( c1 >= c2 )
      cout << "List c1 is greater than or equal to list c2." << endl;
   else
      cout << "List c1 is less than list c2." << endl;
}
\* Output:
List c1 is greater than or equal to list c2.
*\
```

## <a name="see-also"></a>Ayrıca bkz.

[\<Liste >](../standard-library/list.md)<br/>
