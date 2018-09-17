---
title: unique_lock sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- mutex/std::unique_lock
dev_langs:
- C++
ms.assetid: f4ed8ba9-c8af-446f-8ef0-0b356bad14bd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 780ccdb7f16ed79ef8205c07e1390e778bc33ef5
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45711392"
---
# <a name="uniquelock-class"></a>unique_lock Sınıfı

Kilitleme ve, kilidini açma yönetme nesneleri oluşturmak için örneği bir şablonunu temsil eden bir `mutex`.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Mutex>
class unique_lock;
```

## <a name="remarks"></a>Açıklamalar

Şablon bağımsız değişkeni `Mutex` adlandırmalısınız bir *mutex türünü*.

Dahili olarak, bir `unique_lock` ilişkili bir yönelik bir işaretçi depolayan `mutex` nesnesi ve bir **bool** geçerli iş parçacığının sahip olup olmadığını bildiren `mutex`.

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Genel Typedefler

|Ad|Açıklama|
|----------|-----------------|
|`mutex_type`|Şablon bağımsız değişkeni için eş anlamlı `Mutex`.|

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[unique_lock](#unique_lock)|Oluşturur bir `unique_lock` nesne.|
|[~ unique_lock yıkıcısı](#dtorunique_lock_destructor)|İle ilişkili tüm kaynakları serbest bırakır `unique_lock` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[lock](#lock)|İş parçacığı ilişkili sahipliğini alana kadar çağıran iş parçacığını engeller `mutex`.|
|[Mutex](#mutex)|İlişkili depolanan işaretçide alır `mutex`.|
|[owns_lock](#owns_lock)|Çağıran iş parçacığını ilişkili sahip olup olmadığını belirtir `mutex`.|
|[Yayın](#release)|Ayırır `unique_lock` ilişkili nesneden `mutex` nesne.|
|[değiştirme](#swap)|İlişkili değiştirir `mutex` ve sahiplik durumunu, belirtilen bir nesnenin sahip.|
|[try_lock](#try_lock)|İlişkili sahipliğini almayı dener `mutex` engelleme olmadan.|
|[try_lock_for](#try_lock_for)|İlişkili sahipliğini almayı dener `mutex` engelleme olmadan.|
|[try_lock_until](#try_lock_until)|İlişkili sahipliğini almayı dener `mutex` engelleme olmadan.|
|[Kilit açma](#unlock)|İlişkili in sahipliğini bırakır `mutex`.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[bool işleci](#op_bool)|Çağıran iş parçacığını sahipliğini ilişkili olup olmadığını belirtir `mutex`.|
|[operator=](#op_eq)|Depolanan kopyalar `mutex` işaretçi ve ilişkili sahiplik durumunu belirtilen bir nesne.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

*unique_lock*<br/>

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<mutex >

**Namespace:** std

## <a name="lock"></a>  Kilit

İş parçacığı ilişkili sahipliğini alana kadar çağıran iş parçacığını engeller `mutex`.

```cpp
void lock();
```

### <a name="remarks"></a>Açıklamalar

Depolanan `mutex` NULL bir işaretçiyse, bu yöntem bir [system_error](../standard-library/system-error-class.md) bir hata koduna sahip `operation_not_permitted`.

Çağıran iş parçacığı zaten ilişkili sahipse `mutex`, bu yöntem bir `system_error` bir hata koduna sahip `resource_deadlock_would_occur`.

Aksi takdirde, bu yöntemin çağırdığı `lock` ilişkili `mutex` ve dahili iş parçacığı sahipliği bayrağı ayarlar **true**.

## <a name="mutex"></a>  Mutex

İlişkili depolanan işaretçide alır `mutex`.

```cpp
mutex_type *mutex() const noexcept;
```

## <a name="op_bool"></a>  bool işleci

Çağıran iş parçacığını ilişkili mutex sahipliğini olup olmadığını belirtir.

```cpp
explicit operator bool() noexcept
```

### <a name="return-value"></a>Dönüş Değeri

**doğru** iş parçacığı; mutex sahipse aksi **false**.

## <a name="op_eq"></a>  işleç =

Depolanan kopyalar `mutex` işaretçi ve ilişkili sahiplik durumunu belirtilen bir nesne.

```cpp
unique_lock& operator=(unique_lock&& Other) noexcept;
```

### <a name="parameters"></a>Parametreler

*Diğer*<br/>
A `unique_lock` nesne.

### <a name="return-value"></a>Dönüş Değeri

`*this`

### <a name="remarks"></a>Açıklamalar

Çağıran iş parçacığının daha önce ilişkili sahipse `mutex`, bu yöntemi çağırmadan önce `unlock` üzerinde `mutex`, yeni değerleri atar.

Kopyalamadan sonra bu yöntem ayarlar *diğer* varsayılan olarak oluşturulmuş bir duruma.

## <a name="owns_lock"></a>  owns_lock

Çağıran iş parçacığını ilişkili sahip olup olmadığını belirtir `mutex`.

```cpp
bool owns_lock() const noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

