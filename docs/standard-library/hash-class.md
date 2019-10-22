---
title: hash Sınıfı
ms.date: 11/04/2016
f1_keywords:
- functional/std::hash
- bitset/std::hash
- memory/std::hash
- string/std::hash
- system_error/std::hash
- thread/std::hash
- typeindex/std::hash
- vector/std::hash
- XSTDDEF/std::hash
- xstring/std::hash
helpviewer_keywords:
- std::hash [C++]
- std::hash [C++]
- std::hash [C++]
- std::hash [C++]
- std::hash [C++]
- std::hash [C++]
- std::hash [C++]
- std::hash [C++]
- std::hash [C++]
ms.assetid: e1b500c6-a5c8-4f6f-ad33-7ec52eb8e2e4
ms.openlocfilehash: e30810412db29473597da144d2dd42bdb8184f7e
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2019
ms.locfileid: "72687995"
---
# <a name="hash-class"></a>hash Sınıfı

Bir değer için karma kodu hesaplar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Ty>
struct hash {
    size_t operator()(Ty val) const;
};
```

## <a name="remarks"></a>Açıklamalar

Function nesnesi bir karma işlevi tanımlar, bu tür değeri, dizin değerlerinin dağıtımına göre değer *eşlemek için uygundur* . Üye `operator()`, sınıf şablonları `unordered_map`, `unordered_multimap`, `unordered_set` ve `unordered_multiset` ile kullanım için uygun *değer için bir*karma kod döndürür. Standart Kitaplık, temel türler için uzmanlık sağlar: *Ty* , işaretçi türleri ve numaralandırma türleri dahil herhangi bir skalar tür olabilir. Ayrıca, kitaplık türleri için `string`, `wstring`, `u16string`, `u32string`, `string_view`, `wstring_view`, `u16string_view`, `u32string_view`, `bitset`, `error_code`, 0, 1, 2 , 3, 4, 5, 6 ve 7.

## <a name="example"></a>Örnek

```cpp
// std__functional__hash.cpp
// compile with: /EHsc
#include <functional>
#include <iostream>
#include <unordered_set>

int main()
    {
    std::unordered_set<int, std::hash<int> > c0;
    c0.insert(3);
    std::cout << *c0.find(3) << std::endl;

    return (0);
    }
```

```Output
3
```

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<functional >

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[< unordered_map >](../standard-library/unordered-map.md) \
[unordered_multimap sınıfı](../standard-library/unordered-multimap-class.md) \
[unordered_multiset sınıfı](../standard-library/unordered-multiset-class.md) \
[<unordered_set>](../standard-library/unordered-set.md)
