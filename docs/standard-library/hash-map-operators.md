---
title: '&lt;hash_map&gt; operatörleri'
ms.date: 11/04/2016
f1_keywords:
- hash_map/std::operator!=
- hash_map/std::operator==
ms.assetid: 24b9bb9e-e983-4060-bce5-2c7c8161ee61
ms.openlocfilehash: ed143349f3afc7a27ad565c1cc929c6ecb5f6ad8
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375454"
---
# <a name="lthash_mapgt-operators"></a>&lt;hash_map&gt; operatörleri

|||
|-|-|
|[işleç!=](#op_neq)|[işleç!= (çok harita)](#op_neq_mm)|
|[işleç==](#op_eq_eq)|[operator== (çok harita)](#op_eq_eq_mm)|

## <a name="operator"></a><a name="op_neq"></a>işleç!=

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map Sınıf](unordered-map-class.md).

Işlecinin sol tarafındaki hash_map nesnenin sağ taraftaki hash_map nesneye eşit olmamasını test edin.

```cpp
bool operator!=(const hash_map <Key, Type, Traits, Allocator>& left, const hash_map <Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*Sol*\
`hash_map` türünün bir nesnesi.

*Doğru*\
`hash_map` türünün bir nesnesi.

### <a name="return-value"></a>Dönüş Değeri

hash_maps eşit değilse **doğrudur;** hash_maps **eşitse yanlış.**

### <a name="remarks"></a>Açıklamalar

hash_map nesneler arasındaki karşılaştırma, öğelerinin çift bir karşılaştırmasını temel adatır. İki hash_maps aynı sayıda öğeye sahipse ve ilgili öğeleri aynı değerlere sahipse eşittir. Aksi takdirde, eşit değildir.

[stdext Namespace](stdext-namespace.md)hash_map [<üyeleri>](hash-map.md) ve<hash_set [>](hash-set.md) üstbilgi dosyaları.

### <a name="example"></a>Örnek

```cpp
// hash_map_op_ne.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_map <int, int> hm1, hm2, hm3;
   int i;
   typedef pair <int, int> Int_Pair;

   for ( i = 0 ; i < 3 ; i++ )
   {
      hm1.insert ( Int_Pair ( i, i ) );
      hm2.insert ( Int_Pair ( i, i * i ) );
      hm3.insert ( Int_Pair ( i, i ) );
   }

   if ( hm1 != hm2 )
      cout << "The hash_maps hm1 and hm2 are not equal." << endl;
   else
      cout << "The hash_maps hm1 and hm2 are equal." << endl;

   if ( hm1 != hm3 )
      cout << "The hash_maps hm1 and hm3 are not equal." << endl;
   else
      cout << "The hash_maps hm1 and hm3 are equal." << endl;
}
```

```Output
The hash_maps hm1 and hm2 are not equal.
The hash_maps hm1 and hm3 are equal.
```

## <a name="operator"></a><a name="op_eq_eq"></a>işleç==

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map Sınıf](unordered-map-class.md).

Işlecinin sol tarafındaki hash_map nesnenin sağ taraftaki hash_map nesneye eşit olup olmadığını test edin.

```cpp
bool operator==(const hash_map <Key, Type, Traits, Allocator>& left, const hash_map <Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*Sol*\
`hash_map` türünün bir nesnesi.

*Doğru*\
`hash_map` türünün bir nesnesi.

### <a name="return-value"></a>Dönüş Değeri

**true** işlecinin sol tarafındaki hash_map işlecinin sağ tarafındaki hash_map eşitse; aksi takdirde **yanlış**.

### <a name="remarks"></a>Açıklamalar

hash_map nesneler arasındaki karşılaştırma, öğelerinin çift bir karşılaştırmasını temel adatır. İki hash_maps aynı sayıda öğeye sahipse ve ilgili öğeleri aynı değerlere sahipse eşittir. Aksi takdirde, eşit değildir.

### <a name="example"></a>Örnek

```cpp
// hash_map_op_eq.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_map <int, int> hm1, hm2, hm3;
   int i;
   typedef pair <int, int> Int_Pair;

   for ( i = 0 ; i < 3 ; i++ )
   {
      hm1.insert ( Int_Pair ( i, i ) );
      hm2.insert ( Int_Pair ( i, i * i ) );
      hm3.insert ( Int_Pair ( i, i ) );
   }

   if ( hm1 == hm2 )
      cout << "The hash_maps hm1 and hm2 are equal." << endl;
   else
      cout << "The hash_maps hm1 and hm2 are not equal." << endl;

   if ( hm1 == hm3 )
      cout << "The hash_maps hm1 and hm3 are equal." << endl;
   else
      cout << "The hash_maps hm1 and hm3 are not equal." << endl;
}
```

```Output
The hash_maps hm1 and hm2 are not equal.
The hash_maps hm1 and hm3 are equal.
```

## <a name="operator-hash_multimap"></a><a name="op_neq_mm"></a>işleç!= (hash_multimap)

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap Sınıf](unordered-multimap-class.md).

