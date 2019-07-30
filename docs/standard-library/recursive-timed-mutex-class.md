---
title: recursive_timed_mutex Sınıfı
ms.date: 11/04/2016
f1_keywords:
- mutex/std::recursive_timed_mutex
- mutex/std::recursive_timed_mutex::recursive_timed_mutex
- mutex/std::recursive_timed_mutex::lock
- mutex/std::recursive_timed_mutex::try_lock
- mutex/std::recursive_timed_mutex::try_lock_for
- mutex/std::recursive_timed_mutex::try_lock_until
- mutex/std::recursive_timed_mutex::unlock
ms.assetid: 59cc2d5c-ed80-45f3-a0a8-05652a8ead7e
helpviewer_keywords:
- std::recursive_timed_mutex [C++]
- std::recursive_timed_mutex [C++], recursive_timed_mutex
- std::recursive_timed_mutex [C++], lock
- std::recursive_timed_mutex [C++], try_lock
- std::recursive_timed_mutex [C++], try_lock_for
- std::recursive_timed_mutex [C++], try_lock_until
- std::recursive_timed_mutex [C++], unlock
ms.openlocfilehash: 6ae61d17084cc744cac8819ac2c0ca48eb59add7
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68460115"
---
# <a name="recursivetimedmutex-class"></a>recursive_timed_mutex Sınıfı

Süreli bir *mutex türünü*temsil eder. Bu türden nesneler, bir program içindeki zaman sınırlı engellemeyi kullanarak karşılıklı dışlamanın uygulanmasını sağlamak için kullanılır. [Timed_mutex](../standard-library/timed-mutex-class.md)türündeki nesnelerden farklı olarak, nesneler için `recursive_timed_mutex` kilitleme yöntemlerinin çağrılması iyi bir şekilde tanımlanır.

## <a name="syntax"></a>Sözdizimi

```cpp
class recursive_timed_mutex;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[recursive_timed_mutex](#recursive_timed_mutex)|Kilitli olmayan `recursive_timed_mutex` bir nesne oluşturur.|
|[~recursive_timed_mutex Destructor](#dtorrecursive_timed_mutex_destructor)|`recursive_timed_mutex` Nesnesi tarafından kullanılan tüm kaynakları serbest bırakır.|

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

## <a name="lock"></a>ine

İş parçacığı sahipliğini `mutex`alıncaya kadar çağıran iş parçacığını engeller.

```cpp
void lock();
```

### <a name="remarks"></a>Açıklamalar

Çağıran iş parçacığı öğesine zaten sahipse `mutex`, yöntemi hemen döndürür ve önceki kilit etkin kalır.

## <a name="recursive_timed_mutex"></a>recursive_timed_mutex Oluşturucusu

Kilitli olmayan `recursive_timed_mutex` bir nesne oluşturur.

```cpp
recursive_timed_mutex();
```

## <a name="dtorrecursive_timed_mutex_destructor"></a>~ recursive_timed_mutex yıkıcısı

`recursive_timed_mutex` Nesnesi tarafından kullanılan tüm kaynakları serbest bırakır.

```cpp
~recursive_timed_mutex();
```

### <a name="remarks"></a>Açıklamalar

Yıkıcı çalıştırıldığında nesne kilitliyse, davranış tanımsızdır.

## <a name="try_lock"></a>try_lock

`mutex` Engellemeden sahipliğini almaya çalışır.

```cpp
bool try_lock() noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

yöntemi, çağıran `mutex` `mutex`iş parçacığının zaten sahip olduğu veya sahip olduğu durumlarda, yanlış bir şekilde sahipliyse **true** ; Aksi takdirde, **false**.

### <a name="remarks"></a>Açıklamalar

Çağıran iş parçacığı öğesine zaten sahipse `mutex`, işlev hemen **true**değerini döndürür ve önceki kilit etkin kalır.

## <a name="try_lock_for"></a>try_lock_for

`mutex` Engellemeden sahipliğini almaya çalışır.

```cpp
template <class Rep, class Period>
bool try_lock_for(const chrono::duration<Rep, Period>& Rel_time);
```

### <a name="parameters"></a>Parametreler

*Rel_time*\
Bir zaman hatası: yöntemin sahipliğini `mutex`almaya çalıştığı maksimum süreyi belirten [:d uration](../standard-library/duration-class.md) nesnesi.

### <a name="return-value"></a>Dönüş Değeri

yöntemi, `mutex` çağıran`mutex`iş parçacığının zaten sahip olduğu bir veya ' nin sahipliğini alırsa doğru, aksi takdirde yanlış olur.

### <a name="remarks"></a>Açıklamalar

Çağıran iş parçacığı zaten öğesine sahipse `mutex`, yöntemi hemen **true**döndürür ve önceki kilit etkin kalır.

## <a name="try_lock_until"></a>try_lock_until

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

yöntemi, `mutex` çağıran`mutex`iş parçacığının zaten sahip olduğu bir veya ' nin sahipliğini alırsa doğru, aksi takdirde yanlış olur.

### <a name="remarks"></a>Açıklamalar

Çağıran iş parçacığı zaten öğesine sahipse `mutex`, yöntemi hemen **true**döndürür ve önceki kilit etkin kalır.

## <a name="unlock"></a>kaldırın

Öğesinin sahipliğini yayınlar `mutex`.

```cpp
void unlock();
```

### <a name="remarks"></a>Açıklamalar

`mutex` Bu yöntem, `recursive_timed_mutex` nesne üzerinde [Lock](#lock), [try_lock](#try_lock), [try_lock_for](#try_lock_for)ve [try_lock_until](#try_lock_until) başarıyla çağrıldıkça, öğesinin sahipliğini yalnızca bir kez çağırılır.

Çağıran iş parçacığı öğesine sahip `mutex`değilse, davranış tanımsızdır.

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)\
[\<mutex >](../standard-library/mutex.md)
