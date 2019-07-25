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
ms.openlocfilehash: 61446ab6b79496024d44a99fcf5f500bb871bb80
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68448814"
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

Function nesnesi bir karma işlevi tanımlar, *Bu tür değeri* , dizin değerlerinin dağıtımına göre değer eşlemek için uygundur. `operator()` Üye, *değer*için `unordered_map` `unordered_multimap` şablonsınıflarıyla`unordered_multiset`,, ve ile kullanım için uygun bir karma kod döndürür. `unordered_set` Standart Kitaplık, temel türler için uzmanlık sağlar: *Ty* , işaretçi türleri ve numaralandırma türleri de dahil olmak üzere herhangi bir skalar tür olabilir. Ayrıca, kitaplık türleri `string` ,`string_view` ,,`wstring_view`,, ,`u32string_view`, ,`bitset`,,,,,,,,,,,,,, `error_code` `u16string_view` `wstring` `u16string` `u32string` `error_condition`, ,`optional` ,,`unique_ptr`,,, ve`vector<bool>`. `shared_ptr` `thread` `type_index` `variant`

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

**Üst bilgi:** \<işlevsel >

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[< unordered_map >](../standard-library/unordered-map.md)\
[unordered_multimap Sınıfı](../standard-library/unordered-multimap-class.md)\
[unordered_multiset sınıfı](../standard-library/unordered-multiset-class.md)\
[<unordered_set>](../standard-library/unordered-set.md)
