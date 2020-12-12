---
description: 'Hakkında daha fazla bilgi edinin: timed_mutex sınıfı'
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
ms.openlocfilehash: af701a8f1f3777fb7f760c3eed561bd3dae5f21f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97167233"
---
# <a name="timed_mutex-class"></a>timed_mutex Sınıfı

Süreli bir *mutex türünü* temsil eder. Bu türden nesneler, bir program içindeki zaman sınırlı engelleme aracılığıyla karşılıklı dışlamayı zorlamak için kullanılır.

## <a name="syntax"></a>Syntax

```cpp
class timed_mutex;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[timed_mutex](#timed_mutex)|`timed_mutex`Kilitli olmayan bir nesne oluşturur.|
|[timed_mutex:: ~ timed_mutex yok edici](#dtortimed_mutex_destructor)|Nesnesi tarafından kullanılan tüm kaynakları serbest bırakır `timed_mutex` .|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[ine](#lock)|İş parçacığı sahipliğini alıncaya kadar çağıran iş parçacığını engeller `mutex` .|
|[try_lock](#try_lock)|Engellemeden sahipliğini almaya çalışır `mutex` .|
|[try_lock_for](#try_lock_for)|`mutex`Belirtilen zaman aralığı için sahipliğini almaya çalışır.|
|[try_lock_until](#try_lock_until)|`mutex`Belirtilen bir zamana kadar sahipliğini almaya çalışır.|
|[kaldırın](#unlock)|Öğesinin sahipliğini yayınlar `mutex` .|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<mutex>

**Ad alanı:** std

## <a name="timed_mutexlock"></a><a name="lock"></a> timed_mutex:: Lock

İş parçacığı sahipliğini alıncaya kadar çağıran iş parçacığını engeller `mutex` .

```cpp
void lock();
```

### <a name="remarks"></a>Açıklamalar

Çağıran iş parçacığı öğesine zaten sahipse `mutex` , davranış tanımsızdır.

## <a name="timed_mutextimed_mutex-constructor"></a><a name="timed_mutex"></a> timed_mutex:: timed_mutex Oluşturucusu

`timed_mutex`Kilitli olmayan bir nesne oluşturur.

```cpp
timed_mutex();
```

## <a name="timed_mutextimed_mutex-destructor"></a><a name="dtortimed_mutex_destructor"></a> timed_mutex:: ~ timed_mutex yok edici

Nesnesi tarafından kullanılan tüm kaynakları serbest bırakır `mutex` .

```cpp
~timed_mutex();
```

### <a name="remarks"></a>Açıklamalar

Yıkıcı çalıştırıldığında nesne kilitliyse, davranış tanımsızdır.

## <a name="timed_mutextry_lock"></a><a name="try_lock"></a> timed_mutex:: try_lock

Engellemeden sahipliğini almaya çalışır `mutex` .

```cpp
bool try_lock();
```

### <a name="return-value"></a>Dönüş Değeri

**`true`** Yöntemi öğesinin sahipliğini başarıyla alırsa `mutex` ; Aksi takdirde, **`false`** .

### <a name="remarks"></a>Açıklamalar

Çağıran iş parçacığı öğesine zaten sahipse `mutex` , davranış tanımsızdır.

## <a name="timed_mutextry_lock_for"></a><a name="try_lock_for"></a> timed_mutex:: try_lock_for

Engellemeden sahipliğini almaya çalışır `mutex` .

```cpp
template <class Rep, class Period>
bool try_lock_for(const chrono::duration<Rep, Period>& Rel_time);
```

### <a name="parameters"></a>Parametreler

*Rel_time*\
Bir zaman hatası: yöntemin sahipliğini almaya çalıştığı maksimum süreyi belirten [:d uration](../standard-library/duration-class.md) nesnesi `mutex` .

### <a name="return-value"></a>Dönüş Değeri

**`true`** Yöntemi öğesinin sahipliğini başarıyla alırsa `mutex` ; Aksi takdirde, **`false`** .

### <a name="remarks"></a>Açıklamalar

Çağıran iş parçacığı öğesine zaten sahipse `mutex` , davranış tanımsızdır.

## <a name="timed_mutextry_lock_until"></a><a name="try_lock_until"></a> timed_mutex:: try_lock_until

Engellemeden sahipliğini almaya çalışır `mutex` .

```cpp
template <class Clock, class Duration>
bool try_lock_for(const chrono::time_point<Clock, Duration>& Abs_time);

bool try_lock_until(const xtime* Abs_time);
```

### <a name="parameters"></a>Parametreler

*Abs_time*\
Bir zaman içinde, yöntemin sahipliğini elde etme girişiminde bulunmayan eşiği belirten bir nokta `mutex` .

### <a name="return-value"></a>Dönüş Değeri

**`true`** Yöntemi öğesinin sahipliğini başarıyla alırsa `mutex` ; Aksi takdirde, **`false`** .

### <a name="remarks"></a>Açıklamalar

Çağıran iş parçacığı öğesine zaten sahipse `mutex` , davranış tanımsızdır.

## <a name="timed_mutexunlock"></a><a name="unlock"></a> timed_mutex:: unlock

Öğesinin sahipliğini yayınlar `mutex` .

```cpp
void unlock();
```

### <a name="remarks"></a>Açıklamalar

Çağıran iş parçacığı öğesine sahip değilse `mutex` , davranış tanımsızdır.

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)\
[\<mutex>](../standard-library/mutex.md)
