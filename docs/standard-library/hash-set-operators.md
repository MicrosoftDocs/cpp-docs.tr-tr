---
title: '&lt;hash_set&gt; işleçleri | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- hash_set/std::operator!=
- hash_set/std::operator==
dev_langs:
- C++
ms.assetid: 403d8e4e-0b3f-43fb-bc5a-8100c4f331c5
caps.latest.revision: 13
manager: ghogen
ms.openlocfilehash: 9db5096e93a5778682eb9e926ac2b44c334b6349
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="lthashsetgt-operators"></a>&lt;hash_set&gt; işleçleri

||||
|-|-|-|
|[operator!=](#op_neq)|[operator! = (hash_multiset)](#op_neq_hash_multiset)|[operator==](#op_eq_eq)|
|[operator == (hash_multiset)](#op_eq_eq_hash_multiset)|

## <a name="op_neq"></a>  operator! =

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set sınıfı](../standard-library/unordered-set-class.md).

Hash_set nesne işlecinin sol tarafındaki sağ tarafında hash_set nesnesine eşit değilse testleri.

```cpp
bool operator!=(const hash_set <Key, Traits, Allocator>& left, const hash_set <Key, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

`left` Türünde bir nesne `hash_set`.

`right` Türünde bir nesne `hash_set`.

### <a name="return-value"></a>Dönüş Değeri

**doğru** hash_sets eşit; değilse **false** hash_sets eşit olması durumunda.

### <a name="remarks"></a>Açıklamalar

Hash_set nesneleri arasındaki karşılaştırmayı ikili karşılaştırma kendi öğeler arasında temel alır. İki hash_sets aynı sayıda öğe varsa ve bunların ilgili öğeleri aynı değerlere eşittir. Aksi takdirde, bunlar eşit.

Üyeleri [< hash_map >](../standard-library/hash-map.md) ve [< hash_set >](../standard-library/hash-set.md) üstbilgi dosyaları olan [stdext Namespace](../standard-library/stdext-namespace.md).

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

## <a name="op_eq_eq"></a>  operator ==

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set sınıfı](../standard-library/unordered-set-class.md).

Hash_set nesne işlecinin sol tarafındaki sağ tarafında hash_set nesnesine eşitse testleri.

```cpp
bool operator!==(const hash_set <Key, Traits, Allocator>& left, const hash_set <Key, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

`left` Türünde bir nesne `hash_set`.

`right` Türünde bir nesne `hash_set`.

### <a name="return-value"></a>Dönüş Değeri

**doğru** hash_set işlecinin sol tarafındaki işlecinin sağ tarafında hash_set eşit; tersi durumda ise **false**.

### <a name="remarks"></a>Açıklamalar

Hash_set nesneleri arasındaki karşılaştırma öğelerini pairwise karşılaştırması hakkında temel alır. İki hash_sets aynı sayıda öğe varsa ve bunların ilgili öğeleri aynı değerlere eşittir. Aksi takdirde, bunlar eşit.

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

## <a name="neq_hash_multiset"></a>  operator! = (hash_multiset)

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set sınıfı](../standard-library/unordered-set-class.md).

Testleri işlecinin sol tarafındaki hash_multiset nesnesi sağ tarafında hash_multiset nesnesine eşit değil.

```cpp
bool operator!=(const hash_multiset <Key, Traits, Allocator>& left, const hash_multiset <Key, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

`left` Türünde bir nesne `hash_multiset`.

`right` Türünde bir nesne `hash_multiset`.

### <a name="return-value"></a>Dönüş Değeri

**doğru** hash_multisets eşit; değilse **false** hash_multisets eşit olması durumunda.

### <a name="remarks"></a>Açıklamalar

Hash_multiset nesneleri arasındaki karşılaştırmayı ikili karşılaştırma kendi öğeler arasında temel alır. İki hash_multisets aynı sayıda öğe varsa ve bunların ilgili öğeleri aynı değerlere eşittir. Aksi takdirde, bunlar eşit.

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

## <a name="eq_eq_hash_multiset"></a>  operator == (hash_multiset)

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set sınıfı](../standard-library/unordered-set-class.md).

Hash_multiset nesne işlecinin sol tarafındaki sağ tarafında hash_multiset nesnesine eşitse testleri.

```cpp
bool operator!==(const hash_multiset <Key, Traits, Allocator>& left, const hash_multiset <Key, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

`left` Türünde bir nesne `hash_multiset`.

`right` Türünde bir nesne `hash_multiset`.

### <a name="return-value"></a>Dönüş Değeri

**doğru** hash_multiset işlecinin sol tarafındaki işlecinin sağ tarafında hash_multiset eşit; tersi durumda ise **false**.

### <a name="remarks"></a>Açıklamalar

Hash_multiset nesneleri arasındaki karşılaştırma öğelerini pairwise karşılaştırması hakkında temel alır. İki hash_multisets aynı sayıda öğe varsa ve bunların ilgili öğeleri aynı değerlere eşittir. Aksi takdirde, bunlar eşit.

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
