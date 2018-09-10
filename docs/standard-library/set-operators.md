---
title: '&lt;ayarlama&gt; işleçler | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- set/std::operator!=
- set/std::operator&gt;
- set/std::operator&gt;=
- set/std::operator&lt;
- set/std::operator&lt;=
- set/std::operator==
dev_langs:
- C++
ms.assetid: b4256ebc-c449-4688-95db-fced42d20d4d
helpviewer_keywords:
- std::operator!= (set)
- std::operator&gt; (set)
- std::operator&gt;= (set)
- std::operator&lt; (set)
- std::operator&lt;= (set)
- std::operator== (set)
ms.openlocfilehash: a90c7e2ea7af1200b3e6cfee895b69b29352fb21
ms.sourcegitcommit: f0c90000125a9497bf61e41624de189a043703c0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/10/2018
ms.locfileid: "44314877"
---
# <a name="ltsetgt-operators"></a>&lt;ayarlama&gt; işleçleri

||||
|-|-|-|
|[işleç! = (set)](#op_neq)|[İşleç&gt; (set)](#op_gt)|[İşleç&gt;= (set)](#eq)|
|[İşleç&lt; (set)](#op_lt)|[İşleç&lt;= (set)](#eq)|[işleç == (set)](#op_eq_eq)|
|[işleç! = (multiset)](#op_neq_multiset)|[İşleç&gt; (multiset)](#op_gt_multiset)|[İşleç&gt;= (multiset)](#op_gt_eq_multiset)|
|[İşleç&lt; (multiset)](#op_lt_multiset)|[İşleç&lt;= (multiset)](#op_lt_eq_multiset)|[işleç == (multiset)](#op_eq_eq_multiset)|

## <a name="op_neq"></a>  işleç! = (set)

İşlecin sol tarafındaki küme nesnesi kümesi nesnesinin işlecin sağ tarafındaki eşit olup olmadığını sınar.

```cpp
bool operator!=(const set <Key, Traits, Allocator>& left, const set <Key, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*Sol*<br/>
Bir nesne türü `set`.

*sağ*<br/>
Bir nesne türü `set`.

### <a name="return-value"></a>Dönüş Değeri

**doğru** kümeleri eşit; değilse, **false** kümeleri eşitse.

### <a name="remarks"></a>Açıklamalar

Küme nesneleri arasında karşılaştırma öğeleri arasında ikili bir karşılaştırma temel alır. Bunlar aynı sayıda öğe varsa ve ilgili öğeleri aynı değerlere sahip iki eşit olur. Aksi takdirde, eşit oldukları.

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

## <a name="op_lt"></a>  İşleç&lt; (set)

İşlecin sol tarafındaki küme nesnesi işlecin sağ tarafındaki kümesi nesneden küçük olup olmadığını sınar.

```cpp
bool operator<(const set <Key, Traits, Allocator>& left, const set <Key, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*Sol*<br/>
Bir nesne türü `set`.

*sağ*<br/>
Bir nesne türü `set`.

### <a name="return-value"></a>Dönüş Değeri

**doğru** işlecinin sol tarafındaki kümesi; işlecin sağ tarafındaki kümesi değerinden kesinlikle küçük ise, aksi takdirde **false**.

### <a name="remarks"></a>Açıklamalar

Küme nesneleri arasında karşılaştırma öğeleri üzerinde bir ikili karşılaştırma temel alır. Daha az-iki nesne arasındaki ilişki ilk çifti eşit olmayan öğelerin karşılaştırması üzerinde alan daha.

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

## <a name="op_lt_eq"></a>  İşleç&lt;= (set)

İşlecinin sol tarafında kümesi nesnesi küçük olup olmadığını sınar veya küme nesnesi eşit işlecin sağ tarafındaki.

```cpp
bool operator!<=(const set <Key, Traits, Allocator>& left, const set <Key, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*Sol*<br/>
Bir nesne türü `set`.

*sağ*<br/>
Bir nesne türü `set`.

### <a name="return-value"></a>Dönüş Değeri

**doğru** işlecinin sol tarafındaki küçük daha veya işlecin sağ tarafındaki kümesinde eşit; Aksi takdirde ayarlanırsa **false**.

### <a name="remarks"></a>Açıklamalar

Küme nesneleri arasında karşılaştırma öğeleri üzerinde bir ikili karşılaştırma temel alır. İki nesne arasındaki ilişki için daha az veya eşit ilk çifti eşit olmayan öğelerin karşılaştırması üzerinde temel alır.

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
/* Output:
Set s1 is less than or equal to the set s2.
The set s1 is greater than the set s3.
Set s1 is less than or equal to the set s4.
*/
```

## <a name="op_eq_eq"></a>  işleç == (set)

İşlecin sol tarafındaki kümesi nesne kümesi nesnesinin işlecin sağ tarafındaki eşit olup olmadığını sınar.

```cpp
bool operator!==(const set <Key, Traits, Allocator>& left, const set <Key, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*Sol*<br/>
Bir nesne türü `set`.

*sağ*<br/>
Bir nesne türü `set`.

### <a name="return-value"></a>Dönüş Değeri

**doğru** işlecinin sol tarafındaki kümesi ise, aksi takdirde işlecin sağ tarafındaki kümesinde eşit **false**.

### <a name="remarks"></a>Açıklamalar

Küme nesneleri arasında karşılaştırma öğeleri üzerinde bir ikili karşılaştırma temel alır. Bunlar aynı sayıda öğe varsa ve ilgili öğeleri aynı değerlere sahip iki eşit olur. Aksi takdirde, eşit oldukları.

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
/* Output:
The sets s1 and s2 are not equal.
The sets s1 and s3 are equal.
*/
```

## <a name="op_gt"></a>  İşleç&gt; (set)

İşlecin sol tarafındaki kümesi nesne kümesi nesnesinin işlecin sağ tarafındaki büyük olup olmadığını sınar.

```cpp
bool operator>(const set <Key, Traits, Allocator>& left, const set <Key, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*Sol*<br/>
Bir nesne türü `set`.

*sağ*<br/>
Bir nesne türü `set`.

### <a name="return-value"></a>Dönüş Değeri

**doğru** işlecinin sol tarafındaki ayarlanırsa işlecin sağ tarafındaki kümesinde büyüktür; Aksi takdirde **false**.

### <a name="remarks"></a>Açıklamalar

Küme nesneleri arasında karşılaştırma öğeleri üzerinde bir ikili karşılaştırma temel alır. Büyük-iki nesne arasındaki ilişki ilk çifti eşit olmayan öğelerin karşılaştırması üzerinde alan daha.

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

## <a name="op_gt_eq"></a>  İşleç&gt;= (set)

Küme nesnesi işlecinin sol tarafındaki büyük veya işlecin sağ tarafındaki kümesi nesneye eşit olup olmadığını sınar.

```cpp
bool operator!>=(const set <Key, Traits, Allocator>& left, const set <Key, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*Sol*<br/>
Bir nesne türü `set`.

*sağ*<br/>
Bir nesne türü `set`.

### <a name="return-value"></a>Dönüş Değeri

**doğru** işlecinin sol tarafındaki ayarlanırsa büyük veya eşit listenin sağ tarafında kümesine; tersi durumda **false**.

### <a name="remarks"></a>Açıklamalar

Küme nesneleri arasında karşılaştırma öğeleri üzerinde bir ikili karşılaştırma temel alır. Büyüktür veya eşittir iki nesne arasındaki ilişki için ilk çifti eşit olmayan öğelerin karşılaştırması üzerinde temel alır.

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
/* Output:
The set s1 is less than the set s2.
Set s1 is greater than or equal to set s3.
Set s1 is greater than or equal to set s4.
*/
```

## <a name="op_neq_multiset"></a>  işleç! = (multiset)

İşlecin sol tarafındaki multiset nesne işlecin sağ tarafındaki multiset nesneye eşit olup olmadığını sınar.

```cpp
bool operator!=(const multiset <Key, Traits, Allocator>& left, const multiset <Key, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*Sol*<br/>
Bir nesne türü `multiset`.

*sağ*<br/>
Bir nesne türü `multiset`.

### <a name="return-value"></a>Dönüş Değeri

**doğru** kümeleri veya multisets eşit; değilse, **false** kümeleri veya multisets eşitse.

### <a name="remarks"></a>Açıklamalar

Çok kümeli nesneler arasında karşılaştırma öğeleri arasında ikili bir karşılaştırma temel alır. Bunlar aynı sayıda öğe varsa ve ilgili öğeleri aynı değerlere sahip iki kümeleri veya multisets eşit olur. Aksi takdirde, eşit oldukları.

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
/* Output:
The multisets s1 and s2 are not equal.
The multisets s1 and s3 are equal.
*/
```

## <a name="op_lt_multiset"></a>  İşleç&lt; (multiset)

İşlecin sol tarafındaki multiset nesnesinin işlecin sağ tarafındaki multiset nesneden küçük olup olmadığını sınar.

```cpp
bool operator<(const multiset <Key, Traits, Allocator>& left, const multiset <Key, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*Sol*<br/>
Bir nesne türü `multiset`.

*sağ*<br/>
Bir nesne türü `multiset`.

### <a name="return-value"></a>Dönüş Değeri

**doğru** işlecinin sol tarafındaki multiset; işlecin sağ tarafındaki multiset değerinden kesinlikle küçük ise, aksi takdirde **false**.

### <a name="remarks"></a>Açıklamalar

Çok kümeli nesneler arasında karşılaştırma öğeleri üzerinde bir ikili karşılaştırma temel alır. Daha az-iki nesne arasındaki ilişki ilk çifti eşit olmayan öğelerin karşılaştırması üzerinde alan daha.

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
/* Output:
The multiset s1 is less than the multiset s2.
The multiset s1 is not less than the multiset s3.
*/
```

## <a name="op_lt_eq_multiset"></a>  İşleç&lt;= (multiset)

Multiset işlecinin sol tarafında nesne küçük olup olmadığını sınar veya çok kümeli nesneye eşitse işlecin sağ tarafındaki.

```cpp
bool operator!<=(const multiset <Key, Traits, Allocator>& left, const multiset <Key, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*Sol*<br/>
Bir nesne türü `multiset`.

*sağ*<br/>
Bir nesne türü `multiset`.

### <a name="return-value"></a>Dönüş Değeri

**doğru** işlecinin sol tarafındaki multiset daha veya işlecin sağ tarafındaki multiset eşit; Aksi takdirde küçükse **false**.

### <a name="remarks"></a>Açıklamalar

Çok kümeli nesneler arasında karşılaştırma öğeleri üzerinde bir ikili karşılaştırma temel alır. İki nesne arasındaki ilişki için daha az veya eşit ilk çifti eşit olmayan öğelerin karşılaştırması üzerinde temel alır.

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
/* Output:
The multiset s1 is less than or equal to the multiset s2.
The multiset s1 is greater than the multiset s3.
The multiset s1 is less than or equal to the multiset s4.
*/
```

## <a name="op_eq_eq_multiset"></a>  işleç == (multiset)

İşlecin sol tarafındaki multiset nesne işlecin sağ tarafındaki multiset nesneye eşit olup olmadığını sınar.

```cpp
bool operator!==(const multiset <Key, Traits, Allocator>& left, const multiset <Key, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*Sol*<br/>
Bir nesne türü `multiset`.

*sağ*<br/>
Bir nesne türü `multiset`.

### <a name="return-value"></a>Dönüş Değeri

**doğru** multiset işlecinin sol tarafındaki ise, aksi takdirde işlecin sağ tarafındaki multiset eşit **false**.

### <a name="remarks"></a>Açıklamalar

Çok kümeli nesneler arasında karşılaştırma öğeleri üzerinde bir ikili karşılaştırma temel alır. Bunlar aynı sayıda öğe varsa ve ilgili öğeleri aynı değerlere sahip iki kümeleri veya multisets eşit olur. Aksi takdirde, eşit oldukları.

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
/* Output:
The multisets s1 and s2 are not equal.
The multisets s1 and s3 are equal.
*/
```

## <a name="op_gt_multiset"></a>  İşleç&gt; (multiset)

İşlecin sol tarafındaki multiset nesne multiset nesnesinin işlecin sağ tarafındaki büyük olup olmadığını sınar.

```cpp
bool operator>(const multiset <Key, Traits, Allocator>& left, const multiset <Key, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*Sol*<br/>
Bir nesne türü `multiset`.

*sağ*<br/>
Bir nesne türü `multiset`.

### <a name="return-value"></a>Dönüş Değeri

**doğru** multiset işlecinin sol tarafındaki ise, aksi takdirde multiset işlecin sağ tarafındaki büyük **false**.

### <a name="remarks"></a>Açıklamalar

Çok kümeli nesneler arasında karşılaştırma öğeleri üzerinde bir ikili karşılaştırma temel alır. Büyük-iki nesne arasındaki ilişki ilk çifti eşit olmayan öğelerin karşılaştırması üzerinde alan daha.

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
/* Output:
The multiset s1 is not greater than the multiset s2.
The multiset s1 is greater than the multiset s3.
*/
```

## <a name="op_gt_eq_multiset"></a>  İşleç&gt;= (multiset)

İşlecin sol tarafındaki multiset nesnesinin değerinden büyük veya çok kümeli nesnesinin işlecin sağ tarafındaki eşit olup olmadığını sınar.

```cpp
bool operator!>=(const multiset <Key, Traits, Allocator>& left, const multiset <Key, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*Sol*<br/>
Bir nesne türü `multiset`.

*sağ*<br/>
Bir nesne türü `multiset`.

### <a name="return-value"></a>Dönüş Değeri

**doğru** işlecinin sol tarafındaki multiset büyüktür veya eşittir multiset listenin sağ tarafında; tersi durumda ise **false**.

### <a name="remarks"></a>Açıklamalar

Çok kümeli nesneler arasında karşılaştırma öğeleri üzerinde bir ikili karşılaştırma temel alır. Büyüktür veya eşittir iki nesne arasındaki ilişki için ilk çifti eşit olmayan öğelerin karşılaştırması üzerinde temel alır.

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
/* Output:
The multiset s1 is less than the multiset s2.
The multiset s1 is greater than or equal to the multiset s3.
The multiset s1 is greater than or equal to the multiset s4.
*/
```

## <a name="see-also"></a>Ayrıca bkz.

[\<kümesi >](../standard-library/set.md)<br/>
