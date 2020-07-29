---
title: unique_lock Sınıfı
ms.date: 11/04/2016
f1_keywords:
- mutex/std::unique_lock
ms.assetid: f4ed8ba9-c8af-446f-8ef0-0b356bad14bd
ms.openlocfilehash: 189fd70ce10b6067646553f2b92a8fc09239d054
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87212041"
---
# <a name="unique_lock-class"></a>unique_lock Sınıfı

Bir öğesinin kilitlenmesini ve kilidinin açılmasını yöneten nesneler oluşturmak için örneklenebilir bir şablonu temsil eder `mutex` .

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Mutex>
class unique_lock;
```

## <a name="remarks"></a>Açıklamalar

Şablon bağımsız değişkeni `Mutex` bir *mutex türü*adı vermelidir.

Dahili olarak, `unique_lock` ilişkili bir nesneye bir işaretçi depolar `mutex` ve **`bool`** geçerli iş parçacığının öğesine sahip olup olmadığını gösterir `mutex` .

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Ortak tür tanımları

|Ad|Açıklama|
|----------|-----------------|
|`mutex_type`|Şablon bağımsız değişkeni için eş anlamlı `Mutex` .|

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[unique_lock](#unique_lock)|Bir `unique_lock` nesnesi oluşturur.|
|[~ unique_lock yok edici](#dtorunique_lock_destructor)|Nesnesiyle ilişkili tüm kaynakları serbest bırakır `unique_lock` .|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[ine](#lock)|İş parçacığı ilişkili sahipliğini alıncaya kadar çağıran iş parçacığını engeller `mutex` .|
|[mutex](#mutex)|Saklı işaretçiyi ilişkili öğesine alır `mutex` .|
|[owns_lock](#owns_lock)|Çağıran iş parçacığının ilişkili öğesine sahip olup olmadığını belirtir `mutex` .|
|[Yayın](#release)|`unique_lock`Nesneyi ilişkili `mutex` nesneden kaldırır.|
|[Kur](#swap)|`mutex`Belirtilen bir nesnenin ilişkili ve sahiplik durumunu değiştirir.|
|[try_lock](#try_lock)|Engellenmeden ilişkili sahipliğini almaya çalışır `mutex` .|
|[try_lock_for](#try_lock_for)|Engellenmeden ilişkili sahipliğini almaya çalışır `mutex` .|
|[try_lock_until](#try_lock_until)|Engellenmeden ilişkili sahipliğini almaya çalışır `mutex` .|
|[kaldırın](#unlock)|İlişkili öğesinin sahipliğini yayınlar `mutex` .|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[işleç bool](#op_bool)|Çağıran iş parçacığının ilişkili öğesinin sahipliğini içerip içermediğini belirtir `mutex` .|
|[işleç =](#op_eq)|`mutex`Belirtilen nesneden saklı işaretçiyi ve ilişkili sahiplik durumunu kopyalar.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

*unique_lock*

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<mutex>

**Ad alanı:** std

## <a name="lock"></a><a name="lock"></a>ine

İş parçacığı ilişkili sahipliğini alıncaya kadar çağıran iş parçacığını engeller `mutex` .

```cpp
void lock();
```

### <a name="remarks"></a>Açıklamalar

Saklı `mutex` IŞARETÇI null ise, bu yöntem hata kodu olan bir [system_error](../standard-library/system-error-class.md) oluşturur `operation_not_permitted` .

Çağıran iş parçacığı ilişkili öğesine zaten sahipse `mutex` , bu yöntem hata kodu olan bir oluşturur `system_error` `resource_deadlock_would_occur` .

Aksi takdirde, bu yöntem `lock` ilişkili öğesine çağrı `mutex` yapar ve iç iş parçacığı sahiplik bayrağını olarak ayarlar **`true`** .

## <a name="mutex"></a><a name="mutex"></a>mutex

Saklı işaretçiyi ilişkili öğesine alır `mutex` .

```cpp
mutex_type *mutex() const noexcept;
```

## <a name="operator-bool"></a><a name="op_bool"></a>işleç bool

Çağıran iş parçacığının ilişkili mutex 'in sahipliğini içerip içermediğini belirtir.

```cpp
explicit operator bool() noexcept
```

### <a name="return-value"></a>Dönüş Değeri

**`true`** iş parçacığı mutex 'e sahipse; Aksi takdirde **`false`** .

## <a name="operator"></a><a name="op_eq"></a>işleç =

`mutex`Belirtilen nesneden saklı işaretçiyi ve ilişkili sahiplik durumunu kopyalar.

```cpp
unique_lock& operator=(unique_lock&& Other) noexcept;
```

### <a name="parameters"></a>Parametreler

*Farklı*\
Bir `unique_lock` nesnesi.

### <a name="return-value"></a>Dönüş Değeri

`*this`

### <a name="remarks"></a>Açıklamalar

Çağıran iş parçacığı daha önce ilişkili öğesine sahipse, `mutex` Bu yöntem üzerinde çağrılmadan `unlock` önce, `mutex` yeni değerleri atar.

Kopyalama işleminden sonra, bu yöntem *diğerini* varsayılan olarak oluşturulmuş bir duruma ayarlar.

## <a name="owns_lock"></a><a name="owns_lock"></a>owns_lock

Çağıran iş parçacığının ilişkili öğesine sahip olup olmadığını belirtir `mutex` .

```cpp
bool owns_lock() const noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

