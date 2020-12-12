---
description: 'Daha fazla bilgi edinin: system_clock yapısı'
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
ms.openlocfilehash: 54d15f5e5ccc75e056cbdcc1d56d05e0a343c76b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97183210"
---
# <a name="system_clock-structure"></a>system_clock Yapısı

Sistemin gerçek zamanlı saatini temel alan bir *Saat türünü* temsil eder.

## <a name="syntax"></a>Syntax

```cpp
struct system_clock;
```

## <a name="remarks"></a>Açıklamalar

*Saat türü* , GEÇERLI saati UTC olarak almak için kullanılır. Tür bir [süre](../standard-library/duration-class.md) ve sınıf şablonu [time_point](../standard-library/time-point-class.md)örneklemeyi içerir ve süreyi döndüren statik bir üye işlevini tanımlar `now()` .

Bir saat,  bir ilk çağrı tarafından döndürülen değer `now()` her zaman bir sonraki çağrısıyla döndürülen değerden küçük veya ona eşit ise monoton 'dir `now()` .

Bir saat *monoton* ise ve saat işaretleri arasındaki süre *sabittir ise sabit olur.*

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Ortak tür tanımları

|Ad|Açıklama|
|----------|-----------------|
|`system_clock::duration`|İçin bir eş anlamlı `duration<rep, period>` .|
|`system_clock::period`|Öğesinin içerilen örneklemesinde değer dönemini temsil etmek için kullanılan türün eş anlamlısı `duration` .|
|`system_clock::rep`|İçinde bulunan örneklemede saat sayısını temsil etmek için kullanılan türün bir eş anlamlı değeri `duration` .|
|`system_clock::time_point`|İçin bir eş anlamlı `time_point<Clock, duration>` , `Clock` veya aynı dönemi temel alan ve aynı iç içe türe sahip olan başka bir saat türü için bir eş anlamlı `duration` .|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[from_time_t](#from_time_t)|Statik. Belirtilen bir `time_point` zamana en yakın bir değer döndürür.|
|[sunuldu](#now)|Statik. Geçerli saati döndürür.|
|[to_time_t](#to_time_t)|Statik. `time_t`Belirtilen bir nesne döndürür `time_point` .|

### <a name="public-constants"></a>Genel sabitler

|Ad|Açıklama|
|----------|-----------------|
|[system_clock:: is_monotonic sabiti](#is_monotonic_constant)|Saat türünün monotonic olup olmadığını belirtir.|
|[system_clock:: is_steady sabiti](#is_steady_constant)|Saat türünün kararlı olup olmadığını belirtir.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<chrono>

**Ad alanı:** std:: hatası

## <a name="system_clockfrom_time_t"></a><a name="from_time_t"></a> system_clock:: from_time_t

*TM* tarafından temsil edilen zamana en yakın bir [time_point](../standard-library/time-point-class.md) döndüren statik yöntem.

```cpp
static time_point from_time_t(time_t Tm) noexcept;
```

### <a name="parameters"></a>Parametreler

*TM*\
[Time_t](../c-runtime-library/standard-types.md) nesnesi.

## <a name="system_clockis_monotonic-constant"></a><a name="is_monotonic_constant"></a> system_clock:: is_monotonic sabiti

Saat türünün monotonic olup olmadığını belirten statik değer.

```cpp
static const bool is_monotonic = false;
```

### <a name="return-value"></a>Dönüş Değeri

Bu uygulamada `system_clock::is_monotonic` her zaman değerini döndürür **`false`** .

### <a name="remarks"></a>Açıklamalar

Bir saat,  bir ilk çağrı tarafından döndürülen değer `now()` her zaman bir sonraki çağrısıyla döndürülen değerden küçük veya ona eşit ise monoton 'dir `now()` .

## <a name="system_clockis_steady-constant"></a><a name="is_steady_constant"></a> system_clock:: is_steady sabiti

Saat türünün *kararlı* olup olmadığını belirten statik değer.

```cpp
static const bool is_steady = false;
```

### <a name="return-value"></a>Dönüş Değeri

Bu uygulamada `system_clock::is_steady` her zaman değerini döndürür **`false`** .

### <a name="remarks"></a>Açıklamalar

Bir saat [monoton](#is_monotonic_constant) ise ve saat işaretleri arasındaki süre *sabittir ise sabit olur.*

## <a name="system_clocknow"></a><a name="now"></a> system_clock:: Now

Geçerli saati döndüren statik yöntem.

```cpp
static time_point now() noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli saati temsil eden bir [time_point](../standard-library/time-point-class.md) nesnesi.

## <a name="system_clockto_time_t"></a><a name="to_time_t"></a> system_clock:: to_time_t

*Zamana* göre temsil edilen zamana en yakın bir [time_t](../c-runtime-library/standard-types.md) döndüren statik yöntem.

```cpp
static time_t to_time_t(const time_point& Time) noexcept;
```

### <a name="parameters"></a>Parametreler

*Işınızda*\
[Time_point](../standard-library/time-point-class.md) nesnesi.

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)\
[\<chrono>](../standard-library/chrono.md)\
[steady_clock yapısı](../standard-library/steady-clock-struct.md)
