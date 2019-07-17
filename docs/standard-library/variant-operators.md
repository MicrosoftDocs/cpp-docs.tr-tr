---
title: '&lt;değişken&gt; işleçleri'
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
ms.openlocfilehash: 0c4042ca1d89f9835b32924b268ef17a56619009
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68267924"
---
# <a name="ltvariantgt-operators"></a>&lt;değişken&gt; işleçleri

## <a name="op_eq_eq"></a> işleç ==

İşlecin sol tarafındaki iletme liste nesnesi işlecin sağ tarafındaki iletme liste nesnesi eşit olup olmadığını sınar.

```cpp
template <class... Types>
    constexpr bool operator==(const variant<Types...>&, const variant<Types...>&);
```

## <a name="op_neq"></a> işleç! =

İşlecin sol tarafındaki iletme liste nesnesi işlecin sağ tarafındaki iletme liste nesnesi eşit olup olmadığını sınar.

```cpp
template <class... Types>
    constexpr bool operator!=(const variant<Types...>&, const variant<Types...>&);
```

## <a name="op_lt"></a> İşleci&lt;

İşlecin sol tarafındaki iletme liste nesnesi işlecin sağ tarafındaki iletme listesi nesneden küçük olup olmadığını sınar.

```cpp
template <class... Types>
    constexpr bool operator<(const variant<Types...>&, const variant<Types...>&);
```

## <a name="op_lt_eq"></a> İşleci&lt;=

İşlecinin sol tarafında iletme liste nesnesi küçük olup olmadığını sınar veya işlecin sağ tarafındaki iletme liste nesnesi eşittir.

```cpp
template <class... Types>
    constexpr bool operator<=(const variant<Types...>&, const variant<Types...>&);
```

## <a name="op_gt"></a> İşleci&gt;

İşlecin sol tarafındaki iletme liste nesnesi iletme liste nesnesi işlecin sağ tarafındaki büyük olup olmadığını sınar.

```cpp
template <class... Types> constexpr
    bool operator>(const variant<Types...>&, const variant<Types...>&);
```

## <a name="op_gt_eq"></a> İşleci&gt;=

İşlecin sol tarafındaki iletme liste nesnesi büyük veya işlecin sağ tarafındaki iletme Liste nesnesine eşit olup olmadığını sınar.

```cpp
template <class... Types> constexpr
    bool operator>=(const variant<Types...>&, const variant<Types...>&);
```
