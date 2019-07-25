---
title: '&lt;iş&gt; parçacığı işlevleri'
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
ms.openlocfilehash: 8064cec7e94a909d7dc2e1b22142d362bb7b9488
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68458509"
---
# <a name="ltthreadgt-functions"></a>&lt;iş&gt; parçacığı işlevleri

||||
|-|-|-|
|[get_id](#get_id)|[sleep_for](#sleep_for)|[sleep_until](#sleep_until)|
|[Kur](#swap)|[yield](#yield)|

## <a name="get_id"></a>  get_id

Yürütmenin geçerli iş parçacığını benzersiz şekilde tanımlar.

```cpp
thread::id this_thread::get_id() noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

Yürütmenin geçerli iş parçacığını benzersiz bir şekilde tanımlayan [thread:: ID](../standard-library/thread-class.md) türünde bir nesne.

## <a name="sleep_for"></a>sleep_for

Çağıran iş parçacığını engeller.

```cpp
template <class Rep,
class Period>
inline void sleep_for(const chrono::duration<Rep, Period>& Rel_time);
```

### <a name="parameters"></a>Parametreler

*Rel_time*\
Bir zaman aralığı belirten [Duration](../standard-library/duration-class.md) nesnesi.

### <a name="remarks"></a>Açıklamalar

İşlevi çağıran iş parçacığını en az *Rel_time*tarafından belirtilen süre için engeller. Bu işlev hiçbir özel durum oluşturmaz.

## <a name="sleep_until"></a>sleep_until

Çağıran iş parçacığını, belirtilen saate kadar en az kadar engeller.

```cpp
template <class Clock, class Duration>
void sleep_until(const chrono::time_point<Clock, Duration>& Abs_time);

void sleep_until(const xtime *Abs_time);
```

### <a name="parameters"></a>Parametreler

*Abs_time*\
Zaman içinde bir noktayı temsil eder.

### <a name="remarks"></a>Açıklamalar

Bu işlev hiçbir özel durum oluşturmaz.

## <a name="swap"></a>Kur

İki **iş parçacığı** nesnesinin durumunu değiştirir.

```cpp
void swap(thread& Left, thread& Right) noexcept;
```

### <a name="parameters"></a>Parametreler

*Tarafta*\
Sol **iş parçacığı** nesnesi.

*Right*\
Sağ **iş parçacığı** nesnesi.

### <a name="remarks"></a>Açıklamalar

İşlev çağırır `Left.swap(Right)`.

## <a name="yield"></a>yield

Geçerli iş parçacığı normalde çalışmaya devam edebilse bile, işletim sistemine diğer iş parçacıklarını çalıştırmasını bildirir.

```cpp
inline void yield() noexcept;
```

## <a name="see-also"></a>Ayrıca bkz.

[\<iş parçacığı >](../standard-library/thread.md)
