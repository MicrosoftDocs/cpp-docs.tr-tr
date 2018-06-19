---
title: '&lt;yığın&gt; işleçleri | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- stack/std::operator!=
- stack/std::operator&gt;
- stack/std::operator&gt;=
- stack/std::operator&lt;
- stack/std::operator&lt;=
- stack/std::operator==
dev_langs:
- C++
ms.assetid: 9c1fc282-2f61-4727-9e80-84ea5d4934a2
helpviewer_keywords:
- std::operator!= (stack)
- std::operator&gt; (stack)
- std::operator&gt;= (stack)
- std::operator&lt; (stack)
- std::operator&lt;= (stack)
- std::operator== (stack)
ms.openlocfilehash: 5d3bafd2d3112a2f4155f55a554b6c9c2e351b1f
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33861652"
---
# <a name="ltstackgt-operators"></a>&lt;yığın&gt; işleçleri

||||
|-|-|-|
|[operator!=](#op_neq)|[işleci&gt;](#op_gt)|[işleci&gt;=](#op_gt_eq)|
|[işleci&lt;](#op_lt)|[işleci&lt;=](#op_lt_eq)|[operator==](#op_eq_eq)|

## <a name="op_neq"></a>  operator! =

Stack nesnesi işlecinin sol tarafındaki yığın eşit değilse testleri sağ tarafta nesne.

```cpp
bool operator!=(const stack <Type, Container>& left, const stack <Type, Container>& right,);
```

### <a name="parameters"></a>Parametreler

`left` Türünde bir nesne **yığını**.

`right` Türünde bir nesne **yığını**.

### <a name="return-value"></a>Dönüş Değeri

**doğru** yığınları veya yığınları eşit; değilse **false** yığınları veya yığınları eşit olması durumunda.

### <a name="remarks"></a>Açıklamalar

Yığınları nesneleri arasındaki karşılaştırma öğelerini pairwise karşılaştırması hakkında temel alır. İki yığınları aynı sayıda öğe varsa ve bunların ilgili öğeleri aynı değerlere eşittir. Aksi takdirde, bunlar eşit.

### <a name="example"></a>Örnek

```cpp
// stack_op_me.cpp
// compile with: /EHsc
#include <stack>
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;

   // Declares stacks with vector base containers
   stack <int, vector<int> > s1, s2, s3;

   // The following would have cause an error because stacks with
   // different base containers are not equality comparable
   // stack <int, list<int> >  s3;

   s1.push( 1 );
   s2.push( 2 );
   s3.push( 1 );

   if ( s1 != s2 )
      cout << "The stacks s1 and s2 are not equal." << endl;
   else
      cout << "The stacks s1 and s2 are equal." << endl;

   if ( s1 != s3 )
      cout << "The stacks s1 and s3 are not equal." << endl;
   else
      cout << "The stacks s1 and s3 are equal." << endl;
}
```

```Output
The stacks s1 and s2 are not equal.
The stacks s1 and s3 are equal.
```

## <a name="op_lt"></a>  işleci&lt;

Stack nesnesi işlecinin sol tarafındaki sağ tarafında stack nesnesi küçükse testleri.

```cpp
bool operator<(const stack <Type, Container>& left, const stack <Type, Container>& right);
```

### <a name="parameters"></a>Parametreler

`left` Türünde bir nesne **yığını**.

`right` Türünde bir nesne **yığını**.

### <a name="return-value"></a>Dönüş Değeri

**doğru** işlecinin sol tarafındaki yığını ve değil işlecinin sağ tarafında yığını eşit; Aksi takdirde düşükse **false**.

### <a name="remarks"></a>Açıklamalar

Stack nesneleri arasındaki karşılaştırma öğelerini pairwise karşılaştırması hakkında temel alır. Küçüktür-iki stack nesneleri arasındaki ilişki ilk çiftlerini eşit olmayan bir karşılaştırmasını dayalı daha.

### <a name="example"></a>Örnek

```cpp
// stack_op_lt.cpp
// compile with: /EHsc
#include <stack>
#include <list>
#include <iostream>

int main( )
{
   using namespace std;

   // Declares stacks with list base container
   stack <int, list<int> > s1, s2, s3;

   s1.push( 2 );
   s1.push( 4 );
   s1.push( 6 );
   s1.push( 8 );
   s2.push( 5 );
   s2.push( 10 );
   s3.push( 2 );
   s3.push( 4 );
   s3.push( 6 );
   s3.push( 8 );

   if ( s1 >= s2 )
      cout << "The stack s1 is greater than or equal to "
           << "the stack s2." << endl;
   else
      cout << "The stack s1 is less than "
           << "the stack s2." << endl;

   if ( s1>= s3 )
      cout << "The stack s1 is greater than or equal to "
           << "the stack s3." << endl;
   else
      cout << "The stack s1 is less than "
           << "the stack s3." << endl;

   // to print out the stack s1 ( by unstacking the elements):
   stack <int>::size_type i_size_s1 = s1.size( );
   cout << "The stack s1 from the top down is: ( ";
   unsigned int i;
   for ( i = 1 ; i <= i_size_s1 ; i++ )
   {
      cout << s1.top( ) << " ";
      s1.pop( );
   }
   cout << ")." << endl;
}
```

```Output
The stack s1 is less than the stack s2.
The stack s1 is greater than or equal to the stack s3.
The stack s1 from the top down is: ( 8 6 4 2 ).
```

## <a name="op_lt_eq"></a>  işleci&lt;=

Yığın işlecinin sol tarafında nesne sağlayıp sağlamadığını test sağ tarafında stack nesnesi eşit veya daha az olur.

```cpp
bool operator<=(const stack <Type, Container>& left, const stack <Type, Container>& right);
```

### <a name="parameters"></a>Parametreler

`left` Türünde bir nesne **yığını**.

`right` Türünde bir nesne **yığını**.

### <a name="return-value"></a>Dönüş Değeri

**doğru** işlecinin sol tarafındaki yığın veya yığın işlecinin sağ tarafında eşit; Aksi takdirde düşükse **false**.

### <a name="remarks"></a>Açıklamalar

Stack nesneleri arasındaki karşılaştırma öğelerini pairwise karşılaştırması hakkında temel alır. İki yığını nesneler arasındaki küçük veya eşittir ilişkiye ilk çiftlerini eşit olmayan bir karşılaştırmasını temel alır.

### <a name="example"></a>Örnek

```cpp
// stack_op_le.cpp
// compile with: /EHsc
#include <stack>
#include <iostream>

int main( )
{
   using namespace std;

   // Declares stacks with default deque base container
   stack <int> s1, s2, s3;

   s1.push( 5 );
   s1.push( 10 );
   s2.push( 1 );
   s2.push( 2 );
   s3.push( 5 );
   s3.push( 10 );

   if ( s1 <= s2 )
      cout << "The stack s1 is less than or equal to "
           << "the stack s2." << endl;
   else
      cout << "The stack s1 is greater than "
           << "the stack s2." << endl;

   if ( s1 <= s3 )
      cout << "The stack s1 is less than or equal to "
           << "the stack s3." << endl;
   else
      cout << "The stack s1 is greater than "
           << "the stack s3." << endl;
}
```

```Output
The stack s1 is greater than the stack s2.
The stack s1 is less than or equal to the stack s3.
```

## <a name="op_eq_eq"></a>  operator ==

Stack nesnesi işlecinin sol tarafındaki yığın eşitse testleri sağ tarafta nesne.

```cpp
bool operator==(const stack <Type, Container>& left, const stack <Type, Container>& right);
```

### <a name="parameters"></a>Parametreler

`left` Türünde bir nesne **yığını**.

`right` Türünde bir nesne **yığını**.

### <a name="return-value"></a>Dönüş Değeri

**doğru** yığınları veya yığınları; eşitse **false** yığınları veya yığınları eşit değilse.

### <a name="remarks"></a>Açıklamalar

Stack nesneleri arasındaki karşılaştırma öğelerini pairwise karşılaştırması hakkında temel alır. İki yığınları aynı sayıda öğe varsa ve bunların ilgili öğeleri aynı değerlere eşittir. Aksi takdirde, bunlar eşit.

### <a name="example"></a>Örnek

```cpp
// stack_op_eq.cpp
// compile with: /EHsc
#include <stack>
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;

   // Declares stacks with vector base containers
   stack <int, vector<int> > s1, s2, s3;

   // The following would have cause an error because stacks with
   // different base containers are not equality comparable
   // stack <int, list<int> > s3;

   s1.push( 1 );
   s2.push( 2 );
   s3.push( 1 );

   if ( s1 == s2 )
      cout << "The stacks s1 and s2 are equal." << endl;
   else
      cout << "The stacks s1 and s2 are not equal." << endl;

   if ( s1 == s3 )
      cout << "The stacks s1 and s3 are equal." << endl;
   else
      cout << "The stacks s1 and s3 are not equal." << endl;
}
```

```Output
The stacks s1 and s2 are not equal.
The stacks s1 and s3 are equal.
```

## <a name="op_gt"></a>  işleci&gt;

Testleri işlecinin sol tarafındaki stack nesnesi sağ tarafında stack nesnesi değerinden daha büyük.

```cpp
bool operator>(const stack <Type, Container>& left, const stack <Type, Container>& right);
```

### <a name="parameters"></a>Parametreler

`left` Türünde bir nesne **yığını**.

`right` Türünde bir nesne **yığını**.

### <a name="return-value"></a>Dönüş Değeri

**doğru** işlecinin sol tarafındaki yığını eşitse büyük ve değil işlecinin sağ tarafında yığınına aksi **false**.

### <a name="remarks"></a>Açıklamalar

Stack nesneleri arasındaki karşılaştırma öğelerini pairwise karşılaştırması hakkında temel alır. Büyük-iki stack nesneleri arasındaki ilişki ilk çiftlerini eşit olmayan bir karşılaştırmasını dayalı daha.

### <a name="example"></a>Örnek

```cpp
// stack_op_gt.cpp
// compile with: /EHsc
#include <stack>
#include <list>
#include <iostream>

int main( )
{
   using namespace std;

   // Declares stacks with list base container
   stack <int, list<int> > s1, s2, s3;

   s1.push( 1 );
   s1.push( 2 );
   s1.push( 3 );
   s2.push( 5 );
   s2.push( 10 );
   s3.push( 1 );
   s3.push( 2 );

   if ( s1 > s2 )
      cout << "The stack s1 is greater than "
           << "the stack s2." << endl;
   else
      cout << "The stack s1 is not greater than "
           << "the stack s2." << endl;

   if ( s1> s3 )
      cout << "The stack s1 is greater than "
           << "the stack s3." << endl;
   else
      cout << "The stack s1 is not greater than "
           << "the stack s3." << endl;
}
```

```Output
The stack s1 is not greater than the stack s2.
The stack s1 is greater than the stack s3.
```

## <a name="op_gt_eq"></a>  işleci&gt;=

Yığın işlecinin sol tarafındaki sağ tarafında yığını nesnesine eşit veya daha büyük bir nesneyse testleri.

```cpp
bool operator>=(const stack <Type, Container>& left, const stack <Type, Container>& right);
```

### <a name="parameters"></a>Parametreler

`left` Türünde bir nesne **yığını**.

`right` Türünde bir nesne **yığını**.

### <a name="return-value"></a>Dönüş Değeri

**doğru** işlecinin sol tarafındaki yığın; işlecinin sağ tarafında yığını kesinlikle değerinden ise, aksi takdirde **false**.

### <a name="remarks"></a>Açıklamalar

Stack nesneleri arasındaki karşılaştırma öğelerini pairwise karşılaştırması hakkında temel alır. Büyük veya ona eşit iki stack nesneleri arasındaki ilişki için ilk çiftlerini eşit olmayan bir karşılaştırmasını temel alır.

### <a name="example"></a>Örnek

```cpp
// stack_op_ge.cpp
// compile with: /EHsc
#include <stack>
#include <list>
#include <iostream>

int main( )
{
   using namespace std;

   // Declares stacks with list base container
   stack <int, list<int> > s1, s2, s3;

   s1.push( 1 );
   s1.push( 2 );
   s2.push( 5 );
   s2.push( 10 );
   s3.push( 1 );
   s3.push( 2 );

   if ( s1 >= s2 )
      cout << "The stack s1 is greater than or equal to "
           << "the stack s2." << endl;
   else
      cout << "The stack s1 is less than "
           << "the stack s2." << endl;

   if ( s1>= s3 )
      cout << "The stack s1 is greater than or equal to "
           << "the stack s3." << endl;
   else
      cout << "The stack s1 is less than "
           << "the stack s3." << endl;
}
```

```Output
The stack s1 is less than the stack s2.
The stack s1 is greater than or equal to the stack s3.
```

## <a name="see-also"></a>Ayrıca bkz.

[\<yığın >](../standard-library/stack.md)<br/>
