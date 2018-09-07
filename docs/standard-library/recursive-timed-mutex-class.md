---
title: recursive_timed_mutex sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- mutex/std::recursive_timed_mutex
- mutex/std::recursive_timed_mutex::recursive_timed_mutex
- mutex/std::recursive_timed_mutex::lock
- mutex/std::recursive_timed_mutex::try_lock
- mutex/std::recursive_timed_mutex::try_lock_for
- mutex/std::recursive_timed_mutex::try_lock_until
- mutex/std::recursive_timed_mutex::unlock
dev_langs:
- C++
ms.assetid: 59cc2d5c-ed80-45f3-a0a8-05652a8ead7e
author: corob-msft
ms.author: corob
helpviewer_keywords:
- std::recursive_timed_mutex [C++]
- std::recursive_timed_mutex [C++], recursive_timed_mutex
- std::recursive_timed_mutex [C++], lock
- std::recursive_timed_mutex [C++], try_lock
- std::recursive_timed_mutex [C++], try_lock_for
- std::recursive_timed_mutex [C++], try_lock_until
- std::recursive_timed_mutex [C++], unlock
ms.workload:
- cplusplus
ms.openlocfilehash: f30cf00a1e551c8d25b17d3a876d556ecea40c9e
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/07/2018
ms.locfileid: "44107646"
---
# <a name="recursivetimedmutex-class"></a>recursive_timed_mutex Sınıfı

Temsil eden bir *mutex türünü zaman aşımına*. Bu tür nesneler bir program içindeki süre sınırlı engelleme kullanarak karşılıklı dışlama uygulamak için kullanılır. Türündeki nesneler aksine [timed_mutex](../standard-library/timed-mutex-class.md), kilitleme yöntemleri çağırma etkisini `recursive_timed_mutex` nesneleri, iyi tanımlanmış.

## <a name="syntax"></a>Sözdizimi

```cpp
class recursive_timed_mutex;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[recursive_timed_mutex](#recursive_timed_mutex)|Oluşturur bir `recursive_timed_mutex` kilitli olmayan bir nesne.|
|[~recursive_timed_mutex Destructor](#dtorrecursive_timed_mutex_destructor)|Tarafından kullanılan kaynakları serbest `recursive_timed_mutex` nesne.|

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

## <a name="lock"></a>  Kilit

İş parçacığı sahipliğini alana kadar çağıran iş parçacığını engeller `mutex`.

```cpp
void lock();
```

### <a name="remarks"></a>Açıklamalar

Çağıran iş parçacığı zaten sahipse `mutex`, yöntem hemen döner ve önceki kilidi yürürlükte kalır.

## <a name="recursive_timed_mutex"></a>  recursive_timed_mutex Oluşturucusu

Oluşturur bir `recursive_timed_mutex` kilitli olmayan bir nesne.

```cpp
recursive_timed_mutex();
```

## <a name="dtorrecursive_timed_mutex_destructor"></a>  ~ recursive_timed_mutex yıkıcısı

Tarafından kullanılan kaynakları serbest `recursive_timed_mutex` nesne.

```cpp
~recursive_timed_mutex();
```

### <a name="remarks"></a>Açıklamalar

Yıkıcı çalıştığında nesne kilitli değilse davranış tanımlanmamıştır.

## <a name="try_lock"></a>  try_lock

Sahipliğini almayı dener `mutex` engelleme olmadan.

```cpp
bool try_lock() noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

**doğru** yöntemi başarıyla sahipliğini aldıysanız `mutex` veya çağıran iş parçacığı zaten sahipse `mutex`; Aksi takdirde **false**.

### <a name="remarks"></a>Açıklamalar

Çağıran iş parçacığı zaten sahipse `mutex`, işlevi hemen döndürür **true**, ve önceki kilidi yürürlükte kalır.

## <a name="try_lock_for"></a>  try_lock_for

Sahipliğini almayı dener `mutex` engelleme olmadan.

```cpp
template <class Rep, class Period>
bool try_lock_for(const chrono::duration<Rep, Period>& Rel_time);
```

### <a name="parameters"></a>Parametreler

*Rel_time*<br/>
A [chrono::duration](../standard-library/duration-class.md) yöntemi sahipliğini almayı dener en uzun süreyi belirten nesne `mutex`.

### <a name="return-value"></a>Dönüş Değeri

**doğru** yöntemi başarıyla sahipliğini elde ederse `mutex` veya çağıran iş parçacığı zaten sahipse `mutex`; Aksi takdirde **false**.

### <a name="remarks"></a>Açıklamalar

Çağıran iş parçacığı zaten sahipse `mutex`, yöntem hemen döner **true**, ve önceki kilidi yürürlükte kalır.

## <a name="try_lock_until"></a>  try_lock_until

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

**doğru** yöntemi başarıyla sahipliğini elde ederse `mutex` veya çağıran iş parçacığı zaten sahipse `mutex`; Aksi takdirde **false**.

### <a name="remarks"></a>Açıklamalar

Çağıran iş parçacığı zaten sahipse `mutex`, yöntem hemen döner **true**, ve önceki kilidi yürürlükte kalır.

## <a name="unlock"></a>  Kilit açma

İn sahipliğini bırakır `mutex`.

```cpp
void unlock();
```

### <a name="remarks"></a>Açıklamalar

Bu yöntem sahipliğini serbest `mutex` yalnızca olarak sayıda çağrıldıktan sonra [kilit](#lock), [try_lock](#try_lock), [try_lock_for](#try_lock_for), ve [try_lock_ kadar](#try_lock_until) üzerinde başarıyla çağrılmışsa `recursive_timed_mutex` nesne.

Çağıran iş parçacığına ait olmayan, `mutex`, davranış tanımlanmamıştır.

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)<br/>
[\<Mutex >](../standard-library/mutex.md)<br/>
