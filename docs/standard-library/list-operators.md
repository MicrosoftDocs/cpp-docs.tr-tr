---
title: '&lt;Liste&gt; işleçler | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- list/std::operator!=
- list/std::operator&gt;
- list/std::operator&gt;=
- list/std::operator&lt;
- list/std::operator&lt;=
- list/std::operator==
dev_langs:
- C++
ms.assetid: 8103d8f2-c30f-49ad-ac50-b3ba6a907ebe
helpviewer_keywords:
- std::operator!= (list)
- std::operator&gt; (list)
- std::operator&gt;= (list)
- std::operator&lt; (list)
- std::operator&lt;= (list)
- std::operator== (list)
ms.openlocfilehash: 809dae9fb6bd255d36f9d7417bf6ab606b1309be
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/07/2018
ms.locfileid: "44102739"
---
# <a name="ltlistgt-operators"></a>&lt;Liste&gt; işleçleri

||||
|-|-|-|
|[operator!=](#op_neq)|[İşleci&gt;](#op_gt)|[İşleci&gt;=](#op_gt_eq)|
|[İşleci&lt;](#op_lt)|[İşleci&lt;=](#op_lt_eq)|[operator==](#op_eq_eq)|

## <a name="op_neq"></a>  işleç! =

İşlecin sol tarafındaki liste nesnesi işlecin sağ tarafındaki liste nesnesine eşit olup olmadığını sınar.

```cpp
bool operator!=(
    const list<Type, Allocator>& left,
    const list<Type, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*Sol*<br/>
Bir nesne türü `list`.

*sağ*<br/>
Bir nesne türü `list`.

### <a name="return-value"></a>Dönüş Değeri

**doğru** listeleri eşit; değilse, **false** listeleri aynıysa.

### <a name="remarks"></a>Açıklamalar

List nesneleri arasında karşılaştırma öğeleri üzerinde bir ikili karşılaştırma temel alır. İki liste, bunlar aynı sayıda öğe varsa ve ilgili öğeleri aynı değerleri eşit olur. Aksi takdirde, eşit oldukları.

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
\* Output:
Lists not equal.
*\
```

## <a name="op_lt"></a>  İşleci&lt;

İşlecin sol tarafındaki liste nesnesi işlecin sağ tarafındaki listesi nesneden küçük olup olmadığını sınar.

```cpp
bool operator<(
    const list<Type, Allocator>& left,
    const list<Type, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*Sol*<br/>
Bir nesne türü `list`.

*sağ*<br/>
Bir nesne türü `list`.

### <a name="return-value"></a>Dönüş Değeri

**doğru** işlecinin sol tarafındaki listenin daha ancak değil işlecin sağ tarafındaki listenin eşit Aksi takdirde küçükse **false**.

### <a name="remarks"></a>Açıklamalar

List nesneleri arasında karşılaştırma öğeleri üzerinde bir ikili karşılaştırma temel alır. Daha az-iki nesne arasındaki ilişki ilk çifti eşit olmayan öğelerin karşılaştırması üzerinde alan daha.

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
\* Output:
List c1 is less than list c2.
*\
```

## <a name="op_lt_eq"></a>  İşleci&lt;=

Listenin işlecinin sol tarafında nesne küçük olup olmadığını sınar veya liste nesnesi eşit işlecin sağ tarafındaki.

```cpp
bool operator<=(
    const list<Type, Allocator>& left,
    const list<Type, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*Sol*<br/>
Bir nesne türü `list`.

*sağ*<br/>
Bir nesne türü `list`.

### <a name="return-value"></a>Dönüş Değeri

**doğru** işlecinin sol tarafındaki listenin daha veya işlecin sağ tarafındaki listenin eşittir; Aksi takdirde küçükse **false**.

### <a name="remarks"></a>Açıklamalar

List nesneleri arasında karşılaştırma öğeleri üzerinde bir ikili karşılaştırma temel alır. İki nesne arasındaki ilişki için daha az veya eşit ilk çifti eşit olmayan öğelerin karşılaştırması üzerinde temel alır.

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
\* Output:
List c1 is less than or equal to list c2.
*\
```

## <a name="op_eq_eq"></a>  işleç ==

İşlecin sol tarafındaki listesi nesnesinin işlecin sağ tarafındaki liste nesnesine eşit olup olmadığını sınar.

```cpp
bool operator==(
    const list<Type, Allocator>& left,
    const list<Type, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*Sol*<br/>
Bir nesne türü `list`.

*sağ*<br/>
Bir nesne türü `list`.

### <a name="return-value"></a>Dönüş Değeri

**doğru** işlecinin sol tarafındaki listenin ise, aksi takdirde işlecin sağ tarafındaki listenin eşit **false**.

### <a name="remarks"></a>Açıklamalar

List nesneleri arasında karşılaştırma öğeleri üzerinde bir ikili karşılaştırma temel alır. İki liste, bunlar aynı sayıda öğe varsa ve ilgili öğeleri aynı değerleri eşit olur. Aksi takdirde, eşit oldukları.

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
\* Output:
The lists are equal.
*\
```

## <a name="op_gt"></a>  İşleci&gt;

İşlecin sol tarafındaki liste nesnesi liste nesnesi işlecin sağ tarafındaki büyük olup olmadığını sınar.

```cpp
bool operator>(
    const list<Type, Allocator>& left,
    const list<Type, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*Sol*<br/>
Bir nesne türü `list`.

*sağ*<br/>
Bir nesne türü `list`.

### <a name="return-value"></a>Dönüş Değeri

**doğru** işlecinin sol tarafındaki listenin ise, aksi takdirde listede bir işlecin sağ tarafındaki büyük **false**.

### <a name="remarks"></a>Açıklamalar

List nesneleri arasında karşılaştırma öğeleri üzerinde bir ikili karşılaştırma temel alır. Büyük-iki nesne arasındaki ilişki ilk çifti eşit olmayan öğelerin karşılaştırması üzerinde alan daha.

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
\* Output:
List c1 is greater than list c2.
*\
```

## <a name="op_gt_eq"></a>  İşleci&gt;=

İşlecin sol tarafındaki liste nesnesi büyük veya işlecin sağ tarafındaki liste nesnesine eşit olup olmadığını sınar.

```cpp
bool operator>=(
    const list<Type, Allocator>& left,
    const list<Type, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*Sol*<br/>
Bir nesne türü `list`.

*sağ*<br/>
Bir nesne türü `list`.

### <a name="return-value"></a>Dönüş Değeri

**doğru** işlecinin sol tarafındaki listenin büyüktür veya eşittir işlecin sağ tarafındaki listenin; tersi durumda ise **false**.

### <a name="remarks"></a>Açıklamalar

List nesneleri arasında karşılaştırma öğeleri üzerinde bir ikili karşılaştırma temel alır. Büyüktür veya eşittir iki nesne arasındaki ilişki için ilk çifti eşit olmayan öğelerin karşılaştırması üzerinde temel alır.

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
\* Output:
List c1 is greater than or equal to list c2.
*\
```

## <a name="see-also"></a>Ayrıca bkz.

[\<listesi >](../standard-library/list.md)<br/>
