---
title: Etkinlik sınıfı
description: C++ derleme öngörüleri SDK 'Sı etkinlik sınıfı başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- Activity
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: ce7e4083411f1654064ca4628d10a767c7be1b7f
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2020
ms.locfileid: "92923403"
---
# <a name="activity-class"></a>Etkinlik sınıfı

::: moniker range="<=msvc-140"

C++ Build Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio **Sürüm** Seçicisi denetimini visual Studio 2017 veya visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=msvc-150"

`Activity`Sınıfı, [matchevent](../functions/match-event.md), [matcheventınmemberfunction](../functions/match-event-in-member-function.md), [Matcheventstack](../functions/match-event-stack.md)ve [matcheventstackinmemberfunction](../functions/match-event-stack-in-member-function.md) işlevleriyle birlikte kullanılır. Herhangi bir etkinlik olayını eşleştirmek için kullanın. Sınıfıyla eşleştirileceği tüm olayları görmek için [olay tablosuna](../event-table.md) bakın `Activity` .

## <a name="syntax"></a>Syntax

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

Sınıftaki birçok üye işlevi `Activity` bir değer sayısı döndürür. C++ derleme öngörüleri, Windows 'un performans sayacını bir ölçü kaynakları olarak kullanır. Değer sayısı, saniye gibi bir zaman birimine dönüştürmek için bir değer sıklığı ile birlikte kullanılmalıdır. `TickFrequency` [Olay](event.md) temel sınıfında bulunan üye işlevi, değer sıklığı elde etmek için çağrılabilir. [EVENT_DATA](../c-event-data-types/event-data-struct.md#tick-conversion-example) sayfasında, işaret sayısını zaman birimine dönüştürme örneği gösterilmektedir.

İşaretleri zaman birimlerine dönüştürmek istemiyorsanız, `Activity` sınıfı nanosaniye cinsinden zaman değerlerini döndüren üye işlevleri sağlar. Standart C++ kitaplığını kullanarak `chrono` bunları diğer zaman birimlerine dönüştürebilirsiniz.

## <a name="members"></a>Üyeler

[Olay](event.md) temel sınıfından devralınan üyeleri ile birlikte, `Activity` sınıfı aşağıdaki üyeleri içerir:

### <a name="constructor"></a>Oluşturucu

