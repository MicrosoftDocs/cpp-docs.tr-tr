---
title: '&lt;unordered_map&gt; işleçleri'
ms.date: 11/04/2016
f1_keywords:
- unordered_map/std::operator!=
- unordered_map/std::operator==
ms.assetid: 9d5add0b-84bd-4a79-bd82-3f58b55145ed
ms.openlocfilehash: fe4877bc5b371a2570c18950bac36a003078ccc7
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68454776"
---
# <a name="ltunorderedmapgt-operators"></a>&lt;unordered_map&gt; işleçleri

|||||
|-|-|-|-|
|[operator!=](#op_neq)|[operator==](#op_eq_eq)|[operator!=](#op_neq_multimap)|[operator==](#op_eq_eq_multimap)|

## <a name="op_neq"></a>işleç! =

İşlecin sol tarafındaki [unordered_map](../standard-library/unordered-map-class.md) nesnesinin sağ taraftaki unordered_map nesnesine eşit olup olmadığını sınar.

```cpp
bool operator!=(const unordered_map <Key, Type, Hash, Pred, Allocator>& left, const unordered_map <Key, Type, Hash, Pred, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*tarafta*\
Türünde `unordered_map`bir nesne.

*Right*\
Türünde `unordered_map`bir nesne.

### <a name="return-value"></a>Dönüş Değeri

unordered_maps eşitse **true** ; eşitse **false** .

### <a name="remarks"></a>Açıklamalar

Unordered_map nesneleri arasındaki karşılaştırma, öğelerini depolayabilecekleri rastgele sıra tarafından etkilenmez. İki unordered_maps aynı sayıda öğe varsa ve bir kapsayıcıdaki öğeler diğer kapsayıcıdaki öğelerin bir permütasyonlarsa eşittir. Aksi takdirde, bunlar eşit değildir.

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

## <a name="op_eq_eq"></a>işleç = =

İşlecin sol tarafındaki [unordered_map](../standard-library/unordered-map-class.md) nesnesinin, sağ taraftaki unordered_map nesnesine eşit olup olmadığını sınar.

```cpp
bool operator==(const unordered_map <Key, Type, Hash, Pred, Allocator>& left, const unordered_map <Key, Type, Hash, Pred, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*tarafta*\
Türünde `unordered_map`bir nesne.

*Right*\
Türünde `unordered_map`bir nesne.

### <a name="return-value"></a>Dönüş Değeri

unordered_maps eşitse **true** ; eşit değilse **false** .

### <a name="remarks"></a>Açıklamalar

Unordered_map nesneleri arasındaki karşılaştırma, öğelerini depolayabilecekleri rastgele sıra tarafından etkilenmez. İki unordered_maps aynı sayıda öğe varsa ve bir kapsayıcıdaki öğeler diğer kapsayıcıdaki öğelerin bir permütasyonlarsa eşittir. Aksi takdirde, bunlar eşit değildir.

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

## <a name="op_neq_multimap"></a>işleç! =

İşlecin sol tarafındaki [unordered_multimap](../standard-library/unordered-multimap-class.md) nesnesinin sağ taraftaki unordered_multimap nesnesine eşit olup olmadığını sınar.

```cpp
bool operator!=(const unordered_multimap <Key, Type, Hash, Pred, Allocator>& left, const unordered_multimap <Key, Type, Hash, Pred, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*tarafta*\
Türünde `unordered_multimap`bir nesne.

*Right*\
Türünde `unordered_multimap`bir nesne.

### <a name="return-value"></a>Dönüş Değeri

unordered_multimaps eşitse **true** ; eşitse **false** .

### <a name="remarks"></a>Açıklamalar

Unordered_multimap nesneleri arasındaki karşılaştırma, öğelerini depolayabilecekleri rastgele sıra tarafından etkilenmez. İki unordered_multimaps aynı sayıda öğe varsa ve bir kapsayıcıdaki öğeler diğer kapsayıcıdaki öğelerin bir permütasyonlarsa eşittir. Aksi halde eşit değildir.

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

## <a name="op_eq_eq_multimap"></a>işleç = =

İşlecin sol tarafındaki [unordered_multimap](../standard-library/unordered-multimap-class.md) nesnesinin, sağ taraftaki unordered_multimap nesnesine eşit olup olmadığını sınar.

```cpp
bool operator==(const unordered_multimap <Key, Type, Hash, Pred, Allocator>& left, const unordered_multimap <Key, Type, Hash, Pred, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*tarafta*\
Türünde `unordered_multimap`bir nesne.

*Right*\
Türünde `unordered_multimap`bir nesne.

### <a name="return-value"></a>Dönüş Değeri

unordered_multimaps eşitse **true** ; eşit değilse **false** .

### <a name="remarks"></a>Açıklamalar

Unordered_multimap nesneleri arasındaki karşılaştırma, öğelerini depolayabilecekleri rastgele sıra tarafından etkilenmez. İki unordered_multimaps aynı sayıda öğe varsa ve bir kapsayıcıdaki öğeler diğer kapsayıcıdaki öğelerin bir permütasyonlarsa eşittir. Aksi takdirde, bunlar eşit değildir.

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
