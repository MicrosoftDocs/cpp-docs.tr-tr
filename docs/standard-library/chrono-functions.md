---
title: '&lt;chrono&gt; işlevleri'
ms.date: 11/04/2016
f1_keywords:
- chrono/std::duration_cast
- chrono/std::time_point_cast
ms.assetid: d6800e15-77a1-4df3-900e-d8b2fee190c7
ms.openlocfilehash: 5aadf776cc25e22a40ed75f854481dff63cce4bb
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50597502"
---
# <a name="ltchronogt-functions"></a>&lt;chrono&gt; işlevleri

||||
|-|-|-|
|[duration_cast](#duration_cast)|[time_point_cast](#time_point_cast)|

## <a name="duration_cast"></a>  duration_cast

Yayınları bir `duration` belirli nesne.

```cpp
template <class To, class Rep, class Period>
constexpr To duration_cast(const duration<Rep, Period>& Dur);
```

### <a name="return-value"></a>Dönüş Değeri

A `duration` türündeki nesne `To` zaman aralığını temsil eden `Dur`, bu hedef türüne sığması gerekirse kesilen.

### <a name="remarks"></a>Açıklamalar

Varsa `To` örneklemesiyse `duration`, bu işlev aşırı yükleme çözünürlüğü içinde yer almaz.

## <a name="time_point_cast"></a>  time_point_cast

Yayınları bir [time_point](../standard-library/time-point-class.md) belirli nesne.

```cpp
template <class To, class Clock, class Duration>
time_point<Clock, To> time_point_cast(const time_point<Clock, Duration>& Tp);
```

### <a name="return-value"></a>Dönüş Değeri

A `time_point` türü süresi olan nesne `To`.

### <a name="remarks"></a>Açıklamalar

Sürece `To` örneklemesiyse [süresi](../standard-library/duration-class.md), bu işlev aşırı yükleme çözünürlüğü içinde yer almaz.

## <a name="see-also"></a>Ayrıca bkz.

[\<chrono >](../standard-library/chrono.md)<br/>
