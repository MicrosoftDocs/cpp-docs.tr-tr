---
title: condition_variable_any sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- condition_variable/std::condition_variable_any
- condition_variable/std::condition_variable_any::condition_variable_any
- condition_variable/std::condition_variable_any::notify_all
- condition_variable/std::condition_variable_any::notify_one
- condition_variable/std::condition_variable_any::wait
- condition_variable/std::condition_variable_any::wait_for
- condition_variable/std::condition_variable_any::wait_until
dev_langs:
- C++
ms.assetid: d8afe5db-1561-4ec2-8e85-21ea03ee4321
author: corob-msft
ms.author: corob
helpviewer_keywords:
- std::condition_variable_any
- std::condition_variable_any::condition_variable_any
- std::condition_variable_any::notify_all
- std::condition_variable_any::notify_one
- std::condition_variable_any::wait
- std::condition_variable_any::wait_for
- std::condition_variable_any::wait_until
ms.workload:
- cplusplus
ms.openlocfilehash: 9acd5abc941c3cc3ab2f1c22486298d7cc7da16c
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/07/2018
ms.locfileid: "44106970"
---
# <a name="conditionvariableany-class"></a>condition_variable_any Sınıfı

Bir sınıf kullanma `condition_variable_any` içeren bir olay beklemek için `mutex` türü.

## <a name="syntax"></a>Sözdizimi

```cpp
class condition_variable_any;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[condition_variable_any](#condition_variable_any)|Oluşturur bir `condition_variable_any` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[notify_all](#notify_all)|İçin bekleyen tüm iş parçacıklarının engellemesinin kaldırıldığı `condition_variable_any` nesne.|
|[notify_one](#notify_one)|İçin bekleyen iş parçacıklarının birinin engellemesini kaldırır `condition_variable_any` nesne.|
|[bekleme](#wait)|Bir iş parçacığını engeller.|
|[wait_for](#wait_for)|Bir iş parçacığını engeller ve sonrasında iş parçacığı engellemesinin kaldırıldığı bir zaman aralığı ayarlar.|
|[wait_until](#wait_until)|Bir iş parçacığını engeller ve hangi iş parçacığı engellemesinin kaldırıldığı zaman maksimum noktası ayarlar.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<condition_variable >

**Namespace:** std

## <a name="condition_variable_any"></a>  condition_variable_any::condition_variable_any Oluşturucusu

Oluşturur bir `condition_variable_any` nesne.

```cpp
condition_variable_any();
```

### <a name="remarks"></a>Açıklamalar

Yeterli bellek yoksa, oluşturucu oluşturur bir [system_error](../standard-library/system-error-class.md) nesnesi bir `not_enough_memory` hata kodu. Başka bir kaynak kullanılamadığından nesne oluşturulamıyorsa, oluşturucu oluşturur bir `system_error` nesnesi bir `resource_unavailable_try_again` hata kodu.

## <a name="notify_all"></a>  condition_variable_any::notify_all

İçin bekleyen tüm iş parçacıklarının engellemesinin kaldırıldığı `condition_variable_any` nesne.

```cpp
void notify_all() noexcept;
```

## <a name="notify_one"></a>  condition_variable_any::notify_one

Bekleyen iş parçacıklarının birinin engellemesini kaldırır `condition_variable_any` nesne.

```cpp
void notify_one() noexcept;
```

## <a name="wait"></a>  condition_variable_any::wait

Bir iş parçacığını engeller.

```cpp
template <class Lock>
void wait(Lock& Lck);

template <class Lock, class Predicate>
void wait(Lock& Lck, Predicate Pred);
```

### <a name="parameters"></a>Parametreler

*Lck*<br/>
A `mutex` herhangi bir türde nesne.

*Pred*<br/>
Döndüren herhangi bir ifade **true** veya **false**.

### <a name="remarks"></a>Açıklamalar

İlk yöntem engeller `condition_variable_any` nesnesine sinyal yollanana kadar [notify_one](../standard-library/condition-variable-class.md#notify_one) veya [notify_all](../standard-library/condition-variable-class.md#notify_all). Bu ayrıca uyanabilir.

İkinci yöntem aşağıdaki kodu aslında çalıştırır.

```cpp
while (!Pred())
    wait(Lck);
