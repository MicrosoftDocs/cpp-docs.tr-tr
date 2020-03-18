---
title: '&lt;kuyruğu&gt; işleçleri'
ms.date: 11/04/2016
f1_keywords:
- queue/std::operator!=
- queue/std::operator&gt;
- queue/std::operator&gt;=
- queue/std::operator&lt;
- queue/std::operator&lt;=
- queue/std::operator==
ms.assetid: 7c435b48-175c-45b0-88eb-24561044019c
helpviewer_keywords:
- std::operator!= (queue)
- std::operator&gt; (queue)
- std::operator&gt;= (queue)
- std::operator&lt; (queue)
- std::operator&lt;= (queue)
- std::operator== (queue)
ms.openlocfilehash: 420d717b34b6c17587f8790701906e06ab008d96
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/16/2020
ms.locfileid: "79419653"
---
# <a name="ltqueuegt-operators"></a>&lt;kuyruğu&gt; işleçleri

## <a name="op_neq"></a>işleç! =

İşlecin sol tarafındaki kuyruk nesnesinin, sağ taraftaki kuyruk nesnesine eşit olup olmadığını sınar.

```cpp
bool operator!=(const queue <Type, Container>& left, const queue <Type, Container>& right,);
```

### <a name="parameters"></a>Parametreler

*sol*\
`queue` türünün bir nesnesi.

*sağ*\
`queue` türünün bir nesnesi.

### <a name="return-value"></a>Dönüş Değeri

Kuyruklar eşit değilse **doğru** ; Kuyruklar eşitse **false** .

### <a name="remarks"></a>Açıklamalar

Kuyruk nesneleri arasındaki karşılaştırma, öğelerinin ikili bir karşılaştırmasını temel alır. İki kuyruk aynı sayıda öğe varsa ve ilgili öğeleri aynı değere sahip olduğunda eşittir. Aksi takdirde, bunlar eşit değildir.

### <a name="example"></a>Örnek

```cpp
// queue_op_ne.cpp
// compile with: /EHsc
#include <queue>
#include <list>
#include <iostream>

int main( )
{
   using namespace std;

   // Declares queues with list base containers
   queue <int, list<int> > q1, q2, q3;

   // The following line would have caused an error because vector
   // does not support pop_front( ) and so cannot be adapted
   // by queue as a base container
   // queue <int, vector<int> > q1, q2, q3;

   q1.push( 1 );
   q2.push( 1 );
   q2.push( 2 );
   q3.push( 1 );

   if ( q1 != q2 )
      cout << "The queues q1 and q2 are not equal." << endl;
   else
      cout << "The queues q1 and q2 are equal." << endl;

   if ( q1 != q3 )
      cout << "The queues q1 and q3 are not equal." << endl;
   else
      cout << "The queues q1 and q3 are equal." << endl;
}
```

```Output
The queues q1 and q2 are not equal.
The queues q1 and q3 are equal.
```

## <a name="op_lt"></a>işleç&lt;

İşlecin sol tarafındaki kuyruk nesnesinin, sağ taraftaki sıra nesnesinden küçük olup olmadığını sınar.

```cpp
bool operator<(const queue <Type, Container>& left, const queue <Type, Container>& right,);
```

### <a name="parameters"></a>Parametreler

*sol*\
`queue` türünün bir nesnesi.

*sağ*\
`queue` türünün bir nesnesi.

### <a name="return-value"></a>Dönüş Değeri

işlecin sol tarafındaki sıra, işlecin sağ tarafındaki sıraya eşit veya daha küçükse **true** ; Aksi halde **yanlış**.

### <a name="remarks"></a>Açıklamalar

Kuyruk nesneleri arasındaki karşılaştırma, öğelerinin ikili bir karşılaştırmasını temel alır. İki kuyruk nesnesi arasındaki daha az ilişki, eşit olmayan öğelerin ilk çiftinin karşılaştırmasını temel alır.

### <a name="example"></a>Örnek

