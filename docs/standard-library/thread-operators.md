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
ms.openlocfilehash: c0593b8016cf45abe64114958ccda84eb3704844
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68458437"
---
# <a name="ltthreadgt-operators"></a>&lt;iş&gt; parçacığı işleçleri

||||
|-|-|-|
|[operator!=](#op_neq)|[işlecinde&gt;](#op_gt)|[işlecinde&gt;=](#op_gt_eq)|
|[işlecinde&lt;](#op_lt)|[işlecinde&lt;&lt;](#op_lt_lt)|[işlecinde&lt;=](#op_lt_eq)|
|[operator==](#op_eq_eq)|

## <a name="op_gt_eq"></a>işlecinde&gt;=

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

## <a name="op_gt"></a>işlecinde&gt;

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

## <a name="op_lt_eq"></a>işlecinde&lt;=

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

## <a name="op_lt"></a>işlecinde&lt;

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

*sol* , toplam sıralamada *sağ* önceyse **doğru** . Aksi takdirde, **false**.

### <a name="remarks"></a>Açıklamalar

İşleci tüm `thread::id` nesnelerde toplam sıralamayı tanımlar. Bu nesneler, ilişkilendirilebilir kapsayıcılarda anahtar olarak kullanılabilir.

Bu işlev hiçbir özel durum oluşturmaz.

## <a name="op_neq"></a>işleç! =

Eşitsizlik için `thread::id` iki nesneyi karşılaştırır.

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

## <a name="op_eq_eq"></a>işleç = =

, Eşitlik `thread::id` için iki nesneyi karşılaştırır.

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

iki nesne yürütmenin aynı iş parçacığını temsil ediyorsa veya hiçbir nesne bir yürütme iş parçacığını temsil ediyorsa, **true** ; Aksi takdirde, **false**.

### <a name="remarks"></a>Açıklamalar

Bu işlev hiçbir özel durum oluşturmaz.

## <a name="op_lt_lt"></a>işlecinde&lt;&lt;

Bir `thread::id` nesnenin bir akışa metin temsilini ekler.

```cpp
template <class Elem, class Tr>
basic_ostream<Elem, Tr>& operator<<(
    basic_ostream<Elem, Tr>& Ostr, thread::id Id);
```

### <a name="parameters"></a>Parametreler

*OSTR*\
Bir [basic_ostream](../standard-library/basic-ostream-class.md) nesnesi.

*Numarasını*\
A `thread::id` nesne.

### <a name="return-value"></a>Dönüş Değeri

*OSTR*.

### <a name="remarks"></a>Açıklamalar

Bu işlev, *OSTR*içine *kimlik* ekler.

İki `thread::id` nesne eşitse, bu nesnelerin eklenen metin gösterimleri aynıdır.

## <a name="see-also"></a>Ayrıca bkz.

[\<iş parçacığı >](../standard-library/thread.md)
