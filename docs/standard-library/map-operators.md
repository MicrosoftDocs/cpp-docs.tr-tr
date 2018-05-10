---
title: '&lt;Harita&gt; işleçleri | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- map/std::operator!=
- map/std::operator&gt;
- map/std::operator&gt;=
- map/std::operator&lt;
- map/std::operator&lt;=
- map/std::operator==
dev_langs:
- C++
ms.assetid: 7df02b9f-701c-44ed-834a-a819badc5bd0
helpviewer_keywords:
- std::operator!= (map)
- std::operator&gt; (map)
- std::operator&gt;= (map)
- std::operator&lt; (map)
- std::operator&lt;= (map)
- std::operator== (map)
ms.openlocfilehash: 60813074eb112836295a72b1c11a24a8c9800313
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
---
# <a name="ltmapgt-operators"></a>&lt;Harita&gt; işleçleri

||||
|-|-|-|
|[operator!=](#op_neq)|[işleci&gt;](#op_gt)|[işleci&gt;=](#op_gt_eq)|
|[işleci&lt;](#op_lt)|[işleci&lt;=](#op_lt_eq)|[operator==](#op_eq_eq)|
|[operator! = (multimap)](#op_neq_multimap)|[işleci&gt;](#op_gt_multimap)|[işleci&gt;=](#op_gt_eq_multimap)|
|[işleci&lt;](#op_lt_multimap)|[işleci&lt;=](#op_lt_eq_multimap)|[operator==](#op_eq_eq_multimap)|

## <a name="op_neq"></a>  operator! =

Testleri işlecinin sol tarafındaki harita nesnesi sağ tarafta eşleme nesnesine eşit değil.

```cpp
bool operator!=(
      const map <Key, Type, Traits, Allocator>& left,
      const map <Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

`left` Türünde bir nesne **harita**.

`right` Türünde bir nesne **harita**.

### <a name="return-value"></a>Dönüş Değeri

**doğru** eşlemeleri eşit; değilse **false** eşlemeleri eşit olması durumunda.

### <a name="remarks"></a>Açıklamalar

Map nesneleri arasındaki karşılaştırma öğelerini pairwise karşılaştırması hakkında temel alır. İki eşlemeleri aynı sayıda öğe varsa ve bunların ilgili öğeleri aynı değerlere eşittir. Aksi takdirde, bunlar eşit.

### <a name="example"></a>Örnek

```cpp
// map_op_ne.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;
   map <int, int> m1, m2, m3;
   int i;
   typedef pair <int, int> Int_Pair;

   for ( i = 0 ; i < 3 ; i++ )
   {
      m1.insert ( Int_Pair ( i, i ) );
      m2.insert ( Int_Pair ( i, i * i ) );
      m3.insert ( Int_Pair ( i, i ) );
   }

   if ( m1 != m2 )
      cout << "The maps m1 and m2 are not equal." << endl;
   else
      cout << "The maps m1 and m2 are equal." << endl;

   if ( m1 != m3 )
      cout << "The maps m1 and m3 are not equal." << endl;
   else
      cout << "The maps m1 and m3 are equal." << endl;
}
\* Output:
The maps m1 and m2 are not equal.
The maps m1 and m3 are equal.
*\
```

## <a name="op_lt"></a>  işleci&lt;

Harita nesnesi işlecinin sol tarafındaki sağ tarafta eşleme nesnesi küçükse testleri.

```cpp
bool operator<(
      const map <Key, Type, Traits, Allocator>& left,
      const map <Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

`left` Türünde bir nesne **harita**.

`right` Türünde bir nesne **harita**.

### <a name="return-value"></a>Dönüş Değeri

**doğru** işlecinin sol tarafındaki harita; işlecinin sağ tarafında harita kesinlikle değerinden ise, aksi takdirde **false**.

### <a name="remarks"></a>Açıklamalar

Map nesneleri arasındaki karşılaştırma öğelerini pairwise karşılaştırması hakkında temel alır. Küçüktür-iki nesne arasındaki ilişki ilk çiftlerini eşit olmayan bir karşılaştırmasını alan daha.

### <a name="example"></a>Örnek

```cpp
// map_op_lt.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;
   map<int, int> m1, m2, m3;
   int i;
   typedef pair<int, int> Int_Pair;

   for ( i = 1 ; i < 3 ; i++ )
   {
      m1.insert ( Int_Pair ( i, i ) );
      m2.insert ( Int_Pair ( i, i * i ) );
      m3.insert ( Int_Pair ( i, i - 1 ) );
   }

   if ( m1 < m2 )
      cout << "The map m1 is less than the map m2." << endl;
   else
      cout << "The map m1 is not less than the map m2." << endl;

   if ( m1 < m3 )
      cout << "The map m1 is less than the map m3." << endl;
   else
      cout << "The map m1 is not less than the map m3." << endl;
}
\* Output:
The map m1 is less than the map m2.
The map m1 is not less than the map m3.
*\
```

## <a name="op_lt_eq"></a>  işleci&lt;=

Harita işlecinin sol tarafında nesne sağlayıp sağlamadığını test sağ tarafında harita nesnesi eşit veya daha az olur.

```cpp
bool operator<=(
      const map <Key, Type, Traits, Allocator>& left,
      const map <Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

`left` Türünde bir nesne **harita**.

`right` Türünde bir nesne **harita**.

### <a name="return-value"></a>Dönüş Değeri

**doğru** işlecinin sol tarafındaki harita veya harita işlecinin sağ tarafında eşit; Aksi takdirde düşükse **false**.

### <a name="example"></a>Örnek

```cpp
// map_op_le.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;
   map <int, int> m1, m2, m3, m4;
   int i;
   typedef pair <int, int> Int_Pair;

   for ( i = 1 ; i < 3 ; i++ )
   {
      m1.insert ( Int_Pair ( i, i ) );
      m2.insert ( Int_Pair ( i, i * i ) );
      m3.insert ( Int_Pair ( i, i - 1 ) );
      m4.insert ( Int_Pair ( i, i ) );
   }

   if ( m1 <= m2 )
      cout << "The map m1 is less than or equal to the map m2." << endl;
   else
      cout << "The map m1 is greater than the map m2." << endl;

   if ( m1 <= m3 )
      cout << "The map m1 is less than or equal to the map m3." << endl;
   else
      cout << "The map m1 is greater than the map m3." << endl;

   if ( m1 <= m4 )
      cout << "The map m1 is less than or equal to the map m4." << endl;
   else
      cout << "The map m1 is greater than the map m4." << endl;
}
\* Output:
The map m1 is less than or equal to the map m2.
The map m1 is greater than the map m3.
The map m1 is less than or equal to the map m4.
*\
```

## <a name="op_eq_eq"></a>  operator ==

Harita nesnesi işlecinin sol tarafındaki sağ tarafta eşleme nesnesine eşitse testleri.

```cpp
bool operator==(
      const map <Key, Type, Traits, Allocator>& left,
      const map <Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

`left` Türünde bir nesne **harita**.

`right` Türünde bir nesne **harita**.

### <a name="return-value"></a>Dönüş Değeri

**doğru** işlecinin sol tarafındaki harita eşitse işlecinin sağ tarafında eşlemeye aksi **false**.

### <a name="remarks"></a>Açıklamalar

Map nesneleri arasındaki karşılaştırma öğelerini pairwise karşılaştırması hakkında temel alır. İki eşlemeleri aynı sayıda öğe varsa ve bunların ilgili öğeleri aynı değerlere eşittir. Aksi takdirde, bunlar eşit.

### <a name="example"></a>Örnek

```cpp
// map_op_eq.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;
   map < int, int > m1, m2, m3;
   int i;
   typedef pair < int, int > Int_Pair;

   for ( i = 0 ; i < 3 ; i++ )
   {
      m1.insert ( Int_Pair ( i, i ) );
      m2.insert ( Int_Pair ( i, i * i ) );
      m3.insert ( Int_Pair ( i, i ) );
   }

   if ( m1 == m2 )
      cout << "The maps m1 and m2 are equal." << endl;
   else
      cout << "The maps m1 and m2 are not equal." << endl;

   if ( m1 == m3 )
      cout << "The maps m1 and m3 are equal." << endl;
   else
      cout << "The maps m1 and m3 are not equal." << endl;
}
\* Output:
The maps m1 and m2 are not equal.
The maps m1 and m3 are equal.
*\
```

## <a name="op_gt"></a>  işleci&gt;

Testleri işlecinin sol tarafındaki harita nesnesi sağ tarafta eşleme nesnesi değerinden daha büyük.

```cpp
bool operator>(
      const map <Key, Type, Traits, Allocator>& left,
      const map <Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

`left` Türünde bir nesne **harita**.

`right` Türünde bir nesne **harita**.

### <a name="return-value"></a>Dönüş Değeri

**doğru** işlecinin sol tarafındaki harita işlecinin sağ tarafında harita büyük; tersi durumda ise **false**.

### <a name="remarks"></a>Açıklamalar

Map nesneleri arasındaki karşılaştırma öğelerini pairwise karşılaştırması hakkında temel alır. Büyük-iki nesne arasındaki ilişki ilk çiftlerini eşit olmayan bir karşılaştırmasını alan daha.

### <a name="example"></a>Örnek

```cpp
// map_op_gt.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;
   map < int, int > m1, m2, m3;
   int i;
   typedef pair < int, int > Int_Pair;

   for ( i = 0 ; i < 3 ; i++ )
   {
      m1.insert ( Int_Pair ( i, i ) );
      m2.insert ( Int_Pair ( i, i * i ) );
      m3.insert ( Int_Pair ( i, i - 1 ) );
   }

   if ( m1 > m2 )
      cout << "The map m1 is greater than the map m2." << endl;
   else
      cout << "The map m1 is not greater than the map m2." << endl;

   if ( m1 > m3 )
      cout << "The map m1 is greater than the map m3." << endl;
   else
      cout << "The map m1 is not greater than the map m3." << endl;
}
\* Output:
The map m1 is not greater than the map m2.
The map m1 is greater than the map m3.
*\
```

## <a name="op_gt_eq"></a>  işleci&gt;=

Harita nesnesi işlecinin sol tarafındaki sağ tarafta eşleme nesnesine eşit veya daha büyük ise testleri.

```cpp
bool operator>=(
      const map <Key, Type, Traits, Allocator>& left,
      const map <Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

`left` Türünde bir nesne **harita**.

`right` Türünde bir nesne **harita**.

### <a name="return-value"></a>Dönüş Değeri

**doğru** işlecinin sol tarafındaki harita eşitse büyüktür veya listesinin sağ taraftaki eşlemeye aksi **false**.

### <a name="example"></a>Örnek

```cpp
// map_op_ge.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;
   map < int, int > m1, m2, m3, m4;
   int i;
   typedef pair < int, int > Int_Pair;

   for ( i = 1 ; i < 3 ; i++ )
   {
      m1.insert ( Int_Pair ( i, i ) );
      m2.insert ( Int_Pair ( i, i * i ) );
      m3.insert ( Int_Pair ( i, i - 1 ) );
      m4.insert ( Int_Pair ( i, i ) );
   }

   if ( m1 >= m2 )
      cout << "Map m1 is greater than or equal to map m2." << endl;
   else
      cout << "The map m1 is less than the map m2." << endl;

   if ( m1 >= m3 )
      cout << "Map m1 is greater than or equal to map m3." << endl;
   else
      cout << "The map m1 is less than the map m3." << endl;

   if ( m1 >= m4 )
      cout << "Map m1 is greater than or equal to map m4." << endl;
   else
      cout << "The map m1 is less than the map m4." << endl;
}
\* Output:
The map m1 is less than the map m2.
Map m1 is greater than or equal to map m3.
Map m1 is greater than or equal to map m4.
*\
```

## <a name="op_neq_multimap"></a>  operator! = (multimap)

Multimap nesne işlecinin sol tarafındaki sağ tarafında multimap nesne eşit değilse testleri.

```cpp
bool operator!=(
      const multimap <Key, Type, Traits, Allocator>& left,
      const multimap <Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

`left` Türünde bir nesne `multimap`.

`right` Türünde bir nesne `multimap`.

### <a name="return-value"></a>Dönüş Değeri

**doğru** multimaps eşit; değilse **false** multimaps varsa eşit.

### <a name="remarks"></a>Açıklamalar

Multimap nesneleri arasındaki karşılaştırma öğelerini pairwise karşılaştırması hakkında temel alır. İki multimaps aynı sayıda öğe varsa ve bunların ilgili öğeleri aynı değerlere eşittir. Aksi takdirde, bunlar eşit.

### <a name="example"></a>Örnek

```cpp
// multimap_op_ne.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;
   multimap <int, int> m1, m2, m3;
   int i;
   typedef pair <int, int> Int_Pair;

   for ( i = 0 ; i < 3 ; i++ )
   {
      m1.insert ( Int_Pair ( i, i ) );
      m2.insert ( Int_Pair ( i, i * i ) );
      m3.insert ( Int_Pair ( i, i ) );
   }

   if ( m1 != m2 )
      cout << "The multimaps m1 and m2 are not equal." << endl;
   else
      cout << "The multimaps m1 and m2 are equal." << endl;

   if ( m1 != m3 )
      cout << "The multimaps m1 and m3 are not equal." << endl;
   else
      cout << "The multimaps m1 and m3 are equal." << endl;
}
\* Output:
The multimaps m1 and m2 are not equal.
The multimaps m1 and m3 are equal.
*\
```

## <a name="op_lt_multimap"></a>  işleci&lt;

Multimap nesne işlecinin sol tarafındaki sağ tarafında multimap nesne küçükse testleri.

```cpp
bool operator<(
      const multimap <Key, Type, Traits, Allocator>& left,
      const multimap <Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

`left` Türünde bir nesne `multimap`.

`right` Türünde bir nesne `multimap`.

### <a name="return-value"></a>Dönüş Değeri

**doğru** işlecinin sol tarafındaki multimap; işlecinin sağ tarafında multimap kesinlikle değerinden ise, aksi takdirde **false**.

### <a name="remarks"></a>Açıklamalar

Multimap nesneleri arasındaki karşılaştırma öğelerini pairwise karşılaştırması hakkında temel alır. Küçüktür-iki nesne arasındaki ilişki ilk çiftlerini eşit olmayan bir karşılaştırmasını alan daha.

### <a name="example"></a>Örnek

```cpp
// multimap_op_lt.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;
   multimap < int, int > m1, m2, m3;
   int i;
   typedef pair < int, int > Int_Pair;

   for ( i = 1 ; i < 3 ; i++ )
   {
      m1.insert ( Int_Pair ( i, i ) );
      m2.insert ( Int_Pair ( i, i * i ) );
      m3.insert ( Int_Pair ( i, i - 1 ) );
   }

   if ( m1 < m2 )
      cout << "The multimap m1 is less than the multimap m2." << endl;
   else
      cout << "The multimap m1 is not less than the multimap m2." << endl;

   if ( m1 < m3 )
      cout << "The multimap m1 is less than the multimap m3." << endl;
   else
      cout << "The multimap m1 is not less than the multimap m3." << endl;
}
\* Output:
The multimap m1 is less than the multimap m2.
The multimap m1 is not less than the multimap m3.
*\
```

## <a name="eq_multimap"></a>  işleci&lt;=

Multimap işlecinin sol tarafında nesne sağlayıp sağlamadığını test sağ tarafında multimap nesnesine eşit veya daha az olur.

```cpp
bool operator<=(
      const multimap <Key, Type, Traits, Allocator>& left,
      const multimap <Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

`left` Türünde bir nesne `multimap`.

`right` Türünde bir nesne `multimap`.

### <a name="return-value"></a>Dönüş Değeri

**doğru** işlecinin sol tarafındaki multimap veya multimap işlecinin sağ tarafında eşit; Aksi takdirde düşükse **false**.

### <a name="example"></a>Örnek

```cpp
// multimap_op_le.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;
   multimap <int, int> m1, m2, m3, m4;
   int i;
   typedef pair <int, int> Int_Pair;

   for ( i = 1 ; i < 3 ; i++ )
   {
      m1.insert ( Int_Pair ( i, i ) );
      m2.insert ( Int_Pair ( i, i * i ) );
      m3.insert ( Int_Pair ( i, i - 1 ) );
      m4.insert ( Int_Pair ( i, i ) );
   }

   if ( m1 <= m2 )
      cout << "m1 is less than or equal to m2" << endl;
   else
      cout << "m1 is greater than m2" << endl;

   if ( m1 <= m3 )
      cout << "m1 is less than or equal to m3" << endl;
   else
      cout << "m1 is greater than m3" << endl;

   if ( m1 <= m4 )
      cout << "m1 is less than or equal to m4" << endl;
   else
      cout << "m1 is greater than m4" << endl;
}
\* Output:
m1 is less than or equal to m2
m1 is greater than m3
m1 is less than or equal to m4
*\
```

## <a name="op_eq_eq_multimap"></a>  operator ==

Multimap nesne işlecinin sol tarafındaki sağ tarafında multimap nesnesine eşitse testleri.

```cpp
bool operator==(
      const multimap <Key, Type, Traits, Allocator>& left,
      const multimap <Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

`left` Türünde bir nesne `multimap`.

`right` Türünde bir nesne `multimap`.

### <a name="return-value"></a>Dönüş Değeri

**doğru** multimap işlecinin sol tarafındaki işlecinin sağ tarafında multimap eşit; tersi durumda ise **false**.

### <a name="remarks"></a>Açıklamalar

Multimap nesneleri arasındaki karşılaştırma öğelerini pairwise karşılaştırması hakkında temel alır. İki multimaps aynı sayıda öğe varsa ve bunların ilgili öğeleri aynı değerlere eşittir. Aksi takdirde, bunlar eşit.

### <a name="example"></a>Örnek

```cpp
// multimap_op_eq.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;
   multimap<int, int> m1, m2, m3;
   int i;
   typedef pair<int, int> Int_Pair;

   for (i = 0; i < 3; i++)
   {
      m1.insert(Int_Pair(i, i));
      m2.insert(Int_Pair(i, i*i));
      m3.insert(Int_Pair(i, i));
   }

   if ( m1 == m2 )
      cout << "m1 and m2 are equal" << endl;
   else
      cout << "m1 and m2 are not equal" << endl;

   if ( m1 == m3 )
      cout << "m1 and m3 are equal" << endl;
   else
      cout << "m1 and m3 are not equal" << endl;
}
\* Output:
m1 and m2 are not equal
m1 and m3 are equal
*\
```

## <a name="op_gt_multimap"></a>  işleci&gt;

Multimap nesne işlecinin sol tarafındaki sağ tarafında multimap nesne büyükse testleri.

```cpp
bool operator>(
      const multimap <Key, Type, Traits, Allocator>& left,
      const multimap <Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

`left` Türünde bir nesne `multimap`.

`right` Türünde bir nesne `multimap`.

### <a name="return-value"></a>Dönüş Değeri

**doğru** multimap işlecinin sol tarafındaki işlecinin sağ tarafında multimap büyük; tersi durumda ise **false**.

### <a name="remarks"></a>Açıklamalar

Multimap nesneleri arasındaki karşılaştırma öğelerini pairwise karşılaştırması hakkında temel alır. Büyük-iki nesne arasındaki ilişki ilk çiftlerini eşit olmayan bir karşılaştırmasını alan daha.

### <a name="example"></a>Örnek

```cpp
// multimap_op_gt.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;
   multimap < int, int > m1, m2, m3;
   int i;
   typedef pair < int, int > Int_Pair;

   for ( i = 0 ; i < 3 ; i++ )
   {
      m1.insert ( Int_Pair ( i, i ) );
      m2.insert ( Int_Pair ( i, i * i ) );
      m3.insert ( Int_Pair ( i, i - 1 ) );
   }

   if ( m1 > m2 )
      cout << "The multimap m1 is greater than the multimap m2." << endl;
   else
      cout << "Multimap m1 is not greater than multimap m2." << endl;

   if ( m1 > m3 )
      cout << "The multimap m1 is greater than the multimap m3." << endl;
   else
      cout << "The multimap m1 is not greater than the multimap m3." << endl;
}
\* Output:
Multimap m1 is not greater than multimap m2.
The multimap m1 is greater than the multimap m3.
*\
```

## <a name="op_gt_eq_multimap"></a>  işleci&gt;=

Multimap işlecinin sol tarafındaki sağ tarafında multimap nesnesine eşit veya daha büyük bir nesneyse testleri.

```cpp
bool operator>=(
      const multimap <Key, Type, Traits, Allocator>& left,
      const multimap <Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

`left` Türünde bir nesne `multimap`.

`right` Türünde bir nesne `multimap`.

### <a name="return-value"></a>Dönüş Değeri

**doğru** işlecinin sol tarafındaki multimap ise, daha büyük veya listesinin sağ taraftaki multimap eşit; Aksi takdirde **false**.

### <a name="example"></a>Örnek

```cpp
// multimap_op_ge.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;
   multimap < int, int > m1, m2, m3, m4;
   int i;
   typedef pair < int, int > Int_Pair;

   for ( i = 1 ; i < 3 ; i++ )
   {
      m1.insert ( Int_Pair ( i, i ) );
      m2.insert ( Int_Pair ( i, i * i ) );
      m3.insert ( Int_Pair ( i, i - 1 ) );
      m4.insert ( Int_Pair ( i, i ) );
   }

   if ( m1 >= m2 )
      cout << "The multimap m1 is greater than or equal to the multimap m2." << endl;
   else
      cout << "The multimap m1 is less than the multimap m2." << endl;

   if ( m1 >= m3 )
      cout << "The multimap m1 is greater than or equal to the multimap m3." << endl;
   else
      cout << "The multimap m1 is less than the multimap m3." << endl;

   if ( m1 >= m4 )
      cout << "The multimap m1 is greater than or equal to the multimap m4." << endl;
   else
      cout << "The multimap m1 is less than the multimap m4." << endl;
}
\* Output:
The multimap m1 is less than the multimap m2.
The multimap m1 is greater than or equal to the multimap m3.
The multimap m1 is greater than or equal to the multimap m4.
*\
```

## <a name="see-also"></a>Ayrıca bkz.

[\<Harita >](../standard-library/map.md)<br/>
