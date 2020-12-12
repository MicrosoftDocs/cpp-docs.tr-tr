---
description: 'Daha fazla bilgi edinin: &lt; hatası &gt;'
title: '&lt;Tarih/ç &gt; işlevleri'
ms.date: 11/04/2016
f1_keywords:
- chrono/std::duration_cast
- chrono/std::time_point_cast
ms.assetid: d6800e15-77a1-4df3-900e-d8b2fee190c7
ms.openlocfilehash: 161edeccace243c10a6382d931f5f9387f35790d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97234208"
---
# <a name="ltchronogt-functions"></a>&lt;Tarih/ç &gt; işlevleri

## <a name="duration_cast"></a><a name="duration_cast"></a> duration_cast

Bir `duration` nesneyi belirtilen bir türe yayınlar.

```cpp
template <class To, class Rep, class Period>
constexpr To duration_cast(const duration<Rep, Period>& Dur);

template <class ToDuration, class Rep, class Period>
constexpr ToDuration floor(const duration<Rep, Period>& d);
template <class ToDuration, class Rep, class Period>
constexpr ToDuration ceil(const duration<Rep, Period>& d);
template <class ToDuration, class Rep, class Period>
constexpr ToDuration round(const duration<Rep, Period>& d);
```

### <a name="return-value"></a>Dönüş Değeri

`duration` `To` `Dur` Hedef türe sığması gerekiyorsa kesilen, zaman aralığını temsil eden türünde bir nesne.

### <a name="remarks"></a>Açıklamalar

`To`Öğesinin bir örneklenmesi ise `duration` , bu işlev aşırı yükleme çözümüne katılmaz.

## <a name="time_point_cast"></a><a name="time_point_cast"></a> time_point_cast

[Time_point](../standard-library/time-point-class.md) nesnesini belirtilen bir türe yayınlar.

```cpp
template <class To, class Clock, class Duration>
time_point<Clock, To> time_point_cast(const time_point<Clock, Duration>& Tp);

template <class ToDuration, class Clock, class Duration>
constexpr time_point<Clock, ToDuration>
floor(const time_point<Clock, Duration>& tp);
template <class ToDuration, class Clock, class Duration>
constexpr time_point<Clock, ToDuration>
ceil(const time_point<Clock, Duration>& tp);
template <class ToDuration, class Clock, class Duration>
constexpr time_point<Clock, ToDuration>
round(const time_point<Clock, Duration>& tp);
```

### <a name="return-value"></a>Dönüş Değeri

`time_point`Süresi türünde bir nesne `To` .

### <a name="remarks"></a>Açıklamalar

`To` [Süre](../standard-library/duration-class.md)örneklemedikçe, bu işlev aşırı yükleme çözümüne katılmaz.
