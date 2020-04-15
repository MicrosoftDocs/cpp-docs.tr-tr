---
title: unique_lock Sınıfı
ms.date: 11/04/2016
f1_keywords:
- mutex/std::unique_lock
ms.assetid: f4ed8ba9-c8af-446f-8ef0-0b356bad14bd
ms.openlocfilehash: 59201fbaba6f2e8ae0ed5f53925b287b4d33aab3
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367264"
---
# <a name="unique_lock-class"></a>unique_lock Sınıfı

Bir 'nin kilitlenmesini ve kilidini açan nesneleri oluşturmak için anında oluşturulabilen şablonu `mutex`temsil eder.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Mutex>
class unique_lock;
```

## <a name="remarks"></a>Açıklamalar

Şablon bağımsız `Mutex` değişkeni bir *mutex türü*adlandırmak gerekir.

`unique_lock` Dahili olarak, ilişkili bir `mutex` nesneye işaretçi ve geçerli iş parçacığının .'a `mutex`sahip olup olmadığını gösteren bir **bool** depolar.

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Genel Typedefs

|Adı|Açıklama|
|----------|-----------------|
|`mutex_type`|Şablon bağımsız değişkeninin `Mutex`eş anlamlısı.|

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[Unique_lock](#unique_lock)|Bir `unique_lock` nesne inşa eder.|
|[~unique_lock Yıkıcı](#dtorunique_lock_destructor)|`unique_lock` Nesneyle ilişkili tüm kaynakları salgılar.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[Kilit](#lock)|İş parçacığı ilişkili `mutex`sahipliğini alana kadar çağrı iş parçacığı engeller.|
|[Mutex](#mutex)|İlişkili için depolanan işaretçiyi `mutex`alır.|
|[owns_lock](#owns_lock)|Arama iş parçacığının ilişkili `mutex`iş parçacığına sahip olup olmadığını belirtir.|
|[Sürüm](#release)|Nesneyi `unique_lock` ilişkili `mutex` nesneden uzaklaştırın.|
|[Takas](#swap)|İlişkili `mutex` ve sahiplik durumunu belirtilen nesnenindurumuyla değiştirir.|
|[try_lock](#try_lock)|Engellenmeden ilişkilinin `mutex` sahipliğini elde etmeye çalışır.|
|[try_lock_for](#try_lock_for)|Engellenmeden ilişkilinin `mutex` sahipliğini elde etmeye çalışır.|
|[try_lock_until](#try_lock_until)|Engellenmeden ilişkilinin `mutex` sahipliğini elde etmeye çalışır.|
|[Kilidini](#unlock)|İlişkilinin `mutex`sahipliğini serbest bırakır.|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[operatör bool](#op_bool)|Arama iş parçacığının ilişkili `mutex`sahipliğe sahip olup olmadığını belirtir.|
|[işleç=](#op_eq)|Depolanan `mutex` işaretçiyi ve ilişkili sahiplik durumunu belirli bir nesneden kopyalar.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

*Unique_lock*

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** \<mutex>

**Ad alanı:** std

## <a name="lock"></a><a name="lock"></a>Kilit

İş parçacığı ilişkili `mutex`sahipliğini alana kadar çağrı iş parçacığı engeller.

```cpp
void lock();
```

### <a name="remarks"></a>Açıklamalar

Depolanan `mutex` işaretçi NULL ise, bu yöntem hata kodu olan `operation_not_permitted`bir [system_error](../standard-library/system-error-class.md) atar.

Arama iş parçacığı zaten `mutex`ilişkili sahibi ise, `system_error` bu yöntem bir `resource_deadlock_would_occur`hata kodu .

Aksi takdirde, `lock` bu yöntem `mutex` ilişkili çağırır ve **gerçek**iç iş parçacığı sahipliği bayrağı ayarlar.

## <a name="mutex"></a><a name="mutex"></a>Mutex

İlişkili için depolanan işaretçiyi `mutex`alır.

```cpp
mutex_type *mutex() const noexcept;
```

## <a name="operator-bool"></a><a name="op_bool"></a>operatör bool

Arama iş parçacığının ilişkili mutex'in mülkiyetine sahip olup olmadığını belirtir.

```cpp
explicit operator bool() noexcept
```

### <a name="return-value"></a>Dönüş Değeri

iş parçacığı mutex sahibi ise **doğru;** aksi takdirde **yanlış**.

## <a name="operator"></a><a name="op_eq"></a>işleç=

Depolanan `mutex` işaretçiyi ve ilişkili sahiplik durumunu belirli bir nesneden kopyalar.

```cpp
unique_lock& operator=(unique_lock&& Other) noexcept;
```

### <a name="parameters"></a>Parametreler

*Diğer*\
Bir `unique_lock` nesnesi.

### <a name="return-value"></a>Dönüş Değeri

`*this`

### <a name="remarks"></a>Açıklamalar

Arama iş parçacığı, bu `mutex`yöntemde çağrıda `unlock` bulunmadan `mutex`önce daha önce ilişkili olana sahipse, yeni değerleri atar.

Kopyadan sonra, bu yöntem *Diğer'i* varsayılan olarak oluşturulmuş duruma ayarlar.

## <a name="owns_lock"></a><a name="owns_lock"></a>owns_lock

Arama iş parçacığının ilişkili `mutex`iş parçacığına sahip olup olmadığını belirtir.

```cpp
bool owns_lock() const noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

