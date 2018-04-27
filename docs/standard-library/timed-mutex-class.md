---
title: timed_mutex sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
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
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
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
ms.openlocfilehash: 4246a9f6413d016dabbde53e5a41067cc6839233
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="timedmutex-class"></a>timed_mutex Sınıfı

Temsil eden bir *mutex türü zaman aşımına*. Bu tür nesneler, zaman sınırlı bir program içinden engelleme yoluyla karşılıklı dışlama zorlamak için kullanılır.

## <a name="syntax"></a>Sözdizimi

```cpp
class timed_mutex;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[timed_mutex](#timed_mutex)|Oluşturan bir `timed_mutex` nesnesi kilitli değil.|
|[timed_mutex:: ~ timed_mutex yıkıcısı](#dtortimed_mutex_destructor)|Tarafından kullanılan tüm kaynakları serbest `timed_mutex` nesnesi.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[lock](#lock)|İş parçacığı sahipliğini alıncaya kadar çağıran iş parçacığı engeller `mutex`.|
|[try_lock](#try_lock)|Sahipliğini almayı denediğinde `mutex` engelleme olmadan.|
|[try_lock_for](#try_lock_for)|Sahipliğini almayı denediğinde `mutex` belirtilen zaman aralığı.|
|[try_lock_until](#try_lock_until)|Sahipliğini almayı denediğinde `mutex` belirtilen süre kadar.|
|[kilidini aç](#unlock)|Serbest sahipliğini `mutex`.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<mutex >

**Namespace:** std

## <a name="lock"></a>  timed_mutex::LOCK

İş parçacığı sahipliğini alıncaya kadar çağıran iş parçacığı engeller `mutex`.

```cpp
void lock();
```

### <a name="remarks"></a>Açıklamalar

Çağıran iş parçacığı zaten sahipse `mutex`, tanımlanmamış bir davranıştır.

## <a name="timed_mutex"></a>  timed_mutex::timed_mutex Oluşturucusu

Oluşturan bir `timed_mutex` nesnesi kilitli değil.

```cpp
timed_mutex();
```

## <a name="dtortimed_mutex_destructor"></a>  timed_mutex:: ~ timed_mutex yıkıcısı

Tarafından kullanılan tüm kaynakları serbest `mutex` nesnesi.

```cpp
~timed_mutex();
```

### <a name="remarks"></a>Açıklamalar

Yok Edicisi çalıştığında nesne kilitliyse tanımlanmamış bir davranıştır.

## <a name="try_lock"></a>  timed_mutex::try_lock

Sahipliğini almayı denediğinde `mutex` engelleme olmadan.

```cpp
bool try_lock();
```

### <a name="return-value"></a>Dönüş Değeri

`true` Yöntem başarıyla sahipliğini elde ederse `mutex`; Aksi halde, `false`.

### <a name="remarks"></a>Açıklamalar

Çağıran iş parçacığı zaten sahipse `mutex`, tanımlanmamış bir davranıştır.

## <a name="try_lock_for"></a>  timed_mutex::try_lock_for

Sahipliğini almayı denediğinde `mutex` engelleme olmadan.

```cpp
template <class Rep, class Period>
bool try_lock_for(const chrono::duration<Rep, Period>& Rel_time);
```

### <a name="parameters"></a>Parametreler

`Rel_time` A [chrono::duration](../standard-library/duration-class.md) yöntemi sahipliğini almayı denediğinde en uzun süreyi belirtir nesne `mutex`.

### <a name="return-value"></a>Dönüş Değeri

`true` Yöntem başarıyla sahipliğini elde ederse `mutex`; Aksi halde, `false`.

### <a name="remarks"></a>Açıklamalar

Çağıran iş parçacığı zaten sahipse `mutex`, tanımlanmamış bir davranıştır.

## <a name="try_lock_until"></a>  timed_mutex::try_lock_until

Sahipliğini almayı denediğinde `mutex` engelleme olmadan.

```cpp
template <class Clock, class Duration>
bool try_lock_for(const chrono::time_point<Clock, Duration>& Abs_time);

bool try_lock_until(const xtime* Abs_time);
```

### <a name="parameters"></a>Parametreler

`Abs_time` Daha sonra yöntemi artık çalışır sahipliğini almak eşik belirtir zaman içinde nokta `mutex`.

### <a name="return-value"></a>Dönüş Değeri

`true` Yöntem başarıyla sahipliğini elde ederse `mutex`; Aksi halde, `false`.

### <a name="remarks"></a>Açıklamalar

Çağıran iş parçacığı zaten sahipse `mutex`, tanımlanmamış bir davranıştır.

## <a name="unlock"></a>  timed_mutex::unlock

Serbest sahipliğini `mutex`.

```cpp
void unlock();
```

### <a name="remarks"></a>Açıklamalar

Çağıran iş parçacığı kendi değil, `mutex`, tanımlanmamış bir davranıştır.

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)<br/>
[\<Mutex >](../standard-library/mutex.md)<br/>
