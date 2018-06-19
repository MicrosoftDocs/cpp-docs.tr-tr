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
ms.openlocfilehash: f151bbaf692d914fa1072021e2f14262b2c72ce4
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33855909"
---
# <a name="ltthreadgt-functions"></a>&lt;iş parçacığı&gt; işlevleri

||||
|-|-|-|
|[get_id](#get_id)|[sleep_for](#sleep_for)|[sleep_until](#sleep_until)|
|[Değiştirme](#swap)|[yield](#yield)|

## <a name="get_id"></a>  get_id

Geçerli yürütme iş parçacığı benzersiz olarak tanımlar.

```cpp
thread::id this_thread::get_id() noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

Türünde bir nesne [thread::id](../standard-library/thread-class.md) , geçerli yürütme iş parçacığı benzersiz şekilde tanımlar.

## <a name="sleep_for"></a>  sleep_for

Çağıran iş parçacığı engeller.

```cpp
template <class Rep,
class Period>
inline void sleep_for(const chrono::duration<Rep, Period>& Rel_time);
```

### <a name="parameters"></a>Parametreler

`Rel_time` A [süresi](../standard-library/duration-class.md) nesne bir zaman aralığı belirtir.

### <a name="remarks"></a>Açıklamalar

İşlevi çağıran iş parçacığı için en az tarafından belirtilen zaman blokları `Rel_time`. Bu işlev, tüm özel durumlar oluşturmadığını.

## <a name="sleep_until"></a>  sleep_until

Çağıran iş parçacığı en az belirtilen zamana kadar engeller.

```cpp
template <class Clock, class Duration>
void sleep_until(const chrono::time_point<Clock, Duration>& Abs_time);

void sleep_until(const xtime *Abs_time);
```

### <a name="parameters"></a>Parametreler

`Abs_time` Bir noktayı zamanında temsil eder.

### <a name="remarks"></a>Açıklamalar

Bu işlev, tüm özel durumlar oluşturmadığını.

## <a name="swap"></a>  Değiştirme

İki durumunu değiştirir `thread` nesneleri.

```cpp
void swap(thread& Left, thread& Right) noexcept;
```

### <a name="parameters"></a>Parametreler

`Left` Sol `thread` nesnesi.

`Right` Sağa `thread` nesnesi.

### <a name="remarks"></a>Açıklamalar

İşlev çağrıları `Left.swap(Right)`.

## <a name="yield"></a>  uyarı simgesi

Geçerli iş parçacığının normal şekilde çalışmaya devam eder olsa bile diğer iş parçacıklarını çalıştırmak için işletim sistemi işaret eder.

```cpp
inline void yield() noexcept;
```

## <a name="see-also"></a>Ayrıca bkz.

[\<iş parçacığı >](../standard-library/thread.md)<br/>
