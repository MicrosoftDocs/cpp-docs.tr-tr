---
title: '&lt;deque&gt; işleçleri | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- deque/std::operator!=
- deque/std::operator&gt;
- deque/std::operator&gt;=
- deque/std::operator&lt;
- deque/std::operator&lt;=
- deque/std::operator==
dev_langs:
- C++
ms.assetid: 482d7c92-54c7-493b-99e6-2a73617481a5
helpviewer_keywords:
- std::operator!= (deque)
- std::operator&gt; (deque)
- std::operator&gt;= (deque)
- std::operator&lt; (deque)
- std::operator&lt;= (deque)
- std::operator== (deque)
ms.openlocfilehash: d4dfa6963e9c8194bd4ee589a1a0adced1f05d0d
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33846850"
---
# <a name="ltdequegt-operators"></a>&lt;deque&gt; işleçleri

||||
|-|-|-|
|[operator!=](#op_neq)|[işleci&gt;](#op_gt)|[işleci&gt;=](#op_gt_eq)|
|[işleci&lt;](#op_lt)|[işleci&lt;=](#op_lt_eq)|[operator==](#op_eq_eq)|

## <a name="op_neq"></a>  operator! =

Deque nesne işlecinin sol tarafındaki sağ tarafında deque nesnesine eşit değilse testleri.

```cpp
bool operator!=(const deque<Type, Allocator>& left, const deque<Type, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

`left` Türünde bir nesne `deque`.

`right` Türünde bir nesne `deque`.

### <a name="return-value"></a>Dönüş Değeri

**doğru** deque nesneleri eşit; değilse **false** deque nesneleri eşit olması durumunda.

### <a name="remarks"></a>Açıklamalar

Deque nesneleri arasındaki karşılaştırma öğelerini pairwise karşılaştırması hakkında temel alır. İki deque nesneleri aynı sayıda öğe varsa ve bunların ilgili öğeleri aynı değerlere eşittir. Aksi takdirde, bunlar eşit.

### <a name="example"></a>Örnek

```cpp
// deque_op_ne.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>

int main( )
{
   using namespace std;
   deque <int> c1, c2;

   c1.push_back( 1 );
   c2.push_back( 2 );

   if ( c1 != c2 )
      cout << "The deques are not equal." << endl;
   else
      cout << "The deques are equal." << endl;
}
\* Output:
The deques are not equal.
*\
```

## <a name="op_lt"></a>  işleci&lt;

Deque nesne işlecinin sol tarafındaki sağ tarafında deque nesne küçükse testleri.

```cpp
bool operator<(const deque<Type, Allocator>& left, const deque<Type, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

`left` Türünde bir nesne `deque`.

`right` Türünde bir nesne `deque`.

### <a name="return-value"></a>Dönüş Değeri

**doğru** işlecinin sol tarafındaki deque ve değil işlecinin sağ tarafında deque eşit; Aksi takdirde düşükse **false**.

### <a name="remarks"></a>Açıklamalar

Deque nesneleri arasındaki karşılaştırma öğelerini pairwise karşılaştırması hakkında temel alır. Küçüktür-iki nesne arasındaki ilişki ilk çiftlerini eşit olmayan bir karşılaştırmasını alan daha.

### <a name="example"></a>Örnek

```cpp
// deque_op_lt.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>

int main( )
{
   using namespace std;
   deque <int> c1, c2;

   c1.push_back( 1 );
   c1.push_back( 2 );
   c1.push_back( 4 );

   c2.push_back( 1 );
   c2.push_back( 3 );

   if ( c1 < c2 )
      cout << "Deque c1 is less than deque c2." << endl;
   else
      cout << "Deque c1 is not less than deque c2." << endl;
}
\* Output:
Deque c1 is less than deque c2.
*\
```

## <a name="op_lt_eq"></a>  işleci&lt;=

Deque işlecinin sol tarafında nesne sağlayıp sağlamadığını test sağ tarafında deque nesnesine eşit veya daha az olur.

```cpp
bool operator<=(const deque<Type, Allocator>& left, const deque<Type, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

`left` Türünde bir nesne `deque`.

`right` Türünde bir nesne `deque`.

### <a name="return-value"></a>Dönüş Değeri

**doğru** işlecinin sol tarafındaki deque veya deque işlecinin sağ tarafında eşit; Aksi takdirde düşükse **false**.

### <a name="remarks"></a>Açıklamalar

Deque nesneleri arasındaki karşılaştırma öğelerini pairwise karşılaştırması hakkında temel alır. İki nesne arasındaki ilişki için küçük veya eşittir ilk çiftlerini eşit olmayan bir karşılaştırmasını temel alır.

### <a name="example"></a>Örnek

```cpp
// deque_op_le.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>

int main( )
{
   using namespace std;
   deque <int> c1, c2;

   c1.push_back( 1 );
   c1.push_back( 2 );
   c1.push_back( 4 );

   c2.push_back( 1 );
   c2.push_back( 3 );

   if ( c1 <= c2 )
      cout << "Deque c1 is less than or equal to deque c2." << endl;
   else
      cout << "Deque c1 is greater than deque c2." << endl;
}
\* Output:
Deque c1 is less than or equal to deque c2.
*\

```

## <a name="op_eq_eq"></a>  operator ==

Deque nesne işlecinin sol tarafındaki sağ tarafında deque nesnesine eşitse testleri.

```cpp
bool operator==(const deque<Type, Allocator>& left, const deque<Type, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

`left` Türünde bir nesne `deque`.

`right` Türünde bir nesne `deque`.

### <a name="return-value"></a>Dönüş Değeri

**doğru** deque işlecinin sol tarafındaki işlecinin sağ tarafında deque eşit; tersi durumda ise **false**.

### <a name="remarks"></a>Açıklamalar

Deque nesneleri arasındaki karşılaştırma öğelerini pairwise karşılaştırması hakkında temel alır. İki deques aynı sayıda öğe varsa ve bunların ilgili öğeleri aynı değerlere eşittir. Aksi takdirde, bunlar eşit.

### <a name="example"></a>Örnek

```cpp
// deque_op_eq.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>

int main( )
{
   using namespace std;
   deque <int> c1, c2;

   c1.push_back( 1 );
   c2.push_back( 1 );

   if ( c1 == c2 )
      cout << "The deques are equal." << endl;
   else
      cout << "The deques are not equal." << endl;

   c1.push_back( 1 );
   if ( c1 == c2 )
      cout << "The deques are equal." << endl;
   else
      cout << "The deques are not equal." << endl;
}
\* Output:
The deques are equal.
The deques are not equal.
*\

```

## <a name="op_gt"></a>  işleci&gt;

Deque nesne işlecinin sol tarafındaki sağ tarafında deque nesne büyükse testleri.

```cpp
bool operator>(const deque<Type, Allocator>& left, const deque<Type, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

`left` Türünde bir nesne `deque`.

`right` Türünde bir nesne `deque`.

### <a name="return-value"></a>Dönüş Değeri

**doğru** deque işlecinin sol tarafındaki işlecinin sağ tarafında deque büyük; tersi durumda ise **false**.

### <a name="remarks"></a>Açıklamalar

Deque nesneleri arasındaki karşılaştırma öğelerini pairwise karşılaştırması hakkında temel alır. Büyük-iki nesne arasındaki ilişki ilk çiftlerini eşit olmayan bir karşılaştırmasını alan daha.

### <a name="example"></a>Örnek

```cpp
// deque_op_gt.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>

int main( )
{
   using namespace std;
   deque <int> c1, c2;

   c1.push_back( 1 );
   c1.push_back( 3 );
   c1.push_back( 1 );

   c2.push_back( 1 );
   c2.push_back( 2 );
   c2.push_back( 2 );

   if ( c1 > c2 )
      cout << "Deque c1 is greater than deque c2." << endl;
   else
      cout << "Deque c1 is not greater than deque c2." << endl;
}
\* Output:
Deque c1 is greater than deque c2.
*\

```

## <a name="op_gt_eq"></a>  işleci&gt;=

Deque işlecinin sol tarafındaki sağ tarafında deque nesnesine eşit veya daha büyük bir nesneyse testleri.

```cpp
bool operator>=(const deque<Type, Allocator>& left, const deque<Type, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

`left` Türünde bir nesne `deque`.

`right` Türünde bir nesne `deque`.

### <a name="return-value"></a>Dönüş Değeri

**doğru** işlecinin sol tarafındaki deque daha büyük veya eşit işlecinin sağ tarafında deque; tersi durumda ise **false**.

### <a name="remarks"></a>Açıklamalar

Deque nesneleri arasındaki karşılaştırma öğelerini pairwise karşılaştırması hakkında temel alır. Büyük veya ona eşit iki nesne arasındaki ilişki için ilk çiftlerini eşit olmayan bir karşılaştırmasını temel alır.

### <a name="example"></a>Örnek

```cpp
// deque_op_ge.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>

int main( )
{
   using namespace std;
   deque <int> c1, c2;

   c1.push_back( 1 );
   c1.push_back( 3 );
   c1.push_back( 1 );

   c2.push_back( 1 );
   c2.push_back( 2 );
   c2.push_back( 2 );

   if ( c1 >= c2 )
      cout << "Deque c1 is greater than or equal to deque c2." << endl;
   else
      cout << "Deque c1 is less than deque c2." << endl;
}
\* Output:
Deque c1 is greater than or equal to deque c2.
*\
```

## <a name="see-also"></a>Ayrıca bkz.

[\<deque >](../standard-library/deque.md)<br/>
