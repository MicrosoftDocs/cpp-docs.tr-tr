---
title: '&lt;unordered_map&gt; operatörleri'
ms.date: 11/04/2016
f1_keywords:
- unordered_map/std::operator!=
- unordered_map/std::operator==
ms.assetid: 9d5add0b-84bd-4a79-bd82-3f58b55145ed
ms.openlocfilehash: f062c4fd0332525a8b8940d2d93df41df56d2baa
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373121"
---
# <a name="ltunordered_mapgt-operators"></a>&lt;unordered_map&gt; operatörleri

|||||
|-|-|-|-|
|[işleç!=](#op_neq)|[işleç==](#op_eq_eq)|[işleç!=](#op_neq_multimap)|[işleç==](#op_eq_eq_multimap)|

## <a name="operator"></a><a name="op_neq"></a>işleç!=

Işlecinin sol tarafındaki [unordered_map](../standard-library/unordered-map-class.md) nesnenin sağ taraftaki unordered_map nesneye eşit olup olmadığını test edin.

```cpp
bool operator!=(const unordered_map <Key, Type, Hash, Pred, Allocator>& left, const unordered_map <Key, Type, Hash, Pred, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*Sol*\
`unordered_map` türünün bir nesnesi.

*Doğru*\
`unordered_map` türünün bir nesnesi.

### <a name="return-value"></a>Dönüş Değeri

unordered_maps eşit değilse **doğrudur;** eşit sayılsalar **yanlış** olur.

### <a name="remarks"></a>Açıklamalar

unordered_map nesneler arasındaki karşılaştırma, öğelerini depoladıkları rasgele sırayla etkilenmez. İki unordered_maps aynı sayıda eleman varsa eşittir ve bir kaptaki elemanlar diğer kaptaki elementlerin permütasyonudur. Aksi takdirde, eşit değildir.

### <a name="example"></a>Örnek

```cpp
// unordered_map_op_ne.cpp
// compile by using: cl.exe /EHsc /nologo /W4 /MTd
#include <unordered_map>
#include <iostream>
#include <ios>

int main( )
{
   using namespace std;
   unordered_map<int, int> um1, um2, um3;

   for ( int i = 0 ; i < 3 ; ++i ) {
      um1.insert( make_pair( i+1, i ) );
      um1.insert( make_pair( i, i ) );

      um2.insert( make_pair( i, i+1 ) );
      um2.insert( make_pair( i, i ) );

      um3.insert( make_pair( i, i ) );
      um3.insert( make_pair( i+1, i ) );
   }

   cout << boolalpha;
   cout << "um1 != um2: " << (um1 != um2) << endl;
   cout << "um1 != um3: " << (um1 != um3) << endl;
   cout << "um2 != um3: " << (um2 != um3) << endl;
}
```

**Çıkış:**

`um1 != um2: true`

`um1 != um3: false`

`um2 != um3: true`

## <a name="operator"></a><a name="op_eq_eq"></a>işleç==

Işlecinin sol tarafındaki [unordered_map](../standard-library/unordered-map-class.md) nesnenin sağ taraftaki unordered_map nesneye eşit olup olmadığını test edin.

```cpp
bool operator==(const unordered_map <Key, Type, Hash, Pred, Allocator>& left, const unordered_map <Key, Type, Hash, Pred, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*Sol*\
`unordered_map` türünün bir nesnesi.

*Doğru*\
`unordered_map` türünün bir nesnesi.

### <a name="return-value"></a>Dönüş Değeri

unordered_maps eşitse **doğrudur;** eşit değilse **yanlış.**

### <a name="remarks"></a>Açıklamalar

unordered_map nesneler arasındaki karşılaştırma, öğelerini depoladıkları rasgele sırayla etkilenmez. İki unordered_maps aynı sayıda eleman varsa eşittir ve bir kaptaki elemanlar diğer kaptaki elementlerin permütasyonudur. Aksi takdirde, eşit değildir.

### <a name="example"></a>Örnek

```cpp
// unordered_map_op_eq.cpp
// compile by using: cl.exe /EHsc /nologo /W4 /MTd
#include <unordered_map>
#include <iostream>
#include <ios>

int main( )
{
   using namespace std;
   unordered_map<int, int> um1, um2, um3;

   for ( int i = 0 ; i < 3 ; ++i ) {
      um1.insert( make_pair( i+1, i ) );
      um1.insert( make_pair( i, i ) );

      um2.insert( make_pair( i, i+1 ) );
      um2.insert( make_pair( i, i ) );

      um3.insert( make_pair( i, i ) );
      um3.insert( make_pair( i+1, i ) );
   }

   cout << boolalpha;
   cout << "um1 == um2: " << (um1 == um2) << endl;
   cout << "um1 == um3: " << (um1 == um3) << endl;
   cout << "um2 == um3: " << (um2 == um3) << endl;
}
```

**Çıkış:**

`um1 == um2: false`

`um1 == um3: true`

`um2 == um3: false`

## <a name="operator"></a><a name="op_neq_multimap"></a>işleç!=

Işlecinin sol tarafındaki [unordered_multimap](../standard-library/unordered-multimap-class.md) nesnenin sağ taraftaki unordered_multimap nesneye eşit olup olmadığını test edin.

```cpp
bool operator!=(const unordered_multimap <Key, Type, Hash, Pred, Allocator>& left, const unordered_multimap <Key, Type, Hash, Pred, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*Sol*\
`unordered_multimap` türünün bir nesnesi.

*Doğru*\
`unordered_multimap` türünün bir nesnesi.

### <a name="return-value"></a>Dönüş Değeri

unordered_multimaps eşit değilse **doğrudur;** eşit sayılsalar **yanlış** olur.

### <a name="remarks"></a>Açıklamalar

unordered_multimap nesneler arasındaki karşılaştırma, öğelerini depoladıkları rasgele sırayla etkilenmez. İki unordered_multimaps aynı sayıda eleman varsa eşittir ve bir kaptaki elemanlar diğer kaptaki elementlerin permütasyonudur. Aksi takdirde, eşit değildir.

### <a name="example"></a>Örnek

```cpp
// unordered_multimap_op_ne.cpp
// compile by using: cl.exe /EHsc /nologo /W4 /MTd
#include <unordered_map>
#include <iostream>
#include <ios>

int main( )
{
   using namespace std;
   unordered_multimap<int, int> um1, um2, um3;

   for ( int i = 0 ; i < 3 ; ++i ) {
      um1.insert( make_pair( i, i ) );
      um1.insert( make_pair( i, i ) );

      um2.insert( make_pair( i, i ) );
      um2.insert( make_pair( i, i ) );
      um2.insert( make_pair( i, i ) );

      um3.insert( make_pair( i, i ) );
      um3.insert( make_pair( i, i ) );
   }

   cout << boolalpha;
   cout << "um1 != um2: " << (um1 != um2) << endl;
   cout << "um1 != um3: " << (um1 != um3) << endl;
   cout << "um2 != um3: " << (um2 != um3) << endl;
}
```

**Çıkış:**

`um1 != um2: true`

`um1 != um3: false`

`um2 != um3: true`

## <a name="operator"></a><a name="op_eq_eq_multimap"></a>işleç==

Işlecinin sol tarafındaki [unordered_multimap](../standard-library/unordered-multimap-class.md) nesnenin sağ taraftaki unordered_multimap nesneye eşit olup olmadığını test edin.

```cpp
bool operator==(const unordered_multimap <Key, Type, Hash, Pred, Allocator>& left, const unordered_multimap <Key, Type, Hash, Pred, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*Sol*\
`unordered_multimap` türünün bir nesnesi.

*Doğru*\
`unordered_multimap` türünün bir nesnesi.

### <a name="return-value"></a>Dönüş Değeri

unordered_multimaps eşitse **doğrudur;** eşit değilse **yanlış.**

### <a name="remarks"></a>Açıklamalar

unordered_multimap nesneler arasındaki karşılaştırma, öğelerini depoladıkları rasgele sırayla etkilenmez. İki unordered_multimaps aynı sayıda eleman varsa eşittir ve bir kaptaki elemanlar diğer kaptaki elementlerin permütasyonudur. Aksi takdirde, eşit değildir.

### <a name="example"></a>Örnek

```cpp
// unordered_multimap_op_eq.cpp
// compile by using: cl.exe /EHsc /nologo /W4 /MTd
#include <unordered_map>
#include <iostream>
#include <ios>

int main( )
{
   using namespace std;
   unordered_multimap<int, int> um1, um2, um3;

   for ( int i = 0 ; i < 3 ; ++i ) {
      um1.insert( make_pair( i, i ) );
      um1.insert( make_pair( i, i ) );

      um2.insert( make_pair( i, i ) );
      um2.insert( make_pair( i, i ) );
      um2.insert( make_pair( i, i ) );

      um3.insert( make_pair( i, i ) );
      um3.insert( make_pair( i, i ) );
   }

   cout << boolalpha;
   cout << "um1 == um2: " << (um1 == um2) << endl;
   cout << "um1 == um3: " << (um1 == um3) << endl;
   cout << "um2 == um3: " << (um2 == um3) << endl;
}
```

**Çıkış:**

`um1 == um2: false`

`um1 == um3: true`

`um2 == um3: false`

## <a name="see-also"></a>Ayrıca bkz.

[<unordered_map>](../standard-library/unordered-map.md)
