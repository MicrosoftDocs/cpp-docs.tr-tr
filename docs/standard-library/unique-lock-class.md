---
title: unique_lock sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- mutex/std::unique_lock
dev_langs:
- C++
ms.assetid: f4ed8ba9-c8af-446f-8ef0-0b356bad14bd
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 313c2aca9d17b5fc75fcf8abddf19f354a99d976
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="uniquelock-class"></a>unique_lock Sınıfı

Kilitleme ve, kilidini açma yönetmek nesneleri oluşturmak için örneği bir şablon temsil eden bir `mutex`.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Mutex>
class unique_lock;
```

## <a name="remarks"></a>Açıklamalar

Şablon bağımsız değişken `Mutex` adı olmalıdır bir *mutex türü*.

Dahili olarak, bir `unique_lock` ilişkili bir işaretçi depolar `mutex` nesne ve `bool` belirten geçerli iş parçacığına sahip olup olmadığını `mutex`.

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Genel tür tanımları

|Ad|Açıklama|
|----------|-----------------|
|`mutex_type`|Şablon bağımsız değişken için eş anlamlı `Mutex`.|

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[unique_lock](#unique_lock)|Oluşturan bir `unique_lock` nesnesi.|
|[~ unique_lock yıkıcısı](#dtorunique_lock_destructor)|İle ilişkili tüm kaynakları serbest `unique_lock` nesnesi.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[lock](#lock)|İş parçacığı ilişkili sahipliğini alıncaya kadar çağıran iş parçacığı engeller `mutex`.|
|[Mutex](#mutex)|İlişkili saklı işaretçisine alır `mutex`.|
|[owns_lock](#owns_lock)|Çağıran iş parçacığı ilişkili sahip olup olmadığını belirtir `mutex`.|
|[Sürüm](#release)|Keser `unique_lock` ilişkili nesnesinden `mutex` nesnesi.|
|[Değiştirme](#swap)|İlişkili değiştirir `mutex` ve sahipliği durumu ile belirtilen bir nesne.|
|[try_lock](#try_lock)|İlişkili sahipliğini almaya çalıştığında `mutex` engelleme olmadan.|
|[try_lock_for](#try_lock_for)|İlişkili sahipliğini almaya çalıştığında `mutex` engelleme olmadan.|
|[try_lock_until](#try_lock_until)|İlişkili sahipliğini almaya çalıştığında `mutex` engelleme olmadan.|
|[kilidini aç](#unlock)|İlişkili sahipliğini serbest `mutex`.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[işleç bool değeri](#op_bool)|Çağıran iş parçacığı sahipliğini ilişkili olup olmadığını belirtir `mutex`.|
|[operator=](#op_eq)|Saklı kopyalar `mutex` işaretçi ve belirtilen bir nesneden ilişkili olma durumu.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`unique_lock`

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<mutex >

**Namespace:** std

## <a name="lock"></a>  kilitleme

İş parçacığı ilişkili sahipliğini alıncaya kadar çağıran iş parçacığı engeller `mutex`.

```cpp
void lock();
```

### <a name="remarks"></a>Açıklamalar

Durumunda depolanan `mutex` işaretçi `null`, bu yöntem oluşturulur bir [system_error](../standard-library/system-error-class.md) hata kodunu olan `operation_not_permitted`.

Çağıran iş parçacığı zaten ilişkili sahipse `mutex`, bu yöntem oluşturulur bir `system_error` hata kodunu olan `resource_deadlock_would_occur`.

Aksi takdirde, bu yöntemi çağırır `lock` ilişkili üzerinde `mutex` ve iç iş parçacığı sahipliği bayrağını ayarlar `true`.

## <a name="mutex"></a>  Mutex

İlişkili saklı işaretçisine alır `mutex`.

```cpp
mutex_type *mutex() const noexcept;
```

## <a name="op_bool"></a>  işleç bool değeri

Çağıran iş parçacığı ilişkili mutex sahipliğini sahip olup olmadığını belirtir.

```cpp
explicit operator bool() noexcept
```

### <a name="return-value"></a>Dönüş Değeri

`true` iş parçacığı mutex sahipse; Aksi takdirde `false`.

## <a name="op_eq"></a>  işleç =

Saklı kopyalar `mutex` işaretçi ve belirtilen bir nesneden ilişkili olma durumu.

```cpp
unique_lock& operator=(unique_lock&& Other) noexcept;
```

### <a name="parameters"></a>Parametreler

`Other` A `unique_lock` nesnesi.

### <a name="return-value"></a>Dönüş Değeri

`*this`

### <a name="remarks"></a>Açıklamalar

Çağıran iş parçacığı daha önce ilişkili sahipse `mutex`, bu yöntemi çağırmadan önce `unlock` üzerinde `mutex`, yeni değerleri atar.

Bu yöntem sonra kopyalama, ayarlar `Other` varsayılan oluşturulan bir duruma.

## <a name="owns_lock"></a>  owns_lock

Çağıran iş parçacığı ilişkili sahip olup olmadığını belirtir `mutex`.

```cpp
bool owns_lock() const noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

