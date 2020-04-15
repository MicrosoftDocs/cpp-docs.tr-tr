---
title: '&lt;isteğe bağlı&gt; operatörler'
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
ms.openlocfilehash: 9bdef0669f90da7865f7652ff4528e51e584e1a2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373629"
---
# <a name="ltoptionalgt-operators"></a>&lt;isteğe bağlı&gt; operatörler

## <a name="operator"></a><a name="op_eq_eq"></a>işleç==

Işlecinin `optional` sol tarafındaki nesnenin sağ taraftaki `optional` nesneye eşit olup olmadığını test edin.

```cpp
template <class T, class U> constexpr bool operator==(const optional<T>& left, const optional<U>& right);
template <class T> constexpr bool operator==(const optional<T>& left, nullopt_t right) noexcept;
template <class T> constexpr bool operator==(nullopt_t left, const optional<T>& right) noexcept;
template <class T, class U> constexpr bool operator==(const optional<T>&, const U&);
template <class T, class U> constexpr bool operator==(const U&, const optional<T>&);
```

### <a name="parameters"></a>Parametreler

*Sol*\
Türünde `optional`bir `nullopt_t`nesne `T`, veya .

*Doğru*\
Türünde `optional`bir `nullopt_t`nesne `T`, veya .

## <a name="operator"></a><a name="op_neq"></a>işleç!=

Işlecinin `optional` sol tarafındaki nesnenin sağ taraftaki `optional` nesneye eşit olmamasını test edin.

```cpp
template <class T, class U> constexpr bool operator!=(const optional<T>&, const optional<U>&);
template <class T> constexpr bool operator!=(const optional<T>&, nullopt_t) noexcept;
template <class T> constexpr bool operator!=(nullopt_t, const optional<T>&) noexcept;
template <class T, class U> constexpr bool operator!=(const optional<T>&, const U&);
template <class T, class U> constexpr bool operator!=(const U&, const optional<T>&);
```

### <a name="parameters"></a>Parametreler

*Sol*\
Türünde `optional`bir `nullopt_t`nesne `T`, veya .

*Doğru*\
Türünde `optional`bir `nullopt_t`nesne `T`, veya .

### <a name="remarks"></a>Açıklamalar

Bu şablon `!(left == right)`işlevi döndürür.

## <a name="operatorlt"></a><a name="op_lt"></a>Işleç&lt;

İşleticinin `optional` sol tarafındaki nesnenin sağ taraftaki `optional` nesneden daha az olup olmadığını test edin.

```cpp
template <class T, class U> constexpr bool operator<(const optional<T>&, const optional<U>&);
template <class T> constexpr bool operator<(const optional<T>&, nullopt_t) noexcept;
template <class T> constexpr bool operator<(nullopt_t, const optional<T>&) noexcept;
template <class T, class U> constexpr bool operator<(const optional<T>&, const U&);
template <class T, class U> constexpr bool operator<(const U&, const optional<T>&);
```

### <a name="parameters"></a>Parametreler

*Sol*\
Türünde `optional`bir `nullopt_t`nesne `T`, veya .

*Doğru*\
Türünde `optional`bir `nullopt_t`nesne `T`, veya .

### <a name="return-value"></a>Dönüş Değeri

işlecinin sol tarafındaki liste, işlecinin sağ tarafındaki listeden daha az ama eşit değilse **doğrudur;** aksi takdirde **yanlış**.

## <a name="operatorlt"></a><a name="op_lt_eq"></a>Işleç&lt;=

İşleticinin `optional` sol tarafındaki nesnenin sağ taraftaki `optional` nesneye daha az veya eşit olup olmadığını test edin.

```cpp
template <class T, class U> constexpr bool operator<=(const optional<T>&, const optional<U>&);
template <class T> constexpr bool operator<=(const optional<T>&, nullopt_t) noexcept;
template <class T> constexpr bool operator<=(nullopt_t, const optional<T>&) noexcept;
template <class T, class U> constexpr bool operator<=(const optional<T>&, const U&);
template <class T, class U> constexpr bool operator<=(const U&, const optional<T>&);
```

### <a name="parameters"></a>Parametreler

*Sol*\
Türünde `optional`bir `nullopt_t`nesne `T`, veya .

*Doğru*\
Türünde `optional`bir `nullopt_t`nesne `T`, veya .

### <a name="return-value"></a>Dönüş Değeri

işlecinin sol tarafındaki liste, işlecinin sağ tarafındaki listeden daha az veya eşitse **doğrudur;** aksi takdirde **yanlış**.

### <a name="remarks"></a>Açıklamalar

Bu şablon `!(right < left)`işlevi döndürür.

## <a name="operatorgt"></a><a name="op_gt"></a>Işleç&gt;

İşleticinin `optional` sol tarafındaki nesnenin sağ taraftaki `optional` nesneden büyük olup olmadığını test edin.

```cpp
template <class T, class U> constexpr bool operator>(const optional<T>&, const optional<U>&);
template <class T> constexpr bool operator>(const optional<T>&, nullopt_t) noexcept;
template <class T> constexpr bool operator>(nullopt_t, const optional<T>&) noexcept;
template <class T, class U> constexpr bool operator>(const optional<T>&, const U&);
template <class T, class U> constexpr bool operator>(const U&, const optional<T>&);
```

### <a name="parameters"></a>Parametreler

*Sol*\
Türünde `optional`bir `nullopt_t`nesne `T`, veya .

*Doğru*\
Türünde `optional`bir `nullopt_t`nesne `T`, veya .

### <a name="return-value"></a>Dönüş Değeri

işlecinin sol tarafındaki liste işlecinin sağ tarafındaki listeden büyükse **doğrudur;** aksi takdirde **yanlış**.

### <a name="remarks"></a>Açıklamalar

Bu şablon `right < left`işlevi döndürür.

## <a name="operatorgt"></a><a name="op_gt_eq"></a>Işleç&gt;=

İşleticinin `optional` sol tarafındaki nesnenin sağ taraftaki `optional` nesneyden büyük veya eşit olup olmadığını test edin.

```cpp
template <class T, class U> constexpr bool operator>=(const optional<T>&, const optional<U>&);
template <class T> constexpr bool operator>=(const optional<T>&, nullopt_t) noexcept;
template <class T> constexpr bool operator>=(nullopt_t, const optional<T>&) noexcept;
template <class T, class U> constexpr bool operator>=(const optional<T>&, const U&);
template <class T, class U> constexpr bool operator>=(const U&, const optional<T>&);
```

### <a name="parameters"></a>Parametreler

*Sol*\
Türünde `optional`bir `nullopt_t`nesne `T`, veya .

*Doğru*\
Türünde `optional`bir `nullopt_t`nesne `T`, veya .

### <a name="return-value"></a>Dönüş Değeri

işlecinin `optional` sol tarafındaki işleç sağ taraftan daha `optional` büyük veya eşitse **doğrudur;** aksi takdirde **yanlış**.

### <a name="remarks"></a>Açıklamalar

Şablon işlevi `!(left < right)`döndürür.
