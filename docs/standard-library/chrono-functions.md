---
title: '&lt;Tarihçe&gt; işlevleri'
ms.date: 11/04/2016
f1_keywords:
- chrono/std::duration_cast
- chrono/std::time_point_cast
ms.assetid: d6800e15-77a1-4df3-900e-d8b2fee190c7
ms.openlocfilehash: 85fdd413354b3f310d3315a80cf7da983cf6621d
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/16/2020
ms.locfileid: "79416776"
---
# <a name="ltchronogt-functions"></a>&lt;Tarihçe&gt; işlevleri

## <a name="duration_cast"></a>duration_cast

`duration` nesnesini belirtilen bir türe yayınlar.

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

Hedef türe sığması gerekiyorsa kesilen `Dur`zaman aralığını temsil eden `To` türünde bir `duration` nesnesi.

### <a name="remarks"></a>Açıklamalar

`To` `duration`örneklemesidir, bu işlev aşırı yükleme çözümüne katılmaz.

## <a name="time_point_cast"></a>time_point_cast

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

`To`türünde bir süre olan `time_point` nesne.

### <a name="remarks"></a>Açıklamalar

`To` [sürenin](../standard-library/duration-class.md)bir örneklenmesi değilse, bu işlev aşırı yükleme çözümüne katılmaz.
