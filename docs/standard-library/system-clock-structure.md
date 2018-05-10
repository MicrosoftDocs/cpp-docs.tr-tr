---
title: system_clock yapısı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- chrono/std::chrono::system_clock
- chrono/std::chrono::system_clock::from_time_t
- chrono/std::chrono::system_clock::now
- chrono/std::chrono::system_clock::to_time_t
- chrono/std::chrono::system_clock::is_monotonic Constant
- chrono/std::chrono::system_clock::is_steady Constant
dev_langs:
- C++
ms.assetid: a97bd46e-267a-4836-9f7d-af1f664e99ae
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 11ea0dd92eda9aad0cb85bbd1385cdec5af349df
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
---
# <a name="systemclock-structure"></a>system_clock Yapısı

Temsil eden bir *saat türü* sistem gerçek zamanlı saati dayanır.

## <a name="syntax"></a>Sözdizimi

```cpp
struct system_clock;
```

## <a name="remarks"></a>Açıklamalar

A *saat türü* geçerli saati UTC olarak elde etmek için kullanılır. Türü, bir örnek oluşturma içerir [süresi](../standard-library/duration-class.md) ve sınıf şablonu [time_point](../standard-library/time-point-class.md)ve statik üye işlevi tanımlar `now()` saati döndürür.

Bir saattir *monoton* durumunda ilk çağrı tarafından döndürülen değer `now()` her zaman bir sonraki çağrı tarafından döndürülen değer küçük veya buna eşit olan `now()`.

Bir saattir *sürekli* , *monoton* ve saat saat dilimleri arasında sabit ise.

Bu uygulamada bir `system_clock` ile çalışır bir `high_resolution_clock`.

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Genel tür tanımları

|Ad|Açıklama|
|----------|-----------------|
|`system_clock::duration`|Eşanlamlısı `duration<rep, period>`.|
|`system_clock::period`|Kapsanan örneği oluşturulmasını onay dönemde temsil etmek için kullanılan türü için eş anlamlı `duration`.|
|`system_clock::rep`|Kapsanan örneği oluşturulmasını, saat sayısı temsil etmek için kullanılan türü için eş anlamlı `duration`.|
|`system_clock::time_point`|Eşanlamlısı `time_point<Clock, duration>`, burada `Clock` saat türü veya üzerinde aynı dönem bağlı başka bir saat türü için eş anlamlı olduğundan ve aynı iç içe `duration` türü.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[from_time_t](#from_time_t)|Statik. Döndürür bir `time_point` en yakından benzeyen, belirli bir süre.|
|[Şimdi](#now)|Statik. Geçerli saati döndürür.|
|[to_time_t](#to_time_t)|Statik. Döndürür bir `time_t` en yakından belirtilen yakın nesne `time_point`.|

### <a name="public-constants"></a>Genel sabitler

|Ad|Açıklama|
|----------|-----------------|
|[system_clock::is_monotonic sabiti](#is_monotonic_constant)|Saat türü monoton olup olmadığını belirtir.|
|[system_clock::is_steady sabiti](#is_steady_constant)|Saat türü sürekli olup olmadığını belirtir.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<chrono >

**Namespace:** std::chrono

## <a name="from_time_t"></a>  system_clock::from_time_t

Döndüren statik yöntem bir [time_point](../standard-library/time-point-class.md) en yakından tarafından temsil edilen zaman yakın `Tm`.

```cpp
static time_point from_time_t(time_t Tm) noexcept;
```

### <a name="parameters"></a>Parametreler

`Tm` A [time_t](../c-runtime-library/standard-types.md) nesnesi.

## <a name="is_monotonic_constant"></a>  system_clock::is_monotonic sabiti

Saat türü monoton olup olmadığını belirtir, statik değer.

```cpp
static const bool is_monotonic = false;
```

### <a name="return-value"></a>Dönüş Değeri

Bu uygulamada `system_clock::is_monotonic` her zaman döndürür `false`.

### <a name="remarks"></a>Açıklamalar

Bir saattir *monoton* durumunda ilk çağrı tarafından döndürülen değer `now()` her zaman bir sonraki çağrı tarafından döndürülen değer küçük veya buna eşit olan `now()`.

## <a name="is_steady_constant"></a>  system_clock::is_steady sabiti

Saat türü olup olmadığını belirtir statik değer *sürekli*.

```cpp
static const bool is_steady = false;
```

### <a name="return-value"></a>Dönüş Değeri

Bu uygulamada `system_clock::is_steady` her zaman döndürür `false`.

### <a name="remarks"></a>Açıklamalar

Bir saattir *sürekli* , [monoton](#is_monotonic_constant) ve saat saat dilimleri arasında sabit ise.

## <a name="now"></a>  system_clock::Now

Geçerli saati döndürür statik yöntem.

```cpp
static time_point now() noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

A [time_point](../standard-library/time-point-class.md) geçerli saati temsil eden nesne.

## <a name="to_time_t"></a>  system_clock::to_time_t

Döndüren statik yöntem bir [time_t](../c-runtime-library/standard-types.md) en yakından tarafından temsil edilen zaman yakın `Time`.

```cpp
static time_t to_time_t(const time_point& Time) noexcept;
```

### <a name="parameters"></a>Parametreler

`Time` A [time_point](../standard-library/time-point-class.md) nesnesi.

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)<br/>
[\<chrono >](../standard-library/chrono.md)<br/>
[steady_clock yapısı](../standard-library/steady-clock-struct.md)<br/>
