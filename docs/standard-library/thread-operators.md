---
title: '&lt;iş parçacığı &gt; işleçleri'
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
ms.openlocfilehash: e7321831b9356fdb9ae5ce147319726def69efc7
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87215575"
---
# <a name="ltthreadgt-operators"></a>&lt;iş parçacığı &gt; işleçleri

||||
|-|-|-|
|[işleç! =](#op_neq)|[işleç&gt;](#op_gt)|[işleç&gt;=](#op_gt_eq)|
|[işleç&lt;](#op_lt)|[işleç&lt;&lt;](#op_lt_lt)|[işleç&lt;=](#op_lt_eq)|
|[işleç = =](#op_eq_eq)|

## <a name="operatorgt"></a><a name="op_gt_eq"></a>işlecinde&gt;=

Bir `thread::id` nesnenin diğerinden büyük veya ona eşit olup olmadığını belirler.

```cpp
bool operator>= (
    thread::id Left,
    thread::id Right) noexcept
```

### <a name="parameters"></a>Parametreler

*Tarafta*\
Sol `thread::id` nesne.

*Right*\
Doğru `thread::id` nesne.

### <a name="return-value"></a>Dönüş Değeri

`!(Left < Right)`

### <a name="remarks"></a>Açıklamalar

Bu işlev hiçbir özel durum oluşturmaz.

## <a name="operatorgt"></a><a name="op_gt"></a>işlecinde&gt;

Bir `thread::id` nesnenin diğerinden daha büyük olup olmadığını belirler.

```cpp
bool operator> (
    thread::id Left,
    thread::id Right) noexcept
```

### <a name="parameters"></a>Parametreler

*Tarafta*\
Sol `thread::id` nesne.

*Right*\
Doğru `thread::id` nesne.

### <a name="return-value"></a>Dönüş Değeri

`Right < Left`

### <a name="remarks"></a>Açıklamalar

Bu işlev hiçbir özel durum oluşturmaz.

## <a name="operatorlt"></a><a name="op_lt_eq"></a>işlecinde&lt;=

Bir `thread::id` nesnenin diğerine eşit veya ondan küçük olup olmadığını belirler.

```cpp
bool operator<= (
    thread::id Left,
    thread::id Right) noexcept
```

### <a name="parameters"></a>Parametreler

*Tarafta*\
Sol `thread::id` nesne.

*Right*\
Doğru `thread::id` nesne.

### <a name="return-value"></a>Dönüş Değeri

`!(Right < Left)`

### <a name="remarks"></a>Açıklamalar

Bu işlev hiçbir özel durum oluşturmaz.

## <a name="operatorlt"></a><a name="op_lt"></a>işlecinde&lt;

Bir `thread::id` nesnenin diğerinden daha küçük olup olmadığını belirler.

```cpp
bool operator<(
    thread::id Left,
    thread::id Right) noexcept
```

### <a name="parameters"></a>Parametreler

*Tarafta*\
Sol `thread::id` nesne.

*Right*\
Doğru `thread::id` nesne.

### <a name="return-value"></a>Dönüş Değeri

**`true`***sol* , toplam sıralamada *sağ* önceyse; Aksi takdirde, **`false`** .

### <a name="remarks"></a>Açıklamalar

İşleci tüm nesnelerde toplam sıralamayı tanımlar `thread::id` . Bu nesneler, ilişkilendirilebilir kapsayıcılarda anahtar olarak kullanılabilir.

Bu işlev hiçbir özel durum oluşturmaz.

## <a name="operator"></a><a name="op_neq"></a>işleç! =

`thread::id`Eşitsizlik için iki nesneyi karşılaştırır.

```cpp
bool operator!= (
    thread::id Left,
    thread::id Right) noexcept
```

### <a name="parameters"></a>Parametreler

*Tarafta*\
Sol `thread::id` nesne.

*Right*\
Doğru `thread::id` nesne.

### <a name="return-value"></a>Dönüş Değeri

`!(Left == Right)`

### <a name="remarks"></a>Açıklamalar

Bu işlev hiçbir özel durum oluşturmaz.

## <a name="operator"></a><a name="op_eq_eq"></a>işleç = =

, `thread::id` Eşitlik için iki nesneyi karşılaştırır.

```cpp
bool operator== (
    thread::id Left,
    thread::id Right) noexcept
```

### <a name="parameters"></a>Parametreler

*Tarafta*\
Sol `thread::id` nesne.

*Right*\
Doğru `thread::id` nesne.

### <a name="return-value"></a>Dönüş Değeri

**`true`** iki nesne yürütmenin aynı iş parçacığını temsil ediyorsa veya hiçbir nesne yürütmenin iş parçacığını temsil ediyorsa; Aksi takdirde, **`false`** .

### <a name="remarks"></a>Açıklamalar

Bu işlev hiçbir özel durum oluşturmaz.

## <a name="operatorltlt"></a><a name="op_lt_lt"></a>işlecinde&lt;&lt;

Bir nesnenin bir akışa metin temsilini ekler `thread::id` .

```cpp
template <class Elem, class Tr>
basic_ostream<Elem, Tr>& operator<<(
    basic_ostream<Elem, Tr>& Ostr, thread::id Id);
```

### <a name="parameters"></a>Parametreler

*OSTR*\
[Basic_ostream](../standard-library/basic-ostream-class.md) nesnesi.

*Numarasını*\
Bir `thread::id` nesnesi.

### <a name="return-value"></a>Dönüş Değeri

*OSTR*.

### <a name="remarks"></a>Açıklamalar

Bu işlev, *OSTR*içine *kimlik* ekler.

İki `thread::id` nesne eşitse, bu nesnelerin eklenen metin gösterimleri aynıdır.

## <a name="see-also"></a>Ayrıca bkz.

[\<thread>](../standard-library/thread.md)
