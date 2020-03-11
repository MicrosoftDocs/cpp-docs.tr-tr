---
title: '&lt;unordered_set&gt; işleçleri'
ms.date: 11/04/2016
f1_keywords:
- unordered_set/std::operator!=
- unordered_set/std::operator==
ms.assetid: 8653eea6-12f2-4dd7-aa2f-db38a71599a0
ms.openlocfilehash: 59a7154ed46ac788516bc9f42c3385ec8f07dcf1
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/06/2020
ms.locfileid: "78890762"
---
# <a name="ltunordered_setgt-operators"></a>&lt;unordered_set&gt; işleçleri

## <a name="op_neq"></a>işleç! =

İşlecin sol tarafındaki [unordered_set](../standard-library/unordered-set-class.md) nesnesinin sağ taraftaki unordered_set nesnesine eşit olup olmadığını sınar.

```cpp
bool operator!=(const unordered_set <Key, Hash, Pred, Allocator>& left, const unordered_set <Key, Hash, Pred, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*sol*\
`unordered_set` türünün bir nesnesi.

*sağ*\
`unordered_set` türünün bir nesnesi.

### <a name="return-value"></a>Dönüş Değeri

unordered_sets eşitse **true** ; eşitse **false** .

### <a name="remarks"></a>Açıklamalar

Unordered_set nesneleri arasındaki karşılaştırma, öğelerini depolayabilecekleri rastgele sıra tarafından etkilenmez. İki unordered_sets, aynı sayıda öğeye sahip olmaları ve bir kapsayıcıdaki öğelerin diğer kapsayıcıdaki öğelerin bir permütasyon olması halinde eşittir. Aksi takdirde, bunlar eşit değildir.

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

**Çıktıların**

`c1 != c2: true`

`c1 != c3: false`

`c2 != c3: true`

## <a name="op_eq_eq"></a>işleç = =

İşlecin sol tarafındaki [unordered_set](../standard-library/unordered-set-class.md) nesnesinin sağ taraftaki unordered_set nesnesine eşit olup olmadığını sınar.

```cpp
bool operator==(const unordered_set <Key, Hash, Pred, Allocator>& left, const unordered_set <Key, Hash, Pred, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*sol*\
`unordered_set` türünün bir nesnesi.

*sağ*\
`unordered_set` türünün bir nesnesi.

### <a name="return-value"></a>Dönüş Değeri

unordered_sets eşitse **true** ; eşit değilse **false** .

### <a name="remarks"></a>Açıklamalar

Unordered_set nesneleri arasındaki karşılaştırma, öğelerini depolayabilecekleri rastgele sıra tarafından etkilenmez. İki unordered_sets, aynı sayıda öğeye sahip olmaları ve bir kapsayıcıdaki öğelerin diğer kapsayıcıdaki öğelerin bir permütasyon olması halinde eşittir. Aksi takdirde, bunlar eşit değildir.

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

```Output
c1 == c2: false
c1 == c3: true
c2 == c3: false
```

## <a name="op_neq_unordered_multiset"></a>işleç! =

İşlecin sol tarafındaki [unordered_multiset](../standard-library/unordered-multiset-class.md) nesnesinin sağ taraftaki unordered_multiset nesnesine eşit olup olmadığını sınar.

```cpp
bool operator!=(const unordered_multiset <Key, Hash, Pred, Allocator>& left, const unordered_multiset <Key, Hash, Pred, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*sol*\
`unordered_multiset` türünün bir nesnesi.

*sağ*\
`unordered_multiset` türünün bir nesnesi.

### <a name="return-value"></a>Dönüş Değeri

unordered_multisets eşitse **true** ; eşitse **false** .

### <a name="remarks"></a>Açıklamalar

Unordered_multiset nesneleri arasındaki karşılaştırma, öğelerini depolayabilecekleri rastgele sıra tarafından etkilenmez. İki unordered_multisets, aynı sayıda öğeye sahip olmaları ve bir kapsayıcıdaki öğelerin diğer kapsayıcıdaki öğelerin bir permütasyon olması halinde eşittir. Aksi takdirde, bunlar eşit değildir.

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

```Output
c1 != c2: true
c1 != c3: false
c2 != c3: true
```

## <a name="op_eq_eq_unordered_multiset"></a>işleç = =

İşlecin sol tarafındaki [unordered_multiset](../standard-library/unordered-multiset-class.md) nesnesinin sağ taraftaki unordered_multiset nesnesine eşit olup olmadığını sınar.

```cpp
bool operator==(const unordered_multiset <Key, Hash, Pred, Allocator>& left, const unordered_multiset <Key, Hash, Pred, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*sol*\
`unordered_multiset` türünün bir nesnesi.

*sağ*\
`unordered_multiset` türünün bir nesnesi.

### <a name="return-value"></a>Dönüş Değeri

unordered_multisets eşitse **true** ; eşit değilse **false** .

### <a name="remarks"></a>Açıklamalar

Unordered_multiset nesneleri arasındaki karşılaştırma, öğelerini depolayabilecekleri rastgele sıra tarafından etkilenmez. İki unordered_multisets, aynı sayıda öğeye sahip olmaları ve bir kapsayıcıdaki öğelerin diğer kapsayıcıdaki öğelerin bir permütasyon olması halinde eşittir. Aksi takdirde, bunlar eşit değildir.

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

```Output
c1 == c2: false
c1 == c3: true
c2 == c3: false
```
