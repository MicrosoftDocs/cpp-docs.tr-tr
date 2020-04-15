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
ms.openlocfilehash: 93ce7b99728d1ce89c8124efd6c74aea7ff66d22
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81320141"
---
# <a name="recursive_timed_mutex-class"></a>recursive_timed_mutex Sınıfı

*Zamanlanmış mutex türünü*temsil eder. Bu tür nesneler, bir program içinde zaman sınırlı engelleme kullanarak karşılıklı dışlama zorlamak için kullanılır. Tür [timed_mutex](../standard-library/timed-mutex-class.md)nesnelerinaksine, nesneler için `recursive_timed_mutex` kilitleme yöntemleri ni çağırma etkisi iyi tanımlanmıştır.

## <a name="syntax"></a>Sözdizimi

```cpp
class recursive_timed_mutex;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[recursive_timed_mutex](#recursive_timed_mutex)|Kilitli olmayan `recursive_timed_mutex` bir nesne inşa eder.|
|[~recursive_timed_mutex Yıkıcı](#dtorrecursive_timed_mutex_destructor)|`recursive_timed_mutex` Nesne tarafından kullanılan tüm kaynakları salgılar.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[Kilit](#lock)|İş `mutex`parçacığı.|
|[try_lock](#try_lock)|`mutex` Engellemeden sahipliğini elde etmeye çalışır.|
|[try_lock_for](#try_lock_for)|Belirli bir zaman `mutex` aralığıiçin sahipliğini elde etmeye çalışır.|
|[try_lock_until](#try_lock_until)|Belirli bir zamana `mutex` kadar sahipliğini elde etmeye çalışır.|
|[Kilidini](#unlock)|`mutex`Sahiplik serbest bırakır.|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** \<mutex>

**Ad alanı:** std

## <a name="lock"></a><a name="lock"></a>Kilit

İş `mutex`parçacığı.

```cpp
void lock();
```

### <a name="remarks"></a>Açıklamalar

Arama iş parçacığı zaten `mutex`sahibi, yöntem hemen döndürür ve önceki kilit etkin kalır.

## <a name="recursive_timed_mutex-constructor"></a><a name="recursive_timed_mutex"></a>recursive_timed_mutex Yapıcı

Kilitli olmayan `recursive_timed_mutex` bir nesne inşa eder.

```cpp
recursive_timed_mutex();
```

## <a name="recursive_timed_mutex-destructor"></a><a name="dtorrecursive_timed_mutex_destructor"></a>~recursive_timed_mutex Yıkıcı

`recursive_timed_mutex` Nesne tarafından kullanılan tüm kaynakları salgılar.

```cpp
~recursive_timed_mutex();
```

### <a name="remarks"></a>Açıklamalar

Yıkıcı çalıştığında nesne kilitlenirse, davranış tanımsız kalır.

## <a name="try_lock"></a><a name="try_lock"></a>try_lock

`mutex` Engellemeden sahipliğini elde etmeye çalışır.

```cpp
bool try_lock() noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

yöntem başarıyla sahiplik `mutex` elde veya arama iş parçacığı `mutex`zaten sahibi ise **doğru** ; aksi takdirde, **yanlış**.

### <a name="remarks"></a>Açıklamalar

Arama iş parçacığı zaten `mutex`sahibi ise , işlev hemen **doğru**döndürür , ve önceki kilit etkin kalır.

## <a name="try_lock_for"></a><a name="try_lock_for"></a>try_lock_for

`mutex` Engellemeden sahipliğini elde etmeye çalışır.

```cpp
template <class Rep, class Period>
bool try_lock_for(const chrono::duration<Rep, Period>& Rel_time);
```

### <a name="parameters"></a>Parametreler

*Rel_time*\
Bir [kronometre::duration](../standard-library/duration-class.md) nesnesi, yöntemin sahipliğini elde etmeye `mutex`çalıştığı maksimum süreyi belirtir.

### <a name="return-value"></a>Dönüş Değeri

yöntem başarıyla sahiplik `mutex` elde veya arama iş parçacığı zaten `mutex`sahibi ise **doğru** ; aksi takdirde, **yanlış**.

### <a name="remarks"></a>Açıklamalar

Arama iş parçacığı zaten `mutex`sahibiise , yöntem hemen **doğru**döndürür ve önceki kilit etkin kalır.

## <a name="try_lock_until"></a><a name="try_lock_until"></a>try_lock_until

`mutex` Engellemeden sahipliğini elde etmeye çalışır.

```cpp
template <class Clock, class Duration>
bool try_lock_for(const chrono::time_point<Clock, Duration>& Abs_time);

bool try_lock_until(const xtime* Abs_time);
```

### <a name="parameters"></a>Parametreler

*Abs_time*\
Zaman içinde bir nokta hangi yöntem artık sahipliğini elde etmek için `mutex`çalışır sonra eşik belirtir .

### <a name="return-value"></a>Dönüş Değeri

yöntem başarıyla sahiplik `mutex` elde veya arama iş parçacığı zaten `mutex`sahibi ise **doğru** ; aksi takdirde, **yanlış**.

### <a name="remarks"></a>Açıklamalar

Arama iş parçacığı zaten `mutex`sahibiise , yöntem hemen **doğru**döndürür ve önceki kilit etkin kalır.

## <a name="unlock"></a><a name="unlock"></a>Kilidini

`mutex`Sahiplik serbest bırakır.

```cpp
void unlock();
```

### <a name="remarks"></a>Açıklamalar

Bu yöntem, yalnızca `mutex` [kilit](#lock), [try_lock](#try_lock), [try_lock_for](#try_lock_for)ve [try_lock_until](#try_lock_until) nesne üzerinde `recursive_timed_mutex` başarıyla çağrıldıktan sonra sahiplik serbest bırakır.

Arama iş parçacığı, davranış `mutex`tanımsız sahibi değilse.

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi Dosyaları Başvurusu](../standard-library/cpp-standard-library-header-files.md)\
[\<mutex>](../standard-library/mutex.md)
