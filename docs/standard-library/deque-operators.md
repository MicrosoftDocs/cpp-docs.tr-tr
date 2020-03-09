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
ms.openlocfilehash: 868909ac4346a59cade3660f288a0f0e71bc4ed0
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/06/2020
ms.locfileid: "78883829"
---
# <a name="ltdequegt-operators"></a>&lt;deque&gt; işleçleri

## <a name="op_neq"></a>işleç! =

İşlecin sol tarafındaki deque nesnesinin, sağ taraftaki nesnenin deque nesnesine eşit olup olmadığını sınar.

```cpp
bool operator!=(const deque<Type, Allocator>& left, const deque<Type, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*sol*\
`deque` türünün bir nesnesi.

*sağ*\
`deque` türünün bir nesnesi.

### <a name="return-value"></a>Dönüş Değeri

deque nesneleri eşitse **true** ; deque nesneleri eşitse **false** .

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

## <a name="op_lt"></a>işleç&lt;

İşlecin sol tarafındaki en que nesnenin sağ taraftaki nesneden daha az olup olmadığını sınar.

```cpp
bool operator<(const deque<Type, Allocator>& left, const deque<Type, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*sol*\
`deque` türünün bir nesnesi.

*sağ*\
`deque` türünün bir nesnesi.

### <a name="return-value"></a>Dönüş Değeri

işlecin sol tarafındaki deque değeri, işlecin sağ tarafındaki deque değerinden küçükse **true** ; Aksi halde **yanlış**.

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

## <a name="op_lt_eq"></a>işleç&lt;=

İşlecin sol tarafındaki deque nesnesinin, sağ taraftaki en que nesneden küçük veya ona eşit olup olmadığını sınar.

```cpp
bool operator<=(const deque<Type, Allocator>& left, const deque<Type, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*sol*\
`deque` türünün bir nesnesi.

*sağ*\
`deque` türünün bir nesnesi.

### <a name="return-value"></a>Dönüş Değeri

işlecin sol tarafındaki deque işleci işlecin sağ tarafındaki deque değerinden küçük veya bu değere eşitse **true** ; Aksi halde **yanlış**.

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

## <a name="op_eq_eq"></a>işleç = =

İşlecin sol tarafındaki deque nesnesinin, sağ taraftaki nesnenin deque nesnesine eşit olup olmadığını sınar.

```cpp
bool operator==(const deque<Type, Allocator>& left, const deque<Type, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*sol*\
`deque` türünün bir nesnesi.

*sağ*\
`deque` türünün bir nesnesi.

### <a name="return-value"></a>Dönüş Değeri

işlecin sol tarafındaki deque işleci işlecin sağ tarafındaki deque 'a eşitse **true** . Aksi halde **yanlış**.

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

## <a name="op_gt"></a>işleç&gt;

İşlecin sol tarafındaki en que nesnenin sağ taraftaki nesneden daha büyük olup olmadığını sınar.

```cpp
bool operator>(const deque<Type, Allocator>& left, const deque<Type, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*sol*\
`deque` türünün bir nesnesi.

*sağ*\
`deque` türünün bir nesnesi.

### <a name="return-value"></a>Dönüş Değeri

işlecin sol tarafındaki deque işleci, işlecin sağ tarafındaki en que değerden büyükse **true** olur; Aksi halde **yanlış**.

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

## <a name="op_gt_eq"></a>işleç&gt;=

İşlecin sol tarafındaki deque nesnesinin, sağ taraftaki en que nesneden büyük veya ona eşit olup olmadığını sınar.

```cpp
bool operator>=(const deque<Type, Allocator>& left, const deque<Type, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*sol*\
`deque` türünün bir nesnesi.

*sağ*\
`deque` türünün bir nesnesi.

### <a name="return-value"></a>Dönüş Değeri

işlecin sol tarafındaki deque işleci işlecin sağ tarafındaki deque değerinden büyük veya bu değere eşitse **true** ; Aksi halde **yanlış**.

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
