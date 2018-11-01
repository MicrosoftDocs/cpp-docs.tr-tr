---
title: '&lt;unordered_set&gt; işleçleri'
ms.date: 11/04/2016
f1_keywords:
- unordered_set/std::operator!=
- unordered_set/std::operator==
ms.assetid: 8653eea6-12f2-4dd7-aa2f-db38a71599a0
ms.openlocfilehash: 501a65c8725631463e9c2a6b7b11e0c6300b6664
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50495023"
---
# <a name="ltunorderedsetgt-operators"></a>&lt;unordered_set&gt; işleçleri

|||||
|-|-|-|-|
|[operator!=](#op_neq)|[operator==](#op_eq_eq)|[operator!=](#op_neq_unordered_multiset)|[operator==](#op_eq_eq_unordered_multiset)|

## <a name="op_neq"></a>  işleç! =

Testleri olmadığını [unordered_set](../standard-library/unordered-set-class.md) işlecinin sol tarafındaki nesne unordered_set nesnesinin işlecin sağ tarafındaki eşit değil.

```cpp
bool operator!=(const unordered_set <Key, Hash, Pred, Allocator>& left, const unordered_set <Key, Hash, Pred, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*Sol*<br/>
Bir nesne türü `unordered_set`.

*sağ*<br/>
Bir nesne türü `unordered_set`.

### <a name="return-value"></a>Dönüş Değeri

**doğru** unordered_sets eşit; değilse, **false** eşit olmaları durumunda.

### <a name="remarks"></a>Açıklamalar

Unordered_set nesneler arasında karşılaştırma öğeleri depoladıkları rastgele sıralama etkilenmez. Bunlar aynı sayıda öğe varsa ve diğer kapsayıcı öğeleri bir sıralamaya öğeler bir kapsayıcıdaki iki unordered_sets eşit olur. Aksi takdirde, eşit oldukları.

### <a name="example"></a>Örnek

```cpp
// unordered_set_ne.cpp
// compile by using: cl.exe /EHsc /nologo /W4 /MTd
#include <unordered_set>
#include <iostream>
#include <ios>

int main()
{
    using namespace std;

    unordered_set<char> c1, c2, c3;

    c1.insert('a');
    c1.insert('b');
    c1.insert('c');

    c2.insert('c');
    c2.insert('a');
    c2.insert('d');

    c3.insert('c');
    c3.insert('a');
    c3.insert('b');

   cout << boolalpha;
   cout << "c1 != c2: " << (c1 != c2) << endl;
   cout << "c1 != c3: " << (c1 != c3) << endl;
   cout << "c2 != c3: " << (c2 != c3) << endl;

    return (0);
}

```

**Çıkış:**

`c1 != c2: true`

`c1 != c3: false`

`c2 != c3: true`

## <a name="op_eq_eq"></a>  işleç ==

Testleri olmadığını [unordered_set](../standard-library/unordered-set-class.md) işlecin sol tarafındaki nesnesinin işlecin sağ tarafındaki unordered_set nesneye eşit olup.

```cpp
bool operator==(const unordered_set <Key, Hash, Pred, Allocator>& left, const unordered_set <Key, Hash, Pred, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*Sol*<br/>
Bir nesne türü `unordered_set`.

*sağ*<br/>
Bir nesne türü `unordered_set`.

### <a name="return-value"></a>Dönüş Değeri

**doğru** unordered_sets eşitse; **false** eşit değilse.

### <a name="remarks"></a>Açıklamalar

Unordered_set nesneler arasında karşılaştırma öğeleri depoladıkları rastgele sıralama etkilenmez. Bunlar aynı sayıda öğe varsa ve diğer kapsayıcı öğeleri bir sıralamaya öğeler bir kapsayıcıdaki iki unordered_sets eşit olur. Aksi takdirde, eşit oldukları.

### <a name="example"></a>Örnek

```cpp
// unordered_set_eq.cpp
// compile by using: cl.exe /EHsc /nologo /W4 /MTd
#include <unordered_set>
#include <iostream>
#include <ios>

int main()
{
    using namespace std;

    unordered_set<char> c1, c2, c3;

    c1.insert('a');
    c1.insert('b');
    c1.insert('c');

    c2.insert('c');
    c2.insert('a');
    c2.insert('d');

    c3.insert('c');
    c3.insert('a');
    c3.insert('b');

   cout << boolalpha;
   cout << "c1 == c2: " << (c1 == c2) << endl;
   cout << "c1 == c3: " << (c1 == c3) << endl;
   cout << "c2 == c3: " << (c2 == c3) << endl;

    return (0);
}

```

**Çıkış:**

`c1 == c2: false`

`c1 == c3: true`

`c2 == c3: false`

## <a name="op_neq_unordered_multiset"></a>  işleç! =

Testleri olmadığını [unordered_multiset](../standard-library/unordered-multiset-class.md) işlecinin sol tarafındaki nesne unordered_multiset nesnesinin işlecin sağ tarafındaki eşit değil.

```cpp
bool operator!=(const unordered_multiset <Key, Hash, Pred, Allocator>& left, const unordered_multiset <Key, Hash, Pred, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*Sol*<br/>
Bir nesne türü `unordered_multiset`.

*sağ*<br/>
Bir nesne türü `unordered_multiset`.

### <a name="return-value"></a>Dönüş Değeri

**doğru** unordered_multisets eşit; değilse, **false** eşit olmaları durumunda.

### <a name="remarks"></a>Açıklamalar

Unordered_multiset nesneler arasında karşılaştırma öğeleri depoladıkları rastgele sıralama etkilenmez. Bunlar aynı sayıda öğe varsa ve diğer kapsayıcı öğeleri bir sıralamaya öğeler bir kapsayıcıdaki iki unordered_multisets eşit olur. Aksi takdirde, eşit oldukları.

### <a name="example"></a>Örnek

```cpp
// unordered_multiset_ne.cpp
// compile by using: cl.exe /EHsc /nologo /W4 /MTd
#include <unordered_set>
#include <iostream>
#include <ios>

int main()
{
    using namespace std;

    unordered_multiset<char> c1, c2, c3;

    c1.insert('a');
    c1.insert('b');
    c1.insert('c');
    c1.insert('c');

    c2.insert('c');
    c2.insert('c');
    c2.insert('a');
    c2.insert('d');

    c3.insert('c');
    c3.insert('c');
    c3.insert('a');
    c3.insert('b');

   cout << boolalpha;
   cout << "c1 != c2: " << (c1 != c2) << endl;
   cout << "c1 != c3: " << (c1 != c3) << endl;
   cout << "c2 != c3: " << (c2 != c3) << endl;

    return (0);
}

```

**Çıkış:**

`c1 != c2: true`

`c1 != c3: false`

`c2 != c3: true`

## <a name="op_eq_eq_unordered_multiset"></a>  işleç ==

Testleri olmadığını [unordered_multiset](../standard-library/unordered-multiset-class.md) işlecin sol tarafındaki nesnesinin işlecin sağ tarafındaki unordered_multiset nesneye eşit olup.

```cpp
bool operator==(const unordered_multiset <Key, Hash, Pred, Allocator>& left, const unordered_multiset <Key, Hash, Pred, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*Sol*<br/>
Bir nesne türü `unordered_multiset`.

*sağ*<br/>
Bir nesne türü `unordered_multiset`.

### <a name="return-value"></a>Dönüş Değeri

**doğru** unordered_multisets eşitse; **false** eşit değilse.

### <a name="remarks"></a>Açıklamalar

Unordered_multiset nesneler arasında karşılaştırma öğeleri depoladıkları rastgele sıralama etkilenmez. Bunlar aynı sayıda öğe varsa ve diğer kapsayıcı öğeleri bir sıralamaya öğeler bir kapsayıcıdaki iki unordered_multisets eşit olur. Aksi takdirde, eşit oldukları.

### <a name="example"></a>Örnek

```cpp
// unordered_multiset_eq.cpp
// compile by using: cl.exe /EHsc /nologo /W4 /MTd
#include <unordered_set>
#include <iostream>
#include <ios>

int main()
{
    using namespace std;

    unordered_multiset<char> c1, c2, c3;

    c1.insert('a');
    c1.insert('b');
    c1.insert('c');
    c1.insert('c');

    c2.insert('c');
    c2.insert('c');
    c2.insert('a');
    c2.insert('d');

    c3.insert('c');
    c3.insert('c');
    c3.insert('a');
    c3.insert('b');

   cout << boolalpha;
   cout << "c1 == c2: " << (c1 == c2) << endl;
   cout << "c1 == c3: " << (c1 == c3) << endl;
   cout << "c2 == c3: " << (c2 == c3) << endl;

    return (0);
}

```

**Çıkış:**

`c1 == c2: false`

`c1 == c3: true`

`c2 == c3: false`

## <a name="see-also"></a>Ayrıca bkz.

[<unordered_set>](../standard-library/unordered-set.md)<br/>
