---
title: '&lt;scoped_allocator &gt; işleçleri'
ms.date: 11/04/2016
f1_keywords:
- scoped_allocator/std::operator!=
- scoped_allocator/std::operator==
ms.assetid: 4dfe0805-cc6e-479f-887f-a1c164f73837
ms.openlocfilehash: 907772069c192b3ef75c7366e079b1da1dd36f8d
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88846257"
---
# <a name="ltscoped_allocatorgt-operators"></a>&lt;scoped_allocator &gt; işleçleri

[işleç! =](#op_neq)\
[işleç = =](#op_eq_eq)

## <a name="operator"></a><a name="op_neq"></a> işleç! =

`scoped_allocator_adaptor`Eşitsizlik için iki nesneyi sınar.

```cpp
template <class Outer, class... Inner>
bool operator!=(
    const scoped_allocator_adaptor<Outer, Inner...>& left,
    const scoped_allocator_adaptor<Outer, Inner...>& right) noexcept;
```

### <a name="parameters"></a>Parametreler

*tarafta*\
Sol `scoped_allocator_adaptor` nesne.

*Right*\
Doğru `scoped_allocator_adaptor` nesne.

### <a name="return-value"></a>Dönüş Değeri

`!(left == right)`

## <a name="operator"></a><a name="op_eq_eq"></a> işleç = =

İki `scoped_allocator_adaptor` nesneyi eşitlik için sınar.

```cpp
template <class Outer, class... Inner>
bool operator==(
    const scoped_allocator_adaptor<Outer, Inner...>& left,
    const scoped_allocator_adaptor<Outer, Inner...>& right) noexcept;
```

### <a name="parameters"></a>Parametreler

*tarafta*\
Sol `scoped_allocator_adaptor` nesne.

*Right*\
Doğru `scoped_allocator_adaptor` nesne.

### <a name="return-value"></a>Dönüş Değeri

`left.outer_allocator() == right.outer_allocator() && left.inner_allocator() == right.inner_allocator()`

## <a name="see-also"></a>Ayrıca bkz.

[<scoped_allocator>](../standard-library/scoped-allocator.md)
