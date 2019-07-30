---
title: unique_lock Sınıfı
ms.date: 11/04/2016
f1_keywords:
- mutex/std::unique_lock
ms.assetid: f4ed8ba9-c8af-446f-8ef0-0b356bad14bd
ms.openlocfilehash: 655d7b08c452bed94277aaed2cc8368aaeb462c9
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68454925"
---
# <a name="uniquelock-class"></a>unique_lock Sınıfı

Bir `mutex`öğesinin kilitlenmesini ve kilidinin açılmasını yöneten nesneler oluşturmak için örneklenebilir bir şablonu temsil eder.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Mutex>
class unique_lock;
```

## <a name="remarks"></a>Açıklamalar

Şablon bağımsız değişkeni `Mutex` bir *mutex türü*adı vermelidir.

Dahili olarak, `unique_lock` ilişkili `mutex` bir nesne için bir işaretçi ve geçerli iş parçacığının öğesine sahip olup olmadığını `mutex`belirten bir bool depolar.

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Ortak tür tanımları

|Ad|Açıklama|
|----------|-----------------|
|`mutex_type`|Şablon bağımsız değişkeni `Mutex`için eş anlamlı.|

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[unique_lock](#unique_lock)|Bir `unique_lock` nesnesi oluşturur.|
|[~ unique_lock yıkıcısı](#dtorunique_lock_destructor)|`unique_lock` Nesnesiyle ilişkili tüm kaynakları serbest bırakır.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[lock](#lock)|İş parçacığı ilişkili `mutex`sahipliğini alıncaya kadar çağıran iş parçacığını engeller.|
|[mutex](#mutex)|Saklı işaretçiyi ilişkili `mutex`öğesine alır.|
|[owns_lock](#owns_lock)|Çağıran iş parçacığının ilişkili `mutex`öğesine sahip olup olmadığını belirtir.|
|[Yayın](#release)|`unique_lock` Nesneyi ilişkili`mutex` nesneden kaldırır.|
|[Kur](#swap)|Belirtilen bir nesnenin `mutex` ilişkili ve sahiplik durumunu değiştirir.|
|[try_lock](#try_lock)|Engellenmeden ilişkili `mutex` sahipliğini almaya çalışır.|
|[try_lock_for](#try_lock_for)|Engellenmeden ilişkili `mutex` sahipliğini almaya çalışır.|
|[try_lock_until](#try_lock_until)|Engellenmeden ilişkili `mutex` sahipliğini almaya çalışır.|
|[kaldırın](#unlock)|İlişkili `mutex`öğesinin sahipliğini yayınlar.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[işleç bool](#op_bool)|Çağıran iş parçacığının ilişkili `mutex`öğesinin sahipliğini içerip içermediğini belirtir.|
|[operator=](#op_eq)|Belirtilen nesneden saklı `mutex` işaretçiyi ve ilişkili sahiplik durumunu kopyalar.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

*unique_lock*

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<mutex >

**Ad alanı:** std

## <a name="lock"></a>ine

İş parçacığı ilişkili `mutex`sahipliğini alıncaya kadar çağıran iş parçacığını engeller.

```cpp
void lock();
```

### <a name="remarks"></a>Açıklamalar

Saklı `mutex` işaretçi null ise, bu yöntem hata kodu `operation_not_permitted`olan bir [system_error](../standard-library/system-error-class.md) oluşturur.

Çağıran iş parçacığı ilişkili `mutex`öğesine zaten sahipse, bu yöntem hata kodu `resource_deadlock_would_occur`olan `system_error` bir oluşturur.

Aksi takdirde, bu yöntem `lock` ilişkili `mutex` öğesine çağrı yapar ve iç iş parçacığı sahiplik bayrağını **true**olarak ayarlar.

## <a name="mutex"></a>mutex

Saklı işaretçiyi ilişkili `mutex`öğesine alır.

```cpp
mutex_type *mutex() const noexcept;
```

## <a name="op_bool"></a>işleç bool

Çağıran iş parçacığının ilişkili mutex 'in sahipliğini içerip içermediğini belirtir.

```cpp
explicit operator bool() noexcept
```

### <a name="return-value"></a>Dönüş Değeri

iş parçacığı mutex 'e sahipse **doğru** ; Aksi halde **yanlış**.

## <a name="op_eq"></a>işleç =

Belirtilen nesneden saklı `mutex` işaretçiyi ve ilişkili sahiplik durumunu kopyalar.

```cpp
unique_lock& operator=(unique_lock&& Other) noexcept;
```

### <a name="parameters"></a>Parametreler

*Farklı*\
A `unique_lock` nesne.

### <a name="return-value"></a>Dönüş Değeri

`*this`

### <a name="remarks"></a>Açıklamalar

Çağıran iş parçacığı daha önce ilişkili `mutex`öğesine sahipse, bu `unlock` yöntem üzerinde `mutex`çağrılmadan önce, yeni değerleri atar.

Kopyalama işleminden sonra, bu yöntem *diğerini* varsayılan olarak oluşturulmuş bir duruma ayarlar.

## <a name="owns_lock"></a>owns_lock

Çağıran iş parçacığının ilişkili `mutex`öğesine sahip olup olmadığını belirtir.

```cpp
bool owns_lock() const noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