`true` iş parçacığı sahipse `mutex`; Aksi halde, `false`.

## <a name="release"></a>  Sürüm

Keser `unique_lock` ilişkili nesnesinden `mutex` nesnesi.

```cpp
mutex_type *release() noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

Önceki değeri saklı `mutex` işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu yöntem saklı değerini ayarlar `mutex` 0 ve kümelerini iç işaretçi `mutex` sahipliği bayrak `false`.

## <a name="swap"></a>  Değiştirme

İlişkili değiştirir `mutex` ve sahipliği durumu ile belirtilen bir nesne.

```cpp
void swap(unique_lock& Other) noexcept;
```

### <a name="parameters"></a>Parametreler

`Other` A `unique_lock` nesnesi.

## <a name="try_lock"></a>  try_lock

İlişkili sahipliğini almaya çalıştığında `mutex` engelleme olmadan.

```cpp
bool try_lock() noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

`true` Yöntem başarıyla sahipliğini elde ederse `mutex`; Aksi halde, `false`.

### <a name="remarks"></a>Açıklamalar

Varsa saklı `mutex` işaretçi `null`, yöntem oluşturulur bir [system_error](../standard-library/system-error-class.md) hata kodunu olan `operation_not_permitted`.

Çağıran iş parçacığı zaten sahipse `mutex`, yöntem oluşturulur bir `system_error` hata kodunu olan `resource_deadlock_would_occur`.

## <a name="try_lock_for"></a>  try_lock_for

İlişkili sahipliğini almaya çalıştığında `mutex` engelleme olmadan.

```cpp
template <class Rep, class Period>
bool try_lock_for(
    const chrono::duration<Rep, Period>& Rel_time);
```

### <a name="parameters"></a>Parametreler

`Rel_time` A [chrono::duration](../standard-library/duration-class.md) yöntemi sahipliğini almayı denediğinde en uzun süreyi belirtir nesne `mutex`.

### <a name="return-value"></a>Dönüş Değeri

`true` Yöntem başarıyla sahipliğini elde ederse `mutex`; Aksi halde, `false`.

### <a name="remarks"></a>Açıklamalar

Varsa saklı `mutex` işaretçi `null`, yöntem oluşturulur bir [system_error](../standard-library/system-error-class.md) hata kodunu olan `operation_not_permitted`.

Çağıran iş parçacığı zaten sahipse `mutex`, yöntem oluşturulur bir `system_error` hata kodunu olan `resource_deadlock_would_occur`.

## <a name="try_lock_until"></a>  try_lock_until

İlişkili sahipliğini almaya çalıştığında `mutex` engelleme olmadan.

```cpp
template <class Clock, class Duration>
bool try_lock_until(const chrono::time_point<Clock, Duration>& Abs_time);

bool try_lock_until(const xtime* Abs_time);
```

### <a name="parameters"></a>Parametreler

`Abs_time` Daha sonra yöntemi artık çalışır sahipliğini almak eşik belirtir zaman içinde nokta `mutex`.

### <a name="return-value"></a>Dönüş Değeri

`true` Yöntem başarıyla sahipliğini elde ederse `mutex`; Aksi halde, `false`.

### <a name="remarks"></a>Açıklamalar

