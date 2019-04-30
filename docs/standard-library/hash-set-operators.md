---
title: '&lt;hash_set&gt; işleçleri'
ms.date: 03/27/2019
f1_keywords:
- hash_set/std::operator!=
- hash_set/std::operator==
ms.assetid: 403d8e4e-0b3f-43fb-bc5a-8100c4f331c5
ms.openlocfilehash: 901070731d372904ae297a5360ec0da78d179468
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62405033"
---
# <a name="lthashsetgt-operators"></a>&lt;hash_set&gt; işleçleri

||||
|-|-|-|
|[operator!=](#op_neq)|[işleç! = (hash_multiset)](#op_neq_hash_multiset)|[operator==](#op_eq_eq)|
|[işleç == (hash_multiset)](#op_eq_eq_hash_multiset)|

## <a name="op_neq"></a>  işleç! =

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set sınıfı](../standard-library/unordered-set-class.md).

İşlecin sol tarafındaki hash_set nesne işlecin sağ tarafındaki hash_set nesneye eşit olup olmadığını sınar.

```cpp
bool operator!=(const hash_set <Key, Traits, Allocator>& left, const hash_set <Key, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*Sol*<br/>
Bir nesne türü `hash_set`.

*sağ*<br/>
Bir nesne türü `hash_set`.

### <a name="return-value"></a>Dönüş Değeri

**doğru** hash_sets eşit; değilse, **false** hash_sets eşitse.

### <a name="remarks"></a>Açıklamalar

Hash_set nesneleri arasında karşılaştırma öğeleri arasında ikili bir karşılaştırma temel alır. Bunlar aynı sayıda öğe varsa ve ilgili öğeleri aynı değerlere sahip iki hash_sets eşit olur. Aksi takdirde, eşit oldukları.

Üyeleri [< hash_map >](../standard-library/hash-map.md) ve [< hash_set >](../standard-library/hash-set.md) üstbilgi dosyalar, [stdext Namespace](../standard-library/stdext-namespace.md).

### <a name="example"></a>Örnek

```cpp
// hash_set_op_ne.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_set <int> hs1, hs2, hs3;
   int i;

   for ( i = 0 ; i < 3 ; i++ )
   {
      hs1.insert ( i );
      hs2.insert ( i * i );
      hs3.insert ( i );
   }

   if ( hs1 != hs2 )
      cout << "The hash_sets hs1 and hs2 are not equal." << endl;
   else
      cout << "The hash_sets hs1 and hs2 are equal." << endl;

   if ( hs1 != hs3 )
      cout << "The hash_sets hs1 and hs3 are not equal." << endl;
   else
      cout << "The hash_sets hs1 and hs3 are equal." << endl;
}
```

```Output
The hash_sets hs1 and hs2 are not equal.
The hash_sets hs1 and hs3 are equal.
```

## <a name="op_eq_eq"></a>  işleç ==

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set sınıfı](../standard-library/unordered-set-class.md).

İşlecin sol tarafındaki hash_set nesnesinin işlecin sağ tarafındaki hash_set nesneye eşit olup olmadığını sınar.

```cpp
bool operator!==(const hash_set <Key, Traits, Allocator>& left, const hash_set <Key, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*Sol*<br/>
Bir nesne türü `hash_set`.

*sağ*<br/>
Bir nesne türü `hash_set`.

### <a name="return-value"></a>Dönüş Değeri

**doğru** hash_set işlecinin sol tarafındaki ise, aksi takdirde işlecin sağ tarafındaki hash_set eşit **false**.

### <a name="remarks"></a>Açıklamalar

Hash_set nesneleri arasında karşılaştırma öğeleri üzerinde bir ikili karşılaştırma temel alır. Bunlar aynı sayıda öğe varsa ve ilgili öğeleri aynı değerlere sahip iki hash_sets eşit olur. Aksi takdirde, eşit oldukları.

### <a name="example"></a>Örnek

```cpp
// hash_set_op_eq.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_set <int> s1, s2, s3;
   int i;

   for ( i = 0 ; i < 3 ; i++ )
   {
      s1.insert ( i );
      s2.insert ( i * i );
      s3.insert ( i );
   }

   if ( s1 == s2 )
      cout << "The hash_sets s1 and s2 are equal." << endl;
   else
      cout << "The hash_sets s1 and s2 are not equal." << endl;

   if ( s1 == s3 )
      cout << "The hash_sets s1 and s3 are equal." << endl;
   else
      cout << "The hash_sets s1 and s3 are not equal." << endl;
}
```

```Output
The hash_sets s1 and s2 are not equal.
The hash_sets s1 and s3 are equal.
```

## <a name="op_neq_hash_multiset"></a>  işleç! = (hash_multiset)

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set sınıfı](../standard-library/unordered-set-class.md).

