---
title: '&lt;yığın&gt; işleçleri'
ms.date: 11/04/2016
f1_keywords:
- stack/std::operator!=
- stack/std::operator&gt;
- stack/std::operator&gt;=
- stack/std::operator&lt;
- stack/std::operator&lt;=
- stack/std::operator==
ms.assetid: 9c1fc282-2f61-4727-9e80-84ea5d4934a2
helpviewer_keywords:
- std::operator!= (stack)
- std::operator&gt; (stack)
- std::operator&gt;= (stack)
- std::operator&lt; (stack)
- std::operator&lt;= (stack)
- std::operator== (stack)
ms.openlocfilehash: 169698d30edd4a7995cb05e1909c1ffc38b0b6ef
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68243649"
---
# <a name="ltstackgt-operators"></a>&lt;yığın&gt; işleçleri

## <a name="op_neq"></a> işleç! =

İşlecin sol tarafındaki yığın nesnesi yığın eşit olup olmadığını sınar sağ tarafta nesne.

```cpp
bool operator!=(const stack <Type, Container>& left, const stack <Type, Container>& right,);
```

### <a name="parameters"></a>Parametreler

*Sol*\
Bir nesne türü `stack`.

*sağ*\
Bir nesne türü `stack`.

### <a name="return-value"></a>Dönüş Değeri

**doğru** yığını veya yığınları eşit; değilse, **false** yığını veya yığınları eşitse.

### <a name="remarks"></a>Açıklamalar

Yığın nesneleri arasında karşılaştırma öğeleri üzerinde bir ikili karşılaştırma temel alır. Bunlar aynı sayıda öğe varsa ve ilgili öğeleri aynı değerlere sahip iki yığınları eşit olur. Aksi takdirde, eşit oldukları.

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

## <a name="op_lt"></a> İşleci&lt;

İşlecin sol tarafındaki yığın nesnesinin yığın nesnesinin işlecin sağ tarafındaki küçüktür olup olmadığını sınar.

```cpp
bool operator<(const stack <Type, Container>& left, const stack <Type, Container>& right);
```

### <a name="parameters"></a>Parametreler

*Sol*\
Bir nesne türü `stack`.

*sağ*\
Bir nesne türü `stack`.

### <a name="return-value"></a>Dönüş Değeri

**doğru** işlecin sol tarafındaki yığında daha ve değil işlecin sağ tarafındaki yığında eşittir; Aksi takdirde küçükse **false**.

### <a name="remarks"></a>Açıklamalar

Stack nesneleri arasında karşılaştırma öğeleri üzerinde bir ikili karşılaştırma temel alır. Daha az-iki yığın nesneleri arasındaki ilişki ilk çifti eşit olmayan öğelerin karşılaştırması üzerinde alan daha.

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

## <a name="op_lt_eq"></a> İşleci&lt;=

İşlecinin sol tarafında yığın nesnesi küçük olup olmadığını sınar veya yığın nesneye eşitse işlecin sağ tarafındaki.

```cpp
bool operator<=(const stack <Type, Container>& left, const stack <Type, Container>& right);
```

### <a name="parameters"></a>Parametreler

*Sol*\
Bir nesne türü `stack`.

*sağ*\
Bir nesne türü `stack`.

### <a name="return-value"></a>Dönüş Değeri

**doğru** işlecin sol tarafındaki yığında daha veya işlecin sağ tarafındaki yığında eşittir; Aksi takdirde küçükse **false**.

### <a name="remarks"></a>Açıklamalar

Stack nesneleri arasında karşılaştırma öğeleri üzerinde bir ikili karşılaştırma temel alır. Küçük veya eşittir ilişki için iki yığın nesneleri arasında eşit olmayan öğelerin ilk çiftinin bir karşılaştırmayı temel alır.

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

## <a name="op_eq_eq"></a> işleç ==

İşlecin sol tarafındaki yığın nesnesinin yığın nesnesinin işlecin sağ tarafındaki eşit olup olmadığını sınar.

```cpp
bool operator==(const stack <Type, Container>& left, const stack <Type, Container>& right);
```

### <a name="parameters"></a>Parametreler

*Sol*\
Bir nesne türü `stack`.

*sağ*\
Bir nesne türü `stack`.

### <a name="return-value"></a>Dönüş Değeri

**doğru** yığını veya yığınları; eşitse **false** yığını veya yığınları eşit değilse.

### <a name="remarks"></a>Açıklamalar

Stack nesneleri arasında karşılaştırma öğeleri üzerinde bir ikili karşılaştırma temel alır. Bunlar aynı sayıda öğe varsa ve ilgili öğeleri aynı değerlere sahip iki yığınları eşit olur. Aksi takdirde, eşit oldukları.

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

## <a name="op_gt"></a> İşleci&gt;

İşlecin sol tarafındaki yığın nesnesinin yığın nesnesinin işlecin sağ tarafındaki büyük olup olmadığını sınar.

```cpp
bool operator>(const stack <Type, Container>& left, const stack <Type, Container>& right);
```

### <a name="parameters"></a>Parametreler

*Sol*\
Bir nesne türü `stack`.

*sağ*\
Bir nesne türü `stack`.

### <a name="return-value"></a>Dönüş Değeri

**doğru** işlecin sol tarafındaki yığında büyüktür ve değil işlecin sağ tarafındaki yığında eşittir; tersi durumda ise **false**.

### <a name="remarks"></a>Açıklamalar

Stack nesneleri arasında karşılaştırma öğeleri üzerinde bir ikili karşılaştırma temel alır. Büyük-iki yığın nesneleri arasındaki ilişki ilk çifti eşit olmayan öğelerin karşılaştırması üzerinde alan daha.

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

## <a name="op_gt_eq"></a> İşleci&gt;=

İşlecin sol tarafındaki yığın nesnesinin değerinden büyük veya eşittir yığın nesnesinin işlecin sağ tarafındaki olup olmadığını sınar.

```cpp
bool operator>=(const stack <Type, Container>& left, const stack <Type, Container>& right);
```

### <a name="parameters"></a>Parametreler

*Sol*\
Bir nesne türü `stack`.

*sağ*\
Bir nesne türü `stack`.

### <a name="return-value"></a>Dönüş Değeri

**doğru** işlecin sol tarafındaki yığında; işlecin sağ tarafındaki yığında değerinden kesinlikle küçük ise, aksi takdirde **false**.

### <a name="remarks"></a>Açıklamalar

Stack nesneleri arasında karşılaştırma öğeleri üzerinde bir ikili karşılaştırma temel alır. Büyüktür veya eşittir iki yığın nesneleri arasındaki ilişki için ilk çifti eşit olmayan öğelerin karşılaştırması üzerinde temel alır.

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
