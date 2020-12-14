---
description: 'Daha fazla bilgi edinin: &lt; isteğe bağlı &gt; işleçler'
title: '&lt;isteğe bağlı &gt; işleçler'
ms.date: 11/04/2016
f1_keywords:
- optional/std::operator!=
- optional/std::operator==
- optional/std::operatoroperator&gt;
- optional/std::operatoroperator&gt=;
- optional/std::operatoroperator&lt;
- optional/std::operatoroperator&lt;=
ms.assetid: 57492e09-3836-4dbc-9ae5-78ecf506c190
helpviewer_keywords:
- std::operator!= (optional)
- std::operator== (optional)
- std::operatoroperator&gt; (optional)
- std::operatoroperator&gt=; (optional)
- std::operatoroperator&lt; (optional)
- std::operatoroperator&lt;= (optional)
ms.openlocfilehash: 3c61f62ff87ab285dfeb5b26f1d22de86ef50fee
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97201865"
---
# <a name="ltoptionalgt-operators"></a>&lt;isteğe bağlı &gt; işleçler

## <a name="operator"></a><a name="op_eq_eq"></a> işleç = =

`optional`İşlecin sol tarafındaki nesnenin sağ taraftaki nesneye eşit olup olmadığını sınar `optional` .

```cpp
template <class T, class U> constexpr bool operator==(const optional<T>& left, const optional<U>& right);
template <class T> constexpr bool operator==(const optional<T>& left, nullopt_t right) noexcept;
template <class T> constexpr bool operator==(nullopt_t left, const optional<T>& right) noexcept;
template <class T, class U> constexpr bool operator==(const optional<T>&, const U&);
template <class T, class U> constexpr bool operator==(const U&, const optional<T>&);
```

### <a name="parameters"></a>Parametreler

*tarafta*\
, Veya türünde bir `optional` nesne `nullopt_t` `T` .

*Right*\
, Veya türünde bir `optional` nesne `nullopt_t` `T` .

## <a name="operator"></a><a name="op_neq"></a> işleç! =

`optional`İşlecin sol tarafındaki nesnenin sağ taraftaki nesneye eşit olup olmadığını sınar `optional` .

```cpp
template <class T, class U> constexpr bool operator!=(const optional<T>&, const optional<U>&);
template <class T> constexpr bool operator!=(const optional<T>&, nullopt_t) noexcept;
template <class T> constexpr bool operator!=(nullopt_t, const optional<T>&) noexcept;
template <class T, class U> constexpr bool operator!=(const optional<T>&, const U&);
template <class T, class U> constexpr bool operator!=(const U&, const optional<T>&);
```

### <a name="parameters"></a>Parametreler

*tarafta*\
, Veya türünde bir `optional` nesne `nullopt_t` `T` .

*Right*\
, Veya türünde bir `optional` nesne `nullopt_t` `T` .

### <a name="remarks"></a>Açıklamalar

Bu şablon işlevi döndürür `!(left == right)` .

## <a name="operatorlt"></a><a name="op_lt"></a> işlecinde&lt;

`optional`İşlecin sol tarafındaki nesnenin sağ taraftaki nesneden daha az olup olmadığını sınar `optional` .

```cpp
template <class T, class U> constexpr bool operator<(const optional<T>&, const optional<U>&);
template <class T> constexpr bool operator<(const optional<T>&, nullopt_t) noexcept;
template <class T> constexpr bool operator<(nullopt_t, const optional<T>&) noexcept;
template <class T, class U> constexpr bool operator<(const optional<T>&, const U&);
template <class T, class U> constexpr bool operator<(const U&, const optional<T>&);
```

### <a name="parameters"></a>Parametreler

*tarafta*\
, Veya türünde bir `optional` nesne `nullopt_t` `T` .

*Right*\
, Veya türünde bir `optional` nesne `nullopt_t` `T` .

### <a name="return-value"></a>Dönüş Değeri

