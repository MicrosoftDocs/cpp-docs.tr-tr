---
title: Etkinlik sınıfı
description: C++ Build Insights SDK 'sı etkinlik sınıfı başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- Activity
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 6de411c375b42e4acfb44bf0fac9d28ad57f1ca7
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78333561"
---
# <a name="activity-class"></a>Etkinlik sınıfı

::: moniker range="<=vs-2015"

Build C++ Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio sürüm Seçicisi denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın.

::: moniker-end
::: moniker range=">=vs-2017"

`Activity` sınıfı [Matchevent](../functions/match-event.md), [matcheventınmemberfunction](../functions/match-event-in-member-function.md), [Matcheventstack](../functions/match-event-stack.md)ve [matcheventstackinmemberfunction](../functions/match-event-stack-in-member-function.md) işlevleriyle birlikte kullanılır. Herhangi bir etkinlik olayını eşleştirmek için kullanın. `Activity` sınıfıyla eşleştirileceği tüm olayları görmek için [olay tablosuna](../event-table.md) bakın.

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

`Activity` sınıfındaki çeşitli üye işlevleri bir değer sayısı döndürür. C++Derleme öngörüleri, Windows 'un performans sayacını bir ölçü kaynakları olarak kullanır. Değer sayısı, saniye gibi bir zaman birimine dönüştürmek için bir değer sıklığı ile birlikte kullanılmalıdır. [Olay](event.md) temel sınıfında bulunan `TickFrequency` üye işlevi, değer sıklığı elde etmek için çağrılabilir. [EVENT_DATA](../c-event-data-types/event-data-struct.md#tick-conversion-example) sayfasında, işaret sayısını zaman birimine dönüştürme örneği gösterilmektedir.

İşaretleri zaman birimlerine dönüştürmek istemiyorsanız, `Activity` sınıfı, nanosaniye olarak zaman değerlerini döndüren üye işlevleri sağlar. Bunları diğer zaman C++ birimlerine dönüştürmek için standart `chrono` kitaplığı kullanın.

## <a name="members"></a>Üyeler

[Olay](event.md) temel sınıfından devralınan üyeleri ile birlikte `Activity` sınıfı aşağıdaki üyeleri içerir:

### <a name="constructor"></a>Oluşturucu

