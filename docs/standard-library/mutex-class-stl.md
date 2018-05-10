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
ms.openlocfilehash: 23e7220d2710465dc8d155cf35ec7d47db4e3c08
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
---
# <a name="mutex-class-c-standard-library"></a>Mutex sınıfı (Standart C++ Kitaplığı)

Temsil eden bir *mutex türü*. Bu tür nesneler bir programdan karşılıklı dışlama zorlamak için kullanılabilir.

## <a name="syntax"></a>Sözdizimi

```cpp
class mutex;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[Mutex](#mutex)|Oluşturan bir `mutex` nesnesi.|
|[Mutex:: ~ mutex yok Edicisi](#dtormutex_destructor)|Tarafından kullanılan tüm kaynakları serbest `mutex` nesnesi.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[lock](#lock)|İş parçacığı sahipliğini alıncaya kadar çağıran iş parçacığı engeller `mutex`.|
|[native_handle](#native_handle)|Mutex tanıtıcı temsil eden uygulamaya özel tür döndürür.|
|[try_lock](#try_lock)|Sahipliğini almayı denediğinde `mutex` engelleme olmadan.|
|[kilidini aç](#unlock)|Serbest sahipliğini `mutex`.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<mutex >

**Namespace:** std

## <a name="lock"></a>  Mutex::LOCK

İş parçacığı sahipliğini alıncaya kadar çağıran iş parçacığı engeller `mutex`.

```cpp
void lock();
```

### <a name="remarks"></a>Açıklamalar

Çağıran iş parçacığı zaten sahipse `mutex`, tanımlanmamış bir davranıştır.

## <a name="mutex"></a>  Mutex::mutex Oluşturucusu

Oluşturan bir `mutex` nesnesi kilitli değil.

```cpp
constexpr mutex() noexcept;
```

## <a name="dtormutex_destructor"></a>  Mutex:: ~ mutex yok Edicisi

Tarafından kullanılan tüm kaynakları serbest `mutex` nesnesi.

```cpp
~mutex();
```

### <a name="remarks"></a>Açıklamalar

Yok Edicisi çalıştığında nesne kilitliyse tanımlanmamış bir davranıştır.

## <a name="native_handle"></a>  Mutex::native_handle

Mutex tanıtıcı temsil eden uygulamaya özel tür döndürür. Mutex tanıtıcı uygulamaya özel yollarla kullanılabilir.

```cpp
native_handle_type native_handle();
```

### <a name="return-value"></a>Dönüş Değeri

`native_handle_type` olarak tanımlanan bir `Concurrency::critical_section *` olarak cast `void *`.

## <a name="try_lock"></a>  Mutex::try_lock

Sahipliğini almayı denediğinde `mutex` engelleme olmadan.

```cpp
bool try_lock();
```

### <a name="return-value"></a>Dönüş Değeri

`true` Yöntem başarıyla sahipliğini elde ederse `mutex`; Aksi halde, `false`.

### <a name="remarks"></a>Açıklamalar

Çağıran iş parçacığı zaten sahipse `mutex`, tanımlanmamış bir davranıştır.

## <a name="unlock"></a>  Mutex::Unlock

Serbest sahipliğini `mutex`.

```cpp
void unlock();
```

### <a name="remarks"></a>Açıklamalar

Çağıran iş parçacığı kendi değil, `mutex`, tanımlanmamış bir davranıştır.

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)<br/>
[\<Mutex >](../standard-library/mutex.md)<br/>
