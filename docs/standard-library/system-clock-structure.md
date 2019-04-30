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
ms.openlocfilehash: 66710f94d96f069d6d388d6b49c76747c618a0d0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62412156"
---
# <a name="systemclock-structure"></a>system_clock Yapısı

Temsil eden bir *saat türü* sistemin gerçek zamanlı saatini temel alır.

## <a name="syntax"></a>Sözdizimi

```cpp
struct system_clock;
```

## <a name="remarks"></a>Açıklamalar

A *saat türü* UTC olarak geçerli zamanı almak için kullanılır. Türü örneklemesi şekillendiren [süresi](../standard-library/duration-class.md) ve sınıf şablonu [time_point](../standard-library/time-point-class.md)ve bir statik üye işlevini tanımlar `now()` saati döndürür.

Bir saat *monoton* varsa bir ilk çağrı tarafından döndürülen değer `now()` her zaman sonraki çağrı tarafından döndürülen değer küçük veya ona eşit olduğundan `now()`.

Bir saat *sürekli* ise *monoton* ve saatin tik takları arasındaki zaman sabittir.

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Genel Typedefler

|Ad|Açıklama|
|----------|-----------------|
|`system_clock::duration`|İçin bir eşanlamlı `duration<rep, period>`.|
|`system_clock::period`|İçinde içerilen tik Tak dönemini temsil etmek için kullanılan türe ilişkin bir eşanlam `duration`.|
|`system_clock::rep`|İçinde içerilen saat tik taklarının sayısını belirtmek için kullanılan türe ilişkin bir eşanlam `duration`.|
|`system_clock::time_point`|İçin bir eşanlamlı `time_point<Clock, duration>`burada `Clock` saat türünün kendisi veya aynı dönemi temel alan bir diğer saat türü eşanlamlıdır ve aynı iç içe toplamalar `duration` türü.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[from_time_t](#from_time_t)|Statik. Döndürür bir `time_point` en yakından benzeyen, belirli bir süre.|
|[Şimdi](#now)|Statik. Geçerli saati döndürür.|
|[to_time_t](#to_time_t)|Statik. Döndürür bir `time_t` en yakından benzeyen bir belirtilen nesne `time_point`.|

### <a name="public-constants"></a>Genel sabitler

|Ad|Açıklama|
|----------|-----------------|
|[system_clock::is_monotonic sabiti](#is_monotonic_constant)|Saat türünün monoton olup olmadığını belirtir.|
|[system_clock::is_steady sabiti](#is_steady_constant)|Saat türünün sürekli olup olmadığını belirtir.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<chrono >

**Namespace:** std::chrono

## <a name="from_time_t"></a>  system_clock::from_time_t

Döndüren statik yöntem bir [time_point](../standard-library/time-point-class.md) en yakından benzeyen tarafından temsil edilen zaman *Tm*.

```cpp
static time_point from_time_t(time_t Tm) noexcept;
```

### <a name="parameters"></a>Parametreler

*TM*<br/>
A [time_t](../c-runtime-library/standard-types.md) nesne.

## <a name="is_monotonic_constant"></a>  system_clock::is_monotonic sabiti

Saat türünün monoton mu olduğunu belirten statik değer.

```cpp
static const bool is_monotonic = false;
```

### <a name="return-value"></a>Dönüş Değeri

Bu uygulamada `system_clock::is_monotonic` her zaman döndürür **false**.

### <a name="remarks"></a>Açıklamalar

Bir saat *monoton* varsa bir ilk çağrı tarafından döndürülen değer `now()` her zaman sonraki çağrı tarafından döndürülen değer küçük veya ona eşit olduğundan `now()`.

## <a name="is_steady_constant"></a>  system_clock::is_steady sabiti

Saat türünün olduğunu belirten statik değer *sürekli*.

```cpp
static const bool is_steady = false;
```

### <a name="return-value"></a>Dönüş Değeri

Bu uygulamada `system_clock::is_steady` her zaman döndürür **false**.

### <a name="remarks"></a>Açıklamalar

Bir saat *sürekli* ise [monoton](#is_monotonic_constant) ve saatin tik takları arasındaki zaman sabittir.

## <a name="now"></a>  system_clock::Now

Geçerli zamanı döndüren statik yöntem.

```cpp
static time_point now() noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

A [time_point](../standard-library/time-point-class.md) geçerli zamanı temsil eden nesne.

## <a name="to_time_t"></a>  system_clock::to_time_t

Döndüren statik yöntem bir [time_t](../c-runtime-library/standard-types.md) en yakından benzeyen tarafından temsil edilen zaman *zaman*.

```cpp
static time_t to_time_t(const time_point& Time) noexcept;
```

### <a name="parameters"></a>Parametreler

*saat*<br/>
A [time_point](../standard-library/time-point-class.md) nesne.

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)<br/>
[\<chrono >](../standard-library/chrono.md)<br/>
[steady_clock yapısı](../standard-library/steady-clock-struct.md)<br/>
