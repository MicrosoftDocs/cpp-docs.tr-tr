---
title: condition_variable sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- condition_variable/std::condition
- condition_variable/std::condition_variable::condition_variable
- condition_variable/std::condition_variable::native_handle
- condition_variable/std::condition_variable::notify_all
- condition_variable/std::condition_variable::notify_one
- condition_variable/std::condition_variable::wait
- condition_variable/std::condition_variable::wait_for
- condition_variable/std::condition_variable::wait_until
dev_langs:
- C++
ms.assetid: 80b1295c-b73d-4d46-b664-6e183f2eec1b
author: corob-msft
ms.author: corob
helpviewer_keywords:
- std::condition
- std::condition_variable::condition_variable
- std::condition_variable::native_handle
- std::condition_variable::notify_all
- std::condition_variable::notify_one
- std::condition_variable::wait
- std::condition_variable::wait_for
- std::condition_variable::wait_until
ms.workload:
- cplusplus
ms.openlocfilehash: ca85765d6fed21938a61f52f25c1a377ec43c499
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38965184"
---
# <a name="conditionvariable-class"></a>condition_variable Sınıfı

Kullanım `condition_variable` varsa bir olay beklemek için sınıf bir `mutex` türü `unique_lock<mutex>`. Bu tür nesneler türündeki nesneler daha iyi performans olabilir [condition_variable_any < unique_lock\<mutex >>](../standard-library/condition-variable-any-class.md).

## <a name="syntax"></a>Sözdizimi

```cpp
class condition_variable;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[condition_variable](#condition_variable)|Oluşturur bir `condition_variable` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[native_handle](#native_handle)|Condition_variable tanıtıcısını temsil eden uygulamaya özel türü döndürür.|
|[notify_all](#notify_all)|İçin bekleyen tüm iş parçacıklarının engellemesinin kaldırıldığı `condition_variable` nesne.|
|[notify_one](#notify_one)|İçin bekleyen iş parçacıklarının birinin engellemesini kaldırır `condition_variable` nesne.|
|[bekleme](#wait)|Bir iş parçacığını engeller.|
|[wait_for](#wait_for)|Bir iş parçacığını engeller ve sonrasında iş parçacığı engellemesinin kaldırıldığı bir zaman aralığı ayarlar.|
|[wait_until](#wait_until)|Bir iş parçacığını engeller ve hangi iş parçacığı engellemesinin kaldırıldığı zaman maksimum noktası ayarlar.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<condition_variable >

**Namespace:** std

## <a name="condition_variable"></a>  condition_variable::condition_variable Oluşturucusu

Oluşturur bir `condition_variable` nesne.

```cpp
condition_variable();
```

### <a name="remarks"></a>Açıklamalar

Yeterli bellek yoksa, oluşturucu oluşturur bir [system_error](../standard-library/system-error-class.md) nesnesi bir `not_enough_memory` hata kodu. Başka bir kaynak kullanılamadığından nesne oluşturulamıyorsa, oluşturucu oluşturur bir `system_error` nesnesi bir `resource_unavailable_try_again` hata kodu.

## <a name="native_handle"></a>  condition_variable::native_handle

Condition_variable tanıtıcısını temsil eden uygulamaya özel türü döndürür.

```cpp
native_handle_type native_handle();
```

### <a name="return-value"></a>Dönüş Değeri

`native_handle_type` Eşzamanlılık Çalışma zamanı iç veri yapılarını işaretçisi olarak tanımlanır.

## <a name="notify_all"></a>  condition_variable::notify_all

İçin bekleyen tüm iş parçacıklarının engellemesinin kaldırıldığı `condition_variable` nesne.

```cpp
void notify_all() noexcept;
```

## <a name="notify_one"></a>  condition_variable::notify_one

Bekleyen iş parçacıklarının birinin engellemesini kaldırır `condition_variable` nesne.

```cpp
void notify_one() noexcept;
```

## <a name="wait"></a>  condition_variable::wait

Bir iş parçacığını engeller.

```cpp
void wait(unique_lock<mutex>& Lck);

