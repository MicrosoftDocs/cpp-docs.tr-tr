---
title: '&lt;Stack&gt; işleçleri'
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
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/06/2020
ms.locfileid: "78865905"
---
# <a name="ltstackgt-operators"></a>&lt;Stack&gt; işleçleri

## <a name="op_neq"></a>işleç! =

İşlecin sol tarafındaki yığın nesnesinin, sağ taraftaki yığın nesnesine eşit olup olmadığını sınar.

```cpp
bool operator!=(const stack <Type, Container>& left, const stack <Type, Container>& right,);
```

### <a name="parameters"></a>Parametreler

*sol*\
`stack` türünün bir nesnesi.

*sağ*\
`stack` türünün bir nesnesi.

### <a name="return-value"></a>Dönüş Değeri

yığınlar veya yığınlar eşit değilse **doğru** ; yığınlar veya yığınlar eşitse **false** .

### <a name="remarks"></a>Açıklamalar

Yığınlar nesneleri arasındaki karşılaştırma, öğelerinin ikili bir karşılaştırmasını temel alır. İki yığın aynı sayıda öğeye sahip olmaları halinde eşittir ve ilgili öğeleri aynı değere sahiptir. Aksi takdirde, bunlar eşit değildir.

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

## <a name="op_lt"></a>işleç&lt;

İşlecin sol tarafındaki yığın nesnesinin, sağ taraftaki yığın nesnesinden küçük olup olmadığını sınar.

```cpp
bool operator<(const stack <Type, Container>& left, const stack <Type, Container>& right);
```

### <a name="parameters"></a>Parametreler

*sol*\
`stack` türünün bir nesnesi.

*sağ*\
`stack` türünün bir nesnesi.

### <a name="return-value"></a>Dönüş Değeri

işlecin sol tarafındaki yığın işlecin sağ tarafındaki yığına eşit veya ondan küçükse **true** ;. Aksi halde **yanlış**.

### <a name="remarks"></a>Açıklamalar

Yığın nesneleri arasındaki karşılaştırma, öğelerinin ikili bir karşılaştırmasını temel alır. İki yığın nesnesi arasındaki daha az ilişki, eşit olmayan öğelerin ilk çiftinin karşılaştırmasına dayalıdır.

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

## <a name="op_lt_eq"></a>işleç&lt;=

İşlecin sol tarafındaki yığın nesnesinin, sağ taraftaki yığın nesnesine eşit veya ondan küçük olup olmadığını test eder.

```cpp
bool operator<=(const stack <Type, Container>& left, const stack <Type, Container>& right);
```

### <a name="parameters"></a>Parametreler

*sol*\
`stack` türünün bir nesnesi.

*sağ*\
`stack` türünün bir nesnesi.

### <a name="return-value"></a>Dönüş Değeri

işlecin sol tarafındaki yığın işlecin sağ tarafındaki yığına küçüktür veya ona eşitse **true** ; Aksi halde **yanlış**.

### <a name="remarks"></a>Açıklamalar

Yığın nesneleri arasındaki karşılaştırma, öğelerinin ikili bir karşılaştırmasını temel alır. İki yığın nesnesi arasındaki en az veya daha fazla ilişki, eşit olmayan öğelerin ilk çiftinin karşılaştırmasına dayalıdır.

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

## <a name="op_eq_eq"></a>işleç = =

İşlecin sol tarafındaki yığın nesnesinin, sağ taraftaki yığın nesnesine eşit olup olmadığını sınar.

```cpp
bool operator==(const stack <Type, Container>& left, const stack <Type, Container>& right);
```

### <a name="parameters"></a>Parametreler

*sol*\
`stack` türünün bir nesnesi.

*sağ*\
`stack` türünün bir nesnesi.

### <a name="return-value"></a>Dönüş Değeri

yığınlar veya yığınlar eşitse **true** ; yığınlar veya yığınlar eşitse **false** .

### <a name="remarks"></a>Açıklamalar

Yığın nesneleri arasındaki karşılaştırma, öğelerinin ikili bir karşılaştırmasını temel alır. İki yığın aynı sayıda öğeye sahip olmaları halinde eşittir ve ilgili öğeleri aynı değere sahiptir. Aksi takdirde, bunlar eşit değildir.

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

## <a name="op_gt"></a>işleç&gt;

İşlecin sol tarafındaki yığın nesnesinin, sağ taraftaki yığın nesnesinden büyük olup olmadığını sınar.

```cpp
bool operator>(const stack <Type, Container>& left, const stack <Type, Container>& right);
```

### <a name="parameters"></a>Parametreler

*sol*\
`stack` türünün bir nesnesi.

*sağ*\
`stack` türünün bir nesnesi.

### <a name="return-value"></a>Dönüş Değeri

işlecin sol tarafındaki yığın işlecin sağ tarafındaki yığına eşit veya ondan büyükse **doğru** ;. Aksi halde **yanlış**.

### <a name="remarks"></a>Açıklamalar

Yığın nesneleri arasındaki karşılaştırma, öğelerinin ikili bir karşılaştırmasını temel alır. İki yığın nesnesi arasındaki büyüktür ilişkisi, eşit olmayan öğelerin ilk çiftinin karşılaştırmasını temel alır.

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

## <a name="op_gt_eq"></a>işleç&gt;=

İşlecin sol tarafındaki yığın nesnesinin, sağ taraftaki yığın nesnesinden büyük veya ona eşit olup olmadığını sınar.

```cpp
bool operator>=(const stack <Type, Container>& left, const stack <Type, Container>& right);
```

### <a name="parameters"></a>Parametreler

*sol*\
`stack` türünün bir nesnesi.

*sağ*\
`stack` türünün bir nesnesi.

### <a name="return-value"></a>Dönüş Değeri

işlecin sol tarafındaki yığın işlecin sağ tarafındaki yığından tamamen daha küçükse **true** ; Aksi halde **yanlış**.

### <a name="remarks"></a>Açıklamalar

Yığın nesneleri arasındaki karşılaştırma, öğelerinin ikili bir karşılaştırmasını temel alır. İki yığın nesnesi arasındaki en büyük veya daha fazla ilişki, eşit olmayan öğelerin ilk çiftinin karşılaştırmasına dayalıdır.

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
