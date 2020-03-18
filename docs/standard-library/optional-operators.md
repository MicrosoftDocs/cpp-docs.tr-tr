---
title: isteğe bağlı&gt; işleçleri &lt;
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
ms.openlocfilehash: c5d0de435180054b186400384fc0583df5b03246
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/16/2020
ms.locfileid: "79419695"
---
# <a name="ltoptionalgt-operators"></a>isteğe bağlı&gt; işleçleri &lt;

## <a name="op_eq_eq"></a>işleç = =

İşlecin sol tarafındaki `optional` nesnesinin sağ taraftaki `optional` nesnesine eşit olup olmadığını sınar.

```cpp
template <class T, class U> constexpr bool operator==(const optional<T>& left, const optional<U>& right);
template <class T> constexpr bool operator==(const optional<T>& left, nullopt_t right) noexcept;
template <class T> constexpr bool operator==(nullopt_t left, const optional<T>& right) noexcept;
template <class T, class U> constexpr bool operator==(const optional<T>&, const U&);
template <class T, class U> constexpr bool operator==(const U&, const optional<T>&);
```

### <a name="parameters"></a>Parametreler

*sol*\
`optional`, `nullopt_t`veya `T`türünde bir nesne.

*sağ*\
`optional`, `nullopt_t`veya `T`türünde bir nesne.

## <a name="op_neq"></a>işleç! =

İşlecin sol tarafındaki `optional` nesnesinin sağ taraftaki `optional` nesnesine eşit olup olmadığını sınar.

```cpp
template <class T, class U> constexpr bool operator!=(const optional<T>&, const optional<U>&);
template <class T> constexpr bool operator!=(const optional<T>&, nullopt_t) noexcept;
template <class T> constexpr bool operator!=(nullopt_t, const optional<T>&) noexcept;
template <class T, class U> constexpr bool operator!=(const optional<T>&, const U&);
template <class T, class U> constexpr bool operator!=(const U&, const optional<T>&);
```

### <a name="parameters"></a>Parametreler

*sol*\
`optional`, `nullopt_t`veya `T`türünde bir nesne.

*sağ*\
`optional`, `nullopt_t`veya `T`türünde bir nesne.

### <a name="remarks"></a>Açıklamalar

Bu şablon işlevi `!(left == right)`döndürür.

## <a name="op_lt"></a>işleç&lt;

İşlecin sol tarafındaki `optional` nesnesinin sağ taraftaki `optional` nesnesinden küçük olup olmadığını sınar.

```cpp
template <class T, class U> constexpr bool operator<(const optional<T>&, const optional<U>&);
template <class T> constexpr bool operator<(const optional<T>&, nullopt_t) noexcept;
template <class T> constexpr bool operator<(nullopt_t, const optional<T>&) noexcept;
template <class T, class U> constexpr bool operator<(const optional<T>&, const U&);
template <class T, class U> constexpr bool operator<(const U&, const optional<T>&);
```

### <a name="parameters"></a>Parametreler

*sol*\
`optional`, `nullopt_t`veya `T`türünde bir nesne.

*sağ*\
`optional`, `nullopt_t`veya `T`türünde bir nesne.

### <a name="return-value"></a>Dönüş Değeri

işlecin sol tarafındaki liste, işlecin sağ tarafındaki listeye eşit ancak bundan küçükse **true** ; Aksi halde **yanlış**.

## <a name="op_lt_eq"></a>işleç&lt;=

İşlecin sol tarafındaki `optional` nesnesinin sağ taraftaki `optional` nesnesinden küçük veya ona eşit olup olmadığını sınar.

```cpp
template <class T, class U> constexpr bool operator<=(const optional<T>&, const optional<U>&);
template <class T> constexpr bool operator<=(const optional<T>&, nullopt_t) noexcept;
template <class T> constexpr bool operator<=(nullopt_t, const optional<T>&) noexcept;
template <class T, class U> constexpr bool operator<=(const optional<T>&, const U&);
template <class T, class U> constexpr bool operator<=(const U&, const optional<T>&);
```

### <a name="parameters"></a>Parametreler

*sol*\
`optional`, `nullopt_t`veya `T`türünde bir nesne.

*sağ*\
`optional`, `nullopt_t`veya `T`türünde bir nesne.

### <a name="return-value"></a>Dönüş Değeri

işlecin sol tarafındaki liste, işlecin sağ tarafındaki listeden daha küçükse veya eşitse **doğru** . Aksi halde **yanlış**.

### <a name="remarks"></a>Açıklamalar

Bu şablon işlevi `!(right < left)`döndürür.

## <a name="op_gt"></a>işleç&gt;

İşlecin sol tarafındaki `optional` nesnesinin sağ taraftaki `optional` nesnesinden büyük olup olmadığını sınar.

```cpp
template <class T, class U> constexpr bool operator>(const optional<T>&, const optional<U>&);
template <class T> constexpr bool operator>(const optional<T>&, nullopt_t) noexcept;
template <class T> constexpr bool operator>(nullopt_t, const optional<T>&) noexcept;
template <class T, class U> constexpr bool operator>(const optional<T>&, const U&);
template <class T, class U> constexpr bool operator>(const U&, const optional<T>&);
```

### <a name="parameters"></a>Parametreler

*sol*\
`optional`, `nullopt_t`veya `T`türünde bir nesne.

*sağ*\
`optional`, `nullopt_t`veya `T`türünde bir nesne.

### <a name="return-value"></a>Dönüş Değeri

işlecin sol tarafındaki liste, işlecin sağ tarafındaki listeden büyükse **true** ; Aksi halde **yanlış**.

### <a name="remarks"></a>Açıklamalar

Bu şablon işlevi `right < left`döndürür.

## <a name="op_gt_eq"></a>işleç&gt;=

İşlecin sol tarafındaki `optional` nesnesinin sağ taraftaki `optional` nesnesinden büyük veya ona eşit olup olmadığını sınar.

```cpp
template <class T, class U> constexpr bool operator>=(const optional<T>&, const optional<U>&);
template <class T> constexpr bool operator>=(const optional<T>&, nullopt_t) noexcept;
template <class T> constexpr bool operator>=(nullopt_t, const optional<T>&) noexcept;
template <class T, class U> constexpr bool operator>=(const optional<T>&, const U&);
template <class T, class U> constexpr bool operator>=(const U&, const optional<T>&);
```

### <a name="parameters"></a>Parametreler

*sol*\
`optional`, `nullopt_t`veya `T`türünde bir nesne.

*sağ*\
`optional`, `nullopt_t`veya `T`türünde bir nesne.

### <a name="return-value"></a>Dönüş Değeri

işlecin sol tarafındaki `optional` işlecin sağ tarafındaki `optional` daha büyükse veya buna eşitse **true** ; Aksi halde **yanlış**.

### <a name="remarks"></a>Açıklamalar

Şablon işlevi `!(left < right)`döndürür.
