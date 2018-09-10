---
title: time_point sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- chrono/std::chrono::time_point
- chrono/std::chrono::time_point::time_point
- chrono/std::chrono::time_point::max
- chrono/std::chrono::time_point::min
- chrono/std::chrono::time_point::time_since_epoch
dev_langs:
- C++
ms.assetid: 18be1e52-57b9-489a-8a9b-f58894f0aaad
author: corob-msft
ms.author: corob
helpviewer_keywords:
- std::chrono [C++], time_point
ms.workload:
- cplusplus
ms.openlocfilehash: 72ce06a3f722bca0147d220fb8602ab9e30f8751
ms.sourcegitcommit: f0c90000125a9497bf61e41624de189a043703c0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/10/2018
ms.locfileid: "44319025"
---
# <a name="timepoint-class"></a>time_point Sınıfı

A `time_point` zamanda bir noktayı temsil eden bir türü açıklar. Bir nesne türü tutar [süresi](../standard-library/duration-class.md) şablon bağımsız değişkeni tarafından temsil edilen dönem bu yana geçen süreyi depolayan `Clock`.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Clock,
    class Duration = typename Clock::duration>
class time_point;
```

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Genel Typedefler

|Ad|Açıklama|
|----------|-----------------|
|`time_point::clock`|Şablon parametresi için eş anlamlı `Clock`.|
|`time_point::duration`|Şablon parametresi için eş anlamlı `Duration`.|
|`time_point::period`|İç içe geçmiş tür adı için eş anlamlı `duration::period`.|
|`time_point::rep`|İç içe geçmiş tür adı için eş anlamlı `duration::rep`.|

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[time_point](#time_point)|Oluşturur bir `time_point` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[en fazla](#max)|Üst sınırını belirtir `time_point::ref`.|
|[Min](#min)|Alt sınırını belirtir `time_point::ref`.|
|[time_since_epoch](#time_since_epoch)|Depolanan döndürür `duration` değeri.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[time_point::operator+=](#op_add_eq)|Depolanan süreye belirtilen bir değer ekler.|
|[time_point::operator-=](#operator-_eq)|Belirtilen bir değeri depolanan süreden çıkarır.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<chrono >

**Namespace:** std::chrono

## <a name="max"></a>  time_point::Max

Türündeki değerlerin üst sınırını döndüren statik yöntem `time_point::ref`.

```cpp
static constexpr time_point max();
```

### <a name="return-value"></a>Dönüş Değeri

Aslında döndürür `time_point(duration::max())`.

## <a name="min"></a>  time_point::Min

Türündeki değerlerin alt sınırını döndüren statik yöntem `time_point::ref`.

```cpp
static constexpr time_point min();
```

### <a name="return-value"></a>Dönüş Değeri

Aslında döndürür `time_point(duration::min())`.

## <a name="op_add_eq"></a>  time_point::operator+=

Belirtilen bir değeri depolanan ekler [süresi](../standard-library/duration-class.md) değeri.

```cpp
time_point& operator+=(const duration& Dur);
```

### <a name="parameters"></a>Parametreler

*Süre*  
 A `duration` nesne.

### <a name="return-value"></a>Dönüş Değeri

`time_point` Toplama işlemi gerçekleştirildikten sonra nesne.

## <a name="time_point__operator-_eq"></a>  time_point::operator-=

Belirtilen bir değeri depolanan çıkarır [süresi](../standard-library/duration-class.md) değeri.

```cpp
time_point& operator-=(const duration& Dur);
```

### <a name="parameters"></a>Parametreler

*Süre*  
 A `duration` nesne.

### <a name="return-value"></a>Dönüş Değeri

`time_point` Çıkarma işlemi gerçekleştirildikten sonra nesne.

## <a name="time_point"></a>  time_point::time_point Oluşturucusu

Oluşturur bir `time_point` nesne.

```cpp
constexpr time_point();

constexpr explicit time_point(const duration& Dur);

template <class Duration2>
constexpr time_point(const time_point<clock, Duration2>& Tp);
```

### <a name="parameters"></a>Parametreler

*Süre*  
 A [süresi](../standard-library/duration-class.md) nesne.

*TP*  
 A `time_point` nesne.

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu bir nesne oluşturur, saklı `duration` değeri eşittir [duration::zero](../standard-library/duration-class.md#zero).

İkinci oluşturucu depolanmış süre değeri eşit olan bir nesne oluşturur *süre*. Sürece `is_convertible<Duration2, duration>` tutan true, İkinci kurucu aşırı yükleme çözünürlüğü içinde yer yok. Daha fazla bilgi için [< type_traits >](../standard-library/type-traits.md).

Üçüncü Oluşturucu başlatır, `duration` kullanarak değer `Tp.time_since_epoch()`.

## <a name="time_since_epoch"></a>  time_point::time_since_epoch

Depolanan alır [süresi](../standard-library/duration-class.md) değeri.

```cpp
constexpr duration time_since_epoch() const;
```

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)<br/>
[\<chrono >](../standard-library/chrono.md)<br/>
