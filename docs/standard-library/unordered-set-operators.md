---
title: '&lt;unordered_set&gt; işleçleri | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- unordered_set/std::operator!=
- unordered_set/std::operator==
dev_langs:
- C++
ms.assetid: 8653eea6-12f2-4dd7-aa2f-db38a71599a0
ms.openlocfilehash: c72058f78a779c6fbac91cac07e9ffef1244a046
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
---
# <a name="ltunorderedsetgt-operators"></a>&lt;unordered_set&gt; işleçleri

|||||
|-|-|-|-|
|[operator!=](#op_neq)|[operator==](#op_eq_eq)|[operator!=](#op_neq_unordered_multiset)|[operator==](#op_eq_eq_unordered_multiset)|

## <a name="op_neq"></a>  operator! =

Testleri olup olmadığını [unordered_set](../standard-library/unordered-set-class.md) nesne işlecinin sol tarafındaki sağ tarafında unordered_set nesnesine eşit değil.

```cpp
bool operator!=(const unordered_set <Key, Hash, Pred, Allocator>& left, const unordered_set <Key, Hash, Pred, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

`left` Türünde bir nesne `unordered_set`.

`right` Türünde bir nesne `unordered_set`.

### <a name="return-value"></a>Dönüş Değeri

`true` unordered_sets eşit değilse; `false` eşit olup olmadıkları.

### <a name="remarks"></a>Açıklamalar

Unordered_set nesneleri arasındaki karşılaştırma öğelerini depoladıkları rastgele sıralama ölçütü etkilenmez. İki unordered_sets aynı sayıda öğe varsa ve diğer kapsayıcı öğeleri sıralamaya öğeleridir bir kapsayıcıdaki eşit. Aksi takdirde, bunlar eşit.

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

**Çıktı:**

`c1 != c2: true`

`c1 != c3: false`

`c2 != c3: true`

## <a name="op_eq_eq"></a>  operator ==

Testleri olup olmadığını [unordered_set](../standard-library/unordered-set-class.md) nesne işlecinin sol tarafındaki sağ tarafında unordered_set nesnesine eşit değil.

```cpp
bool operator==(const unordered_set <Key, Hash, Pred, Allocator>& left, const unordered_set <Key, Hash, Pred, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

`left` Türünde bir nesne `unordered_set`.

`right` Türünde bir nesne `unordered_set`.

### <a name="return-value"></a>Dönüş Değeri

`true` unordered_sets eşitse; `false` eşit değillerse.

### <a name="remarks"></a>Açıklamalar

Unordered_set nesneleri arasındaki karşılaştırma öğelerini depoladıkları rastgele sıralama ölçütü etkilenmez. İki unordered_sets aynı sayıda öğe varsa ve diğer kapsayıcı öğeleri sıralamaya öğeleridir bir kapsayıcıdaki eşit. Aksi takdirde, bunlar eşit.

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

**Çıktı:**

`c1 == c2: false`

`c1 == c3: true`

`c2 == c3: false`

## <a name="op_neq_unordered_multiset"></a>  operator! =

Testleri olup olmadığını [unordered_multiset](../standard-library/unordered-multiset-class.md) nesne işlecinin sol tarafındaki sağ tarafında unordered_multiset nesnesine eşit değil.

```cpp
bool operator!=(const unordered_multiset <Key, Hash, Pred, Allocator>& left, const unordered_multiset <Key, Hash, Pred, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

`left` Türünde bir nesne `unordered_multiset`.

`right` Türünde bir nesne `unordered_multiset`.

### <a name="return-value"></a>Dönüş Değeri

`true` unordered_multisets eşit değilse; `false` eşit olup olmadıkları.

### <a name="remarks"></a>Açıklamalar

Unordered_multiset nesneleri arasındaki karşılaştırma öğelerini depoladıkları rastgele sıralama ölçütü etkilenmez. İki unordered_multisets aynı sayıda öğe varsa ve diğer kapsayıcı öğeleri sıralamaya öğeleridir bir kapsayıcıdaki eşit. Aksi takdirde, bunlar eşit.

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

**Çıktı:**

`c1 != c2: true`

`c1 != c3: false`

`c2 != c3: true`

## <a name="op_eq_eq_unordered_multiset"></a>  operator ==

Testleri olup olmadığını [unordered_multiset](../standard-library/unordered-multiset-class.md) nesne işlecinin sol tarafındaki sağ tarafında unordered_multiset nesnesine eşit değil.

```cpp
bool operator==(const unordered_multiset <Key, Hash, Pred, Allocator>& left, const unordered_multiset <Key, Hash, Pred, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

`left` Türünde bir nesne `unordered_multiset`.

`right` Türünde bir nesne `unordered_multiset`.

### <a name="return-value"></a>Dönüş Değeri

`true` unordered_multisets eşitse; `false` eşit değillerse.

### <a name="remarks"></a>Açıklamalar

Unordered_multiset nesneleri arasındaki karşılaştırma öğelerini depoladıkları rastgele sıralama ölçütü etkilenmez. İki unordered_multisets aynı sayıda öğe varsa ve diğer kapsayıcı öğeleri sıralamaya öğeleridir bir kapsayıcıdaki eşit. Aksi takdirde, bunlar eşit.

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

**Çıktı:**

`c1 == c2: false`

`c1 == c3: true`

`c2 == c3: false`

## <a name="see-also"></a>Ayrıca bkz.

[<unordered_set>](../standard-library/unordered-set.md)<br/>
