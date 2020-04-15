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
ms.openlocfilehash: e1de674d4a13ba465100923bffe6cba76e61ab4a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368027"
---
# <a name="time_point-class"></a>time_point Sınıfı

A, `time_point` zaman daki bir noktayı temsil eden bir türü açıklar. Şablon bağımsız değişkeni tarafından temsil edilen çağdan bu yana geçen süreyi depolayan bir tür [süresi](../standard-library/duration-class.md) nesnesi `Clock`tutar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Clock,
    class Duration = typename Clock::duration>
class time_point;
```

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Genel Typedefs

|Adı|Açıklama|
|----------|-----------------|
|`time_point::clock`|Şablon parametresi `Clock`ile eş anlamlı.|
|`time_point::duration`|Şablon parametresi `Duration`ile eş anlamlı.|
|`time_point::period`|İç içe gelen tür adı `duration::period`ile eş anlamlı.|
|`time_point::rep`|İç içe gelen tür adı `duration::rep`ile eş anlamlı.|

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[Time_point](#time_point)|Bir `time_point` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[Max](#max)|Üst sınırı `time_point::ref`belirtir.|
|[Dk](#min)|Alt sınırı `time_point::ref`belirtir.|
|[time_since_epoch](#time_since_epoch)|Depolanan `duration` değeri verir.|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[time_point::operator+=](#op_add_eq)|Depolanan süreye belirli bir değer ekler.|
|[time_point::operator-=](#operator-_eq)|Depolanan süreden belirli bir değer çıkarır.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<chrono>

**Ad alanı:** std::chrono

## <a name="time_pointmax"></a><a name="max"></a>time_point::max

Tür `time_point::ref`değerleri için üst sınırı döndüren statik yöntem.

```cpp
static constexpr time_point max();
```

### <a name="return-value"></a>Dönüş Değeri

Aslında, döner. `time_point(duration::max())`

## <a name="time_pointmin"></a><a name="min"></a>time_point::dk

Tür `time_point::ref`değerleri için alt sınırı döndüren statik yöntem.

```cpp
static constexpr time_point min();
```

### <a name="return-value"></a>Dönüş Değeri

Aslında, döner. `time_point(duration::min())`

## <a name="time_pointoperator"></a><a name="op_add_eq"></a>time_point::operator+=

Depolanan [süre](../standard-library/duration-class.md) değerine belirli bir değer ekler.

```cpp
time_point& operator+=(const duration& Dur);
```

### <a name="parameters"></a>Parametreler

*Dur*\
Bir `duration` nesnesi.

### <a name="return-value"></a>Dönüş Değeri

Ekleme `time_point` yapıldıktan sonra nesne.

## <a name="time_pointoperator-"></a><a name="operator-_eq"></a>time_point::operator-=

Depolanan [süre](../standard-library/duration-class.md) değerinden belirli bir değer çıkarır.

```cpp
time_point& operator-=(const duration& Dur);
```

### <a name="parameters"></a>Parametreler

*Dur*\
Bir `duration` nesnesi.

### <a name="return-value"></a>Dönüş Değeri

Çıkarma `time_point` yapıldıktan sonra nesne.

## <a name="time_pointtime_point-constructor"></a><a name="time_point"></a>time_point::time_point Yapıcı

Bir `time_point` nesne inşa eder.

```cpp
constexpr time_point();

constexpr explicit time_point(const duration& Dur);

template <class Duration2>
constexpr time_point(const time_point<clock, Duration2>& Tp);
```

### <a name="parameters"></a>Parametreler

*Dur*\
[Bir süre nesnesi.](../standard-library/duration-class.md)

*Tp*\
Bir `time_point` nesnesi.

### <a name="remarks"></a>Açıklamalar

İlk oluşturucu, depolanan `duration` değeri süreye eşit olan bir nesne yi inşa [eder::sıfır.](../standard-library/duration-class.md#zero)

İkinci oluşturucu, depolanan süre değeri *Dur'a*eşit olan bir nesne inşa eder. Geçerli `is_convertible<Duration2, duration>` olmadığı sürece, ikinci yapıcı aşırı yük çözünürlüğüne katılmaz. Daha fazla bilgi için [<type_traits>](../standard-library/type-traits.md)bakın.

Üçüncü oluşturucu kullanarak değerini `duration` ilk `Tp.time_since_epoch()`olarak çözer.

## <a name="time_pointtime_since_epoch"></a><a name="time_since_epoch"></a>time_point:time_since_epoch

Depolanan [süre](../standard-library/duration-class.md) değerini alır.

```cpp
constexpr duration time_since_epoch() const;
```

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi Dosyaları Başvurusu](../standard-library/cpp-standard-library-header-files.md)\
[\<chrono>](../standard-library/chrono.md)