**`true`** iş parçacığı öğesine sahipse `mutex` ; Aksi takdirde, **`false`** .

## <a name="release"></a><a name="release"></a>Yayın

`unique_lock`Nesneyi ilişkili `mutex` nesneden kaldırır.

```cpp
mutex_type *release() noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

Saklı işaretçinin önceki değeri `mutex` .

### <a name="remarks"></a>Açıklamalar

Bu yöntem, saklı `mutex` işaretçinin değerini 0 olarak ayarlar ve iç `mutex` sahiplik bayrağını olarak ayarlar **`false`** .

## <a name="swap"></a><a name="swap"></a>Kur

`mutex`Belirtilen bir nesnenin ilişkili ve sahiplik durumunu değiştirir.

```cpp
void swap(unique_lock& Other) noexcept;
```

### <a name="parameters"></a>Parametreler

*Farklı*\
Bir `unique_lock` nesnesi.

## <a name="try_lock"></a><a name="try_lock"></a>try_lock

Engellenmeden ilişkili sahipliğini almaya çalışır `mutex` .

```cpp
bool try_lock() noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

**`true`** Yöntemi öğesinin sahipliğini başarıyla alırsa `mutex` ; Aksi takdirde, **`false`** .

### <a name="remarks"></a>Açıklamalar

Saklı `mutex` IŞARETÇI null ise, yöntemi hata kodu olan bir [system_error](../standard-library/system-error-class.md) oluşturur `operation_not_permitted` .

Çağıran iş parçacığı öğesine zaten sahip ise `mutex` , yöntemi hata kodu olan bir oluşturur `system_error` `resource_deadlock_would_occur` .

## <a name="try_lock_for"></a><a name="try_lock_for"></a>try_lock_for

Engellenmeden ilişkili sahipliğini almaya çalışır `mutex` .

```cpp
template <class Rep, class Period>
bool try_lock_for(
    const chrono::duration<Rep, Period>& Rel_time);
```

### <a name="parameters"></a>Parametreler

*Rel_time*\
Bir zaman hatası: yöntemin sahipliğini almaya çalıştığı maksimum süreyi belirten [:d uration](../standard-library/duration-class.md) nesnesi `mutex` .

### <a name="return-value"></a>Dönüş Değeri

**`true`** Yöntemi öğesinin sahipliğini başarıyla alırsa `mutex` ; Aksi takdirde, **`false`** .

### <a name="remarks"></a>Açıklamalar

Saklı `mutex` IŞARETÇI null ise, yöntemi hata kodu olan bir [system_error](../standard-library/system-error-class.md) oluşturur `operation_not_permitted` .

Çağıran iş parçacığı öğesine zaten sahip ise `mutex` , yöntemi hata kodu olan bir oluşturur `system_error` `resource_deadlock_would_occur` .

## <a name="try_lock_until"></a><a name="try_lock_until"></a>try_lock_until