[Etkinlik](#activity)

### <a name="functions"></a>İşlevler

[CPUTicks](#cpu-ticks)\
[CPUTime](#cpu-time)\
[Sürenin](#duration)\
[ExclusiveCPUTicks](#exclusive-cpu-ticks)\
[ExclusiveCPUTime](#exclusive-cpu-time)\
[ExclusiveDuration](#exclusive-duration)\
[ExclusiveDurationTicks](#exclusive-duration-ticks)\
[Exclusiveduvar Clocktimeresponbili](#exclusive-wall-clock-time-responsibility)\
[Exclusiveduvar Clocktimeresponsibilityticks](#exclusive-wall-clock-time-responsibility-ticks)\
[StartTimestamp](#start-timestamp)\
[StopTimestamp](#stop-timestamp)\
[Duvar Clocktimeresponbili](#wall-clock-time-responsibility)\
[Duvar Clocktimeresponsibilityticks](#wall-clock-time-responsibility-ticks)

## <a name="activity"></a><a name="activity"></a> Etkinlik

```cpp
Activity(const RawEvent& event);
```

### <a name="parameters"></a>Parametreler

*olay*\
Herhangi bir etkinlik olayı.

## <a name="cputicks"></a><a name="cpu-ticks"></a> CPUTicks

```cpp
const long long& CPUTicks() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu etkinlik sırasında oluşan CPU onay işareti sayısı. Bir CPU çentik, düzenli bir Tick 'ten farklıdır. CPU işaretleri yalnızca CPU bir etkinlikte kod yürütürken sayılır. Etkinlikle ilişkili iş parçacığı uyurken CPU işaretleri sayılmaz.

## <a name="cputime"></a><a name="cpu-time"></a> CPUTime

```cpp
std::chrono::nanoseconds CPUTime()() const;
```

### <a name="return-value"></a>Dönüş Değeri

CPU 'nun bu etkinliğin içinde kod yürütmesi için geçen süre. Bu değer, alt etkinliklerin ayrı iş parçacıklarında yürütülmesi durumunda etkinliğin süresinden daha yüksek olabilir. Değer nanosaniye cinsinden döndürülür.

## <a name="duration"></a><a name="duration"></a> Sürenin

```cpp
std::chrono::nanoseconds Duration() const;
```

### <a name="return-value"></a>Dönüş Değeri

Etkinliğin nanosaniye cinsinden süresi.

## <a name="exclusivecputicks"></a><a name="exclusive-cpu-ticks"></a> ExclusiveCPUTicks

```cpp
const long long& ExclusiveCPUTicks() const;
```

### <a name="return-value"></a>Dönüş Değeri

[Cputicks](#cpu-ticks)ile aynıdır, ancak alt etkınlıklerde gerçekleşen CPU işaretleriyle birlikte dahil değildir.

## <a name="exclusivecputime"></a><a name="exclusive-cpu-time"></a> ExclusiveCPUTime

```cpp
std::chrono::nanoseconds ExclusiveCPUTime() const;
```

### <a name="return-value"></a>Dönüş Değeri

[CpuTime](#cpu-time)ile aynıdır, ancak alt etkinliklerin CPU süresi dahil değildir.

## <a name="exclusiveduration"></a><a name="exclusive-duration"></a> ExclusiveDuration

```cpp
std::chrono::nanoseconds ExclusiveDuration() const;
```

### <a name="return-value"></a>Dönüş Değeri

Etkinliğin nanosaniye cinsinden süresi, alt etkinliklerde harcanan süre dahil değildir.

## <a name="exclusivedurationticks"></a><a name="exclusive-duration-ticks"></a> ExclusiveDurationTicks

```cpp
const long long& ExclusiveDurationTicks() const;
```

### <a name="return-value"></a>Dönüş Değeri

Alt etkinliklerde gerçekleşen onay işareti sayısı hariç, bu etkinlikte gerçekleşen onay işareti sayısı.

## <a name="exclusivewallclocktimeresponsibility"></a><a name="exclusive-wall-clock-time-responsibility"></a> Exclusiveduvar Clocktimeresponbili

```cpp
std::chrono::nanoseconds ExclusiveWallClockTimeResponsibility() const;
```

### <a name="return-value"></a>Dönüş Değeri

Duvarsaatiyle [Timeesponbilili](#wall-clock-time-responsibility)ile aynıdır, ancak alt etkinliklerin duvar saati zaman sorumluluğunu dahil etmez.

## <a name="exclusivewallclocktimeresponsibilityticks"></a><a name="exclusive-wall-clock-time-responsibility-ticks"></a> Exclusiveduvar Clocktimeresponsibilityticks

```cpp
const long long& ExclusiveWallClockTimeResponsibilityTicks() const;
```

### <a name="return-value"></a>Dönüş Değeri

Çocuk etkinliklerinin duvar saati zaman sorumluluğu işaretlerini dahil değil, [Duvarclocktimeresponsibilityticks](#wall-clock-time-responsibility-ticks)ile aynıdır.

## <a name="starttimestamp"></a><a name="start-timestamp"></a> StartTimestamp

```cpp
const long long& StartTimestamp() const;
```

### <a name="return-value"></a>Dönüş Değeri

Etkinlik başlatıldığı sırada yakalanan bir değer çizgisi.

## <a name="stoptimestamp"></a><a name="stop-timestamp"></a> StopTimestamp

```cpp
const long long& StopTimestamp() const;
```

### <a name="return-value"></a>Dönüş Değeri

Etkinliğin durdurulduğu zamanda yakalanan bir değer çizgisi.

## <a name="wallclocktimeresponsibility"></a><a name="wall-clock-time-responsibility"></a> Duvar Clocktimeresponbili

```cpp
std::chrono::nanoseconds WallClockTimeResponsibility() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu etkinliğin, nanosaniye cinsinden duvar saati zaman sorumluluğu. Duvar saati zaman sorumluluğunun anlamı hakkında daha fazla bilgi için bkz. [duvar Clocktimeresponsibilityticks](#wall-clock-time-responsibility-ticks).

## <a name="wallclocktimeresponsibilityticks"></a><a name="wall-clock-time-responsibility-ticks"></a> Duvar Clocktimeresponsibilityticks

```cpp
const long long& WallClockTimeResponsibilityTicks() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu etkinliğin genel duvar saati saatine katkısı temsil eden bir değer sayısı. Bir duvar saati zaman sorumluluğu çentik, düzenli bir Tick 'ten farklıdır. Duvar saati zaman sorumluluk işaretleri, etkinlikler arasında paralellik hesaba sahiptir. İki paralel Etkinliğin süresi 50 saat ve aynı başlangıç ve bitiş zamanı olabilir. Bu durumda, her ikisine de 25 saat için bir duvar saati saati sorumluluğu atanır.

::: moniker-end
