---
title: condition_variable_any Sınıfı
ms.date: 11/04/2016
f1_keywords:
- condition_variable/std::condition_variable_any
- condition_variable/std::condition_variable_any::condition_variable_any
- condition_variable/std::condition_variable_any::notify_all
- condition_variable/std::condition_variable_any::notify_one
- condition_variable/std::condition_variable_any::wait
- condition_variable/std::condition_variable_any::wait_for
- condition_variable/std::condition_variable_any::wait_until
ms.assetid: d8afe5db-1561-4ec2-8e85-21ea03ee4321
helpviewer_keywords:
- std::condition_variable_any
- std::condition_variable_any::condition_variable_any
- std::condition_variable_any::notify_all
- std::condition_variable_any::notify_one
- std::condition_variable_any::wait
- std::condition_variable_any::wait_for
- std::condition_variable_any::wait_until
ms.openlocfilehash: 9187bddef456f131982d39fd64dacea5953b959b
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87222569"
---
# <a name="condition_variable_any-class"></a>condition_variable_any Sınıfı

`condition_variable_any`Herhangi bir türe sahip bir olay beklemek için sınıfını kullanın `mutex` .

## <a name="syntax"></a>Sözdizimi

```cpp
class condition_variable_any;
```

## <a name="members"></a>Üyeler

### <a name="constructors"></a>Oluşturucular