```cpp
// queue_op_lt.cpp
// compile with: /EHsc
#include <queue>
#include <iostream>

int main( )
{
   using namespace std;

   // Declares queues with default deque base container
   queue <int> q1, q2, q3;

   q1.push( 1 );
   q1.push( 2 );
   q2.push( 5 );
   q2.push( 10 );
   q3.push( 1 );
   q3.push( 2 );

   if ( q1 < q2 )
      cout << "The queue q1 is less than the queue q2." << endl;
   else
      cout << "The queue q1 is not less than the queue q2." << endl;

   if ( q1 < q3 )
      cout << "The queue q1 is less than the queue q3." << endl;
   else
      cout << "The queue q1 is not less than the queue q3." << endl;
}
```

```Output
The queue q1 is less than the queue q2.
The queue q1 is not less than the queue q3.
```

## <a name="op_lt_eq"></a>işleç&lt;=

İşlecin sol tarafındaki kuyruk nesnesinin, sağ taraftaki kuyruk nesnesinden küçük veya ona eşit olup olmadığını sınar.

```cpp
bool operator<=(const queue <Type, Container>& left, const queue <Type, Container>& right,);
```

### <a name="parameters"></a>Parametreler

*sol*\
`queue` türünün bir nesnesi.

*sağ*\
`queue` türünün bir nesnesi.

### <a name="return-value"></a>Dönüş Değeri

işlecin sol tarafındaki sıra işlecin sağ tarafındaki kuyruktan tamamen daha küçükse **true** ; Aksi halde **yanlış**.

### <a name="remarks"></a>Açıklamalar

Kuyruk nesneleri arasındaki karşılaştırma, öğelerinin ikili bir karşılaştırmasını temel alır. İki kuyruk nesnesi arasındaki en az veya daha fazla ilişki, eşit olmayan öğelerin ilk çiftinin karşılaştırmasına bağlıdır.

### <a name="example"></a>Örnek

```cpp
// queue_op_le.cpp
// compile with: /EHsc
#include <queue>
#include <iostream>

int main( )
{
   using namespace std;
   queue <int> q1, q2, q3;

   q1.push( 5 );
   q1.push( 10 );
   q2.push( 1 );
   q2.push( 2 );
   q3.push( 5 );
   q3.push( 10 );

   if ( q1 <= q2 )
      cout << "The queue q1 is less than or equal to "
           << "the queue q2." << endl;
   else
      cout << "The queue q1 is greater than "
           << "the queue q2." << endl;

   if ( q1 <= q3 )
      cout << "The queue q1 is less than or equal to "
           << "the queue q3." << endl;
   else
      cout << "The queue q1 is greater than "
           << "the queue q3." << endl;
}
```

```Output
The queue q1 is greater than the queue q2.
The queue q1 is less than or equal to the queue q3.
```

## <a name="op_eq_eq"></a>işleç = =

İşlecin sol tarafındaki kuyruk nesnesinin, sağ taraftaki kuyruk nesnesine eşit olup olmadığını sınar.

```cpp
bool operator==(const queue <Type, Container>& left, const queue <Type, Container>& right,);
```

### <a name="parameters"></a>Parametreler

*sol*\
`queue` türünün bir nesnesi.

*sağ*\
`queue` türünün bir nesnesi.

### <a name="return-value"></a>Dönüş Değeri

Kuyruklar eşit değilse **doğru** ; Kuyruklar eşitse **false** .

### <a name="remarks"></a>Açıklamalar

Kuyruk nesneleri arasındaki karşılaştırma, öğelerinin ikili bir karşılaştırmasını temel alır. İki kuyruk aynı sayıda öğe varsa ve ilgili öğeleri aynı değere sahip olduğunda eşittir. Aksi takdirde, bunlar eşit değildir.

### <a name="example"></a>Örnek

```cpp
// queue_op_eq.cpp
// compile with: /EHsc
#include <queue>
#include <list>
#include <iostream>

int main( )
{
   using namespace std;

   // Declares queues with list base containers
   queue <int, list<int> > q1, q2, q3;

   // The following line would have caused an error because vector
   // does not support pop_front( ) and so cannot be adapted
   // by queue as a base container
   // queue <int, vector<int> > q1, q2, q3;

   q1.push( 1 );
   q2.push( 2 );
   q3.push( 1 );

   if ( q1 != q2 )
      cout << "The queues q1 and q2 are not equal." << endl;
   else
      cout << "The queues q1 and q2 are equal." << endl;

   if ( q1 != q3 )
      cout << "The queues q1 and q3 are not equal." << endl;
   else
      cout << "The queues q1 and q3 are equal." << endl;
}
```

