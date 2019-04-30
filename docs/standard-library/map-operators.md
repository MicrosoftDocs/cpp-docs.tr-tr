---
title: '&lt;Harita&gt; işleçleri'
ms.date: 03/27/2019
f1_keywords:
- map/std::operator!=
- map/std::operator&gt;
- map/std::operator&gt;=
- map/std::operator&lt;
- map/std::operator&lt;=
- map/std::operator==
ms.assetid: 7df02b9f-701c-44ed-834a-a819badc5bd0
helpviewer_keywords:
- std::operator!= (map)
- std::operator&gt; (map)
- std::operator&gt;= (map)
- std::operator&lt; (map)
- std::operator&lt;= (map)
- std::operator== (map)
ms.openlocfilehash: b6d2ac108652e33fdd76abaac9b982840d4fce7f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62413027"
---
# <a name="ltmapgt-operators"></a>&lt;Harita&gt; işleçleri

||||
|-|-|-|
|[operator!=](#op_neq)|[İşleci&gt;](#op_gt)|[İşleci&gt;=](#op_gt_eq)|
|[İşleci&lt;](#op_lt)|[İşleci&lt;=](#op_lt_eq)|[operator==](#op_eq_eq)|
|[işleç! = (multimap)](#op_neq_multimap)|[İşleç&gt; (multimap)](#op_gt_multimap)|[İşleç&gt;= (multimap)](#op_gt_eq_multimap)|
|[İşleç&lt; (multimap)](#op_lt_multimap)|[İşleç&lt;= (multimap)](#op_lt_eq_multimap)|[işleç == (multimap)](#op_eq_eq_multimap)|

## <a name="op_neq"></a>  işleç! =

İşlecin sol tarafındaki eşlem nesnesine sağ tarafta eşleme nesnesine eşit olup olmadığını sınar.

```cpp
bool operator!=(
      const map <Key, Type, Traits, Allocator>& left,
      const map <Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*Sol*<br/>
Bir nesne türü `map`.

*sağ*<br/>
Bir nesne türü `map`.

### <a name="return-value"></a>Dönüş Değeri

**doğru** eşlemeleri eşit; değilse, **false** haritalar eşitse.

### <a name="remarks"></a>Açıklamalar

Map nesneleri arasında karşılaştırma öğeleri üzerinde bir ikili karşılaştırma temel alır. İki haritalar, bunlar aynı sayıda öğe varsa ve ilgili öğeleri aynı değerleri eşit olur. Aksi takdirde, eşit oldukları.

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
/* Output:
The maps m1 and m2 are not equal.
The maps m1 and m3 are equal.
*/
```

## <a name="op_lt"></a>  İşleci&lt;

İşlecin sol tarafındaki harita nesne eşleme nesnesinin işlecin sağ tarafındaki küçüktür olup olmadığını sınar.

```cpp
bool operator<(
      const map <Key, Type, Traits, Allocator>& left,
      const map <Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*Sol*<br/>
Bir nesne türü `map`.

*sağ*<br/>
Bir nesne türü `map`.

### <a name="return-value"></a>Dönüş Değeri

**doğru** işlecin sol tarafındaki haritada; işlecin sağ tarafındaki haritada değerinden kesinlikle küçük ise, aksi takdirde **false**.

### <a name="remarks"></a>Açıklamalar

Map nesneleri arasında karşılaştırma öğeleri üzerinde bir ikili karşılaştırma temel alır. Daha az-iki nesne arasındaki ilişki ilk çifti eşit olmayan öğelerin karşılaştırması üzerinde alan daha.

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
/* Output:
The map m1 is less than the map m2.
The map m1 is not less than the map m3.
*/
```

## <a name="op_lt_eq"></a>  İşleci&lt;=

Harita işlecinin sol tarafında nesne küçük olup olmadığını sınar eşlem nesnesine eşit veya işlecin sağ tarafındaki.

```cpp
bool operator<=(
      const map <Key, Type, Traits, Allocator>& left,
      const map <Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*Sol*<br/>
Bir nesne türü `map`.

*sağ*<br/>
Bir nesne türü `map`.

### <a name="return-value"></a>Dönüş Değeri

**doğru** işlecin sol tarafındaki haritada daha veya işlecin sağ tarafındaki haritada eşittir; Aksi takdirde küçükse **false**.

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
/* Output:
The map m1 is less than or equal to the map m2.
The map m1 is greater than the map m3.
The map m1 is less than or equal to the map m4.
*/
```

## <a name="op_eq_eq"></a>  işleç ==

İşlecin sol tarafındaki eşleme nesnesinin işlecin sağ tarafındaki eşleme nesnesine eşit olup olmadığını sınar.

```cpp
bool operator==(
      const map <Key, Type, Traits, Allocator>& left,
      const map <Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*Sol*<br/>
Bir nesne türü `map`.

*sağ*<br/>
Bir nesne türü `map`.

### <a name="return-value"></a>Dönüş Değeri

**doğru** işlecinin sol tarafında haritasıdır durumunda eşit işlecin sağ tarafındaki haritada; Aksi takdirde **false**.

### <a name="remarks"></a>Açıklamalar

Map nesneleri arasında karşılaştırma öğeleri üzerinde bir ikili karşılaştırma temel alır. İki haritalar, bunlar aynı sayıda öğe varsa ve ilgili öğeleri aynı değerleri eşit olur. Aksi takdirde, eşit oldukları.

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
/* Output:
The maps m1 and m2 are not equal.
The maps m1 and m3 are equal.
*/
```

## <a name="op_gt"></a>  İşleci&gt;

İşlecin sol tarafındaki harita nesne eşleme nesnesinin işlecin sağ tarafındaki büyük olup olmadığını sınar.

```cpp
bool operator>(
      const map <Key, Type, Traits, Allocator>& left,
      const map <Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*Sol*<br/>
Bir nesne türü `map`.

*sağ*<br/>
Bir nesne türü `map`.

### <a name="return-value"></a>Dönüş Değeri

**doğru** işlecinin sol tarafında haritasıdır, aksi takdirde işlecin sağ tarafındaki haritada daha büyük **false**.

### <a name="remarks"></a>Açıklamalar

Map nesneleri arasında karşılaştırma öğeleri üzerinde bir ikili karşılaştırma temel alır. Büyük-iki nesne arasındaki ilişki ilk çifti eşit olmayan öğelerin karşılaştırması üzerinde alan daha.

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
/* Output:
The map m1 is not greater than the map m2.
The map m1 is greater than the map m3.
*/
```

## <a name="op_gt_eq"></a>  İşleci&gt;=

Eşlem nesnesine işlecinin sol tarafındaki büyük veya işlecin sağ tarafındaki eşleme nesnesine eşit olup olmadığını sınar.

```cpp
bool operator>=(
      const map <Key, Type, Traits, Allocator>& left,
      const map <Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*Sol*<br/>
Bir nesne türü `map`.

*sağ*<br/>
Bir nesne türü `map`.

### <a name="return-value"></a>Dönüş Değeri

**doğru** işlecinin sol tarafında haritasıdır, daha büyük veya eşit eşlemesine listenin sağ tarafında; tersi durumda **false**.

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
/* Output:
The map m1 is less than the map m2.
Map m1 is greater than or equal to map m3.
Map m1 is greater than or equal to map m4.
*/
```

## <a name="op_neq_multimap"></a>  işleç! = (multimap)

İşlecin sol tarafındaki multimap nesne işlecin sağ tarafındaki multimap nesneye eşit olup olmadığını sınar.

```cpp
bool operator!=(
      const multimap <Key, Type, Traits, Allocator>& left,
      const multimap <Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*Sol*<br/>
Bir nesne türü `multimap`.

*sağ*<br/>
Bir nesne türü `multimap`.

### <a name="return-value"></a>Dönüş Değeri

**doğru** multimaps eşit; değilse, **false** multimaps durumunda eşit.

### <a name="remarks"></a>Açıklamalar

Multimap nesneler arasında karşılaştırma öğeleri üzerinde bir ikili karşılaştırma temel alır. Bunlar aynı sayıda öğe varsa ve ilgili öğeleri aynı değerlere sahip iki multimaps eşit olur. Aksi takdirde, eşit oldukları.

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
/* Output:
The multimaps m1 and m2 are not equal.
The multimaps m1 and m3 are equal.
*/
```

## <a name="op_lt_multimap"></a>  İşleci&lt;

İşlecin sol tarafındaki multimap nesnesinin işlecin sağ tarafındaki multimap nesneden küçük olup olmadığını sınar.

```cpp
bool operator<(
      const multimap <Key, Type, Traits, Allocator>& left,
      const multimap <Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*Sol*<br/>
Bir nesne türü `multimap`.

*sağ*<br/>
Bir nesne türü `multimap`.

### <a name="return-value"></a>Dönüş Değeri

**doğru** işlecinin sol tarafındaki multimap; işlecin sağ tarafındaki multimap değerinden kesinlikle küçük ise, aksi takdirde **false**.

### <a name="remarks"></a>Açıklamalar

Multimap nesneler arasında karşılaştırma öğeleri üzerinde bir ikili karşılaştırma temel alır. Daha az-iki nesne arasındaki ilişki ilk çifti eşit olmayan öğelerin karşılaştırması üzerinde alan daha.

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
/* Output:
The multimap m1 is less than the multimap m2.
The multimap m1 is not less than the multimap m3.
*/
```

## <a name="op_lt_eq_multimap"></a>  İşleci&lt;=

Multimap işlecinin sol tarafında nesne küçük olup olmadığını sınar multimap nesnesine eşit veya işlecin sağ tarafındaki.

```cpp
bool operator<=(
      const multimap <Key, Type, Traits, Allocator>& left,
      const multimap <Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*Sol*<br/>
Bir nesne türü `multimap`.

*sağ*<br/>
Bir nesne türü `multimap`.

### <a name="return-value"></a>Dönüş Değeri

**doğru** işlecinin sol tarafındaki multimap daha veya işlecin sağ tarafındaki multimap eşit; Aksi takdirde küçükse **false**.

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
/* Output:
m1 is less than or equal to m2
m1 is greater than m3
m1 is less than or equal to m4
*/
```

## <a name="op_eq_eq_multimap"></a>  işleç ==

İşlecin sol tarafındaki multimap nesne işlecin sağ tarafındaki multimap nesneye eşit olup olmadığını sınar.

```cpp
bool operator==(
      const multimap <Key, Type, Traits, Allocator>& left,
      const multimap <Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*Sol*<br/>
Bir nesne türü `multimap`.

*sağ*<br/>
Bir nesne türü `multimap`.

### <a name="return-value"></a>Dönüş Değeri

**doğru** multimap işlecinin sol tarafındaki ise, aksi takdirde işlecin sağ tarafındaki multimap eşit **false**.

### <a name="remarks"></a>Açıklamalar

Multimap nesneler arasında karşılaştırma öğeleri üzerinde bir ikili karşılaştırma temel alır. Bunlar aynı sayıda öğe varsa ve ilgili öğeleri aynı değerlere sahip iki multimaps eşit olur. Aksi takdirde, eşit oldukları.

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
/* Output:
m1 and m2 are not equal
m1 and m3 are equal
*/
```

## <a name="op_gt_multimap"></a>  İşleci&gt;

İşlecin sol tarafındaki multimap nesne multimap nesnesinin işlecin sağ tarafındaki büyük olup olmadığını sınar.

```cpp
bool operator>(
      const multimap <Key, Type, Traits, Allocator>& left,
      const multimap <Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*Sol*<br/>
Bir nesne türü `multimap`.

*sağ*<br/>
Bir nesne türü `multimap`.

### <a name="return-value"></a>Dönüş Değeri

**doğru** işlecinin sol tarafındaki multimap ise, aksi takdirde multimap işlecin sağ tarafındaki büyük **false**.

### <a name="remarks"></a>Açıklamalar

Multimap nesneler arasında karşılaştırma öğeleri üzerinde bir ikili karşılaştırma temel alır. Büyük-iki nesne arasındaki ilişki ilk çifti eşit olmayan öğelerin karşılaştırması üzerinde alan daha.

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
/* Output:
Multimap m1 is not greater than multimap m2.
The multimap m1 is greater than the multimap m3.
*/
```

## <a name="op_gt_eq_multimap"></a>  İşleci&gt;=

İşlecin sol tarafındaki multimap nesnesinin değerinden büyük veya işlecin sağ tarafındaki multimap nesneye eşit olup olmadığını sınar.

```cpp
bool operator>=(
      const multimap <Key, Type, Traits, Allocator>& left,
      const multimap <Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*Sol*<br/>
Bir nesne türü `multimap`.

*sağ*<br/>
Bir nesne türü `multimap`.

### <a name="return-value"></a>Dönüş Değeri

**doğru** işlecinin sol tarafındaki multimap büyüktür veya eşittir multimap listenin sağ tarafında; tersi durumda ise **false**.

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
/* Output:
The multimap m1 is less than the multimap m2.
The multimap m1 is greater than or equal to the multimap m3.
The multimap m1 is greater than or equal to the multimap m4.
*/
```

## <a name="see-also"></a>Ayrıca bkz.

[\<Harita >](../standard-library/map.md)<br/>
