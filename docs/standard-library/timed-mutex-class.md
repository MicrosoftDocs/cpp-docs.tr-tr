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
ms.openlocfilehash: 6c9840d9b8c00d4b03e6ea329c7707a0edff9512
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368012"
---
# <a name="timed_mutex-class"></a>timed_mutex Sınıfı

*Zamanlanmış mutex türünü*temsil eder. Bu tür nesneler, program içinde zaman sınırlı engelleme yoluyla karşılıklı dışlama zorlamak için kullanılır.

## <a name="syntax"></a>Sözdizimi

```cpp
class timed_mutex;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[timed_mutex](#timed_mutex)|Kilitli olmayan `timed_mutex` bir nesne inşa eder.|
|[timed_mutex::~timed_mutex Yıkıcı](#dtortimed_mutex_destructor)|`timed_mutex` Nesne tarafından kullanılan tüm kaynakları salgılar.|

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

## <a name="timed_mutexlock"></a><a name="lock"></a>timed_mutex::kilit

İş `mutex`parçacığı.

```cpp
void lock();
```

### <a name="remarks"></a>Açıklamalar

Arama iş parçacığı zaten `mutex`sahibi ise, davranış tanımsız.

## <a name="timed_mutextimed_mutex-constructor"></a><a name="timed_mutex"></a>timed_mutex::timed_mutex Yapıcı

Kilitli olmayan `timed_mutex` bir nesne inşa eder.

```cpp
timed_mutex();
```

## <a name="timed_mutextimed_mutex-destructor"></a><a name="dtortimed_mutex_destructor"></a>timed_mutex::~timed_mutex Yıkıcı

`mutex` Nesne tarafından kullanılan tüm kaynakları salgılar.

```cpp
~timed_mutex();
```

### <a name="remarks"></a>Açıklamalar

Yıkıcı çalıştığında nesne kilitlenirse, davranış tanımsız kalır.

## <a name="timed_mutextry_lock"></a><a name="try_lock"></a>timed_mutex:try_lock

`mutex` Engellemeden sahipliğini elde etmeye çalışır.

```cpp
bool try_lock();
```

### <a name="return-value"></a>Dönüş Değeri

yöntem başarıyla sahiplik elde ederse `mutex` **doğrudur;** aksi takdirde, **yanlış**.

### <a name="remarks"></a>Açıklamalar

Arama iş parçacığı zaten `mutex`sahibi ise, davranış tanımsız.

## <a name="timed_mutextry_lock_for"></a><a name="try_lock_for"></a>timed_mutex::try_lock_for

`mutex` Engellemeden sahipliğini elde etmeye çalışır.

```cpp
template <class Rep, class Period>
bool try_lock_for(const chrono::duration<Rep, Period>& Rel_time);
```

### <a name="parameters"></a>Parametreler

*Rel_time*\
Bir [kronometre::duration](../standard-library/duration-class.md) nesnesi, yöntemin sahipliğini elde etmeye `mutex`çalıştığı maksimum süreyi belirtir.

### <a name="return-value"></a>Dönüş Değeri

yöntem başarıyla sahiplik elde ederse `mutex` **doğrudur;** aksi takdirde, **yanlış**.

### <a name="remarks"></a>Açıklamalar

Arama iş parçacığı zaten `mutex`sahibi ise, davranış tanımsız.

## <a name="timed_mutextry_lock_until"></a><a name="try_lock_until"></a>timed_mutex:try_lock_until

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

yöntem başarıyla sahiplik elde ederse `mutex` **doğrudur;** aksi takdirde, **yanlış**.

### <a name="remarks"></a>Açıklamalar

Arama iş parçacığı zaten `mutex`sahibi ise, davranış tanımsız.

## <a name="timed_mutexunlock"></a><a name="unlock"></a>timed_mutex::kilidini açın

`mutex`Sahiplik serbest bırakır.

```cpp
void unlock();
```

### <a name="remarks"></a>Açıklamalar

Arama iş parçacığı, davranış `mutex`tanımsız sahibi değilse.

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi Dosyaları Başvurusu](../standard-library/cpp-standard-library-header-files.md)\
[\<mutex>](../standard-library/mutex.md)
