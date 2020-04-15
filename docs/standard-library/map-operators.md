---
title: '&lt;harita&gt; operatörleri'
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
ms.openlocfilehash: 1b16028ea4be5303df5c6337260de5098e9c6ed6
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371034"
---
# <a name="ltmapgt-operators"></a>&lt;harita&gt; operatörleri

## <a name="operator"></a><a name="op_neq"></a>işleç!=

İşleticinin sol tarafındaki harita nesnesinin sağ taraftaki harita nesnesine eşit olup olmadığını test edin.

```cpp
bool operator!=(
      const map <Key, Type, Traits, Allocator>& left,
      const map <Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*Sol*\
`map` türünün bir nesnesi.

*Doğru*\
`map` türünün bir nesnesi.

### <a name="return-value"></a>Dönüş Değeri

haritalar eşit değilse **doğrudur;** haritalar **eşitse false.**

### <a name="remarks"></a>Açıklamalar

Eşlemi nesneleri arasındaki karşılaştırma, öğelerinin çift eşli bir karşılaştırmasını temel adatır. Aynı sayıda eleman varsa ve ilgili öğeleri aynı değerlere sahipse, iki eşeeşittir. Aksi takdirde, eşit değildir.

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
```

```Output
The maps m1 and m2 are not equal.
The maps m1 and m3 are equal.
```

## <a name="operatorlt"></a><a name="op_lt"></a>Işleç&lt;

İşleticinin sol tarafındaki harita nesnesinin sağ taraftaki harita nesnesinden daha az olup olmadığını test edin.

```cpp
bool operator<(
      const map <Key, Type, Traits, Allocator>& left,
      const map <Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*Sol*\
`map` türünün bir nesnesi.

*Doğru*\
`map` türünün bir nesnesi.

### <a name="return-value"></a>Dönüş Değeri

işlecinin sol tarafındaki harita, operatörün sağ tarafındaki haritadan kesinlikle daha **azsa** doğrudur; aksi takdirde **yanlış**.

### <a name="remarks"></a>Açıklamalar

Eşlemi nesneleri arasındaki karşılaştırma, öğelerinin çift eşli bir karşılaştırmasını temel adatır. İki nesne arasındaki az ilişki, eşit olmayan öğelerin ilk çiftinin karşılaştırılmasına dayanır.

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
```

```Output
The map m1 is less than the map m2.
The map m1 is not less than the map m3.
```

## <a name="operatorlt"></a><a name="op_lt_eq"></a>Işleç&lt;=

İşleticinin sol tarafındaki harita nesnesinin sağ taraftaki harita nesnesinden daha az veya eşit olup olmadığını test edin.

```cpp
bool operator<=(
      const map <Key, Type, Traits, Allocator>& left,
      const map <Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*Sol*\
`map` türünün bir nesnesi.

*Doğru*\
`map` türünün bir nesnesi.

### <a name="return-value"></a>Dönüş Değeri

işlecinin sol tarafındaki harita operatörün sağ tarafındaki haritadan daha az veya eşitse **doğrudur;** aksi takdirde **yanlış**.

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
```

```Output
The map m1 is less than or equal to the map m2.
The map m1 is greater than the map m3.
The map m1 is less than or equal to the map m4.
```

## <a name="operator"></a><a name="op_eq_eq"></a>işleç==

İşleticinin sol tarafındaki harita nesnesinin sağ taraftaki harita nesnesine eşit olup olmadığını test edin.

```cpp
bool operator==(
      const map <Key, Type, Traits, Allocator>& left,
      const map <Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*Sol*\
`map` türünün bir nesnesi.

*Doğru*\
`map` türünün bir nesnesi.

### <a name="return-value"></a>Dönüş Değeri

işlecinin sol tarafındaki harita işlecinin sağ tarafındaki haritaya eşitse **doğrudur;** aksi takdirde **yanlış**.

### <a name="remarks"></a>Açıklamalar

Eşlemi nesneleri arasındaki karşılaştırma, öğelerinin çift eşli bir karşılaştırmasını temel adatır. Aynı sayıda eleman varsa ve ilgili öğeleri aynı değerlere sahipse, iki eşeeşittir. Aksi takdirde, eşit değildir.

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
```

