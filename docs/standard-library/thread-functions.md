---
title: '&lt;iş&gt; parçacığı fonksiyonları'
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
ms.openlocfilehash: bb0a0a12ec2882701447804f9c88d1776a196cb7
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375844"
---
# <a name="ltthreadgt-functions"></a>&lt;iş&gt; parçacığı fonksiyonları

||||
|-|-|-|
|[get_id](#get_id)|[sleep_for](#sleep_for)|[sleep_until](#sleep_until)|
|[Takas](#swap)|[yield](#yield)|

## <a name="get_id"></a><a name="get_id"></a>get_id

Özgün olarak yürütme nin geçerli iş parçacığı tanımlar.

```cpp
thread::id this_thread::get_id() noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli yürütme iş parçacığıtanımlayan tür [iş parçacığı::id](../standard-library/thread-class.md) nesnesi.

## <a name="sleep_for"></a><a name="sleep_for"></a>sleep_for

Arama iş parçacığı engeller.

```cpp
template <class Rep,
class Period>
inline void sleep_for(const chrono::duration<Rep, Period>& Rel_time);
```

### <a name="parameters"></a>Parametreler

*Rel_time*\
Bir zaman aralığı belirten bir [süre](../standard-library/duration-class.md) nesnesi.

### <a name="remarks"></a>Açıklamalar

İşlev, *Rel_time*tarafından belirtilen en az süre için çağrı iş parçacığı engeller. Bu işlev herhangi bir özel durum atmaz.

## <a name="sleep_until"></a><a name="sleep_until"></a>sleep_until

Arama iş parçacığının en azından belirtilen zamana kadar engellemesi.

```cpp
template <class Clock, class Duration>
void sleep_until(const chrono::time_point<Clock, Duration>& Abs_time);

void sleep_until(const xtime *Abs_time);
```

### <a name="parameters"></a>Parametreler

*Abs_time*\
Zaman içinde bir noktayı temsil eder.

### <a name="remarks"></a>Açıklamalar

Bu işlev herhangi bir özel durum atmaz.

## <a name="swap"></a><a name="swap"></a>Takas

İki **iş parçacığı** nesnesinin durumlarını değiştirir.

```cpp
void swap(thread& Left, thread& Right) noexcept;
```

### <a name="parameters"></a>Parametreler

*Sol*\
Sol **iş parçacığı nesnesi.**

*Doğru*\
Sağ **iş parçacığı nesnesi.**

### <a name="remarks"></a>Açıklamalar

Fonksiyon çağırır. `Left.swap(Right)`

## <a name="yield"></a><a name="yield"></a>Verim

Geçerli iş parçacığı normalde çalışmaya devam etse bile, işletim sisteminin diğer iş parçacıklarını çalıştırmasını bildirir.

```cpp
inline void yield() noexcept;
```

## <a name="see-also"></a>Ayrıca bkz.

[\<iş parçacığı>](../standard-library/thread.md)
