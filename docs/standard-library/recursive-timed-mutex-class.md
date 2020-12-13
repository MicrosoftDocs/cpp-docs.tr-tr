---
description: 'Hakkında daha fazla bilgi edinin: recursive_timed_mutex sınıfı'
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
ms.openlocfilehash: 55722414e89f6ec91fd355208ffe5dcc491405be
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97337873"
---
# <a name="recursive_timed_mutex-class"></a>recursive_timed_mutex Sınıfı

Süreli bir *mutex türünü* temsil eder. Bu türden nesneler, bir program içindeki zaman sınırlı engellemeyi kullanarak karşılıklı dışlamanın uygulanmasını sağlamak için kullanılır. [Timed_mutex](../standard-library/timed-mutex-class.md)türündeki nesnelerden farklı olarak, nesneler için kilitleme yöntemlerinin çağrılması iyi bir şekilde `recursive_timed_mutex` tanımlanır.

## <a name="syntax"></a>Syntax

```cpp
class recursive_timed_mutex;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[recursive_timed_mutex](#recursive_timed_mutex)|`recursive_timed_mutex`Kilitli olmayan bir nesne oluşturur.|
|[~ recursive_timed_mutex yok edici](#dtorrecursive_timed_mutex_destructor)|Nesnesi tarafından kullanılan tüm kaynakları serbest bırakır `recursive_timed_mutex` .|

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

## <a name="lock"></a><a name="lock"></a> ine

İş parçacığı sahipliğini alıncaya kadar çağıran iş parçacığını engeller `mutex` .

```cpp
void lock();
```

### <a name="remarks"></a>Açıklamalar

Çağıran iş parçacığı öğesine zaten sahipse `mutex` , yöntemi hemen döndürür ve önceki kilit etkin kalır.

## <a name="recursive_timed_mutex-constructor"></a><a name="recursive_timed_mutex"></a> recursive_timed_mutex Oluşturucusu

`recursive_timed_mutex`Kilitli olmayan bir nesne oluşturur.

```cpp
recursive_timed_mutex();
```

## <a name="recursive_timed_mutex-destructor"></a><a name="dtorrecursive_timed_mutex_destructor"></a>  ~ recursive_timed_mutex yok edici

Nesnesi tarafından kullanılan tüm kaynakları serbest bırakır `recursive_timed_mutex` .

```cpp
~recursive_timed_mutex();
```

### <a name="remarks"></a>Açıklamalar

Yıkıcı çalıştırıldığında nesne kilitliyse, davranış tanımsızdır.

## <a name="try_lock"></a><a name="try_lock"></a> try_lock

Engellemeden sahipliğini almaya çalışır `mutex` .

```cpp
bool try_lock() noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

**`true`** yöntemi, `mutex` çağıran iş parçacığı öğesine zaten sahip ise veya sahipliğini başarıyla aldıysanız `mutex` ; Aksi takdirde, **`false`** .

### <a name="remarks"></a>Açıklamalar

Çağıran iş parçacığı öğesine zaten sahipse `mutex` , işlev hemen döner **`true`** ve önceki kilit etkin kalır.

## <a name="try_lock_for"></a><a name="try_lock_for"></a> try_lock_for

Engellemeden sahipliğini almaya çalışır `mutex` .

```cpp
template <class Rep, class Period>
bool try_lock_for(const chrono::duration<Rep, Period>& Rel_time);
```

### <a name="parameters"></a>Parametreler

*Rel_time*\
Bir zaman hatası: yöntemin sahipliğini almaya çalıştığı maksimum süreyi belirten [:d uration](../standard-library/duration-class.md) nesnesi `mutex` .

### <a name="return-value"></a>Dönüş Değeri

**`true`** Yöntemi ' nin sahipliğini başarıyla alırsa `mutex` veya çağıran iş parçacığı öğesine zaten sahipse `mutex` ; Aksi takdirde, **`false`** .

### <a name="remarks"></a>Açıklamalar

Çağıran iş parçacığı öğesine zaten sahipse `mutex` , yöntemi hemen döner **`true`** ve önceki kilit etkin kalır.

## <a name="try_lock_until"></a><a name="try_lock_until"></a> try_lock_until

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

**`true`** Yöntemi ' nin sahipliğini başarıyla alırsa `mutex` veya çağıran iş parçacığı öğesine zaten sahipse `mutex` ; Aksi takdirde, **`false`** .

### <a name="remarks"></a>Açıklamalar

Çağıran iş parçacığı öğesine zaten sahipse `mutex` , yöntemi hemen döner **`true`** ve önceki kilit etkin kalır.

## <a name="unlock"></a><a name="unlock"></a> kaldırın

Öğesinin sahipliğini yayınlar `mutex` .

```cpp
void unlock();
```

### <a name="remarks"></a>Açıklamalar

Bu yöntem, `mutex` nesne üzerinde [kilit](#lock), [try_lock](#try_lock), [try_lock_for](#try_lock_for)ve [try_lock_until](#try_lock_until) başarıyla çağrıldıkça, yalnızca öğesinin sahipliğini bir kez bırakır `recursive_timed_mutex` .

Çağıran iş parçacığı öğesine sahip değilse `mutex` , davranış tanımsızdır.

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)\
[\<mutex>](../standard-library/mutex.md)