**doğru** iş parçacığı sahipse `mutex`; Aksi takdirde **false**.

## <a name="release"></a>  Yayın

Ayırır `unique_lock` ilişkili nesneden `mutex` nesne.

```cpp
mutex_type *release() noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

Önceki değeri depolanan `mutex` işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu yöntem depolanmış değerini ayarlar `mutex` 0 ile kümeleri iç işaretçiye `mutex` sahipliği bayrak **false**.

## <a name="swap"></a>  değiştirme

İlişkili değiştirir `mutex` ve sahiplik durumunu, belirtilen bir nesnenin sahip.

```cpp
void swap(unique_lock& Other) noexcept;
```

### <a name="parameters"></a>Parametreler

*Diğer*<br/>
A `unique_lock` nesne.

## <a name="try_lock"></a>  try_lock

İlişkili sahipliğini almayı dener `mutex` engelleme olmadan.

```cpp
bool try_lock() noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

**doğru** yöntemi başarıyla sahipliğini elde ederse `mutex`; Aksi takdirde **false**.

### <a name="remarks"></a>Açıklamalar

Depolanan `mutex` NULL bir işaretçiyse, çağırılıyorsa yöntem bir [system_error](../standard-library/system-error-class.md) bir hata koduna sahip `operation_not_permitted`.

Çağıran iş parçacığı zaten sahipse `mutex`, çağırılıyorsa yöntem bir `system_error` bir hata koduna sahip `resource_deadlock_would_occur`.

## <a name="try_lock_for"></a>  try_lock_for

İlişkili sahipliğini almayı dener `mutex` engelleme olmadan.

```cpp
template <class Rep, class Period>
bool try_lock_for(
    const chrono::duration<Rep, Period>& Rel_time);
```

### <a name="parameters"></a>Parametreler

*Rel_time*<br/>
A [chrono::duration](../standard-library/duration-class.md) yöntemi sahipliğini almayı dener en uzun süreyi belirten nesne `mutex`.

### <a name="return-value"></a>Dönüş Değeri

**doğru** yöntemi başarıyla sahipliğini elde ederse `mutex`; Aksi takdirde **false**.

### <a name="remarks"></a>Açıklamalar

Depolanan `mutex` NULL bir işaretçiyse, çağırılıyorsa yöntem bir [system_error](../standard-library/system-error-class.md) bir hata koduna sahip `operation_not_permitted`.

Çağıran iş parçacığı zaten sahipse `mutex`, çağırılıyorsa yöntem bir `system_error` bir hata koduna sahip `resource_deadlock_would_occur`.

## <a name="try_lock_until"></a>  try_lock_until

İlişkili sahipliğini almayı dener `mutex` engelleme olmadan.