template <class Predicate>
void wait(unique_lock<mutex>& Lck, Predicate Pred);
```

### <a name="parameters"></a>Parametreler

*Lck* A [unique_lock\<mutex >](../standard-library/unique-lock-class.md) nesne.

*Pred* döndüren herhangi bir ifade **true** veya **false**.

### <a name="remarks"></a>Açıklamalar

İlk yöntem engeller `condition_variable` nesnesine sinyal yollanana kadar [notify_one](#notify_one) veya [notify_all](#notify_all). Bu ayrıca uyanabilir.

Aslında, ikinci yöntem aşağıdaki kodu çalıştırır.

```cpp
while(!Pred())
    wait(Lck);
```

## <a name="wait_for"></a>  condition_variable::wait_for

Bir iş parçacığını engeller ve sonrasında iş parçacığı engellemesinin kaldırıldığı bir zaman aralığı ayarlar.

```cpp
template <class Rep, class Period>
cv_status wait_for(
    unique_lock<mutex>& Lck,
    const chrono::duration<Rep, Period>& Rel_time);

template <class Rep, class Period, class Predicate>
bool wait_for(
    unique_lock<mutex>& Lck,
    const chrono::duration<Rep, Period>& Rel_time,
    Predicate Pred);
```

### <a name="parameters"></a>Parametreler

*Lck* A [unique_lock\<mutex >](../standard-library/unique-lock-class.md) nesne.

*Rel_time* A `chrono::duration` iş parçacığı süre miktarını belirten nesne uyanır.

*Pred* döndüren herhangi bir ifade **true** veya **false**.

### <a name="return-value"></a>Dönüş Değeri

İlk yöntem döndürür `cv_status::timeout` bekleme *Rel_time* geçti. Aksi takdirde yöntem döndürür `cv_status::no_timeout`.

İkinci yöntem değerini döndürür *Pred*.

### <a name="remarks"></a>Açıklamalar

İlk yöntem engeller `condition_variable` nesnesine sinyal yollanana kadar [notify_one](#notify_one) veya [notify_all](#notify_all) veya zaman aralığı kadar *Rel_time* geçti. Bu ayrıca uyanabilir.

Aslında, ikinci yöntem aşağıdaki kodu çalıştırır.

```cpp
while(!Pred())
    if(wait_for(Lck, Rel_time) == cv_status::timeout)
    return Pred();

return true;
```

## <a name="wait_until"></a>  condition_variable::wait_until

Bir iş parçacığını engeller ve hangi iş parçacığı engellemesinin kaldırıldığı zaman maksimum noktası ayarlar.

```cpp
template <class Clock, class Duration>
cv_status wait_until(
    unique_lock<mutex>& Lck,
    const chrono::time_point<Clock, Duration>& Abs_time);

template <class Clock, class Duration, class Predicate>
bool wait_until(
    unique_lock<mutex>& Lck,
    const chrono::time_point<Clock, Duration>& Abs_time,
    Predicate Pred);

cv_status wait_until(
    unique_lock<mutex>& Lck,
    const xtime* Abs_time);

template <class Predicate>
bool wait_until(
    unique_lock<mutex>& Lck,
    const xtime* Abs_time,
    Predicate Pred);
```

### <a name="parameters"></a>Parametreler

*Lck* A [unique_lock\<mutex >](../standard-library/unique-lock-class.md) nesne.

*Abs_time* A [chrono::time_point](../standard-library/time-point-class.md) nesne.

*Pred* döndüren herhangi bir ifade **true** veya **false**.

### <a name="return-value"></a>Dönüş Değeri

Döndüren yöntemler bir `cv_status` türünü `cv_status::timeout` bekleme *Abs_time* geçen. Aksi takdirde, yöntemlerin dönüş `cv_status::no_timeout`.

Döndüren yöntemler bir **bool** dönüş değeri *Pred*.

### <a name="remarks"></a>Açıklamalar

İlk yöntem engeller `condition_variable` nesnesine sinyal yollanana kadar [notify_one](#notify_one) veya [notify_all](#notify_all) veya kadar `Abs_time`. Bu ayrıca uyanabilir.

Aslında, ikinci yöntem aşağıdaki kodu çalıştırır

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
