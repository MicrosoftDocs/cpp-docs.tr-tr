---
description: 'Daha fazla bilgi edinin: mutex sınıfı (C++ Standart Kitaplığı)'
title: Mutex sınıfı (C++ Standart Kitaplığı) | Microsoft Docs
ms.date: 11/04/2016
f1_keywords:
- mutex/std::mutex
- mutex/std::mutex::mutex
- mutex/std::mutex::lock
- mutex/std::mutex::native_handle
- mutex/std::mutex::try_lock
- mutex/std::mutex::unlock
ms.assetid: 7999d055-f74f-4303-810f-8d3c9cde2f69
helpviewer_keywords:
- std::mutex [C++]
- std::mutex [C++], mutex
- std::mutex [C++], lock
- std::mutex [C++], native_handle
- std::mutex [C++], try_lock
- std::mutex [C++], unlock
ms.openlocfilehash: 528fe0698fb7815be9b678d72055c54bad5ce2bd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97338280"
---
# <a name="mutex-class-c-standard-library"></a>Mutex sınıfı (C++ Standart Kitaplığı)

Bir *mutex türünü* temsil eder. Bu türden nesneler, bir program içinde karşılıklı dışlamayı zorlamak için kullanılabilir.

## <a name="syntax"></a>Syntax

```cpp
class mutex;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[mutex](#mutex)|Bir `mutex` nesnesi oluşturur.|
|[mutex:: ~ mutex yıkıcısı](#dtormutex_destructor)|Nesnesi tarafından kullanılan tüm kaynakları serbest bırakır `mutex` .|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[ine](#lock)|İş parçacığı sahipliğini alıncaya kadar çağıran iş parçacığını engeller `mutex` .|
|[native_handle](#native_handle)|Mutex tanıtıcısını temsil eden uygulamaya özel türü döndürür.|
|[try_lock](#try_lock)|Engellemeden sahipliğini almaya çalışır `mutex` .|
|[kaldırın](#unlock)|Öğesinin sahipliğini yayınlar `mutex` .|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<mutex>

**Ad alanı:** std

## <a name="mutexlock"></a><a name="lock"></a> mutex:: Lock

İş parçacığı sahipliğini alıncaya kadar çağıran iş parçacığını engeller `mutex` .

```cpp
void lock();
```

### <a name="remarks"></a>Açıklamalar

Çağıran iş parçacığı öğesine zaten sahipse `mutex` , davranış tanımsızdır.

## <a name="mutexmutex-constructor"></a><a name="mutex"></a> mutex:: mutex Oluşturucusu

`mutex`Kilitli olmayan bir nesne oluşturur.

```cpp
constexpr mutex() noexcept;
```

## <a name="mutexmutex-destructor"></a><a name="dtormutex_destructor"></a> mutex:: ~ mutex yıkıcısı

Nesnesi tarafından kullanılan tüm kaynakları serbest bırakır `mutex` .

```cpp
~mutex();
```

### <a name="remarks"></a>Açıklamalar

Yıkıcı çalıştırıldığında nesne kilitliyse, davranış tanımsızdır.

## <a name="mutexnative_handle"></a><a name="native_handle"></a> mutex:: native_handle

Mutex tanıtıcısını temsil eden uygulamaya özel türü döndürür. Mutex tanıtıcısı, uygulamaya özgü yollarla kullanılabilir.

```cpp
native_handle_type native_handle();
```

### <a name="return-value"></a>Dönüş Değeri

`native_handle_type` , `Concurrency::critical_section *` olarak cast olarak tanımlanır `void *` .

## <a name="mutextry_lock"></a><a name="try_lock"></a> mutex:: try_lock

Engellemeden sahipliğini almaya çalışır `mutex` .

```cpp
bool try_lock();
```

### <a name="return-value"></a>Dönüş Değeri

**`true`** Yöntemi öğesinin sahipliğini başarıyla alırsa `mutex` ; Aksi takdirde, **`false`** .

### <a name="remarks"></a>Açıklamalar

Çağıran iş parçacığı öğesine zaten sahipse `mutex` , davranış tanımsızdır.

## <a name="mutexunlock"></a><a name="unlock"></a> mutex:: unlock

Öğesinin sahipliğini yayınlar `mutex` .

```cpp
void unlock();
```

### <a name="remarks"></a>Açıklamalar

Çağıran iş parçacığı öğesine sahip değilse `mutex` , davranış tanımsızdır.

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)\
[\<mutex>](../standard-library/mutex.md)
