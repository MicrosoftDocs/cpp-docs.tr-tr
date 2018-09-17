---
title: timed_mutex sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- mutex/std::timed_mutex
- mutex/std::timed_mutex::timed_mutex
- mutex/std::timed_mutex::lock
- mutex/std::timed_mutex::try_lock
- mutex/std::timed_mutex::try_lock_for
- mutex/std::timed_mutex::try_lock_until
- mutex/std::timed_mutex::unlock
dev_langs:
- C++
ms.assetid: cd198081-6f38-447a-9dba-e06dfbfafe59
author: corob-msft
ms.author: corob
helpviewer_keywords:
- std::timed_mutex [C++]
- std::timed_mutex [C++], timed_mutex
- std::timed_mutex [C++], lock
- std::timed_mutex [C++], try_lock
- std::timed_mutex [C++], try_lock_for
- std::timed_mutex [C++], try_lock_until
- std::timed_mutex [C++], unlock
ms.workload:
- cplusplus
ms.openlocfilehash: 4ed4f12e127c6ceef212ffefc512e764dd53fb19
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45706556"
---
# <a name="timedmutex-class"></a>timed_mutex Sınıfı

Temsil eden bir *mutex türünü zaman aşımına*. Bu tür nesneler bir program içindeki süre sınırlı engelleme üzerinden karşılıklı dışlama uygulamak için kullanılır.

## <a name="syntax"></a>Sözdizimi

```cpp
class timed_mutex;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[timed_mutex](#timed_mutex)|Oluşturur bir `timed_mutex` kilitli olmayan bir nesne.|
|[timed_mutex:: ~ timed_mutex yıkıcısı](#dtortimed_mutex_destructor)|Tarafından kullanılan kaynakları serbest `timed_mutex` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[lock](#lock)|İş parçacığı sahipliğini alana kadar çağıran iş parçacığını engeller `mutex`.|
|[try_lock](#try_lock)|Sahipliğini almayı dener `mutex` engelleme olmadan.|
|[try_lock_for](#try_lock_for)|Sahipliğini almayı dener `mutex` belirtilen zaman aralığı için.|
|[try_lock_until](#try_lock_until)|Sahipliğini almayı dener `mutex` belirli bir süre kadar.|
|[Kilit açma](#unlock)|İn sahipliğini bırakır `mutex`.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<mutex >

**Namespace:** std

## <a name="lock"></a>  timed_mutex::LOCK

İş parçacığı sahipliğini alana kadar çağıran iş parçacığını engeller `mutex`.

```cpp
void lock();
```

### <a name="remarks"></a>Açıklamalar

Çağıran iş parçacığı zaten sahipse `mutex`, davranış tanımlanmamıştır.

## <a name="timed_mutex"></a>  timed_mutex::timed_mutex Oluşturucusu

Oluşturur bir `timed_mutex` kilitli olmayan bir nesne.

```cpp
timed_mutex();
```

## <a name="dtortimed_mutex_destructor"></a>  timed_mutex:: ~ timed_mutex yıkıcısı

Tarafından kullanılan kaynakları serbest `mutex` nesne.

```cpp
~timed_mutex();
```

### <a name="remarks"></a>Açıklamalar

Yıkıcı çalıştığında nesne kilitli değilse davranış tanımlanmamıştır.

## <a name="try_lock"></a>  timed_mutex::try_lock

Sahipliğini almayı dener `mutex` engelleme olmadan.

```cpp
bool try_lock();
```

### <a name="return-value"></a>Dönüş Değeri

**doğru** yöntemi başarıyla sahipliğini elde ederse `mutex`; Aksi takdirde **false**.

### <a name="remarks"></a>Açıklamalar

Çağıran iş parçacığı zaten sahipse `mutex`, davranış tanımlanmamıştır.

## <a name="try_lock_for"></a>  timed_mutex::try_lock_for

Sahipliğini almayı dener `mutex` engelleme olmadan.

```cpp
template <class Rep, class Period>
bool try_lock_for(const chrono::duration<Rep, Period>& Rel_time);
```

### <a name="parameters"></a>Parametreler

*Rel_time*<br/>
A [chrono::duration](../standard-library/duration-class.md) yöntemi sahipliğini almayı dener en uzun süreyi belirten nesne `mutex`.

### <a name="return-value"></a>Dönüş Değeri

**doğru** yöntemi başarıyla sahipliğini elde ederse `mutex`; Aksi takdirde **false**.

### <a name="remarks"></a>Açıklamalar

Çağıran iş parçacığı zaten sahipse `mutex`, davranış tanımlanmamıştır.

## <a name="try_lock_until"></a>  timed_mutex::try_lock_until

Sahipliğini almayı dener `mutex` engelleme olmadan.

```cpp
template <class Clock, class Duration>
bool try_lock_for(const chrono::time_point<Clock, Duration>& Abs_time);

bool try_lock_until(const xtime* Abs_time);
```

### <a name="parameters"></a>Parametreler

*Abs_time*<br/>
Sonra yöntemi artık girişimlerini sahipliğini almayı eşiği belirten zaman içinde nokta `mutex`.

### <a name="return-value"></a>Dönüş Değeri

**doğru** yöntemi başarıyla sahipliğini elde ederse `mutex`; Aksi takdirde **false**.

### <a name="remarks"></a>Açıklamalar

Çağıran iş parçacığı zaten sahipse `mutex`, davranış tanımlanmamıştır.

## <a name="unlock"></a>  timed_mutex::unlock

İn sahipliğini bırakır `mutex`.

```cpp
void unlock();
```

### <a name="remarks"></a>Açıklamalar

Çağıran iş parçacığına ait olmayan, `mutex`, davranış tanımlanmamıştır.

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)<br/>
[\<Mutex >](../standard-library/mutex.md)<br/>