**true** iş parçacığı sahibi `mutex`ise doğru ; aksi takdirde, **yanlış**.

## <a name="release"></a><a name="release"></a>Sürüm

Nesneyi `unique_lock` ilişkili `mutex` nesneden uzaklaştırın.

```cpp
mutex_type *release() noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

Depolanan `mutex` işaretçinin önceki değeri.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, depolanan `mutex` işaretçinin değerini 0 `mutex` olarak ayarlar ve iç sahiplik bayrağını **false**olarak ayarlar.

## <a name="swap"></a><a name="swap"></a>Takas

İlişkili `mutex` ve sahiplik durumunu belirtilen nesnenindurumuyla değiştirir.

```cpp
void swap(unique_lock& Other) noexcept;
```

### <a name="parameters"></a>Parametreler

*Diğer*\
Bir `unique_lock` nesnesi.

## <a name="try_lock"></a><a name="try_lock"></a>try_lock

Engellenmeden ilişkilinin `mutex` sahipliğini elde etmeye çalışır.

```cpp
bool try_lock() noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

yöntem başarıyla sahiplik elde ederse `mutex` **doğrudur;** aksi takdirde, **yanlış**.

### <a name="remarks"></a>Açıklamalar

Depolanan `mutex` işaretçi NULL ise, yöntem [system_error](../standard-library/system-error-class.md) `operation_not_permitted`hata kodu olan bir system_error atar.

Arama iş parçacığı zaten `mutex`sahibi ise, `system_error` yöntem bir hata `resource_deadlock_would_occur`kodu olan atar .

## <a name="try_lock_for"></a><a name="try_lock_for"></a>try_lock_for

Engellenmeden ilişkilinin `mutex` sahipliğini elde etmeye çalışır.

```cpp
template <class Rep, class Period>
bool try_lock_for(
    const chrono::duration<Rep, Period>& Rel_time);
```

### <a name="parameters"></a>Parametreler

*Rel_time*\
Bir [kronometre::duration](../standard-library/duration-class.md) nesnesi, yöntemin sahipliğini elde etmeye `mutex`çalıştığı maksimum süreyi belirtir.

### <a name="return-value"></a>Dönüş Değeri

yöntem başarıyla sahiplik elde ederse `mutex` **doğrudur;** aksi takdirde, **yanlış**.

### <a name="remarks"></a>Açıklamalar

Depolanan `mutex` işaretçi NULL ise, yöntem [system_error](../standard-library/system-error-class.md) `operation_not_permitted`hata kodu olan bir system_error atar.

Arama iş parçacığı zaten `mutex`sahibi ise, `system_error` yöntem bir hata `resource_deadlock_would_occur`kodu olan atar .

## <a name="try_lock_until"></a><a name="try_lock_until"></a>try_lock_until

Engellenmeden ilişkilinin `mutex` sahipliğini elde etmeye çalışır.