|||
|-|-|
|[condition_variable_any](#condition_variable_any)|Bir `condition_variable_any` nesnesi oluşturur.|

### <a name="functions"></a>İşlevler

|||
|-|-|
|[notify_all](#notify_all)|Nesne için bekleyen tüm iş parçacıklarının bloklarını kaldırır `condition_variable_any` .|
|[notify_one](#notify_one)|Nesne için bekleyen iş parçacıklarından birinin engellemesini kaldırır `condition_variable_any` .|
|[bekleneceğini](#wait)|Bir iş parçacığını engeller.|
|[wait_for](#wait_for)|Bir iş parçacığını engeller ve sonra iş parçacığı bloklarından sonra bir zaman aralığı ayarlar.|
|[wait_until](#wait_until)|Bir iş parçacığını engeller ve iş parçacığı bloklarından en fazla bir zaman noktası ayarlar.|

## <a name="condition_variable_any"></a><a name="condition_variable_any"></a>condition_variable_any

Bir `condition_variable_any` nesnesi oluşturur.

```cpp
condition_variable_any();
```

### <a name="remarks"></a>Açıklamalar

Yeterli kullanılabilir bellek yoksa, Oluşturucu hata koduna sahip bir [system_error](../standard-library/system-error-class.md) nesnesi oluşturur `not_enough_memory` . Başka bir kaynak kullanılabilir olmadığından nesne oluşturulamıyor, Oluşturucu `system_error` hata koduna sahip bir nesne oluşturur `resource_unavailable_try_again` .

## <a name="notify_all"></a><a name="notify_all"></a>notify_all

Nesne için bekleyen tüm iş parçacıklarının bloklarını kaldırır `condition_variable_any` .

```cpp
void notify_all() noexcept;
```

## <a name="notify_one"></a><a name="notify_one"></a>notify_one

Nesne üzerinde bekleyen iş parçacıklarından birinin engellemesini kaldırır `condition_variable_any` .

```cpp
void notify_one() noexcept;
```

## <a name="wait"></a><a name="wait"></a>bekleneceğini

Bir iş parçacığını engeller.

```cpp
template <class Lock>
void wait(Lock& Lck);

template <class Lock, class Predicate>
void wait(Lock& Lck, Predicate Pred);
```

### <a name="parameters"></a>Parametreler

*LCK*\
`mutex`Herhangi bir türdeki nesne.

*Pred*\
Veya döndüren herhangi bir **`true`** ifade **`false`** .

### <a name="remarks"></a>Açıklamalar

İlk yöntem, `condition_variable_any` nesneye bir [notify_one](../standard-library/condition-variable-class.md#notify_one) veya [notify_all](../standard-library/condition-variable-class.md#notify_all)çağrısıyla sinyallene kadar engeller. Ayrıca, uyanabilir 'i de uyandırabilirler.

Etkin ikinci yöntem aşağıdaki kodu yürütür.

```cpp
while (!Pred())
    wait(Lck);
```

## <a name="wait_for"></a><a name="wait_for"></a>wait_for

Bir iş parçacığını engeller ve sonra iş parçacığı bloklarından sonra bir zaman aralığı ayarlar.

```cpp
template <class Lock, class Rep, class Period>
bool wait_for(Lock& Lck, const chrono::duration<Rep, Period>& Rel_time);

template <class Lock, class Rep, class Period, class Predicate>
bool wait_for(Lock& Lck, const chrono::duration<Rep, Period>& Rel_time, Predicate Pred);
```

### <a name="parameters"></a>Parametreler

*LCK*\
`mutex`Herhangi bir türdeki nesne.

*Rel_time*\
`chrono::duration`İş parçacığı uyanmadan önce geçen süreyi belirten bir nesne.

*Pred*\
Veya döndüren herhangi bir **`true`** ifade **`false`** .

### <a name="return-value"></a>Dönüş Değeri

İlk yöntem, `cv_status::timeout` *Rel_time* geçtiğinde bekleme sonlandırılırsa döndürür. Aksi takdirde, yöntemi döndürür `cv_status::no_timeout` .

İkinci yöntem *Pred*değerini döndürür.

### <a name="remarks"></a>Açıklamalar

İlk yöntem, `condition_variable_any` nesne [notify_one](../standard-library/condition-variable-class.md#notify_one) veya [notify_all](../standard-library/condition-variable-class.md#notify_all)bir çağrı tarafından sinyallene veya zaman aralığı *Rel_time* bitene kadar engeller. Ayrıca, uyanabilir 'i de uyandırabilirler.

Etkin ikinci yöntem aşağıdaki kodu yürütür.

```cpp
while(!Pred())
    if(wait_for(Lck, Rel_time) == cv_status::timeout)
    return Pred();

return true;
```

## <a name="wait_until"></a><a name="wait_until"></a>wait_until

Bir iş parçacığını engeller ve iş parçacığı bloklarından en fazla bir zaman noktası ayarlar.

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

*LCK*\
Bir mutex nesnesi.

*Abs_time*\
Bir zaman [hatası:: time_point](../standard-library/time-point-class.md) nesnesi.

*Pred*\
Veya döndüren herhangi bir **`true`** ifade **`false`** .

### <a name="return-value"></a>Dönüş Değeri

Bir tür döndüren yöntemler `cv_status` `cv_status::timeout` , *Abs_time* geçtiğinde bekleme sona erdiğinde döndürülür. Aksi halde Yöntemler döndürülür `cv_status::no_timeout` .

Döndüren yöntemler **`bool`** *Pred*değerini döndürür.

### <a name="remarks"></a>Açıklamalar

İlk yöntem, `condition_variable` nesneye [notify_one](../standard-library/condition-variable-class.md#notify_one) veya [notify_all](../standard-library/condition-variable-class.md#notify_all)veya *Abs_time*kadar bir çağrı tarafından bildirilene kadar engeller. Ayrıca, uyanabilir 'i de uyandırabilirler.

Etkin ikinci yöntem aşağıdaki kodu yürütür.

```cpp
while(!Pred())
    if(wait_until(Lck, Abs_time) == cv_status::timeout)
    return Pred();

return true;
```

Üçüncü ve dördüncü Yöntemler, nesneyi değiştirmek için türünde bir nesne işaretçisi kullanır `xtime` `chrono::time_point` . `xtime`Nesne, bir sinyal için beklenecek en uzun süreyi belirtir.
