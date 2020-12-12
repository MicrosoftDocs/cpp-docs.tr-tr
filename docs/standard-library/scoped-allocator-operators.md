---
description: 'Daha fazla bilgi edinin: &lt; scoped_allocator &gt; işleçleri'
title: '&lt;scoped_allocator &gt; işleçleri'
ms.date: 11/04/2016
f1_keywords:
- scoped_allocator/std::operator!=
- scoped_allocator/std::operator==
ms.assetid: 4dfe0805-cc6e-479f-887f-a1c164f73837
ms.openlocfilehash: 2f32a42ded9c73cbc2608f3e39f3566deee20e83
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97197146"
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
