---
title: Etkinlik sınıfı
description: C++ Build Insights SDK Etkinlik sınıf başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- Activity
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 2ea04150aec9c0b2366d97e6e4c15de557a4f47c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81325255"
---
# <a name="activity-class"></a>Etkinlik sınıfı

::: moniker range="<=vs-2015"

C++ Build Insights SDK, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlere ait belgeleri görmek için, bu makalenin Visual Studio **Sürüm** seçici denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=vs-2017"

Sınıf `Activity` [MatchEvent,](../functions/match-event.md) [MatchEventInMemberFunction,](../functions/match-event-in-member-function.md) [MatchEventStack](../functions/match-event-stack.md)ve [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) işlevleri ile kullanılır. Herhangi bir etkinlik olayı yla eşleştirmek için kullanın. Sınıftarafından eşleşebilecek tüm olayları görmek için `Activity` [etkinlik tablosuna](../event-table.md) bakın.

## <a name="syntax"></a>Sözdizimi

```cpp
class Activity : public Event
{
public:
    Activity(const RawEvent& event);

    const long long& StartTimestamp() const;
    const long long& StopTimestamp() const;
    const long long& ExclusiveDurationTicks() const;
    const long long& CPUTicks() const;
    const long long& ExclusiveCPUTicks() const;
    const long long& WallClockTimeResponsibilityTicks() const;
    const long long& ExclusiveWallClockTimeResponsibilityTicks() const;

    std::chrono::nanoseconds Duration() const;
    std::chrono::nanoseconds ExclusiveDuration() const;
    std::chrono::nanoseconds CPUTime() const ;
    std::chrono::nanoseconds ExclusiveCPUTime() const;
    std::chrono::nanoseconds WallClockTimeResponsibility() const;
    std::chrono::nanoseconds ExclusiveWallClockTimeResponsibility() const;
};
```

## <a name="remarks"></a>Açıklamalar

Sınıftaki `Activity` birkaç üye işlev kene sayısını döndürer. C++ Build Insights, Windows'un performans sayacını onay kaynağı olarak kullanır. Kene sayısı, saniye gibi bir zaman birimine dönüştürmek için kene sıklığı ile kullanılmalıdır. Olay `TickFrequency` taban sınıfında bulunan [Event](event.md) üye işlev, kene sıklığını elde etmek için çağrılabilir. EVENT_DATA [EVENT_DATA](../c-event-data-types/event-data-struct.md#tick-conversion-example) sayfası, keneleri bir zaman birimine dönüştürme örneğini gösterir.

Keneleri zaman birimlerine kendiniz dönüştürmek istemiyorsanız, `Activity` sınıf nanosaniye cinsinden zaman değerlerini döndüren üye işlevler sağlar. Diğer zaman birimlerine dönüştürmek için standart C++ `chrono` kitaplığını kullanın.

## <a name="members"></a>Üyeler

[Olay](event.md) taban sınıfından devralınan üyeleriyle `Activity` birlikte, sınıf aşağıdaki üyeleri içerir:

### <a name="constructor"></a>Oluşturucu

