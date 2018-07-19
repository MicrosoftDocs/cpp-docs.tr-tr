---
title: Mutex sınıfı (Standart C++ Kitaplığı) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- mutex/std::mutex
- mutex/std::mutex::mutex
- mutex/std::mutex::lock
- mutex/std::mutex::native_handle
- mutex/std::mutex::try_lock
- mutex/std::mutex::unlock
dev_langs:
- C++
ms.assetid: 7999d055-f74f-4303-810f-8d3c9cde2f69
author: corob-msft
ms.author: corob
helpviewer_keywords:
- std::mutex [C++]
- std::mutex [C++], mutex
- std::mutex [C++], lock
- std::mutex [C++], native_handle
- std::mutex [C++], try_lock
- std::mutex [C++], unlock
ms.workload:
- cplusplus
ms.openlocfilehash: 84a6b685501927d9fbd79fa7c82a90c5671f70b2
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38958952"
---
# <a name="mutex-class-c-standard-library"></a>Mutex sınıfı (Standart C++ Kitaplığı)

Temsil eden bir *mutex türünü*. Bu tür nesneler bir programın içinde karşılıklı dışlamayı zorlamak için kullanılabilir.

## <a name="syntax"></a>Sözdizimi

```cpp
class mutex;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[Mutex](#mutex)|Oluşturur bir `mutex` nesne.|
|[Mutex:: ~ mutex yıkıcısı](#dtormutex_destructor)|Tarafından kullanılan kaynakları serbest `mutex` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[lock](#lock)|İş parçacığı sahipliğini alana kadar çağıran iş parçacığını engeller `mutex`.|
|[native_handle](#native_handle)|Mutex tanıtıcısını temsil eden uygulamaya özel türü döndürür.|
|[try_lock](#try_lock)|Sahipliğini almayı dener `mutex` engelleme olmadan.|
|[Kilit açma](#unlock)|İn sahipliğini bırakır `mutex`.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<mutex >

**Namespace:** std

## <a name="lock"></a>  Mutex::LOCK

İş parçacığı sahipliğini alana kadar çağıran iş parçacığını engeller `mutex`.

```cpp
void lock();
```

### <a name="remarks"></a>Açıklamalar

Çağıran iş parçacığı zaten sahipse `mutex`, davranış tanımlanmamıştır.

## <a name="mutex"></a>  Mutex::mutex Oluşturucusu

Oluşturur bir `mutex` kilitli olmayan bir nesne.

```cpp
constexpr mutex() noexcept;
```

## <a name="dtormutex_destructor"></a>  Mutex:: ~ mutex yıkıcısı

Tarafından kullanılan kaynakları serbest `mutex` nesne.

```cpp
~mutex();
```

### <a name="remarks"></a>Açıklamalar

Yıkıcı çalıştığında nesne kilitli değilse davranış tanımlanmamıştır.

## <a name="native_handle"></a>  Mutex::native_handle

Mutex tanıtıcısını temsil eden uygulamaya özel türü döndürür. Mutex tanıtıcısını uygulamaya özel şekillerde kullanılabilir.

```cpp
native_handle_type native_handle();
```

### <a name="return-value"></a>Dönüş Değeri

`native_handle_type` olarak tanımlanan bir `Concurrency::critical_section *` olarak cast `void *`.

## <a name="try_lock"></a>  Mutex::try_lock

Sahipliğini almayı dener `mutex` engelleme olmadan.

```cpp
bool try_lock();
```

### <a name="return-value"></a>Dönüş Değeri

**doğru** yöntemi başarıyla sahipliğini elde ederse `mutex`; Aksi takdirde **false**.

### <a name="remarks"></a>Açıklamalar

Çağıran iş parçacığı zaten sahipse `mutex`, davranış tanımlanmamıştır.

## <a name="unlock"></a>  Mutex::Unlock

İn sahipliğini bırakır `mutex`.

```cpp
void unlock();
```

### <a name="remarks"></a>Açıklamalar

Çağıran iş parçacığına ait olmayan, `mutex`, davranış tanımlanmamıştır.

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)<br/>
[\<Mutex >](../standard-library/mutex.md)<br/>
