---
title: '&lt;&gt;işleç ayarla'
ms.date: 03/27/2019
f1_keywords:
- set/std::operator!=
- set/std::operator&gt;
- set/std::operator&gt;=
- set/std::operator&lt;
- set/std::operator&lt;=
- set/std::operator==
ms.assetid: b4256ebc-c449-4688-95db-fced42d20d4d
helpviewer_keywords:
- std::operator!= (set)
- std::operator&gt; (set)
- std::operator&gt;= (set)
- std::operator&lt; (set)
- std::operator&lt;= (set)
- std::operator== (set)
ms.openlocfilehash: a3256b7d963feca75e4a975def0f6da77538d278
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87217512"
---
# <a name="ltsetgt-operators"></a>&lt;&gt;işleç ayarla

## <a name="operator-set"></a><a name="op_neq"></a>işleç! = (küme)

İşlecin sol tarafındaki küme nesnesinin, sağ taraftaki küme nesnesine eşit olup olmadığını sınar.

```cpp
bool operator!=(const set <Key, Traits, Allocator>& left, const set <Key, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*tarafta*\
`set` türünün bir nesnesi.

*Right*\
`set` türünün bir nesnesi.

### <a name="return-value"></a>Dönüş Değeri

**`true`** kümeler eşitse; **`false`** Eğer kümeler eşitse.

### <a name="remarks"></a>Açıklamalar

Küme nesneleri arasındaki karşılaştırma, öğeleri arasındaki ikili karşılaştırmayı temel alır. İki küme aynı sayıda öğeye sahip olmaları halinde eşittir ve ilgili öğeleri aynı değere sahiptir. Aksi takdirde, bunlar eşit değildir.

### <a name="example"></a>Örnek

```cpp
// set_op_ne.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main( )
{
   using namespace std;
   set <int> s1, s2, s3;
   int i;

   for ( i = 0 ; i < 3 ; i++ )
   {
      s1.insert ( i );
      s2.insert ( i * i );
      s3.insert ( i );
   }

   if ( s1 != s2 )
      cout << "The sets s1 and s2 are not equal." << endl;
   else
      cout << "The sets s1 and s2 are equal." << endl;

   if ( s1 != s3 )
      cout << "The sets s1 and s3 are not equal." << endl;
   else
      cout << "The sets s1 and s3 are equal." << endl;
}
/* Output:
The sets s1 and s2 are not equal.
The sets s1 and s3 are equal.
*/
```

## <a name="operatorlt-set"></a><a name="op_lt"></a>işleç &lt; (küme)

İşlecin sol tarafındaki küme nesnesinin, sağ taraftaki küme nesnesinden küçük olup olmadığını sınar.

```cpp
bool operator<(const set <Key, Traits, Allocator>& left, const set <Key, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*tarafta*\
`set` türünün bir nesnesi.

*Right*\
`set` türünün bir nesnesi.

### <a name="return-value"></a>Dönüş Değeri

**`true`** işlecin sol tarafındaki küme, işlecin sağ tarafındaki kümesinden tamamen daha küçüktür; Aksi takdirde **`false`** .

### <a name="remarks"></a>Açıklamalar

Küme nesneleri arasındaki karşılaştırma, öğelerinin ikili bir karşılaştırmasını temel alır. İki nesne arasındaki daha az ilişki, eşit olmayan öğelerin ilk çiftinin karşılaştırmasına dayalıdır.

### <a name="example"></a>Örnek

```cpp
// set_op_lt.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main( )
{
   using namespace std;
   set <int> s1, s2, s3;
   int i;

   for ( i = 0 ; i < 3 ; i++ )
   {
      s1.insert ( i );
      s2.insert ( i * i );
      s3.insert ( i - 1 );
   }

   if ( s1 < s2 )
      cout << "The set s1 is less than the set s2." << endl;
   else
      cout << "The set s1 is not less than the set s2." << endl;

   if ( s1 < s3 )
      cout << "The set s1 is less than the set s3." << endl;
   else
      cout << "The set s1 is not less than the set s3." << endl;
}
/* Output:
The set s1 is less than the set s2.
The set s1 is not less than the set s3.
*/
```

## <a name="operatorlt-set"></a><a name="op_lt_eq"></a>operator &lt; = (küme)

İşlecin sol tarafındaki küme nesnesinin, sağ taraftaki küme nesnesinden küçük veya ona eşit olup olmadığını sınar.

```cpp
bool operator!<=(const set <Key, Traits, Allocator>& left, const set <Key, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*tarafta*\
`set` türünün bir nesnesi.

*Right*\
`set` türünün bir nesnesi.

### <a name="return-value"></a>Dönüş Değeri

**`true`** işlecin sol tarafındaki küme, işlecin sağ tarafındaki ayarla değerinden küçükse veya eşitse, Aksi takdirde **`false`** .

### <a name="remarks"></a>Açıklamalar

Küme nesneleri arasındaki karşılaştırma, öğelerinin ikili bir karşılaştırmasını temel alır. İki nesne arasındaki en az veya daha fazla ilişki, eşit olmayan öğelerin ilk çiftinin karşılaştırmasına bağlıdır.

### <a name="example"></a>Örnek

```cpp
// set_op_le.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main( )
{
   using namespace std;
   set <int> s1, s2, s3, s4;
   int i;

   for ( i = 0 ; i < 3 ; i++ )
   {
      s1.insert ( i );
      s2.insert ( i * i );
      s3.insert ( i - 1 );
      s4.insert ( i );
   }

   if ( s1 <= s2 )
      cout << "Set s1 is less than or equal to the set s2." << endl;
   else
      cout << "The set s1 is greater than the set s2." << endl;

   if ( s1 <= s3 )
      cout << "Set s1 is less than or equal to the set s3." << endl;
   else
      cout << "The set s1 is greater than the set s3." << endl;

   if ( s1 <= s4 )
      cout << "Set s1 is less than or equal to the set s4." << endl;
   else
      cout << "The set s1 is greater than the set s4." << endl;
}
```

```Output
Set s1 is less than or equal to the set s2.
The set s1 is greater than the set s3.
Set s1 is less than or equal to the set s4.
```

## <a name="operator-set"></a><a name="op_eq_eq"></a>işleç = = (küme)

İşlecin sol tarafındaki küme nesnesinin, sağ taraftaki küme nesnesine eşit olup olmadığını sınar.

```cpp
bool operator!==(const set <Key, Traits, Allocator>& left, const set <Key, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*tarafta*\
`set` türünün bir nesnesi.

*Right*\
`set` türünün bir nesnesi.

### <a name="return-value"></a>Dönüş Değeri

**`true`** işlecin sol tarafındaki küme, işlecin sağ tarafındaki ayarlamaya eşitse; Aksi takdirde **`false`** .

### <a name="remarks"></a>Açıklamalar

Küme nesneleri arasındaki karşılaştırma, öğelerinin ikili bir karşılaştırmasını temel alır. İki küme aynı sayıda öğeye sahip olmaları halinde eşittir ve ilgili öğeleri aynı değere sahiptir. Aksi takdirde, bunlar eşit değildir.

### <a name="example"></a>Örnek

```cpp
// set_op_eq.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main( )
{
   using namespace std;
   set <int> s1, s2, s3;
   int i;

   for ( i = 0 ; i < 3 ; i++ )
   {
      s1.insert ( i );
      s2.insert ( i * i );
      s3.insert ( i );
   }

   if ( s1 == s2 )
      cout << "The sets s1 and s2 are equal." << endl;
   else
      cout << "The sets s1 and s2 are not equal." << endl;

   if ( s1 == s3 )
      cout << "The sets s1 and s3 are equal." << endl;
   else
      cout << "The sets s1 and s3 are not equal." << endl;
}
```

```Output
The sets s1 and s2 are not equal.
The sets s1 and s3 are equal.
```

## <a name="operatorgt-set"></a><a name="op_gt"></a>işleç &gt; (küme)

İşlecin sol tarafındaki küme nesnesinin, sağ taraftaki küme nesnesinden büyük olup olmadığını sınar.

```cpp
bool operator>(const set <Key, Traits, Allocator>& left, const set <Key, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*tarafta*\
`set` türünün bir nesnesi.

*Right*\
`set` türünün bir nesnesi.

### <a name="return-value"></a>Dönüş Değeri

**`true`** işlecin sol tarafındaki küme, işlecin sağ tarafındaki kümesinden büyükse; Aksi takdirde **`false`** .

### <a name="remarks"></a>Açıklamalar

Küme nesneleri arasındaki karşılaştırma, öğelerinin ikili bir karşılaştırmasını temel alır. İki nesne arasındaki büyüktür ilişkisi, eşit olmayan öğelerin ilk çiftinin karşılaştırmasını temel alır.

### <a name="example"></a>Örnek

```cpp
// set_op_gt.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main( )
{
   using namespace std;
   set <int> s1, s2, s3;
   int i;

   for ( i = 0 ; i < 3 ; i++ )
   {
      s1.insert ( i );
      s2.insert ( i * i );
      s3.insert ( i - 1 );
   }

   if ( s1 > s2 )
      cout << "The set s1 is greater than the set s2." << endl;
   else
      cout << "The set s1 is not greater than the set s2." << endl;

   if ( s1 > s3 )
      cout << "The set s1 is greater than the set s3." << endl;
   else
      cout << "The set s1 is not greater than the set s3." << endl;
}
/* Output:
The set s1 is not greater than the set s2.
The set s1 is greater than the set s3.
*/
```

## <a name="operatorgt-set"></a><a name="op_gt_eq"></a>operator &gt; = (küme)

İşlecin sol tarafındaki küme nesnesinin, sağ taraftaki küme nesnesinden büyük veya ona eşit olup olmadığını sınar.

```cpp
bool operator!>=(const set <Key, Traits, Allocator>& left, const set <Key, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*tarafta*\
`set` türünün bir nesnesi.

*Right*\
`set` türünün bir nesnesi.

### <a name="return-value"></a>Dönüş Değeri

**`true`** işlecin sol tarafındaki küme, listenin sağ tarafındaki ayarla değerinden büyükse veya bu değere eşitse; Aksi takdirde **`false`** .

### <a name="remarks"></a>Açıklamalar

Küme nesneleri arasındaki karşılaştırma, öğelerinin ikili bir karşılaştırmasını temel alır. İki nesne arasındaki en büyük veya daha fazla ilişki, eşit olmayan öğelerin ilk çiftinin karşılaştırmasına bağlıdır.

### <a name="example"></a>Örnek

```cpp
// set_op_ge.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main( )
{
   using namespace std;
   set <int> s1, s2, s3, s4;
   int i;

   for ( i = 0 ; i < 3 ; i++ )
   {
      s1.insert ( i );
      s2.insert ( i * i );
      s3.insert ( i - 1 );
      s4.insert ( i );
   }

   if ( s1 >= s2 )
      cout << "Set s1 is greater than or equal to set s2." << endl;
   else
      cout << "The set s1 is less than the set s2." << endl;

   if ( s1 >= s3 )
      cout << "Set s1 is greater than or equal to set s3." << endl;
   else
      cout << "The set s1 is less than the set s3." << endl;

   if ( s1 >= s4 )
      cout << "Set s1 is greater than or equal to set s4." << endl;
   else
      cout << "The set s1 is less than the set s4." << endl;
}
```

```Output
The set s1 is less than the set s2.
Set s1 is greater than or equal to set s3.
Set s1 is greater than or equal to set s4.
```

## <a name="operator-multiset"></a><a name="op_neq_multiset"></a>işleç! = (çoklu küme)

İşlecin sol tarafındaki çok kümeli nesnenin sağ taraftaki çoklu küme nesnesine eşit olup olmadığını sınar.

```cpp
bool operator!=(const multiset <Key, Traits, Allocator>& left, const multiset <Key, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*tarafta*\
`multiset` türünün bir nesnesi.

*Right*\
`multiset` türünün bir nesnesi.

### <a name="return-value"></a>Dönüş Değeri

**`true`** kümeler veya çoklu kümeler eşit değilse; **`false`** Eğer kümeler veya çoklu kümeler eşitse.

### <a name="remarks"></a>Açıklamalar

Çoklu küme nesneleri arasındaki karşılaştırma, öğeleri arasında ikili bir karşılaştırmayı temel alır. İki küme veya birden çok küme aynı sayıda öğeye sahip olmaları halinde eşittir ve ilgili öğeleri aynı değere sahiptir. Aksi takdirde, bunlar eşit değildir.

### <a name="example"></a>Örnek

```cpp
// multiset_op_ne.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main( )
{
   using namespace std;
   multiset <int> s1, s2, s3;
   int i;

   for ( i = 0 ; i < 3 ; i++ )
   {
      s1.insert ( i );
      s2.insert ( i * i );
      s3.insert ( i );
   }

   if ( s1 != s2 )
      cout << "The multisets s1 and s2 are not equal." << endl;
   else
      cout << "The multisets s1 and s2 are equal." << endl;

   if ( s1 != s3 )
      cout << "The multisets s1 and s3 are not equal." << endl;
   else
      cout << "The multisets s1 and s3 are equal." << endl;
}
```

```Output
The multisets s1 and s2 are not equal.
The multisets s1 and s3 are equal.
```

## <a name="operatorlt-multiset"></a><a name="op_lt_multiset"></a>işleç &lt; (çoklu küme)

İşlecin sol tarafındaki çok kümeli nesnenin sağ taraftaki çoklu küme nesnesinden küçük olup olmadığını sınar.

```cpp
bool operator<(const multiset <Key, Traits, Allocator>& left, const multiset <Key, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*tarafta*\
`multiset` türünün bir nesnesi.

*Right*\
`multiset` türünün bir nesnesi.

### <a name="return-value"></a>Dönüş Değeri

**`true`** işlecin sol tarafındaki çoklu küme, işlecin sağ tarafındaki çoklu kümeli tamamen daha küçüktür; Aksi takdirde **`false`** .

### <a name="remarks"></a>Açıklamalar

Çoklu küme nesneleri arasındaki karşılaştırma, öğelerinin ikili bir karşılaştırmasını temel alır. İki nesne arasındaki daha az ilişki, eşit olmayan öğelerin ilk çiftinin karşılaştırmasına dayalıdır.

### <a name="example"></a>Örnek

```cpp
// multiset_op_lt.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main( )
{
   using namespace std;
   multiset <int> s1, s2, s3;
   int i;

   for ( i = 0 ; i < 3 ; i++ )
   {
      s1.insert ( i );
      s2.insert ( i * i );
      s3.insert ( i - 1 );
   }

   if ( s1 < s2 )
      cout << "The multiset s1 is less than "
           << "the multiset s2." << endl;
   else
      cout << "The multiset s1 is not less than "
           << "the multiset s2." << endl;

   if ( s1 < s3 )
      cout << "The multiset s1 is less than "
           << "the multiset s3." << endl;
   else
      cout << "The multiset s1 is not less than "
           << "the multiset s3." << endl;
}
```

```Output
The multiset s1 is less than the multiset s2.
The multiset s1 is not less than the multiset s3.
```

## <a name="operatorlt-multiset"></a><a name="op_lt_eq_multiset"></a>operator &lt; = (çoklu küme)

İşlecin sol tarafındaki çok kümeli nesnenin sağ taraftaki çoklu küme nesnesine eşit veya ondan küçük olup olmadığını sınar.

```cpp
bool operator!<=(const multiset <Key, Traits, Allocator>& left, const multiset <Key, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*tarafta*\
`multiset` türünün bir nesnesi.

*Right*\
`multiset` türünün bir nesnesi.

### <a name="return-value"></a>Dönüş Değeri

**`true`** işlecin sol tarafındaki çoklu küme, işlecin sağ tarafındaki çok kümeli veya daha küçükse; Aksi takdirde **`false`** .

### <a name="remarks"></a>Açıklamalar

Çoklu küme nesneleri arasındaki karşılaştırma, öğelerinin ikili bir karşılaştırmasını temel alır. İki nesne arasındaki en az veya daha fazla ilişki, eşit olmayan öğelerin ilk çiftinin karşılaştırmasına bağlıdır.

### <a name="example"></a>Örnek

```cpp
// multiset_op_le.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main( )
{
   using namespace std;
   multiset <int> s1, s2, s3, s4;
   int i;

   for ( i = 0 ; i < 3 ; i++ )
   {
      s1.insert ( i );
      s2.insert ( i * i );
      s3.insert ( i - 1 );
      s4.insert ( i );
   }

   if ( s1 <= s2 )
      cout << "The multiset s1 is less than "
           << "or equal to the multiset s2." << endl;
   else
      cout << "The multiset s1 is greater than "
           << "the multiset s2." << endl;

   if ( s1 <= s3 )
      cout << "The multiset s1 is less than "
           << "or equal to the multiset s3." << endl;
   else
      cout << "The multiset s1 is greater than "
           << "the multiset s3." << endl;

   if ( s1 <= s4 )
      cout << "The multiset s1 is less than "
           << "or equal to the multiset s4." << endl;
   else
      cout << "The multiset s1 is greater than "
           << "the multiset s4." << endl;
}
```

```Output
The multiset s1 is less than or equal to the multiset s2.
The multiset s1 is greater than the multiset s3.
The multiset s1 is less than or equal to the multiset s4.
```

## <a name="operator-multiset"></a><a name="op_eq_eq_multiset"></a>işleç = = (çoklu küme)

İşlecin sol tarafındaki çok kümeli nesnenin sağ taraftaki çoklu küme nesnesine eşit olup olmadığını sınar.

```cpp
bool operator!==(const multiset <Key, Traits, Allocator>& left, const multiset <Key, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*tarafta*\
`multiset` türünün bir nesnesi.

*Right*\
`multiset` türünün bir nesnesi.

### <a name="return-value"></a>Dönüş Değeri

**`true`** işlecin sol tarafındaki çoklu küme, işlecin sağ tarafındaki çoklu kümeli birine eşitse; Aksi takdirde **`false`** .

### <a name="remarks"></a>Açıklamalar

Çoklu küme nesneleri arasındaki karşılaştırma, öğelerinin ikili bir karşılaştırmasını temel alır. İki küme veya birden çok küme aynı sayıda öğeye sahip olmaları halinde eşittir ve ilgili öğeleri aynı değere sahiptir. Aksi takdirde, bunlar eşit değildir.

### <a name="example"></a>Örnek

```cpp
// multiset_op_eq.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main( )
{
   using namespace std;
   multiset <int> s1, s2, s3;
   int i;

   for ( i = 0 ; i < 3 ; i++ )
   {
      s1.insert ( i );
      s2.insert ( i * i );
      s3.insert ( i );
   }

   if ( s1 == s2 )
      cout << "The multisets s1 and s2 are equal." << endl;
   else
      cout << "The multisets s1 and s2 are not equal." << endl;

   if ( s1 == s3 )
      cout << "The multisets s1 and s3 are equal." << endl;
   else
      cout << "The multisets s1 and s3 are not equal." << endl;
}
```

```Output
The multisets s1 and s2 are not equal.
The multisets s1 and s3 are equal.
```

## <a name="operatorgt-multiset"></a><a name="op_gt_multiset"></a>işleç &gt; (çoklu küme)

İşlecin sol tarafındaki çok kümeli nesnenin sağ taraftaki çoklu küme nesnesinden büyük olup olmadığını sınar.

```cpp
bool operator>(const multiset <Key, Traits, Allocator>& left, const multiset <Key, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*tarafta*\
`multiset` türünün bir nesnesi.

*Right*\
`multiset` türünün bir nesnesi.

### <a name="return-value"></a>Dönüş Değeri

**`true`** işlecin sol tarafındaki çoklu küme, işlecin sağ tarafındaki çoklu kümeli daha büyükse; Aksi takdirde **`false`** .

### <a name="remarks"></a>Açıklamalar

Çoklu küme nesneleri arasındaki karşılaştırma, öğelerinin ikili bir karşılaştırmasını temel alır. İki nesne arasındaki büyüktür ilişkisi, eşit olmayan öğelerin ilk çiftinin karşılaştırmasını temel alır.

### <a name="example"></a>Örnek

```cpp
// multiset_op_gt.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main( )
{
   using namespace std;
   multiset <int> s1, s2, s3;
   int i;

   for ( i = 0 ; i < 3 ; i++ )
   {
      s1.insert ( i );
      s2.insert ( i * i );
      s3.insert ( i - 1 );
   }

   if ( s1 > s2 )
      cout << "The multiset s1 is greater than "
           << "the multiset s2." << endl;
   else
      cout << "The multiset s1 is not greater "
           << "than the multiset s2." << endl;

   if ( s1 > s3 )
      cout << "The multiset s1 is greater than "
           << "the multiset s3." << endl;
   else
      cout << "The multiset s1 is not greater than "
           << "the multiset s3." << endl;
}
```

```Output
The multiset s1 is not greater than the multiset s2.
The multiset s1 is greater than the multiset s3.
```

## <a name="operatorgt-multiset"></a><a name="op_gt_eq_multiset"></a>operator &gt; = (çoklu küme)

İşlecin sol tarafındaki çok kümeli nesnenin sağ taraftaki çoklu küme nesnesinden büyük veya ona eşit olup olmadığını sınar.

```cpp
bool operator!>=(const multiset <Key, Traits, Allocator>& left, const multiset <Key, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*tarafta*\
`multiset` türünün bir nesnesi.

*Right*\
`multiset` türünün bir nesnesi.

### <a name="return-value"></a>Dönüş Değeri

**`true`** işlecin sol tarafındaki çoklu küme, listenin sağ tarafındaki çoklu kümeli daha büyükse veya buna eşitse; Aksi takdirde **`false`** .

### <a name="remarks"></a>Açıklamalar

Çoklu küme nesneleri arasındaki karşılaştırma, öğelerinin ikili bir karşılaştırmasını temel alır. İki nesne arasındaki en büyük veya daha fazla ilişki, eşit olmayan öğelerin ilk çiftinin karşılaştırmasına bağlıdır.

### <a name="example"></a>Örnek

```cpp
// multiset_op_ge.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main( )
{
   using namespace std;
   multiset <int> s1, s2, s3, s4;
   int i;

   for ( i = 0 ; i < 3 ; i++ )
   {
      s1.insert ( i );
      s2.insert ( i * i );
      s3.insert ( i - 1 );
      s4.insert ( i );
   }

   if ( s1 >= s2 )
      cout << "The multiset s1 is greater than "
           << "or equal to the multiset s2." << endl;
   else
      cout << "The multiset s1 is less than "
           << "the multiset s2." << endl;

   if ( s1 >= s3 )
      cout << "The multiset s1 is greater than "
           << "or equal to the multiset s3." << endl;
   else
      cout << "The multiset s1 is less than "
           << "the multiset s3." << endl;

   if ( s1 >= s4 )
      cout << "The multiset s1 is greater than "
           << "or equal to the multiset s4." << endl;
   else
      cout << "The multiset s1 is less than "
           << "the multiset s4." << endl;
}
```

```Output
The multiset s1 is less than the multiset s2.
The multiset s1 is greater than or equal to the multiset s3.
The multiset s1 is greater than or equal to the multiset s4.
```
