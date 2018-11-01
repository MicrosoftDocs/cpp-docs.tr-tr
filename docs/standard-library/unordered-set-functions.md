---
title: '&lt;unordered_set&gt; işlevleri'
ms.date: 11/04/2016
f1_keywords:
- unordered_set/std::swap (set)
- unordered_set/std::swap (unordered_multiset)
ms.assetid: 66b35671-4023-4411-ad50-83786580d8ee
ms.openlocfilehash: 4616161c30a9059c413fc2ddf8fc577abe3ea845
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50490083"
---
# <a name="ltunorderedsetgt-functions"></a>&lt;unordered_set&gt; işlevleri

|||
|-|-|
|[Swap (set)](#swap)|[Swap (unordered_multiset)](#swap_unordered_multiset)|

## <a name="swap"></a>  Swap (unordered_set)

İki kapsayıcının içeriğinin yerini değiştirir.

```

template <class Key, class Hash, class Pred, class Alloc>
void swap(
   unordered_set <Key, Hash, Pred, Alloc>& left,
   unordered_set <Key, Hash, Pred, Alloc>& right);
```

### <a name="parameters"></a>Parametreler

*Key*<br/>
Anahtar türü.

*Karma*<br/>
Karma işlev nesne türü.

*Pred*<br/>
Eşitlik karşılaştırma işlevi nesne türü.

*Ayırma*<br/>
Ayırıcı sınıf.

*Sol*<br/>
Takas etmek için ilk kapsayıcı.

*sağ*<br/>
Takas etmek için ikinci kapsayıcı.

### <a name="remarks"></a>Açıklamalar

Şablon işlevi yürütür `left.` [unordered_set::swap](../standard-library/unordered-set-class.md#swap)`(right)`.

### <a name="example"></a>Örnek

```cpp
#include <unordered_set>
#include <iostream>

typedef std::unordered_set<char> Myset;
int main()
{
Myset c1;

c1.insert('a');
c1.insert('b');
c1.insert('c');

// display contents " [c] [b] [a]"
for (Myset::const_iterator it = c1.begin();
it != c1.end(); ++it)
std::cout << " [" << *it << "]";
std::cout << std::endl;

Myset c2;

c2.insert('d');
c2.insert('e');
c2.insert('f');

c1.swap(c2);

// display contents " [f] [e] [d]"
for (Myset::const_iterator it = c1.begin();
it != c1.end(); ++it)
std::cout << " [" << *it << "]";
std::cout << std::endl;

swap(c1, c2);

// display contents " [c] [b] [a]"
for (Myset::const_iterator it = c1.begin();
it != c1.end(); ++it)
std::cout << " [" << *it << "]";
std::cout << std::endl;

return (0);
}

```

```Output

[c] [b] [a]
[f] [e] [d]
[c] [b] [a]

```

## <a name="swap_unordered_multiset"></a>  Swap (unordered_multiset)

İki kapsayıcının içeriğinin yerini değiştirir.

```

template <class Key, class Hash, class Pred, class Alloc>
void swap(
   unordered_multiset <Key, Hash, Pred, Alloc>& left,
   unordered_multiset <Key, Hash, Pred, Alloc>& right);
```

### <a name="parameters"></a>Parametreler

*Key*<br/>
Anahtar türü.

*Karma*<br/>
Karma işlev nesne türü.

*Pred*<br/>
Eşitlik karşılaştırma işlevi nesne türü.

*Ayırma*<br/>
Ayırıcı sınıf.

*Sol*<br/>
Takas etmek için ilk kapsayıcı.

*sağ*<br/>
Takas etmek için ikinci kapsayıcı.

### <a name="remarks"></a>Açıklamalar

Şablon işlevi yürütür `left.` [unordered_multiset::swap](../standard-library/unordered-multiset-class.md#swap)`(right)`.

### <a name="example"></a>Örnek

```cpp
// std__unordered_set__u_ms_swap.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_multiset<char> Myset;
int main()
{
    Myset c1;

    c1.insert('a');
    c1.insert('b');
    c1.insert('c');

    // display contents " [c] [b] [a]"
    for (Myset::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << " [" << *it << "]";
    std::cout << std::endl;

    Myset c2;

    c2.insert('d');
    c2.insert('e');
    c2.insert('f');

    c1.swap(c2);

    // display contents " [f] [e] [d]"
    for (Myset::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << " [" << *it << "]";
    std::cout << std::endl;

    swap(c1, c2);

    // display contents " [c] [b] [a]"
    for (Myset::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << " [" << *it << "]";
    std::cout << std::endl;

    return (0);
}

```

```Output

[c] [b] [a]
[f] [e] [d]
[c] [b] [a]

```

## <a name="see-also"></a>Ayrıca bkz.

[<unordered_set>](../standard-library/unordered-set.md)<br/>
