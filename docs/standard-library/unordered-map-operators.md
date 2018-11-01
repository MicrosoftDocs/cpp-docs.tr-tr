---
title: '&lt;unordered_map&gt; işleçleri'
ms.date: 11/04/2016
f1_keywords:
- unordered_map/std::operator!=
- unordered_map/std::operator==
ms.assetid: 9d5add0b-84bd-4a79-bd82-3f58b55145ed
ms.openlocfilehash: 280b9c866c17d69bca21ed6685f67f9fe986d45a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50480411"
---
# <a name="ltunorderedmapgt-operators"></a>&lt;unordered_map&gt; işleçleri

|||||
|-|-|-|-|
|[operator!=](#op_neq)|[operator==](#op_eq_eq)|[operator!=](#op_neq_multimap)|[operator==](#op_eq_eq_multimap)|

## <a name="op_neq"></a>  işleç! =

Testleri olmadığını [unordered_map](../standard-library/unordered-map-class.md) işlecinin sol tarafındaki nesne unordered_map nesnesinin işlecin sağ tarafındaki eşit değil.

```cpp
bool operator!=(const unordered_map <Key, Type, Hash, Pred, Allocator>& left, const unordered_map <Key, Type, Hash, Pred, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*Sol*<br/>
Bir nesne türü `unordered_map`.

*sağ*<br/>
Bir nesne türü `unordered_map`.

### <a name="return-value"></a>Dönüş Değeri

**doğru** unordered_maps eşit; değilse, **false** eşit olmaları durumunda.

### <a name="remarks"></a>Açıklamalar

Unordered_map nesneler arasında karşılaştırma öğeleri depoladıkları rastgele sıralama etkilenmez. Bunlar aynı sayıda öğe varsa ve diğer kapsayıcı öğeleri bir sıralamaya öğeler bir kapsayıcıdaki iki unordered_maps eşit olur. Aksi takdirde, eşit oldukları.

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

## <a name="op_eq_eq"></a>  işleç ==

Testleri olmadığını [unordered_map](../standard-library/unordered-map-class.md) işlecin sol tarafındaki nesnesinin işlecin sağ tarafındaki unordered_map nesneye eşit olup.

```cpp
bool operator==(const unordered_map <Key, Type, Hash, Pred, Allocator>& left, const unordered_map <Key, Type, Hash, Pred, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*Sol*<br/>
Bir nesne türü `unordered_map`.

*sağ*<br/>
Bir nesne türü `unordered_map`.

### <a name="return-value"></a>Dönüş Değeri

**doğru** unordered_maps eşitse; **false** eşit değilse.

### <a name="remarks"></a>Açıklamalar

Unordered_map nesneler arasında karşılaştırma öğeleri depoladıkları rastgele sıralama etkilenmez. Bunlar aynı sayıda öğe varsa ve diğer kapsayıcı öğeleri bir sıralamaya öğeler bir kapsayıcıdaki iki unordered_maps eşit olur. Aksi takdirde, eşit oldukları.

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

## <a name="op_neq_multimap"></a>  işleç! =

Testleri olmadığını [unordered_multimap](../standard-library/unordered-multimap-class.md) işlecinin sol tarafındaki nesne unordered_multimap nesnesinin işlecin sağ tarafındaki eşit değil.

```cpp
bool operator!=(const unordered_multimap <Key, Type, Hash, Pred, Allocator>& left, const unordered_multimap <Key, Type, Hash, Pred, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*Sol*<br/>
Bir nesne türü `unordered_multimap`.

*sağ*<br/>
Bir nesne türü `unordered_multimap`.

### <a name="return-value"></a>Dönüş Değeri

**doğru** unordered_multimaps eşit; değilse, **false** eşit olmaları durumunda.

### <a name="remarks"></a>Açıklamalar

Unordered_multimap nesneler arasında karşılaştırma öğeleri depoladıkları rastgele sıralama etkilenmez. Bunlar aynı sayıda öğe varsa ve diğer kapsayıcı öğeleri bir sıralamaya öğeler bir kapsayıcıdaki iki unordered_multimaps eşit olur. Aksi takdirde, bunlar eşit değildir.

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

## <a name="op_eq_eq_multimap"></a>  işleç ==

Testleri olmadığını [unordered_multimap](../standard-library/unordered-multimap-class.md) işlecin sol tarafındaki nesnesinin işlecin sağ tarafındaki unordered_multimap nesneye eşit olup.

```cpp
bool operator==(const unordered_multimap <Key, Type, Hash, Pred, Allocator>& left, const unordered_multimap <Key, Type, Hash, Pred, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*Sol*<br/>
Bir nesne türü `unordered_multimap`.

*sağ*<br/>
Bir nesne türü `unordered_multimap`.

### <a name="return-value"></a>Dönüş Değeri

**doğru** unordered_multimaps eşitse; **false** eşit değilse.

### <a name="remarks"></a>Açıklamalar

Unordered_multimap nesneler arasında karşılaştırma öğeleri depoladıkları rastgele sıralama etkilenmez. Bunlar aynı sayıda öğe varsa ve diğer kapsayıcı öğeleri bir sıralamaya öğeler bir kapsayıcıdaki iki unordered_multimaps eşit olur. Aksi takdirde, eşit oldukları.

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

[<unordered_map>](../standard-library/unordered-map.md)<br/>
