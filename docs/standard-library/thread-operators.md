---
title: '&lt;iş parçacığı&gt; işleçleri'
ms.date: 11/04/2016
f1_keywords:
- thread/std::operator!=
- thread/std::operator&gt;
- thread/std::operator&gt;=
- thread/std::operator&lt;
- thread/std::operator&lt;&lt;
- thread/std::operator&lt;=
- thread/std::operator==
ms.assetid: e6bb6c0f-64f9-4cb2-9ff2-05b88a6ba7ac
helpviewer_keywords:
- std::operator!= (thread)
- std::operator&gt; (thread)
- std::operator&gt;= (thread)
- std::operator&lt; (thread)
- std::operator&lt;&lt; (thread)
- std::operator&lt;= (thread)
- std::operator== (thread)
ms.openlocfilehash: 5a2fd845598ac9f9c983bf53cbd7665ef66ffb70
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62412052"
---
# <a name="ltthreadgt-operators"></a>&lt;iş parçacığı&gt; işleçleri

||||
|-|-|-|
|[operator!=](#op_neq)|[İşleci&gt;](#op_gt)|[İşleci&gt;=](#op_gt_eq)|
|[İşleci&lt;](#op_lt)|[İşleci&lt;&lt;](#op_lt_lt)|[İşleci&lt;=](#op_lt_eq)|
|[operator==](#op_eq_eq)|

## <a name="op_gt_eq"></a>  İşleci&gt;=

Az olup olmadığını belirler `thread::id` büyüktür veya eşittir başka bir nesne.

```cpp
bool operator>= (
    thread::id Left,
    thread::id Right) noexcept
```

### <a name="parameters"></a>Parametreler

*Sol*<br/>
Sol `thread::id` nesne.

*sağ*<br/>
Sağa `thread::id` nesne.

### <a name="return-value"></a>Dönüş Değeri

`!(Left < Right)`

### <a name="remarks"></a>Açıklamalar

Bu işlev bir özel durum oluşturmaz.

## <a name="op_gt"></a>  İşleci&gt;

Az olup olmadığını belirler `thread::id` nesnedir diğerinden daha büyük.

```cpp
bool operator> (
    thread::id Left,
    thread::id Right) noexcept
```

### <a name="parameters"></a>Parametreler

*Sol*<br/>
Sol `thread::id` nesne.

*sağ*<br/>
Sağa `thread::id` nesne.

### <a name="return-value"></a>Dönüş Değeri

`Right < Left`

### <a name="remarks"></a>Açıklamalar

Bu işlev bir özel durum oluşturmaz.

## <a name="op_lt_eq"></a>  İşleci&lt;=

Az olup olmadığını belirler `thread::id` küçüktür veya eşittir başka bir nesne değil.

```cpp
bool operator<= (
    thread::id Left,
    thread::id Right) noexcept
```

### <a name="parameters"></a>Parametreler

*Sol*<br/>
Sol `thread::id` nesne.

*sağ*<br/>
Sağa `thread::id` nesne.

### <a name="return-value"></a>Dönüş Değeri

`!(Right < Left)`

### <a name="remarks"></a>Açıklamalar

Bu işlev bir özel durum oluşturmaz.

## <a name="op_lt"></a>  İşleci&lt;

Az olup olmadığını belirler `thread::id` başka bir nesne değil.

```cpp
bool operator<(
    thread::id Left,
    thread::id Right) noexcept
```

### <a name="parameters"></a>Parametreler

*Sol*<br/>
Sol `thread::id` nesne.

*sağ*<br/>
Sağa `thread::id` nesne.

### <a name="return-value"></a>Dönüş Değeri

**doğru** varsa *sol* önündeki *sağ* içinde toplam sıralama; Aksi takdirde, **false**.

### <a name="remarks"></a>Açıklamalar

İşleci bir toplam tüm sıralamasını tanımlar `thread::id` nesneleri. Bu nesneler, ilişkili kapsayıcılar anahtar olarak kullanılabilir.

Bu işlev bir özel durum oluşturmaz.

## <a name="op_neq"></a>  işleç! =

İki karşılaştırır `thread::id` nesneleri için eşitsizlik.

```cpp
bool operator!= (
    thread::id Left,
    thread::id Right) noexcept
```

### <a name="parameters"></a>Parametreler

*Sol*<br/>
Sol `thread::id` nesne.

*sağ*<br/>
Sağa `thread::id` nesne.

### <a name="return-value"></a>Dönüş Değeri

`!(Left == Right)`

### <a name="remarks"></a>Açıklamalar

Bu işlev bir özel durum oluşturmaz.

## <a name="op_eq_eq"></a>  işleç ==

İki karşılaştırır `thread::id` eşitlik için nesneleri.

```cpp
bool operator== (
    thread::id Left,
    thread::id Right) noexcept
```

### <a name="parameters"></a>Parametreler

*Sol*<br/>
Sol `thread::id` nesne.

*sağ*<br/>
Sağa `thread::id` nesne.

### <a name="return-value"></a>Dönüş Değeri

**doğru** iki nesnenin aynı iş parçacığı yürütme temsil ediyorsa veya bir iş parçacığı yürütme; her iki nesne temsil ediyorsa Aksi takdirde, **false**.

### <a name="remarks"></a>Açıklamalar

Bu işlev bir özel durum oluşturmaz.

## <a name="op_lt_lt"></a>  İşleci&lt;&lt;

Bir metin temsilini ekler bir `thread::id` bir akış nesnesine.

```cpp
template <class Elem, class Tr>
basic_ostream<Elem, Tr>& operator<<(
    basic_ostream<Elem, Tr>& Ostr, thread::id Id);
```

### <a name="parameters"></a>Parametreler

*Ostr*<br/>
A [basic_ostream](../standard-library/basic-ostream-class.md) nesne.

*Kimlik*<br/>
A `thread::id` nesne.

### <a name="return-value"></a>Dönüş Değeri

*Ostr*.

### <a name="remarks"></a>Açıklamalar

Bu işlev ekler *kimliği* içine *Ostr*.

İki `thread::id` nesneler eşit karşılaştırın, söz konusu nesnelerin eklenen metin temsilleridir aynıdır.

## <a name="see-also"></a>Ayrıca bkz.

[\<iş parçacığı >](../standard-library/thread.md)<br/>
