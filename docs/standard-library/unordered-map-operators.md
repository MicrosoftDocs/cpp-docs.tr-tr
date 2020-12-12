---
description: 'Daha fazla bilgi edinin: &lt; unordered_map &gt; işleçleri'
title: '&lt;unordered_map &gt; işleçleri'
ms.date: 11/04/2016
f1_keywords:
- unordered_map/std::operator!=
- unordered_map/std::operator==
ms.assetid: 9d5add0b-84bd-4a79-bd82-3f58b55145ed
ms.openlocfilehash: b7bf3712a7068b3af2d8316249d169854401b93e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97321484"
---
# <a name="ltunordered_mapgt-operators"></a>&lt;unordered_map &gt; işleçleri

[unordered_map:: operator! =](#op_neq)\
[unordered_map:: operator = =](#op_eq_eq)\
[unordered_multimap:: operator! =](#op_neq_multimap)\
[unordered_multimap:: operator = =](#op_eq_eq_multimap)

## <a name="operator"></a><a name="op_neq"></a> işleç! =

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

/* Output:
um1 != um2: true
um1 != um3: false
um2 != um3: true
*/
```

## <a name="operator"></a><a name="op_eq_eq"></a> işleç = =

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

/* Output:
um1 == um2: false
um1 == um3: true
um2 == um3: false
*/
```

## <a name="operator-multimap"></a><a name="op_neq_multimap"></a> işleç! = (multimap)

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

/* Output:
um1 != um2: true
um1 != um3: false
um2 != um3: true
*/
```

## <a name="operator-multimap"></a><a name="op_eq_eq_multimap"></a> işleç = = (multimap)

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

/* Output:
um1 == um2: false
um1 == um3: true
um2 == um3: false
*/
```

## <a name="see-also"></a>Ayrıca bkz.

[<unordered_map>](../standard-library/unordered-map.md)
