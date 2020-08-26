---
title: '&lt;hash_set &gt; işleçleri'
ms.date: 03/27/2019
f1_keywords:
- hash_set/std::operator!=
- hash_set/std::operator==
ms.assetid: 403d8e4e-0b3f-43fb-bc5a-8100c4f331c5
ms.openlocfilehash: 04b662ea260ca650fc51b17c804594fe25434f61
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88845802"
---
# <a name="lthash_setgt-operators"></a>&lt;hash_set &gt; işleçleri

[işleç! =](#op_neq)\
[işleç! = (hash_multiset)](#op_neq_hash_multiset)\
[işleç = =](#op_eq_eq)\
[işleç = = (hash_multiset)](#op_eq_eq_hash_multiset)

## <a name="operator"></a><a name="op_neq"></a> işleç! =

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set sınıfıdır](../standard-library/unordered-set-class.md).

İşlecin sol tarafındaki hash_set nesnesinin sağ taraftaki hash_set nesnesine eşit olup olmadığını sınar.

```cpp
bool operator!=(const hash_set <Key, Traits, Allocator>& left, const hash_set <Key, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*tarafta*\
`hash_set` türünün bir nesnesi.

*Right*\
`hash_set` türünün bir nesnesi.

### <a name="return-value"></a>Dönüş Değeri

**`true`** hash_sets eşitse; **`false`** hash_sets eşitse.

### <a name="remarks"></a>Açıklamalar

Hash_set nesneler arasındaki karşılaştırma, öğeleri arasındaki ikili karşılaştırmayı temel alır. İki hash_sets, aynı sayıda öğe varsa ve ilgili öğeleri aynı değere sahip olduğunda eşittir. Aksi takdirde, bunlar eşit değildir.

[<hash_map>](../standard-library/hash-map.md) ve [<hash_set](../standard-library/hash-set.md) üst bilgi dosyalarının üyeleri, [stdext ad alanında](../standard-library/stdext-namespace.md)yer alan.

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

## <a name="operator"></a><a name="op_eq_eq"></a> işleç = =

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set sınıfıdır](../standard-library/unordered-set-class.md).

İşlecin sol tarafındaki hash_set nesnesinin sağ taraftaki hash_set nesnesine eşit olup olmadığını sınar.

```cpp
bool operator!==(const hash_set <Key, Traits, Allocator>& left, const hash_set <Key, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*tarafta*\
`hash_set` türünün bir nesnesi.

*Right*\
`hash_set` türünün bir nesnesi.

### <a name="return-value"></a>Dönüş Değeri

**`true`** işlecin sol tarafındaki hash_set, işlecin sağ tarafındaki hash_set eşitse; Aksi takdirde **`false`** .

### <a name="remarks"></a>Açıklamalar

Hash_set nesneler arasındaki karşılaştırma, öğelerinin ikili bir karşılaştırmasını temel alır. İki hash_sets, aynı sayıda öğe varsa ve ilgili öğeleri aynı değere sahip olduğunda eşittir. Aksi takdirde, bunlar eşit değildir.

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

## <a name="operator-hash_multiset"></a><a name="op_neq_hash_multiset"></a> işleç! = (hash_multiset)

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set sınıfıdır](../standard-library/unordered-set-class.md).

İşlecin sol tarafındaki hash_multiset nesnesinin sağ taraftaki hash_multiset nesnesine eşit olup olmadığını sınar.

```cpp
bool operator!=(const hash_multiset <Key, Traits, Allocator>& left, const hash_multiset <Key, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*tarafta*\
`hash_multiset` türünün bir nesnesi.

*Right*\
`hash_multiset` türünün bir nesnesi.

### <a name="return-value"></a>Dönüş Değeri

**`true`** hash_multisets eşitse; **`false`** hash_multisets eşitse.

### <a name="remarks"></a>Açıklamalar

Hash_multiset nesneler arasındaki karşılaştırma, öğeleri arasındaki ikili karşılaştırmayı temel alır. İki hash_multisets, aynı sayıda öğe varsa ve ilgili öğeleri aynı değere sahip olduğunda eşittir. Aksi takdirde, bunlar eşit değildir.

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

## <a name="operator-hash_multiset"></a><a name="op_eq_eq_hash_multiset"></a> işleç = = (hash_multiset)

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set sınıfıdır](../standard-library/unordered-set-class.md).

İşlecin sol tarafındaki hash_multiset nesnesinin sağ taraftaki hash_multiset nesnesine eşit olup olmadığını sınar.

```cpp
bool operator!==(const hash_multiset <Key, Traits, Allocator>& left, const hash_multiset <Key, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*tarafta*\
`hash_multiset` türünün bir nesnesi.

*Right*\
`hash_multiset` türünün bir nesnesi.

### <a name="return-value"></a>Dönüş Değeri

**`true`** işlecin sol tarafındaki hash_multiset, işlecin sağ tarafındaki hash_multiset eşitse; Aksi takdirde **`false`** .

### <a name="remarks"></a>Açıklamalar

Hash_multiset nesneler arasındaki karşılaştırma, öğelerinin ikili bir karşılaştırmasını temel alır. İki hash_multisets, aynı sayıda öğe varsa ve ilgili öğeleri aynı değere sahip olduğunda eşittir. Aksi takdirde, bunlar eşit değildir.

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

[<hash_set>](../standard-library/hash-set.md)
