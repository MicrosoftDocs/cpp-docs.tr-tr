---
title: '&lt;iş parçacığı&gt; işlevleri | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
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
ms.openlocfilehash: 948c00f7c0b773bf366f4ea9e102c832e9878d9b
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38960456"
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

*Rel_time*  
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

*Abs_time*  
 Bir kez temsil eder.

### <a name="remarks"></a>Açıklamalar

Bu işlev bir özel durum oluşturmaz.

## <a name="swap"></a>  değiştirme

İki durumlarını değiştirir **iş parçacığı** nesneleri.

```cpp
void swap(thread& Left, thread& Right) noexcept;
```

### <a name="parameters"></a>Parametreler

*Sol*  
 Sol **iş parçacığı** nesne.

*Sağ*  
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
