---
title: recursive_mutex Sınıfı
ms.date: 11/04/2016
f1_keywords:
- mutex/std::recursive_mutex
- mutex/std::recursive_mutex::recursive_mutex
- mutex/std::recursive_mutex::lock
- mutex/std::recursive_mutex::try_lock
- mutex/std::recursive_mutex::unlock
ms.assetid: eb5ffd1b-7e78-4559-8391-bb220ead42fc
helpviewer_keywords:
- std::recursive_mutex [C++]
- std::recursive_mutex [C++], recursive_mutex
- std::recursive_mutex [C++], lock
- std::recursive_mutex [C++], try_lock
- std::recursive_mutex [C++], unlock
ms.openlocfilehash: 9ab7a96a7c07582450ab41b140dcc5494a63661f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81320200"
---
# <a name="recursive_mutex-class"></a>recursive_mutex Sınıfı

*Mutex türünü*temsil eder. [Mutex](../standard-library/mutex-class-stl.md)aksine, zaten kilitli nesneler için kilitleme yöntemleri çağrıları davranışı iyi tanımlanmıştır.

## <a name="syntax"></a>Sözdizimi

```cpp
class recursive_mutex;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[recursive_mutex](#recursive_mutex)|Bir `recursive_mutex` nesne inşa eder.|
|[~recursive_mutex Yıkıcı](#dtorrecursive_mutex_destructor)|`recursive_mutex` Nesne tarafından kullanılan tüm kaynakları salgılar.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[Kilit](#lock)|İş parçacığı mutex sahipliğini elde edene kadar arama iş parçacığı engeller.|
|[try_lock](#try_lock)|Engellemeden mutex sahipliğini elde etmeye çalışır.|
|[Kilidini](#unlock)|Mutex'in sahipliğini serbest bırakır.|

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

## <a name="recursive_mutex"></a><a name="recursive_mutex"></a>recursive_mutex

Kilitli olmayan `recursive_mutex` bir nesne inşa eder.

```cpp
recursive_mutex();
```

## <a name="recursive_mutex"></a><a name="dtorrecursive_mutex_destructor"></a>~recursive_mutex

Nesne tarafından kullanılan tüm kaynakları salgılar.

```cpp
~recursive_mutex();
```

### <a name="remarks"></a>Açıklamalar

Yıkıcı çalıştığında nesne kilitlenirse, davranış tanımsız kalır.

## <a name="try_lock"></a><a name="try_lock"></a>try_lock

`mutex` Engellemeden sahipliğini elde etmeye çalışır.

```cpp
bool try_lock() noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

yöntem başarıyla sahiplik `mutex` elde veya arama iş parçacığı zaten `mutex**; otherwise, **false`sahip sayılsa **doğru .**

### <a name="remarks"></a>Açıklamalar

Arama iş parçacığı zaten `mutex`sahibi ise , işlev hemen **doğru**döndürür , ve önceki kilit etkin kalır.

## <a name="unlock"></a><a name="unlock"></a>Kilidini

Mutex'in sahipliğini serbest bırakır.

```cpp
void unlock();
```

### <a name="remarks"></a>Açıklamalar

Bu yöntem, yalnızca `mutex` [kilit](#lock) ve [try_lock](#try_lock) nesne üzerinde `recursive_mutex` başarıyla çağrıldıktan sonra sahiplik serbest bırakır.

Arama iş parçacığı, davranış `mutex`tanımsız sahibi değilse.

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi Dosyaları Başvurusu](../standard-library/cpp-standard-library-header-files.md)\
[\<mutex>](../standard-library/mutex.md)