iş parçacığı öğesine sahipse `mutex`doğru; Aksi takdirde, **false**.

## <a name="release"></a>Yayın

`unique_lock` Nesneyi ilişkili`mutex` nesneden kaldırır.

```cpp
mutex_type *release() noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

Saklı `mutex` işaretçinin önceki değeri.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, saklı `mutex` işaretçinin değerini 0 olarak ayarlar ve iç `mutex` sahiplik bayrağını **false**olarak ayarlar.

## <a name="swap"></a>Kur

Belirtilen bir nesnenin `mutex` ilişkili ve sahiplik durumunu değiştirir.

```cpp
void swap(unique_lock& Other) noexcept;
```

### <a name="parameters"></a>Parametreler

*Farklı*\
A `unique_lock` nesne.

## <a name="try_lock"></a>try_lock

Engellenmeden ilişkili `mutex` sahipliğini almaya çalışır.

```cpp
bool try_lock() noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

Yöntem öğesinin `mutex`sahipliğini başarıyla alırsa doğru, aksi takdirde **yanlış**olur.

### <a name="remarks"></a>Açıklamalar

Saklı `mutex` işaretçi null ise, yöntemi hata kodu `operation_not_permitted`olan bir [system_error](../standard-library/system-error-class.md) oluşturur.

Çağıran iş parçacığı öğesine zaten sahip `mutex`ise, yöntemi hata kodu `resource_deadlock_would_occur`olan `system_error` bir oluşturur.

## <a name="try_lock_for"></a>try_lock_for

Engellenmeden ilişkili `mutex` sahipliğini almaya çalışır.

```cpp
template <class Rep, class Period>
bool try_lock_for(
    const chrono::duration<Rep, Period>& Rel_time);
```

### <a name="parameters"></a>Parametreler

*Rel_time*\
Bir zaman hatası: yöntemin sahipliğini `mutex`almaya çalıştığı maksimum süreyi belirten [:d uration](../standard-library/duration-class.md) nesnesi.

### <a name="return-value"></a>Dönüş Değeri

Yöntem öğesinin `mutex`sahipliğini başarıyla alırsa doğru, aksi takdirde **yanlış**olur.

### <a name="remarks"></a>Açıklamalar

Saklı `mutex` işaretçi null ise, yöntemi hata kodu `operation_not_permitted`olan bir [system_error](../standard-library/system-error-class.md) oluşturur.

Çağıran iş parçacığı öğesine zaten sahip `mutex`ise, yöntemi hata kodu `resource_deadlock_would_occur`olan `system_error` bir oluşturur.

## <a name="try_lock_until"></a>try_lock_until

Engellenmeden ilişkili `mutex` sahipliğini almaya çalışır.

