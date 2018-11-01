---
title: '&lt;deque&gt; işleçleri'
ms.date: 11/04/2016
f1_keywords:
- deque/std::operator!=
- deque/std::operator&gt;
- deque/std::operator&gt;=
- deque/std::operator&lt;
- deque/std::operator&lt;=
- deque/std::operator==
ms.assetid: 482d7c92-54c7-493b-99e6-2a73617481a5
helpviewer_keywords:
- std::operator!= (deque)
- std::operator&gt; (deque)
- std::operator&gt;= (deque)
- std::operator&lt; (deque)
- std::operator&lt;= (deque)
- std::operator== (deque)
ms.openlocfilehash: 886edb75e63d34e3bab2dd223d2cdac00f6fd41a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50437377"
---
# <a name="ltdequegt-operators"></a>&lt;deque&gt; işleçleri

||||
|-|-|-|
|[operator!=](#op_neq)|[İşleci&gt;](#op_gt)|[İşleci&gt;=](#op_gt_eq)|
|[İşleci&lt;](#op_lt)|[İşleci&lt;=](#op_lt_eq)|[operator==](#op_eq_eq)|

## <a name="op_neq"></a>  işleç! =

İşlecin sol tarafındaki deque nesne işlecin sağ tarafındaki deque nesneye eşit olup olmadığını sınar.

```cpp
bool operator!=(const deque<Type, Allocator>& left, const deque<Type, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*Sol*<br/>
Bir nesne türü `deque`.

*sağ*<br/>
Bir nesne türü `deque`.

### <a name="return-value"></a>Dönüş Değeri

**doğru** deque nesneleri eşit; değilse, **false** deque nesneler eşit ise.

### <a name="remarks"></a>Açıklamalar

Deque nesneleri arasında karşılaştırma öğeleri üzerinde bir ikili karşılaştırma temel alır. İki deque nesneleri, bunlar aynı sayıda öğe varsa ve ilgili öğeleri aynı değerleri eşit olur. Aksi takdirde, eşit oldukları.

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
/* Output:
The deques are not equal.
*/
```

## <a name="op_lt"></a>  İşleci&lt;

İşlecin sol tarafındaki deque nesnesinin işlecin sağ tarafındaki deque nesneden küçük olup olmadığını sınar.

```cpp
bool operator<(const deque<Type, Allocator>& left, const deque<Type, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*Sol*<br/>
Bir nesne türü `deque`.

*sağ*<br/>
Bir nesne türü `deque`.

### <a name="return-value"></a>Dönüş Değeri

**doğru** işlecinin sol tarafındaki deque daha ve değil işlecin sağ tarafındaki deque eşit Aksi takdirde küçükse **false**.

### <a name="remarks"></a>Açıklamalar

Deque nesneleri arasında karşılaştırma öğeleri üzerinde bir ikili karşılaştırma temel alır. Daha az-iki nesne arasındaki ilişki ilk çifti eşit olmayan öğelerin karşılaştırması üzerinde alan daha.

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
/* Output:
Deque c1 is less than deque c2.
*/
```

## <a name="op_lt_eq"></a>  İşleci&lt;=

Deque işlecinin sol tarafında nesne küçük olup olmadığını sınar deque nesnesine eşit veya işlecin sağ tarafındaki.

```cpp
bool operator<=(const deque<Type, Allocator>& left, const deque<Type, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*Sol*<br/>
Bir nesne türü `deque`.

*sağ*<br/>
Bir nesne türü `deque`.

### <a name="return-value"></a>Dönüş Değeri

**doğru** işlecinin sol tarafındaki deque daha veya işlecin sağ tarafındaki deque eşittir; Aksi takdirde küçükse **false**.

### <a name="remarks"></a>Açıklamalar

Deque nesneleri arasında karşılaştırma öğeleri üzerinde bir ikili karşılaştırma temel alır. İki nesne arasındaki ilişki için daha az veya eşit ilk çifti eşit olmayan öğelerin karşılaştırması üzerinde temel alır.

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
/* Output:
Deque c1 is less than or equal to deque c2.
*/

```

## <a name="op_eq_eq"></a>  işleç ==

İşlecin sol tarafındaki deque nesnesinin işlecin sağ tarafındaki deque nesneye eşit olup olmadığını sınar.

```cpp
bool operator==(const deque<Type, Allocator>& left, const deque<Type, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*Sol*<br/>
Bir nesne türü `deque`.

*sağ*<br/>
Bir nesne türü `deque`.

### <a name="return-value"></a>Dönüş Değeri

**doğru** deque işlecinin sol tarafındaki ise, aksi takdirde işlecin sağ tarafındaki deque eşit **false**.

### <a name="remarks"></a>Açıklamalar

Deque nesneleri arasında karşılaştırma öğeleri üzerinde bir ikili karşılaştırma temel alır. Bunlar aynı sayıda öğe varsa ve ilgili öğeleri aynı değerlere sahip iki deques eşit olur. Aksi takdirde, eşit oldukları.

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
/* Output:
The deques are equal.
The deques are not equal.
*/

```

## <a name="op_gt"></a>  İşleci&gt;

İşlecin sol tarafındaki deque nesnesinin işlecin sağ tarafındaki deque nesneden büyük olup olmadığını sınar.

```cpp
bool operator>(const deque<Type, Allocator>& left, const deque<Type, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*Sol*<br/>
Bir nesne türü `deque`.

*sağ*<br/>
Bir nesne türü `deque`.

### <a name="return-value"></a>Dönüş Değeri

**doğru** işlecinin sol tarafındaki deque ise, aksi takdirde deque işlecin sağ tarafındaki büyük **false**.

### <a name="remarks"></a>Açıklamalar

Deque nesneleri arasında karşılaştırma öğeleri üzerinde bir ikili karşılaştırma temel alır. Büyük-iki nesne arasındaki ilişki ilk çifti eşit olmayan öğelerin karşılaştırması üzerinde alan daha.

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
/* Output:
Deque c1 is greater than deque c2.
*/

```

## <a name="op_gt_eq"></a>  İşleci&gt;=

İşlecin sol tarafındaki deque nesnesinin değerinden büyük veya işlecin sağ tarafındaki deque nesneye eşit olup olmadığını sınar.

```cpp
bool operator>=(const deque<Type, Allocator>& left, const deque<Type, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*Sol*<br/>
Bir nesne türü `deque`.

*sağ*<br/>
Bir nesne türü `deque`.

### <a name="return-value"></a>Dönüş Değeri

**doğru** işlecinin sol tarafındaki deque büyüktür veya eşittir işlecin sağ tarafındaki deque; tersi durumda ise **false**.

### <a name="remarks"></a>Açıklamalar

Deque nesneleri arasında karşılaştırma öğeleri üzerinde bir ikili karşılaştırma temel alır. Büyüktür veya eşittir iki nesne arasındaki ilişki için ilk çifti eşit olmayan öğelerin karşılaştırması üzerinde temel alır.

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
/* Output:
Deque c1 is greater than or equal to deque c2.
*/
```

## <a name="see-also"></a>Ayrıca bkz.

[\<deque >](../standard-library/deque.md)<br/>