Engellenmeden ilişkili sahipliğini almaya çalışır `mutex` .

```cpp
template <class Clock, class Duration>
bool try_lock_until(const chrono::time_point<Clock, Duration>& Abs_time);

bool try_lock_until(const xtime* Abs_time);
```

### <a name="parameters"></a>Parametreler

*Abs_time*\
Bir zaman içinde, yöntemin sahipliğini elde etme girişiminde bulunmayan eşiği belirten bir nokta `mutex` .

### <a name="return-value"></a>Dönüş Değeri

**`true`** Yöntemi öğesinin sahipliğini başarıyla alırsa `mutex` ; Aksi takdirde, **`false`** .

### <a name="remarks"></a>Açıklamalar

Saklı `mutex` IŞARETÇI null ise, yöntemi hata kodu olan bir [system_error](../standard-library/system-error-class.md) oluşturur `operation_not_permitted` .

Çağıran iş parçacığı öğesine zaten sahip ise `mutex` , yöntemi hata kodu olan bir oluşturur `system_error` `resource_deadlock_would_occur` .

## <a name="unique_lock-constructor"></a><a name="unique_lock"></a>unique_lock Oluşturucusu

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
Bir zaman hatası: yöntemin sahipliğini almaya çalıştığı maksimum süreyi belirten [:d uration](../standard-library/duration-class.md) nesnesi `mutex` .

*Abs_time*\
Bir zaman içinde, yöntemin sahipliğini elde etme girişiminde bulunmayan eşiği belirten bir nokta `mutex` .

*Farklı*\
Bir `unique_lock` nesnesi.

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu, ilişkili bir mutex işaretçi değeri 0 olan bir nesnesi oluşturur.

İkinci Oluşturucu ilişkili mutex durumunu *diğer*öğesinden taşımaktır. Taşıma işleminden sonra *diğeri* artık bir mutex ile ilişkilendirilmez.

Kalan oluşturucular & *MTX* saklı işaretçi olarak depolar `mutex` . Öğesinin sahipliği, varsa `mutex` ikinci bağımsız değişkenle belirlenir.

|||
|-|-|
|`No argument`|Sahiplik, `lock` ilişkili nesne üzerinde yöntemi çağırarak elde edilir `mutex` .|
|`Adopt`|Sahiplik kabul edilir. `Mtx`Oluşturucu çağrıldığında kilitlenmelidir.|
|`Defer`|Çağıran iş parçacığının nesneye sahip olmadığı varsayılır `mutex` . `Mtx`Oluşturucu çağrıldığında kilitlenmemelidir.|
|`Try`|Sahiplik, `try_lock` ilişkili nesne üzerinde çağırarak belirlenir `mutex` . Oluşturucu hiçbir şey yapmaz.|
|`Rel_time`|Sahiplik, çağırarak belirlenir `try_lock_for(Rel_time)` .|
|`Abs_time`|Sahiplik, çağırarak belirlenir `try_lock_until(Abs_time)` .|

## <a name="unique_lock-destructor"></a><a name="dtorunique_lock_destructor"></a>~ unique_lock yok edici

Nesnesiyle ilişkili tüm kaynakları serbest bırakır `unique_lock` .

```cpp
~unique_lock() noexcept;
```

### <a name="remarks"></a>Açıklamalar

Çağıran iş parçacığı ilişkili öğesine sahipse `mutex` , yıkıcı nesne üzerinde unlock 'u çağırarak sahipliğini yayınlar `mutex` .

## <a name="unlock"></a><a name="unlock"></a>kaldırın

İlişkili öğesinin sahipliğini yayınlar `mutex` .

```cpp
void unlock();
```

### <a name="remarks"></a>Açıklamalar

Çağıran iş parçacığı ilişkili bir sahip değilse `mutex` , bu yöntem hata kodu olan bir [system_error](../standard-library/system-error-class.md) oluşturur `operation_not_permitted` .

Aksi takdirde, bu yöntem `unlock` ilişkili öğesine çağrı `mutex` yapar ve iç iş parçacığı sahiplik bayrağını olarak ayarlar **`false`** .

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)\
[\<mutex>](../standard-library/mutex.md)
