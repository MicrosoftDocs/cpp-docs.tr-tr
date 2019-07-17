---
title: '&lt;İsteğe bağlı&gt; işleçleri'
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
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68268032"
---
# <a name="ltoptionalgt-operators"></a>&lt;İsteğe bağlı&gt; işleçleri

## <a name="op_eq_eq"></a> işleç ==

Olmadığını test eder `optional` işlecin sol tarafındaki nesnesinin eşit olup `optional` işlecin sağ tarafındaki nesne.

```cpp
template <class T, class U> constexpr bool operator==(const optional<T>& left, const optional<U>& right);
template <class T> constexpr bool operator==(const optional<T>& left, nullopt_t right) noexcept;
template <class T> constexpr bool operator==(nullopt_t left, const optional<T>& right) noexcept;
template <class T, class U> constexpr bool operator==(const optional<T>&, const U&);
template <class T, class U> constexpr bool operator==(const U&, const optional<T>&);
```

### <a name="parameters"></a>Parametreler

*Sol*\
Bir nesne türü `optional`, `nullopt_t`, veya `T`.

*sağ*\
Bir nesne türü `optional`, `nullopt_t`, veya `T`.

## <a name="op_neq"></a> işleç! =

Olmadığını test eder `optional` işlecinin sol tarafındaki nesnesi eşit değil `optional` işlecin sağ tarafındaki nesne.

```cpp
template <class T, class U> constexpr bool operator!=(const optional<T>&, const optional<U>&);
template <class T> constexpr bool operator!=(const optional<T>&, nullopt_t) noexcept;
template <class T> constexpr bool operator!=(nullopt_t, const optional<T>&) noexcept;
template <class T, class U> constexpr bool operator!=(const optional<T>&, const U&);
template <class T, class U> constexpr bool operator!=(const U&, const optional<T>&);
```

### <a name="parameters"></a>Parametreler

*Sol*\
Bir nesne türü `optional`, `nullopt_t`, veya `T`.

*sağ*\
Bir nesne türü `optional`, `nullopt_t`, veya `T`.

### <a name="remarks"></a>Açıklamalar

Bu şablon işlevinin döndürdüğü `!(left == right)`.

## <a name="op_lt"></a> İşleci&lt;

Olmadığını test eder `optional` nesne işlecinin sol tarafındaki küçüktür `optional` işlecin sağ tarafındaki nesne.

```cpp
template <class T, class U> constexpr bool operator<(const optional<T>&, const optional<U>&);
template <class T> constexpr bool operator<(const optional<T>&, nullopt_t) noexcept;
template <class T> constexpr bool operator<(nullopt_t, const optional<T>&) noexcept;
template <class T, class U> constexpr bool operator<(const optional<T>&, const U&);
template <class T, class U> constexpr bool operator<(const U&, const optional<T>&);
```

### <a name="parameters"></a>Parametreler

*Sol*\
Bir nesne türü `optional`, `nullopt_t`, veya `T`.

*sağ*\
Bir nesne türü `optional`, `nullopt_t`, veya `T`.

### <a name="return-value"></a>Dönüş Değeri

**doğru** işlecinin sol tarafındaki listenin daha ancak değil işlecin sağ tarafındaki listenin eşit Aksi takdirde küçükse **false**.

## <a name="op_lt_eq"></a>  İşleci&lt;=

Olmadığını test eder `optional` işlecin sol tarafındaki nesnesinin değerinden küçük veya buna eşit olup `optional` işlecin sağ tarafındaki nesne.

```cpp
template <class T, class U> constexpr bool operator<=(const optional<T>&, const optional<U>&);
template <class T> constexpr bool operator<=(const optional<T>&, nullopt_t) noexcept;
template <class T> constexpr bool operator<=(nullopt_t, const optional<T>&) noexcept;
template <class T, class U> constexpr bool operator<=(const optional<T>&, const U&);
template <class T, class U> constexpr bool operator<=(const U&, const optional<T>&);
```

### <a name="parameters"></a>Parametreler

*Sol*\
Bir nesne türü `optional`, `nullopt_t`, veya `T`.

*sağ*\
Bir nesne türü `optional`, `nullopt_t`, veya `T`.

### <a name="return-value"></a>Dönüş Değeri

**doğru** işlecinin sol tarafındaki listenin daha veya işlecin sağ tarafındaki listenin eşittir; Aksi takdirde küçükse **false**.

### <a name="remarks"></a>Açıklamalar

Bu şablon işlevinin döndürdüğü `!(right < left)`.

## <a name="op_gt"></a> İşleci&gt;

Olmadığını test eder `optional` nesne işlecinin sol tarafındaki büyük `optional` işlecin sağ tarafındaki nesne.

```cpp
template <class T, class U> constexpr bool operator>(const optional<T>&, const optional<U>&);
template <class T> constexpr bool operator>(const optional<T>&, nullopt_t) noexcept;
template <class T> constexpr bool operator>(nullopt_t, const optional<T>&) noexcept;
template <class T, class U> constexpr bool operator>(const optional<T>&, const U&);
template <class T, class U> constexpr bool operator>(const U&, const optional<T>&);
```

### <a name="parameters"></a>Parametreler

*Sol*\
Bir nesne türü `optional`, `nullopt_t`, veya `T`.

*sağ*\
Bir nesne türü `optional`, `nullopt_t`, veya `T`.

### <a name="return-value"></a>Dönüş Değeri

**doğru** işlecinin sol tarafındaki listenin ise, aksi takdirde listede bir işlecin sağ tarafındaki büyük **false**.

### <a name="remarks"></a>Açıklamalar

Bu şablon işlevinin döndürdüğü `right < left`.

## <a name="op_gt_eq"></a> İşleci&gt;=

Olmadığını test eder `optional` işlecin sol tarafındaki nesnesinin değerinden büyük veya ona eşit olup `optional` işlecin sağ tarafındaki nesne.

```cpp
template <class T, class U> constexpr bool operator>=(const optional<T>&, const optional<U>&);
template <class T> constexpr bool operator>=(const optional<T>&, nullopt_t) noexcept;
template <class T> constexpr bool operator>=(nullopt_t, const optional<T>&) noexcept;
template <class T, class U> constexpr bool operator>=(const optional<T>&, const U&);
template <class T, class U> constexpr bool operator>=(const U&, const optional<T>&);
```

### <a name="parameters"></a>Parametreler

*Sol*\
Bir nesne türü `optional`, `nullopt_t`, veya `T`.

*sağ*\
Bir nesne türü `optional`, `nullopt_t`, veya `T`.

### <a name="return-value"></a>Dönüş Değeri

**doğru** varsa `optional` büyüktür veya eşittir işleci sol tarafında olduğu `optional` ; işlecin sağ tarafındaki aksi **false**.

### <a name="remarks"></a>Açıklamalar

Şablon işlevinin döndürdüğü `!(left < right)`.