Işlecinin sol tarafındaki hash_multimap nesnenin sağ taraftaki hash_multimap nesneye eşit olmadığını test edin.

```cpp
bool operator!=(const hash_multimap <Key, Type, Traits, Allocator>& left, const hash_multimap <Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*Sol*\
`hash_multimap` türünün bir nesnesi.

*Doğru*\
`hash_multimap` türünün bir nesnesi.

### <a name="return-value"></a>Dönüş Değeri

hash_multimaps eşit değilse **doğrudur;** hash_multimaps **eşitse yanlış.**

### <a name="remarks"></a>Açıklamalar

hash_multimap nesneler arasındaki karşılaştırma, öğelerinin çift başına karşılaştırılmasına dayanır. İki hash_multimaps aynı sayıda elemanvarsa ve ilgili öğeleri aynı değerlere sahipse eşittir. Aksi takdirde, eşit değildir.

### <a name="example"></a>Örnek

```cpp
// hash_multimap_op_ne.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_multimap <int, int> hm1, hm2, hm3;
   int i;
   typedef pair <int, int> Int_Pair;

   for ( i = 0 ; i < 3 ; i++ )
   {
      hm1.insert ( Int_Pair ( i, i ) );
      hm2.insert ( Int_Pair ( i, i * i ) );
      hm3.insert ( Int_Pair ( i, i ) );
   }

   if ( hm1 != hm2 )
      cout << "The hash_multimaps hm1 and hm2 are not equal." << endl;
   else
      cout << "The hash_multimaps hm1 and hm2 are equal." << endl;

   if ( hm1 != hm3 )
      cout << "The hash_multimaps hm1 and hm3 are not equal." << endl;
   else
      cout << "The hash_multimaps hm1 and hm3 are equal." << endl;
}
```

```Output
The hash_multimaps hm1 and hm2 are not equal.
The hash_multimaps hm1 and hm3 are equal.
```

## <a name="operator--hash_multimap"></a><a name="op_eq_eq_mm"></a>işleç== (hash_multimap)

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap Sınıf](unordered-multimap-class.md).

Işlecinin sol tarafındaki hash_multimap nesnenin sağ taraftaki hash_multimap nesneye eşit olup olmadığını test edin.

```cpp
bool operator==(const hash_multimap <Key, Type, Traits, Allocator>& left, const hash_multimap <Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*Sol*\
`hash_multimap` türünün bir nesnesi.

*Doğru*\
`hash_multimap` türünün bir nesnesi.

### <a name="return-value"></a>Dönüş Değeri

**true** işlecinin sol tarafındaki hash_multimap işlecinin sağ tarafındaki hash_multimap eşitse; aksi takdirde **yanlış**.

### <a name="remarks"></a>Açıklamalar

hash_multimap nesneler arasındaki karşılaştırma, öğelerinin çift başına karşılaştırılmasına dayanır. İki hash_multimaps aynı sayıda elemanvarsa ve ilgili öğeleri aynı değerlere sahipse eşittir. Aksi takdirde, eşit değildir.

### <a name="example"></a>Örnek

```cpp
// hash_multimap_op_eq.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_multimap<int, int> hm1, hm2, hm3;
   int i;
   typedef pair<int, int> Int_Pair;

   for (i = 0; i < 3; i++)
   {
      hm1.insert(Int_Pair(i, i));
      hm2.insert(Int_Pair(i, i*i));
      hm3.insert(Int_Pair(i, i));
   }

   if ( hm1 == hm2 )
      cout << "The hash_multimaps hm1 and hm2 are equal." << endl;
   else
      cout << "The hash_multimaps hm1 and hm2 are not equal." << endl;

   if ( hm1 == hm3 )
      cout << "The hash_multimaps hm1 and hm3 are equal." << endl;
   else
      cout << "The hash_multimaps hm1 and hm3 are not equal." << endl;
}
```

```Output
The hash_multimaps hm1 and hm2 are not equal.
The hash_multimaps hm1 and hm3 are equal.
```

## <a name="see-also"></a>Ayrıca bkz.

[<hash_map>](hash-map.md)
