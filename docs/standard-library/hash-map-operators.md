---
description: 'Daha fazla bilgi edinin: &lt; hash_map &gt; işleçleri'
title: '&lt;hash_map &gt; işleçleri'
ms.date: 11/04/2016
f1_keywords:
- hash_map/std::operator!=
- hash_map/std::operator==
ms.assetid: 24b9bb9e-e983-4060-bce5-2c7c8161ee61
ms.openlocfilehash: f3374ee86a989a90add86e85d6a9bf15959e26b4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97324128"
---
# <a name="lthash_mapgt-operators"></a>&lt;hash_map &gt; işleçleri

[işleç! =](#op_neq)\
[işleç! = (multimap)](#op_neq_mm)\
[işleç = =](#op_eq_eq)\
[işleç = = (multimap)](#op_eq_eq_mm)

## <a name="operator"></a><a name="op_neq"></a> işleç! =

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map sınıfıdır](unordered-map-class.md).

İşlecin sol tarafındaki hash_map nesnesinin sağ taraftaki hash_map nesnesine eşit olup olmadığını sınar.

```cpp
bool operator!=(const hash_map <Key, Type, Traits, Allocator>& left, const hash_map <Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*tarafta*\
`hash_map` türünün bir nesnesi.

*Right*\
`hash_map` türünün bir nesnesi.

### <a name="return-value"></a>Dönüş Değeri

**`true`** hash_maps eşitse; **`false`** hash_maps eşitse.

### <a name="remarks"></a>Açıklamalar

Hash_map nesneler arasındaki karşılaştırma, öğelerinin ikili bir karşılaştırmasını temel alır. İki hash_maps, aynı sayıda öğe varsa ve ilgili öğeleri aynı değere sahip olduğunda eşittir. Aksi takdirde, bunlar eşit değildir.

[<üyeleri hash_map>](hash-map.md) ve hash_set üst bilgi [ad alanındaki](stdext-namespace.md) [<](hash-set.md)>.

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

## <a name="operator"></a><a name="op_eq_eq"></a> işleç = =

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map sınıfıdır](unordered-map-class.md).

İşlecin sol tarafındaki hash_map nesnesinin sağ taraftaki hash_map nesnesine eşit olup olmadığını sınar.

```cpp
bool operator==(const hash_map <Key, Type, Traits, Allocator>& left, const hash_map <Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*tarafta*\
`hash_map` türünün bir nesnesi.

*Right*\
`hash_map` türünün bir nesnesi.

### <a name="return-value"></a>Dönüş Değeri

**`true`** işlecin sol tarafındaki hash_map, işlecin sağ tarafındaki hash_map eşitse; Aksi takdirde **`false`** .

### <a name="remarks"></a>Açıklamalar

Hash_map nesneler arasındaki karşılaştırma, öğelerinin ikili bir karşılaştırmasını temel alır. İki hash_maps, aynı sayıda öğe varsa ve ilgili öğeleri aynı değere sahip olduğunda eşittir. Aksi takdirde, bunlar eşit değildir.

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

## <a name="operator-hash_multimap"></a><a name="op_neq_mm"></a> işleç! = (hash_multimap)

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfıdır](unordered-multimap-class.md).

İşlecin sol tarafındaki hash_multimap nesnesinin sağ taraftaki hash_multimap nesnesine eşit olup olmadığını sınar.

```cpp
bool operator!=(const hash_multimap <Key, Type, Traits, Allocator>& left, const hash_multimap <Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*tarafta*\
`hash_multimap` türünün bir nesnesi.

*Right*\
`hash_multimap` türünün bir nesnesi.

### <a name="return-value"></a>Dönüş Değeri

**`true`** hash_multimaps eşitse; **`false`** hash_multimaps eşitse.

### <a name="remarks"></a>Açıklamalar

Hash_multimap nesneler arasındaki karşılaştırma, öğelerinin ikili bir karşılaştırmasını temel alır. İki hash_multimaps, aynı sayıda öğe varsa ve ilgili öğeleri aynı değere sahip olduğunda eşittir. Aksi takdirde, bunlar eşit değildir.

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

## <a name="operator--hash_multimap"></a><a name="op_eq_eq_mm"></a> işleç = = (hash_multimap)

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfıdır](unordered-multimap-class.md).

İşlecin sol tarafındaki hash_multimap nesnesinin sağ taraftaki hash_multimap nesnesine eşit olup olmadığını sınar.

```cpp
bool operator==(const hash_multimap <Key, Type, Traits, Allocator>& left, const hash_multimap <Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*tarafta*\
`hash_multimap` türünün bir nesnesi.

*Right*\
`hash_multimap` türünün bir nesnesi.

### <a name="return-value"></a>Dönüş Değeri

**`true`** işlecin sol tarafındaki hash_multimap, işlecin sağ tarafındaki hash_multimap eşitse; Aksi takdirde **`false`** .

### <a name="remarks"></a>Açıklamalar

Hash_multimap nesneler arasındaki karşılaştırma, öğelerinin ikili bir karşılaştırmasını temel alır. İki hash_multimaps, aynı sayıda öğe varsa ve ilgili öğeleri aynı değere sahip olduğunda eşittir. Aksi takdirde, bunlar eşit değildir.

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