```Output
The maps m1 and m2 are not equal.
The maps m1 and m3 are equal.
```

## <a name="operatorgt"></a><a name="op_gt"></a>Işleç&gt;

İşleticinin sol tarafındaki harita nesnesinin sağ taraftaki harita nesnesinden büyük olup olmadığını test edin.

```cpp
bool operator>(
      const map <Key, Type, Traits, Allocator>& left,
      const map <Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*Sol*\
`map` türünün bir nesnesi.

*Doğru*\
`map` türünün bir nesnesi.

### <a name="return-value"></a>Dönüş Değeri

işlecinin sol tarafındaki harita işlecinin sağ tarafındaki haritadan büyükse **doğrudur;** aksi takdirde **yanlış**.

### <a name="remarks"></a>Açıklamalar

Eşlemi nesneleri arasındaki karşılaştırma, öğelerinin çift eşli bir karşılaştırmasını temel adatır. İki nesne arasındaki büyük-daha büyük ilişki eşit olmayan öğelerin ilk çifti bir karşılaştırma dayanmaktadır.

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

## <a name="operatorgt"></a><a name="op_gt_eq"></a>Işleç&gt;=

İşleticinin sol tarafındaki harita nesnesinin sağ taraftaki harita nesnesinden büyük veya eşit olup olmadığını test edin.

```cpp
bool operator>=(
      const map <Key, Type, Traits, Allocator>& left,
      const map <Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*Sol*\
`map` türünün bir nesnesi.

*Doğru*\
`map` türünün bir nesnesi.

### <a name="return-value"></a>Dönüş Değeri

işlecinin sol tarafındaki harita listenin sağ tarafındaki haritadan daha büyük veya eşitse **doğrudur;** aksi takdirde **yanlış**.

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
```

```Output
The map m1 is less than the map m2.
Map m1 is greater than or equal to map m3.
Map m1 is greater than or equal to map m4.
```

## <a name="operator-multimap"></a><a name="op_neq_multimap"></a>işleç!= (çok harita)

İşleticinin sol tarafındaki çok eşlilik nesnesinin sağ taraftaki çok eşli lik nesnesine eşit olup olmadığını test edin.

```cpp
bool operator!=(
      const multimap <Key, Type, Traits, Allocator>& left,
      const multimap <Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*Sol*\
`multimap` türünün bir nesnesi.

*Doğru*\
`multimap` türünün bir nesnesi.

### <a name="return-value"></a>Dönüş Değeri

çoklu haritalar eşit değilse **doğrudur;** çoklu haritalar **eşitse yanlış.**

### <a name="remarks"></a>Açıklamalar

Çok eşli nesneler arasındaki karşılaştırma, öğelerinin çift yönlü bir karşılaştırmasını temel adatır. İki çok eş, aynı sayıda elemana sahipse ve ilgili öğeleri aynı değerlere sahipse eşittir. Aksi takdirde, eşit değildir.

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
```

```Output
The multimaps m1 and m2 are not equal.
The multimaps m1 and m3 are equal.
```

## <a name="operatorlt"></a><a name="op_lt_multimap"></a>Işleç&lt;

İşleticinin sol tarafındaki çok eşlilik nesnesinin sağ taraftaki çok eşli lik nesnesinden küçük olup olmadığını test edin.

```cpp
bool operator<(
      const multimap <Key, Type, Traits, Allocator>& left,
      const multimap <Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*Sol*\
`multimap` türünün bir nesnesi.

*Doğru*\
`multimap` türünün bir nesnesi.

### <a name="return-value"></a>Dönüş Değeri

işlecinin sol tarafındaki çoklu harita, operatörün sağ tarafındaki çoklu haritadan kesinlikle daha azsa **doğrudur;** aksi takdirde **yanlış**.

### <a name="remarks"></a>Açıklamalar

Çok eşli nesneler arasındaki karşılaştırma, öğelerinin çift yönlü bir karşılaştırmasını temel adatır. İki nesne arasındaki az ilişki, eşit olmayan öğelerin ilk çiftinin karşılaştırılmasına dayanır.

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
```

```Output
The multimap m1 is less than the multimap m2.
The multimap m1 is not less than the multimap m3.
```

## <a name="operatorlt"></a><a name="op_lt_eq_multimap"></a>Işleç&lt;=

İşleticinin sol tarafındaki çok eşlilik nesnesinin sağ taraftaki çok eşlilik nesnesinden daha az veya eşit olup olmadığını test edin.

```cpp
bool operator<=(
      const multimap <Key, Type, Traits, Allocator>& left,
      const multimap <Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*Sol*\
`multimap` türünün bir nesnesi.

*Doğru*\
`multimap` türünün bir nesnesi.

### <a name="return-value"></a>Dönüş Değeri

işlecinin sol tarafındaki çoklu harita, işlecinin sağ tarafındaki çoklu haritadan daha az veya eşitse **doğrudur;** aksi takdirde **yanlış**.

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
```

```Output
m1 is less than or equal to m2
m1 is greater than m3
m1 is less than or equal to m4
```

## <a name="operator"></a><a name="op_eq_eq_multimap"></a>işleç==

İşleticinin sol tarafındaki çok eşlilik nesnesinin sağ taraftaki çok eşli lik nesnesine eşit olup olmadığını test edin.

```cpp
bool operator==(
      const multimap <Key, Type, Traits, Allocator>& left,
      const multimap <Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*Sol*\
`multimap` türünün bir nesnesi.

*Doğru*\
`multimap` türünün bir nesnesi.

### <a name="return-value"></a>Dönüş Değeri

işlecinin sol tarafındaki çoklu harita, işlecinin sağ tarafındaki çoklu haritaya eşitse **doğrudur;** aksi takdirde **yanlış**.

### <a name="remarks"></a>Açıklamalar

Çok eşli nesneler arasındaki karşılaştırma, öğelerinin çift yönlü bir karşılaştırmasını temel adatır. İki çok eş, aynı sayıda elemana sahipse ve ilgili öğeleri aynı değerlere sahipse eşittir. Aksi takdirde, eşit değildir.

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
```

```Output
m1 and m2 are not equal
m1 and m3 are equal
```

## <a name="operatorgt"></a><a name="op_gt_multimap"></a>Işleç&gt;

İşleticinin sol tarafındaki çok eşlilik nesnesinin sağ taraftaki çok eşli lik nesnesinden büyük olup olmadığını test edin.

```cpp
bool operator>(
      const multimap <Key, Type, Traits, Allocator>& left,
      const multimap <Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*Sol*\
`multimap` türünün bir nesnesi.

*Doğru*\
`multimap` türünün bir nesnesi.

### <a name="return-value"></a>Dönüş Değeri

işlecinin sol tarafındaki çoklu harita operatörün sağ tarafındaki çoklu haritadan büyükse **doğrudur;** aksi takdirde **yanlış**.

### <a name="remarks"></a>Açıklamalar

Çok eşli nesneler arasındaki karşılaştırma, öğelerinin çift yönlü bir karşılaştırmasını temel adatır. İki nesne arasındaki büyük-daha büyük ilişki eşit olmayan öğelerin ilk çifti bir karşılaştırma dayanmaktadır.

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
```

```Output
Multimap m1 is not greater than multimap m2.
The multimap m1 is greater than the multimap m3.
```

## <a name="operatorgt"></a><a name="op_gt_eq_multimap"></a>Işleç&gt;=

İşleticinin sol tarafındaki çok eşlilik nesnesinin sağ taraftaki çok eşli lik nesnesinden büyük veya eşit olup olmadığını test edin.

```cpp
bool operator>=(
      const multimap <Key, Type, Traits, Allocator>& left,
      const multimap <Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*Sol*\
`multimap` türünün bir nesnesi.

*Doğru*\
`multimap` türünün bir nesnesi.

### <a name="return-value"></a>Dönüş Değeri

işlecinin sol tarafındaki çoklu harita listenin sağ tarafındaki çoklu haritadan daha büyük veya eşitse **doğrudur;** aksi takdirde **yanlış**.

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
```

```Output
The multimap m1 is less than the multimap m2.
The multimap m1 is greater than or equal to the multimap m3.
The multimap m1 is greater than or equal to the multimap m4.
```