```

## <a name="wait_for"></a>  condition_variable_any::wait_for

Bir iş parçacığını engeller ve sonrasında iş parçacığı engellemesinin kaldırıldığı bir zaman aralığı ayarlar.

```cpp
template <class Lock, class Rep, class Period>
bool wait_for(Lock& Lck, const chrono::duration<Rep, Period>& Rel_time);

template <class Lock, class Rep, class Period, class Predicate>
bool wait_for(Lock& Lck, const chrono::duration<Rep, Period>& Rel_time, Predicate Pred);
```

### <a name="parameters"></a>Parametreler

*Lck*<br/>
A `mutex` herhangi bir türde nesne.

*Rel_time*<br/>
A `chrono::duration` iş parçacığı süre miktarını belirten nesne uyanır.

*Pred*<br/>
Döndüren herhangi bir ifade **true** veya **false**.

### <a name="return-value"></a>Dönüş Değeri

İlk yöntem döndürür `cv_status::timeout` bekleme *Rel_time* geçti. Aksi takdirde yöntem döndürür `cv_status::no_timeout`.

İkinci yöntem değerini döndürür *Pred*.

### <a name="remarks"></a>Açıklamalar

İlk yöntem engeller `condition_variable_any` nesnesine sinyal yollanana kadar [notify_one](../standard-library/condition-variable-class.md#notify_one) veya [notify_all](../standard-library/condition-variable-class.md#notify_all), veya zaman aralığı kadar *Rel_time* geçti. Bu ayrıca uyanabilir.

İkinci yöntem aşağıdaki kodu aslında çalıştırır.

```cpp
while(!Pred())
    if(wait_for(Lck, Rel_time) == cv_status::timeout)
    return Pred();

return true;
```

## <a name="wait_until"></a>  condition_variable_any::wait_until

Bir iş parçacığını engeller ve hangi iş parçacığı engellemesinin kaldırıldığı zaman maksimum noktası ayarlar.

```cpp
template <class Lock, class Clock, class Duration>
void wait_until(Lock& Lck, const chrono::time_point<Clock, Duration>& Abs_time);

template <class Lock, class Clock, class Duration, class Predicate>
void wait_until(
    Lock& Lck,
    const chrono::time_point<Clock, Duration>& Abs_time,
    Predicate Pred);

template <class Lock>
void wait_until(Lock Lck, const xtime* Abs_time);

template <class Lock, class Predicate>
void wait_until(
    Lock Lck,
    const xtime* Abs_time,
    Predicate Pred);
```

### <a name="parameters"></a>Parametreler

*Lck*<br/>
Mutex nesnesi.

*Abs_time*<br/>
A [chrono::time_point](../standard-library/time-point-class.md) nesne.

*Pred*<br/>
Döndüren herhangi bir ifade **true** veya **false**.

### <a name="return-value"></a>Dönüş Değeri

Döndüren yöntemler bir `cv_status` türünü `cv_status::timeout` bekleme *Abs_time* geçen. Aksi takdirde, yöntemlerin dönüş `cv_status::no_timeout`.

Döndüren yöntemler bir `bool` dönüş değeri *Pred*.

### <a name="remarks"></a>Açıklamalar

İlk yöntem engeller `condition_variable` nesnesine sinyal yollanana kadar [notify_one](../standard-library/condition-variable-class.md#notify_one) veya [notify_all](../standard-library/condition-variable-class.md#notify_all), veya kadar *Abs_time*. Bu ayrıca uyanabilir.

İkinci yöntem aşağıdaki kodu aslında çalıştırır.

```cpp
while(!Pred())
    if(wait_until(Lck, Abs_time) == cv_status::timeout)
    return Pred();

return true;
```

Üçüncü ve dördüncü yöntemler türünde bir nesne için bir işaretçi kullanın `xtime` değiştirilecek `chrono::time_point` nesne. `xtime` Nesnesini bir sinyal için beklenecek en uzun süreyi belirtir.

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)<br/>
[<condition_variable>](../standard-library/condition-variable.md)<br/>