[Etkinlik](#activity)

### <a name="functions"></a>İşlevler

[CPUTicks](#cpu-ticks)\
[CPUTime](#cpu-time)\
[Süre](#duration)\
[ExclusiveCPUTicks](#exclusive-cpu-ticks)\
[ExclusiveCPUTime](#exclusive-cpu-time)\
[ÖzelSüre](#exclusive-duration)\
[ExclusiveDurationTicks](#exclusive-duration-ticks)\
[ExclusiveWallClockTimeResponsibility](#exclusive-wall-clock-time-responsibility)\
[ExclusiveWallClockTimeResponsibilityTicks](#exclusive-wall-clock-time-responsibility-ticks)\
[Başlangıç Zamanı Damgası](#start-timestamp)\
[StopTimestamp](#stop-timestamp)\
[WallClockTimeResponsibility](#wall-clock-time-responsibility)\
[WallClockTimeResponsibilityTicks](#wall-clock-time-responsibility-ticks)

## <a name="activity"></a><a name="activity"></a>Etkinlik

```cpp
Activity(const RawEvent& event);
```

### <a name="parameters"></a>Parametreler

*Olay*\
Herhangi bir etkinlik olayı.

## <a name="cputicks"></a><a name="cpu-ticks"></a>CPUTicks

```cpp
const long long& CPUTicks() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu etkinlik sırasında oluşan CPU işaretlerinin sayısı. CPU işareti normal bir keneden farklıdır. CPU tikleri yalnızca CPU bir etkinlikte kod yürütüldüğünde sayılır. Etkinlikle ilişkili iş parçacığı uyku dayadığında CPU tikleri sayılmaz.

## <a name="cputime"></a><a name="cpu-time"></a>CPUTime

```cpp
std::chrono::nanoseconds CPUTime()() const;
```

### <a name="return-value"></a>Dönüş Değeri

CPU'nun bu etkinlik içinde kodu yürütme süresi. Alt etkinlikler ayrı iş parçacıkları üzerinde yürütülürse, bu değer etkinlik süresinden daha yüksek olabilir. Değer nanosaniye cinsinden döndürülür.

## <a name="duration"></a><a name="duration"></a>Süre

```cpp
std::chrono::nanoseconds Duration() const;
```

### <a name="return-value"></a>Dönüş Değeri

Nanosaniye cinsinden etkinliğin süresi.

## <a name="exclusivecputicks"></a><a name="exclusive-cpu-ticks"></a>ExclusiveCPUTicks

```cpp
const long long& ExclusiveCPUTicks() const;
```

### <a name="return-value"></a>Dönüş Değeri

[CPUTicks](#cpu-ticks)ile aynı, ancak alt etkinliklerde oluşan CPU ticks dahil değil.

## <a name="exclusivecputime"></a><a name="exclusive-cpu-time"></a>ExclusiveCPUTime

```cpp
std::chrono::nanoseconds ExclusiveCPUTime() const;
```

### <a name="return-value"></a>Dönüş Değeri

[CPUTime](#cpu-time)ile aynıdır, ancak alt etkinliklerin CPU zamanı dahil değildir.

## <a name="exclusiveduration"></a><a name="exclusive-duration"></a>ÖzelSüre

```cpp
std::chrono::nanoseconds ExclusiveDuration() const;
```

### <a name="return-value"></a>Dönüş Değeri

Alt etkinliklerde harcanan süreyi dahil etmek üzere nanosaniye cinsinden etkinliğin süresi.

## <a name="exclusivedurationticks"></a><a name="exclusive-duration-ticks"></a>ExclusiveDurationTicks

```cpp
const long long& ExclusiveDurationTicks() const;
```

### <a name="return-value"></a>Dönüş Değeri

Alt etkinliklerde oluşan kene sayısı hariç, bu etkinlikte oluşan kene sayısı.

## <a name="exclusivewallclocktimeresponsibility"></a><a name="exclusive-wall-clock-time-responsibility"></a>ExclusiveWallClockTimeResponsibility

```cpp
std::chrono::nanoseconds ExclusiveWallClockTimeResponsibility() const;
```

### <a name="return-value"></a>Dönüş Değeri

[WallClockTimeResponsibility](#wall-clock-time-responsibility)ile aynı , ancak çocuk faaliyetlerinin duvar saati zaman sorumluluğu hariç değildir.

## <a name="exclusivewallclocktimeresponsibilityticks"></a><a name="exclusive-wall-clock-time-responsibility-ticks"></a>ExclusiveWallClockTimeResponsibilityTicks

```cpp
const long long& ExclusiveWallClockTimeResponsibilityTicks() const;
```

### <a name="return-value"></a>Dönüş Değeri

[WallClockTimeResponsibilityTicks](#wall-clock-time-responsibility-ticks)ile aynı , ancak çocuk etkinliklerinin duvar saati zaman sorumluluğu keneler dahil değildir.

## <a name="starttimestamp"></a><a name="start-timestamp"></a>Başlangıç Zamanı Damgası

```cpp
const long long& StartTimestamp() const;
```

### <a name="return-value"></a>Dönüş Değeri

Etkinlik başladığında yakalanan bir onay değeri.

## <a name="stoptimestamp"></a><a name="stop-timestamp"></a>StopTimestamp

```cpp
const long long& StopTimestamp() const;
```

### <a name="return-value"></a>Dönüş Değeri

Etkinlik durdurulduğu sırada yakalanan bir onay değeri.

## <a name="wallclocktimeresponsibility"></a><a name="wall-clock-time-responsibility"></a>WallClockTimeResponsibility

```cpp
std::chrono::nanoseconds WallClockTimeResponsibility() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu etkinliğin duvar saati zaman sorumluluğu, nanosaniye cinsinden. Duvar saati zamanı sorumluluğunun ne anlama geldiğini hakkında daha fazla bilgi için [WallClockTimeResponsibilityTicks'e](#wall-clock-time-responsibility-ticks)bakın.

## <a name="wallclocktimeresponsibilityticks"></a><a name="wall-clock-time-responsibility-ticks"></a>WallClockTimeResponsibilityTicks

```cpp
const long long& WallClockTimeResponsibilityTicks() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu etkinliğin genel duvar saati zamanına katkısını temsil eden bir kene sayısı. Bir duvar saati zaman sorumluluk kene normal bir kene farklıdır. Duvar saati zaman sorumluluğu, etkinlikler arasındaki paralelliği dikkate alır. İki paralel etkinlik 50 kene süresine ve aynı başlangıç ve durdurma süresine sahip olabilir. Bu durumda, her ikisi de 25 kene bir duvar saati zaman sorumluluğu atanır.

::: moniker-end
