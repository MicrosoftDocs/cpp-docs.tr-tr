---
title: RawEvent sınıfı
description: C++ Build Insights SDK 'Sı RawEvent sınıfı başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- RawEvent
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 1cf96e1b8eadaf1de9fe2cf565a993f3bcafe358
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2020
ms.locfileid: "92920469"
---
# <a name="rawevent-class"></a>RawEvent sınıfı

::: moniker range="<=msvc-140"

C++ Build Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio **Sürüm** Seçicisi denetimini visual Studio 2017 veya visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=msvc-150"

`RawEvent`Sınıfı, bir [eventstack](event-stack.md)içinde genel bir olayı göstermek için kullanılır.

## <a name="syntax"></a>Syntax

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

Sınıftaki birçok üye işlevi `RawEvent` bir değer sayısı döndürür. C++ derleme öngörüleri, Windows 'un performans sayacını bir ölçü kaynakları olarak kullanır. Değer sayısı, saniye gibi bir zaman birimine dönüştürmek için bir değer sıklığı ile birlikte kullanılmalıdır. `TickFrequency`Değer sıklığı elde etmek için üye işlevi çağrılabilir. Tick 'lerin zaman birimine nasıl dönüştürüleceği hakkında bir örnek için [EVENT_DATA](../c-event-data-types/event-data-struct.md#tick-conversion-example) sayfasına bakın.

İşaretleri kendiniz dönüştürmek istemiyorsanız, `RawEvent` sınıfı nanosaniye cinsinden zaman değerlerini döndüren üye işlevleri sağlar. `chrono`Nanosaniye 'yi diğer zaman birimlerine dönüştürmek için standart C++ kitaplığını kullanın.

## <a name="members"></a>Üyeler

### <a name="constructor"></a>Oluşturucu

[RawEvent](#raw-event)

### <a name="functions"></a>İşlevler

[CPUTicks](#cpu-ticks)\
[CPUTime](#cpu-time)\
[Verileri](#data)\
[Sürenin](#duration)\
[EventID](#event-id) 
 [Eventınstanceıd](#event-instance-id) 
 [EventName](#event-name)\
[EventWideName](#event-wide-name)\
[ExclusiveCPUTicks](#exclusive-cpu-ticks)\
[ExclusiveCPUTime](#exclusive-cpu-time)\
[ExclusiveDuration](#exclusive-duration)\
[ExclusiveDurationTicks](#exclusive-duration-ticks)\
[Exclusiveduvar Clocktimeresponbili](#exclusive-wall-clock-time-responsibility)\
[Exclusiveduvar Clocktimeresponsibilityticks](#exclusive-wall-clock-time-responsibility-ticks)\
[Işlem](#process-id)\
[Processorındex](#processor-index)\
[StartTimestamp](#start-timestamp)\
[StopTimestamp](#stop-timestamp)\
[ThreadID](#thread-id)\
[TickFrequency](#tick-frequency)\
[Duvar Clocktimeresponbili](#wall-clock-time-responsibility)\
[Duvar Clocktimeresponsibilityticks](#wall-clock-time-responsibility-ticks)

## <a name="rawevent"></a><a name="raw-event"></a> RawEvent

```cpp
RawEvent(const EVENT_DATA& data);
```

### <a name="parameters"></a>Parametreler

*olay*\
Olay verileri.

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

## <a name="data"></a><a name="data"></a> Verileri

```cpp
const void* Data() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu olayda bulunan ek verilere yönelik bir işaretçi. Bu alanı yorumlama hakkında daha fazla bilgi için bkz. [EVENT_DATA](../c-event-data-types/event-data-struct.md).

## <a name="duration"></a><a name="duration"></a> Sürenin

```cpp
std::chrono::nanoseconds Duration() const;
```

### <a name="return-value"></a>Dönüş Değeri

Etkinliğin nanosaniye cinsinden süresi.

## <a name="eventid"></a><a name="event-id"></a> Even

```cpp
const unsigned short& EventId() const;
```

### <a name="return-value"></a>Dönüş Değeri

Olay türünü tanımlayan bir sayı. Olay tanımlayıcılarının listesi için bkz. [EVENT_ID](../c-event-data-types/event-id-enum.md).

## <a name="eventinstanceid"></a><a name="event-instance-id"></a> Eventınstanceıd

```cpp
const unsigned long long& EventInstanceId() const;
```

### <a name="return-value"></a>Dönüş Değeri

Olayı bir izleme içinde benzersiz bir şekilde tanımlayan bir sayı. Bu değer, aynı izlemeyi birden çok kez analiz veya yeniden günlüğe kaydetme sırasında değişmez. Aynı olayı birden çok çözümlemede veya yeniden günlüğe kaydetmenin aynı izleme üzerinden tanımlamak için bu değeri kullanın.

## <a name="eventname"></a><a name="event-name"></a> EventName

```cpp
const char* EventName() const;
```

### <a name="return-value"></a>Dönüş Değeri

[EventID](#event-id)tarafından tanımlanan olay türünün adını IÇEREN bir ANSI dizesi.

## <a name="eventwidename"></a><a name="event-wide-name"></a> EventWideName

```cpp
const wchar_t* EventWideName() const;
```

### <a name="return-value"></a>Dönüş Değeri

[EventID](#event-id)tarafından tanımlanan olay türünün adını içeren geniş bir dize.

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

## <a name="processid"></a><a name="process-id"></a> Işlem

```cpp
const unsigned long& ProcessId() const;
```

### <a name="return-value"></a>Dönüş Değeri

Olayın gerçekleştiği işlemin tanımlayıcısı.

## <a name="processorindex"></a><a name="processor-index"></a> Processorındex

```cpp
const unsigned short& ProcessorIndex() const;
```

### <a name="return-value"></a>Dönüş Değeri

Olayın gerçekleştiği mantıksal işlemcinin sıfır tabanlı dizini.

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

## <a name="threadid"></a><a name="thread-id"></a> ThreadID

```cpp
const unsigned long& ThreadId() const;
```

### <a name="return-value"></a>Dönüş Değeri

Olayın gerçekleştiği iş parçacığının tanımlayıcısı.

## <a name="tickfrequency"></a><a name="tick-frequency"></a> TickFrequency

```cpp
const long long& TickFrequency() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu olay için zaman işaretleri cinsinden ölçülen bir süre değerlendirilirken kullanılacak saniye başına saat sayısı.

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
