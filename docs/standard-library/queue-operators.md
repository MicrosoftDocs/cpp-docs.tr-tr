---
title: '&lt;Kuyruk&gt; işleçleri'
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
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68240283"
---
# <a name="ltqueuegt-operators"></a>&lt;Kuyruk&gt; işleçleri

## <a name="op_neq"></a> işleç! =

Sıra nesnesinin işlecin sol tarafındaki sıra nesnesinin işlecin sağ tarafındaki eşit olup olmadığını sınar.

```cpp
bool operator!=(const queue <Type, Container>& left, const queue <Type, Container>& right,);
```

### <a name="parameters"></a>Parametreler

*Sol*\
Bir nesne türü `queue`.

*sağ*\
Bir nesne türü `queue`.

### <a name="return-value"></a>Dönüş Değeri

**doğru** kuyrukları eşit; değilse, **false** kuyrukları eşitse.

### <a name="remarks"></a>Açıklamalar

Queue nesneleri arasında karşılaştırma öğeleri üzerinde bir ikili karşılaştırma temel alır. İki kuyrukları, bunlar aynı sayıda öğe varsa ve ilgili öğeleri aynı değerleri eşit olur. Aksi takdirde, eşit oldukları.

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

## <a name="op_lt"></a> İşleci&lt;

Sıra nesnesinin işlecin sol tarafındaki sıra nesnesinin işlecin sağ tarafındaki küçüktür olup olmadığını sınar.

```cpp
bool operator<(const queue <Type, Container>& left, const queue <Type, Container>& right,);
```

### <a name="parameters"></a>Parametreler

*Sol*\
Bir nesne türü `queue`.

*sağ*\
Bir nesne türü `queue`.

### <a name="return-value"></a>Dönüş Değeri

**doğru** sıranın işlecinin sol tarafındaki daha ve değil sıranın işlecin sağ tarafındaki eşit Aksi takdirde küçükse **false**.

### <a name="remarks"></a>Açıklamalar

Queue nesneleri arasında karşılaştırma öğeleri üzerinde bir ikili karşılaştırma temel alır. Daha az-iki queue nesneleri arasındaki ilişki ilk çifti eşit olmayan öğelerin karşılaştırması üzerinde alan daha.

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

## <a name="op_lt_eq"></a> İşleci&lt;=

Sıranın işlecinin sol tarafında nesne olup olmadığını test eder küçüktür veya eşittir sıra nesnesinin işlecin sağ tarafındaki.

```cpp
bool operator<=(const queue <Type, Container>& left, const queue <Type, Container>& right,);
```

### <a name="parameters"></a>Parametreler

*Sol*\
Bir nesne türü `queue`.

*sağ*\
Bir nesne türü `queue`.

### <a name="return-value"></a>Dönüş Değeri

**doğru** sıranın işlecinin sol tarafındaki sıranın; işlecin sağ tarafındaki değerinden kesinlikle küçük ise, aksi takdirde **false**.

### <a name="remarks"></a>Açıklamalar

Queue nesneleri arasında karşılaştırma öğeleri üzerinde bir ikili karşılaştırma temel alır. İki queue nesneleri arasındaki ilişki için daha az veya eşit ilk çifti eşit olmayan öğelerin karşılaştırması üzerinde temel alır.

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

## <a name="op_eq_eq"></a> işleç ==

İşlecin sol tarafındaki sıra nesnesinin işlecin sağ tarafındaki sıra nesnesinin eşit olup olmadığını sınar.

```cpp
bool operator==(const queue <Type, Container>& left, const queue <Type, Container>& right,);
```

### <a name="parameters"></a>Parametreler

*Sol*\
Bir nesne türü `queue`.

*sağ*\
Bir nesne türü `queue`.

### <a name="return-value"></a>Dönüş Değeri

**doğru** kuyrukları eşit; değilse, **false** kuyrukları eşitse.

### <a name="remarks"></a>Açıklamalar

Queue nesneleri arasında karşılaştırma öğeleri üzerinde bir ikili karşılaştırma temel alır. İki kuyrukları, bunlar aynı sayıda öğe varsa ve ilgili öğeleri aynı değerleri eşit olur. Aksi takdirde, eşit oldukları.

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

## <a name="op_gt"></a> İşleci&gt;

Sıra nesnesinin işlecin sol tarafındaki sıra nesnesinin işlecin sağ tarafındaki büyük olup olmadığını sınar.

```cpp
bool operator>(const queue <Type, Container>& left, const queue <Type, Container>& right,);
```

### <a name="parameters"></a>Parametreler

*Sol*\
Bir nesne türü `queue`.

*sağ*\
Bir nesne türü `queue`.

### <a name="return-value"></a>Dönüş Değeri

**doğru** sıranın işlecinin sol tarafındaki sıranın; işlecin sağ tarafındaki değerinden kesinlikle küçük ise, aksi takdirde **false**.

### <a name="remarks"></a>Açıklamalar

Queue nesneleri arasında karşılaştırma öğeleri üzerinde bir ikili karşılaştırma temel alır. Büyük-iki queue nesneleri arasındaki ilişki ilk çifti eşit olmayan öğelerin karşılaştırması üzerinde alan daha.

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

## <a name="op_gt_eq"></a> İşleci&gt;=

İşlecin sol tarafındaki sıra nesnesinin değerinden büyük veya eşittir sıra nesnesinin işlecin sağ tarafındaki olup olmadığını sınar.

```cpp
bool operator>=(const queue <Type, Container>& left, const queue <Type, Container>& right,);
```

### <a name="parameters"></a>Parametreler

*Sol*\
Bir nesne türü `queue`.

*sağ*\
Bir nesne türü `queue`.

### <a name="return-value"></a>Dönüş Değeri

**doğru** sıranın işlecinin sol tarafındaki sıranın; işlecin sağ tarafındaki değerinden kesinlikle küçük ise, aksi takdirde **false**.

### <a name="remarks"></a>Açıklamalar

Queue nesneleri arasında karşılaştırma öğeleri üzerinde bir ikili karşılaştırma temel alır. İki kuyrukları, bunlar aynı sayıda öğe varsa ve ilgili öğeleri aynı değerleri eşit olur. Aksi takdirde, eşit oldukları.

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