Varsa saklı `mutex` işaretçi `null`, yöntem oluşturulur bir [system_error](../standard-library/system-error-class.md) hata kodunu olan `operation_not_permitted`.

Çağıran iş parçacığı zaten sahipse `mutex`, yöntem oluşturulur bir `system_error` hata kodunu olan `resource_deadlock_would_occur`.

## <a name="unique_lock"></a>  unique_lock Oluşturucusu

Oluşturan bir `unique_lock` nesnesi.

```cpp
unique_lock() noexcept;
unique_lock(unique_lock&& Other) noexcept;
explicit unique_lock(mutex_type& Mtx);

unique_lock(mutex_type& Mtx, adopt_lock_t Adopt);

unique_lock(mutex_type& Mtx, defer_lock_t Defer) noexcept;
unique_lock(mutex_type& Mtx, try_to_lock_t Try);

template <class Rep, class Period>
unique_lock(mutex_type& Mtx,
    const chrono::duration<Rep, Period>
Rel_time);

template <class Clock, class Duration>
unique_lock(mutex_type& Mtx,
    const chrono::time_point<Clock, Duration>
Abs_time);

unique_lock(mutex_type& Mtx,
    const xtime* Abs_time) noexcept;
```

### <a name="parameters"></a>Parametreler

`Mtx` Mutex türü nesnesi.

`Rel_time` A [chrono::duration](../standard-library/duration-class.md) yöntemi sahipliğini almayı denediğinde en uzun süreyi belirtir nesne `mutex`.

`Abs_time` Daha sonra yöntemi artık çalışır sahipliğini almak eşik belirtir zaman içinde nokta `mutex`.

`Other` A `unique_lock` nesnesi.

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucusu bir ilişkili mutex işaretçi değeri 0 olan bir nesne oluşturur.

İkinci oluşturucu ilişkili mutex durumundan taşır `Other`. Taşıma sonrasında `Other` artık mutex ile ilişkili değil.

Kalan oluşturucular deposu & `Mtx` saklanan `mutex` işaretçi. Sahipliğini `mutex` varsa ikinci bağımsız değişkeni tarafından belirlenir.

|||
|-|-|
|`No argument`|Sahipliği çağırarak elde edilir `lock` yöntemi ilişkili `mutex` nesnesi.|
|`Adopt`|Sahipliği varsayılır. `Mtx` Oluşturucu çağrıldığında kilitlenmiş olması gerekir.|
|`Defer`|Çağıran iş parçacığı için kendi varsayılır `mutex` nesnesi. `Mtx` Oluşturucu çağrıldığında kilitlenmesi gerekir değil.|
|`Try`|Sahipliği çağırarak belirlenir `try_lock` ilişkili üzerinde `mutex` nesnesi. Oluşturucusu hiçbir şey oluşturur.|
|`Rel_time`|Sahipliği çağırarak belirlenir `try_lock_for(Rel_time)`.|
|`Abs_time`|Sahipliği çağırarak belirlenir `try_lock_until(Abs_time)`.|

## <a name="dtorunique_lock_destructor"></a>  ~ unique_lock yıkıcısı

İle ilişkili tüm kaynakları serbest `unique_lock` nesnesi.

```cpp
~unique_lock() noexcept;
```

### <a name="remarks"></a>Açıklamalar

Çağıran iş parçacığı ilişkili sahipse `mutex`, çağırarak yıkıcı sürümleri sahipliği kilidini `mutex` nesnesi.

## <a name="unlock"></a>  kilidini aç

İlişkili sahipliğini serbest `mutex`.

```cpp
void unlock();
```

### <a name="remarks"></a>Açıklamalar

Çağıran iş parçacığı ilişkili olmayan sahipseniz `mutex`, bu yöntem oluşturulur bir [system_error](../standard-library/system-error-class.md) hata kodunu olan `operation_not_permitted`.

Aksi takdirde, bu yöntemi çağırır `unlock` ilişkili üzerinde `mutex` ve iç iş parçacığı sahipliği bayrağını ayarlar `false`.

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)<br/>
[\<Mutex >](../standard-library/mutex.md)<br/>