```cpp
template <class Clock, class Duration>
bool try_lock_until(const chrono::time_point<Clock, Duration>& Abs_time);

bool try_lock_until(const xtime* Abs_time);
```

### <a name="parameters"></a>Parametreler

*Abs_time*\
Bir zaman içinde, `mutex`yöntemin sahipliğini elde etme girişiminde bulunmayan eşiği belirten bir nokta.

### <a name="return-value"></a>Dönüş Değeri

Yöntem öğesinin `mutex`sahipliğini başarıyla alırsa doğru, aksi takdirde **yanlış**olur.

### <a name="remarks"></a>Açıklamalar

Saklı `mutex` işaretçi null ise, yöntemi hata kodu `operation_not_permitted`olan bir [system_error](../standard-library/system-error-class.md) oluşturur.

Çağıran iş parçacığı öğesine zaten sahip `mutex`ise, yöntemi hata kodu `resource_deadlock_would_occur`olan `system_error` bir oluşturur.

## <a name="unique_lock"></a>unique_lock Oluşturucusu

Bir `unique_lock` nesnesi oluşturur.

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

*MTX*\
Bir mutex tür nesnesi.

*Rel_time*\
Bir zaman hatası: yöntemin sahipliğini `mutex`almaya çalıştığı maksimum süreyi belirten [:d uration](../standard-library/duration-class.md) nesnesi.

*Abs_time*\
Bir zaman içinde, `mutex`yöntemin sahipliğini elde etme girişiminde bulunmayan eşiği belirten bir nokta.

*Farklı*\
Bir `unique_lock` nesne.

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu, ilişkili bir mutex işaretçi değeri 0 olan bir nesnesi oluşturur.

İkinci Oluşturucu ilişkili mutex durumunu *diğer*öğesinden taşımaktır. Taşıma işleminden sonra *diğeri* artık bir mutex ile ilişkilendirilmez.

Kalan oluşturucular & *MTX* saklı `mutex` işaretçi olarak depolar. Öğesinin `mutex` sahipliği, varsa ikinci bağımsız değişkenle belirlenir.

|||
|-|-|
|`No argument`|Sahiplik, ilişkili `lock` `mutex` nesne üzerinde yöntemi çağırarak elde edilir.|
|`Adopt`|Sahiplik kabul edilir. `Mtx`Oluşturucu çağrıldığında kilitlenmelidir.|
|`Defer`|Çağıran iş parçacığının `mutex` nesneye sahip olmadığı varsayılır. `Mtx`Oluşturucu çağrıldığında kilitlenmemelidir.|
|`Try`|Sahiplik, ilişkili `mutex` nesne üzerinde `try_lock` çağırarak belirlenir. Oluşturucu hiçbir şey yapmaz.|
|`Rel_time`|Sahiplik, çağırarak `try_lock_for(Rel_time)`belirlenir.|
|`Abs_time`|Sahiplik, çağırarak `try_lock_until(Abs_time)`belirlenir.|

## <a name="dtorunique_lock_destructor"></a>~ unique_lock yıkıcısı

`unique_lock` Nesnesiyle ilişkili tüm kaynakları serbest bırakır.

```cpp
~unique_lock() noexcept;
```

### <a name="remarks"></a>Açıklamalar

Çağıran iş parçacığı ilişkili `mutex`öğesine sahipse, yıkıcı `mutex` nesne üzerinde unlock 'u çağırarak sahipliğini yayınlar.

## <a name="unlock"></a>kaldırın

İlişkili `mutex`öğesinin sahipliğini yayınlar.

```cpp
void unlock();
```

### <a name="remarks"></a>Açıklamalar

Çağıran iş parçacığı ilişkili `mutex`bir sahip değilse, bu yöntem hata kodu `operation_not_permitted`olan bir [system_error](../standard-library/system-error-class.md) oluşturur.

Aksi takdirde, bu yöntem `unlock` ilişkili `mutex` öğesine çağrı yapar ve iç iş parçacığı sahiplik bayrağını **false**olarak ayarlar.

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)\
[\<mutex >](../standard-library/mutex.md)
