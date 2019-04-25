---
title: '&lt;iş parçacığı&gt; işlevleri'
ms.date: 11/04/2016
f1_keywords:
- thread/std::get_id
- thread/std::sleep_for
- thread/std::sleep_until
- thread/std::swap
- thread/std::yield
ms.assetid: bb1aa1ef-fe3f-4e2c-8b6e-e22dbf2f5a19
helpviewer_keywords:
- std::get_id [C++]
- std::sleep_for [C++]
- std::sleep_until [C++]
- std::swap [C++]
- std::yield [C++]
ms.openlocfilehash: c0a8e42cb7ee78c399459be82e50ef37ab203816
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62279040"
---
# <a name="ltthreadgt-functions"></a>&lt;iş parçacığı&gt; işlevleri

||||
|-|-|-|
|[get_id](#get_id)|[sleep_for](#sleep_for)|[sleep_until](#sleep_until)|
|[değiştirme](#swap)|[yield](#yield)|

## <a name="get_id"></a>  get_id

Geçerli iş parçacığı yürütme benzersiz olarak tanımlar.

```cpp
thread::id this_thread::get_id() noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

Bir nesne türü [thread::id](../standard-library/thread-class.md) tanımlamasının, geçerli iş parçacığı yürütme.

## <a name="sleep_for"></a>  sleep_for

Çağıran iş parçacığını engeller.

```cpp
template <class Rep,
class Period>
inline void sleep_for(const chrono::duration<Rep, Period>& Rel_time);
```

### <a name="parameters"></a>Parametreler

*Rel_time*<br/>
A [süresi](../standard-library/duration-class.md) zaman aralığını belirten bir nesne.

### <a name="remarks"></a>Açıklamalar

İşlev çağırma iş parçacığı tarafından belirtilen zaman en az engeller *Rel_time*. Bu işlev bir özel durum oluşturmaz.

## <a name="sleep_until"></a>  sleep_until

Çağıran iş parçacığını en az belirtilen süre kadar engeller.

```cpp
template <class Clock, class Duration>
void sleep_until(const chrono::time_point<Clock, Duration>& Abs_time);

void sleep_until(const xtime *Abs_time);
```

### <a name="parameters"></a>Parametreler

*Abs_time*<br/>
Bir kez temsil eder.

### <a name="remarks"></a>Açıklamalar

Bu işlev bir özel durum oluşturmaz.

## <a name="swap"></a>  değiştirme

İki durumlarını değiştirir **iş parçacığı** nesneleri.

```cpp
void swap(thread& Left, thread& Right) noexcept;
```

### <a name="parameters"></a>Parametreler

*Sol*<br/>
Sol **iş parçacığı** nesne.

*sağ*<br/>
Sağa **iş parçacığı** nesne.

### <a name="remarks"></a>Açıklamalar

İşlev çağrıları `Left.swap(Right)`.

## <a name="yield"></a>  yield

Geçerli iş parçacığını normal şekilde çalışmaya devam ediyordu olsa bile işletim sisteminin diğer iş parçacıklarını çalıştırmasını bildirir.

```cpp
inline void yield() noexcept;
```

## <a name="see-also"></a>Ayrıca bkz.

[\<iş parçacığı >](../standard-library/thread.md)<br/>
