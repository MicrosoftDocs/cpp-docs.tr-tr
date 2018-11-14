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
ms.openlocfilehash: 2f7206e3764df384004b78e6df2127833a784f70
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/10/2018
ms.locfileid: "51521043"
---
# <a name="hash-class"></a>hash Sınıfı

Hesaplar karma kodu için bir değer.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Ty>
struct hash {
    size_t operator()(Ty val) const;
};
```

## <a name="remarks"></a>Açıklamalar

İşlev nesnesi türü için uygun bir karma işlevi tanımlar *Ty* dizin değerlerinin dağıtımına. Üye `operator()` bir karma kodu döndürür *val*, şablon sınıfları ile kullanım için uygun `unordered_map`, `unordered_multimap`, `unordered_set`, ve `unordered_multiset`. Standart kitaplık temel türleri için uzmanlıklar sağlar: *Ty* işaretçi türleri ve Numaralandırma türleri dahil olmak üzere herhangi bir skalar türü olabilir. Ayrıca, kitaplık türleri için uzmanlıklar vardır `string`, `wstring`, `u16string`, `u32string`, `string_view`, `wstring_view`, `u16string_view`, `u32string_view`, `bitset`, `error_code`, `error_condition`, `optional`, `shared_ptr`, `thread`, `type_index`, `unique_ptr`, `variant`, ve `vector<bool>`.

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

**Başlık:** \<işlev >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[<unordered_map>](../standard-library/unordered-map.md)<br/>
[unordered_multimap Sınıfı](../standard-library/unordered-multimap-class.md)<br/>
[unordered_multiset Sınıfı](../standard-library/unordered-multiset-class.md)<br/>
[<unordered_set>](../standard-library/unordered-set.md)<br/>
