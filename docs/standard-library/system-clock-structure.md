---
title: system_clock Yapısı
ms.date: 11/04/2016
f1_keywords:
- chrono/std::chrono::system_clock
- chrono/std::chrono::system_clock::from_time_t
- chrono/std::chrono::system_clock::now
- chrono/std::chrono::system_clock::to_time_t
- chrono/std::chrono::system_clock::is_monotonic Constant
- chrono/std::chrono::system_clock::is_steady Constant
ms.assetid: a97bd46e-267a-4836-9f7d-af1f664e99ae
ms.openlocfilehash: ca516551bb1b41d96b99aaf7b842666c9341ee7d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376523"
---
# <a name="system_clock-structure"></a>system_clock Yapısı

Sistemin gerçek zamanlı saatini temel alan bir *saat türünü* temsil eder.

## <a name="syntax"></a>Sözdizimi

```cpp
struct system_clock;
```

## <a name="remarks"></a>Açıklamalar

Geçerli saati UTC olarak elde etmek için *saat türü* kullanılır. Tür, [süre](../standard-library/duration-class.md) ve sınıf [şablonu time_point](../standard-library/time-point-class.md)bir anlık temsil eder ve `now()` zamanı döndüren statik bir üye işlev tanımlar.

İlk çağrıyla döndürülen değer, bir sonraki çağrı `now()` yla döndürülen değerden her zaman daha az veya `now()`eşitse, saat *monotondur.*

Bir saat *monotonise* *sabitse* ve saat keneler arasındaki zaman sabitse sabittir.

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Genel Typedefs

|Adı|Açıklama|
|----------|-----------------|
|`system_clock::duration`|Bir eşanlamlı `duration<rep, period>`.|
|`system_clock::period`|'nin içerdiği anlık `duration`olarak kene dönemini temsil etmek için kullanılan türiçin eşanlamlı.|
|`system_clock::rep`|'nin içerdiği anlık `duration`saat işaretçisi sayısını temsil etmek için kullanılan tür için eşanlamlı.|
|`system_clock::time_point`|Saat türünün kendisi `time_point<Clock, duration>`veya `Clock` aynı çağa dayanan ve aynı iç içe `duration` türüne sahip başka bir saat türü için eşanlamlı olan , eşanlamlısı olan bir eşanlamlıdır.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[from_time_t](#from_time_t)|Statik. En `time_point` yakından belirli bir süreye yakın bir verir.|
|[Nwo](#now)|Statik. Geçerli saati döndürür.|
|[to_time_t](#to_time_t)|Statik. Belirtilen `time_t` nesneye en yakın olan `time_point`nesneyi döndürür.|

### <a name="public-constants"></a>Genel Sabitler

|Adı|Açıklama|
|----------|-----------------|
|[system_clock::is_monotonic Sabit](#is_monotonic_constant)|Saat türünün monoton olup olmadığını belirtir.|
|[system_clock::is_steady Sabit](#is_steady_constant)|Saat türünün sabit olup olmadığını belirtir.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<chrono>

**Ad alanı:** std::chrono

## <a name="system_clockfrom_time_t"></a><a name="from_time_t"></a>system_clock:from_time_t

*Tm*tarafından temsil edilen süreye en yakın olan [time_point](../standard-library/time-point-class.md) döndüren statik yöntem.

```cpp
static time_point from_time_t(time_t Tm) noexcept;
```

### <a name="parameters"></a>Parametreler

*Tm*\
[time_t](../c-runtime-library/standard-types.md) bir nesne.

## <a name="system_clockis_monotonic-constant"></a><a name="is_monotonic_constant"></a>system_clock::is_monotonic Sabit

Saat türünün monoton olup olmadığını belirten statik değer.

```cpp
static const bool is_monotonic = false;
```

### <a name="return-value"></a>Dönüş Değeri

Bu uygulamada, `system_clock::is_monotonic` her zaman **yanlış**döndürür.

### <a name="remarks"></a>Açıklamalar

İlk çağrıyla döndürülen değer, bir sonraki çağrı `now()` yla döndürülen değerden her zaman daha az veya `now()`eşitse, saat *monotondur.*

## <a name="system_clockis_steady-constant"></a><a name="is_steady_constant"></a>system_clock::is_steady Sabit

Saat türünün *sabit*olup olmadığını belirten statik değer.

```cpp
static const bool is_steady = false;
```

### <a name="return-value"></a>Dönüş Değeri

Bu uygulamada, `system_clock::is_steady` her zaman **yanlış**döndürür.

### <a name="remarks"></a>Açıklamalar

Bir saat [monotonise](#is_monotonic_constant) *sabitse* ve saat keneler arasındaki zaman sabitse sabittir.

## <a name="system_clocknow"></a><a name="now"></a>system_clock::şimdi

Geçerli saati döndüren statik yöntem.

```cpp
static time_point now() noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli zamanı temsil eden [time_point](../standard-library/time-point-class.md) nesnesi.

## <a name="system_clockto_time_t"></a><a name="to_time_t"></a>system_clock:to_time_t

*Zaman*tarafından temsil edilen süreyi en yakından gösteren [bir time_t](../c-runtime-library/standard-types.md) döndüren statik yöntem.

```cpp
static time_t to_time_t(const time_point& Time) noexcept;
```

### <a name="parameters"></a>Parametreler

*Zaman*\
[time_point](../standard-library/time-point-class.md) bir nesne.

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi Dosyaları Başvurusu](../standard-library/cpp-standard-library-header-files.md)\
[\<chrono>](../standard-library/chrono.md)\
[steady_clock yapısı](../standard-library/steady-clock-struct.md)
