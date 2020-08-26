---
title: condition_variable Sınıfı
ms.date: 11/04/2016
f1_keywords:
- condition_variable/std::condition
- condition_variable/std::condition_variable::condition_variable
- condition_variable/std::condition_variable::native_handle
- condition_variable/std::condition_variable::notify_all
- condition_variable/std::condition_variable::notify_one
- condition_variable/std::condition_variable::wait
- condition_variable/std::condition_variable::wait_for
- condition_variable/std::condition_variable::wait_until
ms.assetid: 80b1295c-b73d-4d46-b664-6e183f2eec1b
helpviewer_keywords:
- std::condition
- std::condition_variable::condition_variable
- std::condition_variable::native_handle
- std::condition_variable::notify_all
- std::condition_variable::notify_one
- std::condition_variable::wait
- std::condition_variable::wait_for
- std::condition_variable::wait_until
ms.openlocfilehash: eef0e7ef013b4faeb6393cade67258a09eda5551
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88842435"
---
# <a name="condition_variable-class"></a>condition_variable Sınıfı

`condition_variable`Bir türe sahip olduğunuzda bir olayı beklemek için sınıfını kullanın `mutex` `unique_lock<mutex>` . Bu türün nesneleri [condition_variable_any<unique_lock \<mutex> > ](../standard-library/condition-variable-any-class.md)türündeki nesnelerden daha iyi performansa sahip olabilir.

## <a name="syntax"></a>Syntax

```cpp
class condition_variable;
```

## <a name="members"></a>Üyeler

### <a name="constructors"></a>Oluşturucular

