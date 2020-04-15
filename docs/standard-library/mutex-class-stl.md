---
title: mutex Sınıfı (C++ Standart Kitaplık)| Microsoft Dokümanlar
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
ms.openlocfilehash: 84e6e3a46903a204444df9886556ae2c563304a9
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364839"
---
# <a name="mutex-class-c-standard-library"></a>mutex Sınıfı (C++ Standart Kitaplığı)

*Mutex türünü*temsil eder. Bu tür nesneler, bir program içinde karşılıklı dışlama zorlamak için kullanılabilir.

## <a name="syntax"></a>Sözdizimi

```cpp
class mutex;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[Mutex](#mutex)|Bir `mutex` nesne inşa eder.|
|[mutex::~mutex Destructor](#dtormutex_destructor)|`mutex` Nesne tarafından kullanılan tüm kaynakları salar.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[Kilit](#lock)|İş `mutex`parçacığı.|
|[native_handle](#native_handle)|Mutex tutamacını temsil eden uygulamaya özgü türü döndürür.|
|[try_lock](#try_lock)|`mutex` Engellemeden sahipliğini elde etmeye çalışır.|
|[Kilidini](#unlock)|`mutex`Sahiplik serbest bırakır.|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** \<mutex>

**Ad alanı:** std

## <a name="mutexlock"></a><a name="lock"></a>mutex::kilit

İş `mutex`parçacığı.

```cpp
void lock();
```

### <a name="remarks"></a>Açıklamalar

Arama iş parçacığı zaten `mutex`sahibi ise, davranış tanımsız.

## <a name="mutexmutex-constructor"></a><a name="mutex"></a>mutex::mutex Yapıcı

Kilitli olmayan `mutex` bir nesne inşa eder.

```cpp
constexpr mutex() noexcept;
```

## <a name="mutexmutex-destructor"></a><a name="dtormutex_destructor"></a>mutex::~mutex Destructor

`mutex` Nesne tarafından kullanılan tüm kaynakları salgılar.

```cpp
~mutex();
```

### <a name="remarks"></a>Açıklamalar

Yıkıcı çalıştığında nesne kilitlenirse, davranış tanımsız kalır.

## <a name="mutexnative_handle"></a><a name="native_handle"></a>mutex::native_handle

Mutex tutamacını temsil eden uygulamaya özgü türü döndürür. Mutex kolu uygulamaya özgü yollarla kullanılabilir.

```cpp
native_handle_type native_handle();
```

### <a name="return-value"></a>Dönüş Değeri

`native_handle_type`olarak kullanılan `Concurrency::critical_section *` bir oyuncu olarak `void *`tanımlanır.

## <a name="mutextry_lock"></a><a name="try_lock"></a>mutex::try_lock

`mutex` Engellemeden sahipliğini elde etmeye çalışır.

```cpp
bool try_lock();
```

### <a name="return-value"></a>Dönüş Değeri

yöntem başarıyla sahiplik elde ederse `mutex` **doğrudur;** aksi takdirde, **yanlış**.

### <a name="remarks"></a>Açıklamalar

Arama iş parçacığı zaten `mutex`sahibi ise, davranış tanımsız.

## <a name="mutexunlock"></a><a name="unlock"></a>mutex::kilidini açmak

`mutex`Sahiplik serbest bırakır.

```cpp
void unlock();
```

### <a name="remarks"></a>Açıklamalar

Arama iş parçacığı, davranış `mutex`tanımsız sahibi değilse.

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi Dosyaları Başvurusu](../standard-library/cpp-standard-library-header-files.md)\
[\<mutex>](../standard-library/mutex.md)