İşlecin sol tarafındaki hash_multiset nesne işlecin sağ tarafındaki hash_multiset nesneye eşit olup olmadığını sınar.

```cpp
bool operator!=(const hash_multiset <Key, Traits, Allocator>& left, const hash_multiset <Key, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*Sol*<br/>
Bir nesne türü `hash_multiset`.

*sağ*<br/>
Bir nesne türü `hash_multiset`.

### <a name="return-value"></a>Dönüş Değeri

**doğru** hash_multisets eşit; değilse, **false** hash_multisets eşitse.

### <a name="remarks"></a>Açıklamalar

Hash_multiset nesneleri arasında karşılaştırma öğeleri arasında ikili bir karşılaştırma temel alır. Bunlar aynı sayıda öğe varsa ve ilgili öğeleri aynı değerlere sahip iki hash_multisets eşit olur. Aksi takdirde, eşit oldukları.

### <a name="example"></a>Örnek

```cpp
// hashset_op_ne.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_multiset <int> hs1, hs2, hs3;
   int i;

   for ( i = 0 ; i < 3 ; i++ )
   {
      hs1.insert ( i );
      hs2.insert ( i * i );
      hs3.insert ( i );
   }

   if ( hs1 != hs2 )
      cout << "The hash_multisets hs1 and hs2 are not equal." << endl;
   else
      cout << "The hash_multisets hs1 and hs2 are equal." << endl;

   if ( hs1 != hs3 )
      cout << "The hash_multisets hs1 and hs3 are not equal." << endl;
   else
      cout << "The hash_multisets hs1 and hs3 are equal." << endl;
}
```

```Output
The hash_multisets hs1 and hs2 are not equal.
The hash_multisets hs1 and hs3 are equal.
```

## <a name="op_eq_eq_hash_multiset"></a>  işleç == (hash_multiset)

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set sınıfı](../standard-library/unordered-set-class.md).

İşlecin sol tarafındaki hash_multiset nesnesinin işlecin sağ tarafındaki hash_multiset nesneye eşit olup olmadığını sınar.

```cpp
bool operator!==(const hash_multiset <Key, Traits, Allocator>& left, const hash_multiset <Key, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*Sol*<br/>
Bir nesne türü `hash_multiset`.

*sağ*<br/>
Bir nesne türü `hash_multiset`.

### <a name="return-value"></a>Dönüş Değeri

**doğru** hash_multiset işlecinin sol tarafındaki ise, aksi takdirde işlecin sağ tarafındaki hash_multiset eşit **false**.

### <a name="remarks"></a>Açıklamalar

Hash_multiset nesneleri arasında karşılaştırma öğeleri üzerinde bir ikili karşılaştırma temel alır. Bunlar aynı sayıda öğe varsa ve ilgili öğeleri aynı değerlere sahip iki hash_multisets eşit olur. Aksi takdirde, eşit oldukları.

### <a name="example"></a>Örnek

```cpp
// hash_multiset_op_eq.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_multiset <int> s1, s2, s3;
   int i;

   for ( i = 0 ; i < 3 ; i++ )
   {
      s1.insert ( i );
      s2.insert ( i * i );
      s3.insert ( i );
   }

   if ( s1 == s2 )
      cout << "The hash_multisets s1 and s2 are equal." << endl;
   else
      cout << "The hash_multisets s1 and s2 are not equal." << endl;

   if ( s1 == s3 )
      cout << "The hash_multisets s1 and s2 are equal." << endl;
   else
      cout << "The hash_multisets s1 and s2 are not equal." << endl;
}
```

```Output
The hash_multisets s1 and s2 are not equal.
The hash_multisets s1 and s2 are equal.
```

## <a name="see-also"></a>Ayrıca bkz.

[<hash_set>](../standard-library/hash-set.md)<br/>