[Etkinlik](#activity)

### <a name="functions"></a>İşlevler

[Cputicks](#cpu-ticks)\
[CpuTime](#cpu-time)\
[Süre](#duration)\
[ExclusiveCPUTicks](#exclusive-cpu-ticks)\
[ExclusiveCPUTime](#exclusive-cpu-time)\
[Exclusiveduration](#exclusive-duration)\
[ExclusiveDurationTicks](#exclusive-duration-ticks)\
[Exclusiveduvar Clocktimeresponbili](#exclusive-wall-clock-time-responsibility)\
[Exclusiveduvar Clocktimeresponsibilityticks](#exclusive-wall-clock-time-responsibility-ticks)\
[StartTimestamp](#start-timestamp)\
[Stoptimestamp](#stop-timestamp)\
[Duvar Clocktimeresponbili](#wall-clock-time-responsibility)\
[Duvar Clocktimeresponsibilityticks](#wall-clock-time-responsibility-ticks)

## <a name="activity"></a>Etkinlik

```cpp
Activity(const RawEvent& event);
```

### <a name="parameters"></a>Parametreler

*olay*\
Herhangi bir etkinlik olayı.

## <a name="cpu-ticks"></a>CPUTicks

```cpp
const long long& CPUTicks() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu etkinlik sırasında oluşan CPU onay işareti sayısı. Bir CPU çentik, düzenli bir Tick 'ten farklıdır. CPU işaretleri yalnızca CPU bir etkinlikte kod yürütürken sayılır. Etkinlikle ilişkili iş parçacığı uyurken CPU işaretleri sayılmaz.

## <a name="cpu-time"></a>CPUTime

```cpp
std::chrono::nanoseconds CPUTime()() const;
```

### <a name="return-value"></a>Dönüş Değeri

CPU 'nun bu etkinliğin içinde kod yürütmesi için geçen süre. Bu değer, alt etkinliklerin ayrı iş parçacıklarında yürütülmesi durumunda etkinliğin süresinden daha yüksek olabilir. Değer nanosaniye cinsinden döndürülür.

## <a name="duration"></a>Sürenin

```cpp
std::chrono::nanoseconds Duration() const;
```

### <a name="return-value"></a>Dönüş Değeri

Etkinliğin nanosaniye cinsinden süresi.

## <a name="exclusive-cpu-ticks"></a>ExclusiveCPUTicks

```cpp
const long long& ExclusiveCPUTicks() const;
```

### <a name="return-value"></a>Dönüş Değeri

[Cputicks](#cpu-ticks)ile aynıdır, ancak alt etkınlıklerde gerçekleşen CPU işaretleriyle birlikte dahil değildir.

## <a name="exclusive-cpu-time"></a>ExclusiveCPUTime

```cpp
std::chrono::nanoseconds ExclusiveCPUTime() const;
```

### <a name="return-value"></a>Dönüş Değeri

[CpuTime](#cpu-time)ile aynıdır, ancak alt etkinliklerin CPU süresi dahil değildir.

## <a name="exclusive-duration"></a>ExclusiveDuration

```cpp
std::chrono::nanoseconds ExclusiveDuration() const;
```

### <a name="return-value"></a>Dönüş Değeri

Etkinliğin nanosaniye cinsinden süresi, alt etkinliklerde harcanan süre dahil değildir.

## <a name="exclusive-duration-ticks"></a>ExclusiveDurationTicks

```cpp
const long long& ExclusiveDurationTicks() const;
```

### <a name="return-value"></a>Dönüş Değeri

Alt etkinliklerde gerçekleşen onay işareti sayısı hariç, bu etkinlikte gerçekleşen onay işareti sayısı.

## <a name="exclusive-wall-clock-time-responsibility"></a>Exclusiveduvar Clocktimeresponbili

```cpp
std::chrono::nanoseconds ExclusiveWallClockTimeResponsibility() const;
```

### <a name="return-value"></a>Dönüş Değeri

Duvarsaatiyle [Timeesponbilili](#wall-clock-time-responsibility)ile aynıdır, ancak alt etkinliklerin duvar saati zaman sorumluluğunu dahil etmez.

## <a name="exclusive-wall-clock-time-responsibility-ticks"></a>Exclusiveduvar Clocktimeresponsibilityticks

```cpp
const long long& ExclusiveWallClockTimeResponsibilityTicks() const;
```

### <a name="return-value"></a>Dönüş Değeri

Çocuk etkinliklerinin duvar saati zaman sorumluluğu işaretlerini dahil değil, [Duvarclocktimeresponsibilityticks](#wall-clock-time-responsibility-ticks)ile aynıdır.

## <a name="start-timestamp"></a>StartTimestamp

```cpp
const long long& StartTimestamp() const;
```

### <a name="return-value"></a>Dönüş Değeri

Etkinlik başlatıldığı sırada yakalanan bir değer çizgisi.

## <a name="stop-timestamp"></a>StopTimestamp

```cpp
const long long& StopTimestamp() const;
```

### <a name="return-value"></a>Dönüş Değeri

Etkinliğin durdurulduğu zamanda yakalanan bir değer çizgisi.

## <a name="wall-clock-time-responsibility"></a>Duvar Clocktimeresponbili

```cpp
std::chrono::nanoseconds WallClockTimeResponsibility() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu etkinliğin, nanosaniye cinsinden duvar saati zaman sorumluluğu. Duvar saati zaman sorumluluğunun anlamı hakkında daha fazla bilgi için bkz. [duvar Clocktimeresponsibilityticks](#wall-clock-time-responsibility-ticks).

## <a name="wall-clock-time-responsibility-ticks"></a>Duvar Clocktimeresponsibilityticks

```cpp
const long long& WallClockTimeResponsibilityTicks() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu etkinliğin genel duvar saati saatine katkısı temsil eden bir değer sayısı. Bir duvar saati zaman sorumluluğu çentik, düzenli bir Tick 'ten farklıdır. Duvar saati zaman sorumluluk işaretleri, etkinlikler arasında paralellik hesaba sahiptir. İki paralel Etkinliğin süresi 50 saat ve aynı başlangıç ve bitiş zamanı olabilir. Bu durumda, her ikisine de 25 saat için bir duvar saati saati sorumluluğu atanır.

::: moniker-end
