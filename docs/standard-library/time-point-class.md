---
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
ms.openlocfilehash: 4511c7b2d8629f1a052137c7997daf5913c976ab
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68459984"
---
# <a name="timepoint-class"></a>time_point Sınıfı

, Zaman içinde bir noktayı temsil eden bir türü açıklar.`time_point` Şablon bağımsız değişkeni `Clock`tarafından temsil edilen dönem bu yana geçen süreyi depolayan, [Duration](../standard-library/duration-class.md) türünde bir nesne tutar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Clock,
    class Duration = typename Clock::duration>
class time_point;
```

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Ortak tür tanımları

|Ad|Açıklama|
|----------|-----------------|
|`time_point::clock`|Şablon parametresi `Clock`için eş anlamlı.|
|`time_point::duration`|Şablon parametresi `Duration`için eş anlamlı.|
|`time_point::period`|İç içe tür adı `duration::period`için eş anlamlı.|
|`time_point::rep`|İç içe tür adı `duration::rep`için eş anlamlı.|

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[time_point](#time_point)|Bir `time_point` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[max](#max)|İçin `time_point::ref`üst sınırı belirtir.|
|[min](#min)|İçin `time_point::ref`alt sınırı belirtir.|
|[time_since_epoch](#time_since_epoch)|Depolanan `duration` değeri döndürür.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[time_point::operator+=](#op_add_eq)|Depolanan süreye belirtilen bir değer ekler.|
|[time_point::operator-=](#operator-_eq)|Belirtilen bir değeri depolanan süreden çıkartır.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<> hatası

**Ad alanı:** std:: hatası

## <a name="max"></a>time_point:: Max

Türündeki `time_point::ref`değerler için üst sınırı döndüren statik yöntem.

```cpp
static constexpr time_point max();
```

### <a name="return-value"></a>Dönüş Değeri

Aslında, döndürür `time_point(duration::max())`.

## <a name="min"></a>time_point:: min

Türündeki `time_point::ref`değerler için alt sınır döndüren statik yöntem.

```cpp
static constexpr time_point min();
```

### <a name="return-value"></a>Dönüş Değeri

Aslında, döndürür `time_point(duration::min())`.

## <a name="op_add_eq"></a>  time_point::operator+=

Saklı [süre](../standard-library/duration-class.md) değerine belirtilen bir değer ekler.

```cpp
time_point& operator+=(const duration& Dur);
```

### <a name="parameters"></a>Parametreler

*Hecesi*\
A `duration` nesne.

### <a name="return-value"></a>Dönüş Değeri

Ekleme gerçekleştirildikten sonra nesnesi. `time_point`

## <a name="operator-_eq"></a>  time_point::operator-=

Saklanan [süre](../standard-library/duration-class.md) değerinden belirtilen değeri çıkartır.

```cpp
time_point& operator-=(const duration& Dur);
```

### <a name="parameters"></a>Parametreler

*Hecesi*\
A `duration` nesne.

### <a name="return-value"></a>Dönüş Değeri

Çıkarma gerçekleştirildikten sonra nesnesi. `time_point`

## <a name="time_point"></a>time_point:: time_point Oluşturucusu

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
A `time_point` nesne.

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu, saklı `duration` değeri [Duration:: Zero](../standard-library/duration-class.md#zero)değerine eşit olan bir nesne oluşturur.

İkinci Oluşturucu, saklı süresi değeri *süre*' ne eşit olan bir nesne oluşturur. Doğru `is_convertible<Duration2, duration>` tutmadığı müddetçe, ikinci Oluşturucu aşırı yükleme çözümüne katılmaz. Daha fazla bilgi için bkz. [< type_traits >](../standard-library/type-traits.md).

Üçüncü Oluşturucu, kullanarak `duration` `Tp.time_since_epoch()`değerini başlatır.

## <a name="time_since_epoch"></a>time_point::time_since_epoch

Saklı [süre](../standard-library/duration-class.md) değerini alır.

```cpp
constexpr duration time_since_epoch() const;
```

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)\
[\<> hatası](../standard-library/chrono.md)
