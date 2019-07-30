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
ms.openlocfilehash: 448b4d03e4d38dc45621cddab7d8f5d03b805968
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68451677"
---
# <a name="recursivemutex-class"></a>recursive_mutex Sınıfı

Bir *mutex türünü*temsil eder. [Mutex](../standard-library/mutex-class-stl.md)'in aksine, zaten kilitli olan nesnelerin kilitleme yöntemlerine yapılan çağrıların iyi tanımlanmış olması önerilir.

## <a name="syntax"></a>Sözdizimi

```cpp
class recursive_mutex;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[recursive_mutex](#recursive_mutex)|Bir `recursive_mutex` nesnesi oluşturur.|
|[~recursive_mutex Destructor](#dtorrecursive_mutex_destructor)|`recursive_mutex` Nesnesi tarafından kullanılan tüm kaynakları serbest bırakır.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[lock](#lock)|İş parçacığı mutex sahipliğini edinene kadar çağıran iş parçacığını engeller.|
|[try_lock](#try_lock)|Mutex 'in sahipliğini engelleme olmadan almaya çalışır.|
|[kaldırın](#unlock)|Mutex 'in sahipliğini yayınlar.|

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

## <a name="recursive_mutex"></a>recursive_mutex

Kilitli olmayan `recursive_mutex` bir nesne oluşturur.

```cpp
recursive_mutex();
```

## <a name="dtorrecursive_mutex_destructor"></a>~ recursive_mutex

Nesnesi tarafından kullanılan tüm kaynakları serbest bırakır.

```cpp
~recursive_mutex();
```

### <a name="remarks"></a>Açıklamalar

Yıkıcı çalıştırıldığında nesne kilitliyse, davranış tanımsızdır.

## <a name="try_lock"></a>try_lock

`mutex` Engellemeden sahipliğini almaya çalışır.

```cpp
bool try_lock() noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

yöntemi, çağıran `mutex` iş parçacığı öğesine zaten sahip olan veya ' nin sahipliğini başarıyla alırsa true. `mutex**; otherwise, **false`

### <a name="remarks"></a>Açıklamalar

Çağıran iş parçacığı öğesine zaten sahipse `mutex`, işlev hemen **true**değerini döndürür ve önceki kilit etkin kalır.

## <a name="unlock"></a>kaldırın

Mutex 'in sahipliğini yayınlar.

```cpp
void unlock();
```

### <a name="remarks"></a>Açıklamalar

Bu yöntem, ' nin sahipliğini `mutex` , `recursive_mutex` nesne üzerinde [Lock](#lock) ve [try_lock](#try_lock) başarıyla çağrıldığı kadar çok kez çağrıldıktan sonra bırakır.

Çağıran iş parçacığı öğesine sahip `mutex`değilse, davranış tanımsızdır.

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)\
[\<mutex >](../standard-library/mutex.md)