```Output
The queues q1 and q2 are not equal.
The queues q1 and q3 are equal.
```

## <a name="op_gt"></a>işleç&gt;

İşlecin sol tarafındaki kuyruk nesnesinin, sağ taraftaki sıra nesnesinden büyük olup olmadığını sınar.

```cpp
bool operator>(const queue <Type, Container>& left, const queue <Type, Container>& right,);
```

### <a name="parameters"></a>Parametreler

*sol*\
`queue` türünün bir nesnesi.

*sağ*\
`queue` türünün bir nesnesi.

### <a name="return-value"></a>Dönüş Değeri

işlecin sol tarafındaki sıra işlecin sağ tarafındaki kuyruktan tamamen daha küçükse **true** ; Aksi halde **yanlış**.

### <a name="remarks"></a>Açıklamalar

Kuyruk nesneleri arasındaki karşılaştırma, öğelerinin ikili bir karşılaştırmasını temel alır. İki kuyruk nesnesi arasındaki büyüktür ilişkisi, eşit olmayan öğelerin ilk çiftinin karşılaştırmasını temel alır.

### <a name="example"></a>Örnek

```cpp
// queue_op_gt.cpp
// compile with: /EHsc
#include <queue>
#include <iostream>

int main( )
{
   using namespace std;
   queue <int> q1, q2, q3;

   q1.push( 1 );
   q1.push( 2 );
   q1.push( 3 );
   q2.push( 5 );
   q2.push( 10 );
   q3.push( 1 );
   q3.push( 2 );

   if ( q1 > q2 )
      cout << "The queue q1 is greater than "
           << "the queue q2." << endl;
   else
      cout << "The queue q1 is not greater than "
           << "the queue q2." << endl;

   if ( q1> q3 )
      cout << "The queue q1 is greater than "
           << "the queue q3." << endl;
   else
      cout << "The queue q1 is not greater than "
           << "the queue q3." << endl;
}
```

```Output
The queue q1 is not greater than the queue q2.
The queue q1 is greater than the queue q3.
```

## <a name="op_gt_eq"></a>işleç&gt;=

İşlecin sol tarafındaki kuyruk nesnesinin, sağ taraftaki sıra nesnesinden büyük veya ona eşit olup olmadığını sınar.

```cpp
bool operator>=(const queue <Type, Container>& left, const queue <Type, Container>& right,);
```

### <a name="parameters"></a>Parametreler

*sol*\
`queue` türünün bir nesnesi.

*sağ*\
`queue` türünün bir nesnesi.

### <a name="return-value"></a>Dönüş Değeri

işlecin sol tarafındaki sıra işlecin sağ tarafındaki kuyruktan tamamen daha küçükse **true** ; Aksi halde **yanlış**.

### <a name="remarks"></a>Açıklamalar

Kuyruk nesneleri arasındaki karşılaştırma, öğelerinin ikili bir karşılaştırmasını temel alır. İki kuyruk aynı sayıda öğe varsa ve ilgili öğeleri aynı değere sahip olduğunda eşittir. Aksi takdirde, bunlar eşit değildir.

### <a name="example"></a>Örnek

```cpp
// queue_op_ge.cpp
// compile with: /EHsc
#include <queue>
#include <iostream>

int main( )
{
   using namespace std;
   queue <int> q1, q2, q3;

   q1.push( 1 );
   q1.push( 2 );
   q2.push( 5 );
   q2.push( 10 );
   q3.push( 1 );
   q3.push( 2 );

   if ( q1 >= q2 )
      cout << "The queue q1 is greater than or equal to "
           << "the queue q2." << endl;
   else
      cout << "The queue q1 is less than "
           << "the queue q2." << endl;

   if ( q1>= q3 )
      cout << "The queue q1 is greater than or equal to "
           << "the queue q3." << endl;
   else
      cout << "The queue q1 is less than "
           << "the queue q3." << endl;
}
```

```Output
The queue q1 is less than the queue q2.
The queue q1 is greater than or equal to the queue q3.
```