|Ad|Açıklama|
|-|-|
|[condition_variable](#condition_variable)|Bir `condition_variable` nesnesi oluşturur.|

### <a name="functions"></a>İşlevler

|Ad|Açıklama|
|-|-|
|[native_handle](#native_handle)|Condition_variable tanıtıcıyı temsil eden uygulamaya özel türü döndürür.|
|[notify_all](#notify_all)|Nesne için bekleyen tüm iş parçacıklarının bloklarını kaldırır `condition_variable` .|
|[notify_one](#notify_one)|Nesne için bekleyen iş parçacıklarından birinin engellemesini kaldırır `condition_variable` .|
|[bekleneceğini](#wait)|Bir iş parçacığını engeller.|
|[wait_for](#wait_for)|Bir iş parçacığını engeller ve sonra iş parçacığı bloklarından sonra bir zaman aralığı ayarlar.|
|[wait_until](#wait_until)|Bir iş parçacığını engeller ve iş parçacığı bloklarından en fazla bir zaman noktası ayarlar.|

## <a name="condition_variable"></a><a name="condition_variable"></a> condition_variable

Bir `condition_variable` nesnesi oluşturur.

```cpp
condition_variable();
```

### <a name="remarks"></a>Açıklamalar

Yeterli kullanılabilir bellek yoksa, Oluşturucu hata koduna sahip bir [system_error](../standard-library/system-error-class.md) nesnesi oluşturur `not_enough_memory` . Başka bir kaynak kullanılabilir olmadığından nesne oluşturulamıyor, Oluşturucu `system_error` hata koduna sahip bir nesne oluşturur `resource_unavailable_try_again` .

## <a name="native_handle"></a><a name="native_handle"></a> native_handle

Condition_variable tanıtıcısını temsil eden uygulamaya özel türü döndürür.

```cpp
native_handle_type native_handle();
```

### <a name="return-value"></a>Dönüş Değeri

`native_handle_type` Eşzamanlılık Çalışma Zamanı iç veri yapıları için bir işaretçi olarak tanımlanır.

## <a name="notify_all"></a><a name="notify_all"></a> notify_all

Nesne için bekleyen tüm iş parçacıklarının bloklarını kaldırır `condition_variable` .

```cpp
void notify_all() noexcept;
```

## <a name="notify_one"></a><a name="notify_one"></a> notify_one

Nesne üzerinde bekleyen iş parçacıklarından birinin engellemesini kaldırır `condition_variable` .

```cpp
void notify_one() noexcept;
```

## <a name="wait"></a><a name="wait"></a> bekleneceğini

Bir iş parçacığını engeller.

```cpp
void wait(unique_lock<mutex>& Lck);

template <class Predicate>
void wait(unique_lock<mutex>& Lck, Predicate Pred);
```

### <a name="parameters"></a>Parametreler

*LCK*\
[Unique_lock \<mutex> ](../standard-library/unique-lock-class.md) nesnesi.

*Pred*\
Veya döndüren herhangi bir **`true`** ifade **`false`** .

### <a name="remarks"></a>Açıklamalar

İlk yöntem, `condition_variable` nesneye bir [notify_one](#notify_one) veya [notify_all](#notify_all)çağrısıyla sinyallene kadar engeller. Ayrıca, uyanabilir 'i de uyandırabilirler.

Aslında, ikinci yöntem aşağıdaki kodu yürütür.

```cpp
while(!Pred())
    wait(Lck);
```

## <a name="wait_for"></a><a name="wait_for"></a> wait_for

Bir iş parçacığını engeller ve sonra iş parçacığı bloklarından sonra bir zaman aralığı ayarlar.

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

*LCK*\
[Unique_lock \<mutex> ](../standard-library/unique-lock-class.md) nesnesi.

*Rel_time*\
`chrono::duration`İş parçacığı uyanmadan önce geçen süreyi belirten bir nesne.

*Pred*\
Veya döndüren herhangi bir **`true`** ifade **`false`** .

### <a name="return-value"></a>Dönüş Değeri

İlk yöntem, `cv_status::timeout` *Rel_time* geçtiğinde bekleme sonlandırılırsa döndürür. Aksi takdirde, yöntemi döndürür `cv_status::no_timeout` .

İkinci yöntem *Pred*değerini döndürür.

### <a name="remarks"></a>Açıklamalar

İlk yöntem, `condition_variable` nesneye bir [notify_one](#notify_one) veya [notify_all](#notify_all) çağrısıyla ya da zaman aralığı *Rel_time* bitene kadar bir çağrı tarafından sinyallene kadar engeller. Ayrıca, uyanabilir 'i de uyandırabilirler.

Aslında, ikinci yöntem aşağıdaki kodu yürütür.

```cpp
while(!Pred())
    if(wait_for(Lck, Rel_time) == cv_status::timeout)
    return Pred();

return true;
```

## <a name="wait_until"></a><a name="wait_until"></a> wait_until

Bir iş parçacığını engeller ve iş parçacığı bloklarından en fazla bir zaman noktası ayarlar.

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

*LCK*\
[Unique_lock \<mutex> ](../standard-library/unique-lock-class.md) nesnesi.

*Abs_time*\
Bir zaman [hatası:: time_point](../standard-library/time-point-class.md) nesnesi.

*Pred*\
Veya döndüren herhangi bir **`true`** ifade **`false`** .

### <a name="return-value"></a>Dönüş Değeri

Bir tür döndüren yöntemler `cv_status` `cv_status::timeout` , *Abs_time* geçtiğinde bekleme sona erdiğinde döndürülür. Aksi halde Yöntemler döndürülür `cv_status::no_timeout` .

Döndüren yöntemler **`bool`** *Pred*değerini döndürür.

### <a name="remarks"></a>Açıklamalar

İlk yöntem, `condition_variable` nesneye [notify_one](#notify_one) veya [notify_all](#notify_all) veya Until çağrısı tarafından sinyallene kadar engeller `Abs_time` . Ayrıca, uyanabilir 'i de uyandırabilirler.

Aslında, ikinci yöntem aşağıdaki kodu yürütür

```cpp
while(!Pred())
    if(wait_until(Lck, Abs_time) == cv_status::timeout)
    return Pred();

return true;
```

Üçüncü ve dördüncü Yöntemler, nesneyi değiştirmek için türünde bir nesne işaretçisi kullanır `xtime` `chrono::time_point` . `xtime`Nesne, bir sinyal için beklenecek en uzun süreyi belirtir.

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)\
[<condition_variable>](../standard-library/condition-variable.md)
