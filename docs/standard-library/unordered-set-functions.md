---
title: '&lt;unordered_set&gt; işlevleri | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- unordered_set/std::swap (set)
- unordered_set/std::swap (unordered_multiset)
ms.assetid: 66b35671-4023-4411-ad50-83786580d8ee
caps.latest.revision: 10
manager: ghogen
ms.openlocfilehash: d4aa4d81233cd7a12028320cf8541cdb3616a653
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
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

`Key` Anahtar türü.

`Hash` Karma işlevi nesne türü.

`Pred` Eşitlik karşılaştırması işlevi nesne türü.

`Alloc` Allocator sınıfı.

`left` Değiştirilecek ilk kapsayıcı.

`right` Değiştirilecek ikinci kapsayıcı.

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

`Key` Anahtar türü.

`Hash` Karma işlevi nesne türü.

`Pred` Eşitlik karşılaştırması işlevi nesne türü.

`Alloc` Allocator sınıfı.

`left` Değiştirilecek ilk kapsayıcı.

`right` Değiştirilecek ikinci kapsayıcı.

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
