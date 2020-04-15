---
title: '&lt;hash_set&gt; operatörleri'
ms.date: 03/27/2019
f1_keywords:
- hash_set/std::operator!=
- hash_set/std::operator==
ms.assetid: 403d8e4e-0b3f-43fb-bc5a-8100c4f331c5
ms.openlocfilehash: 5830c9e459c0d778e85c5ab5900d39c3190df178
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368577"
---
# <a name="lthash_setgt-operators"></a>&lt;hash_set&gt; operatörleri

||||
|-|-|-|
|[işleç!=](#op_neq)|[işleç!= (hash_multiset)](#op_neq_hash_multiset)|[işleç==](#op_eq_eq)|
|[işleç== (hash_multiset)](#op_eq_eq_hash_multiset)|

## <a name="operator"></a><a name="op_neq"></a>işleç!=

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set Sınıf](../standard-library/unordered-set-class.md).

Işlecinin sol tarafındaki hash_set nesnenin sağ taraftaki hash_set nesneye eşit olmamasını test edin.

```cpp
bool operator!=(const hash_set <Key, Traits, Allocator>& left, const hash_set <Key, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*Sol*\
`hash_set` türünün bir nesnesi.

*Doğru*\
`hash_set` türünün bir nesnesi.

### <a name="return-value"></a>Dönüş Değeri

hash_sets eşit değilse **doğrudur;** hash_sets **eşitse yanlış.**

### <a name="remarks"></a>Açıklamalar

hash_set nesneler arasındaki karşılaştırma, öğeleri arasındaki çift eve karşılaştırmaya dayanır. İki hash_sets aynı sayıda elemana sahipse ve ilgili öğeleri aynı değerlere sahipse eşittir. Aksi takdirde, eşit değildir.

[<hash_map>](../standard-library/hash-map.md) ve<hash_set [>](../standard-library/hash-set.md) üstbilgi dosyaları [stdext Namespace](../standard-library/stdext-namespace.md)bulunmaktadır.

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

## <a name="operator"></a><a name="op_eq_eq"></a>işleç==

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set Sınıf](../standard-library/unordered-set-class.md).

Işlecinin sol tarafındaki hash_set nesnenin sağ taraftaki hash_set nesneye eşit olup olmadığını test edin.

```cpp
bool operator!==(const hash_set <Key, Traits, Allocator>& left, const hash_set <Key, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*Sol*\
`hash_set` türünün bir nesnesi.

*Doğru*\
`hash_set` türünün bir nesnesi.

### <a name="return-value"></a>Dönüş Değeri

işlecinin sol tarafındaki hash_set işlecinin sağ tarafındaki hash_set eşitse **doğrudur;** aksi takdirde **yanlış**.

### <a name="remarks"></a>Açıklamalar

hash_set nesneler arasındaki karşılaştırma, öğelerinin çift bir karşılaştırmadayanmaktadır. İki hash_sets aynı sayıda elemana sahipse ve ilgili öğeleri aynı değerlere sahipse eşittir. Aksi takdirde, eşit değildir.

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

## <a name="operator-hash_multiset"></a><a name="op_neq_hash_multiset"></a>işleç!= (hash_multiset)

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set Sınıf](../standard-library/unordered-set-class.md).

Işlecinin sol tarafındaki hash_multiset nesnenin sağ taraftaki hash_multiset nesneye eşit olmamasını test edin.

```cpp
bool operator!=(const hash_multiset <Key, Traits, Allocator>& left, const hash_multiset <Key, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*Sol*\
`hash_multiset` türünün bir nesnesi.

*Doğru*\
`hash_multiset` türünün bir nesnesi.

### <a name="return-value"></a>Dönüş Değeri

hash_multisets eşit değilse **doğrudur;** hash_multisets **eşitse yanlış.**

### <a name="remarks"></a>Açıklamalar

hash_multiset nesneler arasındaki karşılaştırma, öğeleri arasındaki çift eve karşılaştırmaya dayanır. İki hash_multisets aynı sayıda öğeye sahipse ve ilgili öğeleri aynı değerlere sahipse eşittir. Aksi takdirde, eşit değildir.

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

## <a name="operator-hash_multiset"></a><a name="op_eq_eq_hash_multiset"></a>işleç== (hash_multiset)

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set Sınıf](../standard-library/unordered-set-class.md).

Işlecinin sol tarafındaki hash_multiset nesnenin sağ taraftaki hash_multiset nesneye eşit olup olmadığını test edin.

```cpp
bool operator!==(const hash_multiset <Key, Traits, Allocator>& left, const hash_multiset <Key, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*Sol*\
`hash_multiset` türünün bir nesnesi.

*Doğru*\
`hash_multiset` türünün bir nesnesi.

### <a name="return-value"></a>Dönüş Değeri

işlecinin sol tarafındaki hash_multiset işlecinin sağ tarafındaki hash_multiset eşitse **doğrudur;** aksi takdirde **yanlış**.

### <a name="remarks"></a>Açıklamalar

hash_multiset nesneler arasındaki karşılaştırma, öğelerinin çift bir karşılaştırmadayanmaktadır. İki hash_multisets aynı sayıda öğeye sahipse ve ilgili öğeleri aynı değerlere sahipse eşittir. Aksi takdirde, eşit değildir.

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
