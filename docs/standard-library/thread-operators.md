---
title: '&lt;iş&gt; parçacığı işleçleri'
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
ms.openlocfilehash: 6312d14dc681736ee396d5c7af6c50ba8d72cd3a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375826"
---
# <a name="ltthreadgt-operators"></a>&lt;iş&gt; parçacığı işleçleri

||||
|-|-|-|
|[işleç!=](#op_neq)|[Işleç&gt;](#op_gt)|[Işleç&gt;=](#op_gt_eq)|
|[Işleç&lt;](#op_lt)|[Işleç&lt;&lt;](#op_lt_lt)|[Işleç&lt;=](#op_lt_eq)|
|[işleç==](#op_eq_eq)|

## <a name="operatorgt"></a><a name="op_gt_eq"></a>Işleç&gt;=

Bir `thread::id` nesnenin diğerinden büyük mü yoksa diğerine eşit mi olduğunu belirler.

```cpp
bool operator>= (
    thread::id Left,
    thread::id Right) noexcept
```

### <a name="parameters"></a>Parametreler

*Sol*\
Sol `thread::id` nesne.

*Doğru*\
Doğru `thread::id` nesne.

### <a name="return-value"></a>Dönüş Değeri

`!(Left < Right)`

### <a name="remarks"></a>Açıklamalar

Bu işlev herhangi bir özel durum atmaz.

## <a name="operatorgt"></a><a name="op_gt"></a>Işleç&gt;

Bir `thread::id` nesnenin diğerinden büyük olup olmadığını belirler.

```cpp
bool operator> (
    thread::id Left,
    thread::id Right) noexcept
```

### <a name="parameters"></a>Parametreler

*Sol*\
Sol `thread::id` nesne.

*Doğru*\
Doğru `thread::id` nesne.

### <a name="return-value"></a>Dönüş Değeri

`Right < Left`

### <a name="remarks"></a>Açıklamalar

Bu işlev herhangi bir özel durum atmaz.

## <a name="operatorlt"></a><a name="op_lt_eq"></a>Işleç&lt;=

Bir `thread::id` nesnenin diğerinden küçük mü yoksa diğerine eşit mi olduğunu belirler.

```cpp
bool operator<= (
    thread::id Left,
    thread::id Right) noexcept
```

### <a name="parameters"></a>Parametreler

*Sol*\
Sol `thread::id` nesne.

*Doğru*\
Doğru `thread::id` nesne.

### <a name="return-value"></a>Dönüş Değeri

`!(Right < Left)`

### <a name="remarks"></a>Açıklamalar

Bu işlev herhangi bir özel durum atmaz.

## <a name="operatorlt"></a><a name="op_lt"></a>Işleç&lt;

Bir `thread::id` nesnenin diğerinden küçük olup olmadığını belirler.

```cpp
bool operator<(
    thread::id Left,
    thread::id Right) noexcept
```

### <a name="parameters"></a>Parametreler

*Sol*\
Sol `thread::id` nesne.

*Doğru*\
Doğru `thread::id` nesne.

### <a name="return-value"></a>Dönüş Değeri

*sol* toplam sıralama *sağ* önce ise **doğrudur;** aksi takdirde, **yanlış**.

### <a name="remarks"></a>Açıklamalar

İşleç tüm `thread::id` nesnelerde toplam sıralama tanımlar. Bu nesneler, bağdaştırıcı kaplarda anahtar olarak kullanılabilir.

Bu işlev herhangi bir özel durum atmaz.

## <a name="operator"></a><a name="op_neq"></a>işleç!=

Eşitsizlik için `thread::id` iki nesneyi karşılaştırır.

```cpp
bool operator!= (
    thread::id Left,
    thread::id Right) noexcept
```

### <a name="parameters"></a>Parametreler

*Sol*\
Sol `thread::id` nesne.

*Doğru*\
Doğru `thread::id` nesne.

### <a name="return-value"></a>Dönüş Değeri

`!(Left == Right)`

### <a name="remarks"></a>Açıklamalar

Bu işlev herhangi bir özel durum atmaz.

## <a name="operator"></a><a name="op_eq_eq"></a>işleç==

Eşitlik için `thread::id` iki nesneyi karşılaştırır.

```cpp
bool operator== (
    thread::id Left,
    thread::id Right) noexcept
```

### <a name="parameters"></a>Parametreler

*Sol*\
Sol `thread::id` nesne.

*Doğru*\
Doğru `thread::id` nesne.

### <a name="return-value"></a>Dönüş Değeri

iki nesne aynı yürütme dizisini temsil ediyorsa veya nesne yürütme iş parçacığıtemsil **değilse;** aksi takdirde, **yanlış**.

### <a name="remarks"></a>Açıklamalar

Bu işlev herhangi bir özel durum atmaz.

## <a name="operatorltlt"></a><a name="op_lt_lt"></a>Işleç&lt;&lt;

Bir `thread::id` nesnenin metin gösterimini bir akışa ekler.

```cpp
template <class Elem, class Tr>
basic_ostream<Elem, Tr>& operator<<(
    basic_ostream<Elem, Tr>& Ostr, thread::id Id);
```

### <a name="parameters"></a>Parametreler

*Ostr*\
[basic_ostream](../standard-library/basic-ostream-class.md) bir nesne.

*Kimliği*\
Bir `thread::id` nesnesi.

### <a name="return-value"></a>Dönüş Değeri

*Ostr.*

### <a name="remarks"></a>Açıklamalar

Bu işlev *Ostr*içine *Id* ekler.

İki `thread::id` nesne eşit olarak karşılaştırırsa, bu nesnelerin eklenen metin gösterimleri aynıdır.

## <a name="see-also"></a>Ayrıca bkz.

[\<iş parçacığı>](../standard-library/thread.md)
