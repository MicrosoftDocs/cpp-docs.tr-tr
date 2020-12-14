---
description: 'Daha fazla bilgi edinin: &lt; Varyant &gt; işleçleri'
title: '&lt;varyant &gt; işleçleri'
ms.date: 04/04/2019
f1_keywords:
- variant/std::operator!=
- variant/std::operator==
- variant/std::operatoroperator&gt;
- variant/std::operatoroperator&gt=;
- variant/std::operatoroperator&lt;
- variant/std::operatoroperator&lt;=
helpviewer_keywords:
- std::operator!= (variant)
- std::operator== (variant)
- std::operatoroperator&gt; (variant)
- std::operatoroperator&gt=; (variant)
- std::operatoroperator&lt; (variant)
- std::operatoroperator&lt;= (variant)
ms.openlocfilehash: 3315c73ea529ad7ade4f32be3784a43bda07ac26
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97312832"
---
# <a name="ltvariantgt-operators"></a>&lt;varyant &gt; işleçleri

## <a name="operator"></a><a name="op_eq_eq"></a> işleç = =

İşlecin sol tarafındaki ileri liste nesnesinin sağ taraftaki ileri liste nesnesine eşit olup olmadığını sınar.

```cpp
template <class... Types>
    constexpr bool operator==(const variant<Types...>&, const variant<Types...>&);
```

## <a name="operator"></a><a name="op_neq"></a> işleç! =

İşlecin sol tarafındaki ileri liste nesnesinin sağ taraftaki ileri liste nesnesine eşit olup olmadığını sınar.

```cpp
template <class... Types>
    constexpr bool operator!=(const variant<Types...>&, const variant<Types...>&);
```

## <a name="operatorlt"></a><a name="op_lt"></a> işlecinde&lt;

İşlecin sol tarafındaki ileri liste nesnesinin sağ taraftaki ileriye doğru liste nesnesinden küçük olup olmadığını sınar.

```cpp
template <class... Types>
    constexpr bool operator<(const variant<Types...>&, const variant<Types...>&);
```

## <a name="operatorlt"></a><a name="op_lt_eq"></a> işlecinde&lt;=

İşlecin sol tarafındaki ileri liste nesnesinin sağ taraftaki ileri liste nesnesinden küçük veya ona eşit olup olmadığını sınar.

```cpp
template <class... Types>
    constexpr bool operator<=(const variant<Types...>&, const variant<Types...>&);
```

## <a name="operatorgt"></a><a name="op_gt"></a> işlecinde&gt;

İşlecin sol tarafındaki ileri liste nesnesinin, sağ taraftaki ileri liste nesnesinden daha büyük olup olmadığını sınar.

```cpp
template <class... Types> constexpr
    bool operator>(const variant<Types...>&, const variant<Types...>&);
```

## <a name="operatorgt"></a><a name="op_gt_eq"></a> işlecinde&gt;=

İşlecin sol tarafındaki ileri liste nesnesinin sağ taraftaki ileri liste nesnesinden büyük veya ona eşit olup olmadığını sınar.

```cpp
template <class... Types> constexpr
    bool operator>=(const variant<Types...>&, const variant<Types...>&);
```
