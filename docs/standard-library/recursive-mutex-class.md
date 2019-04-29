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
ms.openlocfilehash: 8be17c8ab361272678c25326464261e153da6a49
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62369650"
---
# <a name="recursivemutex-class"></a>recursive_mutex Sınıfı

Temsil eden bir *mutex türünü*. Tersine [mutex](../standard-library/mutex-class-stl.md), zaten kilitli olan nesneler için kilitleme yöntemlere yapılan çağrılar, davranışı iyi tanımlanmış olur.

## <a name="syntax"></a>Sözdizimi

```cpp
class recursive_mutex;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[recursive_mutex](#recursive_mutex)|Oluşturur bir `recursive_mutex` nesne.|
|[~recursive_mutex Destructor](#dtorrecursive_mutex_destructor)|Tarafından kullanılan kaynakları serbest `recursive_mutex` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[lock](#lock)|İş parçacığı mutex sahipliğini alana kadar çağıran iş parçacığını engeller.|
|[try_lock](#try_lock)|Engelleme olmadan mutex sahipliğini almayı dener.|
|[Kilit açma](#unlock)|Mutex sahipliğini serbest bırakır.|

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

## <a name="recursive_mutex"></a>  recursive_mutex

Oluşturur bir `recursive_mutex` kilitli olmayan bir nesne.

```cpp
recursive_mutex();
```

## <a name="dtorrecursive_mutex_destructor"></a>  ~ recursive_mutex

Nesne tarafından kullanılan tüm kaynakları serbest bırakır.

```cpp
~recursive_mutex();
```

### <a name="remarks"></a>Açıklamalar

Yıkıcı çalıştığında nesne kilitli değilse davranış tanımlanmamıştır.

## <a name="try_lock"></a>  try_lock

Sahipliğini almayı dener `mutex` engelleme olmadan.

```cpp
bool try_lock() noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

**doğru** yöntemi başarıyla sahipliğini elde ederse `mutex` veya çağıran iş parçacığı zaten sahipse `mutex**; otherwise, **false`.

### <a name="remarks"></a>Açıklamalar

Çağıran iş parçacığı zaten sahipse `mutex`, işlevi hemen döndürür **true**, ve önceki kilidi yürürlükte kalır.

## <a name="unlock"></a>  Kilit açma

Mutex sahipliğini serbest bırakır.

```cpp
void unlock();
```

### <a name="remarks"></a>Açıklamalar

Bu yöntem sahipliğini serbest `mutex` yalnızca olarak sayıda çağrıldıktan sonra [kilit](#lock) ve [try_lock](#try_lock) üzerinde başarıyla çağrılmışsa `recursive_mutex` nesne.

Çağıran iş parçacığına ait olmayan, `mutex`, davranış tanımlanmamıştır.

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)<br/>
[\<Mutex >](../standard-library/mutex.md)<br/>