```cpp
template <class Clock, class Duration>
bool try_lock_until(const chrono::time_point<Clock, Duration>& Abs_time);

bool try_lock_until(const xtime* Abs_time);
```

### <a name="parameters"></a>Parametreler

*Abs_time*\
Zaman içinde bir nokta hangi yöntem artık sahipliğini elde etmek için `mutex`çalışır sonra eşik belirtir .

### <a name="return-value"></a>Dönüş Değeri

yöntem başarıyla sahiplik elde ederse `mutex` **doğrudur;** aksi takdirde, **yanlış**.

### <a name="remarks"></a>Açıklamalar

Depolanan `mutex` işaretçi NULL ise, yöntem [system_error](../standard-library/system-error-class.md) `operation_not_permitted`hata kodu olan bir system_error atar.

Arama iş parçacığı zaten `mutex`sahibi ise, `system_error` yöntem bir hata `resource_deadlock_would_occur`kodu olan atar .

## <a name="unique_lock-constructor"></a><a name="unique_lock"></a>unique_lock Yapıcı

Bir `unique_lock` nesne inşa eder.

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

*Mtx*\
Mutex türü nde bir nesne.

*Rel_time*\
Bir [kronometre::duration](../standard-library/duration-class.md) nesnesi, yöntemin sahipliğini elde etmeye `mutex`çalıştığı maksimum süreyi belirtir.

*Abs_time*\
Zaman içinde bir nokta hangi yöntem artık sahipliğini elde etmek için `mutex`çalışır sonra eşik belirtir .

*Diğer*\
Bir `unique_lock` nesnesi.

### <a name="remarks"></a>Açıklamalar

İlk oluşturucu, ilişkili mutex işaretçisi değeri 0 olan bir nesne yi kınır.

İkinci oluşturucu ilişkili mutex durumunu *Diğer'den*taşır. Taşımadan sonra, *Diğer* artık bir mutex ile ilişkilidir.

Kalan oluşturucular depolanan `mutex` işaretçi olarak *Mtx&* depolar. `mutex` Varsa, ikinci bağımsız değişkentarafından belirlenir.

|||
|-|-|
|`No argument`|Sahiplik ilişkili `mutex` nesne `lock` üzerinde yöntem çağırarak elde edilir.|
|`Adopt`|Sahiplik varsayılır. `Mtx`oluşturucu çağrıldığında kilitlenmelidir.|
|`Defer`|Arama iş parçacığının `mutex` nesneye sahip olmadığı varsayılır. `Mtx`oluşturucu çağrıldığında kilitlenmemelidir.|
|`Try`|Sahiplik ilişkili `mutex` `try_lock` nesneyi çağırarak belirlenir. Yapıcı hiçbir şey atmaz.|
|`Rel_time`|Sahiplik arayarak `try_lock_for(Rel_time)`belirlenir.|
|`Abs_time`|Sahiplik arayarak `try_lock_until(Abs_time)`belirlenir.|

## <a name="unique_lock-destructor"></a><a name="dtorunique_lock_destructor"></a>~unique_lock Yıkıcı

`unique_lock` Nesneyle ilişkili tüm kaynakları salgılar.

```cpp
~unique_lock() noexcept;
```

### <a name="remarks"></a>Açıklamalar

Arama iş parçacığı ilişkili `mutex`sahibi ise, yıkıcı `mutex` nesne üzerinde kilidini çağırarak sahiplik bültenleri.

## <a name="unlock"></a><a name="unlock"></a>Kilidini

İlişkilinin `mutex`sahipliğini serbest bırakır.

```cpp
void unlock();
```

### <a name="remarks"></a>Açıklamalar

Arama iş parçacığı ilişkili `mutex`sahibi değilse, bu yöntem `operation_not_permitted`hata kodu olan bir [system_error](../standard-library/system-error-class.md) atar .

Aksi takdirde, `unlock` bu yöntem `mutex` ilişkili çağırır ve iç iş parçacığı sahipliği bayrağı **yanlış**ayarlar.

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi Dosyaları Başvurusu](../standard-library/cpp-standard-library-header-files.md)\
[\<mutex>](../standard-library/mutex.md)
