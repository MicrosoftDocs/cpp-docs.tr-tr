---
title: '&lt;iş parçacığı&gt; işleçleri | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- thread/std::operator!=
- thread/std::operator&gt;
- thread/std::operator&gt;=
- thread/std::operator&lt;
- thread/std::operator&lt;&lt;
- thread/std::operator&lt;=
- thread/std::operator==
dev_langs:
- C++
ms.assetid: e6bb6c0f-64f9-4cb2-9ff2-05b88a6ba7ac
caps.latest.revision: 11
manager: ghogen
helpviewer_keywords:
- std::operator!= (thread)
- std::operator&gt; (thread)
- std::operator&gt;= (thread)
- std::operator&lt; (thread)
- std::operator&lt;&lt; (thread)
- std::operator&lt;= (thread)
- std::operator== (thread)
ms.openlocfilehash: 58c690b51d51a75b644430aaf4e5b3eeb672ae5a
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="ltthreadgt-operators"></a>&lt;iş parçacığı&gt; işleçleri

||||
|-|-|-|
|[operator!=](#op_neq)|[işleci&gt;](#op_gt)|[işleci&gt;=](#op_gt_eq)|
|[işleci&lt;](#op_lt)|[işleci&lt;&lt;](#op_lt_lt)|[işleci&lt;=](#op_lt_eq)|
|[operator==](#op_eq_eq)|

## <a name="op_gt_eq"></a>  işleci&gt;=

Bir olup olmadığını belirleyen `thread::id` nesnesidir başka eşit veya daha büyük.

```cpp
bool operator>= (
    thread::id Left,
    thread::id Right) noexcept
```

### <a name="parameters"></a>Parametreler

`Left` Sol `thread::id` nesnesi.

`Right` Sağa `thread::id` nesnesi.

### <a name="return-value"></a>Dönüş Değeri

`!(Left < Right)`

### <a name="remarks"></a>Açıklamalar

Bu işlev, tüm özel durumlar oluşturmadığını.

## <a name="op_gt"></a>  işleci&gt;

Bir olup olmadığını belirleyen `thread::id` nesnesidir diğerinden daha büyük.

```cpp
bool operator> (
    thread::id Left,
    thread::id Right) noexcept
```

### <a name="parameters"></a>Parametreler

`Left` Sol `thread::id` nesnesi.

`Right` Sağa `thread::id` nesnesi.

### <a name="return-value"></a>Dönüş Değeri

`Right < Left`

### <a name="remarks"></a>Açıklamalar

Bu işlev, tüm özel durumlar oluşturmadığını.

## <a name="op_lt_eq"></a>  işleci&lt;=

Bir olup olmadığını belirleyen `thread::id` nesnesidir değerinden küçük veya eşit başka.

```cpp
bool operator<= (
    thread::id Left,
    thread::id Right) noexcept
```

### <a name="parameters"></a>Parametreler

`Left` Sol `thread::id` nesnesi.

`Right` Sağa `thread::id` nesnesi.

### <a name="return-value"></a>Dönüş Değeri

`!(Right < Left)`

### <a name="remarks"></a>Açıklamalar

Bu işlev, tüm özel durumlar oluşturmadığını.

## <a name="op_lt"></a>  işleci&lt;

Bir olup olmadığını belirleyen `thread::id` nesnesi, başka değerinden.

```cpp
bool operator<(
    thread::id Left,
    thread::id Right) noexcept
```

### <a name="parameters"></a>Parametreler

`Left` Sol `thread::id` nesnesi.

`Right` Sağa `thread::id` nesnesi.

### <a name="return-value"></a>Dönüş Değeri

`true` varsa `Left` önündeki `Right` içinde toplam sıralama; Aksi halde, `false`.

### <a name="remarks"></a>Açıklamalar

Bir toplam tüm sıralama işleci tanımlar `thread::id` nesneleri. Bu nesneler ilişkilendirilebilir kapsayıcılar anahtar olarak kullanılabilir.

Bu işlev, tüm özel durumlar oluşturmadığını.

## <a name="op_neq"></a>  operator! =

İki karşılaştırır `thread::id` eşitsizlik nesneleri.

```cpp
bool operator!= (
    thread::id Left,
    thread::id Right) noexcept
```

### <a name="parameters"></a>Parametreler

`Left` Sol `thread::id` nesnesi.

`Right` Sağa `thread::id` nesnesi.

### <a name="return-value"></a>Dönüş Değeri

`!(Left == Right)`

### <a name="remarks"></a>Açıklamalar

Bu işlev, tüm özel durumlar oluşturmadığını.

## <a name="op_eq_eq"></a>  operator ==

İki karşılaştırır `thread::id` nesneleri eşitlik için.

```cpp
bool operator== (
    thread::id Left,
    thread::id Right) noexcept
```

### <a name="parameters"></a>Parametreler

`Left` Sol `thread::id` nesnesi.

`Right` Sağa `thread::id` nesnesi.

### <a name="return-value"></a>Dönüş Değeri

`true` iki nesnenin iş parçacığı yürütme veya hiçbiri nesne yürütme iş parçacığı temsil edip etmediğini temsil ediyorsa; Aksi takdirde `false`.

### <a name="remarks"></a>Açıklamalar

Bu işlev, tüm özel durumlar oluşturmadığını.

## <a name="op_lt_lt"></a>  işleci&lt;&lt;

Bir metin gösterimini ekler bir `thread::id` bir akış nesnesine.

```cpp
template <class Elem, class Tr>
basic_ostream<Elem, Tr>& operator<<(
    basic_ostream<Elem, Tr>& Ostr, thread::id Id);
```

### <a name="parameters"></a>Parametreler

`Ostr` A [basic_ostream](../standard-library/basic-ostream-class.md) nesnesi.

`Id` A `thread::id` nesnesi.

### <a name="return-value"></a>Dönüş Değeri

`Ostr`.

### <a name="remarks"></a>Açıklamalar

Bu işlev ekler `Id` içine `Ostr`.

İki `thread::id` nesneleri eşit karşılaştırmak, bu nesneler eklenen metin temsilleridir aynıdır.

## <a name="see-also"></a>Ayrıca bkz.

[\<iş parçacığı >](../standard-library/thread.md)<br/>
