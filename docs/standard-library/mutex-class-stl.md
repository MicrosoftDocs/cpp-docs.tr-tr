---
title: Mutex sınıfı (C++ standart kitaplık) | Microsoft Docs
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
ms.openlocfilehash: 099cf17db7b99f9cd1d953a603db70f75c33358e
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68457063"
---
# <a name="mutex-class-c-standard-library"></a>Mutex sınıfı (C++ standart kitaplık)

Bir *mutex türünü*temsil eder. Bu türden nesneler, bir program içinde karşılıklı dışlamayı zorlamak için kullanılabilir.

## <a name="syntax"></a>Sözdizimi

```cpp
class mutex;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[mutex](#mutex)|Bir `mutex` nesnesi oluşturur.|
|[mutex:: ~ mutex yıkıcısı](#dtormutex_destructor)|`mutex` Nesnesi tarafından kullanılan tüm kaynakları serbest bırakır.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[lock](#lock)|İş parçacığı sahipliğini `mutex`alıncaya kadar çağıran iş parçacığını engeller.|
|[native_handle](#native_handle)|Mutex tanıtıcısını temsil eden uygulamaya özel türü döndürür.|
|[try_lock](#try_lock)|`mutex` Engellemeden sahipliğini almaya çalışır.|
|[kaldırın](#unlock)|Öğesinin sahipliğini yayınlar `mutex`.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<mutex >

**Ad alanı:** std

## <a name="lock"></a>mutex:: Lock

İş parçacığı sahipliğini `mutex`alıncaya kadar çağıran iş parçacığını engeller.

```cpp
void lock();
```

### <a name="remarks"></a>Açıklamalar

Çağıran iş parçacığı öğesine zaten sahipse `mutex`, davranış tanımsızdır.

## <a name="mutex"></a>mutex:: mutex Oluşturucusu

Kilitli olmayan `mutex` bir nesne oluşturur.

```cpp
constexpr mutex() noexcept;
```

## <a name="dtormutex_destructor"></a>mutex:: ~ mutex yıkıcısı

`mutex` Nesnesi tarafından kullanılan tüm kaynakları serbest bırakır.

```cpp
~mutex();
```

### <a name="remarks"></a>Açıklamalar

Yıkıcı çalıştırıldığında nesne kilitliyse, davranış tanımsızdır.

## <a name="native_handle"></a>mutex:: native_handle

Mutex tanıtıcısını temsil eden uygulamaya özel türü döndürür. Mutex tanıtıcısı, uygulamaya özgü yollarla kullanılabilir.

```cpp
native_handle_type native_handle();
```

### <a name="return-value"></a>Dönüş Değeri

`native_handle_type`, olarak `Concurrency::critical_section *` `void *`cast olarak tanımlanır.

## <a name="try_lock"></a>mutex:: try_lock

`mutex` Engellemeden sahipliğini almaya çalışır.

```cpp
bool try_lock();
```

### <a name="return-value"></a>Dönüş Değeri

Yöntem öğesinin `mutex`sahipliğini başarıyla alırsa doğru, aksi takdirde **yanlış**olur.

### <a name="remarks"></a>Açıklamalar

Çağıran iş parçacığı öğesine zaten sahipse `mutex`, davranış tanımsızdır.

## <a name="unlock"></a>mutex:: unlock

Öğesinin sahipliğini yayınlar `mutex`.

```cpp
void unlock();
```

### <a name="remarks"></a>Açıklamalar

Çağıran iş parçacığı öğesine sahip `mutex`değilse, davranış tanımsızdır.

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)\
[\<mutex >](../standard-library/mutex.md)
