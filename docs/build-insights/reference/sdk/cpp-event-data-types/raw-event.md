---
title: RawEvent sınıfı
description: C++ Build Insights SDK RawEvent sınıf başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- RawEvent
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 83629457ac3a0d1f991f6b084af2f3400612b2ac
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81324378"
---
# <a name="rawevent-class"></a>RawEvent sınıfı

::: moniker range="<=vs-2015"

C++ Build Insights SDK, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlere ait belgeleri görmek için, bu makalenin Visual Studio **Sürüm** seçici denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=vs-2017"

Sınıf, `RawEvent` [Bir EventStack'teki](event-stack.md)genel bir olayı temsil etmek için kullanılır.

## <a name="syntax"></a>Sözdizimi

```cpp
class RawEvent
{
public:
    RawEvent(const EVENT_DATA& event);

    const unsigned short&        EventId() const;
    const unsigned long long&    EventInstanceId() const;
    const long long&             TickFrequency() const;
    const long long&             StartTimestamp() const;
    const long long&             StopTimestamp() const;
    const long long&             ExclusiveDurationTicks() const;
    const long long&             CPUTicks() const;
    const long long&             ExclusiveCPUTicks() const;
    const long long&             WallClockTimeResponsibilityTicks() const;
    const long long&             ExclusiveWallClockTimeResponsibilityTicks() const;
    const void*                  Data() const;
    const unsigned long&         ProcessId() const;
    const unsigned long&         ThreadId() const;
    const unsigned short&        ProcessorIndex() const;
    const char*                  EventName() const;
    const wchar_t*               EventWideName() const;

    std::chrono::nanoseconds Duration() const;
    std::chrono::nanoseconds ExclusiveDuration() const;
    std::chrono::nanoseconds CPUTime() const ;
    std::chrono::nanoseconds ExclusiveCPUTime() const;
    std::chrono::nanoseconds WallClockTimeResponsibility() const;
    std::chrono::nanoseconds ExclusiveWallClockTimeResponsibility() const;
};
```

## <a name="remarks"></a>Açıklamalar

Sınıftaki `RawEvent` birkaç üye işlev kene sayısını döndürer. C++ Build Insights, Windows'un performans sayacını onay kaynağı olarak kullanır. Kene sayısı, saniye gibi bir zaman birimine dönüştürmek için kene sıklığı ile kullanılmalıdır. Onay `TickFrequency` frekansını elde etmek için üye işlev çağrılabilir. Kenelerin zaman birimine nasıl dönüştürüldüğünü anlatan bir örnek için [EVENT_DATA](../c-event-data-types/event-data-struct.md#tick-conversion-example) sayfasına bakın.

Keneleri kendiniz dönüştürmek istemiyorsanız, `RawEvent` sınıf zaman değerlerini nanosaniye cinsinden döndüren üye işlevler sağlar. Nanosaniyeleri diğer `chrono` zaman birimlerine dönüştürmek için standart C++ kitaplığını kullanın.

## <a name="members"></a>Üyeler

### <a name="constructor"></a>Oluşturucu

[RawEvent](#raw-event)

### <a name="functions"></a>İşlevler

[CPUTicks](#cpu-ticks)\
[CPUTime](#cpu-time)\
[Veri](#data)\
[Süre](#duration)\
[EventId](#event-id)
[EventInstanceId](#event-instance-id)
[EventName](#event-name)\
[EventWideName](#event-wide-name)\
[ExclusiveCPUTicks](#exclusive-cpu-ticks)\
[ExclusiveCPUTime](#exclusive-cpu-time)\
[ÖzelSüre](#exclusive-duration)\
[ExclusiveDurationTicks](#exclusive-duration-ticks)\
[ExclusiveWallClockTimeResponsibility](#exclusive-wall-clock-time-responsibility)\
[ExclusiveWallClockTimeResponsibilityTicks](#exclusive-wall-clock-time-responsibility-ticks)\
[Processıd](#process-id)\
[İşleme Dizini](#processor-index)\
[Başlangıç Zamanı Damgası](#start-timestamp)\
[StopTimestamp](#stop-timestamp)\
[Threadıd](#thread-id)\
[Tickfrequency](#tick-frequency)\
[WallClockTimeResponsibility](#wall-clock-time-responsibility)\
[WallClockTimeResponsibilityTicks](#wall-clock-time-responsibility-ticks)

## <a name="rawevent"></a><a name="raw-event"></a>RawEvent

```cpp
RawEvent(const EVENT_DATA& data);
```

### <a name="parameters"></a>Parametreler

*Olay*\
Olay verileri.

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

## <a name="data"></a><a name="data"></a>Veri

```cpp
const void* Data() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu olayda bulunan ek veri için bir işaretçi. Bu alanın nasıl yorumlanacağı hakkında daha fazla bilgi için [EVENT_DATA.](../c-event-data-types/event-data-struct.md)

## <a name="duration"></a><a name="duration"></a>Süre

```cpp
std::chrono::nanoseconds Duration() const;
```

### <a name="return-value"></a>Dönüş Değeri

Nanosaniye cinsinden etkinliğin süresi.

## <a name="eventid"></a><a name="event-id"></a>Eventıd

```cpp
const unsigned short& EventId() const;
```

### <a name="return-value"></a>Dönüş Değeri

Olay türünü tanımlayan bir sayı. Olay tanımlayıcılarının listesi için [bkz. EVENT_ID.](../c-event-data-types/event-id-enum.md)

## <a name="eventinstanceid"></a><a name="event-instance-id"></a>EventInstanceId

```cpp
const unsigned long long& EventInstanceId() const;
```

### <a name="return-value"></a>Dönüş Değeri

İziçindeki olayı benzersiz olarak tanımlayan bir sayı. Aynı izlemeyi birden çok kez analiz ederken veya yeniden günlüğe kaydederken bu değer değişmez. Aynı olayı birden çok çözümlemede veya aynı izleme üzerinde yeniden günlüğe kaydetme geçişlerinde tanımlamak için bu değeri kullanın.

## <a name="eventname"></a><a name="event-name"></a>Olay Adı

```cpp
const char* EventName() const;
```

### <a name="return-value"></a>Dönüş Değeri

[EventId](#event-id)tarafından tanımlanan olay türünün adını içeren bir ANSI dizesi.

## <a name="eventwidename"></a><a name="event-wide-name"></a>EventWideName

```cpp
const wchar_t* EventWideName() const;
```

### <a name="return-value"></a>Dönüş Değeri

[EventId](#event-id)tarafından tanımlanan olay türünün adını içeren geniş bir dize.

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

## <a name="processid"></a><a name="process-id"></a>Processıd

```cpp
const unsigned long& ProcessId() const;
```

### <a name="return-value"></a>Dönüş Değeri

Olayın oluştuğu işlemin tanımlayıcısı.

## <a name="processorindex"></a><a name="processor-index"></a>İşleme Dizini

```cpp
const unsigned short& ProcessorIndex() const;
```

### <a name="return-value"></a>Dönüş Değeri

Olayın oluştuğu mantıksal işlemcinin sıfır tabanlı dizini.

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

## <a name="threadid"></a><a name="thread-id"></a>Threadıd

```cpp
const unsigned long& ThreadId() const;
```

### <a name="return-value"></a>Dönüş Değeri

Olayın oluştuğu iş parçacığı için tanımlayıcı.

## <a name="tickfrequency"></a><a name="tick-frequency"></a>Tickfrequency

```cpp
const long long& TickFrequency() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu olay için kene cinsinden ölçülen bir süreyi değerlendirirken kullanılacak saniye başına keneler sayısı.

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
