---
title: '&lt;liste &gt; işleçleri'
ms.date: 11/04/2016
f1_keywords:
- list/std::operator!=
- list/std::operator&gt;
- list/std::operator&gt;=
- list/std::operator&lt;
- list/std::operator&lt;=
- list/std::operator==
ms.assetid: 8103d8f2-c30f-49ad-ac50-b3ba6a907ebe
helpviewer_keywords:
- std::operator!= (list)
- std::operator&gt; (list)
- std::operator&gt;= (list)
- std::operator&lt; (list)
- std::operator&lt;= (list)
- std::operator== (list)
ms.openlocfilehash: 8648258f17bff577ba1c0dde5016f5f284b82e25
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87224844"
---
# <a name="ltlistgt-operators"></a>&lt;liste &gt; işleçleri

## <a name="operator"></a><a name="op_neq"></a>işleç! =

İşlecin sol tarafındaki list nesnesinin sağ taraftaki liste nesnesine eşit olup olmadığını sınar.

```cpp
bool operator!=(
    const list<Type, Allocator>& left,
    const list<Type, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*tarafta*\
`list` türünün bir nesnesi.

*Right*\
`list` türünün bir nesnesi.

### <a name="return-value"></a>Dönüş Değeri

**`true`** listeler eşitse; **`false`** listeler eşitse.

### <a name="remarks"></a>Açıklamalar

Liste nesneleri arasındaki karşılaştırma, öğelerinin ikili bir karşılaştırmasını temel alır. İki liste aynı sayıda öğeye sahip olmaları ve ilgili öğeleri aynı değere sahip olduğunda eşittir. Aksi takdirde, bunlar eşit değildir.

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
/* Output:
Lists not equal.
*/
```

## <a name="operatorlt"></a><a name="op_lt"></a>işlecinde&lt;

İşlecin sol tarafındaki liste nesnesinin sağ taraftaki liste nesnesinden küçük olup olmadığını sınar.

```cpp
bool operator<(
    const list<Type, Allocator>& left,
    const list<Type, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*tarafta*\
`list` türünün bir nesnesi.

*Right*\
`list` türünün bir nesnesi.

### <a name="return-value"></a>Dönüş Değeri

**`true`** işlecin sol tarafındaki liste, işlecin sağ tarafındaki listeye eşit ancak ondan küçükse; Aksi takdirde **`false`** .

### <a name="remarks"></a>Açıklamalar

Liste nesneleri arasındaki karşılaştırma, öğelerinin ikili bir karşılaştırmasını temel alır. İki nesne arasındaki daha az ilişki, eşit olmayan öğelerin ilk çiftinin karşılaştırmasına dayalıdır.

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
/* Output:
List c1 is less than list c2.
*/
```

## <a name="operatorlt"></a><a name="op_lt_eq"></a>işlecinde&lt;=

İşlecin sol tarafındaki liste nesnesinin sağ taraftaki liste nesnesinden küçük veya ona eşit olup olmadığını sınar.

```cpp
bool operator<=(
    const list<Type, Allocator>& left,
    const list<Type, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*tarafta*\
`list` türünün bir nesnesi.

*Right*\
`list` türünün bir nesnesi.

### <a name="return-value"></a>Dönüş Değeri

**`true`** işlecin sol tarafındaki liste işlecin sağ tarafındaki listeden daha küçükse veya eşitse, Aksi takdirde **`false`** .

### <a name="remarks"></a>Açıklamalar

Liste nesneleri arasındaki karşılaştırma, öğelerinin ikili bir karşılaştırmasını temel alır. İki nesne arasındaki en az veya daha fazla ilişki, eşit olmayan öğelerin ilk çiftinin karşılaştırmasına bağlıdır.

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
/* Output:
List c1 is less than or equal to list c2.
*/
```

## <a name="operator"></a><a name="op_eq_eq"></a>işleç = =

İşlecin sol tarafındaki list nesnesinin sağ taraftaki liste nesnesine eşit olup olmadığını sınar.

```cpp
bool operator==(
    const list<Type, Allocator>& left,
    const list<Type, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*tarafta*\
`list` türünün bir nesnesi.

*Right*\
`list` türünün bir nesnesi.

### <a name="return-value"></a>Dönüş Değeri

**`true`** işlecin sol tarafındaki liste, işlecin sağ tarafındaki listeye eşitse; Aksi takdirde **`false`** .

### <a name="remarks"></a>Açıklamalar

Liste nesneleri arasındaki karşılaştırma, öğelerinin ikili bir karşılaştırmasını temel alır. İki liste aynı sayıda öğeye sahip olmaları ve ilgili öğeleri aynı değere sahip olduğunda eşittir. Aksi takdirde, bunlar eşit değildir.

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
/* Output:
The lists are equal.
*/
```

## <a name="operatorgt"></a><a name="op_gt"></a>işlecinde&gt;

İşlecin sol tarafındaki list nesnesinin sağ taraftaki liste nesnesinden büyük olup olmadığını sınar.

```cpp
bool operator>(
    const list<Type, Allocator>& left,
    const list<Type, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*tarafta*\
`list` türünün bir nesnesi.

*Right*\
`list` türünün bir nesnesi.

### <a name="return-value"></a>Dönüş Değeri

**`true`** işlecin sol tarafındaki liste, işlecin sağ tarafındaki listeden büyükse; Aksi takdirde **`false`** .

### <a name="remarks"></a>Açıklamalar

Liste nesneleri arasındaki karşılaştırma, öğelerinin ikili bir karşılaştırmasını temel alır. İki nesne arasındaki büyüktür ilişkisi, eşit olmayan öğelerin ilk çiftinin karşılaştırmasını temel alır.

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
/* Output:
List c1 is greater than list c2.
*/
```

## <a name="operatorgt"></a><a name="op_gt_eq"></a>işlecinde&gt;=

İşlecin sol tarafındaki liste nesnesinin sağ taraftaki liste nesnesinden büyük veya ona eşit olup olmadığını sınar.

```cpp
bool operator>=(
    const list<Type, Allocator>& left,
    const list<Type, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*tarafta*\
`list` türünün bir nesnesi.

*Right*\
`list` türünün bir nesnesi.

### <a name="return-value"></a>Dönüş Değeri

**`true`** işlecin sol tarafındaki liste işlecin sağ tarafındaki listeden büyükse veya buna eşitse; Aksi takdirde **`false`** .

### <a name="remarks"></a>Açıklamalar

Liste nesneleri arasındaki karşılaştırma, öğelerinin ikili bir karşılaştırmasını temel alır. İki nesne arasındaki en büyük veya daha fazla ilişki, eşit olmayan öğelerin ilk çiftinin karşılaştırmasına bağlıdır.

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
/* Output:
List c1 is greater than or equal to list c2.
*/
```
