---
description: 'Daha fazla bilgi edinin: &lt; deque &gt; işleçleri'
title: '&lt;deque &gt; işleçleri'
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
ms.openlocfilehash: f162a234aec66982e274755e7898cbbc1c63ab22
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97324567"
---
# <a name="ltdequegt-operators"></a>&lt;deque &gt; işleçleri

## <a name="operator"></a><a name="op_neq"></a> işleç! =

İşlecin sol tarafındaki deque nesnesinin, sağ taraftaki nesnenin deque nesnesine eşit olup olmadığını sınar.

```cpp
bool operator!=(const deque<Type, Allocator>& left, const deque<Type, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*tarafta*\
`deque` türünün bir nesnesi.

*Right*\
`deque` türünün bir nesnesi.

### <a name="return-value"></a>Dönüş Değeri

**`true`** deque nesneleri eşitse; **`false`** Eğer deque nesneleri eşitse.

### <a name="remarks"></a>Açıklamalar

Deque nesneleri arasındaki karşılaştırma, öğelerinin ikili bir karşılaştırmasını temel alır. İki deque nesne, aynı sayıda öğeye sahip olmaları halinde eşittir ve ilgili öğeleri aynı değere sahiptir. Aksi takdirde, bunlar eşit değildir.

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
```

```Output
The deques are not equal.
```

## <a name="operatorlt"></a><a name="op_lt"></a> işlecinde&lt;

İşlecin sol tarafındaki en que nesnenin sağ taraftaki nesneden daha az olup olmadığını sınar.

```cpp
bool operator<(const deque<Type, Allocator>& left, const deque<Type, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*tarafta*\
`deque` türünün bir nesnesi.

*Right*\
`deque` türünün bir nesnesi.

### <a name="return-value"></a>Dönüş Değeri

**`true`** işlecin sol tarafındaki deque işleci, işlecin sağ tarafındaki deque değerinden küçük ve bu değere eşit değilse; Aksi takdirde **`false`** .

### <a name="remarks"></a>Açıklamalar

Deque nesneleri arasındaki karşılaştırma, öğelerinin ikili bir karşılaştırmasını temel alır. İki nesne arasındaki daha az ilişki, eşit olmayan öğelerin ilk çiftinin karşılaştırmasına dayalıdır.

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
```

```Output
Deque c1 is less than deque c2.
```

## <a name="operatorlt"></a><a name="op_lt_eq"></a> işlecinde&lt;=

İşlecin sol tarafındaki deque nesnesinin, sağ taraftaki en que nesneden küçük veya ona eşit olup olmadığını sınar.

```cpp
bool operator<=(const deque<Type, Allocator>& left, const deque<Type, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*tarafta*\
`deque` türünün bir nesnesi.

*Right*\
`deque` türünün bir nesnesi.

### <a name="return-value"></a>Dönüş Değeri

**`true`** işlecin sol tarafındaki deque işleci, işlecin sağ tarafındaki deque değerinden küçükse veya eşitse; Aksi takdirde **`false`** .

### <a name="remarks"></a>Açıklamalar

Deque nesneleri arasındaki karşılaştırma, öğelerinin ikili bir karşılaştırmasını temel alır. İki nesne arasındaki en az veya daha fazla ilişki, eşit olmayan öğelerin ilk çiftinin karşılaştırmasına bağlıdır.

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
```

```Output
Deque c1 is less than or equal to deque c2.
```

## <a name="operator"></a><a name="op_eq_eq"></a> işleç = =

İşlecin sol tarafındaki deque nesnesinin, sağ taraftaki nesnenin deque nesnesine eşit olup olmadığını sınar.

```cpp
bool operator==(const deque<Type, Allocator>& left, const deque<Type, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*tarafta*\
`deque` türünün bir nesnesi.

*Right*\
`deque` türünün bir nesnesi.

### <a name="return-value"></a>Dönüş Değeri

**`true`** işlecin sol tarafındaki deque işleci işlecin sağ tarafındaki dekiye eşitse; Aksi takdirde **`false`** .

### <a name="remarks"></a>Açıklamalar

Deque nesneleri arasındaki karşılaştırma, öğelerinin ikili bir karşılaştırmasını temel alır. İki deques aynı sayıda öğe varsa ve ilgili öğeleri aynı değere sahip olduğunda eşittir. Aksi takdirde, bunlar eşit değildir.

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
```

```Output
The deques are equal.
The deques are not equal.
```

## <a name="operatorgt"></a><a name="op_gt"></a> işlecinde&gt;

İşlecin sol tarafındaki en que nesnenin sağ taraftaki nesneden daha büyük olup olmadığını sınar.

```cpp
bool operator>(const deque<Type, Allocator>& left, const deque<Type, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*tarafta*\
`deque` türünün bir nesnesi.

*Right*\
`deque` türünün bir nesnesi.

### <a name="return-value"></a>Dönüş Değeri

**`true`** işlecin sol tarafındaki deque işleci işlecin sağ tarafındaki değerden büyükse; Aksi takdirde **`false`** .

### <a name="remarks"></a>Açıklamalar

Deque nesneleri arasındaki karşılaştırma, öğelerinin ikili bir karşılaştırmasını temel alır. İki nesne arasındaki büyüktür ilişkisi, eşit olmayan öğelerin ilk çiftinin karşılaştırmasını temel alır.

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
```

```Output
Deque c1 is greater than deque c2.
```

## <a name="operatorgt"></a><a name="op_gt_eq"></a> işlecinde&gt;=

İşlecin sol tarafındaki deque nesnesinin, sağ taraftaki en que nesneden büyük veya ona eşit olup olmadığını sınar.

```cpp
bool operator>=(const deque<Type, Allocator>& left, const deque<Type, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*tarafta*\
`deque` türünün bir nesnesi.

*Right*\
`deque` türünün bir nesnesi.

### <a name="return-value"></a>Dönüş Değeri

**`true`** işlecin sol tarafındaki deque işleci işlecin sağ tarafındaki dekinden büyükse veya eşitse; Aksi takdirde **`false`** .

### <a name="remarks"></a>Açıklamalar

Deque nesneleri arasındaki karşılaştırma, öğelerinin ikili bir karşılaştırmasını temel alır. İki nesne arasındaki en büyük veya daha fazla ilişki, eşit olmayan öğelerin ilk çiftinin karşılaştırmasına bağlıdır.

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
```

```Output
Deque c1 is greater than or equal to deque c2.
```
