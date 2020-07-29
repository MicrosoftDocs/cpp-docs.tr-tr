---
title: '&lt;unordered_map &gt; işleçleri'
ms.date: 11/04/2016
f1_keywords:
- unordered_map/std::operator!=
- unordered_map/std::operator==
ms.assetid: 9d5add0b-84bd-4a79-bd82-3f58b55145ed
ms.openlocfilehash: 6a22ccfaf77c3be524bf7127eac3d76c7be827ca
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87201862"
---
# <a name="ltunordered_mapgt-operators"></a>&lt;unordered_map &gt; işleçleri

|||||
|-|-|-|-|
|[işleç! =](#op_neq)|[işleç = =](#op_eq_eq)|[işleç! =](#op_neq_multimap)|[işleç = =](#op_eq_eq_multimap)|

## <a name="operator"></a><a name="op_neq"></a>işleç! =

İşlecin sol tarafındaki [unordered_map](../standard-library/unordered-map-class.md) nesnesinin sağ taraftaki unordered_map nesnesine eşit olup olmadığını sınar.

```cpp
bool operator!=(const unordered_map <Key, Type, Hash, Pred, Allocator>& left, const unordered_map <Key, Type, Hash, Pred, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*tarafta*\
`unordered_map` türünün bir nesnesi.

*Right*\
`unordered_map` türünün bir nesnesi.

### <a name="return-value"></a>Dönüş Değeri

**`true`** unordered_maps eşitse; **`false`** eşittir.

### <a name="remarks"></a>Açıklamalar

Unordered_map nesneleri arasındaki karşılaştırma, öğelerini depolayabilecekleri rastgele sıra tarafından etkilenmez. İki unordered_maps, aynı sayıda öğeye sahip olmaları ve bir kapsayıcıdaki öğelerin diğer kapsayıcıdaki öğelerin bir permütasyon olması halinde eşittir. Aksi takdirde, bunlar eşit değildir.

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

**Çıktıların**

`um1 != um2: true`

`um1 != um3: false`

`um2 != um3: true`

## <a name="operator"></a><a name="op_eq_eq"></a>işleç = =

İşlecin sol tarafındaki [unordered_map](../standard-library/unordered-map-class.md) nesnesinin sağ taraftaki unordered_map nesnesine eşit olup olmadığını sınar.

```cpp
bool operator==(const unordered_map <Key, Type, Hash, Pred, Allocator>& left, const unordered_map <Key, Type, Hash, Pred, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*tarafta*\
`unordered_map` türünün bir nesnesi.

*Right*\
`unordered_map` türünün bir nesnesi.

### <a name="return-value"></a>Dönüş Değeri

**`true`** unordered_maps eşitse; **`false`** eşit değilse.

### <a name="remarks"></a>Açıklamalar

Unordered_map nesneleri arasındaki karşılaştırma, öğelerini depolayabilecekleri rastgele sıra tarafından etkilenmez. İki unordered_maps, aynı sayıda öğeye sahip olmaları ve bir kapsayıcıdaki öğelerin diğer kapsayıcıdaki öğelerin bir permütasyon olması halinde eşittir. Aksi takdirde, bunlar eşit değildir.

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

**Çıktıların**

`um1 == um2: false`

`um1 == um3: true`

`um2 == um3: false`

## <a name="operator"></a><a name="op_neq_multimap"></a>işleç! =

İşlecin sol tarafındaki [unordered_multimap](../standard-library/unordered-multimap-class.md) nesnesinin sağ taraftaki unordered_multimap nesnesine eşit olup olmadığını sınar.

```cpp
bool operator!=(const unordered_multimap <Key, Type, Hash, Pred, Allocator>& left, const unordered_multimap <Key, Type, Hash, Pred, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*tarafta*\
`unordered_multimap` türünün bir nesnesi.

*Right*\
`unordered_multimap` türünün bir nesnesi.

### <a name="return-value"></a>Dönüş Değeri

**`true`** unordered_multimaps eşitse; **`false`** eşittir.

### <a name="remarks"></a>Açıklamalar

Unordered_multimap nesneleri arasındaki karşılaştırma, öğelerini depolayabilecekleri rastgele sıra tarafından etkilenmez. İki unordered_multimaps, aynı sayıda öğeye sahip olmaları ve bir kapsayıcıdaki öğelerin diğer kapsayıcıdaki öğelerin bir permütasyon olması halinde eşittir. Aksi halde eşit değildir.

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

**Çıktıların**

`um1 != um2: true`

`um1 != um3: false`

`um2 != um3: true`

## <a name="operator"></a><a name="op_eq_eq_multimap"></a>işleç = =

İşlecin sol tarafındaki [unordered_multimap](../standard-library/unordered-multimap-class.md) nesnesinin sağ taraftaki unordered_multimap nesnesine eşit olup olmadığını sınar.

```cpp
bool operator==(const unordered_multimap <Key, Type, Hash, Pred, Allocator>& left, const unordered_multimap <Key, Type, Hash, Pred, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*tarafta*\
`unordered_multimap` türünün bir nesnesi.

*Right*\
`unordered_multimap` türünün bir nesnesi.

### <a name="return-value"></a>Dönüş Değeri

**`true`** unordered_multimaps eşitse; **`false`** eşit değilse.

### <a name="remarks"></a>Açıklamalar

Unordered_multimap nesneleri arasındaki karşılaştırma, öğelerini depolayabilecekleri rastgele sıra tarafından etkilenmez. İki unordered_multimaps, aynı sayıda öğeye sahip olmaları ve bir kapsayıcıdaki öğelerin diğer kapsayıcıdaki öğelerin bir permütasyon olması halinde eşittir. Aksi takdirde, bunlar eşit değildir.

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

**Çıktıların**

`um1 == um2: false`

`um1 == um3: true`

`um2 == um3: false`

## <a name="see-also"></a>Ayrıca bkz.

[<unordered_map>](../standard-library/unordered-map.md)