**`true`** işlecin sol tarafındaki liste, işlecin sağ tarafındaki listeye eşit ancak ondan küçükse; Aksi takdirde **`false`** .

## <a name="operatorlt"></a><a name="op_lt_eq"></a> işlecinde&lt;=

`optional`İşlecin sol tarafındaki nesnenin sağ taraftaki nesneden küçük veya ona eşit olup olmadığını sınar `optional` .

```cpp
template <class T, class U> constexpr bool operator<=(const optional<T>&, const optional<U>&);
template <class T> constexpr bool operator<=(const optional<T>&, nullopt_t) noexcept;
template <class T> constexpr bool operator<=(nullopt_t, const optional<T>&) noexcept;
template <class T, class U> constexpr bool operator<=(const optional<T>&, const U&);
template <class T, class U> constexpr bool operator<=(const U&, const optional<T>&);
```

### <a name="parameters"></a>Parametreler

*tarafta*\
, Veya türünde bir `optional` nesne `nullopt_t` `T` .

*Right*\
, Veya türünde bir `optional` nesne `nullopt_t` `T` .

### <a name="return-value"></a>Dönüş Değeri

**`true`** işlecin sol tarafındaki liste işlecin sağ tarafındaki listeden daha küçükse veya eşitse, Aksi takdirde **`false`** .

### <a name="remarks"></a>Açıklamalar

Bu şablon işlevi döndürür `!(right < left)` .

## <a name="operatorgt"></a><a name="op_gt"></a> işlecinde&gt;

`optional`İşlecin sol tarafındaki nesnenin sağ taraftaki nesneden daha büyük olup olmadığını sınar `optional` .

```cpp
template <class T, class U> constexpr bool operator>(const optional<T>&, const optional<U>&);
template <class T> constexpr bool operator>(const optional<T>&, nullopt_t) noexcept;
template <class T> constexpr bool operator>(nullopt_t, const optional<T>&) noexcept;
template <class T, class U> constexpr bool operator>(const optional<T>&, const U&);
template <class T, class U> constexpr bool operator>(const U&, const optional<T>&);
```

### <a name="parameters"></a>Parametreler

*tarafta*\
, Veya türünde bir `optional` nesne `nullopt_t` `T` .

*Right*\
, Veya türünde bir `optional` nesne `nullopt_t` `T` .

### <a name="return-value"></a>Dönüş Değeri

**`true`** işlecin sol tarafındaki liste, işlecin sağ tarafındaki listeden büyükse; Aksi takdirde **`false`** .

### <a name="remarks"></a>Açıklamalar

Bu şablon işlevi döndürür `right < left` .

## <a name="operatorgt"></a><a name="op_gt_eq"></a> işlecinde&gt;=

`optional`İşlecin sol tarafındaki nesnenin sağ taraftaki nesneden büyük veya ona eşit olup olmadığını sınar `optional` .

```cpp
template <class T, class U> constexpr bool operator>=(const optional<T>&, const optional<U>&);
template <class T> constexpr bool operator>=(const optional<T>&, nullopt_t) noexcept;
template <class T> constexpr bool operator>=(nullopt_t, const optional<T>&) noexcept;
template <class T, class U> constexpr bool operator>=(const optional<T>&, const U&);
template <class T, class U> constexpr bool operator>=(const U&, const optional<T>&);
```

### <a name="parameters"></a>Parametreler

*tarafta*\
, Veya türünde bir `optional` nesne `nullopt_t` `T` .

*Right*\
, Veya türünde bir `optional` nesne `nullopt_t` `T` .

### <a name="return-value"></a>Dönüş Değeri

**`true`**`optional`işlecin sol tarafındaki işlecinin sağ tarafından büyük veya ona eşitse `optional` ; Aksi takdirde **`false`** .

### <a name="remarks"></a>Açıklamalar

Şablon işlevi döndürür `!(left < right)` .
