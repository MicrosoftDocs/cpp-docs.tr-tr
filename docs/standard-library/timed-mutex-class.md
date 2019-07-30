---
title: timed_mutex Sınıfı
ms.date: 11/04/2016
f1_keywords:
- mutex/std::timed_mutex
- mutex/std::timed_mutex::timed_mutex
- mutex/std::timed_mutex::lock
- mutex/std::timed_mutex::try_lock
- mutex/std::timed_mutex::try_lock_for
- mutex/std::timed_mutex::try_lock_until
- mutex/std::timed_mutex::unlock
ms.assetid: cd198081-6f38-447a-9dba-e06dfbfafe59
helpviewer_keywords:
- std::timed_mutex [C++]
- std::timed_mutex [C++], timed_mutex
- std::timed_mutex [C++], lock
- std::timed_mutex [C++], try_lock
- std::timed_mutex [C++], try_lock_for
- std::timed_mutex [C++], try_lock_until
- std::timed_mutex [C++], unlock
ms.openlocfilehash: 6b9785dc41791be63d585d18802953eade370b2a
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68459917"
---
# <a name="timedmutex-class"></a>timed_mutex Sınıfı

Süreli bir *mutex türünü*temsil eder. Bu türden nesneler, bir program içindeki zaman sınırlı engelleme aracılığıyla karşılıklı dışlamayı zorlamak için kullanılır.

## <a name="syntax"></a>Sözdizimi

```cpp
class timed_mutex;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[timed_mutex](#timed_mutex)|Kilitli olmayan `timed_mutex` bir nesne oluşturur.|
|[timed_mutex:: ~ timed_mutex yıkıcısı](#dtortimed_mutex_destructor)|`timed_mutex` Nesnesi tarafından kullanılan tüm kaynakları serbest bırakır.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[lock](#lock)|İş parçacığı sahipliğini `mutex`alıncaya kadar çağıran iş parçacığını engeller.|
|[try_lock](#try_lock)|`mutex` Engellemeden sahipliğini almaya çalışır.|
|[try_lock_for](#try_lock_for)|Belirtilen zaman aralığı `mutex` için sahipliğini almaya çalışır.|
|[try_lock_until](#try_lock_until)|Belirtilen bir zamana `mutex` kadar sahipliğini almaya çalışır.|
|[kaldırın](#unlock)|Öğesinin sahipliğini yayınlar `mutex`.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<mutex >

**Ad alanı:** std

## <a name="lock"></a>timed_mutex:: Lock

İş parçacığı sahipliğini `mutex`alıncaya kadar çağıran iş parçacığını engeller.

```cpp
void lock();
```

### <a name="remarks"></a>Açıklamalar

Çağıran iş parçacığı öğesine zaten sahipse `mutex`, davranış tanımsızdır.

## <a name="timed_mutex"></a>timed_mutex:: timed_mutex Oluşturucusu

Kilitli olmayan `timed_mutex` bir nesne oluşturur.

```cpp
timed_mutex();
```

## <a name="dtortimed_mutex_destructor"></a>timed_mutex:: ~ timed_mutex yıkıcısı

`mutex` Nesnesi tarafından kullanılan tüm kaynakları serbest bırakır.

```cpp
~timed_mutex();
```

### <a name="remarks"></a>Açıklamalar

Yıkıcı çalıştırıldığında nesne kilitliyse, davranış tanımsızdır.

## <a name="try_lock"></a>timed_mutex::try_lock

`mutex` Engellemeden sahipliğini almaya çalışır.

```cpp
bool try_lock();
```

### <a name="return-value"></a>Dönüş Değeri

Yöntem öğesinin `mutex`sahipliğini başarıyla alırsa doğru, aksi takdirde **yanlış**olur.

### <a name="remarks"></a>Açıklamalar

Çağıran iş parçacığı öğesine zaten sahipse `mutex`, davranış tanımsızdır.

## <a name="try_lock_for"></a>timed_mutex::try_lock_for

`mutex` Engellemeden sahipliğini almaya çalışır.

```cpp
template <class Rep, class Period>
bool try_lock_for(const chrono::duration<Rep, Period>& Rel_time);
```

### <a name="parameters"></a>Parametreler

*Rel_time*\
Bir zaman hatası: yöntemin sahipliğini `mutex`almaya çalıştığı maksimum süreyi belirten [:d uration](../standard-library/duration-class.md) nesnesi.

### <a name="return-value"></a>Dönüş Değeri

Yöntem öğesinin `mutex`sahipliğini başarıyla alırsa doğru, aksi takdirde **yanlış**olur.

### <a name="remarks"></a>Açıklamalar

Çağıran iş parçacığı öğesine zaten sahipse `mutex`, davranış tanımsızdır.

## <a name="try_lock_until"></a>timed_mutex::try_lock_until

`mutex` Engellemeden sahipliğini almaya çalışır.

```cpp
template <class Clock, class Duration>
bool try_lock_for(const chrono::time_point<Clock, Duration>& Abs_time);

bool try_lock_until(const xtime* Abs_time);
```

### <a name="parameters"></a>Parametreler

*Abs_time*\
Bir zaman içinde, `mutex`yöntemin sahipliğini elde etme girişiminde bulunmayan eşiği belirten bir nokta.

### <a name="return-value"></a>Dönüş Değeri

Yöntem öğesinin `mutex`sahipliğini başarıyla alırsa doğru, aksi takdirde **yanlış**olur.

### <a name="remarks"></a>Açıklamalar

Çağıran iş parçacığı öğesine zaten sahipse `mutex`, davranış tanımsızdır.

## <a name="unlock"></a>  timed_mutex::unlock

Öğesinin sahipliğini yayınlar `mutex`.

```cpp
void unlock();
```

### <a name="remarks"></a>Açıklamalar

Çağıran iş parçacığı öğesine sahip `mutex`değilse, davranış tanımsızdır.

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)\
[\<mutex >](../standard-library/mutex.md)