```cpp
template <class Clock, class Duration>
bool try_lock_until(const chrono::time_point<Clock, Duration>& Abs_time);

bool try_lock_until(const xtime* Abs_time);
```

### <a name="parameters"></a>Parametreler

*Abs_time*<br/>
Sonra yöntemi artık girişimlerini sahipliğini almayı eşiği belirten zaman içinde nokta `mutex`.

### <a name="return-value"></a>Dönüş Değeri

**doğru** yöntemi başarıyla sahipliğini elde ederse `mutex`; Aksi takdirde **false**.

### <a name="remarks"></a>Açıklamalar

Depolanan `mutex` NULL bir işaretçiyse, çağırılıyorsa yöntem bir [system_error](../standard-library/system-error-class.md) bir hata koduna sahip `operation_not_permitted`.

Çağıran iş parçacığı zaten sahipse `mutex`, çağırılıyorsa yöntem bir `system_error` bir hata koduna sahip `resource_deadlock_would_occur`.

## <a name="unique_lock"></a>  unique_lock Oluşturucusu

Oluşturur bir `unique_lock` nesne.

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

*Mtx*<br/>
Mutex nesnesi türü.

*Rel_time*<br/>
A [chrono::duration](../standard-library/duration-class.md) yöntemi sahipliğini almayı dener en uzun süreyi belirten nesne `mutex`.

*Abs_time*<br/>
Sonra yöntemi artık girişimlerini sahipliğini almayı eşiği belirten zaman içinde nokta `mutex`.

*Diğer*<br/>
A `unique_lock` nesne.

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu, bir ilişkili mutex işaretçi değeri 0 olan bir nesne oluşturur.

İkinci oluşturucu ilişkili mutex durumundan taşır *diğer*. Taşıma sonrasında *diğer* artık bir mutex ile ilişkili değil.

Kalan oluşturucular deponun & *Mtx* saklanan `mutex` işaretçi. Sahipliğini `mutex` varsa ikinci bağımsız değişkeni tarafından belirlenir.

|||
|-|-|
|`No argument`|Sahipliği çağırarak elde `lock` ilişkili yöntemi `mutex` nesne.|
|`Adopt`|Sahipliği varsayılır. `Mtx` Oluşturucu çağrıldığında kilitlenmelidir.|
|`Defer`|Çağıran iş parçacığı için kendi varsayılır `mutex` nesne. `Mtx` Oluşturucu çağrıldığında kilitlenip değil.|
|`Try`|Sahipliği çağırarak belirlenir `try_lock` ilişkili `mutex` nesne. Oluşturucu hiçbir şey oluşturur.|
|`Rel_time`|Sahipliği çağırarak belirlenir `try_lock_for(Rel_time)`.|
|`Abs_time`|Sahipliği çağırarak belirlenir `try_lock_until(Abs_time)`.|

## <a name="dtorunique_lock_destructor"></a>  ~ unique_lock yıkıcısı

İle ilişkili tüm kaynakları serbest bırakır `unique_lock` nesne.

```cpp
~unique_lock() noexcept;
```

### <a name="remarks"></a>Açıklamalar

Çağıran iş parçacığını ilişkili sahipse `mutex`, çağırarak yok Edicisi yayınlar sahipliği kilidini üzerinde `mutex` nesne.

## <a name="unlock"></a>  Kilit açma

İlişkili in sahipliğini bırakır `mutex`.

```cpp
void unlock();
```

### <a name="remarks"></a>Açıklamalar

Çağıran iş parçacığını ilişkili olmayan sahipseniz `mutex`, bu yöntem bir [system_error](../standard-library/system-error-class.md) bir hata koduna sahip `operation_not_permitted`.

Aksi takdirde, bu yöntemin çağırdığı `unlock` ilişkili `mutex` ve dahili iş parçacığı sahipliği bayrağı ayarlar **false**.

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)<br/>
[\<Mutex >](../standard-library/mutex.md)<br/>
