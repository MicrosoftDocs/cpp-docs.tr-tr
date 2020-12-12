---
description: 'Daha fazla bilgi edinin: karma sınıf'
title: hash Sınıfı
ms.date: 11/04/2016
f1_keywords:
- functional/std::hash
- bitset/std::hash
- memory/std::hash
- string/std::hash
- system_error/std::hash
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
ms.openlocfilehash: 124740486482722ec065c01f0d71e9bbc413f8f7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97324167"
---
# <a name="hash-class"></a>hash Sınıfı

Bir değer için karma kodu hesaplar.

## <a name="syntax"></a>Syntax

```cpp
template <class Ty>
struct hash {
    size_t operator()(Ty val) const;
};
```

## <a name="remarks"></a>Açıklamalar

Function nesnesi bir karma işlevi tanımlar, bu tür değeri, dizin değerlerinin dağıtımına göre değer *eşlemek için uygundur* . Üye, `operator()` sınıf şablonları,,, ve ile kullanım için uygun değer için bir karma kod döndürür `unordered_map` `unordered_multimap` `unordered_set` `unordered_multiset` . Standart Kitaplık, temel türler için uzmanlık sağlar: *Ty* , işaretçi türleri ve numaralandırma türleri dahil herhangi bir skalar tür olabilir. Bunlara ek olarak,,,,,,,, `string` , `wstring` `u16string` `u32string` `string_view` `wstring_view` `u16string_view` `u32string_view` `bitset` `error_code` , `error_condition` , `optional` , `shared_ptr` ,, `thread` `type_index` ,,, `unique_ptr` `variant` ve `vector<bool>` kitaplık türleri için uzmanlık vardır.

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

**Üst bilgi:**\<functional>

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[<unordered_map>](../standard-library/unordered-map.md)\
[unordered_multimap Sınıfı](../standard-library/unordered-multimap-class.md)\
[unordered_multiset sınıfı](../standard-library/unordered-multiset-class.md)\
[<unordered_set>](../standard-library/unordered-set.md)
