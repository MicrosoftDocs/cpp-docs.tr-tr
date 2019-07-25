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
ms.openlocfilehash: 7a9fd83840883de5172df8b2e1e451984a95ea47
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68450182"
---
# <a name="systemclock-structure"></a>system_clock Yapısı

Sistemin gerçek zamanlı saatini temel alan bir *Saat türünü* temsil eder.

## <a name="syntax"></a>Sözdizimi

```cpp
struct system_clock;
```

## <a name="remarks"></a>Açıklamalar

*Saat türü* , GEÇERLI saati UTC olarak almak için kullanılır. Tür, [Duration](../standard-library/duration-class.md) ve [time_point](../standard-library/time-point-class.md)sınıf şablonu için bir örneklemeyi içerir ve süreyi döndüren statik bir üye işlevini `now()` tanımlar.

Bir saat, bir ilk çağrı `now()` tarafından döndürülen değer her zaman bir sonraki çağrısıyla `now()`döndürülen değerden küçük veya ona eşit ise *monoton* 'dir.

Bir saat *monoton* ise ve saat işaretleri arasındaki süre sabittir ise *sabit olur.*

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Ortak tür tanımları

|Ad|Açıklama|
|----------|-----------------|
|`system_clock::duration`|İçin `duration<rep, period>`bir eş anlamlı.|
|`system_clock::period`|Öğesinin `duration`içerilen örneklemesinde değer dönemini temsil etmek için kullanılan türün eş anlamlısı.|
|`system_clock::rep`|İçinde bulunan örneklemede `duration`saat sayısını temsil etmek için kullanılan türün bir eş anlamlı değeri.|
|`system_clock::time_point`|İçin `time_point<Clock, duration>`bir eş anlamlı `Clock` , veya aynı dönemi temel alan ve aynı iç içe `duration` türe sahip olan başka bir saat türü için bir eş anlamlı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[from_time_t](#from_time_t)|Se. Belirtilen bir `time_point` zamana en yakın bir değer döndürür.|
|[sunuldu](#now)|Se. Geçerli saati döndürür.|
|[to_time_t](#to_time_t)|Se. `time_t` Belirtilen`time_point`bir nesne döndürür.|

### <a name="public-constants"></a>Genel sabitler

|Ad|Açıklama|
|----------|-----------------|
|[system_clock:: is_monotonic sabiti](#is_monotonic_constant)|Saat türünün monotonic olup olmadığını belirtir.|
|[system_clock:: is_steady sabiti](#is_steady_constant)|Saat türünün kararlı olup olmadığını belirtir.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<> hatası

**Ad alanı:** std:: hatası

## <a name="from_time_t"></a>system_clock::from_time_t

*TM*tarafından temsil edilen zamanı en yakından karşılayan bir [time_point](../standard-library/time-point-class.md) döndüren statik yöntem.

```cpp
static time_point from_time_t(time_t Tm) noexcept;
```

### <a name="parameters"></a>Parametreler

*TM*\
Bir [time_t](../c-runtime-library/standard-types.md) nesnesi.

## <a name="is_monotonic_constant"></a>system_clock:: is_monotonic sabiti

Saat türünün monotonic olup olmadığını belirten statik değer.

```cpp
static const bool is_monotonic = false;
```

### <a name="return-value"></a>Dönüş Değeri

Bu uygulamada `system_clock::is_monotonic` her zaman **false**değerini döndürür.

### <a name="remarks"></a>Açıklamalar

Bir saat, bir ilk çağrı `now()` tarafından döndürülen değer her zaman bir sonraki çağrısıyla `now()`döndürülen değerden küçük veya ona eşit ise *monoton* 'dir.

## <a name="is_steady_constant"></a>system_clock:: is_steady sabiti

Saat türünün *kararlı*olup olmadığını belirten statik değer.

```cpp
static const bool is_steady = false;
```

### <a name="return-value"></a>Dönüş Değeri

Bu uygulamada `system_clock::is_steady` her zaman **false**değerini döndürür.

### <a name="remarks"></a>Açıklamalar

Bir saat [monoton](#is_monotonic_constant) ise ve saat işaretleri arasındaki süre sabittir ise *sabit olur.*

## <a name="now"></a>system_clock:: Now

Geçerli saati döndüren statik yöntem.

```cpp
static time_point now() noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli saati temsil eden bir [time_point](../standard-library/time-point-class.md) nesnesi.

## <a name="to_time_t"></a>system_clock::to_time_t

*Zamana*göre temsil edilen zamana en yakın bir [time_t](../c-runtime-library/standard-types.md) döndüren statik yöntem.

```cpp
static time_t to_time_t(const time_point& Time) noexcept;
```

### <a name="parameters"></a>Parametreler

*Işınızda*\
Bir [time_point](../standard-library/time-point-class.md) nesnesi.

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)\
[\<> hatası](../standard-library/chrono.md)\
[steady_clock yapısı](../standard-library/steady-clock-struct.md)
