---
title: time_point sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
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
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
helpviewer_keywords:
- std::chrono [C++], time_point
ms.workload:
- cplusplus
ms.openlocfilehash: 9e01a168312f83d375f40102705f3ac52138f0eb
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="timepoint-class"></a>time_point Sınıfı

A `time_point` bir noktası zamanında temsil eden bir tür açıklar. Türünde bir nesne tutan [süresi](../standard-library/duration-class.md) , depolar geçen süre Şablon değişkeni tarafından temsil edilen dönem itibaren `Clock`.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Clock,
    class Duration = typename Clock::duration>
class time_point;
```

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Genel tür tanımları

|Ad|Açıklama|
|----------|-----------------|
|`time_point::clock`|Şablon parametresi için eş anlamlı `Clock`.|
|`time_point::duration`|Şablon parametresi için eş anlamlı `Duration`.|
|`time_point::period`|İç içe geçmiş tür adı için eş anlamlı `duration::period`.|
|`time_point::rep`|İç içe geçmiş tür adı için eş anlamlı `duration::rep`.|

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[time_point](#time_point)|Oluşturan bir `time_point` nesnesi.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[max](#max)|Üst sınırını belirtir `time_point::ref`.|
|[Min](#min)|Alt sınırını belirtir `time_point::ref`.|
|[time_since_epoch](#time_since_epoch)|Saklı döndürür `duration` değeri.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[time_point::operator+=](#op_add_eq)|Belirtilen bir değeri saklanan süresi ekler.|
|[time_point::operator-=](#operator-_eq)|Saklanan süresi belirtilen değeri çıkarır.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<chrono >

**Namespace:** std::chrono

## <a name="max"></a>  time_point::Max

Türü değerleri için üst sınır döndüren statik yöntem `time_point::ref`.

```cpp
static constexpr time_point max();
```

### <a name="return-value"></a>Dönüş Değeri

Uygulamada döndürür `time_point(duration::max())`.

## <a name="min"></a>  time_point::Min

Alt sınır türü değerleri için döndüren statik yöntem `time_point::ref`.

```cpp
static constexpr time_point min();
```

### <a name="return-value"></a>Dönüş Değeri

Uygulamada döndürür `time_point(duration::min())`.

## <a name="op_add_eq"></a>  time_point::operator+=

Belirtilen bir değeri saklı ekler [süresi](../standard-library/duration-class.md) değeri.

```cpp
time_point& operator+=(const duration& Dur);
```

### <a name="parameters"></a>Parametreler

`Dur` A `duration` nesnesi.

### <a name="return-value"></a>Dönüş Değeri

`time_point` Eklenmesi gerçekleştirildikten sonra nesnesi.

## <a name="time_point__operator-_eq"></a>  time_point::operator-=

Saklı belirtilen değeri çıkarır [süresi](../standard-library/duration-class.md) değeri.

```cpp
time_point& operator-=(const duration& Dur);
```

### <a name="parameters"></a>Parametreler

`Dur` A `duration` nesnesi.

### <a name="return-value"></a>Dönüş Değeri

`time_point` Çıkarma işlemi yapıldıktan sonra nesnesi.

## <a name="time_point"></a>  time_point::time_point Oluşturucusu

Oluşturan bir `time_point` nesnesi.

```cpp
constexpr time_point();

constexpr explicit time_point(const duration& Dur);

template <class Duration2>
constexpr time_point(const time_point<clock, Duration2>& Tp);
```

### <a name="parameters"></a>Parametreler

`Dur` A [süre](../standard-library/duration-class.md) nesnesi.

`Tp` A `time_point` nesnesi.

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucusu bir nesne oluşturur, depolanan `duration` değerdir eşit [duration::zero](../standard-library/duration-class.md#zero).

İkinci oluşturucu saklanan süresi değeri eşit olan bir nesne oluşturur `Dur`. Sürece `is_convertible<Duration2, duration>` *doğru kalıp*, ikinci oluşturucu aşırı yük çözüm katılmıyor. Daha fazla bilgi için bkz: [< type_traits >](../standard-library/type-traits.md).

Üçüncü Oluşturucu başlatır, `duration` kullanarak değer `Tp.time_since_epoch()`.

## <a name="time_since_epoch"></a>  time_point::time_since_epoch

Saklı alır [süresi](../standard-library/duration-class.md) değeri.

```cpp
constexpr duration time_since_epoch() const;
```

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)<br/>
[\<chrono >](../standard-library/chrono.md)<br/>
