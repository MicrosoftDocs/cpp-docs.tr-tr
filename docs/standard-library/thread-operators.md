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
ms.openlocfilehash: c0593b8016cf45abe64114958ccda84eb3704844
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/06/2020
ms.locfileid: "78876183"
---
# <a name="ltthreadgt-operators"></a>&lt;iş parçacığı&gt; işleçleri

||||
|-|-|-|
|[operator!=](#op_neq)|[işleç&gt;](#op_gt)|[işleç&gt;=](#op_gt_eq)|
|[işleç&lt;](#op_lt)|[işleç&lt;&lt;](#op_lt_lt)|[işleç&lt;=](#op_lt_eq)|
|[işleç = =](#op_eq_eq)|

## <a name="op_gt_eq"></a>işleç&gt;=

Bir `thread::id` nesnesinin diğerinden büyük veya ona eşit olup olmadığını belirler.

```cpp
bool operator>= (
    thread::id Left,
    thread::id Right) noexcept
```

### <a name="parameters"></a>Parametreler

*Sol*\
Sol `thread::id` nesnesi.

*Sağ*\
Doğru `thread::id` nesnesi.

### <a name="return-value"></a>Dönüş Değeri

`!(Left < Right)`

### <a name="remarks"></a>Açıklamalar

Bu işlev hiçbir özel durum oluşturmaz.

## <a name="op_gt"></a>işleç&gt;

Bir `thread::id` nesnesinin diğerinden daha büyük olup olmadığını belirler.

```cpp
bool operator> (
    thread::id Left,
    thread::id Right) noexcept
```

### <a name="parameters"></a>Parametreler

*Sol*\
Sol `thread::id` nesnesi.

*Sağ*\
Doğru `thread::id` nesnesi.

### <a name="return-value"></a>Dönüş Değeri

`Right < Left`

### <a name="remarks"></a>Açıklamalar

Bu işlev hiçbir özel durum oluşturmaz.

## <a name="op_lt_eq"></a>işleç&lt;=

Bir `thread::id` nesnesinin diğerinden daha küçük veya ona eşit olup olmadığını belirler.

```cpp
bool operator<= (
    thread::id Left,
    thread::id Right) noexcept
```

### <a name="parameters"></a>Parametreler

*Sol*\
Sol `thread::id` nesnesi.

*Sağ*\
Doğru `thread::id` nesnesi.

### <a name="return-value"></a>Dönüş Değeri

`!(Right < Left)`

### <a name="remarks"></a>Açıklamalar

Bu işlev hiçbir özel durum oluşturmaz.

## <a name="op_lt"></a>işleç&lt;

Bir `thread::id` nesnesinin diğerinden daha küçük olup olmadığını belirler.

```cpp
bool operator<(
    thread::id Left,
    thread::id Right) noexcept
```

### <a name="parameters"></a>Parametreler

*Sol*\
Sol `thread::id` nesnesi.

*Sağ*\
Doğru `thread::id` nesnesi.

### <a name="return-value"></a>Dönüş Değeri

*sol* , toplam sıralamada *sağ* önceyse **doğru** . Aksi takdirde, **false**.

### <a name="remarks"></a>Açıklamalar

İşleci tüm `thread::id` nesnelerinde toplam sıralamayı tanımlar. Bu nesneler, ilişkilendirilebilir kapsayıcılarda anahtar olarak kullanılabilir.

Bu işlev hiçbir özel durum oluşturmaz.

## <a name="op_neq"></a>işleç! =

Eşitsizlik için iki `thread::id` nesnesini karşılaştırır.

```cpp
bool operator!= (
    thread::id Left,
    thread::id Right) noexcept
```

### <a name="parameters"></a>Parametreler

*Sol*\
Sol `thread::id` nesnesi.

*Sağ*\
Doğru `thread::id` nesnesi.

### <a name="return-value"></a>Dönüş Değeri

`!(Left == Right)`

### <a name="remarks"></a>Açıklamalar

Bu işlev hiçbir özel durum oluşturmaz.

## <a name="op_eq_eq"></a>işleç = =

, Eşitlik için iki `thread::id` nesnesini karşılaştırır.

```cpp
bool operator== (
    thread::id Left,
    thread::id Right) noexcept
```

### <a name="parameters"></a>Parametreler

*Sol*\
Sol `thread::id` nesnesi.

*Sağ*\
Doğru `thread::id` nesnesi.

### <a name="return-value"></a>Dönüş Değeri

iki nesne yürütmenin aynı iş parçacığını temsil ediyorsa veya hiçbir nesne bir yürütme iş parçacığını temsil ediyorsa, **true** ; Aksi takdirde, **false**.

### <a name="remarks"></a>Açıklamalar

Bu işlev hiçbir özel durum oluşturmaz.

## <a name="op_lt_lt"></a>işleç&lt;&lt;

Bir `thread::id` nesnesinin bir akışa metin temsilini ekler.

```cpp
template <class Elem, class Tr>
basic_ostream<Elem, Tr>& operator<<(
    basic_ostream<Elem, Tr>& Ostr, thread::id Id);
```

### <a name="parameters"></a>Parametreler

*OSTR*\
[Basic_ostream](../standard-library/basic-ostream-class.md) nesnesi.

*Kimlik*\
Bir `thread::id` nesnesi.

### <a name="return-value"></a>Dönüş Değeri

*OSTR*.

### <a name="remarks"></a>Açıklamalar

Bu işlev, *OSTR*içine *kimlik* ekler.

İki `thread::id` nesnesi eşit olarak karşılaştırırsanız, bu nesnelerin eklenen metin gösterimleri aynı olanlardır.

## <a name="see-also"></a>Ayrıca bkz.

[\<iş parçacığı >](../standard-library/thread.md)
