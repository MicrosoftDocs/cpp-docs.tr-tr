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
ms.openlocfilehash: 8455548997c4ccf1b950e26e01df67306554b945
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87217616"
---
# <a name="recursive_mutex-class"></a>recursive_mutex Sınıfı

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
|[~ recursive_mutex yok edici](#dtorrecursive_mutex_destructor)|Nesnesi tarafından kullanılan tüm kaynakları serbest bırakır `recursive_mutex` .|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[ine](#lock)|İş parçacığı mutex sahipliğini edinene kadar çağıran iş parçacığını engeller.|
|[try_lock](#try_lock)|Mutex 'in sahipliğini engelleme olmadan almaya çalışır.|
|[kaldırın](#unlock)|Mutex 'in sahipliğini yayınlar.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<mutex>

**Ad alanı:** std

## <a name="lock"></a><a name="lock"></a>ine

İş parçacığı sahipliğini alıncaya kadar çağıran iş parçacığını engeller `mutex` .

```cpp
void lock();
```

### <a name="remarks"></a>Açıklamalar

Çağıran iş parçacığı öğesine zaten sahipse `mutex` , yöntemi hemen döndürür ve önceki kilit etkin kalır.

## <a name="recursive_mutex"></a><a name="recursive_mutex"></a>recursive_mutex

`recursive_mutex`Kilitli olmayan bir nesne oluşturur.

```cpp
recursive_mutex();
```

## <a name="recursive_mutex"></a><a name="dtorrecursive_mutex_destructor"></a>~ recursive_mutex

Nesnesi tarafından kullanılan tüm kaynakları serbest bırakır.

```cpp
~recursive_mutex();
```

### <a name="remarks"></a>Açıklamalar

Yıkıcı çalıştırıldığında nesne kilitliyse, davranış tanımsızdır.

## <a name="try_lock"></a><a name="try_lock"></a>try_lock

Engellemeden sahipliğini almaya çalışır `mutex` .

```cpp
bool try_lock() noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

**`true`** Yöntemi ' nin sahipliğini başarıyla alırsa, `mutex` çağıran iş parçacığı öğesine zaten sahip olur `mutex**; otherwise, **false` .

### <a name="remarks"></a>Açıklamalar

Çağıran iş parçacığı öğesine zaten sahipse `mutex` , işlev hemen döner **`true`** ve önceki kilit etkin kalır.

## <a name="unlock"></a><a name="unlock"></a>kaldırın

Mutex 'in sahipliğini yayınlar.

```cpp
void unlock();
```

### <a name="remarks"></a>Açıklamalar

Bu yöntem, ' nin sahipliğini `mutex` yalnızca [kilit](#lock) olarak çağrılır ve [try_lock](#try_lock) nesne üzerinde başarıyla çağrıldıktan sonra bırakır `recursive_mutex` .

Çağıran iş parçacığı öğesine sahip değilse `mutex` , davranış tanımsızdır.

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)\
[\<mutex>](../standard-library/mutex.md)
