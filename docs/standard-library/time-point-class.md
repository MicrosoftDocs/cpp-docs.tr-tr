---
description: 'Hakkında daha fazla bilgi edinin: time_point sınıfı'
title: time_point Sınıfı
ms.date: 03/27/2019
f1_keywords:
- chrono/std::chrono::time_point
- chrono/std::chrono::time_point::time_point
- chrono/std::chrono::time_point::max
- chrono/std::chrono::time_point::min
- chrono/std::chrono::time_point::time_since_epoch
ms.assetid: 18be1e52-57b9-489a-8a9b-f58894f0aaad
helpviewer_keywords:
- std::chrono [C++], time_point
ms.openlocfilehash: f9818c6ec3817608864fac0108d73666a0ef3bf9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97167285"
---
# <a name="time_point-class"></a>time_point Sınıfı

`time_point`, Zaman içinde bir noktayı temsil eden bir türü açıklar. Şablon bağımsız değişkeni tarafından temsil edilen dönem bu yana geçen süreyi depolayan, [Duration](../standard-library/duration-class.md) türünde bir nesne tutar `Clock` .

## <a name="syntax"></a>Syntax

```cpp
template <class Clock,
    class Duration = typename Clock::duration>
class time_point;
```

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Ortak tür tanımları

|Ad|Açıklama|
|----------|-----------------|
|`time_point::clock`|Şablon parametresi için eş anlamlı `Clock` .|
|`time_point::duration`|Şablon parametresi için eş anlamlı `Duration` .|
|`time_point::period`|İç içe tür adı için eş anlamlı `duration::period` .|
|`time_point::rep`|İç içe tür adı için eş anlamlı `duration::rep` .|

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[time_point](#time_point)|Bir `time_point` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Biçimlendir](#max)|İçin üst sınırı belirtir `time_point::ref` .|
|[Min](#min)|İçin alt sınırı belirtir `time_point::ref` .|
|[time_since_epoch](#time_since_epoch)|Depolanan değeri döndürür `duration` .|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[time_point:: operator + =](#op_add_eq)|Depolanan süreye belirtilen bir değer ekler.|
|[time_point:: operator-=](#operator-_eq)|Belirtilen bir değeri depolanan süreden çıkartır.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<chrono>

**Ad alanı:** std:: hatası

## <a name="time_pointmax"></a><a name="max"></a> time_point:: Max

Türündeki değerler için üst sınırı döndüren statik yöntem `time_point::ref` .

```cpp
static constexpr time_point max();
```

### <a name="return-value"></a>Dönüş Değeri

Aslında, döndürür `time_point(duration::max())` .

## <a name="time_pointmin"></a><a name="min"></a> time_point:: min

Türündeki değerler için alt sınır döndüren statik yöntem `time_point::ref` .

```cpp
static constexpr time_point min();
```

### <a name="return-value"></a>Dönüş Değeri

Aslında, döndürür `time_point(duration::min())` .

## <a name="time_pointoperator"></a><a name="op_add_eq"></a> time_point:: operator + =

Saklı [süre](../standard-library/duration-class.md) değerine belirtilen bir değer ekler.

```cpp
time_point& operator+=(const duration& Dur);
```

### <a name="parameters"></a>Parametreler

*Hecesi*\
Bir `duration` nesnesi.

### <a name="return-value"></a>Dönüş Değeri

`time_point`Ekleme gerçekleştirildikten sonra nesnesi.

## <a name="time_pointoperator-"></a><a name="operator-_eq"></a> time_point:: operator-=

Saklanan [süre](../standard-library/duration-class.md) değerinden belirtilen değeri çıkartır.

```cpp
time_point& operator-=(const duration& Dur);
```

### <a name="parameters"></a>Parametreler

*Hecesi*\
Bir `duration` nesnesi.

### <a name="return-value"></a>Dönüş Değeri

`time_point`Çıkarma gerçekleştirildikten sonra nesnesi.

## <a name="time_pointtime_point-constructor"></a><a name="time_point"></a> time_point:: time_point Oluşturucusu

Bir `time_point` nesnesi oluşturur.

```cpp
constexpr time_point();

constexpr explicit time_point(const duration& Dur);

template <class Duration2>
constexpr time_point(const time_point<clock, Duration2>& Tp);
```

### <a name="parameters"></a>Parametreler

*Hecesi*\
[Süre](../standard-library/duration-class.md) nesnesi.

*'Ye*\
Bir `time_point` nesnesi.

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu, saklı `duration` değeri [Duration:: Zero](../standard-library/duration-class.md#zero)değerine eşit olan bir nesne oluşturur.

İkinci Oluşturucu, saklı süresi değeri *süre*' ne eşit olan bir nesne oluşturur. `is_convertible<Duration2, duration>`Doğru tutmadığı müddetçe, ikinci Oluşturucu aşırı yükleme çözümüne katılmaz. Daha fazla bilgi için bkz. [<type_traits>](../standard-library/type-traits.md).

Üçüncü Oluşturucu, `duration` kullanarak değerini başlatır `Tp.time_since_epoch()` .

## <a name="time_pointtime_since_epoch"></a><a name="time_since_epoch"></a> time_point:: time_since_epoch

Saklı [süre](../standard-library/duration-class.md) değerini alır.

```cpp
constexpr duration time_since_epoch() const;
```

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)\
[\<chrono>](../standard-library/chrono.md)
